---
title: Предварительные требования для перехода с доставки журналов на группы доступности AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 2738ce65-205e-4682-92d8-dc7e37c58b2b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 76b50d5af8eb520b3764ff56397c040f2d0d0141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734461"
---
# <a name="prerequisites-for-migrating-from-log-shipping-to-alwayson-availability-groups-sql-server"></a><span data-ttu-id="139f0-102">Необходимые условия для выполнения перехода от использования доставки журналов к использованию групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="139f0-102">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="139f0-103">В этом разделе описаны предварительные условия для преобразования базы данных-источника доставки журналов вместе с одной или несколькими базами данных-получателями в базу данных-источник и базы данных-получатели AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="139f0-103">This topic describes the prerequisites for converting a log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and secondary database(s).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="139f0-104">В качестве первичной базы данных для доставки журналов вы можете настроить любую базу данных-источник или базу данных-получатель (по возможности предназначенную для чтения).</span><span class="sxs-lookup"><span data-stu-id="139f0-104">You can configure any primary or secondary database (possibly readable) in an availability group as a log shipping primary database.</span></span>  
  
 <span data-ttu-id="139f0-105">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="139f0-105">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="139f0-106">Предварительные условия для группы доступности</span><span class="sxs-lookup"><span data-stu-id="139f0-106">Availability Group Prerequisites</span></span>](#AGPrereqsRealAddress)  
  
-   [<span data-ttu-id="139f0-107">Предварительные условия для доставки журналов</span><span class="sxs-lookup"><span data-stu-id="139f0-107">Log Shipping Prerequisites</span></span>](#LogShipPrereqs)  
  
-   [<span data-ttu-id="139f0-108">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="139f0-108">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="139f0-109">См. также</span><span class="sxs-lookup"><span data-stu-id="139f0-109">Related Content</span></span>](#RelatedContent)  
  
##  <a name="availability-group-prerequisites"></a><a name="AGPrereqsRealAddress"></a><span data-ttu-id="139f0-110">Предварительные требования для группы доступности</span><span class="sxs-lookup"><span data-stu-id="139f0-110">Availability Group Prerequisites</span></span>  
 <span data-ttu-id="139f0-111">Чтобы разрешить выполнение заданий резервного копирования в первичной реплике группы доступности, используйте следующие параметры резервного копирования групп доступности AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="139f0-111">To allow backup jobs to run on the primary replica of the availability group, use the following AlwaysOn Availability Groups backup settings:</span></span>  
  
|<span data-ttu-id="139f0-112">Свойство.</span><span class="sxs-lookup"><span data-stu-id="139f0-112">Property</span></span>|<span data-ttu-id="139f0-113">Параметр</span><span class="sxs-lookup"><span data-stu-id="139f0-113">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="139f0-114">Автоматическое резервное копирование группы доступности</span><span class="sxs-lookup"><span data-stu-id="139f0-114">Automated backup preference of availability group</span></span>|<span data-ttu-id="139f0-115">Только в первичной реплике</span><span class="sxs-lookup"><span data-stu-id="139f0-115">Only on the primary replica</span></span>|  
|<span data-ttu-id="139f0-116">Приоритет резервного копирования первичной реплики.</span><span class="sxs-lookup"><span data-stu-id="139f0-116">Backup priority of the primary replica.</span></span>|<span data-ttu-id="139f0-117">> 0</span><span class="sxs-lookup"><span data-stu-id="139f0-117">>0</span></span>|  
  
 <span data-ttu-id="139f0-118">**Дополнительные сведения:**</span><span class="sxs-lookup"><span data-stu-id="139f0-118">**For more information:**</span></span>  
  
 [<span data-ttu-id="139f0-119">Просмотр свойств группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="139f0-119">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
 [<span data-ttu-id="139f0-120">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="139f0-120">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="log-shipping-prerequisites"></a><a name="LogShipPrereqs"></a><span data-ttu-id="139f0-121">Предварительные требования для доставки журналов</span><span class="sxs-lookup"><span data-stu-id="139f0-121">Log Shipping Prerequisites</span></span>  
  
-   <span data-ttu-id="139f0-122">База данных-источник доставки журналов должна находиться на экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором размещается первоначальная или текущая первичная реплика группы доступности.</span><span class="sxs-lookup"><span data-stu-id="139f0-122">The log shipping primary database must reside on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the initial/current primary replica of the availability group.</span></span>  
  
-   <span data-ttu-id="139f0-123">Для преобразования базы данных-получателя доставки журнала в базу данных-получатель AlwaysOn необходимо:</span><span class="sxs-lookup"><span data-stu-id="139f0-123">For a given log shipping secondary database to be converted to an AlwaysOn secondary database, it must:</span></span>  
  
    -   <span data-ttu-id="139f0-124">использовать то же имя, что и у базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="139f0-124">Use the same name as the primary database.</span></span>  
  
    -   <span data-ttu-id="139f0-125">Размещение на экземпляре сервера, на котором размещается вторичная реплика для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="139f0-125">Reside on a server instance that hosts a secondary replica for the availability group.</span></span>  
  
 <span data-ttu-id="139f0-126">После выполнения задания резервного копирования для базы данных-источника отключите задание резервного копирования и после выполнения задания по восстановлению для выбранной базы данных-получателя отключите задание восстановления.</span><span class="sxs-lookup"><span data-stu-id="139f0-126">Once the backup job has run on the primary database, disable the backup job, and once the restore job has run on a given secondary database, disable the restore job.</span></span>  
  
 <span data-ttu-id="139f0-127">После создания всех баз данных-получателей для группы доступности при необходимости проведения резервного копирования во вторичных репликах нужно изменить параметры автоматического резервного копирования для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="139f0-127">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you need to re-configure the automated backup preference of the availability group.</span></span>  
  
 <span data-ttu-id="139f0-128">**Дополнительные сведения:**</span><span class="sxs-lookup"><span data-stu-id="139f0-128">**For more information:**</span></span>  
  
 <span data-ttu-id="139f0-129">[Преобразование конфигурации доставки журналов в группу доступности](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (блог по SQL Server)</span><span class="sxs-lookup"><span data-stu-id="139f0-129">[Converting a logshipping configuration to Availability Group](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (a SQL Server blog)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="139f0-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="139f0-130">Related Tasks</span></span>  
 <span data-ttu-id="139f0-131">**Доставка журналов**</span><span class="sxs-lookup"><span data-stu-id="139f0-131">**Log shipping**</span></span>  
  
-   [<span data-ttu-id="139f0-132">Обновление доставки журналов до SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="139f0-132">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](../../log-shipping/upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="139f0-133">Удаление доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="139f0-133">Remove Log Shipping &#40;SQL Server&#41;</span></span>](../../log-shipping/remove-log-shipping-sql-server.md)  
  
 <span data-ttu-id="139f0-134">**Группы доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="139f0-134">**AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="139f0-135">Использование мастера групп доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="139f0-135">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="139f0-136">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="139f0-136">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="139f0-137">Создание группы доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="139f0-137">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="139f0-138">Создание группы доступности (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="139f0-138">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="139f0-139">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="139f0-139">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="139f0-140">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="139f0-140">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="139f0-141">См. также</span><span class="sxs-lookup"><span data-stu-id="139f0-141">Related Content</span></span>  
  
-   <span data-ttu-id="139f0-142">**Блоги**</span><span class="sxs-lookup"><span data-stu-id="139f0-142">**Blogs:**</span></span>  
  
     [<span data-ttu-id="139f0-143">Преобразование конфигурации доставки журналов в группу доступности</span><span class="sxs-lookup"><span data-stu-id="139f0-143">Converting a logshipping configuration to Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/converting-a-logshipping-configuration-to-availability-group)  
  
     [<span data-ttu-id="139f0-144">Добавление базы данных-источника доставки журналов и баз данных-получателей к существующей группе доступности</span><span class="sxs-lookup"><span data-stu-id="139f0-144">Add a Log Shipping Primary Database and Secondary Database(s) to an Existing Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/add-a-log-shipping-primary-database-and-secondary-databases-to-an-existing-availability-group)  
  
     [<span data-ttu-id="139f0-145">Блоги команды разработчиков SQL Server AlwaysOn: официальный блог по SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="139f0-145">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/)  
  
     [<span data-ttu-id="139f0-146">Блоги инженеров CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="139f0-146">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="139f0-147">**Технические документы**</span><span class="sxs-lookup"><span data-stu-id="139f0-147">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="139f0-148">Руководство по миграции. Переход на группы доступности AlwaysOn с предыдущих развертываний, сочетающих зеркальное отображение базы данных и доставку журналов</span><span class="sxs-lookup"><span data-stu-id="139f0-148">Migration Guide: Migrating to AlwaysOn Availability Groups from Prior Deployments Combining Database Mirroring and Log Shipping</span></span>](https://msdn.microsoft.com/library/jj635217)  
  
     [<span data-ttu-id="139f0-149">Технические документы Майкрософт Microsoft по SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="139f0-149">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="139f0-150">Технические документы группы консультантов по SQL Server</span><span class="sxs-lookup"><span data-stu-id="139f0-150">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="139f0-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="139f0-151">See Also</span></span>  
 <span data-ttu-id="139f0-152">[Сведения о доставке журналов (SQL Server)](../../log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="139f0-152">[About Log Shipping &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="139f0-153">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="139f0-153">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="139f0-154">Отслеживание групп доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="139f0-154">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
