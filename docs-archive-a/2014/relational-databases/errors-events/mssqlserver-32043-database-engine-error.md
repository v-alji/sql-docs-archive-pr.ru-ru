---
title: MSSQLSERVER_32043 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32043 (Database Engine error)
ms.assetid: a0c48ae3-4c8c-419c-afb5-579fcefac01d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2febc7173c8144451c7a9b0576f2293d5594c6df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655237"
---
# <a name="mssqlserver_32043"></a><span data-ttu-id="14b4f-102">MSSQLSERVER_32043</span><span class="sxs-lookup"><span data-stu-id="14b4f-102">MSSQLSERVER_32043</span></span>
    
## <a name="details"></a><span data-ttu-id="14b4f-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="14b4f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14b4f-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="14b4f-104">Product Name</span></span>|<span data-ttu-id="14b4f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="14b4f-105">SQL Server</span></span>|  
|<span data-ttu-id="14b4f-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="14b4f-106">Event ID</span></span>|<span data-ttu-id="14b4f-107">32043</span><span class="sxs-lookup"><span data-stu-id="14b4f-107">32043</span></span>|  
|<span data-ttu-id="14b4f-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="14b4f-108">Event Source</span></span>|<span data-ttu-id="14b4f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="14b4f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="14b4f-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="14b4f-110">Component</span></span>|<span data-ttu-id="14b4f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="14b4f-111">SQLEngine</span></span>|  
|<span data-ttu-id="14b4f-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="14b4f-112">Symbolic Name</span></span>|<span data-ttu-id="14b4f-113">SQLErrorNum32043</span><span class="sxs-lookup"><span data-stu-id="14b4f-113">SQLErrorNum32043</span></span>|  
|<span data-ttu-id="14b4f-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="14b4f-114">Message Text</span></span>|<span data-ttu-id="14b4f-115">Активировано предупреждение «Невосстановленный журнал».</span><span class="sxs-lookup"><span data-stu-id="14b4f-115">The alert for 'unrestored log' has been raised.</span></span> <span data-ttu-id="14b4f-116">Текущее значение «%d» превосходит пороговое значение «%d».</span><span class="sxs-lookup"><span data-stu-id="14b4f-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14b4f-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="14b4f-117">Explanation</span></span>  
 <span data-ttu-id="14b4f-118">Это событие зеркального отображения базы данных произошло на экземпляре зеркального сервера и указывает, что объем невосстановленного журнала достиг указанного пользователем порогового значения.</span><span class="sxs-lookup"><span data-stu-id="14b4f-118">This database mirroring event is issued on the mirror server instance to indicate that the amount of unrestored log reached a user-specified threshold value.</span></span> <span data-ttu-id="14b4f-119">Обычно причиной этого события становится изменение показателей производительности системы.</span><span class="sxs-lookup"><span data-stu-id="14b4f-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="14b4f-120">Либо уменьшилась пропускная способность между двумя системами, либо возросла нагрузка.</span><span class="sxs-lookup"><span data-stu-id="14b4f-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="14b4f-121">Невосстановленный журнал — это журнал, полученный экземпляром зеркального сервера и записанный на диск, который ожидает восстановления в зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="14b4f-121">An unrestored log is a log that has been received by the mirror server instance and written to disk but is waiting to be restored to the mirror database.</span></span> <span data-ttu-id="14b4f-122">Объем невосстановленного журнала в килобайтах (КБ) представляет собой показатель производительности, позволяющий оценить значение текущего времени отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="14b4f-122">The amount of unrestored log in kilobytes (KB) is a performance metric that can help you evaluate the current failover time.</span></span> <span data-ttu-id="14b4f-123">Время, необходимое для применения невосстановленного журнала, — это главный фактор, определяющий время отработки отказа; также учитывается небольшой промежуток времени, требуемый для восстановления базы данных и перевода ее в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="14b4f-123">The time that is required to apply the unrestored log is the main factor in failover time, along with a short additional time that is required to recover the database and bring it online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14b4f-124">В режиме автоматической отработки отказа время, необходимое системе для уведомления о сбое, не зависит от времени отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="14b4f-124">For an automatic failover, the time for the system to notice the failure is independent of the failover time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14b4f-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="14b4f-125">User Action</span></span>  
 <span data-ttu-id="14b4f-126">Проверьте, не является ли причиной ошибки уровень нагрузки на экземпляр основного или зеркального серверов или сетевое соединение между ними.</span><span class="sxs-lookup"><span data-stu-id="14b4f-126">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b4f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="14b4f-127">See Also</span></span>  
 <span data-ttu-id="14b4f-128">[Зеркальное отображение базы данных (SQL Server)](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="14b4f-128">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="14b4f-129">Использование пороговых значений предупреждений и оповещений в метриках производительности зеркального отображения (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="14b4f-129">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
