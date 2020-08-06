---
title: Удаление соединений (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- removing joins
- joins [SQL Server], removing
- deleting joins
ms.assetid: ccc212a1-fd13-48d6-85e5-5ff310c34bbd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b037e317b629671f6ec5ea1fa90edfca6fafa627
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87653989"
---
# <a name="remove-joins-visual-database-tools"></a><span data-ttu-id="21a98-102">Удаление соединений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="21a98-102">Remove Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="21a98-103">Если нежелательно, чтобы таблицы были соединены с помощью внутреннего или внешнего соединения, можно удалить это соединение между таблицами.</span><span class="sxs-lookup"><span data-stu-id="21a98-103">If you do not want tables to be joined via an inner join or an outer join, you can remove the join between them.</span></span> <span data-ttu-id="21a98-104">Например, можно удалить соединение, автоматически созданное между двумя таблицами в [конструкторе запросов и представлений](visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="21a98-104">For example, you might remove a join that the [Query and View Designer](visual-database-tools.md) has been created automatically between two tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21a98-105">Удаление соединения из запроса не влияет на базовые связи, существующие в базе данных.</span><span class="sxs-lookup"><span data-stu-id="21a98-105">Removing a join from a query does not alter the underlying relationship in the database.</span></span>  
  
 <span data-ttu-id="21a98-106">Если две соединяемые таблицы являются частью запроса и все условия соединения между ними удаляются, то результирующий запрос становится пересечением этих таблиц, то есть перекрестным соединением (CROSS JOIN).</span><span class="sxs-lookup"><span data-stu-id="21a98-106">If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables - that is, it becomes a CROSS JOIN.</span></span>  
  
### <a name="to-remove-a-join"></a><span data-ttu-id="21a98-107">Удаление соединения</span><span class="sxs-lookup"><span data-stu-id="21a98-107">To remove a join</span></span>  
  
-   <span data-ttu-id="21a98-108">На [панели диаграммы](diagram-pane-visual-database-tools.md)выберите удаляемую линию соединения и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="21a98-108">In the [Diagram pane](diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the DELETE key.</span></span> <span data-ttu-id="21a98-109">Можно одновременно выбрать и удалить несколько линий соединений.</span><span class="sxs-lookup"><span data-stu-id="21a98-109">You can select and delete multiple join lines at one time.</span></span>  
  
 <span data-ttu-id="21a98-110">Конструктор запросов и представлений удаляет линию соединения и изменяет инструкцию на [панели SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="21a98-110">The Query and View Designer removes the join line and alters the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a98-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="21a98-111">See Also</span></span>  
 <span data-ttu-id="21a98-112">[Автоматическое соединение таблиц &#40;визуальных инструментов для баз данных&#41;](join-tables-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="21a98-112">[Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span></span>  
 <span data-ttu-id="21a98-113">[Соединение таблиц вручную &#40;визуальных инструментов для баз данных&#41;](join-tables-manually-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="21a98-113">[Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="21a98-114">Запросы с соединениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="21a98-114">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
