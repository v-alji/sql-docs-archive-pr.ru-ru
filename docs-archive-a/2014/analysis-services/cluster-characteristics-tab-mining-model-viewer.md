---
title: Вкладка "характеристики кластера" (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.characteristics.f1
ms.assetid: 8e33ed1d-1ce4-405d-895b-7e995b2c910d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 959d94767b6cb27d9ebb6e06c592034fca20ac89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656779"
---
# <a name="cluster-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="73f6e-102">Вкладка «Характеристики кластеров» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="73f6e-102">Cluster Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="73f6e-103">На вкладке **Характеристики кластера** можно рассмотреть характеристики кластера в модели кластеризации или набор всех вариантов в модели.</span><span class="sxs-lookup"><span data-stu-id="73f6e-103">The **Cluster Characteristics** tab lets you explore the characteristics of a cluster in a clustering model, or the set of all cases in the model.</span></span> <span data-ttu-id="73f6e-104">На диаграмме показана важность каждой пары «атрибут-значение» как характеристики, определяющей кластер, в сравнении с другими кластерами.</span><span class="sxs-lookup"><span data-stu-id="73f6e-104">The graph shows the importance of each attribute-value pair as a characteristic that defines the cluster, in comparison with other clusters.</span></span>  
  
 <span data-ttu-id="73f6e-105">**Дополнительные сведения:** [Алгоритм кластеризации (Майкрософт)](data-mining/microsoft-clustering-algorithm.md), [Просмотр модели с помощью средства просмотра кластеров (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="73f6e-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="73f6e-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="73f6e-106">Options</span></span>  
 <span data-ttu-id="73f6e-107">**Обновить содержимое средства просмотра**</span><span class="sxs-lookup"><span data-stu-id="73f6e-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="73f6e-108">Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="73f6e-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="73f6e-109">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="73f6e-109">**Mining Model**</span></span>  
 <span data-ttu-id="73f6e-110">Выберите модель интеллектуального анализа данных из числа содержащихся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="73f6e-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="73f6e-111">Модель интеллектуального анализа данных откроется в пользовательском средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="73f6e-111">The mining model will open in the custom viewer.</span></span>  
  
 <span data-ttu-id="73f6e-112">**Зритель**</span><span class="sxs-lookup"><span data-stu-id="73f6e-112">**Viewer**</span></span>  
 <span data-ttu-id="73f6e-113">Выберите средство просмотра для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="73f6e-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="73f6e-114">Для этого типа модели можно использовать сопоставленное с ним пользовательское средство просмотра или средство просмотра содержимого интеллектуального анализа данных [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73f6e-114">You can use the custom viewer associated with this model type, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="73f6e-115">Также можно использовать любые подключаемые модули просмотра, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="73f6e-115">You can also use any plug-in viewers that are available.</span></span>  
  
 <span data-ttu-id="73f6e-116">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="73f6e-116">**Cluster**</span></span>  
 <span data-ttu-id="73f6e-117">Выберите кластер для просмотра или **Заполнение (все)**, чтобы увидеть распределение атрибутов для всей модели.</span><span class="sxs-lookup"><span data-stu-id="73f6e-117">Choose the cluster you want to view, or choose **Population (All)** to see the distribution of attributes for the model as a whole.</span></span>  
  
 <span data-ttu-id="73f6e-118">**Характеристики\<cluster>**</span><span class="sxs-lookup"><span data-stu-id="73f6e-118">**Characteristics for \<cluster>**</span></span>  
 <span data-ttu-id="73f6e-119">Диаграмма содержит следующие столбцы, описывающие характеристики выбранного кластера.</span><span class="sxs-lookup"><span data-stu-id="73f6e-119">The graph contains the following columns, which describe the characteristics of the selected cluster.</span></span>  
  
|<span data-ttu-id="73f6e-120">Значение</span><span class="sxs-lookup"><span data-stu-id="73f6e-120">Value</span></span>|<span data-ttu-id="73f6e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="73f6e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73f6e-122">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="73f6e-122">**Variable**</span></span>|<span data-ttu-id="73f6e-123">Список атрибутов из модели интеллектуального анализа данных, которые находятся в выбранном кластере.</span><span class="sxs-lookup"><span data-stu-id="73f6e-123">Lists the attributes from the mining model that are found in the selected cluster.</span></span>|  
|<span data-ttu-id="73f6e-124">**Значения**</span><span class="sxs-lookup"><span data-stu-id="73f6e-124">**Values**</span></span>|<span data-ttu-id="73f6e-125">Перечисляет значения текущих атрибутов, которые находятся в текущем выбранном кластере.</span><span class="sxs-lookup"><span data-stu-id="73f6e-125">Lists the values of the current attributes that are found in the currently selected cluster.</span></span>|  
|<span data-ttu-id="73f6e-126">**Вероятность**</span><span class="sxs-lookup"><span data-stu-id="73f6e-126">**Probability**</span></span>|<span data-ttu-id="73f6e-127">Полоса показывает важность пары «атрибут-значение» как отличительной характеристики этого кластера.</span><span class="sxs-lookup"><span data-stu-id="73f6e-127">The bar indicates the strength of the attribute-value pair as a distinguishing feature of this cluster.</span></span> <span data-ttu-id="73f6e-128">Наведя курсор мыши на полосу, можно увидеть значение вероятности в процентах.</span><span class="sxs-lookup"><span data-stu-id="73f6e-128">If you hover the mouse over the bar, you can see the probability value, represented as a percentage.</span></span> <span data-ttu-id="73f6e-129">При данном сочетании атрибута и значения в любом конкретном варианте эта величина указывает вероятность, что данный вариант принадлежит кластеру.</span><span class="sxs-lookup"><span data-stu-id="73f6e-129">What this indicates is, given this attribute and value combination in any particular case, what is the probability that the case would belong in this cluster.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73f6e-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="73f6e-130">See Also</span></span>  
 <span data-ttu-id="73f6e-131">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="73f6e-131">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="73f6e-132">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="73f6e-132">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="73f6e-133">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="73f6e-133">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
