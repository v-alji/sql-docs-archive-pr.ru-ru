---
title: Очистка журнала заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- clearing job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 34b9398a-c409-4040-8ea1-0deceb18f961
author: stevestein
ms.author: sstein
ms.openlocfilehash: 813c2c7c86a769eea09a093f2de999460d78ef54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668599"
---
# <a name="clear-the-job-history-log"></a><span data-ttu-id="d607f-102">Clear the Job History Log</span><span class="sxs-lookup"><span data-stu-id="d607f-102">Clear the Job History Log</span></span>
  <span data-ttu-id="d607f-103">В этом разделе описано, как удалить содержимое [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] журнала заданий агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d607f-103">This topic describes how to delete the contents of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="d607f-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d607f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d607f-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d607f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d607f-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d607f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d607f-107">**Для очистки журнала заданий используется:**</span><span class="sxs-lookup"><span data-stu-id="d607f-107">**To clear the job history log, using:**</span></span>  
  
     [<span data-ttu-id="d607f-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d607f-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="d607f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d607f-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="d607f-110">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="d607f-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d607f-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d607f-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d607f-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="d607f-112">Security</span></span>  
 <span data-ttu-id="d607f-113">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d607f-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d607f-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d607f-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="d607f-115">Очистка журнала заданий</span><span class="sxs-lookup"><span data-stu-id="d607f-115">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="d607f-116">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d607f-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d607f-117">Раскройте узел **Агент SQL Server**, а затем узел **Задания**.</span><span class="sxs-lookup"><span data-stu-id="d607f-117">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="d607f-118">Щелкните правой кнопкой мыши задание и выберите **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="d607f-118">Right-click a job and click **View history**.</span></span>  
  
4.  <span data-ttu-id="d607f-119">В **Программе просмотра файла журнала**выберите задание, журнал которого нужно очистить, и выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d607f-119">In the **Log File Viewer**, select the job for which you want to clear history, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="d607f-120">В окне **Удалить журнал**нажмите кнопку **Удалить** , затем **Удалить весь журнал** .</span><span class="sxs-lookup"><span data-stu-id="d607f-120">Click **Delete**, and then click **Delete all history** in the **Delete History** dialog.</span></span> <span data-ttu-id="d607f-121">Можно удалить как весь журнал заданий, так и только записи, сделанные до указанной даты.</span><span class="sxs-lookup"><span data-stu-id="d607f-121">You can delete all job history or only history that is older than a specified date.</span></span> <span data-ttu-id="d607f-122">Чтобы удалить весь журнал заданий, нажмите кнопку **Удалить весь журнал**.</span><span class="sxs-lookup"><span data-stu-id="d607f-122">If you want to remove all job history, click **Delete all history**.</span></span> <span data-ttu-id="d607f-123">Чтобы удалить из журнала заданий записи определенной давности, нажмите кнопку **Удалить журнал до**и укажите дату.</span><span class="sxs-lookup"><span data-stu-id="d607f-123">If you only want to remove older job history logs, click **Delete history before**, and then specify a date.</span></span>  
  
    -   <span data-ttu-id="d607f-124">Чтобы очистить журнал многосерверного задания, нажмите кнопку **Состояние задания** .</span><span class="sxs-lookup"><span data-stu-id="d607f-124">Click **Job status** if you want to clear the history log of a multiserver job.</span></span> <span data-ttu-id="d607f-125">Нажмите кнопку **Задание**, выберите имя задания, а затем выберите пункт **Просмотреть удаленный журнал заданий**.</span><span class="sxs-lookup"><span data-stu-id="d607f-125">Click **Job**, click a job name, and then click **View Remote Job History**.</span></span>  
  
5.  <span data-ttu-id="d607f-126">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d607f-126">Click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="d607f-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d607f-127">Using Transact-SQL</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="d607f-128">Очистка журнала заданий</span><span class="sxs-lookup"><span data-stu-id="d607f-128">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="d607f-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d607f-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d607f-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d607f-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d607f-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d607f-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- example removes the history for a job named NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_purge_jobhistory  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d607f-132">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="d607f-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="d607f-133">**Очистка журнала заданий**</span><span class="sxs-lookup"><span data-stu-id="d607f-133">**To clear the job history log**</span></span>  
  
 <span data-ttu-id="d607f-134">Вызовите метод `PurgeJobHistory` класса `JobServer`, используя выбранный язык программирования, например Visual Basic, Visual C# или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d607f-134">Use the `PurgeJobHistory` method of the `JobServer` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="d607f-135">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="d607f-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
