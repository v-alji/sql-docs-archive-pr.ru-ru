---
title: Просмотр активности заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- viewing job activity
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- displaying job activity
ms.assetid: 5c284e5e-7775-435d-ac49-f3f12a27ddc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 56b159952c83ed243c4c5d8012c76e5a2a248519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750443"
---
# <a name="view-job-activity"></a><span data-ttu-id="3cdd5-102">Просмотр активности заданий</span><span class="sxs-lookup"><span data-stu-id="3cdd5-102">View Job Activity</span></span>
  <span data-ttu-id="3cdd5-103">В этом разделе описано, как с помощью хранимых процедур просматривать состояние среды выполнения заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cdd5-103">This topic describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3cdd5-104">При запуске службы агента [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создается новый сеанс, а в таблицу **sysjobactivity** базы данных **msdb** заносятся все существующие определенные задания.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-104">When the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service starts, a new session is created and the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="3cdd5-105">В таблице регистрируется текущая активность задания и его состояние.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-105">This table records current job activity and status.</span></span> <span data-ttu-id="3cdd5-106">Монитор активности заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] позволяет просматривать текущее состояние заданий.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-106">You can use the Job Activity Monitor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to view the current state of jobs.</span></span> <span data-ttu-id="3cdd5-107">Если служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] непредвиденно останавливается, в таблице **sysjobactivity** можно будет увидеть, какие задания выполнялись в момент прекращения работы службы.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service unexpectedly terminates, you can refer to the **sysjobactivity** table to see which jobs were being executed when the service terminated.</span></span>  
  
 <span data-ttu-id="3cdd5-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3cdd5-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3cdd5-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3cdd5-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3cdd5-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3cdd5-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3cdd5-111">**Для просмотра активности заданий используется:**</span><span class="sxs-lookup"><span data-stu-id="3cdd5-111">**To view job activity, using:**</span></span>  
  
     [<span data-ttu-id="3cdd5-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cdd5-112">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="3cdd5-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cdd5-113">Transact-SQL</span></span>](#TSQL)  
  
## <a name="before-you-begin"></a><span data-ttu-id="3cdd5-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3cdd5-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3cdd5-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="3cdd5-115">Security</span></span>  
 <span data-ttu-id="3cdd5-116">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3cdd5-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="3cdd5-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cdd5-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="3cdd5-118">Просмотр активности заданий</span><span class="sxs-lookup"><span data-stu-id="3cdd5-118">To view job activity</span></span>  
  
1.  <span data-ttu-id="3cdd5-119">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3cdd5-120">Разверните узел **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-120">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3cdd5-121">Щелкните правой кнопкой мыши **Монитор активности заданий** и выберите команду **Просмотреть активность заданий**.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-121">Right-click **Job Activity Monitor** and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="3cdd5-122">В **мониторе активности заданий**можно просмотреть подробные сведения о каждом из заданий, определенных для данного сервера.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-122">In the **Job Activity Monitor**, you can view details about each job that is defined for this server.</span></span>  
  
5.  <span data-ttu-id="3cdd5-123">По щелчку правой кнопки мыши можно запустить задание, остановить его, включить или отключить, обновить состояние, отображаемое в «Мониторе активности задания», удалить задание или просмотреть его историю или свойства.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-123">Right-click a job to start it, stop it, enable or disable it, refresh its status as displayed in the Job Activity Monitor, delete it, or view its history or properties.</span></span>  <span data-ttu-id="3cdd5-124">Чтобы запустить, остановить, включить или отключить либо обновить несколько заданий, выберите несколько строк в «Мониторе активности заданий» и щелкните выделенные элементы правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-124">To start, stop, enable or disable, or refresh multiple jobs, select multiple rows in the Job Activity Monitor, and right-click your selection.</span></span>  
  
6.  <span data-ttu-id="3cdd5-125">Для обновления «Монитора активности заданий» выберите пункт **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-125">To update the Job Activity Monitor, click **Refresh**.</span></span> <span data-ttu-id="3cdd5-126">Для уменьшения количества отображаемых строк щелкните **Фильтр** и введите параметры фильтрации.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-126">To view fewer rows, click **Filter** and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="3cdd5-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cdd5-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="3cdd5-128">Просмотр активности заданий</span><span class="sxs-lookup"><span data-stu-id="3cdd5-128">To view job activity</span></span>  
  
1.  <span data-ttu-id="3cdd5-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cdd5-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3cdd5-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3cdd5-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- lists activity for all jobs that the current user has permission to view.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobactivity ;  
    GO  
    ```  
  
 <span data-ttu-id="3cdd5-132">Дополнительные сведения см. в разделе [sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cdd5-132">For more information, see [sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span></span>  
  
  
