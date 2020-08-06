---
title: Указание нескольких условий поиска для одного столбца (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 2c006e36-56b1-4992-89b4-c6c0b19808f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a07322120bd3b3f543e6f54fa50cdf75aa32be59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659067"
---
# <a name="specify-multiple-search-conditions-for-one-column-visual-database-tools"></a><span data-ttu-id="b3e96-102">Указание нескольких условий поиска для одного столбца (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b3e96-102">Specify Multiple Search Conditions for One Column (Visual Database Tools)</span></span>
  <span data-ttu-id="b3e96-103">Иногда может понадобиться сочетание нескольких условий поиска для одного столбца.</span><span class="sxs-lookup"><span data-stu-id="b3e96-103">In some instances, you might want to apply a number of search conditions to the same data column.</span></span> <span data-ttu-id="b3e96-104">Например, может понадобиться:</span><span class="sxs-lookup"><span data-stu-id="b3e96-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="b3e96-105">Найти несколько разных имен сотрудников в таблице `employee` , находящихся в разных группах по уровню зарплаты.</span><span class="sxs-lookup"><span data-stu-id="b3e96-105">Search for several different names in an `employee` table or for employees who are in different salary ranges.</span></span> <span data-ttu-id="b3e96-106">Такой тип поиска требует использования условия OR (или).</span><span class="sxs-lookup"><span data-stu-id="b3e96-106">This type of search requires an OR condition.</span></span>  
  
-   <span data-ttu-id="b3e96-107">Найти книгу, название которой начинается со слова «The» и содержит слово «Cook».</span><span class="sxs-lookup"><span data-stu-id="b3e96-107">Search for a book title that both starts with the word "The" and contains the word "Cook."</span></span> <span data-ttu-id="b3e96-108">Такой тип поиска требует использования условия AND (и).</span><span class="sxs-lookup"><span data-stu-id="b3e96-108">This type of search requires an AND condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3e96-109">Сведения, приведенные в этом подразделе, применимы к условиям поиска как в предложении WHERE, так и в предложении HAVING запроса.</span><span class="sxs-lookup"><span data-stu-id="b3e96-109">The information in this topic applies to search conditions in both the WHERE and HAVING clauses of a query.</span></span> <span data-ttu-id="b3e96-110">В примерах в основном используется предложение WHERE, но рассматриваемые принципы применимы к обоим типам задания условий поиска.</span><span class="sxs-lookup"><span data-stu-id="b3e96-110">The examples focus on creating WHERE clauses, but the principles apply to both types of search conditions.</span></span>  
  
 <span data-ttu-id="b3e96-111">Для поиска альтернативных значений в одном столбце данных используется условие OR.</span><span class="sxs-lookup"><span data-stu-id="b3e96-111">To search for alternative values in the same data column, you specify an OR condition.</span></span> <span data-ttu-id="b3e96-112">Для поиска значений, удовлетворяющих одновременно нескольким условиям, используется условие AND.</span><span class="sxs-lookup"><span data-stu-id="b3e96-112">To search for values that meet several conditions, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="b3e96-113">Указание условия OR</span><span class="sxs-lookup"><span data-stu-id="b3e96-113">Specifying an OR Condition</span></span>  
 <span data-ttu-id="b3e96-114">Использование условия OR позволяет указать несколько альтернативных значений для поиска в столбце.</span><span class="sxs-lookup"><span data-stu-id="b3e96-114">Using an OR condition enables you to specify several alternative values to search for in a column.</span></span> <span data-ttu-id="b3e96-115">Этот параметр расширяет пространство поиска и может вернуть больше записей, чем при поиске одного значения.</span><span class="sxs-lookup"><span data-stu-id="b3e96-115">This option expands the scope of the search and can return more rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="b3e96-116">Часто можно использовать оператор IN вместо того, чтобы искать несколько значений в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="b3e96-116">You can often use the IN operator instead to search for multiple values in the same data column.</span></span>  
  
#### <a name="to-specify-an-or-condition"></a><span data-ttu-id="b3e96-117">Указание условия OR</span><span class="sxs-lookup"><span data-stu-id="b3e96-117">To specify an OR condition</span></span>  
  
1.  <span data-ttu-id="b3e96-118">На [панели критериев](visual-database-tools.md)добавьте столбец для поиска.</span><span class="sxs-lookup"><span data-stu-id="b3e96-118">In the [Criteria Pane](visual-database-tools.md), add the column to search.</span></span>  
  
2.  <span data-ttu-id="b3e96-119">Укажите первое условие в столбце **Фильтр** только что добавленного столбца данных.</span><span class="sxs-lookup"><span data-stu-id="b3e96-119">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="b3e96-120">Укажите второе условие в столбце **Или...** этого столбца данных.</span><span class="sxs-lookup"><span data-stu-id="b3e96-120">In the **Or...** column for the same data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="b3e96-121">Конструктор запросов и представлений создает предложение WHERE, содержащее условие OR, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="b3e96-121">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
```  
SELECT fname, lname  
FROM employees  
WHERE (salary < 30000) OR (salary > 100000)  
```  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="b3e96-122">Указание условия AND</span><span class="sxs-lookup"><span data-stu-id="b3e96-122">Specifying an AND Condition</span></span>  
 <span data-ttu-id="b3e96-123">Использование оператора AND позволяет задать такие условия поиска, при которых результирующий набор удовлетворяет сразу двум (или более) критериям поиска.</span><span class="sxs-lookup"><span data-stu-id="b3e96-123">Using an AND condition enables you to specify that values in a column must meet two (or more) conditions for the row to be included in the result set.</span></span> <span data-ttu-id="b3e96-124">При использовании этого параметра пространство поиска сужается и обычно возвращается меньше записей, чем при поиске по одному значению.</span><span class="sxs-lookup"><span data-stu-id="b3e96-124">This option narrows the scope of the search and usually returns fewer rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="b3e96-125">Для поиска в диапазоне значений можно использовать оператор BETWEEN вместо двух условий, объединенных оператором AND.</span><span class="sxs-lookup"><span data-stu-id="b3e96-125">If you are searching for a range of values, you can use the BETWEEN operator instead of linking two conditions with AND.</span></span>  
  
#### <a name="to-specify-an-and-condition"></a><span data-ttu-id="b3e96-126">Указание условия AND</span><span class="sxs-lookup"><span data-stu-id="b3e96-126">To specify an AND condition</span></span>  
  
1.  <span data-ttu-id="b3e96-127">На панели критериев добавьте столбец для поиска.</span><span class="sxs-lookup"><span data-stu-id="b3e96-127">In the Criteria pane, add the column to search.</span></span>  
  
2.  <span data-ttu-id="b3e96-128">Укажите первое условие в столбце **Фильтр** только что добавленного столбца данных.</span><span class="sxs-lookup"><span data-stu-id="b3e96-128">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="b3e96-129">Добавьте тот же столбец на панель критериев еще раз, поместив его в пустую строку сетки.</span><span class="sxs-lookup"><span data-stu-id="b3e96-129">Add the same data column to the Criteria pane again, placing it in an empty row of the grid.</span></span>  
  
4.  <span data-ttu-id="b3e96-130">В столбце **Фильтр** второй строки укажите второе условие.</span><span class="sxs-lookup"><span data-stu-id="b3e96-130">In the **Filter** column for the second instance of the data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="b3e96-131">Конструктор запросов создает предложение WHERE, которое содержит условие AND, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="b3e96-131">The Query Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
```  
SELECT title_id, title  
FROM titles  
WHERE (title LIKE '%Cook%') AND   
  (title LIKE '%Recipe%')  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3e96-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3e96-132">See Also</span></span>  
 <span data-ttu-id="b3e96-133">[Соглашения для комбинирования условий поиска на панели критериев &#40;визуальных инструментов для баз данных&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b3e96-133">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="b3e96-134">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b3e96-134">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
