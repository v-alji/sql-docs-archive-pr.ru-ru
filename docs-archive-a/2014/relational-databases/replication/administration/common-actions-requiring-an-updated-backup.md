---
title: Общие действия, для которых необходима обновленная резервная копия | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], actions requiring a backup
- restoring [SQL Server replication], actions requiring a backup
- backups [SQL Server replication], actions requiring a backup
ms.assetid: a5975bf4-183e-42e3-b7d1-ad02f89d2e1d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3eb10bdca8ee188f7b322a46665c38129d57052b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729354"
---
# <a name="common-actions-requiring-an-updated-backup"></a><span data-ttu-id="05d67-102">Общие действия, для которых необходима обновленная резервная копия</span><span class="sxs-lookup"><span data-stu-id="05d67-102">Common Actions Requiring an Updated Backup</span></span>
  <span data-ttu-id="05d67-103">Если резервное копирование журналов выполняется регулярно, любые изменения, касающиеся репликации, будут заноситься в резервные копии журнала.</span><span class="sxs-lookup"><span data-stu-id="05d67-103">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="05d67-104">Если резервные копии журналов не создаются, выполняйте резервное копирование базы данных публикации, базы данных распространителя, базы данных подписки, баз данных **msdb**и **master** после внесения изменений в схему или топологию репликации.</span><span class="sxs-lookup"><span data-stu-id="05d67-104">If you don't perform log backups, perform a backup of the publication, distribution, subscription, **msdb**, and **master** databases after making modifications to your replication schema or topology.</span></span>  
  
## <a name="publication-database"></a><span data-ttu-id="05d67-105">База данных публикации</span><span class="sxs-lookup"><span data-stu-id="05d67-105">Publication Database</span></span>  
 <span data-ttu-id="05d67-106">Рекомендуется создавать резервную копию базы данных публикации после:</span><span class="sxs-lookup"><span data-stu-id="05d67-106">Backup the publication database after:</span></span>  
  
-   <span data-ttu-id="05d67-107">Создания новых публикаций.</span><span class="sxs-lookup"><span data-stu-id="05d67-107">Creating new publications.</span></span>  
  
-   <span data-ttu-id="05d67-108">Внесения изменений в любые свойства публикации, включая фильтры.</span><span class="sxs-lookup"><span data-stu-id="05d67-108">Changing any publication property, including filtering.</span></span>  
  
-   <span data-ttu-id="05d67-109">Добавления статей в существующую публикацию.</span><span class="sxs-lookup"><span data-stu-id="05d67-109">Adding articles to an existing publication.</span></span>  
  
-   <span data-ttu-id="05d67-110">Проведения повторной инициализации всех подписок на уровне публикаций.</span><span class="sxs-lookup"><span data-stu-id="05d67-110">Performing a publication-wide reinitialization of subscriptions.</span></span>  
  
-   <span data-ttu-id="05d67-111">Внесения изменений схемы в опубликованную таблицу.</span><span class="sxs-lookup"><span data-stu-id="05d67-111">Making a schema change on a published table.</span></span>  
  
-   <span data-ttu-id="05d67-112">Выполнение скрипта по требованию с помощью процедуры [sp_addscriptexec (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05d67-112">Performing on-demand script execution with [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span>  
  
-   <span data-ttu-id="05d67-113">Изменения любого свойства статьи.</span><span class="sxs-lookup"><span data-stu-id="05d67-113">Changing any article property.</span></span>  
  
-   <span data-ttu-id="05d67-114">Удаления любых публикаций.</span><span class="sxs-lookup"><span data-stu-id="05d67-114">Dropping any publications.</span></span>  
  
-   <span data-ttu-id="05d67-115">Удаления любых статей.</span><span class="sxs-lookup"><span data-stu-id="05d67-115">Dropping any articles.</span></span>  
  
-   <span data-ttu-id="05d67-116">Отключения репликации.</span><span class="sxs-lookup"><span data-stu-id="05d67-116">Disabling replication.</span></span>  
  
## <a name="distribution-database"></a><span data-ttu-id="05d67-117">База данных распространителя</span><span class="sxs-lookup"><span data-stu-id="05d67-117">Distribution Database</span></span>  
 <span data-ttu-id="05d67-118">Рекомендуется создавать резервную копию базы данных распространителя после:</span><span class="sxs-lookup"><span data-stu-id="05d67-118">Backup the distribution database after:</span></span>  
  
-   <span data-ttu-id="05d67-119">Создания или изменения профилей агентов репликации.</span><span class="sxs-lookup"><span data-stu-id="05d67-119">Creating or modifying replication agent profiles.</span></span>  
  
-   <span data-ttu-id="05d67-120">Изменения параметров профилей агентов репликации.</span><span class="sxs-lookup"><span data-stu-id="05d67-120">Modifying replication agent profile parameters.</span></span>  
  
-   <span data-ttu-id="05d67-121">Изменения свойств агентов репликации (включая расписания) для любых принудительных подписок.</span><span class="sxs-lookup"><span data-stu-id="05d67-121">Changing the replication agent properties (including schedules) for any push subscriptions.</span></span>  
  
-   <span data-ttu-id="05d67-122">Назначения нового диапазона идентификаторов автоматической функцией управления диапазонами идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="05d67-122">A new range of identities is assigned by the automatic identity range management feature.</span></span>  
  
## <a name="subscription-database"></a><span data-ttu-id="05d67-123">База данных подписки</span><span class="sxs-lookup"><span data-stu-id="05d67-123">Subscription Database</span></span>  
 <span data-ttu-id="05d67-124">Рекомендуется создавать резервную копию базы данных подписок после:</span><span class="sxs-lookup"><span data-stu-id="05d67-124">Backup the subscription database after:</span></span>  
  
-   <span data-ttu-id="05d67-125">Изменения любого свойства подписки.</span><span class="sxs-lookup"><span data-stu-id="05d67-125">Changing any subscription property.</span></span>  
  
-   <span data-ttu-id="05d67-126">Изменения приоритета подписки на публикацию слиянием на издателе.</span><span class="sxs-lookup"><span data-stu-id="05d67-126">Changing the priority for a merge subscription at the Publisher.</span></span>  
  
-   <span data-ttu-id="05d67-127">Удаления любых подписок.</span><span class="sxs-lookup"><span data-stu-id="05d67-127">Dropping any subscriptions.</span></span>  
  
-   <span data-ttu-id="05d67-128">Отключения репликации.</span><span class="sxs-lookup"><span data-stu-id="05d67-128">Disabling replication.</span></span>  
  
## <a name="msdb-database"></a><span data-ttu-id="05d67-129">База данных msdb</span><span class="sxs-lookup"><span data-stu-id="05d67-129">msdb Database</span></span>  
 <span data-ttu-id="05d67-130">Рекомендуется создавать резервную копию системной базы данных **msdb** на соответствующем узле после:</span><span class="sxs-lookup"><span data-stu-id="05d67-130">Backup the **msdb** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="05d67-131">Включения или отключения репликации.</span><span class="sxs-lookup"><span data-stu-id="05d67-131">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="05d67-132">Добавления или удаления базы данных распространителя (на распространителе).</span><span class="sxs-lookup"><span data-stu-id="05d67-132">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="05d67-133">Включения или отключения базы данных публикации (на издателе).</span><span class="sxs-lookup"><span data-stu-id="05d67-133">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="05d67-134">Создания или изменения профилей агентов репликации (на распространителе).</span><span class="sxs-lookup"><span data-stu-id="05d67-134">Creating or modifying replication agent profiles (at the Distributor).</span></span>  
  
-   <span data-ttu-id="05d67-135">Изменения каких-либо параметров профилей агентов репликации (на распространителе).</span><span class="sxs-lookup"><span data-stu-id="05d67-135">Modifying any replication agent profile parameters (at the Distributor).</span></span>  
  
-   <span data-ttu-id="05d67-136">Изменения свойств агентов репликации (включая расписания) для любых принудительных подписок (на распространителе).</span><span class="sxs-lookup"><span data-stu-id="05d67-136">Changing the replication agent properties (including schedules) for any push subscriptions (at the Distributor).</span></span>  
  
-   <span data-ttu-id="05d67-137">Изменения свойств агентов репликации (включая расписания) для любых подписок по запросу (на подписчике).</span><span class="sxs-lookup"><span data-stu-id="05d67-137">Changing the replication agent properties (including schedules) for any pull subscriptions (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="05d67-138">Создания пакета DTS, связанного с публикацией транзакций, использующей трансформируемые подписки (на распространителе и на подписчике).</span><span class="sxs-lookup"><span data-stu-id="05d67-138">Creating a DTS package associated with a transactional publication that uses transformable subscriptions (at the Distributor and Subscriber).</span></span>  
  
-   <span data-ttu-id="05d67-139">Добавления или удаления трансформируемой подписки (на распространителе и на подписчике).</span><span class="sxs-lookup"><span data-stu-id="05d67-139">Adding or dropping a transformable subscription (at the Distributor and Subscriber).</span></span>  
  
## <a name="master-database"></a><span data-ttu-id="05d67-140">База данных master</span><span class="sxs-lookup"><span data-stu-id="05d67-140">master Database</span></span>  
 <span data-ttu-id="05d67-141">Рекомендуется создавать резервную копию системной базы данных **master** на соответствующем узле после:</span><span class="sxs-lookup"><span data-stu-id="05d67-141">Backup the **master** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="05d67-142">Включения или отключения репликации.</span><span class="sxs-lookup"><span data-stu-id="05d67-142">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="05d67-143">Добавления или удаления базы данных распространителя (на распространителе).</span><span class="sxs-lookup"><span data-stu-id="05d67-143">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="05d67-144">Включения или отключения базы данных публикации (на издателе).</span><span class="sxs-lookup"><span data-stu-id="05d67-144">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="05d67-145">Добавления первой или удаления последней публикации в любой базе данных (на издателе).</span><span class="sxs-lookup"><span data-stu-id="05d67-145">Adding the first or dropping the last publication in any database (at the Publisher).</span></span>  
  
-   <span data-ttu-id="05d67-146">Добавления первой или удаления последней подписки в любой базе данных (на подписчике).</span><span class="sxs-lookup"><span data-stu-id="05d67-146">Adding the first or dropping the last subscription in any database (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="05d67-147">Включения или отключения режима издателя на распространяющем издателе (на издателе и на распространителе).</span><span class="sxs-lookup"><span data-stu-id="05d67-147">Enabling or disabling a Publisher at a Distribution Publisher (at the Publisher and Distributor).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d67-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="05d67-148">See Also</span></span>  
 <span data-ttu-id="05d67-149">[Резервное копирование и восстановление баз данных SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="05d67-149">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="05d67-150">Создание резервных копий реплицируемых баз данных и восстановление из них</span><span class="sxs-lookup"><span data-stu-id="05d67-150">Back Up and Restore Replicated Databases</span></span>](back-up-and-restore-replicated-databases.md)  
  
  
