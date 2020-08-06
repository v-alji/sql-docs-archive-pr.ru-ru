---
title: Просмотр журнала заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- viewing job history
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
- displaying job history
ms.assetid: 3bbd1556-abdb-48a3-b249-546eace76343
author: stevestein
ms.author: sstein
ms.openlocfilehash: e84fafdaeddb5748a8129cd5d71d667db7e5fa37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734893"
---
# <a name="view-the-job-history"></a><span data-ttu-id="652c7-102">View the Job History</span><span class="sxs-lookup"><span data-stu-id="652c7-102">View the Job History</span></span>
  <span data-ttu-id="652c7-103">В этом разделе описано, как просмотреть [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Журнал заданий агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="652c7-103">This topic describes how to view the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="652c7-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="652c7-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="652c7-105">Безопасность</span><span class="sxs-lookup"><span data-stu-id="652c7-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="652c7-106">**Для просмотра журнала заданий используется:**</span><span class="sxs-lookup"><span data-stu-id="652c7-106">**To view the job history log, using:**</span></span>  
  
     [<span data-ttu-id="652c7-107">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="652c7-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="652c7-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="652c7-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="652c7-109">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="652c7-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="652c7-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="652c7-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="652c7-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="652c7-111">Security</span></span>  
 <span data-ttu-id="652c7-112">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="652c7-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="652c7-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="652c7-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="652c7-114">Просмотр журнала заданий</span><span class="sxs-lookup"><span data-stu-id="652c7-114">To view the job history log</span></span>  
  
1.  <span data-ttu-id="652c7-115">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="652c7-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="652c7-116">Раскройте узел **Агент SQL Server**, а затем узел **Задания**.</span><span class="sxs-lookup"><span data-stu-id="652c7-116">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="652c7-117">Щелкните задание правой кнопкой мыши и выберите **Просмотр журнала**.</span><span class="sxs-lookup"><span data-stu-id="652c7-117">Right-click a job, and then click **View History**.</span></span>  
  
4.  <span data-ttu-id="652c7-118">В обозревателе файла журнала просмотрите журнал заданий.</span><span class="sxs-lookup"><span data-stu-id="652c7-118">In the Log File Viewer, view the job history.</span></span>  
  
5.  <span data-ttu-id="652c7-119">Для обновления журнала заданий нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="652c7-119">To update the job history, click **Refresh**.</span></span> <span data-ttu-id="652c7-120">Для ограничения числа строк нажмите кнопку **Фильтр** и введите параметры фильтрации.</span><span class="sxs-lookup"><span data-stu-id="652c7-120">To view fewer rows, click the **Filter** button and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="652c7-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="652c7-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="652c7-122">Просмотр журнала заданий</span><span class="sxs-lookup"><span data-stu-id="652c7-122">To view the job history log</span></span>  
  
1.  <span data-ttu-id="652c7-123">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="652c7-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="652c7-124">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="652c7-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="652c7-125">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="652c7-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all job information for the NightlyBackups job.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobhistory   
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="652c7-126">Дополнительные сведения см. в разделе [sp_help_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="652c7-126">For more information, see [sp_help_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="652c7-127">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="652c7-127">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="652c7-128">**Просмотр журнала заданий**</span><span class="sxs-lookup"><span data-stu-id="652c7-128">**To view the job history log**</span></span>  
  
 <span data-ttu-id="652c7-129">Вызовите метод `EnumHistory` класса `Job` на языке программирования по своему выбору (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="652c7-129">Call the `EnumHistory` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="652c7-130">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="652c7-130">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
