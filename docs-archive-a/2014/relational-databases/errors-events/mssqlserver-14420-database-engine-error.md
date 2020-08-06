---
title: MSSQLSERVER_14420 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14420 (Database Engine error)
ms.assetid: 4a1d72b1-ab1b-4119-a11b-a8a05c6fdb45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7a17ab1e2281530b06c9ad27ac2a31672de0681e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657810"
---
# <a name="mssqlserver_14420"></a><span data-ttu-id="7cff6-102">MSSQLSERVER_14420</span><span class="sxs-lookup"><span data-stu-id="7cff6-102">MSSQLSERVER_14420</span></span>
    
## <a name="details"></a><span data-ttu-id="7cff6-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7cff6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7cff6-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7cff6-104">Product Name</span></span>|<span data-ttu-id="7cff6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7cff6-105">SQL Server</span></span>|  
|<span data-ttu-id="7cff6-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7cff6-106">Event ID</span></span>|<span data-ttu-id="7cff6-107">14420</span><span class="sxs-lookup"><span data-stu-id="7cff6-107">14420</span></span>|  
|<span data-ttu-id="7cff6-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7cff6-108">Event Source</span></span>|<span data-ttu-id="7cff6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7cff6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7cff6-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7cff6-110">Component</span></span>|<span data-ttu-id="7cff6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7cff6-111">SQLEngine</span></span>|  
|<span data-ttu-id="7cff6-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7cff6-112">Symbolic Name</span></span>|<span data-ttu-id="7cff6-113">SQLErrorNum14420</span><span class="sxs-lookup"><span data-stu-id="7cff6-113">SQLErrorNum14420</span></span>|  
|<span data-ttu-id="7cff6-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7cff6-114">Message Text</span></span>|<span data-ttu-id="7cff6-115">Для базы данных-источника доставки журналов %s.%s установлен порог восстановления, равный %d минутам, операция резервного копирования журналов не выполнялась в течение %d минут.</span><span class="sxs-lookup"><span data-stu-id="7cff6-115">The log shipping primary database %s.%s has backup threshold of %d minutes and has not performed a backup log operation for %d minutes.</span></span> <span data-ttu-id="7cff6-116">Проверьте журнал агента и сведения монитора доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="7cff6-116">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7cff6-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7cff6-117">Explanation</span></span>  
 <span data-ttu-id="7cff6-118">Доставка журналов не синхронизирована за порогом резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7cff6-118">Log shipping is out of synchronization beyond the backup threshold.</span></span> <span data-ttu-id="7cff6-119">Порог резервного копирования определяется как число минут, которое может пройти между заданиями резервного копирования доставки журналов до того, как будет сформировано сообщение.</span><span class="sxs-lookup"><span data-stu-id="7cff6-119">The backup threshold is the number of minutes that are allowed to elapse between log-shipping backup jobs before an alert is generated.</span></span> <span data-ttu-id="7cff6-120">Это сообщение не обязательно свидетельствует о проблеме с доставкой журналов.</span><span class="sxs-lookup"><span data-stu-id="7cff6-120">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="7cff6-121">Оно может указывать на одну из следующих неполадок.</span><span class="sxs-lookup"><span data-stu-id="7cff6-121">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="7cff6-122">Задание резервного копирования не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7cff6-122">The backup job is not running.</span></span> <span data-ttu-id="7cff6-123">Возможные причины: служба агента SQL Server на экземпляре сервера-источника не работает, задание отключено, или было изменено расписание задания.</span><span class="sxs-lookup"><span data-stu-id="7cff6-123">Possible causes for this include the following: the SQL Server Agent service on the primary server instance is not running, the job is disabled, or the job's schedule has been changed.</span></span>  
  
-   <span data-ttu-id="7cff6-124">Ошибка задания резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7cff6-124">The backup job is failing.</span></span> <span data-ttu-id="7cff6-125">Возможные причины: неправильный путь к папке резервного копирования, диск заполнен или любая другая причина, из-за которой инструкция BACKUP может завершиться неуспешно.</span><span class="sxs-lookup"><span data-stu-id="7cff6-125">Possible causes for this include the following: the backup folder path is not valid, the disk is full, or any other reason that the BACKUP statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7cff6-126">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7cff6-126">User Action</span></span>  
 <span data-ttu-id="7cff6-127">Чтобы устранить неполадку, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="7cff6-127">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="7cff6-128">Удостоверьтесь, что служба «агент SQL Server» на экземпляре сервера-источника работает, и что задание резервного копирования в базе данных-источнике включено и выполняется по расписанию с подходящей частотой.</span><span class="sxs-lookup"><span data-stu-id="7cff6-128">Make sure that the SQL Server Agent service is running for the primary server instance and that the backup job for this primary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="7cff6-129">Возможно, произошла ошибка задания резервного копирования на сервере-источнике.</span><span class="sxs-lookup"><span data-stu-id="7cff6-129">The backup job on the primary server might be failing.</span></span> <span data-ttu-id="7cff6-130">В этом случае проверьте журнал заданий резервного копирования, чтобы попытаться найти ошибку.</span><span class="sxs-lookup"><span data-stu-id="7cff6-130">In this case, examine the job history for the backup job to look for the cause.</span></span>  
  
-   <span data-ttu-id="7cff6-131">Возможно, заданию резервного копирования доставки журналов, выполняющемуся на экземпляре сервера-источника, не удается подключиться к экземпляру сервера мониторинга для обновления таблицы **log_shipping_monitor_primary**.</span><span class="sxs-lookup"><span data-stu-id="7cff6-131">The log shipping backup job, which runs on the primary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_primary** table.</span></span> <span data-ttu-id="7cff6-132">Причиной этого может быть проблема проверки подлинности между экземпляром сервера мониторинга и экземпляром сервера-источника.</span><span class="sxs-lookup"><span data-stu-id="7cff6-132">This could be caused by an authentication problem between the monitor server instance and the primary server instance.</span></span>  
  
-   <span data-ttu-id="7cff6-133">Неправильное пороговое значение предупреждения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7cff6-133">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="7cff6-134">В идеальном случае это значение должно быть минимум в три раза больше частоты запуска задания резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7cff6-134">Ideally, this value is set to at least three times the frequency of the backup job.</span></span> <span data-ttu-id="7cff6-135">Если частота запуска задания резервного копирования изменяется после настройки доставки журналов, когда она уже успешно работает, необходимо соответствующим образом обновить пороговое значение предупреждения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7cff6-135">If you change the frequency of the backup job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="7cff6-136">Если экземпляр сервера мониторинга переходит в режим "вне сети", а затем снова в режим "в сети", в таблице **log_shipping_monitor_primary** не отображаются текущие значения до тех пор, пока не будет выполнено задание предупреждения.</span><span class="sxs-lookup"><span data-stu-id="7cff6-136">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_primary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="7cff6-137">Чтобы таблицы мониторинга получили новейшие данные из базы данных-источника, выполните процедуру **sp_refresh_log_shipping_monitor** на экземпляре сервера-источника.</span><span class="sxs-lookup"><span data-stu-id="7cff6-137">To update the monitor tables with the latest data for the primary database, run **sp_refresh_log_shipping_monitor** on the primary server instance.</span></span>  
  
-   <span data-ttu-id="7cff6-138">На экземпляре сервера-источника или сервера мониторинга установлена неправильная дата или время.</span><span class="sxs-lookup"><span data-stu-id="7cff6-138">On the primary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="7cff6-139">При этом также могут формироваться предупреждения.</span><span class="sxs-lookup"><span data-stu-id="7cff6-139">This may also generate alert messages.</span></span> <span data-ttu-id="7cff6-140">Вероятно, была изменена системная дата или время на одном из этих серверов.</span><span class="sxs-lookup"><span data-stu-id="7cff6-140">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7cff6-141">Разные часовые пояса на двух экземплярах серверов не должны быть причиной проблемы.</span><span class="sxs-lookup"><span data-stu-id="7cff6-141">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cff6-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="7cff6-142">See Also</span></span>  
 <span data-ttu-id="7cff6-143">[log_shipping_monitor_primary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-primary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7cff6-143">[log_shipping_monitor_primary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-primary-transact-sql) </span></span>  
 <span data-ttu-id="7cff6-144">[Сведения о доставке журналов (SQL Server)](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7cff6-144">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="7cff6-145">[sp_help_log_shipping_monitor_primary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-primary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7cff6-145">[sp_help_log_shipping_monitor_primary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-primary-transact-sql) </span></span>  
 <span data-ttu-id="7cff6-146">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7cff6-146">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="7cff6-147">Сведения о доставке журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7cff6-147">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
