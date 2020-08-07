---
title: Занятие 7. определение ключевых показателей эффективности (KPI) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 36d53770-294f-43ab-8850-15d5351ff60c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87df6fd91a66505f124144cafd9a44c6e5e70e85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731026"
---
# <a name="lesson-7-defining-key-performance-indicators-kpis"></a><span data-ttu-id="0ff47-102">Занятие 7: Определение ключевых показателей эффективности</span><span class="sxs-lookup"><span data-stu-id="0ff47-102">Lesson 7: Defining Key Performance Indicators (KPIs)</span></span>
  <span data-ttu-id="0ff47-103">На этом занятии обсуждается определение ключевых показателей эффективности в проекте служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ff47-103">In this lesson, you learn to define Key Performance Indicators (KPIs) in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="0ff47-104">Ключевые показатели эффективности предоставляют среду для определения вычислений по мерам деятельности организации на стороне сервера, а также приводят к единому виду отображения результатов.</span><span class="sxs-lookup"><span data-stu-id="0ff47-104">KPIs provide a framework for defining server-side calculations that measure your business, and they standardize how the resulting information is displayed.</span></span> <span data-ttu-id="0ff47-105">Ключевые показатели эффективности могут отображаться в отчетах, на порталах и инструментальных панелях, через API-интерфейсы доступа к данным, а также с использованием средств [!INCLUDE[msCoName](../includes/msconame-md.md)] и средств сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="0ff47-105">KPIs can be displayed in reports, portals, and dashboards, through data access APIs, and through [!INCLUDE[msCoName](../includes/msconame-md.md)] tools and third-party tools.</span></span> <span data-ttu-id="0ff47-106">Ключевые показатели эффективности представляют собой упакованные в метаданные обычные меры и иные многомерные выражения.</span><span class="sxs-lookup"><span data-stu-id="0ff47-106">KPIs are metadata wrappers around regular measures and other Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="0ff47-107">Дополнительные сведения см. в разделе [Ключевые показатели эффективности в многомерных моделях](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="0ff47-107">For more information, see [Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ff47-108">Завершенные проекты для всех занятий в этом учебнике доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="0ff47-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="0ff47-109">Можно перейти вперед к любому занятию, используя в качестве отправной точки завершенный проект из предыдущего урока.</span><span class="sxs-lookup"><span data-stu-id="0ff47-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="0ff47-110">[Щелкните здесь](https://go.microsoft.com/fwlink/?LinkID=221866) для загрузки образцов проектов, прилагаемых к этому учебнику.</span><span class="sxs-lookup"><span data-stu-id="0ff47-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="0ff47-111">Это занятие содержит следующую задачу:</span><span class="sxs-lookup"><span data-stu-id="0ff47-111">This lesson contains the following task:</span></span>  
  
 [<span data-ttu-id="0ff47-112">Определение и поиск ключевых показателей эффективности</span><span class="sxs-lookup"><span data-stu-id="0ff47-112">Defining and Browsing KPIs</span></span>](lesson-7-1-defining-and-browsing-kpis.md)  
 <span data-ttu-id="0ff47-113">В этом задании определяются ключевые показатели эффективности в представлении формы, а затем после переключения в представление браузера данные куба просматриваются с применением этих показателей.</span><span class="sxs-lookup"><span data-stu-id="0ff47-113">In this task, you define KPIs in the Form view and then switch to the Browser view to browse the cube data by using the KPIs.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0ff47-114">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="0ff47-114">Next Lesson</span></span>  
 [<span data-ttu-id="0ff47-115">Урок 8. Определение действий</span><span class="sxs-lookup"><span data-stu-id="0ff47-115">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ff47-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ff47-116">See Also</span></span>  
 <span data-ttu-id="0ff47-117">[Analysis Services сценарий учебника](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0ff47-117">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="0ff47-118">[&#40;учебника по Adventure Works в многомерном моделировании&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="0ff47-118">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="0ff47-119">Ключевые показатели эффективности в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="0ff47-119">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)  
  
  
