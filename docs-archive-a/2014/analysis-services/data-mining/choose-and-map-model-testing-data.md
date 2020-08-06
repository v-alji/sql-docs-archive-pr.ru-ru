---
title: Выбор и сопоставьте данные тестирования модели | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining accuracy charts
- Mining Accuracy Chart [Analysis Services], column mappings
- input column mapping [Analysis Services]
- mapping input columns [Analysis Services]
ms.assetid: be0d9f20-40c3-4dac-81da-281cfe724126
author: minewiskan
ms.author: owend
ms.openlocfilehash: 84f1d01c40070069d610bb028ab003223c5afbcd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658559"
---
# <a name="choose-and-map-model-testing-data"></a><span data-ttu-id="ff3ec-102">Выбрать и сопоставить данные проверки модели</span><span class="sxs-lookup"><span data-stu-id="ff3ec-102">Choose and Map Model Testing Data</span></span>
  <span data-ttu-id="ff3ec-103">Чтобы создать диаграмму точности прогнозов в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], необходимо выбрать данные, которые будут использоваться для проверки модели, и сопоставить эти данные с моделью.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-103">To create an accuracy chart in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must choose the data that will be used to test the model, and map the data to the model.</span></span>  
  
 <span data-ttu-id="ff3ec-104">По умолчанию в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] будут использоваться проверочные данные модели интеллектуального анализа данных, если при создании структуры интеллектуального анализа данных был создан набор контрольных данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-104">By default, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will use the mining model testing data, provided that you created a holdout data set when you built the mining structure.</span></span> <span data-ttu-id="ff3ec-105">Создание набора контрольных данных — самый простой способ проверки моделей на основе одной структуры интеллектуального анализа данных, поскольку имена столбцов и типы данных всегда будут совпадать с моделью и можно быть достаточно уверенным в том, что распределение данных будет аналогичным.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-105">Creating a holdout test set is the easiest way to test models that are based on the same mining structure, because the column names and data types will always match the model, and you can be reasonably assured that the distribution of the data is similar.</span></span> <span data-ttu-id="ff3ec-106">Кроме того, конструктор автоматически создает связи между входом и столбцами модели.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-106">Also, the designer will automatically create the relationships between the input and model columns.</span></span>  
  
 <span data-ttu-id="ff3ec-107">Иначе можно указать внешний источник данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-107">Alternatively, you can specify an external source of data.</span></span> <span data-ttu-id="ff3ec-108">Для внешних данных существуют некоторые дополнительные требования.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-108">For external data, there are some additional requirements:</span></span>  
  
-   <span data-ttu-id="ff3ec-109">Набор внешних данных должен быть определен как представление источника данных в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff3ec-109">The external data set must be defined as a data source view in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="ff3ec-110">Во внешнем наборе данных должен содержаться по крайней мере один столбец, который можно сопоставить с прогнозируемым столбцом в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-110">The external data set must at least contain one column that can be mapped to the predictable column in the mining model.</span></span> <span data-ttu-id="ff3ec-111">Можно не учитывать некоторые столбцы.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-111">You can choose to ignore some columns.</span></span>  
  
-   <span data-ttu-id="ff3ec-112">Нельзя добавлять новые столбцы или сопоставлять столбцы из другого представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-112">You cannot add new columns or map columns in a different data source view.</span></span> <span data-ttu-id="ff3ec-113">Выбранное представление источника данных должно содержать все столбцы, необходимые для прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-113">The data source view that you select must contain all the columns that you need for the prediction query.</span></span>  
  
-   <span data-ttu-id="ff3ec-114">Если имена внешних столбцов в точности совпадают с именами в модели, конструктор автоматически выполнит сопоставление.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-114">If the external column names exactly match those in the model, the designer will map them for you.</span></span> <span data-ttu-id="ff3ec-115">Если сопоставление неправильное, можно изменить их либо удалить и создать новые привязки для существующих столбцов.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-115">If the mappings are wrong, you can change them, or delete and create new mappings for existing columns.</span></span>  
  
-   <span data-ttu-id="ff3ec-116">Если использовать внешний источник данных, можно применять фильтры для ограничения проверочных данных релевантным подмножеством вариантов.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-116">If you use an external data source, you can apply filters to restrict the testing data to a relevant subset of cases.</span></span>  
  
-   <span data-ttu-id="ff3ec-117">Даже при использовании набора контрольных данных следует иметь в виду, что фильтры могут вызывать различия между проверочными данными, связанными со структурой интеллектуального анализа данных, и проверочными вариантами модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-117">Even when you use the holdout test set, you should be aware that filters can cause differences between the testing data associated with a mining structure and the mining model test cases.</span></span>  
  
 <span data-ttu-id="ff3ec-118">В разделе описан выбор и сопоставление проверочных данных:</span><span class="sxs-lookup"><span data-stu-id="ff3ec-118">This topic describes how to choose and map the testing data:</span></span>  
  
 [<span data-ttu-id="ff3ec-119">Выбор входных таблиц для проверки точности модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ff3ec-119">Select input tables to test the accuracy of a mining model</span></span>](#bkmk_SelectInputs)  
  
 [<span data-ttu-id="ff3ec-120">Сопоставление столбцов модели со столбцами проверочных данных</span><span class="sxs-lookup"><span data-stu-id="ff3ec-120">Map model columns to the columns in the testing data</span></span>](#bkmk_MapColumns)  
  
 [<span data-ttu-id="ff3ec-121">Изменение способа сопоставления столбцов в проверочных данных с моделью</span><span class="sxs-lookup"><span data-stu-id="ff3ec-121">Change the way that columns in the testing data are mapped to the model</span></span>](#bkmk_ChangeMappings)  
  
##  <a name="to-select-input-tables-to-test-the-accuracy-of-a-mining-model"></a><a name="bkmk_SelectInputs"></a> <span data-ttu-id="ff3ec-122">Выбор входных таблиц для проверки точности модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ff3ec-122">To select input tables to test the accuracy of a mining model</span></span>  
  
1.  <span data-ttu-id="ff3ec-123">В конструкторе интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]дважды щелкните структуру интеллектуального анализа данных, которая содержит модели для диаграммы.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-123">In Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="ff3ec-124">Перейдите на вкладку **Диаграмма точности интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="ff3ec-125">На вкладке **Выбор входа** представления **Диаграмма точности интеллектуального анализа** выберите один из приведенных ниже параметров:</span><span class="sxs-lookup"><span data-stu-id="ff3ec-125">On the **Input Selection Tab** of the **Mining Accuracy Chart** view, select one of the following options:</span></span>  
  
     <span data-ttu-id="ff3ec-126">**Использовать проверочные варианты модели интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="ff3ec-126">**Use mining model test cases**</span></span>  
  
     <span data-ttu-id="ff3ec-127">**Использовать проверочные варианты структуры интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="ff3ec-127">**Use mining structure test cases**</span></span>  
  
     <span data-ttu-id="ff3ec-128">**Задать другой набор данных**</span><span class="sxs-lookup"><span data-stu-id="ff3ec-128">**Specify a different data set**</span></span>  
  
4.  <span data-ttu-id="ff3ec-129">Если был выбран вариант **Задать другой набор данных**, то при необходимости можно создать критерии фильтра для входного набора данных. Для этого выберите команду **Открыть редактор фильтров** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-129">If you selected **Specify a different data set**, optionally click **Open Filter Editor** to create filter conditions on the input data set.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="ff3ec-130">Перейдите на вкладку **Диаграмма точности прогнозов** или **Матрица классификации** для автоматического построения диаграммы с использованием только что указанных проверочных данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-130">Click the **Lift Chart** tab or the **Classification Matrix** tab to automatically build the chart by using the testing data you specified.</span></span>  
  
##  <a name="to-map-model-columns-to-the-columns-in-the-testing-data"></a><a name="bkmk_MapColumns"></a> <span data-ttu-id="ff3ec-131">Сопоставление столбцов модели со столбцами проверочных данных</span><span class="sxs-lookup"><span data-stu-id="ff3ec-131">To map model columns to the columns in the testing data</span></span>  
  
1.  <span data-ttu-id="ff3ec-132">Дважды щелкните структуру интеллектуального анализа данных, содержащую модели, для которых необходимо построить диаграммы, чтобы открыть эти структуры и модели в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-132">Double-click the mining structure that contains the models you want to chart, to open the structure and models in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="ff3ec-133">Перейдите на вкладку **Диаграмма точности интеллектуального анализа** , а затем на вкладку **Выбор входных данных** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-133">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="ff3ec-134">На вкладке **Выбор входа** в области **Выбор набора данных для диаграммы точности**выберите параметр **Задать другой набор данных**.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-134">In the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="ff3ec-135">Нажмите кнопку обзора **(...)** , чтобы открыть диалоговое окно и построить определение внешнего набора данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-135">Click the browse button **(...)** to open a dialog box and build the definition of the external data set.</span></span>  
  
5.  <span data-ttu-id="ff3ec-136">В диалоговом окне **Выбор структуры интеллектуального анализа данных** выберите структуру интеллектуального анализа данных, которая содержит модели, с которыми необходимо работать, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-136">In the **Select Mining Structure** dialog box, select the mining structure that contains the models you want to work with, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="ff3ec-137">В таблице **Выбор входных таблиц** вкладки **Диаграмма точности интеллектуального анализа данных** нажмите кнопку **Выбор таблицы вариантов** , чтобы открыть диалоговое окно **Выбор таблицы** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-137">On the **Select Input Table(s)** table of the **Mining Accuracy Chart** tab, click **Select Case Table** to open the **Select Table** dialog box.</span></span>  
  
7.  <span data-ttu-id="ff3ec-138">В диалоговом окне **Выбор таблицы** выберите источник данных из списка **Источник данных** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-138">In the **Select Table** dialog box, select a data source from the **Data Source** list.</span></span> <span data-ttu-id="ff3ec-139">Выберите таблицу с данными, которые необходимо использовать в запросах для определения точности моделей.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-139">Choose a table that contains the data that you want to use in the prediction queries to determine the accuracy of the models.</span></span>  
  
8.  <span data-ttu-id="ff3ec-140">В поле **Имя таблицы или представления** выберите таблицу, содержащую данные, с помощью которых нужно проверить модели.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-140">In the **Table/View Name** box, select the table that contains the data that you want to use to test the models.</span></span>  
  
9. <span data-ttu-id="ff3ec-141">При необходимости измените сопоставления.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-141">Edit the mappings, if necessary.</span></span> <span data-ttu-id="ff3ec-142">Столбцы в структуре интеллектуального анализа данных автоматически сопоставляются со столбцами входной таблицы, имеющими те же имена.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-142">Columns in the mining structure are automatically mapped to the columns with the same name in the input table.</span></span> <span data-ttu-id="ff3ec-143">Чтобы создать сопоставления вручную, щелкните столбец в таблице **Выбор входных таблиц** и перетащите его на соответствующий столбец в таблице **Структура интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-143">To manually create mappings, click a column in the **Select Input Table(s)** table and drag it onto the corresponding column in the **Mining Structure** table.</span></span> <span data-ttu-id="ff3ec-144">Чтобы удалить сопоставление, щелкните линию, связывающую столбец таблицы **Структура интеллектуального анализа данных** с сопоставленным столбцом таблицы **Выбор входных таблиц** , а затем нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-144">To delete a mapping, click the line that links the column in the **Mining Structure** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="to-modify-the-way-input-data-is-mapped-to-the-model"></a><a name="bkmk_ChangeMappings"></a><span data-ttu-id="ff3ec-145">Изменение способа сопоставления входных данных с моделью</span><span class="sxs-lookup"><span data-stu-id="ff3ec-145">To modify the way input data is mapped to the model</span></span>  
  
1.  <span data-ttu-id="ff3ec-146">В конструкторе интеллектуального анализа данных дважды щелкните структуру, содержащую модели, для которых необходимо построить диаграммы.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-146">In Data Mining Designer, double-click the structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="ff3ec-147">Перейдите на вкладку **Диаграмма точности интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-147">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="ff3ec-148">Перейдите на вкладку **Выбор входа** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-148">Click the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="ff3ec-149">На **диаграмме выбор набора данных, используемого для диаграммы точности**, выберите параметр **указать другой набор данных**.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-149">In **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
5.  <span data-ttu-id="ff3ec-150">Нажмите кнопку обзора **(...)** , чтобы открыть диалоговое окно и построить определение внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-150">Click the browse button **(...)** to open a dialog box and build the definition of the external data source.</span></span>  
  
6.  <span data-ttu-id="ff3ec-151">В диалоговом окне **Укажите сопоставление столбцов** нажмите кнопку **Выбор таблицы вариантов**.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-151">In the **Specify Column Mapping** dialog box, click **Select Case Table**.</span></span>  
  
7.  <span data-ttu-id="ff3ec-152">В диалоговом окне «Выбор таблицы», выберите из списка источник данных, а затем выберите таблицу, содержащую данные вариантов.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-152">In the Select Table dialog box, Select a data source view from the list, and select the table that contains the case data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="ff3ec-153">Если необходимые таблицы недоступны, то следует закрыть диалоговое окно и создать новое представление источника данных, содержащее таблицу.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-153">If the tables you need are not available, close the dialog box and create a new data source view that contains the table.</span></span> <span data-ttu-id="ff3ec-154">Дополнительные сведения о создании представления источников данных см. в разделе [Определение представления источников данных (службы Analysis Services)](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ec-154">For information about how to create a data source view, see [Defining a Data Source View &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span></span>  
  
9. <span data-ttu-id="ff3ec-155">Если в модели интеллектуального анализа данных содержится вложенная таблица, нажмите кнопку **Выбор вложенной таблицы**и выберите необходимую вложенную таблицу из списка таблиц в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-155">If the mining model contains a nested table, click **Select Nested Table**, and select the nested table from the list of tables in the data source view.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="ff3ec-156">Выберите линию соединения сопоставления, которое нужно изменить, а затем команду **Изменение соединений**.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-156">Select the join line of the mapping you want to modify, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="ff3ec-157">Откроется диалоговое окно **Изменение сопоставления** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-157">The **Modify Mapping** dialog box opens.</span></span> <span data-ttu-id="ff3ec-158">В списке **Столбец структуры интеллектуального анализа данных** таблицы данного диалогового окна перечислены все столбцы, содержащиеся в выбранной структуре интеллектуального анализа данных, а в списке **Столбец таблицы** перечислены столбцы из входных таблиц, сопоставленные со столбцами в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-158">In the table in this dialog box, **Mining Structure Column** lists each column that the selected mining structure contains, and **Table Column** lists the columns from input tables that are mapped to columns in the mining structure.</span></span>  
  
11. <span data-ttu-id="ff3ec-159">В списке **Столбец таблицы**выберите строку, соответствующую строке в списке **Столбец структуры интеллектуального анализа данных** , для которой требуется изменить связь.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-159">Under **Table Column**, select the row that corresponds to the row under **Mining Structure Column** for which you want to modify a relationship.</span></span> <span data-ttu-id="ff3ec-160">Выберите новый столбец из списка или выберите пустую запись, чтобы удалить столбец.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-160">Select a new column from the list, or select the blank entry from the list to delete the column.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="ff3ec-161">Новые сопоставления столбцов отображаются в диалоговом окне **Укажите сопоставление столбцов** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-161">The new column mappings are displayed in the **Specify Column Mapping** dialog box.</span></span> <span data-ttu-id="ff3ec-162">Удалить сопоставление можно, выбрав линию между столбцами и нажав клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="ff3ec-162">You can remove a mapping by selecting the line between the columns and pressing the DELETE key.</span></span> <span data-ttu-id="ff3ec-163">Можно создать новое соединение, выбрав столбец в таблице **Структура интеллектуального анализа данных** и перетащив его в соответствующий столбец таблицы **Выбор входных таблиц** .</span><span class="sxs-lookup"><span data-stu-id="ff3ec-163">You can create a new connection by selecting a column in the **Mining Structure** table and dragging it to the corresponding column in the **SelectInput Table(s)** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3ec-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff3ec-164">See Also</span></span>  
 [<span data-ttu-id="ff3ec-165">Задачи и решения по тестированию и проверке (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="ff3ec-165">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
  
