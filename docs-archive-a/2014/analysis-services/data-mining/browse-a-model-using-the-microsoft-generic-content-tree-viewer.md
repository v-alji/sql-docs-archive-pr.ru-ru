---
title: Просмотр модели с помощью средства просмотра деревьев содержимого общего вида (Майкрософт) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining model content, viewing
ms.assetid: 4a5f7c51-c704-4214-b05d-21cf735e6d96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90d47262a09060a11020e50b3724753799d2d188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668543"
---
# <a name="browse-a-model-using-the-microsoft-generic-content-tree-viewer"></a><span data-ttu-id="6cb55-102">Просмотр модели в средстве просмотра деревьев содержимого общего вида (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="6cb55-102">Browse a Model Using the Microsoft Generic Content Tree Viewer</span></span>
  <span data-ttu-id="6cb55-103">Средство просмотра содержимого общего вида модели интеллектуального анализа данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] предоставляет подробные сведения о закономерностях, обнаруженных алгоритмом интеллектуального анализа данных, а также доступ к различной статистической информации, созданной в процессе анализа.</span><span class="sxs-lookup"><span data-stu-id="6cb55-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Mining Model Content Viewer provides detailed information about the patterns found by the mining algorithm, and also provides access to various statistics generated during the analysis process.</span></span> <span data-ttu-id="6cb55-104">Объем и тип этих сведений зависит от использованного алгоритма, но может включать в себя следующие категории:</span><span class="sxs-lookup"><span data-stu-id="6cb55-104">The amount and type of information depends on the algorithm that was used, but can include the following categories:</span></span>  
  
-   <span data-ttu-id="6cb55-105">сегменты данных и их характеристики;</span><span class="sxs-lookup"><span data-stu-id="6cb55-105">Segments of data, and their characteristics.</span></span>  
  
-   <span data-ttu-id="6cb55-106">описательную статистику для каждой группы или для набора данных в целом;</span><span class="sxs-lookup"><span data-stu-id="6cb55-106">Descriptive statistics about each group or about the whole set of data.</span></span>  
  
-   <span data-ttu-id="6cb55-107">количество ветвей или дочерних узлов дерева;</span><span class="sxs-lookup"><span data-stu-id="6cb55-107">The number of branches or child nodes in a tree.</span></span>  
  
-   <span data-ttu-id="6cb55-108">результаты вычислений (например, дисперсию и среднее значение) для кластера или набора данных в целом.</span><span class="sxs-lookup"><span data-stu-id="6cb55-108">Calculations, such as variance and mean, for a cluster or a whole set of data.</span></span>  
  
 <span data-ttu-id="6cb55-109">Просмотр этих сведений поможет лучше понять результаты анализа.</span><span class="sxs-lookup"><span data-stu-id="6cb55-109">Viewing this information can help you better understand the results of your analysis.</span></span> <span data-ttu-id="6cb55-110">Кроме того, можно выявить способы настройки и повторного обучения модели.</span><span class="sxs-lookup"><span data-stu-id="6cb55-110">You can also identify ways to fine-tune, and then retrain, your model.</span></span> <span data-ttu-id="6cb55-111">Можно также принять решение о повторном обучении модели с помощью другого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="6cb55-111">Or, you might decide to retrain by using a different algorithm.</span></span>  
  
## <a name="viewing-mining-model-content"></a><span data-ttu-id="6cb55-112">Просмотр содержимого модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="6cb55-112">Viewing Mining Model Content</span></span>  
 <span data-ttu-id="6cb55-113">Средство просмотра общего содержимого [!INCLUDE[msCoName](../../includes/msconame-md.md)] отображает столбцы, правила, свойства, атрибуты, узлы и другое содержимое *набора строк схемы содержимого* модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6cb55-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Viewer displays the columns, rules, properties, attributes, nodes, and other content from the *content schema rowset* of the mining model.</span></span> <span data-ttu-id="6cb55-114">Набор строк схемы содержимого представляет собой общую платформу, предназначенную для предоставления подробных сведений о содержимом модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6cb55-114">The content schema rowset is a generic framework for presenting detailed information about the content of a data mining model.</span></span>  
  
 <span data-ttu-id="6cb55-115">Эти подробные сведения содержатся в HTML-таблице, которая представляет шаблоны, кластеры или деревья модели в виде узлов.</span><span class="sxs-lookup"><span data-stu-id="6cb55-115">This detailed information is contained in an HTML table that represents the patterns, clusters, or trees in the model as nodes.</span></span> <span data-ttu-id="6cb55-116">Если щелкнуть по отдельному узлу и развернуть его, можно увидеть подробные сведения, включая формулы или счетчик различных значений для числового атрибута.</span><span class="sxs-lookup"><span data-stu-id="6cb55-116">You can click on each node and expand it to see more detail, such as the formulas or the count of distinct values for a numeric attribute.</span></span> <span data-ttu-id="6cb55-117">Можно также изучить отношения дочерних и родительских элементов узлов.</span><span class="sxs-lookup"><span data-stu-id="6cb55-117">You can also explore the child-parent relationships among the nodes.</span></span>  
  
 <span data-ttu-id="6cb55-118">Дополнительные сведения об общем значении терминов, используемых в содержимом модели интеллектуального анализа данных, см. в разделе [Содержимое модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6cb55-118">For more information about the general meaning of the terms used in the mining model content, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span> <span data-ttu-id="6cb55-119">В этом разделе также приводятся ссылки на сведения о содержимом для определенных типов моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6cb55-119">The topic also contains links to information about mining model content for specific types of models.</span></span> <span data-ttu-id="6cb55-120">Каждый тип модели интеллектуального анализа данных содержит сведения, которые сильно зависят от алгоритма и закономерностей, обнаруженных в данных, поэтому рекомендуется ознакомиться с разделом технического справочника по каждому типу модели, чтобы полностью понять их принцип работы.</span><span class="sxs-lookup"><span data-stu-id="6cb55-120">Each type of mining model contains information that is highly specific to the algorithm and the patterns found in the data, so we recommend that you consult the technical reference topic for each model type in order to fully understand each model type.</span></span>  
  
## <a name="querying-mining-model-content"></a><span data-ttu-id="6cb55-121">Запрос содержимого модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="6cb55-121">Querying Mining Model Content</span></span>  
 <span data-ttu-id="6cb55-122">Сведения, предоставляемые средством просмотра деревьев общего содержимого [!INCLUDE[msCoName](../../includes/msconame-md.md)] , можно также получить с помощью запросов к модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6cb55-122">The same information that is provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer is also available by querying the mining model.</span></span> <span data-ttu-id="6cb55-123">Запросы к набору строк схемы модели интеллектуального анализа данных можно создавать при помощи инструкций на языке расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6cb55-123">You can create queries against mining model content by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="6cb55-124">Например, в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]запросить содержимое можно, выполнив следующую инструкцию на языке расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6cb55-124">For example, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can run a content query by executing the following DMX statement:</span></span>  
  
```  
SELECT * FROM [<mining model name>].CONTENT  
```  
  
 <span data-ttu-id="6cb55-125">Дополнительные сведения см. в статье [Запросы интеллектуального анализа данных](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6cb55-125">For more information, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb55-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="6cb55-126">See Also</span></span>  
 <span data-ttu-id="6cb55-127">[Средство просмотра деревьев содержимого общего вида (Майкрософт) &#40;интеллектуального анализа данных&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6cb55-127">[Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span></span>  
 [<span data-ttu-id="6cb55-128">Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="6cb55-128">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
  
