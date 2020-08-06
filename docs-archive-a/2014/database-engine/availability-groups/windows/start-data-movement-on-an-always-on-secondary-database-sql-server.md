---
title: Запуск перемещения данных в базе данных-получателе AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], databases
ms.assetid: 498eb3fb-6a43-434d-ad95-68a754232c45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ce4f80b456244cd6e024377383abe75e002057a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750188"
---
# <a name="start-data-movement-on-an-alwayson-secondary-database-sql-server"></a><span data-ttu-id="ae5b9-102">Запуск перемещения данных для базы данных-получателя AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ae5b9-102">Start Data Movement on an AlwaysOn Secondary Database (SQL Server)</span></span>
  <span data-ttu-id="ae5b9-103">В этом разделе приведены сведения о запуске синхронизации данных после добавления базы данных в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-103">This topic contains information about how to start data synchronization after you add a database to an AlwaysOn availability group.</span></span> <span data-ttu-id="ae5b9-104">Для каждой новой первичной реплики необходимо подготовить базы данных-получатели на экземплярах сервера, размещающих вторичные реплики.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-104">For each new primary replica, secondary databases must be prepared on the server instances that host the secondary replicas.</span></span> <span data-ttu-id="ae5b9-105">Затем каждую из этих баз данных-получателей необходимо вручную присоединить к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-105">Then each of these secondary databases must be manually joined to the availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae5b9-106">Если пути к файлам на всех экземплярах сервера, размещающих реплики доступности группы доступности, одинаковые, то [мастер создания групп доступности](use-the-availability-group-wizard-sql-server-management-studio.md), [мастер добавления реплики в группу доступности](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)или [мастер добавления базы данных в группу доступности](availability-group-add-database-to-group-wizard.md) может автоматически запустить синхронизацию данных.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-106">If the file paths are identical on every server instance that hosts an availability replica for an availability group, the [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md) might be able to automatically start data synchronization for you.</span></span>  
  
 <span data-ttu-id="ae5b9-107">Для запуска синхронизации данных вручную потребуется поочередное подключение ко всем экземплярам сервера, на которых размещаются вторичные реплики для группы доступности, и выполнение следующих действий.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-107">To start data synchronization manually, you need to connect, in turn, to each server instance that is hosting a secondary replica for the availability group and complete the following steps:</span></span>  
  
1.  <span data-ttu-id="ae5b9-108">Восстановление текущих резервных копий всех баз данных-источников и их журналов транзакций (с помощью инструкции RESTORE WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="ae5b9-108">Restore current backups of each primary database and its transaction log (using RESTORE WITH NORECOVERY).</span></span> <span data-ttu-id="ae5b9-109">Можно использовать один из следующих альтернативных подходов.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-109">You can use either of the following alternative approaches:</span></span>  
  
    -   <span data-ttu-id="ae5b9-110">Вручную восстановить последнюю резервную копию базы данных-источника с помощью инструкции RESTORE WITH NORECOVERY, а затем восстановить все последовательные резервные копии журнала с помощью инструкции RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-110">Manually restore a recent database backup of the primary database using RESTORE WITH NORECOVERY, and then restore each subsequent log backup using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="ae5b9-111">Выполните эту последовательность восстановления на каждом экземпляре сервера, на котором расположена вторичная реплика этой группы доступности.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-111">Perform this restore sequence on every server instance that hosts a secondary replica for the availability group.</span></span>  
  
         <span data-ttu-id="ae5b9-112">**Дополнительные сведения:**</span><span class="sxs-lookup"><span data-stu-id="ae5b9-112">**For more information:**</span></span>  
  
         [<span data-ttu-id="ae5b9-113">Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ae5b9-113">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
    -   <span data-ttu-id="ae5b9-114">При добавлении одной или нескольких баз данных-источников к группе доступности можно будет перевести одну или несколько соответствующих баз данных-получателей из доставки журналов в группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-114">If you are adding one or more log shipping primary databases to an availability group, you might be able to migrate one or more of the corresponding secondary databases from log shipping to AlwaysOn Availability Groups.</span></span> <span data-ttu-id="ae5b9-115">Для выполнения переноса базы данных-получателя доставки журналов необходимо, чтобы эта база называлась так же, как и база данных-источник, и размещалась на экземпляре сервера, на котором находится вторичная реплика для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-115">Migrating a log shipping secondary database requires that it use the same database name as the primary database and that it reside on a server instance that is hosting a secondary replica for the availability group.</span></span> <span data-ttu-id="ae5b9-116">Кроме того, группа доступности должна быть настроена так, чтобы первичная реплика была первым кандидатом для выполнения резервного копирования (то есть иметь приоритет резервного копирования >0).</span><span class="sxs-lookup"><span data-stu-id="ae5b9-116">Furthermore, the availability group must be configured so that the primary replica is preferred for backups and is a candidate for performing backups (that is, that has a backup priority that is >0).</span></span> <span data-ttu-id="ae5b9-117">После завершения задания резервного копирования для базы данных-источника необходимо отключить задание резервного копирования, а после выполнения задания по восстановлению для выбранной базы данных-получателя — отключить задание восстановления.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-117">Once the backup job has run on the primary database, you will need to disable the backup job, and once the restore job has run on a given secondary database, you will need to disable the restore job.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="ae5b9-118">После создания всех баз данных-получателей для группы доступности, при необходимости проведения резервного копирования на вторичных репликах, нужно изменить параметры автоматического резервного копирования для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-118">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you will need to re-configure the automated backup preference of the availability group.</span></span>  
  
         <span data-ttu-id="ae5b9-119">**Дополнительные сведения:**</span><span class="sxs-lookup"><span data-stu-id="ae5b9-119">**For more information:**</span></span>  
  
         [<span data-ttu-id="ae5b9-120">Необходимые условия для перехода с доставки журналов на группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5b9-120">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
         [<span data-ttu-id="ae5b9-121">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ae5b9-121">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
2.  <span data-ttu-id="ae5b9-122">Как можно скорее присоедините все новые подготовленные базы данных-получатели к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-122">As soon as possible, join each newly prepared secondary database to the availability group.</span></span>  
  
     <span data-ttu-id="ae5b9-123">**Дополнительные сведения:**</span><span class="sxs-lookup"><span data-stu-id="ae5b9-123">**For more information:**</span></span>  
  
     [<span data-ttu-id="ae5b9-124">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ae5b9-124">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="LaunchWiz"></a> <span data-ttu-id="ae5b9-125">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="ae5b9-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ae5b9-126">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ae5b9-126">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ae5b9-127">Использование мастера добавления реплики в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ae5b9-127">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ae5b9-128">Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ae5b9-128">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="ae5b9-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae5b9-129">See Also</span></span>  
 [<span data-ttu-id="ae5b9-130">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5b9-130">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
