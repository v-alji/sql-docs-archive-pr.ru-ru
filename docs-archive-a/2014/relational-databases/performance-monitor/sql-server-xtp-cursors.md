---
title: Курсоры XTP | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 84bf4654-3ef7-4d7f-a269-c8bb4ed4acad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 217a1196717492cb92adb24eaf7c06c8867abc2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735214"
---
# <a name="xtp-cursors"></a><span data-ttu-id="afabb-102">Курсоры XTP</span><span class="sxs-lookup"><span data-stu-id="afabb-102">XTP Cursors</span></span>
  <span data-ttu-id="afabb-103">Объект производительности XTP Cursors содержит счетчики, относящиеся к внутренним курсорам механизма XTP.</span><span class="sxs-lookup"><span data-stu-id="afabb-103">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="afabb-104">Курсоры — низкоуровневые строительные блоки, используемые механизмом XTP для обработки запросов [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afabb-104">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="afabb-105">Обычно вы не имеете прямого контроля над ними как таковыми.</span><span class="sxs-lookup"><span data-stu-id="afabb-105">As such, you do not typically have direct control over them.</span></span>  
  
 <span data-ttu-id="afabb-106">В этой таблице описаны счетчики **курсоров XTP** .</span><span class="sxs-lookup"><span data-stu-id="afabb-106">This table describes the **XTP Cursors** counters.</span></span>  
  
|<span data-ttu-id="afabb-107">Счетчик</span><span class="sxs-lookup"><span data-stu-id="afabb-107">Counter</span></span>|<span data-ttu-id="afabb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="afabb-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="afabb-109">**Удалений курсоров/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-109">**Cursor deletes/sec**</span></span>|<span data-ttu-id="afabb-110">Число удалений курсоров (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-110">The number of cursor deletes (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-111">**Вставок курсоров/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-111">**Cursor inserts/sec**</span></span>|<span data-ttu-id="afabb-112">Число вставок курсоров (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-112">The number of cursor inserts (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-113">**Начатые сканирования курсоров/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-113">**Cursor scans started /sec**</span></span>|<span data-ttu-id="afabb-114">Число начатых сканирований курсоров (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-114">The number of cursor scans started (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-115">**Нарушений уникальности курсоров/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-115">**Cursor unique violations/sec**</span></span>|<span data-ttu-id="afabb-116">Число нарушений ограничений уникальности курсоров (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-116">The number of unique-constraint violations (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-117">**Обновлений курсоров/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-117">**Cursor updates/sec**</span></span>|<span data-ttu-id="afabb-118">Число обновлений курсоров (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-118">The number of cursor updates (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-119">**Конфликты записи курсора/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-119">**Cursor write   conflicts/sec**</span></span>|<span data-ttu-id="afabb-120">Число конфликтов «запись-запись» в одну версию строки (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-120">The number of write-write conflicts to the same row version (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-121">**Число попыток сканирования «пыльных углов»/с (от пользователя)**</span><span class="sxs-lookup"><span data-stu-id="afabb-121">**Dusty corner scan retries/sec (user-issued)**</span></span>|<span data-ttu-id="afabb-122">Число повторных попыток сканирования из-за конфликтов записи при обработке «пыльных углов», выданное при сканировании полной таблицы пользователем (в среднем), в секунду</span><span class="sxs-lookup"><span data-stu-id="afabb-122">The number of scan retries due to write conflicts during dusty corner sweeps issued by a user's full-table scan (on average), per second.</span></span> <span data-ttu-id="afabb-123">Это счетчик очень низкого уровня, не предназначенный для пользователей.</span><span class="sxs-lookup"><span data-stu-id="afabb-123">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="afabb-124">**Удаленные просроченные строки/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-124">**Expired rows removed/sec**</span></span>|<span data-ttu-id="afabb-125">Число просроченных строк, удаленных курсорами (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-125">The number of expired rows removed by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-126">**Затронутых просроченных строк/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-126">**Expired rows touched/sec**</span></span>|<span data-ttu-id="afabb-127">Число просроченных строк, затронутых курсорами (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-127">The number of expired rows touched by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-128">**Возвращено строк/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-128">**Rows returned/sec**</span></span>|<span data-ttu-id="afabb-129">Число строк, возвращенных курсорами (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-129">The number of rows returned by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-130">**Затронутых строк/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-130">**Rows touched/sec**</span></span>|<span data-ttu-id="afabb-131">Число строк, затронутых курсорами (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-131">The number of rows touched by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="afabb-132">**Затронутых условно удаленных строк/с**</span><span class="sxs-lookup"><span data-stu-id="afabb-132">**Tentatively-deleted rows touched/sec**</span></span>|<span data-ttu-id="afabb-133">Число строк с истекающим сроком действия, затронутых курсорами (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="afabb-133">The number of expiring rows touched by cursors (on average), per second.</span></span> <span data-ttu-id="afabb-134">Срок действия строки истекает, если удалившая ее транзакция все еще активна (т. е. пока не зафиксирована или не отменена.)</span><span class="sxs-lookup"><span data-stu-id="afabb-134">A row is expiring if the transaction that deleted it is still active (i.e. has not yet committed or aborted.)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afabb-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="afabb-135">See Also</span></span>  
 [<span data-ttu-id="afabb-136">Счетчики производительности XTP &#40;в памяти OLTP&#41;</span><span class="sxs-lookup"><span data-stu-id="afabb-136">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
