---
title: Сохранение учетных данных в источнике данных Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 09/23/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- credentials [Reporting Services]
- security [Analysis Services], data sources
- stored credentials [Reporting Services]
- data sources [Reporting Services], stored credentials
ms.assetid: dc700922-97fa-4b30-9547-05bbbec4f09c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fccf8669d1f39d19a26b443ffcead8e86db66a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666444"
---
# <a name="store-credentials-in-a-reporting-services-data-source"></a><span data-ttu-id="a8e9a-102">Сохраненные учетные данные в источнике данных Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a8e9a-102">Store Credentials in a Reporting Services Data Source</span></span>
  <span data-ttu-id="a8e9a-103">Сохраненные учетные данные, используемые сервером отчетов [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] , можно настроить для получения доступа к внешним данным отчета.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-103">You can configure stored credentials that a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] report server uses to access external data for a report.</span></span> <span data-ttu-id="a8e9a-104">Сохраненные учетные данные используются, если отчет запускается автоматически, например, подписка [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] , которая публикует отчет как электронное письмо.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-104">Stored credentials are used if the report runs unattended, for example a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription that publishes a report as an e-mail.</span></span> <span data-ttu-id="a8e9a-105">Сервер отчетов возвращает и использует учетные данные при планировании или запуске обработки отчета.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-105">The report server retrieves and uses the credentials when report processing is scheduled or triggered.</span></span> <span data-ttu-id="a8e9a-106">В этом разделе описывается настройка сохраненных учетных данных для серверов отчетов как в собственном режиме, так и в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-106">This topic walks you through configuring stored credentials for both Native mode and SharePoint mode report servers.</span></span>

||
|-|
|<span data-ttu-id="a8e9a-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в собственном режиме | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="a8e9a-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="a8e9a-108">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-108">**In this topic:**</span></span>

-   [<span data-ttu-id="a8e9a-109">Настройка сохраненных учетных данных для источника данных, относящегося к отчету (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-109">Configure stored credentials for a report-specific data source (Native mode)</span></span>](#bkmk_stored_credentials_data_source_native)

-   [<span data-ttu-id="a8e9a-110">Настройка сохраненных учетных данных для источника данных, связанного с отчетами (режим интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-110">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_data_source_sharepoint)

-   [<span data-ttu-id="a8e9a-111">Настройка сохраненных учетных данных для общего источника данных (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-111">Configure stored credentials for a shared data source (Native mode)</span></span>](#bkmk_stored_credentials_shared_data_source_native)

-   [<span data-ttu-id="a8e9a-112">Настройка сохраненных учетных данных для общедоступного источника данных (режим интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-112">Configure stored credentials for a shared data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_shared_data_source_sharepoint)

##  <a name="security-policy-requirements-for-stored-credentials"></a><a name="bkmk_top"></a> <span data-ttu-id="a8e9a-113">Требования политики безопасности для сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="a8e9a-113">Security policy requirements for stored credentials</span></span>
 <span data-ttu-id="a8e9a-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") Учетная запись, которая используется для сохраненных учетных данных, должна быть настроена в соответствии с одной из указанных ниже политик безопасности на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") It is required that the account you use for stored credentials, is configured for one of the following security policies on the report server.</span></span> <span data-ttu-id="a8e9a-115">Рекомендуется выбирать политику с минимальным уровнем разрешений, необходимых для используемой среды.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-115">It is recommended you select the policy with the minimum level of permissions you require for your environment.</span></span>

1.  <span data-ttu-id="a8e9a-116">Локальный **Вход в**систему.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-116">**Allow log on locally**.</span></span> <span data-ttu-id="a8e9a-117">Дополнительные сведения см. в разделе [Разрешение локального входа](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="a8e9a-117">For more information, see [Allow log on locally](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span></span>

2.  <span data-ttu-id="a8e9a-118">**Вход в качестве пакетного задания**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-118">**Log on as a batch job**.</span></span> <span data-ttu-id="a8e9a-119">Дополнительные сведения см. в разделе [Вход в качестве пакетного задания](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="a8e9a-119">For more information, see [Log on as a batch job](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span></span>

3.  <span data-ttu-id="a8e9a-120">Общие сведения о политиках см. в разделе [Изменение параметров безопасности для объекта групповой политики](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="a8e9a-120">For general information on policies, see [Edit security settings on a Group Policy object](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-native-mode"></a><a name="bkmk_stored_credentials_data_source_native"></a> <span data-ttu-id="a8e9a-121">Настройка сохраненных учетных данных для источника данных, связанного с отчетами (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-121">Configure stored credentials for a report-specific data source (Native mode)</span></span>

1.  <span data-ttu-id="a8e9a-122">В диспетчере отчетов в собственном режиме откройте папку с отчетом.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-122">In Native mode Report Manager, browse to the folder that contains the report.</span></span> <span data-ttu-id="a8e9a-123">Щелкните контекстное меню элемента контекстного меню ![диспетчера отчетов для элементов SSRS](../media/ssrs-report-manager-item-context-menu.png "контекстное меню в диспетчере отчетов для элементов ssrs").</span><span class="sxs-lookup"><span data-stu-id="a8e9a-123">Click the item context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items").</span></span>

2.  <span data-ttu-id="a8e9a-124">Щелкните кнопку **Управление** , а затем — **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-124">Click **Manage** and then click **Data Sources**.</span></span>

3.  <span data-ttu-id="a8e9a-125">Выберите **Пользовательский источник данных**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-125">Select **A custom data source**.</span></span>

4.  <span data-ttu-id="a8e9a-126">В списке **Тип источника данных** выберите модуль обработки данных, который будет использоваться для обработки данных, получаемых из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-126">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="a8e9a-127">В поле **строка подключения**укажите строку соединения, которую сервер отчетов использует для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-127">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="a8e9a-128">В следующем примере показана строка подключения, используемая для подключения к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-128">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="a8e9a-129">В поле **Соединиться при помощи**выберите **Учетные данные, которые безопасно хранятся на сервере отчетов**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-129">For **Connect Using**, select **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="a8e9a-130">Введите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-130">Type a user name and password.</span></span>

    -   <span data-ttu-id="a8e9a-131">Если учетная запись является учетной записью пользователя домена Windows, укажите ее в следующем формате: \<domain> \\<учетная запись \> , а затем установите флажок **использовать учетные данные Windows при подключении к источнику данных.**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-131">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="a8e9a-132">Если имя пользователя и пароль являются учетными данными базы данных, флажок **Использовать учетные данные Windows при соединении с источником данных**устанавливать не следует.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-132">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="a8e9a-133">Если сервер базы данных поддерживает олицетворение или делегирование, можно выбрать параметр **Олицетворение авторизованного пользователя после установки соединения с источником данных**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-133">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

8.  <span data-ttu-id="a8e9a-134">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-134">Click **Apply**.</span></span>

     <span data-ttu-id="a8e9a-135">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [Требования политики безопасности для хранимых учетных данных](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-135">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_data_source_sharepoint"></a><span data-ttu-id="a8e9a-136">Настройка сохраненных учетных данных для источника данных, относящегося к отчету (режим интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-136">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="a8e9a-137">Откройте библиотеку документов, которая содержит отчет, и нажмите кнопку открытия меню ![контекстное меню библиотеки документов для элементов SSRS](../media/ssrs-sharepoint-item-context-menu.png "Контекстное меню библиотеки документов для элементов SSRS").</span><span class="sxs-lookup"><span data-stu-id="a8e9a-137">Browse to the document library that contains the report and then click the open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

2.  <span data-ttu-id="a8e9a-138">Откройте второе меню ![контекстное меню библиотеки документов для элементов SSRS](../media/ssrs-sharepoint-item-context-menu.png "Контекстное меню библиотеки документов для элементов SSRS") и выберите пункт **Управление источниками данных**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-138">Click second open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click **Manage Data Sources**.</span></span>

3.  <span data-ttu-id="a8e9a-139">Выберите имя **настраиваемого** источника данных, который необходимо настроить с помощью сохраненных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-139">Click the name of the **Custom** data source you want to configure with stored credentials.</span></span>

4.  <span data-ttu-id="a8e9a-140">В списке **Тип источника данных** выберите модуль обработки данных, который будет использоваться для обработки данных, получаемых из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-140">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="a8e9a-141">В поле **строка подключения**укажите строку соединения, которую сервер отчетов использует для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-141">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="a8e9a-142">В следующем примере показана строка подключения, используемая для подключения к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-142">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="a8e9a-143">В поле **Учетные данные**выберите вариант **Сохраненные учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-143">For **Credentials**, select **Stored Credentials**.</span></span>

7.  <span data-ttu-id="a8e9a-144">Введите **имя пользователя** и **пароль**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-144">Type a **user name** and **password**.</span></span>

    -   <span data-ttu-id="a8e9a-145">Если учетная запись является учетной записью пользователя домена Windows, укажите ее в следующем формате: \<domain> \\<учетная запись \> , а затем установите флажок **использовать учетные данные Windows при подключении к источнику данных.**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-145">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="a8e9a-146">Если имя пользователя и пароль являются учетными данными базы данных, не выбирайте параметр **Использовать как учетные данные Windows**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-146">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="a8e9a-147">Если сервер базы данных поддерживает олицетворение или делегирование, можно выбрать параметр **задать контекст выполнения для этой учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-147">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>

8.  <span data-ttu-id="a8e9a-148">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-148">Click **ok**.</span></span>

     <span data-ttu-id="a8e9a-149">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [Требования политики безопасности для хранимых учетных данных](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-149">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-native-mode"></a><a name="bkmk_stored_credentials_shared_data_source_native"></a> <span data-ttu-id="a8e9a-150">Настройка сохраненных учетных данных для общедоступного источника данных (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-150">Configure stored credentials for a shared data source (Native mode)</span></span>

1.  <span data-ttu-id="a8e9a-151">Откройте в диспетчере отчетов в собственном режиме элемент общедоступного источника данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-151">In Native mode Report Manager, browse to the shared data source item.</span></span> <span data-ttu-id="a8e9a-152">![Значок общего источника данных](../media/hlp-16datasource.png "Значок общего источника данных")</span><span class="sxs-lookup"><span data-stu-id="a8e9a-152">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="a8e9a-153">Щелкните контекстное меню контекстного меню ![диспетчера отчетов для элементов SSRS](../media/ssrs-report-manager-item-context-menu.png "контекстное меню в диспетчере отчетов для элементов ssrs") и выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-153">Click the context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items") and then click **Manage**.</span></span>

3.  <span data-ttu-id="a8e9a-154">В списке **тип источника данных** Укажите модуль обработки данных, который используется для обработки данных из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-154">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

4.  <span data-ttu-id="a8e9a-155">В поле **строка подключения**укажите строку соединения, которую сервер отчетов использует для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-155">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="a8e9a-156">рекомендует не указывать учетные данные в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-156">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="a8e9a-157">В следующем примере показана строка подключения, используемая для подключения к локальной [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] базе данных:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-157">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

5.  <span data-ttu-id="a8e9a-158">Введите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-158">Type a user name and password.</span></span>

    -   <span data-ttu-id="a8e9a-159">Если учетная запись является учетной записью пользователя домена Windows, укажите ее в следующем формате: \<domain> \\<учетная запись \> , а затем установите флажок **использовать учетные данные Windows при подключении к источнику данных.**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-159">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="a8e9a-160">Если имя пользователя и пароль являются учетными данными базы данных, флажок **Использовать учетные данные Windows при соединении с источником данных**устанавливать не следует.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-160">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="a8e9a-161">Если сервер базы данных поддерживает олицетворение или делегирование, можно выбрать параметр **Олицетворение авторизованного пользователя после установки соединения с источником данных**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-161">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

6.  <span data-ttu-id="a8e9a-162">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-162">Click **Apply**.</span></span>

     <span data-ttu-id="a8e9a-163">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [Требования политики безопасности для хранимых учетных данных](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_shared_data_source_sharepoint"></a><span data-ttu-id="a8e9a-164">Настройка сохраненных учетных данных для общего источника данных (режим интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-164">Configure stored credentials for a shared data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="a8e9a-165">Откройте в библиотеке документов элемент общего источника данных.![Значок общего источника данных](../media/hlp-16datasource.png "Значок общего источника данных")</span><span class="sxs-lookup"><span data-stu-id="a8e9a-165">In the document library, browse to the shared data source item.![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="a8e9a-166">Откройте контекстное меню ![контекстное меню библиотеки документов для элементов SSRS](../media/ssrs-sharepoint-item-context-menu.png "Контекстное меню библиотеки документов для элементов SSRS"), а затем второе контекстное меню ![контекстное меню библиотеки документов для элементов SSRS](../media/ssrs-sharepoint-item-context-menu.png "Контекстное меню библиотеки документов для элементов SSRS").</span><span class="sxs-lookup"><span data-stu-id="a8e9a-166">Click the context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click the second context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

3.  <span data-ttu-id="a8e9a-167">Нажмите кнопку **Изменить определение источника данных**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-167">Click **Edit Data Source Definition**.</span></span>

4.  <span data-ttu-id="a8e9a-168">В списке **тип источника данных** Укажите модуль обработки данных, который используется для обработки данных из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-168">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="a8e9a-169">В поле **строка подключения**укажите строку соединения, которую сервер отчетов использует для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-169">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="a8e9a-170">рекомендует не указывать учетные данные в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-170">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="a8e9a-171">В следующем примере показана строка подключения, используемая для подключения к локальной [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] базе данных:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-171">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="a8e9a-172">Введите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-172">Type a user name and password.</span></span>

    -   <span data-ttu-id="a8e9a-173">Если учетная запись является учетной записью пользователя домена Windows, укажите ее в следующем формате: \<domain> \\<учетная запись \> , а затем выберите **использовать как учетные данные Windows.**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-173">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials.**</span></span>

    -   <span data-ttu-id="a8e9a-174">Если имя пользователя и пароль являются учетными данными базы данных, не выбирайте параметр **Использовать как учетные данные Windows**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-174">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="a8e9a-175">Если сервер базы данных поддерживает олицетворение или делегирование, можно выбрать параметр **Выполнять в контексте этой учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-175">If the database server supports impersonation or delegation, you can select **Set Execution context to this account**.</span></span>

7.  <span data-ttu-id="a8e9a-176">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-176">Click **Ok**.</span></span>

     <span data-ttu-id="a8e9a-177">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [Требования политики безопасности для хранимых учетных данных](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="a8e9a-177">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

## <a name="see-also"></a><span data-ttu-id="a8e9a-178">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-178">See Also</span></span>
 <span data-ttu-id="a8e9a-179">[Указание учетных данных и сведений о соединении для источников данных отчета](../../integration-services/connection-manager/data-sources.md) [Настройка свойств источника данных для отчета &#40;диспетчер отчетов&#41;](configure-data-source-properties-for-a-report-report-manager.md) [Создание, удаление или изменение общего источника данных &#40;диспетчер отчетов](../create-delete-or-modify-a-shared-data-source-report-manager.md)&#41;[Страница "свойства источников данных](../data-sources-properties-page-report-manager.md) " &#40;диспетчер отчетов&#41;[Новая страница источника данных &#40;](../new-data-source-page-report-manager.md) диспетчер отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="a8e9a-179">[Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md) [Configure Data Source Properties for a Report  &#40;Report Manager&#41;](configure-data-source-properties-for-a-report-report-manager.md) [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) [Data Sources Properties Page &#40;Report Manager&#41;](../data-sources-properties-page-report-manager.md) [New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md)</span></span>


