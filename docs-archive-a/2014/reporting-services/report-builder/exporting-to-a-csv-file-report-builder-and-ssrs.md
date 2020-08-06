---
title: Экспорт в CSV-файл (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 68ec746e-8c82-47f5-8c3d-dbe403a441e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 635d5904acf6e616378f5423bfbaf4cf5390fa9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654875"
---
# <a name="exporting-to-a-csv-file-report-builder-and-ssrs"></a><span data-ttu-id="7b2d1-102">Экспорт в CSV-файл (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7b2d1-102">Exporting to a CSV File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7b2d1-103">Модуль подготовки отчетов в формате с разделителями-запятыми (CSV) готовит отчеты для просмотра в виде плоских представлений данных стандартизованного текстового вида. Этот формат легко читается и может использоваться для обмена со многими приложениями.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-103">The Comma-Separated Value (CSV) rendering extension renders reports as a flattened representation of data from a report in a standardized, plain-text format that is easily readable and exchangeable with many applications.</span></span>  
  
 <span data-ttu-id="7b2d1-104">Модуль подготовки отчетов в формате CSV использует строковый символ-разделитель для отделения полей и строк. Строковый разделитель можно настроить, чтобы использовать символ, отличный от запятой.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-104">The CSV rendering extension uses a string character delimiter to separate fields and rows, with the string character delimiter configurable to be a character other than a comma.</span></span> <span data-ttu-id="7b2d1-105">Полученный файл может быть открыт в электронных таблицах (например в [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] ) или импортирован в другие программы.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-105">The resulting file can be opened in a spreadsheet program like [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] or used as an import format for other programs.</span></span> <span data-ttu-id="7b2d1-106">Отчет экспортируется в CSV-файл и возвращает тип MIME `text/csv`.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-106">The exported report becomes a .csv file, and returns a MIME type of `text/csv`.</span></span>  
  
 <span data-ttu-id="7b2d1-107">Если необходимо работать с данными, связанными с диаграммами, гистограммами, инфокривыми, датчиками и индикаторами в [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)], экспортируйте отчет в файл в формате CSV и откройте файл в [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-107">If you want to work with data related to charts, data bars, sparklines, gauges, and indicators in [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)], export the report to a CSV file, and then open the file in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="csv-rendering"></a><a name="CSVRendering"></a> <span data-ttu-id="7b2d1-108">Подготовка CSV-отчетов</span><span class="sxs-lookup"><span data-stu-id="7b2d1-108">CSV Rendering</span></span>  
 <span data-ttu-id="7b2d1-109">Если для отображения используются параметры по умолчанию, отчет в формате CSV имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="7b2d1-109">When rendered using the default settings, a CSV report has the following characteristics:</span></span>  
  
-   <span data-ttu-id="7b2d1-110">По умолчанию строка разделителя полей — запятая (,).</span><span class="sxs-lookup"><span data-stu-id="7b2d1-110">The default field delimiter string is a comma (,).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b2d1-111">В качестве разделителя полей можно задать любой символ, в том числе символ табуляции. Для этого нужно изменить настройки сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-111">You can change the field delimiter to any character that you want, including TAB, by changing the device information settings.</span></span> <span data-ttu-id="7b2d1-112">Дополнительные сведения см. в разделе [CSV Device Information Settings](../csv-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d1-112">For more information, see [CSV Device Information Settings](../csv-device-information-settings.md).</span></span>  
  
-   <span data-ttu-id="7b2d1-113">Строка разделителя записей — это возврат каретки и перевод строки ( \<cr> \<lf> ).</span><span class="sxs-lookup"><span data-stu-id="7b2d1-113">The record delimiter string is the carriage return and line feed (\<cr>\<lf>).</span></span>  
  
-   <span data-ttu-id="7b2d1-114">Ограничитель текста — кавычка (").</span><span class="sxs-lookup"><span data-stu-id="7b2d1-114">The text qualifier string is a quotation mark (").</span></span>  
  
     <span data-ttu-id="7b2d1-115">Модуль подготовки отчетов в формате CSV не заключает все текстовые строки в квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-115">The CSV renderer does not add qualifiers around all text strings.</span></span> <span data-ttu-id="7b2d1-116">Ограничители текста добавляются только в случаях, когда строка содержит символ разделителя или символ конца строки.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-116">Text qualifiers are added only when the value contains the delimiter character or when the value has a line break.</span></span>  
  
-   <span data-ttu-id="7b2d1-117">Если текст содержит внедренную строку разделителя или строку ограничителя текста, вокруг текста помещается ограничитель текста, а внедренные ограничители удваиваются.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-117">If the text contains an embedded delimiter string or qualifier string, the text qualifier is placed around the text, and the embedded qualifier strings are doubled.</span></span>  
  
-   <span data-ttu-id="7b2d1-118">Форматирование и макет игнорируются.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-118">Formatting and layout are ignored.</span></span>  
  
 <span data-ttu-id="7b2d1-119">При обработке не учитываются следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-119">The following items are ignored during rendering:</span></span>  
  
-   <span data-ttu-id="7b2d1-120">Верхний колонтитул страницы</span><span class="sxs-lookup"><span data-stu-id="7b2d1-120">Page header</span></span>  
  
-   <span data-ttu-id="7b2d1-121">Нижний колонтитул страницы</span><span class="sxs-lookup"><span data-stu-id="7b2d1-121">Page footer</span></span>  
  
-   <span data-ttu-id="7b2d1-122">Пользовательские элементы отчета</span><span class="sxs-lookup"><span data-stu-id="7b2d1-122">Custom report items</span></span>  
  
-   <span data-ttu-id="7b2d1-123">Строка</span><span class="sxs-lookup"><span data-stu-id="7b2d1-123">Line</span></span>  
  
-   <span data-ttu-id="7b2d1-124">Образ —</span><span class="sxs-lookup"><span data-stu-id="7b2d1-124">Image</span></span>  
  
-   <span data-ttu-id="7b2d1-125">Прямоугольник</span><span class="sxs-lookup"><span data-stu-id="7b2d1-125">Rectangle</span></span>  
  
-   <span data-ttu-id="7b2d1-126">Автоматические подытоги</span><span class="sxs-lookup"><span data-stu-id="7b2d1-126">Automatic subtotals</span></span>  
  
 <span data-ttu-id="7b2d1-127">Остальные элементы отчета сортируются сверху вниз, затем слева направо.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-127">The remaining report items are sorted, from top to bottom, then left to right.</span></span> <span data-ttu-id="7b2d1-128">Каждый элемент присваивается столбцу.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-128">Each item is then rendered to a column.</span></span> <span data-ttu-id="7b2d1-129">Если отчет имеет вложенные элементы данных, такие как списки или таблицы, родительские элементы повторяются в каждой записи.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-129">If the report has nested data items like lists or tables, the parent items are repeated in each record.</span></span>  
  
 <span data-ttu-id="7b2d1-130">В следующей таблице описывается, как выглядят подготовленные к просмотру элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-130">The following table indicates the appearance of report items when rendered:</span></span>  
  
|<span data-ttu-id="7b2d1-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b2d1-131">Item</span></span>|<span data-ttu-id="7b2d1-132">Поведение при подготовке к просмотру</span><span class="sxs-lookup"><span data-stu-id="7b2d1-132">Rendering behavior</span></span>|  
|----------|------------------------|  
|<span data-ttu-id="7b2d1-133">Текстовое поле</span><span class="sxs-lookup"><span data-stu-id="7b2d1-133">Text box</span></span>|<span data-ttu-id="7b2d1-134">Подготовка содержимого текстового поля.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-134">Renders the contents of the text box.</span></span> <span data-ttu-id="7b2d1-135">По умолчанию элементы форматируются на основе их форматирующих свойств.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-135">In default mode, items are formatted based on the item's formatting properties.</span></span> <span data-ttu-id="7b2d1-136">В режиме совместимости форматирование можно изменить, изменив настройки сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-136">In compliant mode, formatting can be changed by device information settings.</span></span> <span data-ttu-id="7b2d1-137">Дополнительные сведения о режимах подготовки отчетов в формате CSV см. ниже.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-137">For more information about CSV rendering modes, see below.</span></span>|  
|<span data-ttu-id="7b2d1-138">Таблица</span><span class="sxs-lookup"><span data-stu-id="7b2d1-138">Table</span></span>|<span data-ttu-id="7b2d1-139">Подготовка путем разворачивания таблицы и создания строки и столбца для каждой строки и столбца на самом низком уровне детализации.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-139">Renders by expanding the table and creating a row and column for each row and column at the lowest level of detail.</span></span> <span data-ttu-id="7b2d1-140">Строки и столбцы подытогов не имеют заголовков строки или столбца.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-140">Subtotal rows and columns do not have column or row headings.</span></span> <span data-ttu-id="7b2d1-141">Детализированные отчеты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-141">Drillthrough reports are not supported.</span></span>|  
|<span data-ttu-id="7b2d1-142">Матрица</span><span class="sxs-lookup"><span data-stu-id="7b2d1-142">Matrix</span></span>|<span data-ttu-id="7b2d1-143">Подготовка с развертыванием таблицы и созданием строки и столбца для каждой строки и столбца на самом низком уровне детализации.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-143">Renders by expanding the matrix and creating a row and column for each row and column at the lowest level of detail.</span></span> <span data-ttu-id="7b2d1-144">Строки и столбцы подытогов не имеют заголовков строки или столбца.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-144">Subtotal rows and columns do not have column or row headings.</span></span>|  
|<span data-ttu-id="7b2d1-145">Список</span><span class="sxs-lookup"><span data-stu-id="7b2d1-145">List</span></span>|<span data-ttu-id="7b2d1-146">Подготовка записи для каждой отдельной строки или экземпляра в списке.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-146">Renders a record for each detail row or instance in the list.</span></span>|  
|<span data-ttu-id="7b2d1-147">Подотчет</span><span class="sxs-lookup"><span data-stu-id="7b2d1-147">Subreport</span></span>|<span data-ttu-id="7b2d1-148">Родительский элемент повторяется для каждого экземпляра содержимого.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-148">The parent item is repeated for each instance of the contents.</span></span>|  
|<span data-ttu-id="7b2d1-149">Диаграмма</span><span class="sxs-lookup"><span data-stu-id="7b2d1-149">Chart</span></span>|<span data-ttu-id="7b2d1-150">Выполняется подготовка к просмотру путем создания строк для всех значений диаграммы и меток элементов.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-150">Renders by creating a row for each chart value and member labels.</span></span> <span data-ttu-id="7b2d1-151">Метки для рядов и категорий в иерархиях приводятся к плоскому формату и включаются в строку для значения диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-151">Labels from series and categories in hierarchies are flattened and included in the row for a chart value.</span></span>|  
|<span data-ttu-id="7b2d1-152">Гистограмма</span><span class="sxs-lookup"><span data-stu-id="7b2d1-152">Data bar</span></span>|<span data-ttu-id="7b2d1-153">Отображается как диаграмма.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-153">Renders like a chart.</span></span> <span data-ttu-id="7b2d1-154">Как правило, гистограмма не содержит иерархии или метки.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-154">Typically, a data bar does not include hierarchies or labels.</span></span>|  
|<span data-ttu-id="7b2d1-155">Спарклайн</span><span class="sxs-lookup"><span data-stu-id="7b2d1-155">Sparkline</span></span>|<span data-ttu-id="7b2d1-156">Отображается как диаграмма.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-156">Renders like a chart.</span></span> <span data-ttu-id="7b2d1-157">Как правило, спарклайн не содержит иерархий или меток.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-157">Typically, a sparkline does not  do not include hierarchies or labels.</span></span>|  
|<span data-ttu-id="7b2d1-158">Индикаторная диаграмма</span><span class="sxs-lookup"><span data-stu-id="7b2d1-158">Gauge</span></span>|<span data-ttu-id="7b2d1-159">Подготавливает единственную запись с минимальным и максимальным значениями линейной шкалы, начальным и конечным значениями диапазона и значением указателя.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-159">Renders as a single record with the minimum and maximum values of the linear scale, start and end values of the range, and the value of the pointer.</span></span>|  
|<span data-ttu-id="7b2d1-160">Индикатор</span><span class="sxs-lookup"><span data-stu-id="7b2d1-160">Indicator</span></span>|<span data-ttu-id="7b2d1-161">Отображается как единственная запись с названием активного состояния, состояний доступности и значений данных.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-161">Renders as a single record with the active state name, available states, and the data value.</span></span>|  
|<span data-ttu-id="7b2d1-162">Схема</span><span class="sxs-lookup"><span data-stu-id="7b2d1-162">Map</span></span>|<span data-ttu-id="7b2d1-163">Подготовка строки с метками и значениями каждого элемента слоя карты.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-163">Renders a row with the labels and values for each map member of a map layer.</span></span><br /><br /> <span data-ttu-id="7b2d1-164">Если карта содержит несколько слоев, значения в строках могут различаться в зависимости от того, используются ли в слоях карты идентичные или различные области данных карты.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-164">If the map has multiple layers the values in the rows varies depending on whether the map layers use the same or different map data regions.</span></span> <span data-ttu-id="7b2d1-165">Если одна область карты используется несколькими слоями карты, то строки содержат данные всех слоев.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-165">If multiple map layers use the same data region, the rows contain data from all layers.</span></span>|  
  
### <a name="hierarchical-and-grouped-data"></a><span data-ttu-id="7b2d1-166">Иерархические и группированные данные</span><span class="sxs-lookup"><span data-stu-id="7b2d1-166">Hierarchical and Grouped Data</span></span>  
 <span data-ttu-id="7b2d1-167">Иерархические и группированные данные должны быть переведены в плоский формат, чтобы их можно было представить в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-167">Hierarchical and grouped data must be flattened in order to be represented in the CSV format.</span></span>  
  
 <span data-ttu-id="7b2d1-168">Модуль подготовки отчетов делает отчет плоским, преобразуя его в древовидную структуру, отображающую вложенные группы области данных.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-168">The rendering extension flattens the report into a tree structure that represents the nested groups within the data region.</span></span> <span data-ttu-id="7b2d1-169">Формирование плоского отчета происходит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-169">To flatten the report:</span></span>  
  
-   <span data-ttu-id="7b2d1-170">Сначала делается плоской иерархия строк, затем — иерархия столбцов.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-170">A row hierarchy is flattened before a column hierarchy.</span></span>  
  
-   <span data-ttu-id="7b2d1-171">Столбцы упорядочены следующим образом: текстовые поля в тексте отчета — слева направо, сверху вниз, а затем области данных — слева направо, сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-171">Columns are ordered as follows: text boxes in body order left-to-right, top-to-bottom followed by data regions ordered left-to-right, top-to-bottom.</span></span>  
  
-   <span data-ttu-id="7b2d1-172">В пределах области данных столбцы упорядочены следующим образом: элементы углов, элементы иерархии строк, элементы иерархии столбцов, а затем ячейки.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-172">Within a data region, the columns are ordered as follows: corner members, row hierarchy members, column hierarchy members, and then cells.</span></span>  
  
-   <span data-ttu-id="7b2d1-173">Одноранговые области данных — это области данных или динамические группы, относящиеся к одной и той же области данных или имеющие одного динамического предка.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-173">Peer data regions are data regions or dynamic groups that share a common data region or dynamic ancestor.</span></span> <span data-ttu-id="7b2d1-174">Одноранговые данные можно определить по разветвлениям уплощенного дерева.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-174">Peer data is identified by branching of the flattened tree.</span></span>  
  
 <span data-ttu-id="7b2d1-175">Дополнительные сведения см. в разделе [Таблицы, матрицы и списки (построитель отчетов и службы SSRS)](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d1-175">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="renderer-modes"></a><a name="RenderingModes"></a> <span data-ttu-id="7b2d1-176">Режимы модуля подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="7b2d1-176">Renderer Modes</span></span>  
 <span data-ttu-id="7b2d1-177">Модуль подготовки отчетов в формате CSV может работать в двух режимах: один оптимизирован для Excel, второй — для приложений сторонних разработчиков, требующих строгого соответствия спецификации CSV в стандарте RFC 4180.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-177">The CSV rendering extension can operate in two modes: one is optimized for Excel and the other is optimized for third-party applications that require strict CSV compliance to the CSV specification in RFC 4180.</span></span> <span data-ttu-id="7b2d1-178">В зависимости от режима одноранговые области данных обрабатываются по-разному.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-178">Depending on which mode you use, peer data regions are handled differently.</span></span>  
  
### <a name="default-mode"></a><span data-ttu-id="7b2d1-179">Режим по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7b2d1-179">Default Mode</span></span>  
 <span data-ttu-id="7b2d1-180">Режим по умолчанию оптимизирован для использования отчетов в электронных таблицах Excel.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-180">The default mode is optimized for Excel.</span></span> <span data-ttu-id="7b2d1-181">Отчет, подготовленный в режиме по умолчанию, имеет формат CSV-файла с несколькими разделами данных в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-181">When rendered in default mode, the report is rendered as a CSV file with multiple sections of CSV-rendered data.</span></span> <span data-ttu-id="7b2d1-182">Каждая одноранговая область данных отделена пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-182">Each peer data region is delimited by an empty line.</span></span> <span data-ttu-id="7b2d1-183">Одноранговые области данных в тексте отчета выводятся как отдельные массивы данных внутри файла CSV.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-183">Peer data regions within the report body are rendered as separate blocks of data within the CSV file.</span></span> <span data-ttu-id="7b2d1-184">Результатом является CSV-файл, в котором:</span><span class="sxs-lookup"><span data-stu-id="7b2d1-184">The result is a CSV file in which:</span></span>  
  
-   <span data-ttu-id="7b2d1-185">индивидуальные текстовые поля в тексте отчета выводятся один раз как первый блок данных в CSV-файле;</span><span class="sxs-lookup"><span data-stu-id="7b2d1-185">Individual text boxes within the report body are rendered once as the first block of data within the CSV file.</span></span>  
  
-   <span data-ttu-id="7b2d1-186">каждая одноранговая область данных верхнего уровня в тексте отчета выводится в своем собственном блоке данных;</span><span class="sxs-lookup"><span data-stu-id="7b2d1-186">Each top-level peer data region in the report body is rendered in its own data block.</span></span>  
  
-   <span data-ttu-id="7b2d1-187">вложенные области данных выводятся диагонально в одном и том же блоке данных.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-187">Nested data regions are rendered diagonally into the same data block.</span></span>  
  
#### <a name="formatting"></a><span data-ttu-id="7b2d1-188">Форматирование</span><span class="sxs-lookup"><span data-stu-id="7b2d1-188">Formatting</span></span>  
 <span data-ttu-id="7b2d1-189">Числовые значения выводятся в форматированном виде.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-189">Numeric values are rendered in their formatted state.</span></span> <span data-ttu-id="7b2d1-190">Программа работы с электронными таблицами Excel распознает форматированные численные значения — денежные суммы, проценты, даты — и форматирует ячейки соответствующим образом при импорте CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-190">Excel can recognize formatted numeric values, such as currency, percentage and date, and format the cells appropriately when importing the CSV file.</span></span>  
  
### <a name="compliant-mode"></a><span data-ttu-id="7b2d1-191">Режим совместимости</span><span class="sxs-lookup"><span data-stu-id="7b2d1-191">Compliant Mode</span></span>  
 <span data-ttu-id="7b2d1-192">Совместимый формат оптимизирован для приложений сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-192">Compliant mode is optimized for third-party applications.</span></span>  
  
#### <a name="data-regions"></a><span data-ttu-id="7b2d1-193">Области данных</span><span class="sxs-lookup"><span data-stu-id="7b2d1-193">Data Regions</span></span>  
 <span data-ttu-id="7b2d1-194">Заголовки столбцов содержатся только в первой строке файла, и каждая строка содержит одинаковое количество столбцов.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-194">Only the first row of the file contains the column headers and each row has the same number of columns.</span></span>  
  
#### <a name="formatting"></a><span data-ttu-id="7b2d1-195">Форматирование</span><span class="sxs-lookup"><span data-stu-id="7b2d1-195">Formatting</span></span>  
 <span data-ttu-id="7b2d1-196">Значения не форматируются.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-196">Values are unformatted.</span></span>  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="7b2d1-197">Интерактивности</span><span class="sxs-lookup"><span data-stu-id="7b2d1-197">Interactivity</span></span>  
 <span data-ttu-id="7b2d1-198">Ни один формат CSV данного модуля подготовки отчетов не поддерживает интерактивности.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-198">Interactivity is not supported by either CSV formats generated by this renderer.</span></span> <span data-ttu-id="7b2d1-199">Не обрабатываются следующие интерактивные элементы.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-199">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="7b2d1-200">Гиперссылки</span><span class="sxs-lookup"><span data-stu-id="7b2d1-200">Hyperlinks</span></span>  
  
-   <span data-ttu-id="7b2d1-201">Показать или скрыть</span><span class="sxs-lookup"><span data-stu-id="7b2d1-201">Show or Hide</span></span>  
  
-   <span data-ttu-id="7b2d1-202">Схема документа</span><span class="sxs-lookup"><span data-stu-id="7b2d1-202">Document Map</span></span>  
  
-   <span data-ttu-id="7b2d1-203">Ссылки с детализацией или дополнительной информацией</span><span class="sxs-lookup"><span data-stu-id="7b2d1-203">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="7b2d1-204">Сортировка конечным пользователем</span><span class="sxs-lookup"><span data-stu-id="7b2d1-204">End user sort</span></span>  
  
-   <span data-ttu-id="7b2d1-205">Фиксированные заголовки</span><span class="sxs-lookup"><span data-stu-id="7b2d1-205">Fixes headers</span></span>  
  
-   <span data-ttu-id="7b2d1-206">Закладки</span><span class="sxs-lookup"><span data-stu-id="7b2d1-206">Bookmarks</span></span>  
  

  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="7b2d1-207">Настройки сведений об устройстве</span><span class="sxs-lookup"><span data-stu-id="7b2d1-207">Device Information Settings</span></span>  
 <span data-ttu-id="7b2d1-208">Некоторые настройки по умолчанию для этого модуля подготовки отчетов можно изменить с помощью изменения настроек сведений об устройстве. Можно, например, указать, в каком режиме готовить отчет, какие символы использовать в качестве разделителей, а какие — в качестве ограничителей текста.</span><span class="sxs-lookup"><span data-stu-id="7b2d1-208">You can change some default settings for this renderer, including which mode to render in, which characters to use as delimiters and which characters to use as the text qualifier default string, by changing the device information settings.</span></span> <span data-ttu-id="7b2d1-209">Дополнительные сведения см. в разделе [CSV Device Information Settings](../csv-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d1-209">For more information, see [CSV Device Information Settings](../csv-device-information-settings.md).</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="7b2d1-210">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b2d1-210">See Also</span></span>  
 <span data-ttu-id="7b2d1-211">[Разбиение на страницы в Reporting Services &#40;построитель отчетов и SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7b2d1-211">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7b2d1-212">[Поведения подготовки к просмотру &#40;построитель отчетов и SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7b2d1-212">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7b2d1-213">[Интерактивные функции для различных модулей подготовки отчетов к просмотру &#40;построитель отчетов и SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="7b2d1-213">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="7b2d1-214">[Подготовка элементов отчета к просмотру &#40;построитель отчетов и SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7b2d1-214">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7b2d1-215">Таблицы, матрицы и списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7b2d1-215">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
