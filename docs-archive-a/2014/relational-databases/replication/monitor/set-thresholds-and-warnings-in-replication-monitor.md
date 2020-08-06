---
title: Настройка пороговых значений и предупреждений в мониторе репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- Merge Agent, thresholds and warnings
- Distribution Agent, thresholds and warnings
- thresholds [SQL Server replication]
- Replication Monitor, thresholds and warnings
- monitoring performance [SQL Server replication], thresholds and warnings
ms.assetid: 3a409c2c-b77e-4001-b81a-1dcd918618ec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f34878a6398df34e55e6dd3783f2da736bee0959
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750727"
---
# <a name="set-thresholds-and-warnings-in-replication-monitor"></a><span data-ttu-id="fa963-102">Настройка пороговых значений и предупреждений в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="fa963-102">Set Thresholds and Warnings in Replication Monitor</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="fa963-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Монитор репликации отображает сведения о состоянии публикаций и подписок.</span><span class="sxs-lookup"><span data-stu-id="fa963-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor displays status information for publications and subscriptions.</span></span> <span data-ttu-id="fa963-104">По умолчанию монитор репликации отображает предупреждения только об неинициализированных подписках, но можно включить другие предупреждения.</span><span class="sxs-lookup"><span data-stu-id="fa963-104">By default, Replication Monitor displays warnings only for uninitialized subscriptions, but you can enable warnings for other conditions.</span></span> <span data-ttu-id="fa963-105">Рекомендуется включить предупреждения для используемой топологии, чтобы своевременно получать сведения о состоянии и производительности репликации.</span><span class="sxs-lookup"><span data-stu-id="fa963-105">It is recommended that you enable warnings for your topology, so that you are informed about status and performance in a timely manner.</span></span>  
  
 <span data-ttu-id="fa963-106">При включении предупреждения требуется задать пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="fa963-106">When you enable a warning, you specify a threshold.</span></span> <span data-ttu-id="fa963-107">Когда это значение достигается или превышается, отображается предупреждение (если отсутствует необходимость в отображении сообщения с более высоким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="fa963-107">When that threshold is met or exceeded, a warning is displayed (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="fa963-108">Достижение порогового значения помимо отображения предупреждения в мониторе репликации может также вызывать системное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="fa963-108">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="fa963-109">Предупреждения могут быть включены для следующих условий.</span><span class="sxs-lookup"><span data-stu-id="fa963-109">You can enable warnings for the following conditions:</span></span>  
  
-   <span data-ttu-id="fa963-110">Приближение срока окончания действия подписки.</span><span class="sxs-lookup"><span data-stu-id="fa963-110">Imminent subscription expiration</span></span>  
  
     <span data-ttu-id="fa963-111">Это относится ко всем типам репликации.</span><span class="sxs-lookup"><span data-stu-id="fa963-111">This applies to all types of replication.</span></span> <span data-ttu-id="fa963-112">Если достигнуто или превышено заданное пороговое значение, то состояние подписки отображается как **Срок действия скоро истекает или истек**.</span><span class="sxs-lookup"><span data-stu-id="fa963-112">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired**.</span></span>  
  
-   <span data-ttu-id="fa963-113">Превышение указанного времени задержки (время между моментом фиксирования транзакции на издателе и моментом фиксирования соответствующей транзакции на подписчике).</span><span class="sxs-lookup"><span data-stu-id="fa963-113">Exceeding the specified latency (the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber).</span></span>  
  
     <span data-ttu-id="fa963-114">Это условие применяется к репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="fa963-114">This applies to transactional replication.</span></span> <span data-ttu-id="fa963-115">Если достигнуто или превышено заданное пороговое значение, состояние подписки отображается как **Критическое для производительности**.</span><span class="sxs-lookup"><span data-stu-id="fa963-115">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical**.</span></span>  
  
-   <span data-ttu-id="fa963-116">Превышение заданного времени синхронизации.</span><span class="sxs-lookup"><span data-stu-id="fa963-116">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="fa963-117">Это условие применяется к репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="fa963-117">This applies to merge replication.</span></span> <span data-ttu-id="fa963-118">Когда достигается или превышается указанное значение порога, состояние отображается как **Продолжительное слияние**.</span><span class="sxs-lookup"><span data-stu-id="fa963-118">If the specified threshold is met or exceeded, the status is displayed as **Long-running merge**.</span></span> <span data-ttu-id="fa963-119">Можно задать различные пороговые значения для коммутируемых соединений и соединений по локальной сети.</span><span class="sxs-lookup"><span data-stu-id="fa963-119">You can specify different thresholds for dialup and Local Area Network (LAN) connections.</span></span>  
  
-   <span data-ttu-id="fa963-120">Невозможность обработки заданного числа строк за указанное время.</span><span class="sxs-lookup"><span data-stu-id="fa963-120">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="fa963-121">Это условие применяется к репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="fa963-121">This applies to merge replication.</span></span> <span data-ttu-id="fa963-122">Когда достигается или превышается указанное значение порога, состояние отображается как **Критическое для производительности**.</span><span class="sxs-lookup"><span data-stu-id="fa963-122">If the specified threshold is met or exceeded, the status is displayed as **Performance critical**.</span></span> <span data-ttu-id="fa963-123">Можно задать различные пороговые значения для коммутируемых соединений и соединений по локальной сети.</span><span class="sxs-lookup"><span data-stu-id="fa963-123">You can specify different thresholds for dialup and LAN connections.</span></span>  
  
 <span data-ttu-id="fa963-124">Дополнительные сведения о предупреждениях **Критическое для производительности** и **Продолжительное слияние** см. в статье [Наблюдение за производительностью с помощью монитора репликации](monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fa963-124">For more information on the warnings **Performance critical** and **Long-running merge**, see [Monitor Performance with Replication Monitor](monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="fa963-125">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="fa963-125">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="fa963-126">Установка пороговых значений и предупреждений для публикации транзакций</span><span class="sxs-lookup"><span data-stu-id="fa963-126">Set thresholds and warnings for a transactional publication</span></span>](#Transactional)  
  
-   [<span data-ttu-id="fa963-127">Установка пороговых значений и предупреждений для публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="fa963-127">Set thresholds and warnings for a merge publication</span></span>](#Merge)  
  
-   [<span data-ttu-id="fa963-128">Установка пороговых значений и предупреждений для публикации моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="fa963-128">Set thresholds and warnings for a snapshot publication</span></span>](#Snapshot)  
  
##  <a name="to-set-thresholds-and-warnings-for-a-transactional-publication"></a><a name="Transactional"></a><span data-ttu-id="fa963-129">Установка пороговых значений и предупреждений для публикации транзакций</span><span class="sxs-lookup"><span data-stu-id="fa963-129">To set thresholds and warnings for a transactional publication</span></span>  
  
1.  <span data-ttu-id="fa963-130">Раскройте на левой панели группу издателей, раскройте издатель и выберите нужную публикацию.</span><span class="sxs-lookup"><span data-stu-id="fa963-130">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="fa963-131">Перейдите на вкладку **предупреждения** . Чтобы просмотреть дополнительные сведения о параметрах на этой вкладке, щелкните **Справка** в строке меню.</span><span class="sxs-lookup"><span data-stu-id="fa963-131">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="fa963-132">Включите нужное предупреждение, установив соответствующий флажок: **Предупреждать, если действие подписки истекает до порогового значения** или **Предупреждать, если задержка превышает пороговое значение**.</span><span class="sxs-lookup"><span data-stu-id="fa963-132">Enable a warning by selecting the appropriate check box: **Warn if a subscription will expire within the threshold** or **Warn if latency exceeds the threshold**.</span></span>  
  
4.  <span data-ttu-id="fa963-133">Установите пороговое значение для предупреждений в столбце **Порог** .</span><span class="sxs-lookup"><span data-stu-id="fa963-133">Set a threshold for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="fa963-134">Например, если на шаге 3 установлен флажок **Предупреждать, если задержка превышает пороговое значение** , можно выбрать задержку, равную **60 секунд** , в столбце **Порог** .</span><span class="sxs-lookup"><span data-stu-id="fa963-134">For example, if you selected **Warn if latency exceeds the threshold** in step 3, you could select a latency of **60 seconds** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="fa963-135">Щелкните **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="fa963-135">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="fa963-136">Настройка предупреждений для пороговых значений</span><span class="sxs-lookup"><span data-stu-id="fa963-136">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="fa963-137">Щелкните **Настройка предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="fa963-137">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="fa963-138">В диалоговом окне **Настройка предупреждений репликации** выберите необходимое предупреждение, а затем щелкните **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="fa963-138">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="fa963-139">Это диалоговое окно отображает предупреждения для всех типов публикаций, включая предупреждения, не связанные с наблюдаемыми пороговыми значениями.</span><span class="sxs-lookup"><span data-stu-id="fa963-139">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="fa963-140">Дополнительные сведения см. в статье [Использование предупреждений для событий агента репликации](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="fa963-140">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="fa963-141">Задайте следующие параметры в диалоговом окне **\<AlertName> свойств предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="fa963-141">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="fa963-142">На странице **Общие** щелкните **Включить**, укажите базу данных, к которой нужно применить данное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="fa963-142">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="fa963-143">На странице **Ответ** укажите, надо ли отправить оповещение по электронной почте и/или запустить задание.</span><span class="sxs-lookup"><span data-stu-id="fa963-143">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="fa963-144">На странице **Параметры** измените текст ответа.</span><span class="sxs-lookup"><span data-stu-id="fa963-144">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="fa963-145">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fa963-145">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-merge-publication"></a><a name="Merge"></a><span data-ttu-id="fa963-146">Установка пороговых значений и предупреждений для публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="fa963-146">Set thresholds and warnings for a merge publication</span></span>  
  
1.  <span data-ttu-id="fa963-147">Раскройте на левой панели группу издателей, раскройте издатель и выберите нужную публикацию.</span><span class="sxs-lookup"><span data-stu-id="fa963-147">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="fa963-148">Перейдите на вкладку **предупреждения** . Чтобы просмотреть дополнительные сведения о параметрах на этой вкладке, нажмите кнопку **Справка** в строке меню.</span><span class="sxs-lookup"><span data-stu-id="fa963-148">Click the **Warnings** tab. To view more information about the options on this tab, click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="fa963-149">Включите нужное предупреждение, установив соответствующий флажок:</span><span class="sxs-lookup"><span data-stu-id="fa963-149">Enable a warning by selecting the appropriate check box:</span></span>  
  
    -   <span data-ttu-id="fa963-150">**Предупреждать, если действие подписки истекает до порогового значения**</span><span class="sxs-lookup"><span data-stu-id="fa963-150">**Warn if a subscription will expire within the threshold**</span></span>  
  
    -   <span data-ttu-id="fa963-151">**Предупреждать при превышении порогового значения длины слияния для удаленных соединений.**</span><span class="sxs-lookup"><span data-stu-id="fa963-151">**Warn if a merge length for dialup connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="fa963-152">**Предупреждать при превышении порогового значения длины слияния для соединений по локальной сети.**</span><span class="sxs-lookup"><span data-stu-id="fa963-152">**Warn if a merge length for LAN connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="fa963-153">**Предупреждать, если число строк слияния в секунду снижается ниже порогового значения для соединений по локальной сети.**</span><span class="sxs-lookup"><span data-stu-id="fa963-153">**Warn if rows merged per second for LAN connections is less than the threshold**</span></span>  
  
    -   <span data-ttu-id="fa963-154">**Предупреждать, если число строк слияния в секунду снижается ниже порогового значения для удаленных соединений.**</span><span class="sxs-lookup"><span data-stu-id="fa963-154">**Warn if rows merged per second for dialup connections is less than the threshold**</span></span>  
  
4.  <span data-ttu-id="fa963-155">Установите пороговые значения для предупреждений в столбце **Порог** .</span><span class="sxs-lookup"><span data-stu-id="fa963-155">Set thresholds for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="fa963-156">Например если на шаге 3 установлен флажок **Предупреждать при превышении порогового значения длины слияния для удаленных соединений** , то в столбце **Порог** можно выбрать **10 минут** .</span><span class="sxs-lookup"><span data-stu-id="fa963-156">For example, if you selected **Warn if a merge length for dialup connections exceeds the threshold** in step 3, you could select a time of **10 minutes** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="fa963-157">Щелкните **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="fa963-157">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="fa963-158">Настройка предупреждений для пороговых значений</span><span class="sxs-lookup"><span data-stu-id="fa963-158">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="fa963-159">Щелкните **Настройка предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="fa963-159">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="fa963-160">В диалоговом окне **Настройка предупреждений репликации** выберите необходимое предупреждение, а затем щелкните **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="fa963-160">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="fa963-161">Это диалоговое окно отображает предупреждения для всех типов публикаций, включая предупреждения, не связанные с наблюдаемыми пороговыми значениями.</span><span class="sxs-lookup"><span data-stu-id="fa963-161">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span>  
  
3.  <span data-ttu-id="fa963-162">Задайте следующие параметры в диалоговом окне **\<AlertName> свойств предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="fa963-162">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="fa963-163">На странице **Общие** щелкните **Включить**, укажите базу данных, к которой нужно применить данное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="fa963-163">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="fa963-164">На странице **Ответ** укажите, надо ли отправить оповещение по электронной почте и/или запустить задание.</span><span class="sxs-lookup"><span data-stu-id="fa963-164">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="fa963-165">На странице **Параметры** измените текст ответа.</span><span class="sxs-lookup"><span data-stu-id="fa963-165">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="fa963-166">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fa963-166">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-snapshot-publication"></a><a name="Snapshot"></a><span data-ttu-id="fa963-167">Установка пороговых значений и предупреждений для публикации моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="fa963-167">Set thresholds and warnings for a snapshot publication</span></span>  
  
1.  <span data-ttu-id="fa963-168">Раскройте на левой панели группу издателей, раскройте издатель и выберите нужную публикацию.</span><span class="sxs-lookup"><span data-stu-id="fa963-168">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="fa963-169">Перейдите на вкладку **предупреждения** . Чтобы просмотреть дополнительные сведения о параметрах на этой вкладке, щелкните **Справка** в верхнем меню.</span><span class="sxs-lookup"><span data-stu-id="fa963-169">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the top menu.</span></span>  
  
3.  <span data-ttu-id="fa963-170">Включите предупреждение, установив флажок **Предупреждать, если действие подписки истекает до порогового значения**.</span><span class="sxs-lookup"><span data-stu-id="fa963-170">Enable a warning by selecting the check box **Warn if a subscription will expire within the threshold**.</span></span>  
  
4.  <span data-ttu-id="fa963-171">Установите пороговое значение для предупреждения в столбце **Порог** .</span><span class="sxs-lookup"><span data-stu-id="fa963-171">Set a threshold for the warning in the **Threshold** column.</span></span> <span data-ttu-id="fa963-172">Например, можно выбрать значение **70%** в столбце **Порог** .</span><span class="sxs-lookup"><span data-stu-id="fa963-172">For example, you could select a value of **70%** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="fa963-173">Щелкните **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="fa963-173">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="fa963-174">Настройка предупреждений для пороговых значений</span><span class="sxs-lookup"><span data-stu-id="fa963-174">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="fa963-175">Щелкните **Настройка предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="fa963-175">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="fa963-176">В диалоговом окне **Настройка предупреждений репликации** выберите необходимое предупреждение, а затем щелкните **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="fa963-176">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="fa963-177">Это диалоговое окно отображает предупреждения для всех типов публикаций, включая предупреждения, не связанные с наблюдаемыми пороговыми значениями.</span><span class="sxs-lookup"><span data-stu-id="fa963-177">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="fa963-178">Дополнительные сведения см. в статье [Использование предупреждений для событий агента репликации](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="fa963-178">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="fa963-179">Задайте следующие параметры в диалоговом окне **\<AlertName> свойств предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="fa963-179">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="fa963-180">На странице **Общие** щелкните **Включить**, укажите базу данных, к которой нужно применить данное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="fa963-180">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="fa963-181">На странице **Ответ** укажите, надо ли отправить оповещение по электронной почте и/или запустить задание.</span><span class="sxs-lookup"><span data-stu-id="fa963-181">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="fa963-182">На странице **Параметры** измените текст ответа.</span><span class="sxs-lookup"><span data-stu-id="fa963-182">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="fa963-183">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fa963-183">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa963-184">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa963-184">See Also</span></span>  
 [<span data-ttu-id="fa963-185">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="fa963-185">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
