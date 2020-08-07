---
title: Изучение модели упрощенного алгоритма Байеса (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b06708d5-4477-4a51-bf8d-0b1e3c1f9ebb
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a26fa972e1ed50e2f4107026210a5935fcb86d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734717"
---
# <a name="exploring-the-naive-bayes-model-basic-data-mining-tutorial"></a><span data-ttu-id="c9a76-102">Изучение модели упрощенного алгоритма Байеса (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="c9a76-102">Exploring the Naive Bayes Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="c9a76-103">[!INCLUDE[msCoName](../includes/msconame-md.md)]Упрощенный алгоритм Байеса предоставляет несколько методов для отображения взаимодействия между покупкой велосипедов и входными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="c9a76-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm provides several methods for displaying the interaction between bike buying and the input attributes.</span></span>  
  
 <span data-ttu-id="c9a76-104">[!INCLUDE[msCoName](../includes/msconame-md.md)]Средство просмотра упрощенного алгоритма Байеса предоставляет следующие вкладки для изучения моделей интеллектуального анализа упрощенного алгоритма Байеса:</span><span class="sxs-lookup"><span data-stu-id="c9a76-104">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for use in exploring Naive Bayes mining models:</span></span>  
  
 
  
##  <a name="dependency-network"></a><a name="DependencyNetwork"></a><span data-ttu-id="c9a76-105">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="c9a76-105">Dependency Network</span></span>  
 <span data-ttu-id="c9a76-106">Вкладка **Сеть зависимостей** работает так же, как и вкладка **Сеть зависимостей** для [!INCLUDE[msCoName](../includes/msconame-md.md)] средства просмотра деревьев.</span><span class="sxs-lookup"><span data-stu-id="c9a76-106">The **Dependency Network** tab works in the same way as the **Dependency Network** tab for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer.</span></span> <span data-ttu-id="c9a76-107">Каждый из узлов в средстве просмотра отображает атрибут, а линии между узлами представляют связи.</span><span class="sxs-lookup"><span data-stu-id="c9a76-107">Each node in the viewer represents an attribute, and the lines between nodes represent relationships.</span></span> <span data-ttu-id="c9a76-108">В средстве просмотра показаны все атрибуты, влияющие на состояние прогнозируемого атрибута «Покупатель велосипеда».</span><span class="sxs-lookup"><span data-stu-id="c9a76-108">In the viewer, you can see all the attributes that affect the state of the predictable attribute, Bike Buyer.</span></span>  
  
#### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="c9a76-109">Исследование модели на вкладке «Сеть зависимостей»</span><span class="sxs-lookup"><span data-stu-id="c9a76-109">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="c9a76-110">Используйте список **модель интеллектуального анализа данных** в верхней части вкладки **средство просмотра моделей интеллектуального анализа данных** , чтобы переключиться на `TM_NaiveBayes` модель.</span><span class="sxs-lookup"><span data-stu-id="c9a76-110">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_NaiveBayes` model.</span></span>  
  
2.  <span data-ttu-id="c9a76-111">Используйте список **средств просмотра** для переключения в **средство просмотра упрощенных алгоритмов**Байеса (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="c9a76-111">Use the **Viewer** list to switch to **Microsoft Naive Bayes Viewer**.</span></span>  
  
3.  <span data-ttu-id="c9a76-112">Щелкните `Bike Buyer` узел, чтобы найти его зависимости.</span><span class="sxs-lookup"><span data-stu-id="c9a76-112">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="c9a76-113">Розовая заливка указывает на то, что все атрибуты влияют на покупку велосипедов.</span><span class="sxs-lookup"><span data-stu-id="c9a76-113">The pink shading indicates that all of the attributes have an effect on bike buying.</span></span>  
  
4.  <span data-ttu-id="c9a76-114">Определите с помощью ползунка атрибут, оказывающий наибольшее влияние.</span><span class="sxs-lookup"><span data-stu-id="c9a76-114">Adjust the slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="c9a76-115">По мере перемещения ползунка вниз остаются только атрибуты, оказывающие наибольшее влияние на столбец [Покупатель велосипеда].</span><span class="sxs-lookup"><span data-stu-id="c9a76-115">As you lower the slider, only the attributes that have the greatest effect on the [Bike Buyer] column remain.</span></span> <span data-ttu-id="c9a76-116">Регулировка ползунка поможет выяснить, что наибольшее значение имеют такие атрибуты, как число автомобилей во владении, расстояние до работы и общее количество детей.</span><span class="sxs-lookup"><span data-stu-id="c9a76-116">By adjusting the slider, you can discover that a few of the most influential attributes are: number of cars owned, commute distance, and total number of children.</span></span>  
 
  
##  <a name="attribute-profiles"></a><a name="AttributeProfiles"></a> <span data-ttu-id="c9a76-117">Профили атрибутов</span><span class="sxs-lookup"><span data-stu-id="c9a76-117">Attribute Profiles</span></span>  
 <span data-ttu-id="c9a76-118">Вкладка **Профили атрибутов** описывает, как различные состояния входных атрибутов влияют на результат прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="c9a76-118">The **Attribute Profiles** tab describes how different states of the input attributes affect the outcome of the predictable attribute.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-profiles-tab"></a><span data-ttu-id="c9a76-119">Исследование модели на вкладке «Профили атрибутов»</span><span class="sxs-lookup"><span data-stu-id="c9a76-119">To explore the model in the Attribute Profiles tab</span></span>  
  
1.  <span data-ttu-id="c9a76-120">Убедитесь, что в поле **прогнозируемый** `Bike Buyer` выбрано значение.</span><span class="sxs-lookup"><span data-stu-id="c9a76-120">In the **Predictable** box, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="c9a76-121">Если **Условные обозначения интеллектуального анализа данных** блокируют отображение **профилей атрибутов**, переместите его в нужное положение.</span><span class="sxs-lookup"><span data-stu-id="c9a76-121">If the **Mining Legend** is blocking display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="c9a76-122">В поле Столбцы **гистограммы** выберите **5**.</span><span class="sxs-lookup"><span data-stu-id="c9a76-122">In the **Histogram** bars box, select **5**.</span></span>  
  
     <span data-ttu-id="c9a76-123">В нашей модели значение 5 — это максимальное количество состояний для любой одной переменной.</span><span class="sxs-lookup"><span data-stu-id="c9a76-123">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
     <span data-ttu-id="c9a76-124">Атрибуты, влияющие на состояние данного прогнозируемого атрибута, перечисляются вместе со значениями каждого состояния входных атрибутов и их распределениями по каждому состоянию прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="c9a76-124">The attributes that affect the state of this predictable attribute are listed together with the values of each state of the input attributes and their distributions in each state of the predictable attribute.</span></span>  
  
4.  <span data-ttu-id="c9a76-125">В столбце **атрибуты** найдите **число машин, принадлежащих владельцу**.</span><span class="sxs-lookup"><span data-stu-id="c9a76-125">In the **Attributes** column, find **Number Cars Owned**.</span></span>  <span data-ttu-id="c9a76-126">Обратите внимание на различия в гистограммах для покупателей велосипедов (столбец с меткой 1) и тех, кто не покупает (столбец с меткой 0).</span><span class="sxs-lookup"><span data-stu-id="c9a76-126">Notice the differences in the histograms for bike buyers (column labeled 1) and non-buyers (column labeled 0).</span></span> <span data-ttu-id="c9a76-127">Человек, у которого есть один автомобиль или вообще нет машины, является наиболее вероятным покупателем велосипеда.</span><span class="sxs-lookup"><span data-stu-id="c9a76-127">A person with zero or one car is much more likely to buy a bike.</span></span>  
  
5.  <span data-ttu-id="c9a76-128">Дважды щелкните ячейку **число машин в собственности** в столбце Bike Buyer (столбец с меткой 1).</span><span class="sxs-lookup"><span data-stu-id="c9a76-128">Double-click the **Number Cars Owned** cell in the bike buyer (column labeled 1) column.</span></span>  
  
     <span data-ttu-id="c9a76-129">**Условные обозначения интеллектуального анализа данных** отображают более подробное представление.</span><span class="sxs-lookup"><span data-stu-id="c9a76-129">The **Mining Legend** displays a more detailed view.</span></span>  
  
  
##  <a name="attribute-characteristics"></a><a name="AttributeCharacteristics"></a> <span data-ttu-id="c9a76-130">Характеристики атрибута</span><span class="sxs-lookup"><span data-stu-id="c9a76-130">Attribute Characteristics</span></span>  
 <span data-ttu-id="c9a76-131">На вкладке **характеристики атрибута** можно выбрать атрибут и значение, чтобы увидеть, как часто значения для других атрибутов отображаются в выбранных вариантах значений.</span><span class="sxs-lookup"><span data-stu-id="c9a76-131">With the **Attribute Characteristics** tab, you can select an attribute and value to see how frequently values for other attributes appear in the selected value cases.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-characteristics-tab"></a><span data-ttu-id="c9a76-132">Исследование модели на вкладке «Характеристики атрибута»</span><span class="sxs-lookup"><span data-stu-id="c9a76-132">To explore the model in the Attribute Characteristics tab</span></span>  
  
1.  <span data-ttu-id="c9a76-133">Убедитесь, что в списке **атрибут** `Bike Buyer` выбрано значение.</span><span class="sxs-lookup"><span data-stu-id="c9a76-133">In the **Attribute** list, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="c9a76-134">Установите **значение** **1**.</span><span class="sxs-lookup"><span data-stu-id="c9a76-134">Set the **Value** to **1**.</span></span>  
  
     <span data-ttu-id="c9a76-135">В средстве просмотра будут показано, что заказчики, которые не имеют проживающих с ними детей, работают недалеко от дома и живут в Североамериканском регионе, являются более вероятными покупателями велосипеда.</span><span class="sxs-lookup"><span data-stu-id="c9a76-135">In the viewer, you will see that customers who have no children at home, short commutes, and live in the North America region are more likely to buy a bike.</span></span>  
  
  
##  <a name="attribute-discrimination"></a><a name="AttributeDiscrimination"></a> <span data-ttu-id="c9a76-136">Сравнение атрибутов</span><span class="sxs-lookup"><span data-stu-id="c9a76-136">Attribute Discrimination</span></span>  
 <span data-ttu-id="c9a76-137">С помощью вкладки **Сравнение атрибутов** можно исследовать связь между двумя дискретными значениями приобретения велосипеда и другими значениями атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c9a76-137">With the **Attribute Discrimination** tab, you can investigate the relationship between two discrete values of bike buying and other attribute values.</span></span> <span data-ttu-id="c9a76-138">Поскольку `TM_NaiveBayes` модель имеет только два состояния, 1 и 0, вносить изменения в средство просмотра не требуется.</span><span class="sxs-lookup"><span data-stu-id="c9a76-138">Because the `TM_NaiveBayes` model has only two states, 1 and 0, you do not have to make any changes to the viewer.</span></span>  
  
 <span data-ttu-id="c9a76-139">В средстве просмотра показано, что велосипеды, как правило, покупают люди, не имеющие в распоряжении машин, и наоборот, люди, имеющие две машины, большей частью велосипеды не покупают.</span><span class="sxs-lookup"><span data-stu-id="c9a76-139">In the viewer, you can see that people who do not own cars tend to buy bicycles, and people who own two cars tend not to buy bicycles.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c9a76-140">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c9a76-140">Related Tasks</span></span>  
 <span data-ttu-id="c9a76-141">Ознакомьтесь со следующими разделами, чтобы изучить другие модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="c9a76-141">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="c9a76-142">Изучение модели дерева принятия решений &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c9a76-142">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="c9a76-143">Изучение модели кластеризации &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c9a76-143">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="c9a76-144">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="c9a76-144">Next Lesson</span></span>  
 [<span data-ttu-id="c9a76-145">Занятие 5. Тестирование моделей &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c9a76-145">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="c9a76-146">Предыдущая задача занятия</span><span class="sxs-lookup"><span data-stu-id="c9a76-146">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="c9a76-147">Изучение модели кластеризации &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c9a76-147">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="c9a76-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9a76-148">See Also</span></span>  
 <span data-ttu-id="c9a76-149">[Просмотр модели с помощью средства просмотра упрощенных алгоритмов Байеса (Майкрософт)](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="c9a76-149">[Browse a Model Using the Microsoft Naive Bayes Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span></span>  
 <span data-ttu-id="c9a76-150">[Вкладка "Сравнение атрибутов" &#40;средство просмотра моделей интеллектуального анализа данных&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="c9a76-150">[Attribute Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="c9a76-151">[Вкладка "Профили атрибутов" &#40;средство просмотра моделей интеллектуального анализа данных&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="c9a76-151">[Attribute Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="c9a76-152">[Вкладка Характеристики атрибута &#40;средство просмотра моделей интеллектуального анализа данных&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="c9a76-152">[Attribute Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="c9a76-153">Вкладка Сеть зависимостей &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c9a76-153">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md)  
  
  
