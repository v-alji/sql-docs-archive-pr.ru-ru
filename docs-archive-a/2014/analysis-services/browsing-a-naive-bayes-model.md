---
title: Просмотр модели упрощенного алгоритма Байеса | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9160b48-3beb-439c-9694-f084e1afa625
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3b0d18cd74e71f1ef18bffd6b0998e0b326e887a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656823"
---
# <a name="browsing-a-naive-bayes-model"></a><span data-ttu-id="b0bc4-102">Обзор модели упрощенного алгоритма Байеса</span><span class="sxs-lookup"><span data-stu-id="b0bc4-102">Browsing a Naive Bayes Model</span></span>
  <span data-ttu-id="b0bc4-103">При открытии модели упрощенного алгоритма Байеса с помощью **кнопки Обзор**модель отображается в интерактивном средстве просмотра с четырьмя разными панелями.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-103">When you open a Naïve Bayes model using **Browse**, the model is displayed in an interactive viewer with four different panes.</span></span> <span data-ttu-id="b0bc4-104">Используйте средство просмотра для исследования корреляций и получайте сведения о модели и базовых данных.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-104">Use the viewer to explore correlations, and get information about the model and the underlying data.</span></span>  
  
-   [<span data-ttu-id="b0bc4-105">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="b0bc4-105">Dependency Network</span></span>](#bkmk_DepNet)  
  
-   [<span data-ttu-id="b0bc4-106">Профили атрибутов</span><span class="sxs-lookup"><span data-stu-id="b0bc4-106">Attribute Profiles</span></span>](#bkmk_AttProf)  
  
-   [<span data-ttu-id="b0bc4-107">Характеристики атрибута</span><span class="sxs-lookup"><span data-stu-id="b0bc4-107">Attribute Characteristics</span></span>](#bkmk_AttChar)  
  
-   [<span data-ttu-id="b0bc4-108">Сравнение атрибутов</span><span class="sxs-lookup"><span data-stu-id="b0bc4-108">Attribute Discrimination</span></span>](#bkmk_AttDisc)  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="b0bc4-109">Изучение модели</span><span class="sxs-lookup"><span data-stu-id="b0bc4-109">Explore the Model</span></span>  
 <span data-ttu-id="b0bc4-110">Средство просмотра помогает исследовать взаимодействие между входными и выходным атрибутами (входные данные и зависимые переменные), которые были обнаружены при помощи модели упрощенного алгоритма Байеса [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0bc4-110">The purpose of the viewer is to help you explore the interaction between input and output attributes (inputs and dependent variables) that were discovered by the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes model.</span></span>  
  
 <span data-ttu-id="b0bc4-111">Если вы хотите поэкспериментировать с помощью средства просмотра упрощенного алгоритма Байеса, используйте [Мастер классификации &#40;мастер надстроек интеллектуального анализа данных для Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) на ленте Интеллектуальный анализ данных, щелкните **Дополнительно** и измените алгоритм, чтобы он использовал упрощенный Байес</span><span class="sxs-lookup"><span data-stu-id="b0bc4-111">If you want to experiment with the Naïve Bayes viewer, use the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard in the Data Mining ribbon, click the **Advanced** option, and change the algorithm to use the Naïve Bayes algorithm</span></span>  
  
 <span data-ttu-id="b0bc4-112">В этих примерах мы использовали исходные данные в образце книги и сгруппированы по столбцу **годовой доход**в пять групп дохода от **очень низких** до **очень высоких**.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-112">For these examples, we used the Source data in the sample workbook, and grouped the column, **Yearly Income**, into five income groups, from **Very Low** to **Very High**.</span></span> <span data-ttu-id="b0bc4-113">Модель упрощенного алгоритма Байеса затем выполнила анализ факторов, связанных с каждой категорией дохода.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-113">The Naïve Bayes model then analyzed the factors correlated with each income category.</span></span>  
  
###  <a name="dependency-network"></a><a name="bkmk_DepNet"></a><span data-ttu-id="b0bc4-114">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="b0bc4-114">Dependency Network</span></span>  
 <span data-ttu-id="b0bc4-115">Первое окно, которое вы будете использовать, — это **Сеть зависимостей**.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-115">The first window you'll use is the **Dependency Network**.</span></span> <span data-ttu-id="b0bc4-116">В нем наглядно отображается, какие входные данные близко связаны с выбранным результатом.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-116">It shows you at a glance which inputs are closely correlated to the selected outcome.</span></span>  
  
 <span data-ttu-id="b0bc4-117">![сеть зависимостей в средстве просмотра упрощенного алгоритма Байеса](media/dm13-nb.gif "сеть зависимостей в средстве просмотра упрощенного алгоритма Байеса")</span><span class="sxs-lookup"><span data-stu-id="b0bc4-117">![dependency network in Naive Bayes viewer](media/dm13-nb.gif "dependency network in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-dependency-network"></a><span data-ttu-id="b0bc4-118">Просмотр сети зависимостей</span><span class="sxs-lookup"><span data-stu-id="b0bc4-118">Explore the dependency network</span></span>  
  
1.  <span data-ttu-id="b0bc4-119">Сначала щелкните целевой результат, **ежегодный доход**, который представлен в виде узла в графе.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-119">First, click the target outcome, **Yearly Income**, which is represented as a node in the graph.</span></span>  
  
     <span data-ttu-id="b0bc4-120">Выделенные узлы, окружающие целевую переменную, — это узлы, наиболее тесно связанные с этим результатом.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-120">The highlighted nodes surrounding the target variable are those that are statistically correlated with this outcome.</span></span> <span data-ttu-id="b0bc4-121">Используйте условные обозначения в нижней части средства просмотра, чтобы понять природу связи.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-121">Use the legend at the bottom of the viewer to understand the nature of the relationship.</span></span>  
  
2.  <span data-ttu-id="b0bc4-122">Щелкните ползунок в левой части средства просмотра и перетащите его вниз.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-122">Click the slider at the left of the viewer and drag it downward.</span></span>  
  
     <span data-ttu-id="b0bc4-123">Этот элемент управления позволяет отфильтровать независимые переменные по степени влияния зависимостей.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-123">This control filters the independent variables, based on the strengths of the dependencies.</span></span> <span data-ttu-id="b0bc4-124">После перетаскивания ползунка вниз только самые прочные из них остаются в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-124">When you drag the slider down, only the strongest links remain in the graph.</span></span>  
  
3.  <span data-ttu-id="b0bc4-125">После фильтрации графа нажмите кнопку **Копировать представление диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-125">After you have filtered the graph, click the button, **Copy Graph View**.</span></span> <span data-ttu-id="b0bc4-126">Выберите лист Excel и нажмите клавиши Ctrl+V.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-126">Then select a worksheet in Excel, and press Ctrl+V.</span></span>  
  
     <span data-ttu-id="b0bc4-127">Этот параметр копирует выбранное представление, в том числе фильтры и выделение.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-127">This option copies the view that you have selected, including filters and highlighting.</span></span>  
  
 [<span data-ttu-id="b0bc4-128">К началу</span><span class="sxs-lookup"><span data-stu-id="b0bc4-128">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-profiles"></a><a name="bkmk_AttProf"></a> <span data-ttu-id="b0bc4-129">Профили атрибутов</span><span class="sxs-lookup"><span data-stu-id="b0bc4-129">Attribute Profiles</span></span>  
 <span data-ttu-id="b0bc4-130">Окна **Профили атрибутов** дают наглядное представление о том, как все остальные переменные связаны с отдельными результатами.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-130">The **Attribute Profiles** windows gives you a visual indication of how all other variables are related to the individual outcomes.</span></span>  
  
##### <a name="explore-the-profiles"></a><span data-ttu-id="b0bc4-131">Исследование профилей</span><span class="sxs-lookup"><span data-stu-id="b0bc4-131">Explore the profiles</span></span>  
  
1.  <span data-ttu-id="b0bc4-132">Чтобы скрыть некоторые значения и нагляднее сравнить результаты, щелкните заголовок столбца и перетащите его под другой столбец.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-132">To hide some values so that you can more easily compare outcomes, click the column heading and drag it under another column.</span></span>  
  
     <span data-ttu-id="b0bc4-133">![профили атрибутов в средстве просмотра упрощенного алгоритма Байеса](media/dm13-nb-attprof.gif "профили атрибутов в средстве просмотра упрощенного алгоритма Байеса")</span><span class="sxs-lookup"><span data-stu-id="b0bc4-133">![attribute profiles in Naive Bayes viewer](media/dm13-nb-attprof.gif "attribute profiles in Naive Bayes viewer")</span></span>  
  
2.  <span data-ttu-id="b0bc4-134">Щелкните любую ячейку, чтобы просмотреть распределение значений в условных обозначениях **интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-134">Click in any cell to view the distribution of values in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="b0bc4-135">Так как атрибуты, связанные с различными результатами, отображаются визуально, легко обнаружить содержательные корреляции, например, как доходы распределяются по регионам.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-135">Because the attributes associated with different outcomes are displayed visually, it is easy to spot interesting correlations, such as how incomes are distributed by region.</span></span>  
  
3.  <span data-ttu-id="b0bc4-136">Чтобы получить данные, лежащие в этом представлении, щелкните **Копировать в Excel**.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-136">To obtain the data underlying this view, click **Copy to Excel**.</span></span> <span data-ttu-id="b0bc4-137">На новом листе создается таблица, в которой указываются корреляции между отдельными атрибутами и результатами.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-137">A table is generated in a new worksheet that shows the correlations among individual attributes and outcomes.</span></span> <span data-ttu-id="b0bc4-138">В этой таблице Excel можно легко скрыть или отфильтровать столбцы.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-138">In this Excel table you can easily hide or filter columns.</span></span>  
  
 [<span data-ttu-id="b0bc4-139">К началу</span><span class="sxs-lookup"><span data-stu-id="b0bc4-139">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-characteristics"></a><a name="bkmk_AttChar"></a> <span data-ttu-id="b0bc4-140">Характеристики атрибута</span><span class="sxs-lookup"><span data-stu-id="b0bc4-140">Attribute Characteristics</span></span>  
 <span data-ttu-id="b0bc4-141">Представление **характеристик атрибута** полезно для глубокого изучения конкретной переменной результата и сопутствующих факторов.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-141">The **Attribute Characteristics** view is useful for in-depth examination of a particular outcome variable and the contributing factors.</span></span>  
  
 <span data-ttu-id="b0bc4-142">![качественные характеристики в средстве просмотра упрощенного алгоритма Байеса](media/dm13-nb-viewer.gif "качественные характеристики в средстве просмотра упрощенного алгоритма Байеса")</span><span class="sxs-lookup"><span data-stu-id="b0bc4-142">![attribute characteristics in Naive Bayes viewer](media/dm13-nb-viewer.gif "attribute characteristics in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-attribute-characteristics"></a><span data-ttu-id="b0bc4-143">Исследование характеристик атрибутов</span><span class="sxs-lookup"><span data-stu-id="b0bc4-143">Explore the attribute characteristics</span></span>  
  
1.  <span data-ttu-id="b0bc4-144">Щелкните **значение** и выберите элемент из **значения**.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-144">Click **Value** and select an item from the **Value**.</span></span>  
  
     <span data-ttu-id="b0bc4-145">По мере выбора целевого результата график будет обновляться и отображать факторы, которые наиболее тесно связаны с результатом, с сортировкой по важности.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-145">As you select a target outcome, the graph updates to show the factors that are most strongly associated with the outcome, sorted by importance.</span></span>  
  
     <span data-ttu-id="b0bc4-146">Обратите внимание, что при создании модели с использованием [ключевых факторов влияния, &#40;средств анализа таблиц для Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) , можно создавать модели, имеющие более одного прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-146">Note that if you create a model using the [Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) option, you can create models that have more than one predictable attribute.</span></span> <span data-ttu-id="b0bc4-147">Тем не менее другие мастера надстроек интеллектуального анализа данных ограничивают возможности одним прогнозируемым атрибутом.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-147">However, all other wizards in the Data Mining add-ins limit you to one predictable attribute.</span></span>  
  
2.  <span data-ttu-id="b0bc4-148">Нажмите кнопку **Копировать в Excel** , чтобы создать таблицу, в новом листе со списком оценок для всех атрибутов, связанных с выбранным исходным результатом.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-148">Click **Copy to Excel** to create a table, in a new worksheet, listing the scores for all attributes that are related to the selected target outcome.</span></span>  
  
 [<span data-ttu-id="b0bc4-149">К началу</span><span class="sxs-lookup"><span data-stu-id="b0bc4-149">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-discrimination"></a><a name="bkmk_AttDisc"></a> <span data-ttu-id="b0bc4-150">Сравнение атрибутов</span><span class="sxs-lookup"><span data-stu-id="b0bc4-150">Attribute Discrimination</span></span>  
 <span data-ttu-id="b0bc4-151">Представление **сравнения атрибутов** помогает сравнить два результата, один результат и все остальные результаты.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-151">The **Attribute Discrimination** view helps compare two outcomes, or one outcome vs. all other outcomes.</span></span>  
  
 <span data-ttu-id="b0bc4-152">![сравнение атрибутов в средстве просмотра упрощенного алгоритма Байеса](media/dm13-nb-attdisc.gif "сравнение атрибутов в средстве просмотра упрощенного алгоритма Байеса")</span><span class="sxs-lookup"><span data-stu-id="b0bc4-152">![attribute discrimination in Naive Bayes viewer](media/dm13-nb-attdisc.gif "attribute discrimination in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-attribute-discrimination"></a><span data-ttu-id="b0bc4-153">Исследование сравнения атрибутов</span><span class="sxs-lookup"><span data-stu-id="b0bc4-153">Explore attribute discrimination</span></span>  
  
1.  <span data-ttu-id="b0bc4-154">Используйте элементы управления, **значение 1** и **значение 2**, чтобы выбрать результаты, которые требуется сравнить.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-154">Use the controls, **Value 1** and **Value 2**, to select the outcomes that you want to compare.</span></span>  
  
     <span data-ttu-id="b0bc4-155">Например, в этой модели было несколько интересных атрибутов в группе "Низкая прибыль", поэтому мы выбрали наименьшую группу доходов в первом раскрывающемся списке и выбрали **все остальные состояния** во втором раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-155">For example, in this model there were some interesting attributes in the low income group, so we chose the lowest income group in the first dropdown list, and chose **All other states** in the second dropdown list.</span></span>  
  
     <span data-ttu-id="b0bc4-156">Атрибуты сортируются по важности (вычисленной на основе обучающих данных).</span><span class="sxs-lookup"><span data-stu-id="b0bc4-156">The attributes are sorted by order of importance (calculated based on the training data).</span></span> <span data-ttu-id="b0bc4-157">Таким образом, род занятий наиболее тесно связан с доходом (по крайней мере для этой целевой группы).</span><span class="sxs-lookup"><span data-stu-id="b0bc4-157">Therefore, occupation is the factor most closely correlated with income (for this target group, at least),</span></span>  
  
     <span data-ttu-id="b0bc4-158">Чтобы увидеть точные данные, щелкните цветную полоску и просмотрите **обозначения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-158">To see the exact figures, click the colored bar and view the **Mining Legend**.</span></span>  
  
2.  <span data-ttu-id="b0bc4-159">Обратите внимание, что более низкие доходы также соотносятся с европейским регионом.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-159">Note that lower incomes are also correlated with the Europe region.</span></span>  
  
     <span data-ttu-id="b0bc4-160">Модель упрощенного алгоритма Байеса не поддерживает углубленную детализацию. Однако, если нужно проверить варианты, связанные с этой группой результатов, можно использовать запрос.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-160">The Naïve Bayes model does not support drilldown; however, if you wanted to investigate the cases associated with this outcome group, you could use a query.</span></span> <span data-ttu-id="b0bc4-161">Дополнительные сведения о запросах для этого типа модели см. в разделе [примеры запросов модели упрощенного алгоритма](data-mining/naive-bayes-model-query-examples.md)Байеса.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-161">For information about queries on this type of model, see [Naive Bayes Model Query Examples](data-mining/naive-bayes-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="b0bc4-162">К началу</span><span class="sxs-lookup"><span data-stu-id="b0bc4-162">Back To Top</span></span>](#BKMK_Tabs)  
  
## <a name="see-also"></a><span data-ttu-id="b0bc4-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0bc4-163">See Also</span></span>  
 [<span data-ttu-id="b0bc4-164">Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="b0bc4-164">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
