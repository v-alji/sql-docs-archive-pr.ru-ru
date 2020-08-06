---
title: Справка F1 мастера статистических схем | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Aggregation Design Wizard
ms.assetid: 39e23cf1-6405-4fb6-bc14-ba103314362d
author: minewiskan
ms.author: owend
ms.openlocfilehash: ace30a07970b1871d037ebe6f31b2079f1895ffa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656946"
---
# <a name="aggregation-design-wizard-f1-help"></a><span data-ttu-id="af8d8-102">Справка F1 мастера статистических схем</span><span class="sxs-lookup"><span data-stu-id="af8d8-102">Aggregation Design Wizard F1 Help</span></span>
  <span data-ttu-id="af8d8-103">Агрегаты обеспечивают повышение производительности, позволяя [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] извлекать предварительно вычисленные итоги непосредственно из хранилища куба вместо того, чтобы пересчитывать данные из базового источника данных для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="af8d8-103">Aggregations provide performance improvements by allowing [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to retrieve pre-calculated totals directly from cube storage instead of having to recalculate data from an underlying data source for each query.</span></span>  
  
 <span data-ttu-id="af8d8-104">Для создания таких схем может быть использован мастер статистических схем.</span><span class="sxs-lookup"><span data-stu-id="af8d8-104">To design these aggregations, you can use the Aggregation Design Wizard.</span></span> <span data-ttu-id="af8d8-105">Мастер помогает выполнять следующие этапы:</span><span class="sxs-lookup"><span data-stu-id="af8d8-105">This wizard guides you through the following steps:</span></span>  
  
-   <span data-ttu-id="af8d8-106">Выбор стандартных или специальных настроек для хранилища и параметров кэша секции, группы мер или куба.</span><span class="sxs-lookup"><span data-stu-id="af8d8-106">Selecting standard or custom settings for the storage and caching options of a partition, measure group, or cube.</span></span>  
  
-   <span data-ttu-id="af8d8-107">Предоставление предполагаемого или фактического числа объектов, на которые ссылается секция, группа мер или куб.</span><span class="sxs-lookup"><span data-stu-id="af8d8-107">Providing estimated or actual counts for objects referenced by the partition, measure group, or cube.</span></span>  
  
-   <span data-ttu-id="af8d8-108">Определение статистических параметров и ограничений, чтобы оптимизировать хранилище и повысить производительность запросов, предоставляемых разработанными статистическими схемами.</span><span class="sxs-lookup"><span data-stu-id="af8d8-108">Specifying aggregation options and limits to optimize the storage and query performance delivered by designed aggregations.</span></span>  
  
-   <span data-ttu-id="af8d8-109">Сохранение и возможность обработки секции, группы мер или куба для создания определяемых статистических схем.</span><span class="sxs-lookup"><span data-stu-id="af8d8-109">Saving and optionally processing the partition, measure group, or cube to generate the defined aggregations.</span></span>  
  
 <span data-ttu-id="af8d8-110">После использования мастера статистических схем можно использовать мастер оптимизации с учетом использования для проектирования статистических схем на основе вариантов использования пользователями и клиентскими приложениями, которые создают запросы к кубу.</span><span class="sxs-lookup"><span data-stu-id="af8d8-110">After you use the Aggregation Design Wizard, you can use the Usage-Based Optimization Wizard to design aggregations based on the usage patterns of the business users and client applications that query the cube.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af8d8-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="af8d8-111">In This Section</span></span>  
  
-   [<span data-ttu-id="af8d8-112">Выберите секции для изменения мастера статистических схем &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="af8d8-112">Select Partitions to Modify &#40;Aggregation Design Wizard&#41;</span></span>](select-partitions-to-modify-aggregation-design-wizard.md)  
  
-   [<span data-ttu-id="af8d8-113">Обзор использования статистической обработки &#40;мастера статистических схем&#41;</span><span class="sxs-lookup"><span data-stu-id="af8d8-113">Review Aggregation Usage &#40;Aggregation Design Wizard&#41;</span></span>](review-aggregation-usage-aggregation-design-wizard.md)  
  
-   [<span data-ttu-id="af8d8-114">Указание счетчиков объектов &#40;мастера статистических схем&#41;</span><span class="sxs-lookup"><span data-stu-id="af8d8-114">Specify Object Counts &#40;Aggregation Design Wizard&#41;</span></span>](specify-object-counts-aggregation-design-wizard.md)  
  
-   [<span data-ttu-id="af8d8-115">Настройка параметров статистической обработки &#40;мастера статистических схем&#41;</span><span class="sxs-lookup"><span data-stu-id="af8d8-115">Set Aggregation Options &#40;Aggregation Design Wizard&#41;</span></span>](set-aggregation-options-aggregation-design-wizard.md)  
  
-   [<span data-ttu-id="af8d8-116">Завершение работы мастера &#40;мастера статистических схем&#41;</span><span class="sxs-lookup"><span data-stu-id="af8d8-116">Completing the Wizard &#40;Aggregation Design Wizard&#41;</span></span>](completing-the-wizard-aggregation-design-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="af8d8-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="af8d8-117">See Also</span></span>  
 <span data-ttu-id="af8d8-118">[Агрегаты и статистические схемы](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md) </span><span class="sxs-lookup"><span data-stu-id="af8d8-118">[Aggregations and Aggregation Designs](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md) </span></span>  
 <span data-ttu-id="af8d8-119">[Кубы в многомерных моделях](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="af8d8-119">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="af8d8-120">[Справка F1 мастера оптимизации с учетом использования](usage-based-optimization-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="af8d8-120">[Usage-Based Optimization Wizard F1 Help](usage-based-optimization-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="af8d8-121">Analysis Services мастера &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="af8d8-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
