---
title: Сведения о публикации, вкладка "Все подписки" (публикация транзакций) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.tran.f1
ms.assetid: 7073350c-f667-4f70-88e9-152c9a1b08dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccc34bbe0933f4558478bd1d8276898219016e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656340"
---
# <a name="publication-information-all-subscriptions-transactional-publication"></a><span data-ttu-id="a77e3-102">Сведения о публикации, вкладка «Все подписки» (публикация транзакций)</span><span class="sxs-lookup"><span data-stu-id="a77e3-102">Publication Information, All Subscriptions (Transactional Publication)</span></span>
  <span data-ttu-id="a77e3-103">Вкладка **Все подписки** отображает сведения обо всех подписках на выбранную публикацию транзакций.</span><span class="sxs-lookup"><span data-stu-id="a77e3-103">The **All Subscriptions** tab displays information on all subscriptions to the selected transactional publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a77e3-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="a77e3-104">Options</span></span>  
 <span data-ttu-id="a77e3-105">Для получения дополнительных сведений о подписке и о связанных с ней задачах щелкните правой кнопкой мыши на строке с этой подпиской, а затем выберите соответствующий параметр в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="a77e3-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="a77e3-106">Чтобы изменить способ отображения данных в сетке, щелкните правой кнопкой мыши сетку, а затем один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="a77e3-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="a77e3-107">**Сортировать**: сортировка по одному или нескольким столбцам в диалоговом окне **Сортировка столбцов** .</span><span class="sxs-lookup"><span data-stu-id="a77e3-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="a77e3-108">**Выберите столбцы для отображения**: выбор столбцов для отображения и порядка их отображения в диалоговом окне **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="a77e3-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="a77e3-109">**Фильтр**: фильтрация строк в сетке на основании значений столбцов в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="a77e3-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="a77e3-110">**Очистить фильтр**: удаление всех параметров фильтра для сетки.</span><span class="sxs-lookup"><span data-stu-id="a77e3-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="a77e3-111">Настройки фильтра уникальны для каждой сетки.</span><span class="sxs-lookup"><span data-stu-id="a77e3-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="a77e3-112">Выбор и сортировка столбцов применяются ко всем сеткам одного типа, как, например, сетка публикаций для каждого издателя.</span><span class="sxs-lookup"><span data-stu-id="a77e3-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="a77e3-113">**Показать**</span><span class="sxs-lookup"><span data-stu-id="a77e3-113">**Show**</span></span>  
 <span data-ttu-id="a77e3-114">Только для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a77e3-114">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="a77e3-115">Выберите состояния подписки, которые должны отображаться для выбранного типа подписки.</span><span class="sxs-lookup"><span data-stu-id="a77e3-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="a77e3-116">Например, можно выбрать отображение только тех подписок, которые содержат ошибку.</span><span class="sxs-lookup"><span data-stu-id="a77e3-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="a77e3-117">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="a77e3-117">**Status**</span></span>  
 <span data-ttu-id="a77e3-118">Состояние каждой подписки, определяемое состоянием агента распространителя или агента чтения журнала (отображается состояние с более высоким приоритетом. Состояние также может определяться агентом чтения очереди, если используются обновляемые посредством очередей подписки).</span><span class="sxs-lookup"><span data-stu-id="a77e3-118">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="a77e3-119">По умолчанию, табличная сетка, содержащая данные о подписке, сортируется по столбцу **Состояние** (и затем — по столбцу **Производительность** для подписок в одном состоянии).</span><span class="sxs-lookup"><span data-stu-id="a77e3-119">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="a77e3-120">В следующем списке показаны возможные значения состояния и порядок сортировки значений (например, ошибки всегда показываются в верхней части сетки).</span><span class="sxs-lookup"><span data-stu-id="a77e3-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="a77e3-121">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a77e3-121">Error</span></span>  
  
-   <span data-ttu-id="a77e3-122">Критическая производительность (только для версии[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий)</span><span class="sxs-lookup"><span data-stu-id="a77e3-122">Performance critical ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="a77e3-123">Срок действия скоро истекает или истек (только для версии[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий)</span><span class="sxs-lookup"><span data-stu-id="a77e3-123">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="a77e3-124">Неинициализированная подписка ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a77e3-124">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="a77e3-125">Повтор последней невыполненной команды</span><span class="sxs-lookup"><span data-stu-id="a77e3-125">Retrying failed command</span></span>  
  
-   <span data-ttu-id="a77e3-126">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="a77e3-126">Not Running</span></span>  
  
-   <span data-ttu-id="a77e3-127">Запущен</span><span class="sxs-lookup"><span data-stu-id="a77e3-127">Running</span></span>  
  
 <span data-ttu-id="a77e3-128">Порядок сортировки также определяет отображаемое значение, если данная подписка имеет более одного состояния.</span><span class="sxs-lookup"><span data-stu-id="a77e3-128">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="a77e3-129">Например, если подписка содержит ошибку и срок ее действия скоро истекает, в столбце **Состояние** отображается **Ошибка**.</span><span class="sxs-lookup"><span data-stu-id="a77e3-129">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="a77e3-130">Значения состояния **Критическое для производительности**, **Срок действия скоро истекает или истек**и **Неинициализированная подписка** являются предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="a77e3-130">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="a77e3-131">Когда выводится предупреждение, столбец **Состояние** также отображается при запущенном агенте.</span><span class="sxs-lookup"><span data-stu-id="a77e3-131">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="a77e3-132">Например, состояние может отображаться как **Запущен, Критическое для производительности**.</span><span class="sxs-lookup"><span data-stu-id="a77e3-132">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="a77e3-133">Значения состояния **Критическое для производительности** и **Срок действия скоро истекает или истек** отображаются только в случае, если заданы пороговые значения.</span><span class="sxs-lookup"><span data-stu-id="a77e3-133">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="a77e3-134">Сведения по измерению производительности и установке пороговых значений см. в статьях [Наблюдение за производительностью с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md) и [Настройка пороговых значений и предупреждений в мониторе репликации](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a77e3-134">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="a77e3-135">**Подписка**</span><span class="sxs-lookup"><span data-stu-id="a77e3-135">**Subscription**</span></span>  
 <span data-ttu-id="a77e3-136">Имя каждой подписки в виде: *имя_подписчика: имя_базы_данных_подписки*.</span><span class="sxs-lookup"><span data-stu-id="a77e3-136">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="a77e3-137">**Производительность**</span><span class="sxs-lookup"><span data-stu-id="a77e3-137">**Performance**</span></span>  
 <span data-ttu-id="a77e3-138">Только для версии[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a77e3-138">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="a77e3-139">Оценка производительности для каждой подписки основывается на самых последних измерениях, взятых монитором репликации, и не отражает историю изменений производительности по журналу.</span><span class="sxs-lookup"><span data-stu-id="a77e3-139">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="a77e3-140">Производительность измеряется только для тех подписок на публикации, для которых указаны пороги производительности. Если пороги производительности для публикации не указаны, в столбце отображается **Не включено**.</span><span class="sxs-lookup"><span data-stu-id="a77e3-140">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="a77e3-141">Рейтинг производительности может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="a77e3-141">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="a77e3-142">Отлично</span><span class="sxs-lookup"><span data-stu-id="a77e3-142">Excellent</span></span>  
  
-   <span data-ttu-id="a77e3-143">Хорошо</span><span class="sxs-lookup"><span data-stu-id="a77e3-143">Good</span></span>  
  
-   <span data-ttu-id="a77e3-144">Ниже среднего</span><span class="sxs-lookup"><span data-stu-id="a77e3-144">Fair</span></span>  
  
-   <span data-ttu-id="a77e3-145">Плохо</span><span class="sxs-lookup"><span data-stu-id="a77e3-145">Poor</span></span>  
  
-   <span data-ttu-id="a77e3-146">Критически важно</span><span class="sxs-lookup"><span data-stu-id="a77e3-146">Critical</span></span>  
  
 <span data-ttu-id="a77e3-147">Если производительность критическая, в столбце **Состояние** отображается значение **Критическое для производительности** .</span><span class="sxs-lookup"><span data-stu-id="a77e3-147">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="a77e3-148">Дополнительные сведения об определении оценки производительности и установке пороговых значений см. в статье [Наблюдение за производительностью с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a77e3-148">For more information on how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="a77e3-149">**Задержка**</span><span class="sxs-lookup"><span data-stu-id="a77e3-149">**Latency**</span></span>  
 <span data-ttu-id="a77e3-150">Только для версии[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a77e3-150">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="a77e3-151">Средняя продолжительность промежутка времени между фиксацией транзакции у издателя и фиксацией соответствующей транзакции у подписчика.</span><span class="sxs-lookup"><span data-stu-id="a77e3-151">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="a77e3-152">Отображаемая задержка основывается на самых последних измерениях, взятых монитором репликации.</span><span class="sxs-lookup"><span data-stu-id="a77e3-152">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="a77e3-153">Дополнительные сведения об измерении задержки см. в разделе [Измерение задержки и проверка правильности соединений для репликации транзакций](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a77e3-153">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a77e3-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="a77e3-154">See Also</span></span>  
 <span data-ttu-id="a77e3-155">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="a77e3-155">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="a77e3-156">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="a77e3-156">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="a77e3-157">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="a77e3-157">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
