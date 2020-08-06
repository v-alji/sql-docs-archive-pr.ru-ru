---
title: Создание запросов на объединение (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- UNION queries
- Select query
- combining query results
- merged SELECT query [SQL Server]
ms.assetid: b5aafb1d-e4ed-4922-b790-56abc5ec551a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3c10f39c3e44844c4ec8a6a2328c41ea2de350d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665209"
---
# <a name="create-union-queries-visual-database-tools"></a><span data-ttu-id="3a13f-102">Создание запросов UNION (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="3a13f-102">Create UNION Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="3a13f-103">Ключевое слово UNION позволяет включить результаты двух инструкций SELECT в одну результирующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="3a13f-103">The UNION keyword enables you to include the results of two SELECT statements in one resulting table.</span></span> <span data-ttu-id="3a13f-104">Все строки, возвращаемые каждой инструкцией SELECT, объединяются в результат выражения UNION.</span><span class="sxs-lookup"><span data-stu-id="3a13f-104">All rows returned from either SELECT statement are combined into the result of the UNION expression.</span></span> <span data-ttu-id="3a13f-105">Примеры см. в разделе [примеры SELECT &#40;&#41;Transact-SQL ](/sql/t-sql/queries/select-examples-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a13f-105">For examples, see [SELECT Examples &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a13f-106">Панель диаграмм может отображать только одно предложение SELECT.</span><span class="sxs-lookup"><span data-stu-id="3a13f-106">The Diagram pane can only display one SELECT clause.</span></span> <span data-ttu-id="3a13f-107">Следовательно, когда пользователь работает с запросом UNION, конструктор запросов скрывает панель «Табличные операции».</span><span class="sxs-lookup"><span data-stu-id="3a13f-107">Therefore, when you are working with a UNION query, Query Designer hides the Table Operations pane.</span></span>  
  
### <a name="to-create-a-merged-select-query"></a><span data-ttu-id="3a13f-108">Создание объединенного запроса SELECT</span><span class="sxs-lookup"><span data-stu-id="3a13f-108">To create a Merged SELECT query</span></span>  
  
1.  <span data-ttu-id="3a13f-109">Откройте запрос или создайте новый.</span><span class="sxs-lookup"><span data-stu-id="3a13f-109">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="3a13f-110">На панели SQL введите допустимое выражение UNION.</span><span class="sxs-lookup"><span data-stu-id="3a13f-110">In the SQL pane, type a valid UNION expression.</span></span>  
  
     <span data-ttu-id="3a13f-111">Следующий пример является допустимым выражением UNION.</span><span class="sxs-lookup"><span data-stu-id="3a13f-111">The following example is a valid UNION expression.</span></span>  
  
    ```  
    SELECT ProductModelID, Name  
    FROM Production.ProductModel  
    UNION  
    SELECT ProductModelID, Name   
    FROM dbo.Gloves;  
    ```  
  
3.  <span data-ttu-id="3a13f-112">В меню **Конструктор запросов** выберите пункт **Выполнить SQL** для запуска запроса.</span><span class="sxs-lookup"><span data-stu-id="3a13f-112">On the **Query Designer** menu, click **Execute SQL** to run the query.</span></span>  
  
     <span data-ttu-id="3a13f-113">Теперь запрос UNION отформатирован конструктором запросов.</span><span class="sxs-lookup"><span data-stu-id="3a13f-113">Your UNION query is now formatted by Query Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a13f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a13f-114">See Also</span></span>  
 <span data-ttu-id="3a13f-115">[Поддерживаемые типы запросов &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3a13f-115">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="3a13f-116">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3a13f-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="3a13f-117">[Выполнение основных операций с запросами &#40;визуальных инструментов для баз данных&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3a13f-117">[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3a13f-118">UNION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3a13f-118">UNION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/set-operators-union-transact-sql)  
  
  
