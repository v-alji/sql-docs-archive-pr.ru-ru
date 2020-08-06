---
title: Восстановление до регистрационного номера транзакции в журнале (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log sequence numbers [SQL Server]
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- LSNs
- database recovery [SQL Server]
- database restores [SQL Server], point in time
ms.assetid: f7b3de5b-198d-448d-8c71-1cdd9239676c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4df55c3468fc009d86cffd58a837d6935f5ce14b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666691"
---
# <a name="recover-to-a-log-sequence-number-sql-server"></a><span data-ttu-id="2a910-102">Восстановление до номера LSN (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2a910-102">Recover to a Log Sequence Number (SQL Server)</span></span>
  <span data-ttu-id="2a910-103">Этот раздел относится только к тем базам данных, которые используют модель полного восстановления или модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="2a910-103">This topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="2a910-104">Можно в качестве точки восстановления во время операции восстановления использовать номер LSN.</span><span class="sxs-lookup"><span data-stu-id="2a910-104">You can use a log sequence number (LSN) to define the recovery point for a restore operation.</span></span> <span data-ttu-id="2a910-105">Однако эта специальная возможность предназначена для средств поставщика, и представляется сомнительным, чтобы она могла оказаться в целом полезной.</span><span class="sxs-lookup"><span data-stu-id="2a910-105">However, this is a specialized feature that is intended for tools vendors and is unlikely to be generally useful.</span></span>  
  
##  <a name="overview-of-log-sequence-numbers"></a><a name="LSNs"></a> <span data-ttu-id="2a910-106">Общие сведения о регистрационных номерах транзакций в журнале</span><span class="sxs-lookup"><span data-stu-id="2a910-106">Overview of Log Sequence Numbers</span></span>  
 <span data-ttu-id="2a910-107">Регистрационные номера транзакций (LSN) в журнале используются во время последовательности восстановления для отслеживания момента времени, на который восстанавливаются данные.</span><span class="sxs-lookup"><span data-stu-id="2a910-107">LSNs are used internally during a RESTORE sequence to track the point in time to which data has been restored.</span></span> <span data-ttu-id="2a910-108">При восстановлении резервной копии данные восстанавливаются к регистрационному номеру транзакции в журнале, который соответствует моменту времени создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="2a910-108">When a backup is restored, the data is restored to the LSN corresponding to the point in time at which the backup was taken.</span></span> <span data-ttu-id="2a910-109">Разностные резервные копии и резервные копии журналов продвигают восстанавливаемую базу данных к более позднему моменту, которому соответствует больший регистрационный номер транзакции в журнале.</span><span class="sxs-lookup"><span data-stu-id="2a910-109">Differential and log backups advance the restored database to a later time, which corresponds to a higher LSN.</span></span>  
  
 <span data-ttu-id="2a910-110">Каждая запись в журнале транзакций однозначно идентифицируется регистрационным номером транзакции в журнале (номером LSN).</span><span class="sxs-lookup"><span data-stu-id="2a910-110">Every record in the transaction log is uniquely identified by a log sequence number (LSN).</span></span> <span data-ttu-id="2a910-111">Регистрационные номера транзакций в журнале упорядочены таким образом, что если два изменения описываются записями в журнале, помеченными номерами LSN1 и LSN2, а LSN2 больше LSN1, то изменение, помеченное номером LSN2, произошло после изменения LSN1.</span><span class="sxs-lookup"><span data-stu-id="2a910-111">LSNs are ordered such that if LSN2 is greater than LSN1, the change described by the log record referred to by LSN2 occurred after the change described by the log record LSN.</span></span>  
  
 <span data-ttu-id="2a910-112">Регистрационный номер транзакции в журнале, в которой произошло важное событие, может оказаться полезен при формировании правильных последовательностей восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a910-112">The LSN of a log record at which a significant event occurred can be useful for constructing correct restore sequences.</span></span> <span data-ttu-id="2a910-113">Так как регистрационные номера LSN упорядочены, их можно сравнивать на равенство и неравенство (т. е.,, **\<**, **>** **=** **\<=**, **>=** ).</span><span class="sxs-lookup"><span data-stu-id="2a910-113">Because LSNs are ordered, they can be compared for equality and inequality (that is, **\<**, **>**, **=**, **\<=**, **>=**).</span></span> <span data-ttu-id="2a910-114">Такие сравнения полезны при построении последовательностей восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a910-114">Such comparisons are useful when constructing restore sequences.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a910-115">Регистрационные номера транзакций в журнале — это значения типа `numeric`(25,0).</span><span class="sxs-lookup"><span data-stu-id="2a910-115">LSNs are values of data type `numeric`(25,0).</span></span> <span data-ttu-id="2a910-116">Арифметические операции (например сложение или вычитание) не имеют смысла и не должны использоваться для регистрационных номеров транзакций в журнале.</span><span class="sxs-lookup"><span data-stu-id="2a910-116">Arithmetic operations (for example, addition or subtraction) are not meaningful and must not be used with LSNs.</span></span>  
  

  
## <a name="viewing-lsns-used-by-backup-and-restore"></a><span data-ttu-id="2a910-117">Просмотр регистрационных номеров транзакций в журнале, используемых при создании и восстановлении резервных копий</span><span class="sxs-lookup"><span data-stu-id="2a910-117">Viewing LSNs Used by Backup and Restore</span></span>  
 <span data-ttu-id="2a910-118">Регистрационный номер транзакции в журнале, которому соответствует данное событие создания резервной копии или восстановления можно просмотреть в следующих источниках:</span><span class="sxs-lookup"><span data-stu-id="2a910-118">The LSN of a log record at which a given backup and restore event occurred is viewable using one or more of the following:</span></span>  
  
-   [<span data-ttu-id="2a910-119">backupset;</span><span class="sxs-lookup"><span data-stu-id="2a910-119">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
-   [<span data-ttu-id="2a910-120">backupfile;</span><span class="sxs-lookup"><span data-stu-id="2a910-120">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)  
  
-   <span data-ttu-id="2a910-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2a910-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span></span>  
  
-   [<span data-ttu-id="2a910-122">инструкция RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="2a910-122">RESTORE HEADERONLY</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="2a910-123">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="2a910-123">RESTORE FILELISTONLY</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="2a910-124">Также регистрационные номера транзакций в журнале появляются в некоторых текстовых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="2a910-124">LSNs also appear in some message texts.</span></span>  
  
## <a name="transact-sql-syntax-for-restoring-to-an-lsn"></a><span data-ttu-id="2a910-125">Синтаксис языка Transact-SQL при восстановлении до номера LSN</span><span class="sxs-lookup"><span data-stu-id="2a910-125">Transact-SQL Syntax for Restoring to an LSN</span></span>  
 <span data-ttu-id="2a910-126">Инструкция [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) позволяет остановить восстановление на транзакции по номеру LSN или непосредственно перед ней следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2a910-126">By using a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, you can stop at or immediately before the LSN, as follows:</span></span>  
  
-   <span data-ttu-id="2a910-127">Используйте предложение WITH STOPATMARK **='** lsn: _<lsn_number>_ **'** , где lsn: *\<lsnNumber>*  — это строка, указывающая, что точкой восстановления является запись в журнале, которая содержит указанный номер LSN.</span><span class="sxs-lookup"><span data-stu-id="2a910-127">Use the WITH STOPATMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record that contains the specified LSN is the recovery point.</span></span>  
  
     <span data-ttu-id="2a910-128">Предложение STOPATMARK выполняет накат до номера LSN, включая указанную запись журнала.</span><span class="sxs-lookup"><span data-stu-id="2a910-128">STOPATMARK roll forwards to the LSN and includes that log record in the roll forward.</span></span>  
  
-   <span data-ttu-id="2a910-129">Используйте предложение WITH STOPBEFOREMARK **='** lsn: _<lsn_number>_ **'** , где lsn: *\<lsnNumber>*  — это строка, указывающая, что запись журнала, стоящая непосредственно перед записью журнала, содержащей номер LSN, является точкой восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a910-129">Use the WITH STOPBEFOREMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record immediately before the log record that contains the specified LSN number is the recovery point.</span></span>  
  
     <span data-ttu-id="2a910-130">Параметр STOPBEFOREMARK выполняет накат до номера LSN, не включая в него указанную запись журнала.</span><span class="sxs-lookup"><span data-stu-id="2a910-130">STOPBEFOREMARK rolls forward to the LSN and excludes that log record from the roll forward.</span></span>  
  
 <span data-ttu-id="2a910-131">Обычно включается или исключается конкретная транзакция.</span><span class="sxs-lookup"><span data-stu-id="2a910-131">Typically, a specific transaction is selected to be included or excluded.</span></span> <span data-ttu-id="2a910-132">Хотя это необязательно, на практике задаваемая запись журнала обычно является записью фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="2a910-132">Although not required, in practice, the specified log record is a transaction-commit record.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2a910-133">Примеры</span><span class="sxs-lookup"><span data-stu-id="2a910-133">Examples</span></span>  
 <span data-ttu-id="2a910-134">В следующем примере предполагается, что база данных `AdventureWorks` была переведена в модель полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a910-134">The following example assumes that the `AdventureWorks` database has been changed to use the full recovery model.</span></span>  
  
```  
RESTORE LOG AdventureWorks FROM DISK = 'c:\adventureworks_log.bak'   
WITH STOPATMARK = 'lsn:15000000040000037'  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2a910-135">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2a910-135">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2a910-136">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2a910-136">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="2a910-137">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2a910-137">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="2a910-138">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2a910-138">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="2a910-139">Восстановление базы данных до точки сбоя в модели полного восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a910-139">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="2a910-140">Восстановление базы данных до помеченной транзакции (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2a910-140">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="2a910-141">Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="2a910-141">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a910-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a910-142">See Also</span></span>  
 <span data-ttu-id="2a910-143">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2a910-143">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="2a910-144">[Журнал транзакций (SQL Server)](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2a910-144">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="2a910-145">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a910-145">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
