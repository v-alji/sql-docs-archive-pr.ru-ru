---
title: Просмотр или изменение модели восстановления для базы данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], recovery models
- recovery [SQL Server], recovery model
- backing up databases [SQL Server], recovery models
- recovery models [SQL Server], switching
- recovery models [SQL Server], viewing
- database restores [SQL Server], recovery models
- modifying database recovery models
ms.assetid: 94918d1d-7c10-4be7-bf9f-27e00b003a0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889080301109938f0514bd6b81265c100237ab60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734181"
---
# <a name="view-or-change-the-recovery-model-of-a-database-sql-server"></a><span data-ttu-id="23a67-102">Просмотр или изменение модели восстановления базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23a67-102">View or Change the Recovery Model of a Database (SQL Server)</span></span>
  <span data-ttu-id="23a67-103">В этом разделе описан порядок просмотра и изменения модели восстановления базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23a67-103">This topic describes how to view or change the recovery model of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="23a67-104">*Модель восстановления* — это свойство базы данных, которое управляет процессом регистрации транзакций, определяет, требуется ли для журнала транзакций резервное копирование, а также определяет, какие типы операций восстановления доступны.</span><span class="sxs-lookup"><span data-stu-id="23a67-104">A *recovery model* is a database property that controls how transactions are logged, whether the transaction log requires (and allows) backing up, and what kinds of restore operations are available.</span></span> <span data-ttu-id="23a67-105">Существует три модели восстановления: простая модель восстановления, модель полного восстановления и модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="23a67-105">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="23a67-106">Обычно в базе данных используется модель полного восстановления или простая модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="23a67-106">Typically, a database uses the full recovery model or simple recovery model.</span></span> <span data-ttu-id="23a67-107">Базу данных можно в любой момент переключить на использование другой модели восстановления.</span><span class="sxs-lookup"><span data-stu-id="23a67-107">A database can be switched to another recovery model at any time.</span></span> <span data-ttu-id="23a67-108">База данных **model** задает модель восстановления по умолчанию для новых баз данных.</span><span class="sxs-lookup"><span data-stu-id="23a67-108">The **model** database sets the default recovery model of new databases.</span></span>  
  
 <span data-ttu-id="23a67-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="23a67-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="23a67-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="23a67-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="23a67-111">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="23a67-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="23a67-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="23a67-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="23a67-113">**Просмотр и изменение модели восстановления базы данных**</span><span class="sxs-lookup"><span data-stu-id="23a67-113">**To view or change the recovery model of a database, using:**</span></span>  
  
     [<span data-ttu-id="23a67-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23a67-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="23a67-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="23a67-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="23a67-116">**Рекомендуемые действия.**  [После изменения модели восстановления](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="23a67-116">**Follow Up Recommendations:**  [After You Change the Recovery Model](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="23a67-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="23a67-117">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="23a67-118">Перед началом</span><span class="sxs-lookup"><span data-stu-id="23a67-118">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="23a67-119">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="23a67-119">Recommendations</span></span>  
  
-   <span data-ttu-id="23a67-120">Перед переключением с модели полного восстановления или восстановления с неполным протоколированием создайте резервную копию журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="23a67-120">Before switching from the full recovery or bulk-logged recovery model, back up the transaction log.</span></span>  
  
-   <span data-ttu-id="23a67-121">Восстановление на момент времени невозможно в модели с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="23a67-121">Point-in-time recovery is not possible with bulk-logged model.</span></span> <span data-ttu-id="23a67-122">Таким образом, при выполнении транзакций в модели восстановления с неполным протоколированием, которая может потребовать восстановления журнала транзакций, эти операции могут привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="23a67-122">Therefore, if you run transactions under the bulk-logged recovery model that might require a transaction log restore, these transactions could be exposed to data loss.</span></span> <span data-ttu-id="23a67-123">Чтобы до максимума повысить восстанавливаемость данных в сценарии аварийного восстановления, рекомендуется переключаться в модель восстановления с неполным протоколированием только в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="23a67-123">To maximize data recoverability in a disaster-recovery scenario, we recommend that you switch to the bulk-logged recovery model only under the following conditions:</span></span>  
  
    -   <span data-ttu-id="23a67-124">в настоящий момент пользователям запрещен доступ к базе данных;</span><span class="sxs-lookup"><span data-stu-id="23a67-124">Users are currently not allowed in the database.</span></span>  
  
    -   <span data-ttu-id="23a67-125">Во время массовой обработки не было изменений, которые невозможно восстановить без применения резервной копии журнала (например, повторным запуском массовой обработки).</span><span class="sxs-lookup"><span data-stu-id="23a67-125">All modifications made during bulk processing are recoverable without depending on taking a log backup; for example, by re-running the bulk processes.</span></span>  
  
     <span data-ttu-id="23a67-126">Если выполняются эти два условия, то при восстановлении журнала транзакций, созданного в модели восстановления с неполным протоколированием, не возникнет угрозы потери данных.</span><span class="sxs-lookup"><span data-stu-id="23a67-126">If you satisfy these two conditions, you will not be exposed to any data loss while restoring a transaction log that was backed up under the bulk-logged recovery model..</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23a67-127">При переключении на модель полного восстановления в ходе массовой операции режим регистрации массовой операции переключается с минимального протоколирования на полное, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="23a67-127">If you switch to the full recovery model during a bulk operation, the logging of the bulk operation changes from minimal logging to full logging, and vice versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="23a67-128">безопасность</span><span class="sxs-lookup"><span data-stu-id="23a67-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="23a67-129">Permissions</span><span class="sxs-lookup"><span data-stu-id="23a67-129">Permissions</span></span>  
 <span data-ttu-id="23a67-130">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="23a67-130">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="23a67-131">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23a67-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-recovery-model"></a><span data-ttu-id="23a67-132">Просмотр или изменение модели восстановления</span><span class="sxs-lookup"><span data-stu-id="23a67-132">To view or change the recovery model</span></span>  
  
1.  <span data-ttu-id="23a67-133">После подключения к соответствующему экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="23a67-133">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="23a67-134">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="23a67-134">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="23a67-135">Щелкните базу данных правой кнопкой мыши и выберите **Свойства**. Откроется диалоговое окно **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="23a67-135">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="23a67-136">На панели **Выбор страницы** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="23a67-136">In the **Select a page** pane, click **Options**.</span></span>  
  
5.  <span data-ttu-id="23a67-137">Текущая модель восстановления будет указана в списке **Модель восстановления** .</span><span class="sxs-lookup"><span data-stu-id="23a67-137">The current recovery model is displayed in the **Recovery model** list box.</span></span>  
  
6.  <span data-ttu-id="23a67-138">Если нужно изменить модель восстановления, выберите в этом списке другую модель.</span><span class="sxs-lookup"><span data-stu-id="23a67-138">Optionally, to change the recovery model select a different model list.</span></span> <span data-ttu-id="23a67-139">Возможные варианты модели восстановления: **Полная**, **С неполным протоколированием**и **Простая**.</span><span class="sxs-lookup"><span data-stu-id="23a67-139">The choices are **Full**, **Bulk-logged**, or **Simple**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="23a67-140">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="23a67-140">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-recovery-model"></a><span data-ttu-id="23a67-141">Просмотр модели восстановления</span><span class="sxs-lookup"><span data-stu-id="23a67-141">To view the recovery model</span></span>  
  
1.  <span data-ttu-id="23a67-142">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23a67-142">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="23a67-143">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="23a67-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="23a67-144">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="23a67-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="23a67-145">В этом примере описано, как запросить через представление каталога [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) модель восстановления для базы данных **model** .</span><span class="sxs-lookup"><span data-stu-id="23a67-145">This example shows how to query the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to learn the recovery model of the **model** database.</span></span>  
  
```sql  
SELECT name, recovery_model_desc  
   FROM sys.databases  
      WHERE name = 'model' ;  
GO  
  
```  
  
#### <a name="to-change-the-recovery-model"></a><span data-ttu-id="23a67-146">Изменение модели восстановления</span><span class="sxs-lookup"><span data-stu-id="23a67-146">To change the recovery model</span></span>  
  
1.  <span data-ttu-id="23a67-147">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23a67-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="23a67-148">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="23a67-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="23a67-149">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="23a67-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="23a67-150">В этом примере показано, как переключить модель восстановления в базе данных `model` в режим `FULL` с помощью параметра `SET RECOVERY` инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="23a67-150">This example shows how to change the recovery model in the `model` database to `FULL` by using the `SET RECOVERY` option of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement.</span></span>  
  
```sql  
USE master ;  
ALTER DATABASE model SET RECOVERY FULL ;  
```  
  
##  <a name="follow-up-recommendations-after-you-change-the-recovery-model"></a><a name="FollowUp"></a><span data-ttu-id="23a67-151">Дальнейшие рекомендации. После изменения модели восстановления</span><span class="sxs-lookup"><span data-stu-id="23a67-151">Follow Up Recommendations: After You Change the Recovery Model</span></span>  
  
-   <span data-ttu-id="23a67-152">**После переключения с модели полного восстановления на модель восстановления с неполным протоколированием**</span><span class="sxs-lookup"><span data-stu-id="23a67-152">**After switching between the full and bulk-logged recovery models**</span></span>  
  
    -   <span data-ttu-id="23a67-153">После завершения массовых операций немедленно переключитесь обратно на модель полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="23a67-153">After completing the bulk operations, immediately switch back to full recovery mode.</span></span>  
  
    -   <span data-ttu-id="23a67-154">После переключения с модели восстановления с неполным протоколированием в модель полного восстановления создайте резервную копию журнала.</span><span class="sxs-lookup"><span data-stu-id="23a67-154">After switching from the bulk-logged recovery model back to the full recovery model, back up the log.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="23a67-155">Стратегия резервного копирования сохраняется: выполняйте периодически резервное копирование базы данных, журнала и создание разностных резервных копий.</span><span class="sxs-lookup"><span data-stu-id="23a67-155">Your backup strategy remains the same: continue performing periodic database, log, and differential backups.</span></span>  
  
-   <span data-ttu-id="23a67-156">**После переключения с простой модели восстановления**</span><span class="sxs-lookup"><span data-stu-id="23a67-156">**After switching from the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="23a67-157">Сразу же после переключения на модель полного восстановления или на модель восстановления с неполным протоколированием создайте полную или разностную резервную копию базы данных, чтобы начать цепочку журналов.</span><span class="sxs-lookup"><span data-stu-id="23a67-157">Immediately after switching to the full recovery model or bulk-logged recovery model, take a full or differential database backup to start the log chain.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="23a67-158">Переключение на модель полного восстановления или модель восстановления с неполным протоколированием вступает в силу только после создания первой резервной копии данных.</span><span class="sxs-lookup"><span data-stu-id="23a67-158">The switch to the full or bulk-logged recovery model takes effect only after the first data backup.</span></span>  
  
    -   <span data-ttu-id="23a67-159">Запланируйте обычное резервное копирование журнала и соответствующим образом обновите план восстановления.</span><span class="sxs-lookup"><span data-stu-id="23a67-159">Schedule regular log backups, and update your restore plan accordingly.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="23a67-160">Если резервные копии журнала создаются недостаточно часто, журнал транзакций начнет разрастаться до тех пор, пока не переполнит диск.</span><span class="sxs-lookup"><span data-stu-id="23a67-160">If you do not back up the log frequently enough, the transaction log can expand until it runs out of disk space.</span></span>  
  
-   <span data-ttu-id="23a67-161">**После переключения на простую модель восстановления**</span><span class="sxs-lookup"><span data-stu-id="23a67-161">**After switching to the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="23a67-162">Отмените все запланированные задания резервного копирования журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="23a67-162">Discontinue any scheduled jobs for backing up the transaction log.</span></span>  
  
    -   <span data-ttu-id="23a67-163">Убедитесь, что запланировано периодическое резервное копирование базы данных.</span><span class="sxs-lookup"><span data-stu-id="23a67-163">Ensure periodic database backups are scheduled.</span></span> <span data-ttu-id="23a67-164">Резервное копирование базы данных очень важно как для защиты ваших данных, так и для усечения неактивной части журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="23a67-164">Backing up your database is essential both to protect your data and to truncate the inactive portion of the transaction log.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="23a67-165">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="23a67-165">Related Tasks</span></span>  
  
-   [<span data-ttu-id="23a67-166">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23a67-166">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="23a67-167">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23a67-167">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="23a67-168">Создание задания</span><span class="sxs-lookup"><span data-stu-id="23a67-168">Create a Job</span></span>](../../ssms/agent/create-a-job.md)  
  
-   [<span data-ttu-id="23a67-169">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="23a67-169">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="23a67-170">См. также</span><span class="sxs-lookup"><span data-stu-id="23a67-170">Related Content</span></span>  
  
-   <span data-ttu-id="23a67-171">[Планы обслуживания базы данных](../maintenance-plans/maintenance-plans.md) (в электронной документации по [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="23a67-171">[Database Maintenance Plans](../maintenance-plans/maintenance-plans.md) (in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a67-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="23a67-172">See Also</span></span>  
 <span data-ttu-id="23a67-173">[Модели восстановления (SQL Server)](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="23a67-173">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="23a67-174">[Журнал транзакций (SQL Server)](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="23a67-174">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="23a67-175">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23a67-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="23a67-176">[sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23a67-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="23a67-177">Модели восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23a67-177">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
