---
title: Определяемые пользователем свойства элементов (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- custom member properties [MDX]
ms.assetid: b64cc581-e784-42c4-bec8-932abd687423
author: minewiskan
ms.author: owend
ms.openlocfilehash: 75e5df5a0677ee205b5517f4c7ca89a390426971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730957"
---
# <a name="user-defined-member-properties-mdx"></a><span data-ttu-id="2704b-102">Пользовательские свойства элементов (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="2704b-102">User-Defined Member Properties (MDX)</span></span>
  <span data-ttu-id="2704b-103">Определяемые пользователем свойства элементов можно добавить к конкретному именованному уровню измерения в виде связей атрибутов.</span><span class="sxs-lookup"><span data-stu-id="2704b-103">User-defined member properties can be added to a specific named level in a dimension as attribute relationships.</span></span> <span data-ttu-id="2704b-104">Определяемые пользователем свойства элементов нельзя добавлять к уровню иерархии `(All)` или в саму иерархию.</span><span class="sxs-lookup"><span data-stu-id="2704b-104">User-defined member properties cannot be added to the `(All)` level of a hierarchy, or to the hierarchy itself.</span></span>  
  
## <a name="creating-user-defined-member-properties"></a><span data-ttu-id="2704b-105">Создание определяемых пользователем  свойств элементов</span><span class="sxs-lookup"><span data-stu-id="2704b-105">Creating User-Defined Member Properties</span></span>  
 <span data-ttu-id="2704b-106">Определяемые пользователем свойства элементов можно добавлять в серверные измерения или кубы при помощи пользовательского интерфейса или программно.</span><span class="sxs-lookup"><span data-stu-id="2704b-106">User-defined member properties can be added to server-based dimensions or cubes either through the user interface or programmatically:</span></span>  
  
-   <span data-ttu-id="2704b-107">Для добавления определяемых пользователем свойств элементов через пользовательский интерфейс служит конструктор измерений в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2704b-107">To add user-defined member properties through the user interface, you use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2704b-108">Дополнительные сведения см. в разделе [Определение связей атрибутов](../attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="2704b-108">For more information, see [Define Attribute Relationships](../attribute-relationships-define.md).</span></span>  
  
-   <span data-ttu-id="2704b-109">Для программного создания определяемых пользователем свойств элементов приложение может использовать либо объекты AMO, либо комбинацию XML для аналитики и языка ASSL.</span><span class="sxs-lookup"><span data-stu-id="2704b-109">To add user-defined member properties programmatically, your application can use either Analysis Manager Objects (AMO) or a combination of XML for Analysis (XMLA) and Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="2704b-110">Дополнительные сведения см. в разделе [Связи атрибутов](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="2704b-110">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
## <a name="retrieving-user-defined-member-properties"></a><span data-ttu-id="2704b-111">Извлечение определяемых пользователем свойств элементов</span><span class="sxs-lookup"><span data-stu-id="2704b-111">Retrieving User-Defined Member Properties</span></span>  
 <span data-ttu-id="2704b-112">Получить определяемые пользователем свойства элементов можно с помощью `PROPERTIES` ключевого слова или функции [свойств](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="2704b-112">You can retrieve user-defined member properties using either the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
### <a name="using-the-properties-keyword-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="2704b-113">Получение определяемых пользователем свойств элементов с помощью ключевого слова PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="2704b-113">Using the PROPERTIES Keyword to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="2704b-114">Для получения определяемых пользователем свойств элементов применяется практически такой же синтаксис, как и при обращении к внутренним свойствам элементов.</span><span class="sxs-lookup"><span data-stu-id="2704b-114">The syntax that retrieves user-defined member properties is similar to that used to retrieve intrinsic level member properties, as shown in the following syntax:</span></span>  
  
 `DIMENSION PROPERTIES [Dimension.]Level.<Custom_Member_Property>`  
  
 <span data-ttu-id="2704b-115">Ключевое слово `PROPERTIES` указывается после выражения набора в определении оси.</span><span class="sxs-lookup"><span data-stu-id="2704b-115">The `PROPERTIES` keyword appears after the set expression of the axis specification.</span></span> <span data-ttu-id="2704b-116">Например, в следующем многомерном запросе, извлекающем определяемых пользователем свойства `List Price` и `Dealer Price`, ключевое слово `PROPERTIES` находится после выражения набора, определяющего продукты, проданные в январе.</span><span class="sxs-lookup"><span data-stu-id="2704b-116">For example, the following MDX query the `PROPERTIES` keyword retrieves the `List Price` and `Dealer Price` user-defined member properties and appears after the set expression that identifies the products sold in January:</span></span>  
  
```  
SELECT   
   CROSSJOIN([Ship Date].[Calendar].[Calendar Year].Members,   
             [Measures].[Sales Amount]) ON COLUMNS,  
   NON EMPTY Product.Product.MEMBERS  
   DIMENSION PROPERTIES   
              Product.Product.[List Price],  
              Product.Product.[Dealer Price]  ON ROWS  
FROM [Adventure Works]  
WHERE ([Date].[Month of Year].[January])   
```  
  
### <a name="using-the-properties-function-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="2704b-117">Получение определяемых пользователем свойств элементов с помощью функции Properties</span><span class="sxs-lookup"><span data-stu-id="2704b-117">Using the Properties Function to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="2704b-118">В качестве альтернативы к пользовательским свойствам элементов можно обращаться при помощи функции `Properties`.</span><span class="sxs-lookup"><span data-stu-id="2704b-118">Alternatively, you can access custom member properties with the `Properties` function.</span></span> <span data-ttu-id="2704b-119">Например, в следующем многомерном запросе ключевое слово `WITH` применяется для создания вычисляемого элемента, состоящего из свойства элемента `List Price`.</span><span class="sxs-lookup"><span data-stu-id="2704b-119">For example, the following MDX query uses the `WITH` keyword to create a calculated member consisting of the `List Price` member property:</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Product List Price] AS  
   [Product].[Product].CurrentMember.Properties("List Price")  
SELECT   
   [Measures].[Product List Price] on COLUMNS,  
   [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="2704b-120">Дополнительные сведения о создании вычисляемых элементов см. в разделе [Создание вычисляемых элементов в многомерных выражениях (многомерные выражения)](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="2704b-120">For more information about building calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2704b-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="2704b-121">See Also</span></span>  
 <span data-ttu-id="2704b-122">[Использование свойств элементов &#40;&#41;многомерных выражений](mdx-member-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2704b-122">[Using Member Properties &#40;MDX&#41;](mdx-member-properties.md) </span></span>  
 [<span data-ttu-id="2704b-123">Properties (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="2704b-123">Properties &#40;MDX&#41;</span></span>](/sql/mdx/properties-mdx)  
  
  
