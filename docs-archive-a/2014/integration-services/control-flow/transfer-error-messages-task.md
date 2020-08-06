---
title: Задача "Передача сообщений об ошибках" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.f1
helpviewer_keywords:
- Transfer Error Messages task [Integration Services]
ms.assetid: da702289-035a-4d14-bd74-04461fbfee1b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952acc28a79fef7e7351c97400e05bc7ba5b9243
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654433"
---
# <a name="transfer-error-messages-task"></a><span data-ttu-id="1719f-102">Задача «Передача сообщений об ошибках»</span><span class="sxs-lookup"><span data-stu-id="1719f-102">Transfer Error Messages Task</span></span>
  <span data-ttu-id="1719f-103">Задача "Передача сообщений об ошибках" передает одно или несколько пользовательских сообщений об ошибках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] между экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1719f-103">The Transfer Error Messages task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined error messages between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1719f-104">Пользовательские сообщения имеют идентификатор, больший или равный 50000.</span><span class="sxs-lookup"><span data-stu-id="1719f-104">User-defined messages are messages with an identifier that is equal to or greater than 50000.</span></span> <span data-ttu-id="1719f-105">Сообщения с идентификаторами, меньшими 50000, являются системными и не могут передаваться с помощью задачи «Передача сообщений об ошибках».</span><span class="sxs-lookup"><span data-stu-id="1719f-105">Messages with an identifier less than 50000 are system error messages, and cannot be transferred by using the Transfer Error Messages task.</span></span>  
  
 <span data-ttu-id="1719f-106">Задачу «Передача сообщений об ошибках» можно настроить на передачу как всех сообщений об ошибках, так и только определенных.</span><span class="sxs-lookup"><span data-stu-id="1719f-106">The Transfer Error Messages task can be configured to transfer all error messages, or only the specified error messages.</span></span> <span data-ttu-id="1719f-107">Пользовательские сообщения об ошибках могут быть на нескольких языках. Задача может быть настроена на передачу сообщений только на выбранных языках.</span><span class="sxs-lookup"><span data-stu-id="1719f-107">User-defined error messages may be available in a number of different languages and the task can be configured to transfer only messages in selected languages.</span></span> <span data-ttu-id="1719f-108">Чтобы передавать на целевой сервер версии сообщения на других языках, на сервере должна существовать англоязычная версия сообщения (кодовая страница 1033, us_english).</span><span class="sxs-lookup"><span data-stu-id="1719f-108">A us_english version of the message that uses code page 1033 must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
 <span data-ttu-id="1719f-109">Таблица sysmessages главной базы данных содержит все системные и пользовательские сообщения об ошибках, используемые в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1719f-109">The sysmessages table in the master database contains all the error messages-both system and user-defined-that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses.</span></span>  
  
 <span data-ttu-id="1719f-110">Передаваемые пользовательские сообщения могут уже существовать в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="1719f-110">The user-defined messages to be transferred may already exist on the destination.</span></span> <span data-ttu-id="1719f-111">Сообщение об ошибке определяется как повторяющееся, если его идентификатор и язык совпадают.</span><span class="sxs-lookup"><span data-stu-id="1719f-111">An error message is defined as a duplicate error message if the identifier and the language are the same.</span></span> <span data-ttu-id="1719f-112">Задача «Передача сообщений об ошибках» может быть настроена на работу с существующими сообщениями об ошибках следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1719f-112">The Transfer Error Messages task can be configured to handle existing error messages in the following ways:</span></span>  
  
-   <span data-ttu-id="1719f-113">Перезаписывать существующие сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1719f-113">Overwrite existing error messages.</span></span>  
  
-   <span data-ttu-id="1719f-114">При обнаружении повторяющегося сообщения завершать задачу сбоем.</span><span class="sxs-lookup"><span data-stu-id="1719f-114">Fail the task when duplicate messages exist.</span></span>  
  
-   <span data-ttu-id="1719f-115">Пропускать повторяющиеся сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1719f-115">Skip duplicate error messages.</span></span>  
  
 <span data-ttu-id="1719f-116">Во время выполнения задача «Передача сообщений об ошибках» подключается к источнику и целевым серверам, используя один или два диспетчера соединений SMO.</span><span class="sxs-lookup"><span data-stu-id="1719f-116">At run time, the Transfer Error Messages task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="1719f-117">Диспетчер соединений SMO настраивается отдельно от задачи «Передача сообщений об ошибках», а затем используется этой задачей.</span><span class="sxs-lookup"><span data-stu-id="1719f-117">The SMO connection manager is configured separately from the Transfer Error Messages task, and then is referenced in the Transfer Error Messages task.</span></span> <span data-ttu-id="1719f-118">Диспетчер соединений SMO определяет сервер и режим проверки подлинности, используемый для доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="1719f-118">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="1719f-119">Дополнительные сведения см. в статье [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1719f-119">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="1719f-120">Задача «Передача сообщений об ошибках» поддерживает источники и целевые объекты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1719f-120">The Transfer Error Messages task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="1719f-121">Ограничений в отношении использования определенных версий источника или целевого объекта не существует.</span><span class="sxs-lookup"><span data-stu-id="1719f-121">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="1719f-122">События</span><span class="sxs-lookup"><span data-stu-id="1719f-122">Events</span></span>  
 <span data-ttu-id="1719f-123">Задача вызывает информационное событие, в котором сообщается о количестве переданных сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1719f-123">The task raises an information event that reports the number of error messages that have been transferred.</span></span>  
  
 <span data-ttu-id="1719f-124">В ходе выполнения задачи «Передача сообщений об ошибках» сведения о состоянии передачи не отображаются, появляются только сообщения о 0% и 100% выполнении.</span><span class="sxs-lookup"><span data-stu-id="1719f-124">The Transfer Error Messages task does not report incremental progress of the error message transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="1719f-125">Значение выполнения</span><span class="sxs-lookup"><span data-stu-id="1719f-125">Execution Value</span></span>  
 <span data-ttu-id="1719f-126">Значение выполнения, определенное свойством задачи `ExecutionValue`, возвращает количество переданных сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1719f-126">The execution value, defined in the `ExecutionValue` property of the task, returns the number of error messages that have been transferred.</span></span> <span data-ttu-id="1719f-127">Сведения о передаче сообщений об ошибках можно сделать доступными другим объектам пакета, если свойству задачи «Передача сообщений об ошибках» `ExecValueVariable` присвоить пользовательскую переменную.</span><span class="sxs-lookup"><span data-stu-id="1719f-127">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Error Message task, information about the error message transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="1719f-128">Дополнительные сведения см. в разделах [Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) и [Использование переменных в пакетах](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1719f-128">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="1719f-129">Записи журнала</span><span class="sxs-lookup"><span data-stu-id="1719f-129">Log Entries</span></span>  
 <span data-ttu-id="1719f-130">Задача «Передача сообщений об ошибках» включает в себя следующие пользовательские записи журнала.</span><span class="sxs-lookup"><span data-stu-id="1719f-130">The Transfer Error Messages task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="1719f-131">TransferErrorMessagesTaskStartTransferringObjects. Это запись журнала о начале передачи.</span><span class="sxs-lookup"><span data-stu-id="1719f-131">TransferErrorMessagesTaskStartTransferringObjects    This log entry reports that the transfer has started.</span></span> <span data-ttu-id="1719f-132">В записях журнала указывается время запуска.</span><span class="sxs-lookup"><span data-stu-id="1719f-132">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="1719f-133">TransferErrorMessagesTaskFinishedTransferringObjects. Это запись журнала об окончании передачи.</span><span class="sxs-lookup"><span data-stu-id="1719f-133">TransferErrorMessagesTaskFinishedTransferringObjects   This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="1719f-134">В записях журнала указывается время завершения.</span><span class="sxs-lookup"><span data-stu-id="1719f-134">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="1719f-135">Также запись журнала о событии `OnInformation` содержит информацию о количестве переданных сообщений об ошибках. Запись журнала для `OnWarning event` сохраняется в обновляемом файле для каждого сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1719f-135">In addition, a log entry for the `OnInformation` event reports the number of error messages that were transferred, and a log entry for the `OnWarning event` is written for each error message on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="1719f-136">Безопасность и разрешения</span><span class="sxs-lookup"><span data-stu-id="1719f-136">Security and Permissions</span></span>  
 <span data-ttu-id="1719f-137">Чтобы создать новое сообщение об ошибке, пользователь, запускающий пакет, должен являться членом роли сервера sysadmin или serveradmin на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="1719f-137">To create new error messages, the user that runs the package must be a member of the sysadmin or serveradmin server role on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-error-messages-task"></a><span data-ttu-id="1719f-138">Настройка задачи «Передача сообщений об ошибках»</span><span class="sxs-lookup"><span data-stu-id="1719f-138">Configuration of the Transfer Error Messages Task</span></span>  
 <span data-ttu-id="1719f-139">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="1719f-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1719f-140">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="1719f-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="1719f-141">Редактор задачи "Передача сообщений об ошибках" (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="1719f-141">Transfer Error Messages Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="1719f-142">Редактор задачи "Передача сообщений об ошибках" (страница "Сообщения")</span><span class="sxs-lookup"><span data-stu-id="1719f-142">Transfer Error Messages Task Editor &#40;Messages Page&#41;</span></span>](../transfer-error-messages-task-editor-messages-page.md)  
  
-   [<span data-ttu-id="1719f-143">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="1719f-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="1719f-144">Сведения о задании этих свойств программными средствами см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="1719f-144">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferErrorMessagesTask.TransferErrorMessagesTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="1719f-145">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1719f-145">Related Tasks</span></span>  
 <span data-ttu-id="1719f-146">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="1719f-146">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="1719f-147">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="1719f-147">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="1719f-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="1719f-148">See Also</span></span>  
 <span data-ttu-id="1719f-149">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="1719f-149">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="1719f-150">Поток управления</span><span class="sxs-lookup"><span data-stu-id="1719f-150">Control Flow</span></span>](control-flow.md)  
  
  
