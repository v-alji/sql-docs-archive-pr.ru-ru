---
title: MSSQL_ENG014161 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014161 error
ms.assetid: 4b983e76-bb77-43c5-b44b-19919d3da619
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8cf85181e444385e1a3908761ba71414b68cf3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654179"
---
# <a name="mssql_eng014161"></a><span data-ttu-id="ae096-102">MSSQL_ENG014161</span><span class="sxs-lookup"><span data-stu-id="ae096-102">MSSQL_ENG014161</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ae096-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="ae096-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae096-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ae096-104">Product Name</span></span>|<span data-ttu-id="ae096-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae096-105">SQL Server</span></span>|  
|<span data-ttu-id="ae096-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ae096-106">Event ID</span></span>|<span data-ttu-id="ae096-107">14161</span><span class="sxs-lookup"><span data-stu-id="ae096-107">14161</span></span>|  
|<span data-ttu-id="ae096-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ae096-108">Event Source</span></span>|<span data-ttu-id="ae096-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ae096-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ae096-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ae096-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ae096-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ae096-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ae096-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ae096-112">Message Text</span></span>|<span data-ttu-id="ae096-113">Задан порог [%s:%s] для публикации [%s].</span><span class="sxs-lookup"><span data-stu-id="ae096-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="ae096-114">Убедитесь, что агент чтения журналов и агент распространителя запущены и соответствуют требованию по задержке.</span><span class="sxs-lookup"><span data-stu-id="ae096-114">Make sure that the logreader and distribution agents are running and can match the latency requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ae096-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ae096-115">Explanation</span></span>  
 <span data-ttu-id="ae096-116">При репликации можно включить предупреждения для ряда условий.</span><span class="sxs-lookup"><span data-stu-id="ae096-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="ae096-117">Сюда входит превышение определенного значения задержки для подписок на публикацию транзакций.</span><span class="sxs-lookup"><span data-stu-id="ae096-117">This includes exceeding a specified latency for transactional subscriptions.</span></span> <span data-ttu-id="ae096-118">Задержка — это интервал времени между фиксацией транзакции на издателе и фиксацией соответствующей транзакции на подписчике.</span><span class="sxs-lookup"><span data-stu-id="ae096-118">Latency is the period of time that elapses between a data change being committed at the Publisher and the corresponding change being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="ae096-119">Когда предупреждение включается при помощи монитора репликации или процедуры [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), необходимо указать пороговое значение, определяющее, в какой момент выдается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="ae096-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="ae096-120">При достижении или превышении порогового значения предупреждение отображается в мониторе репликации, а в журнал событий Windows записывается событие.</span><span class="sxs-lookup"><span data-stu-id="ae096-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="ae096-121">Достижение порогового значения также может приводить к выдаче предупреждения агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae096-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="ae096-122">Дополнительные сведения см. в статьях [Настройка пороговых значений и предупреждений в мониторе репликации](monitor/set-thresholds-and-warnings-in-replication-monitor.md). и [Наблюдение за репликацией программным образом](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ae096-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae096-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ae096-123">User Action</span></span>  
 <span data-ttu-id="ae096-124">Если подписка превышает пороговое значение задержки, необходимо определить, является это проблемой производительности системы или свидетельствует о необходимости скорректировать пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="ae096-124">If a subscription exceeds a latency threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="ae096-125">После настройки репликации разработайте базовый уровень производительности, позволяющий определить работу репликации при рабочей нагрузке, типичной для ваших приложений и топологии.</span><span class="sxs-lookup"><span data-stu-id="ae096-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="ae096-126">Включите в базовый уровень задержку, чтобы правильно выбрать подходящее пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="ae096-126">Include latency in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="ae096-127">Если пороговое значение выбрано верно, но превышение порогового значения все же наблюдается, то нужно определить, где в системе находится узкое место по производительности.</span><span class="sxs-lookup"><span data-stu-id="ae096-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="ae096-128">Дополнительные сведения о мониторинге и устранении неполадок, влияющих на производительность репликации, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ae096-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   [<span data-ttu-id="ae096-129">Измерение задержки и проверка правильности соединений для репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="ae096-129">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
-   [<span data-ttu-id="ae096-130">Наблюдение за производительностью с помощью монитора репликации</span><span class="sxs-lookup"><span data-stu-id="ae096-130">Monitor Performance with Replication Monitor</span></span>](monitor/monitor-performance-with-replication-monitor.md)  
  
## <a name="see-also"></a><span data-ttu-id="ae096-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae096-131">See Also</span></span>  
 [<span data-ttu-id="ae096-132">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="ae096-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
