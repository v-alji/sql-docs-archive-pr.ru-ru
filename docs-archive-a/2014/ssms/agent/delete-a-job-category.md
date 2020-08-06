---
title: Удаление категории заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- deleting job category
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- removing job category
ms.assetid: 47a7640b-20b3-4639-ab37-b6fc73575e6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: e96dd0461f3dace138b7822cdbaaa2fa242e2cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729009"
---
# <a name="delete-a-job-category"></a><span data-ttu-id="6bd6c-102">Удаление категории заданий</span><span class="sxs-lookup"><span data-stu-id="6bd6c-102">Delete a Job Category</span></span>
  <span data-ttu-id="6bd6c-103">В этом разделе описывается удаление [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] категории заданий агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-103">This topic describes how to delete a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="6bd6c-104">Категории заданий помогают упорядочивать их, упрощая их фильтрацию и группирование.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="6bd6c-105">Например, все фоновые задания можно поместить в категорию «Обслуживание базы данных».</span><span class="sxs-lookup"><span data-stu-id="6bd6c-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span>  

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6bd6c-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6bd6c-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6bd6c-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6bd6c-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6bd6c-108">При удалении пользовательской категории заданий агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предлагает переназначить другим категориям задания, которые ей назначены.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-108">When you delete a user-defined job category, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prompts you to reassign the jobs that are assigned to it to another job category.</span></span> <span data-ttu-id="6bd6c-109">Могут быть удалены только пользовательские категории заданий.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-109">You can only delete user-defined job categories.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6bd6c-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="6bd6c-110">Security</span></span>  
 <span data-ttu-id="6bd6c-111">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="6bd6c-111">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="6bd6c-112">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6bd6c-112">Using SQL Server Management Studio</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="6bd6c-113">Удаление категории заданий</span><span class="sxs-lookup"><span data-stu-id="6bd6c-113">To delete a job category</span></span>  
  
1.  <span data-ttu-id="6bd6c-114">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, на котором нужно удалить категорию заданий.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-114">In **Object Explorer**, click the plus sign to expand the server where you want to delete a job category.</span></span>  
  
2.  <span data-ttu-id="6bd6c-115">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-115">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="6bd6c-116">Щелкните правой кнопкой мыши папку **Задания** и выберите пункт **Управление категориями заданий**.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-116">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="6bd6c-117">В диалоговом окне **Управление категориями заданий**_имя_сервера_ выберите нужную категорию.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-117">In the **Manage Job Categories**_server_name_ dialog box, select the job category to delete.</span></span>  
  
5.  <span data-ttu-id="6bd6c-118">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-118">Click **Delete**.</span></span>  
  
6.  <span data-ttu-id="6bd6c-119">В диалоговом окне **Управление категориями заданий** щелкните **Да**.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-119">In the **Job Categories** dialog box, click **Yes**.</span></span>  
  
7.  <span data-ttu-id="6bd6c-120">Закройте диалоговое окно **Управление категориями заданий**_имя_сервера_ .</span><span class="sxs-lookup"><span data-stu-id="6bd6c-120">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="6bd6c-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6bd6c-121">Using Transact-SQL</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="6bd6c-122">Удаление категории заданий</span><span class="sxs-lookup"><span data-stu-id="6bd6c-122">To delete a job category</span></span>  
  
1.  <span data-ttu-id="6bd6c-123">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bd6c-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6bd6c-124">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6bd6c-125">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- deletes the job category named AdminJobs.  
    USE msdb ;  
    GO   
    EXEC dbo.sp_delete_category  
        @name = N'AdminJobs',  
        @class = N'JOB' ;  
    GO  
    ```  
  
 <span data-ttu-id="6bd6c-126">Дополнительные сведения см. в разделе [sp_delete_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6bd6c-126">For more information, see [sp_delete_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span></span>  

  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="6bd6c-127">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="6bd6c-127">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-a-job-category"></a><span data-ttu-id="6bd6c-128">Удаление категории заданий</span><span class="sxs-lookup"><span data-stu-id="6bd6c-128">To delete a job category</span></span>
  
 <span data-ttu-id="6bd6c-129">Вызовите класс `JobCategory` с использованием выбранного языка программирования, например Visual Basic, Visual C# или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6bd6c-129">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
