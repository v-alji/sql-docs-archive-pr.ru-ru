---
title: Включение отслеживания удаленных ошибок (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- remote data source [Reporting Services]
- EnableRemoteError server property
ms.assetid: 5f05022b-d557-43e0-b50a-f5e2a1846b83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d2a7e7e0b38b38bf563dfc2a8cff65c897c5293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665795"
---
# <a name="enable-remote-errors-reporting-services"></a><span data-ttu-id="b7146-102">Включение отслеживания удаленных ошибок (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="b7146-102">Enable Remote Errors (Reporting Services)</span></span>
  <span data-ttu-id="b7146-103">Можно задать свойства сервера на сервере отчетов [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , чтобы возвращались дополнительные сведения об ошибках, возникающих на удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="b7146-103">You can set server properties on a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server to return additional information about error conditions that occur on remote servers.</span></span> <span data-ttu-id="b7146-104">Если сообщение об ошибке содержит текст «Чтобы получить дополнительные сведения об этой ошибке, перейдите к серверу отчетов на локальном сервере или включите отслеживание удаленных ошибок», то можно задать свойство `EnableRemoteErrors`, чтобы получить доступ к дополнительным сведениям, которые могут помочь в устранении возникшей неполадки.</span><span class="sxs-lookup"><span data-stu-id="b7146-104">If an error message contains the text "For more information about this error, navigate to the report server on the local server machine, or enable remote errors", you can set the `EnableRemoteErrors` property to access additional information that can help you troubleshoot the problem.</span></span> <span data-ttu-id="b7146-105">Дополнительные сведения см. в разделе [Системные свойства сервера отчетов](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7146-105">For more information, see [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="b7146-106">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="b7146-106">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="b7146-107">Включение отслеживания удаленных ошибок для режима SharePoint</span><span class="sxs-lookup"><span data-stu-id="b7146-107">Enable Remote Errors for SharePoint Mode</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="b7146-108">Включение отслеживания удаленных ошибок в среде SQL Server Management Studio (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="b7146-108">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>](#bkmk_mgtStudio)  
  
-   [<span data-ttu-id="b7146-109">Включение отслеживания удаленных ошибок с помощью скрипта (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="b7146-109">Enable remote errors through script (Native Mode)</span></span>](#bkmk_script)  
  
-   [<span data-ttu-id="b7146-110">Изменение таблицы ConfigurationInfo (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="b7146-110">Modifying the ConfigurationInfo table (Native Mode)</span></span>](#bkmk_ConfigurationInfo)  
  
##  <a name="enable-remote-errors-for-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="b7146-111">Включение отслеживания удаленных ошибок для режима SharePoint</span><span class="sxs-lookup"><span data-stu-id="b7146-111">Enable Remote Errors for SharePoint Mode</span></span>  
 <span data-ttu-id="b7146-112">Существуют две различные процедуры для включения отслеживания удаленных ошибок для служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме совместимости с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b7146-112">There are two different procedures for enabling remote errors for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="b7146-113">Процедуры для двух разных архитектур сервера отчетов отличаются.</span><span class="sxs-lookup"><span data-stu-id="b7146-113">The procedure is different for the two different report server architectures.</span></span> <span data-ttu-id="b7146-114">В выпуске [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] была представлена новая архитектура, основанная на службах SharePoint. В ней используются настройки, которые могут быть изменены для каждого приложения службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7146-114">The newer SharePoint service based architecture that was introduced in the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, utilizes a setting that can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="b7146-115">Прежняя архитектура использовала общие настройки на уровне веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="b7146-115">The older architecture utilizes a single site level setting.</span></span>  
  
#### <a name="enable-remote-errors-for-a-reporting-services-service-application"></a><span data-ttu-id="b7146-116">Включение отслеживания удаленных ошибок для приложения службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b7146-116">Enable Remote errors for a Reporting Services Service Application</span></span>  
  
1.  <span data-ttu-id="b7146-117">Для сервера отчетов в режиме интеграции с SharePoint, установленном с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] или обновленной версией [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], включите настройку приложения службы **Включение удаленного контроля ошибок**.</span><span class="sxs-lookup"><span data-stu-id="b7146-117">For a SharePoint mode report server installed with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] or a newer version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], enable the service application setting **Enable remote errors**.</span></span> <span data-ttu-id="b7146-118">Настройка может быть изменена для каждого приложения службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7146-118">The setting can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="b7146-119">В центре администрирования SharePoint в разделе **Управление приложениями** выберите **Управление приложениями служб** .</span><span class="sxs-lookup"><span data-stu-id="b7146-119">In SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
3.  <span data-ttu-id="b7146-120">Найдите нужное приложение службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и щелкните его название.</span><span class="sxs-lookup"><span data-stu-id="b7146-120">Find your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and click the name of your service application.</span></span>  
  
4.  <span data-ttu-id="b7146-121">Нажмите кнопку **Системные параметры**.</span><span class="sxs-lookup"><span data-stu-id="b7146-121">Click **System Settings**.</span></span>  
  
5.  <span data-ttu-id="b7146-122">В разделе **Безопасность** нажмите кнопку **Включить отслеживание удаленных ошибок** .</span><span class="sxs-lookup"><span data-stu-id="b7146-122">Click **Enable Remote Errors** in the **Security** section.</span></span>  
  
6.  <span data-ttu-id="b7146-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b7146-123">Click **OK**.</span></span>  
  
#### <a name="enable-remote-errors-for-a-sharepoint-site"></a><span data-ttu-id="b7146-124">Включение отслеживания удаленных ошибок для сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="b7146-124">Enable Remote Errors for a SharePoint Site</span></span>  
  
1.  <span data-ttu-id="b7146-125">Для сервера отчетов в режиме интеграции с SharePoint, установленном с версией [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] до [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], включите настройку сайта **Включение удаленного контроля ошибок в локальном режиме**.</span><span class="sxs-lookup"><span data-stu-id="b7146-125">For a SharePoint mode report server installed with a version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] prior to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], enable the site setting **Enable remote errors in local mode**.</span></span>  
  
2.  <span data-ttu-id="b7146-126">В области **Действия сайта** выберите **Настройки сайта** для сайта, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="b7146-126">In **Site Actions** click **Site Settings** for the site you want to modify.</span></span>  
  
3.  <span data-ttu-id="b7146-127">Выберите **Настройки сайта служб Reporting Services** в группе **Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="b7146-127">Click **Reporting Services Site Settings** in the **Reporting Services** group.</span></span>  
  
4.  <span data-ttu-id="b7146-128">Выберите **Включить отслеживание удаленных ошибок в локальном режиме**.</span><span class="sxs-lookup"><span data-stu-id="b7146-128">Click **Enable remote errors in local mode**.</span></span>  
  
5.  <span data-ttu-id="b7146-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b7146-129">Click **OK**</span></span>  
  
##  <a name="enable-remote-errors-through-sql-server-management-studio-native-mode"></a><a name="bkmk_mgtStudio"></a> <span data-ttu-id="b7146-130">Включение отслеживания удаленных ошибок в среде SQL Server Management Studio (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="b7146-130">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>  
  
1.  <span data-ttu-id="b7146-131">Запустите среду Management Studio и соединитесь с экземпляром сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b7146-131">Start Management Studio and connect to a report server instance.</span></span> <span data-ttu-id="b7146-132">Дополнительные сведения см. в разделе [Подключение к серверу отчетов в среде Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7146-132">For more information, see [Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="b7146-133">Щелкните правой кнопкой мыши узел сервера отчетов и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b7146-133">Right-click the report server node, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="b7146-134">Нажмите кнопку **Дополнительно** , чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="b7146-134">Click **Advanced** to open the properties page.</span></span> <span data-ttu-id="b7146-135">Дополнительные сведения см. в разделе [Свойства сервера (страница "Дополнительно") — службы Reporting Services](../tools/server-properties-advanced-page-reporting-services.md) в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7146-135">For more information, see [Server Properties &#40;Advanced Page&#41; - Reporting Services](../tools/server-properties-advanced-page-reporting-services.md)in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="b7146-136">В `EnableRemoteErrors` выберите `True` .</span><span class="sxs-lookup"><span data-stu-id="b7146-136">In `EnableRemoteErrors`, select `True`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="enable-remote-errors-through-script-native-mode"></a><a name="bkmk_script"></a> <span data-ttu-id="b7146-137">Включение отслеживания удаленных ошибок с помощью скрипта (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="b7146-137">Enable remote errors through script (Native Mode)</span></span>  
  
1.  <span data-ttu-id="b7146-138">Создайте текстовый файл и скопируйте в него следующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="b7146-138">Create a text file and copy the following script into the file.</span></span>  
  
    ```  
    Public Sub Main()  
      Dim P As New [Property]()  
      P.Name = "EnableRemoteErrors"  
      P.Value = True  
      Dim Properties(0) As [Property]  
      Properties(0) = P  
      Try  
        rs.SetSystemProperties(Properties)  
        Console.WriteLine("Remote errors enabled.")  
      Catch SE As SoapException  
        Console.WriteLine(SE.Detail.OuterXml)  
      End Try  
    End Sub  
    ```  
  
2.  <span data-ttu-id="b7146-139">Сохраните файл с именем EnableRemoteErrors.rss.</span><span class="sxs-lookup"><span data-stu-id="b7146-139">Save the file as EnableRemoteErrors.rss.</span></span>  
  
3.  <span data-ttu-id="b7146-140">Нажмите кнопку **Пуск**, укажите команду **Выполнить**, введите **cmd**и нажмите кнопку **ОК** , чтобы открыть окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="b7146-140">Click **Start**, point to **Run**, type **cmd**, and click **OK** to open a command prompt window.</span></span>  
  
4.  <span data-ttu-id="b7146-141">Перейдите к каталогу, содержащему только что созданный файл RSS.</span><span class="sxs-lookup"><span data-stu-id="b7146-141">Navigate to the directory that contains the .rss file you just created.</span></span>  
  
5.  <span data-ttu-id="b7146-142">Введите в командной строке следующую команду, заменив местозаполнитель *имя_сервера* реальным именем сервера:</span><span class="sxs-lookup"><span data-stu-id="b7146-142">Type the following command line, replacing *servername* with the actual name of your server:</span></span>  
  
    ```  
    rs -i EnableRemoteErrors.rss -s http://servername/ReportServer  
    ```  
  
6.  <span data-ttu-id="b7146-143">Дополнительные сведения см. в разделе [Программа RS.exe (SSRS)](../tools/rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b7146-143">For more information, see [RS.exe Utility &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md)</span></span>  
  
##  <a name="modifying-the-configurationinfo-table-native-mode"></a><a name="bkmk_ConfigurationInfo"></a> <span data-ttu-id="b7146-144">Изменение таблицы ConfigurationInfo (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="b7146-144">Modifying the ConfigurationInfo table (Native Mode)</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="b7146-145">Можно изменить таблицу **ConfigurationInfo** в базе данных сервера отчетов, чтобы задать `EnableRemoteErrors` для значение `True` , но если сервер отчетов используется активно, следует использовать SQL Server Management Studio или сценарий для изменения параметров.</span><span class="sxs-lookup"><span data-stu-id="b7146-145">You can edit the **ConfigurationInfo** table in the report server database to set `EnableRemoteErrors` to `True`, but if the report server is actively used, you should use SQL Server Management Studio or script to modify the settings.</span></span> <span data-ttu-id="b7146-146">При изменении настроек базы данных необходимо перезапустить службу [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="b7146-146">If you modify the setting in the database, you need to restart the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service before the changes take effect.</span></span>  
  
  
