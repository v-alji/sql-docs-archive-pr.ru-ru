---
title: Инициализация подписки на публикацию транзакций из резервной копии (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: d0637fc4-27cc-4046-98ea-dc86b7a3bd75
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1563d58f2d54f77680781e22a162112ade1658e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655592"
---
# <a name="initialize-a-transactional-subscription-from-a-backup-replication-transact-sql-programming"></a><span data-ttu-id="c9093-102">инициализировать подписку на публикацию транзакций из резервной копии (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c9093-102">Initialize a Transactional Subscription from a Backup (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="c9093-103">Хотя инициализация подписки на публикацию транзакций осуществляется через моментальный снимок, она также может быть выполнена с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="c9093-103">Although a subscription to a transactional publication is typically initialized with a snapshot, a subscription can be initialized from a backup using replication stored procedures.</span></span> <span data-ttu-id="c9093-104">Дополнительные сведения см. в статье [Инициализация подписки на публикацию транзакций без моментального снимка](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="c9093-104">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
### <a name="to-initialize-a-transactional-subscriber-from-a-backup"></a><span data-ttu-id="c9093-105">Инициализация подписчика на публикацию транзакций из резервной копии</span><span class="sxs-lookup"><span data-stu-id="c9093-105">To initialize a transactional subscriber from a backup</span></span>  
  
1.  <span data-ttu-id="c9093-106">Убедитесь, что существующая публикация поддерживает возможность инициализации из резервной копии. Для этого в базе данных публикации на издателе выполните хранимую процедуру [sp_helppublication (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9093-106">For an existing publication, ensure that the publication supports the ability to initialize from backup by executing [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="c9093-107">В результирующем наборе проверьте значение параметра **allow_initialize_from_backup** .</span><span class="sxs-lookup"><span data-stu-id="c9093-107">Note the value of **allow_initialize_from_backup** in the result set.</span></span>  
  
    -   <span data-ttu-id="c9093-108">Если оно равно **1**, то публикация поддерживает данную функцию.</span><span class="sxs-lookup"><span data-stu-id="c9093-108">If the value is **1**, the publication supports this functionality.</span></span>  
  
    -   <span data-ttu-id="c9093-109">Если значение равно **0**, выполните хранимую процедуру [sp_changepublication (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) на издателе в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="c9093-109">If the value is **0**, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="c9093-110">Укажите значение **allow_initialize_from_backup** для \*\* \@ Свойства\*\* и значение `true` для параметра \*\* \@ значение\*\*.</span><span class="sxs-lookup"><span data-stu-id="c9093-110">Specify a value of **allow_initialize_from_backup** for **\@property** and a value of `true` for **\@value**.</span></span>  
  
2.  <span data-ttu-id="c9093-111">В новой публикации выполните хранимую процедуру [sp_addpublication (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) на издателе в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="c9093-111">For a new publication, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="c9093-112">Укажите значение `true` для **allow_initialize_from_backup**.</span><span class="sxs-lookup"><span data-stu-id="c9093-112">Specify a value of `true` for **allow_initialize_from_backup**.</span></span> <span data-ttu-id="c9093-113">Дополнительные сведения см. в разделе [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c9093-113">For more information, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="c9093-114">Чтобы предотвратить отсутствие данных подписчика, при использовании процедуры **sp_addpublication** с `@allow_initialize_from_backup = N'true'`всегда используйте `@immediate_sync = N'true'`.</span><span class="sxs-lookup"><span data-stu-id="c9093-114">To avoid missing subscriber data, when using **sp_addpublication** with `@allow_initialize_from_backup = N'true'`, always use `@immediate_sync = N'true'`.</span></span>  
  
3.  <span data-ttu-id="c9093-115">Создайте резервную копию базы данных публикации с использованием инструкции [BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9093-115">Create a backup of the publication database using the [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
4.  <span data-ttu-id="c9093-116">Восстановите резервную копию на подписчике, выполнив инструкцию [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9093-116">Restore the backup on the Subscriber using the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement.</span></span>  
  
5.  <span data-ttu-id="c9093-117">На издателе в базе данных издателя выполните хранимую процедуру [sp_addsubscription (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9093-117">At the Publisher on the publication database, execute the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="c9093-118">Укажите значения следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="c9093-118">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="c9093-119">\*\* \@ sync_type\*\* — значение " **инициализировать с резервной копией**".</span><span class="sxs-lookup"><span data-stu-id="c9093-119">**\@sync_type** - a value of **initialize with backup**.</span></span>  
  
    -   <span data-ttu-id="c9093-120">\*\* \@ backupdevicetype\*\* — тип устройства резервного копирования: **логический** (по умолчанию), **диск**или **Лента**.</span><span class="sxs-lookup"><span data-stu-id="c9093-120">**\@backupdevicetype** - the type of backup device: **logical** (default), **disk**, or **tape**.</span></span>  
  
    -   <span data-ttu-id="c9093-121">\*\* \@ backupdevicename\*\* — логическое или физическое устройство резервного копирования, используемое для восстановления.</span><span class="sxs-lookup"><span data-stu-id="c9093-121">**\@backupdevicename** - the logical or physical backup device to use for the restore.</span></span>  
  
         <span data-ttu-id="c9093-122">Для логического устройства задайте имя устройства резервного копирования, указанное при создании устройства при помощи хранимой процедуры **sp_addumpdevice** .</span><span class="sxs-lookup"><span data-stu-id="c9093-122">For a logical device, specify the name of the backup device specified when **sp_addumpdevice** was used to create the device.</span></span>  
  
         <span data-ttu-id="c9093-123">Для физического устройства укажите полный путь и имя файла, например: `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` или `TAPE = '\\.\TAPE0'`.</span><span class="sxs-lookup"><span data-stu-id="c9093-123">For a physical device, specify a complete path and file name, such as `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` or `TAPE = '\\.\TAPE0'`.</span></span>  
  
    -   <span data-ttu-id="c9093-124">Используемых \*\* \@ Password\*\* — пароль, указанный при создании резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="c9093-124">(Optional) **\@password** - a password that was provided when the backup set was created.</span></span>  
  
    -   <span data-ttu-id="c9093-125">Используемых \*\* \@ MEDIAPASSWORD\*\* — пароль, указанный при форматировании набора носителей.</span><span class="sxs-lookup"><span data-stu-id="c9093-125">(Optional) **\@mediapassword** - a password that was provided when the media set was formatted.</span></span>  
  
    -   <span data-ttu-id="c9093-126">Используемых \*\* \@ fileidhint\*\* — идентификатор восстанавливаемого резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="c9093-126">(Optional) **\@fileidhint** - identifier for the backup set to be restored.</span></span> <span data-ttu-id="c9093-127">Например, значение **1** указывает первый резервный набор данных на носителе данных резервных копий, а значение **2** — второй резервный набор данных.</span><span class="sxs-lookup"><span data-stu-id="c9093-127">For example, specifying **1** indicates the first backup set on the backup medium and **2** indicates the second backup set.</span></span>  
  
    -   <span data-ttu-id="c9093-128">(Необязательно для ленточных устройств) \*\* \@ выгрузка\*\* — укажите значение **1** (по умолчанию), если лента должна быть выгружена с диска после завершения восстановления, и **0** , если его не нужно выгружать.</span><span class="sxs-lookup"><span data-stu-id="c9093-128">(Optional for tape devices) **\@unload** - specify a value of **1** (default) if the tape should be unloaded from the drive after the restore is complete and **0** if it should not be unloaded.</span></span>  
  
6.  <span data-ttu-id="c9093-129">(Необязательно.) Для подписки по запросу выполните процедуру [sp_addpullsubscription (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) и [sp_addpullsubscription_agent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) на подписчике в базе данных подписки.</span><span class="sxs-lookup"><span data-stu-id="c9093-129">(Optional) For a pull subscription, execute [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) and [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="c9093-130">Дополнительные сведения см. в статье [Создание подписки по запросу](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c9093-130">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
7.  <span data-ttu-id="c9093-131">(Необязательно) Запустите агент распространителя.</span><span class="sxs-lookup"><span data-stu-id="c9093-131">(Optional) Start the Distribution Agent.</span></span> <span data-ttu-id="c9093-132">Дополнительные сведения см. в разделе [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) или [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c9093-132">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) or [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9093-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9093-133">See Also</span></span>  
 <span data-ttu-id="c9093-134">[Копирование баз данных путем создания и восстановления резервных копий](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="c9093-134">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="c9093-135">Резервное копирование и восстановление баз данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9093-135">Back Up and Restore of SQL Server Databases</span></span>](../backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
  
