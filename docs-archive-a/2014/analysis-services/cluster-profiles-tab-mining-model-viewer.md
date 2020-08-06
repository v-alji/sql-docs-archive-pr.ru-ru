---
title: Вкладка "Профили кластера" (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.profiles.f1
ms.assetid: 1ebafa1f-74e9-4c05-b278-a690fa8543bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7ec1ce5b5204ae81a9313ca7b7e5df58c98c5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657399"
---
# <a name="cluster-profiles-tab-mining-model-viewer"></a><span data-ttu-id="b7bb0-102">Вкладка «Профили кластеров» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="b7bb0-102">Cluster Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="b7bb0-103">Вкладка **Профили кластеров** используется для общего представления кластеров, обнаруженных алгоритмом в модели кластеризации.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-103">Use the **Cluster Profiles** tab for an overall view of the clusters that the algorithm discovered within a clustering model.</span></span> <span data-ttu-id="b7bb0-104">Эта вкладка выводит каждый атрибут и распределение этого атрибута в каждом кластере.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-104">The tab displays each attribute, together with the distribution of the attribute in each cluster.</span></span>  
  
 <span data-ttu-id="b7bb0-105">**Дополнительные сведения:** [Алгоритм кластеризации (Майкрософт)](data-mining/microsoft-clustering-algorithm.md), [Просмотр модели с помощью средства просмотра кластеров (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="b7bb0-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="b7bb0-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="b7bb0-106">Options</span></span>  
 <span data-ttu-id="b7bb0-107">**Обновить содержимое средства просмотра**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="b7bb0-108">Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="b7bb0-109">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-109">**Mining Model**</span></span>  
 <span data-ttu-id="b7bb0-110">Выберите модель интеллектуального анализа данных из числа содержащихся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="b7bb0-111">Модель интеллектуального анализа данных открывается в связанном средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="b7bb0-112">**Зритель**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-112">**Viewer**</span></span>  
 <span data-ttu-id="b7bb0-113">Выберите средство просмотра, используемое для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="b7bb0-114">Можно применить пользовательское средство просмотра, предоставленное для этой модели интеллектуального анализа данных, или средство просмотра содержимого интеллектуального анализа данных [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7bb0-114">You can use the custom viewer for the mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="b7bb0-115">Также можно использовать подключаемые модули просмотра, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="b7bb0-116">**Показать условные обозначения**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-116">**Show Legend**</span></span>  
 <span data-ttu-id="b7bb0-117">Выберите данный параметр, чтобы показать ключ, отображающий сопоставление цветов в средстве просмотра со значениями в столбце **Состояния** .</span><span class="sxs-lookup"><span data-stu-id="b7bb0-117">Select this option to display a key that shows the mapping of colors in the viewer to values in the **States** column.</span></span>  
  
 <span data-ttu-id="b7bb0-118">**Столбцы гистограммы**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-118">**Histogram Bars**</span></span>  
 <span data-ttu-id="b7bb0-119">Измените это значение, чтобы назначить количество состояний, включенных в каждую гистограмму.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-119">Change this value to control how many states are included in each histogram.</span></span> <span data-ttu-id="b7bb0-120">Если доступно больше состояний, чем выбрано для отображения, состояния с наибольшей вероятностью отображаются в гистограмме, а оставшиеся состояния группируются в разделе **Другие**.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-120">If there are more states than you choose to display, the states with the highest probability are shown in the histogram, and the remaining states are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="b7bb0-121">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-121">**Attributes**</span></span>  
 <span data-ttu-id="b7bb0-122">Перечисляет столбцы, содержащиеся в модели кластеризации.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-122">Lists the columns that are in the clustering model.</span></span> <span data-ttu-id="b7bb0-123">Гистограммы для каждого атрибута показывают, как атрибут распределен по кластерам, идентифицированным алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-123">The histograms for each attribute show how the attribute is distributed among the clusters identified by the algorithm.</span></span>  
  
 <span data-ttu-id="b7bb0-124">**Состояния**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-124">**States**</span></span>  
 <span data-ttu-id="b7bb0-125">Предоставляет ключ, указывающий, какой цвет представляет каждое состояние в соответствующей строке кластеров, или ползунок с ромбом, указывающий распределение непрерывных числовых значений.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-125">Provides a key that either denotes what color represents each state in the corresponding row of clusters, or a slider with diamond that indicates the distribution of continuous numeric values.</span></span> <span data-ttu-id="b7bb0-126">Можно показать или скрыть этот столбец с помощью флажка **Показать условные обозначения** .</span><span class="sxs-lookup"><span data-stu-id="b7bb0-126">You can show or hide this column by using the **Show Legend** check box.</span></span>  
  
 <span data-ttu-id="b7bb0-127">**Профили кластеров**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-127">**Cluster Profiles**</span></span>  
 <span data-ttu-id="b7bb0-128">В этом разделе содержится столбец для каждого кластера модели.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-128">This section contains a column for each cluster in the model.</span></span> <span data-ttu-id="b7bb0-129">Для каждого атрибута гистограмма показывает распределение значений в атрибуте только для этого кластера.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-129">For each attribute, the histogram shows the distribution of the values in the attribute for just that cluster.</span></span> <span data-ttu-id="b7bb0-130">В диаграмме также есть столбец **Заполнение**, в котором также используются гистограммы, отображающие распределение значений для каждого атрибута, но для всех вариантов в модели.</span><span class="sxs-lookup"><span data-stu-id="b7bb0-130">The chart also has a column for **Population**, which also uses histograms to display the distribution of values for each attribute, but for all cases in the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bb0-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7bb0-131">See Also</span></span>  
 <span data-ttu-id="b7bb0-132">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b7bb0-132">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="b7bb0-133">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b7bb0-133">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="b7bb0-134">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="b7bb0-134">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
