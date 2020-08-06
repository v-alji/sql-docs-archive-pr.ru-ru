---
title: Анализ ключевых факторов влияния (средства анализа таблиц для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- key influencers
- factor analysis
ms.assetid: 54d7b4ce-7b79-407a-985c-aa655ad19280
author: minewiskan
ms.author: owend
ms.openlocfilehash: f60eb5144059b0976d52eec2329f27553132146c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656897"
---
# <a name="analyze-key-influencers-table-analysis-tools-for-excel"></a><span data-ttu-id="e6c4c-102">Анализ ключевых факторов влияния (средства анализа таблиц для Excel)</span><span class="sxs-lookup"><span data-stu-id="e6c4c-102">Analyze Key Influencers (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="e6c4c-103">![Кнопка «Анализ ключевых факторов влияния» на ленте](media/tat-aki.gif "Кнопка «Анализ ключевых факторов влияния» на ленте")</span><span class="sxs-lookup"><span data-stu-id="e6c4c-103">![Analyze Key Influencers button in ribbon](media/tat-aki.gif "Analyze Key Influencers button in ribbon")</span></span>  
  
 <span data-ttu-id="e6c4c-104">С помощью средства **Анализ ключевых факторов влияния** вы выбираете столбец, содержащий целевой результат, и алгоритм определяет, какие факторы приводят к наибольшему влиянию на результат.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-104">With the **Analyze Key Influencers** tool, you choose a column that contains a target outcome, and the algorithm determines which factors had the strongest influence on the outcome.</span></span>  
  
 <span data-ttu-id="e6c4c-105">Средство создает новые таблицы данных с факторами, связанными с каждым результатом, и графически отображает вероятность связи между ними.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-105">The tool creates new data tables that report the factors associated with each outcome and graphically displays the probability of the relationship.</span></span> <span data-ttu-id="e6c4c-106">Эти таблицы можно отфильтровать по различным факторам и результатам, чтобы подробнее проанализировать результаты.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-106">You can filter the tables by different factors and outcomes to explore the results in more depth.</span></span>  
  
 <span data-ttu-id="e6c4c-107">Вы также можете выбрать пару возможных результатов и сравнить их.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-107">You can also select a pair of possible outcomes and compare them.</span></span> <span data-ttu-id="e6c4c-108">Например, можно сравнить различные группы потребителей, чтобы определить факторы, влияющие на принятие решений.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-108">For example, you might compare different groups of consumers to determine possible decision-making factors.</span></span>  
  
## <a name="using-the-analyze-key-influencers-tool"></a><span data-ttu-id="e6c4c-109">Использование средства «Анализ ключевых факторов влияния»</span><span class="sxs-lookup"><span data-stu-id="e6c4c-109">Using the Analyze Key Influencers Tool</span></span>  
  
1.  <span data-ttu-id="e6c4c-110">Откройте таблицу данных Excel.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-110">Open an Excel data table.</span></span>  
  
2.  <span data-ttu-id="e6c4c-111">В окне **инструменты таблицы**на ленте **анализ** щелкните **Анализ ключевых факторов влияния.**</span><span class="sxs-lookup"><span data-stu-id="e6c4c-111">In **Table Tools**, on the **Analyze** ribbon, click **Analyze Key Influencers.**</span></span>  
  
3.  <span data-ttu-id="e6c4c-112">Выберите столбец, который будет целью анализа.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-112">Select the single column that is the target of analysis.</span></span>  
  
4.  <span data-ttu-id="e6c4c-113">При необходимости нажмите кнопку **выбрать столбцы, которые будут использоваться для анализа**.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-113">Optionally, click **Choose columns to be used for analysis**.</span></span> <span data-ttu-id="e6c4c-114">В диалоговом окне **Выбор дополнительных столбцов** выберите столбцы, которые, скорее всего, будут содержать нужные данные.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-114">In the **Advanced Columns Selection** dialog box, choose the columns that are most likely to contain relevant data.</span></span> <span data-ttu-id="e6c4c-115">Чтобы повысить производительность и точность, отмените выбор столбцов, например идентификатора или имени, не относящихся к анализу закономерностей.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-115">To improve performance and accuracy, deselect columns such as ID or name that are unimportant for pattern analysis.</span></span> <span data-ttu-id="e6c4c-116">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Выбор дополнительных столбцов** .</span><span class="sxs-lookup"><span data-stu-id="e6c4c-116">Click **OK** to close the **Advanced Columns Selection** dialog box.</span></span>  
  
5.  <span data-ttu-id="e6c4c-117">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-117">Click **Run**.</span></span>  
  
     <span data-ttu-id="e6c4c-118">Средство **Анализ ключевых факторов влияния** выполняет анализ данных для определения оптимальных параметров и автоматически задает все параметры.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-118">The **Analyze Key Influencers** tool conducts an analysis of the data to determine the optimum settings, and sets all parameters automatically.</span></span>  
  
6.  <span data-ttu-id="e6c4c-119">Если закономерности не были обнаружены, то мастер создаст новый лист, в котором будет описана проблема.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-119">If no patterns were detected, the wizard creates a new worksheet that contains a description of the problem.</span></span>  
  
7.  <span data-ttu-id="e6c4c-120">При обнаружении закономерностей мастер создаст на новом листе отчет, в котором будут отображены эти закономерности.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-120">If patterns are detected, the wizard creates a report on a new worksheet that shows the patterns.</span></span> <span data-ttu-id="e6c4c-121">Отчет называется \*\*ключевыми факторами влияния для \<column> \*\*.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-121">The report is named **Key Influencers for \<column>**.</span></span> <span data-ttu-id="e6c4c-122">Отчет можно настроить, как это описано в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-122">You can customize the report as described in the following procedure.</span></span>  
  
#### <a name="create-a-custom-report"></a><span data-ttu-id="e6c4c-123">Создание пользовательского отчета</span><span class="sxs-lookup"><span data-stu-id="e6c4c-123">Create a custom report</span></span>  
  
1.  <span data-ttu-id="e6c4c-124">В диалоговом окне **Сравнение на основе ключевых факторов влияния** выберите два значения, которые необходимо сравнить, выбрав их в раскрывающихся списках **значение 1** и **значение 2** .</span><span class="sxs-lookup"><span data-stu-id="e6c4c-124">In the **Discrimination based on key influencers** dialog box, choose the two values that you want to compare by selecting them from the **Value 1** and **Value 2** dropdown lists.</span></span> <span data-ttu-id="e6c4c-125">Например, можно сравнить покупателей и тех, кто не покупает.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-125">For example, you might compare buyers to non-buyers.</span></span>  
  
2.  <span data-ttu-id="e6c4c-126">Нажмите кнопку **Добавить отчет**.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-126">Click **Add Report**.</span></span>  
  
     <span data-ttu-id="e6c4c-127">Мастер создаст новый лист и добавит таблицу для каждой пары сравнения ключевых факторов влияния.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-127">The wizard creates a new worksheet and adds a table for each pair of key factor comparisons.</span></span>  
  
3.  <span data-ttu-id="e6c4c-128">Завершив сравнение, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-128">When you are done making comparisons, click **Close**.</span></span>  
  
## <a name="understanding-the-key-influencers-report"></a><span data-ttu-id="e6c4c-129">Основные сведения об отчете по ключевым факторам влияния</span><span class="sxs-lookup"><span data-stu-id="e6c4c-129">Understanding the Key Influencers Report</span></span>  
 <span data-ttu-id="e6c4c-130">После создания модели данных средство **Анализ ключевых факторов влияния** создает отчеты, помогающие исследовать и сравнивать ключевые факторы влияния.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-130">After the data model has been created, the **Analyze Key Influencers** tool creates reports that help you explore and compare key influencers.</span></span>  
  
-   <span data-ttu-id="e6c4c-131">Отчет в левой части создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-131">The report on the left side is the one generated by default.</span></span> <span data-ttu-id="e6c4c-132">В нем отображаются столбцы, которые лучше всего подходят для прогнозирования столбца итогового результата (зависимой переменной).</span><span class="sxs-lookup"><span data-stu-id="e6c4c-132">It shows the strongest predictors of the outcome column (the dependent variable).</span></span>  
  
-   <span data-ttu-id="e6c4c-133">Отчет, отображаемый в правой части, является необязательным. Его можно создать путем сравнения двух конкретных значений результатов.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-133">The report on the right side is optional, which you can create by comparing two specific outcome values.</span></span> <span data-ttu-id="e6c4c-134">Этот отчет сравнивает тех, кто купил, и тех, кто не купил.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-134">This report compares buyers and non-buyers.</span></span>  
  
-   <span data-ttu-id="e6c4c-135">Обратите внимание, что новый лист добавляется для каждого создаваемого отчета.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-135">Note that a new worksheet is added for each report that you create.</span></span> <span data-ttu-id="e6c4c-136">Таблицы после их создания можно перемещать. Для сравнения мы разместили их рядом друг с другом.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-136">You can move the tables after they are created; we placed them side by side for comparison.</span></span>  
  
 <span data-ttu-id="e6c4c-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span><span class="sxs-lookup"><span data-stu-id="e6c4c-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span></span>  
  
 <span data-ttu-id="e6c4c-138">**Относительное влияние**</span><span class="sxs-lookup"><span data-stu-id="e6c4c-138">**Relative Impact**</span></span>  
 <span data-ttu-id="e6c4c-139">Затененная полоса в первом отчете показывает степень взаимосвязи этого атрибута с результатом.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-139">The shaded bar in the first report indicates the strength of the association of this attribute with the outcome.</span></span>  
  
 <span data-ttu-id="e6c4c-140">Длина полосы показывает вероятность влияния фактора на результат и, следовательно, чем она длиннее, тем теснее взаимосвязь.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-140">The length of the bar indicates the probability that the factor contributes to the outcome; therefore, the longer the shaded bar, the stronger the association.</span></span>  
  
 <span data-ttu-id="e6c4c-141">**Подходит**</span><span class="sxs-lookup"><span data-stu-id="e6c4c-141">**Favors**</span></span>  
 <span data-ttu-id="e6c4c-142">Во втором отчете сравниваемые целевые значения приведены в двух столбцах, а связанные факторы указаны в порядке нисходящей достоверности.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-142">In the second report, the target values that you compare are listed in two columns, with the related factors listed in order of descending confidence.</span></span>  
  
-   <span data-ttu-id="e6c4c-143">**Синяя** полоса показывает атрибуты, влияющие на результат «нет» (= не приобретается).</span><span class="sxs-lookup"><span data-stu-id="e6c4c-143">The **blue** bar shows attributes contributing to the outcome, "No" (=did not purchase).</span></span>  
  
-   <span data-ttu-id="e6c4c-144">**Красная** полоса показывает атрибуты, влияющие на результат "Да" (= куплен велосипед).</span><span class="sxs-lookup"><span data-stu-id="e6c4c-144">The **red** bar shows attributes contributing to the outcome, "Yes" (=purchased a bike).</span></span>  
  
 <span data-ttu-id="e6c4c-145">Цвета заливки произвольные.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-145">The colors in the shading bar are arbitrary.</span></span> <span data-ttu-id="e6c4c-146">Цвета можно изменить путем задания параметров для проекта таблицы в Excel.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-146">You can change these colors by setting the options for table design in Excel.</span></span>  
  
 <span data-ttu-id="e6c4c-147">При создании отчета, сравнивающего два значения, во втором отчете ключевые факторы влияния сортируются с учетом их влияния на целевые значения.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-147">In a report that contrasts two values, the second report ranks the key influencers by the amount of impact on the target values.</span></span>  
  
 <span data-ttu-id="e6c4c-148">Поскольку все диаграммы созданы на основе таблиц Excel, данные можно фильтровать и сортировать для выделения определенных факторов или результатов.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-148">Because all the charts are based on Excel tables, you can filter and sort to focus on specific factors or outcomes.</span></span>  
  
## <a name="more-about-the-analyze-key-influencers-tool"></a><span data-ttu-id="e6c4c-149">Дополнительные сведения об использовании средства «Анализ ключевых факторов влияния»</span><span class="sxs-lookup"><span data-stu-id="e6c4c-149">More About the Analyze Key Influencers Tool</span></span>  
 <span data-ttu-id="e6c4c-150">Когда средство **Анализ ключевых факторов влияния** анализирует данные, оно выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e6c4c-150">When the **Analyze Key Influencers** tool analyzes your data, it does the following:</span></span>  
  
-   <span data-ttu-id="e6c4c-151">Создает структуру данных, в которой хранятся основные сведения о распределении данных.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-151">Creates a data structure that stores key information about the distribution of your data.</span></span>  
  
-   <span data-ttu-id="e6c4c-152">Создает модель с помощью упрощенного алгоритма Байеса (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="e6c4c-152">Creates a model using the Microsoft Naïve Bayes algorithm.</span></span>  
  
-   <span data-ttu-id="e6c4c-153">Создает прогнозы, в которых каждый столбец данных связывается с указанным результатом.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-153">Creates predictions that correlates each column of data with the specified outcome.</span></span>  
  
-   <span data-ttu-id="e6c4c-154">Использует показатель достоверности для каждого из прогнозов с целью определения факторов, оказывающих наибольшее влияние при получении целевого результата.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-154">Uses the confidence score for each of the predictions to identify the factors that are the most influential in producing the targeted outcome.</span></span>  
  
-   <span data-ttu-id="e6c4c-155">Создает отчет, в котором описываются ключевые факторы влияния, упорядоченные по достоверности.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-155">Creates a report describing the key influencers, ordered by confidence scores.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="e6c4c-156">Требования</span><span class="sxs-lookup"><span data-stu-id="e6c4c-156">Requirements</span></span>  
 <span data-ttu-id="e6c4c-157">Если целевой столбец содержит непрерывные числовые значения, они автоматически сегментируются на группы.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-157">If the target column contains continuous numeric values, the tool automatically segments the numeric values into groups.</span></span> <span data-ttu-id="e6c4c-158">Эти группы представляют собой кластеры вариантов, имеющих схожие характеристики.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-158">These groupings represent clusters of cases that have similar characteristics.</span></span> <span data-ttu-id="e6c4c-159">Однако числовые значения могут быть не разделены на удобные для пользователей группы.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-159">However, numeric values might not be divided into user-friendly groups.</span></span> <span data-ttu-id="e6c4c-160">Например, отчет может содержать группирование « \< 12,85701», в то время как пользователи отчетов обычно должны видеть группирования, использующие целые числа, такие как 10-19, 20-29 и т. д.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-160">For example, the report might contain a grouping such as "\<12.85701", whereas report users typically like to see groupings that use whole numbers, such as 10-19, 20-29, and so on.</span></span>  
  
 <span data-ttu-id="e6c4c-161">Если требуется сгруппировать числовые данные по-другому, то перед созданием анализа их необходимо соответствующим образом сегментировать.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-161">If you want to group numeric data in a different way, you must segment the data the way you want before creating the analysis.</span></span> <span data-ttu-id="e6c4c-162">Например, можно использовать средство [Переразметка](relabel-sql-server-data-mining-add-ins.md) в клиенте интеллектуального анализа данных для Excel, чтобы создать новую метку группирования в отдельном столбце, а затем использовать только этот новый столбец в анализе.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-162">For example, you can use the [Relabel](relabel-sql-server-data-mining-add-ins.md) tool in the Data Mining Client for Excel to create a new grouping label in a separate column, and then use only that new column in analysis.</span></span>  
  
### <a name="related-tools"></a><span data-ttu-id="e6c4c-163">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="e6c4c-163">Related Tools</span></span>  
 <span data-ttu-id="e6c4c-164">На ленте **интеллектуальный анализ данных** предоставляются более сложные средства, включая возможность настройки моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-164">The **Data Mining** ribbon provides more advanced tools, including the ability to customize data mining models</span></span>  
  
 <span data-ttu-id="e6c4c-165">При сохранении модели с помощью средства **Анализ ключевых факторов влияния** можно использовать клиент интеллектуального анализа данных для просмотра модели и более подробного изучения связей.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-165">If you save your model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="e6c4c-166">Дополнительные сведения см. [в разделе Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e6c4c-166">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span> <span data-ttu-id="e6c4c-167">Microsoft Office Visio можно использовать для создания графиков и схем, отображающих связи в виде кластеров или сетей зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-167">You can also use Microsoft Office Visio to create charts and diagrams that display the relationships as cluster or as dependency networks.</span></span> <span data-ttu-id="e6c4c-168">Дополнительные сведения см. в разделе [Устранение неполадок диаграмм интеллектуального анализа данных Visio &#40;SQL Server надстроек интеллектуального анализа данных&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e6c4c-168">For more information, see [Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6c4c-169">Модели, создаваемые при работе со средствами анализа таблиц, удаляются при закрытии листа или разрыве соединения с сервером служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6c4c-169">The models that are created when you use the Table Analysis Tools are deleted when you close your worksheet or terminate the connection with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span> <span data-ttu-id="e6c4c-170">В связи с этим можно только просматривать модели, пока соединение остается открытым.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-170">Therefore, you can only browse the models as long as the connection remains open.</span></span> <span data-ttu-id="e6c4c-171">Невозможно подготовить модели к просмотру в Visio после разрыва соединения или закрытия листа.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-171">You cannot render the models in Visio if you close the connection or close the worksheet.</span></span>  
  
 <span data-ttu-id="e6c4c-172">Дополнительные сведения о алгоритме, используемом средством **анализа ключевых факторов влияния** , см. в подразделе "упрощенный алгоритм Байеса (Майкрософт)" в Электронная документация на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6c4c-172">For more information about the algorithm used by the **Analyze Key Influencers** tool, see "Microsoft Naïve Bayes Algorithm" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6c4c-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6c4c-173">See Also</span></span>  
 <span data-ttu-id="e6c4c-174">[Средства анализа таблиц для Excel](table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="e6c4c-174">[Table Analysis Tools for Excel](table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="e6c4c-175">Создание модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="e6c4c-175">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
