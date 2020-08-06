---
title: Средства и подходы для обработки (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- process [Analysis Services]
- processing [Analysis Services]
ms.assetid: 82347a16-4145-4655-8adf-2a300f1fdf99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d2b28ecf29adc8240f76ec9888f9d4cb06dda887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664570"
---
# <a name="tools-and-approaches-for-processing-analysis-services"></a><span data-ttu-id="8f554-102">Средства и способы обработки (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="8f554-102">Tools and Approaches for Processing (Analysis Services)</span></span>
  <span data-ttu-id="8f554-103">Обработка — это операция, при которой службы Analysis Services запрашивают реляционный источник данных и заполняют этими данными объекты служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="8f554-103">Processing is an operation in which Analysis Services queries a relational data source and populates Analysis Services objects using that data.</span></span>  
  
 <span data-ttu-id="8f554-104">Как администратор служб Analysis Services, вы можете выполнять и мониторить обработку объектов служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] с применением следующих подходов.</span><span class="sxs-lookup"><span data-stu-id="8f554-104">As an Analysis Services system administrator, you can execute and monitor the processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects using these approaches:</span></span>  
  
-   <span data-ttu-id="8f554-105">Проведение анализа влияния для получения представления о зависимостях объектов и области операций.</span><span class="sxs-lookup"><span data-stu-id="8f554-105">Run Impact Analysis to understand object dependencies and scope of operations</span></span>  
  
-   <span data-ttu-id="8f554-106">Обработка отдельных объектов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f554-106">Process individual objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="8f554-107">Обработка отдельных или нескольких объектов в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f554-107">Process individual or multiple objects in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="8f554-108">Проведение анализа влияния для просмотра списка связанных объектов, обработка которых будет отменена в результате текущего действия.</span><span class="sxs-lookup"><span data-stu-id="8f554-108">Run Impact Analysis to review a list of related objects that will be unprocessed as result of the current action.</span></span>  
  
-   <span data-ttu-id="8f554-109">Создание и выполнение скрипта в окне запросов XMLA служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] для обработки отдельных или нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="8f554-109">Generate and run a script in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to process individual or multiple objects</span></span>  
  
-   <span data-ttu-id="8f554-110">Использование командлетов PowerShell в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f554-110">Use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell cmdlets</span></span>  
  
-   <span data-ttu-id="8f554-111">Использование потоков управления и задач в пакетах служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f554-111">Use control flows and tasks in [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages</span></span>  
  
-   <span data-ttu-id="8f554-112">Наблюдение за обработкой с помощью приложения SQL Server Profiler.</span><span class="sxs-lookup"><span data-stu-id="8f554-112">Monitor processing with SQL Server Profiler</span></span>  
  
-   <span data-ttu-id="8f554-113">Программирование пользовательского решения с помощью объектов AMO.</span><span class="sxs-lookup"><span data-stu-id="8f554-113">Program a custom solution using AMO.</span></span> <span data-ttu-id="8f554-114">Дополнительные сведения см. в статье [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="8f554-114">For more information, see [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span></span>  
  
 <span data-ttu-id="8f554-115">Обработка имеет широкие возможности настройки, управляемые набором параметров обработки, которые определяют тип обработки (полная или добавочная), выполняемой на уровне объектов.</span><span class="sxs-lookup"><span data-stu-id="8f554-115">Processing is a highly configurable operation, controlled by a set of processing options that determine whether full or incremental processing occurs at the object level.</span></span> <span data-ttu-id="8f554-116">Дополнительные сведения об обработке параметров и объектов см. в разделах [Параметры обработки (службы Analysis Services)](processing-options-and-settings-analysis-services.md) и [Обработка объектов служб Analysis Services](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="8f554-116">For more information about processing options and objects, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) and [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f554-117">В этом разделе описываются средства и подходы для обработки многомерных моделей.</span><span class="sxs-lookup"><span data-stu-id="8f554-117">This topic describes the tools and approaches for processing multidimensional models.</span></span> <span data-ttu-id="8f554-118">Дополнительные сведения об обработке табличных моделей см. в разделах [Обработка базы данных, таблицы или секции](../tabular-models/process-database-table-or-partition-analysis-services.md) и [обработка данных &#40;табличных&#41;SSAS ](../process-data-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="8f554-118">For more information about processing tabular models, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md) and [Process Data &#40;SSAS Tabular&#41;](../process-data-ssas-tabular.md).</span></span>  
  
### <a name="processing-objects-in-sql-server-management-studio"></a><span data-ttu-id="8f554-119">Обработка объектов в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f554-119">Processing objects in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="8f554-120">Запустите среду [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и подключитесь к службам Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="8f554-120">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="8f554-121">Щелкните правой кнопкой мыши объект служб Analysis Services, который необходимо обработать, и выберите команду **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="8f554-121">Right-click the Analysis Services object you want to process and then click **Process**.</span></span> <span data-ttu-id="8f554-122">Данные можно обрабатывать на любом из следующих уровней:</span><span class="sxs-lookup"><span data-stu-id="8f554-122">You can process data at any of these levels:</span></span>  
  
    -   <span data-ttu-id="8f554-123">Базы данных</span><span class="sxs-lookup"><span data-stu-id="8f554-123">Databases</span></span>  
  
    -   <span data-ttu-id="8f554-124">Кубы</span><span class="sxs-lookup"><span data-stu-id="8f554-124">Cubes</span></span>  
  
    -   <span data-ttu-id="8f554-125">Группы мер или отдельные секции в группе мер</span><span class="sxs-lookup"><span data-stu-id="8f554-125">Measure Groups or individual partitions in the measure group</span></span>  
  
    -   <span data-ttu-id="8f554-126">Измерения</span><span class="sxs-lookup"><span data-stu-id="8f554-126">Dimensions</span></span>  
  
    -   <span data-ttu-id="8f554-127">Модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="8f554-127">Mining Models</span></span>  
  
    -   <span data-ttu-id="8f554-128">Структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="8f554-128">Mining Structures</span></span>  
  
     <span data-ttu-id="8f554-129">Объекты служб Analysis Services являются иерархическими.</span><span class="sxs-lookup"><span data-stu-id="8f554-129">Analysis Services objects are hierarchical.</span></span> <span data-ttu-id="8f554-130">При выборе базы данных может произойти обработка всех содержащихся в базе данных объектов.</span><span class="sxs-lookup"><span data-stu-id="8f554-130">If you choose database, processing can occur for all of the objects contained in the database.</span></span> <span data-ttu-id="8f554-131">Происходит ли обработка фактически, зависит от выбранных параметров обработки и состояния объектов.</span><span class="sxs-lookup"><span data-stu-id="8f554-131">Whether processing actually occurs will vary depending on the process option you select and the state of the object.</span></span> <span data-ttu-id="8f554-132">В частности, если объект не обработан, то при обработке его родительского объекта будет обработан и сам этот объект.</span><span class="sxs-lookup"><span data-stu-id="8f554-132">Specifically, if an object is unprocessed, processing its parent will result in that object getting processed.</span></span> <span data-ttu-id="8f554-133">Дополнительные сведения о зависимостях объектов см. в разделе [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="8f554-133">For more information about object dependencies, see [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
3.  <span data-ttu-id="8f554-134">В диалоговом окне **Обработка** в поле **Параметры обработки**оставьте заданное по умолчанию значение или выберите другой вариант из списка.</span><span class="sxs-lookup"><span data-stu-id="8f554-134">In the **Process** dialog box, in **Process Options**, use the default value provided or select a different option from the list.</span></span> <span data-ttu-id="8f554-135">Дополнительные сведения о каждом параметре см. в разделе [Настройка параметров обработки (службы Analysis Services)](processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="8f554-135">For more information about each option, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="8f554-136">Нажмите кнопку **Анализ влияния** , чтобы выделить и при необходимости обработать зависимые объекты, которые будут затронуты при обработке объектов, перечисленных в диалоговом окне «Обработка».</span><span class="sxs-lookup"><span data-stu-id="8f554-136">Click **Impact Analysis** to identify and optionally process dependent objects that are affected if the objects listed in the Process dialog box are processed.</span></span>  
  
5.  <span data-ttu-id="8f554-137">Также можно нажать кнопку **Изменить параметры** , чтобы изменить порядок обработки, операции обработки при определенных видах ошибок или другие параметры.</span><span class="sxs-lookup"><span data-stu-id="8f554-137">Optionally, click **Change Settings** to modify the processing order, processing behavior relative to specific types of errors, and other settings.</span></span>  
  
6.  <span data-ttu-id="8f554-138">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8f554-138">Click **OK**.</span></span>  
  
     <span data-ttu-id="8f554-139">В диалоговом окне «Ход обработки» отображается текущее состояние выполнения каждой из команд.</span><span class="sxs-lookup"><span data-stu-id="8f554-139">The Process Progress dialog box provides ongoing status for each command.</span></span> <span data-ttu-id="8f554-140">Если сообщение о состоянии усечено, нажмите кнопку **Просмотр подробностей** , чтобы просмотреть сообщение целиком.</span><span class="sxs-lookup"><span data-stu-id="8f554-140">If a status message is truncated, you can click **View Details** to read the entire message.</span></span>  
  
### <a name="processing-objects-in-sql-server-data-tools"></a><span data-ttu-id="8f554-141">Обработка объектов в SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="8f554-141">Processing Objects in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="8f554-142">Запустите среду [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] и откройте уже развернутый проект.</span><span class="sxs-lookup"><span data-stu-id="8f554-142">Start [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open a project that has been deployed.</span></span>  
  
2.  <span data-ttu-id="8f554-143">В обозревателе решений откройте папку **Измерения** , вложенную в развернутый проект.</span><span class="sxs-lookup"><span data-stu-id="8f554-143">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
3.  <span data-ttu-id="8f554-144">Щелкните измерение правой кнопкой мыши и выберите команду **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="8f554-144">Right-click a dimension, and then click **Process**.</span></span> <span data-ttu-id="8f554-145">Вы можете щелкнуть правой кнопкой мыши несколько измерений, чтобы одновременно обработать несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="8f554-145">You can right-click multiple dimensions to process multiple objects at once.</span></span> <span data-ttu-id="8f554-146">Дополнительные сведения см. в разделе [Пакетная обработка (службы Analysis Services)](batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="8f554-146">For more information, see [Batch Processing &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="8f554-147">Убедитесь в том, что в диалоговом окне **Обработка измерения** в разделе **Список объектов** для столбца **Параметры обработки**выбран параметр **Обработка. Полная**.</span><span class="sxs-lookup"><span data-stu-id="8f554-147">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="8f554-148">Если этот параметр не выбран, выделите столбец **Параметры обработки**, а затем в раскрывающемся списке выберите пункт **Полная обработка** .</span><span class="sxs-lookup"><span data-stu-id="8f554-148">If it is not, under **Process Options**, click the option, and select **Process Full** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="8f554-149">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="8f554-149">Click **Run**.</span></span>  
  
6.  <span data-ttu-id="8f554-150">После завершения обработки нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8f554-150">When processing is finished, click **Close**.</span></span>  
  
##  <a name="run-impact-analysis-to-identify-object-dependencies-and-scope-of-operations"></a><a name="bkmk_impactanalysis"></a><span data-ttu-id="8f554-151">Выполнение анализа влияния для определения зависимостей объектов и области операций</span><span class="sxs-lookup"><span data-stu-id="8f554-151">Run Impact Analysis to identify object dependencies and scope of operations</span></span>  
  
1.  <span data-ttu-id="8f554-152">Перед обработкой объекта служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] или [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]можно выполнить анализ влияния на связанные объекты, нажав кнопку **Анализ влияния** в одном из диалоговых окон **Обработка объектов** .</span><span class="sxs-lookup"><span data-stu-id="8f554-152">Before you process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object in either [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can analyze the effect on related objects by clicking **Impact Analysis** in one of the **Process Objects** dialog boxes.</span></span>  
  
2.  <span data-ttu-id="8f554-153">Щелкните правой кнопкой мыши измерение, куб, группу мер или секцию, чтобы открыть диалоговое окно **Обработка объектов** .</span><span class="sxs-lookup"><span data-stu-id="8f554-153">Right-click a dimension, cube, measure group, or partition to open a **Process Objects** dialog box.</span></span>  
  
3.  <span data-ttu-id="8f554-154">Нажмите кнопку **Анализ влияния**.</span><span class="sxs-lookup"><span data-stu-id="8f554-154">Click **Impact Analysis**.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="8f554-155">просматривают модель и сообщают о требованиях повторной обработки для объектов, которые связаны с объектом, выбранным для обработки.</span><span class="sxs-lookup"><span data-stu-id="8f554-155">scans the model and reports on reprocessing requirements for objects that are related to the one you selected for processing.</span></span>  
  
### <a name="processing-objects-using-xmla"></a><span data-ttu-id="8f554-156">Обработка объектов с помощью XMLA</span><span class="sxs-lookup"><span data-stu-id="8f554-156">Processing objects using XMLA</span></span>  
  
1.  <span data-ttu-id="8f554-157">Запустите среду [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и подключитесь к службам Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="8f554-157">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="8f554-158">Щелкните правой кнопкой мыши обрабатываемый объект и выберите команду **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="8f554-158">Right-click the object to be processed and then click **Process**.</span></span>  
  
3.  <span data-ttu-id="8f554-159">В диалоговом окне **Обработка** выберите нужный параметр обработки.</span><span class="sxs-lookup"><span data-stu-id="8f554-159">In the **Process** dialog box, select the process option you want to use.</span></span> <span data-ttu-id="8f554-160">При необходимости измените другие параметры.</span><span class="sxs-lookup"><span data-stu-id="8f554-160">Modify any other settings.</span></span> <span data-ttu-id="8f554-161">Запустите анализ влияния, чтобы определить, какие изменения может потребоваться внести.</span><span class="sxs-lookup"><span data-stu-id="8f554-161">Run Impact Analysis to identify any changes you might need to make.</span></span>  
  
4.  <span data-ttu-id="8f554-162">На экране **Обработать объекты** нажмите кнопку **Скрипт** .</span><span class="sxs-lookup"><span data-stu-id="8f554-162">Click **Script** on the **Process Objects** screen.</span></span>  
  
     <span data-ttu-id="8f554-163">Будет сформирован скрипт XMLA, а затем откроется окно «Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] — запрос XML для аналитики».</span><span class="sxs-lookup"><span data-stu-id="8f554-163">This generates an XMLA script and opens an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window.</span></span>  
  
5.  <span data-ttu-id="8f554-164">Закройте диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="8f554-164">Close the dialog box.</span></span> <span data-ttu-id="8f554-165">Скрипт содержит команду обработки и параметры, указанные в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="8f554-165">The script contains the processing command and options that were specified in the dialog box.</span></span>  
  
6.  <span data-ttu-id="8f554-166">Также вы можете продолжить добавление инструкций в скрипт, если нужно обработать в этом пакете дополнительные объекты.</span><span class="sxs-lookup"><span data-stu-id="8f554-166">Optionally, you can continue adding to the script if you want to process additional objects in the same batch.</span></span> <span data-ttu-id="8f554-167">Чтобы продолжить, повторите предыдущие действия, добавив инструкции в созданный скрипт, чтобы получить один скрипт для всех операций обработки.</span><span class="sxs-lookup"><span data-stu-id="8f554-167">To continue, repeat the previous steps, appending the generated script so that you have a single script for all processing operations.</span></span> <span data-ttu-id="8f554-168">Пример см. в разделе [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="8f554-168">To view an example, see [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span></span>  
  
7.  <span data-ttu-id="8f554-169">Нажмите в строке меню кнопку **Запрос**и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8f554-169">From the menu bar, click **Query**, and then click **Execute**.</span></span>  
  
### <a name="processing-objects-using-powershell"></a><span data-ttu-id="8f554-170">Обработка объектов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f554-170">Processing objects using PowerShell</span></span>  
  
1.  <span data-ttu-id="8f554-171">Начиная с этого выпуска SQL Server, командлеты служб Analysis Services PowerShell можно использовать для обработки объектов.</span><span class="sxs-lookup"><span data-stu-id="8f554-171">Starting in this release of SQL Server, you can use Analysis Services PowerShell cmdlets to process objects.</span></span> <span data-ttu-id="8f554-172">Следующие командлеты можно запускать интерактивно или из скрипта:</span><span class="sxs-lookup"><span data-stu-id="8f554-172">The following cmdlets can be run interactively or in script:</span></span>  
  
    -   [<span data-ttu-id="8f554-173">Командлет Invoke-ProcessCube</span><span class="sxs-lookup"><span data-stu-id="8f554-173">Invoke-ProcessCube cmdlet</span></span>](/powershell/module/sqlserver/invoke-processcube)  
  
    -   [<span data-ttu-id="8f554-174">Командлет Invoke-ProcessDimension</span><span class="sxs-lookup"><span data-stu-id="8f554-174">Invoke-ProcessDimension cmdlet</span></span>](/powershell/module/sqlserver/invoke-processdimension)  
  
    -   [<span data-ttu-id="8f554-175">Командлет Invoke-ProcessPartition</span><span class="sxs-lookup"><span data-stu-id="8f554-175">Invoke-ProcessPartition cmdlet</span></span>](/powershell/module/sqlserver/invoke-processpartition)  
  
    -   <span data-ttu-id="8f554-176">[Командлет Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd), который может использоваться для выполнения скриптов XMLA, MDX или DMX, содержащих команды обработки.</span><span class="sxs-lookup"><span data-stu-id="8f554-176">[Invoke-ASCmd cmdlet](/powershell/module/sqlserver/invoke-ascmd), which can be used to execute XMLA, MDX, or DMX script that includes processing commands.</span></span>  
  
### <a name="monitoring-object-processing-using-sql-server-profiler"></a><span data-ttu-id="8f554-177">Наблюдение за обработкой объектов в приложении SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8f554-177">Monitoring object processing using SQL Server Profiler</span></span>  
  
1.  <span data-ttu-id="8f554-178">Подключитесь к экземпляру служб Analysis Services в приложении SQL Server Profiler.</span><span class="sxs-lookup"><span data-stu-id="8f554-178">Connect to an Analysis Services instance in SQL Server Profiler.</span></span>  
  
2.  <span data-ttu-id="8f554-179">В окне «Выбор событий» нажмите кнопку **Показать все события** , чтобы добавить все события в список.</span><span class="sxs-lookup"><span data-stu-id="8f554-179">In Events Selection, click **Show all events** to add all events to the list.</span></span>  
  
3.  <span data-ttu-id="8f554-180">Выберите следующие события.</span><span class="sxs-lookup"><span data-stu-id="8f554-180">Choose the following events:</span></span>  
  
    -   <span data-ttu-id="8f554-181">**Начало команды** и **Завершение команды** , чтобы показать, когда обработка начинается и останавливается.</span><span class="sxs-lookup"><span data-stu-id="8f554-181">**Command Begin** and **Command End** to show when processing starts and stops</span></span>  
  
    -   <span data-ttu-id="8f554-182">**Ошибка** , чтобы регистрировать ошибки.</span><span class="sxs-lookup"><span data-stu-id="8f554-182">**Error** to capture any errors</span></span>  
  
    -   <span data-ttu-id="8f554-183">**Начало отчета о состоянии**, **Текущий отчет о состоянии**и **Окончание отчета о состоянии** , чтобы сообщать о состоянии обработки и показывать SQL-запросы, используемые для получения данных.</span><span class="sxs-lookup"><span data-stu-id="8f554-183">**Progress Report Begin**, **Progress Report Current**, and **Progress Report End** to report on process status and show the SQL queries used to retrieve the data</span></span>  
  
    -   <span data-ttu-id="8f554-184">**Начало выполнения скрипта многомерных выражений** и **Конец выполнения скрипта многомерных выражений** , чтобы показать вычисления кубов.</span><span class="sxs-lookup"><span data-stu-id="8f554-184">**Execute MDX Script Begin** and **Execute MDX Script End** to show the cube calculations</span></span>  
  
    -   <span data-ttu-id="8f554-185">Также можно добавить события блокировки, если идет диагностика проблем с производительностью, относящихся к обработке.</span><span class="sxs-lookup"><span data-stu-id="8f554-185">Optionally, add lock events if you are diagnosing performance problems related to processing</span></span>  
  
### <a name="process-analysis-services-objects-using-integration-services"></a><span data-ttu-id="8f554-186">Обработка объектов служб Analysis Services с использованием служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="8f554-186">Process Analysis Services objects using Integration Services</span></span>  
  
1.  <span data-ttu-id="8f554-187">В службах [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]создайте пакет, который используют задачу «Обработка средствами Analysis Services» для автоматического заполнения объектов новыми данными при регулярном обновлении исходной реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="8f554-187">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], create a package that uses the Analysis Services Processing Task to automatically populate objects with new data when you make regular updates to your source relational database.</span></span>  
  
2.  <span data-ttu-id="8f554-188">В окне **Область элементов служб SSIS**дважды щелкните элемент **Обработка средствами Analysis Services** , чтобы добавить его в пакет.</span><span class="sxs-lookup"><span data-stu-id="8f554-188">In the **SSIS Toolbox**, double-click **Analysis Services Processing** to add it to the package.</span></span>  
  
3.  <span data-ttu-id="8f554-189">Измените задачу, указав соединение с базой данных, объекты для обработки и параметр обработки.</span><span class="sxs-lookup"><span data-stu-id="8f554-189">Edit the task to specify a connection to the database, which objects to process, and the process option.</span></span> <span data-ttu-id="8f554-190">Дополнительные сведения о реализации этой задачи см. в разделе [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="8f554-190">For more information about how to implement this task, see [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f554-191">См. также:</span><span class="sxs-lookup"><span data-stu-id="8f554-191">See Also</span></span>  
 [<span data-ttu-id="8f554-192">Обработка объектов многомерной модели</span><span class="sxs-lookup"><span data-stu-id="8f554-192">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
