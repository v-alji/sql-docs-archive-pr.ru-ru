---
title: Переупорядочение данных в иерархической таблице с применением иерархических методов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 7b8064c7-62c6-488d-84d2-57a5828fb907
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac6c93f359a81a80af81182120f213564680de0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654985"
---
# <a name="reordering-data-in-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="47a42-102">Переупорядочение данных в иерархической таблице с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="47a42-102">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>
  <span data-ttu-id="47a42-103">Реорганизация иерархии — это распространенная задача обслуживания.</span><span class="sxs-lookup"><span data-stu-id="47a42-103">Reorganizing a hierarchy is a common maintenance task.</span></span> <span data-ttu-id="47a42-104">В этой задаче в первую очередь переместим одну строку в новую позицию в иерархии с помощью инструкции UPDATE с методом [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="47a42-104">In this task, we will use an UPDATE statement with the [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) method to first move a single row to a new location in the hierarchy.</span></span> <span data-ttu-id="47a42-105">Затем переместим все поддерево в новое место.</span><span class="sxs-lookup"><span data-stu-id="47a42-105">Then we will move an entire sub-tree to a new location.</span></span>  
  
 <span data-ttu-id="47a42-106">Метод `GetReparentedValue` имеет два аргумента.</span><span class="sxs-lookup"><span data-stu-id="47a42-106">The `GetReparentedValue` method takes two arguments.</span></span> <span data-ttu-id="47a42-107">В первом аргументе описывается та часть иерархии, которая будет изменена.</span><span class="sxs-lookup"><span data-stu-id="47a42-107">The first argument describes the part of the hierarchy to be modified.</span></span> <span data-ttu-id="47a42-108">Например, если в иерархии **/1/4/2/3/** необходимо изменить сегмент **/1/4/** так, чтобы в результате получилась иерархия **/2/1/2/3/**, в которой последние два узла (**2/3/**) остались бы без изменений, необходимо указать в качестве первого аргумента изменяемые узлы (**/1/4/**).</span><span class="sxs-lookup"><span data-stu-id="47a42-108">For example, if a hierarchy is **/1/4/2/3/** and you want to change the **/1/4/** section, the hierarchy becomes **/2/1/2/3/**, leaving the last two nodes (**2/3/**) unchanged, you must provide the changing nodes (**/1/4/**) as the first argument.</span></span> <span data-ttu-id="47a42-109">Второй аргумент предоставляет новый уровень иерархии; для этого примера это **/2/1/**.</span><span class="sxs-lookup"><span data-stu-id="47a42-109">The second argument provides the new hierarchy level, in our example **/2/1/**.</span></span> <span data-ttu-id="47a42-110">Эти два аргумента не обязаны содержать одинаковое число уровней.</span><span class="sxs-lookup"><span data-stu-id="47a42-110">The two arguments do not have to contain the same number of levels.</span></span>  
  
### <a name="to-move-a-single-row-to-a-new-location-in-the-hierarchy"></a><span data-ttu-id="47a42-111">Перемещение одной строки на новое место в иерархии</span><span class="sxs-lookup"><span data-stu-id="47a42-111">To move a single row to a new location in the hierarchy</span></span>  
  
1.  <span data-ttu-id="47a42-112">В настоящий момент Wanida является подчиненной Sariya.</span><span class="sxs-lookup"><span data-stu-id="47a42-112">Currently Wanida reports to Sariya.</span></span> <span data-ttu-id="47a42-113">В этой процедуре переместим Wanida из ее текущего узла **/1/1/** в другой так, чтобы она стала подчиненной Jill.</span><span class="sxs-lookup"><span data-stu-id="47a42-113">In this procedure, you move Wanida from her current node **/1/1/,** so that she reports to Jill.</span></span> <span data-ttu-id="47a42-114">Ее новым узлом будет узел **/3/1/** , следовательно, первым аргументом будет **/1/** , а вторым — **/3/** .</span><span class="sxs-lookup"><span data-stu-id="47a42-114">Her new node will become **/3/1/** so **/1/** is the first argument and **/3/** is the second.</span></span> <span data-ttu-id="47a42-115">Эти значения соответствуют значениям Sariya и Jill в столбце **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="47a42-115">These correspond to the **OrgNode** values of Sariya and Jill.</span></span> <span data-ttu-id="47a42-116">Исполните следующий код, чтобы переместить Wanida из организации Sariya в организацию Jill:</span><span class="sxs-lookup"><span data-stu-id="47a42-116">Execute the following code to move Wanida from Sariya's organization to Jill's:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @CurrentEmployee = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 269 ;   
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 46 ;   
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 119 ;   
  
    UPDATE HumanResources.EmployeeOrg  
    SET OrgNode = @CurrentEmployee. GetReparentedValue(@OldParent, @NewParent)   
    WHERE OrgNode = @CurrentEmployee ;  
    GO  
    ```  
  
2.  <span data-ttu-id="47a42-117">Чтобы просмотреть результат, выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="47a42-117">Execute the following code to see the result:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     <span data-ttu-id="47a42-118">Теперь Wanida находится в узле **/3/1/**.</span><span class="sxs-lookup"><span data-stu-id="47a42-118">Wanida is now at node **/3/1/**.</span></span>  
  
### <a name="to-reorganize-a-section-of-a-hierarchy"></a><span data-ttu-id="47a42-119">Реорганизация раздела иерархии</span><span class="sxs-lookup"><span data-stu-id="47a42-119">To reorganize a section of a hierarchy</span></span>  
  
1.  <span data-ttu-id="47a42-120">Чтобы продемонстрировать, как можно одновременно переместить большее количество людей, сначала необходимо выполнить следующий код, чтобы добавить Ваниде подчиненного.</span><span class="sxs-lookup"><span data-stu-id="47a42-120">To demonstrate how to move a larger number of people at the same time, first execute the following code to add an intern reporting to Wanida:</span></span>  
  
    ```  
    EXEC AddEmp 269, 291, 'Kevin', 'Marketing Intern'  ;  
    GO  
    ```  
  
2.  <span data-ttu-id="47a42-121">Теперь Кевин — подчиненный Ваниды, которая является подчиненной Jill, которая является подчиненной David.</span><span class="sxs-lookup"><span data-stu-id="47a42-121">Now Kevin reports to Wanida, who reports to Jill, who reports to David.</span></span> <span data-ttu-id="47a42-122">Это означает, что Kevin находится на уровне **/3/1/1/**.</span><span class="sxs-lookup"><span data-stu-id="47a42-122">That means that Kevin is at level **/3/1/1/**.</span></span> <span data-ttu-id="47a42-123">Чтобы переместить всех подчиненных Jill к новому руководителю, мы присвоим новое значение всем узлам, имеющим значение **/3/** в столбце **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="47a42-123">To move all of Jill's subordinates to a new manager, we will update all nodes that have **/3/** as their **OrgNode** to a new value.</span></span> <span data-ttu-id="47a42-124">Выполните следующий код, чтобы произвести изменение, в результате которого Wanida станет подчиненной Sariya, но Kevin останется подчиненным Wanida:</span><span class="sxs-lookup"><span data-stu-id="47a42-124">Execute the following code to update Wanida to report to Sariya, but keep  Kevin reporting to Wanida:</span></span>  
  
    ```  
    DECLARE @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 119 ; -- Jill  
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ; -- Sariya  
    DECLARE children_cursor CURSOR FOR  
    SELECT OrgNode FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @OldParent;  
    DECLARE @ChildId hierarchyid;  
    OPEN children_cursor  
    FETCH NEXT FROM children_cursor INTO @ChildId;  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
    START:  
        DECLARE @NewId hierarchyid;  
        SELECT @NewId = @NewParent.GetDescendant(MAX(OrgNode), NULL)  
        FROM HumanResources.EmployeeOrg WHERE OrgNode.GetAncestor(1) = @NewParent;  
  
        UPDATE HumanResources.EmployeeOrg  
        SET OrgNode = OrgNode.GetReparentedValue(@ChildId, @NewId)  
        WHERE OrgNode.IsDescendantOf(@ChildId) = 1;  
        IF @@error <> 0 GOTO START -- On error, retry  
            FETCH NEXT FROM children_cursor INTO @ChildId;  
    END  
    CLOSE children_cursor;  
    DEALLOCATE children_cursor;  
  
    ```  
  
3.  <span data-ttu-id="47a42-125">Чтобы просмотреть результат, выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="47a42-125">Execute the following code to see the result:</span></span>  
  
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
/1/1//2      0x5AD0  3        291        Kevin   Marketing Intern  
/2/          0x68    1        271        John    Marketing Specialist  
/2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
/3/          0x78    1        119        Jill    Marketing Specialist  
```  
  
 <span data-ttu-id="47a42-126">Все организационное дерево, которое подчинялось Jill (Wanida и Kevin) теперь подчиняется Sariya.</span><span class="sxs-lookup"><span data-stu-id="47a42-126">The entire organizational tree that had reported to Jill (both Wanida and Kevin) now reports to Sariya.</span></span>  
  
 <span data-ttu-id="47a42-127">Хранимую процедуру для реорганизации раздела иерархии можно найти в подразделе "Перемещение поддеревьев" раздела [Реорганизация раздела иерархии](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span><span class="sxs-lookup"><span data-stu-id="47a42-127">For a stored procedure to reorganize a section of a hierarchy, see the "Moving Subtrees" section of [Moving Subtrees](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="47a42-128">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="47a42-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="47a42-129">Сводка. Управление данными в иерархической таблице</span><span class="sxs-lookup"><span data-stu-id="47a42-129">Summary: Managing Data in a Hierarchical Table</span></span>](lesson-2-5-summary-managing-data-in-a-hierarchical-table.md)  
  
  
