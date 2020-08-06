---
title: Редактор преобразования "Нечеткое группирование" (вкладка "столбцы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.columns.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 24f4539f-2a9f-4acd-acc7-06228a07f7df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d3aef9c30a81760b7f09378a8ecd66fee0dac62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729629"
---
# <a name="fuzzy-grouping-transformation-editor-columns-tab"></a><span data-ttu-id="a8014-102">Редактор преобразования «Нечеткое группирование» (вкладка «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="a8014-102">Fuzzy Grouping Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="a8014-103">Используйте вкладку **Столбцы** диалогового окна **Редактор преобразования «Нечеткое группирование»** для задания столбцов, используемых при группировке строк с повторяющимися значениями.</span><span class="sxs-lookup"><span data-stu-id="a8014-103">Use the **Columns** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify the columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="a8014-104">Дополнительные сведения о преобразовании «Нечеткое группирование» см. в разделе [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a8014-104">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a8014-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8014-105">Options</span></span>  
 <span data-ttu-id="a8014-106">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="a8014-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="a8014-107">Выберите из списка входные столбцы, используемые для группировки строк с повторяющимися значениями.</span><span class="sxs-lookup"><span data-stu-id="a8014-107">Select from this list the input columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="a8014-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a8014-108">**Name**</span></span>  
 <span data-ttu-id="a8014-109">Просмотрите имена доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="a8014-109">View the names of available input columns.</span></span>  
  
 <span data-ttu-id="a8014-110">**Передать**</span><span class="sxs-lookup"><span data-stu-id="a8014-110">**Pass Through**</span></span>  
 <span data-ttu-id="a8014-111">Выберите, следует ли включить входной столбец в вывод преобразования.</span><span class="sxs-lookup"><span data-stu-id="a8014-111">Select whether to include the input column in the output of the transformation.</span></span> <span data-ttu-id="a8014-112">Все используемые для группирования столбцы автоматически копируются в выход.</span><span class="sxs-lookup"><span data-stu-id="a8014-112">All columns used for grouping are automatically copied to the output.</span></span> <span data-ttu-id="a8014-113">Дополнительные столбцы можно включать с помощью установки флажка.</span><span class="sxs-lookup"><span data-stu-id="a8014-113">You can include additional columns by checking this column.</span></span>  
  
 <span data-ttu-id="a8014-114">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="a8014-114">**Input Column**</span></span>  
 <span data-ttu-id="a8014-115">Выберите один из входных столбцов, указанных ранее в списке **Доступные входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="a8014-115">Select one of the input columns selected earlier in the **Available Input Columns** list.</span></span>  
  
 <span data-ttu-id="a8014-116">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="a8014-116">**Output Alias**</span></span>  
 <span data-ttu-id="a8014-117">Введите описательное имя соответствующего выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="a8014-117">Enter a descriptive name for the corresponding output column.</span></span> <span data-ttu-id="a8014-118">По умолчанию, имя выходного столбца совпадает с именем входного столбца.</span><span class="sxs-lookup"><span data-stu-id="a8014-118">By default, the output column name is the same as the input column name.</span></span>  
  
 <span data-ttu-id="a8014-119">**Псевдоним группы выхода**</span><span class="sxs-lookup"><span data-stu-id="a8014-119">**Group Output Alias**</span></span>  
 <span data-ttu-id="a8014-120">Введите описательное имя столбца, содержащего каноническое значение сгруппированных повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="a8014-120">Enter a descriptive name for the column that will contain the canonical value for the grouped duplicates.</span></span> <span data-ttu-id="a8014-121">По умолчанию, именем этого выходного столбца является имя входного столбца с добавлением в конце _clean.</span><span class="sxs-lookup"><span data-stu-id="a8014-121">The default name of this output column is the input column name with _clean appended.</span></span>  
  
 <span data-ttu-id="a8014-122">**Тип соответствия**</span><span class="sxs-lookup"><span data-stu-id="a8014-122">**Match Type**</span></span>  
 <span data-ttu-id="a8014-123">Выберите нечеткое или четкое соответствие.</span><span class="sxs-lookup"><span data-stu-id="a8014-123">Select fuzzy or exact matching.</span></span> <span data-ttu-id="a8014-124">Строки считаются повторяющимися, если они подобны по всем столбцам в случае нечеткого соответствия.</span><span class="sxs-lookup"><span data-stu-id="a8014-124">Rows are considered duplicates if they are sufficiently similar across all columns with a fuzzy match type.</span></span> <span data-ttu-id="a8014-125">Если также задано четкое соответствие по определенным столбцам в качестве вероятно повторяющихся, рассматриваются только строки, которые содержат одинаковые значения в столбцах четкого соответствия.</span><span class="sxs-lookup"><span data-stu-id="a8014-125">If you also specify exact matching on certain columns, only rows that contain identical values in the exact matching columns are considered as possible duplicates.</span></span> <span data-ttu-id="a8014-126">Таким образом, если известно, что определенный столбец не содержит ошибок или несоответствий, по нему можно задать четкое соответствие для повышения точности нечеткого соответствия по другим столбцам.</span><span class="sxs-lookup"><span data-stu-id="a8014-126">Therefore, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column to increase the accuracy of the fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="a8014-127">**Минимальное подобие**</span><span class="sxs-lookup"><span data-stu-id="a8014-127">**Minimum Similarity**</span></span>  
 <span data-ttu-id="a8014-128">Задайте порог подобия на уровне соединения с помощью ползунка.</span><span class="sxs-lookup"><span data-stu-id="a8014-128">Set the similarity threshold at the join level by using the slider.</span></span> <span data-ttu-id="a8014-129">Чем ближе значение к 1, тем ближе к искомому должно быть значение строки уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="a8014-129">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="a8014-130">Увеличение порогового значения может увеличить скорость соответствия, так как при этом будет рассматриваться меньшее количество предполагаемых совпадений.</span><span class="sxs-lookup"><span data-stu-id="a8014-130">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="a8014-131">**Псевдоним выхода подобия**</span><span class="sxs-lookup"><span data-stu-id="a8014-131">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="a8014-132">Задайте имя нового выходного столбца, который содержит метки подобия для выбранного соединения.</span><span class="sxs-lookup"><span data-stu-id="a8014-132">Specify the name for a new output column that contains the similarity scores for the selected join.</span></span> <span data-ttu-id="a8014-133">Если оставить это значение пустым, то выходной столбец не будет создан.</span><span class="sxs-lookup"><span data-stu-id="a8014-133">If you leave this value empty, the output column is not created.</span></span>  
  
 <span data-ttu-id="a8014-134">**Цифры**</span><span class="sxs-lookup"><span data-stu-id="a8014-134">**Numerals**</span></span>  
 <span data-ttu-id="a8014-135">Задайте значимость начальных и конечных цифр при сравнении данных столбцов.</span><span class="sxs-lookup"><span data-stu-id="a8014-135">Specify the significance of leading and trailing numerals in comparing the column data.</span></span> <span data-ttu-id="a8014-136">Например, если начальные цифры являются значимыми, группировка строк «123 Main Street» и «456 Main Street» не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a8014-136">For example, if leading numerals are significant, "123 Main Street" will not be grouped with "456 Main Street."</span></span>  
  
|<span data-ttu-id="a8014-137">Значение</span><span class="sxs-lookup"><span data-stu-id="a8014-137">Value</span></span>|<span data-ttu-id="a8014-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a8014-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a8014-139">**Нет**</span><span class="sxs-lookup"><span data-stu-id="a8014-139">**Neither**</span></span>|<span data-ttu-id="a8014-140">Начальные и конечные цифры не являются значимыми.</span><span class="sxs-lookup"><span data-stu-id="a8014-140">Leading and trailing numerals are not significant.</span></span>|  
|<span data-ttu-id="a8014-141">**06**</span><span class="sxs-lookup"><span data-stu-id="a8014-141">**Leading**</span></span>|<span data-ttu-id="a8014-142">Значимыми являются только начальные цифры.</span><span class="sxs-lookup"><span data-stu-id="a8014-142">Only leading numerals are significant.</span></span>|  
|<span data-ttu-id="a8014-143">**Конечные**</span><span class="sxs-lookup"><span data-stu-id="a8014-143">**Trailing**</span></span>|<span data-ttu-id="a8014-144">Значимыми являются только конечные цифры.</span><span class="sxs-lookup"><span data-stu-id="a8014-144">Only trailing numerals are significant.</span></span>|  
|<span data-ttu-id="a8014-145">**Начальные и конечные**</span><span class="sxs-lookup"><span data-stu-id="a8014-145">**LeadingAndTrailing**</span></span>|<span data-ttu-id="a8014-146">Значимыми являются и начальные, и конечные цифры.</span><span class="sxs-lookup"><span data-stu-id="a8014-146">Both leading and trailing numerals are significant.</span></span>|  
  
 <span data-ttu-id="a8014-147">**Флаги сравнения**</span><span class="sxs-lookup"><span data-stu-id="a8014-147">**Comparison Flags**</span></span>  
 <span data-ttu-id="a8014-148">Дополнительные сведения о параметрах сравнения строк см. в разделе [Сравнение строковых данных](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="a8014-148">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8014-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8014-149">See Also</span></span>  
 <span data-ttu-id="a8014-150">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a8014-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="a8014-151">Определение подобных строк данных с помощью преобразования «Нечеткое группирование»</span><span class="sxs-lookup"><span data-stu-id="a8014-151">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
