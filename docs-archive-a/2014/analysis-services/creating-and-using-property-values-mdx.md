---
title: Создание и использование значений свойств (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- property values [MDX]
- queries [MDX], property values
- MDX [Analysis Services], property values
- Multidimensional Expressions [Analysis Services], property values
ms.assetid: 0cafb269-03c8-4183-b6e9-220f071e4ef2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67eadc6bc2f0bf6f318f20ad42a5cc9e7a5afa5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665164"
---
# <a name="creating-and-using-property-values-mdx"></a><span data-ttu-id="1bbfd-102">Создание и использование значений свойств (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="1bbfd-102">Creating and Using Property Values (MDX)</span></span>
  <span data-ttu-id="1bbfd-103">Многомерные выражения поддерживают внутренние и заданные пользователем свойства для измерений, уровней, элементов и ячеек.</span><span class="sxs-lookup"><span data-stu-id="1bbfd-103">Multidimensional Expressions (MDX) supports intrinsic and user-defined properties for dimensions, levels, members, and cells.</span></span> <span data-ttu-id="1bbfd-104">Для отдельных ячеек внутренние свойства предоставляют уникальные имена, заголовки и даже форматирование и размер шрифта.</span><span class="sxs-lookup"><span data-stu-id="1bbfd-104">The intrinsic properties provide unique names, captions, and even formatting and font sizes for individual cells.</span></span> <span data-ttu-id="1bbfd-105">В то же время заданные пользователем свойства могут давать элементам дополнительные атрибуты практически любого типа.</span><span class="sxs-lookup"><span data-stu-id="1bbfd-105">User-defined properties, on the other hand, can provide almost any kind of additional attribute to members.</span></span>  
  
 <span data-ttu-id="1bbfd-106">Встроенные и заданные пользователем свойства доступны на следующих уровнях:</span><span class="sxs-lookup"><span data-stu-id="1bbfd-106">Intrinsic and user-defined properties are available at the following levels:</span></span>  
  
 <span data-ttu-id="1bbfd-107">**Свойства элемента**</span><span class="sxs-lookup"><span data-stu-id="1bbfd-107">**Member properties**</span></span>  
 <span data-ttu-id="1bbfd-108">Свойства элементов включают основные сведения о каждом элементе каждого кортежа.</span><span class="sxs-lookup"><span data-stu-id="1bbfd-108">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="1bbfd-109">К таким основным сведениям относятся имя элемента, родительский уровень, число потомков и т. д.</span><span class="sxs-lookup"><span data-stu-id="1bbfd-109">This basic information includes the member name, parent level, the number of children, and so on.</span></span>  
  
 <span data-ttu-id="1bbfd-110">Дополнительные сведения о свойствах элементов и их применении см. в разделе [Использование свойств элементов (многомерные выражения)](multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1bbfd-110">For information about member properties and how to use them, see [Using Member Properties &#40;MDX&#41;](multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
 <span data-ttu-id="1bbfd-111">**Свойства ячеек**</span><span class="sxs-lookup"><span data-stu-id="1bbfd-111">**Cell properties**</span></span>  
 <span data-ttu-id="1bbfd-112">Свойства ячеек содержат сведения о содержимом и формате ячеек в многомерном источнике данных, таком как куб.</span><span class="sxs-lookup"><span data-stu-id="1bbfd-112">Cell properties contain information about the content and format of cells in a multidimensional data source, such as a cube.</span></span>  
  
 <span data-ttu-id="1bbfd-113">Дополнительные сведения о свойствах ячеек и их применении см. в разделе [Использование свойств ячеек (многомерные выражения)](multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1bbfd-113">For more information about cell properties and how to use them, see [Using Cell Properties &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbfd-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bbfd-114">See Also</span></span>  
 [<span data-ttu-id="1bbfd-115">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="1bbfd-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  
