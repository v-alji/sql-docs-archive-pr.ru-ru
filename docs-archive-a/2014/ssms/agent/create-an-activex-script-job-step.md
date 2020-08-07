---
title: Создание шага задания со скриптом ActiveX | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ActiveX scripting jobs [SQL Server]
- job steps [Analysis Services]
ms.assetid: e6c46c6b-2d61-4571-bc8e-a831cd6e6302
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6604ba75af7acdd5bd2521433e8310c74150ce8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727902"
---
# <a name="create-an-activex-script-job-step"></a><span data-ttu-id="cf8ef-102">Create an ActiveX Script Job Step</span><span class="sxs-lookup"><span data-stu-id="cf8ef-102">Create an ActiveX Script Job Step</span></span>
  <span data-ttu-id="cf8ef-103">В этом разделе описывается создание и определение [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] шага задания агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , который выполняет Скрипт ActiveX с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that executes an ActiveX script by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="cf8ef-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="cf8ef-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cf8ef-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="cf8ef-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cf8ef-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="cf8ef-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cf8ef-107">**Для создания шага задания Transact-SQL используется:**</span><span class="sxs-lookup"><span data-stu-id="cf8ef-107">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="cf8ef-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf8ef-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="cf8ef-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cf8ef-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="cf8ef-110">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="cf8ef-110">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="cf8ef-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="cf8ef-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cf8ef-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="cf8ef-112">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cf8ef-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="cf8ef-113">Security</span></span>  
 <span data-ttu-id="cf8ef-114">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="cf8ef-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="cf8ef-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf8ef-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="cf8ef-116">Создание шага задания скрипта ActiveX</span><span class="sxs-lookup"><span data-stu-id="cf8ef-116">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="cf8ef-117">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cf8ef-118">Разверните **Агент SQL Server**, создайте задание или щелкните правой кнопкой мыши существующее задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="cf8ef-119">Дополнительные сведения о создании заданий см. в разделе [Создание заданий](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="cf8ef-119">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="cf8ef-120">В диалоговом окне **Свойства задания** выберите страницу **Шаги** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="cf8ef-121">В диалоговом окне **Новый шаг задания** введите **имя шага**задания.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="cf8ef-122">В списке **Тип** выберите **Скрипт ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-122">In the **Type** list, click **ActiveX Script**.</span></span>  
  
6.  <span data-ttu-id="cf8ef-123">В списке **Выполнять как** выберите учетную запись-посредник с учетными данными, используемыми в задании.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="cf8ef-124">Выберите **Язык** , на котором написан скрипт.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-124">Select the **Language** in which the script was written.</span></span> <span data-ttu-id="cf8ef-125">Или выберите **Другой** и введите имя языка скриптов [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX, на котором будет написан скрипт.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-125">Alternatively, click **Other** and then enter the name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX scripting language in which the script will be written.</span></span>  
  
8.  <span data-ttu-id="cf8ef-126">В поле **Команда** введите скрипт, который будет выполняться этим шагом задания.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-126">In the **Command** box, enter the script syntax that will be executed for the job step.</span></span> <span data-ttu-id="cf8ef-127">Или нажмите кнопку **Открыть** и выберите файл, содержащий скрипт.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-127">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
9. <span data-ttu-id="cf8ef-128">Выберите страницу **Дополнительно** , чтобы задать следующие параметры шага задания: какие действия предпринять в случае успешного или неуспешного выполнения шага задания, сколько раз агенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пытаться его выполнить и как часто повторять эти попытки.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-128">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="cf8ef-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cf8ef-129">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="cf8ef-130">Создание шага задания скрипта ActiveX</span><span class="sxs-lookup"><span data-stu-id="cf8ef-130">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="cf8ef-131">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf8ef-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cf8ef-132">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cf8ef-133">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="cf8ef-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- create an ActiveX Script job step written in VBScript that creates a restore point  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a restore point',  
        @subsystem = N'ACTIVESCRIPTING',  
        @command = N'Const RESTORE_POINT = 20  
  
    strComputer = "."  
    Set objWMIService = GetObject("winmgmts:" _  
        & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\default")  
  
    Set objItem = objWMIService.Get("SystemRestore")  
    errResults = objItem.Restore(RESTORE_POINT)',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="cf8ef-134">Дополнительные сведения см. в разделе [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cf8ef-134">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="cf8ef-135">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="cf8ef-135">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="cf8ef-136">**Создание шага задания скрипта ActiveX**</span><span class="sxs-lookup"><span data-stu-id="cf8ef-136">**To create an ActiveX Script job step**</span></span>  
  
 <span data-ttu-id="cf8ef-137">Воспользуйтесь классом `JobStep` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="cf8ef-137">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
