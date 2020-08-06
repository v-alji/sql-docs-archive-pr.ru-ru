---
title: Создание прогнозирующего запроса с помощью конструктор запросов прогнозирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- Mining Model Prediction [Analysis Services], prediction queries
ms.assetid: e02836e5-dd8c-4c97-a078-840ae79d3660
author: minewiskan
ms.author: owend
ms.openlocfilehash: 13f39de4085cb74949e9540570d574c09e72ee27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656048"
---
# <a name="create-a-prediction-query-using-the-prediction-query-builder"></a><span data-ttu-id="53f41-102">Создание прогнозирующего запроса с помощью построителя прогнозирующих запросов</span><span class="sxs-lookup"><span data-stu-id="53f41-102">Create a Prediction Query Using the Prediction Query Builder</span></span>
  <span data-ttu-id="53f41-103">Создать прогнозирующий запрос можно при создании решения интеллектуального анализа данных в среде BI Development Studio. Можно также щелкнуть правой кнопкой мыши существующую модель интеллектуального анализа данных в среде SQL Server Management Studio и выбрать параметр **Построить прогнозирующий запрос**.</span><span class="sxs-lookup"><span data-stu-id="53f41-103">You can create prediction queries either while you are building a data mining solution in BI Development Studio, or by right-clicking an existing mining model in SQL Server Management Studio, and then choosing the option, **Build Prediction Query**.</span></span>  
  
 <span data-ttu-id="53f41-104">**Построитель прогнозирующих запросов** имеет три режима конструктора. Для перехода из одного режима в другой используются значки в верхнем левом углу.</span><span class="sxs-lookup"><span data-stu-id="53f41-104">The **Prediction Query Builder** has the following three design modes, which you can switch among by clicking the icons in the upper-left corner.</span></span>  
  
-   <span data-ttu-id="53f41-105">**Оформление**</span><span class="sxs-lookup"><span data-stu-id="53f41-105">**Design**</span></span>  
  
-   <span data-ttu-id="53f41-106">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="53f41-106">**Query**</span></span>  
  
-   <span data-ttu-id="53f41-107">**Результат**</span><span class="sxs-lookup"><span data-stu-id="53f41-107">**Result**</span></span>  
  
 <span data-ttu-id="53f41-108">Режим**конструктора** позволяет создать прогнозирующий запрос, для чего необходимо выбрать входные данные, связать данные с моделью, а затем добавить прогнозирующие функции в инструкции, создаваемые с помощью сетки.</span><span class="sxs-lookup"><span data-stu-id="53f41-108">**Design** mode lets you build a prediction query by choosing input data, mapping the data to the model, and then adding prediction functions into statements you build by using the grid.</span></span> <span data-ttu-id="53f41-109">Сетка конструктора содержит следующие строительные блоки.</span><span class="sxs-lookup"><span data-stu-id="53f41-109">The design grid contains these building blocks:</span></span>  
  
 <span data-ttu-id="53f41-110">**Source**</span><span class="sxs-lookup"><span data-stu-id="53f41-110">**Source**</span></span>  
 <span data-ttu-id="53f41-111">Выберите источник нового столбца.</span><span class="sxs-lookup"><span data-stu-id="53f41-111">Choose the source of the new column.</span></span> <span data-ttu-id="53f41-112">Можно использовать столбцы из модели интеллектуального анализа данных, входных таблиц, включенных в представление источника данных, прогнозирующей функции или пользовательского выражения.</span><span class="sxs-lookup"><span data-stu-id="53f41-112">You can use columns from the mining model, input tables included in the data source view, a prediction function, or a customized expression.</span></span>  
  
 <span data-ttu-id="53f41-113">**Поле**</span><span class="sxs-lookup"><span data-stu-id="53f41-113">**Field**</span></span>  
 <span data-ttu-id="53f41-114">Определяет конкретный столбец или функцию, связанные с элементом, выбранным в столбце **Источник** .</span><span class="sxs-lookup"><span data-stu-id="53f41-114">Determines the specific column or function that is associated with the selection in the **Source** column.</span></span>  
  
 <span data-ttu-id="53f41-115">**Псевдоним**</span><span class="sxs-lookup"><span data-stu-id="53f41-115">**Alias**</span></span>  
 <span data-ttu-id="53f41-116">Определяет, как столбец будет называться в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="53f41-116">Determines how the column is to be named in the result set.</span></span>  
  
 <span data-ttu-id="53f41-117">**Показать**</span><span class="sxs-lookup"><span data-stu-id="53f41-117">**Show**</span></span>  
 <span data-ttu-id="53f41-118">Определяет, отображается ли элемент, выбранный в столбце **Источник** , в результатах.</span><span class="sxs-lookup"><span data-stu-id="53f41-118">Determines whether the selection in the **Source** column is displayed in the results.</span></span>  
  
 <span data-ttu-id="53f41-119">**Группа**</span><span class="sxs-lookup"><span data-stu-id="53f41-119">**Group**</span></span>  
 <span data-ttu-id="53f41-120">Работает со столбцом **и/или** для группирования выражений с использованием скобок.</span><span class="sxs-lookup"><span data-stu-id="53f41-120">Works with the **And/Or** column to group expressions together by using parentheses.</span></span> <span data-ttu-id="53f41-121">Например, (expr1 или expr2) и expr3.</span><span class="sxs-lookup"><span data-stu-id="53f41-121">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="53f41-122">**И (или)**</span><span class="sxs-lookup"><span data-stu-id="53f41-122">**And/Or**</span></span>  
 <span data-ttu-id="53f41-123">Создает логику в запросе.</span><span class="sxs-lookup"><span data-stu-id="53f41-123">Creates logic in the query.</span></span> <span data-ttu-id="53f41-124">Например, (expr1 или expr2) и expr3.</span><span class="sxs-lookup"><span data-stu-id="53f41-124">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="53f41-125">**Критерий/Аргумент**</span><span class="sxs-lookup"><span data-stu-id="53f41-125">**Criteria/Argument**</span></span>  
 <span data-ttu-id="53f41-126">Указывает условие или пользовательское выражение, которое применяется к столбцу.</span><span class="sxs-lookup"><span data-stu-id="53f41-126">Specifies a condition or user expression that applies to the column.</span></span> <span data-ttu-id="53f41-127">Можно перетаскивать столбцы из таблиц в ячейку.</span><span class="sxs-lookup"><span data-stu-id="53f41-127">You can drag columns from the tables to the cell.</span></span>  
  
 <span data-ttu-id="53f41-128">Режим**запросов** предоставляет текстовый редактор, обеспечивающий прямой доступ к языку DMX, а также к представлению входных данных и столбцов модели.</span><span class="sxs-lookup"><span data-stu-id="53f41-128">**Query** mode provides a text editor that gives you direct access to the Data Mining Extensions (DMX) language, along with a view of the input data and model columns.</span></span> <span data-ttu-id="53f41-129">Если выбран режим **запросов** , сетка, которая использовалась для определения запроса, заменяется базовым текстовым редактором.</span><span class="sxs-lookup"><span data-stu-id="53f41-129">When you select **Query** mode, the grid that you used to define the query is replaced by a basic text editor.</span></span> <span data-ttu-id="53f41-130">Этот редактор можно использовать для копирования и сохранения созданных запросов или для вставки существующих DMX-запросов через буфер обмена и выполнения этих запросов.</span><span class="sxs-lookup"><span data-stu-id="53f41-130">You can use this editor to copy and save queries you have composed, or to paste in existing DMX queries and from the Clipboard and run them.</span></span>  
  
 <span data-ttu-id="53f41-131">Представление**результатов** выполняет текущий запрос и показывает результаты в сетке.</span><span class="sxs-lookup"><span data-stu-id="53f41-131">**Result** view runs the current query and displays the results in a grid.</span></span> <span data-ttu-id="53f41-132">Если базовые данные изменились и необходимо выполнить запрос еще раз, нажмите кнопку «Выполнить» в строке состояния.</span><span class="sxs-lookup"><span data-stu-id="53f41-132">If the underlying data has changed and you want to rerun the query, click the Play button in the status bar</span></span>  
  
 <span data-ttu-id="53f41-133">При создании запроса интеллектуального анализа данных можно одновременно использовать и визуальные средства и текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="53f41-133">You can design a data mining query by using a combination of the visual tools and the text editor.</span></span> <span data-ttu-id="53f41-134">Если внести изменения в запрос в текстовом редакторе и вернуться в представление **конструктора** , все изменения будут потеряны и запрос вернется к исходному виду, в котором он был создан построителем прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="53f41-134">If you type changes to the query in the text editor and switch back to the **Design** view, all the changes are lost, and the query reverts to the original query created by Prediction Query Builder This topic walks you through use of the graphical query builder.</span></span>  
  
### <a name="to-create-a-prediction-query"></a><span data-ttu-id="53f41-135">Создание прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="53f41-135">To create a prediction query</span></span>  
  
1.  <span data-ttu-id="53f41-136">Перейдите на вкладку **Прогноз моделей интеллектуального анализа данных** в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="53f41-136">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="53f41-137">Нажмите кнопку **Выбрать модель** в таблице **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="53f41-137">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="53f41-138">Откроется диалоговое окно **Выбор модели интеллектуального анализа данных** со списком всех структур интеллектуального анализа данных, существующих в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="53f41-138">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
3.  <span data-ttu-id="53f41-139">Выберите модель, по которой нужно сделать прогноз, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="53f41-139">Select the model on which you want to create a prediction, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="53f41-140">В окне **Выбор входных таблиц** нажмите кнопку **Выбрать таблицу вариантов**.</span><span class="sxs-lookup"><span data-stu-id="53f41-140">On the **Select Input Table(s)** table, click **Select Case Table**.</span></span>  
  
     <span data-ttu-id="53f41-141">Откроется диалоговое окно **Выбор таблицы** .</span><span class="sxs-lookup"><span data-stu-id="53f41-141">The **Select Table** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="53f41-142">Из списка **Источник данных** выберите источник данных, содержащий данные, на основе которых необходимо создать прогноз.</span><span class="sxs-lookup"><span data-stu-id="53f41-142">In the **Data Source** list, select the data source that contains the data on which to create a prediction.</span></span>  
  
6.  <span data-ttu-id="53f41-143">В поле **Имя таблицы или представления** выберите таблицу, содержащую данные, на основе которых необходимо создать прогноз, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="53f41-143">In the **Table/View Name** box, select the table that contains the data on which to create a prediction, and then click **OK**.</span></span>  
  
     <span data-ttu-id="53f41-144">После выбора входной таблицы в построителе прогнозирующих запросов будет создано сопоставление по умолчанию между моделью интеллектуального анализа данных и таблицей входных данных на основе имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="53f41-144">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="53f41-145">Для удаления сопоставления щелкните кнопкой мыши, чтобы выбрать строку, связывающую столбец в таблице **Модель интеллектуального анализа данных** с сопоставляемым столбцом в таблице **Выбор входных таблиц** , а затем нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="53f41-145">To delete a mapping, click to select the line that links the column in the **Mining Model** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span> <span data-ttu-id="53f41-146">Можно также вручную создать сопоставления, щелкнув столбец в таблице **Выбор входных таблиц** и перетащив его в соответствующий столбец в таблице **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="53f41-146">You can also manually create mappings by clicking a column in the **Select Input Table(s)** table and dragging it onto the corresponding column in the **Mining Model** table.</span></span>  
  
7.  <span data-ttu-id="53f41-147">Добавьте любое сочетание следующих типов данных в сетку построителя прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="53f41-147">Add any combination of the following three types of information to the Prediction Query Builder grid:</span></span>  
  
    -   <span data-ttu-id="53f41-148">Прогнозируемые столбцы из поля **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="53f41-148">Predictable columns from the **Mining Model** box.</span></span>  
  
    -   <span data-ttu-id="53f41-149">Любое сочетание входных столбцов из поля **Выбор входных таблиц** .</span><span class="sxs-lookup"><span data-stu-id="53f41-149">Any combination of input columns from the **Select Input Table(s)** box.</span></span>  
  
    -   <span data-ttu-id="53f41-150">Прогнозирующие функции</span><span class="sxs-lookup"><span data-stu-id="53f41-150">Prediction functions</span></span>  
  
8.  <span data-ttu-id="53f41-151">Запустите запрос, нажав первую кнопку на панели инструментов вкладки **Прогноз моделей интеллектуального анализа данных** , а затем выбрав пункт **Результат**.</span><span class="sxs-lookup"><span data-stu-id="53f41-151">Run the query by clicking the first button on the toolbar of the **Mining Model Prediction** tab, and then selecting **Result**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f41-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="53f41-152">See Also</span></span>  
 <span data-ttu-id="53f41-153">[Создание одноэлементного запроса в конструкторе интеллектуального анализа данных](create-a-singleton-query-in-the-data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="53f41-153">[Create a Singleton Query in the Data Mining Designer](create-a-singleton-query-in-the-data-mining-designer.md) </span></span>  
 [<span data-ttu-id="53f41-154">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="53f41-154">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
