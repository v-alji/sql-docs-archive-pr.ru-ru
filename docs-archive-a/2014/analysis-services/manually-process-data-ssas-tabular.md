---
title: Обработка данных вручную (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.datarefreshprogressdb.f1
ms.assetid: 0918c04c-c1e6-45b4-acfa-96fa578e684b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51bdb1b9535685db4fc35dbdd791e6b4d9bed1b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666845"
---
# <a name="manually-process-data-ssas-tabular"></a><span data-ttu-id="d8834-102">Обработка данных вручную (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="d8834-102">Manually Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="d8834-103">В этом разделе описан процесс обработки данных рабочей области вручную в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8834-103">This topic describes how to manually process workspace data in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="d8834-104">При создании табличной модели, использующей внешние данные, данные можно обновить вручную с помощью команды «Обработать».</span><span class="sxs-lookup"><span data-stu-id="d8834-104">When you author a tabular model that uses external data, you can manually refresh the data by using the Process command.</span></span> <span data-ttu-id="d8834-105">Можно обработать одну таблицу, все таблицы, все таблицы в модели либо одну или несколько секций.</span><span class="sxs-lookup"><span data-stu-id="d8834-105">You can process a single table, all tables in the model, or one or more partitions.</span></span> <span data-ttu-id="d8834-106">Обработка данных может потребовать повторного вычисления данных.</span><span class="sxs-lookup"><span data-stu-id="d8834-106">Whenever you process data, you may also need to recalculate data.</span></span>  <span data-ttu-id="d8834-107">Обработка данных означает получение последних данных из внешних источников.</span><span class="sxs-lookup"><span data-stu-id="d8834-107">Processing data means getting the latest data from external sources.</span></span> <span data-ttu-id="d8834-108">Повторное вычисление означает обновление результатов вычисления формул на основе этих данных.</span><span class="sxs-lookup"><span data-stu-id="d8834-108">Recalculating means updating the result of any formula that uses the data.</span></span>  
  
 <span data-ttu-id="d8834-109">Разделы данной темы:</span><span class="sxs-lookup"><span data-stu-id="d8834-109">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="d8834-110">Обработка данных вручную</span><span class="sxs-lookup"><span data-stu-id="d8834-110">Manually Process Data</span></span>](#bkmk_mahually_process)  
  
-   [<span data-ttu-id="d8834-111">Ход обработки данных</span><span class="sxs-lookup"><span data-stu-id="d8834-111">Data Process Progress</span></span>](#bkmk_data_process_progress)  
  
##  <a name="manually-process-data"></a><a name="bkmk_mahually_process"></a><span data-ttu-id="d8834-112">Обработка данных вручную</span><span class="sxs-lookup"><span data-stu-id="d8834-112">Manually Process Data</span></span>  
  
#### <a name="to-process-data-for-a-single-table-or-all-tables-in-a-model"></a><span data-ttu-id="d8834-113">Обработка данных для одной таблицы или всех таблиц в модели</span><span class="sxs-lookup"><span data-stu-id="d8834-113">To process data for a single table or all tables in a model</span></span>  
  
1.  <span data-ttu-id="d8834-114">В конструкторе моделей щелкните таблицу, которую необходимо обработать.</span><span class="sxs-lookup"><span data-stu-id="d8834-114">In the model designer, click the table you want to process.</span></span>  
  
2.  <span data-ttu-id="d8834-115">Выберите в меню **Модель** пункт **Обработать**, а затем пункт **Обработать** или **Обработать все**.</span><span class="sxs-lookup"><span data-stu-id="d8834-115">Click on the **Model** menu, then click **Process**, and then click **Process** or **Process All**.</span></span>  
  
#### <a name="to-process-data-for-all-tables-using-the-same-connection"></a><span data-ttu-id="d8834-116">Обработка данных для всех таблиц, использующих одно соединение</span><span class="sxs-lookup"><span data-stu-id="d8834-116">To process data for all tables using the same connection</span></span>  
  
1.  <span data-ttu-id="d8834-117">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите в меню **Модель** пункт **Существующие соединения**.</span><span class="sxs-lookup"><span data-stu-id="d8834-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="d8834-118">В диалоговом окне **Существующие соединения** выберите соединение и нажмите **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="d8834-118">In the **Existing Connections** dialog box, select a connection, and then click **Process**.</span></span>  
  
#### <a name="to-process-data-for-one-or-more-partitions"></a><span data-ttu-id="d8834-119">Обработка данных для одного или нескольких разделов</span><span class="sxs-lookup"><span data-stu-id="d8834-119">To process data for one or more partitions</span></span>  
  
1.  <span data-ttu-id="d8834-120">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите в меню **Модель** пункт **Обработать**, а затем пункт **Обработать секции**.</span><span class="sxs-lookup"><span data-stu-id="d8834-120">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Process**, and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="d8834-121">В диалоговом окне **Обработка секций** в разделе **Режим**выберите один из следующих режимов обработки.</span><span class="sxs-lookup"><span data-stu-id="d8834-121">In the **Process Partitions** dialog box, in **Mode**, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="d8834-122">Режим</span><span class="sxs-lookup"><span data-stu-id="d8834-122">Mode</span></span>|<span data-ttu-id="d8834-123">Описание</span><span class="sxs-lookup"><span data-stu-id="d8834-123">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="d8834-124">**Обработка. По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="d8834-124">**Process Default**</span></span>|<span data-ttu-id="d8834-125">Обнаруживает состояние обработки объекта секции и выполняет обработку, необходимую для перевода необработанных или частично обработанных объектов секции в полностью обработанное состояние.</span><span class="sxs-lookup"><span data-stu-id="d8834-125">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="d8834-126">Выполняется загрузка данных для пустых таблиц и секций; иерархии, вычисляемые столбцы и связи строятся или перестраиваются.</span><span class="sxs-lookup"><span data-stu-id="d8834-126">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="d8834-127">**Обработка. Полная**</span><span class="sxs-lookup"><span data-stu-id="d8834-127">**Process Full**</span></span>|<span data-ttu-id="d8834-128">Обрабатывает объект секций и все объекты, которые в нем содержатся.</span><span class="sxs-lookup"><span data-stu-id="d8834-128">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="d8834-129">Если объект, который обрабатывается методом полной обработки, уже был обработан, службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] удаляют все данные объекта, а затем обрабатывают его.</span><span class="sxs-lookup"><span data-stu-id="d8834-129">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="d8834-130">Этот тип обработки требуется при внесении структурных изменений в объект.</span><span class="sxs-lookup"><span data-stu-id="d8834-130">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="d8834-131">**Обработка данных**</span><span class="sxs-lookup"><span data-stu-id="d8834-131">**Process Data**</span></span>|<span data-ttu-id="d8834-132">Выполняется загрузка данных в секцию или таблицу без перестроения иерархий или связей или повторного вычисления вычисленных столбцов и мер.</span><span class="sxs-lookup"><span data-stu-id="d8834-132">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="d8834-133">**Обработка с очисткой**</span><span class="sxs-lookup"><span data-stu-id="d8834-133">**Process Clear**</span></span>|<span data-ttu-id="d8834-134">Удаляет все данные из секции.</span><span class="sxs-lookup"><span data-stu-id="d8834-134">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="d8834-135">**Обработка с добавлением**</span><span class="sxs-lookup"><span data-stu-id="d8834-135">**Process Add**</span></span>|<span data-ttu-id="d8834-136">Постепенно обновляет секцию с включением новых данных.</span><span class="sxs-lookup"><span data-stu-id="d8834-136">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="d8834-137">В списке секций выберите разделы для обработки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d8834-137">In the partitions list, select the partitions you want to process, and then click **OK**.</span></span>  
  
##  <a name="data-process-progress"></a><a name="bkmk_data_process_progress"></a><span data-ttu-id="d8834-138">Ход обработки данных</span><span class="sxs-lookup"><span data-stu-id="d8834-138">Data Process Progress</span></span>  
 <span data-ttu-id="d8834-139">Диалоговое окно **Ход обработки данных** позволяет наблюдать за обработкой данных, импортированных в модель из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="d8834-139">The **Data Process Progress** dialog box enables you to monitor the processing of data that you have imported into the model from an external source.</span></span> <span data-ttu-id="d8834-140">Чтобы открыть это диалоговое окно, выберите в меню **Модель** пункт **Обработать секции**, **Обработать таблицу** или **Обработать все**.</span><span class="sxs-lookup"><span data-stu-id="d8834-140">To access this dialog box, click on the **Model** menu, and then click **Process Partitions**, **Process Table** or **Process All**.</span></span>  
  
 <span data-ttu-id="d8834-141">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="d8834-141">**Status**</span></span>  
 <span data-ttu-id="d8834-142">Сообщает об успешности операции обработки.</span><span class="sxs-lookup"><span data-stu-id="d8834-142">Indicates whether the process operation was successful or not.</span></span>  
  
 <span data-ttu-id="d8834-143">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d8834-143">**Details**</span></span>  
 <span data-ttu-id="d8834-144">Перечисляет импортированные таблицы и представления, сообщает количество импортированных строк и предоставляет ссылку на отчет о неполадках.</span><span class="sxs-lookup"><span data-stu-id="d8834-144">Lists the tables and views that were imported, the number of rows that were imported, and provides a link to a report of any issues.</span></span>  
  
 <span data-ttu-id="d8834-145">**Прервать обновление**</span><span class="sxs-lookup"><span data-stu-id="d8834-145">**Stop Refresh**</span></span>  
 <span data-ttu-id="d8834-146">Нажмите, чтобы остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="d8834-146">Click to halt the process operation.</span></span> <span data-ttu-id="d8834-147">Этот параметр может оказаться полезным в том случае, если операция развертывания занимает слишком много времени или обнаружено слишком много ошибок.</span><span class="sxs-lookup"><span data-stu-id="d8834-147">This option is useful if the operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8834-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8834-148">See Also</span></span>  
 <span data-ttu-id="d8834-149">[Обработка данных &#40;табличные&#41;SSAS](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d8834-149">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="d8834-150">Устранение неполадок обработки данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="d8834-150">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)  
  
  
