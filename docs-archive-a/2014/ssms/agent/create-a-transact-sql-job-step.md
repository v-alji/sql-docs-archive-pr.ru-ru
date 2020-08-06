---
title: Создание шага задания Transact-SQL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: 69c571a7-debe-4063-9d38-e4b6a1e8e84c
author: stevestein
ms.author: sstein
ms.openlocfilehash: b83ee944d2ca5c10ff1b77f3e6e6da6054b5c99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737472"
---
# <a name="create-a-transact-sql-job-step"></a><span data-ttu-id="3fbfc-102">Создание шага задания Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3fbfc-102">Create a Transact-SQL Job Step</span></span>
  <span data-ttu-id="3fbfc-103">В этом разделе описывается создание [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] шага задания агента, выполняющего [!INCLUDE[tsql](../../includes/tsql-md.md)] скрипты в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="3fbfc-104">Эти скрипты шагов задания могут вызывать хранимые процедуры и расширенные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-104">These job step scripts may call stored procedures and extended stored procedures.</span></span> <span data-ttu-id="3fbfc-105">Один шаг задания [!INCLUDE[tsql](../../includes/tsql-md.md)] может содержать несколько пакетов и команд GO.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-105">A single [!INCLUDE[tsql](../../includes/tsql-md.md)] job step can contain multiple batches and embedded GO commands.</span></span> <span data-ttu-id="3fbfc-106">Дополнительные сведения о создании заданий см. в разделе [Создание заданий](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="3fbfc-106">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
 <span data-ttu-id="3fbfc-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3fbfc-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3fbfc-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3fbfc-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3fbfc-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3fbfc-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3fbfc-110">**Для создания шага задания Transact-SQL используется:**</span><span class="sxs-lookup"><span data-stu-id="3fbfc-110">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="3fbfc-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3fbfc-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="3fbfc-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3fbfc-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="3fbfc-113">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="3fbfc-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3fbfc-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3fbfc-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3fbfc-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="3fbfc-115">Security</span></span>  
 <span data-ttu-id="3fbfc-116">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3fbfc-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="3fbfc-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3fbfc-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="3fbfc-118">Создание шага задания Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3fbfc-118">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="3fbfc-119">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3fbfc-120">Разверните **Агент SQL Server**, создайте задание или щелкните правой кнопкой мыши существующее задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-120">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3fbfc-121">В диалоговом окне **Свойства задания** выберите страницу **Шаги** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-121">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="3fbfc-122">В диалоговом окне **Новый шаг задания** введите **имя шага**задания.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-122">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="3fbfc-123">В списке **Тип** выберите **Скрипт Transact-SQL (TSQL)**.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-123">In the **Type** list, click **Transact-SQL Script (TSQL)**.</span></span>  
  
6.  <span data-ttu-id="3fbfc-124">На панели **Команда** введите пакет команд [!INCLUDE[tsql](../../includes/tsql-md.md)] или нажмите кнопку **Открыть** и выберите файл [!INCLUDE[tsql](../../includes/tsql-md.md)] , используемый в качестве команды.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-124">In the **Command** box, type the [!INCLUDE[tsql](../../includes/tsql-md.md)] command batches, or click **Open** to select a [!INCLUDE[tsql](../../includes/tsql-md.md)] file to use as the command.</span></span>  
  
7.  <span data-ttu-id="3fbfc-125">Нажмите кнопку **Синтаксический анализ** для проверки синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-125">Click **Parse** to check your syntax.</span></span>  
  
8.  <span data-ttu-id="3fbfc-126">Если синтаксис правильный, появится сообщение «Синтаксический анализ успешно завершен».</span><span class="sxs-lookup"><span data-stu-id="3fbfc-126">The message "Parse succeeded" is displayed when your syntax is correct.</span></span> <span data-ttu-id="3fbfc-127">При обнаружении ошибки исправьте ее.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-127">If an error is found, correct the syntax before continuing.</span></span>  
  
9. <span data-ttu-id="3fbfc-128">Щелкните вкладку **Дополнительно** , чтобы задать следующие параметры шага задания: какое действие необходимо выполнить при успешном или неуспешном выполнении шага задания, сколько раз агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен пытаться выполнить шаг задания, а также файл или таблицу, куда агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может записывать результат выполнения шага задания.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-128">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file or table where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="3fbfc-129">Только члены предопределенной роли сервера **sysadmin** могут записывать выходные данные шага задания в файл операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-129">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span> <span data-ttu-id="3fbfc-130">В таблицу выходные данные могут записывать все пользователи агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-130">All SQL Server Agent users can log output to a table.</span></span>  
  
10. <span data-ttu-id="3fbfc-131">Если члену предопределенной роли сервера **sysadmin** нужно выполнить шаг задания в контексте другого имени входа SQL, ему следует выбрать имя входа SQL из списка **Выполнять от имени** .</span><span class="sxs-lookup"><span data-stu-id="3fbfc-131">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="3fbfc-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3fbfc-132">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="3fbfc-133">Создание шага задания Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3fbfc-133">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="3fbfc-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fbfc-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3fbfc-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3fbfc-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3fbfc-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses Transact-SQL  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="3fbfc-137">Дополнительные сведения см. в разделе [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3fbfc-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="3fbfc-138">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="3fbfc-138">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="3fbfc-139">**Создание шага задания Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3fbfc-139">**To create a Transact-SQL job step**</span></span>  
  
 <span data-ttu-id="3fbfc-140">Воспользуйтесь классом `JobStep` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="3fbfc-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
