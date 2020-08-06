---
title: Резервные копии только для копирования (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- copy-only backups [SQL Server]
- COPY_ONLY option [BACKUP statement]
- backups [SQL Server], copy-only backups
ms.assetid: f82d6918-a5a7-4af8-868e-4247f5b00c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc74d7b1bba2a0163ac9edefb5d465c54ef6296c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668930"
---
# <a name="copy-only-backups-sql-server"></a><span data-ttu-id="a8d09-102">Резервные копии только для копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a8d09-102">Copy-Only Backups (SQL Server)</span></span>
  <span data-ttu-id="a8d09-103">*Резервная копия только для копирования* — это резервная копия [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которая не зависит от обычной последовательности создания традиционных резервных копий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8d09-103">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="a8d09-104">Обычно создание резервного копирования приводит к изменению базы данных и влияет на то, как будут восстанавливаться последующие резервные копии.</span><span class="sxs-lookup"><span data-stu-id="a8d09-104">Usually, taking a backup changes the database and affects how later backups are restored.</span></span> <span data-ttu-id="a8d09-105">Однако иногда приходится выполнять резервное копирование базы данных для особых нужд, когда это не сказывается на общем процессе резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="a8d09-105">However, occasionally, it is useful to take a backup for a special purpose without affecting the overall backup and restore procedures for the database.</span></span> <span data-ttu-id="a8d09-106">Этой цели служат резервные копии только для копирования.</span><span class="sxs-lookup"><span data-stu-id="a8d09-106">Copy-only backups serve this purpose.</span></span>  
  
 <span data-ttu-id="a8d09-107">Резервные копии только для копирования имеют следующие типы.</span><span class="sxs-lookup"><span data-stu-id="a8d09-107">The types of copy-only backups are as follows:</span></span>  
  
-   <span data-ttu-id="a8d09-108">Полные резервные копии только для копирования (все модели восстановления).</span><span class="sxs-lookup"><span data-stu-id="a8d09-108">Copy-only full backups (all recovery models)</span></span>  
  
     <span data-ttu-id="a8d09-109">Резервная копия только для копирования не может служить в качестве базовой копии для разностного копирования или разностного резервного копирования и не влияет на базовую копию для разностного копирования.</span><span class="sxs-lookup"><span data-stu-id="a8d09-109">A copy-only backup cannot serve as a differential base or differential backup and does not affect the differential base.</span></span>  
  
     <span data-ttu-id="a8d09-110">Операция восстановления полной резервной копии только для копирования аналогична операции восстановления любой полной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="a8d09-110">Restoring a copy-only full backup is the same as restoring any other full backup.</span></span>  
  
-   <span data-ttu-id="a8d09-111">Резервные копии журналов только для копирования (модель полного восстановления и модель восстановления с неполным протоколированием).</span><span class="sxs-lookup"><span data-stu-id="a8d09-111">Copy-only log backups (full recovery model and bulk-logged recovery model only)</span></span>  
  
     <span data-ttu-id="a8d09-112">Резервная копия журналов только для копирования сохраняет текущую точку архивирования журнала и, следовательно, не влияет на последовательность обычных резервных копий журналов.</span><span class="sxs-lookup"><span data-stu-id="a8d09-112">A copy-only log backup preserves the existing log archive point and, therefore, does not affect the sequencing of regular log backups.</span></span> <span data-ttu-id="a8d09-113">Никакой необходимости в резервных копиях журналов только для копирования обычно нет.</span><span class="sxs-lookup"><span data-stu-id="a8d09-113">Copy-only log backups are typically unnecessary.</span></span> <span data-ttu-id="a8d09-114">Вместо этого можно создать новую обычную резервную копию журналов (с параметром WITH NORECOVERY), затем использовать ее совместно со всеми остальными ранее созданными резервными копиями журналов, которые необходимы для последовательности восстановления.</span><span class="sxs-lookup"><span data-stu-id="a8d09-114">Instead, you can create a new routine log backup (using WITH NORECOVERY) and use that backup together with any previous log backups that are required for the restore sequence.</span></span> <span data-ttu-id="a8d09-115">Однако резервная копия журналов только для копирования иногда может быть полезна для выполнения восстановления в сети.</span><span class="sxs-lookup"><span data-stu-id="a8d09-115">However, a copy-only log backup can sometimes be useful for performing an online restore.</span></span> <span data-ttu-id="a8d09-116">Пример см. в разделе [Пример. Оперативное восстановление файла, доступного для чтения и записи &#40;модель полного восстановления&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="a8d09-116">For an example of this, see [Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span></span>  
  
     <span data-ttu-id="a8d09-117">Журнал транзакций никогда не усекается после создания резервной копии только для копирования.</span><span class="sxs-lookup"><span data-stu-id="a8d09-117">The transaction log is never truncated after a copy-only backup.</span></span>  
  
 <span data-ttu-id="a8d09-118">Резервные копии только для копирования записываются в столбец **is_copy_only** таблицы [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a8d09-118">Copy-only backups are recorded in the **is_copy_only** column of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) table.</span></span>  
  
## <a name="to-create-a-copy-only-backup"></a><span data-ttu-id="a8d09-119">Создание резервной копии только для копирования</span><span class="sxs-lookup"><span data-stu-id="a8d09-119">To Create a Copy-Only Backup</span></span>  
 <span data-ttu-id="a8d09-120">Резервную копию только для копирования можно создать с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8d09-120">You can create a copy-only backup by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a8d09-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8d09-121">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="a8d09-122">На странице **Общие** диалогового окна **Создание резервной копии базы данных** выберите **Резервная копия только для копирования** .</span><span class="sxs-lookup"><span data-stu-id="a8d09-122">On the **General** page of the **Back Up Database** dialog box, select the **Copy Only Backup** option.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a8d09-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8d09-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="a8d09-124">Требуемый синтаксис [!INCLUDE[tsql](../../../includes/tsql-md.md)] выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a8d09-124">The essential [!INCLUDE[tsql](../../../includes/tsql-md.md)] syntax is as follows:</span></span>  
  
-   <span data-ttu-id="a8d09-125">Для полных резервных копий только для копирования:</span><span class="sxs-lookup"><span data-stu-id="a8d09-125">For a copy-only full backup:</span></span>  
  
     <span data-ttu-id="a8d09-126">Резервное копирование базы данных *database_name* в \<backup_device*> \*... С COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="a8d09-126">BACKUP DATABASE *database_name* TO \<backup_device*>\* ... WITH COPY_ONLY ...</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8d09-127">Если параметр COPY_ONLY указан одновременно с параметром DIFFERENTIAL, он не имеет эффекта.</span><span class="sxs-lookup"><span data-stu-id="a8d09-127">COPY_ONLY has no effect when specified with the DIFFERENTIAL option.</span></span>  
  
-   <span data-ttu-id="a8d09-128">Для резервных копий журнала только для копирования:</span><span class="sxs-lookup"><span data-stu-id="a8d09-128">For a copy-only log backup:</span></span>  
  
     <span data-ttu-id="a8d09-129">Резервное копирование журнала *database_name* в *\<*backup_device*>* ... С COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="a8d09-129">BACKUP LOG *database_name* TO *\<*backup_device*>* ... WITH COPY_ONLY ...</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a8d09-130">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8d09-130">Using PowerShell</span></span>  
  
<span data-ttu-id="a8d09-131">Используйте командлет `Backup-SqlDatabase` с параметром `-CopyOnly`.</span><span class="sxs-lookup"><span data-stu-id="a8d09-131">Use the `Backup-SqlDatabase` cmdlet with the `-CopyOnly` parameter.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a8d09-132">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="a8d09-132">Related Tasks</span></span>  

### <a name="to-create-a-full-or-log-backup"></a><span data-ttu-id="a8d09-133">Создание полной резервной копии или резервной копии журнала</span><span class="sxs-lookup"><span data-stu-id="a8d09-133">To create a full or log backup</span></span>
  
-   [<span data-ttu-id="a8d09-134">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a8d09-134">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="a8d09-135">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a8d09-135">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
### <a name="to-view-copy-only-backups"></a><span data-ttu-id="a8d09-136">Просмотр резервных копий только для копирования</span><span class="sxs-lookup"><span data-stu-id="a8d09-136">To view copy-only backups</span></span>
  
-   [<span data-ttu-id="a8d09-137">backupset (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a8d09-137">backupset &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
### <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><span data-ttu-id="a8d09-138">Настройка и использование поставщика SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8d09-138">To set up and use the SQL Server PowerShell provider</span></span>
  
-   [<span data-ttu-id="a8d09-139">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8d09-139">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  

## <a name="see-also"></a><span data-ttu-id="a8d09-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8d09-140">See Also</span></span>  
 <span data-ttu-id="a8d09-141">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a8d09-141">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="a8d09-142">[Модели восстановления (SQL Server)](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a8d09-142">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="a8d09-143">[Копирование баз данных путем создания и восстановления резервных копий](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="a8d09-143">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="a8d09-144">Обзор процессов восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a8d09-144">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
