---
title: Задача "Отслеживание событий WMI" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatchertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Event Watcher task [Integration Services]
ms.assetid: b5bb52e9-a77e-41e1-93f9-d4c3bc6b2c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be20624e5ccdf665e6274f647c342498e9c0f0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750052"
---
# <a name="wmi-event-watcher-task"></a><span data-ttu-id="c02f7-102">Задача «Отслеживание событий WMI»</span><span class="sxs-lookup"><span data-stu-id="c02f7-102">WMI Event Watcher Task</span></span>
  <span data-ttu-id="c02f7-103">Задача «Отслеживание событий WMI» осуществляет наблюдение за событием инструментария управления Windows (WMI) при помощи запроса на языке запросов к инструментарию управления (WQL), определяющего нужные события.</span><span class="sxs-lookup"><span data-stu-id="c02f7-103">The WMI Event Watcher task watches for a Windows Management Instrumentation (WMI) event using a Management Instrumentation Query Language (WQL) event query to specify events of interest.</span></span> <span data-ttu-id="c02f7-104">Задачу «Отслеживание событий WMI» можно использовать в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="c02f7-104">You can use the WMI Event Watcher task for the following purposes:</span></span>  
  
-   <span data-ttu-id="c02f7-105">ожидание уведомления о добавлении файлов в папку и запуск обработки файла;</span><span class="sxs-lookup"><span data-stu-id="c02f7-105">Wait for notification that files have been added to a folder and then initiate the processing of the file.</span></span>  
  
-   <span data-ttu-id="c02f7-106">выполнение пакета, удаляющего файлы, когда объем доступной памяти на сервере падает ниже заданного значения;</span><span class="sxs-lookup"><span data-stu-id="c02f7-106">Run a package that deletes files when the available memory on a server drops lower than a specified percentage.</span></span>  
  
-   <span data-ttu-id="c02f7-107">отслеживание установки приложения и последующий запуск пакета, использующего это приложение.</span><span class="sxs-lookup"><span data-stu-id="c02f7-107">Watch for installation of an application, and then run a package that uses the application.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="c02f7-108">содержат задачу, считывающую данные WMI.</span><span class="sxs-lookup"><span data-stu-id="c02f7-108">includes a task that reads WMI information.</span></span>  
  
 <span data-ttu-id="c02f7-109">Дополнительные сведения об этой задаче см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="c02f7-109">For more information about this task, click the following topic:</span></span>  
  
-   [<span data-ttu-id="c02f7-110">Задача «Модуль чтения данных WMI»</span><span class="sxs-lookup"><span data-stu-id="c02f7-110">WMI Data Reader Task</span></span>](wmi-data-reader-task.md)  
  
## <a name="wql-queries"></a><span data-ttu-id="c02f7-111">WQL-запрос</span><span class="sxs-lookup"><span data-stu-id="c02f7-111">WQL Queries</span></span>  
 <span data-ttu-id="c02f7-112">WQL — это разновидность языка SQL с выражениями, поддерживающими уведомления о событиях инструментария WMI и другие функции WMI.</span><span class="sxs-lookup"><span data-stu-id="c02f7-112">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="c02f7-113">Дополнительные сведения о WQL см. в документации по инструментарию управления Windows в [библиотеке MSDN](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="c02f7-113">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c02f7-114">Классы WMI отличаются в различных версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="c02f7-114">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="c02f7-115">В следующем запросе отслеживается уведомление об использовании более 40 процентов мощности ЦП.</span><span class="sxs-lookup"><span data-stu-id="c02f7-115">The following query watches for notification that the CPU use is more than 40 percent.</span></span>  
  
```  
SELECT * from __InstanceModificationEvent WITHIN 2 WHERE TargetInstance ISA 'Win32_Processor' and TargetInstance.LoadPercentage > 40  
```  
  
 <span data-ttu-id="c02f7-116">В следующем запросе отслеживается уведомление о добавлении файла в папку.</span><span class="sxs-lookup"><span data-stu-id="c02f7-116">The following query watches for notification that a file has been added to a folder.</span></span>  
  
```  
SELECT * FROM __InstanceCreationEvent WITHIN 10 WHERE TargetInstance ISA "CIM_DirectoryContainsFile" and TargetInstance.GroupComponent= "Win32_Directory.Name=\"c:\\\\WMIFileWatcher\""   
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-event-watcher-task"></a><span data-ttu-id="c02f7-117">Пользовательские сообщения для ведения журнала, доступные в задаче «Отслеживание событий WMI»</span><span class="sxs-lookup"><span data-stu-id="c02f7-117">Custom Logging Messages Available on the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="c02f7-118">В следующей таблице перечислены пользовательские записи в журнале для задачи «Отслеживание событий WMI».</span><span class="sxs-lookup"><span data-stu-id="c02f7-118">The following table lists the custom log entries for the WMI Event Watcher task.</span></span> <span data-ttu-id="c02f7-119">Дополнительные сведения см. в разделах [Ведение журналов в службах Integration Services (SSIS)](../performance/integration-services-ssis-logging.md) и [Пользовательские сообщения для ведения журнала](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c02f7-119">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="c02f7-120">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="c02f7-120">Log entry</span></span>|<span data-ttu-id="c02f7-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c02f7-121">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="c02f7-122">Указывает, что произошло событие, отслеживаемое задачей.</span><span class="sxs-lookup"><span data-stu-id="c02f7-122">Indicates that an event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="c02f7-123">Указывает, что время ожидания выполнения задачи истекло.</span><span class="sxs-lookup"><span data-stu-id="c02f7-123">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="c02f7-124">Указывает, что задача приступила к выполнению WQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="c02f7-124">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="c02f7-125">Эта запись содержит запрос.</span><span class="sxs-lookup"><span data-stu-id="c02f7-125">The entry includes the query.</span></span>|  
  
## <a name="configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="c02f7-126">Настройка задачи «Отслеживание событий WMI»</span><span class="sxs-lookup"><span data-stu-id="c02f7-126">Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="c02f7-127">Настроить задачу «Модуль чтения данных WMI» можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="c02f7-127">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="c02f7-128">Указать, какой диспетчер соединений WMI необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="c02f7-128">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="c02f7-129">Указать источник WQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="c02f7-129">Specify the source of the WQL query.</span></span> <span data-ttu-id="c02f7-130">По отношению к задаче источник может быть внешним (переменной или файлом), или же запрос может быть сохранен как свойство задачи.</span><span class="sxs-lookup"><span data-stu-id="c02f7-130">The source can be external to the task, a variable or a file, or the query can be stored in a task property.</span></span>  
  
-   <span data-ttu-id="c02f7-131">Укажите, какое действие должно быть выполнено задачей по событию инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="c02f7-131">Specify the action that the task takes when the WMI event occurs.</span></span> <span data-ttu-id="c02f7-132">Можно вести журнал уведомлений о событии и состоянии после события или инициировать пользовательские события служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , которые предоставляют данные, связанные с событием WMI, уведомлением и состоянием после события.</span><span class="sxs-lookup"><span data-stu-id="c02f7-132">You can log the event notification and the status after the event, or raise custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] events that provide information associated with the WMI event, the notification, and the status after the event.</span></span>  
  
-   <span data-ttu-id="c02f7-133">Определите реакцию задачи на события.</span><span class="sxs-lookup"><span data-stu-id="c02f7-133">Define how the task responds to the event.</span></span> <span data-ttu-id="c02f7-134">В зависимости от события задача может быть настроена на выполнение или сбой, либо на дальнейшее отслеживание событий.</span><span class="sxs-lookup"><span data-stu-id="c02f7-134">The task can be configured to succeed or fail, depending on the event, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="c02f7-135">Укажите, какое действие должно быть предпринято задачей по истечении времени ожидания запроса WMI. Можно вести журнал истечения времени ожидания и состояния после него или инициировать пользовательское событие служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , указывающее, что время ожидания события инструментария WMI истекло, а также записывающее состояние ожидания в журнал.</span><span class="sxs-lookup"><span data-stu-id="c02f7-135">Specify the action the task takes when the WMI query times out. You can log the time-out and the status after time-out, or raise a custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] event, indicating that the WMI event timed out and logging the time-out and time-out status.</span></span>  
  
-   <span data-ttu-id="c02f7-136">Определите реакцию задачи на истечение срока ожидания. Задача может быть настроена на выполнение или сбой, либо на дальнейшее отслеживание событий.</span><span class="sxs-lookup"><span data-stu-id="c02f7-136">Define how the task responds to the time-out. The task can be configured to succeed or fail, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="c02f7-137">Укажите, сколько раз задача должна отслеживать событие.</span><span class="sxs-lookup"><span data-stu-id="c02f7-137">Specify the number of times the task watches for the event.</span></span>  
  
-   <span data-ttu-id="c02f7-138">Укажите время ожидания.</span><span class="sxs-lookup"><span data-stu-id="c02f7-138">Specify the time-out.</span></span>  
  
 <span data-ttu-id="c02f7-139">Если источником является файл, задача «Отслеживание событий инструментария WMI» использует диспетчер подключения файлов для подключения к файлу.</span><span class="sxs-lookup"><span data-stu-id="c02f7-139">If the source is a file, the WMI Event Watcher task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="c02f7-140">Дополнительные сведения см. в статье [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c02f7-140">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="c02f7-141">Задача «Отслеживание событий инструментария WMI» использует диспетчер WMI-соединение для подключения к серверу, с которого она считывает данные WMI.</span><span class="sxs-lookup"><span data-stu-id="c02f7-141">The WMI Event Watcher task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="c02f7-142">Дополнительные сведения см. в статье [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c02f7-142">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
 <span data-ttu-id="c02f7-143">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="c02f7-143">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c02f7-144">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c02f7-144">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c02f7-145">Редактор задачи "Отслеживание событий WMI" (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="c02f7-145">WMI Event Watcher Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="c02f7-146">Редактор задачи "Отслеживание событий WMI" (страница "Параметры WMI")</span><span class="sxs-lookup"><span data-stu-id="c02f7-146">WMI Event Watcher Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-event-watcher-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="c02f7-147">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="c02f7-147">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="c02f7-148">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="c02f7-148">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="c02f7-149">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="c02f7-149">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="c02f7-150">Настройка задачи «Отслеживание событий WMI» с помощью программных средств</span><span class="sxs-lookup"><span data-stu-id="c02f7-150">Programmatic Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="c02f7-151">Дополнительные сведения об установке этих свойств программными средствами см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="c02f7-151">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiEventWatcherTask.WmiEventWatcherTask>  
  
  
