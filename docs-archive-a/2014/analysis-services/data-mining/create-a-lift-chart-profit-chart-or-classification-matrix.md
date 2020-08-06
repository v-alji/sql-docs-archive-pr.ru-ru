---
title: Создание диаграммы точности прогнозов, диаграммы роста прибыли или матрицы классификации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], mining structures
ms.assetid: aa3d052f-58a9-4417-8e7a-5e6feb562af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 932138b37b36269bed86df42786bd5d684f75ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728973"
---
# <a name="create-a-lift-chart-profit-chart-or-classification-matrix"></a><span data-ttu-id="aee40-102">Создать диаграмму точности прогнозов, диаграмму роста прибыли или матрицу классификации</span><span class="sxs-lookup"><span data-stu-id="aee40-102">Create a Lift Chart, Profit Chart, or Classification Matrix</span></span>
  <span data-ttu-id="aee40-103">Диаграмма точности для модели интеллектуального анализа данных [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] создается в пять простых шагов.</span><span class="sxs-lookup"><span data-stu-id="aee40-103">You can create an accuracy chart for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data mining model in five basic steps:</span></span>  
  
-   <span data-ttu-id="aee40-104">Выберите структуру интеллектуального анализа данных, содержащую модели интеллектуального анализа данных, которые нужно сравнить.</span><span class="sxs-lookup"><span data-stu-id="aee40-104">Select the mining structure that contains the mining models that you want to compare.</span></span>  
  
-   <span data-ttu-id="aee40-105">Выберите модели интеллектуального анализа данных, которые будут добавлены в диаграмму.</span><span class="sxs-lookup"><span data-stu-id="aee40-105">Select the mining models to add to the chart.</span></span>  
  
-   <span data-ttu-id="aee40-106">Задайте источник проверочных данных, на основании которого будет создана диаграмма.</span><span class="sxs-lookup"><span data-stu-id="aee40-106">Specify a source of testing data to use in generating the chart.</span></span>  
  
-   <span data-ttu-id="aee40-107">Выберите тип диаграммы.</span><span class="sxs-lookup"><span data-stu-id="aee40-107">Choose the chart type.</span></span>  
  
-   <span data-ttu-id="aee40-108">Настройте параметры диаграммы.</span><span class="sxs-lookup"><span data-stu-id="aee40-108">Configure the chart options.</span></span>  
  
 <span data-ttu-id="aee40-109">Эти шаги одинаковы для диаграммы точности прогнозов, диаграммы роста прибыли и матрицы классификации.</span><span class="sxs-lookup"><span data-stu-id="aee40-109">These basic steps are the same for the lift chart, profit chart, and classification matrix.</span></span> <span data-ttu-id="aee40-110">Далее описываются процедуры настройки общих параметров для этих типов диаграмм.</span><span class="sxs-lookup"><span data-stu-id="aee40-110">The following procedures outline the steps to configure the basic chart options for these chart types.</span></span> <span data-ttu-id="aee40-111">Дополнительные сведения о создании отчета перекрестной проверки см. в разделе [Меры в отчете перекрестной проверки](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="aee40-111">For information about how to create a cross-validation report, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
### <a name="open-the-mining-structure-in-the-accuracy-chart-designer"></a><span data-ttu-id="aee40-112">Откройте структуру интеллектуального анализа данных в конструкторе диаграмм точности</span><span class="sxs-lookup"><span data-stu-id="aee40-112">Open the mining structure in the Accuracy Chart Designer</span></span>  
  
1.  <span data-ttu-id="aee40-113">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте конструктор интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="aee40-113">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="aee40-114">В обозревателе решений дважды щелкните структуру, которая содержит модель или модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="aee40-114">In Solution Explorer, double-click the structure that contains the mining model or models.</span></span>  
  
3.  <span data-ttu-id="aee40-115">Перейдите на вкладку **Диаграмма точности интеллектуального анализа** .</span><span class="sxs-lookup"><span data-stu-id="aee40-115">Click the **Mining Accuracy Chart** tab.</span></span>  
  
### <a name="select-mining-models-for-inclusion-in-the-chart"></a><span data-ttu-id="aee40-116">Выберите модели интеллектуального анализа данных для включения в диаграмму</span><span class="sxs-lookup"><span data-stu-id="aee40-116">Select mining models for inclusion in the chart</span></span>  
  
1.  <span data-ttu-id="aee40-117">На вкладке **Диаграмма точности интеллектуального анализа** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]перейдите на вкладку **Выбор входных данных** .</span><span class="sxs-lookup"><span data-stu-id="aee40-117">On the **Mining Accuracy Chart** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Input Selection** tab.</span></span>  
  
     <span data-ttu-id="aee40-118">Появится список всех моделей текущей структуры, содержащих этот же прогнозируемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="aee40-118">The list displays all models in the current structure that have the same predictable attribute.</span></span>  
  
2.  <span data-ttu-id="aee40-119">Установите флажок **Показать** для всех моделей, которые нужно включить в диаграмму.</span><span class="sxs-lookup"><span data-stu-id="aee40-119">Select the **Show box** for each model that you want to include in the chart.</span></span>  
  
3.  <span data-ttu-id="aee40-120">Щелкните текстовое поле **Имя прогнозируемого столбца** и выберите имя прогнозируемого столбца из списка.</span><span class="sxs-lookup"><span data-stu-id="aee40-120">Click the **Predictable Column Name** text box, and select the name of a predictable column from the list.</span></span> <span data-ttu-id="aee40-121">Все модели, включенные в диаграмму, должны иметь один и тот же прогнозируемый столбец.</span><span class="sxs-lookup"><span data-stu-id="aee40-121">All models that you put in one chart must have the same predictable column.</span></span>  
  
4.  <span data-ttu-id="aee40-122">Если у сравниваемых моделей значения или типы данных в прогнозируемых столбцах различаются, следует снять флажок **Синхронизировать столбцы и значения прогноза** , чтобы произвести сравнение принудительно.</span><span class="sxs-lookup"><span data-stu-id="aee40-122">If you compare two models and the predictable columns have different values or different data types, clear the **Synchonize prediction columns and values** box to force a comparison.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aee40-123">Если флажок **Синхронизировать столбцы и значения прогноза** установлен, службы Analysis Services анализируют данные в прогнозируемых столбцах модели и проверочных данных и пытаются найти наилучшее соответствие.</span><span class="sxs-lookup"><span data-stu-id="aee40-123">If the **Synchonize prediction columns and values** box is selected, Analysis Services analyzes the data in the predictable columns of the model and the test data, and attempts to find the best match.</span></span> <span data-ttu-id="aee40-124">Этот флажок следует снимать только в случаях, когда нужно выполнить принудительное сравнение столбцов.</span><span class="sxs-lookup"><span data-stu-id="aee40-124">Therefore, do not clear the box unless absolutely necessary to force a comparison of the columns.</span></span>  
  
5.  <span data-ttu-id="aee40-125">Щелкните текстовое поле **Прогнозируемое значение** и выберите значение из списка.</span><span class="sxs-lookup"><span data-stu-id="aee40-125">Click the **Predict Value** text box, and select a value from the list.</span></span> <span data-ttu-id="aee40-126">Если данные в прогнозируемом столбце имеют непрерывный тип, введите в это текстовое поле значение.</span><span class="sxs-lookup"><span data-stu-id="aee40-126">If the predictable column is a continuous data type, you must type a value in the text box.</span></span>  
  
     <span data-ttu-id="aee40-127">Дополнительные сведения см. в разделе [Выбор столбца, используемого для тестирования модели интеллектуального анализа](choose-the-column-to-use-for-testing-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="aee40-127">For more information, see [Choose the Column to Use for Testing a Mining Model](choose-the-column-to-use-for-testing-a-mining-model.md).</span></span>  
  
### <a name="select-testing-data"></a><span data-ttu-id="aee40-128">Выбор проверочных данных</span><span class="sxs-lookup"><span data-stu-id="aee40-128">Select testing data</span></span>  
  
1.  <span data-ttu-id="aee40-129">На вкладке **Выбор входных данных** страницы **Диаграмма точности интеллектуального анализа** задайте источник данных, который будет использоваться для создания диаграммы. Для этого выберите один из параметров в группе **Выбор набора данных для диаграммы точности**.</span><span class="sxs-lookup"><span data-stu-id="aee40-129">On the **Input Selection** tab of the **Mining Accuracy Chart** tab, specify the source of the data that you will use to generate the chart by selecting one of the options in the group, **Select data set to be used for accuracy chart**.</span></span>  
  
    -   <span data-ttu-id="aee40-130">Выберите вариант **Использовать проверочные варианты модели интеллектуального анализа данных**, если нужно использовать подмножество вариантов, определяемых пересечением проверочных вариантов структуры интеллектуального анализа данных и любых фильтров, которые могли применяться во время создания модели.</span><span class="sxs-lookup"><span data-stu-id="aee40-130">Select the option, **Use Mining Model test cases**, if you want to use the subset of cases that is defined by the intersection of the mining structure test cases and any filters that may have been applied during model creation.</span></span>  
  
    -   <span data-ttu-id="aee40-131">Выберите вариант **Использовать проверочные варианты структуры интеллектуального анализа данных**для использования полного набора проверочных вариантов, которые были определены в составе набора контрольных данных структур интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="aee40-131">Select the option, **Use mining structure test cases**, to use the full set of testing cases that were defined as part of the mining structures holdout data set.</span></span>  
  
    -   <span data-ttu-id="aee40-132">Выберите параметр **Задать другой набор данных**, если нужно использовать внешние данные.</span><span class="sxs-lookup"><span data-stu-id="aee40-132">Select the option, **Specify a different data set**, if you want to use external data.</span></span>  <span data-ttu-id="aee40-133">Набор данных должен быть доступен в форме представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="aee40-133">The data set must be available as a data source view.</span></span>   <span data-ttu-id="aee40-134">Нажмите кнопку обзора (**...**), чтобы выбрать таблицы данных для использования в диаграмме точности.</span><span class="sxs-lookup"><span data-stu-id="aee40-134">Click the browse (**...**) button to choose the data tables to use for the accuracy chart.</span></span> <span data-ttu-id="aee40-135">Дополнительные сведения см. в статье [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="aee40-135">For more information, see [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span></span>  
  
         <span data-ttu-id="aee40-136">При использовании внешнего набора данных можно, по желанию, фильтровать набор входных данных.</span><span class="sxs-lookup"><span data-stu-id="aee40-136">If you are using an external data set, you can optionally filter the input data set.</span></span> <span data-ttu-id="aee40-137">Дополнительные сведения см. в статье [Применение фильтров к данным проверки модели](apply-filters-to-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="aee40-137">For more information, see [Apply Filters to Model Testing Data](apply-filters-to-model-testing-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aee40-138">Нельзя создать фильтр для тестовых случаев модели или проверочных вариантов структуры интеллектуального анализа данных на вкладке **Выбор входа** . Чтобы создать фильтр для модели интеллектуального анализа данных, измените свойство Filter модели.</span><span class="sxs-lookup"><span data-stu-id="aee40-138">You cannot create a filter on the model test cases or the mining structure test cases on the **Input Selection** tab. To create a filter on the mining model, modify the Filter property of the model.</span></span> <span data-ttu-id="aee40-139">Дополнительные сведения см. в разделе [Применение фильтра к модели интеллектуального анализа данных](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="aee40-139">For more information, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
### <a name="configure-chart-settings-and-generate-the-chart"></a><span data-ttu-id="aee40-140">Настройка параметров диаграммы и формирование диаграммы</span><span class="sxs-lookup"><span data-stu-id="aee40-140">Configure chart settings and generate the chart</span></span>  
  
1.  <span data-ttu-id="aee40-141">На вкладке **Диаграмма точности интеллектуального анализа данных** перейдите на вкладку диаграммы, которую нужно создать.</span><span class="sxs-lookup"><span data-stu-id="aee40-141">In the **Mining Accuracy Chart** tab, click the tab for the chart you want to create.</span></span>  
  
2.  <span data-ttu-id="aee40-142">Для **диаграммы точности прогнозов**перейдите на вкладку **Диаграмма точности прогнозов** . Диаграмма создается автоматически на основе модели, прогнозируемых атрибутов и входных данных, которые вы только что выбрали.</span><span class="sxs-lookup"><span data-stu-id="aee40-142">For a **lift chart**, click the **Lift Chart** tab. The chart is automatically generated based on the model, predictable attributes, and input data that you just selected.</span></span>  
  
3.  <span data-ttu-id="aee40-143">Для **матрицы классификации**перейдите на вкладку **Матрица классификации** . Дальнейшие настройки не требуются. диаграмма создается автоматически на основе выбранных входных данных и модели.</span><span class="sxs-lookup"><span data-stu-id="aee40-143">For a **classification matrix**, click the **Classification Matrix** tab. No further settings are needed; the chart is automatically generated based on the input data and model that you selected.</span></span>  
  
4.  <span data-ttu-id="aee40-144">Для **диаграммы роста прибыли**сначала щелкните вкладку **Диаграмма точности прогнозов** . Затем в раскрывающемся списке **тип диаграммы** выберите пункт **Диаграмма роста прибыли**.</span><span class="sxs-lookup"><span data-stu-id="aee40-144">For a **profit chart**, first click the **Lift Chart** tab. Then, from the **Chart type** drop-down list, select **Profit chart**.</span></span>  
  
     <span data-ttu-id="aee40-145">Введите следующие параметры в диалоговом окне **Настройки диаграммы роста прибыли** .</span><span class="sxs-lookup"><span data-stu-id="aee40-145">Enter the following settings in the **Profit Chart Settings** dialog box.</span></span>  
  
     <span data-ttu-id="aee40-146">**Повтор**</span><span class="sxs-lookup"><span data-stu-id="aee40-146">**Population**</span></span>  
     <span data-ttu-id="aee40-147">Число вариантов из набора данных, который нужно использовать для создания диаграммы точности прогнозов.</span><span class="sxs-lookup"><span data-stu-id="aee40-147">The number of cases from the data set that you want to use when creating the lift chart.</span></span>  
  
     <span data-ttu-id="aee40-148">Модель всегда выбирает варианты в порядке убывания вероятности. Это значит, что если оцениваются потенциальные клиенты и нужно выбрать число, которое представляет только половину записей в базе данных клиентов, то модель будет измерять точность для подмножества вариантов, которые лучше всего соответствуют модели.</span><span class="sxs-lookup"><span data-stu-id="aee40-148">The model always chooses the cases in order of decreasing probability; that is, if you are assessing potential customers and you choose a number that represents only half the records in your customer database, the model will measure accuracy on the subset of cases that best fit your model.</span></span>  
  
     <span data-ttu-id="aee40-149">Это происходит из-за того, что во время использования модели для формирования рассылки или создания кампании будет использоваться вероятность прогноза, связанная с каждым вариантом, чтобы включить в рассылку только клиентов, вероятность получить положительный отклик от которых будет максимальной.</span><span class="sxs-lookup"><span data-stu-id="aee40-149">This is because when you use the model to generate a mailing or create a campaign, you will use the prediction probability associated with each case to target only the customers who have the highest probability of making a positive response.</span></span>  
  
     <span data-ttu-id="aee40-150">**Фиксированные затраты**</span><span class="sxs-lookup"><span data-stu-id="aee40-150">**Fixed Cost**</span></span>  
     <span data-ttu-id="aee40-151">Фиксированные издержки, связанные с бизнес-задачами.</span><span class="sxs-lookup"><span data-stu-id="aee40-151">The fixed cost that is associated with the business problem.</span></span>  
  
     <span data-ttu-id="aee40-152">Фиксированные затраты на целевую рассылку могут представлять оплату установки принтера, включая первоначальные затраты по подготовке рекламной рассылки.</span><span class="sxs-lookup"><span data-stu-id="aee40-152">If this were for a targeted mailing solution, the fixed cost might represent a printer setup fee that covers the initial cost of preparing the promotional mailing.</span></span>  
  
     <span data-ttu-id="aee40-153">Эти затраты учитываются один раз для всей целевой совокупности.</span><span class="sxs-lookup"><span data-stu-id="aee40-153">This cost applies one time to the entire target population.</span></span>  
  
     <span data-ttu-id="aee40-154">**Индивидуальная стоимость**</span><span class="sxs-lookup"><span data-stu-id="aee40-154">**Individual Cost**</span></span>  
     <span data-ttu-id="aee40-155">Расходы, добавляющиеся к фиксированным издержкам, которые могут быть связаны с обращением к каждому заказчику.</span><span class="sxs-lookup"><span data-stu-id="aee40-155">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="aee40-156">Например, сюда можно включить почтовые расходы по доставке рекламных писем или расходы на оплату телефонных переговоров.</span><span class="sxs-lookup"><span data-stu-id="aee40-156">For example, you might enter the postage cost for a promotional mailing or the cost of making telephone calls.</span></span>  
  
     <span data-ttu-id="aee40-157">Эти расходы должны быть одинаковы для всей целевой совокупности.</span><span class="sxs-lookup"><span data-stu-id="aee40-157">This cost must be the same for the entire target population.</span></span> <span data-ttu-id="aee40-158">Каждое значение умножается на число целевых вариантов.</span><span class="sxs-lookup"><span data-stu-id="aee40-158">Each value is multiplied by the number of cases that are targeted.</span></span>  
  
     <span data-ttu-id="aee40-159">**Доход на единицу**</span><span class="sxs-lookup"><span data-stu-id="aee40-159">**Revenue Per Individual**</span></span>  
     <span data-ttu-id="aee40-160">Сумма прибыли, связанная с каждой успешной продажей.</span><span class="sxs-lookup"><span data-stu-id="aee40-160">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee40-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="aee40-161">See Also</span></span>  
 <span data-ttu-id="aee40-162">[Диаграмма точности прогнозов &#40;Analysis Services&#41;интеллектуального анализа данных](lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="aee40-162">[Lift Chart &#40;Analysis Services - Data Mining&#41;](lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="aee40-163">Матрица классификации (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="aee40-163">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](classification-matrix-analysis-services-data-mining.md)  
  
  
