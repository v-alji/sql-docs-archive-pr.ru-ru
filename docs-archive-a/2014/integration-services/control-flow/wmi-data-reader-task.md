---
title: Задача "Модуль чтения данных WMI" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Data Reader task [Integration Services]
ms.assetid: dae57067-0275-4ac3-8f34-1b9d169f1112
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1d2f16a28e8b6c94c7275468dedb6d2dfec76d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656509"
---
# <a name="wmi-data-reader-task"></a><span data-ttu-id="2b57f-102">Задача «Модуль чтения данных WMI»</span><span class="sxs-lookup"><span data-stu-id="2b57f-102">WMI Data Reader Task</span></span>
  <span data-ttu-id="2b57f-103">Задача «Модуль чтения данных WMI» использует для выполнения запросов язык WQL, который возвращает от инструментария WMI сведения о системе компьютера.</span><span class="sxs-lookup"><span data-stu-id="2b57f-103">The WMI Data Reader task runs queries using the Windows Management Instrumentation (WMI) Query Language that returns information from WMI about a computer system.</span></span> <span data-ttu-id="2b57f-104">Задача «Модуль чтения данных WMI» может быть использована в следующих целях.</span><span class="sxs-lookup"><span data-stu-id="2b57f-104">You can use the WMI Data Reader task for the following purposes:</span></span>  
  
-   <span data-ttu-id="2b57f-105">Выполнение запросов к журналам событий Windows на локальном или удаленном компьютере, а также запись полученных сведений в файл или переменную.</span><span class="sxs-lookup"><span data-stu-id="2b57f-105">Query the Windows event logs on a local or remote computer and write the information to a file or variable.</span></span>  
  
-   <span data-ttu-id="2b57f-106">Сбор сведений о наличии, состоянии и свойствах компонентов оборудования, а также дальнейшее использование этих сведений для определения необходимости запуска других задач в потоке управления.</span><span class="sxs-lookup"><span data-stu-id="2b57f-106">Obtain information about the presence, state, or properties of hardware components, and then use this information to determine whether other tasks in the control flow should run.</span></span>  
  
-   <span data-ttu-id="2b57f-107">Составление списка приложений с указанием установленной версии.</span><span class="sxs-lookup"><span data-stu-id="2b57f-107">Get a list of applications and determine what version of each application is installed.</span></span>  
  
 <span data-ttu-id="2b57f-108">Настроить задачу «Модуль чтения данных WMI» можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="2b57f-108">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="2b57f-109">Указать, какой диспетчер соединений WMI необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="2b57f-109">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="2b57f-110">Указать источник WQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="2b57f-110">Specify the source of the WQL query.</span></span> <span data-ttu-id="2b57f-111">Запрос может храниться либо в свойствах задачи, либо в переменной или файле вне задачи.</span><span class="sxs-lookup"><span data-stu-id="2b57f-111">The query can be stored in a task property, or the query can be stored outside the task, in a variable or a file.</span></span>  
  
-   <span data-ttu-id="2b57f-112">Указать формат результатов WQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="2b57f-112">Define the format of the WQL query results.</span></span> <span data-ttu-id="2b57f-113">Задача поддерживает результаты в формате таблиц, пар имен значений и свойств или значений свойства.</span><span class="sxs-lookup"><span data-stu-id="2b57f-113">The task supports a table, property name/value pair, or property value format.</span></span>  
  
-   <span data-ttu-id="2b57f-114">Указать целевой объект запроса.</span><span class="sxs-lookup"><span data-stu-id="2b57f-114">Specify the destination of the query.</span></span> <span data-ttu-id="2b57f-115">Целевым объектом запроса может являться переменная или файл.</span><span class="sxs-lookup"><span data-stu-id="2b57f-115">The destination can be a variable or a file.</span></span>  
  
-   <span data-ttu-id="2b57f-116">Указать способ обращения к целевому объекту запроса: перезапись, сохранение или добавление.</span><span class="sxs-lookup"><span data-stu-id="2b57f-116">Indicate whether the query destination is overwritten, kept, or appended.</span></span>  
  
 <span data-ttu-id="2b57f-117">В случае если источником или целевым объектом является файл, задача «Модуль чтения данных WMI» использует диспетчер подключения файлов для подключения к файлу.</span><span class="sxs-lookup"><span data-stu-id="2b57f-117">If the source or destination is a file, the WMI Data Reader task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="2b57f-118">Дополнительные сведения см. в статье [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2b57f-118">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="2b57f-119">Задача «Модуль чтения данных WMI» использует диспетчер WMI-соединений для подключения к серверу, с которого происходит считывание данных WMI.</span><span class="sxs-lookup"><span data-stu-id="2b57f-119">The WMI Data Reader task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="2b57f-120">Дополнительные сведения см. в статье [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2b57f-120">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="wql-query"></a><span data-ttu-id="2b57f-121">Запрос WQL</span><span class="sxs-lookup"><span data-stu-id="2b57f-121">WQL Query</span></span>  
 <span data-ttu-id="2b57f-122">WQL — это разновидность языка SQL с выражениями, поддерживающими уведомления о событиях инструментария WMI и другие функции WMI.</span><span class="sxs-lookup"><span data-stu-id="2b57f-122">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="2b57f-123">Дополнительные сведения о WQL см. в документации по инструментарию управления Windows в [библиотеке MSDN](https://go.microsoft.com/fwlink/?linkid=7022).</span><span class="sxs-lookup"><span data-stu-id="2b57f-123">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b57f-124">Классы WMI отличаются в различных версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="2b57f-124">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="2b57f-125">Приведенный ниже пример WQL-запроса выводит записи событий в журнале приложений.</span><span class="sxs-lookup"><span data-stu-id="2b57f-125">The following WQL query returns entries in the Application log event.</span></span>  
  
```  
SELECT * FROM Win32_NTLogEvent WHERE LogFile = 'Application' AND (SourceName='SQLISService' OR SourceName='SQLISPackage') AND TimeGenerated > '20050117'  
```  
  
 <span data-ttu-id="2b57f-126">Приведенный ниже пример WQL-запроса выводит сведения о логическом диске.</span><span class="sxs-lookup"><span data-stu-id="2b57f-126">The following WQL query returns logical disk information.</span></span>  
  
```  
SELECT FreeSpace, DeviceId, Size, SystemName, Description FROM Win32_LlogicalDisk  
```  
  
 <span data-ttu-id="2b57f-127">Приведенный ниже пример WQL-запроса выводит список исправлений QFE, произведенных в текущей операционной системе.</span><span class="sxs-lookup"><span data-stu-id="2b57f-127">The following WQL query returns a list of the quick fix engineering (QFE) updates to the operating system.</span></span>  
  
```  
Select * FROM Win32_QuickFixEngineering  
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-data-reader-task"></a><span data-ttu-id="2b57f-128">Пользовательские сообщения для ведения журнала, доступные в задаче «Модуль чтения данных WMI»</span><span class="sxs-lookup"><span data-stu-id="2b57f-128">Custom Logging Messages Available on the WMI Data Reader Task</span></span>  
 <span data-ttu-id="2b57f-129">В следующей таблице перечислены пользовательские записи в журнале для задачи «Модуль чтения данных WMI».</span><span class="sxs-lookup"><span data-stu-id="2b57f-129">The following table lists the custom log entries for the WMI Data Reader task.</span></span> <span data-ttu-id="2b57f-130">Дополнительные сведения см. в разделах [Ведение журналов в службах Integration Services (SSIS)](../performance/integration-services-ssis-logging.md) и [Пользовательские сообщения для ведения журнала](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="2b57f-130">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="2b57f-131">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="2b57f-131">Log entry</span></span>|<span data-ttu-id="2b57f-132">Описание</span><span class="sxs-lookup"><span data-stu-id="2b57f-132">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="2b57f-133">Указывает, что задача приступила к чтению данных инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="2b57f-133">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="2b57f-134">Сообщает о WQL-запросе, выполняемом задачей.</span><span class="sxs-lookup"><span data-stu-id="2b57f-134">Reports the WQL query that the task ran.</span></span>|  
  
## <a name="configuration-of-the-wmi-data-reader-task"></a><span data-ttu-id="2b57f-135">Настройка задачи «Модуль чтения данных WMI»</span><span class="sxs-lookup"><span data-stu-id="2b57f-135">Configuration of the WMI Data Reader Task</span></span>  
 <span data-ttu-id="2b57f-136">Свойства задаются программно или через конструктор служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b57f-136">You can set properties programmatically or through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="2b57f-137">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="2b57f-137">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2b57f-138">Редактор задачи "Модуль чтения данных WMI" (страница "Параметры инструментария WMI")</span><span class="sxs-lookup"><span data-stu-id="2b57f-138">WMI Data Reader Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-data-reader-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="2b57f-139">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="2b57f-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="2b57f-140">Сведения о задании этих свойств программными средствами см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="2b57f-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiDataReaderTask.WmiDataReaderTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="2b57f-141">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2b57f-141">Related Tasks</span></span>  
 <span data-ttu-id="2b57f-142">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="2b57f-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="2b57f-143">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="2b57f-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b57f-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b57f-144">See Also</span></span>  
 <span data-ttu-id="2b57f-145">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="2b57f-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="2b57f-146">Поток управления</span><span class="sxs-lookup"><span data-stu-id="2b57f-146">Control Flow</span></span>](control-flow.md)  
  
  
