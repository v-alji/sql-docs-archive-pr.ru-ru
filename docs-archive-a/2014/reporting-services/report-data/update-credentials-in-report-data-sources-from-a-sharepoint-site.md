---
title: Обновление учетных данных в источниках данных отчетов с сайта SharePoint | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e0c50b6e-89e7-4b4d-8fe5-c90682c5d1b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 923fee5656ed6032201fb4276fcca75be799e42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654823"
---
# <a name="update-credentials-in-report-data-sources-from-a-sharepoint-site"></a><span data-ttu-id="fc592-102">Обновление учетных данных в источниках данных отчетов с сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="fc592-102">Update Credentials in Report Data Sources from a SharePoint Site</span></span>
  <span data-ttu-id="fc592-103">В этом разделе описывается процесс обновления источников данных, встроенных в отчеты, и совместно используемых источников данных, сохраненных в библиотеке документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc592-103">This topic describes how to update data sources embedded in reports and shared data sources that are saved in a SharePoint document library.</span></span>  
  
 <span data-ttu-id="fc592-104">Во многих отчетах могут быть включены источники данных или общие источники данных, настроенные на использование проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="fc592-104">Many of your reports might include data sources or use shared data sources that are configured to use Windows Authentication.</span></span> <span data-ttu-id="fc592-105">В некоторых ситуациях, например при создании предупреждений об изменении данных для отчетов, сохраненных в библиотеку документов SharePoint, необходимо настроить учетные данные источника данных на использование сохраненных учетных данных или на работу без учетных данных.</span><span class="sxs-lookup"><span data-stu-id="fc592-105">Under some circumstances, such as creating data alerts on reports saved to a SharePoint document library, you need to update the data source credentials to stored credentials or require no credentials.</span></span>  
  
 <span data-ttu-id="fc592-106">Для использования сохраненных учетных данных в отчетах вам может понадобиться создать и использовать новое имя входа SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc592-106">To use stored credentials in reports, you might decide to create and use a new SQL Server login.</span></span> <span data-ttu-id="fc592-107">Дополнительные сведения см. в разделе [Создание имени входа](../../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="fc592-107">For more information, see [Create a Login](../../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
### <a name="to-update-an-embedded-data-source-to-use-stored-credentials"></a><span data-ttu-id="fc592-108">Настройка внедренного источника данных на использование сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="fc592-108">To update an embedded data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="fc592-109">Перейдите к библиотеке документов SharePoint, в которой сохранен отчет.</span><span class="sxs-lookup"><span data-stu-id="fc592-109">Go to the SharePoint document library where you saved the report.</span></span>  
  
2.  <span data-ttu-id="fc592-110">Щелкните значок, чтобы развернуть раскрывающееся меню для отчета, и выберите пункт **Управление источниками данных**.</span><span class="sxs-lookup"><span data-stu-id="fc592-110">Click the icon for the expand drop-down menu on the report and then click **Manage Data Sources**.</span></span>  
  
     <span data-ttu-id="fc592-111">Откроется страница «Управление источниками данных».</span><span class="sxs-lookup"><span data-stu-id="fc592-111">The Manage Data Sources page opens.</span></span>  
  
3.  <span data-ttu-id="fc592-112">В столбце **Имя** щелкните источник данных.</span><span class="sxs-lookup"><span data-stu-id="fc592-112">In the **Name** column, click the data source.</span></span>  
  
4.  <span data-ttu-id="fc592-113">Убедитесь, что в поле **Тип соединения** выбран вариант **Пользовательский источник данных** .</span><span class="sxs-lookup"><span data-stu-id="fc592-113">For **Connection Type** verify that the **Custom data source** option is selected.</span></span>  
  
     <span data-ttu-id="fc592-114">Этот параметр указывает, что источник данных внедрен в отчет.</span><span class="sxs-lookup"><span data-stu-id="fc592-114">This option indicates that the data source is embedded in the report.</span></span>  
  
5.  <span data-ttu-id="fc592-115">Оставьте в полях **Тип источника данных** и **Строка подключения** исходные значения, если вам не нужно, чтобы отчет подключался к другому типу источника данных, другому серверу или хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="fc592-115">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the report to connect to different type of data source, a different server, or data store.</span></span>  
  
6.  <span data-ttu-id="fc592-116">В поле **Учетные данные**, выберите вариант **Сохраненные учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="fc592-116">For **Credentials**, select **Stored credentials**.</span></span> <span data-ttu-id="fc592-117">Этот вариант работает, только если источник данных не принимает учетные данные или если учетные данные передаются каким-то другим способом.</span><span class="sxs-lookup"><span data-stu-id="fc592-117">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="fc592-118">Вариант **Учетные данные не требуются** также можно использовать в определенных обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="fc592-118">The **Credentials are not required** option can also be used under some circumstances.</span></span>  
  
     <span data-ttu-id="fc592-119">Для некоторых типов источников данных необходимо настроить на сервере отчетов учетную запись автоматического выполнения.</span><span class="sxs-lookup"><span data-stu-id="fc592-119">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="fc592-120">Дополнительные сведения см. в подразделе по соответствующему типу источника данных: [Добавление данных из внешних источников данных (службы SSRS)](add-data-from-external-data-sources-ssrs.md) и [Настройка учетной записи автоматического выполнения (диспетчер конфигурации служб SSRS)](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fc592-120">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
7.  <span data-ttu-id="fc592-121">Введите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="fc592-121">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="fc592-122">Если учетная запись является учетной записью пользователя домена Windows, укажите ее в следующем формате: \<domain> \\<учетная запись \> , а затем установите флажок **использовать учетные данные Windows при подключении к источнику данных**.</span><span class="sxs-lookup"><span data-stu-id="fc592-122">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source**.</span></span>  
  
    -   <span data-ttu-id="fc592-123">Если имя пользователя и пароль являются учетными данными базы данных, флажок **Использовать учетные данные Windows при соединении с источником данных**устанавливать не следует.</span><span class="sxs-lookup"><span data-stu-id="fc592-123">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="fc592-124">Если сервер базы данных поддерживает олицетворение или делегирование, можно выбрать параметр **Выполнять в контексте этой учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="fc592-124">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
8.  <span data-ttu-id="fc592-125">Чтобы проверить возможность соединения для источника данных с использованием новых учетных данных, щелкните **Проверить соединение**.</span><span class="sxs-lookup"><span data-stu-id="fc592-125">To verify the data source can connect by using the updated credentials, click **Test connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-update-a-shared-data-source-to-use-stored-credentials"></a><span data-ttu-id="fc592-126">Настройка общего источника данных на использование сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="fc592-126">To update a shared data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="fc592-127">Перейдите к библиотеке документов SharePoint, в которой сохранен общий источник данных.</span><span class="sxs-lookup"><span data-stu-id="fc592-127">Go to the SharePoint document library where you saved the shared data source.</span></span>  
  
2.  <span data-ttu-id="fc592-128">Щелкните значок, чтобы развернуть раскрывающееся меню для общего источника данных, и выберите пункт **Редактировать определение источника данных**.</span><span class="sxs-lookup"><span data-stu-id="fc592-128">Click the icon for the expand drop-down menu on shared data source, and then click **Edit Data Source Definition**.</span></span>  
  
     <span data-ttu-id="fc592-129">Откроется страница «Источник данных».</span><span class="sxs-lookup"><span data-stu-id="fc592-129">The Data Source page opens.</span></span>  
  
3.  <span data-ttu-id="fc592-130">Оставьте в полях **Тип источника данных** и **Строка подключения** исходные значения, если вам не нужно, чтобы общий источник данных подключался к другому типу источника данных, другому серверу или хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="fc592-130">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the shared data source to connect to different type of data source, a different server, or data store.</span></span>  
  
4.  <span data-ttu-id="fc592-131">В поле **Учетные данные**, выберите вариант **Сохраненные учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="fc592-131">For **Credentials**, select **Stored credentials**.</span></span>  
  
     <span data-ttu-id="fc592-132">Вариант **Учетные данные не требуются** также можно использовать в определенных обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="fc592-132">The **Credentials are not required** option can also be used under some circumstances.</span></span> <span data-ttu-id="fc592-133">Этот вариант работает, только если источник данных не принимает учетные данные или если учетные данные передаются каким-то другим способом.</span><span class="sxs-lookup"><span data-stu-id="fc592-133">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="fc592-134">Для некоторых типов источников данных необходимо настроить на сервере отчетов учетную запись автоматического выполнения.</span><span class="sxs-lookup"><span data-stu-id="fc592-134">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="fc592-135">Дополнительные сведения см. в подразделе по соответствующему типу источника данных: [Добавление данных из внешних источников данных (службы SSRS)](add-data-from-external-data-sources-ssrs.md) и [Настройка учетной записи автоматического выполнения (диспетчер конфигурации служб SSRS)](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fc592-135">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="fc592-136">Введите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="fc592-136">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="fc592-137">Если учетная запись является учетной записью пользователя домена Windows, укажите ее в следующем формате: \<domain> \\<учетная запись \> , а затем установите флажок **использовать учетные данные Windows при подключении к источнику данных.**</span><span class="sxs-lookup"><span data-stu-id="fc592-137">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>  
  
    -   <span data-ttu-id="fc592-138">Если имя пользователя и пароль являются учетными данными базы данных, флажок **Использовать учетные данные Windows при соединении с источником данных**устанавливать не следует.</span><span class="sxs-lookup"><span data-stu-id="fc592-138">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="fc592-139">Если сервер базы данных поддерживает олицетворение или делегирование, можно выбрать параметр **Выполнять в контексте этой учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="fc592-139">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
6.  <span data-ttu-id="fc592-140">Чтобы проверить возможность соединения для источника данных с использованием новых учетных данных, щелкните **Проверить соединение**.</span><span class="sxs-lookup"><span data-stu-id="fc592-140">To verify the data source can connect using the updated credentials, **Test connection**.</span></span>  
  
7.  <span data-ttu-id="fc592-141">Убедитесь, что установлен флажок «Включить этот источник данных».</span><span class="sxs-lookup"><span data-stu-id="fc592-141">Verify that Enable this data source is selected.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc592-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc592-142">See Also</span></span>  
 [<span data-ttu-id="fc592-143">Загрузка документов в библиотеку SharePoint (службы Reporting Services в режиме SharePoint)</span><span class="sxs-lookup"><span data-stu-id="fc592-143">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
  
