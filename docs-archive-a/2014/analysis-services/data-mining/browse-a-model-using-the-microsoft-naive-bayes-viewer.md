---
title: Просмотр модели с помощью средства просмотра упрощенных алгоритмов Байеса (Майкрософт) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discrimination [Analysis Services]
- naive bayes model [Analysis Services]
- Bayesian classifiers
- mining model content, viewing
- predictive modeling [Analysis Services]
- Naive Bayes Viewer [Analysis Services]
- data mining [Analysis Services], predictive modeling
- Microsoft Naive Bayes Viewer
- histograms [Analysis Services]
- mining models [Analysis Services], predictive modeling
- dependencies [Analysis Services]
ms.assetid: 19743095-63c1-4486-8c1d-2efc143243be
author: minewiskan
ms.author: owend
ms.openlocfilehash: 03469e73d82a389426f91d8757630f50fe78fc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669203"
---
# <a name="browse-a-model-using-the-microsoft-naive-bayes-viewer"></a><span data-ttu-id="0ab64-102">Просмотр модели с помощью средства просмотра упрощенного алгоритма Байеса (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="0ab64-102">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>
  <span data-ttu-id="0ab64-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)]Средство просмотра упрощенного алгоритма Байеса в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] отображает модели интеллектуального анализа данных, построенные с помощью [!INCLUDE[msCoName](../../includes/msconame-md.md)] упрощенного алгоритма Байеса.</span><span class="sxs-lookup"><span data-stu-id="0ab64-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm.</span></span> <span data-ttu-id="0ab64-104">Упрощенный алгоритм Байеса ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) — это алгоритм классификации, хорошо адаптирующийся к задачам прогнозирующего моделирования.</span><span class="sxs-lookup"><span data-stu-id="0ab64-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm is a classification algorithm that is highly adaptable to predictive modeling tasks.</span></span> <span data-ttu-id="0ab64-105">Дополнительные сведения об этом алгоритме см. в разделе [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="0ab64-105">For more information about this algorithm, see [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="0ab64-106">Ввиду того что одной из главных задач упрощенной модели Байеса является предоставление способа быстрого просмотра данных в наборе, средство просмотра упрощенных алгоритмов Байеса ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) содержит несколько методов отображения взаимодействия между прогнозируемыми и входными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="0ab64-106">Because one of the main purposes of a naive Bayes model is to provide a way to quickly explore the data in a dataset, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides several methods for displaying the interaction between predictable attributes and input attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ab64-107">Чтобы просмотреть подробные сведения об использованных в модели уравнениях и обнаруженных закономерностях, используйте средство просмотра деревьев содержимого общего вида ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="0ab64-107">If you want to view detailed information about the equations used in the model and the patterns that were discovered, you can switch to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="0ab64-108">Дополнительные сведения см. в разделах [Просмотр модели в средстве просмотра деревьев содержимого общего вида (Майкрософт)](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) и [Средство просмотра деревьев содержимого общего вида (Майкрософт) (интеллектуальный анализ данных)](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="0ab64-108">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="0ab64-109">Вкладки средства просмотра</span><span class="sxs-lookup"><span data-stu-id="0ab64-109">Viewer Tabs</span></span>  
 <span data-ttu-id="0ab64-110">При просмотре модели интеллектуального анализа данных в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]модель отображается на вкладке **Средство просмотра моделей интеллектуального анализа данных** конструктора интеллектуального анализа данных с использованием соответствующего средства просмотра для данной модели.</span><span class="sxs-lookup"><span data-stu-id="0ab64-110">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="0ab64-111">Средство просмотра упрощенных алгоритмов Байеса ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) содержит следующие вкладки, на которых можно изучить данные:</span><span class="sxs-lookup"><span data-stu-id="0ab64-111">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for exploring data:</span></span>  
  
-   [<span data-ttu-id="0ab64-112">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="0ab64-112">Dependency Network</span></span>](#BKMK_Dependency)  
  
-   [<span data-ttu-id="0ab64-113">Профили атрибутов</span><span class="sxs-lookup"><span data-stu-id="0ab64-113">Attribute Profiles</span></span>](#BKMK_Profiles)  
  
-   [<span data-ttu-id="0ab64-114">Характеристики атрибута</span><span class="sxs-lookup"><span data-stu-id="0ab64-114">Attribute Characteristics</span></span>](#BKMK_Characteristics)  
  
-   [<span data-ttu-id="0ab64-115">Сравнение атрибутов</span><span class="sxs-lookup"><span data-stu-id="0ab64-115">Attribute Discrimination</span></span>](#BKMK_Discrimination)  
  
##  <a name="dependency-network"></a><a name="BKMK_Dependency"></a><span data-ttu-id="0ab64-116">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="0ab64-116">Dependency Network</span></span>  
 <span data-ttu-id="0ab64-117">Вкладка **Сеть зависимостей** отображает зависимости между входными атрибутами и прогнозируемыми атрибутами модели.</span><span class="sxs-lookup"><span data-stu-id="0ab64-117">The **Dependency Network** tab displays the dependencies between the input attributes and the predictable attributes in a model.</span></span> <span data-ttu-id="0ab64-118">Ползунок слева от средства просмотра выступает в качестве фильтра, привязанного к прочности зависимостей.</span><span class="sxs-lookup"><span data-stu-id="0ab64-118">The slider at the left of the viewer acts as a filter that is tied to the strengths of the dependencies.</span></span> <span data-ttu-id="0ab64-119">При движении ползунка вниз отображаются только самые прочные связи.</span><span class="sxs-lookup"><span data-stu-id="0ab64-119">Lowering the slider shows only the strongest links.</span></span>  
  
 <span data-ttu-id="0ab64-120">После выбора узла в средстве просмотра выделяются зависимости, относящиеся к узлу.</span><span class="sxs-lookup"><span data-stu-id="0ab64-120">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="0ab64-121">Например, при выборе прогнозируемого узла в средстве просмотра также выделяется каждый узел, оказывающий содействие в прогнозировании этого узла.</span><span class="sxs-lookup"><span data-stu-id="0ab64-121">For example, if you choose a predictable node, the viewer also highlights each node that helps predict the predictable node.</span></span>  
  
 <span data-ttu-id="0ab64-122">Условные обозначения в нижней части средства просмотра связывают цветовые коды с типом зависимости на графе.</span><span class="sxs-lookup"><span data-stu-id="0ab64-122">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="0ab64-123">Например, при выборе прогнозируемого узла он выделяется бирюзовым цветом, а узлы, которые прогнозируют выбранный узел, — оранжевым цветом.</span><span class="sxs-lookup"><span data-stu-id="0ab64-123">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="0ab64-124">К началу</span><span class="sxs-lookup"><span data-stu-id="0ab64-124">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-profiles"></a><a name="BKMK_Profiles"></a> <span data-ttu-id="0ab64-125">Профили атрибутов</span><span class="sxs-lookup"><span data-stu-id="0ab64-125">Attribute Profiles</span></span>  
 <span data-ttu-id="0ab64-126">Вкладка **Профили атрибутов** отображает гистограммы на сетке.</span><span class="sxs-lookup"><span data-stu-id="0ab64-126">The **Attribute Profiles** tab displays histograms in a grid.</span></span> <span data-ttu-id="0ab64-127">Можно использовать эту сетку для сравнения прогнозируемого атрибута, выбранного в поле **Прогнозируемый** с остальными атрибутами модели.</span><span class="sxs-lookup"><span data-stu-id="0ab64-127">You can use this grid to compare the predictable attribute that you select in the **Predictable** box to all other attributes that are in the model.</span></span> <span data-ttu-id="0ab64-128">Каждый столбец вкладки представляет состояние прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="0ab64-128">Each column in the tab represents a state of the predictable attribute.</span></span> <span data-ttu-id="0ab64-129">Если у него много состояний, можно изменить число состояний, отображаемых на гистограмме, с помощью **Столбцов гистограммы**.</span><span class="sxs-lookup"><span data-stu-id="0ab64-129">If the predictable attribute has many states, you can change the number of states that appear in the histogram by adjusting the **Histogram bars**.</span></span> <span data-ttu-id="0ab64-130">Если указанное число будет меньше полного числа состояний атрибута, то они будут перечислены в порядке вклада в прогноз, а оставшиеся будут собраны в один серый сегмент.</span><span class="sxs-lookup"><span data-stu-id="0ab64-130">If the number you choose is less than the total number of states in the attribute, the states are listed in order of support, with the remaining states collected into a single gray bucket.</span></span>  
  
 <span data-ttu-id="0ab64-131">Чтобы показать условные обозначения интеллектуального анализа данных цветами на гистограмме, установите флажок **Показать обозначения** .</span><span class="sxs-lookup"><span data-stu-id="0ab64-131">To display a Mining Legend that relates the colors of the histogram to the states of an attribute, click the **Show Legend** check box.</span></span> <span data-ttu-id="0ab64-132">Кроме того, в условных обозначениях интеллектуального анализа данных отображается распределение вариантов для каждой выбранной пары «атрибут-значение».</span><span class="sxs-lookup"><span data-stu-id="0ab64-132">The Mining Legend also displays the distribution of cases for each attribute-value pair that you select.</span></span>  
  
 <span data-ttu-id="0ab64-133">Чтобы скопировать содержимое сетки в буфер обмена в виде HTML-таблицы, щелкните правой кнопкой мыши вкладку **Профили атрибутов** и выберите пункт **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="0ab64-133">To copy the contents of the grid to the Clipboard as an HTML table, right-click the **Attribute Profiles** tab and select **Copy**.</span></span>  
  
 [<span data-ttu-id="0ab64-134">К началу</span><span class="sxs-lookup"><span data-stu-id="0ab64-134">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-characteristics"></a><a name="BKMK_Characteristics"></a> <span data-ttu-id="0ab64-135">Характеристики атрибута</span><span class="sxs-lookup"><span data-stu-id="0ab64-135">Attribute Characteristics</span></span>  
 <span data-ttu-id="0ab64-136">Чтобы воспользоваться вкладкой **Характеристики атрибута** , выберите прогнозируемый атрибут из списка **Атрибуты** , а затем состояние выбранного атрибута из списка **Значение** .</span><span class="sxs-lookup"><span data-stu-id="0ab64-136">To use the **Attribute Characteristics** tab, select a predictable attribute from the **Attribute** list and select a state of the selected attribute from the **Value** list.</span></span> <span data-ttu-id="0ab64-137">После задания этих переменных на вкладке **Характеристики атрибута** отобразятся состояния атрибутов, связанные с выбранным вариантом выбранного атрибута.</span><span class="sxs-lookup"><span data-stu-id="0ab64-137">When you set these variables, the **Attribute Characteristics** tab displays the states of the attributes that are associated with the selected case of the selected attribute.</span></span> <span data-ttu-id="0ab64-138">Атрибуты сортируются по важности.</span><span class="sxs-lookup"><span data-stu-id="0ab64-138">The attributes are sorted by importance.</span></span>  
  
 [<span data-ttu-id="0ab64-139">К началу</span><span class="sxs-lookup"><span data-stu-id="0ab64-139">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-discrimination"></a><a name="BKMK_Discrimination"></a> <span data-ttu-id="0ab64-140">Сравнение атрибутов</span><span class="sxs-lookup"><span data-stu-id="0ab64-140">Attribute Discrimination</span></span>  
 <span data-ttu-id="0ab64-141">Чтобы воспользоваться вкладкой **Сравнение атрибутов** , выберите прогнозируемый атрибут и пару его состояний из списков **Атрибут**, **Значение 1**и **Значение 2** .</span><span class="sxs-lookup"><span data-stu-id="0ab64-141">To use the **Attribute Discrimination** tab, select a predictable attribute and two of its states from the **Attribute**, **Value 1**, and **Value 2** lists.</span></span> <span data-ttu-id="0ab64-142">В столбцах сетки на вкладке **Сравнение атрибутов** отобразятся следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="0ab64-142">The grid on the **Attribute Discrimination** tab then displays the following information in columns:</span></span>  
  
 <span data-ttu-id="0ab64-143">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="0ab64-143">**Attribute**</span></span>  
 <span data-ttu-id="0ab64-144">Перечисляет другие атрибуты из набора данных, которые содержат состояние, сильно благоприятствующее одному из состояний прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="0ab64-144">Lists other attributes in the dataset that contain a state that highly favors one state of the predictable attribute.</span></span>  
  
 <span data-ttu-id="0ab64-145">**Значения**</span><span class="sxs-lookup"><span data-stu-id="0ab64-145">**Values**</span></span>  
 <span data-ttu-id="0ab64-146">Показывает значение атрибута в столбце **Атрибут**.</span><span class="sxs-lookup"><span data-stu-id="0ab64-146">Shows the value of the attribute in the **Attribute** column.</span></span>  
  
 <span data-ttu-id="0ab64-147">**Подходит\<value 1>**</span><span class="sxs-lookup"><span data-stu-id="0ab64-147">**Favors \<value 1>**</span></span>  
 <span data-ttu-id="0ab64-148">Выводит цветную полоску, показывающую, насколько значение атрибута соответствует значению прогнозируемого атрибута, показанному в поле **Значение 1**.</span><span class="sxs-lookup"><span data-stu-id="0ab64-148">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 1**.</span></span>  
  
 <span data-ttu-id="0ab64-149">**Подходит\<value 2>**</span><span class="sxs-lookup"><span data-stu-id="0ab64-149">**Favors \<value 2>**</span></span>  
 <span data-ttu-id="0ab64-150">Выводит цветную полоску, показывающую, насколько значение атрибута соответствует значению прогнозируемого атрибута, показанному в поле **Значение 2**.</span><span class="sxs-lookup"><span data-stu-id="0ab64-150">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 2**.</span></span>  
  
 [<span data-ttu-id="0ab64-151">К началу</span><span class="sxs-lookup"><span data-stu-id="0ab64-151">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="0ab64-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ab64-152">See Also</span></span>  
 <span data-ttu-id="0ab64-153">[Упрощенный алгоритм Байеса (Майкрософт)](microsoft-naive-bayes-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="0ab64-153">[Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md) </span></span>  
 <span data-ttu-id="0ab64-154">[Задачи и инструкции средства просмотра моделей интеллектуального анализа данных](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="0ab64-154">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="0ab64-155">[Средства интеллектуального анализа данных](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0ab64-155">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="0ab64-156">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0ab64-156">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  
