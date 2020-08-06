---
title: Создание псевдонимов таблиц (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table aliases [SQL Server]
- aliases [SQL Server], tables
ms.assetid: 49e61e85-8abf-4ca7-8c70-7e9f8f1078bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f9e6269fe6e24e8d98922094e799fbf4b5af584
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665210"
---
# <a name="create-table-aliases-visual-database-tools"></a><span data-ttu-id="fb311-102">Создание псевдонимов таблицы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="fb311-102">Create Table Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="fb311-103">Псевдонимы облегчают работу с именами таблиц.</span><span class="sxs-lookup"><span data-stu-id="fb311-103">Aliases can make it easier to work with table names.</span></span> <span data-ttu-id="fb311-104">Использование псевдонимов полезно в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="fb311-104">Using aliases is helpful when:</span></span>  
  
-   <span data-ttu-id="fb311-105">Нужно сделать инструкцию на [панели SQL](visual-database-tools.md) более короткой и удобочитаемой.</span><span class="sxs-lookup"><span data-stu-id="fb311-105">You want to make the statement in the [SQL Pane](visual-database-tools.md) shorter and easier to read.</span></span>  
  
-   <span data-ttu-id="fb311-106">Запрос часто ссылается на имя таблицы (например, на квалификаторы имен столбцов), и при этом нужно сохранить определенную длину запроса.</span><span class="sxs-lookup"><span data-stu-id="fb311-106">You refer to the table name often in your query - such as in qualifying column names - and want to be sure you stay within a specific character-length limit for your query.</span></span> <span data-ttu-id="fb311-107">(В некоторых базах данных имеется ограничение на длину запроса).</span><span class="sxs-lookup"><span data-stu-id="fb311-107">(Some databases impose a maximum length for queries.)</span></span>  
  
-   <span data-ttu-id="fb311-108">Обрабатывается несколько экземпляров одной таблицы (например при самосоединении), и нужно иметь возможность ссылаться на тот или иной экземпляр.</span><span class="sxs-lookup"><span data-stu-id="fb311-108">You are working with multiple instances of the same table (such as in a self-join) and need a way to refer to one instance or the other.</span></span>  
  
 <span data-ttu-id="fb311-109">Например можно создать псевдоним `"e"` для имени таблицы `employee`_`information`, а затем ссылаться на нее, как `"e"` , по всему запросу.</span><span class="sxs-lookup"><span data-stu-id="fb311-109">For example, you can create an alias `"e"` for a table name `employee`_`information`, and then refer to the table as `"e"` throughout the rest of the query.</span></span>  
  
### <a name="to-create-an-alias-for-a-table-or-table-valued-object"></a><span data-ttu-id="fb311-110">Создание псевдонима таблицы или возвращающего табличное значение объекта</span><span class="sxs-lookup"><span data-stu-id="fb311-110">To create an alias for a table or table-valued object</span></span>  
  
1.  <span data-ttu-id="fb311-111">Добавьте таблицу или возвращающий табличное значение объект к запросу.</span><span class="sxs-lookup"><span data-stu-id="fb311-111">Add the table or table-valued object to your query.</span></span>  
  
2.  <span data-ttu-id="fb311-112">На **панели диаграммы**щелкните правой кнопкой нужный объект и выберите пункт **Свойства** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="fb311-112">In the **Diagram Pane**, right-click the object for which you want to create an alias, then select **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="fb311-113">В окне **Свойства** введите псевдоним в поле **Псевдоним** .</span><span class="sxs-lookup"><span data-stu-id="fb311-113">In the **Properties** window, enter the alias in the **Alias** field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb311-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb311-114">See Also</span></span>  
 <span data-ttu-id="fb311-115">[Добавление таблиц в запросы &#40;визуальных инструментов для баз данных&#41;](add-tables-to-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fb311-115">[Add Tables to Queries &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fb311-116">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fb311-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fb311-117">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fb311-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fb311-118">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="fb311-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
