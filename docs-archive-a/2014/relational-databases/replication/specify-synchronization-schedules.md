---
title: Указание расписаний синхронизации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], synchronizing
- scheduling synchronization [SQL Server replication]
- synchronization [SQL Server replication], schedules
- replication [SQL Server], synchronization
ms.assetid: 97f2535b-ec19-4973-823d-bcf3d5aa0216
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d752817f7d620b2c6e5fdc5eeb2178c50c42040
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738192"
---
# <a name="specify-synchronization-schedules"></a><span data-ttu-id="b1b14-102">Указание расписаний синхронизации</span><span class="sxs-lookup"><span data-stu-id="b1b14-102">Specify Synchronization Schedules</span></span>
  <span data-ttu-id="b1b14-103">В данном разделе описывается процесс задания расписаний синхронизации в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="b1b14-103">This topic describes how to specify synchronization schedules in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="b1b14-104">При создании подписки можно определить расписание синхронизации, управляющее запуском агента репликации для подписки.</span><span class="sxs-lookup"><span data-stu-id="b1b14-104">When you create a subscription, you can define a synchronization schedule that controls when the replication agent for the subscription will run.</span></span> <span data-ttu-id="b1b14-105">Если не указать параметры расписания, подписка использует расписание по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1b14-105">If you do not specify scheduling parameters, the subscription will use the default schedule.</span></span>  
  
 <span data-ttu-id="b1b14-106">Подписки синхронизируются агентом распространителя (для репликации моментальных снимков и репликации транзакций) или агентом слияния (для репликации слиянием).</span><span class="sxs-lookup"><span data-stu-id="b1b14-106">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="b1b14-107">Агенты могут работать непрерывно, запускаться по запросу или по расписанию.</span><span class="sxs-lookup"><span data-stu-id="b1b14-107">Agents can run continuously, run on demand, or run on a schedule.</span></span>  
  
 <span data-ttu-id="b1b14-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b1b14-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b1b14-109">**Для задания расписаний синхронизации используется:**</span><span class="sxs-lookup"><span data-stu-id="b1b14-109">**To specify synchronization schedules, using:**</span></span>  
  
     [<span data-ttu-id="b1b14-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1b14-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b1b14-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1b14-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b1b14-112">объекты RMO;</span><span class="sxs-lookup"><span data-stu-id="b1b14-112">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b1b14-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1b14-113">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b1b14-114">Укажите расписания синхронизации на странице **Расписание синхронизации** мастера создания подписки.</span><span class="sxs-lookup"><span data-stu-id="b1b14-114">Specify synchronization schedules on the **Synchronization Schedule** page of the New Subscription Wizard.</span></span> <span data-ttu-id="b1b14-115">Дополнительные сведения о доступе к этому мастеру см. в разделах [Create a Push Subscription](create-a-push-subscription.md) и [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-115">For more information about accessing this wizard, see [Create a Push Subscription](create-a-push-subscription.md) and [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="b1b14-116">Измените расписания синхронизации в диалоговом окне **Свойства расписания задания** , доступном из папки **Задания** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и в окнах подробных сведений агента в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="b1b14-116">Modify synchronization schedules in the **Job Schedule Properties** dialog box, which is available from the **Jobs** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and from the agent details windows in Replication Monitor.</span></span> <span data-ttu-id="b1b14-117">Сведения о запуске монитора репликации см. в [этой статье](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-117">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="b1b14-118">При указании расписаний из папки **Задания** используйте следующую таблицу для определения имени задания агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-118">If you specify schedules from the **Jobs** folder, use the following table to determine the agent job name.</span></span>  
  
|<span data-ttu-id="b1b14-119">Агент</span><span class="sxs-lookup"><span data-stu-id="b1b14-119">Agent</span></span>|<span data-ttu-id="b1b14-120">Имя задания</span><span class="sxs-lookup"><span data-stu-id="b1b14-120">Job name</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="b1b14-121">Агент слияния для подписок по запросу</span><span class="sxs-lookup"><span data-stu-id="b1b14-121">Merge Agent for pull subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<integer>**|  
|<span data-ttu-id="b1b14-122">Агент слияния для принудительных подписок</span><span class="sxs-lookup"><span data-stu-id="b1b14-122">Merge Agent for push subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|  
|<span data-ttu-id="b1b14-123">Агент распространителя для принудительных подписок</span><span class="sxs-lookup"><span data-stu-id="b1b14-123">Distribution Agent for push subscriptions</span></span>|<span data-ttu-id="b1b14-124">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b1b14-124">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span></span>|  
|<span data-ttu-id="b1b14-125">Агент распространителя для подписок по запросу</span><span class="sxs-lookup"><span data-stu-id="b1b14-125">Distribution Agent for pull subscriptions</span></span>|<span data-ttu-id="b1b14-126">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b1b14-126">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span></span>|  
|<span data-ttu-id="b1b14-127">Агент распространителя для принудительных подписок подписчиков серверов, отличных от подписчиков SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1b14-127">Distribution Agent for push subscriptions to non-SQL Server Subscribers</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|  
  
 <span data-ttu-id="b1b14-128"><sup>1</sup> Для принудительных подписок на публикации Oracle это \*\*\<Publisher>-\<Publisher**>, а не **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="b1b14-128"><sup>1</sup> For push subscriptions to Oracle publications, it is \*\*\<Publisher>-\<Publisher**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
 <span data-ttu-id="b1b14-129"><sup>2</sup> Для подписок по запросу на публикации Oracle это \*\*\<Publisher>-\<DistributionDatabase**>, а не **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="b1b14-129"><sup>2</sup> For pull subscriptions to Oracle publications, it is \*\*\<Publisher>-\<DistributionDatabase**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
#### <a name="to-specify-synchronization-schedules"></a><span data-ttu-id="b1b14-130">Указание расписаний синхронизации</span><span class="sxs-lookup"><span data-stu-id="b1b14-130">To specify synchronization schedules</span></span>  
  
1.  <span data-ttu-id="b1b14-131">На странице **Расписание синхронизации** мастера создания подписки выберите одно из следующих значений в раскрывающемся списке **Расписание агента** для каждой создаваемой подписки:</span><span class="sxs-lookup"><span data-stu-id="b1b14-131">On the **SynchronizationSchedule** page of the New Subscription Wizard, select one of the following values from the **Agent Schedule** drop-down list for each subscription you are creating:</span></span>  
  
    -   <span data-ttu-id="b1b14-132">**Выполнять постоянно**</span><span class="sxs-lookup"><span data-stu-id="b1b14-132">**Run continuously**</span></span>  
  
    -   <span data-ttu-id="b1b14-133">**Запуск только по запросу**</span><span class="sxs-lookup"><span data-stu-id="b1b14-133">**Run on demand only**</span></span>  
  
    -   **\<Define Schedule...>**  
  
2.  <span data-ttu-id="b1b14-134">При выборе **\<Define Schedule...>** укажите расписание в диалоговом окне **Свойства расписания задания** и затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-134">If you select **\<Define Schedule...>**, specify a schedule in the **Job Schedule Properties** dialog box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b1b14-135">Завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="b1b14-135">Complete the wizard.</span></span>  
  
#### <a name="to-modify-a-synchronization-schedule-for-a-push-subscription-in-replication-monitor"></a><span data-ttu-id="b1b14-136">Изменение расписания синхронизации для принудительных подписок в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="b1b14-136">To modify a synchronization schedule for a push subscription in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="b1b14-137">На левой панели монитора репликации раскройте группу издателей, раскройте нужный издатель, а затем выберите публикацию.</span><span class="sxs-lookup"><span data-stu-id="b1b14-137">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="b1b14-138">Перейдите на вкладку **Все подписки** .</span><span class="sxs-lookup"><span data-stu-id="b1b14-138">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="b1b14-139">Щелкните правой кнопкой мыши подписку, а затем выберите **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-139">Right-click a subscription, and then click **View Details**.</span></span>  
  
4.  <span data-ttu-id="b1b14-140">В окне **подписка \< SubscriptionName> \*\* щелкните **действие**и выберите \*\* \<AgentName> Свойства задания**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-140">In the **Subscription \< SubscriptionName>** window, click **Action**, and then click **\<AgentName> Job Properties**.</span></span>  
  
5.  <span data-ttu-id="b1b14-141">На странице **Расписания** диалогового окна **Свойства задания — \<JobName>** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-141">On the **Schedules** page of the **Job Properties - \<JobName>** dialog box, click **Edit.**</span></span>  
  
6.  <span data-ttu-id="b1b14-142">В диалоговом окне **Свойства расписания задания** выберите значение из раскрывающегося списка **Тип расписания** :</span><span class="sxs-lookup"><span data-stu-id="b1b14-142">In the **Job Schedule Properties** dialog box, select a value from the **Schedule Type** drop-down list:</span></span>  
  
    -   <span data-ttu-id="b1b14-143">Для указания непрерывной работы агента выберите **Запускать автоматически при запуске агента SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-143">To specify that the agent should run continuously, select **Start automatically when SQL Server Agent starts**.</span></span>  
  
    -   <span data-ttu-id="b1b14-144">Для указания работы агента по расписанию выберите **Периодически**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-144">To specify that the agent should run on a schedule, select **Recurring**.</span></span>  
  
    -   <span data-ttu-id="b1b14-145">Для указания запуска агента по запросу выберите **Один раз**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-145">To specify that the agent should run on demand, select **One time**.</span></span>  
  
7.  <span data-ttu-id="b1b14-146">При выборе значения **Периодически**укажите расписание для агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-146">If you select **Recurring**, specify a schedule for the agent.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
#### <a name="to-modify-a-synchronization-schedule-for-a-push-subscription-in-management-studio"></a><span data-ttu-id="b1b14-147">Изменение расписания синхронизации для принудительных подписок в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1b14-147">To modify a synchronization schedule for a push subscription in Management Studio</span></span>  
  
1.  <span data-ttu-id="b1b14-148">Подключитесь к распространителю в [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]и разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="b1b14-148">Connect to the Distributor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b1b14-149">Раскройте папку **Агент SQL Server** , а затем — папку **Задания** .</span><span class="sxs-lookup"><span data-stu-id="b1b14-149">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="b1b14-150">Щелкните правой кнопкой задание для агента распространителя или агента слияния, связанных с подпиской, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-150">Right-click the job for the Distribution Agent or Merge Agent associated with the subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b1b14-151">На странице **Расписания** диалогового окна **Свойства задания — \<JobName>** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-151">On the **Schedules** page of the **Job Properties - \<JobName>** dialog box, click **Edit.**</span></span>  
  
5.  <span data-ttu-id="b1b14-152">В диалоговом окне **Свойства расписания задания** выберите значение из раскрывающегося списка **Тип расписания** :</span><span class="sxs-lookup"><span data-stu-id="b1b14-152">In the **Job Schedule Properties** dialog box, select a value from the **Schedule Type** drop-down list:</span></span>  
  
    -   <span data-ttu-id="b1b14-153">Для указания непрерывной работы агента выберите **Запускать автоматически при запуске агента SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-153">To specify that the agent should run continuously, select **Start automatically when SQL Server Agent starts**.</span></span>  
  
    -   <span data-ttu-id="b1b14-154">Для указания работы агента по расписанию выберите **Периодически**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-154">To specify that the agent should run on a schedule, select **Recurring**.</span></span>  
  
    -   <span data-ttu-id="b1b14-155">Для указания запуска агента по запросу выберите **Один раз**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-155">To specify that the agent should run on demand, select **One time**.</span></span>  
  
6.  <span data-ttu-id="b1b14-156">При выборе значения **Периодически**укажите расписание для агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-156">If you select **Recurring**, specify a schedule for the agent.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
#### <a name="to-modify-a-synchronization-schedule-for-a-pull-subscription-in-management-studio"></a><span data-ttu-id="b1b14-157">Изменение расписания синхронизации для подписок по запросу в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1b14-157">To modify a synchronization schedule for a pull subscription in Management Studio</span></span>  
  
1.  <span data-ttu-id="b1b14-158">Подключитесь к подписчику в [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]и раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="b1b14-158">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b1b14-159">Раскройте папку **Агент SQL Server** , а затем — папку **Задания** .</span><span class="sxs-lookup"><span data-stu-id="b1b14-159">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="b1b14-160">Щелкните правой кнопкой задание для агента распространителя или агента слияния, связанных с подпиской, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-160">Right-click the job for the Distribution Agent or Merge Agent associated with the subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b1b14-161">На странице **Расписания** диалогового окна **Свойства задания — \<JobName>** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-161">On the **Schedules** page of the **Job Properties - \<JobName>** dialog box, click **Edit.**</span></span>  
  
5.  <span data-ttu-id="b1b14-162">В диалоговом окне **Свойства расписания задания** выберите значение из раскрывающегося списка **Тип расписания** :</span><span class="sxs-lookup"><span data-stu-id="b1b14-162">In the **Job Schedule Properties** dialog box, select a value from the **Schedule Type** drop-down list:</span></span>  
  
    -   <span data-ttu-id="b1b14-163">Для указания непрерывной работы агента выберите **Запускать автоматически при запуске агента SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-163">To specify that the agent should run continuously, select **Start automatically when SQL Server Agent starts**.</span></span>  
  
    -   <span data-ttu-id="b1b14-164">Для указания работы агента по расписанию выберите **Периодически**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-164">To specify that the agent should run on a schedule, select **Recurring**.</span></span>  
  
    -   <span data-ttu-id="b1b14-165">Для указания запуска агента по запросу выберите **Один раз**.</span><span class="sxs-lookup"><span data-stu-id="b1b14-165">To specify that the agent should run on demand, select **One time**.</span></span>  
  
6.  <span data-ttu-id="b1b14-166">При выборе значения **Периодически**укажите расписание для агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-166">If you select **Recurring**, specify a schedule for the agent.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b1b14-167">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1b14-167">Using Transact-SQL</span></span>  
 <span data-ttu-id="b1b14-168">Можно определить расписание синхронизации программно с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="b1b14-168">You can define synchronization schedules programmatically using replication stored procedures.</span></span> <span data-ttu-id="b1b14-169">Эти хранимые процедуры зависят от типа репликации и типа подписки (по запросу или принудительная).</span><span class="sxs-lookup"><span data-stu-id="b1b14-169">The stored procedures that you use depend on the type of replication and the type of subscription (pull or push).</span></span>  
  
 <span data-ttu-id="b1b14-170">Расписание определяется следующими параметрами, поведение которых наследуется из процедуры [sp_add_schedule (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql):</span><span class="sxs-lookup"><span data-stu-id="b1b14-170">A schedule is defined by the following scheduling parameters, the behaviors of which are inherited from [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql):</span></span>  
  
-   <span data-ttu-id="b1b14-171">**@frequency_type**— Тип частоты, используемой при планировании агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-171">**@frequency_type** - the type of frequency used when scheduling the agent.</span></span>  
  
-   <span data-ttu-id="b1b14-172">**@frequency_interval**— день недели, когда запускается агент.</span><span class="sxs-lookup"><span data-stu-id="b1b14-172">**@frequency_interval** - the day of the week when an agent runs.</span></span>  
  
-   <span data-ttu-id="b1b14-173">**@frequency_relative_interval**— Неделя в заданном месяце, когда агент планируется выполнять ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="b1b14-173">**@frequency_relative_interval** - the week of a given month when the agent is scheduled to run monthly.</span></span>  
  
-   <span data-ttu-id="b1b14-174">**@frequency_recurrence_factor**— число единиц типа Frequency, которые происходят между синхронизациями.</span><span class="sxs-lookup"><span data-stu-id="b1b14-174">**@frequency_recurrence_factor** - the number of frequency-type units that occur between synchronizations.</span></span>  
  
-   <span data-ttu-id="b1b14-175">**@frequency_subday**— единица частоты, когда агент запускается чаще одного раза в день.</span><span class="sxs-lookup"><span data-stu-id="b1b14-175">**@frequency_subday** - the frequency unit when the agent runs more often than once a day.</span></span>  
  
-   <span data-ttu-id="b1b14-176">**@frequency_subday_interval**— число единиц частоты между запусками, когда агент запускается чаще одного раза в день.</span><span class="sxs-lookup"><span data-stu-id="b1b14-176">**@frequency_subday_interval** - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
-   <span data-ttu-id="b1b14-177">**@active_start_time_of_day**— самое раннее время в указанном дне, когда запускается агент.</span><span class="sxs-lookup"><span data-stu-id="b1b14-177">**@active_start_time_of_day** - the earliest time in a given day when an agent run will start.</span></span>  
  
-   <span data-ttu-id="b1b14-178">**@active_end_time_of_day**— Последнее время в заданный день, когда запускается агент.</span><span class="sxs-lookup"><span data-stu-id="b1b14-178">**@active_end_time_of_day** - the latest time in a given day when an agent run will start.</span></span>  
  
-   <span data-ttu-id="b1b14-179">**@active_start_date**— первый день, когда расписание агента будет действовать.</span><span class="sxs-lookup"><span data-stu-id="b1b14-179">**@active_start_date** - the first day that the agent schedule will be in effect.</span></span>  
  
-   <span data-ttu-id="b1b14-180">**@active_end_date**— последний день, когда расписание агента будет действовать.</span><span class="sxs-lookup"><span data-stu-id="b1b14-180">**@active_end_date** - the last day that the agent schedule will be in effect.</span></span>  
  
#### <a name="to-define-the-synchronization-schedule-for-a-pull-subscription-to-a-transactional-publication"></a><span data-ttu-id="b1b14-181">Определение расписания синхронизации для подписки по запросу на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="b1b14-181">To define the synchronization schedule for a pull subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="b1b14-182">Создайте подписку по запросу на публикацию транзакций.</span><span class="sxs-lookup"><span data-stu-id="b1b14-182">Create a new pull subscription to a transactional publication.</span></span> <span data-ttu-id="b1b14-183">Дополнительные сведения см. в статье [Создание подписки по запросу](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-183">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
2.  <span data-ttu-id="b1b14-184">На подписчике выполните процедуру [sp_addpullsubscription_agent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b14-184">At the Subscriber, execute [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql).</span></span> <span data-ttu-id="b1b14-185">Укажите **@publisher** , **@publisher_db** , **@publication** и [!INCLUDE[msCoName](../../includes/msconame-md.md)] учетные данные Windows, с которыми работает агент распространения на подписчике, для **@job_name** и **@password** .</span><span class="sxs-lookup"><span data-stu-id="b1b14-185">Specify **@publisher**, **@publisher_db**, **@publication**, and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows credentials under which the Distribution Agent at the Subscriber runs for **@job_name** and **@password**.</span></span> <span data-ttu-id="b1b14-186">Укажите описанные выше параметры синхронизации, определяющие расписание для задания агента распространителя, синхронизирующего подписку.</span><span class="sxs-lookup"><span data-stu-id="b1b14-186">Specify the synchronization parameters, detailed above, that define the schedule for the Distribution Agent job that synchronizes the subscription.</span></span>  
  
#### <a name="to-define-the-synchronization-schedule-for-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="b1b14-187">Определение расписания синхронизации для принудительной подписки на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="b1b14-187">To define the synchronization schedule for a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="b1b14-188">Создайте принудительную подписку на публикацию транзакций.</span><span class="sxs-lookup"><span data-stu-id="b1b14-188">Create a new push subscription to a transactional publication.</span></span> <span data-ttu-id="b1b14-189">Дополнительные сведения см. в статье [Создание принудительной подписки](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-189">For more information, see [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="b1b14-190">На подписчике выполните процедуру [sp_addpushsubscription_agent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b14-190">At the Subscriber, execute [sp_addpushsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql).</span></span> <span data-ttu-id="b1b14-191">Укажите **@subscriber** , **@subscriber_db** , **@publication** и учетные данные Windows, с которыми работает агент распространения на подписчике, для **@job_name** и **@password** .</span><span class="sxs-lookup"><span data-stu-id="b1b14-191">Specify **@subscriber**, **@subscriber_db**, **@publication**, and the Windows credentials under which the Distribution Agent at the Subscriber runs for **@job_name** and **@password**.</span></span> <span data-ttu-id="b1b14-192">Укажите описанные выше параметры синхронизации, определяющие расписание для задания агента распространителя, синхронизирующего подписку.</span><span class="sxs-lookup"><span data-stu-id="b1b14-192">Specify the synchronization parameters, detailed above, that define the schedule for the Distribution Agent job that synchronizes the subscription.</span></span>  
  
#### <a name="to-define-the-synchronization-schedule-for-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="b1b14-193">Определение расписания синхронизации для подписки по запросу для публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="b1b14-193">To define the synchronization schedule for a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b1b14-194">Создайте подписку по запросу на публикацию слиянием.</span><span class="sxs-lookup"><span data-stu-id="b1b14-194">Create a new pull subscription to a merge publication.</span></span> <span data-ttu-id="b1b14-195">Дополнительные сведения см. в статье [Создание подписки по запросу](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-195">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
2.  <span data-ttu-id="b1b14-196">Выполните процедуру [sp_addmergepullsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql)на подписчике.</span><span class="sxs-lookup"><span data-stu-id="b1b14-196">At the Subscriber, execute [sp_addmergepullsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql).</span></span> <span data-ttu-id="b1b14-197">Укажите **@publisher** , **@publisher_db** , **@publication** и учетные данные Windows, с которыми работает агент слияния на подписчике, для **@job_name** и **@password** .</span><span class="sxs-lookup"><span data-stu-id="b1b14-197">Specify **@publisher**, **@publisher_db**, **@publication**, and the Windows credentials under which the Merge Agent at the Subscriber runs for **@job_name** and **@password**.</span></span> <span data-ttu-id="b1b14-198">Укажите описанные выше параметры синхронизации, определяющие расписание для задания агента слияния, синхронизирующего подписку.</span><span class="sxs-lookup"><span data-stu-id="b1b14-198">Specify the synchronization parameters, detailed above, that define the schedule for the Merge Agent job that synchronizes the subscription.</span></span>  
  
#### <a name="to-define-the-synchronization-schedule-for-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="b1b14-199">Определение расписания синхронизации для принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="b1b14-199">To define the synchronization schedule for a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b1b14-200">Создайте принудительную подписку на публикацию слиянием.</span><span class="sxs-lookup"><span data-stu-id="b1b14-200">Create a new push subscription to a merge publication.</span></span> <span data-ttu-id="b1b14-201">Дополнительные сведения см. в статье [Создание принудительной подписки](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-201">For more information, see [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="b1b14-202">Выполните на подписчике хранимую процедуру [sp_addmergepushsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b14-202">At the Subscriber, execute [sp_addmergepushsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql).</span></span> <span data-ttu-id="b1b14-203">Укажите **@subscriber** , **@subscriber_db** , **@publication** и учетные данные Windows, с которыми работает агент слияния на подписчике, для **@job_name** и **@password** .</span><span class="sxs-lookup"><span data-stu-id="b1b14-203">Specify **@subscriber**, **@subscriber_db**, **@publication**, and the Windows credentials under which the Merge Agent at the Subscriber runs for **@job_name** and **@password**.</span></span> <span data-ttu-id="b1b14-204">Укажите описанные выше параметры синхронизации, определяющие расписание для задания агента слияния, синхронизирующего подписку.</span><span class="sxs-lookup"><span data-stu-id="b1b14-204">Specify the synchronization parameters, detailed above, that define the schedule for the Merge Agent job that synchronizes the subscription.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="b1b14-205">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="b1b14-205">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="b1b14-206">При выполнении репликации агент SQL Server производит планирование заданий для создания моментальных снимков и синхронизации подписок.</span><span class="sxs-lookup"><span data-stu-id="b1b14-206">Replication uses the SQL Server Agent to schedule jobs for activities that occur periodically, such as snapshot generation and subscription synchronization.</span></span> <span data-ttu-id="b1b14-207">Расписание заданий агента репликации может быть задано программным путем с помощью объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="b1b14-207">You can use Replication Management Objects (RMO) programmatically to specify schedules for replication agent jobs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1b14-208">Если при создании подписки в параметре `false` указано значение `CreateSyncAgentByDefault` (по умолчанию для подписок по запросу), то задание агента не создается, а параметры расписания не учитываются.</span><span class="sxs-lookup"><span data-stu-id="b1b14-208">When you create a subscription and specify a value `false` for `CreateSyncAgentByDefault` (the default behavior for pull subscriptions) the agent job is not created and scheduling properties are ignored.</span></span> <span data-ttu-id="b1b14-209">В этом случае расписание синхронизации задается приложением.</span><span class="sxs-lookup"><span data-stu-id="b1b14-209">In this case, the synchronization schedule must be determined by the application.</span></span> <span data-ttu-id="b1b14-210">Дополнительные сведения см. в разделах [Create a Pull Subscription](create-a-pull-subscription.md) и [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-210">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md) and [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
#### <a name="to-define-a-replication-agent-schedule-when-you-create-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="b1b14-211">Создание нового расписания агента репликации при создании принудительной подписки на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="b1b14-211">To define a replication agent schedule when you create a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="b1b14-212">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransSubscription> для создаваемой подписки.</span><span class="sxs-lookup"><span data-stu-id="b1b14-212">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class for the subscription you are creating.</span></span> <span data-ttu-id="b1b14-213">Дополнительные сведения см. в статье [Создание принудительной подписки](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-213">For more information, see [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="b1b14-214">Перед вызовом метода <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A>установите одно или несколько из следующих полей свойства <xref:Microsoft.SqlServer.Replication.Subscription.AgentSchedule%2A> :</span><span class="sxs-lookup"><span data-stu-id="b1b14-214">Before you call <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A>, set one or more of the following fields of the <xref:Microsoft.SqlServer.Replication.Subscription.AgentSchedule%2A> property:</span></span>  
  
    -   <span data-ttu-id="b1b14-215"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> — частота запуска агента по расписанию (например ежедневно или еженедельно);</span><span class="sxs-lookup"><span data-stu-id="b1b14-215"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - the type of frequency (such as daily or weekly) you use when you schedule the agent.</span></span>  
  
    -   <span data-ttu-id="b1b14-216"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> — день недели, в который запускается агент;</span><span class="sxs-lookup"><span data-stu-id="b1b14-216"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - the day of the week that an agent runs.</span></span>  
  
    -   <span data-ttu-id="b1b14-217"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> — номер недели в месяце, если агент запускается ежемесячно;</span><span class="sxs-lookup"><span data-stu-id="b1b14-217"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - the week of a given month when the agent is scheduled to run monthly.</span></span>  
  
    -   <span data-ttu-id="b1b14-218"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> — число частотных единиц, проходящих между последовательными синхронизациями;</span><span class="sxs-lookup"><span data-stu-id="b1b14-218"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - the number of frequency-type units that occur between synchronizations.</span></span>  
  
    -   <span data-ttu-id="b1b14-219"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> — частотная единица, используемая, если агент запускается чаще одного раза в день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-219"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - the frequency unit when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="b1b14-220"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> — число частотных единиц, проходящих между запусками агента, если он запускается чаще одного раза в день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-220"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="b1b14-221"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> — время самого раннего запуска агента в заданный день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-221"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - earliest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="b1b14-222"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> — время самого позднего запуска агента в заданный день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-222"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - latest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="b1b14-223"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> — первый день действия расписания агента;</span><span class="sxs-lookup"><span data-stu-id="b1b14-223"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - first day that the agent schedule is in effect.</span></span>  
  
    -   <span data-ttu-id="b1b14-224"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> — последний день действия расписания агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-224"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - last day that the agent schedule is in effect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b1b14-225">Если не задать одно из этих свойств, будет использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1b14-225">If you do not specify one of these properties, a default value is set.</span></span>  
  
3.  <span data-ttu-id="b1b14-226">Вызовите метод <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A> , чтобы создать подписку.</span><span class="sxs-lookup"><span data-stu-id="b1b14-226">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A> method to create the subscription.</span></span>  
  
#### <a name="to-define-a-replication-agent-schedule-when-you-create-a-pull-subscription-to-a-transactional-publication"></a><span data-ttu-id="b1b14-227">Создание расписания агента репликации при создании подписки по запросу на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="b1b14-227">To define a replication agent schedule when you create a pull subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="b1b14-228">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransPullSubscription> для создаваемой подписки.</span><span class="sxs-lookup"><span data-stu-id="b1b14-228">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class for the subscription you are creating.</span></span> <span data-ttu-id="b1b14-229">Дополнительные сведения см. в статье [Создание подписки по запросу](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-229">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
2.  <span data-ttu-id="b1b14-230">Перед вызовом метода <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A>установите одно или несколько из следующих полей свойства <xref:Microsoft.SqlServer.Replication.PullSubscription.AgentSchedule%2A> :</span><span class="sxs-lookup"><span data-stu-id="b1b14-230">Before you call <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A>, set one or more of the following fields of the <xref:Microsoft.SqlServer.Replication.PullSubscription.AgentSchedule%2A> property:</span></span>  
  
    -   <span data-ttu-id="b1b14-231"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> — тип интервала для запуска агента по расписанию (например ежедневно или еженедельно);</span><span class="sxs-lookup"><span data-stu-id="b1b14-231"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - the type of frequency (such as daily or weekly) that you use when you schedule the agent.</span></span>  
  
    -   <span data-ttu-id="b1b14-232"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> — день недели, в который запускается агент;</span><span class="sxs-lookup"><span data-stu-id="b1b14-232"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - the day of the week that an agent runs.</span></span>  
  
    -   <span data-ttu-id="b1b14-233"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> — неделя в заданном месяце, на которой запускается агент при ежемесячном режиме работы;</span><span class="sxs-lookup"><span data-stu-id="b1b14-233"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - the week of a given month that the agent is scheduled to run monthly.</span></span>  
  
    -   <span data-ttu-id="b1b14-234"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> — число частотных единиц, проходящих между последовательными синхронизациями;</span><span class="sxs-lookup"><span data-stu-id="b1b14-234"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - the number of frequency-type units that occur between synchronizations.</span></span>  
  
    -   <span data-ttu-id="b1b14-235"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> — частотная единица, используемая, если агент запускается чаще одного раза в день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-235"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - the frequency unit when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="b1b14-236"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> — число частотных единиц, проходящих между запусками агента, если он запускается чаще одного раза в день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-236"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="b1b14-237"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> — время самого раннего запуска агента в заданный день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-237"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - earliest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="b1b14-238"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> — время самого позднего запуска агента в заданный день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-238"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - latest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="b1b14-239"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> — первый день действия расписания агента;</span><span class="sxs-lookup"><span data-stu-id="b1b14-239"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - first day that the agent schedule is in effect.</span></span>  
  
    -   <span data-ttu-id="b1b14-240"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> — последний день действия расписания агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-240"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - last day that the agent schedule is in effect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b1b14-241">Если не задать одно из этих свойств, будет использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1b14-241">If you do not specify one of these properties, a default value is set.</span></span>  
  
3.  <span data-ttu-id="b1b14-242">Вызовите метод <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A> , чтобы создать подписку.</span><span class="sxs-lookup"><span data-stu-id="b1b14-242">Call the <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A> method to create the subscription.</span></span>  
  
#### <a name="to-define-a-replication-agent-schedule-when-you-create-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="b1b14-243">Создание расписания агента репликации при создании подписки по запросу на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="b1b14-243">To define a replication agent schedule when you create a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b1b14-244">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergePullSubscription> для создаваемой подписки.</span><span class="sxs-lookup"><span data-stu-id="b1b14-244">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class for the subscription you are creating.</span></span> <span data-ttu-id="b1b14-245">Дополнительные сведения см. в статье [Создание подписки по запросу](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-245">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
2.  <span data-ttu-id="b1b14-246">Перед вызовом метода <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A>установите одно или несколько из следующих полей свойства <xref:Microsoft.SqlServer.Replication.PullSubscription.AgentSchedule%2A> :</span><span class="sxs-lookup"><span data-stu-id="b1b14-246">Before you call <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A>, set one or more of the following fields of the <xref:Microsoft.SqlServer.Replication.PullSubscription.AgentSchedule%2A> property:</span></span>  
  
    -   <span data-ttu-id="b1b14-247"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> — тип интервала для запуска агента по расписанию (например ежедневно или еженедельно);</span><span class="sxs-lookup"><span data-stu-id="b1b14-247"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - the type of frequency (such as daily or weekly) that you use when you schedule the agent.</span></span>  
  
    -   <span data-ttu-id="b1b14-248"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> — день недели, в который запускается агент;</span><span class="sxs-lookup"><span data-stu-id="b1b14-248"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - the day of the week that an agent runs.</span></span>  
  
    -   <span data-ttu-id="b1b14-249"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> — неделя в заданном месяце, на которой запускается агент при ежемесячном режиме работы;</span><span class="sxs-lookup"><span data-stu-id="b1b14-249"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - the week of a given month that the agent is scheduled to run monthly.</span></span>  
  
    -   <span data-ttu-id="b1b14-250"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> — число частотных единиц, проходящих между последовательными синхронизациями;</span><span class="sxs-lookup"><span data-stu-id="b1b14-250"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - the number of frequency-type units that occur between synchronizations.</span></span>  
  
    -   <span data-ttu-id="b1b14-251"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> — частотная единица, используемая, если агент запускается чаще одного раза в день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-251"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - the frequency unit when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="b1b14-252"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> — число частотных единиц, проходящих между запусками агента, если он запускается чаще одного раза в день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-252"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="b1b14-253"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> — время самого раннего запуска агента в заданный день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-253"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - earliest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="b1b14-254"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> — время самого позднего запуска агента в заданный день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-254"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - latest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="b1b14-255"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> — первый день действия расписания агента;</span><span class="sxs-lookup"><span data-stu-id="b1b14-255"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - first day that the agent schedule is in effect.</span></span>  
  
    -   <span data-ttu-id="b1b14-256"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> — последний день действия расписания агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-256"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - last day that the agent schedule is in effect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b1b14-257">Если не задать одно из этих свойств, будет использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1b14-257">If you do not specify one of these properties, a default value is set.</span></span>  
  
3.  <span data-ttu-id="b1b14-258">Вызовите метод <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A> , чтобы создать подписку.</span><span class="sxs-lookup"><span data-stu-id="b1b14-258">Call the <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A> method to create the subscription.</span></span>  
  
#### <a name="to-define-a-replication-agent-schedule-when-you-create-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="b1b14-259">Создание расписания агента репликации при создании принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="b1b14-259">To define a replication agent schedule when you create a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b1b14-260">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeSubscription> для создаваемой подписки.</span><span class="sxs-lookup"><span data-stu-id="b1b14-260">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class for the subscription you are creating.</span></span> <span data-ttu-id="b1b14-261">Дополнительные сведения см. в статье [Создание принудительной подписки](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b1b14-261">For more information, see [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="b1b14-262">Перед вызовом метода <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A>установите одно или несколько из следующих полей свойства <xref:Microsoft.SqlServer.Replication.Subscription.AgentSchedule%2A> :</span><span class="sxs-lookup"><span data-stu-id="b1b14-262">Before you call <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A>, set one or more of the following fields of the <xref:Microsoft.SqlServer.Replication.Subscription.AgentSchedule%2A> property:</span></span>  
  
    -   <span data-ttu-id="b1b14-263"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> — тип интервала для запуска агента по расписанию (например ежедневно или еженедельно);</span><span class="sxs-lookup"><span data-stu-id="b1b14-263"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - the type of frequency (such as daily or weekly) that you use when you schedule the agent.</span></span>  
  
    -   <span data-ttu-id="b1b14-264"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> — день недели, в который запускается агент;</span><span class="sxs-lookup"><span data-stu-id="b1b14-264"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - the day of the week that an agent runs.</span></span>  
  
    -   <span data-ttu-id="b1b14-265"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> — неделя в заданном месяце, на которой запускается агент при ежемесячном режиме работы;</span><span class="sxs-lookup"><span data-stu-id="b1b14-265"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - the week of a given month that the agent is scheduled to run monthly.</span></span>  
  
    -   <span data-ttu-id="b1b14-266"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> — число частотных единиц, проходящих между последовательными синхронизациями;</span><span class="sxs-lookup"><span data-stu-id="b1b14-266"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - the number of frequency-type units that occur between synchronizations.</span></span>  
  
    -   <span data-ttu-id="b1b14-267"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> — частотная единица, используемая, если агент запускается чаще одного раза в день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-267"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - the frequency unit when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="b1b14-268"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> — число частотных единиц, проходящих между запусками агента, если он запускается чаще одного раза в день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-268"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="b1b14-269"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> — время самого раннего запуска агента в заданный день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-269"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - earliest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="b1b14-270"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> — время самого позднего запуска агента в заданный день;</span><span class="sxs-lookup"><span data-stu-id="b1b14-270"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - latest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="b1b14-271"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> — первый день действия расписания агента;</span><span class="sxs-lookup"><span data-stu-id="b1b14-271"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - first day that the agent schedule is in effect.</span></span>  
  
    -   <span data-ttu-id="b1b14-272"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> — последний день действия расписания агента.</span><span class="sxs-lookup"><span data-stu-id="b1b14-272"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - last day that the agent schedule is in effect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b1b14-273">Если не задать одно из этих свойств, будет использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1b14-273">If you do not specify one of these properties, a default value is set.</span></span>  
  
3.  <span data-ttu-id="b1b14-274">Вызовите метод <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A> , чтобы создать подписку.</span><span class="sxs-lookup"><span data-stu-id="b1b14-274">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A> method to create the subscription.</span></span>  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="b1b14-275">Пример (объекты RMO)</span><span class="sxs-lookup"><span data-stu-id="b1b14-275">Example (RMO)</span></span>  
 <span data-ttu-id="b1b14-276">В следующем примере производится создание принудительной подписки на публикацию слиянием, а также задается расписание синхронизации указанной подписки.</span><span class="sxs-lookup"><span data-stu-id="b1b14-276">This example creates a push subscription to a merge publication and specifies the schedule on which the subscription is synchronized.</span></span>  
  
 [!code-csharp[HowTo#rmo_CreateMergePushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_createmergepushsub)]  
  
 [!code-vb[HowTo#rmo_vb_CreateMergePushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_createmergepushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="b1b14-277">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1b14-277">See Also</span></span>  
 <span data-ttu-id="b1b14-278">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="b1b14-278">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 <span data-ttu-id="b1b14-279">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="b1b14-279">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="b1b14-280">[Синхронизация принудительной подписки](synchronize-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b1b14-280">[Synchronize a Push Subscription](synchronize-a-push-subscription.md) </span></span>  
 <span data-ttu-id="b1b14-281">[Синхронизация подписки по запросу](synchronize-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b1b14-281">[Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="b1b14-282">Синхронизация данных</span><span class="sxs-lookup"><span data-stu-id="b1b14-282">Synchronize Data</span></span>](synchronize-data.md)  
  
  
