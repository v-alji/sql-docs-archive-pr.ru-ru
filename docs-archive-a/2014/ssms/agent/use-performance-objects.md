---
title: Использование объектов производительности | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- SQL Server Agent service, monitoring
- SQL Server Agent service, performance objects
- SQL Server Agent, performance objects
- performance objects [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- performance counters [SQL Server], SQL Server Agent
- counters [SQL Server], SQL Server Agent
ms.assetid: 830b843a-6b2a-4620-a51b-98358e9fc54b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7c1fe3f4a7d9a5fec901f84d8e913e49a4dbd1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665749"
---
# <a name="use-performance-objects"></a><span data-ttu-id="51b39-102">Использование объектов производительности</span><span class="sxs-lookup"><span data-stu-id="51b39-102">Use Performance Objects</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="51b39-103">Агент включает объекты и счетчики производительности, позволяющие отслеживать работу служб.</span><span class="sxs-lookup"><span data-stu-id="51b39-103">Agent includes performance objects and counters to monitor how the service is performing.</span></span> <span data-ttu-id="51b39-104">Эти объекты производительности дают возможность использования системного монитора, средства Windows для определения задач, выполняемых службой агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="51b39-104">These performance objects allow you to use Performance Monitor, a Windows tool, to identify what the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is doing in the background.</span></span> <span data-ttu-id="51b39-105">Например, можно узнать, сколько активных заданий запущено в данный момент в службе агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и определить заблокированные задания.</span><span class="sxs-lookup"><span data-stu-id="51b39-105">For example, you can identify how many active jobs the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is currently running to identify those jobs that are blocked.</span></span>  
  
 <span data-ttu-id="51b39-106">Объекты и счетчики производительности службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предусмотрены для каждого установленного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51b39-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects and counters exist for each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is installed on a computer.</span></span> <span data-ttu-id="51b39-107">Имена объектам производительности присваиваются в соответствии с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые они представляют.</span><span class="sxs-lookup"><span data-stu-id="51b39-107">Performance objects are named according to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that each object represents.</span></span>  
  
 <span data-ttu-id="51b39-108">В следующей таблице содержатся правила именования объектов производительности службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51b39-108">The following table shows how the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects are named:</span></span>  
  
|<span data-ttu-id="51b39-109">Тип экземпляра</span><span class="sxs-lookup"><span data-stu-id="51b39-109">Instance type</span></span>|<span data-ttu-id="51b39-110">Имя объекта</span><span class="sxs-lookup"><span data-stu-id="51b39-110">Object name</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="51b39-111">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="51b39-111">Default</span></span>|<span data-ttu-id="51b39-112">**SQLAgent:** *объект*:*счетчик*</span><span class="sxs-lookup"><span data-stu-id="51b39-112">**SQLAgent:** *object*:*counter*</span></span>|  
|<span data-ttu-id="51b39-113">именованная</span><span class="sxs-lookup"><span data-stu-id="51b39-113">Named</span></span>|<span data-ttu-id="51b39-114">**SQLAgent$**</span><span class="sxs-lookup"><span data-stu-id="51b39-114">**SQLAgent$**</span></span><br /> <span data-ttu-id="51b39-115">***instance_name* :** *объект*:*Counter*</span><span class="sxs-lookup"><span data-stu-id="51b39-115">***instance_name* :** *object*:*counter*</span></span>|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="51b39-116">содержит следующие объекты производительности для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51b39-116">includes the following performance objects for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
|<span data-ttu-id="51b39-117">Имя объекта</span><span class="sxs-lookup"><span data-stu-id="51b39-117">Object name</span></span>|<span data-ttu-id="51b39-118">Описание</span><span class="sxs-lookup"><span data-stu-id="51b39-118">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="51b39-119">SQLAgent:Jobs</span><span class="sxs-lookup"><span data-stu-id="51b39-119">SQLAgent:Jobs</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobs-object.md)|<span data-ttu-id="51b39-120">Сведения о производительности запущенных заданий, проценте успешных попыток и текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="51b39-120">Performance information about jobs that have been started, success rates, and current status</span></span>|  
|[<span data-ttu-id="51b39-121">SQLAgent:JobSteps</span><span class="sxs-lookup"><span data-stu-id="51b39-121">SQLAgent:JobSteps</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobsteps-object.md)|<span data-ttu-id="51b39-122">Сведения о состоянии шагов заданий.</span><span class="sxs-lookup"><span data-stu-id="51b39-122">Status information about job steps</span></span>|  
|[<span data-ttu-id="51b39-123">SQLAgent:Alerts</span><span class="sxs-lookup"><span data-stu-id="51b39-123">SQLAgent:Alerts</span></span>](../../relational-databases/performance-monitor/sql-server-agent-alerts-object.md)|<span data-ttu-id="51b39-124">Сведения о количестве предупреждений и уведомлений.</span><span class="sxs-lookup"><span data-stu-id="51b39-124">Information about number of alerts and notifications</span></span>|  
|[<span data-ttu-id="51b39-125">SQLAgent:Statistics</span><span class="sxs-lookup"><span data-stu-id="51b39-125">SQLAgent:Statistics</span></span>](../../relational-databases/performance-monitor/sql-server-agent-statistics-object.md)|<span data-ttu-id="51b39-126">Общие сведения о производительности.</span><span class="sxs-lookup"><span data-stu-id="51b39-126">General performance information</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51b39-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="51b39-127">See Also</span></span>  
 <span data-ttu-id="51b39-128">[Наблюдение и настройка производительности](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span><span class="sxs-lookup"><span data-stu-id="51b39-128">[Monitor and Tune for Performance](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span></span>  
 [<span data-ttu-id="51b39-129">Запуск системного монитора (Windows)</span><span class="sxs-lookup"><span data-stu-id="51b39-129">Start System Monitor &#40;Windows&#41;</span></span>](../../relational-databases/performance/start-system-monitor-windows.md)  
  
  
