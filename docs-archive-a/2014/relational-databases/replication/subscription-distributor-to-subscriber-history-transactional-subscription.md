---
title: Подписка, вкладка "Журнал операций от распространителя к подписчику" (транзакционная подписка) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.disttosub.f1
ms.assetid: 1aad5b82-592e-4907-92f7-b90794175be5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5cb9d708b75a9414725907530c7454cdba26d135
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749696"
---
# <a name="subscription-distributor-to-subscriber-history-transactional-subscription"></a><span data-ttu-id="f2864-102">Подписка, журнал от распространителя к подписчику (подписка на публикацию транзакций)</span><span class="sxs-lookup"><span data-stu-id="f2864-102">Subscription, Distributor to Subscriber History (Transactional Subscription)</span></span>
  <span data-ttu-id="f2864-103"> Вкладка **Журнал операций от распространителя к подписчику** содержит подробные сведения об агенте распространителя, включая состояние, журнал, информационные сообщения и любые сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f2864-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f2864-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="f2864-104">Options</span></span>  
 <span data-ttu-id="f2864-105">В меню **Вид** выберите сеансы, какого агента распространителя необходимо просмотреть, а затем в сетке **Сеансы агента распространителя**выберите определенный сеанс.</span><span class="sxs-lookup"><span data-stu-id="f2864-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="f2864-106">Подробные сведения об этом сеансе отображаются в сетке, помеченной как **Действия в выбранном сеансе**.</span><span class="sxs-lookup"><span data-stu-id="f2864-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="f2864-107">Если выбранный сеанс закончен с ошибкой, также выводится на экран текстовое поле, помеченное как **Описание ошибки или сообщение выбранного сеанса** .</span><span class="sxs-lookup"><span data-stu-id="f2864-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="f2864-108">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="f2864-108">**View**</span></span>  
 <span data-ttu-id="f2864-109">Выберите агента распространителя, сеансы которого необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="f2864-109">Select which Distribution Agent sessions to view.</span></span> <span data-ttu-id="f2864-110">Как правило, агент распространителя работает постоянно, поэтому просмотреть можно только один сеанс.</span><span class="sxs-lookup"><span data-stu-id="f2864-110">The Distribution Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="f2864-111">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="f2864-111">**Status**</span></span>  
 <span data-ttu-id="f2864-112">Состояние агента распространителя.</span><span class="sxs-lookup"><span data-stu-id="f2864-112">The status of the Distribution Agent.</span></span> <span data-ttu-id="f2864-113">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="f2864-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="f2864-114">Ошибка</span><span class="sxs-lookup"><span data-stu-id="f2864-114">Error</span></span>  
  
-   <span data-ttu-id="f2864-115">Завершено</span><span class="sxs-lookup"><span data-stu-id="f2864-115">Completed</span></span>  
  
-   <span data-ttu-id="f2864-116">Повтор</span><span class="sxs-lookup"><span data-stu-id="f2864-116">Retrying</span></span>  
  
-   <span data-ttu-id="f2864-117">Запущен</span><span class="sxs-lookup"><span data-stu-id="f2864-117">Running</span></span>  
  
 <span data-ttu-id="f2864-118">**Время начала**</span><span class="sxs-lookup"><span data-stu-id="f2864-118">**Start Time**</span></span>  
 <span data-ttu-id="f2864-119">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="f2864-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="f2864-120">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="f2864-120">**End Time**</span></span>  
 <span data-ttu-id="f2864-121">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="f2864-121">The end time of the session.</span></span> <span data-ttu-id="f2864-122">Если агент не остановлен, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="f2864-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="f2864-123">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="f2864-123">**Duration**</span></span>  
 <span data-ttu-id="f2864-124">Длительность работы агента распространителя в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="f2864-124">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="f2864-125">Если в данный момент агент работает, отображается время его работы, после завершения сеанса агента отображается общая длительность сеанса.</span><span class="sxs-lookup"><span data-stu-id="f2864-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="f2864-126">**Сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="f2864-126">**Error Message**</span></span>  
 <span data-ttu-id="f2864-127">Если сеанс завершился ошибкой, в данном поле отображается последнее сообщение об ошибке, зарегистрированное агентом распространителя.</span><span class="sxs-lookup"><span data-stu-id="f2864-127">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="f2864-128">Если сеанс завершился без ошибки, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="f2864-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="f2864-129">**Сообщение действия**</span><span class="sxs-lookup"><span data-stu-id="f2864-129">**Action Message**</span></span>  
 <span data-ttu-id="f2864-130">Все информационные сообщения и сообщения об ошибках, зарегистрированные агентом распространителя в течение выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="f2864-130">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="f2864-131">**Время действия**</span><span class="sxs-lookup"><span data-stu-id="f2864-131">**Action Time**</span></span>  
 <span data-ttu-id="f2864-132">Время, когда было выполнено действие, описанное в столбце **Сообщение действия** .</span><span class="sxs-lookup"><span data-stu-id="f2864-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="f2864-133">**Описание ошибки или сообщение выбранного сеанса**</span><span class="sxs-lookup"><span data-stu-id="f2864-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="f2864-134">Выводится, только если выбранный сеанс отображает значение **Ошибка** в столбце **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="f2864-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="f2864-135">Это текстовое поле отображает подробные данные об ошибке и о выполняемой во время возникновения ошибки команде.</span><span class="sxs-lookup"><span data-stu-id="f2864-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="f2864-136">Также содержит ссылки на дополнительные данные, имеющие отношение к ошибке.</span><span class="sxs-lookup"><span data-stu-id="f2864-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2864-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2864-137">See Also</span></span>  
 <span data-ttu-id="f2864-138">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f2864-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f2864-139">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f2864-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="f2864-140">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="f2864-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="f2864-141">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="f2864-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
