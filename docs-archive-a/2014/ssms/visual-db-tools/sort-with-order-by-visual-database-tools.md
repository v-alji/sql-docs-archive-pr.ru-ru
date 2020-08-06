---
title: Сортировка с помощью предложения ORDER BY (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ORDER BY clause [Visual Database Tools]
ms.assetid: 459f5640-8058-4c24-97e7-7bbd6168bc39
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93bdb9ed01c7935c5b9dae543804fca758a9262d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737361"
---
# <a name="sort-with-order-by-visual-database-tools"></a><span data-ttu-id="e1f4d-102">Произведение сортировки с помощью предложения ORDER BY (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e1f4d-102">Sort with ORDER BY (Visual Database Tools)</span></span>
  <span data-ttu-id="e1f4d-103">Предложение ORDER BY позволяет сортировать результаты запроса по одному или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="e1f4d-103">You can sort query results by one or more of the columns in the returned rows by using an ORDER BY clause.</span></span> <span data-ttu-id="e1f4d-104">Его можно определить, выбрав параметры на панели «Подробности критериев».</span><span class="sxs-lookup"><span data-stu-id="e1f4d-104">You can define an ORDER BY clause by choosing options in the Criteria Details pane.</span></span>  
  
### <a name="to-sort-a-query-using-an-order-by-clause"></a><span data-ttu-id="e1f4d-105">Для сортировки результатов запроса с помощью предложения ORDER BY:</span><span class="sxs-lookup"><span data-stu-id="e1f4d-105">To sort a query using an ORDER BY clause</span></span>  
  
1.  <span data-ttu-id="e1f4d-106">Откройте запрос или создайте новый.</span><span class="sxs-lookup"><span data-stu-id="e1f4d-106">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="e1f4d-107">На [панели критериев](visual-database-tools.md)щелкните в столбце **Тип сортировки** строку, соответствующую столбцу, по которому нужно отсортировать результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="e1f4d-107">In the [Criteria Pane](visual-database-tools.md), click the **Sort Type** column for the row corresponding to the column that you want to use to sort your query results.</span></span>  
  
3.  <span data-ttu-id="e1f4d-108">В раскрывающемся списке выберите *По возрастанию* или *По убыванию* .</span><span class="sxs-lookup"><span data-stu-id="e1f4d-108">Choose *Ascending* or *Descending* from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1f4d-109">Очистка элемента **Тип сортировки** для столбца удаляет этот столбец из предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="e1f4d-109">Clearing the **Sort Type** entry for a column removes that column from the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="e1f4d-110">Обратите внимание, что во время работы с панелью критериев предложение UNION запроса изменяется в соответствии с последними действиями.</span><span class="sxs-lookup"><span data-stu-id="e1f4d-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1f4d-111">При сортировке результатов по нескольким столбцам в столбце **Порядок сортировки** укажите порядок, в котором будут просматриваться столбцы при сортировке.</span><span class="sxs-lookup"><span data-stu-id="e1f4d-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the **Sort Order** column.</span></span> <span data-ttu-id="e1f4d-112">Дополнительные сведения см. в разделе **Как производить сортировку нескольких столбцов в запросе**.</span><span class="sxs-lookup"><span data-stu-id="e1f4d-112">For more information, see **How to: Sort Multiple Columns in Queries**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f4d-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1f4d-113">See Also</span></span>  
 <span data-ttu-id="e1f4d-114">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e1f4d-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="e1f4d-115">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e1f4d-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e1f4d-116">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e1f4d-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
