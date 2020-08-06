---
title: Вкладка «Сравнение атрибутов» (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.discrimination.f1
ms.assetid: 68323f23-121e-44fc-be85-6f9915d6d3c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: a8b0d4bc99b1c8f1c5de0269312f02eeb09df022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656885"
---
# <a name="attribute-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="d30a8-102">Вкладка «Сравнение атрибутов» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d30a8-102">Attribute Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="d30a8-103">Используйте вкладку **Сравнение атрибутов** , чтобы сравнить состояние входных атрибутов и выяснить, как они связаны с атрибутом результата.</span><span class="sxs-lookup"><span data-stu-id="d30a8-103">Use the **Attribute Discrimination** tab to compare the states of the input attributes and see how they are related to the outcome attribute.</span></span> <span data-ttu-id="d30a8-104">Значения атрибутов, имеющих наибольшее влияние на разницу между состояниями двух выбранных прогнозируемых атрибутов, перечисляются в начале списка.</span><span class="sxs-lookup"><span data-stu-id="d30a8-104">The attribute values that make the most difference between the two selected predictable attribute states are listed first.</span></span>  
  
 <span data-ttu-id="d30a8-105">**Дополнительные сведения:** [Упрощенный алгоритм Байеса (Майкрософт)](data-mining/microsoft-naive-bayes-algorithm.md), [Просмотр модели с помощью средства просмотра упрощенного алгоритма Байеса (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="d30a8-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="d30a8-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="d30a8-106">Options</span></span>  
 <span data-ttu-id="d30a8-107">**Обновить содержимое средства просмотра**</span><span class="sxs-lookup"><span data-stu-id="d30a8-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="d30a8-108">Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="d30a8-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="d30a8-109">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="d30a8-109">**Mining Model**</span></span>  
 <span data-ttu-id="d30a8-110">Выберите модель интеллектуального анализа данных из числа содержащихся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="d30a8-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="d30a8-111">Модель интеллектуального анализа данных автоматически открывается в соответствующем пользовательском средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="d30a8-111">The mining model automatically opens in the correct custom viewer.</span></span>  
  
 <span data-ttu-id="d30a8-112">**Зритель**</span><span class="sxs-lookup"><span data-stu-id="d30a8-112">**Viewer**</span></span>  
 <span data-ttu-id="d30a8-113">Выберите средство просмотра для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="d30a8-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="d30a8-114">Для каждой модели можно выбрать пользовательское средство просмотра или средство просмотра содержимого интеллектуального анализа данных [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d30a8-114">For each model, you can choose either the custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="d30a8-115">Также можно использовать подключаемые модули просмотра, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="d30a8-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="d30a8-116">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="d30a8-116">**Attribute**</span></span>  
 <span data-ttu-id="d30a8-117">Выберите прогнозируемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="d30a8-117">Choose a predictable attribute.</span></span>  
  
 <span data-ttu-id="d30a8-118">**Значение 1**</span><span class="sxs-lookup"><span data-stu-id="d30a8-118">**Value 1**</span></span>  
 <span data-ttu-id="d30a8-119">Выберите состояние прогнозируемого атрибута для сравнения с состоянием, содержащимся в **Значении 2**.</span><span class="sxs-lookup"><span data-stu-id="d30a8-119">Choose a state of the predictable attribute to compare to the state that is contained in **Value 2**.</span></span>  
  
 <span data-ttu-id="d30a8-120">**Значение 2**</span><span class="sxs-lookup"><span data-stu-id="d30a8-120">**Value 2**</span></span>  
 <span data-ttu-id="d30a8-121">Выберите состояние прогнозируемого атрибута для сравнения с состоянием, содержащимся в **Значении 1**.</span><span class="sxs-lookup"><span data-stu-id="d30a8-121">Select a state of the predictable attribute to compare to the state that is contained in **Value 1**.</span></span> <span data-ttu-id="d30a8-122">Можно также выбрать **все другие состояния** , чтобы сравнить значение в **значении 1** с его дополнением, то есть все остальные значения, кроме значения 1.</span><span class="sxs-lookup"><span data-stu-id="d30a8-122">You can also select **All Other States** to compare the value in **Value 1** with its complement-that is, all other values except Value 1.</span></span>  
  
 <span data-ttu-id="d30a8-123">**Оценки сравнения для \<Value 1> и\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="d30a8-123">**Discrimination scores for \<Value 1> and \<Value 2>**</span></span>  
 <span data-ttu-id="d30a8-124">Диаграмма содержит следующие столбцы, описывающие связь целевого атрибута с определенными состояниями входного атрибута.</span><span class="sxs-lookup"><span data-stu-id="d30a8-124">The graph contains the following columns, which describe how the target attribute is related to specific states of the input attribute.</span></span>  
  
|<span data-ttu-id="d30a8-125">Значение</span><span class="sxs-lookup"><span data-stu-id="d30a8-125">Value</span></span>|<span data-ttu-id="d30a8-126">Описание</span><span class="sxs-lookup"><span data-stu-id="d30a8-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d30a8-127">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="d30a8-127">**Attributes**</span></span>|<span data-ttu-id="d30a8-128">Входной атрибут в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="d30a8-128">An input attribute in the mining model.</span></span>|  
|<span data-ttu-id="d30a8-129">**Значения**</span><span class="sxs-lookup"><span data-stu-id="d30a8-129">**Values**</span></span>|<span data-ttu-id="d30a8-130">Состояние атрибута, содержащегося в списке **Атрибуты**.</span><span class="sxs-lookup"><span data-stu-id="d30a8-130">A state of the attribute that is listed in **Attributes**.</span></span>|  
|<span data-ttu-id="d30a8-131">**Подходит\<Value 1>**</span><span class="sxs-lookup"><span data-stu-id="d30a8-131">**Favors \<Value 1>**</span></span>|<span data-ttu-id="d30a8-132">Полоса указывает, подходят ли текущий атрибут и значение к целевому результату, выбранному в поле **Значение 1**.</span><span class="sxs-lookup"><span data-stu-id="d30a8-132">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 1**.</span></span>|  
|<span data-ttu-id="d30a8-133">**Подходит\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="d30a8-133">**Favors \<Value 2>**</span></span>|<span data-ttu-id="d30a8-134">Полоса указывает, подходят ли текущий атрибут и значение к целевому результату, выбранному в поле **Значение 2**.</span><span class="sxs-lookup"><span data-stu-id="d30a8-134">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d30a8-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="d30a8-135">See Also</span></span>  
 <span data-ttu-id="d30a8-136">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d30a8-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="d30a8-137">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="d30a8-137">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="d30a8-138">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="d30a8-138">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
