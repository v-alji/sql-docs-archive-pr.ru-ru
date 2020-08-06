---
title: Просмотр модели дерева принятия решений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- tree viewer
- mining model, decision tree
- decision tree [data mining]
- dependency network
ms.assetid: 6b3dd1ae-caff-41c3-817b-802dc020ff88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 809d2e494cfa7a6c4078acf95c2c70a0e68c188d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656830"
---
# <a name="browsing-a-decision-trees-model"></a><span data-ttu-id="88f49-102">Просмотр модели дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="88f49-102">Browsing a Decision Trees Model</span></span>
  <span data-ttu-id="88f49-103">При открытии модели классификации с помощью **кнопки Обзор**модель отображается в интерактивном средстве просмотра деревьев решений, подобно [!INCLUDE[msCoName](../includes/msconame-md.md)] средству просмотра деревьев решений в среде [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88f49-103">When you open a classification model using **Browse**, the model is displayed in an interactive decision tree viewer, similar to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="88f49-104">В средстве просмотра отображаются результаты классификации в виде диаграммы, разработанной для выделения условий, которые отличают одну группу данных от другой.</span><span class="sxs-lookup"><span data-stu-id="88f49-104">The viewer displays the results of classification as a graph that is designed to highlight the criteria that differentiate one group of data from another.</span></span> <span data-ttu-id="88f49-105">Также можно выполнить детализацию до отдельных подмножеств дерева и получить базовые данные.</span><span class="sxs-lookup"><span data-stu-id="88f49-105">You can also drill down into individual subsets of the tree and retrieve the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="88f49-106">Изучение модели</span><span class="sxs-lookup"><span data-stu-id="88f49-106">Explore the Model</span></span>  
 <span data-ttu-id="88f49-107">Модели на основе алгоритма деревьев решений содержат много полезных сведений, которые рекомендуется изучить.</span><span class="sxs-lookup"><span data-stu-id="88f49-107">Models based on the Decision Trees algorithm have lots of interesting information to explore.</span></span> <span data-ttu-id="88f49-108">Окно **Обзор** содержит следующие вкладки и панели, которые помогут узнать закономерности и прогнозировать результаты с помощью графа:</span><span class="sxs-lookup"><span data-stu-id="88f49-108">The **Browse** window includes the following tabs and panes to help you learn the patterns and predict outcomes using the graph:</span></span>  
  
-   [<span data-ttu-id="88f49-109">Дерево принятия решений</span><span class="sxs-lookup"><span data-stu-id="88f49-109">Decision Tree</span></span>](#BKMK_DecisionTree)  
  
-   [<span data-ttu-id="88f49-110">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="88f49-110">Dependency Network</span></span>](#BKMK_DNetwork)  
  
 <span data-ttu-id="88f49-111">Для экспериментов с моделью дерева решений можно использовать образцы данных на вкладке «Обучающие данные» (или «Исходные данные») книги с образцами данных и построить модель дерева решений, использовав «Покупатель велосипеда» в качестве прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="88f49-111">To experiment with a decision trees model, you can use the sample data on the Training Data (or Source Data) tab of the sample data workbook, and build a decision tree model using Bike Buyer as the predictable attribute.</span></span>  
  
###  <a name="decision-tree"></a><a name="BKMK_DecisionTree"></a><span data-ttu-id="88f49-112">Дерево принятия решений</span><span class="sxs-lookup"><span data-stu-id="88f49-112">Decision Tree</span></span>  
 <span data-ttu-id="88f49-113">Это представление может помочь в понимании и исследовании факторов, которые привели к получению результата.</span><span class="sxs-lookup"><span data-stu-id="88f49-113">This view is intended to help you understand and explore the factors that lead to an outcome.</span></span>  
  
 <span data-ttu-id="88f49-114">Диаграмму дерева решений можно читать слева направо следующим образом.</span><span class="sxs-lookup"><span data-stu-id="88f49-114">The decision tree graph can be read from left to right as follows:</span></span>  
  
-   <span data-ttu-id="88f49-115">Прямоугольники, которые называются *узлами*, содержат подмножества данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-115">The rectangles, which are referred to as *nodes*, contain subsets of the data.</span></span> <span data-ttu-id="88f49-116">Метка на узле указывает определяющие характеристики этого подмножества.</span><span class="sxs-lookup"><span data-stu-id="88f49-116">The label on the node tells you the defining characteristics of that subset.</span></span>  
  
-   <span data-ttu-id="88f49-117">Самый левый узел с меткой **ALL**представляет полный набор данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-117">The leftmost node, labeled **All**, represents the complete data set.</span></span> <span data-ttu-id="88f49-118">Все последующие узлы представляют подмножества данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-118">All subsequent nodes represent subsets of the data.</span></span>  
  
-   <span data-ttu-id="88f49-119">Дерево принятия решений содержит много *разделений*или мест, где данные расходятся на несколько наборов на основе атрибутов.</span><span class="sxs-lookup"><span data-stu-id="88f49-119">A decision tree contains many *splits*, or places where the data diverges into multiple sets based on attributes.</span></span>  
  
     <span data-ttu-id="88f49-120">Например, в образце первое разбиение модели разделяет набор данных на три группы по возрасту.</span><span class="sxs-lookup"><span data-stu-id="88f49-120">For example, the first split in the sample model divides the dataset into three groups by age.</span></span>  
  
-   <span data-ttu-id="88f49-121">Раздел, расположенный сразу после узла **все** , наиболее важен, так как он показывает основное условие, которое делит этот набор данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-121">The split immediately after the **All** node is most important because it shows the primary condition that divides this dataset.</span></span>  
  
     <span data-ttu-id="88f49-122">Дополнительные разбиения расположены справа.</span><span class="sxs-lookup"><span data-stu-id="88f49-122">Additional splits occur to the right.</span></span> <span data-ttu-id="88f49-123">Таким образом, путем анализа различных фрагментов дерева можно определить атрибуты, оказывающие наибольшее влияние на оценку возможности приобретения.</span><span class="sxs-lookup"><span data-stu-id="88f49-123">Thus, by analyzing different segments of the tree, you can learn which attributes had the most influence on purchasing behavior.</span></span>  
  
 <span data-ttu-id="88f49-124">![Диаграмма сети зависимостей для модели взаимосвязей](media/dm13-dec-tree-split-definition.gif "Диаграмма сети зависимостей для модели взаимосвязей")</span><span class="sxs-lookup"><span data-stu-id="88f49-124">![Dependency network graph for an association model](media/dm13-dec-tree-split-definition.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="88f49-125">Используя эти сведения, можно сосредоточить маркетинговую кампанию на клиентах, которым просто необходимо поощрение для совершения покупки.</span><span class="sxs-lookup"><span data-stu-id="88f49-125">Using this information, you might focus a marketing campaign on customers that might simply need encouragement to make a purchase.</span></span>  
  
##### <a name="explore-the-decision-tree"></a><span data-ttu-id="88f49-126">Просмотр дерева решений</span><span class="sxs-lookup"><span data-stu-id="88f49-126">Explore the decision tree</span></span>  
  
1.  <span data-ttu-id="88f49-127">Щелкните узел **все** и просмотрите **обозначения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="88f49-127">Click the **All** node, and look at the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="88f49-128">Они указывают точное число вариантов в наборе данных для обучения, а также распределение выходных данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-128">It displays the exact count of cases in the training data set, as well as a breakdown of the outcomes.</span></span>  
  
     <span data-ttu-id="88f49-129">Эти сведения можно просмотреть в подсказке при наведении указателя мыши на узел.</span><span class="sxs-lookup"><span data-stu-id="88f49-129">You can view the same information in a tooltip if you pause the mouse over a node.</span></span>  
  
2.  <span data-ttu-id="88f49-130">Щелкните знак «плюс» и «минус» рядом с каждым узлом, чтобы развернуть или свернуть дерево.</span><span class="sxs-lookup"><span data-stu-id="88f49-130">Click the plus and minus signs next to each node to expand or collapse the tree.</span></span>  
  
     <span data-ttu-id="88f49-131">Можно также использовать ползунок « **Показывать уровень** », чтобы развернуть или свернуть дерево.</span><span class="sxs-lookup"><span data-stu-id="88f49-131">You can also use the **Show Level** slider to expand or shrink the tree.</span></span>  
  
3.  <span data-ttu-id="88f49-132">Обратите внимание на то, что некоторые узлы темнее, чем другие.</span><span class="sxs-lookup"><span data-stu-id="88f49-132">Notice that some nodes are darker than others?</span></span>  
  
     <span data-ttu-id="88f49-133">По умолчанию **Заполнение** используется в качестве переменной заливки, что означает, что интенсивность цвета показывает, какие узлы имеют наибольшую поддержку.</span><span class="sxs-lookup"><span data-stu-id="88f49-133">By default, **Population** is used as the shading variable, which means that the intensity of the color shows you which nodes have the most support.</span></span>  
  
     <span data-ttu-id="88f49-134">Поэтому крайний левый узел является наиболее темным, поскольку он содержит весь набор данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-134">Therefore the leftmost node is darkest, because it contains the entire dataset.</span></span>  
  
4.  <span data-ttu-id="88f49-135">Измените значение параметра **фон** со **всех вариантов** на **Да**.</span><span class="sxs-lookup"><span data-stu-id="88f49-135">Change the value for **Background** from **All Cases** to **Yes**.</span></span>  
  
     <span data-ttu-id="88f49-136">![Изменение графа дерева принятия решений для выделения покупателей](media/dm13-dectreeshadedbuyer.gif "Изменение графа дерева принятия решений для выделения покупателей")</span><span class="sxs-lookup"><span data-stu-id="88f49-136">![changing decision tree graph to highlight buyers](media/dm13-dectreeshadedbuyer.gif "changing decision tree graph to highlight buyers")</span></span>  
  
5.  <span data-ttu-id="88f49-137">Теперь насыщенность цвета показывает, сколько клиентов в каждом узле купили велосипед, т.е. интересующий нас показатель.</span><span class="sxs-lookup"><span data-stu-id="88f49-137">Now the intensity of the color tells you how many customers in each node purchased a bike, which is the behavior you are interested in.</span></span>  
  
     <span data-ttu-id="88f49-138">Обратите внимание на цветные линии в каждом узле.</span><span class="sxs-lookup"><span data-stu-id="88f49-138">Notice the colored bars within each node.</span></span> <span data-ttu-id="88f49-139">Это гистограмма, показывающая распределение выходных данных в этом подмножество данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-139">This is a histogram that shows the distribution of outcomes within this subset of data.</span></span> <span data-ttu-id="88f49-140">Например, в образце дерева принятия решений о покупателях велосипедов цветная строка показывает долю клиентов, которые купили велосипеды (значения Да), а также тех, кто не имеет значений.</span><span class="sxs-lookup"><span data-stu-id="88f49-140">For example, in the sample Bike Buyer decision tree, the colored bar shows the proportion of customers who bought bikes (Yes values) vs. those who did not (No values).</span></span> <span data-ttu-id="88f49-141">Чтобы получить точные значения, можно щелкнуть узел и просмотреть **обозначения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="88f49-141">To get the exact values, you can click the node and view the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="88f49-142">Проанализировав диаграмму, можно определить, как каждое подмножество данных разделено на более мелкие группы и какие атрибуты наиболее полезны при прогнозировании результата.</span><span class="sxs-lookup"><span data-stu-id="88f49-142">By following the graph, you can see how each subset of data is further decomposed into smaller groups, and which attributes are most useful in predicting an outcome.</span></span>  
  
     <span data-ttu-id="88f49-143">Интенсивность заливки позволяет сосредоточиться на нескольких наиболее важных группах и получить более подробные данные о них для выполнения сравнения.</span><span class="sxs-lookup"><span data-stu-id="88f49-143">Just by looking at the intensity of the shading, you can focus on a couple groups of interest, and get more detailed data on them for comparison.</span></span> <span data-ttu-id="88f49-144">Например, эти группы имеют очень высокую вероятность покупки велосипедов:</span><span class="sxs-lookup"><span data-stu-id="88f49-144">For example, these groups have a fairly high probability of buying bikes:</span></span>  
  
    -   <span data-ttu-id="88f49-145">Age >= 32 и \< 53 and Yearly Income > = 26000, а потомки = 0</span><span class="sxs-lookup"><span data-stu-id="88f49-145">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children = 0</span></span>  
  
         <span data-ttu-id="88f49-146">Всего вариантов: 1150</span><span class="sxs-lookup"><span data-stu-id="88f49-146">Total cases: 1150</span></span>  
  
         <span data-ttu-id="88f49-147">Вероятность закупщика велосипеда: 18%</span><span class="sxs-lookup"><span data-stu-id="88f49-147">Bike buyer probability: 18%</span></span>  
  
    -   <span data-ttu-id="88f49-148">Age >= 32 и \< 53 and Yearly Income > = 26000, а Children не = 0 и семейное состояние = ' Single '</span><span class="sxs-lookup"><span data-stu-id="88f49-148">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children not = 0 and Marital Status = 'Single'</span></span>  
  
         <span data-ttu-id="88f49-149">Всего вариантов: 402</span><span class="sxs-lookup"><span data-stu-id="88f49-149">Total cases: 402</span></span>  
  
         <span data-ttu-id="88f49-150">Вероятность закупщика велосипеда: 16%</span><span class="sxs-lookup"><span data-stu-id="88f49-150">Bike buyer probability: 16%</span></span>  
  
7.  <span data-ttu-id="88f49-151">Измените значение параметра **фон** с **Да** на **нет** и посмотрите на изменение графа.</span><span class="sxs-lookup"><span data-stu-id="88f49-151">Change the value for **Background** from **Yes** to **No** and see how the graph changes.</span></span>  
  
     <span data-ttu-id="88f49-152">![Диаграмма сети зависимостей для модели взаимосвязей](media/dm13-dec-tree-background-no.gif "Диаграмма сети зависимостей для модели взаимосвязей")</span><span class="sxs-lookup"><span data-stu-id="88f49-152">![Dependency network graph for an association model](media/dm13-dec-tree-background-no.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="88f49-153">**Советы**</span><span class="sxs-lookup"><span data-stu-id="88f49-153">**Tips**</span></span>  
  
-   <span data-ttu-id="88f49-154">Если данные можно разделить на несколько рядов, другая модель создается для каждого набора данных, подлежащего моделированию.</span><span class="sxs-lookup"><span data-stu-id="88f49-154">If your data can be divided into multiple series, a different model is built for each set of data that you want to model.</span></span>  
  
-   <span data-ttu-id="88f49-155">В образце модели данных имеется только один прогнозируемый результат — Покупатель велосипеда, но предположим, что у клиента есть информация о том, приобрел ли клиент план обслуживания и хотели бы предсказать его.</span><span class="sxs-lookup"><span data-stu-id="88f49-155">In the sample data model, there is only one predictable outcome - Bike Buyer - but suppose you had information about whether the customer purchased a service plan and wanted to predict that as well.</span></span> <span data-ttu-id="88f49-156">В таком случае эти данные будут указаны в отдельном столбце и в модель будут включены два прогнозируемых атрибута.</span><span class="sxs-lookup"><span data-stu-id="88f49-156">In that case you would have that data in a separate column, and include two predictable attributes in the model.</span></span>  
  
     <span data-ttu-id="88f49-157">Щелкните параметр **гистограмма** в левом верхнем углу панели дерева принятия решений, чтобы изменить максимальное число состояний, которые могут отображаться в гистограммах дерева.</span><span class="sxs-lookup"><span data-stu-id="88f49-157">Click the **Histogram** option, in the upper left corner of the Decision Tree pane, to change the maximum number of states that can appear in the histograms in the tree.</span></span> <span data-ttu-id="88f49-158">Это полезно, когда у прогнозируемого атрибута много состояний.</span><span class="sxs-lookup"><span data-stu-id="88f49-158">This is useful if the predictable attribute has many states.</span></span> <span data-ttu-id="88f49-159">Состояния появляются на гистограмме упорядоченными по степени распространенности, слева направо.</span><span class="sxs-lookup"><span data-stu-id="88f49-159">The states appear in a histogram in order of popularity from left to right.</span></span>  
  
-   <span data-ttu-id="88f49-160">Можно также использовать параметры на вкладке **Дерево принятия решений** , чтобы повлиять на отображение дерева, путем изменения масштаба или при изменении размера диаграммы в соответствии с размерами окна.</span><span class="sxs-lookup"><span data-stu-id="88f49-160">You can also use the options on the **Decision Tree** tab to affect how the tree is displayed, by zooming in or out, or sizing the graph to fit the window.</span></span>  
  
-   <span data-ttu-id="88f49-161">Используйте ползунок **Расширение по умолчанию** для установки количества уровней по умолчанию, которые отображаются для всех деревьев в модели.</span><span class="sxs-lookup"><span data-stu-id="88f49-161">Use **Default Expansion** to set the default number of levels that are displayed for all trees in the model.</span></span>  
  
-   <span data-ttu-id="88f49-162">Выберите **Показать длинное имя** , чтобы отобразить полное имя атрибута, включая источник данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-162">Select **Show long name** to display the full name of the attribute, including the data source.</span></span> <span data-ttu-id="88f49-163">Короткие и длинные имена одинаковы, если только атрибуты не получены из различных источников данных.</span><span class="sxs-lookup"><span data-stu-id="88f49-163">Short names and long names are the same unless your cases are obtained from a different data source than the attributes for each case.</span></span>  
  
 [<span data-ttu-id="88f49-164">К началу</span><span class="sxs-lookup"><span data-stu-id="88f49-164">Back To Top</span></span>](#bkmk_Top)  
  
###  <a name="dependency-network"></a><a name="BKMK_DNetwork"></a><span data-ttu-id="88f49-165">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="88f49-165">Dependency Network</span></span>  
 <span data-ttu-id="88f49-166">В представлении **сети зависимостей** отображаются соединения между входными атрибутами и прогнозируемыми атрибутами модели.</span><span class="sxs-lookup"><span data-stu-id="88f49-166">The **Dependency Network** view displays the connections between the input attributes and the predictable attributes in the model.</span></span>  
  
1.  <span data-ttu-id="88f49-167">Перетащите ползунок в левой части средства просмотра</span><span class="sxs-lookup"><span data-stu-id="88f49-167">Click and drag the slider at the left of the viewer</span></span>  
  
     <span data-ttu-id="88f49-168">В верхней части отображаются все связи.</span><span class="sxs-lookup"><span data-stu-id="88f49-168">At the top position, all connections are shown.</span></span> <span data-ttu-id="88f49-169">Если переместить ползунок ниже, будут видны только наиболее прочные из них.</span><span class="sxs-lookup"><span data-stu-id="88f49-169">When you drag the slider down, only the strongest links are shown in the viewer.</span></span>  
  
2.  <span data-ttu-id="88f49-170">Теперь выберите узел «Покупатель велосипеда».</span><span class="sxs-lookup"><span data-stu-id="88f49-170">Now click the Bike Buyer node.</span></span>  
  
     <span data-ttu-id="88f49-171">![Представление сети зависимостей для деревьев принятия решений](media/dm13-dectree-depnet.gif "Представление сети зависимостей для деревьев принятия решений")</span><span class="sxs-lookup"><span data-stu-id="88f49-171">![Dependency network view for decision trees](media/dm13-dectree-depnet.gif "Dependency network view for decision trees")</span></span>  
  
     <span data-ttu-id="88f49-172">После выбора узла в средстве просмотра выделяются зависимости, относящиеся к узлу.</span><span class="sxs-lookup"><span data-stu-id="88f49-172">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="88f49-173">В этом случае в средстве просмотра выделяется каждый узел, позволяющий прогнозировать результат.</span><span class="sxs-lookup"><span data-stu-id="88f49-173">In this case, the viewer highlights each node that helps predict the outcome.</span></span>  
  
3.  <span data-ttu-id="88f49-174">Если средство просмотра содержит много узлов, можно выполнить поиск конкретных узлов с помощью кнопки **Найти узел** .</span><span class="sxs-lookup"><span data-stu-id="88f49-174">If the viewer contains many nodes, you can search for specific nodes by using the **Find Node** button.</span></span> <span data-ttu-id="88f49-175">После нажатия кнопки **Найти узел** откроется диалоговое окно **Поиск узла** , где можно использовать фильтр для поиска и выбора нужных узлов.</span><span class="sxs-lookup"><span data-stu-id="88f49-175">Clicking **Find Node** opens the **Find Node** dialog box, in which you can use a filter to search for and select specific nodes.</span></span>  
  
4.  <span data-ttu-id="88f49-176">Условные обозначения в нижней части средства просмотра связывают цветовые коды с типом зависимости на графе.</span><span class="sxs-lookup"><span data-stu-id="88f49-176">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="88f49-177">Например, при выборе прогнозируемого узла он выделяется бирюзовым цветом, а узлы, которые прогнозируют выбранный узел, — оранжевым цветом.</span><span class="sxs-lookup"><span data-stu-id="88f49-177">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="88f49-178">К началу</span><span class="sxs-lookup"><span data-stu-id="88f49-178">Back To Top</span></span>](#bkmk_Top)  
  
### <a name="drill-through-to-underlying-data"></a><span data-ttu-id="88f49-179">Углубленная детализация до базовых данных</span><span class="sxs-lookup"><span data-stu-id="88f49-179">Drill through to Underlying Data</span></span>  
 <span data-ttu-id="88f49-180">Несколько типов моделей поддерживают возможность *детализации* от модели до базовых данных варианта.</span><span class="sxs-lookup"><span data-stu-id="88f49-180">Several types of models support the ability to *drill through* from the model to the underlying case data.</span></span> <span data-ttu-id="88f49-181">Это может быть полезно, если нужно связаться с клиентами в определенном сегменте или извлечь данные для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="88f49-181">This can be very useful if you want to contact customers in a particular segment or pull out the data to perform further analysis.</span></span>  
  
##### <a name="get-case-data"></a><span data-ttu-id="88f49-182">Извлечение данных вариантов</span><span class="sxs-lookup"><span data-stu-id="88f49-182">Get case data</span></span>  
  
1.  <span data-ttu-id="88f49-183">Щелкните правой кнопкой мыши узел дерева, содержащий нужные данные, и выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="88f49-183">Right-click the node in the tree that contains the desired data and select one of these options:</span></span>  
  
    -   <span data-ttu-id="88f49-184">**Детализация модели**.</span><span class="sxs-lookup"><span data-stu-id="88f49-184">**Drill Through Model**.</span></span> <span data-ttu-id="88f49-185">Этот аргумент возвращает варианты, принадлежащие выбранному узлу, и сохраняет их в таблице в Excel.</span><span class="sxs-lookup"><span data-stu-id="88f49-185">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="88f49-186">Возвращаются только столбцы данных, которые действительно использовались для построения модели.</span><span class="sxs-lookup"><span data-stu-id="88f49-186">You get back only the columns of data that were actually used in building the model.</span></span>  
  
    -   <span data-ttu-id="88f49-187">**Детализация столбцов структуры**.</span><span class="sxs-lookup"><span data-stu-id="88f49-187">**Drill Through Structure Columns**.</span></span> <span data-ttu-id="88f49-188">Этот аргумент возвращает варианты, принадлежащие выбранному узлу, и сохраняет их в таблице в Excel.</span><span class="sxs-lookup"><span data-stu-id="88f49-188">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="88f49-189">При построении вы получаете все сведения, которые были доступны в базовых данных, даже если столбец не использовался в модели.</span><span class="sxs-lookup"><span data-stu-id="88f49-189">You get all information that was available in the underlying data when you built it, even of a column wasn't used in the model.</span></span> <span data-ttu-id="88f49-190">Например, адрес клиента и почтовый индекс могли быть исключены, поскольку эти поля не требуются для анализа, но они остались в структуре.</span><span class="sxs-lookup"><span data-stu-id="88f49-190">For example, you might have excluded the customer address and zip code because those fields are not useful with analysis, but left them in the structure.</span></span>  
  
     <span data-ttu-id="88f49-191">Вернитесь в Excel, чтобы просмотреть данные.</span><span class="sxs-lookup"><span data-stu-id="88f49-191">Return to Excel to view your data.</span></span> <span data-ttu-id="88f49-192">Средство просмотра «Обзор» выполняет запрос, сохраняет данные в таблице на новом листе и присваивает метки результатам.</span><span class="sxs-lookup"><span data-stu-id="88f49-192">The Browse viewer runs a query, saves the data to a table in a new worksheet, and labels the results.</span></span>  
  
     <span data-ttu-id="88f49-193">![Результаты детализации сохраняются в таблице Excel](media/dm13-dectree-drillthroughresults.gif "Результаты детализации сохраняются в таблице Excel")</span><span class="sxs-lookup"><span data-stu-id="88f49-193">![results of drillthrough are saved to Excel](media/dm13-dectree-drillthroughresults.gif "results of drillthrough are saved to Excel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88f49-194">См. также:</span><span class="sxs-lookup"><span data-stu-id="88f49-194">See Also</span></span>  
 [<span data-ttu-id="88f49-195">Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="88f49-195">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
