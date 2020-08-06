---
title: Применение фильтра к модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filters [data mining]
- filtering input rows [Analysis Services]
- filtering data [Analysis Services]
ms.assetid: 4d0abeb5-e939-46d3-9097-6e0358244300
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9f3147c36e69d9c2249d5bf6d1ba201799c6e27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666279"
---
# <a name="apply-a-filter-to-a-mining-model"></a><span data-ttu-id="17735-102">Применение фильтра к модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="17735-102">Apply a Filter to a Mining Model</span></span>
  <span data-ttu-id="17735-103">Если структура интеллектуального анализа данных содержит вложенную таблицу, можно применить фильтр к таблице вариантов, вложенной таблице или к обеим таблицам.</span><span class="sxs-lookup"><span data-stu-id="17735-103">If your mining structure contains a nested table, you can apply a filter to the case table, the nested table, or both.</span></span>  
  
 <span data-ttu-id="17735-104">Следующая процедура демонстрирует создание обоих видов фильтров: фильтров вариантов и фильтров строк вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="17735-104">The following procedure demonstrates how to create both kinds of filters: case filters, and filters on the nested table rows.</span></span>  
  
 <span data-ttu-id="17735-105">Условие для таблицы вариантов выбирает клиентов, имеющих доход от 30 000 до 40 000.</span><span class="sxs-lookup"><span data-stu-id="17735-105">The condition on the case table restricts customers to those with income between 30000 and 40000.</span></span> <span data-ttu-id="17735-106">Условие для вложенной таблицы выбирает клиентов, которые не приобрели какой-то конкретный товар.</span><span class="sxs-lookup"><span data-stu-id="17735-106">The condition on the nested table restricts the customers to those who did not purchase a particular item.</span></span>  
  
 <span data-ttu-id="17735-107">Полное условие фильтра, созданное в этом примере, выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="17735-107">The complete filter condition created in this example is as follows:</span></span>  
  
```  
[Income] > '30000'   
AND  [Income] < '40000'   
AND EXISTS (SELECT * FROM [<nested table name>]   
WHERE [Model] <> 'Water Bottle' )   
```  
  
### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="17735-108">Создание фильтра вариантов в модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="17735-108">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="17735-109">В обозревателе решений [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]щелкните структуру интеллектуального анализа данных, содержащую ту модель интеллектуального анализа данных, к которой нужно применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="17735-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="17735-110">Перейдите на вкладку **Модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="17735-110">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="17735-111">Выберите модель и щелкните правой кнопкой мыши, чтобы открыть контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="17735-111">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="17735-112">-или-</span><span class="sxs-lookup"><span data-stu-id="17735-112">-or-</span></span>  
  
     <span data-ttu-id="17735-113">Выберите модель.</span><span class="sxs-lookup"><span data-stu-id="17735-113">Select the model.</span></span> <span data-ttu-id="17735-114">Затем в меню **Модель интеллектуального анализа данных** выберите команду **Настроить фильтр моделей**.</span><span class="sxs-lookup"><span data-stu-id="17735-114">Then, on the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="17735-115">В диалоговом окне **Фильтр модели** щелкните верхнюю строку сетки в текстовом поле **Столбец структуры интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="17735-115">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
5.  <span data-ttu-id="17735-116">Если источник данных содержит единственную плоскую таблицу, в раскрывающемся списке отображаются только имена столбцов этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="17735-116">If the data source contains a single flat table, the drop-down list displays only the names of the columns in that table.</span></span>  
  
     <span data-ttu-id="17735-117">Если структура интеллектуального анализа данных содержит несколько таблиц, то в списке отображаются имена этих исходных таблиц.</span><span class="sxs-lookup"><span data-stu-id="17735-117">If the mining structure contains multiple tables, the list shows the names of the source tables.</span></span> <span data-ttu-id="17735-118">Имена столбцов не отображаются до тех пор, пока не будет выбрана таблица.</span><span class="sxs-lookup"><span data-stu-id="17735-118">The column names do not display until a table has been selected.</span></span>  
  
     <span data-ttu-id="17735-119">Если структура интеллектуального анализа данных содержит таблицу вариантов и вложенную таблицу, то в раскрывающемся списке отображаются столбцы из таблицы вариантов и имя вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="17735-119">If the mining structure contains a case table and a nested table, the drop-down list shows columns from the case table, and the name of the nested table.</span></span>  
  
6.  <span data-ttu-id="17735-120">Выберите столбец из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="17735-120">Select a column from the drop-down list.</span></span>  
  
     <span data-ttu-id="17735-121">Значок слева от текстового поля изменится, указывая, что выбранным элементом является таблица или столбец.</span><span class="sxs-lookup"><span data-stu-id="17735-121">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
7.  <span data-ttu-id="17735-122">Щелкните текстовое поле **Оператор** и выберите оператор из списка.</span><span class="sxs-lookup"><span data-stu-id="17735-122">Click the **Operator** text box and select an operator from the list.</span></span> <span data-ttu-id="17735-123">Перечень допустимых операторов зависит от типа данных выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="17735-123">The valid operators change depending on the data type of the column you selected.</span></span>  
  
8.  <span data-ttu-id="17735-124">Щелкните текстовое поле **Значение** и введите значение в поле.</span><span class="sxs-lookup"><span data-stu-id="17735-124">Click the **Value** text box, and type a value in the box.</span></span>  
  
     <span data-ttu-id="17735-125">Например, выберите в `Income` качестве столбца, выберите оператор "больше" (>), а затем введите `30000` .</span><span class="sxs-lookup"><span data-stu-id="17735-125">For example, select `Income` as the column, select the greater than operator (>), and then type `30000`.</span></span>  
  
9. <span data-ttu-id="17735-126">Щелкните следующую строку сетки.</span><span class="sxs-lookup"><span data-stu-id="17735-126">Click the next row in the grid.</span></span>  
  
     <span data-ttu-id="17735-127">Созданное условие фильтра автоматически добавится к содержимому текстового поля «Выражение».</span><span class="sxs-lookup"><span data-stu-id="17735-127">The filter condition that you created is automatically added to the Expression text box.</span></span> <span data-ttu-id="17735-128">Например `[Income] > '30000'`.</span><span class="sxs-lookup"><span data-stu-id="17735-128">For example, `[Income] > '30000'`</span></span>  
  
10. <span data-ttu-id="17735-129">Щелкните текстовое поле **AND/OR** в следующей строке сетки, чтобы добавить условие.</span><span class="sxs-lookup"><span data-stu-id="17735-129">Click the **AND/OR** text box in the next row of the grid to add a condition.</span></span>  
  
     <span data-ttu-id="17735-130">Например, чтобы создать условие между, выберите `AND` из раскрывающегося списка логических операндов.</span><span class="sxs-lookup"><span data-stu-id="17735-130">For example, to create a BETWEEN condition, select `AND` from the drop-down list of logical operands.</span></span>  
  
11. <span data-ttu-id="17735-131">Выберите оператор и введите значение, как описано в шагах 7 и 8.</span><span class="sxs-lookup"><span data-stu-id="17735-131">Select an operator and type a value as described in Steps 7 and 8.</span></span>  
  
     <span data-ttu-id="17735-132">Например, выберите в `Income` качестве столбца еще раз, выберите оператор «меньше» (<), а затем введите `40000` .</span><span class="sxs-lookup"><span data-stu-id="17735-132">For example, select `Income` as the column again, select the less than operator (<), and then type `40000`.</span></span>  
  
12. <span data-ttu-id="17735-133">Щелкните следующую строку сетки.</span><span class="sxs-lookup"><span data-stu-id="17735-133">Click the next row in the grid.</span></span>  
  
13. <span data-ttu-id="17735-134">Условие фильтра в текстовом поле «Выражение» автоматически обновится, чтобы включить новое условие.</span><span class="sxs-lookup"><span data-stu-id="17735-134">The filter condition in the Expression text box is automatically updated to include the new condition.</span></span> <span data-ttu-id="17735-135">Законченное выражение выглядит следующим образом: `[Income] > '30000'AND [Income] < '40000'`</span><span class="sxs-lookup"><span data-stu-id="17735-135">The completed expression is as follows: `[Income] > '30000'AND [Income] < '40000'`</span></span>  
  
### <a name="to-add-a-filter-on-the-nested-table-in-a-mining-model"></a><span data-ttu-id="17735-136">Добавление фильтра к вложенной таблице в модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="17735-136">To add a filter on the nested table in a mining model</span></span>  
  
1.  <span data-ttu-id="17735-137">В диалоговом окне \*\* \<name> Фильтр модели\*\* щелкните пустую строку в сетке в **столбце структура интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="17735-137">In the **\<name>Model Filter** Dialog box, click an empty row in the grid under **Mining Structure Column**.</span></span>  
  
2.  <span data-ttu-id="17735-138">Выберите имя вложенной таблицы из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="17735-138">Select the name of the nested table from the drop-down list.</span></span>  
  
     <span data-ttu-id="17735-139">Значок в левой стороне текстового поля изменится, указывая, что выбранным элементом является имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="17735-139">The icon at the left side of the text box changes to indicate that the selected item is the name of a table.</span></span>  
  
3.  <span data-ttu-id="17735-140">Щелкните текстовое поле **Оператор** и выберите **Содержит** или **Не содержит**.</span><span class="sxs-lookup"><span data-stu-id="17735-140">Click the **Operator** text box and select **Contains** or **Not Contain**.</span></span>  
  
     <span data-ttu-id="17735-141">В диалоговом окне **Фильтр модели** для вложенной таблицы доступны только эти условия, поскольку таблица вариантов ограничена вариантами, содержащими определенное значение во вложенной таблице.</span><span class="sxs-lookup"><span data-stu-id="17735-141">These are the only conditions available for the nested table in the **Model Filter** dialog box, because you are restricting the case table to only those cases that contain a certain value in the nested table.</span></span> <span data-ttu-id="17735-142">Значение условия для вложенной таблицы будет задано в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="17735-142">You will set the value for the condition on the nested table in the next step.</span></span>  
  
4.  <span data-ttu-id="17735-143">Щелкните поле **значение** и нажмите кнопку **(...)** , чтобы создать выражение.</span><span class="sxs-lookup"><span data-stu-id="17735-143">Click the **Value** box, and then click the **(...)** button to build an expression.</span></span>  
  
     <span data-ttu-id="17735-144">Откроется диалоговое окно \*\* \<name> Фильтр\*\* .</span><span class="sxs-lookup"><span data-stu-id="17735-144">The **\<name>Filter** dialog box opens.</span></span> <span data-ttu-id="17735-145">Это диалоговое окно позволяет задавать условия только для текущей таблицы, которая в данном случае является вложенной таблицей.</span><span class="sxs-lookup"><span data-stu-id="17735-145">This dialog box can set conditions only on the current table, which in this case is the nested table.</span></span>  
  
5.  <span data-ttu-id="17735-146">Щелкните поле **Столбец структуры интеллектуального анализа данных** и выберите имя столбца из раскрывающихся списков столбцов вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="17735-146">Click the **Mining Structure Column** box and select a column name from the dropdown lists of nested table columns.</span></span>  
  
6.  <span data-ttu-id="17735-147">Нажмите текстовое поле **Оператор** и выберите оператор из списка допустимых операторов для столбца.</span><span class="sxs-lookup"><span data-stu-id="17735-147">Click **Operator** and select an operator from the list of valid operators for the column.</span></span>  
  
7.  <span data-ttu-id="17735-148">Щелкните поле **Значение** и введите значение.</span><span class="sxs-lookup"><span data-stu-id="17735-148">Click **Value** and type a value.</span></span>  
  
     <span data-ttu-id="17735-149">Например, для **столбца структура интеллектуального анализа данных** выберите `Model` .</span><span class="sxs-lookup"><span data-stu-id="17735-149">For example, for **Mining Structure Column,** select `Model`.</span></span> <span data-ttu-id="17735-150">В поле **оператор**выберите `<>` и введите значение `Water Bottle` .</span><span class="sxs-lookup"><span data-stu-id="17735-150">For **Operator**, select `<>`, and type the value `Water Bottle`.</span></span> <span data-ttu-id="17735-151">Это условие приведет к созданию следующего критерия фильтра:</span><span class="sxs-lookup"><span data-stu-id="17735-151">This condition creates the following filter expression:</span></span>  
  
```  
EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] <> 'Water Bottle' )   
```  
  
> [!NOTE]  
>  <span data-ttu-id="17735-152">Количество атрибутов вложенной таблицы потенциально может быть неограниченным, поэтому службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не предоставляют список возможных значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="17735-152">Because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="17735-153">Необходимо вводить точное значение.</span><span class="sxs-lookup"><span data-stu-id="17735-153">You must type the exact value.</span></span> <span data-ttu-id="17735-154">Кроме того, во вложенной таблице не может использоваться оператор LIKE.</span><span class="sxs-lookup"><span data-stu-id="17735-154">Also, you cannot use a LIKE operator in a nested table.</span></span>  
  
1.  <span data-ttu-id="17735-155">При необходимости добавьте дополнительные условия, объединив условия, выбрав `AND` или `OR` в поле или **/или** в левой части сетки **условий** .</span><span class="sxs-lookup"><span data-stu-id="17735-155">Add more conditions as necessary, combining the conditions by selecting `AND` or `OR` in the **AND/OR** box at the left side of the **Conditions** grid.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="17735-156">В диалоговом окне **Фильтр модели** просмотрите созданные условия с помощью диалогового окна **Фильтр** .</span><span class="sxs-lookup"><span data-stu-id="17735-156">In the **Model Filter** dialog box, review the conditions that you created by using the **Filter** dialog box.</span></span> <span data-ttu-id="17735-157">Условия для вложенной таблицы добавляются к условиям таблицы вариантов, а неполный набор условий фильтра отображается в текстовом поле **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="17735-157">The conditions for the nested table are appended to the conditions for the case table, and the complete set of filter conditions is displayed in the **Expression** text box.</span></span>  
  
3.  <span data-ttu-id="17735-158">Можно также дополнительно нажать кнопку **Изменить запрос** и вручную изменить критерий фильтра.</span><span class="sxs-lookup"><span data-stu-id="17735-158">Optionally, click **Edit Query** to manually change the filter expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="17735-159">Если какая-либо часть критерия фильтра изменена вручную, то сетка становится недоступной и работать с выражением фильтра в дальнейшем можно только в режиме изменения текста.</span><span class="sxs-lookup"><span data-stu-id="17735-159">If you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="17735-160">Чтобы снова перейти в режим изменения с помощью сетки, необходимо очистить критерий фильтра и начать сначала.</span><span class="sxs-lookup"><span data-stu-id="17735-160">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="17735-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="17735-161">See Also</span></span>  
 <span data-ttu-id="17735-162">[Фильтры для моделей интеллектуального анализа данных &#40;Analysis Services интеллектуального анализа&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="17735-162">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="17735-163">[Задачи и инструкции по модели интеллектуального анализа данных](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="17735-163">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="17735-164">удалить фильтр из модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="17735-164">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
