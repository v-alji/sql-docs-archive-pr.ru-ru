---
title: Сортировка данных в порядке убывания или возрастания (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- descending sorts
- ascending sorts
ms.assetid: d61cc55b-9ee8-4ecf-a32f-6459ae43910b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b5e6b00f62cfc297cc5930bc8cf3a41314a2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668000"
---
# <a name="sort-in-ascending-or-descending-order-visual-database-tools"></a><span data-ttu-id="abb01-102">отсортировать данные в порядке убывания и возрастания (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="abb01-102">Sort in Ascending or Descending Order (Visual Database Tools)</span></span>
  <span data-ttu-id="abb01-103">Результаты запроса можно отсортировать в возрастающем или убывающем порядке по одному или нескольким столбцам результирующего набора при помощи ключевых слов `ASC` и `DESC` в предложении `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="abb01-103">You can sort query results in ascending or descending order on one or more of the columns in the result set by using the `ASC` or `DESC` keywords with the `ORDER BY` clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abb01-104">Порядок сортировки частично определяется параметрами сортировки столбца.</span><span class="sxs-lookup"><span data-stu-id="abb01-104">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="abb01-105">Очередность использования параметров сортировки можно изменить в диалоговом окне [Параметры сортировки](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="abb01-105">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="abb01-106">Следующая инструкция подразумевает, что в конструкторе запросов и представлений открыт запрос, содержащий предложение ORDER BY для сортировки по одному или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="abb01-106">The following procedure assumes that you have a query open in Query and View Designer that uses the ORDER BY clause to sort one or more columns.</span></span>  
  
### <a name="to-specify-or-change-the-order-in-which-results-are-sorted"></a><span data-ttu-id="abb01-107">Указание или изменение порядка, в котором будут отсортированы результаты:</span><span class="sxs-lookup"><span data-stu-id="abb01-107">To specify or change the order in which results are sorted</span></span>  
  
1.  <span data-ttu-id="abb01-108">На [панели критериев](criteria-pane-visual-database-tools.md)перейдите в поле **Тип сортировки** , соответствующее сортируемому столбцу.</span><span class="sxs-lookup"><span data-stu-id="abb01-108">In the [Criteria pane](criteria-pane-visual-database-tools.md), click the **Sort Type** field for the column that you want to reorder.</span></span>  
  
2.  <span data-ttu-id="abb01-109">Выберите **По возрастанию** или **По убыванию** , чтобы указать порядок сортировки для данного столбца.</span><span class="sxs-lookup"><span data-stu-id="abb01-109">Choose **Ascending** or **Descending** to specify the sort order for the column.</span></span>  
  
 <span data-ttu-id="abb01-110">Обратите внимание, что во время работы с панелью критериев предложение UNION запроса изменяется в соответствии с последними действиями.</span><span class="sxs-lookup"><span data-stu-id="abb01-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abb01-111">При сортировке результатов по нескольким столбцам в столбце «Порядок сортировки» укажите порядок, в котором будут просматриваться столбцы при сортировке.</span><span class="sxs-lookup"><span data-stu-id="abb01-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the Sort Order column.</span></span> <span data-ttu-id="abb01-112">Дополнительные сведения см. в разделе [Сортировка по нескольким столбцам в запросах (визуальные инструменты для баз данных)](sort-multiple-columns-in-queries-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="abb01-112">For more information, see [Sort Multiple Columns in Queries &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb01-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="abb01-113">See Also</span></span>  
 <span data-ttu-id="abb01-114">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="abb01-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="abb01-115">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="abb01-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="abb01-116">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="abb01-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
