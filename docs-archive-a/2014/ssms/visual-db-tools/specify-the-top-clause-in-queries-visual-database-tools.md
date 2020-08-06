---
title: Определение предложения TOP в запросах (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- TOP clause, queries
- percentage of rows returned [SQL Server]
- number of rows
- search conditions [SQL Server], TOP clause
- restricting rows returned
- search criteria [SQL Server], limiting rows returned
- inspecting portion of results
- limiting rows returned
- search criteria [SQL Server], TOP clause
ms.assetid: ba7d7c10-9bb3-4d9b-90b0-5fa94ecae59b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8228779703b1bbe3753f1e2728e83b4b5c3a3d17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749547"
---
# <a name="specify-the-top-clause-in-queries-visual-database-tools"></a><span data-ttu-id="0620e-102">Указание предложения TOP в запросах (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="0620e-102">Specify the TOP Clause in Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="0620e-103">При использовании предложения TOP возвращаются только первые *n* или *n процентов* строк запроса.</span><span class="sxs-lookup"><span data-stu-id="0620e-103">The TOP clause returns only the first *n* or *n percent* rows from a query.</span></span> <span data-ttu-id="0620e-104">Предложение TOP полезно, когда нужно исследовать только часть результатов, чтобы определить, выполняет ли запрос то, что предполагалось, и не затрачивать ресурсы, необходимые для возвращения всех результатов.</span><span class="sxs-lookup"><span data-stu-id="0620e-104">The TOP clause is useful when you want to inspect a portion of your results to find out if your query does what you expect it to do, without taking the resources necessary to return all of the query results.</span></span>  
  
### <a name="to-specify-the-top-clause-in-queries"></a><span data-ttu-id="0620e-105">Указание в запросе предложения TOP</span><span class="sxs-lookup"><span data-stu-id="0620e-105">To specify the TOP clause in queries</span></span>  
  
1.  <span data-ttu-id="0620e-106">Откройте запрос с помощью обозревателя решений или создайте новый.</span><span class="sxs-lookup"><span data-stu-id="0620e-106">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="0620e-107">В меню **Вид** выберите **Окно "Свойства"** .</span><span class="sxs-lookup"><span data-stu-id="0620e-107">From the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="0620e-108">В разделе **Окно "Свойства"** найдите и разверните свойство **Параметр TOP** .</span><span class="sxs-lookup"><span data-stu-id="0620e-108">In the **Properties Window**, locate and expand the **Top Specification** property.</span></span>  
  
4.  <span data-ttu-id="0620e-109">Щелкните дочернее свойство **(Top)** и выберите значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="0620e-109">Click the **(Top)** child property and set it to **Yes**.</span></span>  
  
5.  <span data-ttu-id="0620e-110">В дочернем свойстве **Выражение** введите выражение с численным результатом (например, "10" или "2\*5").</span><span class="sxs-lookup"><span data-stu-id="0620e-110">In the **Expression** child property, type an expression that has a numeric result (for example, "10" or "2\*5").</span></span>  
  
6.  <span data-ttu-id="0620e-111">Щелкните дочернее свойство **В процентах** и определите, обрабатывать ли значение свойства **Выражение** как проценты от числа возвращаемых строк ("Да") или как абсолютное число возвращаемых строк ("Нет").</span><span class="sxs-lookup"><span data-stu-id="0620e-111">Click the **Percent** child property and indicate whether or not to treat the **Expression** property as a percentage of all rows returned (Yes) or as the absolute number of rows returned (No).</span></span>  
  
7.  <span data-ttu-id="0620e-112">Если в запросе присутствует предложение ORDER BY, щелкните дочернее свойство **Со связями** и выберите **Да** для отображения всех строк группы, если в результаты вошла только часть группы, или **Нет** для усечения результатов.</span><span class="sxs-lookup"><span data-stu-id="0620e-112">If your query uses the ORDER BY clause, click the **With Ties** child property and choose **Yes** to display all rows in a group if only part of the group is included or **No** to truncate them.</span></span>  
  
 <span data-ttu-id="0620e-113">Обратите внимание, что при выполнении шагов описанной выше процедуры предложение TOP, отображающееся на панели SQL, меняется в соответствии с текущими значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="0620e-113">As you work through the preceding procedure, notice that the TOP clause, displayed in the SQL pane, changes to reflect the current settings of the properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0620e-114">Можно также изменить значения дочерних свойств **Параметр TOP** , редактируя предложение TOP на панели SQL.</span><span class="sxs-lookup"><span data-stu-id="0620e-114">You can also change the values of the child properties of the **Top Specification** by editing the TOP clause in the SQL pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0620e-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="0620e-115">See Also</span></span>  
 <span data-ttu-id="0620e-116">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0620e-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0620e-117">Свойства запроса (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="0620e-117">Query Properties &#40;Visual Database Tools&#41;</span></span>](query-properties-visual-database-tools.md)  
  
  
