---
title: Диалоговое окно «сведения об издателе» Репликация SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.publications.f1
ms.assetid: 0b2e3d4e-03b7-4c31-8f96-48648d750010
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3797ae4f9fe8f42b4abec715c63bc627c2a62cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730466"
---
# <a name="sql-server-replication-publisher-information-dialog-box"></a><span data-ttu-id="c058b-102">Диалоговое окно "сведения об издателе" Репликация SQL Server</span><span class="sxs-lookup"><span data-stu-id="c058b-102">SQL Server Replication 'Publisher Information' dialog box</span></span>
  <span data-ttu-id="c058b-103">Вкладка **Публикации** содержит сводные данные по всем публикациям на издателе, выбранном в левой панели.</span><span class="sxs-lookup"><span data-stu-id="c058b-103">The **Publications** tab provides summary information for all publications at the Publisher selected in the left pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c058b-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="c058b-104">Options</span></span>  
 <span data-ttu-id="c058b-105">Чтобы изменить способ отображения данных в сетке, щелкните правой кнопкой мыши сетку, а затем один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="c058b-105">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="c058b-106">**Сортировать**: сортировка по одному или нескольким столбцам в диалоговом окне **Сортировка столбцов** .</span><span class="sxs-lookup"><span data-stu-id="c058b-106">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="c058b-107">**Выберите столбцы для отображения**: выбор столбцов для отображения и порядка их отображения в диалоговом окне **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="c058b-107">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="c058b-108">**Фильтр**: фильтрация строк в сетке на основании значений столбцов в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="c058b-108">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="c058b-109">**Очистить фильтр**: удаление всех параметров фильтра для сетки.</span><span class="sxs-lookup"><span data-stu-id="c058b-109">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="c058b-110">Настройки фильтра уникальны для каждой сетки.</span><span class="sxs-lookup"><span data-stu-id="c058b-110">Filter settings are specific to each grid.</span></span> <span data-ttu-id="c058b-111">Выбор и сортировка столбцов применяются ко всем сеткам одного типа, как, например, сетка публикаций для каждого издателя.</span><span class="sxs-lookup"><span data-stu-id="c058b-111">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="c058b-112">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="c058b-112">**Status**</span></span>  
 <span data-ttu-id="c058b-113">Состояние каждой публикации, определяемое по состоянию наивысшего приоритета его подписок.</span><span class="sxs-lookup"><span data-stu-id="c058b-113">The status of each publication, which is determined by the highest priority status of its subscriptions.</span></span> <span data-ttu-id="c058b-114">По умолчанию сетка, содержащая сведения о публикациях, сортируется по столбцу **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="c058b-114">By default, the grid containing publication information is sorted by the **Status** column.</span></span> <span data-ttu-id="c058b-115">Следующий список показывает возможные значения состояния и порядок их сортировки (например, ошибки всегда выводятся вверху табличной сетки):</span><span class="sxs-lookup"><span data-stu-id="c058b-115">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid):</span></span>  
  
-   <span data-ttu-id="c058b-116">Ошибка</span><span class="sxs-lookup"><span data-stu-id="c058b-116">Error</span></span>  
  
-   <span data-ttu-id="c058b-117">Критическая производительность</span><span class="sxs-lookup"><span data-stu-id="c058b-117">Performance critical</span></span>  
  
-   <span data-ttu-id="c058b-118">Повтор последней невыполненной команды</span><span class="sxs-lookup"><span data-stu-id="c058b-118">Retrying failed command</span></span>  
  
-   <span data-ttu-id="c058b-119">OK</span><span class="sxs-lookup"><span data-stu-id="c058b-119">OK</span></span>  
  
 <span data-ttu-id="c058b-120">Состояние **Критическое для производительности** относится к подпискам на публикации транзакций и подпискам на публикации слиянием, для подписок на публикации транзакций оно выводится только при установленном пороге.</span><span class="sxs-lookup"><span data-stu-id="c058b-120">The status value **Performance critical** is relevant for transactional subscriptions and merge subscriptions; for transactional subscriptions, it can be displayed only if a threshold is set.</span></span> <span data-ttu-id="c058b-121">Сведения по измерению производительности и установке пороговых значений см. в статьях [Наблюдение за производительностью с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md) и [Настройка пороговых значений и предупреждений в мониторе репликации](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="c058b-121">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="c058b-122">**Публикация**</span><span class="sxs-lookup"><span data-stu-id="c058b-122">**Publication**</span></span>  
 <span data-ttu-id="c058b-123">Имя каждой публикации в виде *имя_базы_данных_публикации: имя_публикации*.</span><span class="sxs-lookup"><span data-stu-id="c058b-123">The name of each publication, in the form *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="c058b-124">**Подписки**</span><span class="sxs-lookup"><span data-stu-id="c058b-124">**Subscriptions**</span></span>  
 <span data-ttu-id="c058b-125">Число подписок для каждой публикации.</span><span class="sxs-lookup"><span data-stu-id="c058b-125">The number of subscriptions for each publication.</span></span>  
  
 <span data-ttu-id="c058b-126">**Синхронизация**</span><span class="sxs-lookup"><span data-stu-id="c058b-126">**Synchronizing**</span></span>  
 <span data-ttu-id="c058b-127">Число подписок для каждой публикации, синхронизируемых в данный момент:</span><span class="sxs-lookup"><span data-stu-id="c058b-127">The number of subscriptions for each publication that are currently synchronizing:</span></span>  
  
-   <span data-ttu-id="c058b-128">При репликации транзакций «синхронизация» означает, что выполняется агент распространителя, но данные необязательно реплицируются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c058b-128">For transactional replication, "synchronizing" means that the Distribution Agent is running, but data is not necessarily being replicated.</span></span>  
  
-   <span data-ttu-id="c058b-129">При репликации слиянием «синхронизация» означает, что выполняется агент слияния и данные реплицируются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c058b-129">For merge replication, "synchronizing" means that the Merge Agent is running and that data is currently being replicated.</span></span>  
  
-   <span data-ttu-id="c058b-130">При репликации моментальных снимков «синхронизация» означает, что выполняется агент распространителя и данные реплицируются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c058b-130">For snapshot replication, "synchronizing" means that the Distribution Agent is running and that data is currently being replicated.</span></span>  
  
 <span data-ttu-id="c058b-131">**Текущая средняя производительность** и **Худшая производительность в данный момент**</span><span class="sxs-lookup"><span data-stu-id="c058b-131">**Current Average Performance** and **Current Worst Performance**</span></span>  
 <span data-ttu-id="c058b-132">Только для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c058b-132">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="c058b-133">Оценка средней и наихудшей производительности соответственно для всех подписок на публикацию.</span><span class="sxs-lookup"><span data-stu-id="c058b-133">The average performance rating and the worst performance rating, respectively, for all subscriptions to a publication.</span></span> <span data-ttu-id="c058b-134">Оценка основывается на самых последних измерениях, снятых монитором репликации, и не отражает производительность подписки за период времени.</span><span class="sxs-lookup"><span data-stu-id="c058b-134">Ratings are based on the most recent measurements taken by Replication Monitor and do not reflect the performance of a subscription over time.</span></span>  
  
 <span data-ttu-id="c058b-135">Для репликации транзакций монитор репликации выводит значение только для публикаций с установленным порогом производительности.</span><span class="sxs-lookup"><span data-stu-id="c058b-135">For transactional replication, Replication Monitor displays a value only for publications that have performance thresholds defined.</span></span> <span data-ttu-id="c058b-136">Если пороги производительности для публикации не установлены, в данном столбце выводится **Не включено**.</span><span class="sxs-lookup"><span data-stu-id="c058b-136">If performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="c058b-137">Для репликации слиянием монитор репликации отображает значение после пяти синхронизаций, использующих один тип соединения (коммутируемое или по локальной сети), каждая из которых содержит 50 или более изменений.</span><span class="sxs-lookup"><span data-stu-id="c058b-137">For merge replication, Replication Monitor displays a value after five synchronizations have occurred with 50 or more changes each over the same type of connection (dial-up or LAN).</span></span> <span data-ttu-id="c058b-138">Если произошло менее 5 синхронизаций с 50 и более изменениями или последняя выполненная синхронизация имела менее 50 изменений, то этот столбец остается пустым.</span><span class="sxs-lookup"><span data-stu-id="c058b-138">If there have been less than five synchronizations with 50 or more changes or the most recent synchronization has less than 50 changes, this column is blank.</span></span>  
  
 <span data-ttu-id="c058b-139">Рейтинг производительности может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="c058b-139">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="c058b-140">Высокая</span><span class="sxs-lookup"><span data-stu-id="c058b-140">Excellent</span></span>  
  
-   <span data-ttu-id="c058b-141">Хорошая.</span><span class="sxs-lookup"><span data-stu-id="c058b-141">Good</span></span>  
  
-   <span data-ttu-id="c058b-142">удовлетворительная</span><span class="sxs-lookup"><span data-stu-id="c058b-142">Fair</span></span>  
  
-   <span data-ttu-id="c058b-143">Низкая</span><span class="sxs-lookup"><span data-stu-id="c058b-143">Poor</span></span>  
  
-   <span data-ttu-id="c058b-144">Critical</span><span class="sxs-lookup"><span data-stu-id="c058b-144">Critical</span></span>  
  
 <span data-ttu-id="c058b-145">Дополнительные сведения об определении оценки производительности и установке пороговых значений см. в статье [Наблюдение за производительностью с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="c058b-145">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c058b-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="c058b-146">See Also</span></span>  
 <span data-ttu-id="c058b-147">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c058b-147">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="c058b-148">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c058b-148">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="c058b-149">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="c058b-149">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
