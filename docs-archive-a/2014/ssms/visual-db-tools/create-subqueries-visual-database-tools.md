---
title: Создание вложенных запросов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], subqueries
- nested queries
- subqueries [SQL Server], SQL pane
ms.assetid: 34f6b9b4-ca3a-4a4f-9594-36e513f1c547
author: stevestein
ms.author: sstein
ms.openlocfilehash: 540228839b9734992be008b5d4fb7d717176832e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665211"
---
# <a name="create-subqueries-visual-database-tools"></a><span data-ttu-id="8961f-102">Создание вложенных запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="8961f-102">Create Subqueries (Visual Database Tools)</span></span>
  <span data-ttu-id="8961f-103">Результаты одного запроса можно использовать в качестве входных данных другого запроса.</span><span class="sxs-lookup"><span data-stu-id="8961f-103">You can use the results of one query as the input for another.</span></span> <span data-ttu-id="8961f-104">Результаты вложенного запроса можно использовать в качестве инструкции, использующей функцию IN( ), оператор EXISTS или предложение FROM.</span><span class="sxs-lookup"><span data-stu-id="8961f-104">You can use the results of a subquery as a statement that uses the IN( ) function, the EXISTS operator, or the FROM clause.</span></span>  
  
 <span data-ttu-id="8961f-105">Вложенный запрос можно ввести непосредственно на панели «SQL» или создать его путем вставки одного запроса в другой.</span><span class="sxs-lookup"><span data-stu-id="8961f-105">You can create a subquery by entering it directly into the SQL pane or by copying a query and pasting it into another.</span></span>  
  
### <a name="to-define-a-subquery-in-the-sql-pane"></a><span data-ttu-id="8961f-106">Создание вложенного запроса на панели «SQL»</span><span class="sxs-lookup"><span data-stu-id="8961f-106">To define a subquery in the SQL pane</span></span>  
  
1.  <span data-ttu-id="8961f-107">Создайте первичный запрос.</span><span class="sxs-lookup"><span data-stu-id="8961f-107">Create the primary query.</span></span>  
  
2.  <span data-ttu-id="8961f-108">На панели "SQL" выберите инструкцию SQL и скопируйте запрос в буфер обмена с помощью команды **Копировать** .</span><span class="sxs-lookup"><span data-stu-id="8961f-108">In the SQL pane, select the SQL statement, and then use **Copy** to move the query to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="8961f-109">Запустите новый запрос и вставьте первоначальный запрос в предложение WHERE или FROM нового запроса с помощью команды **Вставить** .</span><span class="sxs-lookup"><span data-stu-id="8961f-109">Start the new query, and then use **Paste** to move the first query into the new query's WHERE or FROM clause.</span></span>  
  
     <span data-ttu-id="8961f-110">Например, есть две таблицы `products` и `suppliers`, и нужно создать запрос, отображающий все продукты поставщиков из Швеции.</span><span class="sxs-lookup"><span data-stu-id="8961f-110">For example, imagine you have two tables, `products` and `suppliers`, and you want to create a query showing all products for suppliers in Sweden.</span></span> <span data-ttu-id="8961f-111">Чтобы найти всех шведских поставщиков, создайте первый запрос в таблице `suppliers` :</span><span class="sxs-lookup"><span data-stu-id="8961f-111">Create the first query on the `suppliers` table to find all Swedish suppliers:</span></span>  
  
    ```  
    SELECT supplier_id  
    FROM supplier  
    WHERE (country = 'Sweden')  
    ```  
  
     <span data-ttu-id="8961f-112">Скопируйте этот запрос в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="8961f-112">Use the Copy command to move this query to the Clipboard.</span></span> <span data-ttu-id="8961f-113">С помощью таблицы `products` создайте второй запрос. Укажите, какие сведения о продуктах нужно получить:</span><span class="sxs-lookup"><span data-stu-id="8961f-113">Create the second query using the `products` table, listing the information you need about products:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    ```  
  
     <span data-ttu-id="8961f-114">На панели «SQL» добавьте во второй запрос предложение WHERE, затем вставьте из буфера обмена первый запрос.</span><span class="sxs-lookup"><span data-stu-id="8961f-114">In the SQL pane, add a WHERE clause to the second query, then paste the first query from the Clipboard.</span></span> <span data-ttu-id="8961f-115">Отделите первый запрос круглыми скобками, чтобы конечный результат выглядел следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8961f-115">Place parentheses around the first query, so that the end result looks like this:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    WHERE supplier_id IN  
       (SELECT supplier_id  
      FROM supplier  
      WHERE (country = 'Sweden'))  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8961f-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="8961f-116">See Also</span></span>  
 <span data-ttu-id="8961f-117">[Поддерживаемые типы запросов &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8961f-117">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="8961f-118">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="8961f-118">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
