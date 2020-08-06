---
title: Средства просмотра моделей интеллектуального анализа (конструктор моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.viewers.f1
ms.assetid: 4ba391d5-c97b-4848-ba7c-7d096fa4b7dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4cc1c9d72a08ef49ed2f4f466953d2ba61394178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740565"
---
# <a name="mining-model-viewers-data-mining-model-designer"></a><span data-ttu-id="7a3c2-102">Средства просмотра моделей интеллектуального анализа данных (конструктор моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-102">Mining Model Viewers (Data Mining Model Designer)</span></span>
  <span data-ttu-id="7a3c2-103">Вкладкой **Средство просмотра моделей интеллектуального анализа данных** можно воспользоваться для обзора моделей интеллектуального анализа данных, содержащихся в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-103">Use the **Mining Model Viewer** tab to explore the mining models that a mining structure contains.</span></span>

 <span data-ttu-id="7a3c2-104">Сначала необходимо выбрать модель интеллектуального анализа данных, а затем средство для ее просмотра.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-104">First you select the mining model and then you select a viewer.</span></span> <span data-ttu-id="7a3c2-105">Каждая модель имеет два доступных средства для просмотра: пользовательское, включающее несколько вкладок, и общее средство просмотра.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-105">Each model always has two viewers available: a custom viewer, which can include multiple tabs, and the generic viewer.</span></span>

 <span data-ttu-id="7a3c2-106">Пошаговое руководство по использованию каждого из средств просмотра содержится в разделе [Средства просмотра моделей интеллектуального анализа данных](data-mining/data-mining-model-viewers.md).</span><span class="sxs-lookup"><span data-stu-id="7a3c2-106">For a walkthrough of how to use each viewer, see [Data Mining Model Viewers](data-mining/data-mining-model-viewers.md).</span></span>

## <a name="common-options"></a><span data-ttu-id="7a3c2-107">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7a3c2-107">Common Options</span></span>
 <span data-ttu-id="7a3c2-108">**Обновить содержимое средства просмотра** Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-108">**Refresh viewer content** Reload the mining model in the viewer.</span></span>

 <span data-ttu-id="7a3c2-109">**Модель интеллектуального анализа данных** Выберите для просмотра модель интеллектуального анализа данных, содержащуюся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-109">**Mining Model** Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="7a3c2-110">Модель интеллектуального анализа данных откроется в связанном пользовательском средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-110">The mining model will first open in its associated custom viewer.</span></span>

 <span data-ttu-id="7a3c2-111">**Средство просмотра** Выберите средство просмотра для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-111">**Viewer** Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="7a3c2-112">В этот список входят средства просмотра, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] предоставляемые для каждой модели интеллектуального анализа данных, [!INCLUDE[msCoName](../includes/msconame-md.md)] средства просмотра содержимого интеллектуального анализа данных и средства просмотра подключаемых модулей.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-112">This list includes the viewers that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides for each mining model, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer, and any plug-in viewers.</span></span>

 <span data-ttu-id="7a3c2-113">На следующей диаграмме показаны различия между пользовательским и универсальным средствами просмотра на примере одной модели.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-113">The following diagram shows a custom viewer and the generic viewer for the same model.</span></span>

-   <span data-ttu-id="7a3c2-114">На верхней диаграмме показано средство просмотра для модели интеллектуального анализа данных, основанное на алгоритме временных рядов (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="7a3c2-114">The upper diagram shows the viewer for a mining model based on the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="7a3c2-115">Оно автоматически создает граф временного ряда и предоставляет пять прогнозов.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-115">This particular custom viewer automatically creates a graph of the time series and provides five predictions.</span></span>

-   <span data-ttu-id="7a3c2-116">На нижней диаграмме та же модель отображается с помощью **средства просмотра деревьев содержимого общего вида (Майкрософт)**.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-116">The lower diagram shows the same model displayed using the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="7a3c2-117">Это средство просмотра представляет содержимое модели интеллектуального анализа данных в соответствии со стандартизованной схемой.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-117">This viewer presents the contents of the mining model according to a standardized schema.</span></span> <span data-ttu-id="7a3c2-118">Дополнительные сведения см. в разделе [Средство просмотра деревьев содержимого общего вида (Майкрософт) (интеллектуальный анализ данных)](microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="7a3c2-118">For more information, see [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span></span>

 <span data-ttu-id="7a3c2-119">![Общие сведения о конструкторе моделей интеллектуального анализа данных](media/generic-mining-model-tab1.gif "Общие сведения о конструкторе моделей интеллектуального анализа данных")</span><span class="sxs-lookup"><span data-stu-id="7a3c2-119">![Overview of mining model designer](media/generic-mining-model-tab1.gif "Overview of mining model designer")</span></span>

## <a name="viewers-and-their-components"></a><span data-ttu-id="7a3c2-120">Средства просмотра и их компоненты</span><span class="sxs-lookup"><span data-stu-id="7a3c2-120">Viewers and Their Components</span></span>
 <span data-ttu-id="7a3c2-121">В зависимости от выбранной модели будут отображаться различные пользовательские средства просмотра, адаптированные к алгоритму, который использовался при создании выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-121">Depending on the model that you select, you will see a different custom viewer, tailored to the algorithm that you used to create the selected data mining model.</span></span> <span data-ttu-id="7a3c2-122">Каждое пользовательское средство просмотра содержит ряд инструментов и диалоговых окон, помогающих исследовать статистические показатели и закономерности изменения данных в модели.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-122">Each custom viewer has a variety of tools and dialog boxes for helping you explore the statistics and patterns in the model.</span></span>

 <span data-ttu-id="7a3c2-123">В следующем списке перечислены возможности каждого из пользовательских средств просмотра.</span><span class="sxs-lookup"><span data-stu-id="7a3c2-123">The following list describes the options in each of the custom viewers.</span></span>

### <a name="microsoft-association-rules-algorithm"></a><span data-ttu-id="7a3c2-124">Алгоритм правил взаимосвязей (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-124">Microsoft Association Rules Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-125">Просмотр модели с помощью средства просмотра правил ассоциации (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-125">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)

    -   [<span data-ttu-id="7a3c2-126">Вкладка "наборы элементов" &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-126">Itemsets Tab &#40;Mining Model Viewer&#41;</span></span>](itemsets-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-127">Вкладка правил &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-127">Rules Tab &#40;Mining Model Viewer&#41;</span></span>](rules-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-128">Вкладка Сеть зависимостей &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-128">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

### <a name="microsoft-clustering-algorithm"></a><span data-ttu-id="7a3c2-129">Алгоритм кластеризации (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-129">Microsoft Clustering Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-130">Просмотр модели с помощью средства просмотра кластеров (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-130">Browse a Model Using the Microsoft Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)

    -   [<span data-ttu-id="7a3c2-131">Вкладка Диаграмма кластеров &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-131">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-132">Вкладка "Профили кластера" &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-132">Cluster Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-133">Вкладка Характеристики кластера &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-133">Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-134">Вкладка "сравнения кластеров" &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-134">Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-135">Диалоговое окно «обозначения интеллектуального анализа данных» &#40;средство&#41;просмотра моделей интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="7a3c2-135">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-decision-tree-algorithm"></a><span data-ttu-id="7a3c2-136">Алгоритм дерева принятия решений (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-136">Microsoft Decision Tree Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-137">Просмотр модели с помощью средства просмотра деревьев (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-137">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)

    -   [<span data-ttu-id="7a3c2-138">Вкладка "дерево решений" &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-138">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-139">Вкладка Сеть зависимостей &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-139">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-140">Диалоговое окно «обозначения интеллектуального анализа данных» &#40;средство&#41;просмотра моделей интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="7a3c2-140">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-linear-regression-algorithm"></a><span data-ttu-id="7a3c2-141">Алгоритм линейной регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-141">Microsoft Linear Regression Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-142">Просмотр модели с помощью средства просмотра нейронных сетей (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-142">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="7a3c2-143">Вкладка "дерево решений" &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-143">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-144">Вкладка Сеть зависимостей &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-144">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-145">Диалоговое окно «обозначения интеллектуального анализа данных» &#40;средство&#41;просмотра моделей интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="7a3c2-145">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-logistic-regression-algorithm"></a><span data-ttu-id="7a3c2-146">Алгоритм логистической регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-146">Microsoft Logistic Regression Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-147">Просмотр модели с помощью средства просмотра нейронных сетей (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-147">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

### <a name="microsoft-nave-bayes-algorithm"></a><span data-ttu-id="7a3c2-148">Упрощенный алгоритм Байеса (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-148">Microsoft Naïve Bayes Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-149">Просмотр модели с помощью средства просмотра упрощенного алгоритма Байеса (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-149">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)

    -   [<span data-ttu-id="7a3c2-150">Вкладка Сеть зависимостей &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-150">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-151">Вкладка "Профили атрибутов" &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-151">Attribute Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-152">Вкладка Характеристики атрибута &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-152">Attribute Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-153">Вкладка "Сравнение атрибутов" &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-153">Attribute Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-discrimination-tab-mining-model-viewer.md)

### <a name="microsoft-neural-network-algorithm"></a><span data-ttu-id="7a3c2-154">Microsoft Neural Network Algorithm</span><span class="sxs-lookup"><span data-stu-id="7a3c2-154">Microsoft Neural Network Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-155">Просмотр модели с помощью средства просмотра нейронных сетей (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-155">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="7a3c2-156">Вкладка Сеть зависимостей &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-156">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-157">&#41;средства просмотра моделей интеллектуального анализа данных &#40;нейронной сети</span><span class="sxs-lookup"><span data-stu-id="7a3c2-157">Neural Network &#40;Mining Model Viewer&#41;</span></span>](neural-network-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-158">Диалоговое окно "Поиск узла" &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-158">Find Node Dialog Box &#40;Mining Model Viewer&#41;</span></span>](find-node-dialog-box-mining-model-viewer.md)

### <a name="microsoft-sequence-clustering-algorithm"></a><span data-ttu-id="7a3c2-159">Алгоритм кластеризации последовательностей (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-159">Microsoft Sequence Clustering Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-160">Просмотр модели с помощью средства просмотра кластеризации последовательностей (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-160">Browse a Model Using the Microsoft Sequence Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)

    -   [<span data-ttu-id="7a3c2-161">Диаграмма кластеризации последовательностей кластеризация вкладка &#40;средство просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="7a3c2-161">Sequence Clustering Cluster Diagram Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-162">Кластеризация последовательностей кластерные профили вкладка &#40;средство просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="7a3c2-162">Sequence Clustering Cluster Profiles Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-163">Вкладка характеристик кластера кластеризации последовательностей &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-163">Sequence Clustering Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-164">Кластер кластеризации последовательностей вкладка "Сравнение" &#40;средства просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-164">Sequence Clustering Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7a3c2-165">Вкладка перехода кластера кластеризации последовательностей &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-165">Sequence Clustering Cluster Transition Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-transition-tab-mining-model-viewer.md)

### <a name="microsoft-time-series-algorithm"></a><span data-ttu-id="7a3c2-166">Алгоритм временных рядов (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-166">Microsoft Time Series Algorithm</span></span>

-   [<span data-ttu-id="7a3c2-167">Просмотр модели с помощью средства просмотра временных рядов (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-167">Browse a Model Using the Microsoft Time Series Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)

    -   [<span data-ttu-id="7a3c2-168">Вкладка "модель" &#40;средств просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-168">Model Tab &#40;Mining Model Viewers&#41;</span></span>](model-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="7a3c2-169">Вкладка "Диаграмма" &#40;средств просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7a3c2-169">Chart Tab &#40;Mining Model Viewers&#41;</span></span>](chart-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="7a3c2-170">Диалоговое окно «обозначения интеллектуального анализа данных» &#40;средство&#41;просмотра моделей интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="7a3c2-170">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

## <a name="see-also"></a><span data-ttu-id="7a3c2-171">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a3c2-171">See Also</span></span>
 <span data-ttu-id="7a3c2-172">[Представление моделей интеллектуального анализа данных &#40;конструктор моделей интеллектуального анализа&#41;](mining-models-view-data-mining-model-designer.md) [представление структуры интеллектуального анализа данных &#40;конструктор моделей интеллектуального анализа,&#41;](mining-structure-view-data-mining-model-designer.md) [конструктор диаграмм точности интеллектуального](mining-accuracy-chart-designer-data-mining.md) анализа данных &#40;[прогноз&#41;конструктор запросов интеллектуального анализа данных &#40;](prediction-query-builder-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="7a3c2-172">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) [Mining Structure View &#40;Data Mining Model Designer&#41;](mining-structure-view-data-mining-model-designer.md) [Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) [Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md)</span></span>


