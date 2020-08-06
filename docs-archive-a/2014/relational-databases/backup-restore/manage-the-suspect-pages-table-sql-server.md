---
title: Управление таблицей suspect_pages (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
- restoring pages [SQL Server]
- pages [SQL Server], suspect
- pages [SQL Server], restoring
- suspect_pages system table
- suspect pages [SQL Server]
- restoring [SQL Server], pages
ms.assetid: f394d4bc-1518-4e61-97fc-bf184d972e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dd7aea63ae85a16e23ff532c7e18ace3c376a707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668928"
---
# <a name="manage-the-suspect_pages-table-sql-server"></a><span data-ttu-id="e3674-102">Управление таблицей suspect_pages (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e3674-102">Manage the suspect_pages Table (SQL Server)</span></span>
  <span data-ttu-id="e3674-103">В этом разделе описывается управление таблицей **suspect_pages** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с использованием [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3674-103">This topic describes how to manage the **suspect_pages** table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e3674-104">Таблица **suspect_pages** содержит сведения о потенциально поврежденных страницах и используется при принятии решений о необходимости восстановления.</span><span class="sxs-lookup"><span data-stu-id="e3674-104">The **suspect_pages** table is used for maintaining information about suspect pages, and is relevant in helping to decide whether a restore is necessary.</span></span> <span data-ttu-id="e3674-105">Таблица [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) находится в [базе данных msdb](../databases/msdb-database.md).</span><span class="sxs-lookup"><span data-stu-id="e3674-105">The [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) table resides in the [msdb database](../databases/msdb-database.md).</span></span>  
  
 <span data-ttu-id="e3674-106">Страница считается «подозрительной», если при попытке ее чтения компонентом [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] обнаруживается одна из следующих ошибок.</span><span class="sxs-lookup"><span data-stu-id="e3674-106">A page is considered "suspect" when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] encounters one of the following errors when it tries to read a data page:</span></span>  
  
-   <span data-ttu-id="e3674-107">[Ошибка 823](../errors-events/mssqlserver-823-database-engine-error.md) , вызванная циклической проверкой избыточности (CRC), выданной операционной системой, например ошибка диска (некоторые ошибки оборудования)</span><span class="sxs-lookup"><span data-stu-id="e3674-107">An [823 error](../errors-events/mssqlserver-823-database-engine-error.md) that was caused by a cyclic redundancy check (CRC) issued by the operating system, such as a disk error (certain hardware errors)</span></span>  
  
-   <span data-ttu-id="e3674-108">[Ошибка 824](../errors-events/mssqlserver-824-database-engine-error.md), например обрыв страницы (любая логическая ошибка)</span><span class="sxs-lookup"><span data-stu-id="e3674-108">An [824 error](../errors-events/mssqlserver-824-database-engine-error.md), such as a torn page (any logical error)</span></span>  
  
 <span data-ttu-id="e3674-109">Идентификатор каждой "подозрительной" страницы записывается в таблицу **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="e3674-109">The page ID of every suspect page is recorded in the **suspect_pages** table.</span></span> <span data-ttu-id="e3674-110">В эту таблицу [!INCLUDE[ssDE](../../includes/ssde-md.md)] записывает все подозрительные страницы, которые встретились при обработке, в частности:</span><span class="sxs-lookup"><span data-stu-id="e3674-110">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] records any suspect pages encountered during regular processing, such as the following:</span></span>  
  
-   <span data-ttu-id="e3674-111">При обработке запроса необходимо считать страницу.</span><span class="sxs-lookup"><span data-stu-id="e3674-111">A query has to read a page.</span></span>  
  
-   <span data-ttu-id="e3674-112">При выполнении инструкции DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="e3674-112">During a DBCC CHECKDB operation.</span></span>  
  
-   <span data-ttu-id="e3674-113">Во время операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="e3674-113">During a backup operation.</span></span>  
  
 <span data-ttu-id="e3674-114">Во время операции восстановления, исправления DBCC или удаления базы данных в случае необходимости также обновляется таблица **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="e3674-114">The **suspect_pages** table is also updated as necessary during a restore operation, a DBCC repair operation, or a drop database operation.</span></span>  
  
 <span data-ttu-id="e3674-115">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="e3674-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e3674-116">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e3674-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e3674-117">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="e3674-117">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e3674-118">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e3674-118">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e3674-119">**Управление таблицей suspect_pages с помощью:**</span><span class="sxs-lookup"><span data-stu-id="e3674-119">**To manage the suspect_pages table, using:**</span></span>  
  
     [<span data-ttu-id="e3674-120">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3674-120">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e3674-121">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3674-121">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3674-122">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e3674-122">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e3674-123">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="e3674-123">Recommendations</span></span>  
  
-   <span data-ttu-id="e3674-124">**Ошибки, заносящиеся в таблицу suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="e3674-124">**Errors Recorded in suspect_pages Table**</span></span>  
  
     <span data-ttu-id="e3674-125">Таблица **suspect_pages** содержит по одной строке на каждую страницу, в которой обнаружена ошибка с номером 824, но не более 1000 строк.</span><span class="sxs-lookup"><span data-stu-id="e3674-125">The **suspect_pages** table contains one row per page that failed with an 824 error, up to a limit of 1,000 rows.</span></span> <span data-ttu-id="e3674-126">В следующей таблице приводятся ошибки, занесенные в столбец **event_type** таблицы **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="e3674-126">The following table shows errors logged in the **event_type** column of the **suspect_pages** table.</span></span>  
  
    |<span data-ttu-id="e3674-127">Описание ошибки</span><span class="sxs-lookup"><span data-stu-id="e3674-127">Error description</span></span>|<span data-ttu-id="e3674-128">Значение**event_type**</span><span class="sxs-lookup"><span data-stu-id="e3674-128">**event_type** value</span></span>|  
    |-----------------------|---------------------------|  
    |<span data-ttu-id="e3674-129">Ошибка 823, вызванная ошибкой CRC операционной системы, или ошибка 824, не относящаяся к неверной контрольной сумме или обрыву страницы (например, неверный идентификатор страницы).</span><span class="sxs-lookup"><span data-stu-id="e3674-129">823 error caused by an operating system CRC error  or 824 error other than a bad checksum or a torn page (for example, a bad page ID)</span></span>|<span data-ttu-id="e3674-130">1</span><span class="sxs-lookup"><span data-stu-id="e3674-130">1</span></span>|  
    |<span data-ttu-id="e3674-131">Неверная контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e3674-131">Bad checksum</span></span>|<span data-ttu-id="e3674-132">2</span><span class="sxs-lookup"><span data-stu-id="e3674-132">2</span></span>|  
    |<span data-ttu-id="e3674-133">Разрыв страницы</span><span class="sxs-lookup"><span data-stu-id="e3674-133">Torn page</span></span>|<span data-ttu-id="e3674-134">3</span><span class="sxs-lookup"><span data-stu-id="e3674-134">3</span></span>|  
    |<span data-ttu-id="e3674-135">Восстановлена (страница была восстановлена после того, как была помечена поврежденной)</span><span class="sxs-lookup"><span data-stu-id="e3674-135">Restored (The page was restored after it was marked bad)</span></span>|<span data-ttu-id="e3674-136">4</span><span class="sxs-lookup"><span data-stu-id="e3674-136">4</span></span>|  
    |<span data-ttu-id="e3674-137">Исправленная (страница исправлена инструкцией DBCC, AlwaysOn или зеркальным отображением)</span><span class="sxs-lookup"><span data-stu-id="e3674-137">Repaired (DBCC, AlwaysOn, or mirroring repaired the page)</span></span>|<span data-ttu-id="e3674-138">5</span><span class="sxs-lookup"><span data-stu-id="e3674-138">5</span></span>|  
    |<span data-ttu-id="e3674-139">Удалена при выполнении DBCC</span><span class="sxs-lookup"><span data-stu-id="e3674-139">Deallocated by DBCC</span></span>|<span data-ttu-id="e3674-140">7</span><span class="sxs-lookup"><span data-stu-id="e3674-140">7</span></span>|  
  
     <span data-ttu-id="e3674-141">В таблицу **suspect_pages** записываются также нерегулярные ошибки.</span><span class="sxs-lookup"><span data-stu-id="e3674-141">The **suspect_pages** table also records transient errors.</span></span> <span data-ttu-id="e3674-142">Их причиной могут быть ошибки ввода-вывода (например отсоединение кабеля) или временно возникшая ошибка проверки контрольной суммы страницы.</span><span class="sxs-lookup"><span data-stu-id="e3674-142">Sources of transient errors include an I/O error (for example, a cable was disconnected) or a page that temporarily fails a repeated checksum test.</span></span>  
  
-   <span data-ttu-id="e3674-143">**Как компонент Database Engine обновляет таблицу suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="e3674-143">**How the Database Engine Updates the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="e3674-144">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] выполняет с таблицей **suspect_pages** следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e3674-144">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes the following actions on the **suspect_pages** table:</span></span>  
  
    -   <span data-ttu-id="e3674-145">Если таблица не заполнена, она обновляется для каждой ошибки с номером 824 для указания на наличие ошибки; при этом счетчик ошибок увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="e3674-145">If the table is not full, it is updated for every 824 error, to indicate that an error has occurred, and the error counter is incremented.</span></span> <span data-ttu-id="e3674-146">Если страница содержит ошибку, которая впоследствии была исправлена, ее счетчик **number_of_errors** увеличивается на единицу и изменяется значение столбца **last_update** .</span><span class="sxs-lookup"><span data-stu-id="e3674-146">If a page has an error after it is fixed by being repaired, restored, or deallocated, its **number_of_errors** count is incremented and its **last_update** column is updated</span></span>  
  
    -   <span data-ttu-id="e3674-147">После того как указанная страница исправлена операцией восстановления или исправления, в соответствующей строке обновляется столбец **suspect_pages** , указывая, что страница исправлена (**event_type** = 5) или восстановлена (**event_type** = 4).</span><span class="sxs-lookup"><span data-stu-id="e3674-147">After a listed page is fixed by a restore or a repair operation, the operation updates the **suspect_pages** row to indicate that the page is repaired (**event_type** = 5) or restored (**event_type** = 4).</span></span>  
  
    -   <span data-ttu-id="e3674-148">В ходе проверки базы данных (DBCC) все страницы, не содержащие ошибок, помечаются как исправленные (**event_type** = 5) или освобожденные (**event_type** = 7).</span><span class="sxs-lookup"><span data-stu-id="e3674-148">If a DBCC check is run, the check marks any error-free pages as repaired (**event_type** = 5) or deallocated (**event_type** = 7).</span></span>  
  
-   <span data-ttu-id="e3674-149">**Автоматические обновления таблицы suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="e3674-149">**Automatic Updates to the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="e3674-150">Участник зеркального отображения базы данных или реплика группы доступности AlwaysOn обновляет таблицу **suspect_pages** , если попытка чтения страницы из файла данных завершается одной из следующих ошибок.</span><span class="sxs-lookup"><span data-stu-id="e3674-150">A database mirroring partner or AlwaysOn availability replica updates the **suspect_pages** table after an attempt to read a page from a data file fails for one of the following reasons.</span></span>  
  
    -   <span data-ttu-id="e3674-151">Ошибка 823, вызываемая ошибкой CRC операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e3674-151">An 823 error that is caused by an operating system CRC error.</span></span>  
  
    -   <span data-ttu-id="e3674-152">Ошибка 824 (логическая ошибка, например разрыв страницы).</span><span class="sxs-lookup"><span data-stu-id="e3674-152">An 824 error (logical corruption such as a torn page).</span></span>  
  
     <span data-ttu-id="e3674-153">Следующие действия также автоматически обновляют строки в таблице **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="e3674-153">The following actions also automatically update rows in the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="e3674-154">Инструкция DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS обновляет таблицу **suspect_pages** , отмечая освобождение или исправление каждой страницы.</span><span class="sxs-lookup"><span data-stu-id="e3674-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS updates the **suspect_pages** table to indicate each page that it has deallocated or repaired.</span></span>  
  
    -   <span data-ttu-id="e3674-155">Операции полного восстановления, восстановления файла или страницы помечают записи для страниц как восстановленные.</span><span class="sxs-lookup"><span data-stu-id="e3674-155">A full, file, or page RESTORE marks the page entries as restored.</span></span>  
  
     <span data-ttu-id="e3674-156">Следующие действия автоматически удаляют строки из таблицы **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="e3674-156">The following actions automatically delete rows from the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="e3674-157">ALTER DATABASE REMOVE FILE</span><span class="sxs-lookup"><span data-stu-id="e3674-157">ALTER DATABASE REMOVE FILE</span></span>  
  
    -   <span data-ttu-id="e3674-158">DROP DATABASE</span><span class="sxs-lookup"><span data-stu-id="e3674-158">DROP DATABASE</span></span>  
  
-   <span data-ttu-id="e3674-159">**Задачи обслуживания, выполняемые администратором базы данных**</span><span class="sxs-lookup"><span data-stu-id="e3674-159">**Maintenance Role of the Database Administrator**</span></span>  
  
     <span data-ttu-id="e3674-160">За обслуживание таблицы, преимущественно за удаление старых строк, отвечают администраторы базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3674-160">Database administrators are responsible for managing the table, primarily by deleting old rows.</span></span> <span data-ttu-id="e3674-161">Размер таблицы **suspect_pages** ограничен, поэтому после того, как она заполнена, новые ошибки в нее не заносятся.</span><span class="sxs-lookup"><span data-stu-id="e3674-161">The **suspect_pages** table is limited in size, and if it fills, new errors are not logged.</span></span> <span data-ttu-id="e3674-162">Чтобы не допустить переполнения таблицы, администратор базы данных или системный администратор должен вручную удалить из нее старые строки.</span><span class="sxs-lookup"><span data-stu-id="e3674-162">To prevent this table from filling up, the database administrator or system administrator must manually clear out old entries from this table by deleting rows.</span></span> <span data-ttu-id="e3674-163">Поэтому рекомендуется периодически удалять или архивировать строки, у которых **event_type** указывает на восстановление, или строки, значение **last_update** у которых устарело.</span><span class="sxs-lookup"><span data-stu-id="e3674-163">Therefore, we recommend that you periodically delete or archive rows that have an **event_type** of restored or repaired, or rows that have an old **last_update** value.</span></span>  
  
     <span data-ttu-id="e3674-164">Для наблюдения за ситуацией в таблице "suspect_pages" можно использовать [класс событий Database Suspect Data Page](../event-classes/database-suspect-data-page-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="e3674-164">To monitor the activity on the suspect_pages table, you can use the [Database Suspect Data Page Event Class](../event-classes/database-suspect-data-page-event-class.md).</span></span> <span data-ttu-id="e3674-165">Строки иногда добавляются в таблицу **suspect_pages** из-за временных ошибок.</span><span class="sxs-lookup"><span data-stu-id="e3674-165">Rows are sometimes added to the **suspect_pages** table because of transient errors.</span></span> <span data-ttu-id="e3674-166">Однако если в таблицу добавляется множество строк, то, скорее всего, проблема существует в подсистеме ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="e3674-166">If many rows are being added to the table, however, a problem probably exists with the I/O subsystem.</span></span> <span data-ttu-id="e3674-167">Если было замечено резко возросшее количество строк, добавляемых в систему, то рекомендуется провести диагностику подсистемы ввода-вывода на предмет возможных проблем.</span><span class="sxs-lookup"><span data-stu-id="e3674-167">If you notice a sudden increase in the number of rows being added to the table, we recommend that you investigate possible problems in your I/O subsystem.</span></span>  
  
     <span data-ttu-id="e3674-168">Администратор базы данных может также вставлять или обновлять записи.</span><span class="sxs-lookup"><span data-stu-id="e3674-168">A database administrator can also insert or update records.</span></span> <span data-ttu-id="e3674-169">Например, обновление строк может оказаться полезным, если администратор базы данных знает, что какая-нибудь из сомнительных страниц на самом деле исправна, но хочет на время сохранить соответствующую запись.</span><span class="sxs-lookup"><span data-stu-id="e3674-169">For example, updating a row might useful when the database administrator knows that a particular suspect page is actually intact, but wants to preserve the record for a while.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3674-170">безопасность</span><span class="sxs-lookup"><span data-stu-id="e3674-170">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3674-171">Permissions</span><span class="sxs-lookup"><span data-stu-id="e3674-171">Permissions</span></span>  
 <span data-ttu-id="e3674-172">Сведения в таблице **suspect_pages** доступны любому пользователю, имеющему доступ к базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="e3674-172">Anyone with access to **msdb** can read the data in the **suspect_pages** table.</span></span> <span data-ttu-id="e3674-173">Информация в таблице suspect_pages может обновляться любым пользователем, обладающим разрешением UPDATE.</span><span class="sxs-lookup"><span data-stu-id="e3674-173">Anyone with UPDATE permission on the suspect_pages table can update its records.</span></span> <span data-ttu-id="e3674-174">Члены предопределенной роли базы данных **db_owner** в **msdb** или предопределенной роли сервера **sysadmin** могут вставлять, обновлять и удалять записи.</span><span class="sxs-lookup"><span data-stu-id="e3674-174">Members the **db_owner** fixed database role on **msdb** or the **sysadmin** fixed server role can insert, update, and delete records.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e3674-175">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3674-175">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="e3674-176">Управление таблицей suspect_pages</span><span class="sxs-lookup"><span data-stu-id="e3674-176">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="e3674-177">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], разверните его, а затем разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="e3674-177">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="e3674-178">Разверните последовательно узлы **Системные базы данных**, **msdb**, **Таблицы**и **Системные таблицы**.</span><span class="sxs-lookup"><span data-stu-id="e3674-178">Expand **System Databases**, expand **msdb**, expand **Tables**, and then expand **System Tables**.</span></span>  
  
3.  <span data-ttu-id="e3674-179">Разверните узел **dbo.suspect_pages** и щелкните правой кнопкой мыши **Изменить 200 верхних строк**.</span><span class="sxs-lookup"><span data-stu-id="e3674-179">Expand **dbo.suspect_pages** and right-click **Edit Top 200 Rows**.</span></span>  
  
4.  <span data-ttu-id="e3674-180">В окне запроса измените, обновите или удалите необходимые строки.</span><span class="sxs-lookup"><span data-stu-id="e3674-180">In the query window, edit, update, or delete the rows that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e3674-181">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3674-181">Using Transact-SQL</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="e3674-182">Управление таблицей suspect_pages</span><span class="sxs-lookup"><span data-stu-id="e3674-182">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="e3674-183">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3674-183">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3674-184">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e3674-184">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3674-185">Скопируйте следующие примеры в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e3674-185">Copy and paste the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="e3674-186">В следующем примере продемонстрировано удаление некоторых строк из таблицы `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="e3674-186">This example deletes some of the rows from the `suspect_pages` table.</span></span>  
  
```  
-- Delete restored, repaired, or deallocated pages.  
DELETE FROM msdb..suspect_pages  
   WHERE (event_type = 4 OR event_type = 5 OR event_type = 7);  
GO  
  
```  
  
 <span data-ttu-id="e3674-187">В этом примере происходит возврат поврежденных страниц в таблице `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="e3674-187">This example returns the bad pages in the `suspect_pages` table.</span></span>  
  
```  
-- Select nonspecific 824, bad checksum, and torn page errors.  
SELECT * FROM msdb..suspect_pages  
   WHERE (event_type = 1 OR event_type = 2 OR event_type = 3);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3674-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3674-188">See Also</span></span>  
 <span data-ttu-id="e3674-189">[DROP DATABASE (Transact-SQL)](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3674-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 <span data-ttu-id="e3674-190">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3674-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="e3674-191">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3674-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="e3674-192">[DBCC (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3674-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="e3674-193">[Восстановление страниц (SQL Server)](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e3674-193">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 <span data-ttu-id="e3674-194">[suspect_pages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3674-194">[suspect_pages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span></span>  
 <span data-ttu-id="e3674-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="e3674-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span></span>  
 [<span data-ttu-id="e3674-196">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="e3674-196">MSSQLSERVER_824</span></span>](../errors-events/mssqlserver-824-database-engine-error.md)  
  
  
