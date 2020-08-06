---
title: Создание сервера централизованного управления и группы
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- configuration server
ms.assetid: da265482-3953-440a-ac23-0ab7e42a55eb
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f53b75966a14dbc6fd6cdc9bea0929ccac7780c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727849"
---
# <a name="create-a-central-management-server-and-server-group-sql-server-management-studio"></a><span data-ttu-id="77a9f-102">Создание центрального сервера управления и группы сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="77a9f-102">Create a Central Management Server and Server Group (SQL Server Management Studio)</span></span>
  <span data-ttu-id="77a9f-103">В этом разделе описывается, как назначить экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в качестве сервера централизованного управления в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77a9f-103">This topic describes how to designate an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a central management server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="77a9f-104">На серверах централизованного управления хранится список экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , организованных в одну или несколько групп серверов централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="77a9f-104">Central management servers store a list of instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is organized into one or more central management server groups.</span></span> <span data-ttu-id="77a9f-105">Действия, производимые с помощью группы серверов централизованного управления, влияют на все серверы в группе.</span><span class="sxs-lookup"><span data-stu-id="77a9f-105">Actions that are taken by using a central management server group act on all servers in the server group.</span></span> <span data-ttu-id="77a9f-106">Это включает соединение с сервером при помощи обозревателя объектов, а также выполнение инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] и применение политик управления на основе политик одновременно на нескольких серверах.</span><span class="sxs-lookup"><span data-stu-id="77a9f-106">This includes connecting to servers by using Object Explorer and executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and Policy-Based Management policies on multiple servers at the same time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77a9f-107">Версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ранее [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] нельзя назначить в качестве сервера централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="77a9f-107">Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] cannot be designated as a central management server.</span></span>  
  
 <span data-ttu-id="77a9f-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="77a9f-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="77a9f-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="77a9f-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="77a9f-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="77a9f-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="77a9f-111">**Для создания сервера централизованного управления и группы серверов используется:**</span><span class="sxs-lookup"><span data-stu-id="77a9f-111">**To create a Central Management Server and Server Group, using:**</span></span>  
  
     [<span data-ttu-id="77a9f-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77a9f-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="77a9f-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="77a9f-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="77a9f-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="77a9f-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="77a9f-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="77a9f-115">Permissions</span></span>  
 <span data-ttu-id="77a9f-116">В базе данных msdb доступ к серверам централизованного управления предоставляют две роли базы данных.</span><span class="sxs-lookup"><span data-stu-id="77a9f-116">Two database roles in the msdb database grant access to central management servers.</span></span> <span data-ttu-id="77a9f-117">Сервером централизованного управления могут управлять только члены роли ServerGroupAdministratorRole.</span><span class="sxs-lookup"><span data-stu-id="77a9f-117">Only members of the ServerGroupAdministratorRole role can manage the central management server.</span></span> <span data-ttu-id="77a9f-118">Для подключения к серверу централизованного управления требуется членство в роли ServerGroupReaderRole.</span><span class="sxs-lookup"><span data-stu-id="77a9f-118">Membership in the ServerGroupReaderRole role is required to connect to a central management server.</span></span>  
  
 <span data-ttu-id="77a9f-119">Поскольку соединения, поддерживаемые сервером централизованного управления, выполняются в контексте пользователя с применением проверки подлинности Windows, действующие разрешения на зарегистрированные серверы могут быть различными.</span><span class="sxs-lookup"><span data-stu-id="77a9f-119">Because the connections that are maintained by a central management server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="77a9f-120">Например, пользователь может входить в предопределенную роль сервера sysadmin на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] А, но иметь ограниченные разрешения на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Б.</span><span class="sxs-lookup"><span data-stu-id="77a9f-120">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="77a9f-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77a9f-121">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="77a9f-122">Ниже описывается, как выполнить следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="77a9f-122">The following procedures describe how to perform the following steps.</span></span>  
  
1.  <span data-ttu-id="77a9f-123">Создание сервера централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="77a9f-123">Create a central management server.</span></span>  
  
2.  <span data-ttu-id="77a9f-124">Добавление одной или нескольких групп серверов на центральный сервер управления или добавление одного или нескольких зарегистрированных серверов в группы серверов.</span><span class="sxs-lookup"><span data-stu-id="77a9f-124">Add one or more server groups to the central management server and add one or more registered servers to the server groups.</span></span>  
  
#### <a name="create-a-central-management-server"></a><span data-ttu-id="77a9f-125">Создание сервера централизованного управления</span><span class="sxs-lookup"><span data-stu-id="77a9f-125">Create a central management server</span></span>  
  
1.  <span data-ttu-id="77a9f-126">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите пункт **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="77a9f-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="77a9f-127">В окне "Зарегистрированные серверы" разверните узел **Компонент Database Engine**, щелкните правой кнопкой мыши **Серверы централизованного управления**и выберите пункт **Зарегистрировать сервер централизованного управления**.</span><span class="sxs-lookup"><span data-stu-id="77a9f-127">In Registered Servers, expand **Database Engine**, right-click **Central Management Servers**, and then  click **Register Central Management Server**.</span></span>  
  
3.  <span data-ttu-id="77a9f-128">В диалоговом окне **Регистрация нового сервера** выберите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который необходимо сделать сервером централизованного управления из раскрывающегося списка серверов.</span><span class="sxs-lookup"><span data-stu-id="77a9f-128">In the **New Server Registration** dialog box, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to become the central management server from the drop-down list of servers.</span></span> <span data-ttu-id="77a9f-129">Для сервера централизованного управления необходимо использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="77a9f-129">You must use Windows Authentication for the central management server.</span></span>  
  
4.  <span data-ttu-id="77a9f-130">В поле **Зарегистрированный сервер**введите имя сервера и описание (необязательно).</span><span class="sxs-lookup"><span data-stu-id="77a9f-130">In **Registered Server**, enter a server name and optional description.</span></span>  
  
5.  <span data-ttu-id="77a9f-131">На вкладке **Свойства подключения** просмотрите или измените свойства сети и подключения.</span><span class="sxs-lookup"><span data-stu-id="77a9f-131">From the **Connection Properties** tab, review or modifiy the network  and connection properties.</span></span> <span data-ttu-id="77a9f-132">Дополнительные сведения см. в статье [Соединение с сервером (страница "Свойства подключения"), компонент Database Engine](../f1-help/connect-to-server-connection-properties-page-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="77a9f-132">For more information, see [Connect to Server &#40;Connection Properties Page&#41; Database Engine](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span></span>  
  
6.  <span data-ttu-id="77a9f-133">Нажмите кнопку **Проверка**, чтобы проверить соединение.</span><span class="sxs-lookup"><span data-stu-id="77a9f-133">Click **Test**, to test the connection.</span></span>  
  
7.  <span data-ttu-id="77a9f-134">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="77a9f-134">Click **Save**.</span></span> <span data-ttu-id="77a9f-135">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] появится в папке **Серверы централизованного управления** .</span><span class="sxs-lookup"><span data-stu-id="77a9f-135">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will appear under the **Central Management Servers** folder.</span></span>  
  
#### <a name="create-a-new-server-group-and-add-servers-to-the-group"></a><span data-ttu-id="77a9f-136">Создание группы серверов и добавление в нее серверов</span><span class="sxs-lookup"><span data-stu-id="77a9f-136">Create a new server group and add servers to the group</span></span>  
  
1.  <span data-ttu-id="77a9f-137">В окне **Зарегистрированные серверы**разверните узел **Серверы централизованного управления**.</span><span class="sxs-lookup"><span data-stu-id="77a9f-137">From **Registered Servers**, expand **Central Management Servers**.</span></span> <span data-ttu-id="77a9f-138">Щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , добавленный в предыдущей процедуре, и выберите пункт **Создать группу серверов**.</span><span class="sxs-lookup"><span data-stu-id="77a9f-138">Right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] added in the procedure above and select **New Server Group**.</span></span>  
  
2.  <span data-ttu-id="77a9f-139">В окне **Свойства новой группы серверов**введите имя группы и описание (необязательно).</span><span class="sxs-lookup"><span data-stu-id="77a9f-139">In **New Server Group Properties**, enter a group name and optional description.</span></span>  
  
3.  <span data-ttu-id="77a9f-140">В окне **Зарегистрированные серверы**щелкните правой кнопкой мыши группу серверов и выберите команду **Регистрация нового сервера**.</span><span class="sxs-lookup"><span data-stu-id="77a9f-140">From **Registered Servers**, right-click the server group and click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="77a9f-141">В окне регистрации сервера выберите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77a9f-141">From New Server Registration, select an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="77a9f-142">Дополнительные сведения см. в статье [Создание нового зарегистрированного сервера (среда SQL Server Management Studio)](create-a-new-registered-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="77a9f-142">For more information, see [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span></span> <span data-ttu-id="77a9f-143">При необходимости добавьте дополнительные серверы.</span><span class="sxs-lookup"><span data-stu-id="77a9f-143">Add more servers as appropriate.</span></span>  
  
#### <a name="to-execute-queries-against-several-configuration-targets-at-the-same-time"></a><span data-ttu-id="77a9f-144">Выполнение запросов одновременно к нескольким целям конфигурации</span><span class="sxs-lookup"><span data-stu-id="77a9f-144">To execute queries against several configuration targets at the same time</span></span>  
  
-   <span data-ttu-id="77a9f-145">После создания сервера централизованного управления, одной или нескольких групп серверов и одного или нескольких зарегистрированных серверов можно выполнять запросы одновременно ко всей группе.</span><span class="sxs-lookup"><span data-stu-id="77a9f-145">After you create a central management server, one or more server groups, and one or more registered servers, you can execute queries against a whole group at the same time.</span></span> <span data-ttu-id="77a9f-146">Дополнительные сведения о выполнении инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] сразу на нескольких серверах в группе серверов см. в статье [Выполнение инструкции на нескольких серверах одновременно (среда SQL Server Management Studio)](execute-statements-against-multiple-servers-simultaneously.md).</span><span class="sxs-lookup"><span data-stu-id="77a9f-146">For more information about how to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on the servers in a server group at the same time, see [Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a9f-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="77a9f-147">See Also</span></span>  
 [<span data-ttu-id="77a9f-148">Администрирование нескольких серверов с использованием центральных серверов управления</span><span class="sxs-lookup"><span data-stu-id="77a9f-148">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
