---
title: MSSQL_ENG014162 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014162 error
ms.assetid: a15eef3f-219f-45d3-8286-6a864c85a723
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 78c6eb13087a7f7d5b2711af4484df7a384d7835
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668809"
---
# <a name="mssql_eng014162"></a><span data-ttu-id="ecc39-102">MSSQL_ENG014162</span><span class="sxs-lookup"><span data-stu-id="ecc39-102">MSSQL_ENG014162</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ecc39-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="ecc39-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecc39-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ecc39-104">Product Name</span></span>|<span data-ttu-id="ecc39-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ecc39-105">SQL Server</span></span>|  
|<span data-ttu-id="ecc39-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ecc39-106">Event ID</span></span>|<span data-ttu-id="ecc39-107">14162</span><span class="sxs-lookup"><span data-stu-id="ecc39-107">14162</span></span>|  
|<span data-ttu-id="ecc39-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ecc39-108">Event Source</span></span>|<span data-ttu-id="ecc39-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ecc39-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ecc39-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ecc39-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ecc39-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ecc39-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ecc39-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ecc39-112">Message Text</span></span>|<span data-ttu-id="ecc39-113">Задан порог [%s:%s] для публикации [%s].</span><span class="sxs-lookup"><span data-stu-id="ecc39-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="ecc39-114">Убедитесь в том, что агент слияния запущен и соответствует предъявляемому требованию.</span><span class="sxs-lookup"><span data-stu-id="ecc39-114">Please make sure that the merge agent is running and can match the expected requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ecc39-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ecc39-115">Explanation</span></span>  
 <span data-ttu-id="ecc39-116">При репликации можно включить предупреждения для ряда условий.</span><span class="sxs-lookup"><span data-stu-id="ecc39-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="ecc39-117">Сюда входит превышение определенного промежутка времени, необходимого для синхронизации изменений между издателем и подписчиком слияния.</span><span class="sxs-lookup"><span data-stu-id="ecc39-117">This includes exceeding a specified length of time for synchronizing changes between a merge Publisher and Subscriber.</span></span> <span data-ttu-id="ecc39-118">Для соединений по локальной сети и коммутируемых соединений можно указать разные значения времени.</span><span class="sxs-lookup"><span data-stu-id="ecc39-118">Different times can be specified for LAN connections and dial-up connections.</span></span>  
  
 <span data-ttu-id="ecc39-119">Когда предупреждение включается при помощи монитора репликации или процедуры [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), необходимо указать пороговое значение, определяющее, в какой момент выдается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="ecc39-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="ecc39-120">При достижении или превышении порогового значения предупреждение отображается в мониторе репликации, а в журнал событий Windows записывается событие.</span><span class="sxs-lookup"><span data-stu-id="ecc39-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="ecc39-121">Достижение порогового значения также может приводить к выдаче предупреждения агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ecc39-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="ecc39-122">Дополнительные сведения см. в статьях [Настройка пороговых значений и предупреждений в мониторе репликации](monitor/set-thresholds-and-warnings-in-replication-monitor.md). и [Наблюдение за репликацией программным образом](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ecc39-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ecc39-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ecc39-123">User Action</span></span>  
 <span data-ttu-id="ecc39-124">Если подписка превышает пороговое значение промежутка времени, необходимо определить, является ли это проблемой производительности системы или свидетельствует о необходимости изменить пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="ecc39-124">If a subscription exceeds a duration threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="ecc39-125">После настройки репликации разработайте базовый уровень производительности, позволяющий определить работу репликации при рабочей нагрузке, типичной для ваших приложений и топологии.</span><span class="sxs-lookup"><span data-stu-id="ecc39-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="ecc39-126">Включите в базовый уровень продолжительность синхронизации, чтобы правильно выбрать подходящее пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="ecc39-126">Include duration of synchronization in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="ecc39-127">Если пороговое значение выбрано верно, но превышение порогового значения все же наблюдается, то нужно определить, где в системе находится узкое место по производительности.</span><span class="sxs-lookup"><span data-stu-id="ecc39-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="ecc39-128">Дополнительные сведения о мониторинге и устранении неполадок, влияющих на производительность репликации, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ecc39-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   <span data-ttu-id="ecc39-129">[Наблюдение за производительностью с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md) (в частности, раздел "Просмотр подробных сведений о производительности синхронизации для репликации слиянием").</span><span class="sxs-lookup"><span data-stu-id="ecc39-129">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (especially the section "Viewing Detailed Synchronization Performance for Merge Replication")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc39-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="ecc39-130">See Also</span></span>  
 [<span data-ttu-id="ecc39-131">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="ecc39-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
