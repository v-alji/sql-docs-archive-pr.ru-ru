---
title: Выполнение инструкций на нескольких серверах одновременно
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- executing queries against multiple servers
- queries [SQL Server], multiserver
ms.assetid: 197760f3-0a06-43de-8162-69c27d3fbe56
author: markingmyname
ms.author: maghan
ms.openlocfilehash: b94775029a1501d3e894d84ef4a027fc1595dc10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733437"
---
# <a name="execute-statements-against-multiple-servers-simultaneously-sql-server-management-studio"></a><span data-ttu-id="8166f-102">Execute Statements Against Multiple Servers Simultaneously (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8166f-102">Execute Statements Against Multiple Servers Simultaneously (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8166f-103">В этом разделе описывается, как в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]выполнить запросы к нескольким серверам одновременно путем создания локальной группы серверов либо создать сервер централизованного управления и одну или несколько групп серверов, затем создать один или несколько зарегистрированных серверов в группах и выполнить запрос ко всей группе.</span><span class="sxs-lookup"><span data-stu-id="8166f-103">This topic describes how to query multiple servers at the same time in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], by creating a local server group, or a Central Management Server and one or more server groups, and one or more registered servers within the groups, and then querying the complete group.</span></span> <span data-ttu-id="8166f-104">Результаты, возвращенные запросом, можно объединить в одну панель результатов или вернуть в отдельные панели результатов.</span><span class="sxs-lookup"><span data-stu-id="8166f-104">The results that are returned by the query can be combined into a single results pane, or can be returned in separate results panes.</span></span> <span data-ttu-id="8166f-105">Набор результатов может включать дополнительные столбцы для имени сервера и имени входа, используемые для запроса к каждому серверу.</span><span class="sxs-lookup"><span data-stu-id="8166f-105">The results set can include additional columns for the server name and the login that is used by the query on each server.</span></span> <span data-ttu-id="8166f-106">Центральные серверы управления и подчиненные серверы могут быть зарегистрированы с применением проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="8166f-106">Central Management Servers and subordinate servers can be registered by using only Windows Authentication.</span></span> <span data-ttu-id="8166f-107">Серверы в локальных группах серверов можно зарегистрировать с использованием проверки подлинности Windows или проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8166f-107">Servers in local server groups can be registered by using Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8166f-108">Перед выполнением следующих процедур создайте центральный сервер управления и группы серверов.</span><span class="sxs-lookup"><span data-stu-id="8166f-108">Before you execute the following procedures, create a Central Management Server and server groups.</span></span> <span data-ttu-id="8166f-109">Дополнительные сведения см. в разделе [Создание центрального сервера управления и группы серверов (среда SQL Server Management Studio)](create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="8166f-109">For more information, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span></span>  
  
 <span data-ttu-id="8166f-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8166f-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8166f-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8166f-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8166f-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8166f-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8166f-113">**Для выполнения инструкций на нескольких серверах используется:**</span><span class="sxs-lookup"><span data-stu-id="8166f-113">**To execute statements against multiple servers, using:**</span></span>  
  
     [<span data-ttu-id="8166f-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8166f-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8166f-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8166f-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8166f-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="8166f-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8166f-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="8166f-117">Permissions</span></span>  
 <span data-ttu-id="8166f-118">Поскольку соединения, поддерживаемые центральным сервером управления, выполняются в контексте пользователя с применением проверки подлинности Windows, действующие разрешения на зарегистрированные серверы могут быть различными.</span><span class="sxs-lookup"><span data-stu-id="8166f-118">Because the connections maintained by a Central Management Server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="8166f-119">Например, пользователь может входить в предопределенную роль сервера sysadmin на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] А, но иметь ограниченные разрешения на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Б.</span><span class="sxs-lookup"><span data-stu-id="8166f-119">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8166f-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8166f-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-statements-against-multiple-configuration-targets-simultaneously"></a><span data-ttu-id="8166f-121">Выполнение инструкций на нескольких целях конфигурации одновременно</span><span class="sxs-lookup"><span data-stu-id="8166f-121">To execute statements against multiple configuration targets simultaneously</span></span>  
  
1.  <span data-ttu-id="8166f-122">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите пункт **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="8166f-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="8166f-123">Разверните центральный сервер управления, щелкните правой кнопкой мыши группу серверов, укажите пункт **Соединить**и выберите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8166f-123">Expand a Central Management Server, right-click a server group, point to **Connect**, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8166f-124">Введите и выполните инструкцию языка [!INCLUDE[tsql](../../includes/tsql-md.md)] в редакторе запросов, например, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="8166f-124">In Query Editor, type and execute a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as the following:</span></span>  
  
    ```  
    USE master  
    GO  
    SELECT * FROM sysdatabases;  
    GO  
    ```  
  
     <span data-ttu-id="8166f-125">По умолчанию панель результатов объединит результаты запросов со всех серверов группы.</span><span class="sxs-lookup"><span data-stu-id="8166f-125">By default, the results pane will combine the query results from all the servers in the server group.</span></span>  
  
#### <a name="to-change-the-multiserver-results-options"></a><span data-ttu-id="8166f-126">Изменение параметров многосерверных результатов</span><span class="sxs-lookup"><span data-stu-id="8166f-126">To change the multiserver results options</span></span>  
  
1.  <span data-ttu-id="8166f-127">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]в меню **Сервис** выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="8166f-127">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="8166f-128">Последовательно раскройте панели **Результаты запроса**и **SQL Server**, затем выберите пункт **Многосерверные результаты**.</span><span class="sxs-lookup"><span data-stu-id="8166f-128">Expand **Query Results**, expand **SQL Server**, and then click **Multiserver Results**.</span></span>  
  
3.  <span data-ttu-id="8166f-129">Укажите требуемые настройки параметра на странице **Многосерверные результаты** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8166f-129">On the **Multiserver Results** page, specify the option settings that you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8166f-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="8166f-130">See Also</span></span>  
 [<span data-ttu-id="8166f-131">Администрирование нескольких серверов с помощью центральных серверов управления</span><span class="sxs-lookup"><span data-stu-id="8166f-131">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
