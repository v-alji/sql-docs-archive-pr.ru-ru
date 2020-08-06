---
title: Вкладка "сравнения кластеров" (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.discrimination.f1
ms.assetid: ae7cfff7-ab1c-4cf5-9a91-97b21d15d85f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 35435736bcdf1b1962de6babace2def953bbfff0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657403"
---
# <a name="cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="102ef-102">Вкладка «Сравнения кластеров» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="102ef-102">Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="102ef-103">Вкладка **Сравнения кластеров** используется для сравнения двух кластеров, существующих в модели кластеризации.</span><span class="sxs-lookup"><span data-stu-id="102ef-103">Use the **Cluster Discrimination** tab to compare two clusters that exist in a clustering model.</span></span> <span data-ttu-id="102ef-104">Вы можете увидеть представление различных сочетаний атрибутов и значений внутри кластеров.</span><span class="sxs-lookup"><span data-stu-id="102ef-104">You can see how different combinations of attributes and values are represented within the clusters.</span></span>  
  
 <span data-ttu-id="102ef-105">**Дополнительные сведения:** [Алгоритм кластеризации (Майкрософт)](data-mining/microsoft-clustering-algorithm.md), [Просмотр модели с помощью средства просмотра кластеров (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="102ef-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="102ef-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="102ef-106">Options</span></span>  
 <span data-ttu-id="102ef-107">**Обновить содержимое средства просмотра**</span><span class="sxs-lookup"><span data-stu-id="102ef-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="102ef-108">Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="102ef-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="102ef-109">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="102ef-109">**Mining Model**</span></span>  
 <span data-ttu-id="102ef-110">Выберите модель интеллектуального анализа данных из числа содержащихся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="102ef-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="102ef-111">Модель интеллектуального анализа данных открывается в связанном средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="102ef-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="102ef-112">**Зритель**</span><span class="sxs-lookup"><span data-stu-id="102ef-112">**Viewer**</span></span>  
 <span data-ttu-id="102ef-113">Выберите средство просмотра для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="102ef-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="102ef-114">Можно применить пользовательское средство просмотра для моделей кластеризации или средство просмотра содержимого интеллектуального анализа данных [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="102ef-114">You can use the custom viewer for clustering models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="102ef-115">Также можно использовать подключаемые модули просмотра, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="102ef-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="102ef-116">**Кластер 1**</span><span class="sxs-lookup"><span data-stu-id="102ef-116">**Cluster 1**</span></span>  
 <span data-ttu-id="102ef-117">Выберите кластер для сравнения с другим кластером.</span><span class="sxs-lookup"><span data-stu-id="102ef-117">Select a cluster, so that you can compare it to another cluster.</span></span>  
  
 <span data-ttu-id="102ef-118">**Кластер 2**</span><span class="sxs-lookup"><span data-stu-id="102ef-118">**Cluster 2**</span></span>  
 <span data-ttu-id="102ef-119">Из списка кластеров в модели интеллектуального анализа данных выберите другой кластер для сравнения с **кластером 1**.</span><span class="sxs-lookup"><span data-stu-id="102ef-119">Select a second cluster from the list of clusters in the mining model, to compare to **Cluster 1**.</span></span> <span data-ttu-id="102ef-120">Можно также сравнить кластер с его дополнением, то есть всеми вариантами в модели, кроме вариантов в выбранном кластере.</span><span class="sxs-lookup"><span data-stu-id="102ef-120">You can also compare a cluster to its complement, meaning all cases in the model except those in the selected cluster.</span></span>  
  
 <span data-ttu-id="102ef-121">**Оценки сравнения для \<cluster 1> и\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="102ef-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="102ef-122">Столбцы в диаграмме предоставляют информацию о способах связи каждой пары «атрибут-значение» с двумя выбранными кластерами.</span><span class="sxs-lookup"><span data-stu-id="102ef-122">The columns in the graph provide information about how each attribute-value pair is related to the two selected clusters.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="102ef-123">**Переменные**</span><span class="sxs-lookup"><span data-stu-id="102ef-123">**Variables**</span></span>|<span data-ttu-id="102ef-124">Атрибут модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="102ef-124">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="102ef-125">**Значения**</span><span class="sxs-lookup"><span data-stu-id="102ef-125">**Values**</span></span>|<span data-ttu-id="102ef-126">Значение атрибута, выбранного в **Переменных**.</span><span class="sxs-lookup"><span data-stu-id="102ef-126">A value of the attribute selected in **Variables**.</span></span>|  
|<span data-ttu-id="102ef-127">**Подходит\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="102ef-127">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="102ef-128">Гистограмма слева показывает вероятность, что выбранная пара "атрибут-значение" типична для кластера, выбранного в поле **Кластер 1**.</span><span class="sxs-lookup"><span data-stu-id="102ef-128">The bar graph on the left represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 1**.</span></span> <span data-ttu-id="102ef-129">Можно остановить курсор мыши над полосой, чтобы увидеть значение в процентах.</span><span class="sxs-lookup"><span data-stu-id="102ef-129">You can pause the mouse over the bar to see the value, represented as a percentage.</span></span> <span data-ttu-id="102ef-130">Обратите внимание, что даже если значение равно нулю, это не значит, что атрибут-значение обязательно отсутствует в кластере.</span><span class="sxs-lookup"><span data-stu-id="102ef-130">Note that even if the value is zero, it doesn't mean the attribute-value is necessarily missing from the cluster, just that the distribution strongly favors one cluster over the other.</span></span>|  
|<span data-ttu-id="102ef-131">**Подходит\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="102ef-131">**Favors \<cluster 2>**</span></span>|<span data-ttu-id="102ef-132">Гистограмма справа показывает вероятность, что выбранная пара "атрибут-значение" типична для кластера, выбранного в поле **Кластер 2**.</span><span class="sxs-lookup"><span data-stu-id="102ef-132">The bar graph on the right represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="102ef-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="102ef-133">See Also</span></span>  
 <span data-ttu-id="102ef-134">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="102ef-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="102ef-135">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="102ef-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="102ef-136">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="102ef-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
