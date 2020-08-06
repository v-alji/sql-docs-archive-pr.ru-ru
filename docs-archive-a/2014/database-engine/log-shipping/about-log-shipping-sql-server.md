---
title: Сведения о доставке журналов (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary servers [SQL Server]
- log shipping [SQL Server], jobs
- copy jobs [SQL Server]
- primary databases [SQL Server]
- log shipping [SQL Server], monitoring
- log shipping [SQL Server], about log shipping
- alert jobs [SQL Server]
- availability [SQL Server]
- jobs [SQL Server], log shipping
- monitor servers [SQL Server]
- restore jobs [SQL Server]
- log shipping [SQL Server]
- backup jobs [SQL Server]
- primary servers [SQL Server]
ms.assetid: 55da6b94-3a4b-4bae-850f-4bf7f6e918ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbf36e0ddd94ec0ab0a40a448e50602decfc0645
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730870"
---
# <a name="about-log-shipping-sql-server"></a><span data-ttu-id="41d80-102">Сведения о доставке журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-102">About Log Shipping (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="41d80-103">позволяет автоматически отправлять резервные копии журналов транзакций из *базы данных-источника* экземпляра *сервера-источника* в одну или более *баз данных-получателей* других экземпляров *сервера-получателя* .</span><span class="sxs-lookup"><span data-stu-id="41d80-103">Log shipping allows you to automatically send transaction log backups from a *primary database* on a *primary server* instance to one or more *secondary databases* on separate *secondary server* instances.</span></span> <span data-ttu-id="41d80-104">Резервные копии журналов транзакций применяются к каждой из баз данных-получателей индивидуально.</span><span class="sxs-lookup"><span data-stu-id="41d80-104">The transaction log backups are applied to each of the secondary databases individually.</span></span> <span data-ttu-id="41d80-105">Необязательный третий экземпляр сервера, известный как *сервер мониторинга*, ведет журнал и отслеживает состояние операций резервного копирования и восстановления и при необходимости выдает предупреждение, если в этих запланированных операциях происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="41d80-105">An optional third server instance, known as the *monitor server*, records the history and status of backup and restore operations and, optionally, raises alerts if these operations fail to occur as scheduled.</span></span>  
  
 <span data-ttu-id="41d80-106">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="41d80-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="41d80-107">Преимущества</span><span class="sxs-lookup"><span data-stu-id="41d80-107">Benefits</span></span>](#Benefits)  
  
-   [<span data-ttu-id="41d80-108">Термины и определения</span><span class="sxs-lookup"><span data-stu-id="41d80-108">Terms and Definitions</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="41d80-109">Общие сведения о доставке журналов</span><span class="sxs-lookup"><span data-stu-id="41d80-109">Log Shipping Overview</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="41d80-110">Совместимость</span><span class="sxs-lookup"><span data-stu-id="41d80-110">Interoperability</span></span>](#Interoperability)  
  
-   [<span data-ttu-id="41d80-111">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="41d80-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="41d80-112">Преимущества</span><span class="sxs-lookup"><span data-stu-id="41d80-112">Benefits</span></span>  
  
-   <span data-ttu-id="41d80-113">Предоставляет решение восстановления при аварии для одной базы данных-источника и одной или нескольких баз данных-получателей, каждая из которых расположена на отдельном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41d80-113">Provides a disaster-recovery solution for a single primary database and one or more secondary databases, each on a separate instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="41d80-114">Поддерживает ограниченный доступ только на чтение к базам данных-получателям (в перерывах между заданиями восстановления).</span><span class="sxs-lookup"><span data-stu-id="41d80-114">Supports limited read-only access to secondary databases (during the interval between restore jobs).</span></span>  
  
-   <span data-ttu-id="41d80-115">Позволяет пользователю задать задержку между моментом, когда сервер-источник создает резервную копию журнала базы данных-источника, и моментом, когда сервер-получатель должен восстановить (применить) резервную копию журнала.</span><span class="sxs-lookup"><span data-stu-id="41d80-115">Allows a user-specified delay between when the primary server backs up the log of the primary database and when the secondary servers must restore (apply) the log backup.</span></span> <span data-ttu-id="41d80-116">Большая задержка может быть полезной, например если данные в базе данных-источнике изменены случайно.</span><span class="sxs-lookup"><span data-stu-id="41d80-116">A longer delay can be useful, for example, if data is accidentally changed on the primary database.</span></span> <span data-ttu-id="41d80-117">Если случайное изменение будет замечено достаточно быстро, задержка позволит получить еще не измененные данные с базы данных-получателя до того, как изменения будут отражены в ней.</span><span class="sxs-lookup"><span data-stu-id="41d80-117">If the accidental change is noticed quickly, a delay can let you retrieve still unchanged data from a secondary database before the change is reflected there.</span></span>  
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="41d80-118">Термины и определения</span><span class="sxs-lookup"><span data-stu-id="41d80-118">Terms and Definitions</span></span>  
 <span data-ttu-id="41d80-119">сервера-источника</span><span class="sxs-lookup"><span data-stu-id="41d80-119">primary server</span></span>  
 <span data-ttu-id="41d80-120">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , являющийся рабочим сервером.</span><span class="sxs-lookup"><span data-stu-id="41d80-120">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is your production server.</span></span>  
  
 <span data-ttu-id="41d80-121">базы данных-источника</span><span class="sxs-lookup"><span data-stu-id="41d80-121">primary database</span></span>  
 <span data-ttu-id="41d80-122">База данных сервера-источника, резервную копию которой нужно создать на другом сервере.</span><span class="sxs-lookup"><span data-stu-id="41d80-122">The database on the primary server that you want to back up to another server.</span></span> <span data-ttu-id="41d80-123">Все администрирование конфигурации доставки журналов через среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] производится на базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="41d80-123">All administration of the log shipping configuration through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is performed from the primary database.</span></span>  
  
 <span data-ttu-id="41d80-124">сервера-получателя</span><span class="sxs-lookup"><span data-stu-id="41d80-124">secondary server</span></span>  
 <span data-ttu-id="41d80-125">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором нужно хранить «горячую» копию базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="41d80-125">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where you want to keep a warm standby copy of your primary database.</span></span>  
  
 <span data-ttu-id="41d80-126">база данных-получатель</span><span class="sxs-lookup"><span data-stu-id="41d80-126">secondary database</span></span>  
 <span data-ttu-id="41d80-127">«Горячая» копия базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="41d80-127">The warm standby copy of the primary database.</span></span> <span data-ttu-id="41d80-128">База данных-получатель может находиться в состояниях RECOVERING или STANDBY, что означает, что она доступна в ограниченном режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="41d80-128">The secondary database may be in either the RECOVERING state or the STANDBY state, which leaves the database available for limited read-only access.</span></span>  
  
 <span data-ttu-id="41d80-129">сервер мониторинга</span><span class="sxs-lookup"><span data-stu-id="41d80-129">monitor server</span></span>  
 <span data-ttu-id="41d80-130">Необязательный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который отслеживает весь процесс доставки журналов, в том числе:</span><span class="sxs-lookup"><span data-stu-id="41d80-130">An optional instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that tracks all of the details of log shipping, including:</span></span>  
  
-   <span data-ttu-id="41d80-131">когда резервная копия журнала транзакций на базе данных-источнике была сохранена в последний раз;</span><span class="sxs-lookup"><span data-stu-id="41d80-131">When the transaction log on the primary database was last backed up.</span></span>  
  
-   <span data-ttu-id="41d80-132">когда серверы-получатели в последний раз копировали и восстанавливали файлы резервных копий;</span><span class="sxs-lookup"><span data-stu-id="41d80-132">When the secondary servers last copied and restored the backup files.</span></span>  
  
-   <span data-ttu-id="41d80-133">сведения о любых предупреждениях о сбоях.</span><span class="sxs-lookup"><span data-stu-id="41d80-133">Information about any backup failure alerts.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="41d80-134">После настройки сервера мониторинга конфигурацию доставки журналов нельзя изменить, не удалив предварительно доставку журналов.</span><span class="sxs-lookup"><span data-stu-id="41d80-134">Once the monitor server has been configured, it cannot be changed without removing log shipping first.</span></span>  
  
 <span data-ttu-id="41d80-135">задание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="41d80-135">backup job</span></span>  
 <span data-ttu-id="41d80-136">Задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которое выполняет операцию резервного копирования, ведет журнал на локальном сервере и на сервере мониторинга и удаляет старые файлы резервных копий и записи своего журнала.</span><span class="sxs-lookup"><span data-stu-id="41d80-136">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that  performs the backup operation, logs history to the local server and the monitor server, and deletes old backup files and history information.</span></span> <span data-ttu-id="41d80-137">При включении доставки журналов на экземпляре сервера-источника создается задание категории «Резервное копирование доставки журналов».</span><span class="sxs-lookup"><span data-stu-id="41d80-137">When log shipping is enabled, the job category "Log Shipping Backup" is created on the primary server instance.</span></span>  
  
 <span data-ttu-id="41d80-138">задание копирования</span><span class="sxs-lookup"><span data-stu-id="41d80-138">copy job</span></span>  
 <span data-ttu-id="41d80-139">Задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которое копирует файлы резервных копий журналов с сервера-источника на указанный сервер-получатель, ведет журнал на сервере-получателе и сервере мониторинга.</span><span class="sxs-lookup"><span data-stu-id="41d80-139">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that copies the backup files from the primary server to a configurable destination on the secondary server and logs history on the secondary server and the monitor server.</span></span> <span data-ttu-id="41d80-140">При включении доставки журналов в базе данных на каждом сервере-получателе в конфигурации доставки журналов создается задание категории «Копирование доставки журналов».</span><span class="sxs-lookup"><span data-stu-id="41d80-140">When log shipping is enabled on a database, the job category "Log Shipping Copy" is created on each secondary server in a log shipping configuration.</span></span>  
  
 <span data-ttu-id="41d80-141">задание восстановления</span><span class="sxs-lookup"><span data-stu-id="41d80-141">restore job</span></span>  
 <span data-ttu-id="41d80-142">Задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которое восстанавливает резервные копии журналов в базах данных-получателях.</span><span class="sxs-lookup"><span data-stu-id="41d80-142">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that restores the copied backup files to the secondary databases.</span></span> <span data-ttu-id="41d80-143">Оно ведет журнал на локальном сервере и на сервере мониторинга и удаляет старые файлы и записи своего журнала.</span><span class="sxs-lookup"><span data-stu-id="41d80-143">It logs history on the local server and the monitor server, and deletes old files and old history information.</span></span> <span data-ttu-id="41d80-144">При включении доставки журналов для базы данных на экземпляре сервера-получателя создается задание категории «Восстановление доставки журналов».</span><span class="sxs-lookup"><span data-stu-id="41d80-144">When log shipping is enabled on a database, the job category "Log Shipping Restore" is created on the secondary server instance.</span></span>  
  
 <span data-ttu-id="41d80-145">задание предупреждения</span><span class="sxs-lookup"><span data-stu-id="41d80-145">alert job</span></span>  
 <span data-ttu-id="41d80-146">Задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которое создает предупреждения для баз данных-источников и получателей, если операции резервного копирования или восстановления не были завершены успешно в течение указанного срока.</span><span class="sxs-lookup"><span data-stu-id="41d80-146">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that raises alerts for primary and secondary databases when a backup or restore operation does not complete successfully within a specified threshold.</span></span> <span data-ttu-id="41d80-147">Если в базе данных включена доставка журналов, на экземпляре сервера мониторинга создается задание категории «Предупреждение доставки журналов».</span><span class="sxs-lookup"><span data-stu-id="41d80-147">When log shipping is enabled on a database, job category "Log Shipping Alert" is created on the monitor server instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="41d80-148">Для каждого предупреждения необходимо задать номер.</span><span class="sxs-lookup"><span data-stu-id="41d80-148">For each alert, you need to specify an alert number.</span></span> <span data-ttu-id="41d80-149">Также необходимо настроить предупреждение для оповещения оператора при появлении этого предупреждения.</span><span class="sxs-lookup"><span data-stu-id="41d80-149">Also, be sure to configure the alert to notify an operator when an alert is raised.</span></span>  
  
##  <a name="log-shipping-overview"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="41d80-150">Общие сведения о доставке журналов</span><span class="sxs-lookup"><span data-stu-id="41d80-150">Log Shipping Overview</span></span>  
 <span data-ttu-id="41d80-151">Доставка журналов состоит из этих трех операций:</span><span class="sxs-lookup"><span data-stu-id="41d80-151">Log shipping consists of three operations:</span></span>  
  
1.  <span data-ttu-id="41d80-152">резервное копирование журнала транзакций на экземпляре сервера-источника;</span><span class="sxs-lookup"><span data-stu-id="41d80-152">Back up the transaction log at the primary server instance.</span></span>  
  
2.  <span data-ttu-id="41d80-153">копирование резервных копий журнала транзакций на экземпляр сервера-получателя;</span><span class="sxs-lookup"><span data-stu-id="41d80-153">Copy the transaction log file to the secondary server instance.</span></span>  
  
3.  <span data-ttu-id="41d80-154">восстановление из резервных копий журнала транзакций на экземпляре сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="41d80-154">Restore the log backup on the secondary server instance.</span></span>  
  
 <span data-ttu-id="41d80-155">Журнал может доставляться нескольким экземплярам серверов-получателей.</span><span class="sxs-lookup"><span data-stu-id="41d80-155">The log can be shipped to multiple secondary server instances.</span></span> <span data-ttu-id="41d80-156">В этих случаях операции 2 и 3 повторяются для каждого экземпляра сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="41d80-156">In such cases, operations 2 and 3 are duplicated for each secondary server instance.</span></span>  
  
 <span data-ttu-id="41d80-157">Конфигурация доставки журналов не позволяет автоматически переходить с сервера-источника на сервер-получатель.</span><span class="sxs-lookup"><span data-stu-id="41d80-157">A log shipping configuration does not automatically fail over from the primary server to the secondary server.</span></span> <span data-ttu-id="41d80-158">Если база данных-источник становится недоступна, любой из серверов-получателей может быть вручную переведен в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="41d80-158">If the primary database becomes unavailable, any of the secondary databases can be brought online manually.</span></span>  
  
 <span data-ttu-id="41d80-159">Сервер-получатель можно использовать для построения отчетов.</span><span class="sxs-lookup"><span data-stu-id="41d80-159">You can use a secondary database for reporting purposes.</span></span>  
  
 <span data-ttu-id="41d80-160">Кроме того, можно настроить предупреждения в конфигурации доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="41d80-160">In addition, you can configure alerts for your log shipping configuration.</span></span>  
  
### <a name="a-typical-log-shipping-configuration"></a><span data-ttu-id="41d80-161">Типичная конфигурация доставки журналов</span><span class="sxs-lookup"><span data-stu-id="41d80-161">A Typical Log Shipping Configuration</span></span>  
 <span data-ttu-id="41d80-162">Следующий рисунок показывает конфигурацию доставки журналов с экземпляром сервера-источника, тремя экземплярами сервера-получателя и экземпляром сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="41d80-162">The following figure shows a log shipping configuration with the primary server instance, three secondary server instances, and a monitor server instance.</span></span> <span data-ttu-id="41d80-163">Рисунок отображает шаги, выполняемые задачами резервного копирования, копирования и восстановления, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41d80-163">The figure illustrates the steps performed by backup, copy, and restorejobs, as follows:</span></span>  
  
1.  <span data-ttu-id="41d80-164">экземпляр сервера-источника запускает задачу резервного копирования, чтобы создать резервную копию журнала транзакций в базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="41d80-164">The primary server instance runs the backup job to back up the transaction log on the primary database.</span></span> <span data-ttu-id="41d80-165">Затем этот экземпляр сервера размещает резервную копию журнала в первичный файл резервной копии журнала, который сохраняется в папке резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="41d80-165">This server instance then places the log backup into a primary log-backup file, which it sends to the backup folder.</span></span>  <span data-ttu-id="41d80-166">На данном рисунке папка резервного копирования находится в общедоступном каталоге — *общем каталоге резервных копий*.</span><span class="sxs-lookup"><span data-stu-id="41d80-166">In this figure, the backup folder is on a shared directory-the *backup share*.</span></span>  
  
2.  <span data-ttu-id="41d80-167">каждый из трех экземпляров сервера-получателя выполняет задачу копирования файла-источника резервной копии журнала в его локальную целевую папку;</span><span class="sxs-lookup"><span data-stu-id="41d80-167">Each of the three secondary server instances runs its own copy job to copy the primary log-backup file to its own local destination folder.</span></span>  
  
3.  <span data-ttu-id="41d80-168">каждый экземпляр сервера-получателя запускает собственную задачу восстановления резервной копии журналов из локальной целевой папки в локальную базу данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="41d80-168">Each secondary server instance runs its own restore job to restore the log backup from the local destination folder onto the local secondary database.</span></span>  
  
 <span data-ttu-id="41d80-169">Экземпляры сервера-источника и сервера-получателя посылают собственный журнал и состояние экземпляру сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="41d80-169">The primary and secondary server instances send their own history and status to the monitor server instance.</span></span>  
  
 <span data-ttu-id="41d80-170">![Конфигурация с отображением заданий резервного копирования, копирования и восстановления](../media/ls-typical-configuration.gif "Конфигурация с отображением заданий резервного копирования, копирования и восстановления")</span><span class="sxs-lookup"><span data-stu-id="41d80-170">![Configuration showing backup, copy, & restore jobs](../media/ls-typical-configuration.gif "Configuration showing backup, copy, & restore jobs")</span></span>  
  
##  <a name="interoperability"></a><a name="Interoperability"></a> <span data-ttu-id="41d80-171">Совместимость</span><span class="sxs-lookup"><span data-stu-id="41d80-171">Interoperability</span></span>  
 <span data-ttu-id="41d80-172">Доставка журналов может использоваться вместе со следующими функциями и компонентами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41d80-172">Log shipping can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="41d80-173">Необходимые условия для перехода с доставки журналов на группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="41d80-173">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
-   [<span data-ttu-id="41d80-174">Зеркальное отображение баз данных и доставка журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-174">Database Mirroring and Log Shipping &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="41d80-175">Репликация и доставка журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-175">Log Shipping and Replication &#40;SQL Server&#41;</span></span>](log-shipping-and-replication-sql-server.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] <span data-ttu-id="41d80-176">и зеркальное отображение баз данных являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="41d80-176">and database mirroring are mutually exclusive.</span></span> <span data-ttu-id="41d80-177">База данных, в которой настроена одна из этих функций, не может использоваться в другой функции.</span><span class="sxs-lookup"><span data-stu-id="41d80-177">A database that is configured for one of these features cannot be configured for the other.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="41d80-178">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="41d80-178">Related Tasks</span></span>  
  
-   [<span data-ttu-id="41d80-179">Обновление доставки журналов до SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="41d80-179">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="41d80-180">Настройка доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-180">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="41d80-181">Добавление базы данных-получателя в конфигурацию доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-181">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="41d80-182">Удаление базы данных-получателя из конфигурации доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-182">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="41d80-183">Удаление доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-183">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="41d80-184">Просмотр отчета о доставке журналов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="41d80-184">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="41d80-185">Наблюдение за доставкой журналов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="41d80-185">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="41d80-186">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-186">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="41d80-187">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-187">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="41d80-188">Управление именами входа и заданиями после переключения ролей (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d80-188">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="41d80-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="41d80-189">See Also</span></span>  
 [<span data-ttu-id="41d80-190">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="41d80-190">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)  
  
  
