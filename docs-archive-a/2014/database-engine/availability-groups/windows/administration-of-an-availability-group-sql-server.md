---
title: Администрирование группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], managing
ms.assetid: 0b7542fa-235e-413d-81bf-3eff9ee07480
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2cac9a34fe71c11f71ec47bbb6d690199869fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655969"
---
# <a name="administration-of-an-availability-group-sql-server"></a><span data-ttu-id="31670-102">Администрирование группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-102">Administration of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="31670-103">Управление существующей группой доступности AlwaysOn в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] включает в себя одну или несколько следующих задач.</span><span class="sxs-lookup"><span data-stu-id="31670-103">Managing an existing AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] involves one or more of the following tasks:</span></span>  
  
-   <span data-ttu-id="31670-104">Изменение свойств существующей реплики доступности, например для изменения клиентского доступа к соединению (для настройки вторичных реплик, доступных для чтения), изменение режима отработки отказа, режима доступности или задание времени ожидания сеанса.</span><span class="sxs-lookup"><span data-stu-id="31670-104">Altering the properties of an existing availability replica, for example to change client connection access (for configuring readable secondary replicas), changing its failover mode, availability mode, or session timeout setting.</span></span>  
  
-   <span data-ttu-id="31670-105">Добавление или удаление вторичных реплик.</span><span class="sxs-lookup"><span data-stu-id="31670-105">Adding or removing secondary replicas.</span></span>  
  
-   <span data-ttu-id="31670-106">Добавление или удаление базы данных.</span><span class="sxs-lookup"><span data-stu-id="31670-106">Adding or removing a database.</span></span>  
  
-   <span data-ttu-id="31670-107">Приостановка или возобновление работы базы данных.</span><span class="sxs-lookup"><span data-stu-id="31670-107">Suspending or resuming a database.</span></span>  
  
-   <span data-ttu-id="31670-108">Выполнение запланированной отработки отказа вручную ( *отработка отказа вручную*) или принудительной отработки отказа вручную ( *принудительная отработка отказа*).</span><span class="sxs-lookup"><span data-stu-id="31670-108">Performing a planned manual failover (a *manual failover*) or a forced manual failover (a *forced failover*).</span></span>  
  
-   <span data-ttu-id="31670-109">Создание или настройка прослушивателя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="31670-109">Creating or configuring an availability group listener.</span></span>  
  
-   <span data-ttu-id="31670-110">Управление [доступными для чтения вторичными репликами](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) для данной группы доступности.</span><span class="sxs-lookup"><span data-stu-id="31670-110">Managing [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="31670-111">Необходимо настроить доступ для чтения для одной или нескольких реплик, выполняемых под вторичной ролью, и настроить маршрутизацию только для чтения.</span><span class="sxs-lookup"><span data-stu-id="31670-111">This involves configuring one or more replicas to read-only access when running under the secondary role, and configuring read-only routing.</span></span>  
  
-   <span data-ttu-id="31670-112">Управление [резервными копиями вторичных реплик](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) определенной группы доступности.</span><span class="sxs-lookup"><span data-stu-id="31670-112">Managing [backups on secondary replicas](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="31670-113">Необходимо настроить место выполнения задач по созданию резервных копий и написать скрипты для этих задач.</span><span class="sxs-lookup"><span data-stu-id="31670-113">This involves configuring where you prefer that backup jobs run and then scripting backup jobs to implement your backup preference.</span></span> <span data-ttu-id="31670-114">необходимо создать скрипты заданий резервного копирования для каждой базы данных в группе доступности на каждом экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором размещается реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="31670-114">you need to script backup jobs for every database in the availability group on every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica.</span></span>  
  
-   <span data-ttu-id="31670-115">Удаление группы доступности.</span><span class="sxs-lookup"><span data-stu-id="31670-115">Deleting an availability group.</span></span>  
  
-   <span data-ttu-id="31670-116">Миграция между кластерами групп доступности AlwaysOn для обновления ОС</span><span class="sxs-lookup"><span data-stu-id="31670-116">Cross-cluster migration of AlwaysOn Availability Groups for OS upgrade</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="31670-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="31670-117">Related Tasks</span></span>  
 <span data-ttu-id="31670-118">**Настройка существующей группы доступности**</span><span class="sxs-lookup"><span data-stu-id="31670-118">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="31670-119">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-119">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-120">Удаление вторичной реплики из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-120">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-121">Добавление базы данных в группу доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-121">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="31670-122">Удаление базы данных-получателя из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-122">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-123">Удаление базы данных-источника из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-123">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-124">Настройка гибкой политики отработки отказа для управления условиями автоматического перехода на другой ресурс &#40;группы доступности AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="31670-124">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover &#40;AlwaysOn Availability Groups&#41;</span></span>](configure-flexible-automatic-failover-policy.md)  
  
 <span data-ttu-id="31670-125">**Управление группой доступности**</span><span class="sxs-lookup"><span data-stu-id="31670-125">**To manage an availability group**</span></span>  
  
-   [<span data-ttu-id="31670-126">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="31670-127">Выполнение запланированного перехода на другой ресурс вручную для группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-127">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-128">Выполнение принудительного перехода на другой ресурс вручную для группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-128">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-129">Удаление группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-129">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="31670-130">**Управление репликой доступности**</span><span class="sxs-lookup"><span data-stu-id="31670-130">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="31670-131">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-131">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-132">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-132">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-133">Удаление вторичной реплики из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-133">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-134">Смена режима доступности для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-134">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="31670-135">Смена режима отработки отказа для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-135">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="31670-136">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-136">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="31670-137">Настройка доступа только для чтения в реплике доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-137">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="31670-138">Настройка маршрутизации только для чтения в группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-138">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-139">Изменение периода ожидания сеанса для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-139">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="31670-140">**Управление базой данных доступности**</span><span class="sxs-lookup"><span data-stu-id="31670-140">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="31670-141">Добавление базы данных в группу доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-141">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="31670-142">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-142">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-143">Удаление базы данных-источника из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-143">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-144">Удаление базы данных-получателя из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-144">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31670-145">Приостановка базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-145">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="31670-146">Возобновление базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-146">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
 <span data-ttu-id="31670-147">**Наблюдение за группой доступности**</span><span class="sxs-lookup"><span data-stu-id="31670-147">**To monitor an availability group**</span></span>  
  
-   [<span data-ttu-id="31670-148">Отслеживание групп доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-148">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
 <span data-ttu-id="31670-149">**Поддержка миграции групп доступности на новый кластер WSFC (миграция с одного кластера на другой)**</span><span class="sxs-lookup"><span data-stu-id="31670-149">**To support migrating availability groups to a new WSFC cluster (cross-cluster migration)**</span></span>  
  
-   [<span data-ttu-id="31670-150">Смена контекста кластера HADR экземпляра сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-150">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
-   [<span data-ttu-id="31670-151">Перевод группы доступности в режим "вне сети" (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31670-151">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="31670-152">См. также</span><span class="sxs-lookup"><span data-stu-id="31670-152">Related Content</span></span>  
  
-   <span data-ttu-id="31670-153">**Блоги**</span><span class="sxs-lookup"><span data-stu-id="31670-153">**Blogs:**</span></span>  
  
     [<span data-ttu-id="31670-154">Блоги команды разработчиков SQL Server AlwaysOn: официальный блог по SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="31670-154">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="31670-155">Блоги инженеров CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="31670-155">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="31670-156">**Видеоролики**</span><span class="sxs-lookup"><span data-stu-id="31670-156">**Videos:**</span></span>  
  
     [<span data-ttu-id="31670-157">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 1: вводные сведения о решении следующего поколения по обеспечению высокого уровня доступности</span><span class="sxs-lookup"><span data-stu-id="31670-157">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="31670-158">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 2: создание критически важного решения по обеспечению высокого уровня доступности с использованием AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="31670-158">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="31670-159">**Технические документы**</span><span class="sxs-lookup"><span data-stu-id="31670-159">**White papers:**</span></span>  
  
     [<span data-ttu-id="31670-160">Технические документы Майкрософт Microsoft по SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="31670-160">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="31670-161">Технические документы группы консультантов по SQL Server</span><span class="sxs-lookup"><span data-stu-id="31670-161">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
  
## <a name="see-also"></a><span data-ttu-id="31670-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="31670-162">See Also</span></span>  
 <span data-ttu-id="31670-163">[Группы доступности AlwaysOn &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31670-163">[AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="31670-164">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31670-164">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="31670-165">Конфигурация экземпляра сервера для группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31670-165">Configuration of a Server Instance for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](configuration-of-a-server-instance-for-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="31670-166">[Создание и настройка групп доступности (SQL Server)](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31670-166">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="31670-167">[Активные вторичные реплики: &#40;группы доступности AlwaysOn для чтения&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="31670-167">[Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="31670-168">Активные вторичные реплики: резервное копирование в &#40;-получателях группы доступности AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="31670-168">Active Secondaries: Backup on Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md)  
 <span data-ttu-id="31670-169">[Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="31670-169">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 <span data-ttu-id="31670-170">[Политики AlwaysOn для проблем в работе с группы доступности AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="31670-170">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="31670-171">[Отслеживание групп доступности (SQL Server)](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31670-171">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="31670-172">[Группы доступности AlwaysOn: взаимодействие &#40;SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31670-172">[AlwaysOn Availability Groups: Interoperability &#40;SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="31670-173">[Общие сведения о инструкциях Transact-SQL для группы доступности AlwaysOn &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="31670-173">[Overview of Transact-SQL Statements for AlwaysOn Availability Groups &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="31670-174">Общие сведения о командлетах PowerShell для группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31670-174">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
