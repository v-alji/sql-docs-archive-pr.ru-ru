---
title: Управление таблицами Filetable | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], security
- FileTables [SQL Server], managing access
ms.assetid: 93af982c-b4fe-4be0-8268-11f86dae27e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a15a914c243f1fafd3b913d98113e984bf533086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731726"
---
# <a name="manage-filetables"></a><span data-ttu-id="ae8a7-102">Управление таблицами FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-102">Manage FileTables</span></span>
  <span data-ttu-id="ae8a7-103">Описывает стандартные административные задачи по управлению таблицами FileTables.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-103">Describes common administrative tasks for managing FileTables.</span></span>  
  
##  <a name="how-to-get-a-list-of-filetables-and-related-objects"></a><a name="HowToEnumerate"></a> <span data-ttu-id="ae8a7-104">Как получить список таблиц FileTable и связанных объектов</span><span class="sxs-lookup"><span data-stu-id="ae8a7-104">How To: Get a List of FileTables and Related Objects</span></span>  
 <span data-ttu-id="ae8a7-105">Чтобы получить список таблиц FileTable, выполните запрос к одному из следующих представлений каталогов:</span><span class="sxs-lookup"><span data-stu-id="ae8a7-105">To get a list of FileTables, query one of the following catalog views:</span></span>  
  
-   [<span data-ttu-id="ae8a7-106">sys.filetables (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ae8a7-106">sys.filetables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-filetables-transact-sql)  
  
-   <span data-ttu-id="ae8a7-107">[sys.tables (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Проверьте значение в столбце **is_filetable**.)</span><span class="sxs-lookup"><span data-stu-id="ae8a7-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Check the value of the **is_filetable** column.)</span></span>  
  
```sql  
SELECT * FROM sys.filetables;  
GO  
  
SELECT * FROM sys.tables WHERE is_filetable = 1;  
GO  
```  
  
 <span data-ttu-id="ae8a7-108">Чтобы получить список системных объектов, которые были созданы при создании связанных таблиц FileTable, выполните запрос к представлению каталога [sys.filetable_system_defined_objects (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae8a7-108">To get a list of the system-defined objects that were created when the associated FileTables were created, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
SELECT object_id, OBJECT_NAME(object_id) AS 'Object Name'  
    FROM sys.filetable_system_defined_objects  
    WHERE object_id = filetable_object_id;  
GO  
```  
  
##  <a name="disabling-and-re-enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsDisabling"></a> <span data-ttu-id="ae8a7-109">Отключить и снова включить нетранзакционный доступ на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="ae8a7-109">Disabling and Re-enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="ae8a7-110">Для монопольного доступа, необходимого для выполнения некоторых задач администрирования, может потребоваться временно отключить нетранзакционный доступ.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-110">To acquire the exclusive access that is required for certain administrative tasks, you may have to disable non-transactional access temporarily.</span></span>  
  
 <span data-ttu-id="ae8a7-111">**Поведение инструкции ALTER DATABASE при изменении уровня нетранзакционного доступа**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-111">**Behavior of the ALTER DATABASE statement when changing the level of non-transactional access**</span></span>  
  
-   <span data-ttu-id="ae8a7-112">В случае задания для нетранзакционного доступа значения READ_ONLY или OFF команда ALTER DATABASE не возвращает управление пользователю, пока имеются открытые дескрипторы файлов, конфликтующие с запрошенной операцией.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-112">When you set non-transactional access to READ_ONLY or OFF, the ALTER DATABASE command does not return control to the user as long as there are open file handles that conflict with the requested operation.</span></span> <span data-ttu-id="ae8a7-113">Дескрипторы файлов, которые конфликтуют с этой операцией:</span><span class="sxs-lookup"><span data-stu-id="ae8a7-113">The file handles that conflict with this operation include the following:</span></span>  
  
    -   <span data-ttu-id="ae8a7-114">Если доступ установлен в режим **NONE**, то все открытые дескрипторы файлов.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-114">When you are setting access to **NONE**, all open file handles.</span></span>  
  
    -   <span data-ttu-id="ae8a7-115">Если доступ установлен в режим **READ_ONLY**, все дескрипторы файлов открыты для записи.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-115">When you are setting access to **READ_ONLY**, all file handles opened for write access.</span></span>  
  
     <span data-ttu-id="ae8a7-116">Сведения об уничтожении открытых дескрипторов файлов см. в подразделе [Уничтожение открытых дескрипторов файлов, связанных с таблицей FileTable](#BasicsKilling) этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-116">For information about killing open file handles, see [Killing Open File Handles Associated with a FileTable](#BasicsKilling) in this topic.</span></span>  
  
     <span data-ttu-id="ae8a7-117">Если команда ALTER DATABASE отменяется или истекает ее время ожидания, уровень транзакционного доступа изменен не будет.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-117">If the ALTER DATABASE command is canceled or ends with a timeout, then the level of transactional access is not changed.</span></span>  
  
-   <span data-ttu-id="ae8a7-118">При вызове инструкции ALTER DATABASE с предложением WITH \<termination> (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT) все открытые нетранзакционные дескрипторы файлов будут уничтожены.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-118">If you call the ALTER DATABASE statement with a WITH \<termination> clause (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), then all open non-transactional file handles are killed.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ae8a7-119">При уничтожении открытых дескрипторов файлов пользователи могут потерять несохраненные данные.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-119">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="ae8a7-120">Такое поведение согласуется с поведением самой файловой системы.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-120">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
 <span data-ttu-id="ae8a7-121">**Последствия отключения нетранзакционного доступа**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-121">**Effects of disabling non-transactional access**</span></span>  
  
 <span data-ttu-id="ae8a7-122">Изменение уровня нетранзакционного доступа на уровне базы данных оказывает следующее влияние на каталоги FileTable, вложенные в каталог уровня базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-122">Changing the level of non-transactional access at the database level has the following effects on the FileTable directories under the database-level directory:</span></span>  
  
-   <span data-ttu-id="ae8a7-123">Если доступ установлен в режим **NONE**, все каталоги FileTable и их содержимое становятся недоступными и невидимыми.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-123">When you set access to **NONE**, then all the FileTable directories and their contents are no longer accessible or visible.</span></span>  
  
-   <span data-ttu-id="ae8a7-124">Если доступ установлен в режим **READ_ONLY**, все каталоги FileTable и их содержимое доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-124">When you set access to **READ_ONLY**, then all the FileTable directories and their contents are also read-only.</span></span>  
  
 <span data-ttu-id="ae8a7-125">Отключение FILESTREAM на уровне экземпляра оказывает следующее влияние на каталоги уровня базы данных этого экземпляра и вложенные в них каталоги FileTable.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-125">Disabling FILESTREAM at the instance level has the following effects on the database-level directories on that instance, and the FileTable directories under them:</span></span>  
  
-   <span data-ttu-id="ae8a7-126">Если FILESTREAM отключен на уровне экземпляра, невидимыми будут все каталоги уровня базы данных этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-126">None of the database-level directories on the instance are visible if FILESTREAM is disabled at the instance level.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-non-transactional-access-at-the-database-level"></a><a name="HowToDisable"></a> <span data-ttu-id="ae8a7-127">Как отключить и снова включить нетранзакционный доступ на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="ae8a7-127">How To: Disable and Re-enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="ae8a7-128">Дополнительные сведения см. в разделе [Параметры ALTER DATABASE SET (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="ae8a7-128">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="ae8a7-129">**Отключение полного нетранзакционного доступа**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-129">**To disable full non-transactional access**</span></span>  
 <span data-ttu-id="ae8a7-130">Вызовите инструкцию **ALTER DATABASE** и задайте параметру **NON_TRANSACTED_ACCESS** значение **READ_ONLY** или **OFF**.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-130">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **READ_ONLY** or **OFF**.</span></span>  
  
```sql  
-- Disable write access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = READ_ONLY );  
GO  
  
-- Disable non-transactional access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = OFF );  
GO  
```  
  
 <span data-ttu-id="ae8a7-131">**Повторное включение полного нетранзакционного доступа**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-131">**To re-enable full non-transactional access**</span></span>  
 <span data-ttu-id="ae8a7-132">Вызовите инструкцию **ALTER DATABASE** и задайте параметру **NON_TRANSACTED_ACCESS** значение **FULL**.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-132">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **FULL**.</span></span>  
  
```sql  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL );  
GO  
```  
  
###  <a name="how-to-ensure-the-visibility-of-the-filetables-in-a-database"></a><a name="visible"></a> <span data-ttu-id="ae8a7-133">Как обеспечить видимость таблиц FileTables в базе данных</span><span class="sxs-lookup"><span data-stu-id="ae8a7-133">How to: Ensure the Visibility of the FileTables in a Database</span></span>  
 <span data-ttu-id="ae8a7-134">Каталог уровня базы данных и находящиеся в нем каталоги FileTable отображаются при соблюдении всех следующих условий.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-134">A database-level directory and the FileTable directories under it are visible when all of these conditions are true:</span></span>  
  
1.  <span data-ttu-id="ae8a7-135">Функция FILESTREAM включена на уровне экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-135">FILESTREAM is enabled at the instance level.</span></span>  
  
2.  <span data-ttu-id="ae8a7-136">Нетранзакционный доступ включен на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-136">Non-transactional access is enabled at the database level.</span></span>  
  
3.  <span data-ttu-id="ae8a7-137">На уровне базы данных указан допустимый каталог.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-137">A valid directory has been specified at the database level.</span></span>  
  
##  <a name="disabling-and-re-enabling-the-filetable-namespace-at-the-table-level"></a><a name="BasicsEnabling"></a> <span data-ttu-id="ae8a7-138">Отключение и повторное включение пространства имен FileTable на уровне таблицы</span><span class="sxs-lookup"><span data-stu-id="ae8a7-138">Disabling and Re-enabling the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="ae8a7-139">При отключении пространства имен FileTable отключаются все системные ограничения и триггеры, созданные в таблице FileTable.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-139">Disabling the FileTable namespace disables all the system-defined constraints and triggers that were created with the FileTable.</span></span> <span data-ttu-id="ae8a7-140">Это полезно в случаях, когда требуется значительная реорганизация таблицы FileTable с помощью операций [!INCLUDE[tsql](../../includes/tsql-md.md)] без дополнительных затрат на применение семантики FileTable.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-140">This is useful in cases where a FileTable has to be reorganized on a large scale by using [!INCLUDE[tsql](../../includes/tsql-md.md)] operations without incurring the expense of enforcing FileTable semantics.</span></span> <span data-ttu-id="ae8a7-141">Но это может привести к несогласованному состоянию таблицы FileTable, что может не позволить снова включить пространство имен FileTable.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-141">However these operations can leave the FileTable in an inconsistent state, and can prevent the re-enabling of the FileTable namespace.</span></span>  
  
 <span data-ttu-id="ae8a7-142">Отключение пространства имен FileTable имеет следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-142">Disabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="ae8a7-143">Столбцы и данные FileTable не будут физически удалены из таблицы.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-143">FileTable columns and data are not physically dropped from the table.</span></span>  
  
-   <span data-ttu-id="ae8a7-144">Каталог таблицы FileTable, а также содержащиеся в нем файлы и каталоги удаляются из файловой системы и становятся недоступными для файлового ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-144">The FileTable directory and the files and directories that it contains disappear from the file system and are not available for file i/o access.</span></span>  
  
-   <span data-ttu-id="ae8a7-145">Системные столбцы таблицы FileTable нельзя удалить и создать заново, в остальном же они ведут себя так же, как любые другие столбцы в операциях DML.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-145">System-defined FileTable columns cannot be dropped and recreated; otherwise, however, they behave like ordinary columns for DML operations.</span></span>  
  
-   <span data-ttu-id="ae8a7-146">Открытые дескрипторы файлов не позволяют отключить ограничения FileTable, поскольку для выполнения этой операции требуется заблокировать схему в таблице.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-146">Open file handles prevent the FileTable constraints from being disabled, since this operation requires a schema lock on the table.</span></span>  
  
-   <span data-ttu-id="ae8a7-147">Действие семантики FileTable, включая системные ограничения и триггеры, прекращается после отключения пространства имен FileTable.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-147">Enforcement of all the FileTable semantics, including system-defined constraints and triggers, stops after the FileTable namespace is disabled.</span></span>  
  
 <span data-ttu-id="ae8a7-148">Повторное включение пространства имен FileTable имеет следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-148">Re-enabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="ae8a7-149">Таблица FileTable проверяется на согласованность.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-149">The FileTable is checked for consistency.</span></span> <span data-ttu-id="ae8a7-150">При обнаружении несогласованности возникает ошибка, и таблица FileTable остается отключенной. В противном случае, таблица FileTable будет включена.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-150">If inconsistencies are found, then an error is raised and the FileTable remains disabled; otherwise, the FileTable is re-enabled.</span></span>  
  
-   <span data-ttu-id="ae8a7-151">Действие семантики FileTable, включая системные ограничения и триггеры, будет восстановлено.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-151">The enforcement of FileTable semantics, including system-defined constraints and triggers, is restored.</span></span>  
  
-   <span data-ttu-id="ae8a7-152">Каталог таблицы FileTable, а также содержащиеся в нем файлы и каталоги появляются в файловой системе и становятся доступными для файлового ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-152">The FileTable directory and the files and directories that it contains become visible in the file system and become available for file i/o access.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-the-filetable-namespace-at-the-table-level"></a><a name="HowToEnableNS"></a> <span data-ttu-id="ae8a7-153">Как отключить и снова включить пространство имен FileTable на уровне таблицы</span><span class="sxs-lookup"><span data-stu-id="ae8a7-153">How To: Disable and Re-enable the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="ae8a7-154">Вызовите инструкцию ALTER TABLE с параметром **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** .</span><span class="sxs-lookup"><span data-stu-id="ae8a7-154">Call the ALTER TABLE statement with the **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** option.</span></span>  
  
 <span data-ttu-id="ae8a7-155">**Отключение пространства имен FileTable**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-155">**To disable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    DISABLE FILETABLE_NAMESPACE;  
GO  
```  
  
 <span data-ttu-id="ae8a7-156">**Повторное включение пространства имен FileTable**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-156">**To re-enable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    ENABLE FILETABLE_NAMESPACE;  
GO  
```  
  
##  <a name="killing-open-file-handles-associated-with-a-filetable"></a><a name="BasicsKilling"></a> <span data-ttu-id="ae8a7-157">Уничтожение открытых дескрипторов файлов, связанных с таблицей FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-157">Killing Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="ae8a7-158">Открытые дескрипторы файлов, хранящихся в таблице FileTable, могут помешать монопольному доступу, который требуется для выполнения определенных задач по администрированию.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-158">Open handles to the files stored in a FileTable can prevent the exclusive access that is required for certain administrative tasks.</span></span> <span data-ttu-id="ae8a7-159">Для включения срочных задач может потребоваться уничтожить открытые дескрипторы файлов, связанные с одной или несколькими таблицами FileTable.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-159">To enable urgent tasks, you may have to kill open file handles associated with one or more FileTables.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ae8a7-160">При уничтожении открытых дескрипторов файлов пользователи могут потерять несохраненные данные.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-160">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="ae8a7-161">Такое поведение согласуется с поведением самой файловой системы.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-161">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
###  <a name="how-to-get-a-list-of-open-file-handles-associated-with-a-filetable"></a><a name="HowToListOpen"></a> <span data-ttu-id="ae8a7-162">Как получить список открытых дескрипторов файлов, связанных с таблицей FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-162">How To: Get a List of Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="ae8a7-163">Выполните запрос к представлению каталога [sys.dm_filestream_non_transacted_handles (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae8a7-163">Query the catalog view [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.dm_filestream_non_transacted_handles;  
GO  
```  
  
###  <a name="how-to-kill-open-file-handles-associated-with-a-filetable"></a><a name="HowToKill"></a> <span data-ttu-id="ae8a7-164">Как уничтожить открытые дескрипторы файлов, связанные с таблицей FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-164">How To: Kill Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="ae8a7-165">Чтобы уничтожить все открытые дескрипторы файлов в базе данных или в таблице FileTable либо конкретный дескриптор, вызовите хранимую процедуру [sp_kill_filestream_non_transacted_handles (Transact-SQL)](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles).</span><span class="sxs-lookup"><span data-stu-id="ae8a7-165">Call the stored procedure [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) with the appropriate arguments to kill all open file handles in the database or in the FileTable, or to kill a specific handle.</span></span>  
  
```  
USE database_name;  
  
-- Kill all open handles in all the filetables in the database.  
EXEC sp_kill_filestream_non_transacted_handles;  
GO  
  
-- Kill all open handles in a single filetable.  
EXEC sp_kill_filestream_non_transacted_handles @table_name = 'filetable_name';  
GO  
  
-- Kill a single handle.  
EXEC sp_kill_filestream_non_transacted_handles @handle_id = integer_handle_id;  
GO  
```  
  
###  <a name="how-to-identify-the-locks-held-by-filetables"></a><a name="HowToIdentifyLocks"></a> <span data-ttu-id="ae8a7-166">Как определить блокировки, имеющиеся в таблицах FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-166">How to: Identify the Locks Held by FileTables</span></span>  
 <span data-ttu-id="ae8a7-167">Большинство блокировок в таблице FileTable связано с файлами, открытыми приложениями.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-167">Most locks taken by FileTables correspond to files opened by applications.</span></span>  
  
 <span data-ttu-id="ae8a7-168">**Определение открытых файлов и связанных с ними блокировок**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-168">**To identify open files and the associated locks**</span></span>  
 <span data-ttu-id="ae8a7-169">Объедините поле **request_owner_id** динамического административного представления [sys.dm_tran_locks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) с полем **fcb_id** динамического административного представления [sys.dm_filestream_non_transacted_handles (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae8a7-169">Join the **request_owner_id** field in the dynamic management view [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) with the **fcb_id** field in [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span> <span data-ttu-id="ae8a7-170">В некоторых случаях блокировка связана с несколькими открытыми файлами.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-170">In some cases, the lock does not correspond to a single open file handle.</span></span>  
  
```sql  
SELECT opened_file_name  
    FROM sys.dm_filestream_non_transacted_handles  
    WHERE fcb_id IN  
        ( SELECT request_owner_id FROM sys.dm_tran_locks );  
GO  
```  
  
##  <a name="filetable-security"></a><a name="BasicsSecurity"></a> <span data-ttu-id="ae8a7-171">Безопасность таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-171">FileTable Security</span></span>  
 <span data-ttu-id="ae8a7-172">Файлы и каталоги, хранящиеся в таблицах FileTable, защищаются только средствами безопасности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-172">The files and directories stored in FileTables are secured by SQL Server security only.</span></span> <span data-ttu-id="ae8a7-173">Средства безопасности на уровне таблицы и столбцов применяются для доступа файловой системы, а также для доступа [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae8a7-173">Table and column-based security is enforced for file system access as well as [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="ae8a7-174">API-интерфейсы безопасности файловой системы Windows и параметры ACL не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-174">Windows file system security APIs and ACL settings are not supported.</span></span>  
  
 <span data-ttu-id="ae8a7-175">Права и разрешения на доступ, применимые к группам файлов и контейнерам FILESTREAM, также применяются и к таблице FileTable, поскольку данные файлов хранятся в столбце FILESTREAM таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-175">The security and access permissions that are applicable to FILESTREAM filegroups and containers also apply to FileTables, since the file data is stored as a FILESTREAM column in the FileTable.</span></span>  
  
 <span data-ttu-id="ae8a7-176">**Безопасность FileTable и доступ Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-176">**FileTable Security and Transact-SQL Access**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="ae8a7-177">Защита доступа к данным из таблицы FileTable обеспечивается так же, как и защита доступа к любой другой таблице.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-177">access to data in FileTables is secured in the same way as any other table.</span></span> <span data-ttu-id="ae8a7-178">Соответствующие проверки безопасности на уровне таблицы и столбца выполняются для каждой операции, которая производит доступ или изменение данных.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-178">Appropriate table and column-level security checks are done for every operation that accesses or changes the data.</span></span>  
  
 <span data-ttu-id="ae8a7-179">**Безопасность таблиц FileTable и доступ файловой системы**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-179">**FileTable Security and File System Access**</span></span>  
 <span data-ttu-id="ae8a7-180">Для открытия дескриптора файла или каталога, хранящегося в таблице FileTable, API-интерфейсам файловой системы требуются соответствующие разрешения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на всю строку таблицы FileTable (то есть разрешение на уровне таблицы).</span><span class="sxs-lookup"><span data-stu-id="ae8a7-180">File system APIs require appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions on the entire row in the FileTable (that is, table-level permission) to open a handle to a file or directory stored in the FileTable.</span></span> <span data-ttu-id="ae8a7-181">Если у пользователя нет соответствующего разрешения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на любой столбец таблицы FileTable, то доступ к файловой системе будет запрещен.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-181">If the user does not have the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission on any column in the FileTable, then file system access is denied.</span></span>  
  
##  <a name="backup-and-filetables"></a><a name="OtherBackup"></a> <span data-ttu-id="ae8a7-182">Резервное копирование и таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-182">Backup and FileTables</span></span>  
 <span data-ttu-id="ae8a7-183">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется для резервного копирования таблицы FileTable, то резервная копия данных FILESTREAM создается со структурированными данными в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-183">When you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to back up a FileTable, the FILESTREAM data is backed up with the structured data in the database.</span></span> <span data-ttu-id="ae8a7-184">Если резервное копирование данных FILESTREAM при помощи реляционных данных выполнять нежелательно, для исключения файловых групп FILESTREAM можно воспользоваться частичным резервным копированием.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-184">If you do not want to back up FILESTREAM data with relational data, you can use a partial backup to exclude FILESTREAM filegroups.</span></span>  
  
 <span data-ttu-id="ae8a7-185">**Согласованность транзакций резервных копий таблиц FileTable**</span><span class="sxs-lookup"><span data-stu-id="ae8a7-185">**Transactional Consistency of FileTable Backups**</span></span>  
  
 <span data-ttu-id="ae8a7-186">Многие средства и операции администрирования (включая резервное копирование, резервное копирование журналов и репликацию транзакций) осуществляют чтение транзакционно согласованных данных путем чтения журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-186">Many administrative tools and operations, (including backup, log backup, and transactional replication) read transactionally consistent data by reading the transaction logs.</span></span> <span data-ttu-id="ae8a7-187">В это время они считывают все данные FILESTREAM, обновленные в рамках транзакции.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-187">At this time, they read any FILESTREAM data updated as part of a transaction.</span></span> <span data-ttu-id="ae8a7-188">Если нетранзакционный доступ не включен на уровне базы данных, эти средства и операции работают в режиме полной транзакционной согласованности.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-188">When non-transactional access is not enabled at the database level, these tools and operations work with full transactional consistency.</span></span>  
  
 <span data-ttu-id="ae8a7-189">Однако, когда включен полный нетранзакционный доступ, таблица FileTable может содержать данные, которые были обновлены (с помощью нетранзакционного обновления) уже после выполнения транзакции, которую средство или процесс считывает из журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-189">However, when full non-transactional access is enabled, then a FileTable could contain data that was updated more recently (through a non-transactional update) than the transaction that the tool or process is reading from the transaction log.</span></span> <span data-ttu-id="ae8a7-190">Это означает, что операция восстановления на момент времени для определенной транзакции может содержать данные FILESTREAM более свежие, чем транзакция.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-190">This means that a "point in time" restore operation to a specific transaction may contain FILESTREAM data that is more recent than that transaction.</span></span> <span data-ttu-id="ae8a7-191">Это ожидаемое поведение при включенном нетранзакционном обновлении для таблиц FileTables.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-191">This is the expected behavior when non-transactional updates are allowed on FileTables.</span></span>  
  
##  <a name="sql-server-profiler-and-filetables"></a><a name="Monitor"></a> <span data-ttu-id="ae8a7-192">Приложение SQL Server Profiler и таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-192">SQL Server Profiler and FileTables</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ae8a7-193">Profiler может включать в трассировку операции Windows по открытию и закрытию файлов, хранящихся в таблице FileTable.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-193">Profiler can capture the Windows File Open and File Close operations in trace output for files that are stored in a FileTable.</span></span>  
  
##  <a name="auditing-and-filetables"></a><a name="OtherAuditing"></a> <span data-ttu-id="ae8a7-194">Аудит и таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-194">Auditing and FileTables</span></span>  
 <span data-ttu-id="ae8a7-195">Аудит таблицы FileTable проводится так же, как и для любых других таблиц.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-195">FileTable can be audited just like any other table.</span></span> <span data-ttu-id="ae8a7-196">Однако шаблоны доступа Win32 не являются операциями на основе множеств.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-196">Howerver, Win32 access patterns are not set based operations.</span></span> <span data-ttu-id="ae8a7-197">Одно действие в файловой системе преобразуется в несколько DML-операций Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-197">A single action in the file system translates into multiple Transact-SQL DML operations.</span></span> <span data-ttu-id="ae8a7-198">Например, открытие файла в Microsoft Word преобразуется в несколько операций открытия/закрытия/создания/переименования/удаления и соответствующие DML-операции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-198">For example, opening a file in Microsoft Word translates into multiple open/close/create/rename/delete operations and corresponding Transact-SQL DML activities.</span></span> <span data-ttu-id="ae8a7-199">Это приводит к записи подробных сведений аудита, где трудно сопоставить записи, относящиеся к действиям файловой системы, и соответствующие записи аудита DML в Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-199">This results in verbose audit records where it is hard to correlate records between file system actions and corresponding Transact-SQL DML audit records.</span></span>  
  
##  <a name="dbcc-and-filetables"></a><a name="OtherDBCC"></a> <span data-ttu-id="ae8a7-200">DBCC и таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="ae8a7-200">DBCC and FileTables</span></span>  
 <span data-ttu-id="ae8a7-201">С помощью инструкции DBCC CHECKCONSTRAINTS можно проверить ограничения для таблицы FileTable, включая системные ограничения.</span><span class="sxs-lookup"><span data-stu-id="ae8a7-201">You can use DBCC CHECKCONSTRAINTS to validate the constraints on a FileTable including system-defined constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8a7-202">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae8a7-202">See Also</span></span>  
 <span data-ttu-id="ae8a7-203">[Совместимость FileTable с другими компонентами SQL Server](filetable-compatibility-with-other-sql-server-features.md) </span><span class="sxs-lookup"><span data-stu-id="ae8a7-203">[FileTable Compatibility with Other SQL Server Features](filetable-compatibility-with-other-sql-server-features.md) </span></span>  
 [<span data-ttu-id="ae8a7-204">Инструкции FileTable языка DDL, функции, хранимые процедуры и представления</span><span class="sxs-lookup"><span data-stu-id="ae8a7-204">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
