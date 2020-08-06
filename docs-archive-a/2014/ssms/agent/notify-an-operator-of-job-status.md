---
title: Уведомление оператора о состоянии задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- jobs [SQL Server Agent], notification options
- SQL Server Agent jobs, status
- jobs [SQL Server Agent], status
- SQL Server Agent jobs, notification options
- notifications [SQL Server], job status
ms.assetid: e7399505-27ac-48d9-a637-73bf92b9df49
author: stevestein
ms.author: sstein
ms.openlocfilehash: a202327ad63cf7ef8f51d3572b257816ee6d9419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658045"
---
# <a name="notify-an-operator-of-job-status"></a><span data-ttu-id="f158a-102">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="f158a-102">Notify an Operator of Job Status</span></span>
  <span data-ttu-id="f158a-103">В этом разделе описано, как задать параметры уведомления в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server, чтобы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агент мог отправлять уведомления операторам о заданиях.</span><span class="sxs-lookup"><span data-stu-id="f158a-103">This topic describes how to set notification options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects, so [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can send notifications to operators about jobs.</span></span>  
  
 <span data-ttu-id="f158a-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f158a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f158a-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f158a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f158a-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f158a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f158a-107">**Для уведомления оператора о состоянии задания используется:**</span><span class="sxs-lookup"><span data-stu-id="f158a-107">**To notify an operator of job status, using:**</span></span>  
  
     [<span data-ttu-id="f158a-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f158a-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f158a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f158a-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="f158a-110">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="f158a-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f158a-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f158a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f158a-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="f158a-112">Security</span></span>  
 <span data-ttu-id="f158a-113">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f158a-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f158a-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f158a-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="f158a-115">Уведомление оператора о состоянии задания</span><span class="sxs-lookup"><span data-stu-id="f158a-115">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="f158a-116">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f158a-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f158a-117">Разверните узел **Агент SQL Server**, выберите раздел **Задания**, щелкните правой кнопкой мыши задание, которое нужно изменить, и затем выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f158a-117">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="f158a-118">В окне **Свойства задания** перейдите на страницу **Уведомления** .</span><span class="sxs-lookup"><span data-stu-id="f158a-118">In the **Job Properties** dialog box, select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="f158a-119">Если нужно оповещать оператора по электронной почте, установите флажок **Электронная почта**, выберите из списка оператора, а затем выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="f158a-119">If you want to notify an operator by e-mail, check **E-mail**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="f158a-120">**При успешном завершении задания** известить оператора о том, что задание удачно завершено.</span><span class="sxs-lookup"><span data-stu-id="f158a-120">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="f158a-121">**При ошибке задания** известить оператора о неуспешном завершении задания.</span><span class="sxs-lookup"><span data-stu-id="f158a-121">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="f158a-122">**При завершении задания** известить оператора независимо от состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="f158a-122">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
5.  <span data-ttu-id="f158a-123">Если необходимо оповещать оператора по пейджеру, отметьте **Пейджер**, выберите из списка оператора, а затем выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="f158a-123">If you want to notify an operator by pager, check **Page**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="f158a-124">**При успешном завершении задания** известить оператора о том, что задание удачно завершено.</span><span class="sxs-lookup"><span data-stu-id="f158a-124">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="f158a-125">**При ошибке задания** известить оператора о неуспешном завершении задания.</span><span class="sxs-lookup"><span data-stu-id="f158a-125">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="f158a-126">**При завершении задания** известить оператора независимо от состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="f158a-126">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
6.  <span data-ttu-id="f158a-127">Если нужно оповещать оператора через net send, установите флажок **Команда net send**, выберите из списка оператора, а затем выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="f158a-127">If you want to notify an operator by net send, check **Net send**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="f158a-128">**При успешном завершении задания** известить оператора о том, что задание удачно завершено.</span><span class="sxs-lookup"><span data-stu-id="f158a-128">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="f158a-129">**При ошибке задания** известить оператора о неуспешном завершении задания.</span><span class="sxs-lookup"><span data-stu-id="f158a-129">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="f158a-130">**При завершении задания** известить оператора независимо от состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="f158a-130">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="f158a-131">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f158a-131">Using Transact-SQL</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="f158a-132">Уведомление оператора о состоянии задания</span><span class="sxs-lookup"><span data-stu-id="f158a-132">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="f158a-133">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f158a-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f158a-134">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f158a-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f158a-135">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f158a-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adds an e-mail notification for the specified alert (Test Alert).  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_notification   
    @alert_name = N'Test Alert',   
    @operator_name = N'Fran??ois Ajenstat',   
    @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="f158a-136">Дополнительные сведения см. в разделе [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f158a-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f158a-137">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="f158a-137">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f158a-138">**Уведомление оператора о состоянии задания**</span><span class="sxs-lookup"><span data-stu-id="f158a-138">**To notify an operator of job status**</span></span>  
  
 <span data-ttu-id="f158a-139">Воспользуйтесь классом `Job` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f158a-139">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="f158a-140">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="f158a-140">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
