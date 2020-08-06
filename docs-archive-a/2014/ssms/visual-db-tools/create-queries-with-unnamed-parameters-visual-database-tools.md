---
title: Создание запросов с неименованными параметрами (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0ea53afd1fa4d44390f5805d6b28494428608b90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654712"
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a><span data-ttu-id="14973-102">Создание запросов с неименованными параметрами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="14973-102">Create Queries with Unnamed Parameters (Visual Database Tools)</span></span>
  <span data-ttu-id="14973-103">Запросы с неименованными параметрами создаются с указанием вопросительного знака (?) в качестве заполнителя литерала.</span><span class="sxs-lookup"><span data-stu-id="14973-103">You can create a query with an unnamed parameter by specifying a question mark (?) as a placeholder for a literal value.</span></span> <span data-ttu-id="14973-104">Конструктор запросов и представлений присваивает такому параметру временное имя.</span><span class="sxs-lookup"><span data-stu-id="14973-104">Query and View Designer will give it a temporary name.</span></span> <span data-ttu-id="14973-105">В запросе можно указать любое число неименованных параметров.</span><span class="sxs-lookup"><span data-stu-id="14973-105">You can specify as many unnamed parameters in the query as you need.</span></span>  
  
 <span data-ttu-id="14973-106">При запуске запроса в конструкторе запросов и представлений в диалоговом окне параметров запроса отображается временное имя.</span><span class="sxs-lookup"><span data-stu-id="14973-106">When you run the query in the Query and View Designer, the Query Parameters Dialog Box is displayed with the temporary name.</span></span>  
  
### <a name="to-specify-an-unnamed-parameter"></a><span data-ttu-id="14973-107">Указание неименованного параметра</span><span class="sxs-lookup"><span data-stu-id="14973-107">To specify an unnamed parameter</span></span>  
  
1.  <span data-ttu-id="14973-108">Добавьте столбцы или выражения, для которых нужно произвести поиск, на [панель критериев](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="14973-108">Add the columns or expressions that you want to search to the [Criteria pane](visual-database-tools.md).</span></span> <span data-ttu-id="14973-109">Если столбцы или выражения поиска не нужно включать в результат запроса, их необходимо удалить из списка выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="14973-109">If you do not want the search columns or expressions to appear in the query output, remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="14973-110">Укажите строку, в которой содержится столбец данных или выражение для поиска, и в столбце сетки **Фильтр** введите вопросительный знак (?).</span><span class="sxs-lookup"><span data-stu-id="14973-110">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter a question mark (?).</span></span>  
  
     <span data-ttu-id="14973-111">По умолчанию конструктор запросов и представлений добавляет оператор «=».</span><span class="sxs-lookup"><span data-stu-id="14973-111">By default, the Query and View Designer adds the "=" operator.</span></span> <span data-ttu-id="14973-112">Однако можно отредактировать ячейку и заменить его на оператор «>», «<» или любой другой оператор сравнения языка SQL.</span><span class="sxs-lookup"><span data-stu-id="14973-112">However, you can edit the cell to substitute ">", "<", or any other SQL comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14973-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="14973-113">See Also</span></span>  
 [<span data-ttu-id="14973-114">Запрос с параметрами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="14973-114">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
