---
title: Вкладка "Сеть зависимостей" (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.dependencynetwork.f1
ms.assetid: e58ce1b7-20d6-42cb-ade5-916da8471e09
author: minewiskan
ms.author: owend
ms.openlocfilehash: 94ce82524445ffb8999c671c736087362ef0adfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728934"
---
# <a name="dependency-network-tab-mining-model-viewer"></a><span data-ttu-id="303e4-102">Вкладка «Сеть зависимостей» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="303e4-102">Dependency Network Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="303e4-103">Вкладка **Сеть зависимостей** обеспечивает графическое представление всех атрибутов, содержащихся в модели интеллектуального анализа данных, и показывает отношения этих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="303e4-103">The **Dependency Net** tab provides a graphical view of all attributes that the mining model contains, and shows how the attributes are related.</span></span>  
  
 <span data-ttu-id="303e4-104">Вкладка **Сеть зависимостей**  используется для нескольких типов моделей интеллектуального анализа данных, в том числе моделей упрощенного алгоритма Байеса, моделей дерева принятия решений и моделей взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="303e4-104">The **Dependency Net**  tab is used for several types of mining models, including Naïve Bayes models, decision tree models, and association models.</span></span> <span data-ttu-id="303e4-105">Дополнительные сведения о том, как трактовать содержимое вкладки **Сеть зависимостей**  в контексте этих моделей, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="303e4-105">For more information about how to interpret the contents of the **Dependency Net**  tab in the context of these models, see the following links:</span></span>  
  
 [<span data-ttu-id="303e4-106">Просмотр модели с помощью средства просмотра деревьев (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="303e4-106">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
 [<span data-ttu-id="303e4-107">Просмотр модели с помощью средства просмотра упрощенного алгоритма Байеса (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="303e4-107">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)  
  
 [<span data-ttu-id="303e4-108">Просмотр модели с помощью средства просмотра правил ассоциации (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="303e4-108">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)  
  
## <a name="options"></a><span data-ttu-id="303e4-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="303e4-109">Options</span></span>  
 <span data-ttu-id="303e4-110">**Обновить содержимое средства просмотра**</span><span class="sxs-lookup"><span data-stu-id="303e4-110">**Refresh viewer content**</span></span>  
 <span data-ttu-id="303e4-111">Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="303e4-111">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="303e4-112">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="303e4-112">**Mining Model**</span></span>  
 <span data-ttu-id="303e4-113">Выбрать модель интеллектуального анализа данных для просмотра из числа содержащихся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="303e4-113">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="303e4-114">Модель интеллектуального анализа данных откроется в пользовательском средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="303e4-114">The mining model will open in a custom viewer.</span></span> <span data-ttu-id="303e4-115">Тип пользовательского средства просмотра, используемого для каждой модели, определяется алгоритмом, использованным при создании модели.</span><span class="sxs-lookup"><span data-stu-id="303e4-115">The type of custom viewer that is used for each model is determined by the algorithm that you used to create the model.</span></span>  
  
 <span data-ttu-id="303e4-116">**Зритель**</span><span class="sxs-lookup"><span data-stu-id="303e4-116">**Viewer**</span></span>  
 <span data-ttu-id="303e4-117">Выберите средство просмотра для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="303e4-117">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="303e4-118">Для каждой модели можно применить пользовательское средство просмотра, предоставленное для каждой модели интеллектуального анализа данных, или средство просмотра содержимого интеллектуального анализа данных [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="303e4-118">For each model, you can use either the custom viewer is provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="303e4-119">Также можно использовать подключаемые модули просмотра, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="303e4-119">You can also use plug-in viewers if available.</span></span> <span data-ttu-id="303e4-120">Средство просмотра деревьев содержимого общего вида (Майкрософт) может использоваться со всеми моделями и представляет содержимое модели в виде HTML-таблицы.</span><span class="sxs-lookup"><span data-stu-id="303e4-120">The Microsoft Content Tree Viewer can be used with all models, and represents the model content in an HTML table.</span></span>  
  
 <span data-ttu-id="303e4-121">**Увеличить масштаб**</span><span class="sxs-lookup"><span data-stu-id="303e4-121">**Zoom In**</span></span>  
 <span data-ttu-id="303e4-122">Увеличить масштаб диаграммы, что позволит увидеть атрибуты более подробно.</span><span class="sxs-lookup"><span data-stu-id="303e4-122">Zoom in to the diagram, so that you can see the attributes in more detail.</span></span>  
  
 <span data-ttu-id="303e4-123">**Уменьшить масштаб**</span><span class="sxs-lookup"><span data-stu-id="303e4-123">**Zoom Out**</span></span>  
 <span data-ttu-id="303e4-124">Уменьшить масштаб диаграммы, что позволит увидеть больше атрибутов и связей между ними.</span><span class="sxs-lookup"><span data-stu-id="303e4-124">Zoom out from the diagram, so that you can see more attributes and the links between them.</span></span>  
  
 <span data-ttu-id="303e4-125">**Копировать представление диаграммы**</span><span class="sxs-lookup"><span data-stu-id="303e4-125">**Copy Graph View**</span></span>  
 <span data-ttu-id="303e4-126">Копировать видимую часть диаграммы в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="303e4-126">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="303e4-127">**Копировать весь граф**</span><span class="sxs-lookup"><span data-stu-id="303e4-127">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="303e4-128">Копировать всю диаграмму в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="303e4-128">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="303e4-129">**Ссылки**</span><span class="sxs-lookup"><span data-stu-id="303e4-129">**Links**</span></span>  
 <span data-ttu-id="303e4-130">Укажите количество связей (ребер) и узлов, отображаемых средством просмотра, перемещая ползунок справа от атрибутов.</span><span class="sxs-lookup"><span data-stu-id="303e4-130">Adjust how many links (edges) and nodes the viewer shows by adjusting the slider to the right of the attributes.</span></span> <span data-ttu-id="303e4-131">При перемещении ползунка вниз значение порога увеличивается, поэтому отображаются только наиболее интенсивные из них.</span><span class="sxs-lookup"><span data-stu-id="303e4-131">Dragging the slider bar down increases the threshold value, so that only the strongest links are shown.</span></span> <span data-ttu-id="303e4-132">Для каждого типа моделей для представления связей в диаграмме используются слегка различные значения.</span><span class="sxs-lookup"><span data-stu-id="303e4-132">For each model type, a slightly different value is used to represent the links in the graph:</span></span>  
  
-   <span data-ttu-id="303e4-133">В модели **дерево принятия решений** ребра представляют прогнозируемую интенсивность соединения, определяемую частично коэффициентом разбиения.</span><span class="sxs-lookup"><span data-stu-id="303e4-133">In a **decision tree** model, the edges represent the predictive strength of the connection, determined partly by the split score.</span></span>  
  
-   <span data-ttu-id="303e4-134">В модели **упрощенного алгоритма Байеса** связи между двумя узлами могут идти в любом направлении, то есть узел А может предсказать узел Б, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="303e4-134">In a **Naïve Bayes** model, the links between two nodes can go either way: that is, node A can predict the node B, and vice versa.</span></span> <span data-ttu-id="303e4-135">Оценка, связанная с ребром, представляет прогностическую интенсивность соединения.</span><span class="sxs-lookup"><span data-stu-id="303e4-135">The score associated with the edge represents the predictive strength of the connection.</span></span>  
  
-   <span data-ttu-id="303e4-136">В **модели взаимосвязей**ребра между узлами представляют оценку важности правила, соединяющего два набора элементов.</span><span class="sxs-lookup"><span data-stu-id="303e4-136">In an **association model**, the edges between nodes represent the importance score of the rule that connects two itemsets.</span></span>  
  
 <span data-ttu-id="303e4-137">Общее правило для моделей всех типов: чем интенсивнее связь, тем сильнее прогнозируемые взаимоотношения между двумя атрибутами.</span><span class="sxs-lookup"><span data-stu-id="303e4-137">A general rule for all model types is that the stronger the link, the stronger the predictive relationship between the two attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303e4-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="303e4-138">See Also</span></span>  
 <span data-ttu-id="303e4-139">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="303e4-139">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="303e4-140">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="303e4-140">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="303e4-141">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="303e4-141">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
