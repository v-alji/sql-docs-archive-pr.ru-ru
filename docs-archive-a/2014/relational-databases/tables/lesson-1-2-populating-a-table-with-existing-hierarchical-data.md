---
title: Заполнение таблицы существующими иерархическими данными | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: fd943d84-dbe6-4a05-912b-c88164998d80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 966548b11ad4697abc06de5c5c239a511f80b7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729345"
---
# <a name="populating-a-table-with-existing-hierarchical-data"></a><span data-ttu-id="844d6-102">Заполнение таблицы существующими иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="844d6-102">Populating a Table with Existing Hierarchical Data</span></span>
  <span data-ttu-id="844d6-103"> В этой задаче таблица создается и заполняется данными из таблицы **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="844d6-103">This task creates a new table and populates it with the data in the **EmployeeDemo** table.</span></span> <span data-ttu-id="844d6-104">Эта задача включает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="844d6-104">This task has the following steps:</span></span>  
  
-   <span data-ttu-id="844d6-105">Создание новой таблицы, содержащей столбец типа данных `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="844d6-105">Create a new table that contains a `hierarchyid` column.</span></span> <span data-ttu-id="844d6-106">Этот столбец может заменить существующие столбцы **EmployeeID** и **ManagerID** .</span><span class="sxs-lookup"><span data-stu-id="844d6-106">This column could replace the existing **EmployeeID** and **ManagerID** columns.</span></span> <span data-ttu-id="844d6-107">Однако эти столбцы нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="844d6-107">However, you will retain those columns.</span></span> <span data-ttu-id="844d6-108">Это нужно для того, чтобы существующие приложения могли ссылаться на эти столбцы, а также для помощи при распознавании данных после передачи.</span><span class="sxs-lookup"><span data-stu-id="844d6-108">This is because existing applications might refer to those columns, and also to help you understand the data after the transfer.</span></span> <span data-ttu-id="844d6-109">Определение таблицы задает столбец **OrgNode** как первичный ключ, следовательно, этот столбец должен содержать уникальные значения.</span><span class="sxs-lookup"><span data-stu-id="844d6-109">The table definition specifies that **OrgNode** is the primary key, which requires the column to contain unique values.</span></span> <span data-ttu-id="844d6-110">В кластеризованном индексе на основе столбца **OrgNode** будут храниться данные в последовательности ключа **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="844d6-110">The clustered index on the **OrgNode** column will store the date in **OrgNode** sequence.</span></span>  
  
-   <span data-ttu-id="844d6-111">Создание временной таблицы, которая будет использована для слежения за тем, сколько сотрудников напрямую подчиняются каждому менеджеру.</span><span class="sxs-lookup"><span data-stu-id="844d6-111">Create a temporary table that is used to track how many employees report directly to each manager.</span></span>  
  
-   <span data-ttu-id="844d6-112">Заполнение новой таблицы данными из таблицы **EmployeeDemo** .</span><span class="sxs-lookup"><span data-stu-id="844d6-112">Populate the new table by using data from the **EmployeeDemo** table.</span></span>  
  
### <a name="to-create-a-new-table-named-neworg"></a><span data-ttu-id="844d6-113">Создание новой таблицы с именем NewOrg</span><span class="sxs-lookup"><span data-stu-id="844d6-113">To create a new table named NewOrg</span></span>  
  
-   <span data-ttu-id="844d6-114">В окне редактора запросов запустите приведенный ниже код, чтобы создать таблицу с именем **HumanResources.NewOrg**.</span><span class="sxs-lookup"><span data-stu-id="844d6-114">In a Query Editor window, run the following code to create a new table named **HumanResources.NewOrg**:</span></span>  
  
    ```  
    CREATE TABLE NewOrg  
    (  
      OrgNode hierarchyid,  
      EmployeeID int,  
      LoginID nvarchar(50),  
      ManagerID int  
    CONSTRAINT PK_NewOrg_OrgNode  
      PRIMARY KEY CLUSTERED (OrgNode)  
    );  
    GO  
    ```  
  
### <a name="to-create-a-temporary-table-named-children"></a><span data-ttu-id="844d6-115">Создание новой таблицы с именем #Children</span><span class="sxs-lookup"><span data-stu-id="844d6-115">To create a temporary table named #Children</span></span>  
  
1.  <span data-ttu-id="844d6-116">Создайте временную таблицу с именем **#Children** . В ней должен быть столбец **Num** , который должен содержать количество потомков каждого узла:</span><span class="sxs-lookup"><span data-stu-id="844d6-116">Create a temporary table named **#Children** with a column named **Num** that will contain the number of children for each node:</span></span>  
  
    ```  
    CREATE TABLE #Children   
       (  
        EmployeeID int,  
        ManagerID int,  
        Num int  
    );  
    GO  
    ```  
  
2.  <span data-ttu-id="844d6-117">Добавьте индекс, который значительно ускорит работу запроса, заполняющего таблицу **NewOrg** :</span><span class="sxs-lookup"><span data-stu-id="844d6-117">Add an index that will significantly speed up the query that populates the **NewOrg** table:</span></span>  
  
    ```  
    CREATE CLUSTERED INDEX tmpind ON #Children(ManagerID, EmployeeID);  
    GO  
    ```  
  
### <a name="to-populate-the-neworg-table"></a><span data-ttu-id="844d6-118">Заполнение таблицы NewOrg</span><span class="sxs-lookup"><span data-stu-id="844d6-118">To populate the NewOrg table</span></span>  
  
1.  <span data-ttu-id="844d6-119">Рекурсивные запросы запрещают использование вложенных запросов со статистическими выражениями.</span><span class="sxs-lookup"><span data-stu-id="844d6-119">Recursive queries forbid subqueries with aggregates.</span></span> <span data-ttu-id="844d6-120">Вместо этого заполните таблицу **#Children** с помощью следующего кода, который использует метод [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) для заполнения столбца **Num** :</span><span class="sxs-lookup"><span data-stu-id="844d6-120">Instead, populate the **#Children** table with the following code, which uses the [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) method to populate the **Num** column:</span></span>  
  
    ```  
    INSERT #Children (EmployeeID, ManagerID, Num)  
    SELECT EmployeeID, ManagerID,  
      ROW_NUMBER() OVER (PARTITION BY ManagerID ORDER BY ManagerID)   
    FROM EmployeeDemo  
    GO  
  
    ```  
  
2.  <span data-ttu-id="844d6-121">Просмотрите таблицу **#Children** .</span><span class="sxs-lookup"><span data-stu-id="844d6-121">Review the **#Children** table.</span></span> <span data-ttu-id="844d6-122">Обратите внимание, что в столбце **Num** содержатся последовательные номера для каждого менеджера.</span><span class="sxs-lookup"><span data-stu-id="844d6-122">Note how the **Num** column contains sequential numbers for each manager.</span></span>  
  
    ```  
    SELECT * FROM #Children ORDER BY ManagerID, Num  
    GO  
  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     `EmployeeID ManagerID Num`  
  
     `---------- --------- ---`  
  
     `1        NULL       1`  
  
     `2         1         1`  
  
     `3         1         2`  
  
     `4         2         1`  
  
     `5         2         2`  
  
     `6         2         3`  
  
     `7         3         1`  
  
     `8         3         2`  
  
     `9         4         1`  
  
     `10        4         2`  
  
3.  <span data-ttu-id="844d6-123">Заполнение таблицы **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="844d6-123">Populate the **NewOrg** table.</span></span> <span data-ttu-id="844d6-124">Используйте методы OrgNode и ToString, чтобы объединить значения **num** в `hierarchyid` Формат, а затем обновите столбец **OrgNode** с помощью итоговых иерархических значений:</span><span class="sxs-lookup"><span data-stu-id="844d6-124">Use the GetRoot and ToString methods to concatenate the **Num** values into the `hierarchyid` format, and then update the **OrgNode** column with the resultant hierarchical values:</span></span>  
  
    ```  
    WITH paths(path, EmployeeID)   
    AS (  
    -- This section provides the value for the root of the hierarchy  
    SELECT hierarchyid::GetRoot() AS OrgNode, EmployeeID   
    FROM #Children AS C   
    WHERE ManagerID IS NULL   
  
    UNION ALL   
    -- This section provides values for all nodes except the root  
    SELECT   
    CAST(p.path.ToString() + CAST(C.Num AS varchar(30)) + '/' AS hierarchyid),   
    C.EmployeeID  
    FROM #Children AS C   
    JOIN paths AS p   
       ON C.ManagerID = P.EmployeeID   
    )  
    INSERT NewOrg (OrgNode, O.EmployeeID, O.LoginID, O.ManagerID)  
    SELECT P.path, O.EmployeeID, O.LoginID, O.ManagerID  
    FROM EmployeeDemo AS O   
    JOIN Paths AS P   
       ON O.EmployeeID = P.EmployeeID  
    GO  
  
    ```  
  
4.  <span data-ttu-id="844d6-125">Столбец типа данных `hierarchyid` становится более понятным, если его преобразовать в символьный формат.</span><span class="sxs-lookup"><span data-stu-id="844d6-125">A `hierarchyid` column is more understandable when you convert it to character format.</span></span> <span data-ttu-id="844d6-126">Просмотрите данные в таблице **NewOrg** , выполнив следующий код, содержащий два представления столбца **OrgNode** :</span><span class="sxs-lookup"><span data-stu-id="844d6-126">Review the data in the **NewOrg** table by executing the following code, which contains two representations of the **OrgNode** column:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode, *   
    FROM NewOrg   
    ORDER BY LogicalNode;  
    GO  
  
    ```  
  
     <span data-ttu-id="844d6-127">Столбец **логикалноде** преобразует `hierarchyid` столбец в более удобочитаемую текстовую форму, представляющую иерархию.</span><span class="sxs-lookup"><span data-stu-id="844d6-127">The **LogicalNode** column converts the `hierarchyid` column into a more readable text form that represents the hierarchy.</span></span> <span data-ttu-id="844d6-128">В оставшихся задачах для представления логического формата столбцов типа данных `hierarchyid` также следует использовать метод `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="844d6-128">In the remaining tasks, you will use the `ToString()` method to show the logical format of the `hierarchyid` columns.</span></span>  
  
5.  <span data-ttu-id="844d6-129">Удалите временную таблицу, она больше не понадобится:</span><span class="sxs-lookup"><span data-stu-id="844d6-129">Drop the temporary table, which is no longer needed:</span></span>  
  
    ```  
    DROP TABLE #Children  
    GO  
    ```  
  
 <span data-ttu-id="844d6-130">Следующая задача создаст индексы для поддержки иерархической структуры.</span><span class="sxs-lookup"><span data-stu-id="844d6-130">The next task will create indexes to support the hierarchical structure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="844d6-131">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="844d6-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="844d6-132">Оптимизация таблицы NewOrg</span><span class="sxs-lookup"><span data-stu-id="844d6-132">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
  
