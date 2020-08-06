---
title: Определение содержимого и типа данных столбца (мастер интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0634be64-4c38-4381-9b19-fe9a5889306c
author: minewiskan
ms.author: owend
ms.openlocfilehash: e22f46808877391376f721bcab55ea4fd9074186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658433"
---
# <a name="specify-column-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="e6cd0-102">Задание содержимого столбца и типа данных (мастер интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="e6cd0-102">Specify Column Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="e6cd0-103">Используйте страницу **Определение содержимого и типа данных столбцов** , чтобы указать назначение и тип данных каждого столбца, выбранного на предыдущей странице мастера.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-103">Use the **Specify Column Content and Data Type** page to specify the usage and data type for each column that you selected on the previous page of the wizard.</span></span> <span data-ttu-id="e6cd0-104">Если требуется пропустить данный столбец, нажмите кнопку **Назад** , чтобы вернуться к странице **Определение обучающих данных**, и снимите все флажки.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-104">If you want to ignore the column, click **Back** to return to the page **Specify the Training Data**, and clear all checkboxes.</span></span>  
  
 <span data-ttu-id="e6cd0-105">Назначение столбца показывает, как его данные будут использоваться в модели.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-105">The usage of a column indicates how the data will be used in the model.</span></span> <span data-ttu-id="e6cd0-106">Столбец может использоваться как ключ для определения ряда, как входное значение для анализа или как прогнозируемое значение.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-106">A column can be used as a key to identify a series, as an input value to use in analysis, or as the value that you want to predict.</span></span> <span data-ttu-id="e6cd0-107">Столбцы могут использоваться и для прогноза, и для входных данных.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-107">Columns can be used for both prediction and input.</span></span>  
  
 <span data-ttu-id="e6cd0-108">Тип данных определяет дополнительные сведения о типе данных, содержащихся в столбце, а также как эти данные будут использоваться во время обучения.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-108">The data type specifies additional detail about the type of data that is contained in the column, and how the data will be used during training.</span></span> <span data-ttu-id="e6cd0-109">Некоторые типы содержимого требуют конкретных типов данных, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-109">Some content types require a specific data type, and vice versa.</span></span> <span data-ttu-id="e6cd0-110">Может также потребоваться указать конкретный тип данных в зависимости от алгоритма, используемого при создании модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-110">You might also need to specify a particular data type depending on the algorithm that you use when you create a mining model.</span></span> <span data-ttu-id="e6cd0-111">Дополнительные сведения о типах содержимого и типах данных в моделях и структурах интеллектуального анализа данных см. в разделе [Типы содержимого (интеллектуальный анализ данных)](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="e6cd0-111">For information about content types and data types in mining models and structures, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="e6cd0-112">**Дополнительные сведения:** [Структуры интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/mining-structures-analysis-services-data-mining.md), [Столбцы модели интеллектуального анализа данных](data-mining/mining-model-columns.md), [Мастер интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Создание реляционной структуры интеллектуального анализа данных](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="e6cd0-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="e6cd0-113">Варианты</span><span class="sxs-lookup"><span data-stu-id="e6cd0-113">Options</span></span>  
 <span data-ttu-id="e6cd0-114">**Структура модели интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="e6cd0-114">**Mining model structure**</span></span>  
 <span data-ttu-id="e6cd0-115">Отображает столбцы из представлений и вложенных таблиц, выбранных на предыдущей странице мастера.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-115">Displays the columns from the views and nested tables that you selected on the previous page of the wizard.</span></span>  
  
 <span data-ttu-id="e6cd0-116">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="e6cd0-116">**Columns**</span></span>  
 <span data-ttu-id="e6cd0-117">Содержит столбцы.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-117">Lists the columns.</span></span>  
  
 <span data-ttu-id="e6cd0-118">**Тип содержимого**</span><span class="sxs-lookup"><span data-stu-id="e6cd0-118">**Content type**</span></span>  
 <span data-ttu-id="e6cd0-119">Укажите тип содержимого для столбца.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-119">Specify the content type for the column.</span></span> <span data-ttu-id="e6cd0-120">Если на предыдущей странице мастера указано, что столбец является ключом, доступны следующие значения.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-120">If you specified that the column is a key on the previous page of the wizard, the following values are available:</span></span>  
  
|<span data-ttu-id="e6cd0-121">Параметр</span><span class="sxs-lookup"><span data-stu-id="e6cd0-121">Option</span></span>|<span data-ttu-id="e6cd0-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e6cd0-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e6cd0-123">Клавиши</span><span class="sxs-lookup"><span data-stu-id="e6cd0-123">Key</span></span>|<span data-ttu-id="e6cd0-124">Указать, что столбец содержит уникальный идентификатор для ряда вариантов.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-124">Specify that the column contains a unique identifier for the case series.</span></span>|  
|<span data-ttu-id="e6cd0-125">Ключевая последовательность</span><span class="sxs-lookup"><span data-stu-id="e6cd0-125">Key Sequence</span></span>|<span data-ttu-id="e6cd0-126">Указать, что столбец содержит идентификатор последовательности.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-126">Specify that the column contains a sequence identifier.</span></span>|  
|<span data-ttu-id="e6cd0-127">Ключевой столбец времени</span><span class="sxs-lookup"><span data-stu-id="e6cd0-127">Key Time</span></span>|<span data-ttu-id="e6cd0-128">Указать, что столбец содержит дату или другое уникальное число из непрерывного ряда чисел, которое используется для определения ряда даты или времени.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-128">Specify that the column contains a date or other unique continuous number that is used to identify a date or time series.</span></span>|  
  
 <span data-ttu-id="e6cd0-129">Если столбец выбран в качестве неключевого столбца, доступны следующие значения, зависящие от типа данных.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-129">If you selected the column as a non-key column, the following values are available, depending on the data type:</span></span>  
  
|<span data-ttu-id="e6cd0-130">Параметр</span><span class="sxs-lookup"><span data-stu-id="e6cd0-130">Option</span></span>|<span data-ttu-id="e6cd0-131">Описание</span><span class="sxs-lookup"><span data-stu-id="e6cd0-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e6cd0-132">С задержкой</span><span class="sxs-lookup"><span data-stu-id="e6cd0-132">Continuous</span></span>|<span data-ttu-id="e6cd0-133">Указать, что столбец содержит числовые значения из непрерывного ряда чисел.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-133">Specify that the column contains continuous numeric values.</span></span>|  
|<span data-ttu-id="e6cd0-134">Дискретизированный</span><span class="sxs-lookup"><span data-stu-id="e6cd0-134">Discretized</span></span>|<span data-ttu-id="e6cd0-135">Указать, что столбец содержит числовые значения, которые либо были дискретизированы, либо могут рассматриваться как дискретные.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-135">Specify that the column contains numeric values that either have been discretized, or can be treated as discrete values.</span></span>|  
|<span data-ttu-id="e6cd0-136">Discrete</span><span class="sxs-lookup"><span data-stu-id="e6cd0-136">Discrete</span></span>|<span data-ttu-id="e6cd0-137">Указать, что столбец содержит текст или другие нечисловые значения.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-137">Specify that the column contains text or other nonnumeric values.</span></span>|  
  
 <span data-ttu-id="e6cd0-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="e6cd0-138">**Data type**</span></span>  
 <span data-ttu-id="e6cd0-139">Указать тип данных для столбца.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-139">Specify the data type for the column.</span></span>  
  
 <span data-ttu-id="e6cd0-140">Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e6cd0-140">The following values are available:</span></span>  
  
-   `Boolean`  
  
-   `Date`  
  
-   `Double`  
  
-   `Long`  
  
-   `Text`  
  
 <span data-ttu-id="e6cd0-141">**Detect**</span><span class="sxs-lookup"><span data-stu-id="e6cd0-141">**Detect**</span></span>  
 <span data-ttu-id="e6cd0-142">Проанализировать образец данных во всех числовых столбцах.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-142">Analyze a sample of data in all numeric columns.</span></span> <span data-ttu-id="e6cd0-143">Заменяет указанные значения **Тип содержимого** рекомендуемым типом содержимого.</span><span class="sxs-lookup"><span data-stu-id="e6cd0-143">Replaces specified **Content Type** values with a recommended content type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6cd0-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6cd0-144">See Also</span></span>  
 <span data-ttu-id="e6cd0-145">[Справка F1 мастера интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e6cd0-145">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="e6cd0-146">[Предлагать связанные столбцы &#40;мастер интеллектуального анализа данных&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e6cd0-146">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="e6cd0-147">[Определение типов таблиц &#40;мастера интеллектуального анализа данных&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e6cd0-147">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="e6cd0-148">Укажите содержимое столбца и тип данных &#40;мастер интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="e6cd0-148">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
