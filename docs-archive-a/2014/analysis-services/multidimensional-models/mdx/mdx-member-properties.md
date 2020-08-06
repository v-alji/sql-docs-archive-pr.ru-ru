---
title: Использование свойств элементов (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DIMENSION PROPERTIES keyword
- Properties function
- member properties [MDX]
- members [MDX], properties
ms.assetid: 26b5ad08-3799-4a5e-89f3-dca25e637d45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5b7fdf989fc23ea70be7d7863f5d4c6ac0b61d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730954"
---
# <a name="using-member-properties-mdx"></a><span data-ttu-id="f6d19-102">Использование свойств элементов (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="f6d19-102">Using Member Properties (MDX)</span></span>
  <span data-ttu-id="f6d19-103">Свойства элементов включают основные сведения о каждом элементе каждого кортежа.</span><span class="sxs-lookup"><span data-stu-id="f6d19-103">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="f6d19-104">К таким основным сведениям относятся имя элемента, родительский уровень, число потомков и т. д.</span><span class="sxs-lookup"><span data-stu-id="f6d19-104">This basic information includes the member name, parent level, the number of children, and so on.</span></span> <span data-ttu-id="f6d19-105">Свойства элемента доступны всем элементам данного уровня.</span><span class="sxs-lookup"><span data-stu-id="f6d19-105">Member properties are available for all members at a given level.</span></span> <span data-ttu-id="f6d19-106">С точки зрения организации свойства элемента рассматриваются как организованные по измерениям данные, хранимые в одном измерении.</span><span class="sxs-lookup"><span data-stu-id="f6d19-106">In terms of organization, member properties are treated as dimensionally organized data, stored on a single dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6d19-107">В [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]свойства элемента рассматриваются как связь атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f6d19-107">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], member properties are know as attribute relationships.</span></span> <span data-ttu-id="f6d19-108">Дополнительные сведения см. в разделе [Связи атрибутов](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f6d19-108">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
 <span data-ttu-id="f6d19-109">Существуют *внутренние* и *пользовательские*свойства:</span><span class="sxs-lookup"><span data-stu-id="f6d19-109">Member properties are either *intrinsic* or *custom*:</span></span>  
  
 <span data-ttu-id="f6d19-110">Внутренние свойства элементов</span><span class="sxs-lookup"><span data-stu-id="f6d19-110">Intrinsic member properties</span></span>  
 <span data-ttu-id="f6d19-111">Все элементы поддерживают внутренние свойства элементов, такие как форматированное значение элемента, а измерения и уровни обеспечивают еще и дополнительные внутренние свойства измерения и уровня элементов, например идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="f6d19-111">All members support intrinsic member properties, such as the formatted value of a member, while dimensions and levels supply additional intrinsic dimension and level member properties, such as the ID of a member.</span></span>  
  
 <span data-ttu-id="f6d19-112">Дополнительные сведения см. в разделе [Внутренние свойства элементов (многомерные выражения)](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f6d19-112">For more information, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
 <span data-ttu-id="f6d19-113">Пользовательские свойства элементов</span><span class="sxs-lookup"><span data-stu-id="f6d19-113">User-defined member properties</span></span>  
 <span data-ttu-id="f6d19-114">С элементами часто связаны дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="f6d19-114">Members often have additional properties associated with them.</span></span> <span data-ttu-id="f6d19-115">Например, каждому товару уровня «Продукты» могут быть присвоены свойства SKU, SRP, Weight и Volume.</span><span class="sxs-lookup"><span data-stu-id="f6d19-115">For example, the Products level may offer the SKU, SRP, Weight, and Volume properties for each product.</span></span> <span data-ttu-id="f6d19-116">Эти свойства не являются элементами, они содержат дополнительные сведения об элементах на уровне «Продукты».</span><span class="sxs-lookup"><span data-stu-id="f6d19-116">These properties are not members, but contain additional information about members at the Products level.</span></span>  
  
 <span data-ttu-id="f6d19-117">Дополнительные сведения см. в разделе [Пользовательские свойства элементов (многомерные выражения)](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f6d19-117">For more information, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
 <span data-ttu-id="f6d19-118">Как встроенные, так и определяемые пользователем свойства элементов можно получить с помощью `PROPERTIES` ключевого слова или функции [свойств](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="f6d19-118">Both intrinsic and user-defined member properties can be retrieved through the use of the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
## <a name="using-the-properties-keyword"></a><span data-ttu-id="f6d19-119">Использование ключевого слова PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="f6d19-119">Using the PROPERTIES Keyword</span></span>  
 <span data-ttu-id="f6d19-120">Ключевое слово `PROPERTIES` указывает свойства элементов, которые будут использоваться для данной оси измерения.</span><span class="sxs-lookup"><span data-stu-id="f6d19-120">The `PROPERTIES` keyword specifies the member properties that are to be used for a given axis dimension.</span></span> <span data-ttu-id="f6d19-121">`PROPERTIES`Ключевое слово скрыто в `<axis specification>` предложении инструкции многомерных выражений [SELECT](/sql/mdx/mdx-data-manipulation-select) :</span><span class="sxs-lookup"><span data-stu-id="f6d19-121">The `PROPERTIES` keyword is buried within the `<axis specification>` clause of the MDX [SELECT](/sql/mdx/mdx-data-manipulation-select) statement:</span></span>  
  
```  
SELECT [<axis_specification>  
       [, <axis_specification>...]]  
  FROM [<cube_specification>]  
[WHERE [<slicer_specification>]]  
```  
  
 <span data-ttu-id="f6d19-122">Предложение `<axis_specification>` содержит необязательное предложение `<dim_props>` , как видно в следующем синтаксисе:</span><span class="sxs-lookup"><span data-stu-id="f6d19-122">The `<axis_specification>` clause includes an optional `<dim_props>` clause, as shown in the following syntax:</span></span>  
  
```  
<axis_specification> ::= <set> [<dim_props>] ON <axis_name>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f6d19-123">Дополнительные сведения о значениях `<set>` и `<axis_name>` см. в разделе [Определение содержимого оси запроса (многомерные выражения)](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="f6d19-123">For more information about the `<set>` and `<axis_name>` values, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
 <span data-ttu-id="f6d19-124">Предложение `<dim_props>` позволяет обратиться с запросом к свойствам измерения, уровня и элементов, используя ключевое слово `PROPERTIES`.</span><span class="sxs-lookup"><span data-stu-id="f6d19-124">The `<dim_props>` clause lets you query dimension, level, and member properties using the `PROPERTIES` keyword.</span></span> <span data-ttu-id="f6d19-125">Следующий синтаксис показывает формат предложения `<dim_props>` :</span><span class="sxs-lookup"><span data-stu-id="f6d19-125">The following syntax shows the formatting of the `<dim_props>` clause:</span></span>  
  
```  
<dim_props> ::= [DIMENSION] PROPERTIES <property> [,<property>...]  
```  
  
 <span data-ttu-id="f6d19-126">Синтаксическая конструкция `<property>` изменяется в зависимости от свойства, к которому обращен запрос.</span><span class="sxs-lookup"><span data-stu-id="f6d19-126">The breakdown of the `<property>` syntax varies depending on the property that you are querying:</span></span>  
  
-   <span data-ttu-id="f6d19-127">Чувствительным к контексту внутренним свойствам элементов должно предшествовать имя измерения или уровня.</span><span class="sxs-lookup"><span data-stu-id="f6d19-127">Context sensitive intrinsic member properties must be preceded with the name of the dimension or level.</span></span> <span data-ttu-id="f6d19-128">Однако нечувствительные к контексту внутренние свойства элементов не могут быть определены именем измерения или уровня.</span><span class="sxs-lookup"><span data-stu-id="f6d19-128">However, non-context sensitive intrinsic member properties cannot be qualified by the dimension or level name.</span></span> <span data-ttu-id="f6d19-129">Дополнительные сведения об использовании `PROPERTIES` ключевого слова с внутренними свойствами элементов см. в разделе [внутренние свойства элементов &#40;&#41;многомерных выражений ](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f6d19-129">For more information about how to use the `PROPERTIES` keyword with intrinsic member properties, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
-   <span data-ttu-id="f6d19-130">Заданным пользователем внутренним свойствам элемента должно предшествовать имя уровня, на котором они располагаются.</span><span class="sxs-lookup"><span data-stu-id="f6d19-130">User-defined member properties should be preceded by the name of the level in which they reside.</span></span> <span data-ttu-id="f6d19-131">Дополнительные сведения об использовании `PROPERTIES` ключевого слова с определяемыми пользователем свойствами элементов см. в разделе [определяемые пользователем свойства элементов &#40;&#41;многомерных выражений ](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f6d19-131">For more information about how to use the `PROPERTIES` keyword with user-defined member properties, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d19-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6d19-132">See Also</span></span>  
 [<span data-ttu-id="f6d19-133">Создание и использование значений свойств (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="f6d19-133">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)  
  
  
