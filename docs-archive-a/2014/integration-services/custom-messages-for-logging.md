---
title: Пользовательские сообщения для ведения журнала | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], custom
- writing log entries
- SSIS packages, logs
- custom messages for logging [Integration Services]
ms.assetid: 3c74bba9-02b7-4bf5-bad5-19278b680730
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b9f450c74ef6d46876adfde45729c71b3262449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664429"
---
# <a name="custom-messages-for-logging"></a><span data-ttu-id="4569e-102">Пользовательские сообщения для ведения журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-102">Custom Messages for Logging</span></span>
  <span data-ttu-id="4569e-103">Службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] предусматривают большой набор пользовательских событий, предполагающих добавление записей в журнал для пакетов и многих задач.</span><span class="sxs-lookup"><span data-stu-id="4569e-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides a rich set of custom events for writing log entries for packages and many tasks.</span></span> <span data-ttu-id="4569e-104">Записывая стандартные события или определенные пользователем сообщения с целью последующего анализа, можно сохранить подробные сведения о процессе выполнения, результатах и проблемах.</span><span class="sxs-lookup"><span data-stu-id="4569e-104">You can use these entries to save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="4569e-105">Например, можно записать, когда начинается и заканчивается массовая вставка, чтобы идентифицировать проблемы с производительностью при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="4569e-105">For example, you can record when a bulk insert begins and ends to identify performance issues when the package runs.</span></span>  
  
 <span data-ttu-id="4569e-106">Пользовательские записи в журнале являются другим набором записей, отличным от стандартных событий ведения журнала, которые доступны для пакетов, всех контейнеров и задач.</span><span class="sxs-lookup"><span data-stu-id="4569e-106">The custom log entries are a different set of entries than the set of standard logging events that are available for packages and all containers and tasks.</span></span> <span data-ttu-id="4569e-107">Пользовательские записи в журнале приспособлены для записи полезных сведений о конкретной задаче или пакете.</span><span class="sxs-lookup"><span data-stu-id="4569e-107">The custom log entries are tailored to capture useful information about a specific task in a package.</span></span> <span data-ttu-id="4569e-108">Например, одна из пользовательских записей в журнале для задачи «Выполнение SQL» содержит инструкцию SQL, которая выполняется в задаче.</span><span class="sxs-lookup"><span data-stu-id="4569e-108">For example, one of the custom log entries for the Execute SQL task records the SQL statement that the task executes in the log.</span></span>  
  
 <span data-ttu-id="4569e-109">Все записи в журнале содержат сведения о дате и времени, в том числе записи, которые автоматически формируются в начале и в конце выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="4569e-109">All log entries include date and time information, including the log entries that are automatically written when a package begins and finishes.</span></span> <span data-ttu-id="4569e-110">Многие события журнала формируют несколько записей журнала.</span><span class="sxs-lookup"><span data-stu-id="4569e-110">Many of the log events write multiple entries to the log.</span></span> <span data-ttu-id="4569e-111">Это обычно происходит в том случае, когда событие состоит из нескольких стадий.</span><span class="sxs-lookup"><span data-stu-id="4569e-111">This typically occurs when the event has different phases.</span></span> <span data-ttu-id="4569e-112">Например, событие журнала `ExecuteSQLExecutingQuery` формирует три записи: одну запись после того, как задача устанавливает соединение с базой данных, вторую после того, как задача приступает к подготовке инструкции SQL, и еще одну после того, как выполнение инструкции SQL завершается.</span><span class="sxs-lookup"><span data-stu-id="4569e-112">For example, the `ExecuteSQLExecutingQuery` log event writes three entries: one entry after the task acquires a connection to the database, another after the task starts to prepare the SQL statement, and one more after the execution of the SQL statement is completed.</span></span>  
  
 <span data-ttu-id="4569e-113">Следующие объекты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] содержат пользовательские записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="4569e-113">The following [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects have custom log entries:</span></span>  
  
 [<span data-ttu-id="4569e-114">Пакет</span><span class="sxs-lookup"><span data-stu-id="4569e-114">Package</span></span>](#Package)  
  
 [<span data-ttu-id="4569e-115">Задача «Массовая вставка»</span><span class="sxs-lookup"><span data-stu-id="4569e-115">Bulk Insert Task</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="4569e-116">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="4569e-116">Data Flow Task</span></span>](#DataFlow)  
  
 [<span data-ttu-id="4569e-117">Задача «Выполнение пакета служб DTS 2000»</span><span class="sxs-lookup"><span data-stu-id="4569e-117">Execute DTS 2000 Task</span></span>](#ExecuteDTS200)  
  
 [<span data-ttu-id="4569e-118">Задача «Выполнение процесса»</span><span class="sxs-lookup"><span data-stu-id="4569e-118">Execute Process Task</span></span>](#ExecuteProcess)  
  
 [<span data-ttu-id="4569e-119">Задача «Выполнение SQL»</span><span class="sxs-lookup"><span data-stu-id="4569e-119">Execute SQL Task</span></span>](#ExecuteSQL)  
  
 [<span data-ttu-id="4569e-120">Задача "Файловая система"</span><span class="sxs-lookup"><span data-stu-id="4569e-120">File System Task</span></span>](#FileSystem)  
  
 [<span data-ttu-id="4569e-121">Задача «FTP»</span><span class="sxs-lookup"><span data-stu-id="4569e-121">FTP Task</span></span>](#FTP)  
  
 [<span data-ttu-id="4569e-122">Задача «Очередь сообщений»</span><span class="sxs-lookup"><span data-stu-id="4569e-122">Message Queue Task</span></span>](#MessageQueue)  
  
 [<span data-ttu-id="4569e-123">Задача «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="4569e-123">Script Task</span></span>](#Script)  
  
 [<span data-ttu-id="4569e-124">Задача «Отправка почты»</span><span class="sxs-lookup"><span data-stu-id="4569e-124">Send Mail Task</span></span>](#SendMail)  
  
 [<span data-ttu-id="4569e-125">Задача «Передача базы данных»</span><span class="sxs-lookup"><span data-stu-id="4569e-125">Transfer Database Task</span></span>](#TransferDatabase)  
  
 [<span data-ttu-id="4569e-126">Задача «Передача сообщений об ошибках»</span><span class="sxs-lookup"><span data-stu-id="4569e-126">Transfer Error Messages Task</span></span>](#TransferErrorMessages)  
  
 [<span data-ttu-id="4569e-127">Задача «Передача заданий»</span><span class="sxs-lookup"><span data-stu-id="4569e-127">Transfer Jobs Task</span></span>](#TransferJobs)  
  
 [<span data-ttu-id="4569e-128">Задача «Передача имен входа»</span><span class="sxs-lookup"><span data-stu-id="4569e-128">Transfer Logins Task</span></span>](#TransferLogins)  
  
 [<span data-ttu-id="4569e-129">Задача «Передача главных хранимых процедур»</span><span class="sxs-lookup"><span data-stu-id="4569e-129">Transfer Master Stored Procedures Task</span></span>](#TransferMasterStoredProcedures)  
  
 [<span data-ttu-id="4569e-130">Задача «Передача объектов SQL Server»</span><span class="sxs-lookup"><span data-stu-id="4569e-130">Transfer SQL Server Objects Task</span></span>](#TransferSQLServerObjects)  
  
 [<span data-ttu-id="4569e-131">Задача «Веб-служба»</span><span class="sxs-lookup"><span data-stu-id="4569e-131">Web Services Task</span></span>](#WebServices)  
  
 [<span data-ttu-id="4569e-132">Задача «Модуль чтения данных WMI»</span><span class="sxs-lookup"><span data-stu-id="4569e-132">WMI Data Reader Task</span></span>](#WMIDataReader)  
  
 [<span data-ttu-id="4569e-133">Задача «Отслеживание событий WMI»</span><span class="sxs-lookup"><span data-stu-id="4569e-133">WMI Event Watcher Task</span></span>](#WMIEventWatcher)  
  
 [<span data-ttu-id="4569e-134">Задача «XML»</span><span class="sxs-lookup"><span data-stu-id="4569e-134">XML Task</span></span>](#XML)  
  
## <a name="log-entries"></a><span data-ttu-id="4569e-135">Записи журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-135">Log Entries</span></span>  
  
###  <a name="package"></a><a name="Package"></a> <span data-ttu-id="4569e-136">Пакет</span><span class="sxs-lookup"><span data-stu-id="4569e-136">Package</span></span>  
 <span data-ttu-id="4569e-137">В следующей таблице перечислены пользовательские записи в журнале для пакетов.</span><span class="sxs-lookup"><span data-stu-id="4569e-137">The following table lists the custom log entries for packages.</span></span>  
  
|<span data-ttu-id="4569e-138">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-138">Log entry</span></span>|<span data-ttu-id="4569e-139">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-139">Description</span></span>|  
|---------------|-----------------|  
|`PackageStart`|<span data-ttu-id="4569e-140">Указывает, что выполнение пакета началось.</span><span class="sxs-lookup"><span data-stu-id="4569e-140">Indicates that the package began to run.</span></span><br /><br /> <span data-ttu-id="4569e-141">Примечание. Эта запись журнала формируется автоматически.</span><span class="sxs-lookup"><span data-stu-id="4569e-141">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="4569e-142">Ее нельзя исключить.</span><span class="sxs-lookup"><span data-stu-id="4569e-142">You cannot exclude it.</span></span>|  
|`PackageEnd`|<span data-ttu-id="4569e-143">Указывает, что выполнение пакета завершено.</span><span class="sxs-lookup"><span data-stu-id="4569e-143">Indicates that the package completed.</span></span><br /><br /> <span data-ttu-id="4569e-144">Примечание. Эта запись журнала формируется автоматически.</span><span class="sxs-lookup"><span data-stu-id="4569e-144">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="4569e-145">Ее нельзя исключить.</span><span class="sxs-lookup"><span data-stu-id="4569e-145">You cannot exclude it.</span></span>|  
|`Diagnostic`|<span data-ttu-id="4569e-146">Предоставляет сведения о настройках системы, влияющих на выполнение пакета, таких как количество одновременно исполняемых объектов.</span><span class="sxs-lookup"><span data-stu-id="4569e-146">Provides information about the system configuration that affects package execution such as the number executables that can be run concurrently.</span></span><br /><br /> <span data-ttu-id="4569e-147">Запись журнала `Diagnostic` также включает записи, сделанные до и после обращения к внешним поставщикам данных.</span><span class="sxs-lookup"><span data-stu-id="4569e-147">The `Diagnostic` log entry also includes before and after entries for calls to external data providers.</span></span> <span data-ttu-id="4569e-148">Дополнительные сведения см. в статье [Troubleshooting Tools Package Connectivity](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="4569e-148">For more information, see [Troubleshooting Tools Package Connectivity](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span></span>|  
  
###  <a name="bulk-insert-task"></a><a name="BulkInsert"></a> <span data-ttu-id="4569e-149">Задача «Массовая вставка»</span><span class="sxs-lookup"><span data-stu-id="4569e-149">Bulk Insert Task</span></span>  
 <span data-ttu-id="4569e-150">В следующей таблице перечислены пользовательские записи в журнале для задачи «Массовая вставка».</span><span class="sxs-lookup"><span data-stu-id="4569e-150">The following table lists the custom log entries for the Bulk Insert task.</span></span>  
  
|<span data-ttu-id="4569e-151">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-151">Log entry</span></span>|<span data-ttu-id="4569e-152">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-152">Description</span></span>|  
|---------------|-----------------|  
|`DTSBulkInsertTaskBegin`|<span data-ttu-id="4569e-153">Указывает, что массовая вставка началась.</span><span class="sxs-lookup"><span data-stu-id="4569e-153">Indicates that the bulk insert began.</span></span>|  
|`DTSBulkInsertTaskEnd`|<span data-ttu-id="4569e-154">Указывает, что массовая вставка завершена.</span><span class="sxs-lookup"><span data-stu-id="4569e-154">Indicates that the bulk insert finished.</span></span>|  
|`DTSBulkInsertTaskInfos`|<span data-ttu-id="4569e-155">Выводит описательные сведения об этой задаче.</span><span class="sxs-lookup"><span data-stu-id="4569e-155">Provides descriptive information about the task.</span></span>|  
  
###  <a name="data-flow-task"></a><a name="DataFlow"></a> <span data-ttu-id="4569e-156">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="4569e-156">Data Flow Task</span></span>  
 <span data-ttu-id="4569e-157">В следующей таблице перечислены пользовательские записи в журнале для задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="4569e-157">The following table lists the custom log entries for the Data Flow task.</span></span>  
  
|<span data-ttu-id="4569e-158">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-158">Log entry</span></span>|<span data-ttu-id="4569e-159">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-159">Description</span></span>|  
|---------------|-----------------|  
|`BufferSizeTuning`|<span data-ttu-id="4569e-160">Указывает, что задача потока данных изменила размер буфера.</span><span class="sxs-lookup"><span data-stu-id="4569e-160">Indicates that the Data Flow task changed the size of the buffer.</span></span> <span data-ttu-id="4569e-161">Эта запись журнала описывает причины изменения размера и фиксирует новый временный размер буфера.</span><span class="sxs-lookup"><span data-stu-id="4569e-161">The log entry describes the reasons for the size change and lists the temporary new buffer size.</span></span>|  
|`OnPipelinePostEndOfRowset`|<span data-ttu-id="4569e-162">Означает, что компонент получил сигнал конца набора строк, который устанавливается при последнем вызове метода `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="4569e-162">Denotes that a component has been given its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="4569e-163">Запись делается для каждого компонента в потоке данных, который обрабатывает ввод.</span><span class="sxs-lookup"><span data-stu-id="4569e-163">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="4569e-164">Запись включает имя компонента.</span><span class="sxs-lookup"><span data-stu-id="4569e-164">The entry includes the name of the component.</span></span>|  
|`OnPipelinePostPrimeOutput`|<span data-ttu-id="4569e-165">Указывает, что компонент завершил последний вызов метода `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="4569e-165">Indicates that the component has completed its last call to the `PrimeOutput` method.</span></span> <span data-ttu-id="4569e-166">В зависимости от потока данных, возможно формирование нескольких записей в журнале.</span><span class="sxs-lookup"><span data-stu-id="4569e-166">Depending on the data flow, multiple log entries may be written.</span></span> <span data-ttu-id="4569e-167">Если компонент является источником, это означает, что компонент завершил обработку строк.</span><span class="sxs-lookup"><span data-stu-id="4569e-167">If the component is a source, this means that the component has finished processing rows.</span></span>|  
|`OnPipelinePreEndOfRowset`|<span data-ttu-id="4569e-168">Показывает, что компонент уже готов получить сигнал конца набора строк, который устанавливается при последнем вызове метода `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="4569e-168">Indicates that a component is about to receive its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="4569e-169">Запись делается для каждого компонента в потоке данных, который обрабатывает ввод.</span><span class="sxs-lookup"><span data-stu-id="4569e-169">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="4569e-170">Запись включает имя компонента.</span><span class="sxs-lookup"><span data-stu-id="4569e-170">The entry includes the name of the component.</span></span>|  
|`OnPipelinePrePrimeOutput`|<span data-ttu-id="4569e-171">Показывает, что компонент готов получить свой вызов из метода `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="4569e-171">Indicates that the component is about to receive its call from the `PrimeOutput` method.</span></span> <span data-ttu-id="4569e-172">В зависимости от потока данных, возможно формирование нескольких записей в журнале.</span><span class="sxs-lookup"><span data-stu-id="4569e-172">Depending on the data flow, multiple log entries may be written.</span></span>|  
|`OnPipelineRowsSent`|<span data-ttu-id="4569e-173">Сообщает количество строк, предоставленных входу компонента с помощью вызова метода `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="4569e-173">Reports the number of rows provided to a component input by a call to the `ProcessInput` method.</span></span> <span data-ttu-id="4569e-174">Запись журнала включает имя компонента.</span><span class="sxs-lookup"><span data-stu-id="4569e-174">The log entry includes the component name.</span></span>|  
|`PipelineBufferLeak`|<span data-ttu-id="4569e-175">Предоставляет сведения обо всех компонентах, которые удерживают буферы от уничтожения после того, как диспетчер буферов завершил свое выполнение.</span><span class="sxs-lookup"><span data-stu-id="4569e-175">Provides information about any component that kept buffers alive after the buffer manager goes away.</span></span> <span data-ttu-id="4569e-176">Это означает, что ресурсы буферов не были освобождены и могут вызвать утечку памяти.</span><span class="sxs-lookup"><span data-stu-id="4569e-176">This means that buffers resources were not released and may cause memory leaks.</span></span> <span data-ttu-id="4569e-177">Запись журнала предоставляет имя компонента и идентификатор буфера.</span><span class="sxs-lookup"><span data-stu-id="4569e-177">The log entry provides the name of the component and the ID of the buffer.</span></span>|  
|`PipelineExecutionPlan`|<span data-ttu-id="4569e-178">Сообщает о плане выполнения потока данных.</span><span class="sxs-lookup"><span data-stu-id="4569e-178">Reports the execution plan of the data flow.</span></span> <span data-ttu-id="4569e-179">Предоставляет сведения о том, как буферы будут отсылаться компонентам.</span><span class="sxs-lookup"><span data-stu-id="4569e-179">It provides information about how buffers will be sent to components.</span></span> <span data-ttu-id="4569e-180">Эти сведения в сочетании с записью PipelineExecutionTrees описывают, что происходит в задаче.</span><span class="sxs-lookup"><span data-stu-id="4569e-180">This information, in combination with the PipelineExecutionTrees entry, describes what is occurring in the task.</span></span>|  
|`PipelineExecutionTrees`|<span data-ttu-id="4569e-181">Сообщает о дереве выполнения макета в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="4569e-181">Reports the execution trees of the layout in the data flow.</span></span> <span data-ttu-id="4569e-182">Планировщик подсистемы обработки потока данных использует эти деревья для построения плана выполнения потока данных.</span><span class="sxs-lookup"><span data-stu-id="4569e-182">The scheduler of the data flow engine use the trees to build the execution plan of the data flow.</span></span>|  
|`PipelineInitialization`|<span data-ttu-id="4569e-183">Предоставляет сведения об инициализации задачи.</span><span class="sxs-lookup"><span data-stu-id="4569e-183">Provides initialization information about the task.</span></span> <span data-ttu-id="4569e-184">Эти сведения включают каталоги, используемые для временного хранения данных большого объема типа BLOB, размер буфера по умолчанию и количество строк в буфере.</span><span class="sxs-lookup"><span data-stu-id="4569e-184">This information includes the directories to use for temporary storage of BLOB data, the default buffer size, and the number of rows in a buffer.</span></span> <span data-ttu-id="4569e-185">В зависимости от настройки задачи потока данных, возможно формирование нескольких записей в журнале.</span><span class="sxs-lookup"><span data-stu-id="4569e-185">Depending on the configuration of the Data Flow task, multiple log entries may be written.</span></span>|  
  
###  <a name="execute-dts-2000-task"></a><a name="ExecuteDTS200"></a> <span data-ttu-id="4569e-186">Задача «Выполнение пакета служб DTS 2000»</span><span class="sxs-lookup"><span data-stu-id="4569e-186">Execute DTS 2000 Task</span></span>  
 <span data-ttu-id="4569e-187">В следующей таблице перечислены пользовательские записи в журнале для задачи «Выполнение пакета служб DTS 2000».</span><span class="sxs-lookup"><span data-stu-id="4569e-187">The following table lists the custom log entries for the Execute DTS 2000 task.</span></span>  
  
|<span data-ttu-id="4569e-188">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-188">Log entry</span></span>|<span data-ttu-id="4569e-189">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-189">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteDTS80PackageTaskBegin`|<span data-ttu-id="4569e-190">Указывает, что задача приступила к выполнению пакета служб DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="4569e-190">Indicates that the task began to run a DTS 2000 package.</span></span>|  
|`ExecuteDTS80PackageTaskEnd`|<span data-ttu-id="4569e-191">Указывает, что выполнение задачи завершено.</span><span class="sxs-lookup"><span data-stu-id="4569e-191">Indicates that the task finished.</span></span><br /><br /> <span data-ttu-id="4569e-192">Примечание. Пакет служб DTS 2000 может продолжить свое выполнение после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="4569e-192">Note: The DTS 2000 package may continue to run after the task ends.</span></span>|  
|`ExecuteDTS80PackageTaskTaskInfo`|<span data-ttu-id="4569e-193">Выводит описательные сведения об этой задаче.</span><span class="sxs-lookup"><span data-stu-id="4569e-193">Provides descriptive information about the task.</span></span>|  
|`ExecuteDTS80PackageTaskTaskResult`|<span data-ttu-id="4569e-194">Сообщает результаты выполнения пакета служб DTS 2000, запущенного задачей.</span><span class="sxs-lookup"><span data-stu-id="4569e-194">Reports the execution result of the DTS 2000 package that the task ran.</span></span>|  
  
###  <a name="execute-process-task"></a><a name="ExecuteProcess"></a> <span data-ttu-id="4569e-195">Задача «Выполнение процесса»</span><span class="sxs-lookup"><span data-stu-id="4569e-195">Execute Process Task</span></span>  
 <span data-ttu-id="4569e-196">В следующей таблице перечислены пользовательские записи в журнале для задачи «Выполнение процесса».</span><span class="sxs-lookup"><span data-stu-id="4569e-196">The following table lists the custom log entries for the Execute Process task.</span></span>  
  
|<span data-ttu-id="4569e-197">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-197">Log entry</span></span>|<span data-ttu-id="4569e-198">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-198">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteProcessExecutingProcess`|<span data-ttu-id="4569e-199">Предоставляет сведения о процессе выполнения исполняемого объекта, на запуск которого настроена задача.</span><span class="sxs-lookup"><span data-stu-id="4569e-199">Provides information about the process of running the executable that the task is configured to run.</span></span><br /><br /> <span data-ttu-id="4569e-200">В журнале формируются две записи.</span><span class="sxs-lookup"><span data-stu-id="4569e-200">Two log entries are written.</span></span> <span data-ttu-id="4569e-201">Одна из них предоставляет сведения об имени и месте выполнения исполняемого объекта, на запуск которого настроена задача, другая фиксирует выход из исполняемого объекта.</span><span class="sxs-lookup"><span data-stu-id="4569e-201">One contains information about the name and location of the executable that the task runs, and the other records the exit from the executable.</span></span>|  
|`ExecuteProcessVariableRouting`|<span data-ttu-id="4569e-202">Предоставляет сведения о том, какие переменные направляются на вход и выходы исполняемого объекта.</span><span class="sxs-lookup"><span data-stu-id="4569e-202">Provides information about which variables are routed to the input and outputs of the executable.</span></span> <span data-ttu-id="4569e-203">Данные журнала записываются для потоков stdin (вход), stdout (выход) и stderr (вывод ошибок на выходе).</span><span class="sxs-lookup"><span data-stu-id="4569e-203">Log entries are written for stdin (the input), stdout (the output), and stderr (the error output).</span></span>|  
  
###  <a name="execute-sql-task"></a><a name="ExecuteSQL"></a> <span data-ttu-id="4569e-204">Задача «Выполнение SQL»</span><span class="sxs-lookup"><span data-stu-id="4569e-204">Execute SQL Task</span></span>  
 <span data-ttu-id="4569e-205">В следующей таблице перечислены пользовательские записи журнала для задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="4569e-205">The following table describes the custom log entry for the Execute SQL task.</span></span>  
  
|<span data-ttu-id="4569e-206">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-206">Log entry</span></span>|<span data-ttu-id="4569e-207">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-207">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteSQLExecutingQuery`|<span data-ttu-id="4569e-208">Предоставляет сведения об этапах выполнения инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="4569e-208">Provides information about the execution phases of the SQL statement.</span></span> <span data-ttu-id="4569e-209">Записи журнала формируются в тот момент, когда задача устанавливает соединение с базой данных, когда задача приступает к подготовке инструкции SQL, и после того, как завершается выполнение инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="4569e-209">Log entries are written when the task acquires connection to the database, when the task starts to prepare the SQL statement, and after the execution of the SQL statement is completed.</span></span> <span data-ttu-id="4569e-210">Запись журнала для этапа подготовки содержит инструкцию SQL, которая используется задачей.</span><span class="sxs-lookup"><span data-stu-id="4569e-210">The log entry for the prepare phase includes the SQL statement that the task uses.</span></span>|  
  
###  <a name="file-system-task"></a><a name="FileSystem"></a> <span data-ttu-id="4569e-211">Задача "Файловая система"</span><span class="sxs-lookup"><span data-stu-id="4569e-211">File System Task</span></span>  
 <span data-ttu-id="4569e-212">В следующей таблице перечислены пользовательские записи журнала для задачи «Файловая система».</span><span class="sxs-lookup"><span data-stu-id="4569e-212">The following table describes the custom log entry for the File System task.</span></span>  
  
|<span data-ttu-id="4569e-213">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-213">Log entry</span></span>|<span data-ttu-id="4569e-214">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-214">Description</span></span>|  
|---------------|-----------------|  
|`FileSystemOperation`|<span data-ttu-id="4569e-215">Сообщает об операции, выполняемой задачей.</span><span class="sxs-lookup"><span data-stu-id="4569e-215">Reports the operation that the task performs.</span></span> <span data-ttu-id="4569e-216">Эта запись журнала формируется, когда операция файловой системы начинается и включает сведения об источнике и назначении.</span><span class="sxs-lookup"><span data-stu-id="4569e-216">The log entry is written when the file system operation starts and includes information about the source and destination.</span></span>|  
  
###  <a name="ftp-task"></a><a name="FTP"></a> <span data-ttu-id="4569e-217">Задача «FTP»</span><span class="sxs-lookup"><span data-stu-id="4569e-217">FTP Task</span></span>  
 <span data-ttu-id="4569e-218">В следующей таблице перечислены пользовательские записи журнала для задачи «FTP».</span><span class="sxs-lookup"><span data-stu-id="4569e-218">The following table lists the custom log entries for the FTP task.</span></span>  
  
|<span data-ttu-id="4569e-219">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-219">Log entry</span></span>|<span data-ttu-id="4569e-220">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-220">Description</span></span>|  
|---------------|-----------------|  
|`FTPConnectingToServer`|<span data-ttu-id="4569e-221">Указывает, что задача инициализировала соединение с FTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="4569e-221">Indicates that the task initiated a connection to the FTP server.</span></span>|  
|`FTPOperation`|<span data-ttu-id="4569e-222">Сообщает о начале FTP-операции, выполняемой задачей, и о типе этой операции.</span><span class="sxs-lookup"><span data-stu-id="4569e-222">Reports the beginning of and the type of FTP operation that the task performs.</span></span>|  
  
###  <a name="message-queue-task"></a><a name="MessageQueue"></a> <span data-ttu-id="4569e-223">Задача «Очередь сообщений»</span><span class="sxs-lookup"><span data-stu-id="4569e-223">Message Queue Task</span></span>  
 <span data-ttu-id="4569e-224">В следующей таблице перечислены пользовательские записи в журнале для задачи «Очередь сообщений».</span><span class="sxs-lookup"><span data-stu-id="4569e-224">The following table lists the custom log entries for the Message Queue task.</span></span>  
  
|<span data-ttu-id="4569e-225">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-225">Log entry</span></span>|<span data-ttu-id="4569e-226">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-226">Description</span></span>|  
|---------------|-----------------|  
|`MSMQAfterOpen`|<span data-ttu-id="4569e-227">Указывает, что задача завершила открытие очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="4569e-227">Indicates that the task finished opening the message queue.</span></span>|  
|`MSMQBeforeOpen`|<span data-ttu-id="4569e-228">Указывает, что задача приступила к открытию очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="4569e-228">Indicates that the task began to open the message queue.</span></span>|  
|`MSMQBeginReceive`|<span data-ttu-id="4569e-229">Указывает, что задача приступила к получению сообщения.</span><span class="sxs-lookup"><span data-stu-id="4569e-229">Indicates that the task began to receive a message.</span></span>|  
|`MSMQBeginSend`|<span data-ttu-id="4569e-230">Указывает, что задача приступила к отправке сообщения.</span><span class="sxs-lookup"><span data-stu-id="4569e-230">Indicates that the task began to send a message.</span></span>|  
|`MSMQEndReceive`|<span data-ttu-id="4569e-231">Указывает, что задача завершила прием сообщения.</span><span class="sxs-lookup"><span data-stu-id="4569e-231">Indicates that the task finished receiving a message.</span></span>|  
|`MSMQEndSend`|<span data-ttu-id="4569e-232">Указывает, что задача завершила отправку сообщения.</span><span class="sxs-lookup"><span data-stu-id="4569e-232">Indicates that the task finished sending a message</span></span>|  
|`MSMQTaskInfo`|<span data-ttu-id="4569e-233">Выводит описательные сведения об этой задаче.</span><span class="sxs-lookup"><span data-stu-id="4569e-233">Provides descriptive information about the task.</span></span>|  
|`MSMQTaskTimeOut`|<span data-ttu-id="4569e-234">Указывает, что время ожидания выполнения задачи истекло.</span><span class="sxs-lookup"><span data-stu-id="4569e-234">Indicates that the task timed out.</span></span>|  
  
###  <a name="script-task"></a><a name="Script"></a> <span data-ttu-id="4569e-235">Задача «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="4569e-235">Script Task</span></span>  
 <span data-ttu-id="4569e-236">В следующей таблице перечислены пользовательские записи журнала для задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="4569e-236">The following table describes the custom log entry for the Script task.</span></span>  
  
|<span data-ttu-id="4569e-237">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-237">Log entry</span></span>|<span data-ttu-id="4569e-238">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-238">Description</span></span>|  
|---------------|-----------------|  
|`ScriptTaskLogEntry`|<span data-ttu-id="4569e-239">Сообщает о результатах выполнения операции ведения журнала в скрипте.</span><span class="sxs-lookup"><span data-stu-id="4569e-239">Reports the results of implementing logging in the script.</span></span> <span data-ttu-id="4569e-240">Запись журнала формируется для каждого вызова метода `Log` объекта `Dts`.</span><span class="sxs-lookup"><span data-stu-id="4569e-240">A log entry is written for each call to the `Log` method of the `Dts` object.</span></span> <span data-ttu-id="4569e-241">Эта запись формируется в момент запуска кода.</span><span class="sxs-lookup"><span data-stu-id="4569e-241">The entry is written when the code is run.</span></span> <span data-ttu-id="4569e-242">Дополнительные сведения см. в разделе [ведения журналов в задаче «скрипт»](extending-packages-scripting/task/logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="4569e-242">For more information, see [Logging in the Script Task](extending-packages-scripting/task/logging-in-the-script-task.md).</span></span>|  
  
###  <a name="send-mail-task"></a><a name="SendMail"></a> <span data-ttu-id="4569e-243">Задача «Отправка почты»</span><span class="sxs-lookup"><span data-stu-id="4569e-243">Send Mail Task</span></span>  
 <span data-ttu-id="4569e-244">В следующей таблице перечислены пользовательские записи в журнале для задачи «Отправка почты».</span><span class="sxs-lookup"><span data-stu-id="4569e-244">The following table lists the custom log entries for the Send Mail task.</span></span>  
  
|<span data-ttu-id="4569e-245">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-245">Log entry</span></span>|<span data-ttu-id="4569e-246">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-246">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="4569e-247">Указывает, что задача приступила к отправке сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4569e-247">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="4569e-248">Указывает, что задача завершила отправку сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4569e-248">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="4569e-249">Выводит описательные сведения об этой задаче.</span><span class="sxs-lookup"><span data-stu-id="4569e-249">Provides descriptive information about the task.</span></span>|  
  
###  <a name="transfer-database-task"></a><a name="TransferDatabase"></a> <span data-ttu-id="4569e-250">Задача «Передача базы данных»</span><span class="sxs-lookup"><span data-stu-id="4569e-250">Transfer Database Task</span></span>  
 <span data-ttu-id="4569e-251">В следующей таблице перечислены пользовательские записи в журнале для задачи «Передача базы данных».</span><span class="sxs-lookup"><span data-stu-id="4569e-251">The following table lists the custom log entries for the Transfer Database task.</span></span>  
  
|<span data-ttu-id="4569e-252">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-252">Log entry</span></span>|<span data-ttu-id="4569e-253">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-253">Description</span></span>|  
|---------------|-----------------|  
|`SourceDB`|<span data-ttu-id="4569e-254">Указывает базу данных, которая копируется задачей.</span><span class="sxs-lookup"><span data-stu-id="4569e-254">Specifies the database that the task copied.</span></span>|  
|`SourceSQLServer`|<span data-ttu-id="4569e-255">Указывает компьютер, с которого копируется база данных.</span><span class="sxs-lookup"><span data-stu-id="4569e-255">Specifies the computer from which the database was copied.</span></span>|  
  
###  <a name="transfer-error-messages-task"></a><a name="TransferErrorMessages"></a> <span data-ttu-id="4569e-256">Задача «Передача сообщений об ошибках»</span><span class="sxs-lookup"><span data-stu-id="4569e-256">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="4569e-257">В следующей таблице перечислены пользовательские записи в журнале для задачи «Передача сообщений об ошибках».</span><span class="sxs-lookup"><span data-stu-id="4569e-257">The following table lists the custom log entries for the Transfer Error Messages task.</span></span>  
  
|<span data-ttu-id="4569e-258">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-258">Log entry</span></span>|<span data-ttu-id="4569e-259">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-259">Description</span></span>|  
|---------------|-----------------|  
|`TransferErrorMessagesTaskFinishedTransferringObjects`|<span data-ttu-id="4569e-260">Указывает, что задача завершила передачу сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="4569e-260">Indicates that the task finished transferring error messages.</span></span>|  
|`TransferErrorMessagesTaskStartTransferringObjects`|<span data-ttu-id="4569e-261">Указывает, что задача приступила к передаче сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="4569e-261">Indicates that the task started to transfer error messages.</span></span>|  
  
###  <a name="transfer-jobs-task"></a><a name="TransferJobs"></a> <span data-ttu-id="4569e-262">Задача «Передача заданий»</span><span class="sxs-lookup"><span data-stu-id="4569e-262">Transfer Jobs Task</span></span>  
 <span data-ttu-id="4569e-263">В следующей таблице перечислены пользовательские записи в журнале для задачи «Передача заданий».</span><span class="sxs-lookup"><span data-stu-id="4569e-263">The following table lists the custom log entries for the Transfer Jobs task.</span></span>  
  
|<span data-ttu-id="4569e-264">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-264">Log entry</span></span>|<span data-ttu-id="4569e-265">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-265">Description</span></span>|  
|---------------|-----------------|  
|`TransferJobsTaskFinishedTransferringObjects`|<span data-ttu-id="4569e-266">Указывает, что задача завершила передачу заданий агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4569e-266">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
|`TransferJobsTaskStartTransferringObjects`|<span data-ttu-id="4569e-267">Указывает, что задача приступила к передаче заданий агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4569e-267">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
  
###  <a name="transfer-logins-task"></a><a name="TransferLogins"></a> <span data-ttu-id="4569e-268">Задача «Передача имен входа»</span><span class="sxs-lookup"><span data-stu-id="4569e-268">Transfer Logins Task</span></span>  
 <span data-ttu-id="4569e-269">В следующей таблице перечислены пользовательские записи в журнале для задачи «Передача имен входа».</span><span class="sxs-lookup"><span data-stu-id="4569e-269">The following table lists the custom log entries for the Transfer Logins task.</span></span>  
  
|<span data-ttu-id="4569e-270">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-270">Log entry</span></span>|<span data-ttu-id="4569e-271">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-271">Description</span></span>|  
|---------------|-----------------|  
|`TransferLoginsTaskFinishedTransferringObjects`|<span data-ttu-id="4569e-272">Указывает, что задача завершила передачу имен входа.</span><span class="sxs-lookup"><span data-stu-id="4569e-272">Indicates that the task finished transferring logins.</span></span>|  
|`TransferLoginsTaskStartTransferringObjects`|<span data-ttu-id="4569e-273">Указывает, что задача приступила к передаче имен входа.</span><span class="sxs-lookup"><span data-stu-id="4569e-273">Indicates that the task started to transfer logins.</span></span>|  
  
###  <a name="transfer-master-stored-procedures-task"></a><a name="TransferMasterStoredProcedures"></a> <span data-ttu-id="4569e-274">Задача «Передача главных хранимых процедур»</span><span class="sxs-lookup"><span data-stu-id="4569e-274">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="4569e-275">В следующей таблице перечислены пользовательские записи в журнале для задачи «Передача главных хранимых процедур».</span><span class="sxs-lookup"><span data-stu-id="4569e-275">The following table lists the custom log entries for the Transfer Master Stored Procedures task.</span></span>  
  
|<span data-ttu-id="4569e-276">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-276">Log entry</span></span>|<span data-ttu-id="4569e-277">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-277">Description</span></span>|  
|---------------|-----------------|  
|`TransferStoredProceduresTaskFinishedTransferringObjects`|<span data-ttu-id="4569e-278">Указывает, что задача завершила передачу пользовательских хранимых процедур, хранящихся в базе данных **master** .</span><span class="sxs-lookup"><span data-stu-id="4569e-278">Indicates that the task finished transferring user-defined stored procedures that are stored in the **master** database.</span></span>|  
|`TransferStoredProceduresTaskStartTransferringObjects`|<span data-ttu-id="4569e-279">Указывает, что задача приступила к передаче пользовательских хранимых процедур, хранящихся в базе данных **master** .</span><span class="sxs-lookup"><span data-stu-id="4569e-279">Indicates that the task started to transfer user-defined stored procedures that are stored in the **master** database.</span></span>|  
  
###  <a name="transfer-sql-server-objects-task"></a><a name="TransferSQLServerObjects"></a> <span data-ttu-id="4569e-280">Задача «Передача объектов SQL Server»</span><span class="sxs-lookup"><span data-stu-id="4569e-280">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="4569e-281">В следующей таблице перечислены пользовательские записи в журнале для задачи «Передача объектов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ».</span><span class="sxs-lookup"><span data-stu-id="4569e-281">The following table lists the custom log entries for the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
|<span data-ttu-id="4569e-282">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-282">Log entry</span></span>|<span data-ttu-id="4569e-283">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-283">Description</span></span>|  
|---------------|-----------------|  
|`TransferSqlServerObjectsTaskFinishedTransferringObjects`|<span data-ttu-id="4569e-284">Указывает, что задача завершила передачу объектов базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4569e-284">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
|`TransferSqlServerObjectsTaskStartTransferringObjects`|<span data-ttu-id="4569e-285">Указывает, что задача приступила к передаче объектов базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4569e-285">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
  
###  <a name="web-services-task"></a><a name="WebServices"></a> <span data-ttu-id="4569e-286">Задача «Веб-служба»</span><span class="sxs-lookup"><span data-stu-id="4569e-286">Web Services Task</span></span>  
 <span data-ttu-id="4569e-287">В следующей таблице перечислены пользовательские записи в журнале для задачи «Веб-служба».</span><span class="sxs-lookup"><span data-stu-id="4569e-287">The following table lists the custom log entries that you can enable for the Web Services task.</span></span>  
  
|<span data-ttu-id="4569e-288">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-288">Log entry</span></span>|<span data-ttu-id="4569e-289">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-289">Description</span></span>|  
|---------------|-----------------|  
|`WSTaskBegin`|<span data-ttu-id="4569e-290">Задача получила доступ к веб-службе.</span><span class="sxs-lookup"><span data-stu-id="4569e-290">The task began to access a Web service.</span></span>|  
|`WSTaskEnd`|<span data-ttu-id="4569e-291">Задача завершила метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="4569e-291">The task completed a Web service method.</span></span>|  
|`WSTaskInfo`|<span data-ttu-id="4569e-292">Описательные сведения об этой задаче.</span><span class="sxs-lookup"><span data-stu-id="4569e-292">Descriptive information about the task.</span></span>|  
  
###  <a name="wmi-data-reader-task"></a><a name="WMIDataReader"></a> <span data-ttu-id="4569e-293">Задача «Модуль чтения данных WMI»</span><span class="sxs-lookup"><span data-stu-id="4569e-293">WMI Data Reader Task</span></span>  
 <span data-ttu-id="4569e-294">В следующей таблице перечислены пользовательские записи в журнале для задачи «Модуль чтения данных WMI».</span><span class="sxs-lookup"><span data-stu-id="4569e-294">The following table lists the custom log entries for the WMI Data Reader task.</span></span>  
  
|<span data-ttu-id="4569e-295">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-295">Log entry</span></span>|<span data-ttu-id="4569e-296">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-296">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="4569e-297">Указывает, что задача приступила к чтению данных инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="4569e-297">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="4569e-298">Сообщает о WQL-запросе, выполняемом задачей.</span><span class="sxs-lookup"><span data-stu-id="4569e-298">Reports the WQL query that the task ran.</span></span>|  
  
###  <a name="wmi-event-watcher-task"></a><a name="WMIEventWatcher"></a> <span data-ttu-id="4569e-299">Задача «Отслеживание событий WMI»</span><span class="sxs-lookup"><span data-stu-id="4569e-299">WMI Event Watcher Task</span></span>  
 <span data-ttu-id="4569e-300">В следующей таблице перечислены пользовательские записи в журнале для задачи «Отслеживание событий WMI».</span><span class="sxs-lookup"><span data-stu-id="4569e-300">The following table lists the custom log entries for the WMI Event Watcher task.</span></span>  
  
|<span data-ttu-id="4569e-301">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-301">Log entry</span></span>|<span data-ttu-id="4569e-302">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-302">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="4569e-303">Сообщает, что произошло событие, отслеживаемое задачей.</span><span class="sxs-lookup"><span data-stu-id="4569e-303">Denotes that the event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="4569e-304">Указывает, что время ожидания выполнения задачи истекло.</span><span class="sxs-lookup"><span data-stu-id="4569e-304">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="4569e-305">Указывает, что задача приступила к выполнению WQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="4569e-305">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="4569e-306">Эта запись содержит запрос.</span><span class="sxs-lookup"><span data-stu-id="4569e-306">The entry includes the query.</span></span>|  
  
###  <a name="xml-task"></a><a name="XML"></a> <span data-ttu-id="4569e-307">Задача «XML»</span><span class="sxs-lookup"><span data-stu-id="4569e-307">XML Task</span></span>  
 <span data-ttu-id="4569e-308">В приведенной ниже таблице перечислены пользовательские записи журнала для задачи «XML».</span><span class="sxs-lookup"><span data-stu-id="4569e-308">The following table describes the custom log entry for the XML task.</span></span>  
  
|<span data-ttu-id="4569e-309">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="4569e-309">Log entry</span></span>|<span data-ttu-id="4569e-310">Описание</span><span class="sxs-lookup"><span data-stu-id="4569e-310">Description</span></span>|  
|---------------|-----------------|  
|`XMLOperation`|<span data-ttu-id="4569e-311">Предоставляет сведения об операции, выполняемой задачей</span><span class="sxs-lookup"><span data-stu-id="4569e-311">Provides information about the operation that the task performs</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="4569e-312">См. также:</span><span class="sxs-lookup"><span data-stu-id="4569e-312">See Also</span></span>  
 [<span data-ttu-id="4569e-313">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="4569e-313">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
