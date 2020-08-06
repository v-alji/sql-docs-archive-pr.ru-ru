---
title: Синхронизация данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], about synchronization
- merge replication synchronization [SQL Server replication]
- scripts [SQL Server replication], synchronization and
- synchronization [SQL Server replication]
- snapshot replication [SQL Server], synchronization
- transactional replication, synchronization
- subscriptions [SQL Server replication], synchronizing
- on demand script execution
- replication [SQL Server], synchronization
- scripts [SQL Server replication]
ms.assetid: 724802f7-7d69-46d3-a330-bd8aa7f53114
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c92cc4d1ae8e836f169a731ecf3c37c81f3dbf10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732550"
---
# <a name="synchronize-data"></a><span data-ttu-id="0d7c6-102">Синхронизация данных</span><span class="sxs-lookup"><span data-stu-id="0d7c6-102">Synchronize Data</span></span>
  <span data-ttu-id="0d7c6-103">Под синхронизацией данных подразумевается процесс распространения изменений данных и схем между издателем и подписчиками, после того как был применен исходный моментальный снимок на подписчике.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-103">Synchronizing data refers to the process of data and schema changes being propagated between the Publisher and Subscribers after the initial snapshot has been applied at the Subscriber.</span></span> <span data-ttu-id="0d7c6-104">Синхронизация может происходить:</span><span class="sxs-lookup"><span data-stu-id="0d7c6-104">Synchronization can occur:</span></span>  
  
-   <span data-ttu-id="0d7c6-105">Непрерывно, что типично для репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-105">Continuously, which is typical for transactional replication.</span></span>  
  
-   <span data-ttu-id="0d7c6-106">По требованию, что типично для репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-106">On demand, which is typical for merge replication.</span></span>  
  
-   <span data-ttu-id="0d7c6-107">По расписанию, что типично для репликации моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-107">On a schedule, which is typical for snapshot replication.</span></span>  
  
 <span data-ttu-id="0d7c6-108">Когда подписка синхронизируется, в зависимости от используемого типа репликации происходят разные процессы:</span><span class="sxs-lookup"><span data-stu-id="0d7c6-108">When a subscription is synchronized, different processes occur based on the type of replication you are using:</span></span>  
  
-   <span data-ttu-id="0d7c6-109">Репликация моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-109">Snapshot replication.</span></span> <span data-ttu-id="0d7c6-110">Синхронизация означает, что агент распространителя повторно применяет моментальный снимок на подписчике — так, чтобы схема и данные в базе данных подписки были согласованы со схемой и данными в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-110">Synchronization means that the Distribution Agent reapplies the snapshot at the Subscriber so that schema and data at the subscription database is consistent with the publication database.</span></span>  
  
     <span data-ttu-id="0d7c6-111">Если на издателе были произведены изменения данных или схемы, для распространения изменений на подписчик должен быть создан новый моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-111">If modifications to data or schema have been made at the Publisher, a new snapshot must be generated in order to propagate modifications to the Subscriber.</span></span>  
  
-   <span data-ttu-id="0d7c6-112">Репликация транзакций.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-112">Transactional replication.</span></span> <span data-ttu-id="0d7c6-113">Синхронизация означает, что агент распространителя передает на подписчик обновления, вставки, удаления и любые другие изменения из базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-113">Synchronization means that the Distribution Agent transfers updates, inserts, deletes, and any other changes from the distribution database to the Subscriber.</span></span>  
  
-   <span data-ttu-id="0d7c6-114">Репликация слиянием.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-114">Merge replication.</span></span> <span data-ttu-id="0d7c6-115">Синхронизация означает, что агент слияния передает изменения с подписчика на издатель, а затем передает изменения с издателя на подписчик.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-115">Synchronization means that the Merge Agent uploads changes from the Subscriber to the Publisher and then downloads changes from the Publisher to the Subscriber.</span></span> <span data-ttu-id="0d7c6-116">Конфликты, если они присутствуют, обнаруживаются и разрешаются.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-116">Conflicts, if any, are detected and resolved.</span></span> <span data-ttu-id="0d7c6-117">Выполняется конвергенция данных, а издатель и все подписчики в итоге достигают состояния с одинаковыми значениями данных.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-117">Data is converged, and the Publisher and all Subscribers eventually end up with the same data values.</span></span> <span data-ttu-id="0d7c6-118">Если были обнаружены и разрешены конфликты, работа, зафиксированная некоторыми из пользователей, изменяется, чтобы разрешить конфликт в соответствии с определенными правилами.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-118">If conflicts were detected and resolved, work that was committed by some of the users is changed to resolve the conflict according to policies you define.</span></span>  
  
 <span data-ttu-id="0d7c6-119">Публикации моментальных снимков полностью обновляют схему на подписчике при каждой синхронизации, так что все изменения схемы применяются на подписчике.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-119">Snapshot publications completely refresh the schema at the Subscriber every time synchronization occurs, so all schema changes are applied to the Subscriber.</span></span> <span data-ttu-id="0d7c6-120">Репликация транзакций и репликация слиянием также поддерживают наиболее распространенные изменения схем.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-120">Transactional replication and merge replication also support the most common schema changes.</span></span> <span data-ttu-id="0d7c6-121">Дополнительные сведения см. в статье [Внесение изменений в схемы баз данных публикации](publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0d7c6-121">For more information, see [Make Schema Changes on Publication Databases](publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
 <span data-ttu-id="0d7c6-122">Сведения о синхронизации принудительной подписки см. в разделе [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="0d7c6-122">To synchronize a push subscription, see [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="0d7c6-123">Сведения о синхронизации подписки по запросу см. в разделе [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="0d7c6-123">To synchronize a pull subscription, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="0d7c6-124">Чтобы настроить расписания синхронизации, см. раздел [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="0d7c6-124">To set synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="0d7c6-125">**Просмотр и разрешение конфликтов синхронизации**</span><span class="sxs-lookup"><span data-stu-id="0d7c6-125">**To view and resolve synchronization conflicts**</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="0d7c6-126">: [Просмотр и разрешение конфликтов данных для публикации слиянием (SQL Server Management Studio)](view-and-resolve-data-conflicts-for-merge-publications.md)</span><span class="sxs-lookup"><span data-stu-id="0d7c6-126">: [View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="0d7c6-127">: [Просмотр конфликтов данных для публикаций транзакций (среда SQL Server Management Studio)](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="0d7c6-127">: [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span></span>  
  
## <a name="executing-code-during-synchronization"></a><span data-ttu-id="0d7c6-128">Выполнение кода во время синхронизации</span><span class="sxs-lookup"><span data-stu-id="0d7c6-128">Executing Code During Synchronization</span></span>  
 <span data-ttu-id="0d7c6-129">Репликация поддерживает два метода выполнения кода во время синхронизации</span><span class="sxs-lookup"><span data-stu-id="0d7c6-129">Replication supports two methods of executing code during synchronization</span></span>  
  
-   <span data-ttu-id="0d7c6-130">Выполнение скрипта по запросу поддерживается для репликации транзакций и репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-130">On demand script execution is supported for transactional replication and merge replication.</span></span> <span data-ttu-id="0d7c6-131">С помощью выполнения скрипта по запросу можно указать, какой скрипт SQL будет выполняться во время синхронизации.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-131">Using on demand script execution you can specify a SQL script to run during synchronization.</span></span> <span data-ttu-id="0d7c6-132">скрипт копируется на подписчик и выполняется с помощью программы **sqlcmd** в начале процесса синхронизации.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-132">The script is copied to the Subscriber and executed using **sqlcmd** at the beginning of the synchronization process.</span></span> <span data-ttu-id="0d7c6-133">скрипт не имеет доступа к реплицированным изменениям, когда они применяются к подписчику.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-133">The script does not have access to the replicated changes as they are applied to the Subscriber.</span></span> <span data-ttu-id="0d7c6-134">Дополнительные сведения см. в статье [Выполнение скриптов во время синхронизации (программирование репликации на языке Transact-SQL)](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="0d7c6-134">For more information, see [Execute Scripts During Synchronization &#40;Replication Transact-SQL Programming&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span></span>  
  
-   <span data-ttu-id="0d7c6-135">Обработчики бизнес-логики поддерживаются для репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-135">Business logic handlers are supported for merge replication.</span></span> <span data-ttu-id="0d7c6-136">С помощью платформы обработчиков бизнес-логики можно создать сборку управляемого кода, которая будет вызываться в процессе синхронизации слиянием.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-136">Using the business logic handler framework you can write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="0d7c6-137">Сборка включает бизнес-логику, которая может учитывать ряд условий во время синхронизации: изменения данных, конфликты и ошибки.</span><span class="sxs-lookup"><span data-stu-id="0d7c6-137">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="0d7c6-138">Дополнительные сведения см. в статье [Выполнение бизнес-логики при синхронизации слиянием](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="0d7c6-138">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7c6-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d7c6-139">See Also</span></span>  
 [<span data-ttu-id="0d7c6-140">Обнаружение и разрешение конфликтов репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="0d7c6-140">Detect and Resolve Merge Replication Conflicts</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
