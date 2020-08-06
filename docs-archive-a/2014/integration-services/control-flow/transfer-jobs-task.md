---
title: Задача "Передача заданий" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.f1
helpviewer_keywords:
- Transfer Jobs task [Integration Services]
ms.assetid: 1bf33885-9c5b-47e4-a549-f5920b66a1de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d692934d5f7c8c1449b123ee8b9caf1d8bb34744
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654432"
---
# <a name="transfer-jobs-task"></a><span data-ttu-id="63927-102">Задача «Передача заданий»</span><span class="sxs-lookup"><span data-stu-id="63927-102">Transfer Jobs Task</span></span>
  <span data-ttu-id="63927-103">Задача «Передача заданий» служит для передачи одного или нескольких заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] между экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63927-103">The Transfer Jobs task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="63927-104">Задачу «Передача заданий» можно настроить на передачу всех или только определенных заданий.</span><span class="sxs-lookup"><span data-stu-id="63927-104">The Transfer Jobs task can be configured to transfer all jobs, or only specified jobs.</span></span> <span data-ttu-id="63927-105">Можно также указать, будут ли переданные задания доступны в месте назначения.</span><span class="sxs-lookup"><span data-stu-id="63927-105">You can also indicate whether the transferred jobs are enabled at the destination.</span></span>  
  
 <span data-ttu-id="63927-106">Задания, подлежащие передаче, могут уже существовать в месте назначения.</span><span class="sxs-lookup"><span data-stu-id="63927-106">The jobs to be transferred may already exist on the destination.</span></span> <span data-ttu-id="63927-107">Задачу «Передача заданий» можно настроить на обработку существующих задач одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="63927-107">The Transfer Jobs task can be configured to handle existing jobs in the following ways:</span></span>  
  
-   <span data-ttu-id="63927-108">Перезаписать существующие задания.</span><span class="sxs-lookup"><span data-stu-id="63927-108">Overwrite existing jobs.</span></span>  
  
-   <span data-ttu-id="63927-109">Аварийно завершить задачу при наличии дубликатов заданий.</span><span class="sxs-lookup"><span data-stu-id="63927-109">Fail the task when duplicate jobs exist.</span></span>  
  
-   <span data-ttu-id="63927-110">Пропустить дубликаты заданий.</span><span class="sxs-lookup"><span data-stu-id="63927-110">Skip duplicate jobs.</span></span>  
  
 <span data-ttu-id="63927-111">Во время выполнения задача «Передача заданий» подключается к исходному и целевому серверу, используя один или два диспетчера соединений SMO.</span><span class="sxs-lookup"><span data-stu-id="63927-111">At run time, the Transfer Jobs task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="63927-112">Диспетчер соединений SMO настраивается независимо от задачи «Передача заданий», но задача будет на него ссылаться.</span><span class="sxs-lookup"><span data-stu-id="63927-112">The SMO connection manager is configured separately from the Transfer Jobs task, and then is referenced in the Transfer Jobs task.</span></span> <span data-ttu-id="63927-113">Диспетчер соединений SMO определяет сервер и режим проверки подлинности, используемый для доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="63927-113">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="63927-114">Дополнительные сведения см. в статье [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="63927-114">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-jobs-between-instances-of-sql-server"></a><span data-ttu-id="63927-115">Передача заданий между экземплярами SQL Server</span><span class="sxs-lookup"><span data-stu-id="63927-115">Transferring Jobs Between Instances of SQL Server</span></span>  
 <span data-ttu-id="63927-116">Задача «Передача заданий» поддерживает исходные серверы и серверы назначения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63927-116">The Transfer Jobs task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="63927-117">Ограничений в отношении использования определенных версий источника или целевого объекта не существует.</span><span class="sxs-lookup"><span data-stu-id="63927-117">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="63927-118">События</span><span class="sxs-lookup"><span data-stu-id="63927-118">Events</span></span>  
 <span data-ttu-id="63927-119">Задача «Передача заданий» инициирует уведомляющее событие, сообщающее число переданных заданий, а также событие-предупреждение в случае, когда задание перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="63927-119">The Transfer Jobs task raises an information event that reports the number of jobs transferred and a warning event when a job is overwritten.</span></span> <span data-ttu-id="63927-120">Задача не сообщает о ходе передачи задания; она сообщает лишь о выполнении 0% и 100%.</span><span class="sxs-lookup"><span data-stu-id="63927-120">The task does not report incremental progress of the job transfer; it reports only 0% and 100% completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="63927-121">Значение выполнения</span><span class="sxs-lookup"><span data-stu-id="63927-121">Execution Value</span></span>  
 <span data-ttu-id="63927-122">Значение выполнения, определяемое свойством `ExecutionValue` задачи, возвращает число переданных заданий.</span><span class="sxs-lookup"><span data-stu-id="63927-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of jobs that are transferred.</span></span> <span data-ttu-id="63927-123">Назначив пользовательскую переменную значению свойства `ExecValueVariable` задачи «Передача заданий», можно сделать сведения о передаче заданий доступными для других объектов пакета.</span><span class="sxs-lookup"><span data-stu-id="63927-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Jobs task, information about the job transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="63927-124">Дополнительные сведения см. в разделах [Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) и [Использование переменных в пакетах](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="63927-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="63927-125">Записи журнала</span><span class="sxs-lookup"><span data-stu-id="63927-125">Log Entries</span></span>  
 <span data-ttu-id="63927-126">Задача «Передача заданий» позволяет настраивать запись в журнал следующих событий:</span><span class="sxs-lookup"><span data-stu-id="63927-126">The Transfer Jobs task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="63927-127">TransferJobsTaskStarTransferringObjects   Эта запись журнала сообщает о начале передачи.</span><span class="sxs-lookup"><span data-stu-id="63927-127">TransferJobsTaskStarTransferringObjects   This log entry reports that the transfer has started.</span></span> <span data-ttu-id="63927-128">В записях журнала указывается время запуска.</span><span class="sxs-lookup"><span data-stu-id="63927-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="63927-129">TransferJobsTaskStarTransferringObjects   Эта запись журнала сообщает об окончании передачи.</span><span class="sxs-lookup"><span data-stu-id="63927-129">TransferJobsTaskFinishedTransferringObjects    This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="63927-130">В записях журнала указывается время завершения.</span><span class="sxs-lookup"><span data-stu-id="63927-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="63927-131">Кроме того, запись журнала о событии `OnInformation` сообщает число переданных заданий, а запись журнала о событии `OnWarning` производится при перезаписи каждого задания, находящегося на сервере назначения.</span><span class="sxs-lookup"><span data-stu-id="63927-131">In addition, a log entry for the `OnInformation` event reports the number of jobs that were transferred and a log entry for the `OnWarning` event is written for each job on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="63927-132">Безопасность и разрешения</span><span class="sxs-lookup"><span data-stu-id="63927-132">Security and Permissions</span></span>  
 <span data-ttu-id="63927-133">Чтобы передавать задания, пользователь должен быть членом предопределенной роли сервера sysadmin или членом одной из предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для базы данных msdb как в экземпляре-источнике, так и в экземпляре назначения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63927-133">To transfer jobs, the user must be a member of the sysadmin fixed server role or one of the fixed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles on the msdb database on the both the source and destination instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="configuration-of-the-transfer-jobs-task"></a><span data-ttu-id="63927-134">Настройка задачи «Передача заданий»</span><span class="sxs-lookup"><span data-stu-id="63927-134">Configuration of the Transfer Jobs Task</span></span>  
 <span data-ttu-id="63927-135">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="63927-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="63927-136">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="63927-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="63927-137">Редактор задачи "Передача заданий" (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="63927-137">Transfer Jobs Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="63927-138">Редактор задачи "Передача заданий" (страница "Задания")</span><span class="sxs-lookup"><span data-stu-id="63927-138">Transfer Jobs Task Editor &#40;Jobs Page&#41;</span></span>](../transfer-jobs-task-editor-jobs-page.md)  
  
-   [<span data-ttu-id="63927-139">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="63927-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="63927-140">Дополнительные сведения об установке этих свойств программным путем см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="63927-140">For information about programmatically setting these properties, click the of the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferJobsTask.TransferJobsTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="63927-141">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="63927-141">Related Tasks</span></span>  
 <span data-ttu-id="63927-142">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="63927-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="63927-143">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="63927-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="63927-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="63927-144">See Also</span></span>  
 <span data-ttu-id="63927-145">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="63927-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="63927-146">Поток управления</span><span class="sxs-lookup"><span data-stu-id="63927-146">Control Flow</span></span>](control-flow.md)  
  
  
