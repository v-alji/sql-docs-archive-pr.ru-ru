---
title: Передача другим пользователям права владения заданием | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], owners
- owners [SQL Server], jobs
- SQL Server Agent jobs, owners
ms.assetid: 2ded5e9c-4251-4fb1-a047-99f13d150b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2cf03fdc9031ce9761125d95619438837f2959bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654722"
---
# <a name="give-others-ownership-of-a-job"></a><span data-ttu-id="9f4f5-102">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="9f4f5-102">Give Others Ownership of a Job</span></span>
  <span data-ttu-id="9f4f5-103">В этом разделе описывается, как переназначить владение [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданиями агента другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-103">This topic describes how to reassign ownership of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>  
  
-   <span data-ttu-id="9f4f5-104">**Перед началом работы**  [Ограничения](#Restrictions), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="9f4f5-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="9f4f5-105">**Для передачи другим пользователям права владения заданием используется:**</span><span class="sxs-lookup"><span data-stu-id="9f4f5-105">**To give others ownership of a job, using:**</span></span>  
  
     [<span data-ttu-id="9f4f5-106">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9f4f5-106">SQL Server Management Studio</span></span>](#SSMSProc2)  
  
     [<span data-ttu-id="9f4f5-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9f4f5-107">Transact-SQL</span></span>](#TsqlProc2)  
  
     [<span data-ttu-id="9f4f5-108">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f4f5-108">SQL Server Management Objects</span></span>](#SMOProc2)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9f4f5-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9f4f5-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9f4f5-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9f4f5-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="9f4f5-111">Чтобы создать задание, пользователь должен быть членом одной из предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="9f4f5-111">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="9f4f5-112">Задание может быть изменено его владельцем или членом роли **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="9f4f5-112">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="9f4f5-113">Дополнительные сведения о предопределенных ролях базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Предопределенные роли базы данных агента SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9f4f5-113">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="9f4f5-114">Чтобы изменить владельца задания, необходимо быть системным администратором.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-114">You must be a system administrator to change the owner of a job.</span></span>  
  
 <span data-ttu-id="9f4f5-115">Назначение задания другому имени входа не гарантирует того, что новый владелец обладает достаточными разрешениями для успешного запуска задания.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-115">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9f4f5-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="9f4f5-116">Security</span></span>  
 <span data-ttu-id="9f4f5-117">Из соображений безопасности изменять определение задания может только его владелец или член роли **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="9f4f5-117">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="9f4f5-118">Только члены предопределенной роли сервера **sysadmin** могут предоставлять права владения заданием другим пользователям, а также могут запускать любое задание, независимо от того, кто является его владельцем.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-118">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f4f5-119">Если задать в качестве нового владельца задания пользователя, не являющегося членом предопределенной роли сервера **sysadmin** , а задание выполняет шаги, которым требуются учетные записи-посредники (например, выполнение пакета служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), убедитесь в том, что пользователь имеет доступ к этой учетной записи-посреднику, в противном случае задание завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-119">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9f4f5-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="9f4f5-120">Permissions</span></span>  
 <span data-ttu-id="9f4f5-121">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="9f4f5-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProc2"></a> <span data-ttu-id="9f4f5-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9f4f5-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9f4f5-123">**Передача другим пользователям права владения заданием**</span><span class="sxs-lookup"><span data-stu-id="9f4f5-123">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="9f4f5-124">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9f4f5-125">Разверните **Агент SQL Server**, **Задания**, затем щелкните правой кнопкой мыши задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9f4f5-126">В списке **Владелец** выберите имя входа.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-126">In the **Owner** list, select a login.</span></span> <span data-ttu-id="9f4f5-127">Чтобы изменить владельца задания, необходимо быть системным администратором.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-127">You must be a system administrator to change the owner of a job.</span></span>  
  
     <span data-ttu-id="9f4f5-128">Назначение задания другому имени входа не гарантирует того, что новый владелец обладает достаточными разрешениями для успешного запуска задания.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-128">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProc2"></a> <span data-ttu-id="9f4f5-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9f4f5-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="9f4f5-130">**Передача другим пользователям права владения заданием**</span><span class="sxs-lookup"><span data-stu-id="9f4f5-130">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="9f4f5-131">В обозревателе объектов подключитесь к экземпляру компонента Database Engine и разверните его.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-131">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9f4f5-132">На панели инструментов нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-132">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9f4f5-133">В окне запроса введите следующие инструкции, использующие [sp_manage_jobs_by_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) системной хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-133">In the query window, enter the following statements that use the [sp_manage_jobs_by_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) system stored procedure.</span></span> <span data-ttu-id="9f4f5-134">В следующем примере производится передача всех заданий от пользователя `danw` пользователю `fran??oisa`.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-134">The following example reassigns all jobs from `danw` to `fran??oisa`.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_manage_jobs_by_login  
        @action = N'REASSIGN',  
        @current_owner_login_name = N'danw',  
        @new_owner_login_name = N'fran??oisa' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProc2"></a><span data-ttu-id="9f4f5-135">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f4f5-135">Using SQL Server Management Objects</span></span>  

### <a name="to-give-others-ownership-of-a-job"></a><span data-ttu-id="9f4f5-136">Передача другим пользователям права владения заданием</span><span class="sxs-lookup"><span data-stu-id="9f4f5-136">To give others ownership of a job</span></span>
  
1.  <span data-ttu-id="9f4f5-137">Вызовите класс `Job` с использованием выбранного языка программирования, например Visual Basic, Visual C# или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f4f5-137">Call the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="9f4f5-138">Пример кода см. в разделе [Планирование автоматических административных задач в агенте SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="9f4f5-138">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f4f5-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f4f5-139">See Also</span></span>  
 <span data-ttu-id="9f4f5-140">[Реализация заданий](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="9f4f5-140">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="9f4f5-141">Создание заданий</span><span class="sxs-lookup"><span data-stu-id="9f4f5-141">Create Jobs</span></span>](create-jobs.md)  
