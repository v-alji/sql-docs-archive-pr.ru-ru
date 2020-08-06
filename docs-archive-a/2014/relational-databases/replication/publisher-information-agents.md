---
title: Данные об издателе, вкладка "Агенты" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.commonjobs.f1
ms.assetid: 2346c00d-c269-45a1-af14-68e7fd7ebd7e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bdd2055ed022257524bc4d2784bdc333537be855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655046"
---
# <a name="publisher-information-agents"></a><span data-ttu-id="e93e3-102">Данные об издателе, агенты</span><span class="sxs-lookup"><span data-stu-id="e93e3-102">Publisher Information, Agents</span></span>
  <span data-ttu-id="e93e3-103">На вкладке **Агенты** отображаются сведения об агентах и заданиях обслуживания, связанных с издателем.</span><span class="sxs-lookup"><span data-stu-id="e93e3-103">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher:</span></span>  
  
-   <span data-ttu-id="e93e3-104">Агент моментальных снимков, который отображается для всех публикаций.</span><span class="sxs-lookup"><span data-stu-id="e93e3-104">Snapshot Agent, which is displayed for all publications.</span></span>  
  
-   <span data-ttu-id="e93e3-105">Агент чтения журнала, который отображается для всех публикаций транзакций</span><span class="sxs-lookup"><span data-stu-id="e93e3-105">Log Reader Agent, which is displayed for all transactional publications.</span></span>  
  
-   <span data-ttu-id="e93e3-106">Агент чтения очереди, который отображается только для тех публикаций транзакций, которые включены для обновляемых посредством очередей подписок.</span><span class="sxs-lookup"><span data-stu-id="e93e3-106">Queue Reader Agent, which is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="e93e3-107">Задания обслуживания, которые отображаются для всех публикаций.</span><span class="sxs-lookup"><span data-stu-id="e93e3-107">Maintenance jobs, displayed for all publications:</span></span>  
  
    -   <span data-ttu-id="e93e3-108">Повторная инициализация подписок, имеющих сбои при выполнении проверки данных</span><span class="sxs-lookup"><span data-stu-id="e93e3-108">Reinitialize subscriptions that have data validation failures</span></span>  
  
    -   <span data-ttu-id="e93e3-109">Агент очистки журнала: распространитель</span><span class="sxs-lookup"><span data-stu-id="e93e3-109">Agent history cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="e93e3-110">Обновитель наблюдения репликации для распространения</span><span class="sxs-lookup"><span data-stu-id="e93e3-110">Replication monitoring refresher for distribution</span></span>  
  
    -   <span data-ttu-id="e93e3-111">Контроль за агентами репликации</span><span class="sxs-lookup"><span data-stu-id="e93e3-111">Replication agents checkup</span></span>  
  
    -   <span data-ttu-id="e93e3-112">Очистка распространителя: распространитель</span><span class="sxs-lookup"><span data-stu-id="e93e3-112">Distribution cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="e93e3-113">Очистка истекших подписок</span><span class="sxs-lookup"><span data-stu-id="e93e3-113">Expired subscription cleanup</span></span>  
  
 <span data-ttu-id="e93e3-114">Дополнительные сведения об этих заданиях см. в статье [Администрирование агента репликации](agents/replication-agent-administration.md).</span><span class="sxs-lookup"><span data-stu-id="e93e3-114">For more information about these jobs, see [Replication Agent Administration](agents/replication-agent-administration.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e93e3-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="e93e3-115">Options</span></span>  
 <span data-ttu-id="e93e3-116">Чтобы вывести сведения об агенте или задании, выберите элемент в раскрывающемся меню **Типы агентов и заданий** .</span><span class="sxs-lookup"><span data-stu-id="e93e3-116">To display information about an agent or job, select from the **Agent and Job Types** drop-down menu.</span></span> <span data-ttu-id="e93e3-117">Чтобы получить дополнительные сведения и задачи, связанные с агентом или заданием, щелкните правой кнопкой мыши строку агента или задания и в контекстном меню выберите нужный пункт.</span><span class="sxs-lookup"><span data-stu-id="e93e3-117">For more detailed information and tasks that are related to an agent or job, right-click the row for that agent or job, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="e93e3-118">Чтобы изменить способ отображения данных в сетке, щелкните правой кнопкой мыши сетку, а затем один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="e93e3-118">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="e93e3-119">**Сортировать**: сортировка по одному или нескольким столбцам в диалоговом окне **Сортировка столбцов** .</span><span class="sxs-lookup"><span data-stu-id="e93e3-119">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="e93e3-120">**Выберите столбцы для отображения**: выбор столбцов для отображения и порядка их отображения в диалоговом окне **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="e93e3-120">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="e93e3-121">**Фильтр**: фильтрация строк в сетке на основании значений столбцов в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="e93e3-121">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="e93e3-122">**Очистить фильтр**: удаление всех параметров фильтра для сетки.</span><span class="sxs-lookup"><span data-stu-id="e93e3-122">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="e93e3-123">Настройки фильтра уникальны для каждой сетки.</span><span class="sxs-lookup"><span data-stu-id="e93e3-123">Filter settings are specific to each grid.</span></span> <span data-ttu-id="e93e3-124">Выбор и сортировка столбцов применяются ко всем сеткам одного типа, как, например, сетка публикаций для каждого издателя.</span><span class="sxs-lookup"><span data-stu-id="e93e3-124">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="e93e3-125">В следующих разделах описываются данные, которые отображаются на этой вкладке для каждого агента и задания.</span><span class="sxs-lookup"><span data-stu-id="e93e3-125">The following sections describe the data that is displayed on this tab for each agent or job.</span></span>  
  
### <a name="snapshot-agent"></a><span data-ttu-id="e93e3-126">агент моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="e93e3-126">Snapshot Agent</span></span>  
 <span data-ttu-id="e93e3-127">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="e93e3-127">**Status**</span></span>  
 <span data-ttu-id="e93e3-128">Состояние агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-128">The status of the agent.</span></span> <span data-ttu-id="e93e3-129">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="e93e3-129">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="e93e3-130">Ошибка</span><span class="sxs-lookup"><span data-stu-id="e93e3-130">Error</span></span>  
  
-   <span data-ttu-id="e93e3-131">Повторить попытку</span><span class="sxs-lookup"><span data-stu-id="e93e3-131">Retry</span></span>  
  
-   <span data-ttu-id="e93e3-132">Запущен</span><span class="sxs-lookup"><span data-stu-id="e93e3-132">Running</span></span>  
  
-   <span data-ttu-id="e93e3-133">Завершено</span><span class="sxs-lookup"><span data-stu-id="e93e3-133">Completed</span></span>  
  
 <span data-ttu-id="e93e3-134">**Публикация**</span><span class="sxs-lookup"><span data-stu-id="e93e3-134">**Publication**</span></span>  
 <span data-ttu-id="e93e3-135">Имя публикации, с которой связан агент.</span><span class="sxs-lookup"><span data-stu-id="e93e3-135">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="e93e3-136">**Время последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="e93e3-136">**Last Start Time**</span></span>  
 <span data-ttu-id="e93e3-137">Время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-137">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="e93e3-138">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="e93e3-138">**Duration**</span></span>  
 <span data-ttu-id="e93e3-139">Продолжительность выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-139">The length of time the agent has run.</span></span> <span data-ttu-id="e93e3-140">Это время представляет собой продолжительность выполнения агента, если он выполняется в настоящее время, и общее время выполнения, если агент запускался ранее.</span><span class="sxs-lookup"><span data-stu-id="e93e3-140">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="e93e3-141">**Последнее действие**</span><span class="sxs-lookup"><span data-stu-id="e93e3-141">**Last Action**</span></span>  
 <span data-ttu-id="e93e3-142">Последнее действие выполнено во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-142">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="e93e3-143">**Скорость доставки**</span><span class="sxs-lookup"><span data-stu-id="e93e3-143">**Delivery Rate**</span></span>  
 <span data-ttu-id="e93e3-144">Скорость (команд в секунду), с которой команды инициализации фиксируются в базе данных распространителя во время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-144">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="e93e3-145">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="e93e3-145">**#Trans**</span></span>  
 <span data-ttu-id="e93e3-146">Количество транзакций, зафиксированных в базе данных распространителя во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-146">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="e93e3-147">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="e93e3-147">**#Cmds**</span></span>  
 <span data-ttu-id="e93e3-148">Количество команд, зафиксированных в базе данных распространителя во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-148">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="e93e3-149">Команда является эквивалентом изменения данных, например обновления.</span><span class="sxs-lookup"><span data-stu-id="e93e3-149">A command is equivalent to a data change, such as an update.</span></span>  
  
### <a name="log-reader-agent"></a><span data-ttu-id="e93e3-150">Агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="e93e3-150">Log Reader Agent</span></span>  
 <span data-ttu-id="e93e3-151">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="e93e3-151">**Status**</span></span>  
 <span data-ttu-id="e93e3-152">Состояние агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-152">The status of the agent.</span></span> <span data-ttu-id="e93e3-153">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="e93e3-153">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="e93e3-154">Ошибка</span><span class="sxs-lookup"><span data-stu-id="e93e3-154">Error</span></span>  
  
-   <span data-ttu-id="e93e3-155">Повторить попытку</span><span class="sxs-lookup"><span data-stu-id="e93e3-155">Retry</span></span>  
  
-   <span data-ttu-id="e93e3-156">Запущен</span><span class="sxs-lookup"><span data-stu-id="e93e3-156">Running</span></span>  
  
-   <span data-ttu-id="e93e3-157">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="e93e3-157">Not running</span></span>  
  
 <span data-ttu-id="e93e3-158">**База данных публикации**</span><span class="sxs-lookup"><span data-stu-id="e93e3-158">**Publication Database**</span></span>  
 <span data-ttu-id="e93e3-159">Имя публикации, с которой связан агент.</span><span class="sxs-lookup"><span data-stu-id="e93e3-159">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="e93e3-160">**Время последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="e93e3-160">**Last Start Time**</span></span>  
 <span data-ttu-id="e93e3-161">Время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-161">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="e93e3-162">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="e93e3-162">**Duration**</span></span>  
 <span data-ttu-id="e93e3-163">Продолжительность выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-163">The length of time the agent has run.</span></span> <span data-ttu-id="e93e3-164">Это время представляет собой продолжительность выполнения агента, если он выполняется в настоящее время, и общее время выполнения, если агент запускался ранее.</span><span class="sxs-lookup"><span data-stu-id="e93e3-164">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="e93e3-165">**Последнее действие**</span><span class="sxs-lookup"><span data-stu-id="e93e3-165">**Last Action**</span></span>  
 <span data-ttu-id="e93e3-166">Последнее действие выполнено во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-166">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="e93e3-167">**Скорость доставки**</span><span class="sxs-lookup"><span data-stu-id="e93e3-167">**Delivery Rate**</span></span>  
 <span data-ttu-id="e93e3-168">Показатель (команд в секунду), с которым изменения фиксируются в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="e93e3-168">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="e93e3-169">**Задержка**</span><span class="sxs-lookup"><span data-stu-id="e93e3-169">**Latency**</span></span>  
 <span data-ttu-id="e93e3-170">Время в секундах, прошедшее с момента фиксации последних изменений в базе данных публикации, до фиксации соответствующих команд в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="e93e3-170">The amount of time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="e93e3-171">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="e93e3-171">**#Trans**</span></span>  
 <span data-ttu-id="e93e3-172">Количество транзакций, зафиксированных в базе данных распространителя во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-172">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="e93e3-173">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="e93e3-173">**#Cmds**</span></span>  
 <span data-ttu-id="e93e3-174">Количество команд, зафиксированных в базе данных распространителя во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-174">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="e93e3-175">Команда является эквивалентом изменения данных, например обновления.</span><span class="sxs-lookup"><span data-stu-id="e93e3-175">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="e93e3-176">**Ср. кол-во команд**</span><span class="sxs-lookup"><span data-stu-id="e93e3-176">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="e93e3-177">Среднее количество команд за транзакцию во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-177">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="queue-reader-agent"></a><span data-ttu-id="e93e3-178">Агент чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="e93e3-178">Queue Reader Agent</span></span>  
 <span data-ttu-id="e93e3-179">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="e93e3-179">**Status**</span></span>  
 <span data-ttu-id="e93e3-180">Состояние агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-180">The status of the agent.</span></span> <span data-ttu-id="e93e3-181">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="e93e3-181">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="e93e3-182">Ошибка</span><span class="sxs-lookup"><span data-stu-id="e93e3-182">Error</span></span>  
  
-   <span data-ttu-id="e93e3-183">Повторить попытку</span><span class="sxs-lookup"><span data-stu-id="e93e3-183">Retry</span></span>  
  
-   <span data-ttu-id="e93e3-184">Запущен</span><span class="sxs-lookup"><span data-stu-id="e93e3-184">Running</span></span>  
  
-   <span data-ttu-id="e93e3-185">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="e93e3-185">Not running</span></span>  
  
 <span data-ttu-id="e93e3-186">**База данных распространителя**</span><span class="sxs-lookup"><span data-stu-id="e93e3-186">**Distribution Database**</span></span>  
 <span data-ttu-id="e93e3-187">Имя базы данных распространителя, с которой связан агент.</span><span class="sxs-lookup"><span data-stu-id="e93e3-187">The name of the distribution database with which the agent is associated.</span></span>  
  
 <span data-ttu-id="e93e3-188">**Время последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="e93e3-188">**Last Start Time**</span></span>  
 <span data-ttu-id="e93e3-189">Время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-189">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="e93e3-190">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="e93e3-190">**Duration**</span></span>  
 <span data-ttu-id="e93e3-191">Продолжительность выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-191">The length of time the agent has run.</span></span> <span data-ttu-id="e93e3-192">Этот параметр представляет собой время, прошедшее с момента начала сеанса, если агент запущен в данный момент, или общее время, если агент был запущен ранее.</span><span class="sxs-lookup"><span data-stu-id="e93e3-192">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="e93e3-193">**Последнее действие**</span><span class="sxs-lookup"><span data-stu-id="e93e3-193">**Last Action**</span></span>  
 <span data-ttu-id="e93e3-194">Последнее действие выполнено во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-194">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="e93e3-195">**Скорость доставки**</span><span class="sxs-lookup"><span data-stu-id="e93e3-195">**Delivery Rate**</span></span>  
 <span data-ttu-id="e93e3-196">Показатель (команд в секунду), с которым изменения фиксируются в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="e93e3-196">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="e93e3-197">**Задержка**</span><span class="sxs-lookup"><span data-stu-id="e93e3-197">**Latency**</span></span>  
 <span data-ttu-id="e93e3-198">Время в секундах, прошедшее с момента фиксации последних изменений в базе данных подписки, до фиксации соответствующих команд в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="e93e3-198">The amount of time, in seconds, that has elapsed between the most recent change being committed in a subscription database, and the corresponding command being committed in the publication database.</span></span>  
  
 <span data-ttu-id="e93e3-199">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="e93e3-199">**#Trans**</span></span>  
 <span data-ttu-id="e93e3-200">Количество транзакций, зафиксированных в базе данных публикации во время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-200">The number of transactions committed in the publication database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="e93e3-201">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="e93e3-201">**#Cmds**</span></span>  
 <span data-ttu-id="e93e3-202">Количество команд, зафиксированных в базе данных публикации во время последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-202">The number of commands committed in the publication database during the most recent run of the agent.</span></span> <span data-ttu-id="e93e3-203">Команда является эквивалентом изменения данных, например обновления.</span><span class="sxs-lookup"><span data-stu-id="e93e3-203">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="e93e3-204">**Ср. кол-во команд**</span><span class="sxs-lookup"><span data-stu-id="e93e3-204">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="e93e3-205">Среднее количество команд за транзакцию во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="e93e3-205">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="maintenance-jobs"></a><span data-ttu-id="e93e3-206">Задания обслуживания</span><span class="sxs-lookup"><span data-stu-id="e93e3-206">Maintenance Jobs</span></span>  
 <span data-ttu-id="e93e3-207">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="e93e3-207">**Status**</span></span>  
 <span data-ttu-id="e93e3-208">Отображает состояние каждого задания.</span><span class="sxs-lookup"><span data-stu-id="e93e3-208">The status of each job.</span></span> <span data-ttu-id="e93e3-209">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="e93e3-209">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="e93e3-210">Ошибка</span><span class="sxs-lookup"><span data-stu-id="e93e3-210">Error</span></span>  
  
-   <span data-ttu-id="e93e3-211">Повторить попытку</span><span class="sxs-lookup"><span data-stu-id="e93e3-211">Retry</span></span>  
  
-   <span data-ttu-id="e93e3-212">Запущен</span><span class="sxs-lookup"><span data-stu-id="e93e3-212">Running</span></span>  
  
-   <span data-ttu-id="e93e3-213">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="e93e3-213">Not running</span></span>  
  
 <span data-ttu-id="e93e3-214">**Задание**</span><span class="sxs-lookup"><span data-stu-id="e93e3-214">**Job**</span></span>  
 <span data-ttu-id="e93e3-215">Имя задания.</span><span class="sxs-lookup"><span data-stu-id="e93e3-215">The name of the job.</span></span>  
  
 <span data-ttu-id="e93e3-216">**Время последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="e93e3-216">**Last Start Time**</span></span>  
 <span data-ttu-id="e93e3-217">Время последнего запуска задания.</span><span class="sxs-lookup"><span data-stu-id="e93e3-217">The last time at which the job started.</span></span>  
  
 <span data-ttu-id="e93e3-218">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="e93e3-218">**Duration**</span></span>  
 <span data-ttu-id="e93e3-219">Продолжительность выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="e93e3-219">The length of time the job has run.</span></span> <span data-ttu-id="e93e3-220">Если задание выполняется, отображается текущее время выполнения, в противном случае отображается общее время выполнения последнего задания.</span><span class="sxs-lookup"><span data-stu-id="e93e3-220">The time represents elapsed time if the job is currently running, and total time if the job has run previously.</span></span>  
  
 <span data-ttu-id="e93e3-221">**Последнее действие**</span><span class="sxs-lookup"><span data-stu-id="e93e3-221">**Last Action**</span></span>  
 <span data-ttu-id="e93e3-222">Последнее действие выполнено во время самого последнего выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="e93e3-222">The last action performed during the most recent run of the job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93e3-223">См. также:</span><span class="sxs-lookup"><span data-stu-id="e93e3-223">See Also</span></span>  
 <span data-ttu-id="e93e3-224">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="e93e3-224">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="e93e3-225">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="e93e3-225">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="e93e3-226">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="e93e3-226">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
