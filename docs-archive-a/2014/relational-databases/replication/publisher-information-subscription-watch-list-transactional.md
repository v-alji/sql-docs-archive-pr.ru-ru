---
title: Сведения об издателе, список наблюдения за подписками (публикация транзакций, SQL Server 2005 и более поздние версии) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.tran.f1
ms.assetid: 6bc64ddb-5c86-4681-a391-77fc1d3c4e6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bf6d151b75bca1dbfd2e5ad8f7601fb1002e84be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654154"
---
# <a name="publisher-information-subscription-watch-list-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="67b07-102">Сведения об издателе, список наблюдения за подписками (публикация транзакций, SQL Server 2005 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="67b07-102">Publisher Information, Subscription Watch List (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="67b07-103">Вкладка **Список наблюдения за подписками** доступна для распространителей под управлением SQL Server 2005 и более поздних версий. Она предназначается для отображения сведений о подписках на все публикации, доступные на выбранном издателе.</span><span class="sxs-lookup"><span data-stu-id="67b07-103">The **Subscription Watch List** tab is available for Distributors running SQL Server 2005 and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="67b07-104">Список подписок можно фильтровать для просмотра ошибок, предупреждений и подписок с низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="67b07-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="67b07-105">Эта вкладка предоставляет администратору единое расположение для контроля за активностью всех репликаций на издателе. Монитор репликации отображает все подписки, требующие внимания администратора, на основе выбранного типа репликации и в соответствии с параметром, выбранным в раскрывающемся списке **Показать** .</span><span class="sxs-lookup"><span data-stu-id="67b07-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="67b07-106">Элементы отображаются на этой вкладке в соответствии с текущим состоянием и производительностью, поэтому подписки отображаются на этой странице только в случае, если они в настоящее время соответствуют параметру в списке **Показать** .</span><span class="sxs-lookup"><span data-stu-id="67b07-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="67b07-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="67b07-107">Options</span></span>  
 <span data-ttu-id="67b07-108">Для получения дополнительных сведений о подписке и о связанных с ней задачах щелкните правой кнопкой мыши на строке с этой подпиской, а затем выберите соответствующий параметр в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="67b07-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="67b07-109">Чтобы изменить способ отображения данных в сетке, щелкните правой кнопкой мыши сетку, а затем один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="67b07-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="67b07-110">**Сортировать**: сортировка по одному или нескольким столбцам в диалоговом окне **Сортировка столбцов** .</span><span class="sxs-lookup"><span data-stu-id="67b07-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="67b07-111">**Выберите столбцы для отображения**: выбор столбцов для отображения и порядка их отображения в диалоговом окне **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="67b07-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="67b07-112">**Фильтр**: фильтрация строк в сетке на основании значений столбцов в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="67b07-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="67b07-113">**Очистить фильтр**: удаление всех параметров фильтра для сетки.</span><span class="sxs-lookup"><span data-stu-id="67b07-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="67b07-114">Настройки фильтра уникальны для каждой сетки.</span><span class="sxs-lookup"><span data-stu-id="67b07-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="67b07-115">Выбор и сортировка столбцов применяются ко всем сеткам одного типа, как, например, сетка публикаций для каждого издателя.</span><span class="sxs-lookup"><span data-stu-id="67b07-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="67b07-116">**Показать подписки на публикацию транзакций**</span><span class="sxs-lookup"><span data-stu-id="67b07-116">**Show Transactional Subscriptions**</span></span>  
 <span data-ttu-id="67b07-117">Выберите типы подписок (на публикацию транзакций, на моментальные снимки или слиянием), которые будут выводиться для выбранного издателя.</span><span class="sxs-lookup"><span data-stu-id="67b07-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="67b07-118">**Показать**</span><span class="sxs-lookup"><span data-stu-id="67b07-118">**Show**</span></span>  
 <span data-ttu-id="67b07-119">Выберите состояния подписки, которые должны отображаться для выбранного типа подписки.</span><span class="sxs-lookup"><span data-stu-id="67b07-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="67b07-120">Например, можно выбрать отображение только тех подписок, которые содержат ошибку.</span><span class="sxs-lookup"><span data-stu-id="67b07-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="67b07-121">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="67b07-121">**Status**</span></span>  
 <span data-ttu-id="67b07-122">Состояние каждой подписки, определяемое состоянием агента распространителя или агента чтения журнала (отображается состояние с более высоким приоритетом. Состояние также может определяться агентом чтения очереди, если используются обновляемые посредством очередей подписки).</span><span class="sxs-lookup"><span data-stu-id="67b07-122">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="67b07-123">По умолчанию, табличная сетка, содержащая данные о подписке, сортируется по столбцу **Состояние** (и затем — по столбцу **Производительность** для подписок в одном состоянии).</span><span class="sxs-lookup"><span data-stu-id="67b07-123">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="67b07-124">В следующем списке показаны возможные значения состояния и порядок сортировки значений (например, ошибки всегда показываются в верхней части сетки).</span><span class="sxs-lookup"><span data-stu-id="67b07-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="67b07-125">Ошибка</span><span class="sxs-lookup"><span data-stu-id="67b07-125">Error</span></span>  
  
-   <span data-ttu-id="67b07-126">Критическая производительность</span><span class="sxs-lookup"><span data-stu-id="67b07-126">Performance critical</span></span>  
  
-   <span data-ttu-id="67b07-127">Срок действия скоро истекает или истек</span><span class="sxs-lookup"><span data-stu-id="67b07-127">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="67b07-128">Неинициализированная подписка</span><span class="sxs-lookup"><span data-stu-id="67b07-128">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="67b07-129">Повтор последней невыполненной команды</span><span class="sxs-lookup"><span data-stu-id="67b07-129">Retrying failed command</span></span>  
  
-   <span data-ttu-id="67b07-130">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="67b07-130">Not Running</span></span>  
  
-   <span data-ttu-id="67b07-131">Запущен</span><span class="sxs-lookup"><span data-stu-id="67b07-131">Running</span></span>  
  
 <span data-ttu-id="67b07-132">Порядок сортировки также определяет отображаемое значение, если данная подписка имеет более одного состояния.</span><span class="sxs-lookup"><span data-stu-id="67b07-132">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="67b07-133">Например, если подписка содержит ошибку и срок ее действия скоро истекает, в столбце **Состояние** отображается **Ошибка**.</span><span class="sxs-lookup"><span data-stu-id="67b07-133">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="67b07-134">Значения состояния **Критическое для производительности**, **Срок действия скоро истекает или истек**и **Неинициализированная подписка** являются предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="67b07-134">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="67b07-135">Когда выводится предупреждение, столбец **Состояние** также отображается при запущенном агенте.</span><span class="sxs-lookup"><span data-stu-id="67b07-135">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="67b07-136">Например, состояние может отображаться как **Запущен, Критическое для производительности**.</span><span class="sxs-lookup"><span data-stu-id="67b07-136">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="67b07-137">Значения состояния **Критическое для производительности** и **Срок действия скоро истекает или истек** отображаются только в случае, если заданы пороговые значения.</span><span class="sxs-lookup"><span data-stu-id="67b07-137">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="67b07-138">Сведения по измерению производительности и установке пороговых значений см. в статьях [Наблюдение за производительностью с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md) и [Настройка пороговых значений и предупреждений в мониторе репликации](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="67b07-138">For information about performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="67b07-139">**подписка**</span><span class="sxs-lookup"><span data-stu-id="67b07-139">**Subscription**</span></span>  
 <span data-ttu-id="67b07-140">Имя каждой подписки в виде: *имя_подписчика: имя_базы_данных_подписки*.</span><span class="sxs-lookup"><span data-stu-id="67b07-140">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="67b07-141">**Публикация**</span><span class="sxs-lookup"><span data-stu-id="67b07-141">**Publication**</span></span>  
 <span data-ttu-id="67b07-142">Имя публикации, с которой синхронизируется подписка, в следующем виде: *имя_базы_данных_публикации: имя_публикации*.</span><span class="sxs-lookup"><span data-stu-id="67b07-142">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="67b07-143">**Производительность**</span><span class="sxs-lookup"><span data-stu-id="67b07-143">**Performance**</span></span>  
 <span data-ttu-id="67b07-144">Оценка производительности для каждой подписки основывается на самых последних измерениях, взятых монитором репликации, и не отражает историю изменений производительности по журналу.</span><span class="sxs-lookup"><span data-stu-id="67b07-144">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="67b07-145">Производительность измеряется только для тех подписок на публикации, для которых указаны пороги производительности. Если пороги производительности для публикации не указаны, в столбце отображается **Не включено**.</span><span class="sxs-lookup"><span data-stu-id="67b07-145">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="67b07-146">Рейтинг производительности может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="67b07-146">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="67b07-147">Высокая</span><span class="sxs-lookup"><span data-stu-id="67b07-147">Excellent</span></span>  
  
-   <span data-ttu-id="67b07-148">Хорошая.</span><span class="sxs-lookup"><span data-stu-id="67b07-148">Good</span></span>  
  
-   <span data-ttu-id="67b07-149">удовлетворительная</span><span class="sxs-lookup"><span data-stu-id="67b07-149">Fair</span></span>  
  
-   <span data-ttu-id="67b07-150">Низкая</span><span class="sxs-lookup"><span data-stu-id="67b07-150">Poor</span></span>  
  
-   <span data-ttu-id="67b07-151">Critical</span><span class="sxs-lookup"><span data-stu-id="67b07-151">Critical</span></span>  
  
 <span data-ttu-id="67b07-152">Если производительность критическая, в столбце **Состояние** отображается значение **Критическое для производительности** .</span><span class="sxs-lookup"><span data-stu-id="67b07-152">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="67b07-153">Дополнительные сведения об определении оценки производительности и установке пороговых значений см. в статье [Наблюдение за производительностью с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="67b07-153">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="67b07-154">**Задержка**</span><span class="sxs-lookup"><span data-stu-id="67b07-154">**Latency**</span></span>  
 <span data-ttu-id="67b07-155">Средняя продолжительность промежутка времени между фиксацией транзакции у издателя и фиксацией соответствующей транзакции у подписчика.</span><span class="sxs-lookup"><span data-stu-id="67b07-155">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="67b07-156">Отображаемая задержка основывается на самых последних измерениях, взятых монитором репликации.</span><span class="sxs-lookup"><span data-stu-id="67b07-156">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="67b07-157">Дополнительные сведения об измерении задержки см. в разделе [Измерение задержки и проверка правильности соединений для репликации транзакций](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="67b07-157">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="67b07-158">**Последняя синхронизация**</span><span class="sxs-lookup"><span data-stu-id="67b07-158">**Last Synchronization**</span></span>  
 <span data-ttu-id="67b07-159">Время последнего запуска агента распространителя.</span><span class="sxs-lookup"><span data-stu-id="67b07-159">The time when the Distribution Agent last ran.</span></span> <span data-ttu-id="67b07-160">Если в данный момент синхронизация выполняется, то выводится сообщение **Выполняется** .</span><span class="sxs-lookup"><span data-stu-id="67b07-160">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b07-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="67b07-161">See Also</span></span>  
 <span data-ttu-id="67b07-162">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="67b07-162">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="67b07-163">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="67b07-163">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="67b07-164">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="67b07-164">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
