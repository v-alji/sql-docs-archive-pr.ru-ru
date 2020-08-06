---
title: Задача "Передача главных хранимых процедур" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfermasterspstask.f1
helpviewer_keywords:
- Transfer Master Stored Procedures task [Integration Services]
ms.assetid: 81702560-48a3-46d1-a469-e41304c7af8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1915a3129eeb6e14c4315c37f2c6c2bf5b0d5412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750059"
---
# <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="e2438-102">Задача «Передача главных хранимых процедур»</span><span class="sxs-lookup"><span data-stu-id="e2438-102">Transfer Master Stored Procedures Task</span></span>
  <span data-ttu-id="e2438-103">Задача "Передача главных хранимых процедур" перемещает одну или несколько пользовательских хранимых процедур между базами данных **master** в экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2438-103">The Transfer Master Stored Procedures task transfers one or more user-defined stored procedures between **master** databases on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e2438-104">Чтобы переместить хранимую процедуру из базы данных **master** , владелец процедуры должен быть dbo.</span><span class="sxs-lookup"><span data-stu-id="e2438-104">To transfer a stored procedure from the **master** database, the owner of the procedure must be dbo.</span></span>  
  
 <span data-ttu-id="e2438-105">Задачу «Передача главных хранимых процедур» можно настроить на перемещение всех хранимых процедур или только определенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="e2438-105">The Transfer Master Stored Procedures task can be configured to transfer all stored procedures or only specified stored procedures.</span></span> <span data-ttu-id="e2438-106">Данная задача не копирует системные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="e2438-106">This task does not copy system stored procedures.</span></span>  
  
 <span data-ttu-id="e2438-107">Главные хранимые процедуры, подлежащие перемещению, уже могут существовать по целевому адресу.</span><span class="sxs-lookup"><span data-stu-id="e2438-107">The master stored procedures to be transferred may already exist on the destination.</span></span> <span data-ttu-id="e2438-108">Задачу «Передача главных хранимых процедур» можно настроить на обработку существующих хранимых процедур следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e2438-108">The Transfer Master Stored Procedures task can be configured to handle existing stored procedures in the following ways:</span></span>  
  
-   <span data-ttu-id="e2438-109">Заменить существующие хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="e2438-109">Overwrite existing stored procedures.</span></span>  
  
-   <span data-ttu-id="e2438-110">Отменить задачу при наличии дубликатов хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="e2438-110">Fail the task when duplicate stored procedures exist.</span></span>  
  
-   <span data-ttu-id="e2438-111">Пропустить дублированные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="e2438-111">Skip duplicate stored procedures.</span></span>  
  
 <span data-ttu-id="e2438-112">Во время выполнения задача «Передача главных хранимых процедур» подключается к исходному и целевому серверам при помощи двух диспетчеров соединений SMO.</span><span class="sxs-lookup"><span data-stu-id="e2438-112">At run time, the Transfer Master Stored Procedures task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="e2438-113">Диспетчеры соединений SMO настроены отдельно от задачи «Передача главных хранимых процедур», и на них имеется ссылка в задаче «Передача главных хранимых процедур».</span><span class="sxs-lookup"><span data-stu-id="e2438-113">The SMO connection managers are configured separately from the Transfer Master Stored Procedures task, and then referenced in the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="e2438-114">Диспетчеры соединений SMO определяют сервер и режим проверки подлинности, используемый для доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="e2438-114">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="e2438-115">Дополнительные сведения см. в статье [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e2438-115">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-stored-procedures-between-instances-of-sql-server"></a><span data-ttu-id="e2438-116">Передача хранимых процедур между экземплярами SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2438-116">Transferring Stored Procedures Between Instances of SQL Server</span></span>  
 <span data-ttu-id="e2438-117">Задача «Передача главных хранимых процедур» поддерживает источник и назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2438-117">The Transfer Master Stored Procedures task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="e2438-118">События</span><span class="sxs-lookup"><span data-stu-id="e2438-118">Events</span></span>  
 <span data-ttu-id="e2438-119">Задача вызывает уведомляющее событие, сообщающее о количестве выполненных перемещений хранимых процедур, и предупреждение при перезаписи хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e2438-119">The task raises an information event that reports the number of stored procedures transferred and a warning event when a stored procedure is overwritten.</span></span>  
  
 <span data-ttu-id="e2438-120">Задача «Передача главных хранимых процедур» не сообщает о прогрессе перемещения; она сообщает только о степени выполнения 0% и 100%.</span><span class="sxs-lookup"><span data-stu-id="e2438-120">The Transfer Master Stored Procedures task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="e2438-121">Значение выполнения</span><span class="sxs-lookup"><span data-stu-id="e2438-121">Execution Value</span></span>  
 <span data-ttu-id="e2438-122">Значение выполнения, определенное в свойстве `ExecutionValue` задачи, возвращает количество перемещенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="e2438-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of stored procedures transferred.</span></span> <span data-ttu-id="e2438-123">После назначения пользовательской переменной свойству `ExecValueVariable` задачи «Передача главных хранимых процедур» сведения о перемещении хранимой процедуры могут стать доступными другим объектам в пакете.</span><span class="sxs-lookup"><span data-stu-id="e2438-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Master Stored Procedures task, information about the stored procedure transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="e2438-124">Дополнительные сведения см. в разделах [Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) и [Использование переменных в пакетах](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="e2438-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="e2438-125">Записи журнала</span><span class="sxs-lookup"><span data-stu-id="e2438-125">Log Entries</span></span>  
 <span data-ttu-id="e2438-126">Задача «Передача главных хранимых процедур» содержит следующие пользовательские записи журнала:</span><span class="sxs-lookup"><span data-stu-id="e2438-126">The Transfer Master Stored Procedures task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="e2438-127">TransferStoredProceduresTaskStartTransferringObjects — данная запись в журнале сообщает о начале перемещения.</span><span class="sxs-lookup"><span data-stu-id="e2438-127">TransferStoredProceduresTaskStartTransferringObjects  This log entry reports that the transfer has started.</span></span> <span data-ttu-id="e2438-128">В записях журнала указывается время запуска.</span><span class="sxs-lookup"><span data-stu-id="e2438-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="e2438-129">TransferSStoredProceduresTaskFinishedTransferringObjects — данная запись в журнале сообщает об окончании перемещения.</span><span class="sxs-lookup"><span data-stu-id="e2438-129">TransferSStoredProceduresTaskFinishedTransferringObjects  This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="e2438-130">В записях журнала указывается время завершения.</span><span class="sxs-lookup"><span data-stu-id="e2438-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="e2438-131">Кроме того, запись журнала для события `OnInformation` сообщает о количестве перемещенных хранимых процедур, а запись журнала для события `OnWarning` фиксирует каждую перезаписываемую хранимую процедуру в целевом месте.</span><span class="sxs-lookup"><span data-stu-id="e2438-131">In addition, a log entry for the `OnInformation` event reports the number of stored procedures that were transferred, and a log entry for the `OnWarning` event is written for each stored procedure on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="e2438-132">Безопасность и разрешения</span><span class="sxs-lookup"><span data-stu-id="e2438-132">Security and Permissions</span></span>  
 <span data-ttu-id="e2438-133">Пользователь должен иметь разрешение на просмотр списка хранимой процедуры в базе данных **master** на источнике и быть членом роли сервера sysadmin или иметь права на созданные хранимые процедуры в базе данных **master** на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="e2438-133">The user must have permission to view the list of stored procedure in the **master** database on the source, and must be a member of the sysadmin server role or have permission to created stored procedures in the **master** database on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-master-stored-procedures-task"></a><span data-ttu-id="e2438-134">Настройка задачи «Передача главных хранимых процедур»</span><span class="sxs-lookup"><span data-stu-id="e2438-134">Configuration of the Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="e2438-135">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="e2438-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e2438-136">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e2438-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e2438-137">Редактор задачи "Передача главных хранимых процедур" (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="e2438-137">Transfer Master Stored Procedures Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="e2438-138">Редактор задачи "Передача главных хранимых процедур" (страница "Хранимые процедуры")</span><span class="sxs-lookup"><span data-stu-id="e2438-138">Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;</span></span>](../transfer-master-stored-procedures-task-editor-stored-procedures-page.md)  
  
-   [<span data-ttu-id="e2438-139">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="e2438-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="e2438-140">Сведения о задании этих свойств программными средствами см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="e2438-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferStoredProceduresTask.TransferStoredProceduresTask>  
  
### <a name="configuring-the-transfer-master-stored-procedures-task-programmatically"></a><span data-ttu-id="e2438-141">Программная настройка задачи «Передача главных хранимых процедур»</span><span class="sxs-lookup"><span data-stu-id="e2438-141">Configuring the Transfer Master Stored Procedures Task Programmatically</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e2438-142">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="e2438-142">Related Tasks</span></span>  
 <span data-ttu-id="e2438-143">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="e2438-143">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e2438-144">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="e2438-144">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2438-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2438-145">See Also</span></span>  
 <span data-ttu-id="e2438-146">[Задача «Передача объектов SQL Server»](transfer-sql-server-objects-task.md) </span><span class="sxs-lookup"><span data-stu-id="e2438-146">[Transfer SQL Server Objects Task](transfer-sql-server-objects-task.md) </span></span>  
 <span data-ttu-id="e2438-147">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="e2438-147">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="e2438-148">Поток управления</span><span class="sxs-lookup"><span data-stu-id="e2438-148">Control Flow</span></span>](control-flow.md)  
  
  
