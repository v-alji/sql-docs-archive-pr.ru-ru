---
title: Использование сеанса system_health | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], system health session
- extended events [SQL Server], system_health session
- system_health session [SQL Server extended events]
- system health session [SQL Server extended events]
ms.assetid: 1e1fad43-d747-4775-ac0d-c50648e56d78
author: yualan
ms.author: alayu
ms.openlocfilehash: 86c3221fb4c0ea0690b369888ac8f2f9f82d6ef9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655166"
---
# <a name="use-the-system_health-session"></a><span data-ttu-id="542b0-102">Использование сеанса system_health</span><span class="sxs-lookup"><span data-stu-id="542b0-102">Use the system_health Session</span></span>
  <span data-ttu-id="542b0-103">Сеанс system_health является сеансом расширенных событий, который по умолчанию включен в состав [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="542b0-103">The system_health session is an Extended Events session that is included by default with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="542b0-104">Этот сеанс запускается автоматически при запуске [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и выполняется без заметного воздействия на производительность.</span><span class="sxs-lookup"><span data-stu-id="542b0-104">This session starts automatically when the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] starts, and runs without any noticeable performance effects.</span></span> <span data-ttu-id="542b0-105">В этом сеансе собираются системные данные, которые можно использовать для устранения неполадок, связанных с производительностью компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="542b0-105">The session collects system data that you can use to help troubleshoot performance issues in the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="542b0-106">Поэтому этот сеанс не рекомендуется останавливать или удалять.</span><span class="sxs-lookup"><span data-stu-id="542b0-106">Therefore, we recommend that you do not stop or delete the session.</span></span>  
  
 <span data-ttu-id="542b0-107">Сеанс собирает следующие данные.</span><span class="sxs-lookup"><span data-stu-id="542b0-107">The session collects information that includes the following:</span></span>  
  
-   <span data-ttu-id="542b0-108">sql_text и session_id для всех сеансов, в которых возникает ошибка с уровнем серьезности >=20.</span><span class="sxs-lookup"><span data-stu-id="542b0-108">The sql_text and session_id for any sessions that encounter an error that has a severity >=20.</span></span>  
  
-   <span data-ttu-id="542b0-109">sql_text и session_id для всех сеансов, в которых возникает ошибка, связанная с памятью.</span><span class="sxs-lookup"><span data-stu-id="542b0-109">The sql_text and session_id for any sessions that encounter a memory-related error.</span></span> <span data-ttu-id="542b0-110">К этим ошибкам относятся 17803, 701, 802, 8645, 8651, 8657 и 8902.</span><span class="sxs-lookup"><span data-stu-id="542b0-110">The errors include 17803, 701, 802, 8645, 8651, 8657 and 8902.</span></span>  
  
-   <span data-ttu-id="542b0-111">Запись всех нерешенных проблем планировщика.</span><span class="sxs-lookup"><span data-stu-id="542b0-111">A record of any non-yielding scheduler problems.</span></span> <span data-ttu-id="542b0-112">(Они записываются в журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в виде ошибки 17883.)</span><span class="sxs-lookup"><span data-stu-id="542b0-112">(These appear in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log as error 17883.)</span></span>  
  
-   <span data-ttu-id="542b0-113">Все обнаруженные взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="542b0-113">Any deadlocks that are detected.</span></span>  
  
-   <span data-ttu-id="542b0-114">callstack, sql_text и session_id для всех сеансов, которые ожидали снятия кратковременной блокировки (или других необходимых ресурсов) более 15 с.</span><span class="sxs-lookup"><span data-stu-id="542b0-114">The callstack, sql_text, and session_id for any sessions that have waited on latches (or other interesting resources) for > 15 seconds.</span></span>  
  
-   <span data-ttu-id="542b0-115">callstack, sql_text и session_id для всех сеансов, которые ожидали снятия блокировки более 30 с.</span><span class="sxs-lookup"><span data-stu-id="542b0-115">The callstack, sql_text, and session_id for any sessions that have waited on locks for > 30 seconds.</span></span>  
  
-   <span data-ttu-id="542b0-116">callstack, sql_text и session_id для всех сеансов, которые долгое время находились в режиме ожидания с вытеснением.</span><span class="sxs-lookup"><span data-stu-id="542b0-116">The callstack, sql_text, and session_id for any sessions that have waited for a long time for preemptive waits.</span></span> <span data-ttu-id="542b0-117">Длительность зависит от типа ожидания.</span><span class="sxs-lookup"><span data-stu-id="542b0-117">The duration varies by wait type.</span></span> <span data-ttu-id="542b0-118">Ожидание с вытеснением возникает в том случае, если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ожидает внешних вызовов API.</span><span class="sxs-lookup"><span data-stu-id="542b0-118">A preemptive wait is where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for external API calls.</span></span>  
  
-   <span data-ttu-id="542b0-119">Значения callstack и session_id для ошибок размещения CLR и виртуального выделения.</span><span class="sxs-lookup"><span data-stu-id="542b0-119">The callstack and session_id for CLR allocation and virtual allocation failures.</span></span>  
  
-   <span data-ttu-id="542b0-120">События ring_buffer для брокера памяти, монитора планировщиков, OOM узла памяти, безопасности и возможности подключения.</span><span class="sxs-lookup"><span data-stu-id="542b0-120">The ring_buffer events for the memory broker, scheduler monitor, memory node OOM, security, and connectivity.</span></span>  
  
-   <span data-ttu-id="542b0-121">Результаты из sp_server_diagnostics.</span><span class="sxs-lookup"><span data-stu-id="542b0-121">System component results from sp_server_diagnostics.</span></span>  
  
-   <span data-ttu-id="542b0-122">Данные об исправности экземпляра, собираемые scheduler_monitor_system_health_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="542b0-122">Instance health collected by scheduler_monitor_system_health_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="542b0-123">Сбои размещения CLR.</span><span class="sxs-lookup"><span data-stu-id="542b0-123">CLR Allocation failures.</span></span>  
  
-   <span data-ttu-id="542b0-124">Ошибки возможности подключения при использовании connectivity_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="542b0-124">Connectivity errors using connectivity_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="542b0-125">Ошибки безопасности при использовании security_error_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="542b0-125">Security errors using security_error_ring_buffer_recorded.</span></span>  
  
## <a name="viewing-the-session-data"></a><span data-ttu-id="542b0-126">Просмотр данных сеанса</span><span class="sxs-lookup"><span data-stu-id="542b0-126">Viewing the Session Data</span></span>  
 <span data-ttu-id="542b0-127">В сеансе для хранения данных используется цель «Кольцевой буфер».</span><span class="sxs-lookup"><span data-stu-id="542b0-127">The session uses the ring buffer target to store the data.</span></span> <span data-ttu-id="542b0-128">Для просмотра данных сеанса используйте следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="542b0-128">To view the session data, use the following query:</span></span>  
  
```  
SELECT CAST(xet.target_data as xml) FROM sys.dm_xe_session_targets xet  
JOIN sys.dm_xe_sessions xe  
ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'system_health'  
```  
  
 <span data-ttu-id="542b0-129">Для просмотра данных сеанса событий из файла пользуйтесь доступным пользовательским интерфейсом расширенных событий в среде Management Studio.</span><span class="sxs-lookup"><span data-stu-id="542b0-129">To view the session data from the event file, use the Extended Events user interface available in Management Studio.</span></span> <span data-ttu-id="542b0-130">Подробнее см. в разделе [View Event Session Data](../../database-engine/view-event-session-data.md) .</span><span class="sxs-lookup"><span data-stu-id="542b0-130">See [View Event Session Data](../../database-engine/view-event-session-data.md) for more information.</span></span>  
  
## <a name="restoring-the-system_health-session"></a><span data-ttu-id="542b0-131">Восстановление сеанса system_health</span><span class="sxs-lookup"><span data-stu-id="542b0-131">Restoring the system_health Session</span></span>  
 <span data-ttu-id="542b0-132">Если сеанс system_healt был удален, то вы можете его восстановить, выполнив файл **u_tables.sql** в редакторе запросов.</span><span class="sxs-lookup"><span data-stu-id="542b0-132">If you delete the system_health session, you can restore it by executing the **u_tables.sql** file in Query Editor.</span></span> <span data-ttu-id="542b0-133">Этот файл находится в следующей папке (где C: означает диск, на котором установлены программные файлы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="542b0-133">This file is located in the following folder, where C: represents the drive where you installed the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] program files:</span></span>  
  
 <span data-ttu-id="542b0-134">C:\Program Files\Microsoft SQL Server\MSSQL12. \<*instanceid*> \мсскл\инсталл</span><span class="sxs-lookup"><span data-stu-id="542b0-134">C:\Program Files\Microsoft SQL Server\MSSQL12.\<*instanceid*>\MSSQL\Install</span></span>  
  
 <span data-ttu-id="542b0-135">Имейте в виду, что после восстановления сеанса необходимо его запустить с помощью инструкции ALTER EVENT SESSION или через узел **Расширенные события** в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="542b0-135">Be aware that after you restore the session, you must start the session by using the ALTER EVENT SESSION statement or by using the **Extended Events** node in Object Explorer.</span></span> <span data-ttu-id="542b0-136">Если этого не сделать, сеанс запустится автоматически при следующем перезапуске службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="542b0-136">Otherwise, the session starts automatically the next time that you restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="542b0-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="542b0-137">See Also</span></span>  
 [<span data-ttu-id="542b0-138">Средства расширенных событий</span><span class="sxs-lookup"><span data-stu-id="542b0-138">Extended Events Tools</span></span>](extended-events-tools.md)  
  
  
