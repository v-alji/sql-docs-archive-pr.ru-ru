---
title: Создание шага задания, использующего скрипт PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], job steps
- jobs [SQL Server Agent], PowerShell
- job steps [PowerShell]
- SQL Server Agent jobs, PowerShell steps
ms.assetid: 50afcf84-fae0-4eb5-9b0f-f2cf144c1433
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4232cdfa584fdcc2e13786ecc9bd00f0c6fe7066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659073"
---
# <a name="create-a-powershell-script-job-step"></a><span data-ttu-id="c36b6-102">Create a PowerShell Script Job Step</span><span class="sxs-lookup"><span data-stu-id="c36b6-102">Create a PowerShell Script Job Step</span></span>
  <span data-ttu-id="c36b6-103">В этом разделе описано, как создать и определить шаг задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполняющий скрипт PowerShell, в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c36b6-103">This topic describes how to create and define a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes a PowerShell script in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c36b6-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c36b6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c36b6-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c36b6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c36b6-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c36b6-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c36b6-107">**Создание шага задания скрипта PowerShell с использованием:**</span><span class="sxs-lookup"><span data-stu-id="c36b6-107">**To create a PowerShell Script job step, using:**</span></span>  
  
     [<span data-ttu-id="c36b6-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c36b6-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="c36b6-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c36b6-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="c36b6-110">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="c36b6-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c36b6-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c36b6-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c36b6-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="c36b6-112">Security</span></span>  
 <span data-ttu-id="c36b6-113">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c36b6-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="c36b6-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c36b6-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="c36b6-115">Создание шага задания скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="c36b6-115">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="c36b6-116">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c36b6-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c36b6-117">Разверните **Агент SQL Server**, создайте задание или щелкните правой кнопкой мыши существующее задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-117">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="c36b6-118">Дополнительные сведения о создании заданий см. в разделе [Создание заданий](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="c36b6-118">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="c36b6-119">В диалоговом окне **Свойства задания** выберите страницу **Шаги** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-119">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="c36b6-120">В диалоговом окне **Новый шаг задания** введите **имя шага**задания.</span><span class="sxs-lookup"><span data-stu-id="c36b6-120">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="c36b6-121">В списке **Тип** выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-121">In the **Type** list, click **PowerShell**.</span></span>  
  
6.  <span data-ttu-id="c36b6-122">В списке **Выполнять как** выберите учетную запись-посредник с учетными данными, используемыми в задании.</span><span class="sxs-lookup"><span data-stu-id="c36b6-122">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="c36b6-123">В поле **Команда** введите синтаксис скрипта PowerShell, который будет выполняться в данном шаге.</span><span class="sxs-lookup"><span data-stu-id="c36b6-123">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="c36b6-124">Или нажмите кнопку **Открыть** и выберите файл, содержащий скрипт.</span><span class="sxs-lookup"><span data-stu-id="c36b6-124">Alternately, click **Open** and select a file containing the script syntax.</span></span> <span data-ttu-id="c36b6-125">В качестве примера скрипта PowerShell см. подраздел **Использование Transact-SQL** ниже.</span><span class="sxs-lookup"><span data-stu-id="c36b6-125">For an example of a PowerShell script, see **Using Transact-SQL** below.</span></span>  
  
8.  <span data-ttu-id="c36b6-126">Выберите страницу **Дополнительно** , чтобы задать следующие параметры шага задания: какие действия предпринять в случае успешного или неуспешного выполнения шага задания, сколько раз агенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пытаться его выполнить и как часто повторять эти попытки.</span><span class="sxs-lookup"><span data-stu-id="c36b6-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="c36b6-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c36b6-127">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="c36b6-128">Создание шага задания скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="c36b6-128">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="c36b6-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c36b6-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c36b6-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c36b6-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a PowerShell job step that finds the processes that use more than 1000 MB of memory and kills them  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Kills all processes that use more than 1000 MB of memory',  
        @subsystem = N'PowerShell',  
        @command = N'Get-Process | Where-Object { $_.WS -gt 1000MB } | Stop-Process',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="c36b6-132">Дополнительные сведения см. в разделе [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c36b6-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="c36b6-133">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="c36b6-133">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="c36b6-134">**Создание шага задания скрипта PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c36b6-134">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="c36b6-135">Воспользуйтесь классом `JobStep` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="c36b6-135">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
