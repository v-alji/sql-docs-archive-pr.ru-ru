---
title: Назначение Excel | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldest.f1
helpviewer_keywords:
- destinations [Integration Services], Excel
- Excel [Integration Services]
ms.assetid: 37c07446-1264-4814-b4f5-9c66d333bb24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e959f14e52fc045cb0cbc2ba0255d20bd0356d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751343"
---
# <a name="excel-destination"></a><span data-ttu-id="fdc25-102">Назначение Excel</span><span class="sxs-lookup"><span data-stu-id="fdc25-102">Excel Destination</span></span>
  <span data-ttu-id="fdc25-103">Назначение «Excel» загружает данные в листы или диапазоны в книгах [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="fdc25-103">The Excel destination loads data into worksheets or ranges in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbooks.</span></span>  
  
## <a name="access-modes"></a><span data-ttu-id="fdc25-104">Режимы доступа</span><span class="sxs-lookup"><span data-stu-id="fdc25-104">Access Modes</span></span>  
 <span data-ttu-id="fdc25-105">Назначение «Excel» предоставляет три различных режима доступа к данным для загрузки:</span><span class="sxs-lookup"><span data-stu-id="fdc25-105">The Excel destination provides three different data access modes for loading data:</span></span>  
  
-   <span data-ttu-id="fdc25-106">Таблица или представление.</span><span class="sxs-lookup"><span data-stu-id="fdc25-106">A table or view.</span></span>  
  
-   <span data-ttu-id="fdc25-107">Таблица или представление, указанные в переменной.</span><span class="sxs-lookup"><span data-stu-id="fdc25-107">A table or view specified in a variable.</span></span>  
  
-   <span data-ttu-id="fdc25-108">Результат выполнения инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="fdc25-108">The results of an SQL statement.</span></span> <span data-ttu-id="fdc25-109">Может использоваться параметризированный запрос.</span><span class="sxs-lookup"><span data-stu-id="fdc25-109">The query can be a parameterized query.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fdc25-110">Лист или диапазон в Excel эквивалентны таблице или представлению.</span><span class="sxs-lookup"><span data-stu-id="fdc25-110">In Excel, a worksheet or range is the equivalent of a table or view.</span></span> <span data-ttu-id="fdc25-111">Списки доступных таблиц в источнике Excel и редакторах назначения отображают только существующие листы (обозначенные знаком $, добавленным к имени листа, как в имени Лист1$) и именованные диапазоны (обозначенные отсутствием знака $, как в имени Мой_диапазон).</span><span class="sxs-lookup"><span data-stu-id="fdc25-111">The lists of available tables in the Excel Source and Destination editors display only existing worksheets (identified by the $ sign appended to the worksheet name, such as Sheet1$) and named ranges (identified by the absence of the $ sign, such as MyRange).</span></span>  
  
## <a name="usage-considerations"></a><span data-ttu-id="fdc25-112">Особенности использования</span><span class="sxs-lookup"><span data-stu-id="fdc25-112">Usage Considerations</span></span>  
 <span data-ttu-id="fdc25-113">Диспетчер соединений Excel использует поставщик [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB для Jet 4.0, который поддерживает драйвер Excel ISAM (индексированный последовательный метод доступа) для подключения, а также чтения и записи данных в источники данных Excel.</span><span class="sxs-lookup"><span data-stu-id="fdc25-113">The Excel Connection Manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span>  
  
 <span data-ttu-id="fdc25-114">Во многих имеющихся статьях базы знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] описывается поведение этого поставщика и драйвера, и хотя эти статьи не относятся к [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] и их предшественникам, службам преобразования данных, вам может быть интересно изучить поведение, которое может привести к неожиданным результатам.</span><span class="sxs-lookup"><span data-stu-id="fdc25-114">Many existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles document the behavior of this provider and driver, and although these articles are not specific to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] or its predecessor Data Transformation Services, you may want to know about certain behaviors that can lead to unexpected results.</span></span> <span data-ttu-id="fdc25-115">Общие сведения об использовании и поведении драйвера Excel см. в разделе [Как использовать ADO с данными Excel из Visual Basic или VBA](https://support.microsoft.com/kb/257819).</span><span class="sxs-lookup"><span data-stu-id="fdc25-115">For general information on the use and behavior of the Excel driver, see [HOWTO: Use ADO with Excel Data from Visual Basic or VBA](https://support.microsoft.com/kb/257819).</span></span>  
  
 <span data-ttu-id="fdc25-116">При сохранении данных в назначение «Excel» следующее поведение поставщика Jet в сочетании с драйвером Excel может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="fdc25-116">The following behaviors of the Jet provider that is included with the Excel driver can lead to unexpected results when saving data to an Excel destination.</span></span>  
  
-   <span data-ttu-id="fdc25-117">**Сохранение текстовых данных**.</span><span class="sxs-lookup"><span data-stu-id="fdc25-117">**Saving text data**.</span></span> <span data-ttu-id="fdc25-118">При сохранении значений текстовых данных в назначение «Excel» драйвер Excel предваряет текст в каждой ячейке символом одинарной кавычки ('); это гарантирует, что сохраненные значения будут интерпретироваться как текстовые.</span><span class="sxs-lookup"><span data-stu-id="fdc25-118">When the Excel driver saves text data values to an Excel destination, the driver precedes the text in each cell with the single quote character (') to ensure that the saved values will be interpreted as text values.</span></span> <span data-ttu-id="fdc25-119">При разработке других приложений, которые считывают или обрабатывают сохраненные данные, следует выполнять специальную обработку для символа одинарной кавычки ('), за которым следуют текстовые значения.</span><span class="sxs-lookup"><span data-stu-id="fdc25-119">If you have or develop other applications that read or process the saved data, you may need to include special handling for the single quote character that precedes each text value.</span></span>  
  
     <span data-ttu-id="fdc25-120">Сведения о том, как избежать включения символа одинарной кавычки, см. в записи блога [Single quote is appended to all strings when data is transformed to excel when using Excel destination data flow component in SSIS package](https://go.microsoft.com/fwlink/?LinkId=400876) (При использовании Excel в качестве целевого компонента потока данных в пакете SSIS преобразование данных в Excel добавляет ко всем строкам одинарную кавычку) на веб-сайте msdn.com.</span><span class="sxs-lookup"><span data-stu-id="fdc25-120">For information on how to avoid including the single quote, see this blog post, [Single quote is appended to all strings when data is transformed to excel when using Excel destination data flow component in SSIS package](https://go.microsoft.com/fwlink/?LinkId=400876), on msdn.com.</span></span>  
  
-   <span data-ttu-id="fdc25-121">**Сохранение данных типа memo (ntext)**.</span><span class="sxs-lookup"><span data-stu-id="fdc25-121">**Saving memo (ntext) da**ta.</span></span> <span data-ttu-id="fdc25-122">Чтобы успешно сохранять в столбцы Excel строки, имеющие длину более 255 символов, драйвер должен распознать тип данных целевого столбца как **memo** , а не как **string**.</span><span class="sxs-lookup"><span data-stu-id="fdc25-122">Before you can successfully save strings longer than 255 characters to an Excel column, the driver must recognize the data type of the destination column as **memo** and not **string**.</span></span> <span data-ttu-id="fdc25-123">Если в целевой таблице уже содержатся строки данных, то в столбце типа memo в первых нескольких строках, которые проверит драйвер, должен содержаться, по крайней мере, один экземпляр значения, имеющего длину более 255 символов.</span><span class="sxs-lookup"><span data-stu-id="fdc25-123">If the destination table already contains rows of data, then the first few rows that are sampled by the driver must contain at least one instance of a value longer than 255 characters in the memo column.</span></span> <span data-ttu-id="fdc25-124">Если целевая таблица создается во время разработки пакета или во время выполнения, то инструкция CREATE TABLE должна использовать LONGTEXT (или один из его синонимов) в качестве типа данных столбца МЕМО.</span><span class="sxs-lookup"><span data-stu-id="fdc25-124">If the destination table is created during package design or at run time, then the CREATE TABLE statement must use LONGTEXT (or one of its synonyms) as the data type of the memo column.</span></span>  
  
-   <span data-ttu-id="fdc25-125">**Типы данных**.</span><span class="sxs-lookup"><span data-stu-id="fdc25-125">**Data types**.</span></span> <span data-ttu-id="fdc25-126">Драйвер Excel распознает только ограниченный набор типов данных.</span><span class="sxs-lookup"><span data-stu-id="fdc25-126">The Excel driver recognizes only a limited set of data types.</span></span> <span data-ttu-id="fdc25-127">Например, все числовые столбцы воспринимаются как тип double (DT_R8), а все строковые столбцы (кроме столбцов типа memo) воспринимаются как строки в Юникоде длиной 255 символов (DT_WSTR).</span><span class="sxs-lookup"><span data-stu-id="fdc25-127">For example, all numeric columns are interpreted as doubles (DT_R8), and all string columns (other than memo columns) are interpreted as 255-character Unicode strings (DT_WSTR).</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="fdc25-128">сопоставляют типы данных Excel следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fdc25-128">maps the Excel data types as follows:</span></span>  
  
    -   <span data-ttu-id="fdc25-129">Числовой — с плавающей запятой двойной точности (DT_R8)</span><span class="sxs-lookup"><span data-stu-id="fdc25-129">Numeric    double-precision float (DT_R8)</span></span>  
  
    -   <span data-ttu-id="fdc25-130">Денежный — денежный (DT_CY)</span><span class="sxs-lookup"><span data-stu-id="fdc25-130">Currency     currency (DT_CY)</span></span>  
  
    -   <span data-ttu-id="fdc25-131">Логический — логический (DT_BOOL)</span><span class="sxs-lookup"><span data-stu-id="fdc25-131">Boolean     Boolean (DT_BOOL)</span></span>  
  
    -   <span data-ttu-id="fdc25-132">Дата и время `datetime` (DT_DATE)</span><span class="sxs-lookup"><span data-stu-id="fdc25-132">Date/time     `datetime` (DT_DATE)</span></span>  
  
    -   <span data-ttu-id="fdc25-133">Строка — строка в Юникоде длиной 255 символов (DT_WSTR)</span><span class="sxs-lookup"><span data-stu-id="fdc25-133">String     Unicode string, length 255 (DT_WSTR)</span></span>  
  
    -   <span data-ttu-id="fdc25-134">Memo — текстовый поток в Юникоде (DT_NTEXT)</span><span class="sxs-lookup"><span data-stu-id="fdc25-134">Memo     Unicode text stream (DT_NTEXT)</span></span>  
  
-   <span data-ttu-id="fdc25-135">**Преобразование типов данных и длины**.</span><span class="sxs-lookup"><span data-stu-id="fdc25-135">**Data type and length conversions**.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="fdc25-136">неявное преобразование типов данных не выполняется.</span><span class="sxs-lookup"><span data-stu-id="fdc25-136">does not implicitly convert data types.</span></span> <span data-ttu-id="fdc25-137">Поэтому может потребоваться использование преобразования «Производный столбец» или «Преобразование данных», чтобы выполнить явное преобразование данных до их загрузки в назначение, отличное от Excel, либо выполнить преобразование данных, отличных от данных Excel, до их загрузки в назначение «Excel».</span><span class="sxs-lookup"><span data-stu-id="fdc25-137">As a result, you may need to use the Derived Column or Data Conversion transformations to convert Excel data explicitly before loading it into a non-Excel destination, or to convert non-Excel data before loading it into an Excel destination.</span></span> <span data-ttu-id="fdc25-138">В этом случае может оказаться полезным создать исходный пакет с помощью мастера импорта и экспорта, который сам настроит необходимые преобразования.</span><span class="sxs-lookup"><span data-stu-id="fdc25-138">In this case, it may be useful to create the initial package by using the Import and Export Wizard, which configures the necessary conversions for you.</span></span> <span data-ttu-id="fdc25-139">Ниже приведены некоторые примеры преобразований, которые могут потребоваться.</span><span class="sxs-lookup"><span data-stu-id="fdc25-139">Some examples of the conversions that may be required include the following:</span></span>  
  
    -   <span data-ttu-id="fdc25-140">Преобразование между строковыми столбцами Excel в Юникоде и строковыми столбцами в формате с конкретными кодовыми страницами, отличными от Юникода.</span><span class="sxs-lookup"><span data-stu-id="fdc25-140">Conversion between Unicode Excel string columns and non-Unicode string columns with specific codepages.</span></span>  
  
    -   <span data-ttu-id="fdc25-141">Преобразование между строковыми столбцами Excel длиной в 255 символов и строковыми столбцами другой длины.</span><span class="sxs-lookup"><span data-stu-id="fdc25-141">Conversion between 255-character Excel string columns and string columns of different lengths.</span></span>  
  
    -   <span data-ttu-id="fdc25-142">Преобразование между числовыми столбцами Excel с плавающей запятой двойной точности и числовыми столбцами других типов.</span><span class="sxs-lookup"><span data-stu-id="fdc25-142">Conversion between double-precision Excel numeric columns and numeric columns of other types.</span></span>  
  
## <a name="configuration-of-the-excel-destination"></a><span data-ttu-id="fdc25-143">Настройка назначения Excel</span><span class="sxs-lookup"><span data-stu-id="fdc25-143">Configuration of the Excel Destination</span></span>  
 <span data-ttu-id="fdc25-144">Назначение «Excel» использует диспетчер соединений Excel для подключения к источнику данных, а диспетчер соединений определяет файл книги для использования.</span><span class="sxs-lookup"><span data-stu-id="fdc25-144">The Excel destination uses an Excel connection manager to connect to a data source, and the connection manager specifies the workbook file to use.</span></span> <span data-ttu-id="fdc25-145">Дополнительные сведения см. в статье [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fdc25-145">For more information, see [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span></span>  
  
 <span data-ttu-id="fdc25-146">Назначение «Excel» имеет один обычный вход и один вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="fdc25-146">The Excel destination has one regular input and one error output.</span></span>  
  
 <span data-ttu-id="fdc25-147">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="fdc25-147">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fdc25-148">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор назначения «Excel»** , см. в одном из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="fdc25-148">For more information about the properties that you can set in the **Excel Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fdc25-149">Редактор назначения "Excel" (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="fdc25-149">Excel Destination Editor &#40;Connection Manager Page&#41;</span></span>](../excel-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="fdc25-150">Редактор назначения "Excel" (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="fdc25-150">Excel Destination Editor &#40;Mappings Page&#41;</span></span>](../excel-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="fdc25-151">Редактор назначения "Excel" (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="fdc25-151">Excel Destination Editor &#40;Error Output Page&#41;</span></span>](../excel-destination-editor-error-output-page.md)  
  
 <span data-ttu-id="fdc25-152">Диалоговое окно **Расширенный редактор** содержит все свойства, которые могут устанавливаться программными средствами.</span><span class="sxs-lookup"><span data-stu-id="fdc25-152">The **Advanced Editor** dialog box reflects all the properties that can be set programmatically.</span></span> <span data-ttu-id="fdc25-153">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="fdc25-153">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fdc25-154">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="fdc25-154">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="fdc25-155">Пользовательские свойства Excel</span><span class="sxs-lookup"><span data-stu-id="fdc25-155">Excel Custom Properties</span></span>](excel-custom-properties.md)  
  
 <span data-ttu-id="fdc25-156">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fdc25-156">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fdc25-157">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="fdc25-157">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fdc25-158">Импорт данных из Excel или экспорт данных в Excel с помощью служб SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="fdc25-158">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)  
  
-   [<span data-ttu-id="fdc25-159">Просмотр файлов и таблиц Excel с помощью контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="fdc25-159">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="fdc25-160">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="fdc25-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="fdc25-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="fdc25-161">See Also</span></span>  
 <span data-ttu-id="fdc25-162">[Источник Excel](excel-source.md) </span><span class="sxs-lookup"><span data-stu-id="fdc25-162">[Excel Source](excel-source.md) </span></span>  
 <span data-ttu-id="fdc25-163">[Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="fdc25-163">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="fdc25-164">[Поток данных](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="fdc25-164">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="fdc25-165">Работа с файлами Excel в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="fdc25-165">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
  
  
