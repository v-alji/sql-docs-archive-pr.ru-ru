---
title: Подписка, вкладка "Журнал операций от распространителя к подписчику" (подписка на моментальные снимки) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.snapshot.f1
ms.assetid: d3575964-f287-4bcf-8d2e-f81a33141b25
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fe894e23e7ad7fef9c328334740eff73164130a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749695"
---
# <a name="subscription-distributor-to-subscriber-history-snapshot-subscription"></a><span data-ttu-id="2a1f0-102">Подписка, журнал распространителя для подписчика (подписка на моментальные снимки)</span><span class="sxs-lookup"><span data-stu-id="2a1f0-102">Subscription, Distributor to Subscriber History (Snapshot Subscription)</span></span>
  <span data-ttu-id="2a1f0-103"> Вкладка **Журнал операций от распространителя к подписчику** содержит подробные сведения об агенте распространителя, включая состояние, журнал, информационные сообщения и любые сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2a1f0-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="2a1f0-104">Options</span></span>  
 <span data-ttu-id="2a1f0-105">В меню **Вид** выберите сеансы, какого агента распространителя необходимо просмотреть, а затем в сетке **Сеансы агента распространителя**выберите определенный сеанс.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="2a1f0-106">Подробные сведения об этом сеансе отображаются в сетке, помеченной как **Действия в выбранном сеансе**.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="2a1f0-107">Если выбранный сеанс закончен с ошибкой, также выводится на экран текстовое поле, помеченное как **Описание ошибки или сообщение выбранного сеанса** .</span><span class="sxs-lookup"><span data-stu-id="2a1f0-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="2a1f0-108">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-108">**View**</span></span>  
 <span data-ttu-id="2a1f0-109">Выберите агента распространителя, сеансы которого необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-109">Select which Distribution Agent sessions to view.</span></span>  
  
 <span data-ttu-id="2a1f0-110">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-110">**Status**</span></span>  
 <span data-ttu-id="2a1f0-111">Состояние агента распространителя.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-111">The status of the Distribution Agent.</span></span> <span data-ttu-id="2a1f0-112">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="2a1f0-113">Ошибка</span><span class="sxs-lookup"><span data-stu-id="2a1f0-113">Error</span></span>  
  
-   <span data-ttu-id="2a1f0-114">Завершено</span><span class="sxs-lookup"><span data-stu-id="2a1f0-114">Completed</span></span>  
  
-   <span data-ttu-id="2a1f0-115">Повтор</span><span class="sxs-lookup"><span data-stu-id="2a1f0-115">Retrying</span></span>  
  
-   <span data-ttu-id="2a1f0-116">Запущен</span><span class="sxs-lookup"><span data-stu-id="2a1f0-116">Running</span></span>  
  
 <span data-ttu-id="2a1f0-117">**Время начала**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-117">**Start Time**</span></span>  
 <span data-ttu-id="2a1f0-118">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="2a1f0-119">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-119">**End Time**</span></span>  
 <span data-ttu-id="2a1f0-120">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-120">The end time of the session.</span></span> <span data-ttu-id="2a1f0-121">Если агент не остановлен, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="2a1f0-122">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-122">**Duration**</span></span>  
 <span data-ttu-id="2a1f0-123">Длительность работы агента распространителя в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-123">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="2a1f0-124">Если агент работает — это время, прошедшее с момента запуска. Если же сеанс агента завершен — общее время выполнения сеанса.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session had ended.</span></span>  
  
 <span data-ttu-id="2a1f0-125">**Сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-125">**Error Message**</span></span>  
 <span data-ttu-id="2a1f0-126">Если сеанс завершился ошибкой, в данном поле отображается последнее сообщение об ошибке, зарегистрированное агентом распространителя.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-126">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="2a1f0-127">Если сеанс завершился без ошибки, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="2a1f0-128">**Сообщение действия**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-128">**Action Message**</span></span>  
 <span data-ttu-id="2a1f0-129">Все информационные сообщения и сообщения об ошибках, зарегистрированные агентом распространителя в течение выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-129">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="2a1f0-130">**Время действия**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-130">**Action Time**</span></span>  
 <span data-ttu-id="2a1f0-131">Время, когда было выполнено действие, описанное в столбце **Сообщение действия** .</span><span class="sxs-lookup"><span data-stu-id="2a1f0-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="2a1f0-132">**Описание ошибки или сообщение выбранного сеанса**</span><span class="sxs-lookup"><span data-stu-id="2a1f0-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="2a1f0-133">Выводится, только если выбранный сеанс отображает значение **Ошибка** в столбце **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="2a1f0-133">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="2a1f0-134">Это текстовое поле отображает подробные данные об ошибке и о выполняемой во время возникновения ошибки команде.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="2a1f0-135">Также содержит ссылки на дополнительные данные, имеющие отношение к ошибке.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1f0-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-136">See Also</span></span>  
 <span data-ttu-id="2a1f0-137">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="2a1f0-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="2a1f0-138">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="2a1f0-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="2a1f0-139">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="2a1f0-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="2a1f0-140">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="2a1f0-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
