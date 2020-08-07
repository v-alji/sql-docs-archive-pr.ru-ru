---
title: Отвода потока данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2d847adf-4b3d-4949-a195-ef43de275077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053b34add45354d0df71fa73a72f8786cc706d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729677"
---
# <a name="data-flow-taps"></a><span data-ttu-id="96690-102">Вкладки «Поток данных»</span><span class="sxs-lookup"><span data-stu-id="96690-102">Data Flow Taps</span></span>
  <span data-ttu-id="96690-103">В [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] представлена новая функция, которая позволяет добавить отвод данных в путь потока данных пакета во время выполнения и перенаправить отвод данных во внешний файл.</span><span class="sxs-lookup"><span data-stu-id="96690-103">[!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] introduces a new feature that allows you to add a data tap on a data flow path of a package at runtime and direct the output from the data tap to an external file.</span></span> <span data-ttu-id="96690-104">Для использования этой функции следует развернуть проект служб SSIS на сервере служб SSIS с помощью модели развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="96690-104">To use this feature, you must deploy your SSIS project using the project deployment model to an SSIS Server.</span></span> <span data-ttu-id="96690-105">После развертывания пакета на сервере до выполнения пакета следует выполнить T-SQL скрипты на базе данных SSISDB, чтобы добавить отводы данных.</span><span class="sxs-lookup"><span data-stu-id="96690-105">After you deploy the package to the server, you need to execute T-SQL scripts against the SSISDB database to add data taps before executing the package.</span></span> <span data-ttu-id="96690-106">Пример сценария.</span><span class="sxs-lookup"><span data-stu-id="96690-106">Here is a sample scenario:</span></span>  
  
1.  <span data-ttu-id="96690-107">Создайте экземпляр выполнения пакета с помощью хранимой процедуры [catalog.create_execution (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="96690-107">Create an execution instance of a package by using the [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) stored procedure.</span></span>  
  
2.  <span data-ttu-id="96690-108">Добавьте отвод данных с помощью хранимой процедуры [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) или [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid).</span><span class="sxs-lookup"><span data-stu-id="96690-108">Add a data tap by using either [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) or [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) stored procedure.</span></span>  
  
3.  <span data-ttu-id="96690-109">Запустите экземпляр выполнения пакета с помощью хранимой процедуры [catalog.start_execution (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="96690-109">Start the execution instance of the package by using the [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
 <span data-ttu-id="96690-110">Пример SQL-скрипта, реализующий шаги, описанные выше.</span><span class="sxs-lookup"><span data-stu-id="96690-110">Here is a sample SQL script that performs the steps described in the above scenario:</span></span>  
  
```  
  
Declare @execid bigint  
EXEC [SSISDB].[catalog].[create_execution] @folder_name=N'ETL Folder', @project_name=N'ETL Project', @package_name=N'Package.dtsx', @execution_id=@execid OUTPUT  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt'  
EXEC [SSISDB].[catalog].[start_execution] @execid  
  
```  
  
 <span data-ttu-id="96690-111">Параметры имен папки, проекта и пакета хранимой процедуры create_execution соответствуют именам папки, проекта и пакета в каталоге служб Integration Services.</span><span class="sxs-lookup"><span data-stu-id="96690-111">The folder name, project name, and package name parameters of the create_execution stored procedure correspond to the folder, project, and package names in the Integration Services catalog.</span></span> <span data-ttu-id="96690-112">Эти имена для вызова процедуры create_execution можно получить в среде SQL Server Management Studio, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="96690-112">You can get the folder, project, and package names to use in the create_execution call from the SQL Server Management Studio as shown in the following image.</span></span> <span data-ttu-id="96690-113">Если вашего проекта служб SSIS здесь нет, возможно, вы еще не развернули проект на сервер служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="96690-113">If you do not see your SSIS project here, you may not have deployed the project to SSIS server yet.</span></span> <span data-ttu-id="96690-114">Щелкните правой кнопкой мыши по проекту служб SSIS в Visual Studio и выберите команду «Развернуть», чтобы развернуть проект на нужный сервер служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="96690-114">Right-click on SSIS project in Visual Studio and click Deploy to deploy the project to the expected SSIS server.</span></span>  
  
 <span data-ttu-id="96690-115">Вместо ввода инструкций SQL можно сформировать скрипт выполнения пакета, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="96690-115">Instead of typing the SQL statements, you can generate the execute package script by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="96690-116">Щелкните правой кнопкой мыши **Package.dtsx** и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="96690-116">Right-click **Package.dtsx** and click **Execute**.</span></span>  
  
2.  <span data-ttu-id="96690-117">Нажмите кнопку **Скрипт** на панели инструментов, чтобы сформировать скрипт.</span><span class="sxs-lookup"><span data-stu-id="96690-117">Click **Script** toolbar button to generate the script.</span></span>  
  
3.  <span data-ttu-id="96690-118">Теперь добавьте инструкцию add_data_tap до вызова start_execution.</span><span class="sxs-lookup"><span data-stu-id="96690-118">Now, add the add_data_tap statement before the start_execution call.</span></span>  
  
 <span data-ttu-id="96690-119">Параметр task_package_path хранимой процедуры add_data_tap соответствует свойству PackagePath задачи потока данных в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96690-119">The task_package_path parameter of add_data_tap stored procedure corresponds to the PackagePath property of the data flow task in Visual Studio.</span></span> <span data-ttu-id="96690-120">В Visual Studio щелкните правой кнопкой мыши **Задача потока данных**, а затем выберите **Свойства** . Откроется окно свойств.</span><span class="sxs-lookup"><span data-stu-id="96690-120">In Visual Studio, right-click the **Data Flow Task**, and click **Properties** to launch the Properties window.</span></span>  <span data-ttu-id="96690-121">Значение свойства **PackagePath** используйте в качестве значения для параметра task_package_path при вызове хранимой процедуры add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="96690-121">Note the value of the **PackagePath** property to use it as a value for the task_package_path parameter for add_data_tap stored procedure call.</span></span>  
  
 <span data-ttu-id="96690-122">Параметр dataflow_path_id_string хранимой процедуры add_data_tap соответствует свойству IdentificationString задания пути потока данных, к которому следует добавить отвод данных.</span><span class="sxs-lookup"><span data-stu-id="96690-122">The dataflow_path_id_string  parameter of add_data_tap stored procedure corresponds to the IdentificationString property of the data flow path to which you want to add a data tap.</span></span> <span data-ttu-id="96690-123">Чтобы получить dataflow_path_id_string, щелкните по пути потока данных (стрелка между задачами в потоке данных) и отметьте значение свойства **IdentificationString** в окне свойств.</span><span class="sxs-lookup"><span data-stu-id="96690-123">To get the dataflow_path_id_string, click the data flow path (arrow between tasks in the data flow), and note the value of the **IdentificationString** property in the Properties window.</span></span>  
  
 <span data-ttu-id="96690-124">При выполнении скрипта выходной файл сохраняется в папке \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span><span class="sxs-lookup"><span data-stu-id="96690-124">When you execute the script, the output file is stored in \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span></span> <span data-ttu-id="96690-125">Если уже существует файл с таким именем, будет создан новый файл с суффиксом (например, output[1].txt).</span><span class="sxs-lookup"><span data-stu-id="96690-125">If a file with the name already exists, a new file with a suffix (for example: output[1].txt)  is created.</span></span>  
  
 <span data-ttu-id="96690-126">Как упоминалось ранее, также вместо использования хранимой процедуры add_data_tap можно применить хранимую процедуру [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid).</span><span class="sxs-lookup"><span data-stu-id="96690-126">As mentioned earlier, you can also use [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)stored procedure instead of using add_data_tap stored procedure.</span></span> <span data-ttu-id="96690-127">Эта хранимая процедура принимает в качестве параметра идентификатор задачи потока данных вместо task_package_path.</span><span class="sxs-lookup"><span data-stu-id="96690-127">This stored procedure takes the ID of data flow task as a parameter instead of task_package_path.</span></span> <span data-ttu-id="96690-128">Идентификатор этой задачи потока данных можно узнать в окне «Свойства» среды Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96690-128">You can get the ID of data flow task from the properties window in Visual Studio.</span></span>  
  
## <a name="removing-a-data-tap"></a><span data-ttu-id="96690-129">Удаление отвода данных</span><span class="sxs-lookup"><span data-stu-id="96690-129">Removing a data tap</span></span>  
 <span data-ttu-id="96690-130">Отвод данных можно удалить до начала выполнения, воспользовавшись хранимой процедурой [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) .</span><span class="sxs-lookup"><span data-stu-id="96690-130">You can remove a data tap before starting the execution by using the [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) stored procedure.</span></span> <span data-ttu-id="96690-131">Эта хранимая процедура принимает в качестве параметра идентификатор отвода данных, который можно получить после вызова хранимой процедуры add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="96690-131">This stored procedure takes the ID of data tap as a parameter, which you can get as an output of the add_data_tap stored procedure.</span></span>  
  
```  
  
DECLARE @tap_id bigint  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt' @data_tap_id=@tap_id OUTPUT  
EXEC [SSISDB].[catalog].remove_data_tap @tap_id  
  
```  
  
## <a name="listing-all-data-taps"></a><span data-ttu-id="96690-132">Перечисление всех отводов данных</span><span class="sxs-lookup"><span data-stu-id="96690-132">Listing all data taps</span></span>  
 <span data-ttu-id="96690-133">С помощью представления add_data_tap можно перечислить все отводы данных.</span><span class="sxs-lookup"><span data-stu-id="96690-133">You can also list all the data taps by using the catalog.execution_data_taps view.</span></span> <span data-ttu-id="96690-134">В следующем примере показано, как извлечь отводы данных для экземпляра выполнения спецификации (ID: 54).</span><span class="sxs-lookup"><span data-stu-id="96690-134">The following example extracts data taps for a specification execution instance (ID: 54).</span></span>  
  
```  
select * from [SSISDB].[catalog].execution_data_taps where execution_id=@execid  
```  
  
## <a name="performance-consideration"></a><span data-ttu-id="96690-135">Вопросы производительности</span><span class="sxs-lookup"><span data-stu-id="96690-135">Performance consideration</span></span>  
 <span data-ttu-id="96690-136">Включение подробного уровня ведения журнала и добавление отводов данных увеличивает количество операций ввода-вывода, выполняемых решением по интеграции данных.</span><span class="sxs-lookup"><span data-stu-id="96690-136">Enabling verbose logging level and adding data taps increase the I/O operations performed by your data integration solution.</span></span> <span data-ttu-id="96690-137">Поэтому рекомендуется добавлять отводы данных только для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="96690-137">Hence, we recommend that you add data taps only for troubleshooting purposes</span></span>  
  
## <a name="video"></a><span data-ttu-id="96690-138">Видеоролик</span><span class="sxs-lookup"><span data-stu-id="96690-138">Video</span></span>  
 <span data-ttu-id="96690-139">Этот [видеоролик в библиотеке TechNet](https://technet.microsoft.com/sqlserver/dn600163) демонстрирует добавление и использование отводов данных в каталоге SQL Server 2012 SSISDB для программной отладки пакетов и получения частичных результатов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="96690-139">This [video on TechNet](https://technet.microsoft.com/sqlserver/dn600163) demonstrates how to add/use data taps in SQL Server 2012 SSISDB catalog that help with debugging packages programmatically and capturing the partial results at the runtime.</span></span> <span data-ttu-id="96690-140">Также там обсуждается вопрос перечисления или удаления отводов данных и рекомендации по их применению в пакетах SSIS.</span><span class="sxs-lookup"><span data-stu-id="96690-140">It also discusses how to list/ remove these data taps and best practices for using data taps in SSIS packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="96690-141">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="96690-141">Related Tasks</span></span>  
 [<span data-ttu-id="96690-142">Отладка потока данных</span><span class="sxs-lookup"><span data-stu-id="96690-142">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="96690-143">Устранение неполадок инструментов с помощью отчетов</span><span class="sxs-lookup"><span data-stu-id="96690-143">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
  
