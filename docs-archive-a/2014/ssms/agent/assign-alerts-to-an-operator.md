---
title: Назначение предупреждений оператору | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- assigning alerts to operator
- SQL Server Agent, alerts
- alerts [SQL Server], assigning to operator
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: aa818155-6fa2-4565-a09f-5c7e31c89754
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cc238b952c03595035856f377b6fdbb9eaf5e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659083"
---
# <a name="assign-alerts-to-an-operator"></a><span data-ttu-id="aaac9-102">Assign Alerts to an Operator</span><span class="sxs-lookup"><span data-stu-id="aaac9-102">Assign Alerts to an Operator</span></span>
  <span data-ttu-id="aaac9-103">В этом разделе описывается назначение [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждений агента операторам, чтобы они могли получать уведомления о заданиях в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaac9-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts to operators so they can receive notifications about jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="aaac9-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="aaac9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aaac9-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="aaac9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aaac9-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="aaac9-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="aaac9-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="aaac9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aaac9-108">**Назначение предупреждений оператору с помощью:**</span><span class="sxs-lookup"><span data-stu-id="aaac9-108">**To assign alerts to an operator, using:**</span></span>  
  
     [<span data-ttu-id="aaac9-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aaac9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="aaac9-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aaac9-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aaac9-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="aaac9-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="aaac9-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="aaac9-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="aaac9-113">обеспечивает простой графический способ управления всей системой предупреждений.</span><span class="sxs-lookup"><span data-stu-id="aaac9-113">provides an easy, graphical way to manage the entire alerting system.</span></span> <span data-ttu-id="aaac9-114">Использование среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] рекомендуется для настройки инфраструктуры предупреждений.</span><span class="sxs-lookup"><span data-stu-id="aaac9-114">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is the recommended way to configure your alert infrastructure.</span></span>  
  
-   <span data-ttu-id="aaac9-115">Чтобы в ответ на предупреждение отправить уведомление, необходимо настроить агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для отправки почты.</span><span class="sxs-lookup"><span data-stu-id="aaac9-115">To send a notification in response to an alert, you must first configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send mail.</span></span> <span data-ttu-id="aaac9-116">Дополнительные сведения см. в статье [Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="aaac9-116">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
-   <span data-ttu-id="aaac9-117">Ошибки, возникающие при отправке сообщения по электронной почте или уведомления по пейджеру, регистрируются в журнале ошибок службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaac9-117">If a failure occurs when sending an e-mail message or pager notification, the failure is reported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service error log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aaac9-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="aaac9-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aaac9-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="aaac9-119">Permissions</span></span>  
 <span data-ttu-id="aaac9-120">Только члены предопределенной роли сервера **sysadmin** могут назначать предупреждения операторам.</span><span class="sxs-lookup"><span data-stu-id="aaac9-120">Only members of the **sysadmin** fixed server role can assign alerts to operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aaac9-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aaac9-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="aaac9-122">Назначение предупреждений оператору</span><span class="sxs-lookup"><span data-stu-id="aaac9-122">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="aaac9-123">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий оператора, которому необходимо назначить предупреждение.</span><span class="sxs-lookup"><span data-stu-id="aaac9-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator to which you want to assign an alert.</span></span>  
  
2.  <span data-ttu-id="aaac9-124">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="aaac9-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="aaac9-125">Щелкните значок «плюс», чтобы развернуть папку **Операторы** .</span><span class="sxs-lookup"><span data-stu-id="aaac9-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="aaac9-126">Щелкните правой кнопкой мыши оператора, для которого нужно назначить предупреждение, выберите пункт **Свойства**и перейдите на страницу **Уведомления** .</span><span class="sxs-lookup"><span data-stu-id="aaac9-126">Right-click the operator to which you want to assign an alert and select **Properties**, and select the **Notifications** page.</span></span>  
  
5.  <span data-ttu-id="aaac9-127">В разделе _Выбор страницы_**диалогового окна** Свойства **имя_оператора**выберите **Уведомления**.</span><span class="sxs-lookup"><span data-stu-id="aaac9-127">In the _operator_name_**Properties** dialog box, under **Select a page**, select **Notifications**.</span></span>  
  
6.  <span data-ttu-id="aaac9-128">В поле **Просмотр отправленных пользователю уведомлений по**выберите **Предупреждения** , чтобы просмотреть список предупреждений, отправляемых этому оператору, либо **Задания** , чтобы просмотреть список заданий, отправляющих уведомления этому оператору.</span><span class="sxs-lookup"><span data-stu-id="aaac9-128">Under **View notifications sent to this user by**, select **Alerts** to view a list of alerts sent to this operator or select **Jobs** to view a list of jobs that send notifications to this operator.</span></span> <span data-ttu-id="aaac9-129">Установите один или более перечисленных ниже флажков, чтобы выбрать способ доставки для каждого из уведомлений: **Электронная почта**, **Пейджер**или **Net send**.</span><span class="sxs-lookup"><span data-stu-id="aaac9-129">Select one or more of the following checkboxes to define the notification method for each notification as necessary: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="aaac9-130">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aaac9-130">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="aaac9-131">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aaac9-131">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="aaac9-132">Назначение предупреждений оператору</span><span class="sxs-lookup"><span data-stu-id="aaac9-132">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="aaac9-133">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaac9-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aaac9-134">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="aaac9-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aaac9-135">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="aaac9-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for the specified alert (Test Alert)  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="aaac9-136">Дополнительные сведения см. в разделе [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aaac9-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
