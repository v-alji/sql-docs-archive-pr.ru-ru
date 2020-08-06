---
title: Развертывание и выполнение пакетов служб SSIS с помощью хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 60914b0c-1f65-45f8-8132-0ca331749fcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1570207dca6e944b54c553a1d83256d8f4fa3244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740166"
---
# <a name="deploy-and-execute-ssis-packages-using-stored-procedures"></a><span data-ttu-id="584d5-102">Развертывание и выполнение пакетов служб SSIS с помощью хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="584d5-102">Deploy and Execute SSIS Packages using Stored Procedures</span></span>
  <span data-ttu-id="584d5-103">После настройки проекта [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] для использования модели развертывания проекта можно вызывать хранимые процедуры в каталоге служб [!INCLUDE[ssIS](../includes/ssis-md.md)] , чтобы развернуть проект и выполнить пакеты.</span><span class="sxs-lookup"><span data-stu-id="584d5-103">When you configure an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to use the project deployment model, you can use stored procedures in the [!INCLUDE[ssIS](../includes/ssis-md.md)] catalog to deploy the project and execute the packages.</span></span> <span data-ttu-id="584d5-104">Дополнительные сведения о модели развертывания проектов см. в разделе [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="584d5-104">For information about the project deployment model, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="584d5-105">Для развертывания и выполнения пакетов также можно использовать среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] или [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="584d5-105">You can also use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to deploy the project and execute the packages.</span></span> <span data-ttu-id="584d5-106">Дополнительные сведения см. в разделе **См. также** .</span><span class="sxs-lookup"><span data-stu-id="584d5-106">For more information, see the topics in the **See Also** section.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="584d5-107">Не составит труда создать инструкции Transact-SQL для хранимых процедур, перечисленных в следующей процедуре, за исключением catalog.deploy_project, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="584d5-107">You can easily generate the Transact-SQL statements for the stored procedures listed in the procedure below, with the exception of catalog.deploy_project, by doing the following:</span></span>  
> 
>  1.  <span data-ttu-id="584d5-108">В [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]разверните узел **Каталоги служб Integration Services** в обозревателе объектов и перейдите к пакету, который нужно выполнить.</span><span class="sxs-lookup"><span data-stu-id="584d5-108">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** node in Object Explorer and navigate to the package you want to execute.</span></span>  
> 2.  <span data-ttu-id="584d5-109">Щелкните правой кнопкой мыши пакет и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="584d5-109">Right-click the package, and then click **Execute**.</span></span>  
> 3.  <span data-ttu-id="584d5-110">При необходимости задайте значения параметров, свойства диспетчера соединений и параметры на вкладке **Дополнительно** , например уровень ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="584d5-110">As needed, set parameters values, connection manager properties, and options in the **Advanced** tab such as the logging level.</span></span>  
> 
>      <span data-ttu-id="584d5-111">Дополнительные сведения об уровнях ведения журнала см. в разделе [Включение ведения журналов при выполнении пакета на сервере служб SSIS](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span><span class="sxs-lookup"><span data-stu-id="584d5-111">For more information about logging levels, see [Enable Logging for Package Execution on the SSIS Server](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span></span>  
> 4.  <span data-ttu-id="584d5-112">Перед нажатием кнопки **ОК** для выполнения пакета выберите пункт **Скрипт**.</span><span class="sxs-lookup"><span data-stu-id="584d5-112">Before clicking **OK** to execute the package, click **Script**.</span></span> <span data-ttu-id="584d5-113">Код Transact-SQL откроется в окне редактора запросов среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="584d5-113">The Transact-SQL appears in a Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="to-deploy-and-execute-a-package-using-stored-procedures"></a><span data-ttu-id="584d5-114">Развертывание и выполнение пакета с помощью хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="584d5-114">To deploy and execute a package using stored procedures</span></span>  
  
1.  <span data-ttu-id="584d5-115">Вызовите [catalog.deploy_project (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database), чтобы развернуть проект [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], который содержит пакет, на сервере [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="584d5-115">Call [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) to deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="584d5-116">Чтобы получить двоичное содержимое [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] файла развертывания проекта, для параметра \* \@ project_stream\* используйте инструкцию SELECT с функцией OPENROWSET и поставщиком больших наборов строк.</span><span class="sxs-lookup"><span data-stu-id="584d5-116">To retrieve the binary contents of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project deployment file, for the *\@project_stream* parameter, use a SELECT statement with the OPENROWSET function and the BULK rowset provider.</span></span> <span data-ttu-id="584d5-117">Поставщик больших наборов строк позволяет считывать данные из файла.</span><span class="sxs-lookup"><span data-stu-id="584d5-117">The BULK rowset provider enables you to read data from a file.</span></span> <span data-ttu-id="584d5-118">Аргумент SINGLE_BLOB для поставщика больших наборов строк возвращает содержимое файла данных в виде набора строк с одной строкой и одним столбцом типа varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="584d5-118">The SINGLE_BLOB argument for the BULK rowset provider returns the contents of the data file as a single-row, single-column rowset of type varbinary(max).</span></span> <span data-ttu-id="584d5-119">Дополнительные сведения см. в разделе [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="584d5-119">For more information, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
     <span data-ttu-id="584d5-120">В следующем примере проект SSISPackages_ProjectDeployment будет развернут в папке SSIS Packages на сервере [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="584d5-120">In the following example, the SSISPackages_ProjectDeployment project is deployed to the SSIS Packages folder on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="584d5-121">Двоичные данные считываются из файла проекта (SSISPackage_ProjectDeployment. ISPAC) и хранятся в параметре \* \@ прожектбинари\* типа varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="584d5-121">The binary data is read from the project file (SSISPackage_ProjectDeployment.ispac) and is stored in the *\@ProjectBinary* parameter of type varbinary(max).</span></span> <span data-ttu-id="584d5-122">Значение параметра \* \@ прожектбинари\* присваивается параметру \* \@ project_stream\* .</span><span class="sxs-lookup"><span data-stu-id="584d5-122">The *\@ProjectBinary* parameter value is assigned to the *\@project_stream* parameter.</span></span>  
  
    ```  
    DECLARE @ProjectBinary as varbinary(max)  
    DECLARE @operation_id as bigint  
    Set @ProjectBinary = (SELECT * FROM OPENROWSET(BULK 'C:\MyProjects\ SSISPackage_ProjectDeployment.ispac', SINGLE_BLOB) as BinaryData)  
  
    Exec catalog.deploy_project @folder_name = 'SSIS Packages', @project_name = 'DeployViaStoredProc_SSIS', @Project_Stream = @ProjectBinary, @operation_id = @operation_id out  
  
    ```  
  
2.  <span data-ttu-id="584d5-123">Вызовите функцию[catalog.create_execution (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), чтобы создать экземпляр выполнения пакета, и при необходимости вызовите функцию [catalog.set_execution_parameter_value (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database), чтобы задать значения параметров среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="584d5-123">Call [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) to create an instance of the package execution, and optionally call [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) to set runtime parameter values.</span></span>  
  
     <span data-ttu-id="584d5-124">В следующем примере catalog.create_execution создает экземпляр для выполнения package.dtsx, содержащегося в проекте SSISPackage_ProjectDeployment.</span><span class="sxs-lookup"><span data-stu-id="584d5-124">In the following example, catalog.create_execution creates an instance of execution for package.dtsx that is contained in the SSISPackage_ProjectDeployment project.</span></span> <span data-ttu-id="584d5-125">Проект располагается в папке SSIS Packages.</span><span class="sxs-lookup"><span data-stu-id="584d5-125">The project is located in the SSIS Packages folder.</span></span> <span data-ttu-id="584d5-126">Значение execution_id, возвращаемое хранимой процедурой, используется для вызова функции catalog.set_execution_parameter_value.</span><span class="sxs-lookup"><span data-stu-id="584d5-126">The execution_id returned by the stored procedure is used in the call to catalog.set_execution_parameter_value.</span></span> <span data-ttu-id="584d5-127">Эта вторая хранимая процедура устанавливает параметр LOGGING_LEVEL равным 3 (подробный уровень ведения журнала) и задает параметру пакета Parameter1 значение 1.</span><span class="sxs-lookup"><span data-stu-id="584d5-127">This second stored procedure sets the LOGGING_LEVEL parameter to 3 (verbose logging) and sets a package parameter named Parameter1 to a value of 1.</span></span>  
  
     <span data-ttu-id="584d5-128">Для таких параметров, как LOGGING_LEVEL, значение object_type равно 50.</span><span class="sxs-lookup"><span data-stu-id="584d5-128">For parameters such as LOGGING_LEVEL the object_type value is 50.</span></span> <span data-ttu-id="584d5-129">Для параметров пакета значение object_type равно 30.</span><span class="sxs-lookup"><span data-stu-id="584d5-129">For package parameters the object_type value is 30.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    GO  
  
    ```  
  
3.  <span data-ttu-id="584d5-130">Вызовите функцию [catalog.start_execution (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="584d5-130">Call [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) to execute the package.</span></span>  
  
     <span data-ttu-id="584d5-131">В следующем примере вызов catalog.start_execution добавляется в Transact-SQL, чтобы можно было начать выполнение пакета.</span><span class="sxs-lookup"><span data-stu-id="584d5-131">In the following example, a call to catalog.start_execution is added to the Transact-SQL to start the package execution.</span></span> <span data-ttu-id="584d5-132">Используется значение execution_id, возвращаемое хранимой процедурой catalog.create_execution.</span><span class="sxs-lookup"><span data-stu-id="584d5-132">The execution_id returned by the catalog.create_execution stored procedure is used.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    EXEC [SSISDB].[catalog].[start_execution] @execution_id  
    GO  
  
    ```  
  
## <a name="to-deploy-a-project-from-server-to-server-using-stored-procedures"></a><span data-ttu-id="584d5-133">Развертывание проекта из сервера на сервер с использованием хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="584d5-133">To deploy a project from server to server using stored procedures</span></span>  
 <span data-ttu-id="584d5-134">Проект можно развернуть из сервера на сервер с помощью хранимых процедур [catalog.get_project (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) и [catalog.deploy_project (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="584d5-134">You can deploy a project from server to server by using the [catalog.get_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) and [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) stored procedures.</span></span>  
  
 <span data-ttu-id="584d5-135">Необходимо выполнить следующие действия перед выполнением хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="584d5-135">You need to do the following before running the stored procedures.</span></span>  
  
-   <span data-ttu-id="584d5-136">Создание связанного объекта сервера.</span><span class="sxs-lookup"><span data-stu-id="584d5-136">Create a linked server object.</span></span> <span data-ttu-id="584d5-137">Дополнительные сведения см. в разделе [(Создание связанных серверов (компонент SQL Server Database Engine))](../database-engine/sql-server-database-engine-overview.md).</span><span class="sxs-lookup"><span data-stu-id="584d5-137">For more information, see [Create Linked Servers &#40;SQL Server Database Engine&#41;](../database-engine/sql-server-database-engine-overview.md).</span></span>  
  
     <span data-ttu-id="584d5-138">На странице **Параметры сервера** диалогового окна **Свойства связанного сервера** назначьте для **RPC** и **RPC Out** значения **True**.</span><span class="sxs-lookup"><span data-stu-id="584d5-138">On the **Server Options** page of the **Linked Server Properties** dialog box, set **RPC** and **RPC Out** to **True**.</span></span> <span data-ttu-id="584d5-139">Кроме того, назначьте свойству **Разрешить продвижение распределенных транзакций для RPC** значение **False**.</span><span class="sxs-lookup"><span data-stu-id="584d5-139">Also, set **Enable Promotion of Distributed Transactions for RPC** to **False**.</span></span>  
  
-   <span data-ttu-id="584d5-140">Включите динамические параметры для поставщика, выбранного для связанного сервера, разверните узел **Поставщики** и выберите **Связанные серверы** в обозревателе объектов, щелкните правой кнопкой мыши поставщик, затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="584d5-140">Enable dynamic parameters for the provider you selected for the linked server, by expanding the **Providers** node under **Linked Servers** in Object Explorer, right-clicking the provider, and then clicking **Properties**.</span></span> <span data-ttu-id="584d5-141">Нажмите кнопку **Включить** рядом с полем **Динамический параметр.**</span><span class="sxs-lookup"><span data-stu-id="584d5-141">Select **Enable** next to **Dynamic parameter.**</span></span>  
  
-   <span data-ttu-id="584d5-142">Убедитесь, что на обоих серверах запущен координатор распределенных транзакций (DTC).</span><span class="sxs-lookup"><span data-stu-id="584d5-142">Confirm that the Distributed Transaction Coordinator (DTC) is started on both servers.</span></span>  
  
 <span data-ttu-id="584d5-143">Вызовите catalog.get_project для получения двоичных файлов проекта, а затем вызовите catalog.deploy_project.</span><span class="sxs-lookup"><span data-stu-id="584d5-143">Call catalog.get_project to return the binary for the project, and then call catalog.deploy_project.</span></span> <span data-ttu-id="584d5-144">Значение, возвращаемое catalog.get_project, вставляется в табличную переменную типа varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="584d5-144">The value returned by catalog.get_project is inserted into a table variable of type varbinary(max).</span></span> <span data-ttu-id="584d5-145">Связанный сервер не может возвращать результаты типа varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="584d5-145">The linked server can't return results that are varbinary(max).</span></span>  
  
 <span data-ttu-id="584d5-146">В следующем примере catalog.get_project возвращает двоичный результат для проекта SSISPackages на связанном сервере.</span><span class="sxs-lookup"><span data-stu-id="584d5-146">In the following example, catalog.get_project returns a binary for the SSISPackages project on the linked server.</span></span> <span data-ttu-id="584d5-147">Catalog.deploy_project развертывает проект на локальном сервере в папке с именем DestFolder.</span><span class="sxs-lookup"><span data-stu-id="584d5-147">The catalog.deploy_project deploys the project to the local server, to the folder named DestFolder.</span></span>  
  
```  
declare @resultsTableVar table (  
project_binary varbinary(max)  
)  
  
INSERT @resultsTableVar (project_binary)  
EXECUTE [MyLinkedServer].[SSISDB].[catalog].[get_project] 'Packages', 'SSISPackages'  
  
declare @project_binary varbinary(max)  
select @project_binary = project_binary from @resultsTableVar  
  
exec [SSISDB].[CATALOG].[deploy_project] 'DestFolder', 'SSISPackages', @project_binary  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="584d5-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="584d5-148">See Also</span></span>  
 <span data-ttu-id="584d5-149">[Развертывание проектов на сервере Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="584d5-149">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 <span data-ttu-id="584d5-150">[Запуск пакета в SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="584d5-150">[Run a Package in SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="584d5-151">Выполнение пакета на сервере служб SSIS с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="584d5-151">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
  
