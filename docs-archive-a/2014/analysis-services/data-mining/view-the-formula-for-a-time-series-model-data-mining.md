---
title: Просмотр формулы для модели временных рядов (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- ARTXP
- time series algorithms [Analysis Services]
- ARIMA
- time series [Analysis Services]
- Time Series Viewer [Analysis Services]
ms.assetid: 825ef719-2f44-4979-be01-5a81f54e1a53
author: minewiskan
ms.author: owend
ms.openlocfilehash: eff61c469d34f084e6a0eb11c49a1c37c7cc97c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654588"
---
# <a name="view-the-formula-for-a-time-series-model-data-mining"></a><span data-ttu-id="eba2e-102">Просмотр формулы для модели временных рядов (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="eba2e-102">View the Formula for a Time Series Model (Data Mining)</span></span>
  <span data-ttu-id="eba2e-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)]Конструктор интеллектуального анализа данных средства просмотра временных рядов предоставляет самый простой способ просмотра формулы регрессии, используемой в модели временных рядов.</span><span class="sxs-lookup"><span data-stu-id="eba2e-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series viewer inData Mining Designer provides the easiest way to view the details of the regression equation used in a time series model.</span></span>  
  
 <span data-ttu-id="eba2e-104">Формулу регрессии для модели временных рядов можно получить с помощью запроса к содержимому модели.</span><span class="sxs-lookup"><span data-stu-id="eba2e-104">You can extract the regression formula for a time series model by querying the model content.</span></span> <span data-ttu-id="eba2e-105">Однако для просмотра полной формулы ARTXP или ARIMA рекомендуется использовать **Условные обозначения интеллектуального анализа данных** [средства просмотра временных рядов (Майкрософт](browse-a-model-using-the-microsoft-time-series-viewer.md)), которые представляют все константы в удобном для чтения формате.</span><span class="sxs-lookup"><span data-stu-id="eba2e-105">However, to view the complete ARTXP or ARIMA formula, we recommend that you use the **Mining Legend** of the [Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md), which presents all the constants in a readable format.</span></span>  
  
 <span data-ttu-id="eba2e-106">Если создать модель смешанного типа, в модели будут два отдельных дерева: одно для алгоритма ARIMA и одно для ARTXP. При этом они будут объединены в корневом узле, представляющем модель.</span><span class="sxs-lookup"><span data-stu-id="eba2e-106">If you create a mixed model, the ARIMA and ARTXP analyses are created in separate trees, joined at the root node representing the model.</span></span> <span data-ttu-id="eba2e-107">Структуры деревьев ARIMA и ARTXP сильно отличаются друг от друга.</span><span class="sxs-lookup"><span data-stu-id="eba2e-107">The structures of the ARIMA and ARTXP trees are very different.</span></span> <span data-ttu-id="eba2e-108">Например, дерево ARTXP на самом деле является структурой дерева как дерева принятия решений, в то время как дерево ARIMA представляет собой последовательность скользящих средних значений.</span><span class="sxs-lookup"><span data-stu-id="eba2e-108">For example, the ARTXP tree is in fact a tree structure, like a decision tree, whereas the ARIMA tree represents a series of moving averages.</span></span> <span data-ttu-id="eba2e-109">Поэтому, даже если в одной модели для удобства используются два типа представления данных, с ними следует работать так, как если бы это были две независимые модели.</span><span class="sxs-lookup"><span data-stu-id="eba2e-109">Therefore, although the two representations are presented in one model for convenience, they should be treated as two independent models.</span></span> <span data-ttu-id="eba2e-110">Уравнения также коренным образом отличаются; их нельзя скомбинировать или сравнить.</span><span class="sxs-lookup"><span data-stu-id="eba2e-110">The equations are also completely different and cannot be combined or compared.</span></span>  
  
 <span data-ttu-id="eba2e-111">Также можно просмотреть модели временных рядов с помощью [средства просмотра деревьев содержимого общего вида (Майкрософт](../microsoft-generic-content-tree-viewer-data-mining.md)).</span><span class="sxs-lookup"><span data-stu-id="eba2e-111">You can also view time series models by using the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="eba2e-112">Дополнительные сведения о содержимом модели временных рядов см. в разделе [содержимое моделей интеллектуального анализа данных для моделей временных рядов &#40;Analysis Services&#41;интеллектуального анализа ](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="eba2e-112">For more information about the content of a time series model, see [Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-view-the-artxp-regression-formula-for-a-time-series-model"></a><span data-ttu-id="eba2e-113">Просмотр формулы регрессии ARTXP для модели временных рядов</span><span class="sxs-lookup"><span data-stu-id="eba2e-113">To view the ARTXP regression formula for a time series model</span></span>  
  
1.  <span data-ttu-id="eba2e-114">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]выберите модель временных рядов, которую нужно просмотреть, и щелкните **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="eba2e-114">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="eba2e-115">-- или --</span><span class="sxs-lookup"><span data-stu-id="eba2e-115">-- or --</span></span>  
  
     <span data-ttu-id="eba2e-116">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]выберите модель временных рядов и перейдите на вкладку **Средство просмотра моделей интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="eba2e-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="eba2e-117">Перейдите на вкладку **Model** (Модель).</span><span class="sxs-lookup"><span data-stu-id="eba2e-117">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="eba2e-118">Если модель содержит несколько деревьев, можно просмотреть отдельное дерево, выбрав его в раскрывающемся списке **Дерево** .</span><span class="sxs-lookup"><span data-stu-id="eba2e-118">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eba2e-119">При наличии нескольких рядов данных модель всегда будет содержать несколько деревьев.</span><span class="sxs-lookup"><span data-stu-id="eba2e-119">A model will always have multiple trees if you have more than one data series.</span></span> <span data-ttu-id="eba2e-120">Однако с помощью **средства просмотра временных рядов** можно увидеть меньше деревьев, чем с помощью [средства просмотра деревьев содержимого общего вида (Майкрософт)](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="eba2e-120">However, you will not see as many trees in the **Time Series viewer** as you will see in the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="eba2e-121">Это происходит потому, что средство просмотра временных рядов комбинирует информацию ARIMA и ARTXP для каждого ряда данных в единое представление.</span><span class="sxs-lookup"><span data-stu-id="eba2e-121">That is because the Time Series viewer combines the ARIMA and ARTXP information for each data series into a single representation.</span></span>  
  
4.  <span data-ttu-id="eba2e-122">Щелкните любой конечный узел дерева.</span><span class="sxs-lookup"><span data-stu-id="eba2e-122">Click any leaf node in the tree.</span></span>  
  
     <span data-ttu-id="eba2e-123">Узлы, помеченные как **Ряды данных** , всегда являются конечными и могут содержать уравнения.</span><span class="sxs-lookup"><span data-stu-id="eba2e-123">Nodes that are labeled as **Data Series** are always leaf nodes and can contain an equation.</span></span> <span data-ttu-id="eba2e-124">Если у узла **(Все)** нет дочерних узлов, он также может содержать уравнение.</span><span class="sxs-lookup"><span data-stu-id="eba2e-124">If an **(All)** node has no child nodes, it can also contain an equation.</span></span>  
  
5.  <span data-ttu-id="eba2e-125">Если вкладка **Условные обозначения интеллектуального анализа данных** недоступна, щелкните узел правой кнопкой мыши и выберите **Показать обозначения**.</span><span class="sxs-lookup"><span data-stu-id="eba2e-125">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
     <span data-ttu-id="eba2e-126">В первой половине вкладки **Условные обозначения интеллектуального анализа данных**в области **Уравнение узла дерева**выводится формула ARTXP.</span><span class="sxs-lookup"><span data-stu-id="eba2e-126">The ARTXP formula is displayed in the first half of the **Mining Legend**, as the **Tree node equation**.</span></span>  
  
### <a name="to-view-the-arima-formula-for-a-time-series-model"></a><span data-ttu-id="eba2e-127">Просмотр формулы ARIMA для модели временных рядов</span><span class="sxs-lookup"><span data-stu-id="eba2e-127">To view the ARIMA formula for a time series model</span></span>  
  
1.  <span data-ttu-id="eba2e-128">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]выберите модель временных рядов, которую нужно просмотреть, и щелкните **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="eba2e-128">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="eba2e-129">-- или --</span><span class="sxs-lookup"><span data-stu-id="eba2e-129">-- or --</span></span>  
  
     <span data-ttu-id="eba2e-130">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]выберите модель временных рядов и перейдите на вкладку **Средство просмотра моделей интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="eba2e-130">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="eba2e-131">Перейдите на вкладку **Model** (Модель).</span><span class="sxs-lookup"><span data-stu-id="eba2e-131">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="eba2e-132">Если модель содержит несколько деревьев, можно просмотреть отдельное дерево, выбрав его в раскрывающемся списке **Дерево** .</span><span class="sxs-lookup"><span data-stu-id="eba2e-132">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eba2e-133">При включении нескольких рядов данных модель всегда будет содержать несколько деревьев.</span><span class="sxs-lookup"><span data-stu-id="eba2e-133">The model will always have multiple trees if you include more than one data series.</span></span>  
  
4.  <span data-ttu-id="eba2e-134">Щелкните любой узел дерева.</span><span class="sxs-lookup"><span data-stu-id="eba2e-134">Click any node in the tree.</span></span>  
  
     <span data-ttu-id="eba2e-135">Во второй половине вкладки **Условные обозначения интеллектуального анализа данных**в области **Уравнение ARIMA**выводится формула ARIMA.</span><span class="sxs-lookup"><span data-stu-id="eba2e-135">The ARIMA formula is displayed in the second half of the **Mining Legend**, as the **ARIMA equation**.</span></span>  
  
5.  <span data-ttu-id="eba2e-136">Если вкладка **Условные обозначения интеллектуального анализа данных** недоступна, щелкните узел правой кнопкой мыши и выберите **Показать обозначения**.</span><span class="sxs-lookup"><span data-stu-id="eba2e-136">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba2e-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="eba2e-137">See Also</span></span>  
 <span data-ttu-id="eba2e-138">[Задачи и инструкции средства просмотра моделей интеллектуального анализа данных](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="eba2e-138">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="eba2e-139">[Просмотр модели с помощью средства просмотра временных рядов (Майкрософт)](browse-a-model-using-the-microsoft-time-series-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="eba2e-139">[Browse a Model Using the Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md) </span></span>  
 [<span data-ttu-id="eba2e-140">Примеры запросов моделей временных рядов</span><span class="sxs-lookup"><span data-stu-id="eba2e-140">Time Series Model Query Examples</span></span>](time-series-model-query-examples.md)  
  
  
