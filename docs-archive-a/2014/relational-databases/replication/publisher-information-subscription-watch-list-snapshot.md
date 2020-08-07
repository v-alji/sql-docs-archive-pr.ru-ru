---
title: Сведения об издателе, список наблюдения за подписками (публикация моментальных снимков, SQL Server 2005 и более поздних версий) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.snapshot.f1
ms.assetid: 2ebeee62-7f54-4c77-9d37-15708bc5cc23
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ea44958c81465570c036ab7dd83247fb55652f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732574"
---
# <a name="publisher-information-subscription-watch-list-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="f417b-102">Сведения об издателе, список наблюдения за подписками (публикация моментальных снимков, SQL Server 2005 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="f417b-102">Publisher Information, Subscription Watch List (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="f417b-103"> Вкладка **Список наблюдения за подписками** доступна для распространителей под управлением [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий. Она предназначена для отображения сведений о подписках на все публикации, доступные в выбранном издателе.</span><span class="sxs-lookup"><span data-stu-id="f417b-103">The **Subscription Watch List** tab is available for Distributors running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="f417b-104">Список подписок можно фильтровать для просмотра ошибок, предупреждений и подписок с низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="f417b-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="f417b-105">Эта вкладка предоставляет администратору единое расположение для контроля за активностью всех репликаций на издателе. Монитор репликации отображает все подписки, требующие внимания администратора, на основе выбранного типа репликации и в соответствии с параметром, выбранным в раскрывающемся списке **Показать** .</span><span class="sxs-lookup"><span data-stu-id="f417b-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="f417b-106">Элементы отображаются на этой вкладке в соответствии с текущим состоянием и производительностью, поэтому подписки отображаются на этой странице только в случае, если они в настоящее время соответствуют параметру в списке **Показать** .</span><span class="sxs-lookup"><span data-stu-id="f417b-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f417b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f417b-107">Options</span></span>  
 <span data-ttu-id="f417b-108">Для получения дополнительных сведений о подписке и о связанных с ней задачах щелкните правой кнопкой мыши на строке с этой подпиской, а затем выберите соответствующий параметр в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="f417b-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="f417b-109">Чтобы изменить способ отображения данных в сетке, щелкните правой кнопкой мыши сетку, а затем один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="f417b-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="f417b-110">**Сортировать**: сортировка по одному или нескольким столбцам в диалоговом окне **Сортировка столбцов** .</span><span class="sxs-lookup"><span data-stu-id="f417b-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f417b-111">**Выберите столбцы для отображения**: выбор столбцов для отображения и порядка их отображения в диалоговом окне **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="f417b-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f417b-112">**Фильтр**: фильтрация строк в сетке на основании значений столбцов в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="f417b-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="f417b-113">**Очистить фильтр**: удаление всех параметров фильтра для сетки.</span><span class="sxs-lookup"><span data-stu-id="f417b-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="f417b-114">Настройки фильтра уникальны для каждой сетки.</span><span class="sxs-lookup"><span data-stu-id="f417b-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="f417b-115">Выбор и сортировка столбцов применяются ко всем сеткам одного типа, как, например, сетка публикаций для каждого издателя.</span><span class="sxs-lookup"><span data-stu-id="f417b-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="f417b-116">**Показать подписки на моментальные снимки**</span><span class="sxs-lookup"><span data-stu-id="f417b-116">**Show Snapshot Subscriptions**</span></span>  
 <span data-ttu-id="f417b-117">Выберите типы подписок (на публикацию транзакций, на моментальные снимки или слиянием), которые будут выводиться для выбранного издателя.</span><span class="sxs-lookup"><span data-stu-id="f417b-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="f417b-118">**Показать**</span><span class="sxs-lookup"><span data-stu-id="f417b-118">**Show**</span></span>  
 <span data-ttu-id="f417b-119">Выберите состояния подписки, которые должны отображаться для выбранного типа подписки.</span><span class="sxs-lookup"><span data-stu-id="f417b-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="f417b-120">Например, можно выбрать отображение только тех подписок, которые содержат ошибку.</span><span class="sxs-lookup"><span data-stu-id="f417b-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="f417b-121">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="f417b-121">**Status**</span></span>  
 <span data-ttu-id="f417b-122">Состояние каждой подписки, определяемое состоянием агента моментальных снимков или агента распространителя (отображается состояние с более высоким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="f417b-122">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="f417b-123">По умолчанию, в сетке, содержащей сведения о подписках, они сортируются по столбцу **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="f417b-123">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="f417b-124">В следующем списке показаны возможные значения состояния и порядок сортировки значений (например, ошибки всегда показываются в верхней части сетки).</span><span class="sxs-lookup"><span data-stu-id="f417b-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="f417b-125">Ошибка</span><span class="sxs-lookup"><span data-stu-id="f417b-125">Error</span></span>  
  
-   <span data-ttu-id="f417b-126">Срок действия скоро истекает или истек</span><span class="sxs-lookup"><span data-stu-id="f417b-126">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="f417b-127">Неинициализированная подписка</span><span class="sxs-lookup"><span data-stu-id="f417b-127">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="f417b-128">Повтор последней невыполненной команды</span><span class="sxs-lookup"><span data-stu-id="f417b-128">Retrying failed command</span></span>  
  
-   <span data-ttu-id="f417b-129">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="f417b-129">Synchronizing</span></span>  
  
-   <span data-ttu-id="f417b-130">Нет синхронизации</span><span class="sxs-lookup"><span data-stu-id="f417b-130">Not synchronizing</span></span>  
  
 <span data-ttu-id="f417b-131">Порядок сортировки также определяет отображаемое значение, если данная подписка имеет более одного состояния.</span><span class="sxs-lookup"><span data-stu-id="f417b-131">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="f417b-132">Например, если подписка содержит ошибку и срок ее действия скоро истекает, в столбце **Состояние** отображается **Ошибка**.</span><span class="sxs-lookup"><span data-stu-id="f417b-132">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="f417b-133">Значения состояний **Срок действия скоро истекает или истек** и **Неинициализированная подписка** являются предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="f417b-133">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="f417b-134">Когда выводится предупреждение, столбец **Состояние** также отображается при запущенном агенте.</span><span class="sxs-lookup"><span data-stu-id="f417b-134">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="f417b-135">Например, возможно состояние **Выполняется, срок действия скоро истекает или истек**.</span><span class="sxs-lookup"><span data-stu-id="f417b-135">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="f417b-136">Значение состояния **Срок действия скоро истекает или истек** отображается только при установленном пороге.</span><span class="sxs-lookup"><span data-stu-id="f417b-136">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="f417b-137">Дополнительные сведения об установке пороговых значений см. в статье [Настройка пороговых значений и предупреждений в мониторе репликации](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="f417b-137">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="f417b-138">**Подписка**</span><span class="sxs-lookup"><span data-stu-id="f417b-138">**Subscription**</span></span>  
 <span data-ttu-id="f417b-139">Имя каждой подписки в виде: *имя_подписчика: имя_базы_данных_подписки*.</span><span class="sxs-lookup"><span data-stu-id="f417b-139">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="f417b-140">**Публикация**</span><span class="sxs-lookup"><span data-stu-id="f417b-140">**Publication**</span></span>  
 <span data-ttu-id="f417b-141">Имя публикации, с которой синхронизируется подписка, в следующем виде: *имя_базы_данных_публикации: имя_публикации*.</span><span class="sxs-lookup"><span data-stu-id="f417b-141">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="f417b-142">**Последняя синхронизация**</span><span class="sxs-lookup"><span data-stu-id="f417b-142">**Last Synchronization**</span></span>  
 <span data-ttu-id="f417b-143">Время последнего запуска агента распространителя.</span><span class="sxs-lookup"><span data-stu-id="f417b-143">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="f417b-144">Если в данный момент синхронизация выполняется, то выводится сообщение **Выполняется** .</span><span class="sxs-lookup"><span data-stu-id="f417b-144">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f417b-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="f417b-145">See Also</span></span>  
 <span data-ttu-id="f417b-146">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f417b-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f417b-147">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f417b-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="f417b-148">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="f417b-148">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
