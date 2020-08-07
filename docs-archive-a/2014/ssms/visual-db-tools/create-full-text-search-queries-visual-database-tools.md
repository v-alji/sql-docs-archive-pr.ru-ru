---
title: Создание запросов полнотекстового поиска (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CONTAINS predicate (Transact-SQL)
- queries [full-text search], creating
- full-text queries [SQL Server], creating
ms.assetid: 537fa556-390e-4c88-9b8e-679848d94abc
author: stevestein
ms.author: sstein
ms.openlocfilehash: f84ab465da0a1b7ac1da1211de1d5199fd28ee95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731289"
---
# <a name="create-full-text-search-queries-visual-database-tools"></a><span data-ttu-id="81486-102">Создание запросов полнотекстового поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="81486-102">Create Full-Text Search Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="81486-103">Чтобы определить строки, содержащие в данном столбце указанный текст, в полнотекстовом поиске используется предикат CONTAINS.</span><span class="sxs-lookup"><span data-stu-id="81486-103">Full-text searches use the CONTAINS predicate to locate rows that have specified text in a given column.</span></span> <span data-ttu-id="81486-104">Полнотекстовый поиск возможен только в тех столбцах, для которых существуют активные полнотекстовые индексы.</span><span class="sxs-lookup"><span data-stu-id="81486-104">Full-Text searches are only possible on columns that have active full-text indexes.</span></span> <span data-ttu-id="81486-105">При попытке использовать предложение CONTAINS со столбцом, для которого в данный момент нет активного полнотекстового индекса, будет возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="81486-105">If you attempt to use the CONTAINS clause on a column that does not have a currently active full-text index, you will receive an error.</span></span> <span data-ttu-id="81486-106">Дополнительные сведения о полнотекстовых индексах и предложении CONTAINS см. в разделе [полнотекстовый поиск](../../relational-databases/search/full-text-search.md) и [содержит &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="81486-106">For more information on full-text indexes and the CONTAINS clause, see [Full-Text Search](../../relational-databases/search/full-text-search.md) and [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
### <a name="to-create-a-full-text-search-query"></a><span data-ttu-id="81486-107">Создание запроса полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="81486-107">To create a full-text search query</span></span>  
  
1.  <span data-ttu-id="81486-108">Откройте запрос с помощью обозревателя решений или создайте новый.</span><span class="sxs-lookup"><span data-stu-id="81486-108">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="81486-109">Чтобы провести полнотекстовой поиск в столбце, в предложении WHERE запроса используйте функцию CONTAINS.</span><span class="sxs-lookup"><span data-stu-id="81486-109">In the WHERE clause of your query, use the CONTAINS function to search a full-text column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81486-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="81486-110">See Also</span></span>  
 <span data-ttu-id="81486-111">[Поддерживаемые типы запросов &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="81486-111">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="81486-112">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="81486-112">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="81486-113">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="81486-113">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
