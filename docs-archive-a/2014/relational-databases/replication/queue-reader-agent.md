---
title: Агент чтения очереди | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.queuereaderagent.f1
helpviewer_keywords:
- Queue Reader Agent dialog box
ms.assetid: f02d24b6-dcb5-4126-b56e-fab41cfe4337
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9649223b35562da97744d79f9506615b97274870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667694"
---
# <a name="queue-reader-agent"></a><span data-ttu-id="59ae4-102">Агент чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="59ae4-102">Queue Reader Agent</span></span>
  <span data-ttu-id="59ae4-103">В диалоговом окне **Агент чтения очереди** предоставляются подробные данные об агенте чтения очереди, в том числе состояние, данные журнала, информационные сообщения и любые сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="59ae4-103">The **Queue Reader Agent** dialog box displays detailed information on the Queue Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="59ae4-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="59ae4-104">Options</span></span>  
 <span data-ttu-id="59ae4-105">Выберите для просмотра в меню **Просмотр** сеансы агента чтения очереди, а затем конкретный сеанс в сетке, обозначенный как **Сеансы агента чтения очереди**.</span><span class="sxs-lookup"><span data-stu-id="59ae4-105">Select which Queue Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Queue Reader Agent**.</span></span> <span data-ttu-id="59ae4-106">Подробные сведения об этом сеансе отображаются в сетке, помеченной как **Действия в выбранном сеансе**.</span><span class="sxs-lookup"><span data-stu-id="59ae4-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="59ae4-107">Если выбранный сеанс закончен с ошибкой, также выводится на экран текстовое поле, помеченное как **Описание ошибки или сообщение выбранного сеанса** .</span><span class="sxs-lookup"><span data-stu-id="59ae4-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="59ae4-108">**View** (Вид)</span><span class="sxs-lookup"><span data-stu-id="59ae4-108">**View**</span></span>  
 <span data-ttu-id="59ae4-109">Выбрать сеансы описываются, как агента чтения очереди для просмотра.</span><span class="sxs-lookup"><span data-stu-id="59ae4-109">Select which Queue Reader Agent sessions to view.</span></span> <span data-ttu-id="59ae4-110">Как правило, агент чтения очереди работает постоянно, поэтому просмотреть можно только один сеанс.</span><span class="sxs-lookup"><span data-stu-id="59ae4-110">The Queue Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="59ae4-111">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="59ae4-111">**Status**</span></span>  
 <span data-ttu-id="59ae4-112">Состояние агента чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="59ae4-112">The status of the Queue Reader Agent.</span></span> <span data-ttu-id="59ae4-113">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="59ae4-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="59ae4-114">Ошибка</span><span class="sxs-lookup"><span data-stu-id="59ae4-114">Error</span></span>  
  
-   <span data-ttu-id="59ae4-115">Попытка повторно выполнить неудачно завершившиеся команды</span><span class="sxs-lookup"><span data-stu-id="59ae4-115">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="59ae4-116">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="59ae4-116">Not running</span></span>  
  
-   <span data-ttu-id="59ae4-117">Запущен</span><span class="sxs-lookup"><span data-stu-id="59ae4-117">Running</span></span>  
  
 <span data-ttu-id="59ae4-118">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="59ae4-118">**Start Time**</span></span>  
 <span data-ttu-id="59ae4-119">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="59ae4-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="59ae4-120">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="59ae4-120">**End Time**</span></span>  
 <span data-ttu-id="59ae4-121">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="59ae4-121">The end time of the session.</span></span> <span data-ttu-id="59ae4-122">Если агент не остановлен, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="59ae4-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="59ae4-123">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="59ae4-123">**Duration**</span></span>  
 <span data-ttu-id="59ae4-124">Продолжительность последнего сеанса агента чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="59ae4-124">The amount of time the Queue Reader Agent has run in this session.</span></span> <span data-ttu-id="59ae4-125">Если в данный момент агент работает, отображается время его работы, после завершения сеанса агента отображается общая длительность сеанса.</span><span class="sxs-lookup"><span data-stu-id="59ae4-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="59ae4-126">**Сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="59ae4-126">**Error Message**</span></span>  
 <span data-ttu-id="59ae4-127">Если сеанс завершился ошибкой, в этом поле выводится последнее сообщение об ошибке, записанное агентом чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="59ae4-127">If a session ended in an error, this field displays the last error message logged by the Queue Reader Agent.</span></span> <span data-ttu-id="59ae4-128">Если сеанс завершился без ошибки, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="59ae4-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="59ae4-129">**Сообщение действия**</span><span class="sxs-lookup"><span data-stu-id="59ae4-129">**Action Message**</span></span>  
 <span data-ttu-id="59ae4-130">Все информационные сообщения и сообщения об ошибках, которые агент чтения очереди записал во время выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="59ae4-130">All informational messages and error messages that the Queue Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="59ae4-131">**Время действия**</span><span class="sxs-lookup"><span data-stu-id="59ae4-131">**Action Time**</span></span>  
 <span data-ttu-id="59ae4-132">Время, когда было выполнено действие, описанное в столбце **Сообщение действия** .</span><span class="sxs-lookup"><span data-stu-id="59ae4-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="59ae4-133">**Описание ошибки или сообщение выбранного сеанса**</span><span class="sxs-lookup"><span data-stu-id="59ae4-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="59ae4-134">Выводится, только если выбранный сеанс отображает значение **Ошибка** в столбце **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="59ae4-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="59ae4-135">Это текстовое поле отображает подробные данные об ошибке и о выполняемой во время возникновения ошибки команде.</span><span class="sxs-lookup"><span data-stu-id="59ae4-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="59ae4-136">Также содержит ссылки на дополнительные данные, имеющие отношение к ошибке.</span><span class="sxs-lookup"><span data-stu-id="59ae4-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ae4-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="59ae4-137">See Also</span></span>  
 <span data-ttu-id="59ae4-138">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="59ae4-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="59ae4-139">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="59ae4-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="59ae4-140">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="59ae4-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="59ae4-141">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="59ae4-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
