---
title: MSSQLSERVER_32042 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32042 (Database Engine error)
ms.assetid: 53a51c7a-dcd4-4c15-b4d2-6aaa9dce76da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd959d84da2c54310dea5156b1a45b73490211a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658788"
---
# <a name="mssqlserver_32042"></a><span data-ttu-id="bd8c4-102">MSSQLSERVER_32042</span><span class="sxs-lookup"><span data-stu-id="bd8c4-102">MSSQLSERVER_32042</span></span>
    
## <a name="details"></a><span data-ttu-id="bd8c4-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bd8c4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd8c4-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bd8c4-104">Product Name</span></span>|<span data-ttu-id="bd8c4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd8c4-105">SQL Server</span></span>|  
|<span data-ttu-id="bd8c4-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bd8c4-106">Event ID</span></span>|<span data-ttu-id="bd8c4-107">32042</span><span class="sxs-lookup"><span data-stu-id="bd8c4-107">32042</span></span>|  
|<span data-ttu-id="bd8c4-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="bd8c4-108">Event Source</span></span>|<span data-ttu-id="bd8c4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bd8c4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bd8c4-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="bd8c4-110">Component</span></span>|<span data-ttu-id="bd8c4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bd8c4-111">SQLEngine</span></span>|  
|<span data-ttu-id="bd8c4-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="bd8c4-112">Symbolic Name</span></span>|<span data-ttu-id="bd8c4-113">SQLErrorNum32042</span><span class="sxs-lookup"><span data-stu-id="bd8c4-113">SQLErrorNum32042</span></span>|  
|<span data-ttu-id="bd8c4-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bd8c4-114">Message Text</span></span>|<span data-ttu-id="bd8c4-115">Было активировано предупреждение «unsent log».</span><span class="sxs-lookup"><span data-stu-id="bd8c4-115">The alert for 'unsent log' has been raised.</span></span> <span data-ttu-id="bd8c4-116">Текущее значение «%d» превосходит пороговое значение «%d».</span><span class="sxs-lookup"><span data-stu-id="bd8c4-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd8c4-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bd8c4-117">Explanation</span></span>  
 <span data-ttu-id="bd8c4-118">Это событие зеркального отображения базы данных произошло на экземпляре основного сервера и указывает, что объем неотправленного журнала достиг указанного пользователем порогового значения.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-118">This database mirroring event is issued on the principal server instance to indicate that the amount of unsent log has reached a user-specified threshold value.</span></span> <span data-ttu-id="bd8c4-119">Обычно причиной этого события становится изменение показателей производительности системы.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="bd8c4-120">Либо уменьшилась пропускная способность между двумя системами, либо возросла нагрузка.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="bd8c4-121">Объем неотправленного журнала — это показатель производительности, позволяющий оценить вероятность потери данных в зависимости от объема (в килобайтах) неотправленного журнала.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-121">The amount of unsent log is a performance metric that can help you evaluate the potential for data loss in terms of the number of kilobytes (KB) of unsent log.</span></span> <span data-ttu-id="bd8c4-122">Эта метрика особенно важна для сеансов, выполняемых в высокопроизводительном режиме.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-122">This metric is particularly relevant for high-performance mode sessions.</span></span> <span data-ttu-id="bd8c4-123">Однако она также важна для сеансов режима высокого уровня безопасности, когда зеркальное отображение приостанавливается или откладывается из-за потери соединения между участниками.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-123">However, this metric is also a relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd8c4-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bd8c4-124">User Action</span></span>  
 <span data-ttu-id="bd8c4-125">Проверьте, не является ли причиной ошибки уровень нагрузки на экземпляр основного или зеркального серверов или сетевое соединение между ними.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd8c4-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-126">See Also</span></span>  
 <span data-ttu-id="bd8c4-127">[Зеркальное отображение базы данных (SQL Server)](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bd8c4-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="bd8c4-128">Использование пороговых значений предупреждений и оповещений в метриках производительности зеркального отображения (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bd8c4-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
