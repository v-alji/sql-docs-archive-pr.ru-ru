---
title: Создание резервных копий реплицируемых баз данных и восстановление из них | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- backups [SQL Server replication]
- administering replication, restoring
- backing up replicated databases
- backups [SQL Server replication], about backups
- restoring replicated databases [SQL Server replication]
- recovery [SQL Server replication], about recovery
- restoring databases [SQL Server], replicated databases
- backing up databases [SQL Server], replicated databases
- restoring [SQL Server replication], about restoring
- recovery [SQL Server replication]
- replication [SQL Server], administering
- distribution databases [SQL Server replication], backing up
- restoring [SQL Server replication]
- administering replication, backing up
ms.assetid: 04588807-21e7-4bbe-9727-b72f692cffa7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e91505bacf67f7f4628bd1b3f6b2cc78a6bc4c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664879"
---
# <a name="back-up-and-restore-replicated-databases"></a><span data-ttu-id="b413a-102">Создание резервных копий реплицируемых баз данных и восстановление из них</span><span class="sxs-lookup"><span data-stu-id="b413a-102">Back Up and Restore Replicated Databases</span></span>
  <span data-ttu-id="b413a-103">Реплицированные базы данных требуют особого внимания к резервному копированию и восстановлению данных.</span><span class="sxs-lookup"><span data-stu-id="b413a-103">Replicated databases require special attention with regards to backing up and restoring data.</span></span> <span data-ttu-id="b413a-104">В данном разделе содержится вводные сведения и ссылки на дополнительные сведения о стратегиях резервного копирования и восстановления для различных типов репликации.</span><span class="sxs-lookup"><span data-stu-id="b413a-104">This topic provides introductory information and links to further information on backup and restore strategies for each type of replication.</span></span>  
  
 <span data-ttu-id="b413a-105">Служба репликации поддерживает восстановление реплицированной базы данных на том же сервере и в той же базе данных, где была создана ее резервная копия.</span><span class="sxs-lookup"><span data-stu-id="b413a-105">Replication supports restoring replicated databases to the same server and database from which the backup was created.</span></span> <span data-ttu-id="b413a-106">Если восстановить резервную копию реплицированной базы данных на другом сервере или в другой базе данных, то станет невозможным сохранение настроек репликации.</span><span class="sxs-lookup"><span data-stu-id="b413a-106">If you restore a backup of a replicated database to another server or database, replication settings cannot be preserved.</span></span> <span data-ttu-id="b413a-107">В этом случае после восстановления из резервной копии потребуется повторно создать все публикации и подписки.</span><span class="sxs-lookup"><span data-stu-id="b413a-107">In this case, you must recreate all publications and subscriptions after backups are restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b413a-108">Реплицируемую базу данных можно восстановить на резервном сервере при использовании доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="b413a-108">It is possible to restore a replicated database to a standby server if log shipping is being used.</span></span> <span data-ttu-id="b413a-109">Дополнительные сведения см. в статье [Репликация и доставка журналов (SQL Server)](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b413a-109">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="b413a-110">Необходимо регулярно выполнять резервное копирование реплицируемых баз данных и связанных с ними системных баз данных.</span><span class="sxs-lookup"><span data-stu-id="b413a-110">Replicated databases and their associated system databases should be backed up regularly.</span></span> <span data-ttu-id="b413a-111">Выполняйте резервное копирование следующих баз данных:</span><span class="sxs-lookup"><span data-stu-id="b413a-111">Back up the following databases:</span></span>  
  
-   <span data-ttu-id="b413a-112">База данных публикаций на издателе.</span><span class="sxs-lookup"><span data-stu-id="b413a-112">The publication database at the Publisher</span></span>  
  
-   <span data-ttu-id="b413a-113">База данных распространителя на распространителе.</span><span class="sxs-lookup"><span data-stu-id="b413a-113">The distribution database at the Distributor</span></span>  
  
-   <span data-ttu-id="b413a-114">База данных подписок на каждом подписчике.</span><span class="sxs-lookup"><span data-stu-id="b413a-114">The subscription database at each Subscriber</span></span>  
  
-   <span data-ttu-id="b413a-115">Системные базы данных **master** и **msdb** на издателе, распространителе и на всех подписчиках.</span><span class="sxs-lookup"><span data-stu-id="b413a-115">The **master** and **msdb** system databases at the Publisher, Distributor and all Subscribers.</span></span> <span data-ttu-id="b413a-116">Резервные копии этих баз данных и копия соответствующей базы данных репликации должны быть сделаны одновременно.</span><span class="sxs-lookup"><span data-stu-id="b413a-116">These databases should be backed up at the same time as each other and the relevant replication database.</span></span> <span data-ttu-id="b413a-117">Например, создавайте резервную копию баз данных **master** и **msdb** на издателе одновременно с резервной копией базы данных публикаций.</span><span class="sxs-lookup"><span data-stu-id="b413a-117">For example, back up the **master** and **msdb** databases at the Publisher at the same time you back up the publication database.</span></span> <span data-ttu-id="b413a-118">Если база данных публикаций восстановлена, убедитесь, что базы данных **master** и **msdb** согласованы с базой данных публикаций по настройке и конфигурации репликации.</span><span class="sxs-lookup"><span data-stu-id="b413a-118">If the publication database is restored, ensure that the **master** and **msdb** database are consistent with the publication database in terms of replication configuration and settings.</span></span>  
  
 <span data-ttu-id="b413a-119">Если резервное копирование журналов выполняется регулярно, любые изменения, касающиеся репликации, будут заноситься в резервные копии журнала.</span><span class="sxs-lookup"><span data-stu-id="b413a-119">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="b413a-120">Если не выполняется резервное копирование журналов, то необходимо выполнить это резервное копирование при каждом изменении настройки, относящейся к репликации.</span><span class="sxs-lookup"><span data-stu-id="b413a-120">If you do not perform log backups, a backup should be performed whenever a setting relevant to replication is changed.</span></span> <span data-ttu-id="b413a-121">Дополнительные сведения см. в статье [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span><span class="sxs-lookup"><span data-stu-id="b413a-121">For more information, see [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span></span>  
  
## <a name="backup-and-restore-strategies"></a><span data-ttu-id="b413a-122">Стратегии резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="b413a-122">Backup and Restore Strategies</span></span>  
 <span data-ttu-id="b413a-123">Стратегии для резервного копирования и восстановления каждого узла в топологии репликации различаются в соответствии с используемым типом репликации.</span><span class="sxs-lookup"><span data-stu-id="b413a-123">The strategies for backing up and restoring each node in a replication topology differ according to the type of replication used.</span></span> <span data-ttu-id="b413a-124">Сведения о стратегиях резервного копирования и восстановления для каждого типа репликации см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b413a-124">For information on backup and restore strategies for each type of replication, see the following topics:</span></span>  
  
-   [<span data-ttu-id="b413a-125">Стратегии резервного копирования и восстановления для моментальных снимков и репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="b413a-125">Strategies for Backing Up and Restoring Snapshot and Transactional Replication</span></span>](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md)  
  
-   [<span data-ttu-id="b413a-126">Стратегии резервного копирования и восстановления для репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="b413a-126">Strategies for Backing Up and Restoring Merge Replication</span></span>](strategies-for-backing-up-and-restoring-merge-replication.md)  
  
 <span data-ttu-id="b413a-127">В состав любой стратегии восстановления всегда должно входить сохранение текущего скрипта настроек репликации в безопасном расположении.</span><span class="sxs-lookup"><span data-stu-id="b413a-127">As part of any recovery strategy, always keep a current script of your replication settings in a safe location.</span></span> <span data-ttu-id="b413a-128">В случае отказа сервера или необходимости создания тестовой среды можно изменить скрипт, изменив ссылки имен серверов, после чего он может использоваться для восстановления настроек репликации.</span><span class="sxs-lookup"><span data-stu-id="b413a-128">In the event of server failure or the need to set up a test environment, you can modify the script by changing server name references, and it can be used to help recreate your replication settings.</span></span> <span data-ttu-id="b413a-129">В дополнение к созданию скрипта текущих настроек репликации нужно создать скрипт включения и отключения репликации.</span><span class="sxs-lookup"><span data-stu-id="b413a-129">In addition to scripting your current replication settings, you should script the enabling and disabling of replication.</span></span> <span data-ttu-id="b413a-130">Сведения о создании скриптов для объектов репликации см. в разделе [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b413a-130">For information about scripting replication objects, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b413a-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="b413a-131">See Also</span></span>  
 <span data-ttu-id="b413a-132">[Резервное копирование и восстановление баз данных SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="b413a-132">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="b413a-133">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="b413a-133">Best Practices for Replication Administration</span></span>](best-practices-for-replication-administration.md)  
  
  
