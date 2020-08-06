---
title: Запуск задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], starting
- SQL Server Agent jobs, starting
- starting jobs
ms.assetid: cec9f7f7-d0a7-4239-9dc5-a69c011ebaa0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d5af895df518a915dacd953331b9139471933aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737415"
---
# <a name="start-a-job"></a><span data-ttu-id="a5084-102">Запуск задания</span><span class="sxs-lookup"><span data-stu-id="a5084-102">Start a Job</span></span>
  <span data-ttu-id="a5084-103">В этом разделе описано, как начать выполнение [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задания агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5084-103">This topic describes how to start running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="a5084-104">Задание — это указанная последовательность действий, выполняемых агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5084-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a5084-105">могут выполняться на одном локальном сервере или на нескольких удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="a5084-105">Agent jobs can run on one local server or on multiple remote servers.</span></span>  
  
-   <span data-ttu-id="a5084-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a5084-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a5084-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a5084-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a5084-108">**Для запуска задания используется:**</span><span class="sxs-lookup"><span data-stu-id="a5084-108">**To start a job, using:**</span></span>  
  
     [<span data-ttu-id="a5084-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a5084-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="a5084-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5084-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="a5084-111">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5084-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a5084-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a5084-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a5084-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="a5084-113">Security</span></span>  
 <span data-ttu-id="a5084-114">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a5084-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="a5084-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a5084-115">Using SQL Server Management Studio</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="a5084-116">Запуск задания</span><span class="sxs-lookup"><span data-stu-id="a5084-116">To start a job</span></span>  
  
1.  <span data-ttu-id="a5084-117">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="a5084-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a5084-118">Разверните узел **Агент SQL Server** , затем разверните узел **Задания**.</span><span class="sxs-lookup"><span data-stu-id="a5084-118">Expand **SQL Server Agent,** and expand **Jobs**.</span></span> <span data-ttu-id="a5084-119">В зависимости от того, как нужно запускать задание, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="a5084-119">Depending on how you want the job to start, do one of the following:</span></span>  
  
    -   <span data-ttu-id="a5084-120">При работе с одиночным сервером, работе на целевом сервере или запуске задания локального сервера на главном сервере щелкните правой кнопкой мыши задание, которое нужно запустить, и выберите пункт **Запустить задание**.</span><span class="sxs-lookup"><span data-stu-id="a5084-120">If you are working on a single server, or working on a target server, or running a local server job on a master server, right-click the job you want to start, and then click **Start Job**.</span></span>  
  
    -   <span data-ttu-id="a5084-121">Если нужно запустить несколько заданий, щелкните правой кнопкой мыши компонент **Монитор активности заданий**, а затем выберите пункт **Просмотр активности заданий**.</span><span class="sxs-lookup"><span data-stu-id="a5084-121">If you want to start multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="a5084-122">В разделе "Монитор активности заданий" можно выбрать несколько заданий, щелкнуть их правой кнопкой мыши и выбрать пункт **Запустить задания**.</span><span class="sxs-lookup"><span data-stu-id="a5084-122">In the Job Activity Monitor you can select multiple jobs, right-click your selection, and click **Start Jobs**.</span></span>  
  
    -   <span data-ttu-id="a5084-123">При работе на главном сервере, чтобы все целевые серверы запускали данное задание одновременно, щелкните правой кнопкой мыши нужное задание, выберите пункт **Запустить задание**, а затем пункт **Запустить на всех целевых серверах**.</span><span class="sxs-lookup"><span data-stu-id="a5084-123">If you are working on a master server and want all targeted servers to run the job simultaneously, right-click the job you want to start, click **Start Job**, and then click **Start on all targeted servers**.</span></span>  
  
    -   <span data-ttu-id="a5084-124">При работе на главном сервере, чтобы указать целевые серверы для данного задания, щелкните правой кнопкой мыши нужное задание, выберите пункт **Запустить задание**, а затем пункт **Запустить на указанных целевых серверах**.</span><span class="sxs-lookup"><span data-stu-id="a5084-124">If you are working on a master server and want to specify target servers for the job, right-click the job you want to start, click **Start Job**, and then click **Start on specific target servers**.</span></span> <span data-ttu-id="a5084-125">В диалоговом окне **Инструкции после загрузки** установите флажок **Эти целевые серверы** и отметьте все серверы, на которых должно запускаться данное задание.</span><span class="sxs-lookup"><span data-stu-id="a5084-125">In the **Post Download Instructions** dialog box, select the **These target servers** check box, and then select each target server on which this job should run.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="a5084-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5084-126">Using Transact-SQL</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="a5084-127">Запуск задания</span><span class="sxs-lookup"><span data-stu-id="a5084-127">To start a job</span></span>  
  
1.  <span data-ttu-id="a5084-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5084-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a5084-129">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a5084-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a5084-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a5084-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- starts a job named Weekly Sales Data Backup.    
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_start_job N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="a5084-131">Дополнительные сведения см. в разделе [sp_start_job (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5084-131">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="a5084-132">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5084-132">Using SQL Server Management Objects</span></span>  

### <a name="to-start-a-job"></a><span data-ttu-id="a5084-133">Запуск задания</span><span class="sxs-lookup"><span data-stu-id="a5084-133">To start a job</span></span>
  
 <span data-ttu-id="a5084-134">Вызовите метод `Start` класса `Job` на языке программирования по своему выбору (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a5084-134">Call the `Start` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="a5084-135">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="a5084-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
