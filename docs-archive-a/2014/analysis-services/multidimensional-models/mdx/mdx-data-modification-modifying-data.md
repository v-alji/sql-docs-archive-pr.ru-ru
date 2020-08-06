---
title: Изменение данных (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01df67471753922e3e7db39c56a9ed50aae900dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665143"
---
# <a name="modifying-data-mdx"></a><span data-ttu-id="55a63-102">Изменение данных (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="55a63-102">Modifying Data (MDX)</span></span>
  <span data-ttu-id="55a63-103">Наряду с использованием многомерных выражений для получения и обработки данных измерений и кубов можно использовать многомерные выражения для обновления и *обратной записи* данных измерений и кубов.</span><span class="sxs-lookup"><span data-stu-id="55a63-103">Besides using Multidimensional Expressions (MDX) to retrieve and handle data from dimensions and cubes, you can use MDX to update or *writeback* dimension and cube data.</span></span> <span data-ttu-id="55a63-104">Обновления могут быть как временными, например в случае гипотетического анализа «что, если...», так и постоянными, когда изменения должны происходить на основе анализа данных.</span><span class="sxs-lookup"><span data-stu-id="55a63-104">These updates can be temporary, as with speculative, or "what if", analysis, or permanent, as when changes must occur based upon data analysis.</span></span>  
  
 <span data-ttu-id="55a63-105">Данные могут обновляться на уровне измерения или куба.</span><span class="sxs-lookup"><span data-stu-id="55a63-105">Updates to data can occur at the dimension or cube level:</span></span>  
  
 <span data-ttu-id="55a63-106">**Обратная запись в измерение**</span><span class="sxs-lookup"><span data-stu-id="55a63-106">**Dimension writebacks**</span></span>  
 <span data-ttu-id="55a63-107">Для изменения данных измерения, доступного для записи, используется [Инструкция ALTER CUBE (многомерные выражения)](/sql/mdx/mdx-data-definition-alter-cube) , а для отражения операций удаления, создания и обновления значений атрибутов используется [Инструкция REFRESH CUBE (многомерные выражения)](/sql/mdx/mdx-data-definition-refresh-cube) .</span><span class="sxs-lookup"><span data-stu-id="55a63-107">You use the [ALTER CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-alter-cube) statement to change a write-enabled dimension's data and the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to reflect the deletion, creation, and updating of attribute values.</span></span> <span data-ttu-id="55a63-108">Кроме того, при помощи инструкции ALTER CUBE можно выполнять такие сложные операции, как удаление всего вложенного дерева в иерархии и продвижение потомков удаленного элемента.</span><span class="sxs-lookup"><span data-stu-id="55a63-108">You can also use the ALTER CUBE statement to perform complex operations, such as deleting a whole sub-tree in a hierarchy and promoting the children of a deleted member.</span></span>  
  
 <span data-ttu-id="55a63-109">**Обратная запись в куб**</span><span class="sxs-lookup"><span data-stu-id="55a63-109">**Cube writebacks**</span></span>  
 <span data-ttu-id="55a63-110">Для обновления данных куба, доступного для записи, используется инструкция [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) .</span><span class="sxs-lookup"><span data-stu-id="55a63-110">You use the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement to make updates to a write-enabled cube.</span></span> <span data-ttu-id="55a63-111">Инструкция UPDATE CUBE позволяет записать конкретное значение в кортеж.</span><span class="sxs-lookup"><span data-stu-id="55a63-111">The UPDATE CUBE statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="55a63-112">[Инструкция REFRESH CUBE (многомерные выражения)](/sql/mdx/mdx-data-definition-refresh-cube) используется для отражения обновленных данных в клиентском сеансе.</span><span class="sxs-lookup"><span data-stu-id="55a63-112">You use the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to refresh data in a client session with updated data from the server.</span></span>  
  
 <span data-ttu-id="55a63-113">Дополнительные сведения см. в разделе [Обратная запись в куб (многомерные выражения)](mdx-data-modification-using-cube-writebacks.md).</span><span class="sxs-lookup"><span data-stu-id="55a63-113">For more information, see [Using Cube Writebacks &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a63-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="55a63-114">See Also</span></span>  
 [<span data-ttu-id="55a63-115">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="55a63-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
