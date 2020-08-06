---
title: Создание запросов к иерархической таблице с помощью иерархических методов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 3b4f7dae-65b5-4d8d-8641-87aba9aa692d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c86c8e8678fc821dc3796a511349c1c3498bdb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665252"
---
# <a name="querying-a-hierarchical-table-using-hierarchy-methods"></a><span data-ttu-id="4a92b-102">Создание запросов к иерархической таблице с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="4a92b-102">Querying a Hierarchical Table Using Hierarchy Methods</span></span>
  <span data-ttu-id="4a92b-103">После того как таблица HumanResources.EmployeeOrg будет заполнена, эта задача продемонстрирует, как можно проводить запросы к иерархии с помощью некоторых иерархических методов.</span><span class="sxs-lookup"><span data-stu-id="4a92b-103">Now that the HumanResources.EmployeeOrg table is fully populated, this task will show you how to query the hierarchy using some of the hierarchical methods.</span></span>  
  
### <a name="to-find-subordinate-nodes"></a><span data-ttu-id="4a92b-104">Поиск подчиненных узлов</span><span class="sxs-lookup"><span data-stu-id="4a92b-104">To find subordinate nodes</span></span>  
  
1.  <span data-ttu-id="4a92b-105">Sariya имеет одного подчиненного.</span><span class="sxs-lookup"><span data-stu-id="4a92b-105">Sariya has one subordinate employee.</span></span> <span data-ttu-id="4a92b-106">Чтобы запросить подчиненных Sariya, выполните следующий запрос, в котором используется метод [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) :</span><span class="sxs-lookup"><span data-stu-id="4a92b-106">To query for Sariya's subordinates, execute the following query that uses the [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) method:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.IsDescendantOf(@CurrentEmployee ) = 1 ;  
    ```  
  
     <span data-ttu-id="4a92b-107">Результатами будут Sariya и Wanida.</span><span class="sxs-lookup"><span data-stu-id="4a92b-107">The result lists both Sariya and Wanida.</span></span> <span data-ttu-id="4a92b-108">Sariya перечисляется, поскольку она является потомком на нулевом уровне.</span><span class="sxs-lookup"><span data-stu-id="4a92b-108">Sariya is listed because she is the descendant at the 0 level.</span></span> <span data-ttu-id="4a92b-109">Wanida является потомком на первом уровне.</span><span class="sxs-lookup"><span data-stu-id="4a92b-109">Wanida is the descendant at the 1 level.</span></span>  
  
2.  <span data-ttu-id="4a92b-110">Запросить эту информацию можно также с помощью метода [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="4a92b-110">You can also query for this information by using the [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="4a92b-111">`GetAncestor` принимает аргумент уровня, попытка вернуть который выполняется.</span><span class="sxs-lookup"><span data-stu-id="4a92b-111">`GetAncestor` takes an argument for the level that you are trying to return.</span></span> <span data-ttu-id="4a92b-112">Поскольку Wanida находится одним уровнем ниже Sariya, следует использовать метод `GetAncestor(1)` так, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="4a92b-112">Since Wanida is one level underneath Sariya, use `GetAncestor(1)` as demonstrated in the following code:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="4a92b-113">В этот раз результатом будет только Wanida.</span><span class="sxs-lookup"><span data-stu-id="4a92b-113">This time the result lists only Wanida.</span></span>  
  
3.  <span data-ttu-id="4a92b-114">Теперь измените значение `@CurrentEmployee` на David (EmployeeID 6), а уровень на 2.</span><span class="sxs-lookup"><span data-stu-id="4a92b-114">Now change the `@CurrentEmployee` to David (EmployeeID 6) and the level to 2.</span></span> <span data-ttu-id="4a92b-115">Выполнение следующей инструкции также вернет значение Wanida:</span><span class="sxs-lookup"><span data-stu-id="4a92b-115">Execute the following to also return Wanida:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 6 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(2) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="4a92b-116">В этот раз в результате также будет возвращена Mary, являющаяся подчиненной David, и находящаяся на два уровня ниже.</span><span class="sxs-lookup"><span data-stu-id="4a92b-116">This time, you also receive Mary who also reports to David, two levels down.</span></span>  
  
### <a name="to-use-getroot-and-getlevel"></a><span data-ttu-id="4a92b-117">Использование методов GetRoot и GetLevel</span><span class="sxs-lookup"><span data-stu-id="4a92b-117">To use GetRoot, and GetLevel</span></span>  
  
1.  <span data-ttu-id="4a92b-118">По мере роста иерархии становится труднее определять положение в ней ее членов.</span><span class="sxs-lookup"><span data-stu-id="4a92b-118">As the hierarchy grows larger it is more difficult to determine where the members are in the hierarchy.</span></span> <span data-ttu-id="4a92b-119">Можно использовать метод [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) для определения того, как глубоко по уровням находится каждая строка в иерархии.</span><span class="sxs-lookup"><span data-stu-id="4a92b-119">Use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to find how many levels down each row is in the hierarchy.</span></span> <span data-ttu-id="4a92b-120">Выполните следующий код, чтобы увидеть уровни всех строк:</span><span class="sxs-lookup"><span data-stu-id="4a92b-120">Execute the following code to view the levels of all the rows:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode.GetLevel() AS EmpLevel, *  
    FROM HumanResources.EmployeeOrg ;  
    GO  
  
    ```  
  
2.  <span data-ttu-id="4a92b-121">Используйте метод [GetRoot](/sql/t-sql/data-types/getroot-database-engine) для нахождения корневого узла в иерархии.</span><span class="sxs-lookup"><span data-stu-id="4a92b-121">Use the [GetRoot](/sql/t-sql/data-types/getroot-database-engine) method to find the root node in the hierarchy.</span></span> <span data-ttu-id="4a92b-122">Следующий код возвращает единственную строку, являющуюся корневым узлом:</span><span class="sxs-lookup"><span data-stu-id="4a92b-122">The following code returns the single row which is the root:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode = hierarchyid::GetRoot() ;  
    GO  
  
    ```  
  
 <span data-ttu-id="4a92b-123">Следующая задача проведет реорганизацию иерархии.</span><span class="sxs-lookup"><span data-stu-id="4a92b-123">The next task will reorganize the hierarchy.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4a92b-124">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="4a92b-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4a92b-125">Переупорядочение данных в иерархической таблице с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="4a92b-125">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
