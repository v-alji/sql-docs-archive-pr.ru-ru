---
title: Создание каталога служб SSIS | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6ed56d36-18d9-40c2-b51f-f2a4c71d1e73
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2572cc131f34a21171054a159e3b7968c453a780
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656497"
---
# <a name="create-the-ssis-catalog"></a><span data-ttu-id="3e199-102">Создание каталога служб SSIS</span><span class="sxs-lookup"><span data-stu-id="3e199-102">Create the SSIS Catalog</span></span>
  <span data-ttu-id="3e199-103">После разработки и тестирования пакетов в [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]можно выполнить развертывание проектов, содержащих пакеты, на сервере [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e199-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="3e199-104">Прежде чем развертывать проекты на сервере служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], необходимо создать каталог `SSISDB` на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="3e199-104">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the server must contain the `SSISDB` catalog.</span></span> <span data-ttu-id="3e199-105">Программа установки [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] не создает этот каталог автоматически. Его необходимо создать вручную, следуя приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="3e199-105">The installation program for [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] does not automatically create the catalog; you need to manually create the catalog by using the following instructions.</span></span>  
  
 <span data-ttu-id="3e199-106">Вы можете создать каталог SSISDB в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e199-106">You can create the SSISDB catalog in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="3e199-107">Можно также создать каталог программным способом с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e199-107">You also create the catalog programmatically by using Windows PowerShell.</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-in-sql-server-management-studio"></a><span data-ttu-id="3e199-108">Создание каталога SSISDB в SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e199-108">To create the SSISDB catalog in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="3e199-109">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e199-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="3e199-110">Соединитесь с ядром СУБД [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e199-110">Connect to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Database Engine.</span></span>  
  
3.  <span data-ttu-id="3e199-111">В обозревателе объектов разверните узел сервера, щелкните правой кнопкой мыши узел **Каталоги служб Integration Services** и выберите пункт **Создать каталог**.</span><span class="sxs-lookup"><span data-stu-id="3e199-111">In Object Explorer, expand the server node, right-click the **Integration Services Catalogs** node, and then click **Create Catalog**.</span></span>  
  
4.  <span data-ttu-id="3e199-112">Установите флажок **Включить интеграцию со средой CLR**.</span><span class="sxs-lookup"><span data-stu-id="3e199-112">Click **Enable CLR Integration**.</span></span>  
  
     <span data-ttu-id="3e199-113">Каталог использует хранимые процедуры CLR.</span><span class="sxs-lookup"><span data-stu-id="3e199-113">The catalog uses CLR stored procedures.</span></span>  
  
5.  <span data-ttu-id="3e199-114">Щелкните **Включить автоматическое выполнение хранимой процедуры служб Integration Services при запуске SQL Server** , чтобы хранимая процедура [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) выполнялась каждый раз при перезапуске экземпляра сервера служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e199-114">Click **Enable automatic execution of Integration Services stored procedure at SQL Server startup** to enable the [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) stored procedure to run each time the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance is restarted.</span></span>  
  
     <span data-ttu-id="3e199-115">Хранимая процедура осуществляет обслуживание состояния операций для каталога SSISDB.</span><span class="sxs-lookup"><span data-stu-id="3e199-115">The stored procedure performs maintenance of the state of operations for the SSISDB catalog.</span></span> <span data-ttu-id="3e199-116">Она исправляет состояние любых пакетов, выполнявшихся в момент отключения экземпляра сервера служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e199-116">It fixes the status of any packages there were running if and when the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance goes down.</span></span>  
  
6.  <span data-ttu-id="3e199-117">Введите пароль и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3e199-117">Enter a password, and then click **Ok**.</span></span>  
  
     <span data-ttu-id="3e199-118">Этот пароль защищает главный ключ базы данных, используемый для шифрования данных каталога.</span><span class="sxs-lookup"><span data-stu-id="3e199-118">The password protects the database master key that is used for encrypting the catalog data.</span></span> <span data-ttu-id="3e199-119">Сохраните пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="3e199-119">Save the password in a secure location.</span></span> <span data-ttu-id="3e199-120">Рекомендуется также создать резервную копию главного ключа базы данных.</span><span class="sxs-lookup"><span data-stu-id="3e199-120">It is recommended that you also back up the database master key.</span></span> <span data-ttu-id="3e199-121">Дополнительные сведения см. в статье [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="3e199-121">For more information, see [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-programmatically"></a><span data-ttu-id="3e199-122">Создание каталога SSISDB программным способом</span><span class="sxs-lookup"><span data-stu-id="3e199-122">To create the SSISDB catalog programmatically</span></span>  
  
1.  <span data-ttu-id="3e199-123">Выполните следующий скрипт PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e199-123">Execute the following PowerShell script:</span></span>  
  
    ```powershell
    # Load the IntegrationServices Assembly  
    [Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Management.IntegrationServices")  
  
    # Store the IntegrationServices Assembly namespace to avoid typing it every time  
    $ISNamespace = "Microsoft.SqlServer.Management.IntegrationServices"  
  
    Write-Host "Connecting to server ..."  
  
    # Create a connection to the server  
    $sqlConnectionString = "Data Source=localhost;Initial Catalog=master;Integrated Security=SSPI;"  
    $sqlConnection = New-Object System.Data.SqlClient.SqlConnection $sqlConnectionString  
  
    # Create the Integration Services object  
    $integrationServices = New-Object $ISNamespace".IntegrationServices" $sqlConnection  
  
    # Provision a new SSIS Catalog  
    $catalog = New-Object $ISNamespace".Catalog" ($integrationServices, "SSISDB", "P@assword1")  
    $catalog.Create()
    ```  
  
     <span data-ttu-id="3e199-124">Дополнительные примеры использования Windows PowerShell и пространства имен <xref:Microsoft.SqlServer.Management.IntegrationServices> см. в записи блога [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539) (Службы SSIS и PowerShell в SQL Server 2012) на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="3e199-124">For more examples of how to use Windows PowerShell and the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace, see the blog entry, [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539), on blogs.msdn.com.</span></span> <span data-ttu-id="3e199-125">Общие сведения о пространстве имен и примеры кода см. в записи блога [Обзор модели управляемых объектов каталога служб SSIS](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892)на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="3e199-125">For an overview of the namespace and code examples, see the blog entry, [A Glimpse of the SSIS Catalog Managed Object Model](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e199-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e199-126">See Also</span></span>  
 <span data-ttu-id="3e199-127">[Каталог служб SSIS](catalog/ssis-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="3e199-127">[SSIS Catalog](catalog/ssis-catalog.md) </span></span>  
 [<span data-ttu-id="3e199-128">Резервное копирование, восстановление и перемещение каталога служб SSIS</span><span class="sxs-lookup"><span data-stu-id="3e199-128">Backup, Restore, and Move the SSIS Catalog</span></span>](../../2014/integration-services/backup-restore-and-move-the-ssis-catalog.md)  
