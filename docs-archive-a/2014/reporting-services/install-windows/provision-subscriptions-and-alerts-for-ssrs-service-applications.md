---
title: Подготовка подписок и предупреждений для приложений служб SSRS | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Shared Service
- SharePoint Mode [Reporting Services]
- SharePoint Mode
- Reporting Services Service Application
- SSRS service application
ms.assetid: d0de3f1f-4887-47fb-bacf-46aaad74c4be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c09033b6a31295b8fbe42058cba9059f5d05629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751839"
---
# <a name="provision-subscriptions-and-alerts-for-ssrs-service-applications"></a><span data-ttu-id="658b7-102">Подготовка подписок и предупреждений для приложений служб SSRS</span><span class="sxs-lookup"><span data-stu-id="658b7-102">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="658b7-103">и предупреждения данных требуют наличия агента SQL Server, а также настройку разрешений для агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="658b7-103">subscriptions and data alerts require SQL Server Agent and require the configuration of permissions for SQL Server Agent.</span></span> <span data-ttu-id="658b7-104">Если появляются сообщения об ошибках, указывающие, что необходим агент SQL Server, хотя агент SQL Server уже запущен, необходимо обновить и проверить разрешения.</span><span class="sxs-lookup"><span data-stu-id="658b7-104">If you see error messages that indicate SQL Server Agent is required and you have verified SQL Server Agent is running, then update or verify permissions.</span></span> <span data-ttu-id="658b7-105">Этот раздел относится к [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint и здесь описаны три способа обновления разрешений агента SQL Server для подписок [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="658b7-105">The scope of this topic is [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode and the topic describes three ways you can update the permissions of SQL Server Agent with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscriptions.</span></span> <span data-ttu-id="658b7-106">Вводимые учетные данные для шагов из данного раздела должны иметь достаточные разрешения для предоставления роли RSExecRole прав на выполнение объектов из приложения службы, баз данных msdb и master.</span><span class="sxs-lookup"><span data-stu-id="658b7-106">The credentials you use for the steps in this topic need to have sufficient permissions to grant execute permissions to the RSExecRole for objects in the service application, msdb, and master databases.</span></span>

||
|-|
|<span data-ttu-id="658b7-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="658b7-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="658b7-108">![Разрешение для агента SQL Server на доступ к базам данных приложений служб](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "Разрешение для агента SQL Server на доступ к базам данных приложений служб")</span><span class="sxs-lookup"><span data-stu-id="658b7-108">![SQL Agent permissions to Service Application DBs](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "SQL Agent permissions to Service Application DBs")</span></span>

||<span data-ttu-id="658b7-109">Description</span><span class="sxs-lookup"><span data-stu-id="658b7-109">Description</span></span>|
|------|-----------------|
|<span data-ttu-id="658b7-110">**1**</span><span class="sxs-lookup"><span data-stu-id="658b7-110">**1**</span></span>|<span data-ttu-id="658b7-111">Экземпляр компонента SQL Server Database Engine, на котором размещаются базы данных приложения службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="658b7-111">The instance of SQL Server Database engine that is hosting the Reporting Services service application databases.</span></span>|
|<span data-ttu-id="658b7-112">**2**</span><span class="sxs-lookup"><span data-stu-id="658b7-112">**2**</span></span>|<span data-ttu-id="658b7-113">Экземпляр агента SQL Server для экземпляра компонента SQL Server Database Engine.</span><span class="sxs-lookup"><span data-stu-id="658b7-113">The instance of SQL Server agent for the instance of the SQL database engine.</span></span>|
|<span data-ttu-id="658b7-114">**3**</span><span class="sxs-lookup"><span data-stu-id="658b7-114">**3**</span></span>|<span data-ttu-id="658b7-115">Базы данных приложения службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="658b7-115">The Reporting Services service application databases.</span></span> <span data-ttu-id="658b7-116">Имена создаются на основе сведений, которые использовались при создании приложения службы.</span><span class="sxs-lookup"><span data-stu-id="658b7-116">The names are based on the information used for creating the service application.</span></span> <span data-ttu-id="658b7-117">Ниже приведены примеры имен баз данных.</span><span class="sxs-lookup"><span data-stu-id="658b7-117">The following are example database names:</span></span><br /><br /> <span data-ttu-id="658b7-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span><span class="sxs-lookup"><span data-stu-id="658b7-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span></span><br /><br /> <span data-ttu-id="658b7-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span><span class="sxs-lookup"><span data-stu-id="658b7-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span></span><br /><br /> <span data-ttu-id="658b7-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span><span class="sxs-lookup"><span data-stu-id="658b7-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span></span>|
|<span data-ttu-id="658b7-121">**4**</span><span class="sxs-lookup"><span data-stu-id="658b7-121">**4**</span></span>|<span data-ttu-id="658b7-122">Базы данных master и MSDB экземпляра компонента SQL Server Database Engine.</span><span class="sxs-lookup"><span data-stu-id="658b7-122">The master and MSDB database of the instance of the SQL Server Database engine.</span></span>|

 <span data-ttu-id="658b7-123">Используйте один из следующих трех методов, чтобы обновить разрешения:</span><span class="sxs-lookup"><span data-stu-id="658b7-123">Use one the following three methods to update the permissions:</span></span>

1.  <span data-ttu-id="658b7-124">На странице **Подготовка подписок и предупреждений** введите учетные данные и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="658b7-124">From the **Provisions and Subscriptions and Alerts** page, type credentials and click **ok**.</span></span>

2.  <span data-ttu-id="658b7-125">На странице «Подготовка подписок и предупреждений» нажмите кнопку **Загрузить скрипт** , чтобы загрузить скрипт Transact-SQL, с помощью которого можно настроить разрешения.</span><span class="sxs-lookup"><span data-stu-id="658b7-125">From the Provisions and Subscriptions and Alerts page, click the **Download Script** button to download a transact SQL script that can be used to configure permissions.</span></span>

3.  <span data-ttu-id="658b7-126">Запустите командлет PowerShell, чтобы построить скрипт SQL, который можно использовать в настройке разрешений.</span><span class="sxs-lookup"><span data-stu-id="658b7-126">Run a PowerShell cmdlet to build a transact SQL script that can be used to configure permissions.</span></span>

### <a name="to-update-permissions-using-the-provision-page"></a><span data-ttu-id="658b7-127">Обновление разрешений с помощью страницы подготовки</span><span class="sxs-lookup"><span data-stu-id="658b7-127">To update permissions using the provision page</span></span>

1.  <span data-ttu-id="658b7-128">В центре администрирования SharePoint в разделе **Управление приложениями** выберите **Управление приложениями службы**.</span><span class="sxs-lookup"><span data-stu-id="658b7-128">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="658b7-129">Найдите нужное приложение службы в списке и щелкните имя приложения либо щелкните столбец **Тип** , чтобы выбрать приложение-службу, а затем нажмите кнопку **Управление** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="658b7-129">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="658b7-130">На странице **Управление приложением служб Reporting Services** щелкните **Подготовка подписок и предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="658b7-130">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="658b7-131">Если администратор SharePoint имеет достаточно прав для базы данных Master и баз данных приложений служб, введите эти учетные данные.</span><span class="sxs-lookup"><span data-stu-id="658b7-131">If the SharePoint administrator has enough privileges to the Master database and the service application databases, type those credentials.</span></span>

5.  <span data-ttu-id="658b7-132">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="658b7-132">Click the **OK** button.</span></span>

##  <a name="to-download-the-transact-sql-script"></a><a name="bkmk_download"></a> <span data-ttu-id="658b7-133">Загрузка скрипта Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="658b7-133">To download the Transact-SQL Script</span></span>

1.  <span data-ttu-id="658b7-134">В центре администрирования SharePoint в разделе **Управление приложениями** выберите **Управление приложениями службы**.</span><span class="sxs-lookup"><span data-stu-id="658b7-134">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="658b7-135">Найдите нужное приложение службы в списке и щелкните имя приложения либо щелкните столбец **Тип** , чтобы выбрать приложение-службу, а затем нажмите кнопку **Управление** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="658b7-135">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="658b7-136">На странице **Управление приложением служб Reporting Services** щелкните **Подготовка подписок и предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="658b7-136">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="658b7-137">В области **Просмотр состояния** убедитесь, что агент SQL Server запущен.</span><span class="sxs-lookup"><span data-stu-id="658b7-137">In the **View Status** area, verify SQL Server Agent is running.</span></span>

5.  <span data-ttu-id="658b7-138">Нажмите **Загрузить скрипт** , чтобы загрузить скрипт Transact SQL, путем запуска которого в среде SQL Server Management Studio можно предоставлять разрешения.</span><span class="sxs-lookup"><span data-stu-id="658b7-138">Click **Download Script** to download a transact SQL script you can run in SQL Server Management studio to grant permissions.</span></span> <span data-ttu-id="658b7-139">Имя созданного файла скрипта будет содержать имя приложения служб Reporting Services, например **[имя приложения службы]-GrantRights.sql**.</span><span class="sxs-lookup"><span data-stu-id="658b7-139">The script file name that is created will contain the name of your Reporting Services service application name, for example **[name of the service application]-GrantRights.sql**.</span></span>

### <a name="to-generate-the-transact-sql-statement-with-powershell"></a><span data-ttu-id="658b7-140">Создание инструкции Transact-SQL с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="658b7-140">To generate the Transact-SQL statement with PowerShell</span></span>

1.  <span data-ttu-id="658b7-141">Создать скрипт Transact-SQL можно с помощью командлета Windows PowerShell в консоли управления SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="658b7-141">You can also use a Windows PowerShell cmdlet in the SharePoint 2010 Management Shell to create the Transact-SQL script.</span></span>

2.  <span data-ttu-id="658b7-142">В меню **Пуск** выберите пункт **Все программы**.</span><span class="sxs-lookup"><span data-stu-id="658b7-142">On the **Start** menu, click **All Programs**.</span></span>

3.  <span data-ttu-id="658b7-143">Разверните **Продукты Microsoft SharePoint 2010** и выберите **Консоль управления SharePoint 2010**.</span><span class="sxs-lookup"><span data-stu-id="658b7-143">Expand **Microsoft SharePoint 2010 Products** and click **SharePoint 2010 Management Shell**.</span></span>

4.  <span data-ttu-id="658b7-144">Обновите следующий командлет PowerShell, заменив имя базы данных сервера отчетов, учетную запись пула приложений и путь к инструкции.</span><span class="sxs-lookup"><span data-stu-id="658b7-144">Update the following PowerShell cmdlet by replacing the name of the report server database, application pool account, and the path of the statement.</span></span>

     <span data-ttu-id="658b7-145">**Синтаксис командлета:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span><span class="sxs-lookup"><span data-stu-id="658b7-145">**Syntax of cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span></span>

     <span data-ttu-id="658b7-146">**Образец командлета:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span><span class="sxs-lookup"><span data-stu-id="658b7-146">**Sample cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span></span>

## <a name="using-the-transact-sql-script"></a><span data-ttu-id="658b7-147">Использование скрипта Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="658b7-147">Using the Transact-SQL Script</span></span>
 <span data-ttu-id="658b7-148">Следующие процедуры можно использовать для скриптов, загруженных со страницы подготовки либо созданных с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="658b7-148">The following procedures can be used with scripts download from the provisions page or scripts created using PowerShell.</span></span>

#### <a name="to-load-the-transact-sql-script-in-sql-server-management-studio"></a><span data-ttu-id="658b7-149">Загрузка скрипта Transact-SQL в среду SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="658b7-149">To load the Transact-SQL script in SQL Server Management Studio</span></span>

1.  <span data-ttu-id="658b7-150">Чтобы открыть среду SQL Server Management Studio, выберите в меню **Пуск** пункт **Microsoft SQL Server 2012** , затем среду **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="658b7-150">To open SQL Server Management Studio, on the **Start** menu, click **Microsoft SQL Server 2012** and click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="658b7-151">В диалоговом окне **Соединение с сервером** установите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="658b7-151">In the **Connect to Server** dialog box set the following options:</span></span>

    -   <span data-ttu-id="658b7-152">В раскрывающемся списке **Тип сервера** выберите **Компонент Database Engine**.</span><span class="sxs-lookup"><span data-stu-id="658b7-152">In the **Server type** list, select **Database Engine**</span></span>

    -   <span data-ttu-id="658b7-153">В поле **Имя сервера**введите имя экземпляра SQL Server, для которого настраивается агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="658b7-153">In **Server Name**, type the name of the SQL Server instance on which you want to configure SQL Server Agent.</span></span>

    -   <span data-ttu-id="658b7-154">Выберите режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="658b7-154">Select an authentication mode.</span></span>

    -   <span data-ttu-id="658b7-155">При соединении с помощью проверки подлинности SQL Server введите имя входа и пароль.</span><span class="sxs-lookup"><span data-stu-id="658b7-155">If connecting using SQL Server Authentication, provide a login and password.</span></span>

3.  <span data-ttu-id="658b7-156">Нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="658b7-156">Click **Connect**.</span></span>

#### <a name="to-run-the-transact-sql-statement"></a><span data-ttu-id="658b7-157">Запуск инструкции Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="658b7-157">To run the Transact-SQL statement</span></span>

1.  <span data-ttu-id="658b7-158">На панели инструментов среды SQL Server Management Studio выберите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="658b7-158">On the toolbar of SQL Server Management Studio, click **New Query**.</span></span>

2.  <span data-ttu-id="658b7-159">В меню **Файл** выберите **Открыть**, затем **Файл**.</span><span class="sxs-lookup"><span data-stu-id="658b7-159">On the **File** menu, click **Open**, and then click **File**.</span></span>

3.  <span data-ttu-id="658b7-160">Перейдите в папку, где была сохранена инструкция Transact-SQL, созданная в консоли управления SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="658b7-160">Navigate to the folder where you saved the Transact-SQL statement that you generated in SharePoint 2010 Management Shell.</span></span>

4.  <span data-ttu-id="658b7-161">Щелкните файл, затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="658b7-161">Click the file and then click **Open**.</span></span>

     <span data-ttu-id="658b7-162">Инструкция будет добавлена в окно запросов.</span><span class="sxs-lookup"><span data-stu-id="658b7-162">The statement is added to the query window.</span></span>

5.  <span data-ttu-id="658b7-163">Нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="658b7-163">Click **Execute**.</span></span>


