---
title: Задача "Передача имен входа" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.f1
helpviewer_keywords:
- Transfer Logins task [Integration Services]
ms.assetid: 1df60fd6-c019-405d-8155-c330dbac2cc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d42d39b6cc7c2f350e3e3adc774be23934981369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654430"
---
# <a name="transfer-logins-task"></a><span data-ttu-id="4f412-102">Задача «Передача имен входа»</span><span class="sxs-lookup"><span data-stu-id="4f412-102">Transfer Logins Task</span></span>
  <span data-ttu-id="4f412-103">Задача «Передача имен входа» служит для передачи одного или нескольких имен входа между экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f412-103">The Transfer Logins task transfers one or more logins between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="transfer-logins-between-instances-of-sql-server"></a><span data-ttu-id="4f412-104">Передача имен входа между экземплярами SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f412-104">Transfer Logins Between Instances of SQL Server</span></span>  
 <span data-ttu-id="4f412-105">Задача «Передача имен входа» поддерживает исходные и целевые серверы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f412-105">The Transfer Logins task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="4f412-106">События</span><span class="sxs-lookup"><span data-stu-id="4f412-106">Events</span></span>  
 <span data-ttu-id="4f412-107">Задача инициирует уведомляющее событие с сообщением числа переданных имен входа, а также событие-предупреждение в случае, когда имя перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="4f412-107">The task raises an information event that reports the number of logins transferred and a warning event when a login is overwritten.</span></span>  
  
 <span data-ttu-id="4f412-108">Задача «Передача имен входа» не сообщает о ходе выполнения передачи имен; она сообщает лишь о выполнении 0% и 100%.</span><span class="sxs-lookup"><span data-stu-id="4f412-108">The Transfer Logins task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="4f412-109">Значение выполнения</span><span class="sxs-lookup"><span data-stu-id="4f412-109">Execution Value</span></span>  
 <span data-ttu-id="4f412-110">Значение выполнения, определяемое свойством `ExecutionValue` задачи, возвращает число переданных имен входа.</span><span class="sxs-lookup"><span data-stu-id="4f412-110">The execution value, defined in the `ExecutionValue` property of the task, returns the number of logins transferred.</span></span> <span data-ttu-id="4f412-111">Назначив пользовательскую переменную в качестве свойства `ExecValueVariable` задачи «Передача имен входа», можно сделать сведения о передаче имен входа доступными для других объектов пакета.</span><span class="sxs-lookup"><span data-stu-id="4f412-111">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Logins task, information about the login transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="4f412-112">Дополнительные сведения см. в разделах [Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) и [Использование переменных в пакетах](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4f412-112">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="4f412-113">Записи журнала</span><span class="sxs-lookup"><span data-stu-id="4f412-113">Log Entries</span></span>  
 <span data-ttu-id="4f412-114">Задача «Передача имен входа» позволяет настраивать запись в журнал следующих событий:</span><span class="sxs-lookup"><span data-stu-id="4f412-114">The Transfer Logins task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="4f412-115">TransferJobsTaskStarTransferringObjects   Эта запись журнала сообщает о начале передачи.</span><span class="sxs-lookup"><span data-stu-id="4f412-115">TransferLoginsTaskStarTransferringObjects    This log entry reports the transfer has started.</span></span> <span data-ttu-id="4f412-116">В записях журнала указывается время запуска.</span><span class="sxs-lookup"><span data-stu-id="4f412-116">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="4f412-117">TransferJobsTaskStarTransferringObjects   Эта запись журнала сообщает об окончании передачи.</span><span class="sxs-lookup"><span data-stu-id="4f412-117">TransferLoginsTaskFinishedTransferringObjects   This log entry reports the transfer has completed.</span></span> <span data-ttu-id="4f412-118">В записях журнала указывается время завершения.</span><span class="sxs-lookup"><span data-stu-id="4f412-118">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="4f412-119">Кроме того, запись журнала о событии `OnInformation` сообщает число переданных имен входа, а запись журнала о событии `OnWarning` производится для каждого имени, перезаписанного на сервере назначения.</span><span class="sxs-lookup"><span data-stu-id="4f412-119">In addition, a log entry for the `OnInformation` event reports the number of logins that were transferred, and a log entry for the `OnWarning` event is written for each login on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="4f412-120">Безопасность и разрешения</span><span class="sxs-lookup"><span data-stu-id="4f412-120">Security and Permissions</span></span>  
 <span data-ttu-id="4f412-121">Для просмотра имен входа на сервере-источнике и для создания их на целевом сервере пользователь должен быть членом роли сервера sysadmin на обоих серверах.</span><span class="sxs-lookup"><span data-stu-id="4f412-121">To browse logins on the source server and to create logins on the destination server, the user must be a member of the sysadmin server role on both servers.</span></span>  
  
## <a name="configuration-of-the-transfer-logins-task"></a><span data-ttu-id="4f412-122">Настройка задачи «Передача имен входа»</span><span class="sxs-lookup"><span data-stu-id="4f412-122">Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="4f412-123">Задачу «Передача имен входа» можно настроить на передачу всех имен входа, только определенных имен или же имен, имеющих доступ к определенной базе данных.</span><span class="sxs-lookup"><span data-stu-id="4f412-123">The Transfer Logins task can be configured to transfer all logins, only specified logins, or all logins that have access to specified databases only.</span></span> <span data-ttu-id="4f412-124">Имя входа sa передать нельзя.</span><span class="sxs-lookup"><span data-stu-id="4f412-124">The sa login cannot be transferred.</span></span> <span data-ttu-id="4f412-125">Имя входа sa можно переименовать, однако даже переименованное имя входа sa передать нельзя.</span><span class="sxs-lookup"><span data-stu-id="4f412-125">The sa login may be renamed; however, the renamed sa login cannot be transferred either.</span></span>  
  
 <span data-ttu-id="4f412-126">Можно также указать, должна ли задача копировать идентификаторы безопасности (SID), связанные с именами входа.</span><span class="sxs-lookup"><span data-stu-id="4f412-126">You can also indicate whether the task copies the security identifiers (SIDs) associated with the logins.</span></span> <span data-ttu-id="4f412-127">Если задача «Передача имен входа» используется в связке с задачей «Передача базы данных», идентификаторы безопасности должны быть скопированы в пункт назначения; в ином случае переданные имена не будут распознаны целевой базой данных.</span><span class="sxs-lookup"><span data-stu-id="4f412-127">If the Transfer Logins task is used in conjunction with the Transfer Database task the SIDs must be copied to the destination; otherwise, the transferred logins are not recognized by the destination database.</span></span>  
  
 <span data-ttu-id="4f412-128">В пункте назначения переданные имена входа отключаются и им присваиваются случайные пароли.</span><span class="sxs-lookup"><span data-stu-id="4f412-128">At the destination, the transferred logins are disabled and assigned random passwords.</span></span> <span data-ttu-id="4f412-129">Прежде чем имена входа можно будет использовать, член роли sysadmin на целевом сервере должен изменить пароли этих имен и разрешить использование имен.</span><span class="sxs-lookup"><span data-stu-id="4f412-129">A member of the sysadmin role on the destination server must change the passwords and enable the logins before the logins can be used.</span></span>  
  
 <span data-ttu-id="4f412-130">Имена входа, подлежащие передаче, могут уже существовать в пункте назначения.</span><span class="sxs-lookup"><span data-stu-id="4f412-130">The logins to be transferred may already exist on the destination.</span></span> <span data-ttu-id="4f412-131">Задачу «Передача имен входа» можно настроить на обработку существующих имен одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="4f412-131">The Transfer Logins task can be configured to handle existing logins in the following ways:</span></span>  
  
-   <span data-ttu-id="4f412-132">Перезаписать существующие имена входа.</span><span class="sxs-lookup"><span data-stu-id="4f412-132">Overwrite existing logins.</span></span>  
  
-   <span data-ttu-id="4f412-133">Аварийно завершить задачу при наличии дубликатов имен входа.</span><span class="sxs-lookup"><span data-stu-id="4f412-133">Fail the task when duplicate logins exist.</span></span>  
  
-   <span data-ttu-id="4f412-134">Пропустить дубликаты имен входа.</span><span class="sxs-lookup"><span data-stu-id="4f412-134">Skip duplicate logins.</span></span>  
  
 <span data-ttu-id="4f412-135">Во время выполнения задача «Передача имен входа» подключается к исходному и целевому серверам, используя один или два диспетчера подключений SMO.</span><span class="sxs-lookup"><span data-stu-id="4f412-135">At run time, the Transfer Logins task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="4f412-136">Диспетчеры соединений SMO настраиваются независимо от задачи «Передача имен входа», после чего последняя на них ссылается.</span><span class="sxs-lookup"><span data-stu-id="4f412-136">The SMO connection managers are configured separately from the Transfer Logins task, and then referenced in the Transfer Logins task.</span></span> <span data-ttu-id="4f412-137">Диспетчеры соединений SMO определяют сервер и режим проверки подлинности, используемый для доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="4f412-137">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="4f412-138">Дополнительные сведения см. в статье [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4f412-138">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="4f412-139">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="4f412-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4f412-140">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4f412-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4f412-141">Редактор задачи "Передача имен входа" (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="4f412-141">Transfer Logins Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="4f412-142">Редактор задачи "Передача имен входа" (страница "Имена входа")</span><span class="sxs-lookup"><span data-stu-id="4f412-142">Transfer Logins Task Editor &#40;Logins Page&#41;</span></span>](../transfer-logins-task-editor-logins-page.md)  
  
-   [<span data-ttu-id="4f412-143">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="4f412-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="4f412-144">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="4f412-144">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="4f412-145">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="4f412-145">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-transfer-logins-task"></a><span data-ttu-id="4f412-146">Программная настройка задачи «Передача имен входа»</span><span class="sxs-lookup"><span data-stu-id="4f412-146">Programmatic Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="4f412-147">Дополнительные сведения об установке этих свойств программными средствами см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="4f412-147">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferLoginsTask.TransferLoginsTask>  
  
  
