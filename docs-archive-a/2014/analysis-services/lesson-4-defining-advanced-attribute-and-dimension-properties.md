---
title: Занятие 4. Определение дополнительных свойств атрибутов и измерений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e86b9be-e47d-4bb4-87eb-136ff3a61aef
author: minewiskan
ms.author: owend
ms.openlocfilehash: deb2d9c40ad5024f6cc4ba6e9148df41a168c6e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734554"
---
# <a name="lesson-4-defining-advanced-attribute-and-dimension-properties"></a><span data-ttu-id="7d029-102">Занятие 4: Определение расширенных свойств атрибутов и измерений</span><span class="sxs-lookup"><span data-stu-id="7d029-102">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>
  <span data-ttu-id="7d029-103">На этом занятии изучается использование расширенных свойств атрибутов, иерархий атрибутов и свойств измерений.</span><span class="sxs-lookup"><span data-stu-id="7d029-103">In this lesson, you will learn how to use some of the advanced properties of attributes, attribute hierarchies, and dimension properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d029-104">Это занятие проводится на основе улучшенной версии проекта Tutorial служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , созданного на первых трех занятиях данного учебного курса.</span><span class="sxs-lookup"><span data-stu-id="7d029-104">This lesson is based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons of this tutorial.</span></span> <span data-ttu-id="7d029-105">В первой задаче занятия рассмотрено, где следует размещать соответствующий образец проекта для данного занятия, а также объясняется разница между этим проектом и проектом, созданным на первых трех занятиях.</span><span class="sxs-lookup"><span data-stu-id="7d029-105">The first task in this lesson describes where to locate the appropriate sample project to use for the lesson, and the difference between this project and the project that you created in the first three lessons.</span></span>  
  
 <span data-ttu-id="7d029-106">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="7d029-106">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="7d029-107">Использование измененной версии проекта Analysis Services Tutorial</span><span class="sxs-lookup"><span data-stu-id="7d029-107">Using a Modified Version of the Analysis Services Tutorial Project</span></span>](lesson-4-1-using-a-modified-version-of-the-analysis-services-tutorial-project.md)  
 <span data-ttu-id="7d029-108">В этой задаче вы откроете, просмотрите и выполните развертывание измененной версии проекта «Учебник по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] », содержащей несколько групп мер и дополнительных измерений.</span><span class="sxs-lookup"><span data-stu-id="7d029-108">In this task, you open, review, and deploy a modified version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, which has multiple measure groups and additional dimensions.</span></span>  
  
 [<span data-ttu-id="7d029-109">Определение свойств родительского атрибута в иерархии «родители-потомки»</span><span class="sxs-lookup"><span data-stu-id="7d029-109">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md)  
 <span data-ttu-id="7d029-110">В этой задаче вы зададите имена уровней в измерении типа «родители-потомки» и укажите, следует ли отображать данные, связанные с элементами-родителями.</span><span class="sxs-lookup"><span data-stu-id="7d029-110">In this task, you define level names in a parent-child dimension and specify whether data related to parent members is displayed.</span></span> <span data-ttu-id="7d029-111">Дополнительные сведения см. в разделе Иерархия и атрибуты « [родители-потомки](multidimensional-models/parent-child-dimension.md) » [в иерархиях «родители-потомки](multidimensional-models/parent-child-dimension-attributes.md)».</span><span class="sxs-lookup"><span data-stu-id="7d029-111">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) and [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md).</span></span>  
  
 [<span data-ttu-id="7d029-112">Автоматическое группирование элементов атрибута</span><span class="sxs-lookup"><span data-stu-id="7d029-112">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)  
 <span data-ttu-id="7d029-113">В этой задаче автоматически создаются группирования элементов атрибутов на основе распределения членов в иерархии атрибутов.</span><span class="sxs-lookup"><span data-stu-id="7d029-113">In this task, you automatically create groupings of attribute members based on the distribution of the members within the attribute hierarchy.</span></span> <span data-ttu-id="7d029-114">Дополнительные сведения см. в разделе [Группирование элементов атрибутов (дискретизация)](multidimensional-models/attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="7d029-114">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span></span>  
  
 [<span data-ttu-id="7d029-115">Скрытие и отключение иерархий атрибутов</span><span class="sxs-lookup"><span data-stu-id="7d029-115">Hiding and Disabling Attribute Hierarchies</span></span>](lesson-4-4-hiding-and-disabling-attribute-hierarchies.md)  
 <span data-ttu-id="7d029-116">В этой задаче предстоит изучить, в каких случаях и как отключить или скрыть иерархии атрибутов.</span><span class="sxs-lookup"><span data-stu-id="7d029-116">In this task, you learn how and when to disable or hide attribute hierarchies.</span></span>  
  
 [<span data-ttu-id="7d029-117">Сортировка элементов атрибута по вторичному атрибуту</span><span class="sxs-lookup"><span data-stu-id="7d029-117">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)  
 <span data-ttu-id="7d029-118">В этой задаче изучается порядок сортировки элементов измерения на основе вторичного атрибута.</span><span class="sxs-lookup"><span data-stu-id="7d029-118">In this task, you learn how to sort dimension members based on a secondary attribute, to achieve the sort order that you want.</span></span>  
  
 [<span data-ttu-id="7d029-119">Определение связей атрибутов в определенной пользователем иерархии</span><span class="sxs-lookup"><span data-stu-id="7d029-119">Specifying Attribute Relationships Between Attributes in a User-Defined Hierarchy</span></span>](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md)  
 <span data-ttu-id="7d029-120">В этой задаче мы изучим, как следует указывать свойства элементов для атрибутов, чтобы задавать статистические связи между ними.</span><span class="sxs-lookup"><span data-stu-id="7d029-120">In this task, you learn how to define member properties for attributes and to specify aggregation relationships between them.</span></span> <span data-ttu-id="7d029-121">Дополнительные сведения см. в разделе [Определение связей атрибутов](multidimensional-models/attribute-relationships-define.md) и [Свойства пользовательской иерархии](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7d029-121">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [User Hierarchy Properties](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span></span>  
  
 [<span data-ttu-id="7d029-122">Определение свойств Unknown Member и Null Processing</span><span class="sxs-lookup"><span data-stu-id="7d029-122">Defining the Unknown Member and Null Processing Properties</span></span>](lesson-4-7-defining-the-unknown-member-and-null-processing-properties.md)  
 <span data-ttu-id="7d029-123">В этой задаче требуется настроить свойства UnknownMember и UnknownMemberName для обработки условий возникновения ошибок, вызванных элементами измерений со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="7d029-123">In this task, you configure the UnknownMember and UnknownMemberName properties to handle error conditions caused by null dimension members.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="7d029-124">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="7d029-124">Next Lesson</span></span>  
 [<span data-ttu-id="7d029-125">Занятие 5.: Определение связей между измерениями и группами мер</span><span class="sxs-lookup"><span data-stu-id="7d029-125">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>](lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d029-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d029-126">See Also</span></span>  
 <span data-ttu-id="7d029-127">[Analysis Services сценарий учебника](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7d029-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="7d029-128">[&#40;учебника по Adventure Works в многомерном моделировании&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="7d029-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="7d029-129">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="7d029-129">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
