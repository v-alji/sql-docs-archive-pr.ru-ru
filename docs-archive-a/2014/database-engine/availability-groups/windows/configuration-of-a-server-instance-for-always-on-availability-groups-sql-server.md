---
title: Настройка экземпляра сервера для Always On групп доступности (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], about
ms.assetid: fad8db32-593e-49d5-989c-39eb8399c416
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3392e6189b687516e627d847acceedb165141117
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750212"
---
# <a name="configuration-of-a-server-instance-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="9f797-102">Настройка экземпляра сервера для групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9f797-102">Configuration of a Server Instance for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="9f797-103">Этот раздел содержит сведения о требованиях к настройке экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для поддержки [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f797-103">This topic contains information about the requirements for configuring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9f797-104">Важные сведения о предварительных требованиях и ограничениях [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] для узлов с отказоустойчивой кластеризацией Windows Server (WSFC) и экземпляров [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] см. в статье [Предварительные требования, ограничения и рекомендации для групп доступности AlwaysOn (SQL Server)](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="9f797-104">For essential information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites and restrictions for Windows Server Failover Clustering (WSFC) nodes and for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
 
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="9f797-105">Термины и определения</span><span class="sxs-lookup"><span data-stu-id="9f797-105">Terms and Definitions</span></span>  
  
 <span data-ttu-id="9f797-106">Решение по обеспечению высокой доступности и аварийного восстановления, заменяющее зеркальное отображение базы данных на уровне предприятия.</span><span class="sxs-lookup"><span data-stu-id="9f797-106">A high-availability and disaster-recovery solution that provides an enterprise-level replacement for database mirroring.</span></span> <span data-ttu-id="9f797-107">*Группа доступности* поддерживает среду отработки отказа для дискретного набора пользовательских баз данных, известных как *базы данных доступности*, которые совместно отключаются при отработке отказа.</span><span class="sxs-lookup"><span data-stu-id="9f797-107">An *availability group* supports a failover environment for a discrete set of user databases, known as *availability databases*, that fail over together.</span></span>  
  
 <span data-ttu-id="9f797-108">реплика доступности</span><span class="sxs-lookup"><span data-stu-id="9f797-108">availability replica</span></span>  
 <span data-ttu-id="9f797-109">Создание экземпляра группы доступности, которая размещена на определенном экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и поддерживает локальную копию каждой базы данных доступности, входящей в группу доступности.</span><span class="sxs-lookup"><span data-stu-id="9f797-109">An instantiation of an availability group that is hosted by a specific instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and that maintains a local copy of each availability database that belongs to the availability group.</span></span> <span data-ttu-id="9f797-110">Существует два типа реплик доступности: одна *первичная* и от одной до четырех *вторичных реплик*.</span><span class="sxs-lookup"><span data-stu-id="9f797-110">Two types of availability replicas exist: a single *primary replica* and one to four *secondary replicas*.</span></span> <span data-ttu-id="9f797-111">Экземпляры сервера, на которых размещаются реплики доступности для данной группы доступности, должны размещаться на разных узлах одной кластеризации WSFC.</span><span class="sxs-lookup"><span data-stu-id="9f797-111">The server instances that host the availability replicas for a given availability group must reside on different nodes of a single Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 [<span data-ttu-id="9f797-112">Конечная точка зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="9f797-112">database mirroring endpoint</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
 <span data-ttu-id="9f797-113">Конечная точка — это объект SQL Server, позволяющий SQL Server обмениваться данными по сети.</span><span class="sxs-lookup"><span data-stu-id="9f797-113">An endpoint is a SQL Server object that enables SQL Server to communicate over the network.</span></span> <span data-ttu-id="9f797-114">Для участия в зеркальном отображении базы данных и/или [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , экземпляр сервера требует наличия специальной, выделенной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9f797-114">To participate in database mirroring and/or [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] a server instance requires a special, dedicated endpoint.</span></span> <span data-ttu-id="9f797-115">Все подключения зеркального отображения и групп доступности на экземпляре сервера используют одну конечную точку зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f797-115">All mirroring and availability group connections on a server instance use the same database mirroring endpoint.</span></span> <span data-ttu-id="9f797-116">Эта точка является конечной точкой специального назначения. Она используется исключительно для приема подключений от других экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="9f797-116">This endpoint is a special-purpose endpoint used exclusively to receive these connections from other server instances.</span></span>  
  
##  <a name="to-configure-a-server-instance-to-support-alwayson-availability-groups"></a><a name="ConfigSI"></a><span data-ttu-id="9f797-117">Настройка экземпляра сервера для поддержки группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="9f797-117">To Configure a Server Instance to Support AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="9f797-118">Для поддержки [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]экземпляр сервера должен находиться на узле в отказоустойчивом кластере WSFC, в котором размещается группа доступности; для него должна быть включена поддержка [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] и должна иметься конечная точка зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f797-118">To support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], a server instance must reside on a node in the WSFC failover cluster that hosts the availability group, be [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] enabled, and possess a database mirroring endpoint.</span></span>  
  
1.  <span data-ttu-id="9f797-119">Включите функцию «Группы доступности AlwaysOn» на всех экземплярах сервера, которые будут использоваться в одной или нескольких группах доступности.</span><span class="sxs-lookup"><span data-stu-id="9f797-119">Enable the AlwaysOn Availability Groups feature on every server instance that is to participate in one or more availability groups.</span></span> <span data-ttu-id="9f797-120">На данном экземпляре сервера может быть размещена только одна реплика доступности для данной группы доступности.</span><span class="sxs-lookup"><span data-stu-id="9f797-120">A given server instance can host only a single availability replica for a given availability group.</span></span>  
  
2.  <span data-ttu-id="9f797-121">Убедитесь, что в экземпляре сервера есть конечная точка зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f797-121">Ensure that the server instance possesses a database mirroring endpoint.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9f797-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9f797-122">Related Tasks</span></span>  
 <span data-ttu-id="9f797-123">**Включение функции «Группы доступности AlwaysOn»**</span><span class="sxs-lookup"><span data-stu-id="9f797-123">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="9f797-124">Включение и отключение групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9f797-124">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="9f797-125">**Определение того, существует ли конечная точка зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="9f797-125">**To determine whether a database mirroring endpoint exists**</span></span>  
  
-   [<span data-ttu-id="9f797-126">sys.database_mirroring_endpoints (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9f797-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="9f797-127">**Создание конечной точки зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="9f797-127">**To create a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="9f797-128">Создание конечной точки зеркального отображения базы данных для группы доступности AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="9f797-128">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="9f797-129">Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9f797-129">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="9f797-130">Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9f797-130">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="9f797-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9f797-131">Related Content</span></span>  
  
-   <span data-ttu-id="9f797-132">**Блоги**</span><span class="sxs-lookup"><span data-stu-id="9f797-132">**Blogs:**</span></span>  
  
     [<span data-ttu-id="9f797-133">Обучающая серия AlwaysON — HADRON. использование пулов рабочих потоков для баз данных с HADRON</span><span class="sxs-lookup"><span data-stu-id="9f797-133">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="9f797-134">Блоги команды разработчиков SQL Server AlwaysOn: официальный блог по SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="9f797-134">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="9f797-135">Блоги инженеров CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f797-135">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="9f797-136">**Видеоролики**</span><span class="sxs-lookup"><span data-stu-id="9f797-136">**Videos:**</span></span>  
  
     [<span data-ttu-id="9f797-137">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 1: вводные сведения о решении следующего поколения по обеспечению высокого уровня доступности</span><span class="sxs-lookup"><span data-stu-id="9f797-137">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="9f797-138">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 2: создание критически важного решения по обеспечению высокого уровня доступности с использованием AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="9f797-138">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="9f797-139">**Технические документы**</span><span class="sxs-lookup"><span data-stu-id="9f797-139">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="9f797-140">Руководство по решениям режима AlwaysOn в Microsoft SQL Server для обеспечения высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="9f797-140">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="9f797-141">Технические документы Майкрософт Microsoft по SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="9f797-141">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="9f797-142">Технические документы группы консультантов по SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f797-142">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="9f797-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f797-143">See Also</span></span>  
 <span data-ttu-id="9f797-144">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f797-144">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="9f797-145">[Предварительные требования, ограничения и рекомендации для группы доступности AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="9f797-145">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="9f797-146">[Конечная точка зеркального отображения базы данных (SQL Server)](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f797-146">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="9f797-147">[Группы доступности AlwaysOn: взаимодействие (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f797-147">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="9f797-148">[Отказоустойчивая кластеризация и группы доступности AlwaysOn &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f797-148">[Failover Clustering and AlwaysOn Availability Groups &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="9f797-149">[Отказоустойчивая кластеризация Windows Server (WSFC) с SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f797-149">[Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="9f797-150">Экземпляры отказоустойчивого кластера AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="9f797-150">AlwaysOn Failover Cluster Instances</span></span>](../../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md)  
  
