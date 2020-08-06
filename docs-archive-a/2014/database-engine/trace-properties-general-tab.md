---
title: Свойства трассировки (вкладка «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.general.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: 25227268-143b-477e-aac9-8268bcaf2078
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 30de30c88db35a41f8f118b6545d56a78b2dec79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750115"
---
# <a name="trace-properties-general-tab"></a><span data-ttu-id="b201c-102">Свойства трассировки (вкладка «Общие»)</span><span class="sxs-lookup"><span data-stu-id="b201c-102">Trace Properties (General Tab)</span></span>
  <span data-ttu-id="b201c-103">Для просмотра и задания свойств трассировки используйте вкладку **Общие** диалогового окна **Свойства трассировки** .</span><span class="sxs-lookup"><span data-stu-id="b201c-103">Use the **General** tab of the **Trace Properties** dialog box to view or specify properties of a trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b201c-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="b201c-104">Options</span></span>  
 <span data-ttu-id="b201c-105">**Имя трассировки**</span><span class="sxs-lookup"><span data-stu-id="b201c-105">**Trace name**</span></span>  
 <span data-ttu-id="b201c-106">Задает имя трассировки.</span><span class="sxs-lookup"><span data-stu-id="b201c-106">Specify the name of the trace.</span></span>  
  
 <span data-ttu-id="b201c-107">**Имя поставщика трассировки**</span><span class="sxs-lookup"><span data-stu-id="b201c-107">**Trace provider name**</span></span>  
 <span data-ttu-id="b201c-108">Показывает имя трассируемого экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b201c-108">Shows the name of the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that will be traced.</span></span> <span data-ttu-id="b201c-109">Это поле заполняется автоматически именем сервера, указанным при подключении.</span><span class="sxs-lookup"><span data-stu-id="b201c-109">This field is populated automatically with the name of the server that you specified when you connected.</span></span> <span data-ttu-id="b201c-110">Для изменения имени поставщика трассировки щелкните **Отмена** , чтобы закрыть диалоговое окно, и запустите новую трассировку.</span><span class="sxs-lookup"><span data-stu-id="b201c-110">To change the name of the trace provider, click **Cancel** to close the dialog box, and start a new trace.</span></span>  
  
 <span data-ttu-id="b201c-111">**Тип поставщика трассировки**</span><span class="sxs-lookup"><span data-stu-id="b201c-111">**Trace provider type**</span></span>  
 <span data-ttu-id="b201c-112">Показывает тип сервера, предоставляющего трассировку.</span><span class="sxs-lookup"><span data-stu-id="b201c-112">Shows the server type that is providing the trace.</span></span> <span data-ttu-id="b201c-113">Файл определения трассировки заполняет поле **Тип поставщика трассировки** автоматически.</span><span class="sxs-lookup"><span data-stu-id="b201c-113">The trace definition file populates the **Trace provider type** field automatically.</span></span> <span data-ttu-id="b201c-114">Это поле нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="b201c-114">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="b201c-115">**version**</span><span class="sxs-lookup"><span data-stu-id="b201c-115">**version**</span></span>  
 <span data-ttu-id="b201c-116">Показывает версию сервера, предоставляющего трассировку.</span><span class="sxs-lookup"><span data-stu-id="b201c-116">Shows the version of the server that is providing the trace.</span></span> <span data-ttu-id="b201c-117">Файл определения трассировки заполняет поле **Версия** автоматически.</span><span class="sxs-lookup"><span data-stu-id="b201c-117">The trace definition file populates the **Version** field automatically.</span></span> <span data-ttu-id="b201c-118">Это поле нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="b201c-118">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="b201c-119">**Использовать шаблон**</span><span class="sxs-lookup"><span data-stu-id="b201c-119">**Use the template**</span></span>  
 <span data-ttu-id="b201c-120">Выбирает шаблон из каталога шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b201c-120">Select a template from the template directory.</span></span> <span data-ttu-id="b201c-121">В каталоге содержатся шаблоны по умолчанию и пользовательские шаблоны, созданные для текущего типа поставщика трассировки.</span><span class="sxs-lookup"><span data-stu-id="b201c-121">The directory is populated with the default templates and any user-defined templates created for the current trace provider type.</span></span>  
  
 <span data-ttu-id="b201c-122">**Сохранить в файл**</span><span class="sxs-lookup"><span data-stu-id="b201c-122">**Save to file**</span></span>  
 <span data-ttu-id="b201c-123">Собирает данные трассировки в файл с расширением TRC.</span><span class="sxs-lookup"><span data-stu-id="b201c-123">Capture the trace data to a .trc file.</span></span> <span data-ttu-id="b201c-124">Сохранение данных трассировки полезно для их просмотра и анализа в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="b201c-124">Saving trace data is useful for later review and analysis.</span></span>  
  
 <span data-ttu-id="b201c-125">**Установить максимальный размер файла (МБ)**</span><span class="sxs-lookup"><span data-stu-id="b201c-125">**Set maximum file size (MB)**</span></span>  
 <span data-ttu-id="b201c-126">Если выбран параметр сохранения данных трассировки в файл, необходимо задать максимальный размер этого файла.</span><span class="sxs-lookup"><span data-stu-id="b201c-126">If you choose to save the trace data to a file, you must specify the maximum size of the trace file.</span></span> <span data-ttu-id="b201c-127">По умолчанию он составляет 5 мегабайт (МБ).</span><span class="sxs-lookup"><span data-stu-id="b201c-127">The default is 5 megabytes (MB).</span></span> <span data-ttu-id="b201c-128">Максимальный размер ограничен только файловой системой (NTFS, FAT), в которой сохраняется файл.</span><span class="sxs-lookup"><span data-stu-id="b201c-128">The maximum size is limited only by the file system (NTFS, FAT) where the file is saved.</span></span>  
  
 <span data-ttu-id="b201c-129">\<Graphic>**Сохранить как**</span><span class="sxs-lookup"><span data-stu-id="b201c-129">\<Graphic> **Save As**</span></span>  
 <span data-ttu-id="b201c-130">После выбора сохранения файла этим значком можно изменить его имя.</span><span class="sxs-lookup"><span data-stu-id="b201c-130">After you have selected to save, you can select this icon to change the file name.</span></span>  
  
 <span data-ttu-id="b201c-131">**Включить операцию переключения на файл продолжения**</span><span class="sxs-lookup"><span data-stu-id="b201c-131">**Enable file rollover**</span></span>  
 <span data-ttu-id="b201c-132">Разрешает создавать дополнительные файлы для данных трассировки, когда достигнут максимальный размер файла.</span><span class="sxs-lookup"><span data-stu-id="b201c-132">Select to enable the creation of additional files to accept the trace data when the maximum file size is reached.</span></span> <span data-ttu-id="b201c-133">Имя нового файла состоит из имени исходного TRC-файла с добавлением последовательного номера.</span><span class="sxs-lookup"><span data-stu-id="b201c-133">Each new file name consists of the original .trc file name, numbered sequentially.</span></span> <span data-ttu-id="b201c-134">Например, если превышен максимальный размер, закрывается файл **NewTrace.trc** и открывается новый файл **NewTrace_1.trc**, затем **NewTrace_2.trc**и т. д.</span><span class="sxs-lookup"><span data-stu-id="b201c-134">For example, once it reaches maximum file size, **NewTrace.trc** closes, and a new file, **NewTrace_1.trc**, opens, followed by **NewTrace_2.trc**, and so on.</span></span> <span data-ttu-id="b201c-135">Операция переключения на файл продолжения по умолчанию включена при сохранении трассировки в файл.</span><span class="sxs-lookup"><span data-stu-id="b201c-135">File rollover is enabled by default when you save a trace to a file.</span></span>  
  
 <span data-ttu-id="b201c-136">**Сервер обрабатывает данные трассировки**</span><span class="sxs-lookup"><span data-stu-id="b201c-136">**Server processes trace data**</span></span>  
 <span data-ttu-id="b201c-137">Указывает, чтобы сервер, на котором выполняется трассировка, обрабатывал ее данные.</span><span class="sxs-lookup"><span data-stu-id="b201c-137">Specify that the server running the trace should process the trace data.</span></span> <span data-ttu-id="b201c-138">При использовании этого параметра уменьшается потеря производительности, обусловленная трассировкой.</span><span class="sxs-lookup"><span data-stu-id="b201c-138">Using this option reduces the performance overhead incurred by tracing.</span></span> <span data-ttu-id="b201c-139">Если этот флажок установлен, не пропускаются никакие события даже в случае нештатной ситуации.</span><span class="sxs-lookup"><span data-stu-id="b201c-139">If selected, no events are skipped even under stress conditions.</span></span> <span data-ttu-id="b201c-140">Если он снят, обработка выполняется приложением SQL Server Profiler; при этом существует вероятность, что некоторые события не будут трассироваться в случае нештатной ситуации.</span><span class="sxs-lookup"><span data-stu-id="b201c-140">If this check box is cleared, processing is performed by SQL Server Profiler, and there is a possibility that some events are not traced under stress conditions.</span></span>  
  
 <span data-ttu-id="b201c-141">**Сохранить в таблицу**</span><span class="sxs-lookup"><span data-stu-id="b201c-141">**Save to table**</span></span>  
 <span data-ttu-id="b201c-142">Собирает данные трассировки в таблицу базы данных.</span><span class="sxs-lookup"><span data-stu-id="b201c-142">Capture the trace data to a database table.</span></span> <span data-ttu-id="b201c-143">Сохранение данных трассировки полезно для их просмотра и анализа в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="b201c-143">Saving trace data is useful for later review and analysis.</span></span> <span data-ttu-id="b201c-144">Однако сохранение этих данных в таблицу может привести к серьезным потерям производительности на сервере, куда записывается трассировка.</span><span class="sxs-lookup"><span data-stu-id="b201c-144">However, saving trace data to a table can incur significant overhead on the server where the trace is being saved.</span></span> <span data-ttu-id="b201c-145">По возможности не храните таблицу трассировки на трассируемом сервере.</span><span class="sxs-lookup"><span data-stu-id="b201c-145">If possible, do not save the trace table on the same server that is being traced.</span></span>  
  
 <span data-ttu-id="b201c-146">\<Graphic>**Целевая таблица**</span><span class="sxs-lookup"><span data-stu-id="b201c-146">\<Graphic> **Destination Table**</span></span>  
 <span data-ttu-id="b201c-147">После выбора сохранения данных трассировки в таблицу базы данных этим значком можно изменять ее имя.</span><span class="sxs-lookup"><span data-stu-id="b201c-147">After you have selected to save the trace data to a database table, you can select this icon to change the table name.</span></span>  
  
 <span data-ttu-id="b201c-148">**Максимальное число строк (тыс.)**</span><span class="sxs-lookup"><span data-stu-id="b201c-148">**Set maximum rows (in thousands)**</span></span>  
 <span data-ttu-id="b201c-149">Задает максимальное количество строк, в которое можно сохранять данные.</span><span class="sxs-lookup"><span data-stu-id="b201c-149">Specify the largest number of rows in which to save data.</span></span> <span data-ttu-id="b201c-150">Значение по умолчанию составляет 1000 строк.</span><span class="sxs-lookup"><span data-stu-id="b201c-150">The default is 1000 rows.</span></span>  
  
 <span data-ttu-id="b201c-151">**Включить время остановки трассировки**</span><span class="sxs-lookup"><span data-stu-id="b201c-151">**Enable trace stop time**</span></span>  
 <span data-ttu-id="b201c-152">Задает дату и время завершения и закрытия трассировки.</span><span class="sxs-lookup"><span data-stu-id="b201c-152">Set the date and time for the trace to end and close itself.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b201c-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="b201c-153">See Also</span></span>  
 [<span data-ttu-id="b201c-154">Создание трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="b201c-154">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
