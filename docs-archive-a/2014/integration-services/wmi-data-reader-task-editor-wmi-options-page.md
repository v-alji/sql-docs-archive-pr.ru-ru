---
title: Редактор задачи "модуль чтения данных WMI" (страница "параметры WMI") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.wmiquery.f1
helpviewer_keywords:
- WMI Data Reader Task Editor
ms.assetid: 4b8d4716-882d-41b0-b77e-e0e2741a2cd5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfb28e7f8f352f708085bf664757391a05869752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667770"
---
# <a name="wmi-data-reader-task-editor-wmi-options-page"></a><span data-ttu-id="82f7f-102">Редактор задачи «Модуль чтения данных WMI» (страница «Параметры инструментария WMI»)</span><span class="sxs-lookup"><span data-stu-id="82f7f-102">WMI Data Reader Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="82f7f-103">Страница **Параметры инструментария WMI** в диалоговом окне **Редактор задачи "Модуль чтения данных WMI"** используется для указания источника запроса WQL (Windows Management Instrumentation Query Language) и назначения результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="82f7f-103">Use the **WMI Options** page of the **WMI Data Reader Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and the destination of the query result.</span></span>  
  
 <span data-ttu-id="82f7f-104">Дополнительные сведения об этой задаче см. в разделе [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span><span class="sxs-lookup"><span data-stu-id="82f7f-104">To learn about this task, see [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span></span> <span data-ttu-id="82f7f-105">Дополнительные сведения о языке запросов WQL см. в разделе документации по инструментарию управления Windows [Запросы с использованием языка запросов WQL](https://go.microsoft.com/fwlink/?LinkId=79045)в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="82f7f-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="82f7f-106">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="82f7f-106">Static Options</span></span>  
 <span data-ttu-id="82f7f-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="82f7f-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="82f7f-108">Выберите в списке диспетчер WMI-соединений или щелкните \<**New WMI Connection...**> для создания диспетчера подключений.</span><span class="sxs-lookup"><span data-stu-id="82f7f-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="82f7f-109">**См. также:** подробные сведения о [диспетчере WMI-соединений](connection-manager/wmi-connection-manager.md) и о [редакторе диспетчера WMI-соединений](../../2014/integration-services/wmi-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="82f7f-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="82f7f-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="82f7f-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="82f7f-111">Выберите тип источника для WQL-запроса, выполняемого данной задачей.</span><span class="sxs-lookup"><span data-stu-id="82f7f-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="82f7f-112">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="82f7f-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="82f7f-113">Значение</span><span class="sxs-lookup"><span data-stu-id="82f7f-113">Value</span></span>|<span data-ttu-id="82f7f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="82f7f-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82f7f-115">**Прямой ввод**</span><span class="sxs-lookup"><span data-stu-id="82f7f-115">**Direct input**</span></span>|<span data-ttu-id="82f7f-116">Задайте источник запроса WQL.</span><span class="sxs-lookup"><span data-stu-id="82f7f-116">Set the source to a WQL query.</span></span> <span data-ttu-id="82f7f-117">При выборе этого значения отображается динамический параметр **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="82f7f-117">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="82f7f-118">**Соединение с файлом**</span><span class="sxs-lookup"><span data-stu-id="82f7f-118">**File connection**</span></span>|<span data-ttu-id="82f7f-119">Выберите файл, содержащий запрос WQL.</span><span class="sxs-lookup"><span data-stu-id="82f7f-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="82f7f-120">При выборе этого значения отображается динамический параметр **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="82f7f-120">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="82f7f-121">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="82f7f-121">**Variable**</span></span>|<span data-ttu-id="82f7f-122">Задайте источник переменной, определяющей запрос WQL.</span><span class="sxs-lookup"><span data-stu-id="82f7f-122">Set the source to a variable that defines the WQL query.</span></span> <span data-ttu-id="82f7f-123">При выборе этого значения отображается динамический параметр **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="82f7f-123">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
  
 <span data-ttu-id="82f7f-124">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="82f7f-124">**OutputType**</span></span>  
 <span data-ttu-id="82f7f-125">Укажите тип выходных данных: таблица данных, значение свойства или имя и значение свойства.</span><span class="sxs-lookup"><span data-stu-id="82f7f-125">Specify whether the output should be a data table, property value, or property name and value.</span></span>  
  
 <span data-ttu-id="82f7f-126">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="82f7f-126">**OverwriteDestination**</span></span>  
 <span data-ttu-id="82f7f-127">Указывает, следует ли сохранить, перезаписать или добавить данные в целевом файле или переменной.</span><span class="sxs-lookup"><span data-stu-id="82f7f-127">Specifies whether to keep, overwrite, or append to the original data in the destination file or variable.</span></span>  
  
 <span data-ttu-id="82f7f-128">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="82f7f-128">**DestinationType**</span></span>  
 <span data-ttu-id="82f7f-129">Выберите тип назначения запроса WQL, выполняемого данной задачей.</span><span class="sxs-lookup"><span data-stu-id="82f7f-129">Select the destination type of the WQL query that the task runs.</span></span> <span data-ttu-id="82f7f-130">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="82f7f-130">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="82f7f-131">Значение</span><span class="sxs-lookup"><span data-stu-id="82f7f-131">Value</span></span>|<span data-ttu-id="82f7f-132">Описание</span><span class="sxs-lookup"><span data-stu-id="82f7f-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82f7f-133">**Соединение с файлом**</span><span class="sxs-lookup"><span data-stu-id="82f7f-133">**File connection**</span></span>|<span data-ttu-id="82f7f-134">Выберите файл, в котором будут храниться результаты запроса WQL.</span><span class="sxs-lookup"><span data-stu-id="82f7f-134">Select a file to save the results of the WQL query in.</span></span> <span data-ttu-id="82f7f-135">При выборе этого значения отображается динамический параметр **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="82f7f-135">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
|<span data-ttu-id="82f7f-136">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="82f7f-136">**Variable**</span></span>|<span data-ttu-id="82f7f-137">Задайте переменную, в которой будут храниться результаты запроса WQL.</span><span class="sxs-lookup"><span data-stu-id="82f7f-137">Set the variable to store the results of the WQL query in.</span></span> <span data-ttu-id="82f7f-138">При выборе этого значения отображается динамический параметр **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="82f7f-138">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
  
## <a name="wqlquerysourcetype-dynamic-options"></a><span data-ttu-id="82f7f-139">Динамические параметры WQLQuerySourceType</span><span class="sxs-lookup"><span data-stu-id="82f7f-139">WQLQuerySourceType Dynamic Options</span></span>  
  
### <a name="wqlquerysourcetype--direct-input"></a><span data-ttu-id="82f7f-140">WQLQuerySourceType = Прямой ввод</span><span class="sxs-lookup"><span data-stu-id="82f7f-140">WQLQuerySourceType = Direct input</span></span>  
 <span data-ttu-id="82f7f-141">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="82f7f-141">**WQLQuerySource**</span></span>  
 <span data-ttu-id="82f7f-142">Введите запрос или нажмите кнопку многоточия (…) и введите запрос, используя диалоговое окно **Запрос WQL**.</span><span class="sxs-lookup"><span data-stu-id="82f7f-142">Provide a query, or click the ellipsis (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysourcetype--file-connection"></a><span data-ttu-id="82f7f-143">WQLQuerySourceType = Соединение с файлом</span><span class="sxs-lookup"><span data-stu-id="82f7f-143">WQLQuerySourceType = File connection</span></span>  
 <span data-ttu-id="82f7f-144">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="82f7f-144">**WQLQuerySource**</span></span>  
 <span data-ttu-id="82f7f-145">Выберите в списке диспетчер подключений файлов или щелкните \<**New connection...**>, чтобы создать диспетчер подключений.</span><span class="sxs-lookup"><span data-stu-id="82f7f-145">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="82f7f-146">**См. также:** подробные сведения о [диспетчере файловых подключений](connection-manager/file-connection-manager.md) и о [редакторе диспетчера файловых подключений](../../2014/integration-services/file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="82f7f-146">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysourcetype--variable"></a><span data-ttu-id="82f7f-147">WQLQuerySourceType = Переменная</span><span class="sxs-lookup"><span data-stu-id="82f7f-147">WQLQuerySourceType = Variable</span></span>  
 <span data-ttu-id="82f7f-148">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="82f7f-148">**WQLQuerySource**</span></span>  
 <span data-ttu-id="82f7f-149">Выберите переменную в списке или щелкните \<**New variable...**> для создания переменной.</span><span class="sxs-lookup"><span data-stu-id="82f7f-149">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="82f7f-150">**См. также:** подробные сведения о [переменных в службах Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) и о [добавлении переменной](../../2014/integration-services/add-variable.md).</span><span class="sxs-lookup"><span data-stu-id="82f7f-150">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="destinationtype-dynamic-options"></a><span data-ttu-id="82f7f-151">Динамические параметры DestinationType</span><span class="sxs-lookup"><span data-stu-id="82f7f-151">DestinationType Dynamic Options</span></span>  
  
### <a name="destinationtype--file-connection"></a><span data-ttu-id="82f7f-152">DestinationType = Соединение с файлом</span><span class="sxs-lookup"><span data-stu-id="82f7f-152">DestinationType = File connection</span></span>  
 <span data-ttu-id="82f7f-153">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="82f7f-153">**Destination**</span></span>  
 <span data-ttu-id="82f7f-154">Выберите в списке диспетчер подключений файлов или щелкните \<**New connection...**>, чтобы создать диспетчер подключений.</span><span class="sxs-lookup"><span data-stu-id="82f7f-154">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="82f7f-155">**См. также:** подробные сведения о [диспетчере файловых подключений](connection-manager/file-connection-manager.md) и о [редакторе диспетчера файловых подключений](../../2014/integration-services/file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="82f7f-155">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="destinationtype--variable"></a><span data-ttu-id="82f7f-156">DestinationType = Переменная</span><span class="sxs-lookup"><span data-stu-id="82f7f-156">DestinationType = Variable</span></span>  
 <span data-ttu-id="82f7f-157">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="82f7f-157">**Destination**</span></span>  
 <span data-ttu-id="82f7f-158">Выберите переменную в списке или щелкните \<**New variable...**> для создания переменной.</span><span class="sxs-lookup"><span data-stu-id="82f7f-158">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="82f7f-159">**См. также:** подробные сведения о [переменных в службах Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) и о [добавлении переменной](../../2014/integration-services/add-variable.md).</span><span class="sxs-lookup"><span data-stu-id="82f7f-159">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f7f-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="82f7f-160">See Also</span></span>  
 <span data-ttu-id="82f7f-161">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="82f7f-161">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="82f7f-162">[Редактор задачи "модуль чтения данных WMI" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="82f7f-162">[WMI Data Reader Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="82f7f-163">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="82f7f-163">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="82f7f-164">Задача «Отслеживание событий WMI»</span><span class="sxs-lookup"><span data-stu-id="82f7f-164">WMI Event Watcher Task</span></span>](control-flow/wmi-event-watcher-task.md)  
  
  
