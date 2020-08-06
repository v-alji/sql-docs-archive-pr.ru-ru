---
title: Резервные копии журнала транзакций (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up [SQL Server], transaction logs
- transaction log backups [SQL Server], creating
- log backups [SQL Server[
- transaction log backups [SQL Server], sequencing
ms.assetid: f4a44a35-0f44-4a42-91d5-d73ac658a3b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 752447d6c38a2df0fcbdce72fbba12edd7a9eeb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734186"
---
# <a name="transaction-log-backups-sql-server"></a><span data-ttu-id="9072e-102">Резервные копии журналов транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9072e-102">Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="9072e-103">Этот раздел относится только к тем базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые используют модель полного восстановления или модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="9072e-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span> <span data-ttu-id="9072e-104">В этом разделе рассматривается создание резервной копии журнала транзакций базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9072e-104">This topic discusses backing up the transaction log of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="9072e-105">Перед созданием любой резервной копии журнала необходимо создать как минимум одну полную резервную копию.</span><span class="sxs-lookup"><span data-stu-id="9072e-105">Minimally, you must have created at least one full backup before you can create any log backups.</span></span> <span data-ttu-id="9072e-106">После этого резервное копирование журнала транзакций может выполняться в любое время, кроме времени другого резервного копирования журнала.</span><span class="sxs-lookup"><span data-stu-id="9072e-106">After that, the transaction log can be backed up at any time unless the log is already being backed up.</span></span> <span data-ttu-id="9072e-107">Рекомендуется периодически производить резервное копирование журнала для снижения вероятности потери результатов работы и для усечения журнала.</span><span class="sxs-lookup"><span data-stu-id="9072e-107">We recommend that you take log backups frequently, both to minimize work loss exposure and to truncate the transaction log.</span></span> <span data-ttu-id="9072e-108">Обычно администратор базы данных время от времени создает полную резервную копию базы данных (например, еженедельно) и дополнительно создает разностные резервные копии через более короткие интервалы, например ежедневно.</span><span class="sxs-lookup"><span data-stu-id="9072e-108">Typically, a database administrator creates a full database backup occasionally, such as weekly, and, optionally, creates a series of differential database backup at a shorter interval, such as daily.</span></span> <span data-ttu-id="9072e-109">Независимо от резервного копирования базы данных администратор создает резервные копии журнала транзакций через еще более короткие интервалы, например каждые 10 минут.</span><span class="sxs-lookup"><span data-stu-id="9072e-109">Independently of the database backups, the database administrator backs up the transaction log at frequent intervals, such as every 10 minutes.</span></span> <span data-ttu-id="9072e-110">При таком подходе к резервному копированию оптимальный интервал между моментами выполнения резервного копирования зависит от множества факторов: важности данных, размера базы данных и рабочей нагрузки сервера.</span><span class="sxs-lookup"><span data-stu-id="9072e-110">For a given type of backup, the optimal interval depends on factors such as the importance of the data, the size of the database, and the workload of the server.</span></span>  
  
 <span data-ttu-id="9072e-111">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="9072e-111">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="9072e-112">Как работает последовательность резервных копий журналов</span><span class="sxs-lookup"><span data-stu-id="9072e-112">How a Sequence of Log Backups Works</span></span>](#LogBackupSequence)  
  
-   [<span data-ttu-id="9072e-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9072e-113">Recommendations</span></span>](#Recommendations)  
  
-   [<span data-ttu-id="9072e-114">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9072e-114">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="9072e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9072e-115">Related Content</span></span>](#RelatedContent)  
  
##  <a name="how-a-sequence-of-log-backups-works"></a><a name="LogBackupSequence"></a><span data-ttu-id="9072e-116">Как работает последовательность резервных копий журналов</span><span class="sxs-lookup"><span data-stu-id="9072e-116">How a Sequence of Log Backups Works</span></span>  
 <span data-ttu-id="9072e-117">Последовательность резервных копий *цепочки журналов* транзакций не зависит от резервных копий данных.</span><span class="sxs-lookup"><span data-stu-id="9072e-117">The sequence of transaction log backups *log chain* is independent of data backups.</span></span> <span data-ttu-id="9072e-118">Например, предположим, что имеется следующая последовательность событий:</span><span class="sxs-lookup"><span data-stu-id="9072e-118">For example, assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="9072e-119">Time</span><span class="sxs-lookup"><span data-stu-id="9072e-119">Time</span></span>|<span data-ttu-id="9072e-120">Событие</span><span class="sxs-lookup"><span data-stu-id="9072e-120">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="9072e-121">8:00</span><span class="sxs-lookup"><span data-stu-id="9072e-121">8:00 A.M.</span></span>|<span data-ttu-id="9072e-122">Резервное копирование базы данных.</span><span class="sxs-lookup"><span data-stu-id="9072e-122">Back up database.</span></span>|  
|<span data-ttu-id="9072e-123">Полдень</span><span class="sxs-lookup"><span data-stu-id="9072e-123">Noon</span></span>|<span data-ttu-id="9072e-124">Резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="9072e-124">Back up transaction log.</span></span>|  
|<span data-ttu-id="9072e-125">16:00</span><span class="sxs-lookup"><span data-stu-id="9072e-125">4:00 P.M.</span></span>|<span data-ttu-id="9072e-126">Резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="9072e-126">Back up transaction log.</span></span>|  
|<span data-ttu-id="9072e-127">18:00</span><span class="sxs-lookup"><span data-stu-id="9072e-127">6:00 P.M.</span></span>|<span data-ttu-id="9072e-128">Резервное копирование базы данных.</span><span class="sxs-lookup"><span data-stu-id="9072e-128">Back up database.</span></span>|  
|<span data-ttu-id="9072e-129">20:00</span><span class="sxs-lookup"><span data-stu-id="9072e-129">8:00 P.M.</span></span>|<span data-ttu-id="9072e-130">Резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="9072e-130">Back up transaction log.</span></span>|  
  
 <span data-ttu-id="9072e-131">Резервная копия журнала транзакций создана в 20:00,</span><span class="sxs-lookup"><span data-stu-id="9072e-131">The transaction log backup created at 8:00 P.M.</span></span> <span data-ttu-id="9072e-132">содержит записи журнала транзакций начиная с 16:00</span><span class="sxs-lookup"><span data-stu-id="9072e-132">contains transaction log records from 4:00 P.M.</span></span> <span data-ttu-id="9072e-133">до 20:00, включая время создания полной резервной копии базы данных в 18:00.</span><span class="sxs-lookup"><span data-stu-id="9072e-133">through 8:00 P.M., spanning the time when the full database backup was created at 6:00 P.M.</span></span> <span data-ttu-id="9072e-134">Последовательность резервных копий журнала транзакций непрерывна, начиная с первого полного резервного копирования базы данных в 8:00</span><span class="sxs-lookup"><span data-stu-id="9072e-134">The sequence of transaction log backups is continuous from the initial full database backup created at 8:00 A.M.</span></span> <span data-ttu-id="9072e-135">и до последнего резервного копирования журнала в 20:00.</span><span class="sxs-lookup"><span data-stu-id="9072e-135">to the last transaction log backup created at 8:00 P.M.</span></span> <span data-ttu-id="9072e-136">Сведения о применении этих резервных копий журналов приводятся в примере в статье [Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9072e-136">For information about how to apply these log backups, see the example in [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9072e-137">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9072e-137">Recommendations</span></span>  
  
-   <span data-ttu-id="9072e-138">Если журнал транзакций поврежден, будут потеряны все результаты работы, начиная с момента самого последнего действительного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="9072e-138">If a transaction log is damaged, work that is performed since the most recent valid backup is lost.</span></span> <span data-ttu-id="9072e-139">Поэтому настоятельно рекомендуется помещать файлы журнала в отказоустойчивое хранилище.</span><span class="sxs-lookup"><span data-stu-id="9072e-139">Therefore we strongly recommend that you put your log files on fault-tolerant storage.</span></span>  
  
-   <span data-ttu-id="9072e-140">Если база данных повреждена или требуется восстановить базу данных, рекомендуется создать [резервную копию заключительного фрагмента журнала](tail-log-backups-sql-server.md) , чтобы можно было восстановить базу данных до текущего момента.</span><span class="sxs-lookup"><span data-stu-id="9072e-140">If a database is damaged or you are about to restore the database, we recommend that you create a [tail-log backup](tail-log-backups-sql-server.md) to enable you to restore the database to the current point in time.</span></span>  
  
-   <span data-ttu-id="9072e-141">По умолчанию каждая успешная операция резервного копирования добавляет запись в журнал ошибок служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и в журнал системных событий.</span><span class="sxs-lookup"><span data-stu-id="9072e-141">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="9072e-142">Если создание резервной копии журналов производится очень часто, это приводит к быстрому накоплению сообщений об успешном завершении. Это приводит к увеличению журналов ошибок, затрудняя поиск других сообщений.</span><span class="sxs-lookup"><span data-stu-id="9072e-142">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="9072e-143">Если работа существующих скриптов не зависит от этих записей, то их можно отключить с помощью флага трассировки 3226.</span><span class="sxs-lookup"><span data-stu-id="9072e-143">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="9072e-144">Дополнительные сведения см. в разделе [Флаги трассировки (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9072e-144">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9072e-145">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9072e-145">Related Tasks</span></span>  
 <span data-ttu-id="9072e-146">**Создание резервной копии журнала транзакций**</span><span class="sxs-lookup"><span data-stu-id="9072e-146">**To create a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="9072e-147">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9072e-147">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="9072e-148"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="9072e-148"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="9072e-149">Описание планирования заданий резервного копирования см. в разделе [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9072e-149">To schedule backup jobs, see [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="9072e-150">См. также</span><span class="sxs-lookup"><span data-stu-id="9072e-150">Related Content</span></span>  
 <span data-ttu-id="9072e-151">Нет.</span><span class="sxs-lookup"><span data-stu-id="9072e-151">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9072e-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="9072e-152">See Also</span></span>  
 <span data-ttu-id="9072e-153">[Журнал транзакций (SQL Server)](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9072e-153">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="9072e-154">[Резервное копирование и восстановление баз данных SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="9072e-154">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="9072e-155">[Резервные копии заключительного фрагмента журнала (SQL Server)](tail-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9072e-155">[Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="9072e-156">Применение резервных копий журналов транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9072e-156">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](transaction-log-backups-sql-server.md)  
  
  
