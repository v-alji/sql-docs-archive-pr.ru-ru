---
title: Проверка пакета приложения уровня данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data-tier application [SQL Server], validate
- data-tier application [SQL Server], compare
- validate DAC
- compare DACs
- data-tier application [SQL Server], view
- view DAC
ms.assetid: 726ffcc2-9221-424a-8477-99e3f85f03bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 078c7bfeef2ff8636243f4853c03de252c7b9289
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668384"
---
# <a name="validate-a-dac-package"></a><span data-ttu-id="10ff5-102">Проверка пакета приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="10ff5-102">Validate a DAC Package</span></span>
  <span data-ttu-id="10ff5-103">Перед развертыванием пакета приложения уровня данных рекомендуется просмотреть его содержимое и проверить действия по обновлению перед обновлением существующего пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-103">It is a good practice to review the contents of a DAC package before deploying it in production, and to validate the upgrade actions before upgrading an existing DAC.</span></span> <span data-ttu-id="10ff5-104">Тем более это истина для развертывания пакетов, которые ранее в организации не развертывались.</span><span class="sxs-lookup"><span data-stu-id="10ff5-104">This is especially true when deploying packages that were not developed in your organization.</span></span>  
  
1.  <span data-ttu-id="10ff5-105">**Перед началом работы**  [Предварительные требования](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="10ff5-105">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
2.  <span data-ttu-id="10ff5-106">**Обновление приложения уровня данных с использованием:**  [просмотра содержимого приложения уровня данных](#ViewDACContents), [просмотра изменений базы данных](#ViewDBChanges), [просмотра действий по обновлению](#ViewUpgradeActions), [сравнения приложений уровня данных](#CompareDACs)</span><span class="sxs-lookup"><span data-stu-id="10ff5-106">**To upgrade a DAC, using:**  [View the Contents of a DAC](#ViewDACContents), [View Database Changes](#ViewDBChanges), [View Upgrade Actions](#ViewUpgradeActions), [Compare DACs](#CompareDACs)</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="10ff5-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="10ff5-107">Prerequisites</span></span>  
 <span data-ttu-id="10ff5-108">Рекомендуется не выполнять развертывание пакетов DAC, полученных из неизвестных или ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="10ff5-108">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="10ff5-109">В этих пакетах может содержаться вредоносный код, вызывающий выполнение непредусмотренных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] или появление ошибок из-за изменения схемы.</span><span class="sxs-lookup"><span data-stu-id="10ff5-109">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="10ff5-110">Прежде чем использовать приложение уровня данных, полученное из ненадежного источника, разверните его на изолированном тестовом экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)], выполните для базы данных инструкцию [DBCC CHECKDB (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql), а также изучите исходный код в базе данных, например хранимые процедуры и другой определенный пользователем код.</span><span class="sxs-lookup"><span data-stu-id="10ff5-110">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], run [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database, and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
##  <a name="view-the-contents-of-a-dac"></a><a name="ViewDACContents"></a> <span data-ttu-id="10ff5-111">просмотр содержимого приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="10ff5-111">View the Contents of a DAC</span></span>  
 <span data-ttu-id="10ff5-112">Просматривать содержимое пакета приложения уровня данных можно с помощью двух механизмов.</span><span class="sxs-lookup"><span data-stu-id="10ff5-112">There are two mechanisms for viewing the contents of a data-tier application (DAC) package.</span></span> <span data-ttu-id="10ff5-113">Можно импортировать пакет приложения уровня данных в проект приложения уровня данных в средствах разработчика SQL Server.</span><span class="sxs-lookup"><span data-stu-id="10ff5-113">You can import the DAC package to a DAC project in SQL Server Developer Tools.</span></span> <span data-ttu-id="10ff5-114">Можно распаковать содержимое пакета в папку.</span><span class="sxs-lookup"><span data-stu-id="10ff5-114">You can unpack the contents of the package to a folder.</span></span>  
  
 <span data-ttu-id="10ff5-115">**Просмотр приложения уровня данных в средствах разработчика SQL Server**</span><span class="sxs-lookup"><span data-stu-id="10ff5-115">**View a DAC in SQL Server Developer Tools**</span></span>  
  
1.  <span data-ttu-id="10ff5-116">Откройте меню **Файл**, выберите **Создать**, затем **Проект...** .</span><span class="sxs-lookup"><span data-stu-id="10ff5-116">Open the **File** menu, select **New**, and then select **Project...**.</span></span>  
  
2.  <span data-ttu-id="10ff5-117">Выберите шаблон проекта **SQL Server** и укажите **Имя**, **Расположение**и **Имя решения**.</span><span class="sxs-lookup"><span data-stu-id="10ff5-117">Select the **SQL Server** project template, and specify a **Name**, **Location**, and **Solution name**.</span></span>  
  
3.  <span data-ttu-id="10ff5-118">В **обозревателе решений** щелкните правой кнопкой мыши узел проекта и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="10ff5-118">In **Solution Explorer**, right click the project node and select **Properties...**.</span></span>  
  
4.  <span data-ttu-id="10ff5-119">На вкладке **Параметры проекта** в разделе **Типы вывода** установите флажок **Приложение уровня данных (файл с расширением DACPAC)** и закройте диалоговое окно свойств.</span><span class="sxs-lookup"><span data-stu-id="10ff5-119">On the **Project Settings** tab, in the **Output Types** section, select the **Data-tier Application (.dacpac File)** check box, and then close the properties dialog.</span></span>  
  
5.  <span data-ttu-id="10ff5-120">В **обозревателе решений** щелкните правой кнопкой мыши узел проекта и выберите **Импорт приложения уровня данных...** .</span><span class="sxs-lookup"><span data-stu-id="10ff5-120">In **Solution Explorer**, right click the project node and select **Import Data-tier Application...**.</span></span>  
  
6.  <span data-ttu-id="10ff5-121">Используйте **Обозреватель решений** , чтобы открыть любые файлы в приложении уровня данных, например политику выбора сервера, а также скрипты, выполняемые до и после развертывания.</span><span class="sxs-lookup"><span data-stu-id="10ff5-121">Use **Solution Explorer** to open all of the files in the DAC, such as the server selection policy and the pre- and post-deployment scripts.</span></span>  
  
7.  <span data-ttu-id="10ff5-122">Используйте **Представление схемы** , чтобы просмотреть все объекты, составляющие схему, обращая особое внимание на код таких объектов, как функции или хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="10ff5-122">Use the **Schema View** to review all of the objects in the schema, particularly reviewing the code in objects such as functions or stored procedures.</span></span>  
  
 <span data-ttu-id="10ff5-123">**Просмотр приложения уровня данных в папке**</span><span class="sxs-lookup"><span data-stu-id="10ff5-123">**View a DAC in a Folder**</span></span>  
  
-   <span data-ttu-id="10ff5-124">Распакуйте пакет приложения уровня данных в папку, следуя инструкциям в [Unpack a DAC Package](unpack-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="10ff5-124">Unpack the DAC package into a folder by following the instructions in [Unpack a DAC Package](unpack-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="10ff5-125">Просмотрите содержимое скриптов [!INCLUDE[tsql](../../includes/tsql-md.md)] , открывая их в редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] в [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10ff5-125">View the contents of the [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts by opening them in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
-   <span data-ttu-id="10ff5-126">Просмотрите содержимое текстовых файлов с помощью таких средств, как Блокнот.</span><span class="sxs-lookup"><span data-stu-id="10ff5-126">View the contents of the text files in tools such as notepad.</span></span>  
  
##  <a name="view-database-changes"></a><a name="ViewDBChanges"></a> <span data-ttu-id="10ff5-127">просмотр изменений базы данных</span><span class="sxs-lookup"><span data-stu-id="10ff5-127">View Database Changes</span></span>  
 <span data-ttu-id="10ff5-128">Непосредственно в связанной базе данных после развертывания текущей версии приложения уровня данных на рабочем сервере могут быть выполнены изменения, конфликтующие со схемой, которая определена в новой версии приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-128">After the current version of a DAC was deployed to production, changes may have been made directly to the associated database that might conflict with the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="10ff5-129">Прежде чем обновлять приложение уровня данных, проверьте, могут ли изменения, внесенные в базу данных, повлиять на процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="10ff5-129">Before upgrading to a new version of the DAC, check to see if such changes have been made to the database.</span></span>  
  
 <span data-ttu-id="10ff5-130">**Просмотр изменений базы данных с помощью мастера**</span><span class="sxs-lookup"><span data-stu-id="10ff5-130">**View Database Changes by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="10ff5-131">Запустите мастер **обновления приложения уровня данных** , указав текущую развернутую версию приложения уровня данных и пакет приложения уровня данных, содержащий новую версию приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-131">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="10ff5-132">На странице **Обнаружение изменений** просмотрите отчет об изменениях, которые были выполнены в базе данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-132">On the **Detect Change** page, review the report of the changes that have been made to the database.</span></span>  
  
3.  <span data-ttu-id="10ff5-133">Выберите **Отмена** , если не желаете продолжать обновление.</span><span class="sxs-lookup"><span data-stu-id="10ff5-133">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="10ff5-134">Дополнительные сведения об использовании мастера см. в разделе [Обновление приложения уровня данных](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="10ff5-134">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
### <a name="view-database-changes-by-using-powershell"></a><span data-ttu-id="10ff5-135">Просмотр изменений базы данных с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="10ff5-135">View Database Changes by Using PowerShell</span></span>
  
1.  <span data-ttu-id="10ff5-136">Создайте объект SMO Server и задайте его равным экземпляру, содержащему приложение уровня данных, которое требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="10ff5-136">Create a SMO Server object and set it to the instance that contains the DAC to be viewed.</span></span>  
  
2.  <span data-ttu-id="10ff5-137">Откройте объект `ServerConnection` и подключитесь к тому же экземпляру.</span><span class="sxs-lookup"><span data-stu-id="10ff5-137">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="10ff5-138">Укажите имя приложения уровня данных в переменной.</span><span class="sxs-lookup"><span data-stu-id="10ff5-138">Specify the DAC name in a variable.</span></span>  
  
4.  <span data-ttu-id="10ff5-139">Используйте метод `GetDatabaseChanges()` для вызова объекта `ChangeResults` и направьте объект по каналу в текстовый файл, чтобы сформировать простой отчет о новых, удаленных и измененных объектах.</span><span class="sxs-lookup"><span data-stu-id="10ff5-139">Use the `GetDatabaseChanges()` method to retrieve a `ChangeResults` object, and pipe the object to a text file to generate a simple report of new, deleted, and changed objects.</span></span>  
  
### <a name="view-database-changes-example-powershell"></a><span data-ttu-id="10ff5-140">Просмотр примера изменений базы данных (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="10ff5-140">View Database Changes Example (PowerShell)</span></span>
  
 <span data-ttu-id="10ff5-141">В следующем примере сообщается о любых изменениях в базе данных, которые были выполнены в развернутом приложении уровня данных с именем MyApplicaiton.</span><span class="sxs-lookup"><span data-stu-id="10ff5-141">The following example reports any database changes that have been made in a deployed DAC named MyApplicaiton.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the change list and save to file.  
$dacChanges = $dacstore.GetDatabaseChanges($dacName) | Out-File -Filepath C:\DACScripts\MyApplicationChanges.txt  
```  
  
##  <a name="view-upgrade-actions"></a><a name="ViewUpgradeActions"></a> <span data-ttu-id="10ff5-142">просмотр действий по обновлению</span><span class="sxs-lookup"><span data-stu-id="10ff5-142">View Upgrade Actions</span></span>  
 <span data-ttu-id="10ff5-143">Перед использованием новой версии пакета приложения уровня данных для обновления приложения уровня данных, которое было развернуто из пакета приложения уровня данных более ранней версии, можно создать отчет, содержащий инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , которые будут выполняться при обновлении, а затем просмотреть эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="10ff5-143">Before using a new version of a DAC package to upgrade a DAC that was deployed from an earlier DAC package, you can generate a report that contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that will be run during the upgrade, and then review the statements.</span></span>  
  
 <span data-ttu-id="10ff5-144">**Действия по обновлению отчета с помощью мастера**</span><span class="sxs-lookup"><span data-stu-id="10ff5-144">**Report Upgrade Actions by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="10ff5-145">Запустите мастер **обновления приложения уровня данных** , указав текущую развернутую версию приложения уровня данных и пакет приложения уровня данных, содержащий новую версию приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-145">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="10ff5-146">На странице **Сводка** просмотрите отчет о действиях обновления.</span><span class="sxs-lookup"><span data-stu-id="10ff5-146">On the **Summary** page, review the report of the upgrade actions.</span></span>  
  
3.  <span data-ttu-id="10ff5-147">Выберите **Отмена** , если не желаете продолжать обновление.</span><span class="sxs-lookup"><span data-stu-id="10ff5-147">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="10ff5-148">Дополнительные сведения об использовании мастера см. в разделе [Обновление приложения уровня данных](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="10ff5-148">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
 <span data-ttu-id="10ff5-149">**Действия по обновлению отчета с помощью PowerShell**</span><span class="sxs-lookup"><span data-stu-id="10ff5-149">**Report Upgrade Actions by Using PowerShell**</span></span>  
  
1.  <span data-ttu-id="10ff5-150">Создайте объект SMO Server и задайте его равным экземпляру, содержащему развернутое приложение уровня данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-150">Create a SMO Server object and set it to the instance that contains the deployed DAC.</span></span>  
  
2.  <span data-ttu-id="10ff5-151">Откройте объект `ServerConnection` и подключитесь к тому же экземпляру.</span><span class="sxs-lookup"><span data-stu-id="10ff5-151">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="10ff5-152">Используйте `System.IO.File` для загрузки файла пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-152">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="10ff5-153">Укажите имя приложения уровня данных в переменной.</span><span class="sxs-lookup"><span data-stu-id="10ff5-153">Specify the DAC name in a variable.</span></span>  
  
5.  <span data-ttu-id="10ff5-154">Используйте метод `GetIncrementalUpgradeScript()` для получения списка инструкций Transact-SQL, которые будут выполняться при обновлении, и направьте этот список по каналу в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="10ff5-154">Use the `GetIncrementalUpgradeScript()` method to get a list of the Transact-SQL statements an upgrade would run, and pipe the list to a text file.</span></span>  
  
6.  <span data-ttu-id="10ff5-155">Закройте файловый поток, используемый для чтения файла пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-155">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="view-upgrade-actions-example-powershell"></a><span data-ttu-id="10ff5-156">Просмотр примера действий по обновлению (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="10ff5-156">View Upgrade Actions Example (PowerShell)</span></span>
  
 <span data-ttu-id="10ff5-157">Следующий пример предоставляет сведения об инструкциях Transact-SQL, которые будут выполняться для обновления приложения уровня данных с именем MyApplicaiton с переходом на схему, указанную в файле MyApplicationVNext.dacpac.</span><span class="sxs-lookup"><span data-stu-id="10ff5-157">The following example reports the Transact-SQL statements that would be run to upgrading a DAC named MyApplicaiton to the schema defined in a MyApplicationVNext.dacpac file.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Load the DAC package file.  
$dacpacPath = "C:\MyDACs\MyApplicationVNext.dacpac"  
$fileStream = [System.IO.File]::Open($dacpacPath,[System.IO.FileMode]::OpenOrCreate)  
$dacType = [Microsoft.SqlServer.Management.Dac.DacType]::Load($fileStream)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the upgrade script and save to file.  
$dacstore.GetIncrementalUpgradeScript($dacName, $dacType) | Out-File -Filepath C:\DACScripts\MyApplicationUpgrade.sql  
  
## Close the filestream to the new DAC package.  
$fileStream.Close()  
```  
  
##  <a name="compare-dacs"></a><a name="CompareDACs"></a><span data-ttu-id="10ff5-158">Сравнить приложений уровня данных</span><span class="sxs-lookup"><span data-stu-id="10ff5-158">Compare DACs</span></span>  
 <span data-ttu-id="10ff5-159">Перед обновлением приложения уровня данных рекомендуется проанализировать различия в базе данных и объектах уровня экземпляра между текущим и новым приложениями уровня данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-159">Before upgrading a DAC, it is a good practice to review the differences in the database and instance-level objects between the current and new DACs.</span></span> <span data-ttu-id="10ff5-160">В случае отсутствия копии пакета действующего приложения уровня данных его можно извлечь из текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="10ff5-160">If you do not have a copy of the package for the current DAC, you can extract a package from the current database.</span></span>  
  
 <span data-ttu-id="10ff5-161">Если импортировать оба пакета приложений уровня данных в проекты приложений уровня данных в средствах разработчика SQL Server, то для анализа различий между ними станет возможным использовать средство «Сравнение схем».</span><span class="sxs-lookup"><span data-stu-id="10ff5-161">If you import both DAC packages into DAC projects in SQL Server Developer Tools, you can use the Schema Compare tool to analyze the differences between the two DACs.</span></span>  
  
 <span data-ttu-id="10ff5-162">Можно также распаковать приложения уровня данных в отдельные папки.</span><span class="sxs-lookup"><span data-stu-id="10ff5-162">Alternatively, unpack the DACs into separate folders.</span></span> <span data-ttu-id="10ff5-163">После этого проанализировать различия можно будет с помощью средства поиска отличий, например программы WinDiff.</span><span class="sxs-lookup"><span data-stu-id="10ff5-163">You can then use a difference tool, such as the WinDiff utility, to analyze the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ff5-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="10ff5-164">See Also</span></span>  
 <span data-ttu-id="10ff5-165">[Приложения уровня данных](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="10ff5-165">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="10ff5-166">[Развертывание приложения уровня данных](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="10ff5-166">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="10ff5-167">Обновление приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="10ff5-167">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
