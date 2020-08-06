---
title: Запросы с параметрами (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- parameter queries [SQL Server]
ms.assetid: 4897c41a-324a-47b8-a30b-cbc9e9e19a8b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f6fd94ef180a34ae91d52c213092898612dc77d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665713"
---
# <a name="parameter-queries-visual-database-tools"></a><span data-ttu-id="0a8a2-102">Запросы с параметрами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="0a8a2-102">Parameter Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="0a8a2-103">В некоторых случаях нужно создать запрос, который можно использовать многократно, на каждый раз с разными значениями.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-103">In some cases you want to create a query that you can use many times, but with a different value each time.</span></span> <span data-ttu-id="0a8a2-104">Например: можно часто запускать запрос, чтобы найти все `title_ids` , записанные одним автором,</span><span class="sxs-lookup"><span data-stu-id="0a8a2-104">For example, you might frequently run a query to find all the `title_ids` written by one author.</span></span> <span data-ttu-id="0a8a2-105">можно выполнять один запрос для каждого поиска, меняя только идентификатор автора.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-105">You could run the same query for each request, except that the author's ID or name would be different each time.</span></span>  
  
 <span data-ttu-id="0a8a2-106">Чтобы создать запрос, который в разное время может иметь разные значения, используются параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-106">To create a query that can have different values at different times, you use parameters in the query.</span></span> <span data-ttu-id="0a8a2-107">Параметр — это заполнитель для значения, которое предоставляется при запуске запроса.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-107">A parameter is a placeholder for a value that is supplied when the query runs.</span></span> <span data-ttu-id="0a8a2-108">Инструкция SQL с параметром может выглядеть следующим образом, где «?» представляет параметр для идентификатора автора:</span><span class="sxs-lookup"><span data-stu-id="0a8a2-108">An SQL statement with a parameter might look like the following, where "?" represents the parameter for the author's ID:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
## <a name="where-you-can-use-parameters"></a><span data-ttu-id="0a8a2-109">Где можно использовать параметры</span><span class="sxs-lookup"><span data-stu-id="0a8a2-109">Where You Can Use Parameters</span></span>  
 <span data-ttu-id="0a8a2-110">Параметры можно использовать как метки-заполнители для литеральных значений — текстовых или числовых.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-110">You can use parameters as placeholders for literal values - for either text or numeric values.</span></span> <span data-ttu-id="0a8a2-111">Наиболее часто параметры используются в качестве меток-заполнителей в условиях поиска отдельных строк или групп строк (то есть в предложениях WHERE и HAVING инструкций SQL).</span><span class="sxs-lookup"><span data-stu-id="0a8a2-111">Most commonly, parameters are used as placeholders in search conditions for individual rows or for groups (that is, in the WHERE or HAVING clauses of an SQL statement).</span></span>  
  
 <span data-ttu-id="0a8a2-112">Параметр можно использовать в качестве меток-заполнителей в выражениях.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-112">You can use parameters as placeholders in expressions.</span></span> <span data-ttu-id="0a8a2-113">Например можно вычислять цены со скидками, предоставляя различное значение скидки при каждом запуске запроса.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-113">For example, you might want to calculate discounted prices by supplying a different discount value each time you run a query.</span></span> <span data-ttu-id="0a8a2-114">Для этого нужно указать следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="0a8a2-114">To do so, you could specify the following expression:</span></span>  
  
```  
(price * ?)  
```  
  
## <a name="specifying-unnamed-and-named-parameters"></a><span data-ttu-id="0a8a2-115">Именованные и неименованные параметры</span><span class="sxs-lookup"><span data-stu-id="0a8a2-115">Specifying Unnamed and Named Parameters</span></span>  
 <span data-ttu-id="0a8a2-116">Можно задать два типа параметров: неименованные и именованные.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-116">You can specify two types of parameters: unnamed and named.</span></span> <span data-ttu-id="0a8a2-117">Неименованный параметр — это восклицательный знак, который можно подставлять в любое место запроса, в котором нужно запросить соответствующее литеральное значение.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-117">An unnamed parameter is a question mark (?) that you put anywhere in the query that you want to prompt for or substitute a literal value.</span></span> <span data-ttu-id="0a8a2-118">Например, если неименованный параметр используется для поиска идентификатора автора в таблице `titleauthor` , то полученная в результате инструкция на [панели SQL](visual-database-tools.md) может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0a8a2-118">For example, if you use an unnamed parameter to search for an author's id in the `titleauthor` table, the resulting statement in the [SQL Pane](visual-database-tools.md) might look like this:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
 <span data-ttu-id="0a8a2-119">При выполнении запроса в [конструкторе запросов и представлений](query-and-view-designer-tools-visual-database-tools.md)в диалоговом окне [Параметры запроса](query-parameters-dialog-box-visual-database-tools.md) появляется "?" в качестве имени параметра.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-119">When you run the query in the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md), the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with "?" as the name of the parameter.</span></span>  
  
 <span data-ttu-id="0a8a2-120">Можно также присвоить имя параметру.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-120">Alternatively, you can assign a name to a parameter.</span></span> <span data-ttu-id="0a8a2-121">Именованные параметры особенно полезны, если в запросе имеется несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-121">Named parameters are particularly useful if you have multiple parameters in a query.</span></span> <span data-ttu-id="0a8a2-122">Например, если именованный параметр используется для поиска имени и фамилии автора в таблице `authors` , то полученная в результате инструкция на панели «SQL» может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0a8a2-122">For example, if you use named parameters to search for an author's first and last names in the `authors` table, the resulting statement in the SQL pane might look like this:</span></span>  
  
```  
SELECT au_id  
FROM authors  
WHERE au_fname = %first name% AND  
      au_lname = %last name%  
```  
  
> [!TIP]  
>  <span data-ttu-id="0a8a2-123">Перед тем как создать запрос с именованным параметром, необходимо определить символы префикса и суффикса.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-123">You must define prefix and suffix characters before creating a named parameter query.</span></span>  
  
 <span data-ttu-id="0a8a2-124">При выполнении запроса в конструкторе запросов и представлений в диалоговом окне [Параметры запроса](query-parameters-dialog-box-visual-database-tools.md) появляется список именованных параметров.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-124">When you run the query in the Query and View Designer, the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with a list of named parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8a2-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a8a2-125">See Also</span></span>  
 <span data-ttu-id="0a8a2-126">[Запрос с параметрами &#40;визуальных инструментов для баз данных&#41;](query-with-parameters-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0a8a2-126">[Query with Parameters &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0a8a2-127">[Поддерживаемые типы запросов &#40;визуальных инструментов для баз данных&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0a8a2-127">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0a8a2-128">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="0a8a2-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
