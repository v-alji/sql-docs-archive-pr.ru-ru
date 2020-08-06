---
title: Просмотр модели кластеризации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- clustering [data mining]
- mining model, clustering
ms.assetid: 7f3f0949-d791-403a-88e2-54cb1a803dae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f1d508603acd29fde981bddc5642b54ca9413f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656845"
---
# <a name="browsing-a-clustering-model"></a><span data-ttu-id="aadec-102">Просмотр модели кластеризации</span><span class="sxs-lookup"><span data-stu-id="aadec-102">Browsing a Clustering Model</span></span>
  <span data-ttu-id="aadec-103">При открытии модели кластеризации с помощью **кнопки Обзор**модель отображается в интерактивном средстве просмотра, аналогичном средству просмотра кластеризации в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aadec-103">When you open a clustering model using **Browse**, the model is displayed in an interactive viewer, similar to the clustering viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="aadec-104">Средство просмотра позволяет просмотреть кластеры и понять характеристики кластеров.</span><span class="sxs-lookup"><span data-stu-id="aadec-104">The viewer helps you explore the clusters that were created, and understand cluster characteristics.</span></span> <span data-ttu-id="aadec-105">Также можно сравнить и сопоставить отдельные сегменты с другими сегментами или с заполнением.</span><span class="sxs-lookup"><span data-stu-id="aadec-105">You can also compare and contrast individual segments with other segments or with the population.</span></span>  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="aadec-106">Изучение модели</span><span class="sxs-lookup"><span data-stu-id="aadec-106">Explore the Model</span></span>  
 <span data-ttu-id="aadec-107">Окно **Обзор** содержит следующие средства, помогающие понять модель кластеризации и изучить атрибуты базовых групп данных:</span><span class="sxs-lookup"><span data-stu-id="aadec-107">The **Browse** window includes the following tools to help you understand your clustering model and explore the attributes of the underlying data groups:</span></span>  
  
-   [<span data-ttu-id="aadec-108">Диаграмма кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-108">Cluster Diagram</span></span>](#BKMK_ClusterDiagram)  
  
-   [<span data-ttu-id="aadec-109">Профили кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-109">Cluster Profiles</span></span>](#BKMK_ClusterProfiles)  
  
-   [<span data-ttu-id="aadec-110">Характеристики кластера</span><span class="sxs-lookup"><span data-stu-id="aadec-110">Cluster Characteristics</span></span>](#BKMK_ClusterCharacteristics)  
  
-   [<span data-ttu-id="aadec-111">Сравнения кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-111">Cluster Discrimination</span></span>](#BKMK_ClusterDiscrimination)  
  
 <span data-ttu-id="aadec-112">Чтобы поэкспериментировать с моделью кластеризации, можно использовать образец данных на вкладке "обучение" книги "образец данных" и создать модель кластеризации с помощью [мастера кластеров &#40;надстройки интеллектуального анализа данных для&#41;Excel](cluster-wizard-data-mining-add-ins-for-excel.md) и все значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aadec-112">To experiment with a clustering model, you can use the sample data on the Training tab of the sample data workbook, and build a clustering model using [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) and all the defaults.</span></span>  
  
###  <a name="cluster-diagram"></a><a name="BKMK_ClusterDiagram"></a><span data-ttu-id="aadec-113">Диаграмма кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-113">Cluster Diagram</span></span>  
 <span data-ttu-id="aadec-114">На вкладке **Диаграмма кластеров** отображаются все кластеры, наявляющиеся в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="aadec-114">The **Cluster Diagram** tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="aadec-115">Здесь можно просмотреть количество различных группировок, найденных в наборе данных, и их удаленность друг от друга.</span><span class="sxs-lookup"><span data-stu-id="aadec-115">Here you can see how many different groupings were found in your data set, and how near or far they are from each other.</span></span>  
  
##### <a name="explore-the-cluster-diagram"></a><span data-ttu-id="aadec-116">Просмотр диаграммы кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-116">Explore the cluster diagram</span></span>  
  
1.  <span data-ttu-id="aadec-117">Щелкните кластер 1 на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="aadec-117">Click Cluster 1 in the diagram.</span></span>  
  
     <span data-ttu-id="aadec-118">Обратите внимание, что серые линии, соединяющие все кластеры, изменяются так, что линии, ведущие к выбранному кластеру, выделяются ярко синим цветом.</span><span class="sxs-lookup"><span data-stu-id="aadec-118">Note how the gray lines connecting all clusters change so that lines leading to the selected cluster are highlighted in bright blue.</span></span>  
  
     <span data-ttu-id="aadec-119">![общие сведения о диаграмме кластеров](media/dm13-cluster-diagram-intro.gif "общие сведения о диаграмме кластеров")</span><span class="sxs-lookup"><span data-stu-id="aadec-119">![cluster diagram intro](media/dm13-cluster-diagram-intro.gif "cluster diagram intro")</span></span>  
  
     <span data-ttu-id="aadec-120">Интенсивность заливки линии, соединяющей кластеры, показывает степень их сходства.</span><span class="sxs-lookup"><span data-stu-id="aadec-120">The intensity of the line that connects one cluster to another represents the strength of the similarity of the clusters.</span></span> <span data-ttu-id="aadec-121">Светлая заливка или отсутствие заливки означает, что кластеры не очень схожи.</span><span class="sxs-lookup"><span data-stu-id="aadec-121">If the shading is light or nonexistent, the clusters are not very similar.</span></span> <span data-ttu-id="aadec-122">Чем темнее линия, тем сильнее сходство двух кластеров.</span><span class="sxs-lookup"><span data-stu-id="aadec-122">As the line becomes darker, it indicates that the similarity between the two clusters is stronger.</span></span>  
  
2.  <span data-ttu-id="aadec-123">Перетащите ползунок слева от диаграммы кластеров, чтобы изменить количество строк, отображаемых в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="aadec-123">Click and drag the slider to the left of the cluster diagram, to adjust how many lines the viewer shows.</span></span>  
  
     <span data-ttu-id="aadec-124">Если переместить ползунок ниже, будут видны только наиболее прочные связи между кластерами.</span><span class="sxs-lookup"><span data-stu-id="aadec-124">When you drag the slider down, only the strongest links between clusters are shown.</span></span> <span data-ttu-id="aadec-125">Это помогает сконцентрироваться на связанных группах.</span><span class="sxs-lookup"><span data-stu-id="aadec-125">This helps you focus on related groups.</span></span>  
  
3.  <span data-ttu-id="aadec-126">Обратите внимание на элемент управления " **Переменная заливки** " в правом верхнем углу окна **Диаграмма кластеров** .</span><span class="sxs-lookup"><span data-stu-id="aadec-126">Notice the **Shading Variable** control in the upper right corner of the **Cluster Diagram** window.</span></span>  
  
     <span data-ttu-id="aadec-127">По умолчанию задано значение **Population**.</span><span class="sxs-lookup"><span data-stu-id="aadec-127">By default, it is set to **Population**.</span></span> <span data-ttu-id="aadec-128">Это означает, что более темные кластеры имеют большую поддержку.</span><span class="sxs-lookup"><span data-stu-id="aadec-128">What this means is that the darker clusters have greater support.</span></span>  
  
4.  <span data-ttu-id="aadec-129">Установите курсор над любым кластером.</span><span class="sxs-lookup"><span data-stu-id="aadec-129">Pause over any cluster with the cursor.</span></span>  
  
     <span data-ttu-id="aadec-130">Отображается всплывающая подсказка, в которой указывается заполнение этого кластера.</span><span class="sxs-lookup"><span data-stu-id="aadec-130">A ToolTip is displayed that contains the population of that cluster.</span></span>  
  
5.  <span data-ttu-id="aadec-131">Теперь щелкните раскрывающийся список **Переменная заливки** и выберите переменную **Age** .</span><span class="sxs-lookup"><span data-stu-id="aadec-131">Now, click the **Shading Variable** dropdown list and choose the **Age** variable.</span></span> <span data-ttu-id="aadec-132">После этого в текстовом поле **состояние** появится список значений.</span><span class="sxs-lookup"><span data-stu-id="aadec-132">As you do so, a list of values appears in the **State** text box.</span></span>  
  
     <span data-ttu-id="aadec-133">Столбец «Возраст», используемый в качестве входных данных для этой модели, содержит непрерывные числовые значения, но для кластеризации алгоритм всегда дискретизирует значения.</span><span class="sxs-lookup"><span data-stu-id="aadec-133">The Age column used as input to this model contains continuous numeric values, but for the purpose of clustering, the algorithm always discretizes numbers.</span></span> <span data-ttu-id="aadec-134">Здесь можно просмотреть ячейки или группы, созданные алгоритмом, например "очень низкий ( \<=27)" and "Very High (> = 63)".</span><span class="sxs-lookup"><span data-stu-id="aadec-134">Here you can see the bins, or groups that the algorithm created, such as "Very Low (\<=27)" and "Very High (>=63)".</span></span>  
  
6.  <span data-ttu-id="aadec-135">В раскрывающихся списках **состояние** выберите **очень высокая** и посмотрите, как изменяется схема.</span><span class="sxs-lookup"><span data-stu-id="aadec-135">From the **State** dropdown lists, select **Very High** and see how the diagram changes.</span></span>  
  
     <span data-ttu-id="aadec-136">Можно изменить переменную заливки, чтобы мгновенно определить кластеры, которые содержат больше клиентов этой возрастной группы, и кластеры, которые содержат очень мало клиентов этой возрастной группы.</span><span class="sxs-lookup"><span data-stu-id="aadec-136">By changing the shading variable, you can see at a glance which clusters contain more of this targeted age group, and which clusters contain very few customers in this age group.</span></span>  
  
     <span data-ttu-id="aadec-137">![Измените параметры диаграммы кластеров, чтобы показывать возраст](media/dm13-cluster-diagramshadebyage.gif "Измените параметры диаграммы кластеров, чтобы показывать возраст")</span><span class="sxs-lookup"><span data-stu-id="aadec-137">![Modify the cluster diagram to show age](media/dm13-cluster-diagramshadebyage.gif "Modify the cluster diagram to show age")</span></span>  
  
     <span data-ttu-id="aadec-138">Чем темнее заливка, тем больше пропорция целевого распределения атрибутов и значений в данном кластере.</span><span class="sxs-lookup"><span data-stu-id="aadec-138">The darker the shading, the larger the proportion of the target attribute and value distribution that cluster.</span></span>  
  
7.  <span data-ttu-id="aadec-139">Выберите кластер с темным затененным, если для **переменной заливки** задано значение Age >65.</span><span class="sxs-lookup"><span data-stu-id="aadec-139">Locate the cluster that is shaded darkest when the **Shading Variable** is set to Age >65.</span></span>  
  
     <span data-ttu-id="aadec-140">Наведите указатель мыши на кластер.</span><span class="sxs-lookup"><span data-stu-id="aadec-140">Hover the mouse over the cluster.</span></span>  
  
     <span data-ttu-id="aadec-141">Значение, отображенное во всплывающей подсказке, теперь указывает число покупателей старше 65 лет в данном кластере.</span><span class="sxs-lookup"><span data-stu-id="aadec-141">The value displayed in the ToolTip now shows you the population of customers in this cluster who are over 65.</span></span>  
  
8.  <span data-ttu-id="aadec-142">Щелкните кластер правой кнопкой мыши и выберите команду **Переименовать кластер**.</span><span class="sxs-lookup"><span data-stu-id="aadec-142">Right-click the cluster and select **Rename Cluster**.</span></span> <span data-ttu-id="aadec-143">Введите новое описательное имя, например, **свыше 65**.</span><span class="sxs-lookup"><span data-stu-id="aadec-143">Type a new name that is descriptive, such as **Over 65**.</span></span> <span data-ttu-id="aadec-144">Новое имя будет сохранено в модели на сервере и может использоваться для определения кластера в других представлениях кластеризации.</span><span class="sxs-lookup"><span data-stu-id="aadec-144">The new name is saved with the model to the server and can be used for identifying the cluster in the other clustering views.</span></span>  
  
 [<span data-ttu-id="aadec-145">К началу</span><span class="sxs-lookup"><span data-stu-id="aadec-145">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-profiles"></a><a name="BKMK_ClusterProfiles"></a> <span data-ttu-id="aadec-146">Профили кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-146">Cluster Profiles</span></span>  
 <span data-ttu-id="aadec-147">Вкладка **Профили кластеров** позволяет быстро сравнить описывающего всех кластеров.</span><span class="sxs-lookup"><span data-stu-id="aadec-147">The **Cluster Profiles** tab lets you compare the makeup of all clusters at a glance.</span></span> <span data-ttu-id="aadec-148">Знакомство с моделью лучше начинать с изучения этого момента.</span><span class="sxs-lookup"><span data-stu-id="aadec-148">This is a good place to start when you are getting familiar with the model.</span></span> <span data-ttu-id="aadec-149">Это представление будет также полезно в будущем, если после изучения определенного кластера потребуется найти связанные с ним кластеры.</span><span class="sxs-lookup"><span data-stu-id="aadec-149">This view is also useful later on, if you have been exploring a particular cluster and decide you need to find related ones.</span></span>  
  
 <span data-ttu-id="aadec-150">**Профили кластеров** также дают хороший обзор того, как кластеры отличаются друг от друга.</span><span class="sxs-lookup"><span data-stu-id="aadec-150">**Cluster Profiles** also gives you a good overview of how the clusters are different from each other.</span></span> <span data-ttu-id="aadec-151">Таким образом, это представление удобно использовать для задания для каждого кластера описательного имени.</span><span class="sxs-lookup"><span data-stu-id="aadec-151">Therefore, you might find it convenient to use this view to give each cluster a descriptive name.</span></span>  
  
##### <a name="explore-the-cluster-profiles"></a><span data-ttu-id="aadec-152">Просмотр профилей кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-152">Explore the cluster profiles</span></span>  
  
1.  <span data-ttu-id="aadec-153">Щелкните ячейку для профессий в столбце **состояния** , чтобы просмотреть список всех значений для профессии.</span><span class="sxs-lookup"><span data-stu-id="aadec-153">Click the cell for Occupations, in the **States** column, to see the list of all values for Occupation.</span></span>  
  
2.  <span data-ttu-id="aadec-154">Теперь поместите курсор над «Род занятий» в профилях кластеров.</span><span class="sxs-lookup"><span data-stu-id="aadec-154">Now move the cursor over Occupation in the cluster profiles.</span></span>  
  
     <span data-ttu-id="aadec-155">Во всплывающей подсказке отобразится распределение рода занятий в этом кластере.</span><span class="sxs-lookup"><span data-stu-id="aadec-155">The ToolTip shows the distribution of occupations in that cluster.</span></span>  
  
     <span data-ttu-id="aadec-156">![Просмотр подробностей в подсказках или условных обозначениях](media/dm13-cluster-profile-age-tooltip.gif "Просмотр подробностей в подсказках или условных обозначениях")</span><span class="sxs-lookup"><span data-stu-id="aadec-156">![View detailed values in Tooltips or in Legend](media/dm13-cluster-profile-age-tooltip.gif "View detailed values in Tooltips or in Legend")</span></span>  
  
     <span data-ttu-id="aadec-157">Обратите внимание, что в некоторых кластерах (например, на рисунке) список профессий не завершен, а некоторые профессии заменяются меткой, **другой**.</span><span class="sxs-lookup"><span data-stu-id="aadec-157">Notice that, in some clusters (such as the one in the graphic), the list of occupations is not complete, and some occupations are replaced with the label, **Other**.</span></span>  
  
     <span data-ttu-id="aadec-158">Это сделано намеренно, так как иногда сложно определить различие между множеством малых панелей в гистограмме.</span><span class="sxs-lookup"><span data-stu-id="aadec-158">This is by design, because it can be hard to tell the difference between many small bars in a histogram.</span></span> <span data-ttu-id="aadec-159">По умолчанию сохраняются только столбцы с наивысшей важностью, а оставшиеся строки группируются в серый **другой** контейнер.</span><span class="sxs-lookup"><span data-stu-id="aadec-159">By default only the bars of highest importance are retained, and the remaining bars are grouped together into a gray **Other** bucket.</span></span>  
  
     <span data-ttu-id="aadec-160">Чтобы изменить число столбцов, отображаемых в любой гистограмме, используйте параметр **гистограммы**.</span><span class="sxs-lookup"><span data-stu-id="aadec-160">To change the number of bars that are visible in any histogram, use the option **Histogram bars**.</span></span>  
  
3.  <span data-ttu-id="aadec-161">Обратите внимание, что столбец **Age** отличается от других.</span><span class="sxs-lookup"><span data-stu-id="aadec-161">Note that the **Age** column looks different from the others.</span></span> <span data-ttu-id="aadec-162">Щелкните ромб на диаграмме, которая используется для представления возраста.</span><span class="sxs-lookup"><span data-stu-id="aadec-162">Click the diamond in the chart used to represent Age.</span></span>  
  
     <span data-ttu-id="aadec-163">Столбец «Возраст» первоначально содержал только непрерывные числа.</span><span class="sxs-lookup"><span data-stu-id="aadec-163">The column Age originally contained only continuous numbers.</span></span> <span data-ttu-id="aadec-164">Для алгоритма кластеризации требуются дискретные значения, поэтому он группирует числовые значения в столбце «Возраст» в ограниченное число возрастных группы на основе распределения значений.</span><span class="sxs-lookup"><span data-stu-id="aadec-164">The clustering algorithm requires discrete values, so it grouped the numeric values in the Age column into a limited number of age groups, based on the distribution of values.</span></span>  
  
4.  <span data-ttu-id="aadec-165">Щелкните одну из ромбовидных диаграмм в профиле кластера.</span><span class="sxs-lookup"><span data-stu-id="aadec-165">Click one of the diamond charts in a cluster profile.</span></span>  
  
     <span data-ttu-id="aadec-166">Эти ромбовидные диаграммы отображаются только в том случае, если в исходных данных используются непрерывные числовые значения.</span><span class="sxs-lookup"><span data-stu-id="aadec-166">These diamond charts are displayed only when the source data uses continuous numeric values.</span></span> <span data-ttu-id="aadec-167">Ромбовидные диаграммы обеспечивают определенные полезные описательные статистические данные, включая среднее и стандартное отклонение для этого значения в каждом кластере.</span><span class="sxs-lookup"><span data-stu-id="aadec-167">The diamond charts provide some useful descriptive statistics, including the mean and standard deviation for that value in each cluster:</span></span>  
  
    -   <span data-ttu-id="aadec-168">Линия на ромбовидной диаграмме представляет диапазон значений для атрибута.</span><span class="sxs-lookup"><span data-stu-id="aadec-168">The line in the diamond chart represents the range of values for the attribute.</span></span> <span data-ttu-id="aadec-169">Значения также отображаются в столбце **состояния** слева от диаграммы **Профили** .</span><span class="sxs-lookup"><span data-stu-id="aadec-169">The values are also shown in the **States** column at the left of the **Profiles** chart.</span></span>  
  
    -   <span data-ttu-id="aadec-170">Центр ромба расположен над средним значением для узла.</span><span class="sxs-lookup"><span data-stu-id="aadec-170">The center of the diamond is positioned at the mean for the node.</span></span>  
  
    -   <span data-ttu-id="aadec-171">Ширина ромба представляет дисперсию атрибута в этом узле.</span><span class="sxs-lookup"><span data-stu-id="aadec-171">The width of the diamond represents the variance of the attribute at that node.</span></span> <span data-ttu-id="aadec-172">Следовательно, более узкий ромб указывает, что узел способен создавать более точный прогноз.</span><span class="sxs-lookup"><span data-stu-id="aadec-172">Therefore, a thinner diamond indicates that the node can create a more accurate prediction.</span></span>  
  
5.  <span data-ttu-id="aadec-173">Чтобы освободить место в графе, щелкните правой кнопкой мыши кластер, который не нужно просматривать сразу, и выберите пункт **Скрыть столбец**.</span><span class="sxs-lookup"><span data-stu-id="aadec-173">To make more room in the graph, right-click a cluster you don't need to view right away, and select **Hide Column**.</span></span> <span data-ttu-id="aadec-174">Это не удаляется из модели, просто сворачивает столбец временно.</span><span class="sxs-lookup"><span data-stu-id="aadec-174">This doesn't delete it from the model, just collapses the column temporarily.</span></span>  
  
     <span data-ttu-id="aadec-175">Чтобы просмотреть скрытые кластеры, можно щелкнуть и перетащить границу столбца или выбрать имя кластера из списка, **большее число кластеров**.</span><span class="sxs-lookup"><span data-stu-id="aadec-175">To view clusters that you've hidden, you can click and drag the column edge, or select the cluster name from the list, **More clusters**.</span></span>  
  
6.  <span data-ttu-id="aadec-176">С помощью прокрутки перейдите в списке к пункту «Покупатель велосипеда», а затем найдите кластер, у которого самый высокий процент значений «Да».</span><span class="sxs-lookup"><span data-stu-id="aadec-176">Scroll down the attribute list till you find Bike Buyer, and then find the cluster that has the highest percentage of Yes values.</span></span>  
  
     <span data-ttu-id="aadec-177">Щелкните правой кнопкой мыши заголовок столбца кластера, который требуется переименовать, выберите команду **Переименовать кластер**и введите **Bike**buyers.</span><span class="sxs-lookup"><span data-stu-id="aadec-177">Right-click the column heading for the cluster that you want to rename, select **Rename cluster**, and type **Bike Buyers**.</span></span>  
  
     <span data-ttu-id="aadec-178">Новое имя кластера сохраняется во всех представлениях и на сервере до повторной обработки модели.</span><span class="sxs-lookup"><span data-stu-id="aadec-178">The new cluster name is persisted in all views, and on the server, until you reprocess the model.</span></span>  
  
     <span data-ttu-id="aadec-179">![Переименование кластеров для более удобного использования диаграммы](media/dm13-cluster-rename.gif "Переименование кластеров для более удобного использования диаграммы")</span><span class="sxs-lookup"><span data-stu-id="aadec-179">![Rename clusters to make chart easier to use](media/dm13-cluster-rename.gif "Rename clusters to make chart easier to use")</span></span>  
  
 <span data-ttu-id="aadec-180">**Советы**</span><span class="sxs-lookup"><span data-stu-id="aadec-180">**Tips**</span></span>  
  
-   <span data-ttu-id="aadec-181">Щелкните заголовок столбца для сортировки атрибутов по важности для этого кластера.</span><span class="sxs-lookup"><span data-stu-id="aadec-181">Click a column heading to sort the attributes in order of importance for that cluster.</span></span>  
  
-   <span data-ttu-id="aadec-182">Изменить порядок столбцов в средстве просмотра также можно путем перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="aadec-182">Drag columns to reorder them in the viewer.</span></span>  
  
-   <span data-ttu-id="aadec-183">Щелкните любую ячейку на диаграмме профили, чтобы просмотреть подробные статистические данные в условных обозначениях **интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="aadec-183">Click any cell in the profiles chart to view detailed statistics in the **Mining Legend**.</span></span>  
  
-   <span data-ttu-id="aadec-184">Щелкните правой кнопкой мыши любую ячейку и выберите **столбцы модели детализации** , чтобы вывести базовые данные на новый лист в Excel.</span><span class="sxs-lookup"><span data-stu-id="aadec-184">Right-click any cell and select **Drillthrough model columns** to output the underlying data to a new worksheet in Excel.</span></span>  
  
-   <span data-ttu-id="aadec-185">Щелкните правой кнопкой мыши заголовок столбца кластера и выберите **детализация для структурирования данных** , чтобы получить подробные сведения о членах кластера, которые не были добавлены в модель.</span><span class="sxs-lookup"><span data-stu-id="aadec-185">Right-click the cluster's column heading and select **Drillthrough to structure data** to get detailed information about the cluster members that wasn't included in the model.</span></span>  
  
     <span data-ttu-id="aadec-186">Например, при профилировании клиентов вы можете оставить контактные данные в базовых данных (структуре интеллектуального анализа), но не включать их в модель, поскольку это не полезно для анализа.</span><span class="sxs-lookup"><span data-stu-id="aadec-186">For example, if you are profiling customers, you might leave the contact information in the underlying data (the mining structure) but not include it in the model, because it's not useful for analysis.</span></span> <span data-ttu-id="aadec-187">Однако после назначения клиентов кластерам можно просмотреть подробные данные с помощью детализации.</span><span class="sxs-lookup"><span data-stu-id="aadec-187">However, after customers have been assigned to clusters, you can view the detailed data by using drillthrough.</span></span>  
  
 [<span data-ttu-id="aadec-188">К началу</span><span class="sxs-lookup"><span data-stu-id="aadec-188">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-characteristics"></a><a name="BKMK_ClusterCharacteristics"></a> <span data-ttu-id="aadec-189">Характеристики кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-189">Cluster Characteristics</span></span>  
 <span data-ttu-id="aadec-190">Представление «Характеристики кластеров» позволяет исследовать один кластер, чтобы найти атрибуты, которые являются основными характеристиками этой группы данных.</span><span class="sxs-lookup"><span data-stu-id="aadec-190">The Cluster Characteristics view lets you really explore a single cluster, to find which attributes most strongly characterize this group of data.</span></span>  
  
##### <a name="explore-the-cluster-characteristics"></a><span data-ttu-id="aadec-191">Анализ характеристик кластера</span><span class="sxs-lookup"><span data-stu-id="aadec-191">Explore the cluster characteristics</span></span>  
  
1.  <span data-ttu-id="aadec-192">Выберите кластер **более 65** из списка **кластеров** .</span><span class="sxs-lookup"><span data-stu-id="aadec-192">Select the **Over 65** cluster from the **Cluster** list.</span></span>  
  
     <span data-ttu-id="aadec-193">После выбора кластера можно просмотреть характеристики, из которых он состоит.</span><span class="sxs-lookup"><span data-stu-id="aadec-193">After you select a cluster, you can see in detail the characteristics that make up that specific cluster.</span></span>  
  
     <span data-ttu-id="aadec-194">Атрибуты, которые содержит кластер, перечислены в столбцах **Переменные** , а их состояние — в столбце **Значения** .</span><span class="sxs-lookup"><span data-stu-id="aadec-194">The attributes that the cluster contains are listed in the **Variables** columns, and the state of the listed attribute is listed in the **Values** column.</span></span>  
  
     <span data-ttu-id="aadec-195">Состояния атрибутов перечислены в порядке важности, которые сопровождаются их вероятностью в этом кластере, представленной в виде цветовой линии в столбце **вероятность** .</span><span class="sxs-lookup"><span data-stu-id="aadec-195">Attribute states are listed in order of importance, accompanied by their probability in this cluster, represented as a colored bar in the **Probability** column.</span></span>  
  
     <span data-ttu-id="aadec-196">![Характеристики модели кластеризации](media/dm13-cluster-characteristics.gif "Характеристики модели кластеризации")</span><span class="sxs-lookup"><span data-stu-id="aadec-196">![Characteristics of a clustering model](media/dm13-cluster-characteristics.gif "Characteristics of a clustering model")</span></span>  
  
2.  <span data-ttu-id="aadec-197">Щелкните столбец **переменные** , чтобы выполнить сортировку по атрибуту.</span><span class="sxs-lookup"><span data-stu-id="aadec-197">Click the **Variables** column to sort by attribute.</span></span>  
  
     <span data-ttu-id="aadec-198">Можно изменить переменную сортировки, чтобы лучше понять, как значения для таких переменных, как «доход» или «владение автомобилем» распределяются в группе.</span><span class="sxs-lookup"><span data-stu-id="aadec-198">By changing the sort variable, you can more easily see how values for variables such as income or car ownership are distributed in the group.</span></span>  
  
3.  <span data-ttu-id="aadec-199">Нажмите кнопку **Копировать в Excel**.</span><span class="sxs-lookup"><span data-stu-id="aadec-199">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="aadec-200">Новый лист добавляется в книгу, содержащую характеристики выбранного кластера.</span><span class="sxs-lookup"><span data-stu-id="aadec-200">A new worksheet is added to your workbook that contains the characteristics of the selected cluster.</span></span>  
  
4.  <span data-ttu-id="aadec-201">Теперь выберите другой кластер из списка, **покупателей велосипедов**.</span><span class="sxs-lookup"><span data-stu-id="aadec-201">Now choose a different cluster from the list, **Bike Buyers**.</span></span>  
  
5.  <span data-ttu-id="aadec-202">Нажмите кнопку **Копировать в Excel**.</span><span class="sxs-lookup"><span data-stu-id="aadec-202">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="aadec-203">Обратите внимание, что новая диаграмма характеристик кластера добавлена в отдельный лист.</span><span class="sxs-lookup"><span data-stu-id="aadec-203">Note that the new cluster characteristics chart is added on its own worksheet.</span></span> <span data-ttu-id="aadec-204">Его можно переместить на тот же лист, что и другой профиль, чтобы упростить его сравнение, что можно сделать на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="aadec-204">You can move it onto the same worksheet as the other profile to make it easier to compare them, which you'll do in the next step.</span></span>  
  
 <span data-ttu-id="aadec-205">**Советы**</span><span class="sxs-lookup"><span data-stu-id="aadec-205">**Tips**</span></span>  
  
-   <span data-ttu-id="aadec-206">Обратите внимание, что основная характеристика клиента в кластере свыше 65 заключается в том, что они не приобретают ваш продукт.</span><span class="sxs-lookup"><span data-stu-id="aadec-206">Note that the primary characteristic of the customer in the Over 65 cluster is that they don't buy your product!</span></span> <span data-ttu-id="aadec-207">Если необходимо выяснить причину этого, можно просмотреть кластеры и сравнить группы или можно создать связанную модель с помощью алгоритма, который используется при анализе причин и результатов, например модель дерева решений или модель упрощенного алгоритма Байеса.</span><span class="sxs-lookup"><span data-stu-id="aadec-207">If you want to know why this is so, you can browse clusters and compare groups, or you might create a related model using an algorithm that is good at exploring causes and outcomes, such as a decision tree model or a Naïve Bayes model.</span></span>  
  
-   <span data-ttu-id="aadec-208">Если необходимо получить полный список атрибутов и вероятностей для данного кластера (или всех кластеров) можно создать запрос.</span><span class="sxs-lookup"><span data-stu-id="aadec-208">If you want to get a complete list of attributes and probabilities for this cluster (or all clusters) you can create a query.</span></span> <span data-ttu-id="aadec-209">Примеры запросов к моделям кластеризации см. в разделе [примеры запросов к модели кластеризации](data-mining/clustering-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="aadec-209">For examples of queries on clustering models, see [Clustering Model Query Examples](data-mining/clustering-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="aadec-210">К началу</span><span class="sxs-lookup"><span data-stu-id="aadec-210">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-discrimination"></a><a name="BKMK_ClusterDiscrimination"></a><span data-ttu-id="aadec-211">Сравнение кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-211">Cluster Discrimination</span></span>  
 <span data-ttu-id="aadec-212">Вкладка **сравнения кластеров** используется для сравнения атрибутов между двумя кластерами или между кластером и другими вариантами в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="aadec-212">You use the **Cluster Discrimination** tab to compare attributes between two clusters, or between a cluster and all the other cases in the data set.</span></span>  
  
 <span data-ttu-id="aadec-213">Чтобы выделить возможности этого средства просмотра, мы будем сравнивать его с параллельными таблицами в Excel, созданными на основе представления **характеристик кластера** .</span><span class="sxs-lookup"><span data-stu-id="aadec-213">To highlight the features of this viewer, we'll compare it to the side-by-side tables in Excel that you created based on the **Cluster Characteristics** view.</span></span>  
  
##### <a name="explore-cluster-discrimination"></a><span data-ttu-id="aadec-214">Анализ сравнения кластеров</span><span class="sxs-lookup"><span data-stu-id="aadec-214">Explore cluster discrimination</span></span>  
  
1.  <span data-ttu-id="aadec-215">Используйте списки **Кластер 1** и **Кластер 2** , чтобы выбрать кластеры для сравнения.</span><span class="sxs-lookup"><span data-stu-id="aadec-215">Use the **Cluster 1** and **Cluster 2** lists to select the clusters to compare.</span></span>  
  
    -   <span data-ttu-id="aadec-216">Для кластера 1 выберите «Старше 65 лет».</span><span class="sxs-lookup"><span data-stu-id="aadec-216">For Cluster 1, select Over 65.</span></span>  
  
    -   <span data-ttu-id="aadec-217">Для кластера 2 выберите «Покупатели велосипедов».</span><span class="sxs-lookup"><span data-stu-id="aadec-217">For Cluster 2, select Bike Buyers.</span></span>  
  
     <span data-ttu-id="aadec-218">Сравнение должно быть схожим со следующим графиком.</span><span class="sxs-lookup"><span data-stu-id="aadec-218">The comparison should look similar to the following graphic.</span></span>  
  
     <span data-ttu-id="aadec-219">![сравнение кластеров в модели](media/dm13-cluster-compareclusters.gif "сравнение кластеров в модели")</span><span class="sxs-lookup"><span data-stu-id="aadec-219">![comparing clusters in a model](media/dm13-cluster-compareclusters.gif "comparing clusters in a model")</span></span>  
  
     <span data-ttu-id="aadec-220">Обратите внимание, что на самом деле средство просмотра **сравнения кластеров** отправляет сложные запросы на сервер интеллектуального анализа данных, чтобы извлечь наиболее важные атрибуты для различения двух групп, что упрощает сравнение двух наборов клиентов.</span><span class="sxs-lookup"><span data-stu-id="aadec-220">Note that, under the covers, the **Cluster Discrimination** viewer sends complex queries to the data mining server, to extract the attributes that are most important in distinguishing between the two groups, making it easier to compare two sets of customers.</span></span>  
  
2.  <span data-ttu-id="aadec-221">Щелкните любой из столбцов. **..** .</span><span class="sxs-lookup"><span data-stu-id="aadec-221">Click either of the **Favors...** columns.</span></span>  
  
     <span data-ttu-id="aadec-222">Полоса справа от атрибута и список значений указывают наиболее важные функции или значения как характеристику выбранного кластера.</span><span class="sxs-lookup"><span data-stu-id="aadec-222">The bar to the right of the attribute and value list shows which features or values are most important as a characteristic of the selected cluster.</span></span>  
  
3.  <span data-ttu-id="aadec-223">Теперь сравним списки в Excel.</span><span class="sxs-lookup"><span data-stu-id="aadec-223">Now compare the lists in Excel.</span></span>  
  
     <span data-ttu-id="aadec-224">![Диаграмма сети зависимостей для модели взаимосвязей](media/dm13-comparing-profiles-in-excel.gif "Диаграмма сети зависимостей для модели взаимосвязей")</span><span class="sxs-lookup"><span data-stu-id="aadec-224">![Dependency network graph for an association model](media/dm13-comparing-profiles-in-excel.gif "Dependency network graph for an association model")</span></span>  
  
     <span data-ttu-id="aadec-225">Поскольку базовые статистические данные, которые были использованы для создания изображения в средстве просмотра, сохраняются в Excel как таблицы, можно фильтровать, сортировать и просматривать фактические значения вероятности.</span><span class="sxs-lookup"><span data-stu-id="aadec-225">Because the underlying statistics that were used to build the image in the viewer are saved to Excel as tables, you can filter and sort, and view the actual probability values.</span></span>  
  
     <span data-ttu-id="aadec-226">Помимо использования Excel, рекомендуется использовать средство просмотра кластеров для Visio, которое позволяет не только просматривать точки данных, но и вносить изменения и усовершенствовать диаграмму.</span><span class="sxs-lookup"><span data-stu-id="aadec-226">In addition to using Excel, we recommend that you try the cluster viewer for Visio, which also allows you to not just view data points but also extensively modify and enhance the graph.</span></span> <span data-ttu-id="aadec-227">Дополнительные сведения см. в разделе [Пошаговое руководство по кластерной диаграмме &#40;&#41;надстроек интеллектуального анализа данных ](cluster-diagram-walkthrough-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="aadec-227">For more information, see [Cluster Diagram Walkthrough &#40;Data Mining Add-ins&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span></span>  
  
 <span data-ttu-id="aadec-228">**Советы**</span><span class="sxs-lookup"><span data-stu-id="aadec-228">**Tips**</span></span>  
  
 <span data-ttu-id="aadec-229">После получения подробных сведений о группах клиентов попробуйте использовать [сценарий "что если" &#40;"средства анализа таблиц для excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) " или " [поиск решения" &#40;средств анализа таблиц для Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) Tools, чтобы исследовать факторы в модели, которые можно изменить, чтобы повлиять на результат.</span><span class="sxs-lookup"><span data-stu-id="aadec-229">After getting some insights into groups of customers, try using the [What-If Scenario &#40;Table Analysis Tools for Excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) or [Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) tools, to explore factors in the model that might be changed to affect the outcome.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aadec-230">См. также:</span><span class="sxs-lookup"><span data-stu-id="aadec-230">See Also</span></span>  
 <span data-ttu-id="aadec-231">[Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="aadec-231">[Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="aadec-232">Мастер кластеров &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="aadec-232">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
  
