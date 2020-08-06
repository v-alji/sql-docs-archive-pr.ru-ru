---
title: Изменение задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
ms.assetid: dd5e5f20-20c4-4ab9-a19a-db87577dcd43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0d25830ad119a1f5f344a4dcf318c35bee5f86ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658060"
---
# <a name="modify-a-job"></a><span data-ttu-id="1bd56-102">Изменение задания</span><span class="sxs-lookup"><span data-stu-id="1bd56-102">Modify a Job</span></span>
  <span data-ttu-id="1bd56-103">В этом разделе описывается изменение свойств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданий агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1bd56-103">This topic describes how to change the properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="1bd56-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1bd56-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1bd56-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1bd56-105">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="1bd56-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1bd56-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1bd56-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1bd56-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1bd56-108">**Для изменения задания используется:**</span><span class="sxs-lookup"><span data-stu-id="1bd56-108">**To modify a job, using:**</span></span>  
  
     [<span data-ttu-id="1bd56-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1bd56-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="1bd56-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1bd56-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="1bd56-111">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bd56-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1bd56-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1bd56-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1bd56-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1bd56-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1bd56-114">Главное задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может быть ориентировано как на локальный, так и на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="1bd56-114">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1bd56-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="1bd56-115">Security</span></span>  
 <span data-ttu-id="1bd56-116">Если пользователь не является членом предопределенной роли сервера **sysadmin** , он может изменять только свои собственные задания.</span><span class="sxs-lookup"><span data-stu-id="1bd56-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="1bd56-117">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="1bd56-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="1bd56-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1bd56-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="1bd56-119">Изменение задания</span><span class="sxs-lookup"><span data-stu-id="1bd56-119">To modify a job</span></span>  
  
1.  <span data-ttu-id="1bd56-120">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1bd56-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1bd56-121">Разверните узел **Агент SQL Server**, выберите раздел **Задания**, щелкните правой кнопкой мыши задание, которое нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1bd56-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1bd56-122">В диалоговом окне **Свойства задания** обновите свойства, шаги, расписание, предупреждения и уведомления задания, воспользовавшись соответствующими страницами.</span><span class="sxs-lookup"><span data-stu-id="1bd56-122">In the **Job Properties** dialog box, update the job's properties, steps, schedule, alerts, and notifications using the corresponding pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="1bd56-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1bd56-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="1bd56-124">Изменение задания</span><span class="sxs-lookup"><span data-stu-id="1bd56-124">To modify a job</span></span>  
  
1.  <span data-ttu-id="1bd56-125">В обозревателе объектов подключитесь к экземпляру компонента Database Engine и разверните его.</span><span class="sxs-lookup"><span data-stu-id="1bd56-125">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1bd56-126">На панели инструментов нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1bd56-126">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1bd56-127">В окне запроса используйте следующие системные хранимые процедуры для изменения задания.</span><span class="sxs-lookup"><span data-stu-id="1bd56-127">In the query window, use the following system stored procedures to modify a job.</span></span>  
  
    -   <span data-ttu-id="1bd56-128">Выполните [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) , чтобы изменить атрибуты задания.</span><span class="sxs-lookup"><span data-stu-id="1bd56-128">Execute [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) to change the attributes of a job.</span></span>  
  
    -   <span data-ttu-id="1bd56-129">Выполните [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) , чтобы изменить сведения о расписании для определения задания.</span><span class="sxs-lookup"><span data-stu-id="1bd56-129">Execute [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) to change the scheduling details for a job definition.</span></span>  
  
    -   <span data-ttu-id="1bd56-130">Выполните [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) , чтобы добавить новые шаги задания.</span><span class="sxs-lookup"><span data-stu-id="1bd56-130">Execute [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) to add new job steps.</span></span>  
  
    -   <span data-ttu-id="1bd56-131">Выполните [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) , чтобы изменить уже существующие шаги задания.</span><span class="sxs-lookup"><span data-stu-id="1bd56-131">Execute [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) to change pre-existing job steps.</span></span>  
  
    -   <span data-ttu-id="1bd56-132">Выполните [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) , чтобы удалить шаг задания из задания.</span><span class="sxs-lookup"><span data-stu-id="1bd56-132">Execute [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) to remove a job step from a job.</span></span>  
  
    -   <span data-ttu-id="1bd56-133">Дополнительные хранимые процедуры для изменения любого главного задания агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1bd56-133">Additional stored procedures to modify any SQL Server Agent master job:</span></span>  
  
        -   <span data-ttu-id="1bd56-134">Выполните [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) , чтобы удалить сервер, который в настоящее время связан с заданием.</span><span class="sxs-lookup"><span data-stu-id="1bd56-134">Execute [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) to delete a server currently associated with a job.</span></span>  
  
        -   <span data-ttu-id="1bd56-135">Выполните [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) , чтобы связать сервер с текущим заданием.</span><span class="sxs-lookup"><span data-stu-id="1bd56-135">Execute [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) to associate a server with the current job.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="1bd56-136">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bd56-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="1bd56-137">**Изменение задания**</span><span class="sxs-lookup"><span data-stu-id="1bd56-137">**To modify a job**</span></span>  
  
 <span data-ttu-id="1bd56-138">Воспользуйтесь классом `Job` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1bd56-138">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="1bd56-139">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="1bd56-139">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
