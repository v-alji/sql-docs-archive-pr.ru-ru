---
title: Подписка, журнал синхронизации (подписка на публикацию слиянием, SQL Server 2005 и более поздние версии) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.synchhistory.f1
- sql12.rep.monitor.subscription.downlevelsynchhistory.f1
ms.assetid: 85f666f6-14ee-4f19-b385-e5cc508aabe4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49fe19f22976116813ac2454b2d08fc1fe47d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667032"
---
# <a name="subscription-synchronization-history-merge-subscription-sql-server-2005-and-later"></a><span data-ttu-id="d2fff-102">Подписка, журнал синхронизации (подписка на публикацию слиянием, SQL Server 2005 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d2fff-102">Subscription, Synchronization History (Merge Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="d2fff-103">На вкладке **Журнал синхронизации** отображаются подробные сведения об агенте слияния, включая состояние, статистику по статьям, данные журнала, информационные сообщения и все сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d2fff-103">The **Synchronization History** tab displays detailed information on the Merge Agent, including status, article statistics, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d2fff-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2fff-104">Options</span></span>  
 <span data-ttu-id="d2fff-105">Выберите сеансы агента слияния для просмотра из меню **Вид** , а затем выберите конкретный сеанс в сетке с названием **Сеансы агента слияния**.</span><span class="sxs-lookup"><span data-stu-id="d2fff-105">Select which Merge Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Merge Agent**.</span></span> <span data-ttu-id="d2fff-106">Подробные сведения об этом сеансе отображаются в сетке с названием **Статьи, обработанные в выбранном сеансе**.</span><span class="sxs-lookup"><span data-stu-id="d2fff-106">Detailed information on this session is displayed in the grid labeled **Articles processed in the selected session**.</span></span>  
  
 <span data-ttu-id="d2fff-107">**View** (Вид)</span><span class="sxs-lookup"><span data-stu-id="d2fff-107">**View**</span></span>  
 <span data-ttu-id="d2fff-108">Выберите сеансы агента слияния для просмотра.</span><span class="sxs-lookup"><span data-stu-id="d2fff-108">Select which Merge Agent sessions to view.</span></span>  
  
 <span data-ttu-id="d2fff-109">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="d2fff-109">**Status**</span></span>  
 <span data-ttu-id="d2fff-110">Состояние агента слияния в конце сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2fff-110">The status of the Merge Agent at the end of the session.</span></span> <span data-ttu-id="d2fff-111">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="d2fff-111">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="d2fff-112">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d2fff-112">Error</span></span>  
  
-   <span data-ttu-id="d2fff-113">Завершено</span><span class="sxs-lookup"><span data-stu-id="d2fff-113">Completed</span></span>  
  
-   <span data-ttu-id="d2fff-114">Повтор</span><span class="sxs-lookup"><span data-stu-id="d2fff-114">Retrying</span></span>  
  
-   <span data-ttu-id="d2fff-115">Запущен</span><span class="sxs-lookup"><span data-stu-id="d2fff-115">Running</span></span>  
  
 <span data-ttu-id="d2fff-116">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="d2fff-116">**Start Time**</span></span>  
 <span data-ttu-id="d2fff-117">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2fff-117">The start time of the session.</span></span>  
  
 <span data-ttu-id="d2fff-118">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="d2fff-118">**End Time**</span></span>  
 <span data-ttu-id="d2fff-119">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2fff-119">The end time of the session.</span></span> <span data-ttu-id="d2fff-120">Если агент не остановлен, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="d2fff-120">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="d2fff-121">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="d2fff-121">**Duration**</span></span>  
 <span data-ttu-id="d2fff-122">Время работы агента слияния в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d2fff-122">The amount of time the Merge Agent has run in a session.</span></span> <span data-ttu-id="d2fff-123">Этот параметр представляет собой время, прошедшее с момента начала сеанса, если агент запущен в данный момент, или общее время, если агент был запущен ранее.</span><span class="sxs-lookup"><span data-stu-id="d2fff-123">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="d2fff-124">**Переданные команды**</span><span class="sxs-lookup"><span data-stu-id="d2fff-124">**Uploaded Commands**</span></span>  
 <span data-ttu-id="d2fff-125">Число строк, переданных в течение сеанса агента слияния.</span><span class="sxs-lookup"><span data-stu-id="d2fff-125">The number of rows uploaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="d2fff-126">**Загруженные команды**</span><span class="sxs-lookup"><span data-stu-id="d2fff-126">**Downloaded Commands**</span></span>  
 <span data-ttu-id="d2fff-127">Число строк, загруженных в течение сеанса агента слияния.</span><span class="sxs-lookup"><span data-stu-id="d2fff-127">The number of rows downloaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="d2fff-128">**Сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="d2fff-128">**Error Message**</span></span>  
 <span data-ttu-id="d2fff-129">Если сеанс завершился с ошибкой, в этом поле отображается последнее сообщение об ошибке, зарегистрированное агентом слияния.</span><span class="sxs-lookup"><span data-stu-id="d2fff-129">If a session ended in an error, this field displays the last error message logged by the Merge Agent.</span></span> <span data-ttu-id="d2fff-130">Если сеанс завершился без ошибки, это поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="d2fff-130">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="d2fff-131">**Статья**</span><span class="sxs-lookup"><span data-stu-id="d2fff-131">**Article**</span></span>  
 <span data-ttu-id="d2fff-132">Имя каждой из статей публикации, а также следующие фазы обработки всей публикации:</span><span class="sxs-lookup"><span data-stu-id="d2fff-132">The name of each article in the publication, and the following processing phases for the entire publication:</span></span>  
  
-   <span data-ttu-id="d2fff-133">**Инициализация**.</span><span class="sxs-lookup"><span data-stu-id="d2fff-133">**Initialization**.</span></span> <span data-ttu-id="d2fff-134">Имеется в виду запуск агента слияния; не путать с инициализацией подписки, при которой применяется моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="d2fff-134">This refers to starting the Merge Agent; this is not synonymous with initializing a subscription, which involves applying a snapshot.</span></span>  
  
-   <span data-ttu-id="d2fff-135">**Изменения схемы и массовые вставки**.</span><span class="sxs-lookup"><span data-stu-id="d2fff-135">**Schema changes and bulk inserts**.</span></span>  
  
-   <span data-ttu-id="d2fff-136">**Загрузить изменения на издатель**.</span><span class="sxs-lookup"><span data-stu-id="d2fff-136">**Upload changes to Publisher**.</span></span>  
  
-   <span data-ttu-id="d2fff-137">**Загрузить изменения на подписчик**.</span><span class="sxs-lookup"><span data-stu-id="d2fff-137">**Download changes to Subscriber**.</span></span>  
  
 <span data-ttu-id="d2fff-138">Фазы включаются таким образом, чтобы в сетке отображалось время каждой фазы и ее процент в общем времени выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2fff-138">The phases are included so that the grid can display the amount of time and percentage of total time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="d2fff-139">**% от общего числа**</span><span class="sxs-lookup"><span data-stu-id="d2fff-139">**% of total**</span></span>  
 <span data-ttu-id="d2fff-140">Процентная доля от общего времени обработки, занимаемая каждой из фаз выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2fff-140">The percentage of total processing time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="d2fff-141">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="d2fff-141">**Duration**</span></span>  
 <span data-ttu-id="d2fff-142">Время, затраченное на каждую фазу обработки.</span><span class="sxs-lookup"><span data-stu-id="d2fff-142">The amount of time spent in each processing phase.</span></span> <span data-ttu-id="d2fff-143">Здесь отображается время, прошедшее с начала сеанса, если агент слияния запущен в данный момент, или общее время, если агент слияния был запущен ранее.</span><span class="sxs-lookup"><span data-stu-id="d2fff-143">The time represents elapsed time if the Merge Agent is currently running for the session and total time if the Merge Agent has run previously.</span></span>  
  
 <span data-ttu-id="d2fff-144">**Вставки**</span><span class="sxs-lookup"><span data-stu-id="d2fff-144">**Inserts**</span></span>  
 <span data-ttu-id="d2fff-145">Число строк, вставленных в этой фазе выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2fff-145">The number of rows inserted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="d2fff-146">**Обновления**</span><span class="sxs-lookup"><span data-stu-id="d2fff-146">**Updates**</span></span>  
 <span data-ttu-id="d2fff-147">Число строк, обновленных в этой фазе выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2fff-147">The number of rows updated in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="d2fff-148">**Deletes**</span><span class="sxs-lookup"><span data-stu-id="d2fff-148">**Deletes**</span></span>  
 <span data-ttu-id="d2fff-149">Число строк, удаленных в этой фазе выбранного сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2fff-149">The number of rows deleted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="d2fff-150">**Конфликты**</span><span class="sxs-lookup"><span data-stu-id="d2fff-150">**Conflicts**</span></span>  
 <span data-ttu-id="d2fff-151">Число конфликтов в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d2fff-151">The number of conflicts in the selected session.</span></span>  
  
 <span data-ttu-id="d2fff-152">**Изменения схемы**</span><span class="sxs-lookup"><span data-stu-id="d2fff-152">**Schema Changes**</span></span>  
 <span data-ttu-id="d2fff-153">Число изменений схемы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d2fff-153">The number of schema changes in the selected session.</span></span> <span data-ttu-id="d2fff-154">Изменения схемы могут быть результатом изменений схемы, реплицированных из базы данных публикации, добавления или удаления статей, изменения свойств статьи или публикации.</span><span class="sxs-lookup"><span data-stu-id="d2fff-154">Schema changes can result from: schema changes being replicated from the publication database; adding or dropping articles; and changes to article or publication properties.</span></span>  
  
 <span data-ttu-id="d2fff-155">**Последнее сообщение выбранного сеанса**</span><span class="sxs-lookup"><span data-stu-id="d2fff-155">**Last message of the selected session**</span></span>  
 <span data-ttu-id="d2fff-156">В этом текстовом поле отображается последнее в выбранном сеансе сообщение.</span><span class="sxs-lookup"><span data-stu-id="d2fff-156">This text area displays the last message in the selected session.</span></span> <span data-ttu-id="d2fff-157">Если произошла ошибка, здесь отображаются детальные сведения о ней и команда, во время попытки выполнения которой ошибка возникла.</span><span class="sxs-lookup"><span data-stu-id="d2fff-157">If an error has occurred, it displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="d2fff-158">Также содержит ссылки на дополнительные данные, имеющие отношение к ошибке.</span><span class="sxs-lookup"><span data-stu-id="d2fff-158">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2fff-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="d2fff-159">See Also</span></span>  
 <span data-ttu-id="d2fff-160">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d2fff-160">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="d2fff-161">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d2fff-161">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="d2fff-162">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d2fff-162">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="d2fff-163">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="d2fff-163">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
