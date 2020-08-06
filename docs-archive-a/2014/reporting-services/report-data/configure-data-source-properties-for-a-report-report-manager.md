---
title: Настройка свойств источника данных для отчета (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
ms.assetid: 27af5195-c845-40e0-9a9c-efe569424022
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 42969b4667dd71e4c6413f38e4deadb96491169c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656172"
---
# <a name="configure-data-source-properties-for-a-report--report-manager"></a><span data-ttu-id="3e009-102">Настройка свойств источника данных для отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="3e009-102">Configure Data Source Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="3e009-103">При запуске отчета сервер отчетов получает сведения о свойствах для определения способа подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="3e009-103">When you run a report, the report server retrieves property information to determine how to connect to a data source.</span></span> <span data-ttu-id="3e009-104">На странице свойств «Источник данных» опубликованного отчета указываются тип источника данных, строка соединения и сведения об учетных данных.</span><span class="sxs-lookup"><span data-stu-id="3e009-104">The data source type, connection string, and credential information are specified in the Data Source property pages of the published report.</span></span> <span data-ttu-id="3e009-105">Можно установить эти свойства, чтобы они отличались от исходных значений, заданных при создании отчета.</span><span class="sxs-lookup"><span data-stu-id="3e009-105">You can set the properties to vary the data source connection information from the original values that were specified when the report was created.</span></span>  
  
 <span data-ttu-id="3e009-106">Но если имеется стандартный общий источник данных, в котором уже заданы сведения о соединении, которые необходимо использовать, то можно вместо этого указать общий источник данных.</span><span class="sxs-lookup"><span data-stu-id="3e009-106">Alternatively, if you have a predefined shared data source that already specifies the connection information you want to use, you can specify a shared data source instead.</span></span> <span data-ttu-id="3e009-107">Для использования общего источника данных щелкните **Общий источник данных** на странице свойств «Источник данных» отчета.</span><span class="sxs-lookup"><span data-stu-id="3e009-107">To use a shared data source, click **A shared data source** on the Data Source properties page of the report.</span></span>  
  
### <a name="to-configure-an-embedded-data-source"></a><span data-ttu-id="3e009-108">Настройка внедренного источника данных</span><span class="sxs-lookup"><span data-stu-id="3e009-108">To configure an embedded data source</span></span>  
  
1.  <span data-ttu-id="3e009-109">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3e009-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="3e009-110">В диспетчер отчетов перейдите на страницу **содержимое** .</span><span class="sxs-lookup"><span data-stu-id="3e009-110">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="3e009-111">Перейдите к отчету, для которого нужно настроить источник данных, связанный с отчетом, и откройте его.</span><span class="sxs-lookup"><span data-stu-id="3e009-111">Navigate to the report that you want to configure a report-specific data source for, and open the report.</span></span>  
  
3.  <span data-ttu-id="3e009-112">Перейдите на вкладку **Свойства** . Откроется страница **Общие** свойства.</span><span class="sxs-lookup"><span data-stu-id="3e009-112">Click the **Properties** tab. The **General** properties page opens.</span></span>  
  
4.  <span data-ttu-id="3e009-113">Перейдите на вкладку **Источники данных** . Откроется страница свойств источника данных отчета.</span><span class="sxs-lookup"><span data-stu-id="3e009-113">Click the **Data Sources** tab. This opens the Data Source properties page of the report.</span></span>  
  
5.  <span data-ttu-id="3e009-114">Щелкните **Пользовательский источник данных** , чтобы указать сведения о соединении с источником данных внутри отчета.</span><span class="sxs-lookup"><span data-stu-id="3e009-114">Click **A custom data source** to specify data source connection information within the report.</span></span>  
  
6.  <span data-ttu-id="3e009-115">В списке **Тип соединения** задайте модуль обработки данных, который будет использоваться для обработки данных, получаемых из источника данных.</span><span class="sxs-lookup"><span data-stu-id="3e009-115">In the **Connection Type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="3e009-116">В поле **строка подключения**укажите строку соединения, которую сервер отчетов использует для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="3e009-116">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="3e009-117">Не рекомендуется указывать в строке соединения учетные данные.</span><span class="sxs-lookup"><span data-stu-id="3e009-117">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="3e009-118">В следующем примере показана строка подключения для подключения к локальной [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="3e009-118">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="3e009-119">В качестве параметра **Соединиться при помощи**укажите, как будут указываться учетные данные при выполнении отчета:</span><span class="sxs-lookup"><span data-stu-id="3e009-119">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="3e009-120">Если имя входа и пароль необходимо спросить у пользователя, выберите **Учетные данные, предоставленные пользователем, запустившим отчет**.</span><span class="sxs-lookup"><span data-stu-id="3e009-120">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span>  
  
    -   <span data-ttu-id="3e009-121">при необходимости использования источника данных с отчетами, которые поддерживают подписки или другие операции по расписанию (например, автоматическое формирование журнала отчетов), выберите **Учетные данные, которые безопасно хранятся на сервере отчетов**.</span><span class="sxs-lookup"><span data-stu-id="3e009-121">If you intend to use the data source with reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span>  
  
    -   <span data-ttu-id="3e009-122">Если необходимо, чтобы сервер отчетов передавал учетные данные пользователя, обращающегося к отчету, на сервер, содержащий внешний источник данных, щелкните **Встроенная безопасность Windows**.</span><span class="sxs-lookup"><span data-stu-id="3e009-122">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="3e009-123">В этом случае у пользователя не будут запрашиваться имя и пароль.</span><span class="sxs-lookup"><span data-stu-id="3e009-123">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="3e009-124">Если для доступа к источнику данных учетные данные не используются (например, если это XML-файл, находящийся в файловой системе), выберите **Учетные данные не требуются**.</span><span class="sxs-lookup"><span data-stu-id="3e009-124">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="3e009-125">Этот тип учетных данных следует указывать только в том случае, если он допустим для источника данных.</span><span class="sxs-lookup"><span data-stu-id="3e009-125">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="3e009-126">Если выбрать этот параметр для источника данных, требующего проверки подлинности, соединение завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3e009-126">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="3e009-127">При выборе этого параметра убедитесь, что настроена учетная запись автоматического выполнения, позволяющая серверу отчетов соединяться с другими компьютерами для получения данных или файлов, если пользовательские учетные данные недоступны.</span><span class="sxs-lookup"><span data-stu-id="3e009-127">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
 <span data-ttu-id="3e009-128">Дополнительные сведения о настройке учетных данных см. в разделе [Указание учетных данных и сведений о соединении для источников данных отчета](specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="3e009-128">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="3e009-129">Дополнительные сведения об учетной записи автоматического выполнения см. в разделе [Настройка учетной записи автоматического выполнения (диспетчер конфигурации служб SSRS)](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="3e009-129">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e009-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e009-130">See Also</span></span>  
 <span data-ttu-id="3e009-131">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3e009-131">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="3e009-132">[Страница "Создание источника данных" &#40;диспетчер отчетов&#41;](../new-data-source-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3e009-132">[New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md) </span></span>  
 <span data-ttu-id="3e009-133">[Создание, изменение и удаление общих источников данных &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3e009-133">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="3e009-134">[Управление источниками данных отчета](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="3e009-134">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="3e009-135">[Создание, удаление или изменение общего источника данных &#40;диспетчер отчетов&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3e009-135">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 [<span data-ttu-id="3e009-136">Страница "Свойства источников данных" (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="3e009-136">Data Sources Properties Page &#40;Report Manager&#41;</span></span>](../data-sources-properties-page-report-manager.md)  
  
  
