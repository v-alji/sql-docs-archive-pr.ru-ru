---
title: Создание шага задания CmdExec | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CmdExec jobs
ms.assetid: b48da5b4-6fe7-4eb7-bade-dc7d697c6d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48c557b8ea4228d27b73d361c50aac62232d1e00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659071"
---
# <a name="create-a-cmdexec-job-step"></a><span data-ttu-id="1ba9a-102">Create a CmdExec Job Step</span><span class="sxs-lookup"><span data-stu-id="1ba9a-102">Create a CmdExec Job Step</span></span>
  <span data-ttu-id="1ba9a-103">В этом разделе описывается создание и определение [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] шага задания агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , использующего исполняемую программу или команду операционной системы с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that uses an executable program or operating system command by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="1ba9a-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1ba9a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1ba9a-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1ba9a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1ba9a-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1ba9a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1ba9a-107">**Для создания шага задания CmdExec используется:**</span><span class="sxs-lookup"><span data-stu-id="1ba9a-107">**To create a CmdExec job step, using:**</span></span>  
  
     [<span data-ttu-id="1ba9a-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ba9a-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="1ba9a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1ba9a-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="1ba9a-110">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ba9a-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1ba9a-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1ba9a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1ba9a-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="1ba9a-112">Security</span></span>  
 <span data-ttu-id="1ba9a-113">По умолчанию только члены предопределенной роли сервера **sysadmin** могут создавать шаги задания CmdExec.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-113">By default, only members of the **sysadmin** fixed server role can create CmdExec job steps.</span></span> <span data-ttu-id="1ba9a-114">Шаги задания службы агента SQL Server запускаются под учетной записью службы агента SQL Server, если пользователь **sysadmin** не создал учетную запись-посредника.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-114">These job steps run under the context of the SQL Server Agent service account unless the **sysadmin** user creates a proxy account.</span></span> <span data-ttu-id="1ba9a-115">Пользователь, не являющийся членом предопределенной роли сервера **sysadmin** может создавать шаги задания CmdExec, только если у него есть доступ к учетной записи-посреднику CmdExec.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-115">Users who are not members of the **sysadmin** role can create CmdExec job steps if they have access to a CmdExec proxy account.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1ba9a-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="1ba9a-116">Permissions</span></span>  
 <span data-ttu-id="1ba9a-117">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="1ba9a-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="1ba9a-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ba9a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="1ba9a-119">Создание шага задания CmdExec</span><span class="sxs-lookup"><span data-stu-id="1ba9a-119">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="1ba9a-120">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1ba9a-121">Разверните **Агент SQL Server**, создайте задание или щелкните правой кнопкой мыши существующее задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-121">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1ba9a-122">В диалоговом окне **Свойства задания** выберите страницу **Шаги** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-122">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="1ba9a-123">В диалоговом окне **Новый шаг задания** введите **имя шага**задания.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-123">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="1ba9a-124">В списке **Тип** выберите **Операционная система (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-124">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
6.  <span data-ttu-id="1ba9a-125">В списке **Выполнять как** выберите учетную запись-посредник с учетными данными, используемыми в задании.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-125">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="1ba9a-126">По умолчанию шаги задания CmdExec выполняются под учетной записью службы агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-126">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
7.  <span data-ttu-id="1ba9a-127">В поле **Код завершения процесса успешной команды** введите значение от 0 до 999999.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-127">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
8.  <span data-ttu-id="1ba9a-128">В поле **Команда** введите команду операционной системы или программу для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-128">In the **Command** box, enter the operating system command or executable program.</span></span> <span data-ttu-id="1ba9a-129">Пример см. в разделе «Использование Transact T-SQL».</span><span class="sxs-lookup"><span data-stu-id="1ba9a-129">See "Using Transact T-SQL for an example.</span></span>  
  
9. <span data-ttu-id="1ba9a-130">Выберите вкладку **Дополнительно** , чтобы задать следующие параметры шага задания: действие, которое необходимо выполнить при успешном или неуспешном выполнении шага задания, количество попыток агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполнить шаг задания и файл, в который агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может записывать результат выполнения шага задания.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-130">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="1ba9a-131">Только члены предопределенной роли сервера **sysadmin** могут записывать выходные данные шага задания в файл операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-131">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="1ba9a-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1ba9a-132">Using Transact-SQL</span></span>  
  
### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="1ba9a-133">Создание шага задания CmdExec</span><span class="sxs-lookup"><span data-stu-id="1ba9a-133">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="1ba9a-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ba9a-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1ba9a-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1ba9a-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1ba9a-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses CmdExec  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'CMDEXEC',  
        @command = C:\clickme_scripts\SQL11\PostBOLReorg GetHsX.exe',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="1ba9a-137">Дополнительные сведения см. в разделе [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="1ba9a-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="1ba9a-138">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ba9a-138">Using SQL Server Management Objects</span></span>  

### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="1ba9a-139">Создание шага задания CmdExec</span><span class="sxs-lookup"><span data-stu-id="1ba9a-139">To create a CmdExec job step</span></span>
  
 <span data-ttu-id="1ba9a-140">Воспользуйтесь классом `JobStep` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1ba9a-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
