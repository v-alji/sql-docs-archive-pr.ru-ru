---
title: Указание нескольких условий поиска для нескольких столбцов (визуальные инструменты для баз данных) | Документация Майкрософт
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
ms.assetid: 06617729-0d0b-4da2-9890-b7e2f5cdbc7b
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccf08a98d39d4ab808b7c2df794164b341be363a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657452"
---
# <a name="specify-multiple-search-conditions-for-multiple-columns-visual-database-tools"></a><span data-ttu-id="124a3-102">Указание нескольких условий поиска для нескольких столбцов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="124a3-102">Specify Multiple Search Conditions for Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="124a3-103">Можно расширить или сузить область видимости, включив несколько столбцов данных в качестве части условия поиска.</span><span class="sxs-lookup"><span data-stu-id="124a3-103">You can expand or narrow the scope of your query by including several data columns as part of your search condition.</span></span> <span data-ttu-id="124a3-104">Например, может понадобиться:</span><span class="sxs-lookup"><span data-stu-id="124a3-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="124a3-105">Выполнить поиск сотрудников, которые либо проработали в компании более пяти лет, либо занимают определенные должности.</span><span class="sxs-lookup"><span data-stu-id="124a3-105">Search for employees who either have worked more than five years at the company or who hold certain jobs.</span></span>  
  
-   <span data-ttu-id="124a3-106">Выполнить поиск книги, которая опубликована указанным издательством и имеет отношение к кулинарии.</span><span class="sxs-lookup"><span data-stu-id="124a3-106">Search for a book that is both published by a specific publisher and pertains to cooking.</span></span>  
  
 <span data-ttu-id="124a3-107">Чтобы создать запрос, осуществляющий поиск значений в каком-либо из двух (или более) столбцов, необходимо указать условие OR.</span><span class="sxs-lookup"><span data-stu-id="124a3-107">To create a query that searches for values in either of two (or more) columns, you specify an OR condition.</span></span> <span data-ttu-id="124a3-108">Чтобы создать запрос, который должен отвечать условиям в двух (или более) столбцах, необходимо указать условие AND.</span><span class="sxs-lookup"><span data-stu-id="124a3-108">To create a query that must meet all conditions in two (or more) columns, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="124a3-109">Указание условия OR</span><span class="sxs-lookup"><span data-stu-id="124a3-109">Specifying an OR Condition</span></span>  
 <span data-ttu-id="124a3-110">Чтобы создать несколько условий, связанных оператором OR, необходимо поместить каждое отдельное условие в отдельный столбец на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="124a3-110">To create multiple conditions linked with OR, you put each separate condition in a different column of the Criteria pane.</span></span>  
  
#### <a name="to-specify-an-or-condition-for-two-different-columns"></a><span data-ttu-id="124a3-111">Указание условия OR для двух различных столбцов</span><span class="sxs-lookup"><span data-stu-id="124a3-111">To specify an OR condition for two different columns</span></span>  
  
1.  <span data-ttu-id="124a3-112">В [панели критериев](visual-database-tools.md)добавьте столбцы для поиска.</span><span class="sxs-lookup"><span data-stu-id="124a3-112">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="124a3-113">В столбце **Фильтр** для первого столбца, подлежащего поиску, укажите первое условие.</span><span class="sxs-lookup"><span data-stu-id="124a3-113">In the **Filter** column for the first column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="124a3-114">В столбце **Или...** для второго столбца данных, подлежащего поиску, укажите второе условие, оставив столбец **Фильтр** пустым.</span><span class="sxs-lookup"><span data-stu-id="124a3-114">In the **Or...** column for the second data column to search, specify the second condition, leaving the **Filter** column blank.</span></span>  
  
     <span data-ttu-id="124a3-115">Конструктор запросов и представлений создает предложение WHERE, содержащее условие OR, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="124a3-115">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
    ```  
    SELECT job_lvl, hire_date  
    FROM employee  
    WHERE (job_lvl >= 200) OR   
      (hire_date < '01/01/1998')  
    ```  
  
4.  <span data-ttu-id="124a3-116">Повторите шаги 2 и 3 для каждого дополнительного условия, которое нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="124a3-116">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span> <span data-ttu-id="124a3-117">Используйте отдельный столбец **Или...** для каждого нового условия.</span><span class="sxs-lookup"><span data-stu-id="124a3-117">Use a different **Or...** column for each new condition.</span></span>  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="124a3-118">Указание условия AND</span><span class="sxs-lookup"><span data-stu-id="124a3-118">Specifying an AND Condition</span></span>  
 <span data-ttu-id="124a3-119">Чтобы выполнить поиск разных столбцов данных с использованием условий, связанных оператором AND, необходимо поместить все условия в столбец **Фильтр** в сетке.</span><span class="sxs-lookup"><span data-stu-id="124a3-119">To search different data columns using conditions linked with AND, you put all the conditions in the **Filter** column of the grid.</span></span>  
  
#### <a name="to-specify-an-and-condition-for-two-different-columns"></a><span data-ttu-id="124a3-120">Указание условия AND для двух различных столбцов</span><span class="sxs-lookup"><span data-stu-id="124a3-120">To specify an AND condition for two different columns</span></span>  
  
1.  <span data-ttu-id="124a3-121">В [панели критериев](visual-database-tools.md)добавьте столбцы для поиска.</span><span class="sxs-lookup"><span data-stu-id="124a3-121">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="124a3-122">В столбце **Фильтр** для первого столбца данных, подлежащего поиску, укажите первое условие.</span><span class="sxs-lookup"><span data-stu-id="124a3-122">In the **Filter** column for the first data column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="124a3-123">В столбце **Фильтр** для второго столбца данных укажите второе условие.</span><span class="sxs-lookup"><span data-stu-id="124a3-123">In the **Filter** column for the second data column, specify the second condition.</span></span>  
  
     <span data-ttu-id="124a3-124">Конструктор запросов и представлений создает предложение WHERE, которое содержит предложение AND, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="124a3-124">The Query and View Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
    ```  
    SELECT pub_id, title  
    FROM titles  
    WHERE (pub_id = '0877') AND (title LIKE '%Cook%')  
    ```  
  
4.  <span data-ttu-id="124a3-125">Повторите шаги 2 и 3 для каждого дополнительного условия, которое нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="124a3-125">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="124a3-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="124a3-126">See Also</span></span>  
 <span data-ttu-id="124a3-127">[Объединение условий, когда и имеет приоритет &#40;визуальных инструментов для баз данных&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="124a3-127">[Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="124a3-128">[Объединение условий, когда или имеет приоритет &#40;визуальных инструментов для баз данных&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="124a3-128">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="124a3-129">[Соглашения для комбинирования условий поиска на панели критериев &#40;визуальных инструментов для баз данных&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="124a3-129">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="124a3-130">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="124a3-130">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
