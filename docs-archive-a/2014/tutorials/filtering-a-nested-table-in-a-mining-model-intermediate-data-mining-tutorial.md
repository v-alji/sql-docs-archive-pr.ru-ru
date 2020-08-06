---
title: Фильтрация вложенной таблицы в модели интеллектуального анализа (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0a3ae0e5-897b-4898-a60d-5455eec3d305
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1e6ce2936a3c6763ea41999b2724c0fe8c79301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739014"
---
# <a name="filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="ce536-102">Фильтрование вложенной таблицы в модели интеллектуального анализа данных (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="ce536-102">Filtering a Nested Table in a Mining Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="ce536-103">После создания и изучения модели принимается решение сосредоточить внимание на подмножестве данных о клиентах.</span><span class="sxs-lookup"><span data-stu-id="ce536-103">After you have created and explored the model, you decide that you want to focus on a subset of the customer data.</span></span> <span data-ttu-id="ce536-104">Например, можно выполнить анализ только тех потребительских корзин, которые содержат конкретный элемент, или проанализировать демографические данных клиентов, которые ничего не купили в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="ce536-104">For example, you might want to analyze only the baskets that contain a specific item, or to analyze the demographics of customers who have not purchased anything in a certain period.</span></span>  
  
 <span data-ttu-id="ce536-105">Службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] предоставляют возможность фильтрации данных, которые используются в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ce536-105">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides the ability to filter the data that is used in a mining model.</span></span> <span data-ttu-id="ce536-106">Эта функция полезна, поскольку не нужно настраивать новое представление источника данных для использования других данных.</span><span class="sxs-lookup"><span data-stu-id="ce536-106">This feature is useful because you do not need to set up a new data source view to use different data.</span></span> <span data-ttu-id="ce536-107">В учебнике по интеллектуальному анализу данных (начальный уровень) рассматривалось, как фильтровать данные из плоской таблицы путем применения условий к таблице вариантов.</span><span class="sxs-lookup"><span data-stu-id="ce536-107">In the Basic Data Mining Tutorial, you learned how to filter data from a flat table by applying conditions to the case table.</span></span> <span data-ttu-id="ce536-108">В этой задаче создается фильтр для применения к вложенной таблице.</span><span class="sxs-lookup"><span data-stu-id="ce536-108">In this task, you create a filter that applies to a nested table.</span></span>  
  
## <a name="filters-on-nested-vs-case-tables"></a><span data-ttu-id="ce536-109">Фильтры для вложенных таблиц и таблиц вариантов</span><span class="sxs-lookup"><span data-stu-id="ce536-109">Filters on Nested vs. Case Tables</span></span>  
 <span data-ttu-id="ce536-110">Если представление источника данных содержит таблицу вариантов и вложенную таблицу (подобно представлению источника данных, которое используется в модели взаимосвязей), фильтр можно использовать на основании значений из таблицы вариантов, наличия или отсутствия определенного значения во вложенной таблице либо сочетания тех и других.</span><span class="sxs-lookup"><span data-stu-id="ce536-110">If your data source view contains a case table and a nested table, like the data source view used in the Association model, you can filter on values from the case table, the presence or absence of a value in the nested table, or some combination of both.</span></span>  
  
 <span data-ttu-id="ce536-111">В этой задаче сначала создается копия модели взаимосвязей, а затем к новой связанной модели добавляются атрибуты IncomeGroup и Region, чтобы можно было выполнить фильтрация по этим атрибутам в таблице вариантов.</span><span class="sxs-lookup"><span data-stu-id="ce536-111">In this task, you will first make a copy of the Association model and then add the IncomeGroup and Region attributes to the new related model, so that you can filter on those attributes in the case table.</span></span>  
  
#### <a name="to-create-and-modify-a-copy-of-the-association-model"></a><span data-ttu-id="ce536-112">Создание и изменение копии модели «Взаимосвязь»</span><span class="sxs-lookup"><span data-stu-id="ce536-112">To create and modify a copy of the Association model</span></span>  
  
1.  <span data-ttu-id="ce536-113">На вкладке **модели интеллектуального анализа** данных в щелкните [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] правой кнопкой мыши `Association` модель и выберите пункт **создать модель интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="ce536-113">In the **Mining Models** tab of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click the `Association` model, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="ce536-114">В качестве **имени модели**введите `Association Filtered` .</span><span class="sxs-lookup"><span data-stu-id="ce536-114">For **Model Name**, type `Association Filtered`.</span></span> <span data-ttu-id="ce536-115">В качестве **имени алгоритма**выберите **Правила взаимосвязей (Майкрософт**).</span><span class="sxs-lookup"><span data-stu-id="ce536-115">For **Algorithm Name**, select **Microsoft Association Rules**.</span></span> <span data-ttu-id="ce536-116">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce536-116">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="ce536-117">В столбце для фильтрованной модели взаимосвязей щелкните строку IncomeGroup и измените значение с **Ignore** на **input**.</span><span class="sxs-lookup"><span data-stu-id="ce536-117">In the column for the Association Filtered model, click the IncomeGroup row and change the value from **Ignore** to **Input**.</span></span>  
  
 <span data-ttu-id="ce536-118">После этого следует создать фильтр для таблицы вариантов в новой модели взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="ce536-118">Next, you will create a filter on the case table in the new association model.</span></span> <span data-ttu-id="ce536-119">Этот фильтр передаст модели только тех заказчиков, которые находятся в целевом регионе или имеют определенный уровень дохода.</span><span class="sxs-lookup"><span data-stu-id="ce536-119">The filter will pass to the model only the customers in the target region or with the target income level.</span></span> <span data-ttu-id="ce536-120">Затем нужно добавить второй набор условий фильтра, чтобы указать, что модель использует только клиентов, в чьих корзинах заказов содержался по крайней мере один элемент.</span><span class="sxs-lookup"><span data-stu-id="ce536-120">Then, you will add a second set of filter conditions to specify that the model uses only customers whose shopping baskets contained at least one item.</span></span>  
  
#### <a name="to-add-a-filter-to-a-mining-model"></a><span data-ttu-id="ce536-121">Добавление фильтра в модель интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ce536-121">To add a filter to a mining model</span></span>  
  
1.  <span data-ttu-id="ce536-122">На вкладке **модели интеллектуального анализа данных** щелкните правой кнопкой мыши отфильтрованную связь модели и выберите команду **задать фильтр модели**.</span><span class="sxs-lookup"><span data-stu-id="ce536-122">In the **Mining Models** tab, right-click the model Association Filtered, and select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="ce536-123">В диалоговом окне **Фильтр модели** щелкните верхнюю строку сетки в текстовом поле **Столбец структуры интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="ce536-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
3.  <span data-ttu-id="ce536-124">В текстовом поле **столбец структуры интеллектуального анализа данных** выберите IncomeGroup.</span><span class="sxs-lookup"><span data-stu-id="ce536-124">In the **Mining Structure Column** text box, select IncomeGroup.</span></span>  
  
     <span data-ttu-id="ce536-125">Значок слева от текстового поля изменится, указывая, что выбранным элементом является столбец.</span><span class="sxs-lookup"><span data-stu-id="ce536-125">The icon at the left side of the text box changes to indicate that the selected item is a column.</span></span>  
  
4.  <span data-ttu-id="ce536-126">Щелкните текстовое поле **оператор** и выберите **=** оператор из списка.</span><span class="sxs-lookup"><span data-stu-id="ce536-126">Click the **Operator** text box and select the **=** operator from the list.</span></span>  
  
5.  <span data-ttu-id="ce536-127">Щелкните текстовое поле **значение** и введите `High` в поле.</span><span class="sxs-lookup"><span data-stu-id="ce536-127">Click the **Value** text box, and type `High` in the box.</span></span>  
  
6.  <span data-ttu-id="ce536-128">Щелкните следующую строку сетки.</span><span class="sxs-lookup"><span data-stu-id="ce536-128">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="ce536-129">Щелкните текстовое поле **и/или** в следующей строке сетки и выберите **или**.</span><span class="sxs-lookup"><span data-stu-id="ce536-129">Click the **AND/OR** text box in the next row of the grid and select **OR**.</span></span>  
  
8.  <span data-ttu-id="ce536-130">В текстовом поле **столбец структуры интеллектуального анализа данных** выберите IncomeGroup.</span><span class="sxs-lookup"><span data-stu-id="ce536-130">In the **Mining Structure Column** text box, select IncomeGroup.</span></span> <span data-ttu-id="ce536-131">В текстовом поле **значение** введите `Moderate` .</span><span class="sxs-lookup"><span data-stu-id="ce536-131">In the **Value** text box, type `Moderate`.</span></span>  
  
     <span data-ttu-id="ce536-132">Созданное условие фильтра автоматически добавляется в текстовое поле **выражение** и должно выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ce536-132">The filter condition that you created is automatically added to the **Expression** text box, and should appears as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate'`  
  
9. <span data-ttu-id="ce536-133">Щелкните следующую строку в сетке, оставьте оператор в качестве значения по умолчанию **и**.</span><span class="sxs-lookup"><span data-stu-id="ce536-133">Click the next row in the grid, leaving the operator as the default, **AND**.</span></span>  
  
10. <span data-ttu-id="ce536-134">В поле **оператор**оставьте значение по умолчанию, **содержащее**.</span><span class="sxs-lookup"><span data-stu-id="ce536-134">For **Operator**, leave the default value, **Contains**.</span></span> <span data-ttu-id="ce536-135">Щелкните текстовое поле **значение** .</span><span class="sxs-lookup"><span data-stu-id="ce536-135">Click the **Value** text box.</span></span>  
  
11. <span data-ttu-id="ce536-136">В диалоговом окне **Фильтр** в первой строке **столбца структура интеллектуального анализа данных**выберите `Model` .</span><span class="sxs-lookup"><span data-stu-id="ce536-136">In the **Filter** dialog box, in the first row under **Mining Structure Column**, select `Model`.</span></span>  
  
12. <span data-ttu-id="ce536-137">Для **оператора**SELECT не равно **null**.</span><span class="sxs-lookup"><span data-stu-id="ce536-137">For **Operator**, select **IS NOT NULL**.</span></span> <span data-ttu-id="ce536-138">Оставьте текстовое поле **значение** пустым.</span><span class="sxs-lookup"><span data-stu-id="ce536-138">Leave the **Value** text box blank.</span></span> <span data-ttu-id="ce536-139">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce536-139">Click **OK**.</span></span>  
  
     <span data-ttu-id="ce536-140">Условие фильтра в текстовом поле **выражение** диалогового окна **Фильтр модели** автоматически обновляется для включения нового условия во вложенную таблицу.</span><span class="sxs-lookup"><span data-stu-id="ce536-140">The filter condition in the **Expression** text box of the **Model Filter** dialog box is automatically updated to include the new condition on the nested table.</span></span> <span data-ttu-id="ce536-141">Законченное выражение выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ce536-141">The completed expression is as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate' AND EXISTS SELECT * FROM [vAssocSeqLineItems] WHERE [Model] <> NULL).`  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)] ``  
  
#### <a name="to-enable-drillthrough-and-to-process-the-filtered-model"></a><span data-ttu-id="ce536-142">Включение детализации и обработка отфильтрованной модели</span><span class="sxs-lookup"><span data-stu-id="ce536-142">To enable drillthrough and to process the filtered model</span></span>  
  
1.  <span data-ttu-id="ce536-143">На вкладке **модели интеллектуального анализа данных** щелкните правой кнопкой мыши `Association Filtered` модель и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ce536-143">In the **Mining Models** tab, right-click the `Association Filtered` model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ce536-144">Измените значение свойства **AllowDrillthrough** на **true**.</span><span class="sxs-lookup"><span data-stu-id="ce536-144">Change the **AllowDrillThrough** property to **True**.</span></span>  
  
3.  <span data-ttu-id="ce536-145">Щелкните правой кнопкой мыши `Association Filtered` модель интеллектуального анализа данных и выберите команду **обработать модель**.</span><span class="sxs-lookup"><span data-stu-id="ce536-145">Right-click the `Association Filtered` mining model, and select **Process Model**.</span></span>  
  
4.  <span data-ttu-id="ce536-146">Нажмите кнопку **Да** в сообщении об ошибке, чтобы развернуть новую модель в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="ce536-146">Click **Yes** in the error message to deploy the new model to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
5.  <span data-ttu-id="ce536-147">В диалоговом окне **Обработка структуры интеллектуального анализа данных** нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ce536-147">In the **Process Mining Structure** dialog box, click **Run**.</span></span>  
  
6.  <span data-ttu-id="ce536-148">После завершения обработки нажмите кнопку **Закрыть** , чтобы выйти из диалогового окна **Ход обработки** , и нажмите кнопку **Закрыть** еще раз, чтобы закрыть диалоговое окно **Обработка структуры интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="ce536-148">When processing is complete click **Close** to exit the **Process Progress** dialog box, and click **Close** again to exit the **Process Mining Structure** dialog box.</span></span>  
  
 <span data-ttu-id="ce536-149">Чтобы убедиться в том, что отфильтрованная модель содержит меньше вариантов, чем исходная модель, проверьте значение параметра NODE_SUPPORT в средстве просмотра деревьев содержимого общего вида (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="ce536-149">You can verify by using the Microsoft Generic Content Tree viewer and looking at the value for NODE_SUPPORT that the filtered model contains fewer cases than the original model.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce536-150">Remarks</span><span class="sxs-lookup"><span data-stu-id="ce536-150">Remarks</span></span>  
 <span data-ttu-id="ce536-151">Только что созданный фильтр вложенной таблицы проверяет лишь наличие по крайней мере одной строки во вложенной таблице. Также можно создать условия фильтра для проверки наличия конкретных продуктов.</span><span class="sxs-lookup"><span data-stu-id="ce536-151">The nested table filter that you just created checks only for the presence of at least one row in the nested table; however, you can also create filter conditions that check for the presence of specific products.</span></span>  <span data-ttu-id="ce536-152">Например, можно создать следующий фильтр:</span><span class="sxs-lookup"><span data-stu-id="ce536-152">For example, you could create the following filter:</span></span>  
  
```  
[IncomeGroup] = 'High' AND  
 EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] = 'Water Bottle' )   
```  
  
 <span data-ttu-id="ce536-153">Данная инструкция означает, что клиенты из таблицы вариантов будут ограничены лишь теми клиентами, которые приобрели флягу для воды.</span><span class="sxs-lookup"><span data-stu-id="ce536-153">This statement means that you are restricting the customers from the case table to only those who have purchased a water bottle.</span></span> <span data-ttu-id="ce536-154">Количество атрибутов вложенной таблицы потенциально может быть неограниченным, поэтому службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] не предоставляют список возможных значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="ce536-154">However, because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="ce536-155">Вместо этого необходимо вводить точное значение.</span><span class="sxs-lookup"><span data-stu-id="ce536-155">Instead, you must type the exact value.</span></span>  
  
 <span data-ttu-id="ce536-156">Можно нажать кнопку **изменить запрос** , чтобы вручную изменить критерий фильтра.</span><span class="sxs-lookup"><span data-stu-id="ce536-156">You can click **Edit Query** to manually change the filter expression.</span></span> <span data-ttu-id="ce536-157">Однако если какая-либо часть критерия фильтра изменяется вручную, сетка становится недоступной и работать с выражением фильтра в дальнейшем можно только в режиме изменения текста.</span><span class="sxs-lookup"><span data-stu-id="ce536-157">However, if you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="ce536-158">Чтобы снова перейти в режим изменения с помощью сетки, необходимо очистить критерий фильтра и начать сначала.</span><span class="sxs-lookup"><span data-stu-id="ce536-158">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ce536-159">В фильтре для вложенной таблицы нельзя использовать оператор LIKE.</span><span class="sxs-lookup"><span data-stu-id="ce536-159">You cannot use the LIKE operator in a nested table filter.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ce536-160">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="ce536-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ce536-161">Учебник по прогнозированию взаимосвязей &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ce536-161">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce536-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce536-162">See Also</span></span>  
 <span data-ttu-id="ce536-163">[Синтаксис и примеры фильтров моделей &#40;Analysis Services — интеллектуальный анализ данных&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ce536-163">[Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="ce536-164">Фильтры для моделей интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="ce536-164">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
