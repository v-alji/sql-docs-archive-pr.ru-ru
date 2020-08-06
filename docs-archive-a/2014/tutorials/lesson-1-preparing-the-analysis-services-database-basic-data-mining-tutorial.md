---
title: Занятие 1. Подготовка базы данных Analysis Services (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a796977-6568-4705-9d27-86a9b36658c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 07647a940851fbdbdc65357e168747662dc88380
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751615"
---
# <a name="lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial"></a><span data-ttu-id="c0c2e-102">Занятие 1. Подготовка базы данных служб Analysis Services (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="c0c2e-102">Lesson 1: Preparing the Analysis Services Database (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="c0c2e-103">Вы являетесь новым сотрудником [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] , который выполнил задачу разработки приложения бизнес-аналитики в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0c2e-103">You are a new employee of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] who has been tasked with designing a business intelligence application in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]<span data-ttu-id="c0c2e-104">надеется использовать [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] возможности интеллектуального анализа данных для обнаружения интересных и практичных сведений о людях, приобретенных в велосипеды.</span><span class="sxs-lookup"><span data-stu-id="c0c2e-104">hopes to leverage your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data mining experience to discover interesting and actionable information about people who have purchased bicycles.</span></span> <span data-ttu-id="c0c2e-105">Необходимо также спрогнозировать, какие потенциальные клиенты с наибольшей вероятностью купят велосипед в будущем.</span><span class="sxs-lookup"><span data-stu-id="c0c2e-105">They then want you to predict which prospective customers are most likely to purchase a bicycle in the future.</span></span>  
  
 <span data-ttu-id="c0c2e-106">Проектирование этого приложения в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] начинается с создания в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] проекте на основе [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] шаблона проекта для многомерного моделирования и интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="c0c2e-106">Designing this application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with the creation in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project template for multidimensional modeling and data mining.</span></span> <span data-ttu-id="c0c2e-107">После создания проекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] необходимо задать один или несколько источников данных.</span><span class="sxs-lookup"><span data-stu-id="c0c2e-107">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you define one or more data sources.</span></span> <span data-ttu-id="c0c2e-108">Затем определяется представление метаданных, называемое *представлением источника данных*, из выбранных таблиц и представлений из источников данных.</span><span class="sxs-lookup"><span data-stu-id="c0c2e-108">Then, you define a view of the metadata, called a *data source view*, from selected tables and views from the data sources.</span></span>  
  
 <span data-ttu-id="c0c2e-109">На этом занятии предстоит создать проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], указать один источник данных и добавить подмножество таблиц в представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="c0c2e-109">In this lesson, you will create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, define a single data source, and add a subset of tables to a data source view.</span></span> <span data-ttu-id="c0c2e-110">Это занятие содержит следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c0c2e-110">This lesson includes the following tasks:</span></span>  
  
 [<span data-ttu-id="c0c2e-111">Учебник по созданию Analysis Services проекта &#40;Basic Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c0c2e-111">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="c0c2e-112">Учебник по созданию источника данных &#40;Basic Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c0c2e-112">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="c0c2e-113">Создание представления источника данных &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c0c2e-113">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="c0c2e-114">Первая задача занятия</span><span class="sxs-lookup"><span data-stu-id="c0c2e-114">First Task in Lesson</span></span>  
 [<span data-ttu-id="c0c2e-115">Учебник по созданию Analysis Services проекта &#40;Basic Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c0c2e-115">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="c0c2e-116">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="c0c2e-116">Next Lesson</span></span>  
 [<span data-ttu-id="c0c2e-117">Занятие 2. Создание структуры целевой рассылки &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c0c2e-117">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="c0c2e-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0c2e-118">See Also</span></span>  
 <span data-ttu-id="c0c2e-119">[Представления источников данных в многомерных моделях](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span><span class="sxs-lookup"><span data-stu-id="c0c2e-119">[Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span></span>  
 <span data-ttu-id="c0c2e-120">[Поддерживаемые источники данных &#40;многомерные&#41;SSAS](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="c0c2e-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span></span>  
 <span data-ttu-id="c0c2e-121">[Сборка Analysis Services проектов &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="c0c2e-121">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="c0c2e-122">Создание проекта служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c0c2e-122">Creating an Analysis Services Project</span></span>](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md)  
  
  
