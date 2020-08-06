---
title: Тестирование фильтрованной модели (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0d74f8c-600d-4df5-a742-695e6947a071
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a97b5ca3523d1fc73405baba52b179a9bef04767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654642"
---
# <a name="testing-a-filtered-model-basic-data-mining-tutorial"></a><span data-ttu-id="5c21c-102">Проверка модели с фильтром (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="5c21c-102">Testing a Filtered Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="5c21c-103">Теперь, когда вы определили, что `TM_Decision_Tree` модель является наиболее точной, вы настроите модель так, чтобы она лучше соответствовала потребностям [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] кампании целевой рассылки.</span><span class="sxs-lookup"><span data-stu-id="5c21c-103">Now that you have determined that the `TM_Decision_Tree` model is the most accurate, you will customize the model to better suit the needs of the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] targeted mailing campaign.</span></span> <span data-ttu-id="5c21c-104">В частности, Отделу маркетинга хотелось бы выяснить, есть ли какие-либо различия между двумя сотрудниками и клиентами-женщина.</span><span class="sxs-lookup"><span data-stu-id="5c21c-104">Specifically, the Marketing department would like to know if there are any differences between male and female customers.</span></span> <span data-ttu-id="5c21c-105">Эти сведения помогут решить, какие журналы следует использовать для рекламы и какие продукты должны быть в своей почте.</span><span class="sxs-lookup"><span data-stu-id="5c21c-105">The information could help them decide which magazines to use for advertising and which products to feature in their mailings.</span></span>  
  
## <a name="using-filters"></a><span data-ttu-id="5c21c-106">Применение фильтров</span><span class="sxs-lookup"><span data-stu-id="5c21c-106">Using Filters</span></span>  
 <span data-ttu-id="5c21c-107">Фильтры позволяют легко создавать модели на основе подмножеств данных.</span><span class="sxs-lookup"><span data-stu-id="5c21c-107">Filtering enables you to easily create models built on subsets of your data.</span></span> <span data-ttu-id="5c21c-108">Фильтр используется только для модели и не изменяет базовый источник данных.</span><span class="sxs-lookup"><span data-stu-id="5c21c-108">The filter is applied only to the model and does not change the underlying data source.</span></span>  
  
 <span data-ttu-id="5c21c-109">На этом занятии будет создана модель, отфильтрованная по полу, для прогнозирования характеристик, которые наиболее влияют на последующее поведение при покупке в мужчин и женщина.</span><span class="sxs-lookup"><span data-stu-id="5c21c-109">In this lesson, you will create a model that is filtered on gender, to predict the characteristics that most influence buying behavior in males and female.</span></span>  
  
 <span data-ttu-id="5c21c-110">Во-первых, вы сделаете копию `TM_Decision_Tree` модели.</span><span class="sxs-lookup"><span data-stu-id="5c21c-110">First you will make a copy of the `TM_Decision_Tree` model.</span></span>  
  
#### <a name="to-copy-the-decision-tree-model"></a><span data-ttu-id="5c21c-111">Создание копии модели дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="5c21c-111">To copy the Decision Tree Model</span></span>  
  
1.  <span data-ttu-id="5c21c-112">В [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Обозреватель решений выберите **BasicDataMining**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, select **BasicDataMining**.</span></span>  
  
2.  <span data-ttu-id="5c21c-113">Перейдите на вкладку **Модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="5c21c-113">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="5c21c-114">Щелкните правой кнопкой мыши `TM_Decision_Tree` модель и выберите **создать модель интеллектуального анализа данных.**</span><span class="sxs-lookup"><span data-stu-id="5c21c-114">Right click the `TM_Decision_Tree` model, and select **New Mining Model.**</span></span>  
  
4.  <span data-ttu-id="5c21c-115">В поле **имя модели** введите `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="5c21c-115">In the **Model name** field, type `TM_Decision_Tree_Male`.</span></span>  
  
5.  <span data-ttu-id="5c21c-116">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-116">Click **OK**.</span></span>  
  
 <span data-ttu-id="5c21c-117">После этого создайте фильтр для выбора клиентов для данной модели на основе пола.</span><span class="sxs-lookup"><span data-stu-id="5c21c-117">Next, create a filter to select customers for the model based on their gender.</span></span>  
  
#### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="5c21c-118">Создание фильтра вариантов в модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5c21c-118">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="5c21c-119">Щелкните правой кнопкой мыши `TM_Decision_Tree_Male` модель интеллектуального анализа данных, чтобы открыть контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="5c21c-119">Right-click the `TM_Decision_Tree_Male` mining model to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="5c21c-120">-- или --</span><span class="sxs-lookup"><span data-stu-id="5c21c-120">-- or --</span></span>  
  
     <span data-ttu-id="5c21c-121">Выберите модель.</span><span class="sxs-lookup"><span data-stu-id="5c21c-121">Select the model.</span></span> <span data-ttu-id="5c21c-122">В меню **Модель интеллектуального анализа данных** выберите команду **Установить фильтр моделей**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-122">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="5c21c-123">В диалоговом окне **Фильтр модели** щелкните верхнюю строку сетки в текстовом поле **Столбец структуры интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="5c21c-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
     <span data-ttu-id="5c21c-124">В раскрывающемся списке отображаются только имена столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="5c21c-124">The drop-down list displays only the names of the columns in that table.</span></span>  
  
3.  <span data-ttu-id="5c21c-125">В текстовом поле столбец структуры интеллектуального анализа данных выберите **Пол**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-125">In the Mining Structure Column text box, select **Gender**.</span></span>  
  
     <span data-ttu-id="5c21c-126">Значок слева от текстового поля изменится, указывая, что выбранным элементом является таблица или столбец.</span><span class="sxs-lookup"><span data-stu-id="5c21c-126">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
4.  <span data-ttu-id="5c21c-127">Щелкните текстовое поле **оператор** и выберите оператор равенства (=) в списке.</span><span class="sxs-lookup"><span data-stu-id="5c21c-127">Click the **Operator** text box and select the equal (=) operator from the list.</span></span>  
  
5.  <span data-ttu-id="5c21c-128">Щелкните текстовое поле **значение** и введите **M**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-128">Click the **Value** text box, and type **M**.</span></span>  
  
6.  <span data-ttu-id="5c21c-129">Щелкните следующую строку сетки.</span><span class="sxs-lookup"><span data-stu-id="5c21c-129">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="5c21c-130">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Фильтр модели** .</span><span class="sxs-lookup"><span data-stu-id="5c21c-130">Click **OK** to close the **Model Filter** dialog box.</span></span>  
  
     <span data-ttu-id="5c21c-131">Фильтр отображается в окне " **Свойства** ".</span><span class="sxs-lookup"><span data-stu-id="5c21c-131">The filter displays in the **Properties** window.</span></span> <span data-ttu-id="5c21c-132">Кроме того, можно запустить диалоговое окно **Фильтр модели** из окна **свойства** .</span><span class="sxs-lookup"><span data-stu-id="5c21c-132">Alternately, you can launch the **Model Filter** dialog from the **Properties** window.</span></span>  
  
8.  <span data-ttu-id="5c21c-133">Повторите описанные выше шаги, но на этот раз назовите модель `TM_Decision_Tree_Female` и введите **F** в текстовое поле **значение** .</span><span class="sxs-lookup"><span data-stu-id="5c21c-133">Repeat the above steps, but this time name the model `TM_Decision_Tree_Female` and type **F** in the **Value** text box.</span></span>  
  
## <a name="process-the-filtered-models"></a><span data-ttu-id="5c21c-134">Обработка моделей с фильтром</span><span class="sxs-lookup"><span data-stu-id="5c21c-134">Process the Filtered Models</span></span>  
 <span data-ttu-id="5c21c-135">Модели можно использовать только после их развертывания и обработки.</span><span class="sxs-lookup"><span data-stu-id="5c21c-135">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="5c21c-136">Дополнительные сведения об обработке моделей см. в разделе [обработка моделей в структуре целевой рассылки &#40;базовом руководстве по интеллектуальному анализу данных&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="5c21c-136">For more information on processing models, see [Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span></span>  
  
#### <a name="to-process-the-filtered-model"></a><span data-ttu-id="5c21c-137">Выполнение обработки модели с фильтром</span><span class="sxs-lookup"><span data-stu-id="5c21c-137">To process the filtered model</span></span>  
  
1.  <span data-ttu-id="5c21c-138">Щелкните правой кнопкой мыши `TM_Decision_Tree_Male` модель и выберите пункт **обработать структуру интеллектуального анализа данных и все модели**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-138">Right-click the `TM_Decision_Tree_Male` model and select **Process Mining Structure and all Model**s</span></span>  
  
2.  <span data-ttu-id="5c21c-139">Нажмите кнопку **выполнить** , чтобы обработать новые модели.</span><span class="sxs-lookup"><span data-stu-id="5c21c-139">Click **Run** to process the new models.</span></span>  
  
3.  <span data-ttu-id="5c21c-140">После завершения обработки нажмите кнопку **Закрыть** в обоих окнах обработки.</span><span class="sxs-lookup"><span data-stu-id="5c21c-140">After processing is complete, click **Close** on both processing windows.</span></span>  
  
     <span data-ttu-id="5c21c-141">Теперь на вкладке **модели интеллектуального анализа данных** отображаются две новые модели.</span><span class="sxs-lookup"><span data-stu-id="5c21c-141">You now have two new models displayed in the **Mining Models** tab.</span></span>  
  
## <a name="evaluate-the-results"></a><span data-ttu-id="5c21c-142">Анализ результатов</span><span class="sxs-lookup"><span data-stu-id="5c21c-142">Evaluate the Results</span></span>  
 <span data-ttu-id="5c21c-143">Изучите результаты и оцените точность моделей с фильтрами тем же способом, который применялся для предыдущих трех моделей.</span><span class="sxs-lookup"><span data-stu-id="5c21c-143">View the results and assess the accuracy of the filtered models in much the same way as you did for the previous three models.</span></span> <span data-ttu-id="5c21c-144">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="5c21c-144">For more information, see:</span></span>  
  
 [<span data-ttu-id="5c21c-145">Изучение модели дерева принятия решений &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="5c21c-145">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="5c21c-146">Проверка точности с помощью диаграмм точности прогнозов (учебник интеллектуального анализа данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="5c21c-146">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
#### <a name="to-explore-the-filtered-models"></a><span data-ttu-id="5c21c-147">Исследование моделей с фильтрами</span><span class="sxs-lookup"><span data-stu-id="5c21c-147">To explore the filtered models</span></span>  
  
1.  <span data-ttu-id="5c21c-148">Выберите вкладку **средство просмотра моделей интеллектуального анализа** **данных в конструкторе интеллектуального анализа**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-148">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="5c21c-149">В поле модель интеллектуального анализа данных выберите `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="5c21c-149">In the Mining Model box, select `TM_Decision_Tree_Male`.</span></span>  
  
3.  <span data-ttu-id="5c21c-150">**Уровень** показа слайдов до `3` .</span><span class="sxs-lookup"><span data-stu-id="5c21c-150">Slide **Show Level** to `3`.</span></span>  
  
4.  <span data-ttu-id="5c21c-151">Измените значение параметра **фон** на `1` .</span><span class="sxs-lookup"><span data-stu-id="5c21c-151">Change the **Background** value to `1`.</span></span>  
  
5.  <span data-ttu-id="5c21c-152">Наведите курсор на узел с меткой **все** , чтобы увидеть число покупателей велосипедов и покупателей, не являющихся велосипедами.</span><span class="sxs-lookup"><span data-stu-id="5c21c-152">Place your cursor over the node labeled **All** to see the number of bike buyers versus non-bike buyers.</span></span>  
  
6.  <span data-ttu-id="5c21c-153">Повторите шаги 1-5 для `TM_Decision_Tree_Female` .</span><span class="sxs-lookup"><span data-stu-id="5c21c-153">Repeat steps 1 - 5 for `TM_Decision_Tree_Female`.</span></span>  
  
7.  <span data-ttu-id="5c21c-154">Изучите результаты для `TM_Decision_Tree` и модели, отфильтрованные для пола.</span><span class="sxs-lookup"><span data-stu-id="5c21c-154">Explore the results for the `TM_Decision_Tree` and the models filtered for gender.</span></span> <span data-ttu-id="5c21c-155">По сравнению со всеми покупателями велосипедов мужчины и женщины, покупающие велосипеды, имеют некоторые общие характеристики с общей массой покупателей велосипедов, но между всеми тремя группами покупателей есть и интересные различия.</span><span class="sxs-lookup"><span data-stu-id="5c21c-155">Compared to all bike buyers, male and female bike buyers share some of the same characteristics as the unfiltered bike buyers but all three have interesting differences as well.</span></span> <span data-ttu-id="5c21c-156">Это полезные сведения, которые [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] могут использоваться для разработки маркетинговых кампаний.</span><span class="sxs-lookup"><span data-stu-id="5c21c-156">This is useful information that [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] can use to develop their marketing campaign.</span></span>  
  
#### <a name="to-test-the-lift-of-the-filtered-models"></a><span data-ttu-id="5c21c-157">Проверка точности моделей с фильтрами</span><span class="sxs-lookup"><span data-stu-id="5c21c-157">To test the lift of the filtered models</span></span>  
  
1.  <span data-ttu-id="5c21c-158">Перейдите на вкладку **Диаграмма точности интеллектуального анализа** в конструкторе интеллектуального анализа данных в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] и выберите вкладку **Выбор входа** .</span><span class="sxs-lookup"><span data-stu-id="5c21c-158">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="5c21c-159">В поле **выберите набор данных для использования в группе диаграмм точности** выберите **использовать проверочные варианты структуры интеллектуального анализа**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-159">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span>  
  
3.  <span data-ttu-id="5c21c-160">На вкладке **Выбор входа** конструктора интеллектуального анализа данных в разделе **Выбор прогнозируемых столбцов модели интеллектуального анализа для отображения на диаграмме точности**прогнозов установите флажок **синхронизировать прогнозируемые столбцы и значения**.</span><span class="sxs-lookup"><span data-stu-id="5c21c-160">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
4.  <span data-ttu-id="5c21c-161">Убедитесь, что в столбце **имя прогнозируемого столбца** выбрано значение **Покупатель велосипеда** для каждой модели.</span><span class="sxs-lookup"><span data-stu-id="5c21c-161">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
5.  <span data-ttu-id="5c21c-162">В столбце **Показывать** выберите каждую из моделей.</span><span class="sxs-lookup"><span data-stu-id="5c21c-162">In the **Show** column, select each of the models.</span></span>  
  
6.  <span data-ttu-id="5c21c-163">В столбце **значение прогноза** выберите `1` .</span><span class="sxs-lookup"><span data-stu-id="5c21c-163">In the **Predict Value** column, select `1`.</span></span>  
  
7.  <span data-ttu-id="5c21c-164">Перейдите на вкладку **Диаграмма точности прогнозов** , чтобы отобразить диаграмму точности прогнозов.</span><span class="sxs-lookup"><span data-stu-id="5c21c-164">Select the **Lift Chart** tab to display the lift chart.</span></span>  
  
     <span data-ttu-id="5c21c-165">Обратите внимание, что все три модели дерева принятия решений демонстрируют заметную точность по сравнению с моделью случайного выбора, а также превосходят по точности модели на основе алгоритма кластеризации и упрощенного алгоритма Байеса.</span><span class="sxs-lookup"><span data-stu-id="5c21c-165">You will now notice that all three Decision Tree models provide significant lift compared to the random guess model, and also outperform the Clustering and Naive-Bayes models.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5c21c-166">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="5c21c-166">Related Tasks</span></span>  
 <span data-ttu-id="5c21c-167">Дополнительные сведения о фильтрах см. в разделе [фильтры для моделей интеллектуального анализа данных &#40;Analysis Services-&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5c21c-167">For more information on filters, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="5c21c-168">Пример применения фильтров к вложенным таблицам см. в разделе [учебник по интеллектуальному анализу данных &#40;Analysis Services-&#41;интеллектуального анализа данных ](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5c21c-168">For an example of how to apply filters to nested tables, see [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="5c21c-169">Предыдущая задача занятия</span><span class="sxs-lookup"><span data-stu-id="5c21c-169">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="5c21c-170">Проверка точности с помощью диаграмм точности прогнозов (учебник интеллектуального анализа данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="5c21c-170">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="5c21c-171">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="5c21c-171">Next Lesson</span></span>  
 [<span data-ttu-id="5c21c-172">Занятие 6. Создание прогнозов и работа с ними (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="5c21c-172">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="5c21c-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c21c-173">See Also</span></span>  
 <span data-ttu-id="5c21c-174">[Учебник по интеллектуальному анализу данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5c21c-174">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="5c21c-175">[Задачи и инструкции по модели интеллектуального анализа данных](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="5c21c-175">[Mining Model Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="5c21c-176">[Удаление фильтра из модели интеллектуального анализа данных](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="5c21c-176">[Delete a Filter from a Mining Model](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="5c21c-177">Фильтры для моделей интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="5c21c-177">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
