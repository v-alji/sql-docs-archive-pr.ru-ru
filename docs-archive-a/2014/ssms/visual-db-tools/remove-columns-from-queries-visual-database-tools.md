---
title: Удаление столбцов из запросов (визуальные инструменты для базы данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- removing columns
- queries [SQL Server], columns
- deleting columns
- dropping columns
ms.assetid: 6d9819b8-ee2f-4838-9713-c5e3ad37ab46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8532f5240729a2516a0c07ae943dd42dc01d9c1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734870"
---
# <a name="remove-columns-from-queries-visual-database-tools"></a><span data-ttu-id="2d52c-102">Удаление столбцов из запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="2d52c-102">Remove Columns from Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="2d52c-103">Если столбец больше не нужен в запросе, то его можно удалить.</span><span class="sxs-lookup"><span data-stu-id="2d52c-103">If you no longer want to use a column in a query, you can remove it.</span></span> <span data-ttu-id="2d52c-104">При удалении столбца конструктор запросов и представлений удалит ссылки на него в списке выборки, установку сортировки, критерии поиска, **панель SQL**и все спецификации группирования.</span><span class="sxs-lookup"><span data-stu-id="2d52c-104">If you do, the Query and View Designer removes references to the column in the select list, the sort specification, the search criteria, **SQL Pane**, and any grouping specifications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d52c-105">Если столбец нужно удалить только из выходных данных запроса Select, то это можно сделать без удаления столбца из запроса.</span><span class="sxs-lookup"><span data-stu-id="2d52c-105">If you want to remove a column from just the output of a Select query, you can do so without removing it from the query altogether.</span></span> <span data-ttu-id="2d52c-106">Дополнительные сведения см. в разделе [Удаление столбцов из результатов запроса (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2d52c-106">For details, see [Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-remove-a-column-from-the-query"></a><span data-ttu-id="2d52c-107">Удаление столбца из запроса</span><span class="sxs-lookup"><span data-stu-id="2d52c-107">To remove a column from the query</span></span>  
  
-   <span data-ttu-id="2d52c-108">На **панели критериев**выберите строку сетки, содержащую нужный столбец, затем нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="2d52c-108">In the **Criteria Pane**, select the grid row containing the column you want to remove and then press DELETE.</span></span>  
  
     <span data-ttu-id="2d52c-109">-или-</span><span class="sxs-lookup"><span data-stu-id="2d52c-109">-or-</span></span>  
  
-   <span data-ttu-id="2d52c-110">Удалите все ссылки на столбец в [панели SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2d52c-110">Remove all references to the column in the [SQL Pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d52c-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d52c-111">See Also</span></span>  
 <span data-ttu-id="2d52c-112">[Добавление столбцов в запросы &#40;визуальных инструментов для баз данных&#41;](add-columns-to-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2d52c-112">[Add Columns to Queries &#40;Visual Database Tools&#41;](add-columns-to-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2d52c-113">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2d52c-113">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2d52c-114">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2d52c-114">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2d52c-115">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="2d52c-115">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
