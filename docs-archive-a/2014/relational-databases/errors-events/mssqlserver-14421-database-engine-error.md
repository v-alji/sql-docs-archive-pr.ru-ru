---
title: MSSQLSERVER_14421 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14421 (Database Engine error)
ms.assetid: 03e76d4a-d463-4673-8843-08e4ecaefe27
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d6bc793911797c334d87238ec46531f7afbf63ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667174"
---
# <a name="mssqlserver_14421"></a><span data-ttu-id="f991e-102">MSSQLSERVER_14421</span><span class="sxs-lookup"><span data-stu-id="f991e-102">MSSQLSERVER_14421</span></span>
    
## <a name="details"></a><span data-ttu-id="f991e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="f991e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f991e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="f991e-104">Product Name</span></span>|<span data-ttu-id="f991e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f991e-105">SQL Server</span></span>|  
|<span data-ttu-id="f991e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f991e-106">Event ID</span></span>|<span data-ttu-id="f991e-107">14421</span><span class="sxs-lookup"><span data-stu-id="f991e-107">14421</span></span>|  
|<span data-ttu-id="f991e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="f991e-108">Event Source</span></span>|<span data-ttu-id="f991e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f991e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f991e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="f991e-110">Component</span></span>|<span data-ttu-id="f991e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f991e-111">SQLEngine</span></span>|  
|<span data-ttu-id="f991e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="f991e-112">Symbolic Name</span></span>|<span data-ttu-id="f991e-113">SQLErrorNum14421</span><span class="sxs-lookup"><span data-stu-id="f991e-113">SQLErrorNum14421</span></span>|  
|<span data-ttu-id="f991e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="f991e-114">Message Text</span></span>|<span data-ttu-id="f991e-115">Для базы данных-получателя в конфигурации доставки журналов %s.%s установлен порог резервного копирования %d минут, нарушена синхронизация.   Восстановление не проводилось в течение %d минут.</span><span class="sxs-lookup"><span data-stu-id="f991e-115">The log shipping secondary database %s.%s has restore threshold of %d minutes and is out of sync. No restore was performed for %d minutes.</span></span> <span data-ttu-id="f991e-116">Задержка восстановления равна %d минутам.</span><span class="sxs-lookup"><span data-stu-id="f991e-116">Restored latency is %d minutes.</span></span> <span data-ttu-id="f991e-117">Проверьте журнал агента и сведения монитора доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="f991e-117">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f991e-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="f991e-118">Explanation</span></span>  
 <span data-ttu-id="f991e-119">Это сообщение указывает, что доставка журналов не синхронизирована за порогом восстановления.</span><span class="sxs-lookup"><span data-stu-id="f991e-119">This message indicates that log shipping is out of synchronization beyond the restore threshold.</span></span> <span data-ttu-id="f991e-120">Порог восстановления определяется как число минут, которое может пройти между операциями восстановления до того, как будет сформировано сообщение.</span><span class="sxs-lookup"><span data-stu-id="f991e-120">The restore threshold is the number of minutes that can elapse between restore operations before a message is generated.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="f991e-121">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="f991e-121">Possible Causes</span></span>  
 <span data-ttu-id="f991e-122">Это сообщение не обязательно свидетельствует о проблеме с доставкой журналов.</span><span class="sxs-lookup"><span data-stu-id="f991e-122">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="f991e-123">Оно может указывать на одну из следующих неполадок.</span><span class="sxs-lookup"><span data-stu-id="f991e-123">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="f991e-124">Задание восстановления не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f991e-124">The restore job is not running.</span></span>  
  
     <span data-ttu-id="f991e-125">Возможные причины: служба агента SQL Server на экземпляре сервера-получателя не работает, задание отключено, или было изменено расписание задания.</span><span class="sxs-lookup"><span data-stu-id="f991e-125">Possible causes of the job not running include the following: the SQL Server Agent service on the secondary server instance is not running, the job is disabled, or the schedule of the job has been changed.</span></span>  
  
-   <span data-ttu-id="f991e-126">Ошибка задания восстановления.</span><span class="sxs-lookup"><span data-stu-id="f991e-126">The restore job is failing.</span></span>  
  
     <span data-ttu-id="f991e-127">Возможные причины: неправильный путь к папке восстановления, диск заполнен или любая другая причина, из-за которой инструкция RESTORE может завершиться неуспешно.</span><span class="sxs-lookup"><span data-stu-id="f991e-127">Possible causes of the job failing include the following: the restore folder path is not valid, the disk is full, or any other reason that the RESTORE statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f991e-128">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="f991e-128">User Action</span></span>  
 <span data-ttu-id="f991e-129">Чтобы устранить неполадку, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="f991e-129">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="f991e-130">Удостоверьтесь, что служба «агент SQL Server» на экземпляре сервера-получателя работает, и что задание восстановления в базе данных-получателе включено и выполняется по расписанию с подходящей частотой.</span><span class="sxs-lookup"><span data-stu-id="f991e-130">Make sure that the SQL Server Agent service is running for the secondary server instance and that the restore job for this secondary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="f991e-131">Возможно, произошла ошибка задания восстановления на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="f991e-131">The restore job on the secondary server might be failing.</span></span> <span data-ttu-id="f991e-132">В этом случае проверьте журнал заданий восстановления, чтобы попытаться найти ошибку.</span><span class="sxs-lookup"><span data-stu-id="f991e-132">In this case, check the job history for the restore job to look for the cause.</span></span>  
  
-   <span data-ttu-id="f991e-133">Заданию восстановления доставки журналов, выполняющемуся на экземпляре сервера-получателя, не удается подключиться к экземпляру сервера мониторинга для обновления таблицы **log_shipping_monitor_secondary**.</span><span class="sxs-lookup"><span data-stu-id="f991e-133">The log shipping restore job, which runs on the secondary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_secondary** table.</span></span> <span data-ttu-id="f991e-134">Причиной этого может быть проблема проверки подлинности между экземпляром сервера мониторинга и экземпляром сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="f991e-134">This might be caused by an authentication problem between the monitor server instance and the secondary server instance.</span></span>  
  
-   <span data-ttu-id="f991e-135">Неправильное пороговое значение предупреждения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f991e-135">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="f991e-136">В идеальном случае это значение должно быть минимум в три раза больше частоты запуска задания восстановления.</span><span class="sxs-lookup"><span data-stu-id="f991e-136">Ideally, this value is set to at least three times the frequency of the restore job.</span></span> <span data-ttu-id="f991e-137">Если частота запуска задания восстановления изменяется после настройки доставки журналов, когда она уже успешно работает, необходимо соответствующим образом обновить пороговое значение предупреждения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f991e-137">If you change the frequency of the restore job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="f991e-138">Когда экземпляр сервера мониторинга переходит в режим "вне сети", а затем снова в режим "в сети", в таблице **log_shipping_monitor_secondary** не отображаются текущие значения до тех пор, пока не будет выполнено задание предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f991e-138">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_secondary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="f991e-139">Ошибка 14421 может произойти после успешного завершения задания восстановления с сообщением «Не удалось найти файл резервной копии журнала, который можно использовать для базы данных-получателя».</span><span class="sxs-lookup"><span data-stu-id="f991e-139">Error 14421 can be raised when a restore job succeeds with, "Could not find a log backup file that could be applied to secondary database."</span></span> <span data-ttu-id="f991e-140">В этом случае время восстановления не обновляется.</span><span class="sxs-lookup"><span data-stu-id="f991e-140">When this occurs, the restore time is not updated.</span></span> <span data-ttu-id="f991e-141">Причиной ошибки в этом случае может быть проблема, связанная с заданием копирования.</span><span class="sxs-lookup"><span data-stu-id="f991e-141">The cause of the error in this case might be an issue with the copy job.</span></span>  
  
     <span data-ttu-id="f991e-142">Чтобы таблицы мониторинга получили новейшие данные из базы данных-получателя, выполните процедуру **sp_refresh_log_shipping_monitor** на экземпляре сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="f991e-142">To update the monitor tables with the latest data for the secondary database, run **sp_refresh_log_shipping_monitor** on the secondary server instance.</span></span>  
  
-   <span data-ttu-id="f991e-143">На экземпляре сервера-получателя или сервера мониторинга установлена неправильная дата или время.</span><span class="sxs-lookup"><span data-stu-id="f991e-143">On the secondary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="f991e-144">При этом также могут формироваться предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f991e-144">This may also generate alert messages.</span></span> <span data-ttu-id="f991e-145">Вероятно, была изменена системная дата или время на одном из этих серверов.</span><span class="sxs-lookup"><span data-stu-id="f991e-145">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f991e-146">Разные часовые пояса на двух экземплярах серверов не должны быть причиной проблемы.</span><span class="sxs-lookup"><span data-stu-id="f991e-146">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f991e-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="f991e-147">See Also</span></span>  
 <span data-ttu-id="f991e-148">[log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f991e-148">[log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="f991e-149">[Сведения о доставке журналов (SQL Server)](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f991e-149">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="f991e-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f991e-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="f991e-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f991e-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="f991e-152">Сведения о доставке журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f991e-152">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
