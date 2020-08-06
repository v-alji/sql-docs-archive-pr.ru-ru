---
title: Вкладка "наборы элементов" (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.itemsets.f1
ms.assetid: 95b2b805-b142-4064-9c80-4b1b3fe2fe63
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b99b62b01b196fd62e1ef264e530487018f6a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656673"
---
# <a name="itemsets-tab-mining-model-viewer"></a><span data-ttu-id="beedf-102">Вкладка «Наборы элементов» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="beedf-102">Itemsets Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="beedf-103">Можно использовать панель **Наборы элементов** для просмотра часто используемых наборов элементов, которые содержит модель интеллектуального анализа правил взаимосвязи.</span><span class="sxs-lookup"><span data-stu-id="beedf-103">You can use the **Itemsets** pane to view the frequent itemsets that an association rules mining model contains.</span></span> <span data-ttu-id="beedf-104">Модель взаимосвязей может содержать много наборов элементов, поэтому в средстве просмотра предоставляются функции управления, упрощающие фильтрацию наборов элементов, отображаемых в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="beedf-104">Because an association model can contain many itemsets, controls are provided in the viewer to help you filter the itemsets that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="beedf-105">**Дополнительные сведения:** [Алгоритм взаимосвязей (Майкрософт)](data-mining/microsoft-association-algorithm.md), [Просмотр модели с помощью средства просмотра правил взаимосвязи (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="beedf-105">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="beedf-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="beedf-106">Options</span></span>  
 <span data-ttu-id="beedf-107">**Обновить содержимое средства просмотра**</span><span class="sxs-lookup"><span data-stu-id="beedf-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="beedf-108">Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="beedf-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="beedf-109">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="beedf-109">**Mining Model**</span></span>  
 <span data-ttu-id="beedf-110">Выберите для просмотра модель интеллектуального анализа данных, содержащуюся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="beedf-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="beedf-111">Модель интеллектуального анализа данных открывается в связанном средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="beedf-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="beedf-112">**Зритель**</span><span class="sxs-lookup"><span data-stu-id="beedf-112">**Viewer**</span></span>  
 <span data-ttu-id="beedf-113">Выберите средство просмотра, используемое для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="beedf-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="beedf-114">Для моделей взаимосвязей можно использовать пользовательское средство просмотра или средство просмотра деревьев содержимого общего вида [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="beedf-114">You can use either the custom viewer for association models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="beedf-115">Также можно использовать подключаемые модули просмотра, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="beedf-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="beedf-116">**Минимальная поддержка**</span><span class="sxs-lookup"><span data-stu-id="beedf-116">**Minimum support**</span></span>  
 <span data-ttu-id="beedf-117">Измените это значение, чтобы задать минимальную поддержку, которую должен содержать набор элементов, чтобы появиться в браузере.</span><span class="sxs-lookup"><span data-stu-id="beedf-117">Change this value to set the minimum support that an itemset must contain to appear in the viewer.</span></span> <span data-ttu-id="beedf-118">Значение по умолчанию, отображаемое при первом открытии модели, вычисляется моделью, но его можно изменить, чтобы показать больше или меньше наборов элементов.</span><span class="sxs-lookup"><span data-stu-id="beedf-118">The default value that is displayed when you first open the model is calculated by the model, but you can change it to see more or fewer itemsets.</span></span>  
  
 <span data-ttu-id="beedf-119">**Минимальный размер набора элементов**</span><span class="sxs-lookup"><span data-stu-id="beedf-119">**Minimum itemset size**</span></span>  
 <span data-ttu-id="beedf-120">Измените это значение, чтобы задать минимальное количество элементов, которое должен содержать набор элементов, прежде чем он может быть показан в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="beedf-120">Change this value to set the minimum number of items that must be included in an itemset before the itemset can be displayed in the viewer.</span></span>  
  
 <span data-ttu-id="beedf-121">**Фильтрация набора элементов**</span><span class="sxs-lookup"><span data-stu-id="beedf-121">**Filter Itemset**</span></span>  
 <span data-ttu-id="beedf-122">Введите строковое значение для фильтрации количества наборов элементов, отображаемых в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="beedf-122">Type a string value to filter the number of itemsets that appear in the viewer.</span></span>  
  
 <span data-ttu-id="beedf-123">Можно также ввести регулярные выражения .NET как критерии фильтра.</span><span class="sxs-lookup"><span data-stu-id="beedf-123">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="beedf-124">Например, следующее выражение возвращает все наборы элементов, содержащие «Road Bottle Cage»:</span><span class="sxs-lookup"><span data-stu-id="beedf-124">For example, the following expression returns all itemsets that contain 'Road Bottle Cage':</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*`  
  
 <span data-ttu-id="beedf-125">Обратите внимание, что, возможно, потребуется обновить представление, чтобы увидеть применяемые критерии фильтра.</span><span class="sxs-lookup"><span data-stu-id="beedf-125">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="beedf-126">Чтобы обновить список, можно включать и отключать параметр **Показывать длинное имя** .</span><span class="sxs-lookup"><span data-stu-id="beedf-126">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="beedf-127">По умолчанию критерии фильтра применяются к полному имени сочетания «атрибут-значение», поэтому при просмотре только имени атрибута не всегда ясно, что критерии фильтра применены верно.</span><span class="sxs-lookup"><span data-stu-id="beedf-127">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="beedf-128">Используйте раскрывающийся список **Отображать** , чтобы выбрать пункт **Отобразить имя и значение атрибута**и проверить правильность фильтрации списка наборов элементов.</span><span class="sxs-lookup"><span data-stu-id="beedf-128">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="beedf-129">**Показать**</span><span class="sxs-lookup"><span data-stu-id="beedf-129">**Show**</span></span>  
 <span data-ttu-id="beedf-130">Настройте способ отображения набора элементов в браузере.</span><span class="sxs-lookup"><span data-stu-id="beedf-130">Adjust how the itemset is displayed in the viewer.</span></span> <span data-ttu-id="beedf-131">Можно выбрать один из трех параметров:</span><span class="sxs-lookup"><span data-stu-id="beedf-131">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="beedf-132">Отобразить имя и значение атрибута</span><span class="sxs-lookup"><span data-stu-id="beedf-132">Show attribute name and value</span></span>  
  
-   <span data-ttu-id="beedf-133">Отобразить только значение атрибута</span><span class="sxs-lookup"><span data-stu-id="beedf-133">Show attribute value only</span></span>  
  
-   <span data-ttu-id="beedf-134">Отобразить только имя атрибута</span><span class="sxs-lookup"><span data-stu-id="beedf-134">Show attribute name only</span></span>  
  
 <span data-ttu-id="beedf-135">Обратите внимание, что этот параметр не требует модели; он только фильтрует отображаемые атрибуты или значения.</span><span class="sxs-lookup"><span data-stu-id="beedf-135">Note that this option does not requery the model; it only filters the attributes or values that are displayed.</span></span>  
  
 <span data-ttu-id="beedf-136">**Показывать длинное имя**</span><span class="sxs-lookup"><span data-stu-id="beedf-136">**Show long name**</span></span>  
 <span data-ttu-id="beedf-137">Выберите этот режим, чтобы показать полное имя набора элементов, как оно отображается в содержимом модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="beedf-137">Select this option to display the full name of the itemset as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="beedf-138">**Максимальное число строк**</span><span class="sxs-lookup"><span data-stu-id="beedf-138">**Maximum rows**</span></span>  
 <span data-ttu-id="beedf-139">Ограничить количество наборов элементов, отображающихся в браузере.</span><span class="sxs-lookup"><span data-stu-id="beedf-139">Limit the number of itemsets that are displayed in the viewer.</span></span> <span data-ttu-id="beedf-140">По умолчанию наборы элементов упорядочиваются по несущему множеству в нисходящем порядке, поэтому уменьшение этого значения ограничивает список самыми часто встречающимися наборами элементов.</span><span class="sxs-lookup"><span data-stu-id="beedf-140">By default, itemsets are ordered by support in descending order, so lowering this value restricts the list to the most common itemsets.</span></span>  
  
 <span data-ttu-id="beedf-141">**Поддержка**</span><span class="sxs-lookup"><span data-stu-id="beedf-141">**Support**</span></span>  
 <span data-ttu-id="beedf-142">Показывает несущее множество для каждого набора элементов.</span><span class="sxs-lookup"><span data-stu-id="beedf-142">Displays the support for each itemset.</span></span>  
  
 <span data-ttu-id="beedf-143">**Размер**</span><span class="sxs-lookup"><span data-stu-id="beedf-143">**Size**</span></span>  
 <span data-ttu-id="beedf-144">Показывает количество элементов в каждом наборе элементов.</span><span class="sxs-lookup"><span data-stu-id="beedf-144">Displays the number of items that exist in each itemset.</span></span>  
  
 <span data-ttu-id="beedf-145">**Набор элементов**</span><span class="sxs-lookup"><span data-stu-id="beedf-145">**Itemset**</span></span>  
 <span data-ttu-id="beedf-146">Показывает описание каждого набора элементов.</span><span class="sxs-lookup"><span data-stu-id="beedf-146">Displays the description of each itemset.</span></span> <span data-ttu-id="beedf-147">По умолчанию наборы элементов представлены как разделенный запятыми список атрибутов и их значений.</span><span class="sxs-lookup"><span data-stu-id="beedf-147">By default, itemsets are presented as a comma-delimited list of attributes and their values.</span></span> <span data-ttu-id="beedf-148">Вы можете изменить способ их отображения с помощью параметра **Показать** .</span><span class="sxs-lookup"><span data-stu-id="beedf-148">You can change the way they are displayed by using the **Show** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beedf-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="beedf-149">See Also</span></span>  
 <span data-ttu-id="beedf-150">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="beedf-150">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="beedf-151">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="beedf-151">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="beedf-152">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="beedf-152">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
