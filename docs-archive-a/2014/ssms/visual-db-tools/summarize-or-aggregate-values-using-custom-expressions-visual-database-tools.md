---
title: Суммирование или агрегирование значений с помощью пользовательских выражений (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- custom expressions to aggregate values [SQL Server]
ms.assetid: 34130ac1-0106-4766-b324-acb0b7bb6f6e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9f03f82842178a68c8a3d04ebc1bd738c0ab0b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735790"
---
# <a name="summarize-or-aggregate-values-using-custom-expressions-visual-database-tools"></a><span data-ttu-id="899f4-102">Суммирование значения или выполнение статистической обработки с помощью пользовательских выражений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="899f4-102">Summarize or Aggregate Values Using Custom Expressions (Visual Database Tools)</span></span>
  <span data-ttu-id="899f4-103">В дополнение к обработке данных с помощью агрегатных функций можно формировать статистические значения с помощью пользовательских выражений.</span><span class="sxs-lookup"><span data-stu-id="899f4-103">In addition to using aggregate functions to aggregate data, you can create custom expressions to produce aggregate values.</span></span> <span data-ttu-id="899f4-104">Эти выражения можно свободно использовать в статистических запросах вместо агрегатных функций.</span><span class="sxs-lookup"><span data-stu-id="899f4-104">You can use custom expressions in place of aggregate functions anywhere in an aggregate query.</span></span>  
  
 <span data-ttu-id="899f4-105">Например, попробуйте создать в таблице `titles` запрос, отображающий не просто среднюю цену, а среднюю цену при наличии скидки.</span><span class="sxs-lookup"><span data-stu-id="899f4-105">For example, in the `titles` table you might want to create a query that shows not just the average price, but what the average price would be if it were discounted.</span></span>  
  
 <span data-ttu-id="899f4-106">В запрос нельзя включать выражения, основанные на вычислении отдельных строк таблицы. Следует создавать выражения на основе статистических значений, поскольку при вычислении выражений доступны только такие значения.</span><span class="sxs-lookup"><span data-stu-id="899f4-106">You cannot include an expression that is based on calculations involving only individual rows in the table; the expression must be based on an aggregate value, because only the aggregate values are available at the time the expression is calculated.</span></span>  
  
### <a name="to-specify-a-custom-expression-for-a-summary-value"></a><span data-ttu-id="899f4-107">Пользовательское выражение для сводного значения</span><span class="sxs-lookup"><span data-stu-id="899f4-107">To specify a custom expression for a summary value</span></span>  
  
1.  <span data-ttu-id="899f4-108">Укажите группы для запроса.</span><span class="sxs-lookup"><span data-stu-id="899f4-108">Specify the groups for your query.</span></span> <span data-ttu-id="899f4-109">Дополнительные сведения см. в разделе [Группирование строк в результатах запроса (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="899f4-109">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="899f4-110">Перейдите к пустой строке на панели критериев и введите выражение в столбце **Столбцы**.</span><span class="sxs-lookup"><span data-stu-id="899f4-110">Move to a blank row of the Criteria pane, and then type the expression in the **Columns** column.</span></span>  
  
     <span data-ttu-id="899f4-111">Чтобы создать полезный заголовок столбца в выходных данных запроса, [конструктор запросов и представлений](query-and-view-designer-tools-visual-database-tools.md) автоматически присваивает выражению псевдоним столбца.</span><span class="sxs-lookup"><span data-stu-id="899f4-111">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically assigns a column alias to the expression to create a useful column heading in query output.</span></span> <span data-ttu-id="899f4-112">Дополнительные сведения см. в разделе [Создание псевдонимов столбцов (визуальные инструменты для баз данных)](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="899f4-112">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
3.  <span data-ttu-id="899f4-113">В столбце **Группировать** выберите **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="899f4-113">In the **Group By** column for the expression, select **Expression**.</span></span>  
  
4.  <span data-ttu-id="899f4-114">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="899f4-114">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="899f4-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="899f4-115">See Also</span></span>  
 <span data-ttu-id="899f4-116">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="899f4-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="899f4-117">Резюмирование результатов запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="899f4-117">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
