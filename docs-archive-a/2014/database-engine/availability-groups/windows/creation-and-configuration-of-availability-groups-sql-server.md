---
title: Создание и настройка групп доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], creating
ms.assetid: 7f89fab8-6ee2-4273-9de0-e594bfb9407f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc33da393527c19985f5e7b214ba4bc02dc2f3af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752343"
---
# <a name="creation-and-configuration-of-availability-groups-sql-server"></a><span data-ttu-id="60d4b-102">Создание и настройка групп доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-102">Creation and Configuration of Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="60d4b-103">В подразделах этого раздела описано развертывание реализации [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] на экземплярах [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , расположенных на различных узлах отказоустойчивой кластеризации Windows Server (WSFC), с помощью одного кластера отработки отказа WSFC.</span><span class="sxs-lookup"><span data-stu-id="60d4b-103">The topics in this section explain how to deploy a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] implementation on instances of [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] that reside on different Windows Server Failover Clustering (WSFC) nodes within a single WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="60d4b-104">Перед созданием первой группы доступности настоятельно рекомендуется ознакомиться со сведениями, представленными в следующих темах.</span><span class="sxs-lookup"><span data-stu-id="60d4b-104">Before you create your first availability group, we strongly recommend that you familiarize yourself with the information in the following topics:</span></span>  
  
 [<span data-ttu-id="60d4b-105">Предварительные требования, ограничения и рекомендации для группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60d4b-105">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
 <span data-ttu-id="60d4b-106">В этом разделе описываются необходимые условия, ограничения и рекомендации для компьютеров, узлы кластеров WSFC, экземпляры [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], группы доступности, реплики и базы данных.</span><span class="sxs-lookup"><span data-stu-id="60d4b-106">This topic describes the prerequisites, restrictions, and recommendations for computers; WSFC nodes; instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; availability groups, replicas, and databases.</span></span> <span data-ttu-id="60d4b-107">В этой теме также содержатся сведения о мерах безопасности.</span><span class="sxs-lookup"><span data-stu-id="60d4b-107">This topic also contains information about security considerations.</span></span>  
  
 [<span data-ttu-id="60d4b-108">Начало работы с группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60d4b-108">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="60d4b-109">Содержит сведения о шагах по настройке экземпляра сервера, созданию группы доступности, настройке группы доступности для подключения клиентов, управлению группами доступности и их отслеживанию.</span><span class="sxs-lookup"><span data-stu-id="60d4b-109">Contains information about the steps for configuring a server instance, creating an availability group, configuring the availability group for client connections, managing availability groups, and monitoring availability groups.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="60d4b-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="60d4b-110">Related Tasks</span></span>  
 <span data-ttu-id="60d4b-111">**Настройка экземпляра сервера для[!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="60d4b-111">**To configure a server instance for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span></span>  
  
-   [<span data-ttu-id="60d4b-112">Включение и отключение групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-112">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-113">Создание конечной точки зеркального отображения базы данных для группы доступности AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="60d4b-113">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="60d4b-114">Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="60d4b-114">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="60d4b-115">Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="60d4b-115">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
 <span data-ttu-id="60d4b-116">**Сведения о начале настройки групп доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="60d4b-116">**To get started with configuring AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="60d4b-117">Начало работы с группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60d4b-117">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="60d4b-118">**Создание и настройка новой группы доступности**</span><span class="sxs-lookup"><span data-stu-id="60d4b-118">**To create and configure a new availability group**</span></span>  
  
-   [<span data-ttu-id="60d4b-119">Использование мастера групп доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="60d4b-119">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="60d4b-120">Создание группы доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="60d4b-120">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="60d4b-121">Создание группы доступности (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="60d4b-121">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="60d4b-122">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="60d4b-122">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="60d4b-123">Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-123">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="60d4b-124">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-124">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-125">Настройка гибкой политики отработки отказа для обеспечения контроля над автоматическим переходом на другой ресурс (группы доступности AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="60d4b-125">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="60d4b-126">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-127">Настройка доступа только для чтения в реплике доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-127">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-128">Настройка маршрутизации только для чтения в группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-128">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-129">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-129">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-130">Запуск перемещения данных для базы данных-получателя AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60d4b-130">Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;</span></span>](start-data-movement-on-an-always-on-secondary-database-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-131">Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-131">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-132">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-132">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-133">Управление именами входа и заданиями для баз данных группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-133">Management of Logins and Jobs for the Databases of an Availability Group &#40;SQL Server&#41;</span></span>](../../logins-and-jobs-for-availability-group-databases.md)  
  
 <span data-ttu-id="60d4b-134">**Устранение неполадок**</span><span class="sxs-lookup"><span data-stu-id="60d4b-134">**To troubleshoot**</span></span>  
  
-   [<span data-ttu-id="60d4b-135">Устранение неполадок при группы доступности AlwaysOn конфигурации (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-135">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="60d4b-136">Устранение неполадок при &#40;операции добавления файла группы доступности AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="60d4b-136">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="60d4b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="60d4b-137">Related Content</span></span>  
  
-   <span data-ttu-id="60d4b-138">**Блоги**</span><span class="sxs-lookup"><span data-stu-id="60d4b-138">**Blogs:**</span></span>  
  
     [<span data-ttu-id="60d4b-139">Обучающая серия AlwaysON — HADRON. использование пулов рабочих потоков для баз данных с HADRON</span><span class="sxs-lookup"><span data-stu-id="60d4b-139">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="60d4b-140">Блоги команды разработчиков SQL Server AlwaysOn: официальный блог по SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="60d4b-140">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="60d4b-141">Блоги инженеров CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="60d4b-141">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="60d4b-142">**Видеоролики**</span><span class="sxs-lookup"><span data-stu-id="60d4b-142">**Videos:**</span></span>  
  
     [<span data-ttu-id="60d4b-143">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 1: вводные сведения о решении следующего поколения по обеспечению высокого уровня доступности</span><span class="sxs-lookup"><span data-stu-id="60d4b-143">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="60d4b-144">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 2: создание критически важного решения по обеспечению высокого уровня доступности с использованием AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="60d4b-144">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="60d4b-145">**Технические документы**</span><span class="sxs-lookup"><span data-stu-id="60d4b-145">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="60d4b-146">Руководство по решениям режима AlwaysOn в Microsoft SQL Server для обеспечения высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="60d4b-146">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="60d4b-147">Технические документы Майкрософт Microsoft по SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="60d4b-147">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="60d4b-148">Технические документы группы консультантов по SQL Server</span><span class="sxs-lookup"><span data-stu-id="60d4b-148">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="60d4b-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="60d4b-149">See Also</span></span>  
 <span data-ttu-id="60d4b-150">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60d4b-150">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="60d4b-151">[Администрирование &#40;SQL Server группы доступности&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60d4b-151">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="60d4b-152">[Политики AlwaysOn для проблем в работе с группы доступности AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="60d4b-152">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="60d4b-153">[Отслеживание групп доступности (SQL Server)](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60d4b-153">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="60d4b-154">Группы доступности AlwaysOn: взаимодействие (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d4b-154">AlwaysOn Availability Groups: Interoperability (SQL Server)</span></span>](always-on-availability-groups-interoperability-sql-server.md)  
  
