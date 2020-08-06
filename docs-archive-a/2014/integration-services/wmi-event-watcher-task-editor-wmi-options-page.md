---
title: Редактор задачи «наблюдатель событий WMI» (страница «параметры WMI») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatcher.wmiquery.f1
helpviewer_keywords:
- WMI Event Watcher Task Editor
ms.assetid: 525f3de7-a021-4e52-9939-3a83c88f131a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d7d95501f6442df3723261c970c7a90f48cbdc87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734249"
---
# <a name="wmi-event-watcher-task-editor-wmi-options-page"></a><span data-ttu-id="9d4bb-102">Редактор задачи «Отслеживание событий WMI» (страница «Параметры WMI»)</span><span class="sxs-lookup"><span data-stu-id="9d4bb-102">WMI Event Watcher Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="9d4bb-103">Страница **Параметры инструментария WMI** диалогового окна **Редактор задачи "Отслеживание событий WMI"** используется для указания источника запроса на языке запросов инструментария управления Windows (WQL) и вариантов реакции задачи "Отслеживание событий WMI" на события инструментария Microsoft Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="9d4bb-103">Use the **WMI Options** page of the **WMI Event Watcher Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and how the WMI Event Watcher task responds to Microsoft Windows Instrumentation (WMI) events.</span></span>  
  
 <span data-ttu-id="9d4bb-104">Дополнительные сведения об этой задаче см. в разделе [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span><span class="sxs-lookup"><span data-stu-id="9d4bb-104">To learn about this task, see [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span></span> <span data-ttu-id="9d4bb-105">Дополнительные сведения о языке запросов WQL см. в разделе документации по инструментарию управления Windows [Запросы с использованием языка запросов WQL](https://go.microsoft.com/fwlink/?LinkId=79045)в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="9d4bb-106">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="9d4bb-106">Static Options</span></span>  
 <span data-ttu-id="9d4bb-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="9d4bb-108">Выберите в списке диспетчер WMI-соединений или щелкните \<**New WMI Connection...**> для создания диспетчера подключений.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="9d4bb-109">**См. также:** подробные сведения о [диспетчере WMI-соединений](connection-manager/wmi-connection-manager.md) и о [редакторе диспетчера WMI-соединений](../../2014/integration-services/wmi-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="9d4bb-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="9d4bb-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="9d4bb-111">Выберите тип источника для WQL-запроса, выполняемого данной задачей.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="9d4bb-112">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="9d4bb-113">Значение</span><span class="sxs-lookup"><span data-stu-id="9d4bb-113">Value</span></span>|<span data-ttu-id="9d4bb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9d4bb-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9d4bb-115">**Прямой ввод**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-115">**Direct input**</span></span>|<span data-ttu-id="9d4bb-116">Задайте источник запроса WQL.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-116">Set the source to a WQL query.</span></span> <span data-ttu-id="9d4bb-117">При выборе этого значения отображается динамический параметр **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-117">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="9d4bb-118">**Соединение с файлом**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-118">**File connection**</span></span>|<span data-ttu-id="9d4bb-119">Выберите файл, содержащий запрос WQL.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="9d4bb-120">При выборе этого значения отображается динамический параметр **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-120">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="9d4bb-121">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-121">**Variable**</span></span>|<span data-ttu-id="9d4bb-122">Задайте источник переменной, определяющей запрос WQL.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-122">Set the source to a variable that defines WQL query.</span></span> <span data-ttu-id="9d4bb-123">При выборе этого значения отображается динамический параметр **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-123">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
  
 <span data-ttu-id="9d4bb-124">**ActionAtEvent**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-124">**ActionAtEvent**</span></span>  
 <span data-ttu-id="9d4bb-125">Укажите, будет ли WMI-событие занесено в журнал, и будет ли оно инициировать действие служб [!INCLUDE[ssIS](../includes/ssis-md.md)] или будет только занесено в журнал.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-125">Specify whether the WMI event logs the event and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] action, or only logs the event.</span></span>  
  
 <span data-ttu-id="9d4bb-126">**AfterEvent**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-126">**AfterEvent**</span></span>  
 <span data-ttu-id="9d4bb-127">Укажите, будет ли задача завершена успешно или неудачно после получения ею WMI-события или она будет продолжать ожидать повторного возникновения события.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-127">Specify whether the task succeeds or fails after it receives the WMI event, or if the task continues watching for the event to occur again.</span></span>  
  
 <span data-ttu-id="9d4bb-128">**ActionAtTimeout**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-128">**ActionAtTimeout**</span></span>  
 <span data-ttu-id="9d4bb-129">Укажите, запишет ли задача в журнал истечение времени ожидания WMI-запроса, и инициирует ли в ответ событие служб [!INCLUDE[ssIS](../includes/ssis-md.md)] или только запишет в журнал истечение времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-129">Specify whether the task logs a WMI query time-out and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] event in response, or only logs the time-out.</span></span>  
  
 <span data-ttu-id="9d4bb-130">**AfterTimeout**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-130">**AfterTimeout**</span></span>  
 <span data-ttu-id="9d4bb-131">Укажите, будет ли задача выполнена успешно или неудачно в ответ на истечение времени ожидания или она будет продолжать ожидать возникновения повторного истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-131">Specify whether the task succeeds or fails in response to a time-out, or if the task continues watching for another time-out to recur.</span></span>  
  
 <span data-ttu-id="9d4bb-132">**NumberOfEvents**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-132">**NumberOfEvents**</span></span>  
 <span data-ttu-id="9d4bb-133">Укажите количество событий для ожидания.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-133">Specify the number of events to watch for.</span></span>  
  
 <span data-ttu-id="9d4bb-134">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-134">**Timeout**</span></span>  
 <span data-ttu-id="9d4bb-135">Укажите количество секунд ожидания возникновения события.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-135">Specify the number of seconds to wait for the event to occur.</span></span> <span data-ttu-id="9d4bb-136">Значение 0 означает отсутствие времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-136">A value of 0 means that no time-out is in effect.</span></span>  
  
## <a name="wqlquerysource-dynamic-options"></a><span data-ttu-id="9d4bb-137">Динамические параметры WQLQuerySource</span><span class="sxs-lookup"><span data-stu-id="9d4bb-137">WQLQuerySource Dynamic Options</span></span>  
  
### <a name="wqlquerysource--direct-input"></a><span data-ttu-id="9d4bb-138">WQLQuerySource = Прямой ввод</span><span class="sxs-lookup"><span data-stu-id="9d4bb-138">WQLQuerySource = Direct input</span></span>  
 <span data-ttu-id="9d4bb-139">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-139">**WQLQuerySource**</span></span>  
 <span data-ttu-id="9d4bb-140">Введите запрос или нажмите кнопку с многоточием "(…)" и введите запрос, используя диалоговое окно **Запрос WQL**.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-140">Provide a query, or click the ellipsis button (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysource--file-connection"></a><span data-ttu-id="9d4bb-141">WQLQuerySource = Соединение с файлом</span><span class="sxs-lookup"><span data-stu-id="9d4bb-141">WQLQuerySource = File connection</span></span>  
 <span data-ttu-id="9d4bb-142">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-142">**WQLQuerySource**</span></span>  
 <span data-ttu-id="9d4bb-143">Выберите в списке диспетчер подключений файлов или щелкните \<**New connection...**>, чтобы создать диспетчер подключений.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-143">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="9d4bb-144">**См. также:** подробные сведения о [диспетчере файловых подключений](connection-manager/file-connection-manager.md) и о [редакторе диспетчера файловых подключений](../../2014/integration-services/file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="9d4bb-144">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysource--variable"></a><span data-ttu-id="9d4bb-145">WQLQuerySource = Переменная</span><span class="sxs-lookup"><span data-stu-id="9d4bb-145">WQLQuerySource = Variable</span></span>  
 <span data-ttu-id="9d4bb-146">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="9d4bb-146">**WQLQuerySource**</span></span>  
 <span data-ttu-id="9d4bb-147">Выберите переменную в списке или щелкните \<**New variable...**> для создания переменной.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-147">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="9d4bb-148">**См. также:** подробные сведения о [переменных в службах Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) и о [добавлении переменной](../../2014/integration-services/add-variable.md).</span><span class="sxs-lookup"><span data-stu-id="9d4bb-148">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4bb-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d4bb-149">See Also</span></span>  
 <span data-ttu-id="9d4bb-150">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9d4bb-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9d4bb-151">[Редактор задачи "наблюдатель событий WMI" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9d4bb-151">[WMI Event Watcher Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="9d4bb-152">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="9d4bb-152">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="9d4bb-153">Задача «Модуль чтения данных WMI»</span><span class="sxs-lookup"><span data-stu-id="9d4bb-153">WMI Data Reader Task</span></span>](control-flow/wmi-data-reader-task.md)  
  
  
