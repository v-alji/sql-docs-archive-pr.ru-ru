---
title: Создание расписания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scheduling jobs [SQL Server]
- SQL Server Agent jobs, scheduling
- jobs [SQL Server Agent], scheduling
- schedules [SQL Server], jobs
ms.assetid: 8c7ef3b3-c06d-4a27-802d-ed329dc86ef3
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac71a61163dceb06697b61ef24fce2117d57cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667540"
---
# <a name="create-a-schedule"></a><span data-ttu-id="df47f-102">Создание расписания</span><span class="sxs-lookup"><span data-stu-id="df47f-102">Create a Schedule</span></span>
  <span data-ttu-id="df47f-103">Расписание для заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] вы можете создать с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или управляющих объектов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="df47f-103">You can create a schedule for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="df47f-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="df47f-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="df47f-105">Безопасность</span><span class="sxs-lookup"><span data-stu-id="df47f-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="df47f-106">**Для создания расписания используется:**</span><span class="sxs-lookup"><span data-stu-id="df47f-106">**To create a schedule, using:**</span></span>  
  
     [<span data-ttu-id="df47f-107">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="df47f-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="df47f-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="df47f-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="df47f-109">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="df47f-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="df47f-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="df47f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="df47f-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="df47f-111">Security</span></span>  
 <span data-ttu-id="df47f-112">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="df47f-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="df47f-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="df47f-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="df47f-114">Создание расписания</span><span class="sxs-lookup"><span data-stu-id="df47f-114">To create a schedule</span></span>  
  
1.  <span data-ttu-id="df47f-115">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="df47f-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="df47f-116">Разверните узел **Агент SQL Server**, щелкните правой кнопкой мыши узел **Задания**и выберите **Управление расписаниями**.</span><span class="sxs-lookup"><span data-stu-id="df47f-116">Expand **SQL Server Agent**, right-click **Jobs**, and select **Manage Schedules**.</span></span>  
  
3.  <span data-ttu-id="df47f-117">В диалоговом окне **Управление расписаниями** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="df47f-117">In the **Manage Schedules** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="df47f-118">В поле **Имя** введите имя нового расписания.</span><span class="sxs-lookup"><span data-stu-id="df47f-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="df47f-119">Если не нужно, чтобы расписание вступило в силу немедленно после создания, снимите флажок **Включено** .</span><span class="sxs-lookup"><span data-stu-id="df47f-119">If you do not want the schedule to take effect immediately after it has been created, clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="df47f-120">Выберите одно из следующих значений для параметра **Тип расписания**:</span><span class="sxs-lookup"><span data-stu-id="df47f-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="df47f-121">Чтобы запускать задание, когда процессоры переходят в состояние бездействия, щелкните **Запускать при бездействии процессоров**.</span><span class="sxs-lookup"><span data-stu-id="df47f-121">To start the job when the CPUs reach an idle condition, click **Start whenever the CPUs become idle**.</span></span>  
  
    -   <span data-ttu-id="df47f-122">Если необходимо периодическое выполнение расписания, выберите пункт **Повторяющееся задание**.</span><span class="sxs-lookup"><span data-stu-id="df47f-122">If you want a schedule to run repeatedly, click **Recurring**.</span></span> <span data-ttu-id="df47f-123">Затем в диалоговом окне заполните группы **Частота**, **Сколько раз в день**и **Продолжительность** .</span><span class="sxs-lookup"><span data-stu-id="df47f-123">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="df47f-124">Если планируется однократное выполнение, выберите **Один раз**.</span><span class="sxs-lookup"><span data-stu-id="df47f-124">If you want the schedule to run only one time, click **One time**.</span></span> <span data-ttu-id="df47f-125">Для установки расписания **Один раз** заполните в диалоговом окне группу **Однократное выполнение** .</span><span class="sxs-lookup"><span data-stu-id="df47f-125">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="df47f-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="df47f-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="df47f-127">Создание расписания</span><span class="sxs-lookup"><span data-stu-id="df47f-127">To create a schedule</span></span>  
  
1.  <span data-ttu-id="df47f-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df47f-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="df47f-129">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="df47f-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="df47f-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="df47f-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a schedule named RunOnce.   
    -- The schedule runs one time, at 23:30 on the day that the schedule is created.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
  
    GO  
    ```  
  
 <span data-ttu-id="df47f-131">Дополнительные сведения см. в разделе [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="df47f-131">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="df47f-132">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="df47f-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="df47f-133">**Создание расписания**</span><span class="sxs-lookup"><span data-stu-id="df47f-133">**To create a schedule**</span></span>  
  
 <span data-ttu-id="df47f-134">Воспользуйтесь классом `JobSchedule` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="df47f-134">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="df47f-135">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="df47f-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
