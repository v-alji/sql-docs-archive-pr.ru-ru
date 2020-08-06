---
title: Изучение модели кластеризации (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ce8aa034-161b-473f-baec-9c29e0a8e5f5
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: cca9d395fece59f607c8faf209128b9d32663a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751619"
---
# <a name="exploring-the-clustering-model-basic-data-mining-tutorial"></a><span data-ttu-id="4c100-102">Изучение модели кластеризации (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="4c100-102">Exploring the Clustering Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="4c100-103">[!INCLUDE[msCoName](../includes/msconame-md.md)]Алгоритм кластеризации группирует варианты в кластеры, которые содержат аналогичные характеристики.</span><span class="sxs-lookup"><span data-stu-id="4c100-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm groups cases into clusters that contain similar characteristics.</span></span> <span data-ttu-id="4c100-104">Такие группирования полезно использовать для просмотра данных, выявления в них аномалий и создания прогнозов.</span><span class="sxs-lookup"><span data-stu-id="4c100-104">These groupings are useful for exploring data, identifying anomalies in the data, and creating predictions.</span></span>  
  
 <span data-ttu-id="4c100-105">Средство просмотра кластеров [!INCLUDE[msCoName](../includes/msconame-md.md)] содержит следующие вкладки для изучения кластерных моделей интеллектуального анализа данных:</span><span class="sxs-lookup"><span data-stu-id="4c100-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Cluster Viewer provides the following tabs for use in exploring clustering mining models:</span></span>  
  

  
##  <a name="cluster-diagram-tab"></a><a name="ClusterDiagramTab"></a><span data-ttu-id="4c100-106">Вкладка «Диаграмма кластеров»</span><span class="sxs-lookup"><span data-stu-id="4c100-106">Cluster Diagram Tab</span></span>  
 <span data-ttu-id="4c100-107">Вкладка «Диаграмма кластеров» содержит все кластеры, которые имеются в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4c100-107">The Cluster Diagram tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="4c100-108">Линии между кластерами показывают «близость», а их заливка отражает степень схожести кластеров.</span><span class="sxs-lookup"><span data-stu-id="4c100-108">The lines between the clusters represent "closeness" and are shaded based on how similar the clusters are.</span></span> <span data-ttu-id="4c100-109">Цвет каждого из кластеров указывает на частоту появления переменной и состояние в кластере.</span><span class="sxs-lookup"><span data-stu-id="4c100-109">The actual color of each cluster represents the frequency of the variable and the state in the cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-diagram-tab"></a><span data-ttu-id="4c100-110">Изучение модели на вкладке «Диаграмма кластеров»</span><span class="sxs-lookup"><span data-stu-id="4c100-110">To explore the model in the Cluster Diagram tab</span></span>  
  
1.  <span data-ttu-id="4c100-111">Используйте список **модель интеллектуального анализа данных** в верхней части вкладки **средство просмотра моделей интеллектуального анализа данных** , чтобы переключиться на `TM_Clustering` модель.</span><span class="sxs-lookup"><span data-stu-id="4c100-111">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_Clustering` model.</span></span>  
  
2.  <span data-ttu-id="4c100-112">В списке **средство просмотра** выберите **средство просмотра кластеров (Майкрософт**).</span><span class="sxs-lookup"><span data-stu-id="4c100-112">In the **Viewer** list, select **Microsoft Cluster Viewer**.</span></span>  
  
3.  <span data-ttu-id="4c100-113">В поле **Переменная заливки** выберите **Покупатель велосипеда**.</span><span class="sxs-lookup"><span data-stu-id="4c100-113">In the **Shading Variable** box, select **Bike Buyer**.</span></span>  
  
     <span data-ttu-id="4c100-114">Переменная по умолчанию — **Population**, но ее можно изменить на любой атрибут в модели, чтобы определить, какие кластеры содержат элементы с нужными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="4c100-114">The default variable is **Population**, but you can change this to any attribute in the model, to discover which clusters contain members that have the attributes you want.</span></span>  
  
4.  <span data-ttu-id="4c100-115">В поле **штат** выберите **1** , чтобы исследовать случаи приобретения велосипеда.</span><span class="sxs-lookup"><span data-stu-id="4c100-115">Select **1** in the **State** box to explore those cases where a bike was purchased.</span></span>  
  
     <span data-ttu-id="4c100-116">Условные обозначения **плотности** описывают плотность пары состояний атрибута, выбранной в переменной заливки и состоянии.</span><span class="sxs-lookup"><span data-stu-id="4c100-116">The **Density** legend describes the density of the attribute state pair selected in the Shading Variable and the State.</span></span> <span data-ttu-id="4c100-117">В этом примере мы получаем, что клустервис самая темная заливка имеет наибольший процент покупателей велосипедов.</span><span class="sxs-lookup"><span data-stu-id="4c100-117">In this example it tells us that the clusterwith the darkest shading has the highest percentage of bike buyers.</span></span>  
  
5.  <span data-ttu-id="4c100-118">Наведите указатель мыши на кластер с самой темной заливкой.</span><span class="sxs-lookup"><span data-stu-id="4c100-118">Pause your mouse over the cluster with the darkest shading.</span></span>  
  
     <span data-ttu-id="4c100-119">Во всплывающей подсказке отобразится процент вариантов, у которых атрибут `Bike Buyer = 1`.</span><span class="sxs-lookup"><span data-stu-id="4c100-119">A tooltip displays the percentage of cases that have the attribute, `Bike Buyer = 1`.</span></span>  
  
6.  <span data-ttu-id="4c100-120">Выберите кластер с наибольшей плотностью, щелкните кластер правой кнопкой мыши, выберите **Переименовать кластер** и введите " **Покупатели велосипедов велико** " для последующей идентификации.</span><span class="sxs-lookup"><span data-stu-id="4c100-120">Select the cluster that has the highest density, right-click the cluster, select **Rename Cluster** and type **Bike Buyers High** for later identification.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="4c100-121">Найдите кластер с самой светлой заливкой (и с наименьшей плотностью).</span><span class="sxs-lookup"><span data-stu-id="4c100-121">Find the cluster that has the lightest shading (and the lowest density).</span></span> <span data-ttu-id="4c100-122">Щелкните кластер правой кнопкой мыши, выберите **Переименовать кластер** и введите **мало покупателей велосипедов**.</span><span class="sxs-lookup"><span data-stu-id="4c100-122">Right-click the cluster, select **Rename Cluster** and type **Bike Buyers Low**.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="4c100-123">Щелкните **большой кластер покупателей велосипедов** и перетащите его в область панели, чтобы получить четкое представление о подключениях к другим кластерам.</span><span class="sxs-lookup"><span data-stu-id="4c100-123">Click the **Bike Buyers High** cluster and drag it to an area of the pane that will give you a clear view of its connections to the other clusters.</span></span>  
  
     <span data-ttu-id="4c100-124">При выборе кластера выделяются линии, соединяющие его с другими кластерами, что позволяет легко определить связи данного кластера.</span><span class="sxs-lookup"><span data-stu-id="4c100-124">When you select a cluster, the lines that connect this cluster to other clusters are highlighted, so that you can easily see all the relationships for this cluster.</span></span> <span data-ttu-id="4c100-125">Если кластер не выделен, по цвету линий можно определить, насколько тесная связь между кластерами на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="4c100-125">When the cluster is not selected, you can tell by the darkness of the lines how strong the relationships are amongst all the clusters in the diagram.</span></span> <span data-ttu-id="4c100-126">Светлая заливка или отсутствие заливки означает, что кластеры не очень схожи.</span><span class="sxs-lookup"><span data-stu-id="4c100-126">If the shading is light or nonexistent, the clusters are not very similar.</span></span>  
  
9. <span data-ttu-id="4c100-127">С помощью ползунка, расположенного слева от сети, можно отфильтровывать слабые связи и находить кластеры с наиболее близкими связями.</span><span class="sxs-lookup"><span data-stu-id="4c100-127">Use the slider to the left of the network, to filter out the weaker links and find the clusters with the closest relationships.</span></span> <span data-ttu-id="4c100-128">Отделу маркетинга компании [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] может потребоваться объединить похожие кластеры при определении наилучшего способа прямой почтовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="4c100-128">The [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department might want to combine similar clusters together when determining the best method for delivering the targeted mailing.</span></span>  
  

  
##  <a name="cluster-profiles-tab"></a><a name="ClusterProfilesTab"></a><span data-ttu-id="4c100-129">Вкладка «Профили кластеров»</span><span class="sxs-lookup"><span data-stu-id="4c100-129">Cluster Profiles Tab</span></span>  
 <span data-ttu-id="4c100-130">Вкладка **Профили кластеров** предоставляет общее представление `TM_Clustering` модели.</span><span class="sxs-lookup"><span data-stu-id="4c100-130">The **Cluster Profiles** tab provides an overall view of the `TM_Clustering` model.</span></span> <span data-ttu-id="4c100-131">Вкладка **Профили кластеров** содержит столбец для каждого кластера в модели.</span><span class="sxs-lookup"><span data-stu-id="4c100-131">The **Cluster Profiles** tab contains a column for each cluster in the model.</span></span> <span data-ttu-id="4c100-132">В первом столбце перечислены атрибуты, связанные по крайней мере с одним кластером.</span><span class="sxs-lookup"><span data-stu-id="4c100-132">The first column lists the attributes that are associated with at least one cluster.</span></span> <span data-ttu-id="4c100-133">В оставшейся области средства просмотра отображается распределение состояний атрибута для каждого из кластеров.</span><span class="sxs-lookup"><span data-stu-id="4c100-133">The rest of the viewer contains the distribution of the states of an attribute for each cluster.</span></span> <span data-ttu-id="4c100-134">Распределение дискретной переменной отображается в виде цветной полосы с максимальным числом столбцов, отображаемых в списке **гистограмм** .</span><span class="sxs-lookup"><span data-stu-id="4c100-134">The distribution of a discrete variable is shown as a colored bar with the maximum number of bars displayed in the **Histogram bars** list.</span></span> <span data-ttu-id="4c100-135">Непрерывные атрибуты отображаются в ромбовидной диаграмме, отражающей среднее и стандартное отклонение в каждом из кластеров.</span><span class="sxs-lookup"><span data-stu-id="4c100-135">Continuous attributes are displayed with a diamond chart, which represents the mean and standard deviation in each cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-profiles-tab"></a><span data-ttu-id="4c100-136">Изучение модели на вкладке «Профили кластера»</span><span class="sxs-lookup"><span data-stu-id="4c100-136">To explore the model in the Cluster Profiles tab</span></span>  
  
1.  <span data-ttu-id="4c100-137">Установите **5**столбцов **гистограммы** .</span><span class="sxs-lookup"><span data-stu-id="4c100-137">Set **Histogram** bars to **5**.</span></span>  
  
     <span data-ttu-id="4c100-138">В нашей модели значение 5 — это максимальное количество состояний для любой одной переменной.</span><span class="sxs-lookup"><span data-stu-id="4c100-138">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
2.  <span data-ttu-id="4c100-139">Если **Условные обозначения интеллектуального анализа данных** блокируют отображение **профилей атрибутов**, перенесите его в нужное положение.</span><span class="sxs-lookup"><span data-stu-id="4c100-139">If the **Mining Legend** blocks the display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="4c100-140">Выберите столбец **Высокая количество покупателей велосипедов** и перетащите его справа от столбца **Заполнение** .</span><span class="sxs-lookup"><span data-stu-id="4c100-140">Select the **Bike Buyers High** column and drag it to the right of the **Population** column.</span></span>  
  
4.  <span data-ttu-id="4c100-141">Выберите столбец **Bike** Buyers Low и перетащите его справа от столбца большой покупатель **велосипеда** .</span><span class="sxs-lookup"><span data-stu-id="4c100-141">Select the **Bike Buyers Low** column and drag it to the right of the **Bike Buyers High** column.</span></span>  
  
5.  <span data-ttu-id="4c100-142">Щелкните столбец " **большой покупатель велосипедов** ".</span><span class="sxs-lookup"><span data-stu-id="4c100-142">Click the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="4c100-143">Столбец **Variables** сортируется в порядке важности для этого кластера.</span><span class="sxs-lookup"><span data-stu-id="4c100-143">The **Variables** column is sorted in order of importance for that cluster.</span></span> <span data-ttu-id="4c100-144">Просмотрите столбец и проанализируйте характеристики кластера «Много покупателей велосипедов».</span><span class="sxs-lookup"><span data-stu-id="4c100-144">Scroll through the column and review characteristics of the Bike Buyer High cluster.</span></span> <span data-ttu-id="4c100-145">Например, вероятно, что они живут недалеко от работы.</span><span class="sxs-lookup"><span data-stu-id="4c100-145">For example, they are more likely to have a short commute.</span></span>  
  
6.  <span data-ttu-id="4c100-146">Дважды щелкните ячейку **Age** в столбце **высокий Покупатель велосипеда** .</span><span class="sxs-lookup"><span data-stu-id="4c100-146">Double-click the **Age** cell in the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="4c100-147">**Условные обозначения интеллектуального анализа данных** отображают более подробное представление, и вы можете увидеть возраст этих клиентов, а также среднюю возраст.</span><span class="sxs-lookup"><span data-stu-id="4c100-147">The **Mining Legend** displays a more detailed view and you can see the age range of these customers as well as the mean age.</span></span>  
  
7.  <span data-ttu-id="4c100-148">Щелкните правой кнопкой мыши столбец **Bike Buyers Low** и выберите **Скрыть столбец**.</span><span class="sxs-lookup"><span data-stu-id="4c100-148">Right-click the **Bike Buyers Low** column and select **Hide Column**.</span></span>  
  

  
##  <a name="cluster-characteristics-tab"></a><a name="ClusterCharacteristicsTab"></a><span data-ttu-id="4c100-149">Вкладка «Характеристики кластера»</span><span class="sxs-lookup"><span data-stu-id="4c100-149">Cluster Characteristics Tab</span></span>  
 <span data-ttu-id="4c100-150">С помощью вкладки **характеристики кластера** можно более подробно изучить характеристики, составляющие кластер.</span><span class="sxs-lookup"><span data-stu-id="4c100-150">With the **Cluster Characteristics** tab, you can examine in more detail the characteristics that make up a cluster.</span></span> <span data-ttu-id="4c100-151">Вместо сравнения характеристик всех кластеров (как на вкладке «Профили кластера») кластеры можно анализировать по одному.</span><span class="sxs-lookup"><span data-stu-id="4c100-151">Instead of comparing the characteristics of all of the clusters (as in the Cluster Profiles tab), you can explore one cluster at a time.</span></span> <span data-ttu-id="4c100-152">Например, если в списке **кластеров** выбрано значение **высокий Покупатель велосипеда** , можно увидеть характеристики клиентов в этом кластере.</span><span class="sxs-lookup"><span data-stu-id="4c100-152">For example, if you select **Bike Buyers High** from the **Cluster** list, you can see the characteristics of the customers in this cluster.</span></span> <span data-ttu-id="4c100-153">Хотя данное представление отличается от средства просмотра профилей кластера, результаты остаются такими же.</span><span class="sxs-lookup"><span data-stu-id="4c100-153">Though the display is different from the Cluster Profiles viewer, the findings are the same.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c100-154">Если не задано начальное значение для **HoldoutSeed**, результаты будут изменяться при каждом обработке модели.</span><span class="sxs-lookup"><span data-stu-id="4c100-154">Unless you set an initial value for **holdoutseed**, results will vary each time you process the model.</span></span> <span data-ttu-id="4c100-155">Дополнительные сведения см. в разделе [элемент HoldoutSeed](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span><span class="sxs-lookup"><span data-stu-id="4c100-155">For more information, see [HoldoutSeed Element](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span></span>  
  

  
##  <a name="cluster-discrimination-tab"></a><a name="ClusterDiscriminationTab"></a><span data-ttu-id="4c100-156">Вкладка «сравнения кластеров»</span><span class="sxs-lookup"><span data-stu-id="4c100-156">Cluster Discrimination Tab</span></span>  
 <span data-ttu-id="4c100-157">Вкладка **сравнения кластеров** позволяет исследовать характеристики, которые отличают один кластер от другого.</span><span class="sxs-lookup"><span data-stu-id="4c100-157">With the **Cluster Discrimination** tab, you can explore the characteristics that distinguish one cluster from another.</span></span> <span data-ttu-id="4c100-158">После выбора двух кластеров: один из списка **кластеров 1** и один из списка **Кластер 2** , средство просмотра вычисляет различия между кластерами и отображает список атрибутов, которые наиболее различны в кластерах.</span><span class="sxs-lookup"><span data-stu-id="4c100-158">After you select two clusters, one from the **Cluster 1** list, and one from the **Cluster 2** list, the viewer calculates the differences between the clusters and displays a list of the attributes that distinguish the clusters most.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-discrimination-tab"></a><span data-ttu-id="4c100-159">Изучение модели на вкладке «Сравнения кластеров»</span><span class="sxs-lookup"><span data-stu-id="4c100-159">To explore the model in the Cluster Discrimination tab</span></span>  
  
1.  <span data-ttu-id="4c100-160">В поле **Кластер 1** выберите **Высокая Покупатель велосипеда**.</span><span class="sxs-lookup"><span data-stu-id="4c100-160">In the **Cluster 1** box, select **Bike Buyers High**.</span></span>  
  
2.  <span data-ttu-id="4c100-161">В поле **Кластер 2** выберите **мало покупателей велосипедов**.</span><span class="sxs-lookup"><span data-stu-id="4c100-161">In the **Cluster 2** box, select **Bike Buyers Low**.</span></span>  
  
3.  <span data-ttu-id="4c100-162">Щелкните **переменные** , чтобы отсортировать по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="4c100-162">Click **Variables** to sort alphabetically.</span></span>  
  
     <span data-ttu-id="4c100-163">Некоторые из наиболее существенных отличий между клиентами в больших кластерах **покупателей велосипедов Low** и **Bike** Buyers включают возраст, владение автомобилями, количество детей и регион.</span><span class="sxs-lookup"><span data-stu-id="4c100-163">Some of the more substantial differences among the customers in the **Bike Buyers Low** and **Bike Buyers High** clusters include age, car ownership, number of children, and region.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4c100-164">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="4c100-164">Related Tasks</span></span>  
 <span data-ttu-id="4c100-165">Ознакомьтесь со следующими разделами, чтобы изучить другие модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4c100-165">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="4c100-166">Изучение модели дерева принятия решений &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="4c100-166">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="4c100-167">Обзор модели упрощенного алгоритма Байеса &#40;учебнике по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="4c100-167">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4c100-168">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="4c100-168">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4c100-169">Обзор модели упрощенного алгоритма Байеса &#40;учебнике по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="4c100-169">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="4c100-170">Предыдущая задача занятия</span><span class="sxs-lookup"><span data-stu-id="4c100-170">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="4c100-171">Изучение модели дерева принятия решений &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="4c100-171">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c100-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="4c100-172">See Also</span></span>  
 <span data-ttu-id="4c100-173">[Просмотр модели с помощью средства просмотра кластеров (Майкрософт)](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4c100-173">[Browse a Model Using the Microsoft Cluster Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span></span>  
 <span data-ttu-id="4c100-174">[Вкладка "сравнения кластеров" &#40;средство просмотра моделей интеллектуального анализа данных&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4c100-174">[Cluster Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="4c100-175">[Вкладка "Профили кластера" &#40;средство просмотра моделей интеллектуального анализа данных&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4c100-175">[Cluster Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="4c100-176">[Вкладка Характеристики кластера &#40;средство просмотра моделей интеллектуального анализа данных&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4c100-176">[Cluster Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="4c100-177">Вкладка Диаграмма кластеров &#40;средство просмотра моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="4c100-177">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/cluster-diagram-tab-mining-model-viewer.md)  
  
  
