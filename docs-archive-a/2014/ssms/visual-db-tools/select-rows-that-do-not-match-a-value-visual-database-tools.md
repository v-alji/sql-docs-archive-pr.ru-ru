---
title: Выбор строк, не соответствующих заданному значению (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], rows not matching value
- row not matching value [SQL Server]
- NOT operator [Visual Database Tools]
- search criteria [SQL Server], rows not matching value
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 412ec93cbfedc87e92da9e86c7e4c7455919722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734854"
---
# <a name="select-rows-that-do-not-match-a-value-visual-database-tools"></a><span data-ttu-id="d9b56-102">Выбор строк, не соответствующих заданному значению (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d9b56-102">Select Rows That Do Not Match a Value (Visual Database Tools)</span></span>
  <span data-ttu-id="d9b56-103">Чтобы найти строки, которые не соответствуют значению, используется оператор NOT.</span><span class="sxs-lookup"><span data-stu-id="d9b56-103">To find rows that do not match a value, use the NOT operator.</span></span>  
  
### <a name="to-find-rows-that-do-not-match-a-value"></a><span data-ttu-id="d9b56-104">Поиск строк, не соответствующих значению</span><span class="sxs-lookup"><span data-stu-id="d9b56-104">To find rows that do not match a value</span></span>  
  
1.  <span data-ttu-id="d9b56-105">Если это еще не сделано, нужно добавить на [панели критериев](visual-database-tools.md)столбцы или выражения, которые необходимо использовать в условиях поиска.</span><span class="sxs-lookup"><span data-stu-id="d9b56-105">If you have not done so already, add the columns or expressions that you want to use within your search condition to the [Criteria pane](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="d9b56-106">Найдите строку, содержащую столбец данных или выражение поиска, и в столбце сетки **Фильтр** введите оператор NOT и затем значение поиска.</span><span class="sxs-lookup"><span data-stu-id="d9b56-106">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the NOT operator followed by a search value.</span></span>  
  
 <span data-ttu-id="d9b56-107">Например, чтобы найти строки в таблице `products` , в которой значения в столбце кода продукта начинаются с символа, отличного от «A», можно ввести такое условие поиска:</span><span class="sxs-lookup"><span data-stu-id="d9b56-107">For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:</span></span>  
  
```  
NOT LIKE 'A%'  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9b56-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9b56-108">See Also</span></span>  
 <span data-ttu-id="d9b56-109">[Правила ввода значений поиска &#40;визуальных инструментов для баз данных&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d9b56-109">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="d9b56-110">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d9b56-110">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
