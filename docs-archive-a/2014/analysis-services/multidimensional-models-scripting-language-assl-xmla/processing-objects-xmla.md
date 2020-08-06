---
title: Обработка объектов (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- objects [XML for Analysis]
- XML for Analysis, objects
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
- writeback [Analysis Services], XML for Analysis
- out-of-line bindings
- processing objects [XML for Analysis]
- XMLA, objects
ms.assetid: a65b3249-303d-49c6-98af-6ac6eed11a03
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e59c7953ae8fc7d3cfceafa7b0e9d8c7186daf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738936"
---
# <a name="processing-objects-xmla"></a><span data-ttu-id="55f29-102">Обработка объектов (XMLA)</span><span class="sxs-lookup"><span data-stu-id="55f29-102">Processing Objects (XMLA)</span></span>
  <span data-ttu-id="55f29-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Обработка — это шаг или последовательность шагов, которые включают данные в данные для бизнес-анализа.</span><span class="sxs-lookup"><span data-stu-id="55f29-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], processing is the step or series of steps that turn data into information for business analysis.</span></span> <span data-ttu-id="55f29-104">Характеристики обработки меняются в зависимости от типа объекта, но обработка всегда является составной частью процесса преобразования данных в сведения.</span><span class="sxs-lookup"><span data-stu-id="55f29-104">Processing is different depending on the type of object, but processing is always part of turning data into information.</span></span>  
  
 <span data-ttu-id="55f29-105">Для обработки [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] объекта можно использовать команду [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="55f29-105">To process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object, you can use the [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) command.</span></span> <span data-ttu-id="55f29-106">Команда `Process` в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] может обрабатывать следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="55f29-106">The `Process` command can process the following objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance:</span></span>  
  
-   <span data-ttu-id="55f29-107">Кубы</span><span class="sxs-lookup"><span data-stu-id="55f29-107">Cubes</span></span>  
  
-   <span data-ttu-id="55f29-108">Базы данных</span><span class="sxs-lookup"><span data-stu-id="55f29-108">Databases</span></span>  
  
-   <span data-ttu-id="55f29-109">Измерения</span><span class="sxs-lookup"><span data-stu-id="55f29-109">Dimensions</span></span>  
  
-   <span data-ttu-id="55f29-110">Группы мер</span><span class="sxs-lookup"><span data-stu-id="55f29-110">Measure groups</span></span>  
  
-   <span data-ttu-id="55f29-111">Модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="55f29-111">Mining models</span></span>  
  
-   <span data-ttu-id="55f29-112">Структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="55f29-112">Mining structures</span></span>  
  
-   <span data-ttu-id="55f29-113">Секции</span><span class="sxs-lookup"><span data-stu-id="55f29-113">Partitions</span></span>  
  
 <span data-ttu-id="55f29-114">Чтобы можно было управлять обработкой объектов, в команде `Process` предусмотрены различные свойства, которые можно задавать.</span><span class="sxs-lookup"><span data-stu-id="55f29-114">To control the processing of objects, the `Process` command has various properties that can be set.</span></span> <span data-ttu-id="55f29-115">Команда `Process` имеет свойства, которые определяют, какой объем обработки должен быть выполнен, какие объекты должны быть обработаны, будут ли использоваться внешние привязки, а также способ обработки ошибок и управления таблицами обратной записи.</span><span class="sxs-lookup"><span data-stu-id="55f29-115">The `Process` command has properties that control: how much processing will be done, which objects will be processed, whether to use out-of-line bindings, how to handle errors, and how to manage writeback tables.</span></span>  
  
## <a name="specifying-processing-options"></a><span data-ttu-id="55f29-116">Указание параметров обработки</span><span class="sxs-lookup"><span data-stu-id="55f29-116">Specifying Processing Options</span></span>  
 <span data-ttu-id="55f29-117">Свойство [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) `Process` команды задает параметр обработки, используемый при обработке объекта.</span><span class="sxs-lookup"><span data-stu-id="55f29-117">The [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) property of the `Process` command specifies the processing option to use when processing the object.</span></span> <span data-ttu-id="55f29-118">Дополнительные сведения об обработке см. в разделе [Настройка параметров обработки (службы Analysis Services)](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="55f29-118">For more information about processing options, see [Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span></span>  
  
 <span data-ttu-id="55f29-119">В следующей таблице приведены константы для свойства `Type`, а также различные объекты, которые можно обрабатывать при помощи каждой константы.</span><span class="sxs-lookup"><span data-stu-id="55f29-119">The following table lists the constants for the `Type` property and the various objects that can be processed using each constant.</span></span>  
  
|<span data-ttu-id="55f29-120">Значение `Type`</span><span class="sxs-lookup"><span data-stu-id="55f29-120">`Type` value</span></span>|<span data-ttu-id="55f29-121">Применимые объекты</span><span class="sxs-lookup"><span data-stu-id="55f29-121">Applicable objects</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="55f29-122">*ProcessFull*</span><span class="sxs-lookup"><span data-stu-id="55f29-122">*ProcessFull*</span></span>|<span data-ttu-id="55f29-123">Куб, база данных, измерение, группа мер, модель интеллектуального анализа данных, структура интеллектуального анализа данных, секция</span><span class="sxs-lookup"><span data-stu-id="55f29-123">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="55f29-124">*ProcessAdd*</span><span class="sxs-lookup"><span data-stu-id="55f29-124">*ProcessAdd*</span></span>|<span data-ttu-id="55f29-125">Измерение, секция</span><span class="sxs-lookup"><span data-stu-id="55f29-125">Dimension, partition</span></span>|  
|<span data-ttu-id="55f29-126">*ProcessUpdate*</span><span class="sxs-lookup"><span data-stu-id="55f29-126">*ProcessUpdate*</span></span>|<span data-ttu-id="55f29-127">Измерение</span><span class="sxs-lookup"><span data-stu-id="55f29-127">Dimension</span></span>|  
|<span data-ttu-id="55f29-128">*ProcessIndexes*</span><span class="sxs-lookup"><span data-stu-id="55f29-128">*ProcessIndexes*</span></span>|<span data-ttu-id="55f29-129">Измерение, куб, группа мер, секция</span><span class="sxs-lookup"><span data-stu-id="55f29-129">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="55f29-130">*ProcessData*</span><span class="sxs-lookup"><span data-stu-id="55f29-130">*ProcessData*</span></span>|<span data-ttu-id="55f29-131">Измерение, куб, группа мер, секция</span><span class="sxs-lookup"><span data-stu-id="55f29-131">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="55f29-132">*ProcessDefault*</span><span class="sxs-lookup"><span data-stu-id="55f29-132">*ProcessDefault*</span></span>|<span data-ttu-id="55f29-133">Куб, база данных, измерение, группа мер, модель интеллектуального анализа данных, структура интеллектуального анализа данных, секция</span><span class="sxs-lookup"><span data-stu-id="55f29-133">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="55f29-134">*ProcessClear*</span><span class="sxs-lookup"><span data-stu-id="55f29-134">*ProcessClear*</span></span>|<span data-ttu-id="55f29-135">Куб, база данных, измерение, группа мер, модель интеллектуального анализа данных, структура интеллектуального анализа данных, секция</span><span class="sxs-lookup"><span data-stu-id="55f29-135">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="55f29-136">*ProcessStructure*</span><span class="sxs-lookup"><span data-stu-id="55f29-136">*ProcessStructure*</span></span>|<span data-ttu-id="55f29-137">Куб, структура интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="55f29-137">Cube, mining structure</span></span>|  
|<span data-ttu-id="55f29-138">*процессклеарструктуреонли*</span><span class="sxs-lookup"><span data-stu-id="55f29-138">*ProcessClearStructureOnly*</span></span>|<span data-ttu-id="55f29-139">Структура интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="55f29-139">Mining structure</span></span>|  
|<span data-ttu-id="55f29-140">*ProcessScriptCache*</span><span class="sxs-lookup"><span data-stu-id="55f29-140">*ProcessScriptCache*</span></span>|<span data-ttu-id="55f29-141">Куб</span><span class="sxs-lookup"><span data-stu-id="55f29-141">Cube</span></span>|  
  
 <span data-ttu-id="55f29-142">Дополнительные сведения об обработке [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] объектов см. в [разделе Обработка объектов многомерной модели](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="55f29-142">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
## <a name="specifying-objects-to-be-processed"></a><span data-ttu-id="55f29-143">Указание объектов для обработки</span><span class="sxs-lookup"><span data-stu-id="55f29-143">Specifying Objects to be Processed</span></span>  
 <span data-ttu-id="55f29-144">Свойство [объекта](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) `Process` команды содержит идентификатор объекта для обработки.</span><span class="sxs-lookup"><span data-stu-id="55f29-144">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Process` command contains the object identifier of the object to be processed.</span></span> <span data-ttu-id="55f29-145">В команде `Process` можно указать только один объект, однако при его обработке обрабатываются также все дочерние объекты.</span><span class="sxs-lookup"><span data-stu-id="55f29-145">Only one object can be specified in a `Process` command, but processing an object also processes any child objects.</span></span> <span data-ttu-id="55f29-146">Например, при обработке группы мер в кубе обрабатываются все секции для этой группы мер, а при обработке базы данных обрабатываются все объекты, включая кубы, измерения и структуры интеллектуального анализа данных, содержащиеся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="55f29-146">For example, processing a measure group in a cube processes all the partitions for that measure group, while processing a database processes all the objects, including cubes, dimensions, and mining structures, that are contained by the database.</span></span>  
  
 <span data-ttu-id="55f29-147">Если атрибуту `ProcessAffectedObjects` команды `Process` задать значение TRUE, то все связанные объекты, вовлеченные в обработку указанного объекта, также будут обработаны.</span><span class="sxs-lookup"><span data-stu-id="55f29-147">If you set the `ProcessAffectedObjects` attribute of the `Process` command to true, any related object affected by processing the specified object is also processed.</span></span> <span data-ttu-id="55f29-148">Например, если измерение постепенно обновляется с помощью параметра обработки *ProcessUpdate* в `Process` команде, все секции, агрегаты которых становятся недействительными из-за добавления или удаления элементов, также обрабатываются, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Если `ProcessAffectedObjects` свойство имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="55f29-148">For example, if a dimension is incrementally updated by using the *ProcessUpdate* processing option in the `Process` command, any partition whose aggregations are invalidated because of members being added or deleted is also processed by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] if `ProcessAffectedObjects` is set to true.</span></span> <span data-ttu-id="55f29-149">В этом случае одна команда `Process` позволяет обрабатывать несколько объектов в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], но службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] определяют, какие объекты также должны обрабатываться, кроме одного объекта, указанного в команде `Process`.</span><span class="sxs-lookup"><span data-stu-id="55f29-149">In this case, a single `Process` command can process multiple objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, but [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determines which objects besides the single object specified in the `Process` command must also be processed.</span></span>  
  
 <span data-ttu-id="55f29-150">Однако можно обрабатывать одновременно несколько объектов, например измерений, при помощи нескольких команд `Process` в составе команды `Batch`.</span><span class="sxs-lookup"><span data-stu-id="55f29-150">However, you can process multiple objects, such as dimensions, at the same time by using multiple `Process` commands within a `Batch` command.</span></span> <span data-ttu-id="55f29-151">Пакетные операции позволяют точнее управлять последовательной или параллельной обработкой объектов в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], чем при использовании атрибута `ProcessAffectedObjects`, а также позволяют подстраивать подход к обработке применительно к более крупным базам данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55f29-151">Batch operations provide a finer level of control for serial or parallel processing of objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance than using the `ProcessAffectedObjects` attribute, and let you to tune your processing approach for larger [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.</span></span> <span data-ttu-id="55f29-152">Дополнительные сведения о выполнении пакетных операций см. в разделе [выполнение пакетных операций &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="55f29-152">For more information about performing batch operations, see [Performing Batch Operations &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span></span>  
  
## <a name="specifying-out-of-line-bindings"></a><span data-ttu-id="55f29-153">Указание внешних привязок</span><span class="sxs-lookup"><span data-stu-id="55f29-153">Specifying Out-of-Line Bindings</span></span>  
 <span data-ttu-id="55f29-154">Если `Process` команда не содержится в `Batch` команде, можно дополнительно указать неиспользуемые привязки в свойствах [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla)и [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) `Process` команды для обрабатываемых объектов.</span><span class="sxs-lookup"><span data-stu-id="55f29-154">If the `Process` command is not contained by a `Batch` command, you can optionally specify out-of-line bindings in the [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla), and [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) properties of the `Process` command for the objects to be processed.</span></span> <span data-ttu-id="55f29-155">Внешние привязки — это ссылки на источники данных, представления источников данных и другие объекты, в которых привязка существует только во время выполнения команды `Process` и которые переопределяют любые существующие привязки, связанные с обрабатываемыми объектами.</span><span class="sxs-lookup"><span data-stu-id="55f29-155">Out-of-line bindings are references to data sources, data source views, and other objects in which the binding exists only during the execution of the `Process` command, and which override any existing bindings associated with the objects being processed.</span></span> <span data-ttu-id="55f29-156">Если внешние привязки не указаны, используются привязки, связанные в данный момент с обрабатываемыми объектами.</span><span class="sxs-lookup"><span data-stu-id="55f29-156">If out-of-line bindings are not specified, the bindings currently associated with the objects to be processed are used.</span></span>  
  
 <span data-ttu-id="55f29-157">Внешние привязки используются в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="55f29-157">Out-of-line bindings are used in the following circumstances:</span></span>  
  
-   <span data-ttu-id="55f29-158">В случае постепенной обработки секции, в которой должна быть указана альтернативная таблица фактов или фильтр для существующей таблицы фактов с тем, чтобы строки не засчитывались дважды.</span><span class="sxs-lookup"><span data-stu-id="55f29-158">Incrementally processing a partition, in which an alternative fact table or a filter on the existing fact table must be specified to make sure that rows are not counted twice.</span></span>  
  
-   <span data-ttu-id="55f29-159">Использование задачи потока данных в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] для предоставления данных при обработке измерения, модели интеллектуального анализа данных или секции.</span><span class="sxs-lookup"><span data-stu-id="55f29-159">Using a data flow task in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to provide data while processing a dimension, mining model, or partition.</span></span>  
  
 <span data-ttu-id="55f29-160">Внешние привязки описаны как часть языка сценариев служб Analysis Services (языка ASSL).</span><span class="sxs-lookup"><span data-stu-id="55f29-160">Out-of-line bindings are described as part of the Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="55f29-161">Дополнительные сведения о нелинейных привязках в ASSL см. в разделе [Источники данных и привязки &#40;многомерных&#41;SSAS ](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="55f29-161">For more information about out-of-line bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span></span>  
  
### <a name="incrementally-updating-partitions"></a><span data-ttu-id="55f29-162">Добавочное обновление секций</span><span class="sxs-lookup"><span data-stu-id="55f29-162">Incrementally Updating Partitions</span></span>  
 <span data-ttu-id="55f29-163">Для добавочного обновления уже обработанной секции обычно требуется внешняя привязка, так как привязка, указанная для этой секции, ссылается на данные таблицы фактов, которые уже были статистически обработаны в рамках данной секции.</span><span class="sxs-lookup"><span data-stu-id="55f29-163">Incrementally updating an already processed partition typically requires an out-of-line binding because the binding specified for the partition references fact table data already aggregated within the partition.</span></span> <span data-ttu-id="55f29-164">При выполнении добавочного обновления уже обработанной секции с помощью команды `Process` службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] выполняют следующие действия.</span><span class="sxs-lookup"><span data-stu-id="55f29-164">When incrementally updating an already processed partition by using the `Process` command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] performs the following actions:</span></span>  
  
-   <span data-ttu-id="55f29-165">Создают временную секцию с такой же структурой, как у секции, добавочное обновление которой необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="55f29-165">Creates a temporary partition with a structure identical to that of the partition to be incrementally updated.</span></span>  
  
-   <span data-ttu-id="55f29-166">Обрабатывают временную секцию при помощи внешней привязки, указанной в команде `Process`.</span><span class="sxs-lookup"><span data-stu-id="55f29-166">Processes the temporary partition, using the out-of-line binding specified in the `Process` command.</span></span>  
  
-   <span data-ttu-id="55f29-167">Объединяют временную секцию с существующей выделенной секцией.</span><span class="sxs-lookup"><span data-stu-id="55f29-167">Merges the temporary partition with the existing selected partition.</span></span>  
  
 <span data-ttu-id="55f29-168">Дополнительные сведения о слиянии секций с помощью XML для аналитики (XMLA) см. в разделе [Слияние секций &#40;xmla&#41;](merging-partitions-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="55f29-168">For more information about merging partitions using XML for Analysis (XMLA), see [Merging Partitions &#40;XMLA&#41;](merging-partitions-xmla.md).</span></span>  
  
## <a name="handling-processing-errors"></a><span data-ttu-id="55f29-169">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="55f29-169">Handling Processing Errors</span></span>  
 <span data-ttu-id="55f29-170">Свойство [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) `Process` команды позволяет указать способ обработки ошибок, обнаруженных при обработке объекта.</span><span class="sxs-lookup"><span data-stu-id="55f29-170">The [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) property of the `Process` command lets you specify how to handle errors encountered while processing an object.</span></span> <span data-ttu-id="55f29-171">Например, при обработке измерения службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] обнаруживают повторяющиеся значение в ключевом столбце ключевого атрибута.</span><span class="sxs-lookup"><span data-stu-id="55f29-171">For example, while processing a dimension, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encounters a duplicate value in the key column of the key attribute.</span></span> <span data-ttu-id="55f29-172">Поскольку ключи атрибутов должны быть уникальны, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] удаляют повторяющиеся записи.</span><span class="sxs-lookup"><span data-stu-id="55f29-172">Because attribute keys must be unique, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] discards the duplicate records.</span></span> <span data-ttu-id="55f29-173">Основываясь на свойстве [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) объекта `ErrorConfiguration` , [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] может:</span><span class="sxs-lookup"><span data-stu-id="55f29-173">Based on the [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) property of `ErrorConfiguration`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] could:</span></span>  
  
-   <span data-ttu-id="55f29-174">Пропустить ошибку и продолжить обработку измерения.</span><span class="sxs-lookup"><span data-stu-id="55f29-174">Ignore the error and continue processing the dimension.</span></span>  
  
-   <span data-ttu-id="55f29-175">Возвратить сообщение, указывающее, что службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] обнаружили повторяющийся ключ, и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="55f29-175">Return a message that states [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encountered a duplicate key and continue processing.</span></span>  
  
 <span data-ttu-id="55f29-176">Существует много схожих условий, для которых предусмотрены параметры свойства `ErrorConfiguration` при выполнении команды `Process`.</span><span class="sxs-lookup"><span data-stu-id="55f29-176">There are many similar conditions for which `ErrorConfiguration` provides options during a `Process` command.</span></span>  
  
## <a name="managing-writeback-tables"></a><span data-ttu-id="55f29-177">Управление таблицами обратной записи</span><span class="sxs-lookup"><span data-stu-id="55f29-177">Managing Writeback Tables</span></span>  
 <span data-ttu-id="55f29-178">Если команда `Process` обнаруживает секцию, доступную для записи, куб или группу мер для такой секции, которые еще не полностью обработаны, для этой секции может еще не существовать таблица обратной записи.</span><span class="sxs-lookup"><span data-stu-id="55f29-178">If the `Process` command encounters a write-enabled partition, or a cube or measure group for such a partition, that is not already fully processed, a writeback table may not already exist for that partition.</span></span> <span data-ttu-id="55f29-179">Свойство [WritebackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) `Process` команды определяет [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , следует ли создавать таблицу обратной записи.</span><span class="sxs-lookup"><span data-stu-id="55f29-179">The [WritebackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) property of the `Process` command determines whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should create a writeback table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="55f29-180">Примеры</span><span class="sxs-lookup"><span data-stu-id="55f29-180">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="55f29-181">Описание</span><span class="sxs-lookup"><span data-stu-id="55f29-181">Description</span></span>  
 <span data-ttu-id="55f29-182">В следующем примере производится полная обработка образца базы данных [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55f29-182">The following example fully processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="55f29-183">Код</span><span class="sxs-lookup"><span data-stu-id="55f29-183">Code</span></span>  
  
```  
<Process xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
  </Object>  
  <Type>ProcessFull</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
### <a name="description"></a><span data-ttu-id="55f29-184">Описание</span><span class="sxs-lookup"><span data-stu-id="55f29-184">Description</span></span>  
 <span data-ttu-id="55f29-185">В следующем примере выполняется добавочная обработка **Internet_Sales_2004** секции в группе мер **Internet Sales** Куба **Adventure Works DW** в [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] образце [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных.</span><span class="sxs-lookup"><span data-stu-id="55f29-185">The following example incrementally processes the **Internet_Sales_2004** partition in the **Internet Sales** measure group of the **Adventure Works DW** cube in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="55f29-186">`Process`Команда добавляет агрегаты для дат заказов позже 31 декабря 2006 в секцию, используя нелинейную привязку запроса в `Bindings` свойстве `Process` команды для получения строк таблицы фактов, из которых формируются агрегаты для добавления в секцию.</span><span class="sxs-lookup"><span data-stu-id="55f29-186">The `Process` command is adding aggregations for order dates later than December 31, 2006 to the partition by using an out-of-line query binding in the `Bindings` property of the `Process` command to retrieve the fact table rows from which to generate aggregations to add to the partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="55f29-187">Код</span><span class="sxs-lookup"><span data-stu-id="55f29-187">Code</span></span>  
  
```  
<Process ProcessAffectedObjects="true" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2006</PartitionID>  
  </Object>  
  <Bindings>  
    <Binding>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2006</PartitionID>  
      <Source xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="QueryBinding">  
        <DataSourceID>Adventure Works DW</DataSourceID>  
        <QueryDefinition>  
          SELECT  
            [dbo].[FactInternetSales].[ProductKey],  
            [dbo].[FactInternetSales].[OrderDateKey],  
            [dbo].[FactInternetSales].[DueDateKey],  
            [dbo].[FactInternetSales].[ShipDateKey],   
            [dbo].[FactInternetSales].[CustomerKey],   
            [dbo].[FactInternetSales].[PromotionKey],  
            [dbo].[FactInternetSales].[CurrencyKey],  
            [dbo].[FactInternetSales].[SalesTerritoryKey],  
            [dbo].[FactInternetSales].[SalesOrderNumber],  
            [dbo].[FactInternetSales].[SalesOrderLineNumber],  
            [dbo].[FactInternetSales].[RevisionNumber],  
            [dbo].[FactInternetSales].[OrderQuantity],  
            [dbo].[FactInternetSales].[UnitPrice],  
            [dbo].[FactInternetSales].[ExtendedAmount],  
            [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
            [dbo].[FactInternetSales].[DiscountAmount],  
            [dbo].[FactInternetSales].[ProductStandardCost],  
            [dbo].[FactInternetSales].[TotalProductCost],  
            [dbo].[FactInternetSales].[SalesAmount],  
            [dbo].[FactInternetSales].[TaxAmt],  
            [dbo].[FactInternetSales].[Freight],  
            [dbo].[FactInternetSales].[CarrierTrackingNumber],  
            [dbo].[FactInternetSales].[CustomerPONumber]  
          FROM [dbo].[FactInternetSales]  
          WHERE OrderDateKey > '1280'  
        </QueryDefinition>  
      </Source>  
    </Binding>  
  </Bindings>  
  <Type>ProcessAdd</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
  
