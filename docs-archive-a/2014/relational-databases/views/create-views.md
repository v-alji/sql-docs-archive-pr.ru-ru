---
title: Создание представлений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], creating
ms.assetid: 0b7bd2a1-544c-42ba-8e7b-4822f34d7b64
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8280f6d65d7252cad423abef849207111492c044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654980"
---
# <a name="create-views"></a><span data-ttu-id="de889-102">Создание представлений</span><span class="sxs-lookup"><span data-stu-id="de889-102">Create Views</span></span>
  <span data-ttu-id="de889-103">Представления можно создать в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de889-103">You can create views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="de889-104">Представление можно использовать в следующих целях.</span><span class="sxs-lookup"><span data-stu-id="de889-104">A view can be used for the following purposes:</span></span>  
  
-   <span data-ttu-id="de889-105">Для направления, упрощения и настройки восприятия информации в базе данных каждым пользователем.</span><span class="sxs-lookup"><span data-stu-id="de889-105">To focus, simplify, and customize the perception each user has of the database.</span></span>  
  
-   <span data-ttu-id="de889-106">В качестве механизма безопасности, позволяющего пользователям обращаться к данным через представления, но не предоставляя им разрешений на непосредственный доступ к базовым таблицам.</span><span class="sxs-lookup"><span data-stu-id="de889-106">As a security mechanism by allowing users to access data through the view, without granting the users permissions to directly access the underlying base tables.</span></span>  
  
-   <span data-ttu-id="de889-107">Для предоставления интерфейса обратной совместимости, моделирующего таблицу, схема которой изменилась.</span><span class="sxs-lookup"><span data-stu-id="de889-107">To provide a backward compatible interface to emulate a table whose schema has changed.</span></span>  
  
 <span data-ttu-id="de889-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="de889-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="de889-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="de889-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="de889-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="de889-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="de889-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="de889-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="de889-112">**Создание представления с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="de889-112">**To create a view, using:**</span></span>  
  
     [<span data-ttu-id="de889-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de889-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="de889-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de889-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="de889-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="de889-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="de889-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="de889-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="de889-117">Представление может быть создано только в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="de889-117">A view can be created only in the current database.</span></span>  
  
 <span data-ttu-id="de889-118">Представление может включать не более 1 024 столбцов.</span><span class="sxs-lookup"><span data-stu-id="de889-118">A view can have a maximum of 1,024 columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="de889-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="de889-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="de889-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="de889-120">Permissions</span></span>  
 <span data-ttu-id="de889-121">Для выполнения этой инструкции требуется разрешение CREATE VIEW в отношении базы данных и разрешение ALTER в отношении схемы, в которой создается представление.</span><span class="sxs-lookup"><span data-stu-id="de889-121">Requires CREATE VIEW permission in the database and ALTER permission on the schema in which the view is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="de889-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de889-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-view-by-using-the-query-and-view-designer"></a><span data-ttu-id="de889-123">Создание представления с использованием конструктора запросов и представлений</span><span class="sxs-lookup"><span data-stu-id="de889-123">To create a view by using the Query and View Designer</span></span>  
  
1.  <span data-ttu-id="de889-124">В **обозревателе объектов**разверните базу данных, в которой необходимо создать новое представление.</span><span class="sxs-lookup"><span data-stu-id="de889-124">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="de889-125">Щелкните правой кнопкой папку **Представления** и выберите **Создать представление...**</span><span class="sxs-lookup"><span data-stu-id="de889-125">Right-click the **Views** folder, then click **New View...**.</span></span>  
  
3.  <span data-ttu-id="de889-126">В диалоговом окне **Добавить таблицу** выберите один или несколько элементов, которые необходимо включить в новое представление, на одной из следующих вкладок: «Таблицы», «Представления», «Функции» и «Синонимы».</span><span class="sxs-lookup"><span data-stu-id="de889-126">In the **Add Table** dialog box, select the element or elements that you want to include in your new view from one of the following tabs: Tables, Views, Functions, and Synonyms.</span></span>  
  
4.  <span data-ttu-id="de889-127">Щелкните **Добавить**, а затем выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="de889-127">Click **Add**, then click **Close**.</span></span>  
  
5.  <span data-ttu-id="de889-128">На **Панели диаграмм**выберите столбцы или другие элементы для включения в новое представление.</span><span class="sxs-lookup"><span data-stu-id="de889-128">In the **Diagram Pane**, select the columns or other elements to include in the new view.</span></span>  
  
6.  <span data-ttu-id="de889-129">На **Панели критериев**выберите дополнительные условия сортировки или фильтрации для столбцов.</span><span class="sxs-lookup"><span data-stu-id="de889-129">In the **Criteria Pane**, select additional sort or filter criteria for the columns.</span></span>  
  
7.  <span data-ttu-id="de889-130">В меню **Файл** выберите пункт **Сохранить**_view name_.</span><span class="sxs-lookup"><span data-stu-id="de889-130">On the **File** menu, click **Save**_view name_.</span></span>  
  
8.  <span data-ttu-id="de889-131">В диалоговом окне **Выбор имени** введите имя нового представления и щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de889-131">In the **Choose Name** dialog box, enter a name for the new view and click **OK**.</span></span>  
  
     <span data-ttu-id="de889-132">Дополнительные сведения о конструкторе запросов и представлений см. в статье [Инструменты конструктора запросов и представлений (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="de889-132">For more information about the query and view designer, see [Query and View Designer Tools &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="de889-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de889-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-view"></a><span data-ttu-id="de889-134">Создание представления</span><span class="sxs-lookup"><span data-stu-id="de889-134">To create a view</span></span>  
  
1.  <span data-ttu-id="de889-135">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de889-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="de889-136">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="de889-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="de889-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="de889-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
    GO  
    -- Query the view  
    SELECT FirstName, LastName, HireDate  
    FROM HumanResources.EmployeeHireDate  
    ORDER BY LastName;  
  
    ```  
  
 <span data-ttu-id="de889-138">Дополнительные сведения см. в статье [CREATE VIEW (Transact-SQL)](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="de889-138">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
  
