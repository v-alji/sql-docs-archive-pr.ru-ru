---
title: Свойства журнала | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- QueryLogFileSize property
- QueryLogTableName property
- TraceBackgroundDistributionPeriod property
- TraceMaxRowsetSize property
- NullKeyConvertedToUnknown property
- CrashReportsFolder property
- TraceDefinitionFile property
- SQLDumperFlagsOn property
- KeyErrorLimit property
- SnapshotDefinitionFile property
- MinidumpErrorList property
- ErrorLogFileName property
- KeyDuplicate property
- IgnoreDataTruncation property
- logs [Analysis Services]
- Enabled property
- FileSizeMB property
- TraceFileWriteTrailerPeriod property
- TraceQueryResponseTextChunkSize property
- File property
- FileBufferSize property
- TraceRowsetBackgroundFlushPeriod property
- ErrorLogFileSize property
- TraceRequestParameters property
- KeyErrorLimitAction property
- CreateQueryLogTable property
- LogDir property
- TraceBackgroundFlushPeriod property
- TraceFileBufferSize property
- SQLDumperFlagsOff property
- QueryLogConnectionString property
- KeyNotFound property
- KeyErrorLogFile property
- TraceReportFQDN property
- KeyErrorAction property
- QueryLogFileName property
- MessageLogs property
- MiniDumpFlagsOn property
- SnapshotFrequencySec property
- QueryLogSampling property
- CreateAndSendCrashReports property
- LogDurationSec property
ms.assetid: 33fd90ee-cead-48f0-8ff9-9b458994c766
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3761ce3dca232db8968a2a7cba083dcc5554d792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752384"
---
# <a name="log-properties"></a><span data-ttu-id="1ca45-102">Свойства журнала</span><span class="sxs-lookup"><span data-stu-id="1ca45-102">Log Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="1ca45-103">поддерживают свойства сервера журналов, список которых приведен в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="1ca45-103">supports the log server properties listed in the following tables.</span></span> <span data-ttu-id="1ca45-104">Дополнительные сведения о дополнительных свойствах сервера и об их настройке см. в разделе [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ca45-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
## <a name="general"></a><span data-ttu-id="1ca45-105">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="1ca45-105">General</span></span>  
 `File`  
 <span data-ttu-id="1ca45-106">Строковое свойство, идентифицирующее имя файла журнала сервера.</span><span class="sxs-lookup"><span data-stu-id="1ca45-106">A string property that identifies the name of the server log file.</span></span> <span data-ttu-id="1ca45-107">Данное свойство применяется только в том случае, когда для ведения журнала используется дисковый файл, а не таблица базы данных (настройка по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1ca45-107">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="1ca45-108">Значение этого свойства по умолчанию равно msmdsrv.log.</span><span class="sxs-lookup"><span data-stu-id="1ca45-108">The default value for this property is msmdsrv.log.</span></span>  
  
 `FileBufferSize`  
 <span data-ttu-id="1ca45-109">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MessageLogs`  
 <span data-ttu-id="1ca45-110">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="error-log"></a><span data-ttu-id="1ca45-111">Журнал ошибок</span><span class="sxs-lookup"><span data-stu-id="1ca45-111">Error Log</span></span>  
 <span data-ttu-id="1ca45-112">Эти свойства можно задать на уровне экземпляра сервера, чтобы изменить значения по умолчанию для конфигурации обработки ошибок, которые применяются в других средствах и конструкторах.</span><span class="sxs-lookup"><span data-stu-id="1ca45-112">You can set these properties at the server instance level to modify the default values for Error Configuration that appear in other tools and designers.</span></span> <span data-ttu-id="1ca45-113">См. [раздел Конфигурация ошибок для обработки кубов, секций и измерений &#40;SSAS — многомерные&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) и дополнительные <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> сведения.</span><span class="sxs-lookup"><span data-stu-id="1ca45-113">See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) and <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> for more information.</span></span>  
  
 <span data-ttu-id="1ca45-114">**ErrorLog\ErrorLogFileName**</span><span class="sxs-lookup"><span data-stu-id="1ca45-114">**ErrorLog\ErrorLogFileName**</span></span>  
 <span data-ttu-id="1ca45-115">Свойство, используемое в качестве значения по умолчанию во время выполнения операции обработки сервером.</span><span class="sxs-lookup"><span data-stu-id="1ca45-115">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="1ca45-116">**ErrorLog\ErrorLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="1ca45-116">**ErrorLog\ErrorLogFileSize**</span></span>  
 <span data-ttu-id="1ca45-117">Свойство, используемое в качестве значения по умолчанию во время выполнения операции обработки сервером.</span><span class="sxs-lookup"><span data-stu-id="1ca45-117">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="1ca45-118">**ErrorLog\KeyErrorAction**</span><span class="sxs-lookup"><span data-stu-id="1ca45-118">**ErrorLog\KeyErrorAction**</span></span>  
 <span data-ttu-id="1ca45-119">Задает действие, которое выполняет сервер при возникновении ошибки `KeyNotFound`.</span><span class="sxs-lookup"><span data-stu-id="1ca45-119">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="1ca45-120">Допустимые действия для этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="1ca45-120">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="1ca45-121">`ConvertToUnknown` указывает, что сервер должен выделить ключевое значение ошибки неизвестному элементу.</span><span class="sxs-lookup"><span data-stu-id="1ca45-121">`ConvertToUnknown` tells the server to allocate the error key value to the unknown member.</span></span>  
  
-   <span data-ttu-id="1ca45-122">`DiscardRecord` указывает, что сервер должен исключить запись.</span><span class="sxs-lookup"><span data-stu-id="1ca45-122">`DiscardRecord` tells the server to exclude the record.</span></span>  
  
 <span data-ttu-id="1ca45-123">**ErrorLog\KeyErrorLogFile**</span><span class="sxs-lookup"><span data-stu-id="1ca45-123">**ErrorLog\KeyErrorLogFile**</span></span>  
 <span data-ttu-id="1ca45-124">Это определяемое пользователем имя файла должно иметь расширение LOG и находиться в папке, для которой учетная запись службы имеет разрешения на чтение и запись.</span><span class="sxs-lookup"><span data-stu-id="1ca45-124">This is a user-defined filename that must have a .log file extension, located in a folder on which the service account has read-write permissions.</span></span> <span data-ttu-id="1ca45-125">Файл журнала будет содержать только ошибки, возникшие во время обработки.</span><span class="sxs-lookup"><span data-stu-id="1ca45-125">This log file will only contain errors generated during processing.</span></span> <span data-ttu-id="1ca45-126">Для сбора более подробной информации воспользуйтесь средством «черный ящик».</span><span class="sxs-lookup"><span data-stu-id="1ca45-126">Use the Flight Recorder if you require more detailed information.</span></span>  
  
 <span data-ttu-id="1ca45-127">**ErrorLog\KeyErrorLimit**</span><span class="sxs-lookup"><span data-stu-id="1ca45-127">**ErrorLog\KeyErrorLimit**</span></span>  
 <span data-ttu-id="1ca45-128">Максимальное число ошибок целостности данных, допустимых для сервера, прежде чем он остановит обработку.</span><span class="sxs-lookup"><span data-stu-id="1ca45-128">This is the maximum number of data integrity errors that the server will allow before failing the processing.</span></span> <span data-ttu-id="1ca45-129">Значение -1 указывает, что предел не установлен.</span><span class="sxs-lookup"><span data-stu-id="1ca45-129">A value of -1 indicates that there is no limit.</span></span> <span data-ttu-id="1ca45-130">Значение по умолчанию — 0, т. е. обработка останавливается при первой ошибке.</span><span class="sxs-lookup"><span data-stu-id="1ca45-130">The default is 0, which means processing stops after the first error occurs.</span></span> <span data-ttu-id="1ca45-131">Также можно задать целое число.</span><span class="sxs-lookup"><span data-stu-id="1ca45-131">You can also set it to a whole number.</span></span>  
  
 <span data-ttu-id="1ca45-132">**ErrorLog\KeyErrorLimitAction**</span><span class="sxs-lookup"><span data-stu-id="1ca45-132">**ErrorLog\KeyErrorLimitAction**</span></span>  
 <span data-ttu-id="1ca45-133">Определяет действие, которое выполняет сервер, когда количество ошибок ключа достигает верхней границы.</span><span class="sxs-lookup"><span data-stu-id="1ca45-133">Specifies the action taken by the server when the number of key errors has reached the upper limit.</span></span> <span data-ttu-id="1ca45-134">Допустимые ответы к данному действию:</span><span class="sxs-lookup"><span data-stu-id="1ca45-134">Valid responses to this action include:</span></span>  
  
-   <span data-ttu-id="1ca45-135">`StopProcessing` предписывает серверу остановить обработку при достижении предельного количества ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ca45-135">`StopProcessing` tells the server to stop processing when the error limit is reached.</span></span>  
  
-   <span data-ttu-id="1ca45-136">`StopLogging` предписывает серверу остановить регистрацию ошибок при достижении предельного количества ошибок, но продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="1ca45-136">`StopLogging` tells the server to stop logging errors when the error limit is reached, but allow processing to continue.</span></span>  
  
 <span data-ttu-id="1ca45-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span><span class="sxs-lookup"><span data-stu-id="1ca45-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span></span>  
 <span data-ttu-id="1ca45-138">Задает действие, которое выполняет сервер при возникновении ошибки `KeyNotFound`.</span><span class="sxs-lookup"><span data-stu-id="1ca45-138">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="1ca45-139">Допустимые действия для этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="1ca45-139">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="1ca45-140">`IgnoreError` указывает, что сервер должен продолжить обработку, не записывая ошибку в журнал и не учитывая ее при подсчете предельного количества ошибок ключа.</span><span class="sxs-lookup"><span data-stu-id="1ca45-140">`IgnoreError` tells the server to continue processing without logging the error or counting it towards the key error limit.</span></span> <span data-ttu-id="1ca45-141">Пропуск данной ошибки просто разрешает продолжение обработки без увеличения количества ошибок и вывода ошибки на экран или в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="1ca45-141">By ignoring the error, you simply allow processing to continue without adding to the error count or logging it to the screen or log file.</span></span> <span data-ttu-id="1ca45-142">Рассматриваемая запись имеет нарушение целостности данных и не может быть добавлена в базу данных.</span><span class="sxs-lookup"><span data-stu-id="1ca45-142">The record in question has a data integrity problem and cannot be added to the database.</span></span> <span data-ttu-id="1ca45-143">Запись или будет пропущена, или будет добавлена в неизвестный элемент, что определяется свойством `KeyErrorAction`.</span><span class="sxs-lookup"><span data-stu-id="1ca45-143">The record will either be discarded or aggregated to Unknown Member, as determined by the `KeyErrorAction` property.</span></span>  
  
-   <span data-ttu-id="1ca45-144">`ReportAndContinue` предписывает серверу зарегистрировать ошибку в журнале, учесть ее при подсчете предельного количества ошибок ключа и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="1ca45-144">`ReportAndContinue` tells the server to log the error, count it towards the key error limit, and continue processing.</span></span> <span data-ttu-id="1ca45-145">Запись, вызвавшая ошибку, пропускается или преобразуется в неизвестный элемент.</span><span class="sxs-lookup"><span data-stu-id="1ca45-145">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
-   <span data-ttu-id="1ca45-146">`ReportAndStop` предписывает серверу немедленно прервать обработку и зарегистрировать ошибку в журнале вне зависимости от предельного количества ошибок ключа.</span><span class="sxs-lookup"><span data-stu-id="1ca45-146">`ReportAndStop` tells the server to log the error and stop processing immediately, regardless of the key error limit.</span></span> <span data-ttu-id="1ca45-147">Запись, вызвавшая ошибку, пропускается или преобразуется в неизвестный элемент.</span><span class="sxs-lookup"><span data-stu-id="1ca45-147">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
 <span data-ttu-id="1ca45-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span><span class="sxs-lookup"><span data-stu-id="1ca45-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span></span>  
 <span data-ttu-id="1ca45-149">Определяет действие, выполняемое сервером при обнаружении повторяющегося ключа.</span><span class="sxs-lookup"><span data-stu-id="1ca45-149">Specifies the action taken by the server when a duplicate key is found.</span></span> <span data-ttu-id="1ca45-150">Допустимые значения: `IgnoreError`, чтобы продолжить обработку, как будто ошибки не было, `ReportAndContinue` для регистрации ошибки и продолжения обработки и `ReportAndStop` для регистрации ошибки и немедленного прерывания обработки, даже если количество ошибок ниже предельного количества ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ca45-150">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="1ca45-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span><span class="sxs-lookup"><span data-stu-id="1ca45-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span></span>  
 <span data-ttu-id="1ca45-152">Указывает действие, выполняемое сервером, когда ключ NULL преобразован в неизвестный элемент.</span><span class="sxs-lookup"><span data-stu-id="1ca45-152">Specifies the action taken by the server when a null key has been converted to Unknown Member.</span></span> <span data-ttu-id="1ca45-153">Допустимые значения: `IgnoreError`, чтобы продолжить обработку, как будто ошибки не было, `ReportAndContinue` для регистрации ошибки и продолжения обработки и `ReportAndStop` для регистрации ошибки и немедленного прерывания обработки, даже если количество ошибок ниже предельного количества ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ca45-153">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="1ca45-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span><span class="sxs-lookup"><span data-stu-id="1ca45-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span></span>  
 <span data-ttu-id="1ca45-155">Указывает действие, выполняемое сервером, когда для `NullProcessing` задается значение `Error` (в атрибуте измерения).</span><span class="sxs-lookup"><span data-stu-id="1ca45-155">Specifies the action taken by the server when `NullProcessing` is set to `Error` for a dimension attribute.</span></span> <span data-ttu-id="1ca45-156">Если значение NULL недопустимо для данного атрибута, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="1ca45-156">An error is generated when a null value is not allowed in a given attribute.</span></span> <span data-ttu-id="1ca45-157">Это свойство конфигурации по обработке ошибок формирует следующий шаг — сообщить об ошибке и продолжить обработку до тех пор, пока не будет достигнуто предельное количество ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ca45-157">This error configuration property informs the next step, which is to report the error and continue processing until the error limit is reached.</span></span> <span data-ttu-id="1ca45-158">Допустимые значения: `IgnoreError`, чтобы продолжить обработку, как будто ошибки не было, `ReportAndContinue` для регистрации ошибки и продолжения обработки и `ReportAndStop` для регистрации ошибки и немедленного прерывания обработки, даже если количество ошибок ниже предельного количества ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ca45-158">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="1ca45-159">**ErrorLog\ LogErrorTypes\CalculationError**</span><span class="sxs-lookup"><span data-stu-id="1ca45-159">**ErrorLog\ LogErrorTypes\CalculationError**</span></span>  
 <span data-ttu-id="1ca45-160">Свойство, используемое в качестве значения по умолчанию во время выполнения операции обработки сервером.</span><span class="sxs-lookup"><span data-stu-id="1ca45-160">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="1ca45-161">**ErrorLog\IgnoreDataTruncation**</span><span class="sxs-lookup"><span data-stu-id="1ca45-161">**ErrorLog\IgnoreDataTruncation**</span></span>  
 <span data-ttu-id="1ca45-162">Свойство, используемое в качестве значения по умолчанию во время выполнения операции обработки сервером.</span><span class="sxs-lookup"><span data-stu-id="1ca45-162">A property used as a default during processing operation performed by the server.</span></span>  
  
## <a name="exception"></a><span data-ttu-id="1ca45-163">Исключение</span><span class="sxs-lookup"><span data-stu-id="1ca45-163">Exception</span></span>  
 <span data-ttu-id="1ca45-164">**Exception\CreateAndSendCrashReports**</span><span class="sxs-lookup"><span data-stu-id="1ca45-164">**Exception\CreateAndSendCrashReports**</span></span>  
 <span data-ttu-id="1ca45-165">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-165">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-166">**Exception\CrashReportsFolder**</span><span class="sxs-lookup"><span data-stu-id="1ca45-166">**Exception\CrashReportsFolder**</span></span>  
 <span data-ttu-id="1ca45-167">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-167">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-168">**Exception\SQLDumperFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="1ca45-168">**Exception\SQLDumperFlagsOn**</span></span>  
 <span data-ttu-id="1ca45-169">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-170">**Exception\SQLDumperFlagsOff**</span><span class="sxs-lookup"><span data-stu-id="1ca45-170">**Exception\SQLDumperFlagsOff**</span></span>  
 <span data-ttu-id="1ca45-171">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-172">**Exception\MiniDumpFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="1ca45-172">**Exception\MiniDumpFlagsOn**</span></span>  
 <span data-ttu-id="1ca45-173">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-173">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-174">**Exception\MinidumpErrorList**</span><span class="sxs-lookup"><span data-stu-id="1ca45-174">**Exception\MinidumpErrorList**</span></span>  
 <span data-ttu-id="1ca45-175">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-175">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="flight-recorder"></a><span data-ttu-id="1ca45-176">«Черный ящик»</span><span class="sxs-lookup"><span data-stu-id="1ca45-176">Flight Recorder</span></span>  
 <span data-ttu-id="1ca45-177">**FlightRecorder\Enabled**</span><span class="sxs-lookup"><span data-stu-id="1ca45-177">**FlightRecorder\Enabled**</span></span>  
 <span data-ttu-id="1ca45-178">Логическое свойство, указывающее, используется ли функция «черного ящика».</span><span class="sxs-lookup"><span data-stu-id="1ca45-178">A Boolean property that indicates whether the flight recorder feature is enabled.</span></span>  
  
 <span data-ttu-id="1ca45-179">**FlightRecorder\FileSizeMB**</span><span class="sxs-lookup"><span data-stu-id="1ca45-179">**FlightRecorder\FileSizeMB**</span></span>  
 <span data-ttu-id="1ca45-180">Свойство с 32-разрядным целочисленным значением со знаком, определяющее размер (в мегабайтах) дискового файла «черного ящика».</span><span class="sxs-lookup"><span data-stu-id="1ca45-180">A signed 32-bit integer property that defines the size of the flight recorder disk file, in megabytes.</span></span>  
  
 <span data-ttu-id="1ca45-181">**FlightRecorder\LogDurationSec**</span><span class="sxs-lookup"><span data-stu-id="1ca45-181">**FlightRecorder\LogDurationSec**</span></span>  
 <span data-ttu-id="1ca45-182">Свойство с 32-разрядным целочисленным значением со знаком, определяющее частоту (в секундах), с которой «черный ящик» переключается на файл продолжения.</span><span class="sxs-lookup"><span data-stu-id="1ca45-182">A signed 32-bit integer property that defines the frequency that the flight recorder is rolled over, in seconds.</span></span>  
  
 <span data-ttu-id="1ca45-183">**FlightRecorder\SnapshotDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="1ca45-183">**FlightRecorder\SnapshotDefinitionFile**</span></span>  
 <span data-ttu-id="1ca45-184">Строковое свойство, определяющее имя файла определения моментального снимка, содержащего команды обнаружения, выдаваемые серверу при создании моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="1ca45-184">A string property that defines the name of the snapshot definition file, containing discover commands that are issued to the server when a snapshot is taken.</span></span>  
  
 <span data-ttu-id="1ca45-185">Значением по умолчанию для этого свойства является пустая строка, что соответствует имени файла FlightRecorderSnapshotDef.xml.</span><span class="sxs-lookup"><span data-stu-id="1ca45-185">The default value for this property is blank, which in turn defaults to file name FlightRecorderSnapshotDef.xml.</span></span>  
  
 <span data-ttu-id="1ca45-186">**FlightRecorder\SnapshotFrequencySec**</span><span class="sxs-lookup"><span data-stu-id="1ca45-186">**FlightRecorder\SnapshotFrequencySec**</span></span>  
 <span data-ttu-id="1ca45-187">Свойство с 32-разрядным целочисленным значением со знаком, определяющее частоту (в секундах) моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="1ca45-187">A signed 32-bit integer property that defines the snapshot frequency, in seconds.</span></span>  
  
 <span data-ttu-id="1ca45-188">**FlightRecorder\TraceDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="1ca45-188">**FlightRecorder\TraceDefinitionFile**</span></span>  
 <span data-ttu-id="1ca45-189">Строковое свойство, задающее имя файла определения трассировки «черного ящика».</span><span class="sxs-lookup"><span data-stu-id="1ca45-189">A string property that specifies the name of the flight recorder trace definition file.</span></span>  
  
 <span data-ttu-id="1ca45-190">Значением по умолчанию для этого свойства является пустая строка, что по умолчанию соответствует файлу FlightRecorderTraceDef.xml.</span><span class="sxs-lookup"><span data-stu-id="1ca45-190">The default value for this property is blank, which in turn defaults to FlightRecorderTraceDef.xml.</span></span>  
  
## <a name="query-log"></a><span data-ttu-id="1ca45-191">Журнал запросов</span><span class="sxs-lookup"><span data-stu-id="1ca45-191">Query Log</span></span>  
 <span data-ttu-id="1ca45-192">**Применимо к:** Только в многомерном режиме сервера</span><span class="sxs-lookup"><span data-stu-id="1ca45-192">**Applies to:** Multidimensional server mode only</span></span>  
  
 <span data-ttu-id="1ca45-193">**QueryLog\QueryLogFileName**</span><span class="sxs-lookup"><span data-stu-id="1ca45-193">**QueryLog\QueryLogFileName**</span></span>  
 <span data-ttu-id="1ca45-194">Строковое свойство, задающее имя файла журнала запросов.</span><span class="sxs-lookup"><span data-stu-id="1ca45-194">A string property that specifies the name of the query log file.</span></span> <span data-ttu-id="1ca45-195">Данное свойство применяется только в том случае, когда для ведения журнала используется дисковый файл, а не таблица базы данных (настройка по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1ca45-195">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="1ca45-196">**QueryLog\QueryLogSampling**</span><span class="sxs-lookup"><span data-stu-id="1ca45-196">**QueryLog\QueryLogSampling**</span></span>  
 <span data-ttu-id="1ca45-197">Свойство с 32-разрядным целочисленным значением со знаком, задающее частоту выборки журнала запросов.</span><span class="sxs-lookup"><span data-stu-id="1ca45-197">A signed 32-bit integer property that specifies the query log sampling rate.</span></span>  
  
 <span data-ttu-id="1ca45-198">Значение этого свойства по умолчанию равно 10, что означает, что в журнал заносится 1 из каждых 10 серверных запросов.</span><span class="sxs-lookup"><span data-stu-id="1ca45-198">The default value for this property is 10, meaning that 1 out of every 10 server queries is logged.</span></span>  
  
 <span data-ttu-id="1ca45-199">**QueryLog\QueryLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="1ca45-199">**QueryLog\QueryLogFileSize**</span></span>  
 <span data-ttu-id="1ca45-200">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-200">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-201">**QueryLog\QueryLogConnectionString**</span><span class="sxs-lookup"><span data-stu-id="1ca45-201">**QueryLog\QueryLogConnectionString**</span></span>  
 <span data-ttu-id="1ca45-202">Строковое свойство, задающее соединение с базой данных журнала запросов.</span><span class="sxs-lookup"><span data-stu-id="1ca45-202">A string property that specifies the connection to the query log database.</span></span>  
  
 <span data-ttu-id="1ca45-203">**QueryLog\QueryLogTableName**</span><span class="sxs-lookup"><span data-stu-id="1ca45-203">**QueryLog\QueryLogTableName**</span></span>  
 <span data-ttu-id="1ca45-204">Строковое свойство, задающее имя таблицы журнала запросов.</span><span class="sxs-lookup"><span data-stu-id="1ca45-204">A string property that specifies the name of the query log table.</span></span>  
  
 <span data-ttu-id="1ca45-205">Значение этого свойства по умолчанию равно OlapQueryLog.</span><span class="sxs-lookup"><span data-stu-id="1ca45-205">The default value for this property is OlapQueryLog.</span></span>  
  
 <span data-ttu-id="1ca45-206">**QueryLog\CreateQueryLogTable**</span><span class="sxs-lookup"><span data-stu-id="1ca45-206">**QueryLog\CreateQueryLogTable**</span></span>  
 <span data-ttu-id="1ca45-207">Логическое свойство, задающее необходимость создания таблицы журнала запросов.</span><span class="sxs-lookup"><span data-stu-id="1ca45-207">A Boolean property that specifies whether to create the query log table.</span></span>  
  
 <span data-ttu-id="1ca45-208">Значение этого свойства по умолчанию равно false, что указывает на то, что сервер не будет автоматически создавать таблицу журнала и не будет записывать в журнал события запросов.</span><span class="sxs-lookup"><span data-stu-id="1ca45-208">The default value for this property is false, which indicates the server will not automatically create the log table and will not log query events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ca45-209">Дополнительные сведения о настройке журнала запросов см. в разделе [операции с журналом в Analysis Services](../instances/log-operations-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ca45-209">For more information about configuring the query log, see [Log operations in Analysis Services](../instances/log-operations-in-analysis-services.md).</span></span>  
  
## <a name="trace"></a><span data-ttu-id="1ca45-210">Трассировка</span><span class="sxs-lookup"><span data-stu-id="1ca45-210">Trace</span></span>  
 <span data-ttu-id="1ca45-211">**Trace\TraceBackgroundDistributionPeriod**</span><span class="sxs-lookup"><span data-stu-id="1ca45-211">**Trace\TraceBackgroundDistributionPeriod**</span></span>  
 <span data-ttu-id="1ca45-212">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-212">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-213">**Trace\TraceBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="1ca45-213">**Trace\TraceBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="1ca45-214">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-215">**Trace\TraceFileBufferSize**</span><span class="sxs-lookup"><span data-stu-id="1ca45-215">**Trace\TraceFileBufferSize**</span></span>  
 <span data-ttu-id="1ca45-216">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-216">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-217">**Trace\TraceFileWriteTrailerPeriod**</span><span class="sxs-lookup"><span data-stu-id="1ca45-217">**Trace\TraceFileWriteTrailerPeriod**</span></span>  
 <span data-ttu-id="1ca45-218">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-219">**Trace\TraceMaxRowsetSize**</span><span class="sxs-lookup"><span data-stu-id="1ca45-219">**Trace\TraceMaxRowsetSize**</span></span>  
 <span data-ttu-id="1ca45-220">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-221">**Trace\TraceProtocolTraffic**</span><span class="sxs-lookup"><span data-stu-id="1ca45-221">**Trace\TraceProtocolTraffic**</span></span>  
 <span data-ttu-id="1ca45-222">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-222">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-223">**Trace\TraceQueryResponseTextChunkSize**</span><span class="sxs-lookup"><span data-stu-id="1ca45-223">**Trace\TraceQueryResponseTextChunkSize**</span></span>  
 <span data-ttu-id="1ca45-224">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-225">**Trace\TraceReportFQDN**</span><span class="sxs-lookup"><span data-stu-id="1ca45-225">**Trace\TraceReportFQDN**</span></span>  
 <span data-ttu-id="1ca45-226">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-226">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-227">**Trace\TraceRequestParameters**</span><span class="sxs-lookup"><span data-stu-id="1ca45-227">**Trace\TraceRequestParameters**</span></span>  
 <span data-ttu-id="1ca45-228">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1ca45-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="1ca45-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="1ca45-230">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca45-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ca45-231">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ca45-231">See Also</span></span>  
 <span data-ttu-id="1ca45-232">[Настройка свойств сервера в Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="1ca45-232">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="1ca45-233">Определение режима работы сервера экземпляра служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1ca45-233">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
