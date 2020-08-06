---
title: Занятие 5. Определение связей между измерениями и группами мер | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 31aeb271-47a1-433b-a8a5-120bcb4584d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6dbdf20e64e3cd8adc751b69122a380d7b3b3648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658506"
---
# <a name="lesson-5-defining-relationships-between-dimensions-and-measure-groups"></a><span data-ttu-id="29d77-102">Занятие 5.: Определение связей между измерениями и группами мер</span><span class="sxs-lookup"><span data-stu-id="29d77-102">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>
  <span data-ttu-id="29d77-103">На предыдущем занятии было рассмотрено, что измерения баз данных, добавленные к кубу, могут использоваться как основа для одного или нескольких измерений куба.</span><span class="sxs-lookup"><span data-stu-id="29d77-103">In the previous lessons in this tutorial, you learned that database dimensions added to a cube can be used as the basis for one or more cube dimensions.</span></span> <span data-ttu-id="29d77-104">На этом занятии предстоит изучить, как следует определять различные типы связей между измерениями куба и группами мер, а также изучить определение свойств этих связей.</span><span class="sxs-lookup"><span data-stu-id="29d77-104">In this lesson, you learn to define different types of relationships between cube dimensions and measure groups, and to specify the properties of these relationships.</span></span>  
  
 <span data-ttu-id="29d77-105">Дополнительные сведения см. в разделе [Связи измерений](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="29d77-105">For more information, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29d77-106">Завершенные проекты для всех занятий в этом учебнике доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="29d77-106">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="29d77-107">Можно перейти вперед к любому занятию, используя в качестве отправной точки завершенный проект из предыдущего урока.</span><span class="sxs-lookup"><span data-stu-id="29d77-107">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="29d77-108">[Щелкните здесь](https://go.microsoft.com/fwlink/?LinkID=221866) для загрузки образцов проектов, прилагаемых к этому учебнику.</span><span class="sxs-lookup"><span data-stu-id="29d77-108">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="29d77-109">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="29d77-109">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="29d77-110">Определение ссылочной связи</span><span class="sxs-lookup"><span data-stu-id="29d77-110">Defining a Referenced Relationship</span></span>](lesson-5-1-defining-a-referenced-relationship.md)  
 <span data-ttu-id="29d77-111">В этой задаче вы узнаете, как напрямую связать измерение с таблицей фактов через измерение, связанное непосредственно через связь «первичный-внешний ключ».</span><span class="sxs-lookup"><span data-stu-id="29d77-111">In this task, you learn to link a dimension to a fact table indirectly through a dimension that is linked directly through a primary key-foreign key relationship.</span></span>  
  
 [<span data-ttu-id="29d77-112">Определение связи фактов</span><span class="sxs-lookup"><span data-stu-id="29d77-112">Defining a Fact Relationship</span></span>](lesson-5-2-defining-a-fact-relationship.md)  
 <span data-ttu-id="29d77-113">В этой задаче будет изучено, как создать измерение, основанное на данных таблицы фактов, а также как определить связь измерений как связь фактов.</span><span class="sxs-lookup"><span data-stu-id="29d77-113">In this task, you learn to define a dimension based on data in the fact table, and to define the dimension relationship as a fact relationship.</span></span>  
  
 [<span data-ttu-id="29d77-114">Определение связи «многие ко многим»</span><span class="sxs-lookup"><span data-stu-id="29d77-114">Defining a Many-to-Many Relationship</span></span>](lesson-5-3-defining-a-many-to-many-relationship.md)  
 <span data-ttu-id="29d77-115">В этой задаче будет изучено, как связать факт с несколькими элементам измерения путем создания связи «многие ко многим» между таблицами измерений и таблицами фактов.</span><span class="sxs-lookup"><span data-stu-id="29d77-115">In this task, you learn to relate a fact to multiple dimension members through the definition of a many-to-many relationship between dimension tables and fact tables.</span></span>  
  
 [<span data-ttu-id="29d77-116">Определение степени гранулярности измерения в группе мер</span><span class="sxs-lookup"><span data-stu-id="29d77-116">Defining Dimension Granularity within a Measure Group</span></span>](lesson-5-4-defining-dimension-granularity-within-a-measure-group.md)  
 <span data-ttu-id="29d77-117">В этой задаче будет изучено, как изменить степень гранулярности измерения для конкретной группы показателей.</span><span class="sxs-lookup"><span data-stu-id="29d77-117">In this task, you learn to modify the granularity of a dimension for a specific measure group.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="29d77-118">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="29d77-118">Next Lesson</span></span>  
 [<span data-ttu-id="29d77-119">Занятие 6: Определение вычислений</span><span class="sxs-lookup"><span data-stu-id="29d77-119">Lesson 6: Defining Calculations</span></span>](lesson-6-defining-calculations.md)  
  
## <a name="see-also"></a><span data-ttu-id="29d77-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="29d77-120">See Also</span></span>  
 <span data-ttu-id="29d77-121">[Analysis Services сценарий учебника](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="29d77-121">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="29d77-122">[&#40;учебника по Adventure Works в многомерном моделировании&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="29d77-122">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="29d77-123">Связи измерений</span><span class="sxs-lookup"><span data-stu-id="29d77-123">Dimension Relationships</span></span>](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md)  
  
  
