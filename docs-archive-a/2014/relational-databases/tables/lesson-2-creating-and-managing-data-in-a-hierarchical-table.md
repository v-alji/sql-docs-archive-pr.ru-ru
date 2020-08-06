---
title: Занятие 2. Создание данных и управление ими в иерархической таблице | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 95f55cff-4abb-4c08-97b3-e3ae5e8b24e2
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2cecdc768b311e53ea7f65d40737fa57477da16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654983"
---
# <a name="lesson-2-creating-and-managing-data-in-a-hierarchical-table"></a><span data-ttu-id="5a2ba-102">Урок 2. Создание данных и управление ими в иерархической таблице</span><span class="sxs-lookup"><span data-stu-id="5a2ba-102">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>
  <span data-ttu-id="5a2ba-103">В занятии 1 существующая таблица была изменена, чтобы использовать тип данных `hierarchyid`, а также столбец `hierarchyid` был заполнен представлением существующих данных.</span><span class="sxs-lookup"><span data-stu-id="5a2ba-103">In Lesson 1, you modified an existing table to use the `hierarchyid` data type, and populated the `hierarchyid` column with the representation of the existing data.</span></span> <span data-ttu-id="5a2ba-104">На этом занятии будет создана новая таблица и вставлены данные с помощью иерархических методов.</span><span class="sxs-lookup"><span data-stu-id="5a2ba-104">In this lesson, you will start with a new table, and insert data by using the hierarchical methods.</span></span> <span data-ttu-id="5a2ba-105">Затем с помощью иерархических методов будет выполнен запрос данных и показано управление данными.</span><span class="sxs-lookup"><span data-stu-id="5a2ba-105">Then, you will query and manipulate the data by using the hierarchical methods.</span></span>  
  
 <span data-ttu-id="5a2ba-106">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="5a2ba-106">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="5a2ba-107">Создание таблицы с помощью типа данных hierarchyid</span><span class="sxs-lookup"><span data-stu-id="5a2ba-107">Creating a Table Using the hierarchyid Data Type</span></span>](lesson-2-1-creating-a-table-using-the-hierarchyid-data-type.md)  
  
-   [<span data-ttu-id="5a2ba-108">Заполнение иерархической таблицы с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="5a2ba-108">Populating a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-2-populating-a-hierarchical-table-using-hierarchical-methods.md)  
  
-   [<span data-ttu-id="5a2ba-109">Создание запросов к иерархической таблице с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="5a2ba-109">Querying a Hierarchical Table Using Hierarchy Methods</span></span>](lesson-2-3-querying-a-hierarchical-table-using-hierarchy-methods.md)  
  
-   [<span data-ttu-id="5a2ba-110">Переупорядочение данных в иерархической таблице с помощью иерархических методов</span><span class="sxs-lookup"><span data-stu-id="5a2ba-110">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
-   [<span data-ttu-id="5a2ba-111">Сводка. Управление данными в иерархической таблице</span><span class="sxs-lookup"><span data-stu-id="5a2ba-111">Summary: Managing Data in a Hierarchical Table</span></span>](lesson-2-5-summary-managing-data-in-a-hierarchical-table.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5a2ba-112">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="5a2ba-112">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5a2ba-113">Создание таблицы с помощью типа данных hierarchyid</span><span class="sxs-lookup"><span data-stu-id="5a2ba-113">Creating a Table Using the hierarchyid Data Type</span></span>](lesson-2-1-creating-a-table-using-the-hierarchyid-data-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="5a2ba-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a2ba-114">See Also</span></span>  
 [<span data-ttu-id="5a2ba-115">Урок 1. Преобразование таблицы в иерархическую структуру</span><span class="sxs-lookup"><span data-stu-id="5a2ba-115">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-converting-a-table-to-a-hierarchical-structure.md)  
  
  
