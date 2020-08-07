---
title: Примеры задачи "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], examples
- examples [Integration Services]
- SSIS Script task, examples
ms.assetid: b0dd77ee-ee11-4cd9-87aa-61dd67f2fe1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 920d2ee5cc2e64db1048d10522d9be644794e55b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732734"
---
# <a name="script-task-examples"></a><span data-ttu-id="b1117-102">Примеры задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-102">Script Task Examples</span></span>
  <span data-ttu-id="b1117-103">Задача «Скрипт» — это многоцелевой инструмент, который можно использовать в пакете для выполнения практически любых действий, которые невозможно произвести с помощью задач, поставляемых со службами [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1117-103">The Script task is a multi-purpose tool that you can use in a package to fill almost any requirement that is not met by the tasks included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="b1117-104">В этом разделе приведены образцы кода задачи «Скрипт», в которых демонстрируются некоторые элементы доступной функциональности.</span><span class="sxs-lookup"><span data-stu-id="b1117-104">This topic lists Script task code samples that demonstrate some of the available functionality.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1117-105">Если необходимо создать задачи, пригодные для повторного использования в нескольких пакетах, рассмотрите возможность использования кода в этих образцах как отправной точки для создания пользовательских задач.</span><span class="sxs-lookup"><span data-stu-id="b1117-105">If you want to create tasks that you can more easily reuse across multiple packages, consider using the code in these Script task samples as the starting point for custom tasks.</span></span> <span data-ttu-id="b1117-106">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="b1117-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1117-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b1117-107">In This Section</span></span>  
  
### <a name="example-topics"></a><span data-ttu-id="b1117-108">Разделы с образцами</span><span class="sxs-lookup"><span data-stu-id="b1117-108">Example Topics</span></span>  
 <span data-ttu-id="b1117-109">В этом разделе содержатся примеры кода, демонстрирующие различные варианты использования классов платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], которые можно включить в задачу «Скрипт» служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1117-109">This section contains code examples that demonstrate various uses of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that you can incorporate into an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task:</span></span>  
  
 [<span data-ttu-id="b1117-110">Обнаружение пустого неструктурированного файла в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-110">Detecting an Empty Flat File with the Script Task</span></span>](../extending-packages-scripting-task-examples/detecting-an-empty-flat-file-with-the-script-task.md)  
 <span data-ttu-id="b1117-111">Проверяет неструктурированный файл, чтобы определить, содержит ли он строки данных, и сохраняет результат в переменную для использования в ветвлении потока управления.</span><span class="sxs-lookup"><span data-stu-id="b1117-111">Checks a flat file to determine whether it contains rows of data, and saves the result to a variable for use in control flow branching.</span></span>  
  
 [<span data-ttu-id="b1117-112">Составление списка для цикла по каждому элементу в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-112">Gathering a List for the ForEach Loop with the Script Task</span></span>](../extending-packages-scripting-task-examples/gathering-a-list-for-the-foreach-loop-with-the-script-task.md)  
 <span data-ttu-id="b1117-113">Собирает список файлов, отвечающих заданным пользователем критериям, и заполняет переменную для использования в дальнейшем в перечислителе по объекту из переменной.</span><span class="sxs-lookup"><span data-stu-id="b1117-113">Gathers a list of files that meet user-specified criteria, and populates a variable for later use by the Foreach from Variable Enumerator.</span></span>  
  
 [<span data-ttu-id="b1117-114">Запрос Active Directory в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-114">Querying the Active Directory with the Script Task</span></span>](../extending-packages-scripting-task-examples/querying-the-active-directory-with-the-script-task.md)  
 <span data-ttu-id="b1117-115">Извлекает сведения о пользователе из службы каталогов Active Directory на основе значения переменной служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] с использованием классов в пространстве имен System.DirectoryServices.</span><span class="sxs-lookup"><span data-stu-id="b1117-115">Retrieves user information from Active Directory based on the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, by using classes in the System.DirectoryServices namespace.</span></span>  
  
 [<span data-ttu-id="b1117-116">Наблюдение за счетчиками производительности в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-116">Monitoring Performance Counters with the Script Task</span></span>](../extending-packages-scripting-task-examples/monitoring-performance-counters-with-the-script-task.md)  
 <span data-ttu-id="b1117-117">Создает пользовательский счетчик производительности, который можно использовать для отслеживания хода выполнения пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], применяя классы в пространстве имен System.Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="b1117-117">Creates a custom performance counter that can be used to track the execution progress of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package, by using classes in the System.Diagnostics namespace.</span></span>  
  
 [<span data-ttu-id="b1117-118">Работа с изображениями в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-118">Working with Images with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md)  
 <span data-ttu-id="b1117-119">Выполняет сжатие изображений в формат JPEG и создает из них эскизы изображений, используя классы в пространстве имен System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="b1117-119">Compresses images into the JPEG format and creates thumbnail images from them, by using classes in the System.Drawing namespace.</span></span>  
  
 [<span data-ttu-id="b1117-120">Обнаружение установленных принтеров с помощью задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-120">Finding Installed Printers with the Script Task</span></span>](../extending-packages-scripting-task-examples/finding-installed-printers-with-the-script-task.md)  
 <span data-ttu-id="b1117-121">Осуществляет поиск установленных принтеров, поддерживающих определенный размер бумаги, используя классы в пространстве имен System.Drawing.Printing.</span><span class="sxs-lookup"><span data-stu-id="b1117-121">Locates installed printers that support a specific paper size, by using classes in the System.Drawing.Printing namespace.</span></span>  
  
 [<span data-ttu-id="b1117-122">Отправка почтового сообщения в формате HTML с помощью задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-122">Sending an HTML Mail Message with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-an-html-mail-message-with-the-script-task.md)  
 <span data-ttu-id="b1117-123">Отправляет почтовое сообщение в формате HTML вместо обычного текстового формата.</span><span class="sxs-lookup"><span data-stu-id="b1117-123">Sends a mail message in HTML format instead of plain text format.</span></span>  
  
 [<span data-ttu-id="b1117-124">Работа с файлами Excel в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-124">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
 <span data-ttu-id="b1117-125">Создает список листов в файле Excel и проверяет существование определенного листа.</span><span class="sxs-lookup"><span data-stu-id="b1117-125">Lists the worksheets in an Excel file and checks for the existence of a specific worksheet.</span></span>  
  
 [<span data-ttu-id="b1117-126">Отправка в удаленную закрытую очередь сообщений в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-126">Sending to a Remote Private Message Queue with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-to-a-remote-private-message-queue-with-the-script-task.md)  
 <span data-ttu-id="b1117-127">Отправляет сообщение в удаленную закрытую очередь сообщений.</span><span class="sxs-lookup"><span data-stu-id="b1117-127">Sends a message to a remote private message queue.</span></span>  
  
### <a name="other-examples"></a><span data-ttu-id="b1117-128">Другие образцы</span><span class="sxs-lookup"><span data-stu-id="b1117-128">Other Examples</span></span>  
 <span data-ttu-id="b1117-129">В разделах, перечисленных ниже, также содержатся примеры кода для использования с задачей «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="b1117-129">The following topics also contain code examples for use with the Script task:</span></span>  
  
 [<span data-ttu-id="b1117-130">Использование переменных в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-130">Using Variables in the Script Task</span></span>](../extending-packages-scripting/task/using-variables-in-the-script-task.md)  
 <span data-ttu-id="b1117-131">Запрашивает у пользователя подтверждение продолжения работы пакета на основе значения переменной пакета, которое может превысить предел, указанный в другой переменной.</span><span class="sxs-lookup"><span data-stu-id="b1117-131">Asks the user for confirmation of whether the package should continue to run, based on the value of a package variable that may exceed the limit specified in another variable.</span></span>  
  
 [<span data-ttu-id="b1117-132">Соединение с источниками данных в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-132">Connecting to Data Sources in the Script Task</span></span>](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md)  
 <span data-ttu-id="b1117-133">Извлекает соединение или данные соединения из диспетчеров соединений, определенных в пакете.</span><span class="sxs-lookup"><span data-stu-id="b1117-133">Retrieves a connection or connection information from connection managers defined in the package.</span></span>  
  
 [<span data-ttu-id="b1117-134">Вызов событий в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-134">Raising Events in the Script Task</span></span>](../extending-packages-scripting/task/raising-events-in-the-script-task.md)  
 <span data-ttu-id="b1117-135">Выдает ошибку, предупреждение или информационное сообщение в зависимости от состояния соединения с Интернетом на сервере.</span><span class="sxs-lookup"><span data-stu-id="b1117-135">Raises an error, a warning, or an informational message based on the status of the Internet connection on the server.</span></span>  
  
 [<span data-ttu-id="b1117-136">Ведение журнала в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b1117-136">Logging in the Script Task</span></span>](../extending-packages-scripting/task/logging-in-the-script-task.md)  
 <span data-ttu-id="b1117-137">Регистрирует число элементов, обработанных задачей в активных регистраторах.</span><span class="sxs-lookup"><span data-stu-id="b1117-137">Logs the number of items processed by the task to enabled log providers.</span></span>  
  
<span data-ttu-id="b1117-138">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b1117-138">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b1117-139">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="b1117-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b1117-140">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="b1117-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b1117-141">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="b1117-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
