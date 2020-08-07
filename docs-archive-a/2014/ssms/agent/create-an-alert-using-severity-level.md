---
title: Создание предупреждения с учетом уровня серьезности | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
- SQL Server Agent, alerts
- severity levels [SQL Server]
- alerts [SQL Server], severity levels
ms.assetid: a1fd71bf-5bf9-4ce2-9a1d-032576a4a6e9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ee353129d60fe7fc8bed0eff279920d8d4ba640
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734909"
---
# <a name="create-an-alert-using-severity-level"></a><span data-ttu-id="40d77-102">Create an Alert Using Severity Level</span><span class="sxs-lookup"><span data-stu-id="40d77-102">Create an Alert Using Severity Level</span></span>
  <span data-ttu-id="40d77-103">В этом разделе описывается создание [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждения агента, которое возникает, когда событие определенного уровня серьезности происходит в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40d77-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when an event of a specific severity level occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="40d77-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="40d77-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="40d77-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="40d77-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="40d77-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="40d77-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="40d77-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="40d77-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="40d77-108">**Для создания предупреждения по степени серьезности используется:**</span><span class="sxs-lookup"><span data-stu-id="40d77-108">**To create an alert using severity level, using:**</span></span>  
  
     [<span data-ttu-id="40d77-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40d77-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="40d77-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="40d77-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="40d77-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="40d77-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="40d77-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="40d77-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="40d77-113">обеспечивает простой графический способ управления всей системой предупреждений и рекомендуется для настройки инфраструктуры предупреждений.</span><span class="sxs-lookup"><span data-stu-id="40d77-113">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="40d77-114">События, сформированные посредством процедуры **xp_logevent** , появляются в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="40d77-114">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="40d77-115">Поэтому **xp_logevent** не вызывает срабатывание предупреждения, если только значение аргумента **@database_name** для предупреждения не равно **'master'** или NULL.</span><span class="sxs-lookup"><span data-stu-id="40d77-115">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="40d77-116">При уровнях серьезности от 19 до 25 сообщение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] направляется в журнал приложения [!INCLUDE[msCoName](../../includes/msconame-md.md)] и вызывает срабатывание предупреждения.</span><span class="sxs-lookup"><span data-stu-id="40d77-116">Severity levels from 19 through 25 send a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] message to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log and trigger an alert.</span></span> <span data-ttu-id="40d77-117">События с уровнями серьезности меньше 19 вызовут срабатывание предупреждения только в случае, если были использованы **sp_altermessage**, RAISERROR WITH LOG или **xp_logevent** , чтобы принудительно осуществить запись этих событий в журнал приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="40d77-117">Events with severity levels less than 19 will trigger alerts only if you have used **sp_altermessage**, RAISERROR WITH LOG, or **xp_logevent** to force them to be written to the Windows application log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="40d77-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="40d77-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="40d77-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="40d77-119">Permissions</span></span>  
 <span data-ttu-id="40d77-120">По умолчанию только члены предопределенной роли сервера **sysadmin** могут выполнять процедуру **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="40d77-120">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="40d77-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40d77-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-alert-using-severity-level"></a><span data-ttu-id="40d77-122">Создание предупреждения с указанием уровня серьезности</span><span class="sxs-lookup"><span data-stu-id="40d77-122">To create an alert using severity level</span></span>  
  
1.  <span data-ttu-id="40d77-123">В **обозревателе объектов** щелкните знак «плюс», чтобы развернуть сервер, на котором необходимо создать предупреждение по степени серьезности.</span><span class="sxs-lookup"><span data-stu-id="40d77-123">In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using severity level.</span></span>  
  
2.  <span data-ttu-id="40d77-124">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="40d77-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="40d77-125">Щелкните правой кнопкой пункт **Предупреждения** и выберите **Создать предупреждение**.</span><span class="sxs-lookup"><span data-stu-id="40d77-125">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="40d77-126">В поле **Имя** диалогового окна **Создание предупреждения** введите имя этого предупреждения.</span><span class="sxs-lookup"><span data-stu-id="40d77-126">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="40d77-127">В списке **Тип** выберите **Предупреждение о событии SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="40d77-127">In the **Type** list, select **SQL Server event alert**.</span></span>  
  
6.  <span data-ttu-id="40d77-128">В разделе **Определение предупреждения о событии**в списке **Имя базы данных** выберите базу данных для установки ограничения на предупреждение относительно конкретной базы банных.</span><span class="sxs-lookup"><span data-stu-id="40d77-128">Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.</span></span>  
  
7.  <span data-ttu-id="40d77-129">В разделе **Предупреждение будет выдано на основании**выберите пункт **Серьезность** , а затем выберите степень серьезности для предупреждения.</span><span class="sxs-lookup"><span data-stu-id="40d77-129">Under **Alerts will be raised based on**, click **Severity** and then select the specific severity that will raise the alert.</span></span>  
  
8.  <span data-ttu-id="40d77-130">Чтобы ограничить сообщение определенной последовательностью символов, установите флажок в поле **Создавать предупреждение, если сообщение содержит** и введите ключевое слово или строку символов в поле **Текст сообщения**.</span><span class="sxs-lookup"><span data-stu-id="40d77-130">Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**.</span></span> <span data-ttu-id="40d77-131">Максимальное количество символов равно 100.</span><span class="sxs-lookup"><span data-stu-id="40d77-131">The maximum number of characters is 100.</span></span>  
  
9. <span data-ttu-id="40d77-132">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="40d77-132">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="40d77-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="40d77-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-alert-using-severity-level"></a><span data-ttu-id="40d77-134">Создание предупреждения с указанием уровня серьезности</span><span class="sxs-lookup"><span data-stu-id="40d77-134">To create an alert using severity level</span></span>  
  
1.  <span data-ttu-id="40d77-135">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40d77-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="40d77-136">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="40d77-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="40d77-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="40d77-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an alert (Test Alert) that runs the Back up the AdventureWorks2012 Database job when fired   
    -- assumes that the message 55001 and the Back up the AdventureWorks2012 Database job already exist.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert',  
        @message_id = 55001,   
       @severity = 0,   
       @notification_message = N'Error 55001 has occurred. The database will be backed up...',   
       @job_name = N'Back up the AdventureWorks2012 Database' ;  
    GO  
    ```  
  
 <span data-ttu-id="40d77-138">Дополнительные сведения см. в разделе [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40d77-138">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
