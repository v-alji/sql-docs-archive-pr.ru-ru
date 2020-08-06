---
title: Область конструктора (представление прогноза модели интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.design.f1
ms.assetid: 17f24c8d-43cd-4f4d-83b3-a41ee8fbe8e8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 32ac73a2d6fde38d15d1f45a8439293695749ea4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733277"
---
# <a name="design-pane-mining-model-prediction-view"></a><span data-ttu-id="2931f-102">Панель «Проект» (представление прогноза модели интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="2931f-102">Design Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="2931f-103">Панель **Проект** содержит построитель прогнозирующих запросов, предназначенный для построения прогнозов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2931f-103">The **Design** pane contains the Prediction Query Builder, which you can use to build data mining predictions.</span></span> <span data-ttu-id="2931f-104">Для массовых прогнозов можно создавать запросы с использованием таблиц входных данных из представления источников данных или создавать одноэлементные прогнозирующие запросы, в которых указываются отдельные значения.</span><span class="sxs-lookup"><span data-stu-id="2931f-104">You can design prediction queries that use tables of input data from a data source view, to generate bulk predictions, or you can create singleton prediction queries, which let you provide individual values.</span></span>  
  
 <span data-ttu-id="2931f-105">Чтобы выполнить запрос и просмотреть результаты, переключитесь в представление результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="2931f-105">To run the query and view the results, switch to query result view.</span></span>  
  
 <span data-ttu-id="2931f-106">Представление **Запрос** выводит запрос расширения интеллектуального анализа данных, созданный построителем прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="2931f-106">The **Query** view displays the Data Mining Extensions (DMX) query that Prediction Query Builder creates.</span></span> <span data-ttu-id="2931f-107">Владея языком DMX, можно настроить этот запрос.</span><span class="sxs-lookup"><span data-stu-id="2931f-107">If you are familiar with DMX, you can customize this query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2931f-108">Если в запрос вручную внесены какие-либо изменения, то они будут потеряны при переключении в представление «Проект».</span><span class="sxs-lookup"><span data-stu-id="2931f-108">If you make any manual changes to the query, your changes will be lost when you switch back to Design view.</span></span> <span data-ttu-id="2931f-109">Если нужно сохранить DMX-запрос, то можно скопировать его в буфер обмена Windows, а затем вставить в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="2931f-109">If you want to save the DMX query, you can copy the query to the Windows Clipboard and then paste it to a text file.</span></span>  
  
 <span data-ttu-id="2931f-110">**Дополнительные сведения:** [Запросы интеллектуального анализа данных](data-mining/data-mining-queries.md)</span><span class="sxs-lookup"><span data-stu-id="2931f-110">**For More Information:** [Data Mining Queries](data-mining/data-mining-queries.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="2931f-111">Варианты</span><span class="sxs-lookup"><span data-stu-id="2931f-111">Options</span></span>  
 <span data-ttu-id="2931f-112">**Переключиться в режим просмотра результата запроса**</span><span class="sxs-lookup"><span data-stu-id="2931f-112">**Switch to query result view**</span></span>  
 <span data-ttu-id="2931f-113">Для переключения между панелями щелкните **Проект**, **Запрос**и **Результат** .</span><span class="sxs-lookup"><span data-stu-id="2931f-113">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="2931f-114">При переключении на панель **Результат** происходит выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="2931f-114">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="2931f-115">**Сохранить результат запроса**</span><span class="sxs-lookup"><span data-stu-id="2931f-115">**Save the query result**</span></span>  
 <span data-ttu-id="2931f-116">Открывает диалоговое окно **Сохранение результата запроса интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="2931f-116">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="2931f-117">**Одноэлементный запрос**</span><span class="sxs-lookup"><span data-stu-id="2931f-117">**Singleton query**</span></span>  
 <span data-ttu-id="2931f-118">Позволяет создать одноэлементный запрос, в котором можно напрямую вводить значения для него вместо создания таблицы в качестве источника известных данных.</span><span class="sxs-lookup"><span data-stu-id="2931f-118">Enables creating a singleton query, in which you can provide values directly for the query instead of providing a table as the source of the known data.</span></span> <span data-ttu-id="2931f-119">Таблица **Выбор входных таблиц** заменяется таблицей **Ввод одноэлементного запроса** .</span><span class="sxs-lookup"><span data-stu-id="2931f-119">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span>  
  
 <span data-ttu-id="2931f-120">**Обновить результаты запроса**</span><span class="sxs-lookup"><span data-stu-id="2931f-120">**Refresh query results**</span></span>  
 <span data-ttu-id="2931f-121">Обработать заново прогнозирующий запрос.</span><span class="sxs-lookup"><span data-stu-id="2931f-121">Reprocesses the prediction query.</span></span> <span data-ttu-id="2931f-122">Это возможно только на панели **Результат** .</span><span class="sxs-lookup"><span data-stu-id="2931f-122">This is enabled only in the **Result** pane.</span></span>  
  
 <span data-ttu-id="2931f-123">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="2931f-123">**Mining Model**</span></span>  
 <span data-ttu-id="2931f-124">Отображает выбранную модель интеллектуального анализа данных, на основе которой будет производиться прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="2931f-124">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="2931f-125">**Выбрать модель**</span><span class="sxs-lookup"><span data-stu-id="2931f-125">**Select Model**</span></span>  
 <span data-ttu-id="2931f-126">Открывает диалоговое окно **Выбор модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="2931f-126">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="2931f-127">**Выбор входных таблиц**</span><span class="sxs-lookup"><span data-stu-id="2931f-127">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="2931f-128">Выводит выбранные входные таблицы, содержащие известные данные для выполнения прогнозов.</span><span class="sxs-lookup"><span data-stu-id="2931f-128">Displays the selected input tables that contain known data on which to base the predictions.</span></span>  
  
 <span data-ttu-id="2931f-129">**Удалить таблицу**</span><span class="sxs-lookup"><span data-stu-id="2931f-129">**Delete Table**</span></span>  
 <span data-ttu-id="2931f-130">Удаляет выделенную таблицу.</span><span class="sxs-lookup"><span data-stu-id="2931f-130">Deletes the selected table.</span></span> <span data-ttu-id="2931f-131">Если таблица не была выбрана или не существует, данная кнопка отключена.</span><span class="sxs-lookup"><span data-stu-id="2931f-131">This button is disabled if a table has not been selected or does not exist.</span></span>  
  
 <span data-ttu-id="2931f-132">**Выбрать таблицу вариантов**</span><span class="sxs-lookup"><span data-stu-id="2931f-132">**Select Case Table**</span></span>  
 <span data-ttu-id="2931f-133">Открывает диалоговое окно **Выбор таблицы** .</span><span class="sxs-lookup"><span data-stu-id="2931f-133">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="2931f-134">Данная кнопка появляется, только если таблица вариантов не была выбрана.</span><span class="sxs-lookup"><span data-stu-id="2931f-134">This button appears only if a case table has not been selected.</span></span>  
  
 <span data-ttu-id="2931f-135">**Выбор вложенной таблицы**</span><span class="sxs-lookup"><span data-stu-id="2931f-135">**Select Nested Table**</span></span>  
 <span data-ttu-id="2931f-136">Открывает диалоговое окно **Выбор таблицы** .</span><span class="sxs-lookup"><span data-stu-id="2931f-136">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="2931f-137">Данная кнопка появляется, только если была выбрана таблица вариантов.</span><span class="sxs-lookup"><span data-stu-id="2931f-137">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="2931f-138">Если связанная структура интеллектуального анализа данных не содержит вложенной таблицы, данная кнопка отключена.</span><span class="sxs-lookup"><span data-stu-id="2931f-138">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="2931f-139">**Изменить соединение**</span><span class="sxs-lookup"><span data-stu-id="2931f-139">**Modify Join**</span></span>  
 <span data-ttu-id="2931f-140">Открывает диалоговое окно **Определение вложенного соединения** .</span><span class="sxs-lookup"><span data-stu-id="2931f-140">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="2931f-141">Данная кнопка активна, только если выбрана вложенная таблица.</span><span class="sxs-lookup"><span data-stu-id="2931f-141">This button is active only if the nested table is selected.</span></span>  
  
 <span data-ttu-id="2931f-142">**Ввод одноэлементного запроса**</span><span class="sxs-lookup"><span data-stu-id="2931f-142">**Singleton Query input**</span></span>  
 <span data-ttu-id="2931f-143">Включено при выборе кнопки **Одноэлементный запрос** .</span><span class="sxs-lookup"><span data-stu-id="2931f-143">Enabled when you select the **Singleton query** button.</span></span> <span data-ttu-id="2931f-144">Содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="2931f-144">Contains the following columns:</span></span>  
  
|<span data-ttu-id="2931f-145">Значение</span><span class="sxs-lookup"><span data-stu-id="2931f-145">Value</span></span>|<span data-ttu-id="2931f-146">Описание</span><span class="sxs-lookup"><span data-stu-id="2931f-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2931f-147">**Столбец модели интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="2931f-147">**Mining Model Column**</span></span>|<span data-ttu-id="2931f-148">Выводит список столбцов модели интеллектуального анализа данных, содержащихся в модели, выбранной в таблице **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="2931f-148">Lists the mining model columns contained within the mining model that is selected in the **Mining Model** table.</span></span>|  
|<span data-ttu-id="2931f-149">**Значение**</span><span class="sxs-lookup"><span data-stu-id="2931f-149">**Value**</span></span>|<span data-ttu-id="2931f-150">Выберите значение из списка, содержащего все возможные состояния выбранного столбца модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2931f-150">Select a value from the list that contains each possible state of the selected mining model column.</span></span><br /><br /> <span data-ttu-id="2931f-151">Если столбец является столбцом вложенной таблицы, то щелчком этого значения открывается диалоговое окно **Вход вложенной таблицы** .</span><span class="sxs-lookup"><span data-stu-id="2931f-151">If the column is a nested table column, clicking the value cell opens the **Nested Table Input** dialog box.</span></span>|  
  
 <span data-ttu-id="2931f-152">**Source**</span><span class="sxs-lookup"><span data-stu-id="2931f-152">**Source**</span></span>  
 <span data-ttu-id="2931f-153">Выберите источник, содержащий поле, которое будет использоваться для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="2931f-153">Select the source that contains the field that you will use for the column.</span></span> <span data-ttu-id="2931f-154">Можно использовать либо модель интеллектуального анализа данных, выбранную в таблице **Модель интеллектуального анализа данных** , входную таблицу или таблицы, выбранные в таблице **Выбор входных таблиц** , функцию предсказания, либо пользовательское выражение.</span><span class="sxs-lookup"><span data-stu-id="2931f-154">You can either use the mining model that is selected in the **Mining Model** table, the input table or tables that are selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="2931f-155">Возможно перетаскивание столбцов из таблиц, содержащих модель интеллектуального анализа данных, и из входных таблиц в данную ячейку.</span><span class="sxs-lookup"><span data-stu-id="2931f-155">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
 <span data-ttu-id="2931f-156">**Поле**</span><span class="sxs-lookup"><span data-stu-id="2931f-156">**Field**</span></span>  
 <span data-ttu-id="2931f-157">Выберите столбец из списка столбцов, полученного из исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="2931f-157">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="2931f-158">При выборе значения **Прогнозирующая функция** в поле **Источник**это поле содержит прогнозирующую функцию, доступную для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2931f-158">If you selected **Prediction Function** in **Source**, this contains the prediction function available for the selected mining model.</span></span>  
  
 <span data-ttu-id="2931f-159">**Группа**</span><span class="sxs-lookup"><span data-stu-id="2931f-159">**Group**</span></span>  
 <span data-ttu-id="2931f-160">Используйте со столбцом **И/ИЛИ** для группирования выражений.</span><span class="sxs-lookup"><span data-stu-id="2931f-160">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="2931f-161">Например, `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="2931f-161">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="2931f-162">**И (или)**</span><span class="sxs-lookup"><span data-stu-id="2931f-162">**And/Or**</span></span>  
 <span data-ttu-id="2931f-163">Используйте для создания логического запроса.</span><span class="sxs-lookup"><span data-stu-id="2931f-163">Use to create a logical query.</span></span> <span data-ttu-id="2931f-164">Например, `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="2931f-164">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="2931f-165">**Критерий/Аргумент**</span><span class="sxs-lookup"><span data-stu-id="2931f-165">**Criteria/Argument**</span></span>  
 <span data-ttu-id="2931f-166">Задайте условие или пользовательское выражение, применимое к столбцу.</span><span class="sxs-lookup"><span data-stu-id="2931f-166">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="2931f-167">Возможно перетаскивание столбцов из таблиц, содержащих модель интеллектуального анализа данных, и из входных таблиц в данную ячейку.</span><span class="sxs-lookup"><span data-stu-id="2931f-167">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2931f-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="2931f-168">See Also</span></span>  
 <span data-ttu-id="2931f-169">[Расширения интеллектуального анализа данных &#40;Справочник по инструкции DMX&#41;](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="2931f-169">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 <span data-ttu-id="2931f-170">[Интерфейсы запросов интеллектуального анализа данных](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2931f-170">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="2931f-171">Построитель прогнозирующих запросов (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="2931f-171">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
