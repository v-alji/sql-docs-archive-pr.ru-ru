---
title: Создание мер в многомерных выражениях | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0347835-4983-4d26-acbb-6c8fae7992bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac49d37f11584bfbc5d372241056da39e7dd8c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658454"
---
# <a name="building-measures-in-mdx"></a><span data-ttu-id="373fd-102">Построение мер в многомерных выражениях</span><span class="sxs-lookup"><span data-stu-id="373fd-102">Building Measures in MDX</span></span>
  <span data-ttu-id="373fd-103">В многомерных выражениях мера — это именованное DAX-выражение, которое разрешается путем вычисления и возвращает значение в табличную модель.</span><span class="sxs-lookup"><span data-stu-id="373fd-103">In Multidimensional Expressions (MDX), a measure is a named DAX expression that is resolved by calculating the expression to return a value in a Tabular Model.</span></span> <span data-ttu-id="373fd-104">В этом определении кроется огромный потенциал.</span><span class="sxs-lookup"><span data-stu-id="373fd-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="373fd-105">Создание и использование мер в многомерных запросах дает широкие возможности для табличных данных.</span><span class="sxs-lookup"><span data-stu-id="373fd-105">The ability to construct and use measures in an MDX query provides a great deal of manipulation capability for tabular data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="373fd-106">Меры могут быть определены только в табличных моделях. Если база данных работает в режиме многомерных выражений, создание мер будет формировать ошибку.</span><span class="sxs-lookup"><span data-stu-id="373fd-106">Measures can only be defined in tabular models; if your database is set in multidimensional mode, creating a measure will generate an error</span></span>  
  
 <span data-ttu-id="373fd-107">Чтобы создать меру, которая определена как часть запроса многомерных выражений, с областью, ограниченной этим запросом, используется ключевое слово WITH.</span><span class="sxs-lookup"><span data-stu-id="373fd-107">To create a measure that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="373fd-108">Затем меру можно использовать внутри инструкции MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="373fd-108">You can then use the measure within an MDX SELECT statement.</span></span> <span data-ttu-id="373fd-109">Этот подход позволяет изменять вычисляемый элемент, созданный при помощи ключевого слова WITH, не изменяя инструкцию SELECT.</span><span class="sxs-lookup"><span data-stu-id="373fd-109">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span> <span data-ttu-id="373fd-110">Однако в многомерных выражениях ссылаться на меру нужно не так, как в DAX-выражениях; для ссылки на эту меру ее нужно рассматривать как элемент измерения [Measures], как в следующем примере с использованием многомерных выражений:</span><span class="sxs-lookup"><span data-stu-id="373fd-110">However, in MDX you reference the measure in a different way than when in DAX expressions; to reference the measure you name it as a member of the [Measures] dimension, see the following MDX example:</span></span>  
  
```  
with measure  'Sales Territory'[Total Sales Amount] = SUM('Internet Sales'[Sales Amount]) + SUM('Reseller Sales'[Sales Amount])  
select measures.[Total Sales Amount] on columns  
     ,NON EMPTY [Date].[Calendar Year].children on rows  
from [Model]  
  
```  
  
 <span data-ttu-id="373fd-111">Возвращает следующие данные при выполнении:</span><span class="sxs-lookup"><span data-stu-id="373fd-111">It will return the following data when executed:</span></span>  
  
||<span data-ttu-id="373fd-112">Total Sales Amount</span><span class="sxs-lookup"><span data-stu-id="373fd-112">Total Sales Amount</span></span>||  
|-|------------------------|-|  
|<span data-ttu-id="373fd-113">2001</span><span class="sxs-lookup"><span data-stu-id="373fd-113">2001</span></span>|<span data-ttu-id="373fd-114">11331808.96</span><span class="sxs-lookup"><span data-stu-id="373fd-114">11331808.96</span></span>||  
|<span data-ttu-id="373fd-115">2002</span><span class="sxs-lookup"><span data-stu-id="373fd-115">2002</span></span>|<span data-ttu-id="373fd-116">30674773.18</span><span class="sxs-lookup"><span data-stu-id="373fd-116">30674773.18</span></span>||  
|<span data-ttu-id="373fd-117">2003</span><span class="sxs-lookup"><span data-stu-id="373fd-117">2003</span></span>|<span data-ttu-id="373fd-118">41993729.72</span><span class="sxs-lookup"><span data-stu-id="373fd-118">41993729.72</span></span>||  
|<span data-ttu-id="373fd-119">2004</span><span class="sxs-lookup"><span data-stu-id="373fd-119">2004</span></span>|<span data-ttu-id="373fd-120">25808962.34</span><span class="sxs-lookup"><span data-stu-id="373fd-120">25808962.34</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="373fd-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="373fd-121">See Also</span></span>  
 <span data-ttu-id="373fd-122">[Инструкция CREATE MEMBER &#40;&#41;многомерных выражений](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="373fd-122">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="373fd-123">[Ссылка на функцию многомерных выражений &#40;&#41;многомерных выражений](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="373fd-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="373fd-124">Инструкция SELECT (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="373fd-124">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
