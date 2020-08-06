---
title: Определение категорий (средства анализа таблиц для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- clustering [data mining]
- mining model, decision tree
- category detection
ms.assetid: 3c7e9ebb-d0c9-498e-a9ba-cc13eaa43520
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4874c85d7e4ab65716741e8ae9433406dfb08b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737181"
---
# <a name="detect-categories-table-analysis-tools-for-excel"></a><span data-ttu-id="732fc-102">Поиск категорий (средства анализа таблиц для Excel)</span><span class="sxs-lookup"><span data-stu-id="732fc-102">Detect Categories (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="732fc-103">![Кнопка «Поиск категорий» на ленте](media/tat-detectcat.gif "Кнопка «Поиск категорий» на ленте")</span><span class="sxs-lookup"><span data-stu-id="732fc-103">![Detect Categories button in ribbon](media/tat-detectcat.gif "Detect Categories button in ribbon")</span></span>

 <span data-ttu-id="732fc-104">Средство « **Поиск категорий** » автоматически находит строки в таблице, имеющие аналогичные характеристики.</span><span class="sxs-lookup"><span data-stu-id="732fc-104">The **Detect Categories** tool automatically finds rows in a table that have similar characteristics.</span></span>

 <span data-ttu-id="732fc-105">После завершения работы средства создается отчет со списком найденных категорий вместе с их отличительными характеристиками.</span><span class="sxs-lookup"><span data-stu-id="732fc-105">When the tool finishes, it creates a report that lists the categories it found, together with their distinguishing characteristics.</span></span> <span data-ttu-id="732fc-106">По умолчанию в таблицу данных добавляется новый столбец с предлагаемой категорией для каждой строки данных.</span><span class="sxs-lookup"><span data-stu-id="732fc-106">By default, it adds a new column to the data table that contains the proposed category for each row of your data.</span></span> <span data-ttu-id="732fc-107">Затем можно просмотреть категории и переименовать их.</span><span class="sxs-lookup"><span data-stu-id="732fc-107">You can then review the categories and rename them.</span></span>

## <a name="using-the-detect-categories-tool"></a><span data-ttu-id="732fc-108">Использование средства «Поиск категорий»</span><span class="sxs-lookup"><span data-stu-id="732fc-108">Using the Detect Categories Tool</span></span>

1.  <span data-ttu-id="732fc-109">Откройте таблицу Excel.</span><span class="sxs-lookup"><span data-stu-id="732fc-109">Open an Excel table.</span></span>

2.  <span data-ttu-id="732fc-110">Нажмите кнопку " **найти категории**".</span><span class="sxs-lookup"><span data-stu-id="732fc-110">Click **Detect Categories**.</span></span>

3.  <span data-ttu-id="732fc-111">Укажите столбцы, используемые при анализе.</span><span class="sxs-lookup"><span data-stu-id="732fc-111">Specify the columns to use in analysis.</span></span> <span data-ttu-id="732fc-112">Можно отменить выбор столбцов с индивидуальными значениями, например личные имена или идентификаторы записи, поскольку эти столбцы могут быть непригодны для анализа.</span><span class="sxs-lookup"><span data-stu-id="732fc-112">You can deselect columns that have distinct values, such as personal names or record IDs, because these columns might not be useful for analysis.</span></span>

4.  <span data-ttu-id="732fc-113">Дополнительно можно указать максимальное число создаваемых категорий.</span><span class="sxs-lookup"><span data-stu-id="732fc-113">Optionally, specify the maximum number of categories to create.</span></span> <span data-ttu-id="732fc-114">По умолчанию средство автоматически создает столько категорий, сколько удается найти.</span><span class="sxs-lookup"><span data-stu-id="732fc-114">By default, the tool automatically creates as many categories as it finds.</span></span>

5.  <span data-ttu-id="732fc-115">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="732fc-115">Click **Run**.</span></span>

6.  <span data-ttu-id="732fc-116">Средство создает новый лист с именем «Отчет по категориям», содержащий список категорий и их характеристики.</span><span class="sxs-lookup"><span data-stu-id="732fc-116">The tool creates a new worksheet, named Categories Report, which contains the list of categories and their characteristics.</span></span>

 <span data-ttu-id="732fc-117">Дополнительные сведения об указании параметров для средства см. в разделе [диалоговое окно «Определение категорий» (средства анализа таблиц для Excel)](detect-categories-table-analysis-tools-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="732fc-117">For more information about how to specify options for the tool, see [Detect Categories Dialog Box (Table Analysis Tools for Excel)](detect-categories-table-analysis-tools-for-excel.md).</span></span>

## <a name="understanding-the-categories-report"></a><span data-ttu-id="732fc-118">Основные сведения об отчете о категориях</span><span class="sxs-lookup"><span data-stu-id="732fc-118">Understanding the Categories Report</span></span>
 <span data-ttu-id="732fc-119">**Отчет о категориях** содержит две таблицы, характеристики **списка категорий** и **категорий**, а также диаграмму **профилей категорий** .</span><span class="sxs-lookup"><span data-stu-id="732fc-119">The **Categories Report** contains two tables, **Category List** and **Category Characteristics**, and a **Category Profiles** chart.</span></span>

### <a name="category-list"></a><span data-ttu-id="732fc-120">Список категорий</span><span class="sxs-lookup"><span data-stu-id="732fc-120">Category List</span></span>
 <span data-ttu-id="732fc-121">В первой таблице перечислены обнаруженные категории.</span><span class="sxs-lookup"><span data-stu-id="732fc-121">The first table lists the categories that were found.</span></span> <span data-ttu-id="732fc-122">Столбец **число строк** показывает, сколько строк данных было назначено каждой категории.</span><span class="sxs-lookup"><span data-stu-id="732fc-122">The **Row Count** column indicates how many rows of data were assigned to each category.</span></span>

 <span data-ttu-id="732fc-123">Модель создает временные имена для каждой категории, но вы можете переименовывать категории по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="732fc-123">The model creates temporary names for each category, but you can rename the categories as you like.</span></span> <span data-ttu-id="732fc-124">Например, в следующем примере первая категория была переименована с **низким уровнем дохода**, так как это был верхний атрибут кластера.</span><span class="sxs-lookup"><span data-stu-id="732fc-124">For example, in the following example, the first category has been renamed **Low Income**, because that was the top attribute of the cluster.</span></span>

 <span data-ttu-id="732fc-125">![отчет, созданный с помощью средства «Поиск категорий»](media/dm13-tat-detectcat-report1.gif "отчет, созданный с помощью средства «Поиск категорий»")</span><span class="sxs-lookup"><span data-stu-id="732fc-125">![report created by Detect Categories tool](media/dm13-tat-detectcat-report1.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="732fc-126">После ввода новой метки изменение распространяется во все остальные диаграммы, а также в список категорий, добавленный на листе исходных данных.</span><span class="sxs-lookup"><span data-stu-id="732fc-126">As soon as you type the new label, the change is propagated to all the other charts as well as to the category list added in the source data worksheet.</span></span>

### <a name="category-characteristics"></a><span data-ttu-id="732fc-127">Характеристики категории</span><span class="sxs-lookup"><span data-stu-id="732fc-127">Category Characteristics</span></span>
 <span data-ttu-id="732fc-128">Вторая таблица, **характеристики категории**, отображает сведения о описывающего каждой категории.</span><span class="sxs-lookup"><span data-stu-id="732fc-128">The second table, **Category Characteristics**, shows details about the makeup of each category.</span></span> <span data-ttu-id="732fc-129">Нажмите кнопку **Фильтр** в верхней части столбца **Категория** , чтобы увидеть одну или несколько категорий.</span><span class="sxs-lookup"><span data-stu-id="732fc-129">Click the **Filter** button at the top of the **Category** column to see focus on one or just a few categories.</span></span>

 <span data-ttu-id="732fc-130">![отчет, созданный с помощью средства «Поиск категорий»](media/dm13-tat-detectcat-report2.gif "отчет, созданный с помощью средства «Поиск категорий»")</span><span class="sxs-lookup"><span data-stu-id="732fc-130">![report created by Detect Categories tool](media/dm13-tat-detectcat-report2.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="732fc-131">Заливка в столбце **Относительная важность**указывает, насколько важно, чтобы сочетание атрибута и значения было в качестве отличительного коэффициента.</span><span class="sxs-lookup"><span data-stu-id="732fc-131">The shading in the column, **Relative Importance**, indicates how important that combination of attribute and value is as a distinguishing factor.</span></span> <span data-ttu-id="732fc-132">Чем длиннее полоса, тем выше вероятность, что этот атрибут является типичным для этой категории.</span><span class="sxs-lookup"><span data-stu-id="732fc-132">The longer the bar, the more likely it is that this attribute is strongly representative of this category.</span></span>

### <a name="categories-profile-chart"></a><span data-ttu-id="732fc-133">Диаграмма профиля категорий</span><span class="sxs-lookup"><span data-stu-id="732fc-133">Categories Profile Chart</span></span>
 <span data-ttu-id="732fc-134">Окончательная диаграмма на листе **отчеты по категориям** , **Профили категорий**, представляет собой интерактивную **сводную диаграмму** , которую можно использовать для изменения порядка полей, фильтрации значений и настройки внешнего вида диаграммы.</span><span class="sxs-lookup"><span data-stu-id="732fc-134">The final chart in the **Categories Report** worksheet, **Category Profiles**, is an interactive **Pivot Chart** that you can use to rearrange and hide fields, filter on values, and customize the chart's appearance.</span></span>

 <span data-ttu-id="732fc-135">Теперь в Excel 2013 доступны **стили диаграмм** и элементы **диаграммы** , находящееся в области конструктора, что позволяет легко улучшить структуру диаграммы.</span><span class="sxs-lookup"><span data-stu-id="732fc-135">Excel 2013 now provides **Chart Styles** and **Chart Elements** controls right in the design surface that make it easy to improve the chart design.</span></span>

 <span data-ttu-id="732fc-136">![отчет, созданный с помощью средства «Поиск категорий»](media/dm13-tat-detectcat-report3.gif "отчет, созданный с помощью средства «Поиск категорий»")</span><span class="sxs-lookup"><span data-stu-id="732fc-136">![report created by Detect Categories tool](media/dm13-tat-detectcat-report3.gif "report created by Detect Categories tool")</span></span>

## <a name="requirements"></a><span data-ttu-id="732fc-137">Требования</span><span class="sxs-lookup"><span data-stu-id="732fc-137">Requirements</span></span>
 <span data-ttu-id="732fc-138">Средство « **Поиск категорий** » не имеет требований к объему или типу данных.</span><span class="sxs-lookup"><span data-stu-id="732fc-138">The **Detect Categories** tool has no requirements for the amount or type of data.</span></span>

> [!NOTE]
>  <span data-ttu-id="732fc-139">При использовании средства « **Поиск категорий** » в исходной таблице данных создается новый столбец Category.</span><span class="sxs-lookup"><span data-stu-id="732fc-139">When you use the **Detect Categories** tool, it creates a new column, Category, in the original data table.</span></span> <span data-ttu-id="732fc-140">При сохранении этого столбца в таблице и выполнении последующих операций интеллектуального анализа данных наличие этого столбца может повлиять на результаты.</span><span class="sxs-lookup"><span data-stu-id="732fc-140">If you leave this column in the data table and then perform subsequent data mining operations, the presence of this column could influence your results.</span></span> <span data-ttu-id="732fc-141">Чтобы гарантировать, что это не повлияет на другие операции, перед использованием средств интеллектуального анализа данных необходимо создать копию таблицы данных без столбца Category.</span><span class="sxs-lookup"><span data-stu-id="732fc-141">To ensure that this does not affect other operations, you should make a copy of the data table without the Category column before using other data mining tools.</span></span>

## <a name="related-tools"></a><span data-ttu-id="732fc-142">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="732fc-142">Related Tools</span></span>
 <span data-ttu-id="732fc-143">Когда средство **обнаружения категорий** анализирует данные, оно создает структуру интеллектуального анализа данных и модель интеллектуального анализа данных с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма кластеризации.</span><span class="sxs-lookup"><span data-stu-id="732fc-143">When the **Detect Categories** tool analyzes your data, it creates a data mining structure and data mining model by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span>

 <span data-ttu-id="732fc-144">После создания модели интеллектуального анализа данных с помощью средства **Анализ ключевых факторов влияния** можно использовать клиент интеллектуального анализа данных для Excel для просмотра модели и более подробное изучение связей.</span><span class="sxs-lookup"><span data-stu-id="732fc-144">After you have created a data mining model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client for Excel to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="732fc-145">Клиент интеллектуального анализа данных для Excel представляет собой отдельную надстройку, обеспечивающую более широкие возможности интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="732fc-145">The Data Mining Client for Excel is a separate add-in that provides more advanced data mining functionality.</span></span> <span data-ttu-id="732fc-146">Дополнительные сведения см. [в разделе Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="732fc-146">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>

 <span data-ttu-id="732fc-147">Дополнительные сведения об использовании возможностей моделирования данных в клиенте интеллектуального анализа данных для Excel см. в разделе [Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="732fc-147">For more information about using the data modeling capabilities in the Data Mining Client for Excel, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="732fc-148">Дополнительные сведения о алгоритме, используемом средством **обнаружения категорий** , см. в разделе «Алгоритм кластеризации (Майкрософт)» [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] электронной документации по.</span><span class="sxs-lookup"><span data-stu-id="732fc-148">For more information about the algorithm used by the **Detect Categories** tool, see the topic "Microsoft Clustering Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="732fc-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="732fc-149">See Also</span></span>
 [<span data-ttu-id="732fc-150">Средства анализа таблиц для Excel</span><span class="sxs-lookup"><span data-stu-id="732fc-150">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


