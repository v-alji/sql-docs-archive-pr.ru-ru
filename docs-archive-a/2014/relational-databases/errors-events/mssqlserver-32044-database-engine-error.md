---
title: MSSQLSERVER_32044 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32044 (Database Engine error)
ms.assetid: f2d073be-d9a1-4837-8a38-028d3e3403bd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27d9655c3a908f1302f048c6f68159d4f610367a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658787"
---
# <a name="mssqlserver_32044"></a><span data-ttu-id="46976-102">MSSQLSERVER_32044</span><span class="sxs-lookup"><span data-stu-id="46976-102">MSSQLSERVER_32044</span></span>
    
## <a name="details"></a><span data-ttu-id="46976-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="46976-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46976-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="46976-104">Product Name</span></span>|<span data-ttu-id="46976-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="46976-105">SQL Server</span></span>|  
|<span data-ttu-id="46976-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="46976-106">Event ID</span></span>|<span data-ttu-id="46976-107">32044</span><span class="sxs-lookup"><span data-stu-id="46976-107">32044</span></span>|  
|<span data-ttu-id="46976-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="46976-108">Event Source</span></span>|<span data-ttu-id="46976-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46976-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46976-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="46976-110">Component</span></span>|<span data-ttu-id="46976-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46976-111">SQLEngine</span></span>|  
|<span data-ttu-id="46976-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="46976-112">Symbolic Name</span></span>|<span data-ttu-id="46976-113">SQLErrorNum32044</span><span class="sxs-lookup"><span data-stu-id="46976-113">SQLErrorNum32044</span></span>|  
|<span data-ttu-id="46976-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="46976-114">Message Text</span></span>|<span data-ttu-id="46976-115">Активировано предупреждение «Затраты на фиксирование транзакции на зеркальном сервере».</span><span class="sxs-lookup"><span data-stu-id="46976-115">The alert for 'mirror commit overhead' has been raised.</span></span> <span data-ttu-id="46976-116">Текущее значение «%d» превосходит пороговое значение «%d».</span><span class="sxs-lookup"><span data-stu-id="46976-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46976-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="46976-117">Explanation</span></span>  
 <span data-ttu-id="46976-118">Это событие зеркального отображения базы данных вызывается на экземпляре основного сервера для уведомления о том, что общее время ожидания фиксации достигло или превысило указанное пользователем пороговое значение из-за выполнения зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="46976-118">This database mirroring event is issued on the principal server instance to indicate that the aggregate commit wait time reached or exceeded a user-specified threshold value because of database mirroring.</span></span> <span data-ttu-id="46976-119">Время ожидания представляет собой произведение числа транзакций на время каждой из них.</span><span class="sxs-lookup"><span data-stu-id="46976-119">The wait time is the product of the number of transactions and the time of each.</span></span> <span data-ttu-id="46976-120">Например, в следующих случаях время ожидания одинаковое и составляет 1000 миллисекунд: 1000 транзакций \* 1 миллисекунду и 1 транзакция \* 1000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="46976-120">For example, the following cases both produce 1000 milliseconds of wait time: 1000 transactions \* 1 millisecond, and 1 transaction \* 1000 milliseconds.</span></span> <span data-ttu-id="46976-121">Увеличение времени ожидания фиксации может вызываться резким повышением количества транзакций, а также задержками при отправке данных в журнал или сбросе журнала на экземпляре зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="46976-121">An increased commit wait time can be caused by a surge in the transaction count, delays in sending the log, or delays in flushing the log on the mirror server instance.</span></span>  
  
 <span data-ttu-id="46976-122">Объем затрат на фиксацию изменений на зеркальном сервере — это показатель производительности, который позволяет оценить влияние синхронной операции на текущую производительность.</span><span class="sxs-lookup"><span data-stu-id="46976-122">The amount of mirror commit overhead is a performance metric that can help you evaluate the current performance impact of synchronous operation.</span></span> <span data-ttu-id="46976-123">Этот показатель важен только в режиме высокого уровня безопасности.</span><span class="sxs-lookup"><span data-stu-id="46976-123">This metric is relevant only in high-safety mode.</span></span> <span data-ttu-id="46976-124">Так как высокий уровень безопасности является синхронным, экземпляр основного сервера не фиксирует транзакцию до тех пор, пока не отправит запись журнала на экземпляр зеркального сервера и не получит подтверждение о том, что на экземпляре зеркального сервера запись журнала была записана на диск.</span><span class="sxs-lookup"><span data-stu-id="46976-124">Because high-safety mode is synchronous, the principal server instance waits to commit the transaction after it sends a log record to the mirror server instance until it receives confirmation that the mirror server instance has written the log record to disk.</span></span> <span data-ttu-id="46976-125">Запись журнала остается на диске экземпляра зеркального сервера, ожидая восстановления в зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="46976-125">The log record remains on disk on the mirror server instance while it waits to be restored to the mirror database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46976-126">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="46976-126">User Action</span></span>  
 <span data-ttu-id="46976-127">Проверьте, не является ли причиной ошибки уровень нагрузки на экземпляр основного или зеркального серверов или сетевое соединение между ними.</span><span class="sxs-lookup"><span data-stu-id="46976-127">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46976-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="46976-128">See Also</span></span>  
 <span data-ttu-id="46976-129">[Зеркальное отображение базы данных (SQL Server)](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="46976-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="46976-130">Использование пороговых значений предупреждений и оповещений в метриках производительности зеркального отображения (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="46976-130">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
