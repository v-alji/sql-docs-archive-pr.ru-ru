---
title: Приостановка или возобновление сеанса зеркального отображения базы данных (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- resuming database mirroring
- database mirroring [SQL Server], sessions
- database mirroring [SQL Server], pausing
- database mirroring [SQL Server], resuming
- pausing database mirroring
ms.assetid: 05ede3b4-6abe-4442-abb7-9f5aee1d6bc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8a9e30bed3ff268fcfdc6e352ad15ebedfe4e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733114"
---
# <a name="pause-or-resume-a-database-mirroring-session-sql-server"></a><span data-ttu-id="7a561-102">Приостановка или возобновление сеанса зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a561-102">Pause or Resume a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="7a561-103">В этом разделе описано, как приостановить и возобновить зеркальное отображение базы данных [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a561-103">This topic describes how to pause or resume database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7a561-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7a561-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a561-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7a561-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a561-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7a561-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a561-107">**Выполнение ReplaceThisText с помощью:**</span><span class="sxs-lookup"><span data-stu-id="7a561-107">**To ReplaceThisText, using:**</span></span>  
  
     [<span data-ttu-id="7a561-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a561-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a561-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a561-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="7a561-110">**Дальнейшие действия.**  [После приостановки или возобновления зеркального отображения базы данных](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="7a561-110">**Follow Up:**  [After Pausing or Resuming Database Mirroring](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a561-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7a561-111">Before You Begin</span></span>  
 <span data-ttu-id="7a561-112">В любой момент сеанс зеркального отображения базы данных можно приостановить, что дает возможность повышать производительность при возникновении узких мест. Затем в любое время приостановленный сеанс можно возобновить.</span><span class="sxs-lookup"><span data-stu-id="7a561-112">At any time, you can suspend a database mirroring session, which might improve performance during bottlenecks, and you can resume a suspended session at any time.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7a561-113">После принудительного обслуживания при повторном подключении исходного основного сервера зеркальное отображение приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="7a561-113">After a forced service, when the original principal server reconnects, mirroring is suspended.</span></span> <span data-ttu-id="7a561-114">Возобновление зеркального отображения в данной ситуации может привести к потере данных исходным основным сервером.</span><span class="sxs-lookup"><span data-stu-id="7a561-114">Resuming mirroring in this situation could possibly cause data loss on the original principal server.</span></span> <span data-ttu-id="7a561-115">Дополнительные сведения о том, как действовать при возможной потере данных, см. в разделе [Переключение ролей во время сеанса зеркального отображения базы данных (SQL Server)](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a561-115">For information about managing the potential data loss, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a561-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="7a561-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a561-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="7a561-117">Permissions</span></span>  
 <span data-ttu-id="7a561-118">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="7a561-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a561-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a561-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7a561-120">Приостановить или возобновить сеанс зеркального отображения базы данных можно на странице **Свойства базы данных — зеркальное отображение** .</span><span class="sxs-lookup"><span data-stu-id="7a561-120">To pause or resume a database mirroring session use the **Database Properties Mirroring** page.</span></span>  
  
#### <a name="to-pause-or-resume-database-mirroring"></a><span data-ttu-id="7a561-121">Приостановление или возобновление зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="7a561-121">To pause or resume database mirroring</span></span>  
  
1.  <span data-ttu-id="7a561-122">Во время сеанса зеркального отображения базы данных установите соединение с экземпляром главного сервера, в обозревателе объектов щелкните имя сервера и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="7a561-122">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="7a561-123">Разверните **Базы данных**и выберите нужную базу данных.</span><span class="sxs-lookup"><span data-stu-id="7a561-123">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="7a561-124">Щелкните базу данных правой кнопкой мыши, выберите **Задачи**, а затем **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="7a561-124">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="7a561-125">Откроется страница **Зеркальное отображение** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="7a561-125">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="7a561-126">Чтобы приостановить сеанс, выберите пункт **Приостановить**.</span><span class="sxs-lookup"><span data-stu-id="7a561-126">To pause the session, click **Pause**.</span></span>  
  
     <span data-ttu-id="7a561-127">Запрашивается подтверждение. Если нажать кнопку **Да**, то сеанс будет приостановлен, а кнопка изменится на **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7a561-127">A prompt asks for confirmation; if you click **Yes**, the session is paused, and the button changes to **Resume**.</span></span>  
  
     <span data-ttu-id="7a561-128">Дополнительные сведения о влиянии приостановки сеанса см. в разделе [Приостановка и возобновление зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a561-128">For more information about the impact of pausing a session, see [Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="7a561-129">Чтобы возобновить сеанс, нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7a561-129">To resume the session, click **Resume**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a561-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a561-130">Using Transact-SQL</span></span>  
  
#### <a name="to-pause-database-mirroring"></a><span data-ttu-id="7a561-131">Приостановка зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="7a561-131">To pause database mirroring</span></span>  
  
1.  <span data-ttu-id="7a561-132">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] для любого участника.</span><span class="sxs-lookup"><span data-stu-id="7a561-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="7a561-133">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7a561-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a561-134">Выполните следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="7a561-134">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="7a561-135">ALTER DATABASE *имя_базы_данных* SET PARTNER SUSPEND</span><span class="sxs-lookup"><span data-stu-id="7a561-135">ALTER DATABASE *database_name* SET PARTNER SUSPEND</span></span>  
  
     <span data-ttu-id="7a561-136">где *имя_базы_данных* — это зеркально отображаемая база данных, сеанс которой нужно приостановить.</span><span class="sxs-lookup"><span data-stu-id="7a561-136">where *database_name* is the mirrored database whose session you want to you want to suspend.</span></span>  
  
     <span data-ttu-id="7a561-137">В следующем примере показана приостановка образца базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a561-137">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER SUSPEND;  
    ```  
  
##### <a name="to-resume-database-mirroring"></a><span data-ttu-id="7a561-138">Возобновление зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="7a561-138">To resume database mirroring</span></span>  
  
1.  <span data-ttu-id="7a561-139">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] для любого участника.</span><span class="sxs-lookup"><span data-stu-id="7a561-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="7a561-140">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7a561-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a561-141">Выполните следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="7a561-141">Issue the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="7a561-142">ALTER DATABASE *имя_базы_данных* SET PARTNER RESUME</span><span class="sxs-lookup"><span data-stu-id="7a561-142">ALTER DATABASE *database_name* SET PARTNER RESUME</span></span>  
  
     <span data-ttu-id="7a561-143">где *database_name* — зеркально отображаемая база данных, сеанс которой нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="7a561-143">where *database_name* is the mirrored database whose session you want to resume.</span></span>  
  
     <span data-ttu-id="7a561-144">В следующем примере показана приостановка образца базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a561-144">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER RESUME;  
    ```  
  
##  <a name="follow-up-after-pausing-or-resuming-database-mirroring"></a><a name="FollowUp"></a><span data-ttu-id="7a561-145">Дальнейшие действия. После приостановки или возобновления зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="7a561-145">Follow Up: After Pausing or Resuming Database Mirroring</span></span>  
  
-   <span data-ttu-id="7a561-146">**После приостановки зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="7a561-146">**After pausing database mirroring**</span></span>  
  
     <span data-ttu-id="7a561-147">В базе данных-источнике примите меры предосторожности, чтобы избежать переполнения журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="7a561-147">On the primary database, take precautions to avoid a full transaction log.</span></span> <span data-ttu-id="7a561-148">Дополнительные сведения см. в статье [Журнал транзакций (SQL Server)](../../relational-databases/logs/the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a561-148">For more information, see [The Transaction Log &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="7a561-149">**После возобновления зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="7a561-149">**After resuming database mirroring**</span></span>  
  
     <span data-ttu-id="7a561-150">Возобновление зеркального отображения базы данных переводит зеркальную базу данных в состояние SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="7a561-150">Resuming database mirroring places the mirror database in the SYNCHRONIZING state.</span></span> <span data-ttu-id="7a561-151">Если уровень безопасности установлен в FULL, зеркало захватывается основным сервером, и зеркальная база данных переходит в состояние SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="7a561-151">If the safety level is FULL, the mirror catches up with the principal and the mirror database enters the SYNCHRONIZED state.</span></span> <span data-ttu-id="7a561-152">В этот момент возможна отработка отказа.</span><span class="sxs-lookup"><span data-stu-id="7a561-152">At this point, failover becomes possible.</span></span> <span data-ttu-id="7a561-153">Если присутствует следящий сервер, установленный в положение ON, возможна автоматическия отработка отказа.</span><span class="sxs-lookup"><span data-stu-id="7a561-153">If the witness is present and ON, automatic failover is possible.</span></span> <span data-ttu-id="7a561-154">В случае отсутствия следящего сервера возможна отработка отказа вручную.</span><span class="sxs-lookup"><span data-stu-id="7a561-154">In the absence of a witness, manual failover is possible.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7a561-155">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7a561-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7a561-156">Удаление зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a561-156">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7a561-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a561-157">See Also</span></span>  
 [<span data-ttu-id="7a561-158">Зеркальное отображение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a561-158">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
