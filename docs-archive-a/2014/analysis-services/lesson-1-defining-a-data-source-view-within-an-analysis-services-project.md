---
title: Занятие 1. определение представления источников данных в проекте Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7d3ffabd-78ae-4204-8323-29949d030c16
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a3d69225217154e5072d0cd34349a247730ddaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740586"
---
# <a name="lesson-1-defining-a-data-source-view-within-an-analysis-services-project"></a><span data-ttu-id="d8e89-102">Урок 1. Определение представления источника данных в проекте Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d8e89-102">Lesson 1: Defining a Data Source View within an Analysis Services Project</span></span>
  <span data-ttu-id="d8e89-103">Разработка приложения бизнес-аналитики в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] начинается с создания проекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e89-103">Designing a business intelligence application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with creating an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d8e89-104">В этом проекте будут определены все элементы решения, начиная с представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="d8e89-104">Within this project, you define all the elements of your solution, starting with a data source view.</span></span>  
  
 <span data-ttu-id="d8e89-105">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="d8e89-105">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="d8e89-106">Создание проекта служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d8e89-106">Creating an Analysis Services Project</span></span>](lesson-1-1-creating-an-analysis-services-project.md)  
 <span data-ttu-id="d8e89-107">В этой задаче будет создан проект [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial на основе шаблона многомерной модели служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e89-107">In this task, you create the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, based on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional model template.</span></span>  
  
 [<span data-ttu-id="d8e89-108">Определение источника данных</span><span class="sxs-lookup"><span data-stu-id="d8e89-108">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
 <span data-ttu-id="d8e89-109">В этой задаче в качестве источника данных для измерений служб **и кубов, которые определятся на следующих занятиях, будет использоваться база данных** AdventureWorksDW2012 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e89-109">In this task, you specify the **AdventureWorksDW2012** database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dimensions and cubes that you will define in subsequent lessons.</span></span>  
  
 [<span data-ttu-id="d8e89-110">Определение представления источников данных</span><span class="sxs-lookup"><span data-stu-id="d8e89-110">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
 <span data-ttu-id="d8e89-111">В этой задаче будет определено единое представление метаданных из выбранных таблиц базы данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="d8e89-111">In this task, you define a single unified view of the metadata from selected tables in the **AdventureWorksDW2012** database.</span></span>  
  
 [<span data-ttu-id="d8e89-112">Изменение имен таблиц по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d8e89-112">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
 <span data-ttu-id="d8e89-113">В этой задаче будут изменены имена таблиц в представлении источников данных, чтобы сделать имена последующих определяемых объектов служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] более понятными для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8e89-113">In this task, you modify table names in the data source view, so that the names of subsequent [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects that you define will be more user-friendly.</span></span>  
  
 <span data-ttu-id="d8e89-114">Сравните свои результаты с образцом файла проекта, созданным на этом занятии.</span><span class="sxs-lookup"><span data-stu-id="d8e89-114">Compare your results against a sample project file that was built for this lesson.</span></span> <span data-ttu-id="d8e89-115">Дополнительные сведения о скачивании образцов проектов для этого учебника см. в разделе [Проекты многомерных моделей служб SSAS для SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) на странице образцов продуктов на сайте CodePlex.</span><span class="sxs-lookup"><span data-stu-id="d8e89-115">For more information about downloading the sample projects that go with this tutorial, see [SSAS Multidimensional Model Projects for SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) on the product samples page on codeplex.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d8e89-116">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="d8e89-116">Next Lesson</span></span>  
 [<span data-ttu-id="d8e89-117">Урок 2. Определение и развертывание куба</span><span class="sxs-lookup"><span data-stu-id="d8e89-117">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8e89-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8e89-118">See Also</span></span>  
 <span data-ttu-id="d8e89-119">[Создание проекта Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="d8e89-119">[Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span></span>  
 <span data-ttu-id="d8e89-120">[Поддерживаемые источники данных &#40;многомерные&#41;SSAS](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="d8e89-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="d8e89-121">[Представления источников данных в многомерных моделях](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="d8e89-121">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="d8e89-122">[Analysis Services сценарий учебника](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d8e89-122">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="d8e89-123">Многомерное моделирование (учебник по Adventure Works)</span><span class="sxs-lookup"><span data-stu-id="d8e89-123">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
