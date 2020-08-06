---
title: Изучение модели дерева принятия решений (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2e1472c2-3f3e-4dae-acb3-62fca374d397
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a2c7f063d7cb73cdc431fb1bc94188c9266c10c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734721"
---
# <a name="exploring-the-decision-tree-model-basic-data-mining-tutorial"></a><span data-ttu-id="673fa-102">Изучение модели дерева принятия решений (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="673fa-102">Exploring the Decision Tree Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="673fa-103">[!INCLUDE[msCoName](../includes/msconame-md.md)]Алгоритм дерева принятия решений прогнозирует, какие столбцы влияют на принятие решения о покупке велосипеда на основе оставшихся столбцов в обучающем наборе.</span><span class="sxs-lookup"><span data-stu-id="673fa-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm predicts which columns influence the decision to purchase a bike based upon the remaining columns in the training set.</span></span>  
  

  
##  <a name="decision-tree-tab"></a><a name="Decision_Tree_Tab"></a><span data-ttu-id="673fa-104">Вкладка дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="673fa-104">Decision Tree Tab</span></span>  
 <span data-ttu-id="673fa-105">На вкладке **дерево решений** можно просматривать деревья принятия решений для каждого прогнозируемого атрибута в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="673fa-105">On the **Decision Tree** tab, you can view decision trees for every predictable attribute in the dataset.</span></span>  
  
 <span data-ttu-id="673fa-106">В этом случае модель прогнозирует только один столбец, Покупатель велосипеда, поэтому для просмотра доступно только одно дерево.</span><span class="sxs-lookup"><span data-stu-id="673fa-106">In this case, the model predicts only one column, Bike Buyer, so there is only one tree to view.</span></span> <span data-ttu-id="673fa-107">При наличии большего числа деревьев можно использовать окно **дерева** для выбора другого дерева.</span><span class="sxs-lookup"><span data-stu-id="673fa-107">If there were more trees, you could use the **Tree** box to choose another tree.</span></span>  
  
 <span data-ttu-id="673fa-108">При просмотре `TM_Decision_Tree` модели в средстве просмотра деревьев решений можно увидеть наиболее важные атрибуты в левой части диаграммы.</span><span class="sxs-lookup"><span data-stu-id="673fa-108">As you view the `TM_Decision_Tree` model in the Decision Tree viewer, you can see the most important attributes at the left side of the chart.</span></span> <span data-ttu-id="673fa-109">«Самое важное» означает, что эти атрибуты оказывают наибольшее влияние на результат.</span><span class="sxs-lookup"><span data-stu-id="673fa-109">"Most important" means that these attributes have the greatest influence on the outcome.</span></span> <span data-ttu-id="673fa-110">Атрибуты, расположенные ниже по дереву (справа от диаграммы), оказываются меньше.</span><span class="sxs-lookup"><span data-stu-id="673fa-110">Attributes further down the tree (to the right of the chart) have less of an effect.</span></span>  
  
 <span data-ttu-id="673fa-111">В этом примере Age является одним из наиболее важных факторов при прогнозировании приобретения велосипеда.</span><span class="sxs-lookup"><span data-stu-id="673fa-111">In this example, age is the single most important factor in predicting bike buying.</span></span> <span data-ttu-id="673fa-112">Модель группирует клиентов по возрасту, а затем показывает следующий важный атрибут для каждой возрастной группы.</span><span class="sxs-lookup"><span data-stu-id="673fa-112">The model groups customers by age, and then shows the next more important attribute for each age group.</span></span> <span data-ttu-id="673fa-113">Например, в группе клиентов с возрастом 34 по 40, число машин, которыми владеет автомобили, является самым надежным прогнозом после возраста.</span><span class="sxs-lookup"><span data-stu-id="673fa-113">For example, in the group of customers aged 34 to 40, the number of cars owned is the strongest predictor after age.</span></span>  
  
#### <a name="to-explore-the-model-in-the-decision-tree-tab"></a><span data-ttu-id="673fa-114">Исследование модели на вкладке «Дерево принятия решений»</span><span class="sxs-lookup"><span data-stu-id="673fa-114">To explore the model in the Decision Tree tab</span></span>  
  
1.  <span data-ttu-id="673fa-115">Выберите вкладку **средство просмотра моделей интеллектуального анализа** **данных в конструкторе интеллектуального анализа**.</span><span class="sxs-lookup"><span data-stu-id="673fa-115">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
     <span data-ttu-id="673fa-116">По умолчанию конструктор открывает первую модель, добавленную в структуру, в данном случае `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="673fa-116">By default, the designer opens to the first model that was added to the structure -- in this case, `TM_Decision_Tree`.</span></span>  
  
2.  <span data-ttu-id="673fa-117">Для настройки размера отображения дерева воспользуйтесь кнопками со значком лупы.</span><span class="sxs-lookup"><span data-stu-id="673fa-117">Use the magnifying glass buttons to adjust the size of the tree display.</span></span>  
  
     <span data-ttu-id="673fa-118">По умолчанию [!INCLUDE[msCoName](../includes/msconame-md.md)] средство просмотра деревьев отображает только первые три уровня дерева.</span><span class="sxs-lookup"><span data-stu-id="673fa-118">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer shows only the first three levels of the tree.</span></span> <span data-ttu-id="673fa-119">Если дерево содержит меньше трех уровней, показываются только существующие уровни.</span><span class="sxs-lookup"><span data-stu-id="673fa-119">If the tree contains fewer than three levels, the viewer shows only the existing levels.</span></span> <span data-ttu-id="673fa-120">Просмотреть дополнительные уровни можно с помощью ползунка **Показать уровень** или списка **расширений по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="673fa-120">You can view more levels by using the **Show Level** slider or the **Default Expansion** list.</span></span>  
  
3.  <span data-ttu-id="673fa-121">**Уровень** слайдового показа на четвертую панель.</span><span class="sxs-lookup"><span data-stu-id="673fa-121">Slide **Show Level** to the fourth bar.</span></span>  
  
4.  <span data-ttu-id="673fa-122">Измените значение параметра **фон** на `1` .</span><span class="sxs-lookup"><span data-stu-id="673fa-122">Change the **Background** value to `1`.</span></span>  
  
     <span data-ttu-id="673fa-123">Изменяя параметры **фона** , можно быстро увидеть количество вариантов в каждом узле, для которых задано целевое значение `1` для [Bike Buyer].</span><span class="sxs-lookup"><span data-stu-id="673fa-123">By changing the **Background** setting, you can quickly see the number of cases in each node that have the target value of `1` for [Bike Buyer].</span></span> <span data-ttu-id="673fa-124">В этом конкретном сценарии следует помнить, что каждый вариант представляет покупателя.</span><span class="sxs-lookup"><span data-stu-id="673fa-124">Remember that in this particular scenario, each case represents a customer.</span></span> <span data-ttu-id="673fa-125">Значение `1` указывает, что клиент ранее приобрел велосипед; значение **0** указывает, что клиент не приобрел велосипед.</span><span class="sxs-lookup"><span data-stu-id="673fa-125">The value `1` indicates that the customer previously purchased a bike; the value **0** indicates that the customer has not purchased a bike.</span></span> <span data-ttu-id="673fa-126">Чем темнее заливка узла, тем больший процент вариантов с нужным целевым значением он содержит.</span><span class="sxs-lookup"><span data-stu-id="673fa-126">The darker the shading of the node, the higher the percentage of cases in the node that have the target value.</span></span>  
  
5.  <span data-ttu-id="673fa-127">Наведите курсор на узел с меткой **все**.</span><span class="sxs-lookup"><span data-stu-id="673fa-127">Place your cursor over the node labeled **All**.</span></span> <span data-ttu-id="673fa-128">В подсказке отобразятся следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="673fa-128">An tooltip will display the following information:</span></span>  
  
    -   <span data-ttu-id="673fa-129">Общее число вариантов</span><span class="sxs-lookup"><span data-stu-id="673fa-129">Total number of cases</span></span>  
  
    -   <span data-ttu-id="673fa-130">Число вариантов покупки товара, не являющегося велосипедом</span><span class="sxs-lookup"><span data-stu-id="673fa-130">Number of non bike buyer cases</span></span>  
  
    -   <span data-ttu-id="673fa-131">Число вариантов покупки велосипеда</span><span class="sxs-lookup"><span data-stu-id="673fa-131">Number of bike buyer cases</span></span>  
  
    -   <span data-ttu-id="673fa-132">Число вариантов с отсутствующими значениями для элемента [Покупатель велосипеда]</span><span class="sxs-lookup"><span data-stu-id="673fa-132">Number of cases with missing values for [Bike Buyer]</span></span>  
  
     <span data-ttu-id="673fa-133">Можно также поместить курсор над любым узлом в дереве и просмотреть условие, необходимое для достижения этого узла из узла, стоящего перед ним.</span><span class="sxs-lookup"><span data-stu-id="673fa-133">Alternately, place your cursor over any node in the tree to see the condition that is required to reach that node from the node that comes before it.</span></span> <span data-ttu-id="673fa-134">Эти же сведения можно также просмотреть в условных обозначениях **интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="673fa-134">You can also view this same information in the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="673fa-135">Щелкните узел для **Age >= 34 и < 41**.</span><span class="sxs-lookup"><span data-stu-id="673fa-135">Click on the node for **Age >=34 and < 41**.</span></span> <span data-ttu-id="673fa-136">Отобразится гистограмма в виде тонкой горизонтальной полоски, пересекающей узел. Она показывает распределение клиентов в этом диапазоне возраста, которые раньше покупали (розовый цвет) и не покупали (синий цвет) велосипед.</span><span class="sxs-lookup"><span data-stu-id="673fa-136">The histogram is displayed as a thin horizontal bar across the node and represents the distribution of customers in this age range who previously did (pink) and did not (blue) purchase a bike.</span></span> <span data-ttu-id="673fa-137">В средстве просмотра показано, что клиенты в возрасте от 34 до 40 лет с одним автомобилем или не имеющие автомобиля, вероятно, купят велосипед.</span><span class="sxs-lookup"><span data-stu-id="673fa-137">The Viewer shows us that customers between the ages of 34 and 40 with one or no cars are likely to purchase a bike.</span></span> <span data-ttu-id="673fa-138">Сделав еще один шаг, мы видим, что вероятность покупки велосипеда увеличивается, если возраст клиента — от 38 до 40 лет.</span><span class="sxs-lookup"><span data-stu-id="673fa-138">Taking it one step further, we find that the likelihood to purchase a bike increases if the customer is actually age 38 to 40.</span></span>  
  
 <span data-ttu-id="673fa-139">Поскольку при создании структуры и модели была включена детализация, из вариантов модели и структуры интеллектуального анализа данных можно получить подробные сведения, в том числе для столбцов, не включенных в модель интеллектуального анализа данных (например, столбцов emailAddress, FirstName).</span><span class="sxs-lookup"><span data-stu-id="673fa-139">Because you enabled drillthrough when you created the structure and model, you can retrieve detailed information from the model cases and mining structure, including those columns that were not included in the mining model (e.g., emailAddress, FirstName).</span></span>  
  
 <span data-ttu-id="673fa-140">Дополнительные сведения см. в разделе [Запросы детализации (интеллектуальный анализ данных)](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="673fa-140">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-drill-through-to-case-data"></a><span data-ttu-id="673fa-141">Углубленная детализация данных вариантов</span><span class="sxs-lookup"><span data-stu-id="673fa-141">To drill through to case data</span></span>  
  
1.  <span data-ttu-id="673fa-142">Щелкните узел правой кнопкой мыши и выберите пункт **детализировать** **только столбцы модели**.</span><span class="sxs-lookup"><span data-stu-id="673fa-142">Right-click a node, and select **Drill Through** then **Model Columns Only**.</span></span>  
  
     <span data-ttu-id="673fa-143">Сведения для каждого обучающего варианта отображаются в формате электронной таблицы.</span><span class="sxs-lookup"><span data-stu-id="673fa-143">The details for each training case are displayed in spreadsheet format.</span></span> <span data-ttu-id="673fa-144">Эти сведения получены из представления vTargetMail, выбранного как таблица вариантов при построении структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="673fa-144">These details come from the vTargetMail view that you selected as the case table when building the mining structure.</span></span>  
  
2.  <span data-ttu-id="673fa-145">Щелкните узел правой кнопкой мыши и выберите пункт **Детализация** , затем **модель и столбцы структуры**.</span><span class="sxs-lookup"><span data-stu-id="673fa-145">Right-click a node, and select **Drill Through** then **Model and Structure Columns**.</span></span>  
  
     <span data-ttu-id="673fa-146">Отобразится та же электронная таблица со столбцами структуры, присоединенными в конец таблицы.</span><span class="sxs-lookup"><span data-stu-id="673fa-146">The same spreadsheet displays with the structure columns appended to the end.</span></span>  
  
  
###  <a name="dependency-network-tab"></a><a name="Dependency_Network_Tab"></a><span data-ttu-id="673fa-147">Вкладка "Сеть зависимостей"</span><span class="sxs-lookup"><span data-stu-id="673fa-147">Dependency Network Tab</span></span>  
 <span data-ttu-id="673fa-148">На вкладке **Сеть зависимостей** отображаются связи между атрибутами, которые влияют на прогнозируемую возможность модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="673fa-148">The **Dependency Network** tab displays the relationships between the attributes that contribute to the predictive ability of the mining model.</span></span> <span data-ttu-id="673fa-149">Средство просмотра «Сеть зависимостей» еще более явно подтверждает предположение, что возраст и регион являются важными факторами в прогнозировании покупки велосипеда.</span><span class="sxs-lookup"><span data-stu-id="673fa-149">The Dependency Network viewer reinforces our findings that Age and Region are important factors in predicting bike buying.</span></span>  
  
##### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="673fa-150">Исследование модели на вкладке «Сеть зависимостей»</span><span class="sxs-lookup"><span data-stu-id="673fa-150">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="673fa-151">Щелкните `Bike Buyer` узел, чтобы найти его зависимости.</span><span class="sxs-lookup"><span data-stu-id="673fa-151">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="673fa-152">Центральный узел для сети зависимостей, `Bike Buyer` представляет прогнозируемый атрибут в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="673fa-152">The center node for the dependency network, `Bike Buyer`, represents the predictable attribute in the mining model.</span></span> <span data-ttu-id="673fa-153">На диаграмме выделяются все подключенные узлы, которые влияют на прогнозируемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="673fa-153">The graph highlights any connected nodes that have an effect on the predictable attribute.</span></span>  
  
2.  <span data-ttu-id="673fa-154">Настройте ползунок **все ссылки** , чтобы указать самый влиятельные атрибут.</span><span class="sxs-lookup"><span data-stu-id="673fa-154">Adjust the **All Links** slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="673fa-155">При перетаскивании ползунка атрибуты, которые имеют Неслабое воздействие на столбец [Bike Buyer], удаляются из диаграммы.</span><span class="sxs-lookup"><span data-stu-id="673fa-155">As you drag down the slider, attributes that have only a weak effect on the [Bike Buyer] column are removed from the graph.</span></span> <span data-ttu-id="673fa-156">Настроив ползунок, можно обнаружить, что возраст и регион являются наибольшими факторами прогнозирования того, является ли кто-либо покупатель велосипедом.</span><span class="sxs-lookup"><span data-stu-id="673fa-156">By adjusting the slider, you can discover that Age and Region are the greatest factors in predicting whether someone is a bike buyer.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="673fa-157">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="673fa-157">Related Tasks</span></span>  
 <span data-ttu-id="673fa-158">Просмотрите эти разделы, чтобы исследовать данные с помощью других типов моделей.</span><span class="sxs-lookup"><span data-stu-id="673fa-158">See these topics to explore the data using the other kinds of models.</span></span>  
  
-   [<span data-ttu-id="673fa-159">Изучение модели кластеризации &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="673fa-159">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="673fa-160">Обзор модели упрощенного алгоритма Байеса &#40;учебнике по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="673fa-160">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="673fa-161">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="673fa-161">Next Task in Lesson</span></span>  
 [<span data-ttu-id="673fa-162">Изучение модели кластеризации &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="673fa-162">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="673fa-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="673fa-163">See Also</span></span>  
 <span data-ttu-id="673fa-164">[Задачи и инструкции средства просмотра моделей интеллектуального анализа данных](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="673fa-164">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="673fa-165">[Вкладка "дерево решений" &#40;средство просмотра моделей интеллектуального анализа данных&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="673fa-165">[Decision Tree Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="673fa-166">[Вкладка Сеть зависимостей &#40;средство просмотра моделей интеллектуального анализа данных&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="673fa-166">[Dependency Network Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="673fa-167">Просмотр модели с помощью средства просмотра деревьев (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="673fa-167">Browse a Model Using the Microsoft Tree Viewer</span></span>](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
  
