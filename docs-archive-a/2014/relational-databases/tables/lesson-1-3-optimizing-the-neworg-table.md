---
title: Оптимизация таблицы NewOrg | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- optimizing tables
ms.assetid: 89ff6d37-94c0-4773-8be9-dde943fff023
author: stevestein
ms.author: sstein
ms.openlocfilehash: 39c09a3a73051e7a61f3a62a125232d83d1570c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654109"
---
# <a name="optimizing-the-neworg-table"></a><span data-ttu-id="a56c4-102">Оптимизация таблицы NewOrg</span><span class="sxs-lookup"><span data-stu-id="a56c4-102">Optimizing the NewOrg Table</span></span>
  <span data-ttu-id="a56c4-103">Таблица **Таблица NewOrd** , созданная в задаче [Заполнение таблицы с существующими иерархическими данными](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) , содержит все сведения о сотрудниках и представляет иерархическую структуру с помощью `hierarchyid` типа данных.</span><span class="sxs-lookup"><span data-stu-id="a56c4-103">The **NewOrd** table that you created in the [Populating a Table with Existing Hierarchical Data](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) task contains all the employee information, and represents the hierarchical structure by using a `hierarchyid` data type.</span></span> <span data-ttu-id="a56c4-104">Эта задача добавляет новые индексы для поддержки поиска по столбцу `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="a56c4-104">This task adds new indexes to support searches on the `hierarchyid` column.</span></span>  
  
## <a name="clustered-index"></a><span data-ttu-id="a56c4-105">Кластеризованный индекс</span><span class="sxs-lookup"><span data-stu-id="a56c4-105">Clustered Index</span></span>  
 <span data-ttu-id="a56c4-106">`hierarchyid`Столбец (**OrgNode**) является первичным ключом для таблицы **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="a56c4-106">The `hierarchyid` column (**OrgNode**) is the primary key for the **NewOrg** table.</span></span> <span data-ttu-id="a56c4-107">После создания таблицы в ней содержался кластеризованный индекс **PK_NewOrg_OrgNode** , обеспечивающий уникальность значений в столбце **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="a56c4-107">When the table was created, it contained a clustered index named **PK_NewOrg_OrgNode** to enforce the uniqueness of the **OrgNode** column.</span></span> <span data-ttu-id="a56c4-108">Кластеризованный индекс также поддерживает поиск по таблице по глубине.</span><span class="sxs-lookup"><span data-stu-id="a56c4-108">This clustered index also supports a depth-first search of the table.</span></span>  
  
## <a name="nonclustered-index"></a><span data-ttu-id="a56c4-109">Некластеризованный индекс</span><span class="sxs-lookup"><span data-stu-id="a56c4-109">Nonclustered Index</span></span>  
 <span data-ttu-id="a56c4-110">Во время этого шага создаются два некластеризованных индекса для поддержки работы обычных видов поиска.</span><span class="sxs-lookup"><span data-stu-id="a56c4-110">This step creates two nonclustered indexes to support typical searches.</span></span>  
  
#### <a name="to-index-the-neworg-table-for-efficient-searches"></a><span data-ttu-id="a56c4-111">Индексация таблицы NewOrg для обеспечения эффективного поиска.</span><span class="sxs-lookup"><span data-stu-id="a56c4-111">To index the NewOrg table for efficient searches</span></span>  
  
1.  <span data-ttu-id="a56c4-112">Чтобы обеспечить функционирование запросов, работающих на одном и том же уровне иерархии, следует использовать метод [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) для создания вычисляемого столбца, содержащего уровень иерархии.</span><span class="sxs-lookup"><span data-stu-id="a56c4-112">To help queries at the same level in the hierarchy, use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to create a computed column that contains the level in the hierarchy.</span></span> <span data-ttu-id="a56c4-113">Затем следует создать составной индекс, основанный на уровне и `Hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="a56c4-113">Then, create a composite index on the level and the `Hierarchyid`.</span></span> <span data-ttu-id="a56c4-114">Запустите следующий код для создания вычисляемого столбца и индекса преимущественно в ширину:</span><span class="sxs-lookup"><span data-stu-id="a56c4-114">Run the following code to create the computed column and the breadth-first index:</span></span>  
  
    ```  
    ALTER TABLE NewOrg   
       ADD H_Level AS OrgNode.GetLevel() ;  
    CREATE UNIQUE INDEX EmpBFInd   
       ON NewOrg(H_Level, OrgNode) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="a56c4-115">Создайте уникальный индекс для столбца **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="a56c4-115">Create a unique index on the **EmployeeID** column.</span></span> <span data-ttu-id="a56c4-116">Это стандартный единичный уточняющий запрос относительно одного сотрудника по номеру **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="a56c4-116">This is the traditional singleton lookup of a single employee by **EmployeeID** number.</span></span> <span data-ttu-id="a56c4-117">Запустите следующий код, чтобы создать индекс для столбца **EmployeeID**:</span><span class="sxs-lookup"><span data-stu-id="a56c4-117">Run the following code to create an index on **EmployeeID**:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmpIDs_unq ON NewOrg(EmployeeID) ;  
    GO  
    ```  
  
3.  <span data-ttu-id="a56c4-118">Запустите следующий код, чтобы получить данные из таблицы, упорядоченные относительно каждого из этих трех индексов:</span><span class="sxs-lookup"><span data-stu-id="a56c4-118">Run the following code to retrieve data from the table in the order of each of the three indexes:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID  
    FROM NewOrg   
    ORDER BY OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY H_Level, OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY EmployeeID;  
    GO  
    ```  
  
4.  <span data-ttu-id="a56c4-119">Сравните результирующие наборы, чтобы понять порядок хранения для каждого типа индекса.</span><span class="sxs-lookup"><span data-stu-id="a56c4-119">Compare the result sets to see how the order is stored in each type of index.</span></span> <span data-ttu-id="a56c4-120">Далее приводятся только первые четыре строки из каждого выходного набора.</span><span class="sxs-lookup"><span data-stu-id="a56c4-120">Only the first four rows of each output follow.</span></span>  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     <span data-ttu-id="a56c4-121">Индекс преимущественно в глубину: записи сотрудников хранятся рядом с записью их менеджера.</span><span class="sxs-lookup"><span data-stu-id="a56c4-121">Depth-first index: Employee records are stored adjacent to their manager.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     <span data-ttu-id="a56c4-122">Индекс преимущественно по**EmployeeID**: строки хранятся в соответствии с последовательностью значений **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="a56c4-122">**EmployeeID**-first index: Rows are stored in **EmployeeID** sequence.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
> [!NOTE]  
>  <span data-ttu-id="a56c4-123">Диаграммы, на которых показана разница между индексом преимущественно в глубину и индексом преимущественно в ширину, см. в разделе [Иерархические данные (SQL Server)](../hierarchical-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a56c4-123">For diagrams that show the difference between a depth-first index and a breadth-first index, see [Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span></span>  
  
#### <a name="to-drop-the-unnecessary-columns"></a><span data-ttu-id="a56c4-124">Удаление ненужных столбцов</span><span class="sxs-lookup"><span data-stu-id="a56c4-124">To drop the unnecessary columns</span></span>  
  
1.  <span data-ttu-id="a56c4-125">Столбец **ManagerID** представляет связь "сотрудник-менеджер", которая на данный момент представлена столбцом **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="a56c4-125">The **ManagerID** column represents the employee/manager relationship, which is now represented by the **OrgNode** column.</span></span> <span data-ttu-id="a56c4-126">Если другим приложениям столбец **ManagerID** не нужен, то, возможно, стоит его удалить с помощью следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="a56c4-126">If other applications do not need the **ManagerID** column, consider dropping it by using the following statement:</span></span>  
  
    ```  
    ALTER TABLE NewOrg DROP COLUMN ManagerID ;  
    GO  
    ```  
  
2.  <span data-ttu-id="a56c4-127">Столбец **EmployeeID** также является избыточным.</span><span class="sxs-lookup"><span data-stu-id="a56c4-127">The **EmployeeID** column is also redundant.</span></span> <span data-ttu-id="a56c4-128">Столбец **OrgNode** уникально идентифицирует каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="a56c4-128">The **OrgNode** column uniquely identifies each employee.</span></span> <span data-ttu-id="a56c4-129">Если другим приложениям столбец **EmployeeID** не нужен, то, возможно, стоит его удалить с помощью следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="a56c4-129">If other applications do not need the **EmployeeID** column, consider dropping the index and then the column by using the following code:</span></span>  
  
    ```  
    DROP INDEX EmpIDs_unq ON NewOrg ;  
    ALTER TABLE NewOrg DROP COLUMN EmployeeID ;  
    GO  
    ```  
  
#### <a name="to-replace-the-original-table-with-the-new-table"></a><span data-ttu-id="a56c4-130">Замена исходной таблицы на новую</span><span class="sxs-lookup"><span data-stu-id="a56c4-130">To replace the original table with the new table</span></span>  
  
1.  <span data-ttu-id="a56c4-131">Если в исходной таблице содержались дополнительные индексы или ограничения, добавьте их в таблицу **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="a56c4-131">If your original table contained any additional indexes or constraints, add them to the **NewOrg** table.</span></span>  
  
2.  <span data-ttu-id="a56c4-132">Замените старую таблицу **EmployeeDemo** новой.</span><span class="sxs-lookup"><span data-stu-id="a56c4-132">Replace the old **EmployeeDemo** table with the new table.</span></span> <span data-ttu-id="a56c4-133">Запустите следующий код, чтобы удалить старую таблицу и присвоить новой таблице имя старой:</span><span class="sxs-lookup"><span data-stu-id="a56c4-133">Run the following code to drop the old table, and then rename the new table with the old name:</span></span>  
  
    ```  
    DROP TABLE EmployeeDemo ;  
    GO  
    sp_rename 'NewOrg', EmployeeDemo ;  
    GO  
    ```  
  
3.  <span data-ttu-id="a56c4-134">Запустите следующий код, чтобы изучить окончательную таблицу:</span><span class="sxs-lookup"><span data-stu-id="a56c4-134">Run the following code to examine the final table:</span></span>  
  
    ```  
    SELECT * FROM EmployeeDemo ;  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a56c4-135">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="a56c4-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a56c4-136">Сводка. Преобразование таблицы в иерархическую структуру</span><span class="sxs-lookup"><span data-stu-id="a56c4-136">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
  
