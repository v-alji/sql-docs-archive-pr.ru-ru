---
title: Изучение и очистка данных | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7c888c95-8986-461e-9f11-2395044b9d97
author: minewiskan
ms.author: owend
ms.openlocfilehash: 154c711f735bcbb472e49654139fd16a036a0dd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654577"
---
# <a name="exploring-and-cleaning-data"></a><span data-ttu-id="f856f-102">Исследование и очистка данных</span><span class="sxs-lookup"><span data-stu-id="f856f-102">Exploring and Cleaning Data</span></span>
  <span data-ttu-id="f856f-103">Подготовка данных — это не просто очистка данных.</span><span class="sxs-lookup"><span data-stu-id="f856f-103">Data preparation is much more than data cleansing.</span></span> <span data-ttu-id="f856f-104">Помните, что качество подготовки данных в конечном итоге влияет на интерпретацию результатов.</span><span class="sxs-lookup"><span data-stu-id="f856f-104">Remember that how data is prepared also affects how results are interpreted in the end.</span></span> <span data-ttu-id="f856f-105">Подготовка данных включает в себя следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f856f-105">Data preparation involves these tasks:</span></span>  
  
-   <span data-ttu-id="f856f-106">анализ и проверка распределения данных;</span><span class="sxs-lookup"><span data-stu-id="f856f-106">Exploring and checking the distribution of data.</span></span>  
  
-   <span data-ttu-id="f856f-107">очистка недействительных записей и выбор столбцов для интеллектуального анализа данных;</span><span class="sxs-lookup"><span data-stu-id="f856f-107">Cleaning bad records, and choosing columns for data mining.</span></span>  
  
-   <span data-ttu-id="f856f-108">правильная обработка значений NULL;</span><span class="sxs-lookup"><span data-stu-id="f856f-108">Handling nulls appropriately.</span></span>  
  
-   <span data-ttu-id="f856f-109">группировка или статистическая обработка значений с различными временными блоками;</span><span class="sxs-lookup"><span data-stu-id="f856f-109">Binning values, or aggregating values by different chunks of time.</span></span>  
  
-   <span data-ttu-id="f856f-110">добавление меток для повышения удобства использования результатов;</span><span class="sxs-lookup"><span data-stu-id="f856f-110">Adding labels to improve the usability of the results.</span></span>  
  
-   <span data-ttu-id="f856f-111">преобразование типов данных или классификации значений, если это необходимо для анализа.</span><span class="sxs-lookup"><span data-stu-id="f856f-111">Converting data types or categorizing values where necessary for analysis.</span></span>  
  
 <span data-ttu-id="f856f-112">Если вы не знакомы с моделированием данных, рекомендуем ознакомиться со статьей, посвященной [подготовке интеллектуального анализа данных](checklist-of-preparation-for-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f856f-112">If you are new to data modeling, we recommend that you read the related topic, [Checklist of Preparation for Data Mining](checklist-of-preparation-for-data-mining.md).</span></span>  
  
## <a name="data-preparation-tools"></a><span data-ttu-id="f856f-113">Средства подготовки данных</span><span class="sxs-lookup"><span data-stu-id="f856f-113">Data Preparation Tools</span></span>  
 <span data-ttu-id="f856f-114">Надстройки интеллектуального анализа данных для Office представляют следующие средства для очистки и подготовки данных:</span><span class="sxs-lookup"><span data-stu-id="f856f-114">The Data Mining Add-ins for Office includes the following tools for data cleansing and preparation:</span></span>  
  
### <a name="explore-data"></a><span data-ttu-id="f856f-115">Просмотр данных</span><span class="sxs-lookup"><span data-stu-id="f856f-115">Explore Data</span></span>  
 <span data-ttu-id="f856f-116">Используйте мастер **просмотра данных** для следующих задач подготовки данных:</span><span class="sxs-lookup"><span data-stu-id="f856f-116">Use the **Explore Data** wizard for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="f856f-117">Предварительный просмотр данных и определение ошибок, которые нужно исправить перед анализом.</span><span class="sxs-lookup"><span data-stu-id="f856f-117">Preview your data and identify errors that must be fixed prior to analysis.</span></span>  
  
-   <span data-ttu-id="f856f-118">Сбор статистических данных, которые могут оказаться полезными для понимания баланса данных и необходимых задач очистки.</span><span class="sxs-lookup"><span data-stu-id="f856f-118">Gather statistical information that is useful for understanding the balance of data and the required clean-up tasks.</span></span>  
  
-   <span data-ttu-id="f856f-119">Определение столбцов, полезных для анализа, и планирование этапа моделирования данных.</span><span class="sxs-lookup"><span data-stu-id="f856f-119">Identify columns that are useful for analysis, and plan the data modeling phase.</span></span>  
  
 <span data-ttu-id="f856f-120">[Изучите &#40;данных SQL Server надстройки интеллектуального анализа данных&#41;](explore-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="f856f-120">[Explore Data &#40;SQL Server Data Mining Add-ins&#41;](explore-data-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="detect-and-handle-outliers"></a><span data-ttu-id="f856f-121">Определение и обработка выбросов</span><span class="sxs-lookup"><span data-stu-id="f856f-121">Detect and Handle Outliers</span></span>  
 <span data-ttu-id="f856f-122">Мастер **выбросов** позволяет вычислить распределение значений в данных и помогает удалять крайние значения.</span><span class="sxs-lookup"><span data-stu-id="f856f-122">The **Outliers** wizard graphs the distribution of values in your data and helps you remove extreme values.</span></span> <span data-ttu-id="f856f-123">Используйте инструмент « **выбросы** » для следующих задач подготовки данных:</span><span class="sxs-lookup"><span data-stu-id="f856f-123">Use the **Outliers** tool for the following data preparation tasks:</span></span>  
  
-   <span data-ttu-id="f856f-124">Определение надежности отдельных значений на основе закономерностей, обнаруженных в данных.</span><span class="sxs-lookup"><span data-stu-id="f856f-124">Determine whether individual values are reliable, based on patterns found in the data.</span></span>  
  
-   <span data-ttu-id="f856f-125">Изучение необычных значений и последующее их удаление или замена.</span><span class="sxs-lookup"><span data-stu-id="f856f-125">Review unusual values and take action by deleting or replacing them.</span></span>  
  
-   <span data-ttu-id="f856f-126">Определение области действия модели для определенного диапазона значений.</span><span class="sxs-lookup"><span data-stu-id="f856f-126">Scope a model to a specific range of values.</span></span> <span data-ttu-id="f856f-127">Например, если известно, что в одном магазине присутствуют выбросы, можно устранить эти значения и получить модель, которая создает более эффективные прогнозы для других магазинов.</span><span class="sxs-lookup"><span data-stu-id="f856f-127">For example, if you know that you have outliers at a particular store, you can eliminate that value and get a model that better predicts other stores.</span></span>  
  
 <span data-ttu-id="f856f-128">[Выбросы &#40;SQL Server&#41;надстроек интеллектуального анализа данных ](outliers-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="f856f-128">[Outliers &#40;SQL Server Data Mining Add-ins&#41;](outliers-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="relabel-and-bin-data"></a><span data-ttu-id="f856f-129">Переразметка и преобразование данных в двоичные</span><span class="sxs-lookup"><span data-stu-id="f856f-129">Relabel and Bin Data</span></span>  
 <span data-ttu-id="f856f-130">Мастер **переразметки** группирует данные по значениям, чтобы можно было изменять метки данных.</span><span class="sxs-lookup"><span data-stu-id="f856f-130">The **Relabel** wizard groups data by values so that you can change the labels on the data.</span></span> <span data-ttu-id="f856f-131">Используйте средство «Переразметка» для выполнения следующих задач подготовки данных:</span><span class="sxs-lookup"><span data-stu-id="f856f-131">Use the Relabel tool for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="f856f-132">Изменение числовых кодов, используемых в результатах опроса, для текстового описания значения числовых кодов.</span><span class="sxs-lookup"><span data-stu-id="f856f-132">Change numeric codes used in survey results to a text description of what the numeric code means.</span></span>  
  
     <span data-ttu-id="f856f-133">Например, можно заменить такие входные данные, как «пол = 1» на «пол = женский».</span><span class="sxs-lookup"><span data-stu-id="f856f-133">For example, you might replace data entries such as Gender = 1 with Gender = Female.</span></span>  
  
-   <span data-ttu-id="f856f-134">Двоичные данные путем создания групп, представляющих диапазоны чисел.</span><span class="sxs-lookup"><span data-stu-id="f856f-134">Bin data, by creating groups to represents number ranges.</span></span>  
  
     <span data-ttu-id="f856f-135">Например, может потребоваться заменить столбец доходов чисел такими метками, как **прибыль — средний** и **доход — высокий**.</span><span class="sxs-lookup"><span data-stu-id="f856f-135">For example, you might want to replace an Income column of numbers with labels such as **Income - Moderate** and **Income - High**.</span></span>  
  
-   <span data-ttu-id="f856f-136">Распределение дискретных значений по категориям.</span><span class="sxs-lookup"><span data-stu-id="f856f-136">Collapse discrete values into categories.</span></span>  
  
     <span data-ttu-id="f856f-137">Например, если имеется слишком много отдельных продуктов, чтобы обнаружить закономерность среди покупок, можно попробовать сгруппировать продукты в более общие категории.</span><span class="sxs-lookup"><span data-stu-id="f856f-137">For example, if you have too many individual products to detect a pattern among purchases, you could try assigning products into broader categories.</span></span>  
  
 [<span data-ttu-id="f856f-138">Переразметка &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="f856f-138">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
### <a name="cleanse-data"></a><span data-ttu-id="f856f-139">Очистка данных</span><span class="sxs-lookup"><span data-stu-id="f856f-139">Cleanse Data</span></span>  
 <span data-ttu-id="f856f-140">Очистка данных включает различные действия, большая часть которых поддерживается надстройками</span><span class="sxs-lookup"><span data-stu-id="f856f-140">Data cleansing encompasses a wide range of activities, most of which are supported by the add-ins</span></span>  
  
-   <span data-ttu-id="f856f-141">Распознает значения NULL и определяет, должны они быть заменены на действительные значения или обработаны как значения `Missing`.</span><span class="sxs-lookup"><span data-stu-id="f856f-141">Identify nulls and determine whether they should be changed to a real value or handled as `Missing` values.</span></span>  
  
-   <span data-ttu-id="f856f-142">Обнаружение отсутствующих значений и их удаление или аппроксимация (например, использование среднего значения, NULL или другого значения).</span><span class="sxs-lookup"><span data-stu-id="f856f-142">Detect missing values, and then remove them, or impute an appropriate value, such as a mean, null, or other value.</span></span>  
  
 [<span data-ttu-id="f856f-143">Изучите &#40;данных SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="f856f-143">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="f856f-144">Переразметка &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="f856f-144">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="f856f-145">Заполнение по примеру</span><span class="sxs-lookup"><span data-stu-id="f856f-145">Fill From Example</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
### <a name="sample-data"></a><span data-ttu-id="f856f-146">Образец данных</span><span class="sxs-lookup"><span data-stu-id="f856f-146">Sample Data</span></span>  
 <span data-ttu-id="f856f-147">Мастер образцов данных предоставляет два метода создания сбалансированных наборов данных для обучения и проверки моделей</span><span class="sxs-lookup"><span data-stu-id="f856f-147">The Sample Data wizard provides two methods for creating balanced data sets for training and testing models.</span></span>  
  
-   <span data-ttu-id="f856f-148">**Случайная выборка.**</span><span class="sxs-lookup"><span data-stu-id="f856f-148">**Random sampling.**</span></span> <span data-ttu-id="f856f-149">Используйте этот параметр, чтобы извлечь репрезентативный набор данных из большего набора данных для использования в обучении или тестировании.</span><span class="sxs-lookup"><span data-stu-id="f856f-149">Use this option to extract a representative set of data from a larger data set, for use in either training or testing.</span></span> <span data-ttu-id="f856f-150">Надстройки интеллектуального анализа данных используют *стратифицированной выборку* , чтобы обеспечить получение сбалансированного набора значений для каждой переменной выборки.</span><span class="sxs-lookup"><span data-stu-id="f856f-150">The Data Mining Add-ins use *stratified sampling* to ensure that a balanced set of values is obtained for each variable sampled.</span></span>  
  
-   <span data-ttu-id="f856f-151">**Избыточная выборка.**</span><span class="sxs-lookup"><span data-stu-id="f856f-151">**Oversampling.**</span></span> <span data-ttu-id="f856f-152">Используйте этот параметр, если данных меньше, чем требуется для целевого результата, и нужно назначить этим данным больший вес.</span><span class="sxs-lookup"><span data-stu-id="f856f-152">Use this option when you have less data than you would like for a target outcome, and need to weight that data more heavily.</span></span> <span data-ttu-id="f856f-153">Например, мошенничество может происходить редко, но по имеющимся случаям можно сформировать избыточную выборку для моделирования.</span><span class="sxs-lookup"><span data-stu-id="f856f-153">For example, fraud might be relatively rare, but you can oversample cases involving fraud to get adequate data for modeling.</span></span>  
  
 <span data-ttu-id="f856f-154">[Образец данных &#40;SQL Server надстройки интеллектуального анализа данных&#41;](sample-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="f856f-154">[Sample Data &#40;SQL Server Data Mining Add-ins&#41;](sample-data-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f856f-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="f856f-155">See Also</span></span>  
 <span data-ttu-id="f856f-156">[Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="f856f-156">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="f856f-157">[Проверка моделей и использование моделей для прогнозирования &#40;надстройки интеллектуального анализа данных для Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="f856f-157">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="f856f-158">Развертывание и масштабирование моделей интеллектуального анализа &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="f856f-158">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
