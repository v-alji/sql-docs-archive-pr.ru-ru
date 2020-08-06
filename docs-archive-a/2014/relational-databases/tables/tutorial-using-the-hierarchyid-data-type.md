---
title: Руководство. Использование типа данных hierarchyid | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- tutorials [hierarchyid]
- hierarchyid [Database Engine], tutorial
ms.assetid: 5a7f7cfd-7faf-439f-8085-8fd6bf7db355
author: stevestein
ms.author: sstein
ms.openlocfilehash: a735b4c2b51e1c680c8129647733ce1efd9f9984
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657625"
---
# <a name="tutorial-using-the-hierarchyid-data-type"></a><span data-ttu-id="835f2-102">Учебник. Использование типа данных hierarchyid</span><span class="sxs-lookup"><span data-stu-id="835f2-102">Tutorial: Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="835f2-103">Этот учебник предназначен для пользователей, имеющих опыт работы с [!INCLUDE[tsql](../../includes/tsql-md.md)], но незнакомых с типом данных `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="835f2-103">This tutorial is intended for users who are experienced with [!INCLUDE[tsql](../../includes/tsql-md.md)], but are new to the `hierarchyid` data type.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="835f2-104">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="835f2-104">What You Will Learn</span></span>  
 <span data-ttu-id="835f2-105">Учебник разделен на два занятия.</span><span class="sxs-lookup"><span data-stu-id="835f2-105">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="835f2-106">Занятие 1. Преобразование таблицы в иерархическую структуру</span><span class="sxs-lookup"><span data-stu-id="835f2-106">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-converting-a-table-to-a-hierarchical-structure.md)  
 <span data-ttu-id="835f2-107">На этом занятии возьмем существующую таблицу сотрудников, структурированную по иерархии «родители-потомки», и переместим данные в новую таблицу, представляющую иерархию с помощью типа данных `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="835f2-107">In this lesson, you take an existing employee table that is structured as a parent/child hierarchy and move the data into a new table that represents the hierarchy by using the `hierarchyid` data type.</span></span> <span data-ttu-id="835f2-108">Для этого занятия требуется образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="835f2-108">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [<span data-ttu-id="835f2-109">Занятие 2. Создание данных и управление ими в иерархической таблице</span><span class="sxs-lookup"><span data-stu-id="835f2-109">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
 <span data-ttu-id="835f2-110">На этом занятии создается таблица, используя тип данных `hierarchyid` для представления структуры иерархии.</span><span class="sxs-lookup"><span data-stu-id="835f2-110">In this lesson, you create a table by using the `hierarchyid` data type to represent the hierarchy structure.</span></span> <span data-ttu-id="835f2-111">Затем создаются запросы и производится управление данными с помощью иерархических методов.</span><span class="sxs-lookup"><span data-stu-id="835f2-111">Then, you manipulate the data in the table by using the hierarchical methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="835f2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="835f2-112">Requirements</span></span>  
 <span data-ttu-id="835f2-113">В системе должно быть установлено следующее.</span><span class="sxs-lookup"><span data-stu-id="835f2-113">Your system must have the following installed:</span></span>  
  
-   <span data-ttu-id="835f2-114">Любой выпуск [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="835f2-114">Any edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span>  
  
-   <span data-ttu-id="835f2-115">Среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="835f2-115">Either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span></span>  
  
-   <span data-ttu-id="835f2-116">Internet Explorer 6 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="835f2-116">Internet Explorer 6 or a later version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="835f2-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="835f2-117">See Also</span></span>  
 <span data-ttu-id="835f2-118">[Учебник. начало работы с ядро СУБД](../tutorial-getting-started-with-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="835f2-118">[Tutorial: Getting Started with the Database Engine](../tutorial-getting-started-with-the-database-engine.md) </span></span>  
 <span data-ttu-id="835f2-119">[Учебник. Написание инструкций Transact-SQL](../../t-sql/tutorial-writing-transact-sql-statements.md) </span><span class="sxs-lookup"><span data-stu-id="835f2-119">[Tutorial: Writing Transact-SQL Statements](../../t-sql/tutorial-writing-transact-sql-statements.md) </span></span>  
 <span data-ttu-id="835f2-120">[Справочник по методам типа данных hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="835f2-120">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="835f2-121">[SQL Server &#40;иерархических данных&#41;](../hierarchical-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="835f2-121">[Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md) </span></span>  
 [<span data-ttu-id="835f2-122">hierarchyid (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="835f2-122">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
