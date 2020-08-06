---
title: Создание таблицы с помощью типа данных hierarchyid | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 0d1f361f-336c-4571-99d1-f4813b2d9fc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2c9b59795949e11cabd21b0be8de844b33d73c37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749687"
---
# <a name="creating-a-table-using-the-hierarchyid-data-type"></a><span data-ttu-id="595bc-102">Создание таблицы с помощью типа данных hierarchyid</span><span class="sxs-lookup"><span data-stu-id="595bc-102">Creating a Table Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="595bc-103">В следующем примере создается таблица EmployeeOrg, включающая данные о сотрудниках и их иерархическом подчинении.</span><span class="sxs-lookup"><span data-stu-id="595bc-103">The following example creates a table named EmployeeOrg, which includes employee data together with their reporting hierarchy.</span></span> <span data-ttu-id="595bc-104">В этом примере в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] создается таблица (что не обязательно).</span><span class="sxs-lookup"><span data-stu-id="595bc-104">The example creates the table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, but that is optional.</span></span> <span data-ttu-id="595bc-105">Для простоты эта таблица содержит только 5 столбцов.</span><span class="sxs-lookup"><span data-stu-id="595bc-105">To keep the example simple, this table includes only five columns:</span></span>  
  
-   <span data-ttu-id="595bc-106">OrgNode — это столбец типа `hierarchyid`, в котором хранятся иерархические связи.</span><span class="sxs-lookup"><span data-stu-id="595bc-106">OrgNode is a `hierarchyid` column that stores the hierarchical relationship.</span></span>  
  
-   <span data-ttu-id="595bc-107">OrgLevel — это вычисляемый столбец, основанный на столбце OrgNode, в котором хранятся данные об уровне каждого узла в иерархии.</span><span class="sxs-lookup"><span data-stu-id="595bc-107">OrgLevel is a computed column, based on the OrgNode column that stores each nodes level in the hierarchy.</span></span> <span data-ttu-id="595bc-108">Эти данные будут использоваться для создания индекса по ширине.</span><span class="sxs-lookup"><span data-stu-id="595bc-108">It will be used for a breadth-first index.</span></span>  
  
-   <span data-ttu-id="595bc-109">Столбец EmployeeID содержит типичные идентификационные номера сотрудников, которые используются для таких задач, как расчет заработной платы.</span><span class="sxs-lookup"><span data-stu-id="595bc-109">EmployeeID contains the typical employee identification number that is used for applications such as payroll.</span></span> <span data-ttu-id="595bc-110">Новые приложения могут использовать столбец OrgNode, и этот отдельный столбец EmployeeID не требуется.</span><span class="sxs-lookup"><span data-stu-id="595bc-110">In new application development, applications can use the OrgNode column and this separate EmployeeID column is not needed.</span></span>  
  
-   <span data-ttu-id="595bc-111">Столбец EmpName содержит имя сотрудника.</span><span class="sxs-lookup"><span data-stu-id="595bc-111">EmpName contains the name of the employee.</span></span>  
  
-   <span data-ttu-id="595bc-112">Столбец Title содержит должность сотрудника.</span><span class="sxs-lookup"><span data-stu-id="595bc-112">Title contains the title of the employee.</span></span>  
  
### <a name="to-create-the-employeeorg-table"></a><span data-ttu-id="595bc-113">Создание таблицы «EmployeeOrg»</span><span class="sxs-lookup"><span data-stu-id="595bc-113">To create the EmployeeOrg table</span></span>  
  
1.  <span data-ttu-id="595bc-114">В окне редактора запросов выполните следующий программный код, чтобы создать таблицу `EmployeeOrg` .</span><span class="sxs-lookup"><span data-stu-id="595bc-114">In a Query Editor window, run the following code to create the `EmployeeOrg` table.</span></span> <span data-ttu-id="595bc-115">Если задать столбец `OrgNode` в качестве первичного ключа кластеризованного индекса, создается индекс по глубине:</span><span class="sxs-lookup"><span data-stu-id="595bc-115">Specifying the `OrgNode` column as the primary key with a clustered index will create a depth-first index:</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    CREATE TABLE HumanResources.EmployeeOrg  
    (  
       OrgNode hierarchyid PRIMARY KEY CLUSTERED,  
       OrgLevel AS OrgNode.GetLevel(),  
       EmployeeID int UNIQUE NOT NULL,  
       EmpName varchar(20) NOT NULL,  
       Title varchar(20) NULL  
    ) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="595bc-116">Чтобы создать составной индекс по столбцам `OrgLevel` и `OrgNode` для эффективного поиска в ширину, выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="595bc-116">Run the following code to create a composite index on the `OrgLevel` and `OrgNode` columns to support efficient breadth-first searches:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmployeeOrgNc1   
    ON HumanResources.EmployeeOrg(OrgLevel, OrgNode) ;  
    GO  
    ```  
  
 <span data-ttu-id="595bc-117">Таблица готова для записи данных.</span><span class="sxs-lookup"><span data-stu-id="595bc-117">The table is now ready for data.</span></span> <span data-ttu-id="595bc-118">В результате выполнения следующего задания таблица будет заполнена данными с применением иерархических методов.</span><span class="sxs-lookup"><span data-stu-id="595bc-118">The next task will populate the table by using hierarchical methods.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="595bc-119">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="595bc-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="595bc-120">Заполнение иерархической таблицы с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="595bc-120">Populating a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-2-populating-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
