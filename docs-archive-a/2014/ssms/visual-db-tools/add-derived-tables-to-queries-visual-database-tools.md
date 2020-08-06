---
title: Добавление производных таблиц в запросы (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [Visual Database Tools]
- joins [SQL Server], derived tables
- table joins [SQL Server]
- derived tables
ms.assetid: 05f1ba1d-465f-4e36-84bb-21b963c9b8f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72169654b878f404950788b468bb6603035fd540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657478"
---
# <a name="add-derived-tables-to-queries-visual-database-tools"></a><span data-ttu-id="42dd6-102">Добавление производных таблиц в запросы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="42dd6-102">Add Derived Tables to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="42dd6-103">Производная таблица — это результирующий набор, используемый в запросе в качестве исходных таблиц.</span><span class="sxs-lookup"><span data-stu-id="42dd6-103">Derived tables are result sets used as table sources in a query.</span></span> <span data-ttu-id="42dd6-104">Производную таблицу можно добавить в запрос на **панели диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="42dd6-104">You can add a derived table to a query in the **Diagram Pane**.</span></span>  
  
### <a name="to-add-a-derived-table-to-a-query"></a><span data-ttu-id="42dd6-105">Добавление в запрос производной таблицы</span><span class="sxs-lookup"><span data-stu-id="42dd6-105">To add a derived table to a query</span></span>  
  
1.  <span data-ttu-id="42dd6-106">Откройте существующий запрос или создайте новый.</span><span class="sxs-lookup"><span data-stu-id="42dd6-106">Open an existing query or create a new query.</span></span>  
  
2.  <span data-ttu-id="42dd6-107">Щелкните правой кнопкой мыши **панель диаграммы** и выберите из контекстного меню пункт **Добавить новую производную таблицу**.</span><span class="sxs-lookup"><span data-stu-id="42dd6-107">Right-click the **Diagram Pane** and choose **Add New Derived Table**.</span></span>  
  
     <span data-ttu-id="42dd6-108">При этом добавляется новая таблица с именем derivedtbl_*N* , а в предложение FROM запроса добавляется инструкция SELECT для производной таблицы.</span><span class="sxs-lookup"><span data-stu-id="42dd6-108">A new table with the name derivedtbl_*N* is added, and the derived table's SELECT statement is added to the query's FROM clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42dd6-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="42dd6-109">See Also</span></span>  
 <span data-ttu-id="42dd6-110">[Выполнение основных операций с запросами &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="42dd6-110">[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="42dd6-111">[Создание запросов &#40;визуальных инструментов для баз данных&#41;](create-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="42dd6-111">[Create Queries &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="42dd6-112">[Открытие запросов &#40;визуальных инструментов для баз данных&#41;](open-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="42dd6-112">[Open Queries &#40;Visual Database Tools&#41;](open-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="42dd6-113">SELECT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42dd6-113">SELECT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/select-transact-sql)  
  
  
