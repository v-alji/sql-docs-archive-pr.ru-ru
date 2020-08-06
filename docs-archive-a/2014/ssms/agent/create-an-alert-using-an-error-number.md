---
title: Создание предупреждения с учетом номера ошибки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
- SQL Server Agent, alerts
- alerts [SQL Server], error numbers
ms.assetid: 03dd7fac-5073-4f86-babd-37e45a86023c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a98f64bc5b9dffc3e2494a0c36c8fc04cdfb6fa2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665223"
---
# <a name="create-an-alert-using-an-error-number"></a><span data-ttu-id="7a10e-102">Создание предупреждения по номеру сообщения</span><span class="sxs-lookup"><span data-stu-id="7a10e-102">Create an Alert Using an Error Number</span></span>
  <span data-ttu-id="7a10e-103">В этом разделе описывается создание [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждения агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] среде, которая будет вызываться при возникновении ошибки определенного числа с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a10e-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that will be raised when an error of a specific number occurs by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7a10e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7a10e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a10e-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7a10e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a10e-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7a10e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7a10e-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7a10e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a10e-108">**Создание предупреждения по номеру ошибки с помощью:**</span><span class="sxs-lookup"><span data-stu-id="7a10e-108">**To create an alert using an error number, using:**</span></span>  
  
     [<span data-ttu-id="7a10e-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a10e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a10e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a10e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a10e-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7a10e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7a10e-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7a10e-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="7a10e-113">обеспечивает простой графический способ управления всей системой предупреждений и рекомендуется для настройки инфраструктуры предупреждений.</span><span class="sxs-lookup"><span data-stu-id="7a10e-113">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="7a10e-114">События, сформированные посредством процедуры **xp_logevent** , появляются в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="7a10e-114">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="7a10e-115">Поэтому **xp_logevent** не вызывает срабатывание предупреждения, если только значение аргумента **@database_name** для предупреждения не равно **'master'** или NULL.</span><span class="sxs-lookup"><span data-stu-id="7a10e-115">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a10e-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="7a10e-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a10e-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="7a10e-117">Permissions</span></span>  
 <span data-ttu-id="7a10e-118">По умолчанию только члены предопределенной роли сервера **sysadmin** могут выполнять процедуру **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="7a10e-118">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a10e-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a10e-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-alert-using-an-error-number"></a><span data-ttu-id="7a10e-120">Создание предупреждения по номеру сообщения</span><span class="sxs-lookup"><span data-stu-id="7a10e-120">To create an alert using an error number</span></span>  
  
1.  <span data-ttu-id="7a10e-121">В **обозревателе объектов** щелкните знак «плюс», чтобы развернуть сервер, на котором необходимо создать предупреждение по номеру ошибки.</span><span class="sxs-lookup"><span data-stu-id="7a10e-121">In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using an error number.</span></span>  
  
2.  <span data-ttu-id="7a10e-122">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7a10e-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="7a10e-123">Щелкните правой кнопкой пункт **Предупреждения** и выберите **Создать предупреждение**.</span><span class="sxs-lookup"><span data-stu-id="7a10e-123">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="7a10e-124">В поле **Имя** диалогового окна **Создание предупреждения** введите имя этого предупреждения.</span><span class="sxs-lookup"><span data-stu-id="7a10e-124">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="7a10e-125">Установите флажок **Включено** , чтобы разрешить выдачу предупреждения.</span><span class="sxs-lookup"><span data-stu-id="7a10e-125">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="7a10e-126">По умолчанию флажок **Включить** установлен.</span><span class="sxs-lookup"><span data-stu-id="7a10e-126">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="7a10e-127">В списке **Тип** выберите **Предупреждение о событии SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7a10e-127">In the **Type** list, select **SQL Server event alert**.</span></span>  
  
7.  <span data-ttu-id="7a10e-128">В разделе **Определение предупреждения о событии**в списке **Имя базы данных** выберите базу данных для установки ограничения на предупреждение относительно конкретной базы банных.</span><span class="sxs-lookup"><span data-stu-id="7a10e-128">Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.</span></span>  
  
8.  <span data-ttu-id="7a10e-129">В разделе **Предупреждение будет выдано на основании**выберите **Номер ошибки**, а затем введите допустимый номер ошибки для предупреждения.</span><span class="sxs-lookup"><span data-stu-id="7a10e-129">Under **Alerts will be raised based on**, click **Error number**, and then type a valid error number for the alert.</span></span> <span data-ttu-id="7a10e-130">Или нажмите кнопку **Серьезность** и выберите определенный уровень серьезности, который вызовет предупреждение.</span><span class="sxs-lookup"><span data-stu-id="7a10e-130">Alternately, click **Severity** and then select the specific severity that will raise the alert.</span></span>  
  
9. <span data-ttu-id="7a10e-131">Чтобы ограничить сообщение определенной последовательностью символов, установите флажок в поле **Создавать предупреждение, если сообщение содержит** и введите ключевое слово или строку символов в поле **Текст сообщения**.</span><span class="sxs-lookup"><span data-stu-id="7a10e-131">Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**.</span></span> <span data-ttu-id="7a10e-132">Максимальное количество символов равно 100.</span><span class="sxs-lookup"><span data-stu-id="7a10e-132">The maximum number of characters is 100.</span></span>  
  
10. <span data-ttu-id="7a10e-133">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7a10e-133">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a10e-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a10e-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-alert-using-an-error-number"></a><span data-ttu-id="7a10e-135">Создание предупреждения по номеру сообщения</span><span class="sxs-lookup"><span data-stu-id="7a10e-135">To create an alert using an error number</span></span>  
  
1.  <span data-ttu-id="7a10e-136">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a10e-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a10e-137">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7a10e-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a10e-138">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7a10e-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
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
  
 <span data-ttu-id="7a10e-139">Дополнительные сведения см. в разделе [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a10e-139">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
