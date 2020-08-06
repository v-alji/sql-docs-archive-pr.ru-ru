---
title: Преобразование "Сведение" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.pivottrans.f1
helpviewer_keywords:
- Pivot transformation
- normalized data [Integration Services]
- PivotUsage property
- datasets [Integration Services], normalized data
- less normalized data set [Integration Services]
ms.assetid: 55f5db6e-6777-435f-8a06-b68c129f8437
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43bdc5be709ea00d4be4601f52c38e96fe3f1ce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752308"
---
# <a name="pivot-transformation"></a><span data-ttu-id="7813c-102">преобразование «Сведение»</span><span class="sxs-lookup"><span data-stu-id="7813c-102">Pivot Transformation</span></span>
  <span data-ttu-id="7813c-103">Преобразование «Сведение» делает нормализованный набор данных менее нормализованным, но более компактным, выполняя сведение входных данных по значению столбца.</span><span class="sxs-lookup"><span data-stu-id="7813c-103">The Pivot transformation makes a normalized data set into a less normalized but more compact version by pivoting the input data on a column value.</span></span> <span data-ttu-id="7813c-104">Например, нормализованный набор данных **Orders** , содержащий имя клиента, продукт и количество приобретенных единиц продукта, обычно содержит множество строк для клиента, купившего несколько наименований продуктов. Каждая строка содержит подробности о различных продуктах.</span><span class="sxs-lookup"><span data-stu-id="7813c-104">For example, a normalized **Orders** data set that lists customer name, product, and quantity purchased typically has multiple rows for any customer who purchased multiple products, with each row for that customer showing order details for a different product.</span></span> <span data-ttu-id="7813c-105">Выполнив сведение набора данных по столбцу продукта, можно получить набор данных, который содержит по одной строке для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="7813c-105">By pivoting the data set on the product column, the Pivot transformation can output a data set with a single row per customer.</span></span> <span data-ttu-id="7813c-106">Каждая строка будет содержать все покупки одного клиента, причем наименования продуктов будут именами столбцов, а количество приобретенных единиц каждого продукта будет значением соответствующих столбцов.</span><span class="sxs-lookup"><span data-stu-id="7813c-106">That single row lists all the purchases by the customer, with the product names shown as column names, and the quantity shown as a value in the product column.</span></span> <span data-ttu-id="7813c-107">Так как не каждый клиент приобретает все виды продукции, многие столбцы могут содержать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="7813c-107">Because not every customer purchases every product, many columns may contain null values.</span></span>  
  
 <span data-ttu-id="7813c-108">При выполнении сведения роли различных входных столбцов различаются.</span><span class="sxs-lookup"><span data-stu-id="7813c-108">When a dataset is pivoted, input columns perform different roles in the pivoting process.</span></span> <span data-ttu-id="7813c-109">Столбец может выступить в следующих ролях.</span><span class="sxs-lookup"><span data-stu-id="7813c-109">A column can participate in the following ways:</span></span>  
  
-   <span data-ttu-id="7813c-110">Столбец передается в результирующий набор данных без изменения.</span><span class="sxs-lookup"><span data-stu-id="7813c-110">The column is passed through unchanged to the output.</span></span> <span data-ttu-id="7813c-111">Так как несколько входных строк могут попасть в одну выходную, то при преобразовании копируется только первое значение входного столбца.</span><span class="sxs-lookup"><span data-stu-id="7813c-111">Because many input rows can result only in one output row, the transformation copies only the first input value for the column.</span></span>  
  
-   <span data-ttu-id="7813c-112">Столбец выступает в качестве ключа или части ключа, который определяет набор записей.</span><span class="sxs-lookup"><span data-stu-id="7813c-112">The column acts as the key or part of the key that identifies a set of records.</span></span>  
  
-   <span data-ttu-id="7813c-113">Столбец определяет сведение.</span><span class="sxs-lookup"><span data-stu-id="7813c-113">The column defines the pivot.</span></span> <span data-ttu-id="7813c-114">То есть множество значений данного столбца определяет множество новых столбцов в результирующем наборе данных.</span><span class="sxs-lookup"><span data-stu-id="7813c-114">The values in this column are associated with columns in the pivoted dataset.</span></span>  
  
-   <span data-ttu-id="7813c-115">Столбец содержит значения, которые переносятся в столбцы, созданные сведением.</span><span class="sxs-lookup"><span data-stu-id="7813c-115">The column contains values that are placed in the columns that the pivot creates.</span></span>  
  
 <span data-ttu-id="7813c-116">Это преобразование содержит один вход, один обычный вывод и один вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="7813c-116">This transformation has one input, one regular output, and one error output.</span></span>  
  
## <a name="sort-and-duplicate-rows"></a><span data-ttu-id="7813c-117">Сортировка и повторяющиеся строки</span><span class="sxs-lookup"><span data-stu-id="7813c-117">Sort and Duplicate Rows</span></span>  
 <span data-ttu-id="7813c-118">Для эффективного выполнения сведения необходимо, чтобы данные были отсортированы по столбцу, выбранному для сведения. Эффективным считается такое сведение, при котором создается минимально возможное количество записей в новом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="7813c-118">To pivot data efficiently, which means creating as few records in the output dataset as possible, the input data must be sorted on the pivot column.</span></span> <span data-ttu-id="7813c-119">Если данные не отсортированы, преобразование «Сведение» может создать несколько записей для каждого значения в ключе набора.</span><span class="sxs-lookup"><span data-stu-id="7813c-119">If the data is not sorted, the Pivot transformation might generate multiple records for each value in the set key, which is the column that defines set membership.</span></span> <span data-ttu-id="7813c-120">Например, если в наборе данных выполняется сведение по столбцу **Name** без сортировки имен, то результирующий набор данных может иметь более одной строки на каждого заказчика, потому что формирование новой строки возникает при каждом изменении значения в поле **Name** .</span><span class="sxs-lookup"><span data-stu-id="7813c-120">For example, if a dataset is pivoted on a **Name** column but the names are not sorted, the output dataset could have more than one row for each customer, because a pivot occurs every time that the value in **Name** changes.</span></span>  
  
 <span data-ttu-id="7813c-121">Введенные данные могут содержать повторяющиеся строки, которые могут вызвать сбой преобразования «Сведение».</span><span class="sxs-lookup"><span data-stu-id="7813c-121">The input data might contain duplicate rows, which will cause the Pivot transformation to fail.</span></span> <span data-ttu-id="7813c-122">Повторяющиеся строки — это строки, имеющие одинаковые значения в наборе ключевых столбцов и столбцов сведения.</span><span class="sxs-lookup"><span data-stu-id="7813c-122">"Duplicate rows" means rows that have the same values in the set key columns and the pivot columns.</span></span> <span data-ttu-id="7813c-123">Чтобы предотвратить сбой, можно либо настроить преобразование для перенаправления ошибочных строк в выход ошибок, либо заранее вычислить значения во избежание повторяющихся рядов.</span><span class="sxs-lookup"><span data-stu-id="7813c-123">To avoid failure, you can either configure the transformation to redirect error rows to an error output or you can pre-aggregate values to ensure there are no duplicate rows.</span></span>  
  
##  <a name="options-in-the-pivot-dialog-box"></a><a name="options"></a> <span data-ttu-id="7813c-124">Параметры в диалоговом окне «Сведение»</span><span class="sxs-lookup"><span data-stu-id="7813c-124">Options in the Pivot Dialog Box</span></span>  
 <span data-ttu-id="7813c-125">Операция сведения настраивается путем установки параметров в диалоговом окне **Сведение** .</span><span class="sxs-lookup"><span data-stu-id="7813c-125">You configure the pivot operation by setting the options in the **Pivot** dialog box.</span></span> <span data-ttu-id="7813c-126">Чтобы открыть диалоговое окно **Сведение** , добавьте преобразование "Сведение" в пакет в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], а затем щелкните компонент правой кнопкой мыши и выберите команду **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="7813c-126">To open the **Pivot** dialog box, add the Pivot transformation to the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and then right-click the component and click **Edit**.</span></span>  
  
 <span data-ttu-id="7813c-127">В следующем списке описаны параметры диалогового окна **Сведение** .</span><span class="sxs-lookup"><span data-stu-id="7813c-127">The following list describes the options in the **Pivot** dialog box.</span></span>  
  
 <span data-ttu-id="7813c-128">**Ключ сведения**</span><span class="sxs-lookup"><span data-stu-id="7813c-128">**Pivot Key**</span></span>  
 <span data-ttu-id="7813c-129">Указывает столбец для использования в качестве значений верхней строки (строки заголовка) таблицы.</span><span class="sxs-lookup"><span data-stu-id="7813c-129">Specifies the column to use for values across the top row (header row) of the table.</span></span>  
  
 <span data-ttu-id="7813c-130">**Ключ набора**</span><span class="sxs-lookup"><span data-stu-id="7813c-130">**Set Key**</span></span>  
 <span data-ttu-id="7813c-131">Указывает столбец для использования в качестве значений левого столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="7813c-131">Specifies the column to use for values in the left column of the table.</span></span> <span data-ttu-id="7813c-132">Входные данные должны быть отсортированы по этому столбцу.</span><span class="sxs-lookup"><span data-stu-id="7813c-132">The input date must be sorted on this column.</span></span>  
  
 <span data-ttu-id="7813c-133">**Значение сведения**</span><span class="sxs-lookup"><span data-stu-id="7813c-133">**Pivot Value**</span></span>  
 <span data-ttu-id="7813c-134">Указывает столбец для использования в качестве значений таблицы, отличающихся от значений в строке заголовка и левом столбце.</span><span class="sxs-lookup"><span data-stu-id="7813c-134">Specifies the column to use for the table values, other than the values in the header row and the left column.</span></span>  
  
 <span data-ttu-id="7813c-135">**Игнорировать несопоставленные значения ключей сведения и сообщать их после выполнения DataFlow**</span><span class="sxs-lookup"><span data-stu-id="7813c-135">**Ignore un-matched Pivot Key values and report them after DataFlow execution**</span></span>  
 <span data-ttu-id="7813c-136">Выберите этот параметр, чтобы настроить преобразование "Сведение" для игнорирования строк, содержащих нераспознанные значения в столбце **Ключ сведения** , и вывода всех значений ключей сведения в сообщение журнала при запуске пакета.</span><span class="sxs-lookup"><span data-stu-id="7813c-136">Select this option to configure the Pivot transformation to ignore rows containing unrecognized values in the **Pivot Key** column and to output all of the pivot key values to a log message, when the package is run.</span></span>  
  
 <span data-ttu-id="7813c-137">Также вы можете настроить преобразование для вывода значений, установив для пользовательского свойства `PassThroughUnmatchedPivotKeys` значение `True`.</span><span class="sxs-lookup"><span data-stu-id="7813c-137">You can also configure the transformation to output the values by setting the `PassThroughUnmatchedPivotKeys` custom property to `True`.</span></span>  
  
 <span data-ttu-id="7813c-138">**Создание выходных столбцов сведения на основе значений**</span><span class="sxs-lookup"><span data-stu-id="7813c-138">**Generate pivot output columns from values**</span></span>  
 <span data-ttu-id="7813c-139">Введите в это поле значения ключей сведения, чтобы позволить преобразованию «Сведение» создать выходные столбцы для каждого значения.</span><span class="sxs-lookup"><span data-stu-id="7813c-139">Enter the pivot key values in this box to enable the Pivot transformation to create output columns for each value.</span></span> <span data-ttu-id="7813c-140">Вы можете либо ввести значения до запуска пакета, либо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7813c-140">You can either enter the values prior to running the package, or do the following.</span></span>  
  
1.  <span data-ttu-id="7813c-141">Выберите параметр **Пропускать несовпадающие значения ключа сведения и создать по ним отчет после выполнения DataFlow** , а затем нажмите кнопку **ОК** в диалоговом окне **Сведение** , чтобы сохранить изменения в преобразовании "Сведение".</span><span class="sxs-lookup"><span data-stu-id="7813c-141">Select the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then click **OK** in the **Pivot** dialog box to save the changes to the Pivot transformation.</span></span>  
  
2.  <span data-ttu-id="7813c-142">Запустите пакет.</span><span class="sxs-lookup"><span data-stu-id="7813c-142">Run the package.</span></span>  
  
3.  <span data-ttu-id="7813c-143">После успешного выполнения пакета выберите вкладку **Ход выполнения** и найдите информационное сообщение журнала о преобразовании «Сведение», которое содержит значения ключей сведения.</span><span class="sxs-lookup"><span data-stu-id="7813c-143">When the package succeeds, click the **Progress** tab and look for the information log message from the Pivot transformation that contains the pivot key values.</span></span>  
  
4.  <span data-ttu-id="7813c-144">Щелкните сообщение правой кнопкой мыши и выберите пункт **Копировать текст сообщения**.</span><span class="sxs-lookup"><span data-stu-id="7813c-144">Right-click the message and click **Copy Message Text**.</span></span>  
  
5.  <span data-ttu-id="7813c-145">Выберите пункт **Остановить отладку** в меню **Отладка** , чтобы переключиться в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="7813c-145">Click **Stop Debugging** on the **Debug** menu to switch to the design mode.</span></span>  
  
6.  <span data-ttu-id="7813c-146">Щелкните правой кнопкой мыши преобразование "Сведение" и выберите команду **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="7813c-146">Right-click the Pivot transformation, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="7813c-147">Снимите флажок **Пропускать несовпадающие значения ключа сведения и создать по ним отчет после выполнения DataFlow** , а затем вставьте значения ключей сведения в поле **Создавать выходные столбцы сведения из значений** в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="7813c-147">Uncheck the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then paste the pivot key values in the **Generate pivot output columns from values** box using the following format.</span></span>  
  
     <span data-ttu-id="7813c-148">[значение1],[значение2],[значение3]</span><span class="sxs-lookup"><span data-stu-id="7813c-148">[value1],[value2],[value3]</span></span>  
  
 <span data-ttu-id="7813c-149">**Сформировать столбцы сейчас**</span><span class="sxs-lookup"><span data-stu-id="7813c-149">**Generate Columns Now**</span></span>  
 <span data-ttu-id="7813c-150">Щелкните, чтобы создать выходной столбец для каждого значения ключа сведения, перечисленного в поле **Создавать выходные столбцы сведения из значений** .</span><span class="sxs-lookup"><span data-stu-id="7813c-150">Click to create an output column for each pivot key value that is listed in the **Generate pivot output columns from values** box.</span></span>  
  
 <span data-ttu-id="7813c-151">Выходные столбцы отображаются в поле **Существующие выходные столбцы сведения** .</span><span class="sxs-lookup"><span data-stu-id="7813c-151">The output columns appear in the **Existing pivoted output columns** box.</span></span>  
  
 <span data-ttu-id="7813c-152">**Существующие выходные столбцы сведения**</span><span class="sxs-lookup"><span data-stu-id="7813c-152">**Existing pivoted output columns**</span></span>  
 <span data-ttu-id="7813c-153">Выводит список выходных столбцов для значений ключей сведения</span><span class="sxs-lookup"><span data-stu-id="7813c-153">Lists the output columns for the pivot key values</span></span>  
  
 <span data-ttu-id="7813c-154">В следующей таблице показан набор данных до их сведения в столбце **Год** .</span><span class="sxs-lookup"><span data-stu-id="7813c-154">The following table shows a data set before the data is pivoted on the **Year** column.</span></span>  
  
|<span data-ttu-id="7813c-155">Год</span><span class="sxs-lookup"><span data-stu-id="7813c-155">Year</span></span>|<span data-ttu-id="7813c-156">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7813c-156">Product Name</span></span>|<span data-ttu-id="7813c-157">Итог</span><span class="sxs-lookup"><span data-stu-id="7813c-157">Total</span></span>|  
|----------|------------------|-----------|  
|<span data-ttu-id="7813c-158">2004</span><span class="sxs-lookup"><span data-stu-id="7813c-158">2004</span></span>|<span data-ttu-id="7813c-159">Шина для велосипеда HL Mountain</span><span class="sxs-lookup"><span data-stu-id="7813c-159">HL Mountain Tire</span></span>|<span data-ttu-id="7813c-160">1504884.15</span><span class="sxs-lookup"><span data-stu-id="7813c-160">1504884.15</span></span>|  
|<span data-ttu-id="7813c-161">2003</span><span class="sxs-lookup"><span data-stu-id="7813c-161">2003</span></span>|<span data-ttu-id="7813c-162">Камера шины для шоссейного велосипеда</span><span class="sxs-lookup"><span data-stu-id="7813c-162">Road Tire Tube</span></span>|<span data-ttu-id="7813c-163">35920.50</span><span class="sxs-lookup"><span data-stu-id="7813c-163">35920.50</span></span>|  
|<span data-ttu-id="7813c-164">2004</span><span class="sxs-lookup"><span data-stu-id="7813c-164">2004</span></span>|<span data-ttu-id="7813c-165">Фляга для воды — 30 унций.</span><span class="sxs-lookup"><span data-stu-id="7813c-165">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="7813c-166">2805.00</span><span class="sxs-lookup"><span data-stu-id="7813c-166">2805.00</span></span>|  
|<span data-ttu-id="7813c-167">2002</span><span class="sxs-lookup"><span data-stu-id="7813c-167">2002</span></span>|<span data-ttu-id="7813c-168">Шина для туристического велосипеда</span><span class="sxs-lookup"><span data-stu-id="7813c-168">Touring Tire</span></span>|<span data-ttu-id="7813c-169">62364.225</span><span class="sxs-lookup"><span data-stu-id="7813c-169">62364.225</span></span>|  
  
 <span data-ttu-id="7813c-170">В следующей таблице показан набор данных после их сведения по столбцу **Год** .</span><span class="sxs-lookup"><span data-stu-id="7813c-170">The following table shows a data set after the data has been pivoted on the **Year** column.</span></span>  
  
||<span data-ttu-id="7813c-171">2002</span><span class="sxs-lookup"><span data-stu-id="7813c-171">2002</span></span>|<span data-ttu-id="7813c-172">2003</span><span class="sxs-lookup"><span data-stu-id="7813c-172">2003</span></span>|<span data-ttu-id="7813c-173">2004</span><span class="sxs-lookup"><span data-stu-id="7813c-173">2004</span></span>|  
|-|----------|----------|----------|  
|<span data-ttu-id="7813c-174">Шина для велосипеда HL Mountain</span><span class="sxs-lookup"><span data-stu-id="7813c-174">HL Mountain Tire</span></span>|<span data-ttu-id="7813c-175">141164.10</span><span class="sxs-lookup"><span data-stu-id="7813c-175">141164.10</span></span>|<span data-ttu-id="7813c-176">446297.775</span><span class="sxs-lookup"><span data-stu-id="7813c-176">446297.775</span></span>|<span data-ttu-id="7813c-177">1504884.15</span><span class="sxs-lookup"><span data-stu-id="7813c-177">1504884.15</span></span>|  
|<span data-ttu-id="7813c-178">Камера шины для шоссейного велосипеда</span><span class="sxs-lookup"><span data-stu-id="7813c-178">Road Tire Tube</span></span>|<span data-ttu-id="7813c-179">3592.05</span><span class="sxs-lookup"><span data-stu-id="7813c-179">3592.05</span></span>|<span data-ttu-id="7813c-180">35920.50</span><span class="sxs-lookup"><span data-stu-id="7813c-180">35920.50</span></span>|<span data-ttu-id="7813c-181">89801.25</span><span class="sxs-lookup"><span data-stu-id="7813c-181">89801.25</span></span>|  
|<span data-ttu-id="7813c-182">Фляга для воды — 30 унций.</span><span class="sxs-lookup"><span data-stu-id="7813c-182">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="7813c-183">*NULL*</span><span class="sxs-lookup"><span data-stu-id="7813c-183">*NULL*</span></span>|<span data-ttu-id="7813c-184">*NULL*</span><span class="sxs-lookup"><span data-stu-id="7813c-184">*NULL*</span></span>|<span data-ttu-id="7813c-185">2805.00</span><span class="sxs-lookup"><span data-stu-id="7813c-185">2805.00</span></span>|  
|<span data-ttu-id="7813c-186">Шина для туристического велосипеда</span><span class="sxs-lookup"><span data-stu-id="7813c-186">Touring Tire</span></span>|<span data-ttu-id="7813c-187">62364.225</span><span class="sxs-lookup"><span data-stu-id="7813c-187">62364.225</span></span>|<span data-ttu-id="7813c-188">375051.60</span><span class="sxs-lookup"><span data-stu-id="7813c-188">375051.60</span></span>|<span data-ttu-id="7813c-189">1041810.00</span><span class="sxs-lookup"><span data-stu-id="7813c-189">1041810.00</span></span>|  
  
 <span data-ttu-id="7813c-190">Для сведения данных по столбцу **Год** , как показано выше, в диалоговом окне **Сведения** задаются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="7813c-190">To pivot the data on the **Year** column, as shown above, the following options are set in the **Pivot** dialog box.</span></span>  
  
-   <span data-ttu-id="7813c-191">В списке **Ключ сведения** выбирается «Год».</span><span class="sxs-lookup"><span data-stu-id="7813c-191">Year is selected in the **Pivot Key** list box.</span></span>  
  
-   <span data-ttu-id="7813c-192">В списке **Ключ набора** выбирается «Название продукта».</span><span class="sxs-lookup"><span data-stu-id="7813c-192">Product Name is selected in the **Set Key** list box.</span></span>  
  
-   <span data-ttu-id="7813c-193">В списке **Значение сведения** выбирается «Итог».</span><span class="sxs-lookup"><span data-stu-id="7813c-193">Total is selected in the **Pivot Value** list box.</span></span>  
  
-   <span data-ttu-id="7813c-194">Следующие значения вводятся в поле **Создание выходных столбцов сведения на основе значений** .</span><span class="sxs-lookup"><span data-stu-id="7813c-194">The following values are entered in the **Generate pivot output columns from values** box.</span></span>  
  
     <span data-ttu-id="7813c-195">[2002],[2003],[2004]</span><span class="sxs-lookup"><span data-stu-id="7813c-195">[2002],[2003],[2004]</span></span>  
  
## <a name="configuration-of-the-pivot-transformation"></a><span data-ttu-id="7813c-196">Настройка преобразования «Сведение»</span><span class="sxs-lookup"><span data-stu-id="7813c-196">Configuration of the Pivot Transformation</span></span>  
 <span data-ttu-id="7813c-197">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="7813c-197">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7813c-198">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7813c-198">For more information about the properties that you can set in the **Advanced Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7813c-199">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="7813c-199">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="7813c-200">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="7813c-200">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-content"></a><span data-ttu-id="7813c-201">См. также</span><span class="sxs-lookup"><span data-stu-id="7813c-201">Related Content</span></span>  
 <span data-ttu-id="7813c-202">Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="7813c-202">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7813c-203">См. также:</span><span class="sxs-lookup"><span data-stu-id="7813c-203">See Also</span></span>  
 <span data-ttu-id="7813c-204">[Преобразование отмены свертывания](pivot-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="7813c-204">[Unpivot Transformation](pivot-transformation.md) </span></span>  
 <span data-ttu-id="7813c-205">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="7813c-205">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="7813c-206">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="7813c-206">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
