---
title: SQL Server, объект JobSteps | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- JobSteps object
- SQLAgent:JobSteps
ms.assetid: 44f9983c-1753-4fe0-8475-973aa2460b3a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3759303807714e2bb7f71f59e644bc485d36cfcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657054"
---
# <a name="sql-server-agent-jobsteps-object"></a><span data-ttu-id="6f0e8-102">Агент SQL Server, объект JobSteps</span><span class="sxs-lookup"><span data-stu-id="6f0e8-102">SQL Server Agent, JobSteps Object</span></span>
  <span data-ttu-id="6f0e8-103">Объект производительности агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**JobSteps** содержит счетчики производительности, сообщающие сведения о шагах задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **JobSteps** performance object contains performance counters that report information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="6f0e8-104">В следующей таблице перечислены счетчики этого объекта.</span><span class="sxs-lookup"><span data-stu-id="6f0e8-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="6f0e8-105">В следующей таблице представлены счетчики **SQLAgent:JobSteps** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-105">The table below contains the **SQLAgent:JobSteps** counters.</span></span>  
  
|<span data-ttu-id="6f0e8-106">Имя</span><span class="sxs-lookup"><span data-stu-id="6f0e8-106">Name</span></span>|<span data-ttu-id="6f0e8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6f0e8-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="6f0e8-108">**Активные шаги**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-108">**Active steps**</span></span>|<span data-ttu-id="6f0e8-109">Этот счетчик сообщает о текущем количестве выполняющихся шагов заданий.</span><span class="sxs-lookup"><span data-stu-id="6f0e8-109">This counter reports the number of job steps currently running.</span></span>|  
|<span data-ttu-id="6f0e8-110">**Шаги в очереди**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-110">**Queued steps**</span></span>|<span data-ttu-id="6f0e8-111">Этот счетчик сообщает о количестве шагов заданий, готовых к запуску, но еще не выполняющихся агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-111">This counter reports the number of job steps that are ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="6f0e8-112">**Общее количество попыток выполнить шаг**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-112">**Total step retries**</span></span>|<span data-ttu-id="6f0e8-113">Этот счетчик сообщает общее число повторных попыток [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запустить шаг задания с момента последнего перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="6f0e8-113">This counter reports the total number of times that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has retried a job step since the last server restart.</span></span>|  
  
 <span data-ttu-id="6f0e8-114">Каждый из счетчиков объекта содержит следующие экземпляры.</span><span class="sxs-lookup"><span data-stu-id="6f0e8-114">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="6f0e8-115">Экземпляр</span><span class="sxs-lookup"><span data-stu-id="6f0e8-115">Instance</span></span>|<span data-ttu-id="6f0e8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6f0e8-116">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6f0e8-117">**_Total**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-117">**_Total**</span></span>|<span data-ttu-id="6f0e8-118">Сведения для всех шагов задания.</span><span class="sxs-lookup"><span data-stu-id="6f0e8-118">Information for all job steps.</span></span>|  
|<span data-ttu-id="6f0e8-119">**ActiveScripting**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-119">**ActiveScripting**</span></span>|<span data-ttu-id="6f0e8-120">Сведения о шагах задания, использующих подсистему **ActiveScripting** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-120">Information for job steps that use the **ActiveScripting** subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-121">**ANALYSISCOMMAND**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-121">**ANALYSISCOMMAND**</span></span>|<span data-ttu-id="6f0e8-122">Сведения о шагах задания, использующих подсистему ANALYSISCOMMAND.</span><span class="sxs-lookup"><span data-stu-id="6f0e8-122">Information for job steps that use the ANALYSISCOMMAND subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-123">**ANALYSISQUERY**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-123">**ANALYSISQUERY**</span></span>|<span data-ttu-id="6f0e8-124">Сведения о шагах задания, использующих подсистему ANALYSISQUERY.</span><span class="sxs-lookup"><span data-stu-id="6f0e8-124">Information for job steps that use the ANALYSISQUERY subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-125">**CmdExec**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-125">**CmdExec**</span></span>|<span data-ttu-id="6f0e8-126">Сведения о шагах задания, использующих подсистему **CmdExec** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-126">Information for job steps that use the **CmdExec** subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-127">**Distribution**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-127">**Distribution**</span></span>|<span data-ttu-id="6f0e8-128">Сведения об шагах задания, использующих подсистему **Distribution** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-128">Information for job steps that use the **Distribution** subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-129">**Dts**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-129">**Dts**</span></span>|<span data-ttu-id="6f0e8-130">Сведения о шагах задания, использующих подсистему [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-130">Information for job steps that use the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-131">**LogReader**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-131">**LogReader**</span></span>|<span data-ttu-id="6f0e8-132">Сведения о шагах задания, использующих подсистему **LogReader** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-132">Information for job steps that use the **LogReader** subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-133">**Объединить**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-133">**Merge**</span></span>|<span data-ttu-id="6f0e8-134">Сведения о шагах задания, использующих подсистему **Merge** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-134">Information for job steps that use the **Merge** subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-135">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-135">**PowerShell**</span></span>|<span data-ttu-id="6f0e8-136">Сведения о шагах задания, использующих подсистему **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-136">Information for job steps that use the **PowerShell** subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-137">**QueueReader**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-137">**QueueReader**</span></span>|<span data-ttu-id="6f0e8-138">Сведения о шагах задания, использующих подсистему **QueueReader** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-138">Information for job steps that use the **QueueReader** subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-139">**Моментальный снимок**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-139">**Snapshot**</span></span>|<span data-ttu-id="6f0e8-140">Сведения о шагах задания, использующих подсистему **Snapshot** .</span><span class="sxs-lookup"><span data-stu-id="6f0e8-140">Information for job steps that use the **Snapshot** subsystem.</span></span>|  
|<span data-ttu-id="6f0e8-141">**TSQL**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-141">**TSQL**</span></span>|<span data-ttu-id="6f0e8-142">Сведения о шагах задания, выполняющих инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f0e8-142">Information for job steps that execute [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f0e8-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f0e8-143">See Also</span></span>  
 <span data-ttu-id="6f0e8-144">[Управление шагами задания](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="6f0e8-144">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 <span data-ttu-id="6f0e8-145">[Использование объектов производительности](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="6f0e8-145">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="6f0e8-146">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="6f0e8-146">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
