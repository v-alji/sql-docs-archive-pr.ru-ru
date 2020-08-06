---
title: Резюмирование результатов запросов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- queries [SQL Server], results
- aggregate queries [SQL Server]
ms.assetid: c9e15350-ed57-4d95-814d-815fbebfd86b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08713be2d4439e520df07ec5efd6cb761a78a994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735789"
---
# <a name="summarize-query-results-visual-database-tools"></a><span data-ttu-id="c275f-102">Резюмирование результатов запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="c275f-102">Summarize Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="c275f-103">К созданию статистических запросов следует применять определенные логические принципы.</span><span class="sxs-lookup"><span data-stu-id="c275f-103">When you create aggregate queries, certain logical principles apply.</span></span> <span data-ttu-id="c275f-104">Например, невозможно вывести содержимое отдельных строк в сводном запросе.</span><span class="sxs-lookup"><span data-stu-id="c275f-104">For example, you cannot display the contents of individual rows in a summary query.</span></span> <span data-ttu-id="c275f-105">Конструктор запросов и представлений помогает соблюсти эти принципы — такое поведение заложено в [панель диаграммы](visual-database-tools.md) и [панель критериев](criteria-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="c275f-105">The Query and View Designer helps you comply with these principles in the way the [Diagram pane](visual-database-tools.md) and [Criteria pane](criteria-pane-visual-database-tools.md) behave.</span></span>  
  
 <span data-ttu-id="c275f-106">Поняв принципы статистических запросов и поведение конструктора запросов и представлений, можно создавать логически безошибочные статистические запросы.</span><span class="sxs-lookup"><span data-stu-id="c275f-106">By understanding the principles of aggregate queries and the Query and View Designer's behavior, you can create logically correct aggregate queries.</span></span> <span data-ttu-id="c275f-107">Важнейший принцип гласит, что статистические запросы могут выдавать только сводные данные.</span><span class="sxs-lookup"><span data-stu-id="c275f-107">The overriding principle is that aggregate queries can result only in summary information.</span></span> <span data-ttu-id="c275f-108">Таким образом, большинство остальных принципов описывают способы создания в статистическом запросе ссылок на отдельные столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="c275f-108">Thus, most of the principles that follow describe the ways that you can reference individual data columns within an aggregate query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c275f-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="c275f-109">In This Section</span></span>  
 [<span data-ttu-id="c275f-110">Работа со столбцами в статистических запросах (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="c275f-110">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](work-with-columns-in-aggregate-queries-visual-database-tools.md)  
 <span data-ttu-id="c275f-111">Описывает концепции группирования и суммирования столбцов при помощи предложений GROUP BY, WHERE и HAVING.</span><span class="sxs-lookup"><span data-stu-id="c275f-111">Describes concepts about grouping and summarizing columns with the GROUP BY, WHERE, and HAVING clauses.</span></span>  
  
 [<span data-ttu-id="c275f-112">Подсчет строк в таблице (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="c275f-112">Count Rows in a Table &#40;Visual Database Tools&#41;</span></span>](count-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="c275f-113">Пошаговые инструкции для подсчета количества строк в таблице или количество строк в таблице, отвечающих набору критериев.</span><span class="sxs-lookup"><span data-stu-id="c275f-113">Provides steps for counting the number of rows in a table or the number of rows in a table that meet a set of criteria.</span></span>  
  
 [<span data-ttu-id="c275f-114">Получение суммарных или статистических значений для всех строк в таблице (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="c275f-114">Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="c275f-115">Пошаговые инструкции относительно суммирования всех строк, а не набора сгруппированных строк.</span><span class="sxs-lookup"><span data-stu-id="c275f-115">Provides steps for summarizing all rows rather than for a set of grouped rows.</span></span>  
  
 [<span data-ttu-id="c275f-116">Суммирование значения или выполнение статистической обработки с помощью пользовательских выражений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="c275f-116">Summarize or Aggregate Values Using Custom Expressions &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
 <span data-ttu-id="c275f-117">Пошаговые инструкции по использованию выражений для суммирования и выполнения статистической обработки вместо стандартных предложений.</span><span class="sxs-lookup"><span data-stu-id="c275f-117">Provides steps for using expressions to summarize or aggregate rather than using the predefined clauses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c275f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c275f-118">Related Sections</span></span>  
 [<span data-ttu-id="c275f-119">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="c275f-119">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
 <span data-ttu-id="c275f-120">Предоставляет ссылки на разделы, объясняющие как использовать конструктор запросов и представлений.</span><span class="sxs-lookup"><span data-stu-id="c275f-120">Provides links to topics covering how to use the Query and View Designer.</span></span>  
  
  
