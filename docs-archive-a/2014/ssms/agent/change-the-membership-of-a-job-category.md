---
title: Изменение состава категории заданий | Документация Майкрософт
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
- members [SQL Server], job categories
ms.assetid: 6a18f7f0-eb50-485f-a9c7-df31ae0f994e
author: stevestein
ms.author: sstein
ms.openlocfilehash: d9ed0db394f63594937ad923734b07fed8050955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668603"
---
# <a name="change-the-membership-of-a-job-category"></a><span data-ttu-id="3a0c3-102">Change the Membership of a Job Category</span><span class="sxs-lookup"><span data-stu-id="3a0c3-102">Change the Membership of a Job Category</span></span>
  <span data-ttu-id="3a0c3-103">В этом разделе описывается изменение членства категории заданий в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или управляющих объектов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-103">This topic describes how to change the membership of the job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="3a0c3-104">Категории заданий помогают упорядочивать их, упрощая их фильтрацию и группирование.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="3a0c3-105">Вы можете создавать собственные категории заданий.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-105">You can create your own job categories.</span></span> <span data-ttu-id="3a0c3-106">Также можно изменять состав категорий заданий агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-106">You can also change Microsoft SQL Server Agent jobs membership in job categories.</span></span>  
  
 <span data-ttu-id="3a0c3-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3a0c3-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3a0c3-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3a0c3-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3a0c3-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3a0c3-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3a0c3-110">**Для изменения состава категории заданий используется:**</span><span class="sxs-lookup"><span data-stu-id="3a0c3-110">**To change the membership of a job category, using:**</span></span>  
  
     [<span data-ttu-id="3a0c3-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a0c3-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="3a0c3-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a0c3-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="3a0c3-113">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a0c3-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3a0c3-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3a0c3-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3a0c3-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="3a0c3-115">Security</span></span>  
 <span data-ttu-id="3a0c3-116">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3a0c3-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="3a0c3-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a0c3-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="3a0c3-118">Изменение состава категории заданий</span><span class="sxs-lookup"><span data-stu-id="3a0c3-118">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="3a0c3-119">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, на котором нужно изменить категорию заданий.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-119">In **Object Explorer**, click the plus sign to expand the server where you want to edit a job category.</span></span>  
  
2.  <span data-ttu-id="3a0c3-120">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3a0c3-121">Щелкните правой кнопкой мыши папку **Задания** и выберите пункт **Управление категориями заданий**.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-121">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="3a0c3-122">В диалоговом окне **Управление категориями заданий**_имя_сервера_ выберите категорию заданий, которую нужно изменить, и нажмите кнопку **Просмотреть задания**.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-122">In the **Manage Job Categories**_server_name_ dialog box, select the job category that you want to edit, and then click **View Jobs**.</span></span>  
  
5.  <span data-ttu-id="3a0c3-123">Установите флажок **Отображать все задания** .</span><span class="sxs-lookup"><span data-stu-id="3a0c3-123">Select the **Show all jobs** check box.</span></span>  
  
6.  <span data-ttu-id="3a0c3-124">Чтобы добавить задание в категорию, в основной сетке установите флажок в столбце **Выбор** , соответствующий заданию.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-124">To add a job to the category, in the main grid, select the check box in the **Select** column corresponding to the job.</span></span> <span data-ttu-id="3a0c3-125">Чтобы удалить задание из категории, снимите флажок.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-125">To remove a job from the category, clear the box.</span></span> <span data-ttu-id="3a0c3-126">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-126">When finished, click **OK**.</span></span>  
  
7.  <span data-ttu-id="3a0c3-127">Закройте диалоговое окно **Управление категориями заданий**_имя_сервера_ .</span><span class="sxs-lookup"><span data-stu-id="3a0c3-127">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="3a0c3-128">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a0c3-128">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="3a0c3-129">Изменение состава категории заданий</span><span class="sxs-lookup"><span data-stu-id="3a0c3-129">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="3a0c3-130">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a0c3-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a0c3-131">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a0c3-132">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3a0c3-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="3a0c3-133">Дополнительные сведения см. в разделе [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a0c3-133">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="3a0c3-134">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a0c3-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="3a0c3-135">**Изменение состава категории заданий**</span><span class="sxs-lookup"><span data-stu-id="3a0c3-135">**To change the membership of a job category**</span></span>  
  
 <span data-ttu-id="3a0c3-136">Воспользуйтесь классом `JobCategory` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="3a0c3-136">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
