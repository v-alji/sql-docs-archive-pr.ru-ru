---
title: Редактор задачи «перемещение заданий» (страница «задания») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.jobs.f1
helpviewer_keywords:
- Transfer Jobs Task Editor
ms.assetid: e72b1dc7-8cda-4ee6-abb5-d438370f04df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d2d506da6997965e40d66521f7dccb8218e165fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669471"
---
# <a name="transfer-jobs-task-editor-jobs-page"></a><span data-ttu-id="cc2ce-102">Редактор задачи «Передача заданий» (страница «Задания»)</span><span class="sxs-lookup"><span data-stu-id="cc2ce-102">Transfer Jobs Task Editor (Jobs Page)</span></span>
  <span data-ttu-id="cc2ce-103">Используйте страницу **Задания** диалогового окна **Редактор задачи «Передача заданий»** для определения свойств копирования одного или более заданий агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] из одного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] в другой.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-103">Use the **Jobs** page of the **Transfer Jobs Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="cc2ce-104">Дополнительные сведения о задаче «Передача заданий» см. в разделе [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span><span class="sxs-lookup"><span data-stu-id="cc2ce-104">For more information about the Transfer Jobs task, see [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc2ce-105">Для доступа к задачам на исходном сервере пользователи должны быть членами хотя бы одной предопределенной роли базы данных **SQLAgentUserRole** на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-105">To access jobs on the source server, users must be a member of at least the **SQLAgentUserRole** fixed database role on the server.</span></span> <span data-ttu-id="cc2ce-106">Для успешного создания задания на целевом сервере пользователь должен быть членом предопределенной роли сервера **sysadmin** или одной из предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc2ce-106">To successfully create jobs on the destination server, the user must be a member of the **sysadmin** fixed server role or one of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles.</span></span> <span data-ttu-id="cc2ce-107">Дополнительные сведения о предопределенных ролях базы данных агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и их разрешениях см. в разделе [Предопределенные роли базы данных агента SQL Server](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cc2ce-107">For more information about [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles and their permissions, see [SQL Server Agent Fixed Database Roles](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc2ce-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc2ce-108">Options</span></span>  
 <span data-ttu-id="cc2ce-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-109">**SourceConnection**</span></span>  
 <span data-ttu-id="cc2ce-110">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="cc2ce-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="cc2ce-112">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к целевому серверу.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="cc2ce-113">**TransferAllJobs**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-113">**TransferAllJobs**</span></span>  
 <span data-ttu-id="cc2ce-114">Укажите, должна задача копировать с исходного сервера на целевой все задания или только те, которые указаны агентом [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc2ce-114">Select whether the task should copy all or only the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from the source to the destination server.</span></span>  
  
 <span data-ttu-id="cc2ce-115">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="cc2ce-116">Значение</span><span class="sxs-lookup"><span data-stu-id="cc2ce-116">Value</span></span>|<span data-ttu-id="cc2ce-117">Описание</span><span class="sxs-lookup"><span data-stu-id="cc2ce-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cc2ce-118">**True**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-118">**True**</span></span>|<span data-ttu-id="cc2ce-119">Копировать все задания.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-119">Copy all jobs.</span></span>|  
|<span data-ttu-id="cc2ce-120">**False**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-120">**False**</span></span>|<span data-ttu-id="cc2ce-121">Копировать только выбранные задания.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-121">Copy only the specified jobs.</span></span>|  
  
 <span data-ttu-id="cc2ce-122">**JobsList**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-122">**JobsList**</span></span>  
 <span data-ttu-id="cc2ce-123">Нажмите кнопку обзора **(…)** , чтобы выбрать задания для копирования.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-123">Click the browse button **(...)** to select the jobs to copy.</span></span> <span data-ttu-id="cc2ce-124">Необходимо выбрать хотя бы одно задание.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-124">At least one job must be selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc2ce-125">Прежде чем выбирать задания для копирования, укажите свойство **SourceConnection** .</span><span class="sxs-lookup"><span data-stu-id="cc2ce-125">Specify the **SourceConnection** before selecting jobs to copy.</span></span>  
  
 <span data-ttu-id="cc2ce-126">Параметр **JobsList** недоступен, если параметр **TransferAllJobs** равен **True**.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-126">The **JobsList** option is unavailable when **TransferAllJobs** is set to **True**.</span></span>  
  
 <span data-ttu-id="cc2ce-127">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-127">**IfObjectExists**</span></span>  
 <span data-ttu-id="cc2ce-128">Определите, как задача должна обрабатывать задания с именем, которое уже есть на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-128">Select how the task should handle jobs of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="cc2ce-129">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-129">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="cc2ce-130">Значение</span><span class="sxs-lookup"><span data-stu-id="cc2ce-130">Value</span></span>|<span data-ttu-id="cc2ce-131">Description</span><span class="sxs-lookup"><span data-stu-id="cc2ce-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cc2ce-132">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-132">**FailTask**</span></span>|<span data-ttu-id="cc2ce-133">Задача завершается сбоем, если задание с таким именем уже есть на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-133">Task fails if jobs of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="cc2ce-134">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-134">**Overwrite**</span></span>|<span data-ttu-id="cc2ce-135">Задача перезаписывает задание с таким же именем на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-135">Task overwrites jobs of the same name on the destination server.</span></span>|  
|<span data-ttu-id="cc2ce-136">**Skip**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-136">**Skip**</span></span>|<span data-ttu-id="cc2ce-137">Задача пропускает задание, если задание с таким именем уже есть на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-137">Task skips jobs of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="cc2ce-138">**EnableJobsAtDestination**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-138">**EnableJobsAtDestination**</span></span>  
 <span data-ttu-id="cc2ce-139">Определите, будут ли активированы задания, скопированные на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-139">Select whether the jobs copied to the destination server should be enabled.</span></span>  
  
 <span data-ttu-id="cc2ce-140">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-140">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="cc2ce-141">Значение</span><span class="sxs-lookup"><span data-stu-id="cc2ce-141">Value</span></span>|<span data-ttu-id="cc2ce-142">Описание</span><span class="sxs-lookup"><span data-stu-id="cc2ce-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cc2ce-143">**True**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-143">**True**</span></span>|<span data-ttu-id="cc2ce-144">Включить задания на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-144">Enable jobs on destination server.</span></span>|  
|<span data-ttu-id="cc2ce-145">**False**</span><span class="sxs-lookup"><span data-stu-id="cc2ce-145">**False**</span></span>|<span data-ttu-id="cc2ce-146">Отключить задания на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="cc2ce-146">Disable jobs on destination server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc2ce-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="cc2ce-147">See Also</span></span>  
 <span data-ttu-id="cc2ce-148">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cc2ce-148">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cc2ce-149">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="cc2ce-149">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="cc2ce-150">[Редактор задачи "перемещение заданий" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="cc2ce-150">[Transfer Jobs Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="cc2ce-151">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="cc2ce-151">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="cc2ce-152">Диспетчер соединений SMO</span><span class="sxs-lookup"><span data-stu-id="cc2ce-152">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
