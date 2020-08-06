---
title: Назначение задания в категорию заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], assigning
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- SQL Server Agent jobs, assigning
- assigning job to category
ms.assetid: a9ea65a2-1d73-4582-a335-63adeb450cb6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 208ff6722a9c18fd4dd0d061575f0d496af27810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668606"
---
# <a name="assign-a-job-to-a-job-category"></a><span data-ttu-id="74310-102">Назначение задания в категорию заданий</span><span class="sxs-lookup"><span data-stu-id="74310-102">Assign a Job to a Job Category</span></span>
  <span data-ttu-id="74310-103">В этом разделе описывается назначение [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданий агента категориям заданий в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74310-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to job categories in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="74310-104">Категории заданий помогают упорядочивать их, упрощая их фильтрацию и группирование.</span><span class="sxs-lookup"><span data-stu-id="74310-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="74310-105">Например, все фоновые задания можно поместить в категорию «Обслуживание базы данных».</span><span class="sxs-lookup"><span data-stu-id="74310-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="74310-106">Задание может быть отнесено либо к встроенной категории, либо к одной из созданных пользовательских категорий заданий.</span><span class="sxs-lookup"><span data-stu-id="74310-106">You can assign jobs to built-in job categories, or you can create a user-defined job category and then assign jobs to that.</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="74310-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="74310-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="74310-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="74310-108">Security</span></span>  
 <span data-ttu-id="74310-109">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="74310-109">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="74310-110">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74310-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="74310-111">Назначение задания в категорию заданий</span><span class="sxs-lookup"><span data-stu-id="74310-111">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="74310-112">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, на котором заданию нужно назначить категорию.</span><span class="sxs-lookup"><span data-stu-id="74310-112">In **Object Explorer**, click the plus sign to expand the server where you want to assign a job to a job category.</span></span>  
  
2.  <span data-ttu-id="74310-113">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="74310-113">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="74310-114">Чтобы развернуть папку **Задания** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="74310-114">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="74310-115">Щелкните правой кнопкой мыши задание, которое необходимо изменить, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="74310-115">Right-click the job you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="74310-116">В диалоговом окне **Свойства задания —**_Job_name_ в списке **Категория** выберите категорию заданий, которую нужно назначить заданию.</span><span class="sxs-lookup"><span data-stu-id="74310-116">In the **Job Properties -**_job_name_ dialog box, in the **Category** list, select the job category you want to assign to the job.</span></span>  
  
6.  <span data-ttu-id="74310-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74310-117">Click **OK**.</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="74310-118">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74310-118">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="74310-119">Назначение задания в категорию заданий</span><span class="sxs-lookup"><span data-stu-id="74310-119">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="74310-120">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74310-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="74310-121">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="74310-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="74310-122">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="74310-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="74310-123">Дополнительные сведения см. в разделе [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="74310-123">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="74310-124">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="74310-124">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="74310-125">**Назначение задания в категорию заданий**</span><span class="sxs-lookup"><span data-stu-id="74310-125">**To assign a job to a job category**</span></span>  
  
 <span data-ttu-id="74310-126">Воспользуйтесь классом `JobCategory` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="74310-126">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
  
  
