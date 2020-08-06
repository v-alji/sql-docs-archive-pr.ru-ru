---
title: Создание псевдонимов столбцов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], aliases
- aliases [SQL Server], columns
ms.assetid: e2e1c166-8ea7-47a2-b6a7-e419bf0fa3bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: febe7ed27ed10a283cab549bc65299577d69761c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657464"
---
# <a name="create-column-aliases-visual-database-tools"></a><span data-ttu-id="66307-102">Создание псевдонимов столбцов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="66307-102">Create Column Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="66307-103">Для имен столбцов можно создать псевдонимы, чтобы облегчить работу с ними, подсчеты и суммирования значений.</span><span class="sxs-lookup"><span data-stu-id="66307-103">You can create aliases for column names to make it easier to work with column names, calculations, and summary values.</span></span> <span data-ttu-id="66307-104">Например, можно создать псевдоним столбца для:</span><span class="sxs-lookup"><span data-stu-id="66307-104">For example, you can create a column alias to:</span></span>  
  
-   <span data-ttu-id="66307-105">создания именованного столбца, например «Общий итог», для выражения типа `(quantity * unit_price)` или агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="66307-105">Create a column name, such as "Total Amount," for an expression such as `(quantity * unit_price)` or for an aggregate function.</span></span>  
  
-   <span data-ttu-id="66307-106">создания сокращенной формы имени столбца, например `"d_id"` для `"discounts.stor_id."`</span><span class="sxs-lookup"><span data-stu-id="66307-106">Create a shortened form of a column name, such as `"d_id"` for `"discounts.stor_id."`</span></span>  
  
 <span data-ttu-id="66307-107">После того, как псевдоним столбца определен, можно использовать его в запросе, чтобы указать данные, выбираемые запросом.</span><span class="sxs-lookup"><span data-stu-id="66307-107">After you have defined a column alias, you can use the alias in a Select query to specify query output.</span></span>  
  
### <a name="to-create-a-column-alias"></a><span data-ttu-id="66307-108">Создание псевдонима столбца</span><span class="sxs-lookup"><span data-stu-id="66307-108">To create a column alias</span></span>  
  
1.  <span data-ttu-id="66307-109">На **панели критериев**укажите строку, содержащую столбец данных, для которого нужно создать псевдоним и, если необходимо, пометьте ее как выходные данные.</span><span class="sxs-lookup"><span data-stu-id="66307-109">In the **Criteria Pane**, locate the row containing the data column for which you want to create an alias, and if necessary, mark it for output.</span></span> <span data-ttu-id="66307-110">Если столбца данных нет в сетке, добавьте его.</span><span class="sxs-lookup"><span data-stu-id="66307-110">If the data column is not already in the grid, add it.</span></span>  
  
2.  <span data-ttu-id="66307-111">В столбце **Псевдоним** для этой строки введите псевдоним.</span><span class="sxs-lookup"><span data-stu-id="66307-111">In the **Alias** column for that row, enter the alias.</span></span> <span data-ttu-id="66307-112">Этот псевдоним должен соответствовать всем соглашениям об именах для SQL.</span><span class="sxs-lookup"><span data-stu-id="66307-112">The alias must follow all naming conventions for SQL.</span></span> <span data-ttu-id="66307-113">Если введенное имя псевдонима содержит пробелы, конструктор запросов и представлений автоматически ставит вокруг них разделители.</span><span class="sxs-lookup"><span data-stu-id="66307-113">If the alias name you enter contains spaces, the Query and View Designer automatically puts delimiters around it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66307-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="66307-114">See Also</span></span>  
 <span data-ttu-id="66307-115">[Добавление столбцов в запросы &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="66307-115">[Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="66307-116">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="66307-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="66307-117">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="66307-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="66307-118">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="66307-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
