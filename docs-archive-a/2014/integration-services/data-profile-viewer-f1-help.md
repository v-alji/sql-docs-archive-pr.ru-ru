---
title: Справка F1 средство просмотра профиля данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dataprofileviewer.f1
helpviewer_keywords:
- Data Profile Viewer [Integration Services]
- Data Profiling task [Integration Services], viewer
ms.assetid: 3469c60a-8f4f-46ba-999a-cb9070197fea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7003e1299938bd53a6d16a5597d4566ba5c46579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656489"
---
# <a name="data-profile-viewer-f1-help"></a><span data-ttu-id="88272-102">Справка F1 средства просмотра профиля данных</span><span class="sxs-lookup"><span data-stu-id="88272-102">Data Profile Viewer F1 Help</span></span>
  <span data-ttu-id="88272-103">Используйте средство просмотра профиля данных для просмотра выхода задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="88272-103">Use the Data Profile Viewer to view the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="88272-104">Дополнительные сведения об использовании средства просмотра профиля данных см. в разделе [Средство просмотра профиля данных](control-flow/data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="88272-104">For more information about how to use the Data Profile Viewer, see [Data Profile Viewer](control-flow/data-profile-viewer.md).</span></span> <span data-ttu-id="88272-105">Дополнительные сведения об использовании задачи "Профилирование данных", создающей профиль, который можно проанализировать с помощью средства просмотра профиля данных, см. в разделе [Установка задачи "Профилирование данных"](control-flow/data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="88272-105">For more information about how to use the Data Profiling task, which creates the profile output that you analyze in the Data Profile Viewer, see [Setup of the Data Profiling Task](control-flow/data-profiling-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="88272-106">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="88272-106">Static Options</span></span>  
 <span data-ttu-id="88272-107">**Открыть**</span><span class="sxs-lookup"><span data-stu-id="88272-107">**Open**</span></span>  
 <span data-ttu-id="88272-108">Нажмите, чтобы просмотреть сохраненный файл, содержащий выход задачи «Профилирование данных»</span><span class="sxs-lookup"><span data-stu-id="88272-108">Click to browse for the saved file that contains the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="88272-109">Панель**Профили**</span><span class="sxs-lookup"><span data-stu-id="88272-109">**Profiles** pane</span></span>  
 <span data-ttu-id="88272-110">Раскройте дерево на панели **Профили** , чтобы увидеть, какие профили включены в выход.</span><span class="sxs-lookup"><span data-stu-id="88272-110">Expand the tree in the **Profiles** pane to see the profiles that are included in the output.</span></span> <span data-ttu-id="88272-111">Выберите профиль, чтобы посмотреть результаты для этого профиля.</span><span class="sxs-lookup"><span data-stu-id="88272-111">Select a profile to view the results for that profile.</span></span>  
  
 <span data-ttu-id="88272-112">Панель**Сообщения**</span><span class="sxs-lookup"><span data-stu-id="88272-112">**Message** pane</span></span>  
 <span data-ttu-id="88272-113">Отображает сообщения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="88272-113">Displays status messages.</span></span>  
  
 <span data-ttu-id="88272-114">Панель**Углубленная детализация**</span><span class="sxs-lookup"><span data-stu-id="88272-114">**Drilldown** pane</span></span>  
 <span data-ttu-id="88272-115">Отображает строки данных, соответствующие значению выхода, если доступен источник данных, который использовался задачей «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="88272-115">Displays the rows of data that match a value in the output, if the data source that is used by the Data Profiling task is available.</span></span>  
  
 <span data-ttu-id="88272-116">Например, при просмотре выхода профиля распределения значений столбцов для столбца US State, панель **Подробное распределение значений** может содержать строку «WA».</span><span class="sxs-lookup"><span data-stu-id="88272-116">For example, if you are viewing the output of a Column Value Distribution profile for a US State column, the **Detailed Value Distribution** pane might contain a row for "WA".</span></span> <span data-ttu-id="88272-117">Дважды щелкните строку на панели **Подробное распределение значений** , чтобы увидеть на панели детализации строки данных, в которых значением столбца штата является "WA".</span><span class="sxs-lookup"><span data-stu-id="88272-117">Double-click the row in the **Detailed Value Distribution** pane to see the rows of data where the value of the state column is "WA" in the drilldown pane.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="88272-118">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="88272-118">Dynamic Options</span></span>  
  
### <a name="profile-type--column-length-distribution-profile"></a><span data-ttu-id="88272-119">Тип профиля = Профиль распределения длины столбцов</span><span class="sxs-lookup"><span data-stu-id="88272-119">Profile Type = Column Length Distribution Profile</span></span>  
  
#### <a name="column-length-distribution-profile---column-pane"></a><span data-ttu-id="88272-120">Профиль распределения длины столбцов — панель \<column></span><span class="sxs-lookup"><span data-stu-id="88272-120">Column Length Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="88272-121">**Минимальная длина**</span><span class="sxs-lookup"><span data-stu-id="88272-121">**Minimum Length**</span></span>  
 <span data-ttu-id="88272-122">Отображает минимальную длину значений в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-122">Displays the minimum length of values in this column.</span></span>  
  
 <span data-ttu-id="88272-123">**Максимальная длина**</span><span class="sxs-lookup"><span data-stu-id="88272-123">**Maximum Length**</span></span>  
 <span data-ttu-id="88272-124">Отображает максимальную длину значений в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-124">Displays the maximum length of values in this column.</span></span>  
  
 <span data-ttu-id="88272-125">**Без учета начальных пробелов**</span><span class="sxs-lookup"><span data-stu-id="88272-125">**Ignore Leading Spaces**</span></span>  
 <span data-ttu-id="88272-126">Показывает, какое значение имело свойство `IgnoreLeadingSpaces` при вычислении этого профиля (True или False).</span><span class="sxs-lookup"><span data-stu-id="88272-126">Displays whether this profile was computed with an `IgnoreLeadingSpaces` value of True or False.</span></span> <span data-ttu-id="88272-127">Это свойство задается на странице **Запросы профиля** задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="88272-127">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="88272-128">**Без учета конечных пробелов**</span><span class="sxs-lookup"><span data-stu-id="88272-128">**Ignore Trailing Spaces**</span></span>  
 <span data-ttu-id="88272-129">Показывает, какое значение имело свойство `IgnoreTrailingSpaces` при вычислении этого профиля (True или False).</span><span class="sxs-lookup"><span data-stu-id="88272-129">Displays whether this profile was computed with an `IgnoreTrailingSpaces` value of True or False.</span></span> <span data-ttu-id="88272-130">Это свойство задается на странице **Запросы профиля** задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="88272-130">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="88272-131">**Количество строк**</span><span class="sxs-lookup"><span data-stu-id="88272-131">**Row Count**</span></span>  
 <span data-ttu-id="88272-132">Отображает число строк в таблице или представлении.</span><span class="sxs-lookup"><span data-stu-id="88272-132">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-length-distribution-pane"></a><span data-ttu-id="88272-133">Панель «Подробное распределение длины»</span><span class="sxs-lookup"><span data-stu-id="88272-133">Detailed Length Distribution pane</span></span>  
 <span data-ttu-id="88272-134">**Длина**</span><span class="sxs-lookup"><span data-stu-id="88272-134">**Length**</span></span>  
 <span data-ttu-id="88272-135">Отображает длины столбцов, обнаруженные в профилируемом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-135">Displays the column lengths found in the profiled column.</span></span>  
  
 <span data-ttu-id="88272-136">**Count**</span><span class="sxs-lookup"><span data-stu-id="88272-136">**Count**</span></span>  
 <span data-ttu-id="88272-137">Отображает число строк, в которых значение профилируемого столбца имело длину, указанную в столбце **Длина** .</span><span class="sxs-lookup"><span data-stu-id="88272-137">Displays the number of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
 <span data-ttu-id="88272-138">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="88272-138">**Percentage**</span></span>  
 <span data-ttu-id="88272-139">Отображает процент строк, в которых значение профилируемого столбца имело длину, указанную в столбце **Длина** .</span><span class="sxs-lookup"><span data-stu-id="88272-139">Displays the percentage of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
### <a name="profile-type--column-null-ratio-profile"></a><span data-ttu-id="88272-140">Тип профиля = Профиль соотношения значений NULL в столбцах</span><span class="sxs-lookup"><span data-stu-id="88272-140">Profile Type = Column Null Ratio Profile</span></span>  
  
#### <a name="column-null-ratio-profile---column-pane"></a><span data-ttu-id="88272-141">Профиль соотношения значений NULL в столбцах — панель \<column></span><span class="sxs-lookup"><span data-stu-id="88272-141">Column Null Ratio Profile - \<column> pane</span></span>  
 <span data-ttu-id="88272-142">**Количество значений NULL**</span><span class="sxs-lookup"><span data-stu-id="88272-142">**Null Count**</span></span>  
 <span data-ttu-id="88272-143">Отображает число строк, в которых профилируемый столбец содержит значение NULL.</span><span class="sxs-lookup"><span data-stu-id="88272-143">Displays the number of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="88272-144">**Процент значений NULL**</span><span class="sxs-lookup"><span data-stu-id="88272-144">**Null Percentage**</span></span>  
 <span data-ttu-id="88272-145">Отображает процент строк, в которых профилируемый столбец содержит значение NULL.</span><span class="sxs-lookup"><span data-stu-id="88272-145">Displays the percentage of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="88272-146">**Количество строк**</span><span class="sxs-lookup"><span data-stu-id="88272-146">**Row Count**</span></span>  
 <span data-ttu-id="88272-147">Отображает число строк в таблице или представлении.</span><span class="sxs-lookup"><span data-stu-id="88272-147">Displays the number of rows in the table or view.</span></span>  
  
### <a name="profile-type--column-pattern-profile"></a><span data-ttu-id="88272-148">Тип профиля = Профиль шаблона столбцов</span><span class="sxs-lookup"><span data-stu-id="88272-148">Profile Type = Column Pattern Profile</span></span>  
  
#### <a name="column-pattern-profile---column-pane"></a><span data-ttu-id="88272-149">Профиль шаблона столбцов — панель \<column></span><span class="sxs-lookup"><span data-stu-id="88272-149">Column Pattern Profile - \<column> pane</span></span>  
 <span data-ttu-id="88272-150">**Количество строк**</span><span class="sxs-lookup"><span data-stu-id="88272-150">**Row Count**</span></span>  
 <span data-ttu-id="88272-151">Отображает число строк в таблице или представлении.</span><span class="sxs-lookup"><span data-stu-id="88272-151">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="pattern-distribution-pane"></a><span data-ttu-id="88272-152">Панель «Распределение шаблонов»</span><span class="sxs-lookup"><span data-stu-id="88272-152">Pattern Distribution pane</span></span>  
 <span data-ttu-id="88272-153">**Шаблон**</span><span class="sxs-lookup"><span data-stu-id="88272-153">**Pattern**</span></span>  
 <span data-ttu-id="88272-154">Отображает шаблоны, вычисляемые для профилируемого столбца.</span><span class="sxs-lookup"><span data-stu-id="88272-154">Displays the patterns computed for the profiled column.</span></span>  
  
 <span data-ttu-id="88272-155">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="88272-155">**Percentage**</span></span>  
 <span data-ttu-id="88272-156">Отображает процент строк, значения которых соответствуют шаблону, отображаемому в столбце **Шаблон** .</span><span class="sxs-lookup"><span data-stu-id="88272-156">Displays the percentage of rows whose values match the pattern displayed in the **Pattern** column.</span></span>  
  
### <a name="profile-type--column-statistics-profile"></a><span data-ttu-id="88272-157">Тип профиля = Профиль статистики столбцов</span><span class="sxs-lookup"><span data-stu-id="88272-157">Profile Type = Column Statistics Profile</span></span>  
  
#### <a name="column-statistics-profile---column-pane"></a><span data-ttu-id="88272-158">Профиль статистики столбцов — панель \<column></span><span class="sxs-lookup"><span data-stu-id="88272-158">Column Statistics Profile - \<column> pane</span></span>  
 <span data-ttu-id="88272-159">**Минимальные**</span><span class="sxs-lookup"><span data-stu-id="88272-159">**Minimum**</span></span>  
 <span data-ttu-id="88272-160">Отображает минимальное значение, обнаруженное в профилируемом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-160">Displays the minimum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="88272-161">**Максимум**</span><span class="sxs-lookup"><span data-stu-id="88272-161">**Maximum**</span></span>  
 <span data-ttu-id="88272-162">Отображает максимальное значение, обнаруженное в профилируемом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-162">Displays the maximum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="88272-163">**Среднее**</span><span class="sxs-lookup"><span data-stu-id="88272-163">**Mean**</span></span>  
 <span data-ttu-id="88272-164">Отображает среднее значение по профилируемому столбцу.</span><span class="sxs-lookup"><span data-stu-id="88272-164">Displays the mean of the values found in the profiled column.</span></span>  
  
 <span data-ttu-id="88272-165">**Стандартное отклонение**</span><span class="sxs-lookup"><span data-stu-id="88272-165">**Standard Deviation**</span></span>  
 <span data-ttu-id="88272-166">Отображает стандартное отклонение для значений профилируемого столбца.</span><span class="sxs-lookup"><span data-stu-id="88272-166">Displays the standard deviation of the values found in the profiled column.</span></span>  
  
### <a name="profile-type--column-value-distribution-profile"></a><span data-ttu-id="88272-167">Тип профиля = Профиль распределения значений столбцов</span><span class="sxs-lookup"><span data-stu-id="88272-167">Profile Type = Column Value Distribution Profile</span></span>  
  
#### <a name="column-value-distribution-profile---column-pane"></a><span data-ttu-id="88272-168">Профиль распределения значений столбцов — панель \<column></span><span class="sxs-lookup"><span data-stu-id="88272-168">Column Value Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="88272-169">**Количество различных значений**</span><span class="sxs-lookup"><span data-stu-id="88272-169">**Number of Distinct Values**</span></span>  
 <span data-ttu-id="88272-170">Отображает число различных значений в профилируемом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-170">Displays the count of distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="88272-171">**Количество строк**</span><span class="sxs-lookup"><span data-stu-id="88272-171">**Row Count**</span></span>  
 <span data-ttu-id="88272-172">Отображает число строк в таблице или представлении.</span><span class="sxs-lookup"><span data-stu-id="88272-172">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-value-distribution-pane"></a><span data-ttu-id="88272-173">Панель «Подробное распределение значений»</span><span class="sxs-lookup"><span data-stu-id="88272-173">Detailed Value Distribution pane</span></span>  
 <span data-ttu-id="88272-174">**Value**</span><span class="sxs-lookup"><span data-stu-id="88272-174">**Value**</span></span>  
 <span data-ttu-id="88272-175">Отображает уникальные значения, обнаруженные в профилируемом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-175">Displays the distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="88272-176">**Count**</span><span class="sxs-lookup"><span data-stu-id="88272-176">**Count**</span></span>  
 <span data-ttu-id="88272-177">Отображает число строк, в которых профилируемый столбец имеет значение, указанное в столбце **Значение** .</span><span class="sxs-lookup"><span data-stu-id="88272-177">Displays the number of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
 <span data-ttu-id="88272-178">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="88272-178">**Percentage**</span></span>  
 <span data-ttu-id="88272-179">Отображает процент строк, в которых профилируемый столбец имеет значение, указанное в столбце **Значение** .</span><span class="sxs-lookup"><span data-stu-id="88272-179">Displays the percentage of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
### <a name="profile-type--candidate-key-profile"></a><span data-ttu-id="88272-180">Тип профиля = Профиль потенциальных ключей</span><span class="sxs-lookup"><span data-stu-id="88272-180">Profile Type = Candidate Key Profile</span></span>  
  
#### <a name="candidate-key-profile---table-pane"></a><span data-ttu-id="88272-181">Профиль потенциальных ключей — панель \<table></span><span class="sxs-lookup"><span data-stu-id="88272-181">Candidate Key Profile - \<table> pane</span></span>  
 <span data-ttu-id="88272-182">**Ключевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="88272-182">**Key Columns**</span></span>  
 <span data-ttu-id="88272-183">Отображает столбцы, которые были выбраны для профилирования, как потенциальные ключи.</span><span class="sxs-lookup"><span data-stu-id="88272-183">Displays the columns that were selected for profiling as a candidate key.</span></span>  
  
 <span data-ttu-id="88272-184">**Сила ключа**</span><span class="sxs-lookup"><span data-stu-id="88272-184">**Key Strength**</span></span>  
 <span data-ttu-id="88272-185">Отображает силу (в процентах) потенциального ключевого столбца или сочетания столбцов.</span><span class="sxs-lookup"><span data-stu-id="88272-185">Displays the strength (as a percentage) of the candidate key column or combination of columns.</span></span> <span data-ttu-id="88272-186">Сила ключа менее 100% означает наличие повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="88272-186">A key strength of less than 100% indicates that duplicate values exist.</span></span>  
  
#### <a name="key-violations-pane"></a><span data-ttu-id="88272-187">Панель «Нарушения ключа»</span><span class="sxs-lookup"><span data-stu-id="88272-187">Key Violations pane</span></span>  
 <span data-ttu-id="88272-188">**\<column1>, \<column2> и т. д.**</span><span class="sxs-lookup"><span data-stu-id="88272-188">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="88272-189">Отображает повторяющиеся значения, обнаруженные в профилируемом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-189">Displays the duplicate values that were found in the profiled column.</span></span>  
  
 <span data-ttu-id="88272-190">**Count**</span><span class="sxs-lookup"><span data-stu-id="88272-190">**Count**</span></span>  
 <span data-ttu-id="88272-191">Отображает число строк, в которых указанный столбец имеет значение, показанное в первом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-191">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
### <a name="profile-type--functional-dependency-profile"></a><span data-ttu-id="88272-192">Тип профиля = Профиль функциональной зависимости</span><span class="sxs-lookup"><span data-stu-id="88272-192">Profile Type = Functional Dependency Profile</span></span>  
  
#### <a name="functional-dependency-profile-pane"></a><span data-ttu-id="88272-193">Панель «Профиль функциональной зависимости»</span><span class="sxs-lookup"><span data-stu-id="88272-193">Functional Dependency Profile pane</span></span>  
 <span data-ttu-id="88272-194">**Определяющие столбцы**</span><span class="sxs-lookup"><span data-stu-id="88272-194">**Determinant Columns**</span></span>  
 <span data-ttu-id="88272-195">Отображает столбец или столбцы, выбранные в качестве определяющих.</span><span class="sxs-lookup"><span data-stu-id="88272-195">Displays the column or columns selected as the determinant column.</span></span> <span data-ttu-id="88272-196">Например, поскольку одному почтовому индексу США всегда соответствует один и тот же штат, поле почтового индекса является определяющим.</span><span class="sxs-lookup"><span data-stu-id="88272-196">In the example where the same United States Zip Code should always have the same state, the Zip Code is the determinant column.</span></span>  
  
 <span data-ttu-id="88272-197">**Зависимые столбцы**</span><span class="sxs-lookup"><span data-stu-id="88272-197">**Dependent Columns**</span></span>  
 <span data-ttu-id="88272-198">Отображает столбец или столбцы, выбранные в качестве зависимых.</span><span class="sxs-lookup"><span data-stu-id="88272-198">Displays the column or columns selected as the dependent column.</span></span> <span data-ttu-id="88272-199">Например, поскольку одному почтовому индексу США всегда соответствует один и тот же штат, поле штата является зависимым.</span><span class="sxs-lookup"><span data-stu-id="88272-199">In the example where the same United States Zip Code should always have the same state, the state is the dependent column.</span></span>  
  
 <span data-ttu-id="88272-200">**Степень функциональной зависимости**</span><span class="sxs-lookup"><span data-stu-id="88272-200">**Functional Dependency Strength**</span></span>  
 <span data-ttu-id="88272-201">Отображает силу (в процентах) функциональной зависимости столбцов.</span><span class="sxs-lookup"><span data-stu-id="88272-201">Displays the strength (as a percentage) of the functional dependency between columns.</span></span> <span data-ttu-id="88272-202">Сила ключа менее 100% означает, что в некоторых случаях определяющее значение не определяет зависимое.</span><span class="sxs-lookup"><span data-stu-id="88272-202">A key strength of less than 100% indicates that there are cases where the determinant value does not determine the dependent value.</span></span> <span data-ttu-id="88272-203">В приведенном примере, где одному почтовому индексу США должен соответствовать один и тот же штат, это может свидетельствовать о недопустимости одного из значений штата.</span><span class="sxs-lookup"><span data-stu-id="88272-203">In the example where the same United States Zip Code should always have the same state, this probably indicates some state values are not valid.</span></span>  
  
#### <a name="functional-dependency-violations-pane"></a><span data-ttu-id="88272-204">Панель «Нарушения функциональной зависимости»</span><span class="sxs-lookup"><span data-stu-id="88272-204">Functional Dependency Violations pane</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88272-205">Высокий процент ошибочных значений данных может привести к непредвиденным результатам в профиле функциональной зависимости.</span><span class="sxs-lookup"><span data-stu-id="88272-205">A high percentage of erroneous values in the data could lead to unexpected results from a Functional Dependency profile.</span></span> <span data-ttu-id="88272-206">Например, 90% строк могут содержать значение штата «WI» для почтового кода «98052».</span><span class="sxs-lookup"><span data-stu-id="88272-206">For example, 90% of the rows have a State value of "WI" for a Postal Code value of "98052."</span></span> <span data-ttu-id="88272-207">В профиле в качестве нарушения приведены строки с правильным значением штата «WA».</span><span class="sxs-lookup"><span data-stu-id="88272-207">The profile reports rows that contain the correct state value of "WA" as violations.</span></span>  
  
 **\<determinant column name>**  
 <span data-ttu-id="88272-208">Отображает значение определяющего столбца или сочетания столбцов для данного случая нарушения функциональной зависимости.</span><span class="sxs-lookup"><span data-stu-id="88272-208">Displays the value of the determinant column or combination of columns in this instance of a functional dependency violation.</span></span>  
  
 **\<dependent column name>**  
 <span data-ttu-id="88272-209">Отображает значение зависимого столбца для данного случая нарушения функциональной зависимости.</span><span class="sxs-lookup"><span data-stu-id="88272-209">Displays the value of the dependent column in this instance of a functional dependency violation.</span></span>  
  
 <span data-ttu-id="88272-210">**Число несущего множества**</span><span class="sxs-lookup"><span data-stu-id="88272-210">**Support Count**</span></span>  
 <span data-ttu-id="88272-211">Отображает число строк, в которых определяющий столбец определяет зависимый столбец.</span><span class="sxs-lookup"><span data-stu-id="88272-211">Displays the number of rows in which the determinant column value determines the dependent column.</span></span>  
  
 <span data-ttu-id="88272-212">**Число нарушений**</span><span class="sxs-lookup"><span data-stu-id="88272-212">**Violation Count**</span></span>  
 <span data-ttu-id="88272-213">Отображает число строк, в которых определяющий столбец не определяет зависимый столбец.</span><span class="sxs-lookup"><span data-stu-id="88272-213">Displays the number of rows in which the determinant column value does not determine the dependent column.</span></span> <span data-ttu-id="88272-214">(Это строки, в которых зависимым является значение, показанное в столбце **\<dependent column name>** .)</span><span class="sxs-lookup"><span data-stu-id="88272-214">(These are the rows where the dependent value is the value shown in the **\<dependent column name>** column.)</span></span>  
  
 <span data-ttu-id="88272-215">**Процент несущего множества**</span><span class="sxs-lookup"><span data-stu-id="88272-215">**Support Percentage**</span></span>  
 <span data-ttu-id="88272-216">Отображает процент строк, в которых определяющий столбец определяет зависимый столбец.</span><span class="sxs-lookup"><span data-stu-id="88272-216">Displays the percentage of rows in which the determinant column determines the dependent column.</span></span>  
  
### <a name="profile-type--value-inclusion-profile"></a><span data-ttu-id="88272-217">Тип профиля = Профиль включения значений</span><span class="sxs-lookup"><span data-stu-id="88272-217">Profile Type = Value Inclusion Profile</span></span>  
  
#### <a name="value-inclusion-profile-pane"></a><span data-ttu-id="88272-218">Панель «Профиль включения значений»</span><span class="sxs-lookup"><span data-stu-id="88272-218">Value Inclusion Profile pane</span></span>  
 <span data-ttu-id="88272-219">**Побочные столбцы подмножества**</span><span class="sxs-lookup"><span data-stu-id="88272-219">**Subset Side Columns**</span></span>  
 <span data-ttu-id="88272-220">Отображает столбец или сочетание столбцов, которые были профилированы для определения того, входят ли они в столбцы надмножества.</span><span class="sxs-lookup"><span data-stu-id="88272-220">Displays the column or combination of columns that were profiled to determine whether they are in the superset columns.</span></span>  
  
 <span data-ttu-id="88272-221">**Побочные столбцы надмножества**</span><span class="sxs-lookup"><span data-stu-id="88272-221">**Superset Side Columns**</span></span>  
 <span data-ttu-id="88272-222">Отображает столбец или сочетание столбцов, которые были профилированы для определения того, включают ли они значения в столбцах подмножества.</span><span class="sxs-lookup"><span data-stu-id="88272-222">Displays the column or combination of columns that were profiled to determine whether they include the values in the subset columns.</span></span>  
  
 <span data-ttu-id="88272-223">**Интенсивность включений**</span><span class="sxs-lookup"><span data-stu-id="88272-223">**Inclusion Strength**</span></span>  
 <span data-ttu-id="88272-224">Отображает силу (в процентах) перекрытия данных между столбцами.</span><span class="sxs-lookup"><span data-stu-id="88272-224">Displays the strength (as a percentage) of the overlap between columns.</span></span> <span data-ttu-id="88272-225">Сила ключа менее 100% означает, что в некоторых случаях значение в подмножестве не обнаружено среди значений в надмножестве.</span><span class="sxs-lookup"><span data-stu-id="88272-225">A key strength of less than 100% indicates that there are cases where the subset value is not found among the superset values.</span></span>  
  
#### <a name="inclusion-violations-pane"></a><span data-ttu-id="88272-226">Панель «Нарушения включения»</span><span class="sxs-lookup"><span data-stu-id="88272-226">Inclusion Violations pane</span></span>  
 <span data-ttu-id="88272-227">**\<column1>, \<column2> и т. д.**</span><span class="sxs-lookup"><span data-stu-id="88272-227">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="88272-228">Отображает значения в столбце или столбцах подмножества, не обнаруженные в столбце или столбцах надмножества.</span><span class="sxs-lookup"><span data-stu-id="88272-228">Displays the values in the subset column or columns that were not found in the superset column or columns.</span></span>  
  
 <span data-ttu-id="88272-229">**Count**</span><span class="sxs-lookup"><span data-stu-id="88272-229">**Count**</span></span>  
 <span data-ttu-id="88272-230">Отображает число строк, в которых указанный столбец имеет значение, показанное в первом столбце.</span><span class="sxs-lookup"><span data-stu-id="88272-230">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88272-231">См. также:</span><span class="sxs-lookup"><span data-stu-id="88272-231">See Also</span></span>  
 <span data-ttu-id="88272-232">[средство просмотра профиля данных](control-flow/data-profile-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="88272-232">[Data Profile Viewer](control-flow/data-profile-viewer.md) </span></span>  
 [<span data-ttu-id="88272-233">Задачи профилирования и просмотра данных</span><span class="sxs-lookup"><span data-stu-id="88272-233">Data Profiling Task and Viewer</span></span>](control-flow/data-profiling-task-and-viewer.md)  
  
  
