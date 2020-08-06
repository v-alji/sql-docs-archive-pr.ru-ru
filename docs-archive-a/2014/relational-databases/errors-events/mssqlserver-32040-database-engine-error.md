---
title: MSSQLSERVER_32040 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32040 (Database Engine error)
ms.assetid: 709219b1-f8b2-4696-8923-dd2e91492eb8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05692e2f20b0719c1ca8f48282c3b7aaed8e2341
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658789"
---
# <a name="mssqlserver_32040"></a><span data-ttu-id="08f86-102">MSSQLSERVER_32040</span><span class="sxs-lookup"><span data-stu-id="08f86-102">MSSQLSERVER_32040</span></span>
    
## <a name="details"></a><span data-ttu-id="08f86-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="08f86-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08f86-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="08f86-104">Product Name</span></span>|<span data-ttu-id="08f86-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="08f86-105">SQL Server</span></span>|  
|<span data-ttu-id="08f86-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="08f86-106">Event ID</span></span>|<span data-ttu-id="08f86-107">32040</span><span class="sxs-lookup"><span data-stu-id="08f86-107">32040</span></span>|  
|<span data-ttu-id="08f86-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="08f86-108">Event Source</span></span>|<span data-ttu-id="08f86-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="08f86-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="08f86-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="08f86-110">Component</span></span>|<span data-ttu-id="08f86-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="08f86-111">SQLEngine</span></span>|  
|<span data-ttu-id="08f86-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="08f86-112">Symbolic Name</span></span>|<span data-ttu-id="08f86-113">SQLErrorNum32040</span><span class="sxs-lookup"><span data-stu-id="08f86-113">SQLErrorNum32040</span></span>|  
|<span data-ttu-id="08f86-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="08f86-114">Message Text</span></span>|<span data-ttu-id="08f86-115">Активировано предупреждение «Самая старая неотправленная транзакция».</span><span class="sxs-lookup"><span data-stu-id="08f86-115">The alert for 'oldest unsent transaction' has been raised.</span></span> <span data-ttu-id="08f86-116">Текущее значение «%d» превосходит пороговое значение «%d».</span><span class="sxs-lookup"><span data-stu-id="08f86-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08f86-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="08f86-117">Explanation</span></span>  
 <span data-ttu-id="08f86-118">Это событие зеркального отображения базы данных происходит на экземпляре основного сервера и указывает, что возраст самой старой неотправленной транзакции достиг указанного пользователем порогового значения.</span><span class="sxs-lookup"><span data-stu-id="08f86-118">This database mirroring event is issued on the principal server instance to indicate that the age of the oldest unsent transaction has reached a user-specified threshold value.</span></span> <span data-ttu-id="08f86-119">Обычно причиной этого события становится изменение показателей производительности системы.</span><span class="sxs-lookup"><span data-stu-id="08f86-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="08f86-120">Либо уменьшилась пропускная способность между двумя системами, либо возросла нагрузка.</span><span class="sxs-lookup"><span data-stu-id="08f86-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="08f86-121">Возраст самой старой неотправленной транзакции представляет собой показатель производительности, который позволяет оценить вероятность утери данных в зависимости от длительности (в минутах) неотправленных транзакций.</span><span class="sxs-lookup"><span data-stu-id="08f86-121">The age of the oldest unsent transaction is a performance metric that can help you evaluate the potential for data loss as measured by the number of minutes of unsent transactions.</span></span> <span data-ttu-id="08f86-122">Эта метрика особенно важна для сеансов, выполняемых в высокопроизводительном режиме.</span><span class="sxs-lookup"><span data-stu-id="08f86-122">This metric is especially relevant for high-performance mode sessions.</span></span> <span data-ttu-id="08f86-123">Однако она также важна для сеансов режима высокого уровня безопасности, когда зеркальное отображение приостанавливается или откладывается из-за потери соединения между участниками.</span><span class="sxs-lookup"><span data-stu-id="08f86-123">However, this metric is also relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08f86-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="08f86-124">User Action</span></span>  
 <span data-ttu-id="08f86-125">Проверьте, не является ли причиной ошибки уровень нагрузки на экземпляр основного или зеркального серверов или сетевое соединение между ними.</span><span class="sxs-lookup"><span data-stu-id="08f86-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f86-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="08f86-126">See Also</span></span>  
 <span data-ttu-id="08f86-127">[Зеркальное отображение базы данных (SQL Server)](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="08f86-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="08f86-128">Использование пороговых значений предупреждений и оповещений в метриках производительности зеркального отображения (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08f86-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
