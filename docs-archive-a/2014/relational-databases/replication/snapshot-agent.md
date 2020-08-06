---
title: Агент моментальных снимков | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.snapshotagent.f1
helpviewer_keywords:
- Snapshot Agent dialog box
ms.assetid: b715e621-2cd5-4a15-8f58-a341aa8ef5e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 925f2d3841b5dded6c8504a4a05dc60e61024161
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668759"
---
# <a name="snapshot-agent"></a><span data-ttu-id="023a5-102">агент моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="023a5-102">Snapshot Agent</span></span>
  <span data-ttu-id="023a5-103">В диалоговом окне **Агент моментальных снимков** отображаются подробные сведения об агенте моментальных снимков, в том числе состояние, журнал, информационные сообщения и сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="023a5-103">The **Snapshot Agent** dialog box displays detailed information on the Snapshot Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="023a5-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="023a5-104">Options</span></span>  
 <span data-ttu-id="023a5-105">Выберите в меню **Вид** , какие сеансы агента моментальных снимков нужно просматривать, затем выберите определенный сеанс в сетке с именем **Сеансы агента моментальных снимков**.</span><span class="sxs-lookup"><span data-stu-id="023a5-105">Select which Snapshot Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Snapshot Agent**.</span></span> <span data-ttu-id="023a5-106">Подробные сведения об этом сеансе отображаются в сетке, помеченной как **Действия в выбранном сеансе**.</span><span class="sxs-lookup"><span data-stu-id="023a5-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="023a5-107">Если выбранный сеанс закончен с ошибкой, также выводится на экран текстовое поле, помеченное как **Описание ошибки или сообщение выбранного сеанса** .</span><span class="sxs-lookup"><span data-stu-id="023a5-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="023a5-108">**View** (Вид)</span><span class="sxs-lookup"><span data-stu-id="023a5-108">**View**</span></span>  
 <span data-ttu-id="023a5-109">Выберите сеансы агента моментальных снимков, которые нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="023a5-109">Select which Snapshot Agent sessions to view.</span></span>  
  
 <span data-ttu-id="023a5-110">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="023a5-110">**Status**</span></span>  
 <span data-ttu-id="023a5-111">Состояние агента моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="023a5-111">The status of the Snapshot Agent.</span></span> <span data-ttu-id="023a5-112">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="023a5-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="023a5-113">Ошибка</span><span class="sxs-lookup"><span data-stu-id="023a5-113">Error</span></span>  
  
-   <span data-ttu-id="023a5-114">Попытка повторно выполнить неудачно завершившиеся команды</span><span class="sxs-lookup"><span data-stu-id="023a5-114">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="023a5-115">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="023a5-115">Not running</span></span>  
  
-   <span data-ttu-id="023a5-116">Завершено</span><span class="sxs-lookup"><span data-stu-id="023a5-116">Completed</span></span>  
  
 <span data-ttu-id="023a5-117">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="023a5-117">**Start Time**</span></span>  
 <span data-ttu-id="023a5-118">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="023a5-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="023a5-119">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="023a5-119">**End Time**</span></span>  
 <span data-ttu-id="023a5-120">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="023a5-120">The end time of the session.</span></span> <span data-ttu-id="023a5-121">Если агент не остановлен, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="023a5-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="023a5-122">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="023a5-122">**Duration**</span></span>  
 <span data-ttu-id="023a5-123">Общее время работы этого сеанса агента моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="023a5-123">The amount of time the Snapshot Agent has run in this session.</span></span> <span data-ttu-id="023a5-124">Если в данный момент агент работает, отображается время его работы, после завершения сеанса агента отображается общая длительность сеанса.</span><span class="sxs-lookup"><span data-stu-id="023a5-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="023a5-125">**Сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="023a5-125">**Error Message**</span></span>  
 <span data-ttu-id="023a5-126">Если сеанс завершился с ошибкой, в данном поле отображается последнее сообщение об ошибке, зарегистрированное агентом моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="023a5-126">If a session ended in an error, this field displays the last error message logged by the Snapshot Agent.</span></span> <span data-ttu-id="023a5-127">Если сеанс завершился без ошибки, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="023a5-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="023a5-128">**Сообщение действия**</span><span class="sxs-lookup"><span data-stu-id="023a5-128">**Action Message**</span></span>  
 <span data-ttu-id="023a5-129">Все информационные сообщения и сообщения об ошибках, зарегистрированные агентом моментальных снимков во время выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="023a5-129">All informational messages and error messages that the Snapshot Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="023a5-130">**Время действия**</span><span class="sxs-lookup"><span data-stu-id="023a5-130">**Action Time**</span></span>  
 <span data-ttu-id="023a5-131">Время, когда было выполнено действие, описанное в столбце **Сообщение действия** .</span><span class="sxs-lookup"><span data-stu-id="023a5-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="023a5-132">**Описание ошибки или сообщение выбранного сеанса**</span><span class="sxs-lookup"><span data-stu-id="023a5-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="023a5-133">Выводится, только если выбранный сеанс отображает значение **Ошибка** в столбце **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="023a5-133">Is displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="023a5-134">Это текстовое поле отображает подробные данные об ошибке и о выполняемой во время возникновения ошибки команде.</span><span class="sxs-lookup"><span data-stu-id="023a5-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="023a5-135">Также содержит ссылки на дополнительные данные, имеющие отношение к ошибке.</span><span class="sxs-lookup"><span data-stu-id="023a5-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023a5-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="023a5-136">See Also</span></span>  
 <span data-ttu-id="023a5-137">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="023a5-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="023a5-138">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="023a5-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="023a5-139">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="023a5-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="023a5-140">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="023a5-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
