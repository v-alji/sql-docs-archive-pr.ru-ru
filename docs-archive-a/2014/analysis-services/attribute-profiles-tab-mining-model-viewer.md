---
title: Вкладка «Профили атрибутов» (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.profiles.f1
ms.assetid: 17c7e7ae-273c-4a6b-9a35-e8b9b8e65999
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61c81b95f030bf1a69aed165bd64e58ff9af8339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656880"
---
# <a name="attribute-profiles-tab-mining-model-viewer"></a><span data-ttu-id="25a4e-102">Вкладка «Профили атрибутов» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="25a4e-102">Attribute Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="25a4e-103">Вкладка **Профили атрибутов** показывает, как распределение входных значений в состоянии модели упрощенного алгоритма Байеса влияет на каждое состояние атрибута результата.</span><span class="sxs-lookup"><span data-stu-id="25a4e-103">Use the **Attribute Profiles** tab to see how the distribution of input values in a Naive Bayes model state contribute to each state of the outcome attribute.</span></span> <span data-ttu-id="25a4e-104">Распределение значений показано в виде цветной гистограммы, все распределения представлены в табличном формате, чтобы упростить сравнение значений.</span><span class="sxs-lookup"><span data-stu-id="25a4e-104">The distribution of values is shown as a colored histogram, all distributions presented in a tabular format, to make it easier to compare values.</span></span>  
  
 <span data-ttu-id="25a4e-105">**Дополнительные сведения:** [Упрощенный алгоритм Байеса (Майкрософт)](data-mining/microsoft-naive-bayes-algorithm.md), [Просмотр модели с помощью средства просмотра упрощенного алгоритма Байеса (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="25a4e-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="25a4e-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="25a4e-106">Options</span></span>  
 <span data-ttu-id="25a4e-107">**Обновить содержимое средства просмотра**</span><span class="sxs-lookup"><span data-stu-id="25a4e-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="25a4e-108">Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="25a4e-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="25a4e-109">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="25a4e-109">**Mining Model**</span></span>  
 <span data-ttu-id="25a4e-110">Выбрать модель интеллектуального анализа данных для просмотра из числа содержащихся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="25a4e-110">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="25a4e-111">Модель интеллектуального анализа данных открывается в связанном средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="25a4e-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="25a4e-112">**Зритель**</span><span class="sxs-lookup"><span data-stu-id="25a4e-112">**Viewer**</span></span>  
 <span data-ttu-id="25a4e-113">Выберите средство просмотра для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="25a4e-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="25a4e-114">Можно выбрать пользовательское средство просмотра, предоставленное для каждой модели интеллектуального анализа данных, или средство просмотра содержимого интеллектуального анализа данных [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25a4e-114">You can choose the custom viewer provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="25a4e-115">Также можно использовать подключаемые модули просмотра, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="25a4e-115">You can also use plug-in viewers if they are available.</span></span>  
  
 <span data-ttu-id="25a4e-116">**Показать условные обозначения**</span><span class="sxs-lookup"><span data-stu-id="25a4e-116">**Show Legend**</span></span>  
 <span data-ttu-id="25a4e-117">Выберите данный параметр, чтобы показать ключ, сопоставляющий каждое значение в поле **Состояния** с одним из цветов, используемых в диаграмме распределения.</span><span class="sxs-lookup"><span data-stu-id="25a4e-117">Select this option to display a key that matches each value in **States** to one of the colors used in the distribution chart.</span></span>  
  
 <span data-ttu-id="25a4e-118">**Столбцы гистограммы**</span><span class="sxs-lookup"><span data-stu-id="25a4e-118">**Histogram bars**</span></span>  
 <span data-ttu-id="25a4e-119">Выберите число столбцов, которые необходимо включить в гистограмму.</span><span class="sxs-lookup"><span data-stu-id="25a4e-119">Select how many bars to include in the histogram.</span></span> <span data-ttu-id="25a4e-120">Если доступно больше столбцов, чем выбрано для отображения, наиболее важные столбцы остаются, а оставшиеся группируются в раздел **Другие**.</span><span class="sxs-lookup"><span data-stu-id="25a4e-120">If more bars exist than you choose to display, the bars of highest importance are retained, and the remaining bars are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="25a4e-121">**Прогнозируемый**</span><span class="sxs-lookup"><span data-stu-id="25a4e-121">**Predictable**</span></span>  
 <span data-ttu-id="25a4e-122">Выберите прогнозируемый столбец для модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="25a4e-122">Select a predictable column from the mining model.</span></span>  
  
 <span data-ttu-id="25a4e-123">**Профили атрибутов**</span><span class="sxs-lookup"><span data-stu-id="25a4e-123">**Attribute Profiles**</span></span>  
 <span data-ttu-id="25a4e-124">Таблица содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="25a4e-124">The table contains the following columns:</span></span>  
  
|<span data-ttu-id="25a4e-125">Значение</span><span class="sxs-lookup"><span data-stu-id="25a4e-125">Value</span></span>|<span data-ttu-id="25a4e-126">Описание</span><span class="sxs-lookup"><span data-stu-id="25a4e-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="25a4e-127">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="25a4e-127">**Attributes**</span></span>|<span data-ttu-id="25a4e-128">Список столбцов, содержащихся в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="25a4e-128">Lists the mining model columns contained within the mining model.</span></span>|  
|<span data-ttu-id="25a4e-129">**Состояния**</span><span class="sxs-lookup"><span data-stu-id="25a4e-129">**States**</span></span>|<span data-ttu-id="25a4e-130">Необязательный столбец, описывающий, какое состояние представляет цвет в соответствующей строке атрибутов.</span><span class="sxs-lookup"><span data-stu-id="25a4e-130">An optional column that describes what state the color in the corresponding row of attributes represents.</span></span> <span data-ttu-id="25a4e-131">Добавьте или удалите с помощью установки или снятия флажка **Показать легенду** .</span><span class="sxs-lookup"><span data-stu-id="25a4e-131">Add or remove by using the **Show Legend** check box.</span></span>|  
|<span data-ttu-id="25a4e-132">**Повтор**</span><span class="sxs-lookup"><span data-stu-id="25a4e-132">**Population**</span></span>|<span data-ttu-id="25a4e-133">Выводит распределение атрибута по всему набору данных.</span><span class="sxs-lookup"><span data-stu-id="25a4e-133">Displays the distribution of the attribute across the whole dataset.</span></span>|  
|<span data-ttu-id="25a4e-134">**Столбец для состояний прогнозируемого атрибута**</span><span class="sxs-lookup"><span data-stu-id="25a4e-134">**Column for states of predictable attribute**</span></span>|<span data-ttu-id="25a4e-135">Выводит столбец для каждого состояния прогнозируемого столбца, где каждая строка соответствует входному атрибуту в модели.</span><span class="sxs-lookup"><span data-stu-id="25a4e-135">Displays a column for each state of the predictable column, with each row corresponding to an input attribute in the model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25a4e-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="25a4e-136">See Also</span></span>  
 <span data-ttu-id="25a4e-137">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="25a4e-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="25a4e-138">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="25a4e-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="25a4e-139">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="25a4e-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
