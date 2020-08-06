---
title: Задание условий для групп (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query groups
- group query conditions [SQL Server]
ms.assetid: 269ad9c5-3261-4526-badf-7be3c869f229
author: stevestein
ms.author: sstein
ms.openlocfilehash: da9bc1b70fbfae8bf2a68a3a3ba332020020f310
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87653988"
---
# <a name="specify-conditions-for-groups-visual-database-tools"></a><span data-ttu-id="9bad6-102">Задание условий для групп (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="9bad6-102">Specify Conditions for Groups (Visual Database Tools)</span></span>
  <span data-ttu-id="9bad6-103">Группы, возвращаемые запросом, можно ограничить, задав условие для групп в целом с помощью предложения HAVING.</span><span class="sxs-lookup"><span data-stu-id="9bad6-103">You can limit the groups that appear in a query by specifying a condition that applies to groups as a whole - a HAVING clause.</span></span> <span data-ttu-id="9bad6-104">Условие в приложении HAVING применяется после группировки и статистической обработки данных.</span><span class="sxs-lookup"><span data-stu-id="9bad6-104">After the data has been grouped and aggregated, the conditions in the HAVING clause are applied.</span></span> <span data-ttu-id="9bad6-105">Запрос возвращает только те группы, которые удовлетворяют условию.</span><span class="sxs-lookup"><span data-stu-id="9bad6-105">Only the groups that meet the conditions appear in the query.</span></span>  
  
 <span data-ttu-id="9bad6-106">Допустим, требуется посмотреть среднюю цену на все книги каждого издателя в таблице `titles` , если средняя цена превышает $10.00.</span><span class="sxs-lookup"><span data-stu-id="9bad6-106">For example, you might want to see the average price of all books for each publisher in a `titles` table, but only if the average price exceeds $10.00.</span></span> <span data-ttu-id="9bad6-107">В этом случае в предложении HAVING можно указать следующее условие: `AVG(price) > 10`.</span><span class="sxs-lookup"><span data-stu-id="9bad6-107">In that case, you could specify a HAVING clause with a condition such as `AVG(price) > 10`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bad6-108">Иногда требуется исключить из групп отдельные строки перед применением условия на всю группу.</span><span class="sxs-lookup"><span data-stu-id="9bad6-108">In some instances, you might want to exclude individual rows from groups before applying a condition to groups as a whole.</span></span> <span data-ttu-id="9bad6-109">Дополнительные сведения см. в разделе [Использование предложения HAVING и WHERE в одном запросе (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9bad6-109">For details, see [Use HAVING and WHERE Clauses in the Same Query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="9bad6-110">Предложение HAVING может содержать сложные условия, соединенные операторами AND и OR.</span><span class="sxs-lookup"><span data-stu-id="9bad6-110">You can create complex conditions for a HAVING clause by using AND and OR to link conditions.</span></span> <span data-ttu-id="9bad6-111">Дополнительные сведения об использовании операторов AND и OR в условиях поиска см. в разделе [Указание нескольких условий поиска для одного столбца (визуальные инструменты для баз данных)](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9bad6-111">For details about using AND and OR in search conditions, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span></span>  
  
### <a name="to-specify-a-condition-for-a-group"></a><span data-ttu-id="9bad6-112">Указание условия для группы</span><span class="sxs-lookup"><span data-stu-id="9bad6-112">To specify a condition for a group</span></span>  
  
1.  <span data-ttu-id="9bad6-113">Укажите группы для запроса.</span><span class="sxs-lookup"><span data-stu-id="9bad6-113">Specify the groups for your query.</span></span> <span data-ttu-id="9bad6-114">Дополнительные сведения см. в разделе [Группирование строк в результатах запроса (визуальные инструменты для баз данных)](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9bad6-114">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="9bad6-115">Если она уже находится на [панели критериев](criteria-pane-visual-database-tools.md), добавьте столбец, лежащий в основе условия.</span><span class="sxs-lookup"><span data-stu-id="9bad6-115">If it is not already in the [Criteria pane](criteria-pane-visual-database-tools.md), add the column on which you want to base the condition.</span></span> <span data-ttu-id="9bad6-116">(Чаще всего условие содержит столбец, который является столбцом группы или суммарным столбцом.) Столбец, который отсутствует в агрегатной функции или предложении GROUP BY, использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="9bad6-116">(Most often the condition involves a column that is already a group or summary column.) You cannot use a column that is not part of an aggregate function or of the GROUP BY clause.</span></span>  
  
3.  <span data-ttu-id="9bad6-117">В столбце **Фильтр** укажите условие, которое требуется применить к группе.</span><span class="sxs-lookup"><span data-stu-id="9bad6-117">In the **Filter** column, specify the condition to apply to the group.</span></span>  
  
     <span data-ttu-id="9bad6-118">[конструктор запросов и представлений](query-and-view-designer-tools-visual-database-tools.md) автоматически добавит предложение HAVING в инструкцию на [панели SQL](sql-pane-visual-database-tools.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9bad6-118">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically creates a HAVING clause in the statement in the [SQL pane](sql-pane-visual-database-tools.md), such as in the following example:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
  
    ```  
  
4.  <span data-ttu-id="9bad6-119">Повторите шаги 2 и 3 для каждого дополнительного условия.</span><span class="sxs-lookup"><span data-stu-id="9bad6-119">Repeat steps 2 and 3 for each additional condition you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bad6-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="9bad6-120">See Also</span></span>  
 [<span data-ttu-id="9bad6-121">Результаты запросов сортировки и группирования (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="9bad6-121">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
