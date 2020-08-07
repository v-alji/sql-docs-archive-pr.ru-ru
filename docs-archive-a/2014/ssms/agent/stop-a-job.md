---
title: Остановка задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
ms.assetid: 4249328a-24d8-4284-9d1d-7d04ed90e3d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 78986e85dd8ee808f5fb621182d903a94bbc5eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727886"
---
# <a name="stop-a-job"></a><span data-ttu-id="eea4a-102">Остановка задания</span><span class="sxs-lookup"><span data-stu-id="eea4a-102">Stop a Job</span></span>
  <span data-ttu-id="eea4a-103">В этом разделе описывается, как прерывать [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Задание агента.</span><span class="sxs-lookup"><span data-stu-id="eea4a-103">This topic describes how to stop a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="eea4a-104">Задание — это указанная последовательность действий, выполняемая агентом SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eea4a-104">A job is a specified series of actions that SQL Server Agent performs.</span></span>  
  
-   <span data-ttu-id="eea4a-105">**Перед началом:** ,</span><span class="sxs-lookup"><span data-stu-id="eea4a-105">**Before you begin:**  ,</span></span>  
  
     [<span data-ttu-id="eea4a-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="eea4a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="eea4a-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="eea4a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eea4a-108">**Для остановки задания используется:**</span><span class="sxs-lookup"><span data-stu-id="eea4a-108">**To stop a job, using:**</span></span>  
  
     [<span data-ttu-id="eea4a-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eea4a-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="eea4a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eea4a-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="eea4a-111">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="eea4a-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eea4a-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="eea4a-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="eea4a-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="eea4a-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="eea4a-114">Если задание в данный момент выполняет этап типа **CmdExec** или **PowerShell**, выполняемый процесс (например MyProgram.exe) принудительно завершается раньше времени.</span><span class="sxs-lookup"><span data-stu-id="eea4a-114">If a job is currently executing a step of type **CmdExec** or **PowerShell**, the process that is being run (for example, MyProgram.exe) is forced to end prematurely.</span></span> <span data-ttu-id="eea4a-115">Это может привести к непредсказуемому поведению, например файлы, используемые процессом, могут остаться открытыми.</span><span class="sxs-lookup"><span data-stu-id="eea4a-115">This can cause unpredictable behavior, such as files that are being used by the process being held open.</span></span>  
  
-   <span data-ttu-id="eea4a-116">Для многосерверного задания инструкция STOP отправляется на все целевые серверы, с которыми связано задание.</span><span class="sxs-lookup"><span data-stu-id="eea4a-116">For a multiserver job, a STOP instruction for the job is posted to all target servers of the job.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eea4a-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="eea4a-117">Security</span></span>  
 <span data-ttu-id="eea4a-118">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="eea4a-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="eea4a-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eea4a-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-stop-a-job"></a><span data-ttu-id="eea4a-120">Остановка задания</span><span class="sxs-lookup"><span data-stu-id="eea4a-120">To stop a job</span></span>  
  
1.  <span data-ttu-id="eea4a-121">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="eea4a-121">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="eea4a-122">Разверните узел **Агент SQL Server**, выберите раздел **Задания**, щелкните правой кнопкой мыши задание, которое необходимо остановить, и выберите команду **Прервать задание**.</span><span class="sxs-lookup"><span data-stu-id="eea4a-122">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to stop, and then click **Stop Job**.</span></span>  
  
3.  <span data-ttu-id="eea4a-123">Если нужно остановить несколько заданий, щелкните правой кнопкой мыши компонент **Монитор активности заданий**, а затем выберите пункт **Просмотр активности заданий**.</span><span class="sxs-lookup"><span data-stu-id="eea4a-123">If you want to stop multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="eea4a-124">На мониторе активности заданий отметьте задания, которые нужно остановить, щелкните выделенные строки правой кнопкой мыши и выберите **Прервать задания**.</span><span class="sxs-lookup"><span data-stu-id="eea4a-124">In the Job Activity Monitor, select the jobs you want to stop, right-click your selection, and then click **Stop Jobs**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="eea4a-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eea4a-125">Using Transact-SQL</span></span>  
  
### <a name="to-stop-a-job"></a><span data-ttu-id="eea4a-126">Остановка задания</span><span class="sxs-lookup"><span data-stu-id="eea4a-126">To stop a job</span></span>  
  
1.  <span data-ttu-id="eea4a-127">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eea4a-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eea4a-128">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="eea4a-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eea4a-129">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="eea4a-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- stops a job named Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_stop_job  
        N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="eea4a-130">Дополнительные сведения см. в разделе [sp_stop_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eea4a-130">For more information, see [sp_stop_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="eea4a-131">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="eea4a-131">Using SQL Server Management Objects</span></span>  

### <a name="to-stop-a-job"></a><span data-ttu-id="eea4a-132">Остановка задания</span><span class="sxs-lookup"><span data-stu-id="eea4a-132">To stop a job</span></span>
  
 <span data-ttu-id="eea4a-133">Вызовите метод `Stop` класса `Job` на языке программирования по своему выбору (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="eea4a-133">Call the `Stop` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="eea4a-134">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="eea4a-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
