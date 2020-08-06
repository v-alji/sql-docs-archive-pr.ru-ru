---
title: Настройка свойств меры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- additivity [Analysis Services]
- ID property
- ErrorConfiguration property
- AggregateFunction property
- DisplayFolder property
- IgnoreUnrelatedDimensions property
- FormatString property
- Description property
- semiadditive
- properties [Analysis Services], measure groups
- aggregate functions [Analysis Services]
- DataType property
- ProcessingMode property
- MeasureExpression property
- AggregationPrefix property
- Visible property
- properties [Analysis Services], measures
- StorageLocation property
- StorageMode property
- formats [Analysis Services], measures
- Source property
- aggregations [Analysis Services], measures
- measures [Analysis Services], properties
- nonadditive [Analysis Services]
- Name property
- measures [Analysis Services], display formats
- ProcessingPriority property
- measure groups [Analysis Services], properties
- Type property
- ProactiveCaching property
ms.assetid: e9031078-c4f5-4986-b0c9-4d064b622ab7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ca291a5181fdb3f7a88845431d61ffd7a1034eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737109"
---
# <a name="configure-measure-properties"></a><span data-ttu-id="817f0-102">Настройка свойств мер</span><span class="sxs-lookup"><span data-stu-id="817f0-102">Configure Measure Properties</span></span>
  <span data-ttu-id="817f0-103">Меры имеют свойства, позволяющие определять и управлять их работой и отображением для пользователей.</span><span class="sxs-lookup"><span data-stu-id="817f0-103">Measures have properties that enable you to define how the measures function and to control how the measures appear to users.</span></span>  
  
 <span data-ttu-id="817f0-104">Свойства в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] можно задать при создании или изменении куба или меры.</span><span class="sxs-lookup"><span data-stu-id="817f0-104">You can set properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] when creating or editing a cube or measure.</span></span> <span data-ttu-id="817f0-105">Можно также задать их программным способом с помощью многомерных выражений или объектов AMO.</span><span class="sxs-lookup"><span data-stu-id="817f0-105">You can also set them programmatically, using MDX or AMO.</span></span> <span data-ttu-id="817f0-106">Дополнительные сведения см. в разделах [Создание мер и групп мер в многомерных моделях](create-measures-and-measure-groups-in-multidimensional-models.md), [Инструкция CREATE MEMBER (многомерные выражения)](/sql/mdx/mdx-data-definition-create-member) и [Программирование основных объектов AMO OLAP](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="817f0-106">See [Create Measures and Measure Groups in Multidimensional Models](create-measures-and-measure-groups-in-multidimensional-models.md) or [CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) or [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects) for details.</span></span>  
  
## <a name="measure-properties"></a><span data-ttu-id="817f0-107">Свойства мер</span><span class="sxs-lookup"><span data-stu-id="817f0-107">Measure Properties</span></span>  
 <span data-ttu-id="817f0-108">Меры наследуют определенные свойства у группы мер, элементами которых они являются, если только эти свойства не переопределены на уровне мер.</span><span class="sxs-lookup"><span data-stu-id="817f0-108">Measures inherit certain properties from the measure group of which they are a member, unless those properties are overridden at the measure level.</span></span> <span data-ttu-id="817f0-109">Свойства мер определяют статистическое вычисление, тип данных, отображаемые для пользователей имена, папку отображения, строку форматирования, выражения меры, базовые исходные столбцы и видимость для пользователей.</span><span class="sxs-lookup"><span data-stu-id="817f0-109">Measure properties determine how a measure is aggregated, its data type, the name that is displayed to the user, the display folder in which the measure will appear, its format string, any measure expression, the underlying source column, and its visibility to users.</span></span>  
  
|<span data-ttu-id="817f0-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="817f0-110">Property</span></span>|<span data-ttu-id="817f0-111">Определение</span><span class="sxs-lookup"><span data-stu-id="817f0-111">Definition</span></span>|  
|--------------|----------------|  
|`AggregateFunction`|<span data-ttu-id="817f0-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="817f0-112">Required.</span></span> <span data-ttu-id="817f0-113">Определяет, как выполняется статистическое вычисление мер.</span><span class="sxs-lookup"><span data-stu-id="817f0-113">Determines how measures are aggregated.</span></span> <span data-ttu-id="817f0-114">`Sum` — это агрегирование по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="817f0-114">`Sum` is the default aggregation.</span></span> <span data-ttu-id="817f0-115">Описание каждой функции см. в разделе [Use Aggregate Functions](use-aggregate-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="817f0-115">For more information, see [Use Aggregate Functions](use-aggregate-functions.md) for a description of each function.</span></span>|  
|`DataType`|<span data-ttu-id="817f0-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="817f0-116">Required.</span></span> <span data-ttu-id="817f0-117">Указывает тип данных столбца базовой таблицы фактов, к которым привязана мера.</span><span class="sxs-lookup"><span data-stu-id="817f0-117">Specifies the data type of the column in the underlying fact table to which the measure is bound.</span></span> <span data-ttu-id="817f0-118">Это значение наследуется из исходного столбца по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="817f0-118">This value is inherited from the source column by default.</span></span>|  
|`Description`|<span data-ttu-id="817f0-119">Содержит описание меры, которое может быть видно в клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="817f0-119">Provides a description of the measure, which may be exposed in client applications.</span></span>|  
|`DisplayFolder`|<span data-ttu-id="817f0-120">Указывает папку отображения, в которой будет представлена мера при подключении пользователя к кубу.</span><span class="sxs-lookup"><span data-stu-id="817f0-120">Specifies the folder in which the measure will appear when users connect to the cube.</span></span> <span data-ttu-id="817f0-121">Если куб содержит множество мер, папки отображения позволяют разбить их по категориям мер, упростив доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="817f0-121">When a cube has many measures, you can use display folders to categorize the measures and improve the user browsing experience.</span></span>|  
|`FormatString`|<span data-ttu-id="817f0-122">Можно выбрать формат, используемый для отображения значений меры пользователям, используя свойство `FormatString` меры.</span><span class="sxs-lookup"><span data-stu-id="817f0-122">You can select the format that is used to display measure values to users by using the `FormatString` property of the measure.</span></span><br /><br /> <span data-ttu-id="817f0-123">Список форматов отображения представлен в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], но можно указать множество дополнительных форматов, не содержащихся в этом списке.</span><span class="sxs-lookup"><span data-stu-id="817f0-123">Although a list of display formats is provided in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can specify many additional formats that are not in the list.</span></span> <span data-ttu-id="817f0-124">Можно указать любой именованный или определенный пользователем формат, допустимый в языке Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="817f0-124">You can specify any named or user-defined format that is valid in Microsoft Visual Basic.</span></span>|  
|`ID`|<span data-ttu-id="817f0-125">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="817f0-125">Required.</span></span> <span data-ttu-id="817f0-126">Отображает уникальный идентификатор (ID) меры.</span><span class="sxs-lookup"><span data-stu-id="817f0-126">Displays the unique identifier (ID) of the measure.</span></span> <span data-ttu-id="817f0-127">Это свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="817f0-127">This property is read-only.</span></span>|  
|`MeasureExpression`|<span data-ttu-id="817f0-128">Указывает ограниченное многомерное выражение, определяющее значение меры.</span><span class="sxs-lookup"><span data-stu-id="817f0-128">Specifies a constrained MDX expression defining the value of the measure.</span></span> <span data-ttu-id="817f0-129">Выражение вычисляется на конечном уровне до агрегирования и позволяет получить взвешенное значение.</span><span class="sxs-lookup"><span data-stu-id="817f0-129">The expression is evaluated at the leaf level before being aggregated, and allows for weighting of a value.</span></span> <span data-ttu-id="817f0-130">Например, конвертация валют, где объем продаж взвешен с учетом обменного курса.</span><span class="sxs-lookup"><span data-stu-id="817f0-130">For example, in currency conversion where a sales amount is weighted by the exchange rate.</span></span>|  
|`Name`|<span data-ttu-id="817f0-131">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="817f0-131">Required.</span></span> <span data-ttu-id="817f0-132">Имя меры.</span><span class="sxs-lookup"><span data-stu-id="817f0-132">Specifies the name of the measure.</span></span>|  
|`Source`|<span data-ttu-id="817f0-133">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="817f0-133">Required.</span></span> <span data-ttu-id="817f0-134">Столбец в представлении источника данных, к которому привязана мера.</span><span class="sxs-lookup"><span data-stu-id="817f0-134">Specifies the column in the data source view to which the measure is bound.</span></span> <span data-ttu-id="817f0-135">См. раздел [Источники данных и привязки (многомерные службы SSAS)](data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="817f0-135">See [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span></span>|  
|`Visible`|<span data-ttu-id="817f0-136">Определяет видимость меры в клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="817f0-136">Determines the visibility of the measure in client applications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="817f0-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="817f0-137">See Also</span></span>  
 <span data-ttu-id="817f0-138">[Настройка свойств группы мер](configure-measure-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="817f0-138">[Configure Measure Group Properties](configure-measure-group-properties.md) </span></span>  
 [<span data-ttu-id="817f0-139">Изменение мер</span><span class="sxs-lookup"><span data-stu-id="817f0-139">Modifying Measures</span></span>](../lesson-3-1-modifying-measures.md)  
  
  
