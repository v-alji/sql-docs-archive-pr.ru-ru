---
title: Занятие 1. Преобразование таблицы в иерархическую структуру | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 5ee6f19a-6dd7-4730-a91c-bbed1bd77e0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 196a546093786f9be4b88536763b3150ae750f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749692"
---
# <a name="lesson-1-converting-a-table-to-a-hierarchical-structure"></a><span data-ttu-id="195e5-102">Урок 1. преобразование таблицы в иерархическую структуру</span><span class="sxs-lookup"><span data-stu-id="195e5-102">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>
  <span data-ttu-id="195e5-103">Если у клиентов имеются таблицы, в которых для выражения иерархических связей используются самосоединения, то эти таблицы можно преобразовать в иерархическую структуру, руководствуясь указаниями из данного занятия.</span><span class="sxs-lookup"><span data-stu-id="195e5-103">Customers who have tables using self joins to express hierarchical relationships can convert their tables to a hierarchical structure using this lesson as a guide.</span></span> <span data-ttu-id="195e5-104">Миграция от старого метода представления к методу представления, использующему тип данных `hierarchyid`, проходит относительно легко.</span><span class="sxs-lookup"><span data-stu-id="195e5-104">It is relatively easy to migrate from this representation to one using `hierarchyid`.</span></span> <span data-ttu-id="195e5-105">После миграции пользователи получат компактное и легкое для понимания иерархическое представление, которое может быть проиндексировано несколькими способами для обеспечения эффективного поиска.</span><span class="sxs-lookup"><span data-stu-id="195e5-105">After migration, users will have a compact and easy to understand hierarchical representation, which can be indexed in several ways for efficient queries.</span></span>  
  
 <span data-ttu-id="195e5-106">В этом занятии происходит изучение существующей таблицы, создание новой таблицы, содержащей столбец `hierarchyid`, заполнение этой таблицы данными из таблицы источника, а также проводится демонстрация трех стратегий индексирования.</span><span class="sxs-lookup"><span data-stu-id="195e5-106">This lesson, examines an existing table, creates a new table containing a `hierarchyid` column, populates the table with the data from the source table, and then demonstrates three indexing strategies.</span></span> <span data-ttu-id="195e5-107">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="195e5-107">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="195e5-108">Изучение текущей структуры таблицы сотрудников</span><span class="sxs-lookup"><span data-stu-id="195e5-108">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
-   [<span data-ttu-id="195e5-109">Заполнение таблицы существующими иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="195e5-109">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
-   [<span data-ttu-id="195e5-110">Оптимизация таблицы NewOrg</span><span class="sxs-lookup"><span data-stu-id="195e5-110">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
-   [<span data-ttu-id="195e5-111">Сводка. Преобразование таблицы в иерархическую структуру</span><span class="sxs-lookup"><span data-stu-id="195e5-111">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
## <a name="prerequisites"></a><span data-ttu-id="195e5-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="195e5-112">Prerequisites</span></span>  
 <span data-ttu-id="195e5-113">Для этого занятия требуется образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="195e5-113">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="195e5-114">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="195e5-114">Next Task in Lesson</span></span>  
 [<span data-ttu-id="195e5-115">Изучение текущей структуры таблицы сотрудников</span><span class="sxs-lookup"><span data-stu-id="195e5-115">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="195e5-116">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="195e5-116">Next Lesson</span></span>  
 [<span data-ttu-id="195e5-117">Урок 2. Создание данных и управление ими в иерархической таблице</span><span class="sxs-lookup"><span data-stu-id="195e5-117">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
  
  
