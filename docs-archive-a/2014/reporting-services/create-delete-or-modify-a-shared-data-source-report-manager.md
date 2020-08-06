---
title: Создание, удаление или изменение общего источника данных (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- removing shared data sources
- data sources [Reporting Services], shared
- deleting shared data sources
- modifying shared data sources
ms.assetid: cd7bace3-f8ec-4ee3-8a9f-2f217cdca9f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6f4ff658e656b159995087df3121806b462e687
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664770"
---
# <a name="create-delete-or-modify-a-shared-data-source-report-manager"></a><span data-ttu-id="96b71-102">Создание, удаление или изменение общего источника данных (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="96b71-102">Create, Delete, or Modify a Shared Data Source (Report Manager)</span></span>
  <span data-ttu-id="96b71-103">Общий источник данных определяет свойства соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="96b71-103">A shared data source specifies connection properties for a data source.</span></span> <span data-ttu-id="96b71-104">Если имеется источник данных, который используется многими отчетами, моделями или управляемыми данными подписками, можно создать общий источник данных, чтобы исключить дополнительные затраты на обслуживание одних и тех же сведений о соединении в разных местах.</span><span class="sxs-lookup"><span data-stu-id="96b71-104">If you have a data source that is used by a large number of reports, models, or data-driven subscriptions, consider creating a shared data source to eliminate the overhead of having to maintain the same connection information in multiple places.</span></span>  
  
 <span data-ttu-id="96b71-105">Следующий значок обозначает общий источник данных в иерархии папок диспетчера отчетов:</span><span class="sxs-lookup"><span data-stu-id="96b71-105">The following icon indicates a shared data source in the Report Manager folder hierarchy:</span></span>  
  
 <span data-ttu-id="96b71-106">![Значок общего источника данных](media/hlp-16datasource.png "Значок общего источника данных")</span><span class="sxs-lookup"><span data-stu-id="96b71-106">![Shared data source icon](media/hlp-16datasource.png "Shared data source icon")</span></span>  
<span data-ttu-id="96b71-107">значок общего источника данных</span><span class="sxs-lookup"><span data-stu-id="96b71-107">shared data source icon</span></span>  
  
### <a name="to-create-a-shared-data-source"></a><span data-ttu-id="96b71-108">Создание общего источника данных</span><span class="sxs-lookup"><span data-stu-id="96b71-108">To create a shared data source</span></span>  
  
1.  <span data-ttu-id="96b71-109">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="96b71-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="96b71-110">В диспетчер отчетов перейдите на страницу **содержимое** .</span><span class="sxs-lookup"><span data-stu-id="96b71-110">In Report Manager, navigate to the **Contents** page.</span></span>  
  
3.  <span data-ttu-id="96b71-111">Нажмите кнопку **Создать источник данных**.</span><span class="sxs-lookup"><span data-stu-id="96b71-111">Click **New Data Source**.</span></span> <span data-ttu-id="96b71-112">Откроется страница **Создание источника данных** .</span><span class="sxs-lookup"><span data-stu-id="96b71-112">The **New Data Source** page opens.</span></span>  
  
4.  <span data-ttu-id="96b71-113">Введите имя элемента.</span><span class="sxs-lookup"><span data-stu-id="96b71-113">Type a name for the item.</span></span> <span data-ttu-id="96b71-114">Имя должно содержать по крайней мере один символ и начинаться с буквы.</span><span class="sxs-lookup"><span data-stu-id="96b71-114">A name must contain at least one character and it must start with a letter.</span></span> <span data-ttu-id="96b71-115">Оно также может включать в себя определенные символы, за исключением пробелов и символов ; ?</span><span class="sxs-lookup"><span data-stu-id="96b71-115">It can also include certain symbols, but not spaces or the characters ; ?</span></span> <span data-ttu-id="96b71-116">: \@ & = +, $/\* \< > | " /.</span><span class="sxs-lookup"><span data-stu-id="96b71-116">: \@ & = + , $ / \* \< > | " /.</span></span>  
  
5.  <span data-ttu-id="96b71-117">Можно также ввести описание, чтобы предоставить пользователям сведения о данном соединении.</span><span class="sxs-lookup"><span data-stu-id="96b71-117">Optionally type a description to provide users with information about the connection.</span></span> <span data-ttu-id="96b71-118">Это описание отображается на странице **Содержимое** диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="96b71-118">This description will appear on the **Contents** page in Report Manager.</span></span>  
  
6.  <span data-ttu-id="96b71-119">В списке **Тип источника данных** задайте модуль обработки данных, который будет использоваться для обработки данных, получаемых из источника данных.</span><span class="sxs-lookup"><span data-stu-id="96b71-119">In the **Data source type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="96b71-120">В поле **Строка подключения**укажите строку соединения, которую сервер отчетов будет использовать для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="96b71-120">For **Connection string**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="96b71-121">Не рекомендуется указывать в строке соединения учетные данные.</span><span class="sxs-lookup"><span data-stu-id="96b71-121">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="96b71-122">В следующем примере показана строка подключения для подключения к локальной [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="96b71-122">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="96b71-123">В качестве параметра **Соединиться при помощи**укажите, как будут указываться учетные данные при выполнении отчета:</span><span class="sxs-lookup"><span data-stu-id="96b71-123">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="96b71-124">Если имя входа и пароль необходимо спросить у пользователя, выберите **Учетные данные, предоставленные пользователем, запустившим отчет**.</span><span class="sxs-lookup"><span data-stu-id="96b71-124">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span> <span data-ttu-id="96b71-125">Чтобы применить учетные данные, которые пользователь вводит как учетные данные Windows, щелкните **Использовать учетные данные Windows при соединении с источником данных**.</span><span class="sxs-lookup"><span data-stu-id="96b71-125">To use the credentials that the user enters as Windows credentials, click **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="96b71-126">Если имя пользователя и пароль не являются учетными данными базы данных, не выбирайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="96b71-126">If the user name and password are database credentials, do not select this option.</span></span>  
  
    -   <span data-ttu-id="96b71-127">Если необходимо использовать источник данных в качестве общего с сохраненными учетными данными, которые управляются владельцем источника данных, или с отчетами, которые поддерживают подписки или другие операции по расписанию (например, автоматическое создание журнала отчетов), выберите **Учетные данные, которые безопасно хранятся на сервере отчетов**.</span><span class="sxs-lookup"><span data-stu-id="96b71-127">If you intend to use the data source as a shared data source with saved credentials that are managed by the owner of the data source, or for reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span> <span data-ttu-id="96b71-128">Если сервер базы данных поддерживает олицетворение или делегирование, можно выбрать параметр **Олицетворение авторизованного пользователя после установки соединения с источником данных**.</span><span class="sxs-lookup"><span data-stu-id="96b71-128">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>  
  
    -   <span data-ttu-id="96b71-129">Если необходимо, чтобы сервер отчетов передавал учетные данные пользователя, обращающегося к отчету, на сервер, содержащий внешний источник данных, щелкните **Встроенная безопасность Windows**.</span><span class="sxs-lookup"><span data-stu-id="96b71-129">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="96b71-130">В этом случае у пользователя не будут запрашиваться имя и пароль.</span><span class="sxs-lookup"><span data-stu-id="96b71-130">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="96b71-131">Если для доступа к источнику данных учетные данные не используются (например, если это XML-файл, находящийся в файловой системе), выберите **Учетные данные не требуются**.</span><span class="sxs-lookup"><span data-stu-id="96b71-131">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="96b71-132">Этот тип учетных данных следует указывать только в том случае, если он допустим для источника данных.</span><span class="sxs-lookup"><span data-stu-id="96b71-132">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="96b71-133">Если выбрать этот параметр для источника данных, требующего проверки подлинности, соединение завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="96b71-133">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="96b71-134">При выборе этого параметра убедитесь, что настроена учетная запись автоматического выполнения, позволяющая серверу отчетов соединяться с другими компьютерами для получения данных или файлов, если пользовательские учетные данные недоступны.</span><span class="sxs-lookup"><span data-stu-id="96b71-134">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
     <span data-ttu-id="96b71-135">Дополнительные сведения о настройке учетных данных см. в разделе [Указание учетных данных и сведений о соединении для источников данных отчета](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="96b71-135">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="96b71-136">Дополнительные сведения об учетной записи автоматического выполнения см. в разделе [Настройка учетной записи автоматического выполнения (диспетчер конфигурации служб SSRS)](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="96b71-136">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
9. <span data-ttu-id="96b71-137">Нажмите кнопку **Проверить соединение** , чтобы проверить настройку источника данных.</span><span class="sxs-lookup"><span data-stu-id="96b71-137">Click the **Test Connection** button to validate the data source configuration.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="96b71-138">Кнопка проверки соединения не поддерживается для источника типа XML-данных.</span><span class="sxs-lookup"><span data-stu-id="96b71-138">The Test Connection button is not supported for the XML data source type.</span></span>  
  
10. <span data-ttu-id="96b71-139">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="96b71-139">Click **OK**</span></span>  
  
### <a name="to-modify-a-shared-data-source"></a><span data-ttu-id="96b71-140">Изменение общего источника данных</span><span class="sxs-lookup"><span data-stu-id="96b71-140">To modify a shared data source</span></span>  
  
1.  <span data-ttu-id="96b71-141">В диспетчере отчетов перейдите на страницу &lt;ui&gt;Содержимое&lt;/ui&gt;.</span><span class="sxs-lookup"><span data-stu-id="96b71-141">In Report Manager, navigate to the Contents page.</span></span>  
  
2.  <span data-ttu-id="96b71-142">Перейдите к элементу общего источника данных, подведите к нему курсор, щелкните стрелку раскрывающегося списка и в контекстном меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="96b71-142">Navigate to the shared data source item, hover over the item, click the drop-down list, and from the context menu, click **Manage**.</span></span> <span data-ttu-id="96b71-143">Откроется страница **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="96b71-143">The **Properties** page opens.</span></span>  
  
3.  <span data-ttu-id="96b71-144">Измените источник данных, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="96b71-144">Modify the data source, and then click **Apply**.</span></span>  
  
### <a name="to-delete-a-shared-data-source"></a><span data-ttu-id="96b71-145">Удаление общего источника данных</span><span class="sxs-lookup"><span data-stu-id="96b71-145">To delete a shared data source</span></span>  
  
-   <span data-ttu-id="96b71-146">В диспетчере отчетов перейдите на страницу **Содержимое** и выполните одну из следующих последовательностей действий.</span><span class="sxs-lookup"><span data-stu-id="96b71-146">In Report Manager, navigate to the **Contents** page and do one of the following:</span></span>  
  
    -   <span data-ttu-id="96b71-147">Перейдите к совместно используемому элементу источника данных.</span><span class="sxs-lookup"><span data-stu-id="96b71-147">Navigate to the shared data source item.</span></span>  
  
         <span data-ttu-id="96b71-148">Щелкните элемент, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="96b71-148">Click the item to open it.</span></span> <span data-ttu-id="96b71-149">Откроется страница «Общие свойства».</span><span class="sxs-lookup"><span data-stu-id="96b71-149">The General Properties page opens.</span></span>  
  
         <span data-ttu-id="96b71-150">Нажмите кнопку **Удалить**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="96b71-150">Click **Delete**, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="96b71-151">На странице **Содержимое** перейдите к папке, содержащей источник данных, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="96b71-151">In the **Contents** page, navigate to the folder that contains the data source you want to delete.</span></span>  
  
         <span data-ttu-id="96b71-152">Подведите к элементу курсор, щелкните стрелку раскрывающегося списка и в контекстном меню выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="96b71-152">Hover over the item, click the drop-down list, and from the context menu, click **Delete**.</span></span>  
  
         [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="96b71-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="96b71-153">See Also</span></span>  
 <span data-ttu-id="96b71-154">[Подключения к данным, источники данных и строки подключения в Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="96b71-154">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="96b71-155">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="96b71-155">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="96b71-156">[Создание, изменение и удаление общих источников данных &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="96b71-156">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="96b71-157">[Управление источниками данных отчета](report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="96b71-157">[Manage Report Data Sources](report-data/manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="96b71-158">Настройка свойств источника данных для отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="96b71-158">Configure Data Source Properties for a Report  &#40;Report Manager&#41;</span></span>](report-data/configure-data-source-properties-for-a-report-report-manager.md)  
  
  
