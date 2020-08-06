---
title: Создание соединения семантической модели бизнес-аналитики с базой данных табличной модели | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 69b306f6-ee8a-44d2-8f51-0cad2c0bc135
author: minewiskan
ms.author: owend
ms.openlocfilehash: 42b4281050b8672891fc01e8bbeb4b3bc1920c94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666794"
---
# <a name="create-a-bi-semantic-model-connection-to-a-tabular-model-database"></a><span data-ttu-id="9a52e-102">Create a BI Semantic Model Connection to a Tabular Model Database</span><span class="sxs-lookup"><span data-stu-id="9a52e-102">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>
  <span data-ttu-id="9a52e-103">Сведения, приведенные в этом разделе, помогут настроить соединение семантической модели бизнес-аналитики, которое перенаправляется на базу данных табличной модели, запущенную в экземпляре служб Analysis Services за пределами фермы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9a52e-103">Use the information in this topic to set up a BI semantic model connection that redirects to a tabular model database running on an Analysis Services instance outside the SharePoint farm.</span></span>  
  
 <span data-ttu-id="9a52e-104">После создания соединения семантической модели бизнес-аналитики и настройки разрешений SharePoint и служб Analysis Services это соединение можно использовать в качестве источника данных для отчетов Excel или [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a52e-104">After you create a BI semantic model connection and configure SharePoint and Analysis Services permissions, people can use it as a data source for Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span>  
  
 <span data-ttu-id="9a52e-105">Этот раздел включает следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="9a52e-105">This topic includes the following sections.</span></span> <span data-ttu-id="9a52e-106">Выполните задачи в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="9a52e-106">Perform each task in the order given.</span></span>  
  
 [<span data-ttu-id="9a52e-107">Проверка предварительных требований</span><span class="sxs-lookup"><span data-stu-id="9a52e-107">Review Prerequisites</span></span>](#bkmk_prereq)  
  
 [<span data-ttu-id="9a52e-108">Предоставление административных разрешений служб Analysis Services приложениям общих служб</span><span class="sxs-lookup"><span data-stu-id="9a52e-108">Grant Analysis Services Administrative Permissions to Shared Service Applications</span></span>](#bkmk_ssas)  
  
 [<span data-ttu-id="9a52e-109">Предоставление разрешений на чтение для базы данных табличной модели</span><span class="sxs-lookup"><span data-stu-id="9a52e-109">Grant Read Permissions on the Tabular Model Database</span></span>](#bkmk_BISM)  
  
 [<span data-ttu-id="9a52e-110">Create a BI Semantic Model Connection to a Tabular Model Database</span><span class="sxs-lookup"><span data-stu-id="9a52e-110">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](#bkmk_connect)  
  
 [<span data-ttu-id="9a52e-111">Настройка разрешений SharePoint для соединения семантической модели бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="9a52e-111">Configure SharePoint permissions on the BI Semantic Model Connection</span></span>](#bkmk_permissions)  
  
 [<span data-ttu-id="9a52e-112">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9a52e-112">Next Steps</span></span>](#bkmk_next)  
  
##  <a name="review-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="9a52e-113">Проверка предварительных требований</span><span class="sxs-lookup"><span data-stu-id="9a52e-113">Review Prerequisites</span></span>  
 <span data-ttu-id="9a52e-114">Для создания файла соединения семантической модели бизнес-аналитики требуется разрешение «Участие» или выше.</span><span class="sxs-lookup"><span data-stu-id="9a52e-114">You must have Contribute permissions or above to create a BI semantic model connection file.</span></span>  
  
 <span data-ttu-id="9a52e-115">Необходима библиотека, поддерживающая тип содержимого соединения семантической модели бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="9a52e-115">You must have a library that supports the BI semantic model connection content type.</span></span> <span data-ttu-id="9a52e-116">Дополнительные сведения см. в разделе [Добавление типа содержимого соединения семантической модели бизнес-аналитики в библиотеку &#40;PowerPivot для SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span><span class="sxs-lookup"><span data-stu-id="9a52e-116">For more information, see [Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span></span>  
  
 <span data-ttu-id="9a52e-117">Необходимо знать имя сервера и базы данных, для которой настраивается соединение семантической модели бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="9a52e-117">You must know the server and database name for which you are setting up a BI semantic model connection.</span></span> <span data-ttu-id="9a52e-118">Службы Analysis Services должны быть настроены для табличного режима.</span><span class="sxs-lookup"><span data-stu-id="9a52e-118">Analysis Services must be configured for tabular mode.</span></span> <span data-ttu-id="9a52e-119">Базы данных на сервере должны быть табличным шаблоном баз данных.</span><span class="sxs-lookup"><span data-stu-id="9a52e-119">Databases running on the server must be tabular model databases.</span></span> <span data-ttu-id="9a52e-120">Инструкции по проверке режима сервера см. в разделе [Определение режима работы сервера экземпляра служб Analysis Services](../instances/determine-the-server-mode-of-an-analysis-services-instance.md).</span><span class="sxs-lookup"><span data-stu-id="9a52e-120">For instructions on how to check for server mode, see [Determine the Server Mode of an Analysis Services Instance](../instances/determine-the-server-mode-of-an-analysis-services-instance.md).</span></span>  
  
 <span data-ttu-id="9a52e-121">В некоторых сценариях общие службы в среде SharePoint должны иметь административные разрешения в экземпляре служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9a52e-121">In certain scenarios, the shared services in a SharePoint environment must have administrative permissions on the Analysis Services instance.</span></span> <span data-ttu-id="9a52e-122">К таким службам относятся приложения службы PowerPivot, приложения службы Reporting Services и приложения службы PerformancePoint.</span><span class="sxs-lookup"><span data-stu-id="9a52e-122">These services include PowerPivot service applications, Reporting Services service applications, and PerformancePoint service applications.</span></span> <span data-ttu-id="9a52e-123">Перед предоставлением административных разрешений необходимо проверить удостоверение этих приложений службы.</span><span class="sxs-lookup"><span data-stu-id="9a52e-123">Before you can grant administrative permissions, you must know the identity of these service applications.</span></span> <span data-ttu-id="9a52e-124">Для определения удостоверения используется центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="9a52e-124">You can use Central Administration to determine the identity.</span></span>  
  
 <span data-ttu-id="9a52e-125">Для просмотра сведений о безопасности в центре администрирования требуются права администратора служб SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9a52e-125">You must be a SharePoint service administrator to view security information in Central Administration.</span></span>  
  
 <span data-ttu-id="9a52e-126">Для предоставления административных прав в среде Management Studio требуются права системного администратора служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9a52e-126">You must be an Analysis Services system administrator to grant administrative rights in Management Studio.</span></span>  
  
 <span data-ttu-id="9a52e-127">Доступ к PowerPivot для SharePoint осуществляется посредством веб-приложений, использующих классический режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9a52e-127">PowerPivot for SharePoint must be accessed via web applications that use classic authentication mode.</span></span> <span data-ttu-id="9a52e-128">Соединение семантической модели бизнес-аналитики с внешними источниками данных имеет зависимость от входа в систему в классическом режиме.</span><span class="sxs-lookup"><span data-stu-id="9a52e-128">BI semantic model connections to external data sources have a dependency on classic mode sign-in.</span></span> <span data-ttu-id="9a52e-129">Дополнительные сведения см. в статье [Проверка подлинности и авторизация PowerPivot](power-pivot-authentication-and-authorization.md).</span><span class="sxs-lookup"><span data-stu-id="9a52e-129">For more information, see [PowerPivot Authentication and Authorization](power-pivot-authentication-and-authorization.md).</span></span>  
  
 <span data-ttu-id="9a52e-130">Все компьютеры и пользователи, участвующие в последовательности соединения, должны относиться к одному домену или находиться в доверенном домене (двустороннее доверие).</span><span class="sxs-lookup"><span data-stu-id="9a52e-130">All computers and users that participate in the connection sequence must be in the same domain or trusted domain (two-way trust).</span></span>  
  
##  <a name="grant-analysis-services-administrative-permissions-to-shared-service-applications"></a><a name="bkmk_ssas"></a><span data-ttu-id="9a52e-131">Предоставление Analysis Services административных разрешений для приложений общих служб</span><span class="sxs-lookup"><span data-stu-id="9a52e-131">Grant Analysis Services Administrative Permissions to Shared Service Applications</span></span>  
 <span data-ttu-id="9a52e-132">Соединения от SharePoint к базе данных табличной модели на сервере служб Analysis Services иногда устанавливаются общей службой от имени пользователя, запрашивающего данные.</span><span class="sxs-lookup"><span data-stu-id="9a52e-132">Connections that originate from SharePoint to a tabular model database on an Analysis Services server are sometimes made by a shared service on behalf of the user requesting the data.</span></span> <span data-ttu-id="9a52e-133">Служба, создающая запрос, может быть приложением службы PowerPivot, приложением службы Reporting Services или приложением службы PerformancePoint.</span><span class="sxs-lookup"><span data-stu-id="9a52e-133">The service making the request might be a PowerPivot service application, a Reporting Services service application, or a PerformancePoint service application.</span></span> <span data-ttu-id="9a52e-134">Для успешного соединения служба должна иметь административные разрешения на сервере служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9a52e-134">In order for the connection to succeed, the service must have administrative permissions on the Analysis Services server.</span></span> <span data-ttu-id="9a52e-135">На сервере служб Analysis Services только администратор может устанавливать олицетворенные соединения от имени других пользователей.</span><span class="sxs-lookup"><span data-stu-id="9a52e-135">In Analysis Services, only an administrator is allowed to make an impersonated connection on behalf of another user.</span></span>  
  
 <span data-ttu-id="9a52e-136">Административные разрешения необходимы, если соединение используется в следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="9a52e-136">Administrative permissions are necessary when the connection is used under these conditions:</span></span>  
  
-   <span data-ttu-id="9a52e-137">Проверяются сведения о соединении при настройке файла соединения с семантической моделью бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="9a52e-137">When verifying the connection information during the configuration of a BI semantic model connection file.</span></span>  
  
-   <span data-ttu-id="9a52e-138">Отчет Power View запускается с помощью соединения с семантической моделью бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="9a52e-138">When starting a Power View report using a BI semantic model connection.</span></span>  
  
-   <span data-ttu-id="9a52e-139">Веб-часть PerformancePoint заполняется с использованием соединения с семантической моделью бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="9a52e-139">When populating a PerformancePoint web part using a BI semantic model connection.</span></span>  
  
 <span data-ttu-id="9a52e-140">Чтобы обеспечить надлежащую работу этих функций, предоставьте каждому удостоверению службы административные разрешения в экземпляре служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9a52e-140">To ensure these behaviors perform as expected, grant to each service identity administrative permissions on the Analysis Services instance.</span></span> <span data-ttu-id="9a52e-141">Чтобы предоставить необходимые разрешения, выполните следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="9a52e-141">Use the following instructions to grant the necessary permission.</span></span>  
  
 <span data-ttu-id="9a52e-142">**Добавьте удостоверения служб в роль «Администратор сервера».**</span><span class="sxs-lookup"><span data-stu-id="9a52e-142">**Add service identities to the Server Administrator role**</span></span>  
  
1.  <span data-ttu-id="9a52e-143">Установите соединение с экземпляром служб Analysis Services в среде SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="9a52e-143">In SQL Server Management Studio, connect to the Analysis Services instance.</span></span>  
  
2.  <span data-ttu-id="9a52e-144">Щелкните имя сервера правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-144">Right-click the server name and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="9a52e-145">Щелкните **Безопасность**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-145">Click **Security**, and then click **Add**.</span></span> <span data-ttu-id="9a52e-146">Введите данные учетной записи пользователя Windows, которая используется для выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="9a52e-146">Enter the Windows user account that is used to run the service application.</span></span>  
  
     <span data-ttu-id="9a52e-147">Для определения удостоверения используется центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="9a52e-147">You can use Central Administration to determine the identity.</span></span> <span data-ttu-id="9a52e-148">В разделе "Безопасность" откройте окно **Настройка учетных записей служб** , чтобы просмотреть, какая учетная запись Windows связана с пулом приложений службы, используемым для каждого приложения, а затем выполните инструкции из этого раздела, чтобы предоставить учетной записи административные разрешения.</span><span class="sxs-lookup"><span data-stu-id="9a52e-148">In the Security section, open the **Configure service accounts** to view which Windows account is associated with the service application pool used for each application, then follow the instructions provided in this topic to grant the account administrative permissions.</span></span>  
  
##  <a name="grant-read-permissions-on-the-tabular-model-database"></a><a name="bkmk_BISM"></a> <span data-ttu-id="9a52e-149">Предоставление разрешений на чтение табличного шаблона базы данных</span><span class="sxs-lookup"><span data-stu-id="9a52e-149">Grant Read Permissions on the Tabular Model Database</span></span>  
 <span data-ttu-id="9a52e-150">Поскольку база данных запущена на сервере за пределами фермы, частью настройки соединения является предоставление административных и пользовательских разрешений для внутреннего сервера служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9a52e-150">Because the database is running on a server that is external to the farm, part of setting up your connections will include granting database user permissions on the backend Analysis Services server.</span></span> <span data-ttu-id="9a52e-151">Службы Analysis Services используют модель разрешений на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="9a52e-151">Analysis Services uses a role-based permission model.</span></span> <span data-ttu-id="9a52e-152">Пользователи, подключающиеся к шаблонам базы данных, должны иметь разрешения «Чтение» или выше, которые они получили от роли, предоставляющей своим членам разрешения на чтение.</span><span class="sxs-lookup"><span data-stu-id="9a52e-152">Users who connect to model databases must do so with Read permissions or higher, through a role that grants read access to its members.</span></span>  
  
 <span data-ttu-id="9a52e-153">Роли, а иногда членство в ролях, определяются при создании модели в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a52e-153">Roles, and sometimes role membership, are defined when the model is created in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="9a52e-154">Для создания ролей нельзя использовать среду SQL Server Management Studio, однако ее можно использовать для добавления членов в уже определенную роль.</span><span class="sxs-lookup"><span data-stu-id="9a52e-154">You cannot use SQL Server Management Studio to create roles, but you can use it to add members to a role that is already defined.</span></span> <span data-ttu-id="9a52e-155">Дополнительные сведения о создании ролей см. в разделе [Создание ролей и управление ими (табличные службы SSAS)](../tabular-models/roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="9a52e-155">For more information about creating roles, see [Create and Manage Roles &#40;SSAS Tabular&#41;](../tabular-models/roles-ssas-tabular.md).</span></span>  
  
#### <a name="assign-role-membership"></a><span data-ttu-id="9a52e-156">Назначение членства в ролях</span><span class="sxs-lookup"><span data-stu-id="9a52e-156">Assign role membership</span></span>  
  
1.  <span data-ttu-id="9a52e-157">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]выполните подключение к экземпляру [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], разверните в обозревателе объектов базу данных, а затем узел **Роли**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-157">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], expand the database in Object Explorer, and then expand **Roles**.</span></span> <span data-ttu-id="9a52e-158">В списке должна быть уже определенная роль.</span><span class="sxs-lookup"><span data-stu-id="9a52e-158">You should see a role that is already defined.</span></span> <span data-ttu-id="9a52e-159">Если роль не существует, свяжитесь с автором модели и попросите его добавить роль.</span><span class="sxs-lookup"><span data-stu-id="9a52e-159">If a role does not exist, contact the author of the model and request the addition or a role.</span></span> <span data-ttu-id="9a52e-160">Модель должна быть развернута повторно, прежде чем роль появится в среде Management Studio.</span><span class="sxs-lookup"><span data-stu-id="9a52e-160">The model must be redeployed before the role is visible in Management Studio.</span></span>  
  
2.  <span data-ttu-id="9a52e-161">Щелкните правой кнопкой мыши роль и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-161">Right-click the role, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="9a52e-162">На странице «Членство» добавьте группу Windows и учетные записи пользователей, которым требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="9a52e-162">In the Membership page, add the Windows group and user accounts that require access.</span></span>  
  
##  <a name="create-a-bi-semantic-model-connection-to-a-tabular-model-database"></a><a name="bkmk_connect"></a><span data-ttu-id="9a52e-163">Создание соединения семантической модели бизнес-аналитики с базой данных табличной модели</span><span class="sxs-lookup"><span data-stu-id="9a52e-163">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>  
 <span data-ttu-id="9a52e-164">После задания разрешений в службах Analysis Services можно вернуться в SharePoint и создать соединение семантической модели бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="9a52e-164">After you set permissions in Analysis Services, you can return to SharePoint and create a BI semantic model connection.</span></span>  
  
1.  <span data-ttu-id="9a52e-165">В библиотеке, в которой будет размещаться соединение семантической модели бизнес-аналитики, нажмите кнопку **Документы** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9a52e-165">In the library that will contain the BI semantic model connection, click **Documents** on the SharePoint ribbon.</span></span>  
  
2.  <span data-ttu-id="9a52e-166">Щелкните стрелку вниз на кнопке "Новый документ" и выберите **Файл соединения BISM** , чтобы открыть страницу "Создание соединения BISM".</span><span class="sxs-lookup"><span data-stu-id="9a52e-166">Click the down arrow on New Document, and select **BI Semantic Model Connection File** to open the New BI Semantic Model Connection page.</span></span>  
  
3.  <span data-ttu-id="9a52e-167">Задайте значения свойств **Сервер** и **База данных** .</span><span class="sxs-lookup"><span data-stu-id="9a52e-167">Set both **Server** and **Database** properties.</span></span> <span data-ttu-id="9a52e-168">Если имя базы данных неизвестно, просмотрите список баз данных, развернутых на сервере, с помощью среды SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="9a52e-168">If you are unsure of the database name, use SQL Server Management Studio to view a list of the databases that are deployed on the server.</span></span>  
  
     <span data-ttu-id="9a52e-169">**Имя сервера** — это сетевое имя сервера, IP-адрес или полное доменное имя (например: myserver.mydomain.corp.adventure-works.com).</span><span class="sxs-lookup"><span data-stu-id="9a52e-169">**Server name** is either the network name of the server, the IP address, or the fully qualified domain name (for example, myserver.mydomain.corp.adventure-works.com).</span></span> <span data-ttu-id="9a52e-170">Если сервер установлен как именованный экземпляр, введите имя сервера в следующем формате: имя_компьютера\имя_экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9a52e-170">If the server is installed as a named instance, enter the server name in this format: computername\instancename.</span></span>  
  
     <span data-ttu-id="9a52e-171">**База данных** должна быть табличной базой данных, доступной на сервере.</span><span class="sxs-lookup"><span data-stu-id="9a52e-171">**Database** must be a tabular database that is currently available on the server.</span></span> <span data-ttu-id="9a52e-172">Не указывайте другой файл соединения BISM, ODC-файл, базу данных OLAP служб Analysis Services или книгу PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9a52e-172">Do not specify another BI semantic model connection file, an Office Data Connection (.odc) file, an Analysis Services OLAP database, or a PowerPivot workbook.</span></span> <span data-ttu-id="9a52e-173">Для получения имени базы данных воспользуйтесь средой Management Studio для подключения к серверу и просмотра списка доступных баз данных.</span><span class="sxs-lookup"><span data-stu-id="9a52e-173">To get the database name, you can use Management Studio to connect to the server and view the list of available databases.</span></span> <span data-ttu-id="9a52e-174">Чтобы проверить имя, перейдите на страницу свойств базы данных.</span><span class="sxs-lookup"><span data-stu-id="9a52e-174">Use the property page of the database to ensure you have the correct name.</span></span>  
  
4.  <span data-ttu-id="9a52e-175">Нажмите кнопку **ОК** , чтобы сохранить страницу.</span><span class="sxs-lookup"><span data-stu-id="9a52e-175">Click **OK** to save the page.</span></span> <span data-ttu-id="9a52e-176">В этот момент приложение службы PowerPivot проверяет соединение.</span><span class="sxs-lookup"><span data-stu-id="9a52e-176">At this point, the PowerPivot service application will verify the connection.</span></span>  
  
     <span data-ttu-id="9a52e-177">Проверка завершается успешно, если правильно заданы сведения о соединении и предоставлены административные разрешения приложению службы PowerPivot, которые позволяют подключаться к службам Analysis Services от имени текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a52e-177">Verification succeeds if the connection information is correct, and you have granted administrative permissions to the PowerPivot service application so that it can connect to Analysis Services as the current user.</span></span>  
  
     <span data-ttu-id="9a52e-178">Проверка завершается ошибкой, если сведения о соединении заданы неправильно или у приложения службы отсутствуют необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="9a52e-178">Verification fails if the connection information is wrong, or the service application lacks permissions.</span></span> <span data-ttu-id="9a52e-179">На странице появится сообщение проверки, предлагающее сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="9a52e-179">A validation message will appear on the page asking whether you want to save the file.</span></span> <span data-ttu-id="9a52e-180">Если известно, что соединение задано правильно, следует сохранить файл, поскольку ошибка возникает в результате отсутствия разрешений, а не ошибочных сведений о соединении.</span><span class="sxs-lookup"><span data-stu-id="9a52e-180">If you know that the connection is valid, you should save the file anyway, because the error is the result of missing permissions rather than invalid connection information.</span></span>  
  
     <span data-ttu-id="9a52e-181">Можно проверить соединение в Excel или Power View, установив подключение к базе данных табличной модели.</span><span class="sxs-lookup"><span data-stu-id="9a52e-181">You can verify the connection by using it in Excel or Power View to connect to tabular model database.</span></span> <span data-ttu-id="9a52e-182">Если подключение к источнику данных устанавливается успешно, то соединение задано правильно несмотря на то, что в ходе проверки создано предупреждение.</span><span class="sxs-lookup"><span data-stu-id="9a52e-182">If the data source connection succeeds, the connection is valid despite the verification warning.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-bi-semantic-model-connection"></a><a name="bkmk_permissions"></a><span data-ttu-id="9a52e-183">Настройка разрешений SharePoint для соединения семантической модели бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="9a52e-183">Configure SharePoint permissions on the BI Semantic Model Connection</span></span>  
 <span data-ttu-id="9a52e-184">Для использования соединения семантической модели бизнес-аналитики в качестве источника данных для книги Excel или отчета служб Reporting Services необходимо разрешение **Чтение** для элемента соединения семантической модели бизнес-аналитики в библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9a52e-184">Ability to use a BI semantic model connection as a data source for an Excel workbook or Reporting Services report requires **Read** permissions on the BI semantic model connection item in a SharePoint library.</span></span> <span data-ttu-id="9a52e-185">Уровень разрешения "Чтение" включает разрешение **Открытие элементов** , которое позволяет загружать сведения о соединении семантической модели бизнес-аналитики в приложение Excel для рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="9a52e-185">The Read permission level includes the **Open Items** permission that enables downloading BI semantic model connection information to an Excel desktop application.</span></span>  
  
 <span data-ttu-id="9a52e-186">В SharePoint имеется несколько способов предоставления разрешений.</span><span class="sxs-lookup"><span data-stu-id="9a52e-186">There are several ways to grant permissions in SharePoint.</span></span> <span data-ttu-id="9a52e-187">В следующей процедуре описывается создание новой группы с именем **Пользователи BISM** , которая получает уровень разрешений **Чтение** .</span><span class="sxs-lookup"><span data-stu-id="9a52e-187">The following instructions explain how to create a new group called **BISM Users** that have the **Read** permission level.</span></span>  
  
 <span data-ttu-id="9a52e-188">Изменять разрешения могут только владельцы сайтов.</span><span class="sxs-lookup"><span data-stu-id="9a52e-188">You must be a site owner to change permissions.</span></span>  
  
1.  <span data-ttu-id="9a52e-189">В разделе "Действия сайта" щелкните **Разрешения сайта**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-189">In Site Actions, click **Site Permissions**.</span></span>  
  
2.  <span data-ttu-id="9a52e-190">Щелкните **Создать группу** и укажите для новой группы имя **Пользователи BISM**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-190">Click **Create Group** and name the new group **BISM Users**.</span></span>  
  
3.  <span data-ttu-id="9a52e-191">Выберите уровень разрешений **Чтение** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-191">Choose the **Read** permission level and click **Create**.</span></span>  
  
4.  <span data-ttu-id="9a52e-192">Выберите **Пользователи BISM** в поле "Пользователи и группы".</span><span class="sxs-lookup"><span data-stu-id="9a52e-192">Select **BISM Users** in People and Groups.</span></span>  
  
5.  <span data-ttu-id="9a52e-193">Наведите указатель мыши на пункт "Создать", выберите **Добавить пользователей**и добавьте учетные записи пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="9a52e-193">Point to New, click **Add Users**, and then add user or group accounts.</span></span>  
  
     <span data-ttu-id="9a52e-194">Теперь у этих пользователей и групп будет разрешение «Чтение» для всего сайта, включая все библиотеки и списки, которые наследуют разрешения на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="9a52e-194">These users and groups will now have Read permissions throughout the site, including all libraries and lists that inherit permissions from the site level.</span></span> <span data-ttu-id="9a52e-195">Если эти разрешения оказываются слишком большими, можно удалить данную группу из определенных библиотек, списков или элементов.</span><span class="sxs-lookup"><span data-stu-id="9a52e-195">If these permissions are too high, you can selectively remove this group from specific libraries, lists, or items.</span></span>  
  
 <span data-ttu-id="9a52e-196">Чтобы выборочно удалить разрешения на уровне элемента, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9a52e-196">To selectively remove permissions at the item level, do the following:</span></span>  
  
1.  <span data-ttu-id="9a52e-197">Выберите документ в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="9a52e-197">In a library, select a document.</span></span> <span data-ttu-id="9a52e-198">Нажмите правую кнопку со стрелкой вниз и выберите пункт **Управление разрешениями**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-198">Click the right down arrow and then click **Manage Permissions**.</span></span>  
  
2.  <span data-ttu-id="9a52e-199">По умолчанию элемент наследует разрешения.</span><span class="sxs-lookup"><span data-stu-id="9a52e-199">By default, an item inherits permissions.</span></span> <span data-ttu-id="9a52e-200">Чтобы изменить разрешения для отдельных документов в этой библиотеке, нажмите кнопку **Прекратить наследование разрешений**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-200">To change the permissions of individual documents in this library, click **Stop Inheriting Permissions**.</span></span>  
  
3.  <span data-ttu-id="9a52e-201">Установите флажок для группы **Пользователи BISM**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-201">Select the checkbox next to **BISM Users**.</span></span>  
  
4.  <span data-ttu-id="9a52e-202">Нажмите кнопку **Удалить разрешения пользователя**.</span><span class="sxs-lookup"><span data-stu-id="9a52e-202">Click **Remove User Permissions**.</span></span>  
  
##  <a name="next-steps"></a><a name="bkmk_next"></a> <span data-ttu-id="9a52e-203">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="9a52e-203">Next Steps</span></span>  
 <span data-ttu-id="9a52e-204">После создания и обеспечения безопасности соединения семантической модели бизнес-аналитики его можно указать в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="9a52e-204">After you create and secure a BI semantic model connection, you can specify it as a data source.</span></span> <span data-ttu-id="9a52e-205">Дополнительные сведения см. в разделе [Использование соединения семантической модели бизнес-аналитики в службах Excel или Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a52e-205">For more information, see [Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a52e-206">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a52e-206">See Also</span></span>  
 <span data-ttu-id="9a52e-207">[Соединение семантической модели бизнес-аналитики PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="9a52e-207">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 [<span data-ttu-id="9a52e-208">Создание соединения семантической модели бизнес-аналитики с книгой PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9a52e-208">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>](create-a-bi-semantic-model-connection-to-a-power-pivot-workbook.md)  
  
  