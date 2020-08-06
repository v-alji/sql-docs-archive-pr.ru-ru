---
title: Занятие 2. Определение и развертывание куба | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bb62e3c9-462f-4ad2-ac8e-92e2f9e9cc28
author: minewiskan
ms.author: owend
ms.openlocfilehash: a2c043920ac646ec4da9eaa2aace4bf6f48e694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666859"
---
# <a name="lesson-2-defining-and-deploying-a-cube"></a><span data-ttu-id="b3d17-102">Урок 2. Определение и развертывание куба</span><span class="sxs-lookup"><span data-stu-id="b3d17-102">Lesson 2: Defining and Deploying a Cube</span></span>
  <span data-ttu-id="b3d17-103">После определения представления источника данных в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] проекте можно приступать к определению исходного [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] куба.</span><span class="sxs-lookup"><span data-stu-id="b3d17-103">After you define a data source view in your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you are ready to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 <span data-ttu-id="b3d17-104">Кроме того, можно определить куб и его измерения за один проход с помощью мастера кубов.</span><span class="sxs-lookup"><span data-stu-id="b3d17-104">You can define a cube and its dimensions in a single pass using the Cube Wizard.</span></span> <span data-ttu-id="b3d17-105">Также можно определить одно или несколько измерений, а затем с помощью мастера кубов определить куб, в котором они будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="b3d17-105">Alternatively, you can define one or more dimensions and then use the Cube Wizard to define a cube that uses those dimensions.</span></span> <span data-ttu-id="b3d17-106">Разработку сложного решения обычно начинают с определения измерений.</span><span class="sxs-lookup"><span data-stu-id="b3d17-106">If you are designing a complex solution, you generally start by defining the dimensions.</span></span> <span data-ttu-id="b3d17-107">Дополнительные сведения см. в разделе [Измерения в многомерных моделях](multidimensional-models/dimensions-in-multidimensional-models.md) или [Кубы в многомерных моделях](multidimensional-models/cubes-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="b3d17-107">For more information, see [Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) or [Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3d17-108">Завершенные проекты для всех занятий в этом учебнике доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b3d17-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="b3d17-109">Можно перейти вперед к любому занятию, используя в качестве отправной точки завершенный проект из предыдущего урока.</span><span class="sxs-lookup"><span data-stu-id="b3d17-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="b3d17-110">[Щелкните здесь](https://go.microsoft.com/fwlink/?LinkID=221866) для загрузки образцов проектов, прилагаемых к этому учебнику.</span><span class="sxs-lookup"><span data-stu-id="b3d17-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="b3d17-111">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="b3d17-111">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="b3d17-112">Определение измерения</span><span class="sxs-lookup"><span data-stu-id="b3d17-112">Defining a Dimension</span></span>](lesson-2-1-defining-a-dimension.md)  
 <span data-ttu-id="b3d17-113">В этой задаче будет определено измерение с помощью мастера измерений.</span><span class="sxs-lookup"><span data-stu-id="b3d17-113">In this task, you use the Dimension Wizard to define a dimension.</span></span>  
  
 [<span data-ttu-id="b3d17-114">Определение куба</span><span class="sxs-lookup"><span data-stu-id="b3d17-114">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
 <span data-ttu-id="b3d17-115">В этой задаче с помощью мастера кубов будет определен исходный куб служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3d17-115">In this task, you use the Cube Wizard to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 [<span data-ttu-id="b3d17-116">Добавление атрибутов к измерениям</span><span class="sxs-lookup"><span data-stu-id="b3d17-116">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
 <span data-ttu-id="b3d17-117">В этой задаче в созданные измерения будут добавлены атрибуты.</span><span class="sxs-lookup"><span data-stu-id="b3d17-117">In this task, you add attributes to the dimensions that you created.</span></span>  
  
 [<span data-ttu-id="b3d17-118">Просмотр свойств куба и измерения</span><span class="sxs-lookup"><span data-stu-id="b3d17-118">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
 <span data-ttu-id="b3d17-119">В этой задаче будет просмотрена структура куба, определенная с помощью мастера кубов.</span><span class="sxs-lookup"><span data-stu-id="b3d17-119">In this task, you review the structure of the cube that you defined by using the Cube Wizard.</span></span>  
  
 [<span data-ttu-id="b3d17-120">Развертывание проекта служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b3d17-120">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
 <span data-ttu-id="b3d17-121">В этой задаче будет выполнено развертывание проекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в локальном экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], и будут изучены некоторые свойства такого развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3d17-121">In this task, you deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project to your local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], and learn about certain deployment properties.</span></span>  
  
 [<span data-ttu-id="b3d17-122">Просмотр куба</span><span class="sxs-lookup"><span data-stu-id="b3d17-122">Browsing the Cube</span></span>](lesson-2-6-browsing-the-cube.md)  
 <span data-ttu-id="b3d17-123">В этой задаче будут просмотрены данные куба и измерения с помощью Excel и конструктора запросов многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="b3d17-123">In this task, you browse the cube and dimension data by using Excel or the MDX query designer.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b3d17-124">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="b3d17-124">Next Lesson</span></span>  
 [<span data-ttu-id="b3d17-125">Урок 3. Изменение мер, атрибутов и иерархий</span><span class="sxs-lookup"><span data-stu-id="b3d17-125">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>](lesson-3-modifying-measures-attributes-and-hierarchies.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3d17-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3d17-126">See Also</span></span>  
 <span data-ttu-id="b3d17-127">[Analysis Services сценарий учебника](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b3d17-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="b3d17-128">[&#40;учебника по Adventure Works в многомерном моделировании&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="b3d17-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="b3d17-129">[Измерения в многомерных моделях](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b3d17-129">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="b3d17-130">[Кубы в многомерных моделях](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b3d17-130">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="b3d17-131">[Настройка Analysis Services свойств проекта &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="b3d17-131">[Configure Analysis Services Project Properties &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span></span>  
 <span data-ttu-id="b3d17-132">[Сборка Analysis Services проектов &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="b3d17-132">[Build Analysis Services Projects &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span></span>  
 [<span data-ttu-id="b3d17-133">Развертывание проектов служб Analysis Services (среда SSDT)</span><span class="sxs-lookup"><span data-stu-id="b3d17-133">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
  
