---
title: Заполнение иерархической таблицы с помощью иерархических методов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- HierarchyID
helpviewer_keywords:
- HierarchyID
ms.assetid: 2c95fa60-5b8e-4a05-ac09-cffe2b05900a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ef99d711a772a075f568a83f5d56fcecaaa598f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665917"
---
# <a name="populating-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="43dd3-102">Заполнение иерархической таблицы с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="43dd3-102">Populating a Hierarchical Table Using Hierarchical Methods</span></span>
  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="43dd3-103">работает 8 человек.</span><span class="sxs-lookup"><span data-stu-id="43dd3-103">has 8 employees working in the Marketing department.</span></span> <span data-ttu-id="43dd3-104">Иерархический список сотрудников выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="43dd3-104">The employee hierarchy looks like this:</span></span>  
  
 <span data-ttu-id="43dd3-105">**Дэвид**, **EmployeeID** 6, начальник отдела маркетинга.</span><span class="sxs-lookup"><span data-stu-id="43dd3-105">**David**, **EmployeeID** 6, is the Marketing Manager.</span></span> <span data-ttu-id="43dd3-106">В подчинении у **Дэвида**находятся три специалиста по маркетингу:</span><span class="sxs-lookup"><span data-stu-id="43dd3-106">Three Marketing Specialists report to **David**:</span></span>  
  
-   <span data-ttu-id="43dd3-107">**Сара**, **EmployeeID** 46</span><span class="sxs-lookup"><span data-stu-id="43dd3-107">**Sariya**, **EmployeeID** 46</span></span>  
  
-   <span data-ttu-id="43dd3-108">**Джон**, **EmployeeID** 271</span><span class="sxs-lookup"><span data-stu-id="43dd3-108">**John**, **EmployeeID** 271</span></span>  
  
-   <span data-ttu-id="43dd3-109">**Джил**, **EmployeeID** 119</span><span class="sxs-lookup"><span data-stu-id="43dd3-109">**Jill**, **EmployeeID** 119</span></span>  
  
 <span data-ttu-id="43dd3-110">Маркетолог **Ванида** (**EmployeeID** 269), подчиняется **Саре**, а маркетолог **Мэри** (**EmployeeID** 272) подчиняется **Джону**.</span><span class="sxs-lookup"><span data-stu-id="43dd3-110">Marketing Assistant **Wanida** (**EmployeeID** 269), reports to **Sariya**, and Marketing Assistant **Mary** (**EmployeeID** 272), reports to **John**.</span></span>  
  
### <a name="to-insert-the-root-of-the-hierarchy-tree"></a><span data-ttu-id="43dd3-111">Вставка корневого элемента иерархического дерева</span><span class="sxs-lookup"><span data-stu-id="43dd3-111">To insert the root of the hierarchy tree</span></span>  
  
1.  <span data-ttu-id="43dd3-112">В следующем примере запись **Дэвид** (начальник отдела маркетинга) вставляется таблицу в качестве корневого элемента иерархии.</span><span class="sxs-lookup"><span data-stu-id="43dd3-112">The following example inserts **David** the Marketing Manager into the table at the root of the hierarchy.</span></span> <span data-ttu-id="43dd3-113">**OrdLevel** — вычисляемый столбец.</span><span class="sxs-lookup"><span data-stu-id="43dd3-113">The **OrdLevel** column is a computed column.</span></span> <span data-ttu-id="43dd3-114">Следовательно, он не является частью инструкции INSERT.</span><span class="sxs-lookup"><span data-stu-id="43dd3-114">Therefore, it is not part of the INSERT statement.</span></span> <span data-ttu-id="43dd3-115">Для вставки первой записи в вершину иерархии используется метод [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="43dd3-115">This first record uses the [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) method to populate this first record as the root of the hierarchy.</span></span>  
  
    ```  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES (hierarchyid::GetRoot(), 6, 'David', 'Marketing Manager') ;  
    GO  
    ```  
  
2.  <span data-ttu-id="43dd3-116">Для просмотра начальной строки таблицы используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="43dd3-116">Execute the following code to examine initial row in the table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    ```  
  
 <span data-ttu-id="43dd3-117">Как и на предыдущем занятии, для преобразования данных типа `hierarchyid` в более наглядный формат используется метод `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="43dd3-117">As in the previous lesson, we use the `ToString()` method to convert the `hierarchyid` data type to a format that is more easily understood.</span></span>  
  
### <a name="to-insert-a-subordinate-employee"></a><span data-ttu-id="43dd3-118">Вставка записи подчиненного</span><span class="sxs-lookup"><span data-stu-id="43dd3-118">To insert a subordinate employee</span></span>  
  
1.  <span data-ttu-id="43dd3-119">**Сара** подчиняется **Дэвиду**.</span><span class="sxs-lookup"><span data-stu-id="43dd3-119">**Sariya** reports to **David**.</span></span> <span data-ttu-id="43dd3-120">Чтобы вставить узел **Sariya** , необходимо создать соответствующее значение **OrgNode** типа данных `hierarchyid` .</span><span class="sxs-lookup"><span data-stu-id="43dd3-120">To insert **Sariya's** node, you must create an appropriate **OrgNode** value of data type `hierarchyid`.</span></span> <span data-ttu-id="43dd3-121">Следующий код создает переменную типа `hierarchyid` и присваивает ей корневое значение OrgNode таблицы.</span><span class="sxs-lookup"><span data-stu-id="43dd3-121">The following code creates a variable of data type `hierarchyid` and populates it with the root OrgNode value of the table.</span></span> <span data-ttu-id="43dd3-122">Затем эта переменная используется методом [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) для вставки строки, представляющей подчиненный узел.</span><span class="sxs-lookup"><span data-stu-id="43dd3-122">Then uses that variable with the [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) method to insert row that is a subordinate node.</span></span> <span data-ttu-id="43dd3-123">`GetDescendant` принимает два аргумента.</span><span class="sxs-lookup"><span data-stu-id="43dd3-123">`GetDescendant` takes two arguments.</span></span> <span data-ttu-id="43dd3-124">Вот список вариантов с разными значениями аргументов.</span><span class="sxs-lookup"><span data-stu-id="43dd3-124">Review the following options for the argument values:</span></span>  
  
    -   <span data-ttu-id="43dd3-125">Если родительская запись — NULL, `GetDescendant` возвращает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="43dd3-125">If parent is NULL, `GetDescendant` returns NULL.</span></span>  
  
    -   <span data-ttu-id="43dd3-126">Если родительская запись — не NULL, а потомки child1 и child2 — NULL, метод `GetDescendant` возвращает одного потомка данного родителя.</span><span class="sxs-lookup"><span data-stu-id="43dd3-126">If parent is not NULL, and both child1 and child2 are NULL, `GetDescendant` returns a child of parent.</span></span>  
  
    -   <span data-ttu-id="43dd3-127">Если родительская запись и потомок child1 — не NULL, а потомок child2 равен NULL, метод `GetDescendant` возвращает значение потомка родителя, который больше чем child1.</span><span class="sxs-lookup"><span data-stu-id="43dd3-127">If parent and child1 are not NULL, and child2 is NULL, `GetDescendant` returns a child of parent greater than child1.</span></span>  
  
    -   <span data-ttu-id="43dd3-128">Если родитель и потомок child2 — не NULL, а потомок child1 равен NULL, метод `GetDescendant` возвращает значение потомка родителя, который меньше child2.</span><span class="sxs-lookup"><span data-stu-id="43dd3-128">If parent and child2 are not NULL and child1 is NULL, `GetDescendant` returns a child of parent less than child2.</span></span>  
  
    -   <span data-ttu-id="43dd3-129">Если родитель, child1 и child2 не равны NULL, метод `GetDescendant` возвращает потомка родителя, который больше child1 и меньше child2.</span><span class="sxs-lookup"><span data-stu-id="43dd3-129">If parent, child1, and child2 are all not NULL, `GetDescendant` returns a child of parent greater than child1 and less than child2.</span></span>  
  
     <span data-ttu-id="43dd3-130">В следующем примере в качестве аргументов корневого родительского элемента используются значения `(NULL, NULL)` , так как таблица пока не содержит никаких строк, кроме корневой.</span><span class="sxs-lookup"><span data-stu-id="43dd3-130">The following code uses the `(NULL, NULL)` arguments of the root parent because there are not yet any rows in the table except the root.</span></span> <span data-ttu-id="43dd3-131">Чтобы вставить запись **Сара**, выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="43dd3-131">Execute the following code to insert **Sariya**:</span></span>  
  
    ```  
    DECLARE @Manager hierarchyid   
    SELECT @Manager = hierarchyid::GetRoot()  
    FROM HumanResources.EmployeeOrg ;  
  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES  
    (@Manager.GetDescendant(NULL, NULL), 46, 'Sariya', 'Marketing Specialist') ;  
  
    ```  
  
2.  <span data-ttu-id="43dd3-132">Чтобы обратиться к таблице и просмотреть вставленные записи, повторите запрос из первой процедуры:</span><span class="sxs-lookup"><span data-stu-id="43dd3-132">Repeat the query from the first procedure to query the table and see how the entries appear:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    ```  
  
### <a name="to-create-a-procedure-for-entering-new-nodes"></a><span data-ttu-id="43dd3-133">Создание процедуры ввода новых узлов</span><span class="sxs-lookup"><span data-stu-id="43dd3-133">To create a procedure for entering new nodes</span></span>  
  
1.  <span data-ttu-id="43dd3-134">Для упрощения ввода данных можно создать следующую хранимую процедуру, вставляющую данные о сотрудниках в таблицу **EmployeeOrg** .</span><span class="sxs-lookup"><span data-stu-id="43dd3-134">To simplify entering data, create the following stored procedure to add employees to the **EmployeeOrg** table.</span></span> <span data-ttu-id="43dd3-135">Входные данные процедуры — это данные о добавляемом сотруднике.</span><span class="sxs-lookup"><span data-stu-id="43dd3-135">The procedure accepts input values about the employee being added.</span></span> <span data-ttu-id="43dd3-136">Это **EmployeeID** руководителя нового сотрудника, **EmployeeID** самого сотрудника, а также их имена и должности.</span><span class="sxs-lookup"><span data-stu-id="43dd3-136">This includes the **EmployeeID** of the new employee's manager, the new employee's **EmployeeID** number, and their first name and title.</span></span> <span data-ttu-id="43dd3-137">В процедуре используются методы `GetDescendant()` и [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="43dd3-137">The procedure uses `GetDescendant()` and also the [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="43dd3-138">Чтобы создать процедуру, выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="43dd3-138">Execute the following code to create the procedure:</span></span>  
  
    ```  
    CREATE PROC AddEmp(@mgrid int, @empid int, @e_name varchar(20), @title varchar(20))   
    AS   
    BEGIN  
       DECLARE @mOrgNode hierarchyid, @lc hierarchyid  
       SELECT @mOrgNode = OrgNode   
       FROM HumanResources.EmployeeOrg   
       WHERE EmployeeID = @mgrid  
       SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
       BEGIN TRANSACTION  
          SELECT @lc = max(OrgNode)   
          FROM HumanResources.EmployeeOrg   
          WHERE OrgNode.GetAncestor(1) =@mOrgNode ;  
  
          INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
          VALUES(@mOrgNode.GetDescendant(@lc, NULL), @empid, @e_name, @title)  
       COMMIT  
    END ;  
    GO  
    ```  
  
2.  <span data-ttu-id="43dd3-139">В следующем примере вставляются записи об остальных 4 сотрудниках, прямо или косвенно подчиняющихся **Дэвиду**.</span><span class="sxs-lookup"><span data-stu-id="43dd3-139">The following example adds the remaining 4 employees that report directly or indirectly to **David**.</span></span>  
  
    ```  
    EXEC AddEmp 6, 271, 'John', 'Marketing Specialist' ;  
    EXEC AddEmp 6, 119, 'Jill', 'Marketing Specialist' ;  
    EXEC AddEmp 46, 269, 'Wanida', 'Marketing Assistant' ;  
    EXEC AddEmp 271, 272, 'Mary', 'Marketing Assistant' ;  
    ```  
  
3.  <span data-ttu-id="43dd3-140">Для просмотра строк таблицы **EmployeeOrg** выполните следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="43dd3-140">Again, execute the following query examine the rows in the **EmployeeOrg** table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    /1/1/        0x5AC0  2        269        Wanida  Marketing Assistant  
    /2/          0x68    1        271        John    Marketing Specialist  
    /2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
    /3/          0x78    1        119        Jill    Marketing Specialist  
    ```  
  
 <span data-ttu-id="43dd3-141">Теперь таблица полностью заполнена записями о сотрудниках отдела маркетинга.</span><span class="sxs-lookup"><span data-stu-id="43dd3-141">The table is now fully populated with the Marketing organization.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="43dd3-142">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="43dd3-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="43dd3-143">Создание запросов к иерархической таблице с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="43dd3-143">Querying a Hierarchical Table Using Hierarchy Methods</span></span>](lesson-2-3-querying-a-hierarchical-table-using-hierarchy-methods.md)  
  
  
