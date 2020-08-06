---
title: Свойства интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ClusterCount property
- AllowedProvidersInOpenRowset property
- MinimumSeriesValue property
- ScoreMethod property
- MinimumImportance property
- ModellingCardinality property
- BrentTolerance property
- ComplexityPenalty property
- MaximumItemsetCount property
- MinimumSupport property
- AllowSessionMiningModels property
- HoldoutPercentage property
- ClusterCountPrior property
- MaximumSequenceStates property
- OptimizedPredictionCount property
- data mining [Analysis Services], properties
- MaximumStates property
- MaximumContinuousInputAttributes property
- MaximumOutputAttributes property
- AllowAdHocOpenRowsetQueries property
- Enabled property
- HistoricModelGap property
- SampleSize property
- MaximumInputAttributes property
- PeriodicityHint property
- MissingValueSubstitution property
- SplitMethod property
- ForceRegressor property
- MaximumBucketsForContinuousSplit property
- MaxConcurrentPredictionQueries property
- MinimumItemsetSize property
- AcyclicGraph property
- HoldoutMethod property
- StoppingTolerance property
- properties [data mining]
- AutoDetectPeriodicity property
- HoldoutTolerance property
- MinimumLeafCases property
- HoldoutSeed property
- MinimumClusterCases property
- ClusterCountDeviation property
- MinimumDependencyProbability property
- ClusteringMethod property
- MaximumItemsetSize property
- HiddenNodeRatio property
- MaximumSeriesValue property
ms.assetid: 9bc9abed-180a-4bd8-b2eb-89c62fa88110
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ed1c47faafeb0c680e6afb6f8e509c426760da2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752407"
---
# <a name="data-mining-properties"></a><span data-ttu-id="71e91-102">Свойства интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="71e91-102">Data Mining Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="71e91-103">поддерживают свойства сервера интеллектуального анализа данных, перечисленные в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="71e91-103">supports the data mining server properties listed in the following tables.</span></span> <span data-ttu-id="71e91-104">Дополнительные сведения о дополнительных свойствах сервера и об их настройке см. в разделе [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="71e91-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="71e91-105">**Применимо к:** Только в многомерном режиме сервера</span><span class="sxs-lookup"><span data-stu-id="71e91-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="71e91-106">Общая категория</span><span class="sxs-lookup"><span data-stu-id="71e91-106">Non-Specific Category</span></span>  
 `AllowSessionMiningModels`  
 <span data-ttu-id="71e91-107">Логическое свойство, указывающее, можно ли создать модели интеллектуального анализа данных в сеансах.</span><span class="sxs-lookup"><span data-stu-id="71e91-107">A Boolean property that indicates whether session mining models can be created.</span></span>  
  
 <span data-ttu-id="71e91-108">Значение этого свойства по умолчанию равно false, что указывает, что модели интеллектуального анализа данных в сеансах создавать нельзя.</span><span class="sxs-lookup"><span data-stu-id="71e91-108">The default value for this property is false, which indicates that session mining models cannot be created.</span></span>  
  
 `AllowAdHocOpenRowsetQueries`  
 <span data-ttu-id="71e91-109">Логическое свойство, указывающее, разрешены ли специализированные запросы открытых наборов строк.</span><span class="sxs-lookup"><span data-stu-id="71e91-109">A Boolean property that indicates whether adhoc open rowset queries are allowed.</span></span>  
  
 <span data-ttu-id="71e91-110">Значение этого свойства по умолчанию равно false, что указывает, что запросы открытых наборов строк не разрешены во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="71e91-110">The default value for this property is false, which indicates that open rowset queries are not allowed during a session.</span></span>  
  
 `AllowedProvidersInOpenRowset`  
 <span data-ttu-id="71e91-111">Строковое свойство, идентифицирующее, какие поставщики разрешены в открытом наборе строк, состоящее из списка идентификаторов поставщиков ProgID, разделенного запятыми/точками с запятыми, или из строки «[All]».</span><span class="sxs-lookup"><span data-stu-id="71e91-111">A string property that identifies which providers are allowed in an open rowset, consisting of a comma/semi-colon separated list of provider ProgIDs, or else [All].</span></span>  
  
 `MaxConcurrentPredictionQueries`  
 <span data-ttu-id="71e91-112">Свойство с 32-разрядным целочисленным значением со знаком, определяющее максимальное количество параллельных прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="71e91-112">A signed 32-bit integer property that defines the maximum number of concurrent prediction queries.</span></span>  
  
## <a name="algorithms-category"></a><span data-ttu-id="71e91-113">Категория алгоритмов</span><span class="sxs-lookup"><span data-stu-id="71e91-113">Algorithms Category</span></span>  
 `Microsoft_Association_Rules\ Enabled`  
 <span data-ttu-id="71e91-114">Логическое свойство, указывающее, включен ли алгоритм Microsoft_Association_Rules.</span><span class="sxs-lookup"><span data-stu-id="71e91-114">A Boolean property that indicates whether the Microsoft_Association_Rules algorithm is enabled.</span></span>  
  
 `Microsoft_Clustering\ Enabled`  
 <span data-ttu-id="71e91-115">Логическое свойство, указывающее, включен ли алгоритм Microsoft_Clustering.</span><span class="sxs-lookup"><span data-stu-id="71e91-115">A Boolean property that indicates whether the Microsoft_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Decision_Trees\ Enabled`  
 <span data-ttu-id="71e91-116">Логическое свойство, указывающее, включен ли алгоритм Microsoft_DecisionTrees.</span><span class="sxs-lookup"><span data-stu-id="71e91-116">A Boolean property that indicates whether the Microsoft_DecisionTrees algorithm is enabled.</span></span>  
  
 `Microsoft_Naive_Bayes\ Enabled`  
 <span data-ttu-id="71e91-117">Логическое свойство, указывающее, включен ли алгоритм Microsoft_Naive_Bayes.</span><span class="sxs-lookup"><span data-stu-id="71e91-117">A Boolean property that indicates whether the Microsoft_ Naive_Bayes algorithm is enabled.</span></span>  
  
 `Microsoft_Neural_Network\ Enabled`  
 <span data-ttu-id="71e91-118">Логическое свойство, указывающее, включен ли алгоритм Microsoft_Neural_Network.</span><span class="sxs-lookup"><span data-stu-id="71e91-118">A Boolean property that indicates whether the Microsoft_Neural_Network algorithm is enabled.</span></span>  
  
 `Microsoft_Sequence_Clustering\ Enabled`  
 <span data-ttu-id="71e91-119">Логическое свойство, указывающее, включен ли алгоритм Microsoft_Sequence_Clustering.</span><span class="sxs-lookup"><span data-stu-id="71e91-119">A Boolean property that indicates whether the Microsoft_Sequence_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Time_Series\ Enabled`  
 <span data-ttu-id="71e91-120">Логическое свойство, указывающее, включен ли алгоритм Microsoft_Time_Series.</span><span class="sxs-lookup"><span data-stu-id="71e91-120">A Boolean property that indicates whether the Microsoft_Time_Series algorithm is enabled.</span></span>  
  
 `Microsoft_Linear_Regression\ Enabled`  
 <span data-ttu-id="71e91-121">Логическое свойство, указывающее, включен ли алгоритм Microsoft_Linear_Regression.</span><span class="sxs-lookup"><span data-stu-id="71e91-121">A Boolean property that indicates whether the Microsoft_Linear_Regression algorithm is enabled.</span></span>  
  
 `Microsoft_Logistic_Regression\ Enabled`  
 <span data-ttu-id="71e91-122">Логическое свойство, указывающее, включен ли алгоритм Microsoft_Logistic_Regression.</span><span class="sxs-lookup"><span data-stu-id="71e91-122">A Boolean property that indicates whether the Microsoft_Logistic_Regression algorithm is enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71e91-123">В дополнение к свойствам, которые определяют доступные службы интеллектуального анализа данных на сервере, имеются свойства интеллектуального анализа данных, определяющие поведение конкретных алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="71e91-123">In addition to properties that define the data mining services available on the server, there are data mining properties that define the behavior of specific algorithms.</span></span> <span data-ttu-id="71e91-124">Настройка этих свойств осуществляется при создании каждой отдельной модели интеллектуального анализа данных, а не на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="71e91-124">You configure these properties when you create an individual data mining model, not at the server level.</span></span> <span data-ttu-id="71e91-125">Дополнительные сведения см. в разделе [Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="71e91-125">For more information, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e91-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="71e91-126">See Also</span></span>  
 <span data-ttu-id="71e91-127">[Физическая архитектура &#40;Analysis Services-интеллектуальный анализ данных&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="71e91-127">[Physical Architecture &#40;Analysis Services - Data Mining&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="71e91-128">[Настройка свойств сервера в Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="71e91-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="71e91-129">Определение режима работы сервера экземпляра служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="71e91-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
