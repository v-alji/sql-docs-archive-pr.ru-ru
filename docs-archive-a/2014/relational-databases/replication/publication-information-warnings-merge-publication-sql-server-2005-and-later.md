---
title: Сведения о публикации, предупреждения (публикация слиянием, SQL Server 2005 и более поздних версий) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.merge.f1
ms.assetid: 9bef3565-5f13-42ac-8723-ebe55b0c11e6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75f58a4cd9bd84791acf7fd9d28147ef3bbd6232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664874"
---
# <a name="publication-information-warnings-merge-publication-sql-server-2005-and-later"></a><span data-ttu-id="4d59a-102">Сведения о публикации, предупреждения (публикации слиянием, SQL Server 2005 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="4d59a-102">Publication Information, Warnings (Merge Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="4d59a-103"> Вкладка **Предупреждения** доступна для распространителей, работающих с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] или более поздними версиями.</span><span class="sxs-lookup"><span data-stu-id="4d59a-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="4d59a-104">Вкладка **Предупреждения** позволяет выполнять следующие задачи для выбранных публикаций:</span><span class="sxs-lookup"><span data-stu-id="4d59a-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="4d59a-105">включить предупреждения;</span><span class="sxs-lookup"><span data-stu-id="4d59a-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="4d59a-106">указать пороговые значения для предупреждений;</span><span class="sxs-lookup"><span data-stu-id="4d59a-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="4d59a-107">указать оповещения, связанные с предупреждениями;</span><span class="sxs-lookup"><span data-stu-id="4d59a-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="4d59a-108">Предупреждения, пороговые значения и оповещения</span><span class="sxs-lookup"><span data-stu-id="4d59a-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="4d59a-109">По умолчанию монитор репликации отображает предупреждения для неинициализированных подписок: состояние **Неинициализированная подписка** отображается в виде предупреждения в столбце **Состояние** страниц, содержащих сведения о подписке.</span><span class="sxs-lookup"><span data-stu-id="4d59a-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="4d59a-110">Для публикаций слиянием можно указать, ведут ли следующие дополнительные условия к предупреждениям.</span><span class="sxs-lookup"><span data-stu-id="4d59a-110">For merge publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="4d59a-111">Приближение даты истечения срока подписки.</span><span class="sxs-lookup"><span data-stu-id="4d59a-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="4d59a-112">Это соответствует параметру **Предупреждать, если действие подписки истекает до порогового значения**.</span><span class="sxs-lookup"><span data-stu-id="4d59a-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="4d59a-113">Если указанное пороговое значение достигнуто или превышено, состояние подписки отображается как **Срок действия скоро истекает или истек** (в том случае если не требуется отобразить более важную информацию).</span><span class="sxs-lookup"><span data-stu-id="4d59a-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="4d59a-114">Превышение заданного времени синхронизации.</span><span class="sxs-lookup"><span data-stu-id="4d59a-114">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="4d59a-115">Это относится к параметрам **Предупреждать при превышении порогового значения длины слияния для удаленных соединений** и **Предупреждать при превышении порогового значения длины слияния для соединений по локальной сети**.</span><span class="sxs-lookup"><span data-stu-id="4d59a-115">This corresponds to the options **Warn if a merge length for dialup connections exceeds the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="4d59a-116">Можно установить оба этих порога, но во время синхронизации используется только один из них.</span><span class="sxs-lookup"><span data-stu-id="4d59a-116">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="4d59a-117">Агент слияния использует порог, соответствующий типу соединения.</span><span class="sxs-lookup"><span data-stu-id="4d59a-117">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="4d59a-118">Если указанное пороговое значение достигнуто или превышено, состояние подписки отображается как **Продолжительное слияние** (в том случае если не требуется отобразить более приоритетную информацию).</span><span class="sxs-lookup"><span data-stu-id="4d59a-118">If the specified threshold is met or exceeded, the subscription status is displayed as **Long-running merge** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="4d59a-119">Невозможность обработки заданного числа строк за указанное время.</span><span class="sxs-lookup"><span data-stu-id="4d59a-119">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="4d59a-120">Это относится к параметрам **Предупреждать, если число строк слияния в секунду снижается ниже порогового значения для удаленных соединений** и **Предупреждать при превышении порогового значения длины слияния для соединений по локальной сети.**</span><span class="sxs-lookup"><span data-stu-id="4d59a-120">This corresponds to the options **Warn if rows merged per second for dialup connections is less than the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="4d59a-121">Можно установить оба этих порога, но во время синхронизации используется только один из них.</span><span class="sxs-lookup"><span data-stu-id="4d59a-121">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="4d59a-122">Агент слияния использует порог, соответствующий типу соединения.</span><span class="sxs-lookup"><span data-stu-id="4d59a-122">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="4d59a-123">Если указанное пороговое значение достигнуто или превышено, состояние подписки отображается как **Критическое для производительности** (в случае если не требуется отобразить более приоритетные сведения).</span><span class="sxs-lookup"><span data-stu-id="4d59a-123">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="4d59a-124">При включении предупреждения задается пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="4d59a-124">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="4d59a-125">Например, включая предупреждение **Предупреждать при превышении порогового значения длины слияния для соединений по локальной сети**, необходимо задать допустимый максимум времени для синхронизации слиянием.</span><span class="sxs-lookup"><span data-stu-id="4d59a-125">For example, if you enable the warning **Warn if a merge length for LAN connections exceeds the threshold**, set the maximum allowable length of time for a merge synchronization.</span></span>  
  
 <span data-ttu-id="4d59a-126">Достижение порогового значения помимо отображения предупреждения в мониторе репликации может также вызывать системное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4d59a-126">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="4d59a-127">Предупреждения определяются нажатием кнопки **Настройка предупреждений** и указанием сведений в диалоговом окне **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="4d59a-127">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d59a-128">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d59a-128">Options</span></span>  
 <span data-ttu-id="4d59a-129">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="4d59a-129">**Enabled**</span></span>  
 <span data-ttu-id="4d59a-130">Выберите, чтобы включить предупреждение и указать пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="4d59a-130">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="4d59a-131">**Оповещение**</span><span class="sxs-lookup"><span data-stu-id="4d59a-131">**Alert**</span></span>  
 <span data-ttu-id="4d59a-132">Включите параметр предупреждения для данного предупреждения по репликации.</span><span class="sxs-lookup"><span data-stu-id="4d59a-132">Select to enable the alert setting for a given replication warning.</span></span>  
  
 <span data-ttu-id="4d59a-133">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="4d59a-133">**Warning**</span></span>  
 <span data-ttu-id="4d59a-134">Описание предупреждения, связанного с пороговым значением.</span><span class="sxs-lookup"><span data-stu-id="4d59a-134">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="4d59a-135">**Пороговое значение**.</span><span class="sxs-lookup"><span data-stu-id="4d59a-135">**Threshold**</span></span>  
 <span data-ttu-id="4d59a-136">Укажите пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="4d59a-136">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="4d59a-137">**Настройка оповещений**</span><span class="sxs-lookup"><span data-stu-id="4d59a-137">**Configure Alerts**</span></span>  
 <span data-ttu-id="4d59a-138">Выберите строку в сетке **Предупреждения** и нажмите кнопку **Настройка предупреждений** для запуска диалогового окна **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="4d59a-138">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="4d59a-139">Это диалоговое окно позволяет определить оповещение, связанное с выбранным пороговым значением и предупреждением.</span><span class="sxs-lookup"><span data-stu-id="4d59a-139">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="4d59a-140">**Отменить изменения**</span><span class="sxs-lookup"><span data-stu-id="4d59a-140">**Discard Changes**</span></span>  
 <span data-ttu-id="4d59a-141">Нажмите эту кнопку для отмены всех произведенных изменений предупреждениях и пороговых значениях.</span><span class="sxs-lookup"><span data-stu-id="4d59a-141">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d59a-142">Нажатие кнопки **Отменить изменения** не затрагивает предупреждения, определенные в диалоговом окне **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="4d59a-142">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="4d59a-143">**Сохранить изменения**</span><span class="sxs-lookup"><span data-stu-id="4d59a-143">**Save Changes**</span></span>  
 <span data-ttu-id="4d59a-144">Нажмите эту кнопку для сохранения всех произведенных изменений предупреждений и пороговых значений.</span><span class="sxs-lookup"><span data-stu-id="4d59a-144">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d59a-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d59a-145">See Also</span></span>  
 <span data-ttu-id="4d59a-146">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4d59a-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="4d59a-147">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4d59a-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="4d59a-148">[Мониторинг производительности с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4d59a-148">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="4d59a-149">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="4d59a-149">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="4d59a-150">Настройка пороговых значений и предупреждений в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="4d59a-150">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
