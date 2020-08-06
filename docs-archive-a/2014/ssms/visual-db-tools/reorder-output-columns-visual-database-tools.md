---
title: Переупорядочение выходных столбцов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- reordering output columns [SQL Server]
- output columns [SQL Server]
ms.assetid: 76462885-de4a-4290-a26b-90696d3671f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 97fa3f768b03f24b8c8d154624a2d7a91aba45f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664638"
---
# <a name="reorder-output-columns-visual-database-tools"></a><span data-ttu-id="0792f-102">Переупорядочение выходных столбцов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="0792f-102">Reorder Output Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="0792f-103">Порядком, в соответствии с которым столбцы данных добавляются в запрос Select, определяется порядок, в котором они будут представлены в результатах.</span><span class="sxs-lookup"><span data-stu-id="0792f-103">The order in which you add data columns to a Select query determines the order in which they appear in the results.</span></span> <span data-ttu-id="0792f-104">Первый столбец, добавляемый в запрос, в результатах располагается в крайней левой позиции, второй добавляемый в запрос столбец следует за ним и т. д.</span><span class="sxs-lookup"><span data-stu-id="0792f-104">The first column you add to the query appears leftmost in the results, the second column next, and so on.</span></span>  
  
 <span data-ttu-id="0792f-105">При создании запросов Update или Insert порядок добавления столбцов влияет на порядок обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0792f-105">If you are creating Update or Insert queries, the order in which you add columns affects the order in which data is processed.</span></span>  
  
 <span data-ttu-id="0792f-106">Переупорядочивая столбцы, можно изменять местоположение столбца данных в результирующем наборе или порядок его использования.</span><span class="sxs-lookup"><span data-stu-id="0792f-106">To control where a data column appears in the result set, or in what order it is used, you can reorder the columns.</span></span>  
  
### <a name="to-reorder-columns-for-output"></a><span data-ttu-id="0792f-107">Переупорядочение столбцов для вывода</span><span class="sxs-lookup"><span data-stu-id="0792f-107">To reorder columns for output</span></span>  
  
1.  <span data-ttu-id="0792f-108">На [панели критериев](visual-database-tools.md)выберите строку, содержащую столбец, нажав кнопку выбора слева от строки.</span><span class="sxs-lookup"><span data-stu-id="0792f-108">In the [Criteria pane](visual-database-tools.md), select the row containing the column by clicking the row selector button to the left of the row.</span></span>  
  
2.  <span data-ttu-id="0792f-109">Укажите кнопку выбора строки и перетащите строку в новое место.</span><span class="sxs-lookup"><span data-stu-id="0792f-109">Point to the row selector button and drag the row to a new location.</span></span>  
  
     <span data-ttu-id="0792f-110">-или-</span><span class="sxs-lookup"><span data-stu-id="0792f-110">-or-</span></span>  
  
     <span data-ttu-id="0792f-111">Измените порядок имен столбцов на [панели SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0792f-111">Edit the order of the column names in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="0792f-112">Можно добавить строку данных в определенную позицию на панель критериев, вставив пустую строку на панель критериев, а затем указав столбец данных для вставки.</span><span class="sxs-lookup"><span data-stu-id="0792f-112">You can add a data row at a specific location in the Criteria pane by inserting a blank row into the Criteria pane, and then specifying the data column to insert.</span></span> <span data-ttu-id="0792f-113">Дополнительные сведения см. в разделе [Добавление столбцов в запросы (визуальные инструменты для баз данных)](add-columns-to-queries-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0792f-113">For details, see [Add Columns to Queries &#40;Visual Database Tools&#41;](add-columns-to-queries-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0792f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="0792f-114">See Also</span></span>  
 <span data-ttu-id="0792f-115">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0792f-115">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0792f-116">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0792f-116">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0792f-117">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="0792f-117">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
