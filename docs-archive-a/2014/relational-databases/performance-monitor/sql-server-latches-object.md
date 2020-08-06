---
title: SQL Server, объект Latches | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Latches object
- SQLServer:Latches
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f49ac00114065e971c0893f9217ab883eb2d7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656346"
---
# <a name="sql-server-latches-object"></a><span data-ttu-id="25a72-102">SQL Server, объект Latches</span><span class="sxs-lookup"><span data-stu-id="25a72-102">SQL Server, Latches Object</span></span>
  <span data-ttu-id="25a72-103">Объект **SQLServer:Latches** в Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предоставляет счетчики для контроля за блокировками внутренних ресурсов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25a72-103">The **SQLServer:Latches** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor internal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource locks called latches.</span></span> <span data-ttu-id="25a72-104">Контроль над кратковременными блокировками с целью определения деятельности пользователей и распределения ресурсов помогает обнаружить узкие места в производительности системы.</span><span class="sxs-lookup"><span data-stu-id="25a72-104">Monitoring the latches to determine user activity and resource usage can help you to identify performance bottlenecks.</span></span>  
  
 <span data-ttu-id="25a72-105">В данной таблице описаны счетчики [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches**.</span><span class="sxs-lookup"><span data-stu-id="25a72-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches** counters.</span></span>  
  
|<span data-ttu-id="25a72-106">Счетчики кратковременных блокировок в SQL Server</span><span class="sxs-lookup"><span data-stu-id="25a72-106">SQL Server Latches counters</span></span>|<span data-ttu-id="25a72-107">Описание</span><span class="sxs-lookup"><span data-stu-id="25a72-107">Description</span></span>|  
|---------------------------------|-----------------|  
|<span data-ttu-id="25a72-108">**Среднее время ожидания кратковременной блокировки (мс)**</span><span class="sxs-lookup"><span data-stu-id="25a72-108">**Average Latch Wait Time (ms)**</span></span>|<span data-ttu-id="25a72-109">Средняя длительность ожидания кратковременной блокировки запроса (в миллисекундах)</span><span class="sxs-lookup"><span data-stu-id="25a72-109">Average latch wait time (in milliseconds) for latch requests that had to wait.</span></span>|  
|<span data-ttu-id="25a72-110">**Ожиданий кратковременных блокировок в секунду**</span><span class="sxs-lookup"><span data-stu-id="25a72-110">**Latch Waits/sec**</span></span>|<span data-ttu-id="25a72-111">Количество запросов на кратковременную блокировку, при которых блокировка не была предоставлена немедленно.</span><span class="sxs-lookup"><span data-stu-id="25a72-111">Number of latch requests that could not be granted immediately.</span></span>|  
|<span data-ttu-id="25a72-112">**Количество кратких блокировок по схеме «superlatch»**</span><span class="sxs-lookup"><span data-stu-id="25a72-112">**Number of SuperLatches**</span></span>|<span data-ttu-id="25a72-113">Текущее количество кратковременных блокировок по схеме «superlatch».</span><span class="sxs-lookup"><span data-stu-id="25a72-113">Number of latches that are currently SuperLatches.</span></span>|  
|<span data-ttu-id="25a72-114">**Переключений из режима краткой блокировки по схеме «superlatch», в секунду**</span><span class="sxs-lookup"><span data-stu-id="25a72-114">**SuperLatch Demotions/sec**</span></span>|<span data-ttu-id="25a72-115">Количество блокировок по схеме «superlatch», пониженных до обычных кратковременных блокировок в течение последней секунды.</span><span class="sxs-lookup"><span data-stu-id="25a72-115">Number of SuperLatches that have been demoted to regular latches in the last second.</span></span>|  
|<span data-ttu-id="25a72-116">**Переключений в режим краткой блокировки по схеме «superlatch», в секунду**</span><span class="sxs-lookup"><span data-stu-id="25a72-116">**SuperLatch Promotions/sec**</span></span>|<span data-ttu-id="25a72-117">Количество кратковременных блокировок по схеме «superlatch» в течение последней секунды.</span><span class="sxs-lookup"><span data-stu-id="25a72-117">Number of latches that have been promoted to SuperLatches in the last second.</span></span>|  
|<span data-ttu-id="25a72-118">**Общее время ожидания кратковременной блокировки (мс)**</span><span class="sxs-lookup"><span data-stu-id="25a72-118">**Total Latch Wait Time (ms)**</span></span>|<span data-ttu-id="25a72-119">Общая длительность ожидания (в миллисекундах) после запросов кратковременной блокировки в течение последней секунды.</span><span class="sxs-lookup"><span data-stu-id="25a72-119">Total latch wait time (in milliseconds) for latch requests in the last second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25a72-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="25a72-120">See Also</span></span>  
 [<span data-ttu-id="25a72-121">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="25a72-121">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
