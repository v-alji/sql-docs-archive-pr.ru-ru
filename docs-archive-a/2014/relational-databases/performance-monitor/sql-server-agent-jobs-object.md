---
title: Объект заданий (агент SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLAgent:Jobs
- Jobs object
ms.assetid: 225b5e2d-4a78-4178-b2b6-b419df83c4aa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 82ee57eba20d44c08eadc125e9dfd69e73c35751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657055"
---
# <a name="sql-server-agent-jobs-object"></a><span data-ttu-id="16471-102">Агент SQL Server, объект Jobs</span><span class="sxs-lookup"><span data-stu-id="16471-102">SQL Server Agent, Jobs Object</span></span>
  <span data-ttu-id="16471-103">Объект производительности **Jobs** агента SQL Server содержит счетчики производительности, отображающие сведения о заданиях агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="16471-103">The SQL Server Agent **Jobs** performance object contains performance counters that report information about SQL Server Agent jobs.</span></span> <span data-ttu-id="16471-104">В следующей таблице перечислены счетчики этого объекта.</span><span class="sxs-lookup"><span data-stu-id="16471-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="16471-105">Приведенная ниже таблица содержит счетчики объекта **SQLAgent:Jobs** .</span><span class="sxs-lookup"><span data-stu-id="16471-105">The table below contains the **SQLAgent:Jobs** counters.</span></span>  
  
|<span data-ttu-id="16471-106">Имя</span><span class="sxs-lookup"><span data-stu-id="16471-106">Name</span></span>|<span data-ttu-id="16471-107">Описание</span><span class="sxs-lookup"><span data-stu-id="16471-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="16471-108">**Активные задания**</span><span class="sxs-lookup"><span data-stu-id="16471-108">**Active Jobs**</span></span>|<span data-ttu-id="16471-109">Данный счетчик отображает количество выполняемых в данный момент заданий.</span><span class="sxs-lookup"><span data-stu-id="16471-109">This counter reports the number of jobs currently running.</span></span>|  
|<span data-ttu-id="16471-110">**Невыполненные задания**</span><span class="sxs-lookup"><span data-stu-id="16471-110">**Failed jobs**</span></span>|<span data-ttu-id="16471-111">Этот счетчик отображает количество заданий, завершенных с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="16471-111">This counter reports the number of jobs that exited with failure.</span></span>|  
|<span data-ttu-id="16471-112">**Эффективность выполнения заданий**</span><span class="sxs-lookup"><span data-stu-id="16471-112">**Job success rate**</span></span>|<span data-ttu-id="16471-113">Этот счетчик отображает процентное соотношение успешно завершенных заданий от общего количества выполняемых заданий.</span><span class="sxs-lookup"><span data-stu-id="16471-113">This counter reports the percentage of executed jobs that completed successfully.</span></span>|  
|<span data-ttu-id="16471-114">**Задания, запускаемые за минуту**</span><span class="sxs-lookup"><span data-stu-id="16471-114">**Jobs activated/minute**</span></span>|<span data-ttu-id="16471-115">Данный счетчик отображает количество заданий, запущенных в течение последней минуты.</span><span class="sxs-lookup"><span data-stu-id="16471-115">This counter reports the number of jobs launched within the last minute.</span></span>|  
|<span data-ttu-id="16471-116">**Задания в очереди**</span><span class="sxs-lookup"><span data-stu-id="16471-116">**Queued jobs**</span></span>|<span data-ttu-id="16471-117">Данный счетчик отображает количество заданий, готовых к выполнению агентом SQL Server, но еще не запущенных.</span><span class="sxs-lookup"><span data-stu-id="16471-117">This counter reports the number of jobs that are ready for SQL Server Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="16471-118">**Успешно выполненные задания**</span><span class="sxs-lookup"><span data-stu-id="16471-118">**Successful jobs**</span></span>|<span data-ttu-id="16471-119">Данный счетчик отображает количество успешно завершенных заданий.</span><span class="sxs-lookup"><span data-stu-id="16471-119">This counter reports the number of jobs that exited with success.</span></span>|  
  
 <span data-ttu-id="16471-120">Каждый из счетчиков объекта содержит следующие экземпляры.</span><span class="sxs-lookup"><span data-stu-id="16471-120">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="16471-121">Экземпляр</span><span class="sxs-lookup"><span data-stu-id="16471-121">Instance</span></span>|<span data-ttu-id="16471-122">Описание</span><span class="sxs-lookup"><span data-stu-id="16471-122">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="16471-123">**_Total**</span><span class="sxs-lookup"><span data-stu-id="16471-123">**_Total**</span></span>|<span data-ttu-id="16471-124">Сведения обо всех заданиях.</span><span class="sxs-lookup"><span data-stu-id="16471-124">Information for all jobs.</span></span>|  
|<span data-ttu-id="16471-125">**Оповещения**</span><span class="sxs-lookup"><span data-stu-id="16471-125">**Alerts**</span></span>|<span data-ttu-id="16471-126">Сведения о заданиях, запущенных по предупреждению.</span><span class="sxs-lookup"><span data-stu-id="16471-126">Information for jobs started by alerts.</span></span>|  
|<span data-ttu-id="16471-127">**Прочие**</span><span class="sxs-lookup"><span data-stu-id="16471-127">**Others**</span></span>|<span data-ttu-id="16471-128">Сведения о заданиях, запущенных не по предупреждению и не по расписанию.</span><span class="sxs-lookup"><span data-stu-id="16471-128">Information for jobs that were not started by alerts or schedules.</span></span> <span data-ttu-id="16471-129">Обычно это задания, запущенные вручную с помощью процедуры **sp_start_job**.</span><span class="sxs-lookup"><span data-stu-id="16471-129">Typically these are jobs started manually using **sp_start_job**.</span></span>|  
|<span data-ttu-id="16471-130">**Расписания**</span><span class="sxs-lookup"><span data-stu-id="16471-130">**Schedules**</span></span>|<span data-ttu-id="16471-131">Сведения о заданиях, запущенных по расписанию.</span><span class="sxs-lookup"><span data-stu-id="16471-131">Information for jobs started by schedules.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16471-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="16471-132">See Also</span></span>  
 <span data-ttu-id="16471-133">[Реализация заданий](../../ssms/agent/implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="16471-133">[Implement Jobs](../../ssms/agent/implement-jobs.md) </span></span>  
 <span data-ttu-id="16471-134">[Использование объектов производительности](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="16471-134">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="16471-135">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="16471-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
