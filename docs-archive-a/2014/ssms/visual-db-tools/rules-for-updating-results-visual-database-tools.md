---
title: Правила обновления результатов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- updating query results
- Query Designer [SQL Server], Results pane
- Results pane
ms.assetid: de131ef0-ccbd-446f-9400-b93c7b8fa537
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc6befc6571f29be95b176f8de6d7dcfaed9108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734869"
---
# <a name="rules-for-updating-results-visual-database-tools"></a><span data-ttu-id="adef8-102">Правила обновления результатов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="adef8-102">Rules for Updating Results (Visual Database Tools)</span></span>
  <span data-ttu-id="adef8-103">В большинстве случаев результирующий набор, отображенный на [панели результатов](visual-database-tools.md), можно обновить.</span><span class="sxs-lookup"><span data-stu-id="adef8-103">In many cases, you can update the result set displayed in the [Results Pane](visual-database-tools.md).</span></span> <span data-ttu-id="adef8-104">Однако в некоторых случаях этого сделать нельзя.</span><span class="sxs-lookup"><span data-stu-id="adef8-104">However, in some cases you cannot.</span></span>  
  
 <span data-ttu-id="adef8-105">Обычно для обновления результатов [конструктор запросов и представлений](query-and-view-designer-tools-visual-database-tools.md) должен иметь достаточно сведений, чтобы однозначно идентифицировать строку в таблице.</span><span class="sxs-lookup"><span data-stu-id="adef8-105">In general, in order to update results, the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) must have sufficient information to uniquely identify the row in the table.</span></span> <span data-ttu-id="adef8-106">Например, если запрос включает в выходном списке первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="adef8-106">An example is if the query includes a primary key in the output list.</span></span> <span data-ttu-id="adef8-107">К тому же необходимо иметь разрешение на обновление базы данных.</span><span class="sxs-lookup"><span data-stu-id="adef8-107">In addition, you must have sufficient permission to update the database.</span></span>  
  
 <span data-ttu-id="adef8-108">Если запрос основан на представлении, его также можно будет обновить.</span><span class="sxs-lookup"><span data-stu-id="adef8-108">If your query is based on a view, you might be able to update it.</span></span> <span data-ttu-id="adef8-109">Здесь действуют те же правила, за исключением того, что они применяются не к представлению, а к его базовым таблицам.</span><span class="sxs-lookup"><span data-stu-id="adef8-109">The same guidelines apply, except that they apply to the underlying tables in the view, not just to the view itself.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="adef8-110">Конструктор запросов и представлений не может заранее определить, можно ли обновить результирующий набор, основанный на представлении.</span><span class="sxs-lookup"><span data-stu-id="adef8-110">The Query and View Designer cannot determine in advance whether you can update a result set based on a view.</span></span> <span data-ttu-id="adef8-111">Поэтому он отображает все представления независимо от того, можно их обновлять или нет.</span><span class="sxs-lookup"><span data-stu-id="adef8-111">Therefore, it displays all views, even though you might not be able to update them.</span></span>  
  
 <span data-ttu-id="adef8-112">В следующей таблице собраны экземпляры, в которых возможно или невозможно обновление результатов запросов на панели результатов.</span><span class="sxs-lookup"><span data-stu-id="adef8-112">The following table summarizes specific instances in which you might and might not be able to update query results in the Results pane.</span></span> <span data-ttu-id="adef8-113">В большинстве случаев возможность или невозможность обновления результатов запросов определяет используемая база данных.</span><span class="sxs-lookup"><span data-stu-id="adef8-113">In many cases, the database you are using dictates whether you can update query results.</span></span>  
  
|<span data-ttu-id="adef8-114">Запрос</span><span class="sxs-lookup"><span data-stu-id="adef8-114">Query</span></span>|<span data-ttu-id="adef8-115">Можно ли обновить результаты?</span><span class="sxs-lookup"><span data-stu-id="adef8-115">Can results be updated?</span></span>|  
|-----------|-----------------------------|  
|<span data-ttu-id="adef8-116">Запрос, основанный на одной таблице с первичным ключом в выходном списке</span><span class="sxs-lookup"><span data-stu-id="adef8-116">Query based on one table with primary key in the output list</span></span>|<span data-ttu-id="adef8-117">Да (кроме перечисленного ниже).</span><span class="sxs-lookup"><span data-stu-id="adef8-117">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="adef8-118">Запрос, основанный на таблице без уникального индекса и первичного ключа</span><span class="sxs-lookup"><span data-stu-id="adef8-118">Query based on a table with no unique index and without a primary key</span></span>|<span data-ttu-id="adef8-119">Зависит от запроса и базы данных.</span><span class="sxs-lookup"><span data-stu-id="adef8-119">Depends on query and database.</span></span> <span data-ttu-id="adef8-120">Некоторые базы данных позволяют производить обновления, если имеется достаточно сведений для однозначной идентификации записей.</span><span class="sxs-lookup"><span data-stu-id="adef8-120">Some databases allow updates if sufficient information is available to uniquely identify records.</span></span>|  
|<span data-ttu-id="adef8-121">Запрос, основанный на нескольких несоединенных таблицах</span><span class="sxs-lookup"><span data-stu-id="adef8-121">Query based on multiple tables which are not joined</span></span>|<span data-ttu-id="adef8-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="adef8-122">No.</span></span>|  
|<span data-ttu-id="adef8-123">Запрос, основанный на данных, помеченных в базе данных, как предназначенные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="adef8-123">Query based on data marked as read-only in the database</span></span>|<span data-ttu-id="adef8-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="adef8-124">No.</span></span>|  
|<span data-ttu-id="adef8-125">Запрос, основанный на представлении, включающее в себя одну таблицу без ограничений</span><span class="sxs-lookup"><span data-stu-id="adef8-125">Query based on a view that involves one table with no constraints</span></span>|<span data-ttu-id="adef8-126">Да (кроме перечисленного ниже).</span><span class="sxs-lookup"><span data-stu-id="adef8-126">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="adef8-127">Запрос, основанный на таблицах, соединенных связью «один к одному»</span><span class="sxs-lookup"><span data-stu-id="adef8-127">Query based on tables joined with a one-to-one relationship</span></span>|<span data-ttu-id="adef8-128">Да (кроме перечисленного ниже).</span><span class="sxs-lookup"><span data-stu-id="adef8-128">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="adef8-129">Запрос, основанный на таблицах, соединенных связью «один ко многим»</span><span class="sxs-lookup"><span data-stu-id="adef8-129">Query based on tables joined with a one-to-many relationship</span></span>|<span data-ttu-id="adef8-130">Обычно.</span><span class="sxs-lookup"><span data-stu-id="adef8-130">Usually.</span></span>|  
|<span data-ttu-id="adef8-131">Запрос, основанный на трех или более таблицах со связью «многие ко многим»</span><span class="sxs-lookup"><span data-stu-id="adef8-131">Query based on three or more tables in which there is a many-to-many relationship</span></span>|<span data-ttu-id="adef8-132">Нет.</span><span class="sxs-lookup"><span data-stu-id="adef8-132">No.</span></span>|  
|<span data-ttu-id="adef8-133">Запрос, основанный на таблице, для которой не предоставлено разрешение на обновление</span><span class="sxs-lookup"><span data-stu-id="adef8-133">Query based on a table for which update permission is not granted</span></span>|<span data-ttu-id="adef8-134">Может удалить, но не обновить.</span><span class="sxs-lookup"><span data-stu-id="adef8-134">Can delete but not update.</span></span>|  
|<span data-ttu-id="adef8-135">Запрос, основанный на таблице, для которой не предоставлено разрешение на удаление</span><span class="sxs-lookup"><span data-stu-id="adef8-135">Query based on a table for which delete permission is not granted</span></span>|<span data-ttu-id="adef8-136">Может обновить, но не удалить.</span><span class="sxs-lookup"><span data-stu-id="adef8-136">Can update but not delete.</span></span>|  
|<span data-ttu-id="adef8-137">Статистический запрос</span><span class="sxs-lookup"><span data-stu-id="adef8-137">Aggregate query</span></span>|<span data-ttu-id="adef8-138">Нет.</span><span class="sxs-lookup"><span data-stu-id="adef8-138">No.</span></span>|  
|<span data-ttu-id="adef8-139">Запрос, основанный на вложенном запросе, содержащем итоги или агрегатные функции</span><span class="sxs-lookup"><span data-stu-id="adef8-139">Query based on a subquery that contains totals or aggregate functions</span></span>|<span data-ttu-id="adef8-140">Нет.</span><span class="sxs-lookup"><span data-stu-id="adef8-140">No.</span></span>|  
|<span data-ttu-id="adef8-141">Запрос, который содержит ключевое слово DISTINCT для исключения повторяющихся строк</span><span class="sxs-lookup"><span data-stu-id="adef8-141">Query that includes the DISTINCT keyword to exclude duplicate rows</span></span>|<span data-ttu-id="adef8-142">Нет.</span><span class="sxs-lookup"><span data-stu-id="adef8-142">No.</span></span>|  
|<span data-ttu-id="adef8-143">Запрос, предложение FROM которого содержит определяемую пользователем функцию, возвращающую таблицу и определяемую пользователем функцию, содержащую несколько выбранных инструкций</span><span class="sxs-lookup"><span data-stu-id="adef8-143">Query whose FROM clause includes a user-defined function that returns a table and the user-defined function contains multiple select statements</span></span>|<span data-ttu-id="adef8-144">Нет.</span><span class="sxs-lookup"><span data-stu-id="adef8-144">No.</span></span>|  
|<span data-ttu-id="adef8-145">Запрос, предложение FROM которого содержит встроенную определяемую пользователем функцию</span><span class="sxs-lookup"><span data-stu-id="adef8-145">Query whose FROM clause includes an inline user-defined function</span></span>|<span data-ttu-id="adef8-146">Да.</span><span class="sxs-lookup"><span data-stu-id="adef8-146">Yes.</span></span>|  
  
 <span data-ttu-id="adef8-147">Дополнительно в результатах запросов невозможно будет обновить указанные столбцы.</span><span class="sxs-lookup"><span data-stu-id="adef8-147">In addition, you might not be able to update specific columns in the query results.</span></span> <span data-ttu-id="adef8-148">В следующем списке собраны типы столбцов, которые не могут быть обновлены на панели результатов:</span><span class="sxs-lookup"><span data-stu-id="adef8-148">The following list summarizes specific types of columns that you cannot update in the Results pane.</span></span>  
  
-   <span data-ttu-id="adef8-149">столбцы, основанные на выражениях;</span><span class="sxs-lookup"><span data-stu-id="adef8-149">Columns based on expressions</span></span>  
  
-   <span data-ttu-id="adef8-150">столбцы, основанные на скалярной определяемой пользователем функции;</span><span class="sxs-lookup"><span data-stu-id="adef8-150">Columns based on scalar user-defined functions</span></span>  
  
-   <span data-ttu-id="adef8-151">строки или столбцы, удаленные другим пользователем;</span><span class="sxs-lookup"><span data-stu-id="adef8-151">Rows or columns deleted by another user</span></span>  
  
-   <span data-ttu-id="adef8-152">строки и столбцы, заблокированные другим пользователем (заблокированные строки обычно могут обновляться сразу же после разблокировки);</span><span class="sxs-lookup"><span data-stu-id="adef8-152">Rows or columns locked by another user (locked rows can usually be updated as soon as they are unlocked)</span></span>  
  
-   <span data-ttu-id="adef8-153">столбцы типа Timestamp или BLOB.</span><span class="sxs-lookup"><span data-stu-id="adef8-153">Timestamp or BLOB columns</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adef8-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="adef8-154">See Also</span></span>  
 [<span data-ttu-id="adef8-155">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="adef8-155">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
