---
title: Связи атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- member properties [Analysis Services], attribute relationships
- security [Analysis Services], properties
- PROPERTIES keyword
- storage [Analysis Services], attribute relationships
- natural hierarchies [Analysis Services]
- dimensions [Analysis Services], member properties
- queries [MDX], attribute relationships
- user-defined hierarchies [Analysis Services]
- attributes [Analysis Services], relationships
- member properties [Analysis Services]
- members [Analysis Services], attribute relationships
- storing data [Analysis Services], attribute relationships
- relationships [Analysis Services], attributes
ms.assetid: 2491422a-4cf5-4b23-b6ab-289222b22ce8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 122638a2728a8a85ee58661196797383da20eef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733226"
---
# <a name="attribute-relationships"></a><span data-ttu-id="e6d17-102">можно изменить расположение фигур на вкладке</span><span class="sxs-lookup"><span data-stu-id="e6d17-102">Attribute Relationships</span></span>
  <span data-ttu-id="e6d17-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] атрибуты в пределах измерения всегда связаны напрямую или косвенно с ключевым атрибутом.</span><span class="sxs-lookup"><span data-stu-id="e6d17-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes within a dimension are always related either directly or indirectly to the key attribute.</span></span> <span data-ttu-id="e6d17-104">Когда измерение определяется по схеме «звезда», где все атрибуты измерения наследуются из одной реляционной таблицы, то связи между ключевыми и не ключевыми атрибутами определяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="e6d17-104">When you define a dimension based on a star schema, which is where all dimension attributes are derived from the same relational table, an attribute relationship is automatically defined between the key attribute and each non-key attribute of the dimension.</span></span> <span data-ttu-id="e6d17-105">Когда измерение определяется по схеме «снежинка», где атрибуты измерения наследуются от разных реляционных таблиц, связи атрибутов автоматически определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e6d17-105">When you define a dimension based on a snowflake schema, which is where dimension attributes are derived from multiple related tables, an attribute relationship is automatically defined as follows:</span></span>  
  
-   <span data-ttu-id="e6d17-106">Между ключевым атрибутом и каждым не ключевым атрибутом, привязанным к столбцу главной таблицы измерения.</span><span class="sxs-lookup"><span data-stu-id="e6d17-106">Between the key attribute and each non-key attribute bound to columns in the main dimension table.</span></span>  
  
-   <span data-ttu-id="e6d17-107">Между ключевым атрибутом и атрибутами, привязанными к внешнему ключу вспомогательной таблицы, которая связывает таблицы базового измерения.</span><span class="sxs-lookup"><span data-stu-id="e6d17-107">Between the key attribute and the attribute bound to the foreign key in the secondary table that links the underlying dimension tables.</span></span>  
  
-   <span data-ttu-id="e6d17-108">Между атрибутом, привязанным к внешнему ключу вспомогательной таблицы, и каждым не ключевым атрибутом, привязанным к столбцам вспомогательной таблицы.</span><span class="sxs-lookup"><span data-stu-id="e6d17-108">Between the attribute bound to foreign key in the secondary table and each non-key attribute bound to columns from the secondary table.</span></span>  
  
 <span data-ttu-id="e6d17-109">Однако по ряду причин может понадобиться изменить связи атрибутов, определенные по умолчанию,</span><span class="sxs-lookup"><span data-stu-id="e6d17-109">However, there are a number of reasons why you might want to change these default attribute relationships.</span></span> <span data-ttu-id="e6d17-110">например чтобы определить естественную иерархию, пользовательский порядок сортировки или степень гранулярности измерения на основе неключевого атрибута.</span><span class="sxs-lookup"><span data-stu-id="e6d17-110">For example, you might want to define a natural hierarchy, a custom sort order, or dimension granularity based on a non-key attribute.</span></span> <span data-ttu-id="e6d17-111">Дополнительные сведения см. в разделе [Справочник по свойствам атрибутов измерения](../multidimensional-models/dimension-attribute-properties-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e6d17-111">For more information, see [Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6d17-112">Связи атрибутов называются в языке многомерных выражений свойствами элементов.</span><span class="sxs-lookup"><span data-stu-id="e6d17-112">Attribute relationships are known in Multidimensional Expressions (MDX) as member properties.</span></span>  
  
## <a name="natural-hierarchy-relationships"></a><span data-ttu-id="e6d17-113">Связи естественной иерархии</span><span class="sxs-lookup"><span data-stu-id="e6d17-113">Natural Hierarchy Relationships</span></span>  
 <span data-ttu-id="e6d17-114">Иерархия является естественной, когда каждый атрибут пользовательской иерархии имеет связь типа «один ко многим» с атрибутом, находящимся непосредственно под ним.</span><span class="sxs-lookup"><span data-stu-id="e6d17-114">A hierarchy is a natural hierarchy when each attribute included in the user-defined hierarchy has a one to many relationship with the attribute immediately below it.</span></span> <span data-ttu-id="e6d17-115">Допустим, измерение Customer основано на реляционной исходной таблице, содержащей восемь столбцов:</span><span class="sxs-lookup"><span data-stu-id="e6d17-115">For example, consider a Customer dimension based on a relational source table with eight columns:</span></span>  
  
-   <span data-ttu-id="e6d17-116">CustomerKey</span><span class="sxs-lookup"><span data-stu-id="e6d17-116">CustomerKey</span></span>  
  
-   <span data-ttu-id="e6d17-117">CustomerName</span><span class="sxs-lookup"><span data-stu-id="e6d17-117">CustomerName</span></span>  
  
-   <span data-ttu-id="e6d17-118">возраст;</span><span class="sxs-lookup"><span data-stu-id="e6d17-118">Age</span></span>  
  
-   <span data-ttu-id="e6d17-119">пол;</span><span class="sxs-lookup"><span data-stu-id="e6d17-119">Gender</span></span>  
  
-   <span data-ttu-id="e6d17-120">Email</span><span class="sxs-lookup"><span data-stu-id="e6d17-120">Email</span></span>  
  
-   <span data-ttu-id="e6d17-121">Город</span><span class="sxs-lookup"><span data-stu-id="e6d17-121">City</span></span>  
  
-   <span data-ttu-id="e6d17-122">Country</span><span class="sxs-lookup"><span data-stu-id="e6d17-122">Country</span></span>  
  
-   <span data-ttu-id="e6d17-123">Регион</span><span class="sxs-lookup"><span data-stu-id="e6d17-123">Region</span></span>  
  
 <span data-ttu-id="e6d17-124">Соответствующее измерение служб Analysis Services содержит семь атрибутов:</span><span class="sxs-lookup"><span data-stu-id="e6d17-124">The corresponding Analysis Services dimension has seven attributes:</span></span>  
  
-   <span data-ttu-id="e6d17-125">Customer (основанное на CustomerKey и CustomerName)</span><span class="sxs-lookup"><span data-stu-id="e6d17-125">Customer (based on CustomerKey, with CustomerName supplying member names)</span></span>  
  
-   <span data-ttu-id="e6d17-126">Age, Gender, Email, City, Region, Country</span><span class="sxs-lookup"><span data-stu-id="e6d17-126">Age, Gender, Email, City, Region, Country</span></span>  
  
 <span data-ttu-id="e6d17-127">Представляющие естественные иерархии связи создают, связывая атрибуты текущего и нижестоящего уровня.</span><span class="sxs-lookup"><span data-stu-id="e6d17-127">Relationships representing natural hierarchies are enforced by creating an attribute relationship between the attribute for a level and the attribute for the level below it.</span></span> <span data-ttu-id="e6d17-128">В службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] это свойство определяет естественную иерархию и возможное статистическое вычисление.</span><span class="sxs-lookup"><span data-stu-id="e6d17-128">For [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], this specifies a natural relationship and potential aggregation.</span></span> <span data-ttu-id="e6d17-129">В измерении Customer естественная иерархия применяется для атрибутов Country, Region, City и Customer.</span><span class="sxs-lookup"><span data-stu-id="e6d17-129">In the Customer dimension, a natural hierarchy exists for the Country, Region, City, and Customer attributes.</span></span> <span data-ttu-id="e6d17-130">Естественная иерархия атрибутов `{Country, Region, City, Customer}` описывается добавлением следующих связей атрибутов:</span><span class="sxs-lookup"><span data-stu-id="e6d17-130">The natural hierarchy for `{Country, Region, City, Customer}` is described by adding the following attribute relationships:</span></span>  
  
-   <span data-ttu-id="e6d17-131">атрибут Country как связь атрибутов к атрибуту Region;</span><span class="sxs-lookup"><span data-stu-id="e6d17-131">The Country attribute as an attribute relationship to the Region attribute.</span></span>  
  
-   <span data-ttu-id="e6d17-132">атрибут Region как связь атрибутов к атрибуту City;</span><span class="sxs-lookup"><span data-stu-id="e6d17-132">The Region attribute as an attribute relationship to the City attribute.</span></span>  
  
-   <span data-ttu-id="e6d17-133">атрибут City как связь атрибутов к атрибуту Customer.</span><span class="sxs-lookup"><span data-stu-id="e6d17-133">The City attribute as an attribute relationship to the Customer attribute.</span></span>  
  
 <span data-ttu-id="e6d17-134">Для перемещения по данным куба можно также создать пользовательскую иерархию, которая не представляет естественную иерархию в данных (которая называется *нерегламентированной* или иерархией *отчетов* ).</span><span class="sxs-lookup"><span data-stu-id="e6d17-134">For navigating data in the cube, you can also create a user-defined hierarchy that does not represent a natural hierarchy in the data (which is called an *ad hoc* or *reporting* hierarchy).</span></span> <span data-ttu-id="e6d17-135">Например, пользовательская иерархия может быть создана на основе `{Age, Gender}`.</span><span class="sxs-lookup"><span data-stu-id="e6d17-135">For example, you could create a user-defined hierarchy based on `{Age, Gender}`.</span></span> <span data-ttu-id="e6d17-136">Пользователи не видят каких-либо различий в принципах работы двух иерархий, хотя естественная иерархия имеет преимущества от структуры статистической обработки и индексирования, скрытой от пользователя для естественных связей в исходных данных.</span><span class="sxs-lookup"><span data-stu-id="e6d17-136">Users do not see any difference in how the two hierarchies behave, although the natural hierarchy benefits from aggregating and indexing structures - hidden from the user - that account for the natural relationships in the source data.</span></span>  
  
 <span data-ttu-id="e6d17-137">Свойство `SourceAttribute` уровня определяет, какой из атрибутов описывает уровень.</span><span class="sxs-lookup"><span data-stu-id="e6d17-137">The `SourceAttribute` property of a level determines which attribute is used to describe the level.</span></span> <span data-ttu-id="e6d17-138">Свойство `KeyColumns` атрибута определяет столбец в представлении источника данных, который является источником элементов.</span><span class="sxs-lookup"><span data-stu-id="e6d17-138">The `KeyColumns` property on the attribute specifies the column in the data source view that supplies the members.</span></span> <span data-ttu-id="e6d17-139">Свойство `NameColumn` атрибута может указывать на другой столбец имен для элементов.</span><span class="sxs-lookup"><span data-stu-id="e6d17-139">The `NameColumn` property on the attribute can specify a different name column for the members.</span></span>  
  
 <span data-ttu-id="e6d17-140">Чтобы определить уровень в пользовательской иерархии с помощью [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , **конструктор измерений** позволяет выбрать атрибут измерения, столбец в таблице измерения или столбец из связанной таблицы, входящей в представление источника данных для куба.</span><span class="sxs-lookup"><span data-stu-id="e6d17-140">To define a level in a user-defined hierarchy using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the **Dimension Designer** allows you to select a dimension attribute, a column in a dimension table, or a column from a related table included in the data source view for the cube.</span></span> <span data-ttu-id="e6d17-141">Дополнительные сведения о создании пользовательских иерархий см. в разделе [Создание определяемых пользователем иерархий](../multidimensional-models/user-defined-hierarchies-create.md).</span><span class="sxs-lookup"><span data-stu-id="e6d17-141">For more information about creating user-defined hierarchies, see [Create User-Defined Hierarchies](../multidimensional-models/user-defined-hierarchies-create.md).</span></span>  
  
 <span data-ttu-id="e6d17-142">В службах Analysis Services о содержимом элементов измерения обычно делается предположение.</span><span class="sxs-lookup"><span data-stu-id="e6d17-142">In Analysis Services, an assumption is usually made about the content of members.</span></span> <span data-ttu-id="e6d17-143">Конечные элементы не имеют потомков и содержат данные, полученные непосредственно из основных источников данных.</span><span class="sxs-lookup"><span data-stu-id="e6d17-143">Leaf members have no descendents and contain data derived from underlying data sources.</span></span> <span data-ttu-id="e6d17-144">Неконечные элементы имеют потомков и содержат данные из статистических вычислений, рассчитанных по дочерним элементам.</span><span class="sxs-lookup"><span data-stu-id="e6d17-144">Nonleaf members have descendents and contain data derived from aggregations performed on child members.</span></span> <span data-ttu-id="e6d17-145">Значения на неконечных уровнях вычисляются на основе статистических вычислений над нижестоящими уровнями.</span><span class="sxs-lookup"><span data-stu-id="e6d17-145">In aggregated levels, members are based on aggregations of subordinate levels.</span></span> <span data-ttu-id="e6d17-146">Таким образом, когда свойству `IsAggregatable` исходного атрибута присваивается значение `False` для некоторого уровня, статистически вычисляемые атрибуты не должны добавляться на вышестоящие уровни.</span><span class="sxs-lookup"><span data-stu-id="e6d17-146">Therefore, when the `IsAggregatable` property is set to `False` on a source attribute for a level, no aggregatable attributes should be added as levels above it.</span></span>  
  
## <a name="defining-an-attribute-relationship"></a><span data-ttu-id="e6d17-147">Определения связи атрибутов</span><span class="sxs-lookup"><span data-stu-id="e6d17-147">Defining an Attribute Relationship</span></span>  
 <span data-ttu-id="e6d17-148">При создании атрибута главное проверить, чтобы атрибут, на который ссылается связь, имел не более одного значения для каждого элемента атрибута, к которому он принадлежит.</span><span class="sxs-lookup"><span data-stu-id="e6d17-148">The main constraint when you create an attribute relationship is to make sure that the attribute referred to by the attribute relationship has no more than one value for any member in the attribute to which the attribute relationship belongs.</span></span> <span data-ttu-id="e6d17-149">Например, если определить связь между атрибутами City и State, каждый город будет принадлежать одному штату.</span><span class="sxs-lookup"><span data-stu-id="e6d17-149">For example, if you define a relationship between a City attribute and a State attribute, each city can only relate to a single state.</span></span>  
  
## <a name="attribute-relationship-queries"></a><span data-ttu-id="e6d17-150">Запросы связи атрибутов</span><span class="sxs-lookup"><span data-stu-id="e6d17-150">Attribute Relationship Queries</span></span>  
 <span data-ttu-id="e6d17-151">Чтобы получить данные о связи атрибутов в форме свойств элементов, можно использовать запросы многомерных выражений с ключевым словом `PROPERTIES` инструкции многомерных выражений `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="e6d17-151">You can use MDX queries to retrieve data from attribute relationships, in the form of member properties, with the `PROPERTIES` keyword of the MDX `SELECT` statement.</span></span> <span data-ttu-id="e6d17-152">Дополнительные сведения об использовании многомерных выражений для получения свойств элементов см. в разделе [использование свойств элементов &#40;&#41;многомерных выражений ](../multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e6d17-152">For more information about how to use MDX to retrieve member properties, see [Using Member Properties &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d17-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6d17-153">See Also</span></span>  
 <span data-ttu-id="e6d17-154">[Атрибуты и иерархии атрибутов](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="e6d17-154">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="e6d17-155">[Справочник по свойствам атрибутов измерения](../multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e6d17-155">[Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="e6d17-156">[Пользовательские иерархии](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="e6d17-156">[User Hierarchies](user-hierarchies.md) </span></span>  
 [<span data-ttu-id="e6d17-157">Свойства пользовательской иерархии</span><span class="sxs-lookup"><span data-stu-id="e6d17-157">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
