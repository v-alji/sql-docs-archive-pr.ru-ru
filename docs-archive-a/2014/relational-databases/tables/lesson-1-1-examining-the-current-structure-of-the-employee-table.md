---
title: Изучение текущей структуры таблицы сотрудников | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- examining the current structure of the employee
ms.assetid: d546a820-105a-417d-ac35-44a6d1d70ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7f63773ebc1f28fb24f8f1000c3f87ee4d50544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654112"
---
# <a name="examining-the-current-structure-of-the-employee-table"></a><span data-ttu-id="72189-102">Изучение текущей структуры таблицы сотрудников</span><span class="sxs-lookup"><span data-stu-id="72189-102">Examining the Current Structure of the Employee Table</span></span>
  <span data-ttu-id="72189-103"> Образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] содержит таблицу **Employee** в схеме **HumanResources**.</span><span class="sxs-lookup"><span data-stu-id="72189-103">The sample [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database contains an **Employee** table in the **HumanResources** schema.</span></span> <span data-ttu-id="72189-104">Чтобы не изменять исходную таблицу, на этом шаге создается копия таблицы **Employee** , называющаяся **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="72189-104">To avoid changing the original table, this step makes a copy of the **Employee** table named **EmployeeDemo**.</span></span> <span data-ttu-id="72189-105">Для упрощения этого примера копируется только пять столбцов из исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="72189-105">To simplify the example, you only copy five columns from the original table.</span></span> <span data-ttu-id="72189-106">Затем вы запрашиваете таблицу **HumanResources. EmployeeDemo** , чтобы узнать, как структурированы данные в таблице, не используя `hierarchyid` тип данных.</span><span class="sxs-lookup"><span data-stu-id="72189-106">Then, you query the **HumanResources.EmployeeDemo** table to review how the data is structured in a table without using the `hierarchyid` data type.</span></span>  
  
### <a name="to-copy-the-employee-table"></a><span data-ttu-id="72189-107">Копирование таблицы Employee</span><span class="sxs-lookup"><span data-stu-id="72189-107">To copy the Employee table</span></span>  
  
1.  <span data-ttu-id="72189-108">Запустите следующий код в окне редактора запросов, чтобы скопировать структуру и данные таблицы **Employee** в новую таблицу **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="72189-108">In a Query Editor window, run the following code to copy the table structure and data from the **Employee** table into a new table named **EmployeeDemo**.</span></span>  
  
    ```  
    USE AdventureWorks ;  
    GO  
  
    SELECT EmployeeID, LoginID, ManagerID, Title, HireDate   
    INTO HumanResources.EmployeeDemo   
    FROM HumanResources.Employee ;  
    GO  
    ```  
  
### <a name="to-examine-the-structure-and-data-of-the-employeedemo-table"></a><span data-ttu-id="72189-109">Изучение структуры и данных таблицы EmployeeDemo</span><span class="sxs-lookup"><span data-stu-id="72189-109">To examine the structure and data of the EmployeeDemo table</span></span>  
  
-   <span data-ttu-id="72189-110">Новая таблица **EmployeeDemo** представляет собой типичный пример таблицы в существующей базе данных, которую можно подвергнуть миграции в новую структуру.</span><span class="sxs-lookup"><span data-stu-id="72189-110">This new **EmployeeDemo** table represents a typical table in an existing database that you might want to migrate to a new structure.</span></span> <span data-ttu-id="72189-111">Запустите следующий код в окне редактора запросов, чтобы увидеть, как таблица использует самосоединение для отображения связей сотрудник-менеджер.</span><span class="sxs-lookup"><span data-stu-id="72189-111">In a Query Editor window, run the following code to show how the table uses a self join to display the employee/manager relationships:</span></span>  
  
    ```  
    SELECT   
         Mgr.EmployeeID AS MgrID, Mgr.LoginID AS Manager,   
         Emp.EmployeeID AS E_ID, Emp.LoginID, Emp.Title  
    FROM HumanResources.EmployeeDemo AS Emp  
    LEFT JOIN HumanResources.EmployeeDemo AS Mgr  
    ON Emp.ManagerID = Mgr.EmployeeID  
    ORDER BY MgrID, E_ID  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    MgrID Manager                 E_ID LoginID                  Title  
    NULL NULL                      109 adventure-works\ken0     Chief Executive Officer  
    3    adventure-works\roberto0  4   adventure-works\rob0     Senior Tool Designer  
    3    adventure-works\roberto0  9   adventure-works\gail0    Design Engineer  
    3    adventure-works\roberto0  11  adventure-works\jossef0  Design Engineer  
    3    adventure-works\roberto0  158 adventure-works\dylan0   Research and Development Manager  
    3    adventure-works\roberto0  263 adventure-works\ovidiu0  Senior Tool Designer  
    3    adventure-works\roberto0  267 adventure-works\michael8 Senior Design Engineer  
    3    adventure-works\roberto0  270 adventure-works\sharon0  Design Engineer  
    6    adventure-works\david0    2   adventure-works\kevin0   Marketing Assistant  
    ...  
    ```  
  
     <span data-ttu-id="72189-112">Получаемый в результате набор содержит 290 строк.</span><span class="sxs-lookup"><span data-stu-id="72189-112">The results continue for a total of 290 rows.</span></span>  
  
 <span data-ttu-id="72189-113">Обратите внимание, что использование предложения `ORDER BY` приводит к тому, что прямые подчиненные каждого уровня управления будут находиться вместе.</span><span class="sxs-lookup"><span data-stu-id="72189-113">Notice that the `ORDER BY` clause caused the output to list the direct reports of each management level together.</span></span> <span data-ttu-id="72189-114">Например, все семь прямых подчиненных уровня **MgrID** 3 (roberto0) перечисляются вместе.</span><span class="sxs-lookup"><span data-stu-id="72189-114">For instance, all seven of the direct reports of **MgrID** 3 (roberto0) are listed adjacent to each other.</span></span> <span data-ttu-id="72189-115">Сгруппировать всех косвенных подчиненных уровня **MgrID** 3 тоже возможно, хотя это гораздо сложнее.</span><span class="sxs-lookup"><span data-stu-id="72189-115">Although not impossible, it is much more difficult to group all those who eventually report to **MgrID** 3.</span></span>  
  
 <span data-ttu-id="72189-116">В следующей задаче мы создадим новую таблицу с типом данных `hierarchyid` и переместим в нее данные.</span><span class="sxs-lookup"><span data-stu-id="72189-116">In the next task, we will create a new table with a `hierarchyid` data type, and move the data into the new table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="72189-117">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="72189-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="72189-118">Заполнение таблицы существующими иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="72189-118">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
  
