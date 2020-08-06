---
title: Создание отчета перекрестной проверки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- validating data mining models
- mining structures [Analysis Services], how-to topics
- cross-validation [data mining]
- statistical standard deviation
ms.assetid: 7b1fec4c-7053-41eb-b030-5179257967a4
author: minewiskan
ms.author: owend
ms.openlocfilehash: ccbafe63b0026cd45a15ea71fd84e223c1b32a9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727478"
---
# <a name="create-a-cross-validation-report"></a><span data-ttu-id="ac26b-102">создать отчет перекрестной проверки</span><span class="sxs-lookup"><span data-stu-id="ac26b-102">Create a Cross-Validation Report</span></span>
  <span data-ttu-id="ac26b-103">В данном разделе описывается создание отчета перекрестной проверки с помощью вкладки «Диаграмма точности» в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ac26b-103">This topic walks you through creation of a cross-validation report using the Accuracy Chart tab in Data Mining Designer.</span></span> <span data-ttu-id="ac26b-104">Дополнительные сведения о том, как выглядит отчет перекрестной проверки, и содержащихся в нем статистических мерах см. в разделе [Перекрестная проверка (службы Analysis Services — интеллектуальный анализ данных)](cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ac26b-104">For general information about what a cross-validation report looks like, and the statistical measures it includes, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="ac26b-105">Отчет перекрестной проверки существенно отличается от диаграммы точности, в том числе от диаграммы точности прогнозов или матрицы классификации.</span><span class="sxs-lookup"><span data-stu-id="ac26b-105">A cross-validation report is fundamentally different from an accuracy chart, such as a lift chart or classification matrix.</span></span>  
  
-   <span data-ttu-id="ac26b-106">Перекрестная проверка оценивает общее распределение данных, используемых в модели или структуре. Таким образом, пользователь не указывает тестируемый набор данных.</span><span class="sxs-lookup"><span data-stu-id="ac26b-106">Cross-validation assesses the overall distribution of data that is used in a model or structure; therefore, you do not specify a testing data set.</span></span> <span data-ttu-id="ac26b-107">При перекрестной проверке всегда задействованы только исходные данные, использованные для обучения модели или структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ac26b-107">Cross-validation always uses only the original data that was used to train the model or the mining structure.</span></span>  
  
-   <span data-ttu-id="ac26b-108">Перекрестная проверка может выполняться только в отношении одного прогнозируемого результата.</span><span class="sxs-lookup"><span data-stu-id="ac26b-108">Cross-validation can only be performed with respect to a single predictable outcome.</span></span> <span data-ttu-id="ac26b-109">Если структура поддерживает модели, имеющие разные прогнозируемые атрибуты, необходимо создать отдельные отчеты для каждого прогнозируемого результата.</span><span class="sxs-lookup"><span data-stu-id="ac26b-109">If the structure supports models that have different predictable attributes, you must create separate reports for each predictable output.</span></span>  
  
-   <span data-ttu-id="ac26b-110">Для перекрестной проверки доступны только те модели, которые связаны со структурой, выбранной в данный момент.</span><span class="sxs-lookup"><span data-stu-id="ac26b-110">Only models that are related to the currently selected structure are available for cross-validation.</span></span>  
  
-   <span data-ttu-id="ac26b-111">Если выбранная в данный момент структура поддерживает сочетание кластеризованных и некластеризованных моделей, то при нажатии кнопки **Получить результаты**хранимая процедура перекрестной проверки автоматически загрузит модели, имеющие одинаковый прогнозируемый столбец, и проигнорирует кластеризованные модели, у которых нет одинакового прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ac26b-111">If the structure that is currently selected supports a combination of clustering and non-clustering models, when you click **Get Results**, the cross-validation stored procedure will automatically load models that have the same predicted column, and ignore clustering models that do not share the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="ac26b-112">Отчет перекрестной проверки для кластеризованной модели, не имеющей предсказуемого атрибута, можно создать, только если структура интеллектуального анализа данных не поддерживает другие прогнозируемые атрибуты.</span><span class="sxs-lookup"><span data-stu-id="ac26b-112">You can create a cross-validation report on a clustering model that does not have a predictable attribute only if the mining structure does not support any other predictable attributes.</span></span>  
  
### <a name="select-a-mining-structure"></a><span data-ttu-id="ac26b-113">Выбор структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ac26b-113">Select a mining structure</span></span>  
  
1.  <span data-ttu-id="ac26b-114">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте конструктор интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ac26b-114">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="ac26b-115">В обозревателе решений откройте базу данных, содержащую структуру или модель, для которой создается отчет.</span><span class="sxs-lookup"><span data-stu-id="ac26b-115">In Solution Explorer, open the database that contains the structure or model for which you want to create a report.</span></span>  
  
3.  <span data-ttu-id="ac26b-116">Дважды щелкните по структуре интеллектуального анализа данных, чтобы открыть структуру и связанные с ней модели в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ac26b-116">Double-click the mining structure to open the structure and its related models in Data Mining Designer.</span></span>  
  
4.  <span data-ttu-id="ac26b-117">Перейдите на вкладку **Диаграмма точности интеллектуального анализа** .</span><span class="sxs-lookup"><span data-stu-id="ac26b-117">Click the **Mining Accuracy Chart** tab.</span></span>  
  
5.  <span data-ttu-id="ac26b-118">Перейдите на вкладку **Перекрестная проверка** .</span><span class="sxs-lookup"><span data-stu-id="ac26b-118">Click the **Cross Validation** tab.</span></span>  
  
### <a name="set-cross-validation-options"></a><span data-ttu-id="ac26b-119">Установка параметров перекрестной проверки</span><span class="sxs-lookup"><span data-stu-id="ac26b-119">Set cross-validation options</span></span>  
  
1.  <span data-ttu-id="ac26b-120">На вкладке **Перекрестная проверка** щелкните стрелку вниз в поле **Количество сверток**и выберите число от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="ac26b-120">On the **Cross Validation** tab, for **Fold Count**, click the down arrow to select a number between 1 and 10.</span></span> <span data-ttu-id="ac26b-121">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="ac26b-121">The default value is 10.</span></span>  
  
     <span data-ttu-id="ac26b-122">Значение **Количество сверток** представляет число секций, которое будет создано в оригинальном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="ac26b-122">The **Fold Count** represents the number of partitions that will be created within the original data set.</span></span> <span data-ttu-id="ac26b-123">Если установить в поле «Количество сверток» значение 1, обучающий набор будет использован без секционирования.</span><span class="sxs-lookup"><span data-stu-id="ac26b-123">If you set Fold Count to 1, the training set will be used without partitioning.</span></span>  
  
2.  <span data-ttu-id="ac26b-124">Щелкните стрелку вниз поля **Целевой атрибут**и выберите из списка столбец.</span><span class="sxs-lookup"><span data-stu-id="ac26b-124">For **Target Attribute**, click the down arrow, and select a column from the list.</span></span> <span data-ttu-id="ac26b-125">При работе с моделью кластеризации выберите значение **#Cluster** , чтобы указать, что модель не имеет прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ac26b-125">If the model is a clustering model, select **#Cluster** to indicate that the model does not have a predictable attribute.</span></span> <span data-ttu-id="ac26b-126">Обратите внимание, что значение **#Cluster**доступно, только когда структура интеллектуального анализа данных не поддерживает другие типы прогнозируемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ac26b-126">Note that the value, **#Cluster**, is available only when the mining structure does not support other types of predictable attributes.</span></span>  
  
     <span data-ttu-id="ac26b-127">Для каждого отчета можно выбрать только один прогнозируемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="ac26b-127">You can select only one predictable attribute per report.</span></span> <span data-ttu-id="ac26b-128">По умолчанию в отчет включаются все связанные модели, имеющие один и тот же прогнозируемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="ac26b-128">By default, all related models that have the same predictable attribute are included in the report.</span></span>  
  
3.  <span data-ttu-id="ac26b-129">В поле **Максимальное число вариантов**введите число, достаточное для обеспечения репрезентативной выборки данных при их разбиении между указанным числом сверток.</span><span class="sxs-lookup"><span data-stu-id="ac26b-129">For **Max Cases**, type a number that is large enough to provide a representative sample of data when the data is split among the specified number of folds.</span></span> <span data-ttu-id="ac26b-130">Если это число больше числа вариантов в обучающем наборе модели, будут использованы все варианты.</span><span class="sxs-lookup"><span data-stu-id="ac26b-130">If the number is greater than the count of cases in the model training set, all cases will be used.</span></span>  
  
     <span data-ttu-id="ac26b-131">При большом размере набора данных для обучения установка значения **Максимальное число вариантов** ограничивает общее число обработанных вариантов и позволяет ускорить обработку отчета.</span><span class="sxs-lookup"><span data-stu-id="ac26b-131">If the training data set is very large, setting the value for **Max Cases** limits the total number of cases processed, and lets the report finish faster.</span></span> <span data-ttu-id="ac26b-132">Однако не следует занижать значение **Максимальное число вариантов** , поскольку это может привести к недостатку данных для перекрестной проверки.</span><span class="sxs-lookup"><span data-stu-id="ac26b-132">However, you should not set **Max Cases** too low or there may be insufficient data for cross-validation.</span></span>  
  
4.  <span data-ttu-id="ac26b-133">Дополнительно можно ввести в поле **Целевое состояние**значение прогнозируемого атрибута, который следует моделировать.</span><span class="sxs-lookup"><span data-stu-id="ac26b-133">Optionally, for **Target State**, type the value of the predictable attribute that you want to model.</span></span> <span data-ttu-id="ac26b-134">Например, если у столбца «Покупатель велосипеда» есть два возможных значения, 1 (Да) и 2 (Нет), то можно ввести значение 1 для оценки точности модели для получения только нужного результата.</span><span class="sxs-lookup"><span data-stu-id="ac26b-134">For example, if the column [Bike Buyer] has two possible values, 1 (Yes) and 2 (No), you can enter the value 1 to assess the accuracy of the model for just the desired outcome.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ac26b-135"> Если значение не было введено, то параметр **Целевой порог** будет недоступен, а оценка модели будет проведена по всем возможным значениям прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ac26b-135">If you do not enter a value, the **Target Threshold** option is not available, and the model is assessed for all possible values of the predictable attribute.</span></span>  
  
5.  <span data-ttu-id="ac26b-136">Дополнительно можно ввести в поле **Целевой порог**десятичную дробь от 0 до 1, чтобы указать минимальную вероятность, при которой прогноз может считаться точным.</span><span class="sxs-lookup"><span data-stu-id="ac26b-136">Optionally, for **Target Threshold**, type a decimal number between 0 and 1 to specify the minimum probability that a prediction must have to be counted as accurate.</span></span>  
  
     <span data-ttu-id="ac26b-137">Дополнительные советы по установке порогов вероятности см. в разделе [Меры в отчете перекрестной проверки](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="ac26b-137">For additional tips about how to set probability thresholds, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
6.  <span data-ttu-id="ac26b-138">Щелкните **Получить результаты**.</span><span class="sxs-lookup"><span data-stu-id="ac26b-138">Click **Get Results**.</span></span>  
  
### <a name="print-the-cross-validation-report"></a><span data-ttu-id="ac26b-139">Печать отчета перекрестной проверки</span><span class="sxs-lookup"><span data-stu-id="ac26b-139">Print the cross-validation report</span></span>  
  
1.  <span data-ttu-id="ac26b-140">Щелкните правой кнопкой мыши готовый отчет на вкладке **Перекрестная проверка** .</span><span class="sxs-lookup"><span data-stu-id="ac26b-140">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="ac26b-141">В контекстном меню выберите пункт **Печать** или **Предварительный просмотр печати** , чтобы выполнить предварительный просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="ac26b-141">In the shortcut menu, select **Print** or **Print Preview** to review the report first.</span></span>  
  
### <a name="create-a-copy-of-the-report-in-microsoft-excel"></a><span data-ttu-id="ac26b-142">Создание копии отчета в Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="ac26b-142">Create a copy of the report in Microsoft Excel</span></span>  
  
1.  <span data-ttu-id="ac26b-143">Щелкните правой кнопкой мыши готовый отчет на вкладке **Перекрестная проверка** .</span><span class="sxs-lookup"><span data-stu-id="ac26b-143">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="ac26b-144">В контекстном меню выберите команду **Выделить все**.</span><span class="sxs-lookup"><span data-stu-id="ac26b-144">In the shortcut menu, select **Select All**.</span></span>  
  
3.  <span data-ttu-id="ac26b-145">Щелкните правой кнопкой мыши выделенный текст и выберите пункт **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="ac26b-145">Right-click the selected text, and select **Copy**.</span></span>  
  
4.  <span data-ttu-id="ac26b-146">Вставьте выбранный текст в открытую книгу Excel.</span><span class="sxs-lookup"><span data-stu-id="ac26b-146">Paste the selection into an open Excel workbook.</span></span> <span data-ttu-id="ac26b-147">Если использовалась команда **Вставить** , отчет будет вставлен в Excel как HTML; это сохранит форматирование строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="ac26b-147">If you use the **Paste** option, the report is pasted into Excel as HTML, which preserves row and column formatting.</span></span> <span data-ttu-id="ac26b-148">Если для вставки отчета использовалась команда **Специальная вставка** для текста или текста в формате Юникод, отчет будет вставлен в формате с разделителями строк.</span><span class="sxs-lookup"><span data-stu-id="ac26b-148">If you paste the report by using the **Paste Special** options for text or Unicode text, the report is pasted in row-delimited format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac26b-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac26b-149">See Also</span></span>  
 [<span data-ttu-id="ac26b-150">Меры в отчете перекрестной проверки</span><span class="sxs-lookup"><span data-stu-id="ac26b-150">Measures in the Cross-Validation Report</span></span>](measures-in-the-cross-validation-report.md)  
  
  
