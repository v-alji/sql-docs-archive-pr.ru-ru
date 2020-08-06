---
title: Диалоговое окно «Добавление таблицы» (конструкторы запросов и представлений) (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.query.addtable
- vdtsql.chm:65565
ms.assetid: fce7adcc-4cf5-4a52-9203-11c13d1ecf08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d7bf30cbdd37927735c36f184208a1ded957763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657468"
---
# <a name="add-table-dialog-box-query-and-view-designers-visual-database-tools"></a><span data-ttu-id="e06a2-102">Диалоговое окно «Добавить таблицу» (конструкторы запросов и представлений) (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e06a2-102">Add Table Dialog Box (Query and View Designers) (Visual Database Tools)</span></span>
  <span data-ttu-id="e06a2-103">Это диалоговое окно позволяет добавлять таблицы, представления, определяемые пользователем функции или синонимы к запросу или представлению.</span><span class="sxs-lookup"><span data-stu-id="e06a2-103">This dialog box lets you add tables, views, user-defined functions, or synonyms to a query or view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e06a2-104">Если таблица опубликована для репликации, то изменения схемы следует проводить при помощи инструкции языка Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) или объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="e06a2-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="e06a2-105">При изменении схемы с помощью конструктора таблиц или конструктора диаграмм баз данных конструктор пытается удалить и затем вновь создать таблицу.</span><span class="sxs-lookup"><span data-stu-id="e06a2-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="e06a2-106">Но поскольку удалять опубликованные объекты нельзя, изменения схемы не будут применены.</span><span class="sxs-lookup"><span data-stu-id="e06a2-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e06a2-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e06a2-107">Options</span></span>  
 <span data-ttu-id="e06a2-108">**Таблицы**</span><span class="sxs-lookup"><span data-stu-id="e06a2-108">**Tables**</span></span>  
 <span data-ttu-id="e06a2-109">Перечисляет таблицы, которые можно добавить на панель **Диаграмма** .</span><span class="sxs-lookup"><span data-stu-id="e06a2-109">Lists the tables you can add to the **Diagram** pane.</span></span> <span data-ttu-id="e06a2-110">Чтобы добавить таблицу, выделите ее и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e06a2-110">To add a table, select it and click **Add**.</span></span> <span data-ttu-id="e06a2-111">Чтобы добавить сразу несколько таблиц, выделите их и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e06a2-111">To add several tables at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="e06a2-112">**Представления**</span><span class="sxs-lookup"><span data-stu-id="e06a2-112">**Views**</span></span>  
 <span data-ttu-id="e06a2-113">Перечисляет представления, которые можно добавить на панель **Диаграмма** .</span><span class="sxs-lookup"><span data-stu-id="e06a2-113">Lists the views you can add to the **Diagram** pane.</span></span> <span data-ttu-id="e06a2-114">Чтобы добавить представление, выделите его и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e06a2-114">To add a view, select it and click **Add**.</span></span> <span data-ttu-id="e06a2-115">Чтобы добавить сразу несколько представлений, выделите их и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e06a2-115">To add several views at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="e06a2-116">**Функции**</span><span class="sxs-lookup"><span data-stu-id="e06a2-116">**Functions**</span></span>  
 <span data-ttu-id="e06a2-117">Перечисляет определяемые пользователем функции, которые можно добавить на панель **Диаграмма** .</span><span class="sxs-lookup"><span data-stu-id="e06a2-117">Lists the user-defined functions you can add to the **Diagram** pane.</span></span> <span data-ttu-id="e06a2-118">Чтобы добавить функцию, выделите ее и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e06a2-118">To add a function, select it and click **Add**.</span></span> <span data-ttu-id="e06a2-119">Чтобы выделить сразу несколько функций, выделите их и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e06a2-119">To add several functions at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="e06a2-120">**Синонимы**</span><span class="sxs-lookup"><span data-stu-id="e06a2-120">**Synonyms**</span></span>  
 <span data-ttu-id="e06a2-121">Перечисляет синонимы, которые можно добавить на панель **Диаграмма** .</span><span class="sxs-lookup"><span data-stu-id="e06a2-121">Lists the synonyms you can add to the **Diagram** pane.</span></span> <span data-ttu-id="e06a2-122">Чтобы добавить синоним, выделите его и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e06a2-122">To add a synonym, select it and click **Add**.</span></span> <span data-ttu-id="e06a2-123">Чтобы добавить сразу несколько синонимов, выделите их и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e06a2-123">To add several synonyms at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="e06a2-124">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="e06a2-124">**Refresh**</span></span>  
 <span data-ttu-id="e06a2-125">Обновление списка включением в него всех изменений, произведенных в базе данных с момента последнего извлечения списка.</span><span class="sxs-lookup"><span data-stu-id="e06a2-125">Update the list to include any changes made to the database since the list was last retrieved.</span></span>  
  
 <span data-ttu-id="e06a2-126">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="e06a2-126">**Add**</span></span>  
 <span data-ttu-id="e06a2-127">Добавить выбранный элемент или элементы.</span><span class="sxs-lookup"><span data-stu-id="e06a2-127">Add the selected item or items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e06a2-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="e06a2-128">See Also</span></span>  
 [<span data-ttu-id="e06a2-129">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e06a2-129">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
