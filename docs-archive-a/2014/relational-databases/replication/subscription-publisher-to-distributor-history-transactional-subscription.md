---
title: Подписка, вкладка "Журнал операций от издателя к распространителю" (транзакционная подписка) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.tran.f1
ms.assetid: d5a4c697-1342-49fd-8b7b-b059af32556a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3806c59e545e325fa7e60f2cd92a4b990b0505cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752103"
---
# <a name="subscription-publisher-to-distributor-history-transactional-subscription"></a><span data-ttu-id="fa66d-102">Подписка, журнал издателя для распространителя (подписка на публикацию транзакций)</span><span class="sxs-lookup"><span data-stu-id="fa66d-102">Subscription, Publisher to Distributor History (Transactional Subscription)</span></span>
  <span data-ttu-id="fa66d-103">Вкладка **Журнал операций от издателя к распространителю** отображает подробные сведения об агенте чтения журнала, включая состояние, журнал, информационные сообщения и любые сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="fa66d-103">The **Publisher to Distributor History** tab displays detailed information on the Log Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa66d-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="fa66d-104">Options</span></span>  
 <span data-ttu-id="fa66d-105">В меню **Вид** выберите сеансы какого агента чтения журнала необходимо просмотреть, а затем в сетке **Сеансы агента чтения журнала**выберите определенный сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa66d-105">Select which Log Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Log Reader Agent**.</span></span> <span data-ttu-id="fa66d-106">Подробные сведения об этом сеансе отображаются в сетке, помеченной как **Действия в выбранном сеансе**.</span><span class="sxs-lookup"><span data-stu-id="fa66d-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="fa66d-107">Если выбранный сеанс закончен с ошибкой, также выводится на экран текстовое поле, помеченное как **Описание ошибки или сообщение выбранного сеанса** .</span><span class="sxs-lookup"><span data-stu-id="fa66d-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="fa66d-108">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="fa66d-108">**View**</span></span>  
 <span data-ttu-id="fa66d-109">Выберите агента чтения журнала, сеансы которого необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="fa66d-109">Select which Log Reader Agent sessions to view.</span></span> <span data-ttu-id="fa66d-110">Обычно агент чтения журнала работает постоянно, поэтому просмотреть можно только один сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa66d-110">The Log Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="fa66d-111">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="fa66d-111">**Status**</span></span>  
 <span data-ttu-id="fa66d-112">Состояние агента чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="fa66d-112">The status of the Log Reader Agent.</span></span> <span data-ttu-id="fa66d-113">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="fa66d-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="fa66d-114">Ошибка</span><span class="sxs-lookup"><span data-stu-id="fa66d-114">Error</span></span>  
  
-   <span data-ttu-id="fa66d-115">Завершено</span><span class="sxs-lookup"><span data-stu-id="fa66d-115">Completed</span></span>  
  
-   <span data-ttu-id="fa66d-116">Повтор</span><span class="sxs-lookup"><span data-stu-id="fa66d-116">Retrying</span></span>  
  
-   <span data-ttu-id="fa66d-117">Запущен</span><span class="sxs-lookup"><span data-stu-id="fa66d-117">Running</span></span>  
  
 <span data-ttu-id="fa66d-118">**Время начала**</span><span class="sxs-lookup"><span data-stu-id="fa66d-118">**Start Time**</span></span>  
 <span data-ttu-id="fa66d-119">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="fa66d-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="fa66d-120">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="fa66d-120">**End Time**</span></span>  
 <span data-ttu-id="fa66d-121">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="fa66d-121">The end time of the session.</span></span> <span data-ttu-id="fa66d-122">Если агент не остановлен, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="fa66d-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="fa66d-123">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="fa66d-123">**Duration**</span></span>  
 <span data-ttu-id="fa66d-124">Длительность работы агента чтения журнала в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="fa66d-124">The amount of time the Log Reader Agent has run in this session.</span></span> <span data-ttu-id="fa66d-125">Если в данный момент агент работает, отображается время его работы, после завершения сеанса агента отображается общая длительность сеанса.</span><span class="sxs-lookup"><span data-stu-id="fa66d-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="fa66d-126">**Сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="fa66d-126">**Error Message**</span></span>  
 <span data-ttu-id="fa66d-127">Если сеанс завершился с ошибкой, в данном поле отображается последнее сообщение об ошибке, зарегистрированное агентом чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="fa66d-127">If a session ended in an error, this field displays the last error message logged by the Log Reader Agent.</span></span> <span data-ttu-id="fa66d-128">Если сеанс завершился без ошибки, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="fa66d-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="fa66d-129">**Сообщение действия**</span><span class="sxs-lookup"><span data-stu-id="fa66d-129">**Action Message**</span></span>  
 <span data-ttu-id="fa66d-130">Все информационные сообщения и сообщения об ошибках, зарегистрированные агентом чтения журнала в течение выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="fa66d-130">All informational messages and error messages that the Log Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="fa66d-131">**Время действия**</span><span class="sxs-lookup"><span data-stu-id="fa66d-131">**Action Time**</span></span>  
 <span data-ttu-id="fa66d-132">Время, когда было выполнено действие, описанное в столбце **Сообщение действия** .</span><span class="sxs-lookup"><span data-stu-id="fa66d-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="fa66d-133">**Описание ошибки или сообщение выбранного сеанса**</span><span class="sxs-lookup"><span data-stu-id="fa66d-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="fa66d-134">Выводится, только если выбранный сеанс отображает значение **Ошибка** в столбце **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="fa66d-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="fa66d-135">Это текстовое поле отображает подробные данные об ошибке и о выполняемой во время возникновения ошибки команде.</span><span class="sxs-lookup"><span data-stu-id="fa66d-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="fa66d-136">Также содержит ссылки на дополнительные данные, имеющие отношение к ошибке.</span><span class="sxs-lookup"><span data-stu-id="fa66d-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa66d-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa66d-137">See Also</span></span>  
 <span data-ttu-id="fa66d-138">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="fa66d-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="fa66d-139">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="fa66d-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="fa66d-140">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="fa66d-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="fa66d-141">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="fa66d-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
