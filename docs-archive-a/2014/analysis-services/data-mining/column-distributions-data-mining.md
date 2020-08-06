---
title: Распределения столбцов (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- normal distribution type [data mining]
- uniform distribution type [data mining]
- columns [data mining], distributions
- log normal distribution type [data mining]
- continuous columns
- distributions [data mining]
ms.assetid: 87e700de-32be-4bc8-b01d-ba4ee1ab48de
author: minewiskan
ms.author: owend
ms.openlocfilehash: 29aad33535c4cc4d9baf4c453249ce3b51595e78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669187"
---
# <a name="column-distributions-data-mining"></a><span data-ttu-id="ccce7-102">Распределения столбцов (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="ccce7-102">Column Distributions (Data Mining)</span></span>
  <span data-ttu-id="ccce7-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] можно определить распределения столбцов в структуре интеллектуального анализа данных, чтобы повлиять на то, как алгоритмы обрабатывают данные в этих столбцах при создании моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ccce7-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can define column distributions in a mining structure, to affect how algorithms process the data in those columns when you create mining models.</span></span> <span data-ttu-id="ccce7-104">В некоторых алгоритмах лучше задавать распределение для всех столбцов, содержащих непрерывные данные, до начала обработки модели в случае, если указанные столбцы содержат общие распределения значений.</span><span class="sxs-lookup"><span data-stu-id="ccce7-104">For some algorithms, it is useful to define the distribution of any continuous columns before you process the model, if the columns are known to contain common distributions of values.</span></span> <span data-ttu-id="ccce7-105">Если распределения не заданы, создаваемые модели интеллектуального анализа данных могут работать менее точно, чем модели с заданными распределениями, так как на вход алгоритмов будет подаваться меньшее количество данных для анализа.</span><span class="sxs-lookup"><span data-stu-id="ccce7-105">If you do not define the distributions, the resulting mining models may produce less accurate predictions than if the distributions were defined, because the algorithms will have less information from which to interpret the data.</span></span>

 <span data-ttu-id="ccce7-106">Алгоритмы, доступные в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , поддерживают следующие типы распределения.</span><span class="sxs-lookup"><span data-stu-id="ccce7-106">The algorithms that are available in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support the following distribution types:</span></span>

 <span data-ttu-id="ccce7-107">`Normal`Значения непрерывного столбца формируют гистограмму с нормальным распределением.</span><span class="sxs-lookup"><span data-stu-id="ccce7-107">`Normal` The values for the continuous column form a histogram with a normal distribution.</span></span>

 <span data-ttu-id="ccce7-108">![Гистограмма с нормальным распределением](../media/normal-distribution.gif "Гистограмма с нормальным распределением")</span><span class="sxs-lookup"><span data-stu-id="ccce7-108">![Histogram with normal distribution](../media/normal-distribution.gif "Histogram with normal distribution")</span></span>

 <span data-ttu-id="ccce7-109">`Log Normal`Значения для непрерывного столбца формируют гистограмму, где кривая вытянута в верхней части и наклонена в сторону нижней границы.</span><span class="sxs-lookup"><span data-stu-id="ccce7-109">`Log Normal` The values for the continuous column form a histogram, where the curve is elongated at the upper end and is skewed toward the lower end.</span></span>

 <span data-ttu-id="ccce7-110">![Гистограмма с логарифмически нормальным распределением](../media/log-normal-distribution.gif "Гистограмма с логарифмически нормальным распределением")</span><span class="sxs-lookup"><span data-stu-id="ccce7-110">![Histogram with log normal distribution](../media/log-normal-distribution.gif "Histogram with log normal distribution")</span></span>

 <span data-ttu-id="ccce7-111">`Uniform`Значения непрерывного столбца образуют плоскую кривую, в которой все значения имеют одинаковую вероятность.</span><span class="sxs-lookup"><span data-stu-id="ccce7-111">`Uniform` The values for the continuous column form a flat curve, in which all values are equally likely.</span></span>

 <span data-ttu-id="ccce7-112">![Гистограмма с равномерным распределением](../media/uniform-distribution.gif "Гистограмма с равномерным распределением")</span><span class="sxs-lookup"><span data-stu-id="ccce7-112">![Histogram with uniform distribution](../media/uniform-distribution.gif "Histogram with uniform distribution")</span></span>

 <span data-ttu-id="ccce7-113">Дополнительные сведения об алгоритмах в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] см. в разделе [Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ccce7-113">For more information about the algorithms that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ccce7-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="ccce7-114">See Also</span></span>
 <span data-ttu-id="ccce7-115">[Типы содержимого &#40;интеллектуального анализа&#41;](content-types-data-mining.md) [структур интеллектуального анализа данных &#40;Analysis Services —](mining-structures-analysis-services-data-mining.md) [методы дискретизации](discretization-methods-data-mining.md)&#41;интеллектуального анализа данных &#40;[распределения&#41;DMX](/sql/dmx/distributions-dmx) &#40;[столбцы структуры интеллектуального](mining-structure-columns.md) анализа данных</span><span class="sxs-lookup"><span data-stu-id="ccce7-115">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) [Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) [Discretization Methods &#40;Data Mining&#41;](discretization-methods-data-mining.md) [Distributions &#40;DMX&#41;](/sql/dmx/distributions-dmx) [Mining Structure Columns](mining-structure-columns.md)</span></span>


