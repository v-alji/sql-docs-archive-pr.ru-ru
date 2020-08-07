---
title: Сведения о публикации, предупреждения (публикация транзакций, SQL Server 2005 и более поздних версий) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.tran.f1
ms.assetid: 4d4baf1d-d0a1-4d09-bec7-137811f43f09
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac7ab0f712fe69d3736985921d70b0ce200d474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733870"
---
# <a name="publication-information-warnings-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="ffecb-102">Сведения о публикации, предупреждения (публикация транзакций, SQL Server 2005 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="ffecb-102">Publication Information, Warnings (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="ffecb-103"> Вкладка **Предупреждения** доступна для распространителей, работающих с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] или более поздними версиями.</span><span class="sxs-lookup"><span data-stu-id="ffecb-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="ffecb-104">Вкладка **Предупреждения** позволяет выполнять следующие задачи для выбранных публикаций:</span><span class="sxs-lookup"><span data-stu-id="ffecb-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="ffecb-105">включать предупреждения, которые будут отображаться в мониторе репликации;</span><span class="sxs-lookup"><span data-stu-id="ffecb-105">Enable warnings to be displayed in Replication Monitor.</span></span>  
  
-   <span data-ttu-id="ffecb-106">указать пороговые значения для предупреждений;</span><span class="sxs-lookup"><span data-stu-id="ffecb-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="ffecb-107">указать оповещения, связанные с предупреждениями;</span><span class="sxs-lookup"><span data-stu-id="ffecb-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="ffecb-108">Предупреждения, пороговые значения и оповещения</span><span class="sxs-lookup"><span data-stu-id="ffecb-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="ffecb-109">По умолчанию монитор репликации отображает предупреждения для неинициализированных подписок: состояние **Неинициализированная подписка** отображается в виде предупреждения в столбце **Состояние** страниц, содержащих сведения о подписке.</span><span class="sxs-lookup"><span data-stu-id="ffecb-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="ffecb-110">Для публикаций транзакций можно задать, должны ли такие дополнительные условия приводить к выдаче следующего предупреждения:</span><span class="sxs-lookup"><span data-stu-id="ffecb-110">For transactional publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="ffecb-111">Приближение даты истечения срока подписки.</span><span class="sxs-lookup"><span data-stu-id="ffecb-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="ffecb-112">Это соответствует параметру **Предупреждать, если действие подписки истекает до порогового значения**.</span><span class="sxs-lookup"><span data-stu-id="ffecb-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="ffecb-113">Если указанное пороговое значение достигнуто или превышено, состояние подписки отображается как **Срок действия скоро истекает или истек** (в том случае если не требуется отобразить более важную информацию).</span><span class="sxs-lookup"><span data-stu-id="ffecb-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="ffecb-114">Превышение заданной задержки.</span><span class="sxs-lookup"><span data-stu-id="ffecb-114">Exceeding the specified latency.</span></span> <span data-ttu-id="ffecb-115">Время, прошедшее между фиксацией транзакции на издателе и фиксацией соответствующей транзакции на подписчике.</span><span class="sxs-lookup"><span data-stu-id="ffecb-115">This is the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="ffecb-116">Это соответствует параметру **Предупредить, если задержка превышает пороговое значение**.</span><span class="sxs-lookup"><span data-stu-id="ffecb-116">This corresponds to the option **Warn if latency exceeds the threshold**.</span></span> <span data-ttu-id="ffecb-117">Если указанное пороговое значение достигнуто или превышено, состояние подписки отображается как **Критическое для производительности** (в случае если не требуется отобразить более приоритетные сведения).</span><span class="sxs-lookup"><span data-stu-id="ffecb-117">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="ffecb-118">Порог также используется для определения оценки производительности, которая отображается в столбце **Производительность** на страницах с данными о подписке.</span><span class="sxs-lookup"><span data-stu-id="ffecb-118">The threshold is also used to provide a performance rating, which is displayed in the **Performance** column of pages that include subscription information.</span></span> <span data-ttu-id="ffecb-119">Рейтинг производительности может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="ffecb-119">The performance rating is one of the following values:</span></span>  
  
    -   <span data-ttu-id="ffecb-120">Отлично</span><span class="sxs-lookup"><span data-stu-id="ffecb-120">Excellent</span></span>  
  
    -   <span data-ttu-id="ffecb-121">Хорошо</span><span class="sxs-lookup"><span data-stu-id="ffecb-121">Good</span></span>  
  
    -   <span data-ttu-id="ffecb-122">Ниже среднего</span><span class="sxs-lookup"><span data-stu-id="ffecb-122">Fair</span></span>  
  
    -   <span data-ttu-id="ffecb-123">Плохо</span><span class="sxs-lookup"><span data-stu-id="ffecb-123">Poor</span></span>  
  
    -   <span data-ttu-id="ffecb-124">Критический</span><span class="sxs-lookup"><span data-stu-id="ffecb-124">Critical</span></span>  
  
 <span data-ttu-id="ffecb-125">При включении предупреждения задается пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="ffecb-125">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="ffecb-126">Например, если включено предупреждение **Предупредить, если задержка превышает пороговое значение**, выберите допустимый интервал времени между фиксацией транзакции на издателе и фиксацией транзакции на подписчике.</span><span class="sxs-lookup"><span data-stu-id="ffecb-126">For example, if you enable the warning **Warn if latency exceeds the threshold**, select the amount of time allowable between a transaction being committed at the Publisher and the transaction being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="ffecb-127">Достижение порогового значения помимо отображения предупреждения в мониторе репликации может также вызывать системное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="ffecb-127">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="ffecb-128">Предупреждения определяются нажатием кнопки **Настройка предупреждений** и указанием сведений в диалоговом окне **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="ffecb-128">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ffecb-129">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffecb-129">Options</span></span>  
 <span data-ttu-id="ffecb-130">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="ffecb-130">**Enabled**</span></span>  
 <span data-ttu-id="ffecb-131">Выберите, чтобы включить предупреждение и указать пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="ffecb-131">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="ffecb-132">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="ffecb-132">**Warning**</span></span>  
 <span data-ttu-id="ffecb-133">Описание предупреждения, связанного с пороговым значением.</span><span class="sxs-lookup"><span data-stu-id="ffecb-133">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="ffecb-134">**Пороговое значение**.</span><span class="sxs-lookup"><span data-stu-id="ffecb-134">**Threshold**</span></span>  
 <span data-ttu-id="ffecb-135">Укажите пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="ffecb-135">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="ffecb-136">**Настройка оповещений**</span><span class="sxs-lookup"><span data-stu-id="ffecb-136">**Configure Alerts**</span></span>  
 <span data-ttu-id="ffecb-137">Выберите строку в сетке **Предупреждения** и нажмите кнопку **Настройка предупреждений** для запуска диалогового окна **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="ffecb-137">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="ffecb-138">Это диалоговое окно позволяет определить оповещение, связанное с выбранным пороговым значением и предупреждением.</span><span class="sxs-lookup"><span data-stu-id="ffecb-138">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="ffecb-139">**Отменить изменения**</span><span class="sxs-lookup"><span data-stu-id="ffecb-139">**Discard Changes**</span></span>  
 <span data-ttu-id="ffecb-140">Нажмите эту кнопку для отмены всех произведенных изменений предупреждениях и пороговых значениях.</span><span class="sxs-lookup"><span data-stu-id="ffecb-140">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ffecb-141">Нажатие кнопки **Отменить изменения** не затрагивает предупреждения, определенные в диалоговом окне **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="ffecb-141">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="ffecb-142">**Сохранить изменения**</span><span class="sxs-lookup"><span data-stu-id="ffecb-142">**Save Changes**</span></span>  
 <span data-ttu-id="ffecb-143">Нажмите эту кнопку для сохранения всех произведенных изменений предупреждений и пороговых значений.</span><span class="sxs-lookup"><span data-stu-id="ffecb-143">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffecb-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="ffecb-144">See Also</span></span>  
 <span data-ttu-id="ffecb-145">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="ffecb-145">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="ffecb-146">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="ffecb-146">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="ffecb-147">[Мониторинг производительности с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="ffecb-147">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="ffecb-148">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="ffecb-148">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="ffecb-149">Настройка пороговых значений и предупреждений в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="ffecb-149">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
