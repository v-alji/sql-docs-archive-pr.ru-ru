---
title: Создание категории заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
ms.assetid: e24a6d38-d231-4f64-ab89-2d1ef6f5792c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f6daeeca6253861e8a9dcbb72faa2bd55eb2761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735845"
---
# <a name="create-a-job-category"></a><span data-ttu-id="dfa23-102">Создание категории заданий</span><span class="sxs-lookup"><span data-stu-id="dfa23-102">Create a Job Category</span></span>
  <span data-ttu-id="dfa23-103">В данном разделе описывается процесс создания категории заданий в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющих объектов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dfa23-103">This topic describes how to create a job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfa23-104">Агент предоставляет встроенные категории заданий, для которых можно назначать задания, кроме того, можно создать категорию задания и назначить ей задания.</span><span class="sxs-lookup"><span data-stu-id="dfa23-104">Agent provides built-in job categories that you can assign jobs to, or you can create a job category and assign jobs to it.</span></span> <span data-ttu-id="dfa23-105">Категории заданий помогают упорядочивать их, упрощая их фильтрацию и группирование.</span><span class="sxs-lookup"><span data-stu-id="dfa23-105">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="dfa23-106">Например, все фоновые задания можно поместить в категорию «Обслуживание базы данных».</span><span class="sxs-lookup"><span data-stu-id="dfa23-106">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="dfa23-107">Можно создавать и собственные категории заданий.</span><span class="sxs-lookup"><span data-stu-id="dfa23-107">You can also create your own job categories.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dfa23-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="dfa23-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dfa23-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="dfa23-109">Limitations and Restrictions</span></span>  
 <span data-ttu-id="dfa23-110">Многосерверные категории существуют только на главном сервере.</span><span class="sxs-lookup"><span data-stu-id="dfa23-110">Multiserver categories exist only on a master server.</span></span> <span data-ttu-id="dfa23-111">На нем по умолчанию имеется только одна категория заданий: [**Без категорий (многосерверный)**].</span><span class="sxs-lookup"><span data-stu-id="dfa23-111">There is only one default job category available on a master server: [**Uncategorized (Multi-Server)**].</span></span> <span data-ttu-id="dfa23-112">Если загружается многосерверное задание, его категория на целевом сервере меняется на **Задания от главного сервера** .</span><span class="sxs-lookup"><span data-stu-id="dfa23-112">When a multiserver job is downloaded, its category is changed to **Jobs From MSX** at the target server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dfa23-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="dfa23-113">Security</span></span>  
 <span data-ttu-id="dfa23-114">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="dfa23-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="dfa23-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dfa23-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="dfa23-116">Создание категории заданий</span><span class="sxs-lookup"><span data-stu-id="dfa23-116">To create a job category</span></span>  
  
1.  <span data-ttu-id="dfa23-117">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, на котором нужно создать категорию заданий.</span><span class="sxs-lookup"><span data-stu-id="dfa23-117">In **Object Explorer**, click the plus sign to expand the server where you want to create a job category.</span></span>  
  
2.  <span data-ttu-id="dfa23-118">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dfa23-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="dfa23-119">Щелкните правой кнопкой мыши папку **Задания** и выберите пункт **Управление категориями заданий**.</span><span class="sxs-lookup"><span data-stu-id="dfa23-119">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="dfa23-120">В диалоговом окне **Управление категориями заданий**_server_name_ нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="dfa23-120">In the **Manage Job Categories**_server_name_ dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="dfa23-121">В поле **Имя** нового диалогового окна введите имя новой категории заданий.</span><span class="sxs-lookup"><span data-stu-id="dfa23-121">In the new dialog box, in the **Name** box, enter a name for the new job category.</span></span>  
  
6.  <span data-ttu-id="dfa23-122">Установите флажок **Отображать все задания** .</span><span class="sxs-lookup"><span data-stu-id="dfa23-122">Select the **Show all jobs** check box.</span></span> <span data-ttu-id="dfa23-123">Выберите одно или несколько заданий для новой категории, установив флажки рядом с соответствующими заданиями.</span><span class="sxs-lookup"><span data-stu-id="dfa23-123">Select one or more jobs for the new category by checking the boxes corresponding to the jobs.</span></span>  
  
7.  <span data-ttu-id="dfa23-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dfa23-124">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="dfa23-125">В диалоговом окне **Управление категориями заданий**_server_name_ нажмите кнопку **Обновить** , чтобы убедиться, что новая категория заданий активна.</span><span class="sxs-lookup"><span data-stu-id="dfa23-125">In the **Manage Job Categories**_server_name_ dialog box, click **Refresh** to ensure that the new job category is active.</span></span> <span data-ttu-id="dfa23-126">Если все выглядит так, как нужно, закройте это диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="dfa23-126">If everything looks as expected, close this dialog box.</span></span>  
  
 <span data-ttu-id="dfa23-127">Дополнительные сведения об этих диалоговых окнах см. в разделе [категории заданий: Управление категориями](job-categories-manage-job-categories.md) заданий и [свойствами категорий заданий и создание категории заданий](job-categories-properties-new-job-category.md).</span><span class="sxs-lookup"><span data-stu-id="dfa23-127">For more information on these dialog boxes, see [Job Categories: Manage Job Categories](job-categories-manage-job-categories.md) and [Job Categories Properties and New Job Category](job-categories-properties-new-job-category.md).</span></span>  

##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="dfa23-128">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dfa23-128">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="dfa23-129">Создание категории заданий</span><span class="sxs-lookup"><span data-stu-id="dfa23-129">To create a job category</span></span>  
  
1.  <span data-ttu-id="dfa23-130">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfa23-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dfa23-131">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="dfa23-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dfa23-132">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="dfa23-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a local job category named AdminJobs   
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_category  
        @class=N'JOB',  
        @type=N'LOCAL',  
        @name=N'AdminJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="dfa23-133">Дополнительные сведения см. в разделе [sp_add_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfa23-133">For more information, see [sp_add_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="dfa23-134">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="dfa23-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="dfa23-135">**Создание категории заданий**</span><span class="sxs-lookup"><span data-stu-id="dfa23-135">**To create a job category**</span></span>  
  
 <span data-ttu-id="dfa23-136">Вызовите класс `JobCategory` с использованием выбранного языка программирования, например Visual Basic, Visual C# или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfa23-136">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="dfa23-137">Пример кода см. в разделе [Планирование автоматических административных задач в агенте SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="dfa23-137">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
