---
title: Планирование трассировок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], events
- traces [SQL Server]
- traces [SQL Server], stopping
- events [SQL Server], filters
- scheduling traces [SQL Server]
- traces [SQL Server], scheduling
- stopping traces
ms.assetid: 620b79db-924b-4502-8af3-39efcfca245d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a698d88db35c84f7611293cf45807203c883865a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665978"
---
# <a name="schedule-traces"></a><span data-ttu-id="35588-102">Планирование трассировок</span><span class="sxs-lookup"><span data-stu-id="35588-102">Schedule Traces</span></span>
  <span data-ttu-id="35588-103">В Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]предусмотрены два способа планирования трассировок.</span><span class="sxs-lookup"><span data-stu-id="35588-103">There are two ways to schedule tracing in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="35588-104">Вы можете:</span><span class="sxs-lookup"><span data-stu-id="35588-104">You can:</span></span>  
  
-   <span data-ttu-id="35588-105">задать время прекращения трассировки;</span><span class="sxs-lookup"><span data-stu-id="35588-105">Enable a trace stop time.</span></span>  
  
-   <span data-ttu-id="35588-106">использовать агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для планирования трассировки.</span><span class="sxs-lookup"><span data-stu-id="35588-106">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to schedule a trace.</span></span>  
  
## <a name="specifying-a-stop-time"></a><span data-ttu-id="35588-107">Задание времени прекращения</span><span class="sxs-lookup"><span data-stu-id="35588-107">Specifying a Stop Time</span></span>  
 <span data-ttu-id="35588-108">Время прекращения трассировки можно указать в том случае, если используются хранимые процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] или приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35588-108">You can specify a trace stop time if you use [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures or if you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="35588-109">Время прекращения указывается после того, как произведено начальное конфигурирование трассировки.</span><span class="sxs-lookup"><span data-stu-id="35588-109">The stop time must be set when the trace is originally configured.</span></span>  
  
## <a name="scheduling-traces-by-using-sql-server-agent"></a><span data-ttu-id="35588-110">Планирование трассировки с помощью агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="35588-110">Scheduling Traces by Using SQL Server Agent</span></span>  
 <span data-ttu-id="35588-111">Наилучшим способом планирования трассировок является использование агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для запуска трассировки с последующим указанием времени ее прекращения хранимой процедурой [!INCLUDE[tsql](../../includes/tsql-md.md)]**sp_trace_setstatus**или приложением [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35588-111">The best way to schedule traces is to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to start the trace and then specify a trace stop time by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure **sp_trace_setstatus**, or [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="35588-112">**Установка фильтра времени прекращения трассировки**</span><span class="sxs-lookup"><span data-stu-id="35588-112">**To set an end time filter for a trace**</span></span>  
  
 [<span data-ttu-id="35588-113">Фильтрация событий по времени окончания (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="35588-113">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
 [<span data-ttu-id="35588-114">Хранимая процедура sp_trace_setstatus (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="35588-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="35588-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="35588-115">See Also</span></span>  
 [<span data-ttu-id="35588-116">Задачи автоматизированного администрирования (агент SQL Server)</span><span class="sxs-lookup"><span data-stu-id="35588-116">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../../ssms/agent/sql-server-agent.md)  
  
  
