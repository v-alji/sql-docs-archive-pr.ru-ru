---
title: Создание предупреждения о событии WMI | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI event alerts [SQL Server Management Studio]
ms.assetid: b8c46db6-408b-484e-98f0-a8af3e7ec763
author: stevestein
ms.author: sstein
ms.openlocfilehash: 737e7ccac9c92e663040e71339aa120f8db8b80b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665760"
---
# <a name="create-a-wmi-event-alert"></a><span data-ttu-id="351d5-102">Создание предупреждения о событии WMI</span><span class="sxs-lookup"><span data-stu-id="351d5-102">Create a WMI Event Alert</span></span>
  <span data-ttu-id="351d5-103">В этом разделе описано, как создать предупреждение агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , вызываемое при возникновении определенного события [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которое отслеживается поставщиком WMI для событий сервера, в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="351d5-103">This topic describes how to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] event occurs that is monitored by the WMI Provider for Server Events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="351d5-104">Дополнительные сведения об использовании поставщика WMI для мониторинга [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] событий см. в разделе [Основные понятия поставщика WMI для событий сервера](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="351d5-104">For information about the using the WMI Provider to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, see [WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span></span> <span data-ttu-id="351d5-105">Дополнительные сведения о разрешениях, которые требуются для получения уведомлений о событиях WMI, см. в разделе [Выбор учетной записи для службы агента SQL Server](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="351d5-105">For information about the permissions necessary to receive WMI event alert notifications, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span> <span data-ttu-id="351d5-106">Дополнительные сведения о языке WQL см. в разделе [Использование WQL с поставщиком WMI для событий сервера](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span><span class="sxs-lookup"><span data-stu-id="351d5-106">For more information about WQL, see [Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span></span>  
  
 <span data-ttu-id="351d5-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="351d5-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="351d5-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="351d5-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="351d5-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="351d5-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="351d5-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="351d5-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="351d5-111">**Создание предупреждения о событии WMI с помощью:**</span><span class="sxs-lookup"><span data-stu-id="351d5-111">**To create a WMI event alert, using:**</span></span>  
  
     [<span data-ttu-id="351d5-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="351d5-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="351d5-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="351d5-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="351d5-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="351d5-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="351d5-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="351d5-115">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="351d5-116">обеспечивает простой графический способ управления всей системой предупреждений и рекомендуется для настройки инфраструктуры предупреждений.</span><span class="sxs-lookup"><span data-stu-id="351d5-116">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="351d5-117">События, сформированные посредством процедуры **xp_logevent** , появляются в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="351d5-117">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="351d5-118">Поэтому **xp_logevent** не вызывает срабатывание предупреждения, если только значение аргумента **@database_name** для предупреждения не равно **'master'** или NULL.</span><span class="sxs-lookup"><span data-stu-id="351d5-118">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="351d5-119">На компьютере, где запущен агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , поддерживаются только пространства имен WMI.</span><span class="sxs-lookup"><span data-stu-id="351d5-119">Only WMI namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="351d5-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="351d5-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="351d5-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="351d5-121">Permissions</span></span>  
 <span data-ttu-id="351d5-122">По умолчанию только члены предопределенной роли сервера **sysadmin** могут выполнять процедуру **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="351d5-122">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="351d5-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="351d5-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="351d5-124">Создание предупреждения о событии WMI</span><span class="sxs-lookup"><span data-stu-id="351d5-124">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="351d5-125">В **обозревателе объектов** щелкните значок «плюс», чтобы развернуть сервер, на котором нужно создать предупреждение о событии WMI.</span><span class="sxs-lookup"><span data-stu-id="351d5-125">In **Object Explorer,** click the plus sign to expand the server where you want to create a WMI event alert.</span></span>  
  
2.  <span data-ttu-id="351d5-126">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="351d5-126">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="351d5-127">Щелкните правой кнопкой пункт **Предупреждения** и выберите **Создать предупреждение**.</span><span class="sxs-lookup"><span data-stu-id="351d5-127">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="351d5-128">В поле **Имя** диалогового окна **Создание предупреждения** введите имя этого предупреждения.</span><span class="sxs-lookup"><span data-stu-id="351d5-128">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="351d5-129">Установите флажок **Включено** , чтобы разрешить выдачу предупреждения.</span><span class="sxs-lookup"><span data-stu-id="351d5-129">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="351d5-130">По умолчанию флажок **Включить** установлен.</span><span class="sxs-lookup"><span data-stu-id="351d5-130">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="351d5-131">В списке **Тип** выберите **Предупреждение о событии WMI**.</span><span class="sxs-lookup"><span data-stu-id="351d5-131">In the **Type** list, select **WMI event alert**.</span></span>  
  
7.  <span data-ttu-id="351d5-132">В разделе **Определение условий предупреждений о событиях WMI**в поле **Пространство имен** укажите пространство имен WMI для инструкций языка WQL, определяющее события WMI, которые будут приводить к возникновению этого предупреждения.</span><span class="sxs-lookup"><span data-stu-id="351d5-132">Under **WMI event alert definition**, in the **Namespace** box, specify the WMI namespace for the WMI Query Language (WQL) statement that identifies which WMI event will trigger this alert.</span></span>  
  
8.  <span data-ttu-id="351d5-133">В поле **Запрос** укажите инструкцию WQL, определяющую событие, на которое реагирует предупреждение.</span><span class="sxs-lookup"><span data-stu-id="351d5-133">In the **Query** box, specify the WQL statement that identifies the event that this alert responds to.</span></span>  
  
9. <span data-ttu-id="351d5-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="351d5-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="351d5-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="351d5-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="351d5-136">Создание предупреждения о событии WMI</span><span class="sxs-lookup"><span data-stu-id="351d5-136">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="351d5-137">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="351d5-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="351d5-138">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="351d5-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="351d5-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="351d5-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a WMI event alert that retrieves all event properties for any ALTER_TABLE event that occurs on table AdventureWorks2012.Sales.SalesOrderDetail  
    -- This example assumes that the message 54001 already exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert 2',  
        @message_id = 54001  
        @notification_message = N'Error 54001 has occurred on the Sales.SalesOrderDetail table on the AdventureWorks2012 database. Please see the following information...',  
        @wmi_namespace = '\\.\root\Microsoft\SqlServer\ServerEvents\,  
        @wmi_query = N'SELECT * FROM ALTER_TABLE   
    WHERE DatabaseName = 'AdventureWorks2012' AND SchemaName = 'Sales'   
        AND ObjectType='Table' AND ObjectName = 'SalesOrderDetail'';  
    GO  
    ```  
  
 <span data-ttu-id="351d5-140">Дополнительные сведения см. в разделе [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="351d5-140">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
