---
title: Кубы в многомерных моделях | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OLAP objects [Analysis Services], cubes
- cubes [Analysis Services], about cubes
- cubes [Analysis Services]
- OLAP [Analysis Services], cubes
ms.assetid: e0f7acf3-4b07-41fc-a5fc-ac30b4a56c54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 372bb8075b232ff8fbf8a54facf9bc065e6763a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750316"
---
# <a name="cubes-in-multidimensional-models"></a><span data-ttu-id="f9ae2-102">Кубы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-102">Cubes in Multidimensional Models</span></span>
  <span data-ttu-id="f9ae2-103">Куб является многомерной структурой, содержащей сведения для анализа. Главными составными элементами куба являются измерения и меры.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-103">A cube is a multidimensional structure that contains information for analytical purposes; the main constituents of a cube are dimensions and measures.</span></span> <span data-ttu-id="f9ae2-104">Измерения определяют структуру куба, используемую для срезов данных, а меры предоставляют статистически вычисленные числовые значения, представляющие интерес для конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-104">Dimensions define the structure of the cube that you use to slice and dice over, and measures provide aggregated numerical values of interest to the end user.</span></span> <span data-ttu-id="f9ae2-105">В качестве логической структуры куб позволяет клиентскому приложению получать значения мер в виде ячеек куба, определенных для всех возможных суммарных значений.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-105">As a logical structure, a cube allows a client application to retrieve values, of measures, as if they were contained in cells in the cube; cells are defined for every possible summarized value.</span></span> <span data-ttu-id="f9ae2-106">Ячейка куба определяется пересечением элементов измерения и содержит статистически вычисляемые значения мер в этом конкретном пересечении.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-106">A cell, in the cube, is defined by the intersection of dimension members and contains the aggregated values of the measures at that specific intersection.</span></span>  
  
## <a name="benefits-of-using-cubes"></a><span data-ttu-id="f9ae2-107">Преимущества использования кубов</span><span class="sxs-lookup"><span data-stu-id="f9ae2-107">Benefits of Using Cubes</span></span>  
 <span data-ttu-id="f9ae2-108">Куб представляет собой единое место, где хранятся все связанные данные для анализа.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-108">A cube provides a single place where all related data, for analysis, is stored.</span></span>  
  
## <a name="components-of-cubes"></a><span data-ttu-id="f9ae2-109">Компоненты кубов</span><span class="sxs-lookup"><span data-stu-id="f9ae2-109">Components of Cubes</span></span>  
 <span data-ttu-id="f9ae2-110">Из чего состоит куб:</span><span class="sxs-lookup"><span data-stu-id="f9ae2-110">A cube is composed of:</span></span>  
  
|<span data-ttu-id="f9ae2-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9ae2-111">Element</span></span>|<span data-ttu-id="f9ae2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f9ae2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f9ae2-113">Измерения</span><span class="sxs-lookup"><span data-stu-id="f9ae2-113">Dimensions</span></span>|[<span data-ttu-id="f9ae2-114">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-114">Dimensions in Multidimensional Models</span></span>](dimensions-in-multidimensional-models.md)|  
|<span data-ttu-id="f9ae2-115">Меры и их группы</span><span class="sxs-lookup"><span data-stu-id="f9ae2-115">Measures and Measure Groups</span></span>|[<span data-ttu-id="f9ae2-116">Создание мер и групп мер в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-116">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|  
|<span data-ttu-id="f9ae2-117">Секции</span><span class="sxs-lookup"><span data-stu-id="f9ae2-117">Partitions</span></span>|[<span data-ttu-id="f9ae2-118">Секции в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-118">Partitions in Multidimensional Models</span></span>](partitions-in-multidimensional-models.md)|  
|<span data-ttu-id="f9ae2-119">Перспективы</span><span class="sxs-lookup"><span data-stu-id="f9ae2-119">Perspectives</span></span>|[<span data-ttu-id="f9ae2-120">Перспективы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-120">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|  
|<span data-ttu-id="f9ae2-121">Иерархии</span><span class="sxs-lookup"><span data-stu-id="f9ae2-121">Hierarchies</span></span>|[<span data-ttu-id="f9ae2-122">Создание пользовательских иерархий</span><span class="sxs-lookup"><span data-stu-id="f9ae2-122">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)|  
|<span data-ttu-id="f9ae2-123">Действия</span><span class="sxs-lookup"><span data-stu-id="f9ae2-123">Actions</span></span>|[<span data-ttu-id="f9ae2-124">Действия в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-124">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|  
|<span data-ttu-id="f9ae2-125">Ключевые показатели эффективности (KPI)</span><span class="sxs-lookup"><span data-stu-id="f9ae2-125">Key Performance Indicators (KPI)</span></span>|[<span data-ttu-id="f9ae2-126">Ключевые показатели эффективности в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-126">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](key-performance-indicators-kpis-in-multidimensional-models.md)|  
|<span data-ttu-id="f9ae2-127">Вычисления</span><span class="sxs-lookup"><span data-stu-id="f9ae2-127">Calculations</span></span>|[<span data-ttu-id="f9ae2-128">Вычисления в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-128">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|  
|<span data-ttu-id="f9ae2-129">Translations</span><span class="sxs-lookup"><span data-stu-id="f9ae2-129">Translations</span></span>|[<span data-ttu-id="f9ae2-130">Переводы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-130">Translations in Multidimensional Models</span></span>](translations-in-multidimensional-models-analysis-services.md)|  
  
## <a name="related-tasks"></a><span data-ttu-id="f9ae2-131">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f9ae2-131">Related Tasks</span></span>  
  
|<span data-ttu-id="f9ae2-132">Раздел</span><span class="sxs-lookup"><span data-stu-id="f9ae2-132">Topic</span></span>|<span data-ttu-id="f9ae2-133">Описание</span><span class="sxs-lookup"><span data-stu-id="f9ae2-133">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f9ae2-134">Создание куба с помощью мастера кубов</span><span class="sxs-lookup"><span data-stu-id="f9ae2-134">Create a Cube Using the Cube Wizard</span></span>](create-a-cube-using-the-cube-wizard.md)|<span data-ttu-id="f9ae2-135">Описывает использование мастера кубов для определения куба, измерений, атрибутов измерения и пользовательских иерархий.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-135">Describes how to use the Cube Wizard to define a cube, dimensions, dimension attributes, and user-defined hierarchies.</span></span>|  
|[<span data-ttu-id="f9ae2-136">Создание мер и групп мер в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-136">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|<span data-ttu-id="f9ae2-137">Описывает процесс определения групп мер.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-137">Describes how to define measure groups.</span></span>|  
|[<span data-ttu-id="f9ae2-138">Вычисления в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-138">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|<span data-ttu-id="f9ae2-139">Описывает определение и настройку вычисления в скрипте многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-139">Describes how to define and configure a calculation in an MDX script.</span></span>|  
|[<span data-ttu-id="f9ae2-140">Действия в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-140">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|<span data-ttu-id="f9ae2-141">Описывает определение и настройку действия.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-141">Describes how to define and configure an action.</span></span>|  
|[<span data-ttu-id="f9ae2-142">Перспективы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9ae2-142">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|<span data-ttu-id="f9ae2-143">Описывает определение и настройку перспективы.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-143">Describes how to define and configure a perspective.</span></span>|  
|[<span data-ttu-id="f9ae2-144">Определение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="f9ae2-144">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)|<span data-ttu-id="f9ae2-145">Описывает работу с хранимыми процедурами.</span><span class="sxs-lookup"><span data-stu-id="f9ae2-145">Describes how to work with stored procedures.</span></span>|  
  
  
