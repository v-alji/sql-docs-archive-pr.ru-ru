---
title: Сжатие базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkdatabase.f1
helpviewer_keywords:
- shrinking databases
- databases [SQL Server], shrinking
- decreasing database size
- database shrinking [SQL Server]
- reducing database size
ms.assetid: 83afbf74-fd50-4c39-831c-b1f473a50620
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246036bfea6dc8431f878165330f7f0571949897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728330"
---
# <a name="shrink-a-database"></a><span data-ttu-id="cf4a2-102">Сжатие базы данных</span><span class="sxs-lookup"><span data-stu-id="cf4a2-102">Shrink a Database</span></span>
  <span data-ttu-id="cf4a2-103">В этом подразделе содержатся инструкции по сжатию базы данных при помощи обозревателя объектов [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf4a2-103">This topic describes how to shrink a database by using Object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="cf4a2-104">Сжатие файлов данных позволяет освободить неиспользуемое пространство путем перемещения страниц данных с конца файла в незанятое пространство ближе к началу файла.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="cf4a2-105">Когда в конце файла образуется достаточно свободного места, страницы данных в конце файла могут быть освобождены и возвращены в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-105">When enough free space is created at the end of the file, data pages at end of the file can be deallocated and returned to the file system.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cf4a2-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="cf4a2-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cf4a2-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="cf4a2-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cf4a2-108">Размер базы данных нельзя сделать меньше минимального размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-108">The database cannot be made smaller than the minimum size of the database.</span></span> <span data-ttu-id="cf4a2-109">Минимальный размер — это первоначальный размер, заданный при создании базы данных, или последний размер, явно установленный операцией изменения размера файла (например, DBCC SHRINKFILE).</span><span class="sxs-lookup"><span data-stu-id="cf4a2-109">The minimum size is the size specified when the database was originally created, or the last explicit size set by using a file-size-changing operation, such as DBCC SHRINKFILE.</span></span> <span data-ttu-id="cf4a2-110">Если, допустим, база данных была создана с размером 10 МБ и затем увеличилась до 100 МБ, ее можно сжать только до 10 МБ, даже если удалить из нее все данные.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-110">For example, if a database was originally created with a size of 10 MB and grew to 100 MB, the smallest size the database could be reduced to is 10 MB, even if all the data in the database has been deleted.</span></span>  
  
-   <span data-ttu-id="cf4a2-111">Невозможно сжать базу данных во время создания ее резервной копии.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-111">You cannot shrink a database while the database is being backed up.</span></span> <span data-ttu-id="cf4a2-112">И наоборот, нельзя создать резервную копию базы данных во время операции сжатия.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-112">Conversely, you cannot backup a database while a shrink operation on the database is in process.</span></span>  
  
-   <span data-ttu-id="cf4a2-113">Инструкция DBCC SHRINKDATABASE завершится с ошибкой при обнаружении оптимизированного для памяти xVelocity индекса columnstore.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-113">DBCC SHRINKDATABASE will fail when it encounters an xVelocity memory optimized columnstore index.</span></span> <span data-ttu-id="cf4a2-114">Работа, выполненная до встречи с индексом columnstore, будет выполнена успешно, поэтому база данных может иметь меньший размер.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-114">Work completed before encountering the columnstore index will succeed so the database might be smaller.</span></span> <span data-ttu-id="cf4a2-115">Чтобы выполнить инструкцию DBCC SHRINKDATABASE, отключите все индексы columnstore до ее запуска, а затем перестройте индексы columnstore.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-115">To complete DBCC SHRINKDATABASE, disable all columnstore indexes before executing DBCC SHRINKDATABASE, and then rebuild the columnstore indexes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="cf4a2-116">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="cf4a2-116">Recommendations</span></span>  
  
-   <span data-ttu-id="cf4a2-117">Просмотр количества свободного (нераспределенного) пространства в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-117">To view the current amount of free (unallocated) space in the database.</span></span> <span data-ttu-id="cf4a2-118">Дополнительные сведения см. в разделе [Отображение данных и сведений о пространстве журнала для базы данных](display-data-and-log-space-information-for-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="cf4a2-118">For more information, see [Display Data and Log Space Information for a Database](display-data-and-log-space-information-for-a-database.md)</span></span>  
  
-   <span data-ttu-id="cf4a2-119">Обратите внимание на следующие сведения при планировании сжатия базы данных.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-119">Consider the following information when you plan to shrink a database:</span></span>  
  
    -   <span data-ttu-id="cf4a2-120">Наибольший эффект от операции сжатия достигается при ее применении после операции, создающей много неиспользуемого пространства, например после усечения таблицы или удаления таблицы.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-120">A shrink operation is most effective after an operation that creates lots of unused space, such as a truncate table or a drop table operation.</span></span>  
  
    -   <span data-ttu-id="cf4a2-121">Большинству баз данных требуется некоторое свободное пространство для выполнения обычных ежедневных операций.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-121">Most databases require some free space to be available for regular day-to-day operations.</span></span> <span data-ttu-id="cf4a2-122">Если сжатие базы данных производится регулярно, но она снова увеличивается в размерах, это означает, что место, освобожденное при сжатии, необходимо для нормальной работы.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-122">If you shrink a database repeatedly and notice that the database size grows again, this indicates that the space that was shrunk is required for regular operations.</span></span> <span data-ttu-id="cf4a2-123">В таких случаях повторное сжатие базы данных бессмысленно.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-123">In these cases, repeatedly shrinking the database is a wasted operation.</span></span>  
  
    -   <span data-ttu-id="cf4a2-124">Операция сжатия не избавляет от фрагментации индексов в базе данных и обычно приводит к еще более сильной фрагментации.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-124">A shrink operation does not preserve the fragmentation state of indexes in the database, and generally increases fragmentation to a degree.</span></span> <span data-ttu-id="cf4a2-125">Это еще одна причина, по которой не стоит выполнять регулярное сжатие базы данных.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-125">This is another reason not to repeatedly shrink the database.</span></span>  
  
    -   <span data-ttu-id="cf4a2-126">Не следует устанавливать параметр базы данных AUTO_SHRINK в значение ON без достаточных на то оснований.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-126">Unless you have a specific requirement, do not set the AUTO_SHRINK database option to ON.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cf4a2-127">безопасность</span><span class="sxs-lookup"><span data-stu-id="cf4a2-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cf4a2-128">Permissions</span><span class="sxs-lookup"><span data-stu-id="cf4a2-128">Permissions</span></span>  
 <span data-ttu-id="cf4a2-129">Необходимо быть членом предопределенной роли сервера **sysadmin** или предопределенной роли базы данных **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="cf4a2-129">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cf4a2-130">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf4a2-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="cf4a2-131">Сжатие базы данных</span><span class="sxs-lookup"><span data-stu-id="cf4a2-131">To shrink a database</span></span>  
  
1.  <span data-ttu-id="cf4a2-132">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-132">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cf4a2-133">Разверните узел **Базы данных**и щелкните правой кнопкой мыши базу данных, которую нужно сжать.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-133">Expand **Databases**, and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="cf4a2-134">В меню наведите указатель на пункт **Задачи**, **Сжать**и выберите команду **База данных**.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-134">Point to **Tasks**, point to **Shrink**, and then click **Database**.</span></span>  
  
     <span data-ttu-id="cf4a2-135">**База данных**</span><span class="sxs-lookup"><span data-stu-id="cf4a2-135">**Database**</span></span>  
     <span data-ttu-id="cf4a2-136">Отображает имя выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-136">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="cf4a2-137">**Выделенное в данный момент место**</span><span class="sxs-lookup"><span data-stu-id="cf4a2-137">**Current allocated space**</span></span>  
     <span data-ttu-id="cf4a2-138">Отображает суммарное используемое и неиспользуемое пространство для выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-138">Displays the total used and unused space for the selected database.</span></span>  
  
     <span data-ttu-id="cf4a2-139">**Доступное свободное место**</span><span class="sxs-lookup"><span data-stu-id="cf4a2-139">**Available free space**</span></span>  
     <span data-ttu-id="cf4a2-140">Отображает суммарное свободное место для файлов журналов и данных в выбранной базе данных.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-140">Displays the sum of free space in the log and data files of the selected database.</span></span>  
  
     <span data-ttu-id="cf4a2-141">**Реорганизовать файлы перед освобождением неиспользованного места**</span><span class="sxs-lookup"><span data-stu-id="cf4a2-141">**Reorganize files before releasing unused space**</span></span>  
     <span data-ttu-id="cf4a2-142">Установка данного флажка эквивалентна выполнению инструкции DBCC SHRINKDATABASE с заданием целевого процентного параметра.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-142">Selecting this option is equivalent to executing DBCC SHRINKDATABASE specifying a target percent option.</span></span> <span data-ttu-id="cf4a2-143">Снятие этого флажка равнозначно выполнению процедуры DBCC SHRINKDATABASE с параметром TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-143">Clearing this option is equivalent to executing DBCC SHRINKDATABASE with TRUNCATEONLY option.</span></span> <span data-ttu-id="cf4a2-144">По умолчанию при открытии диалогового окна этот флажок не установлен.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-144">By default, this option is not selected when the dialog is opened.</span></span> <span data-ttu-id="cf4a2-145">Если этот флажок установлен, то пользователь должен задать целевое процентное значение.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-145">If this option is selected, the user must specify a target percent option.</span></span>  
  
     <span data-ttu-id="cf4a2-146">**Максимальное свободное пространство в файлах после сжатия**</span><span class="sxs-lookup"><span data-stu-id="cf4a2-146">**Maximum free space in files after shrinking**</span></span>  
     <span data-ttu-id="cf4a2-147">Введите максимальный процент свободного пространства, которое должно остаться в базе данных после ее сжатия.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-147">Enter the maximum percentage of free space to be left in the database files after the database has been shrunk.</span></span> <span data-ttu-id="cf4a2-148">Допустимы значения от 0 до 99.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-148">Permissible values are between 0 and 99.</span></span>  
  
4.  <span data-ttu-id="cf4a2-149">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-149">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cf4a2-150">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cf4a2-150">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="cf4a2-151">Сжатие базы данных</span><span class="sxs-lookup"><span data-stu-id="cf4a2-151">To shrink a database</span></span>  
  
1.  <span data-ttu-id="cf4a2-152">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf4a2-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cf4a2-153">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cf4a2-154">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cf4a2-155">В этом примере инструкция [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) используется для уменьшения размера данных и файлов журнала в базе данных `UserDB` и для выделения `10` процентов свободного пространства в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-155">This example uses [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) to decreases the size of the data and log files in the `UserDB` database and to allow for `10` percent free space in the database.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKDB1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkdb1)]  
  
##  <a name="follow-up-after-you-shrink-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="cf4a2-156">Дальнейшие действия. После сжатия базы данных</span><span class="sxs-lookup"><span data-stu-id="cf4a2-156">Follow Up: After you shrink a database</span></span>  
 <span data-ttu-id="cf4a2-157">Данные, перемещаемые в процессе сжатия файла, могут быть разбросаны по любым доступным местам в файле.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-157">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="cf4a2-158">Это вызывает фрагментацию индекса и может увеличить время выполнения запросов, выполняющих поиск в диапазоне индекса.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-158">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="cf4a2-159">Чтобы устранить фрагментацию, предусмотрите возможность перестроения индексов файла после сжатия.</span><span class="sxs-lookup"><span data-stu-id="cf4a2-159">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf4a2-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf4a2-160">See Also</span></span>  
 <span data-ttu-id="cf4a2-161">[Сжатие файла](shrink-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="cf4a2-161">[Shrink a File](shrink-a-file.md) </span></span>  
 <span data-ttu-id="cf4a2-162">[sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf4a2-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="cf4a2-163">[sys.database_files (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf4a2-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="cf4a2-164">[DBCC (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf4a2-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="cf4a2-165">[DBCC SHRINKFILE (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf4a2-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span></span>  
 [<span data-ttu-id="cf4a2-166">Файлы и файловые группы базы данных</span><span class="sxs-lookup"><span data-stu-id="cf4a2-166">Database Files and Filegroups</span></span>](database-files-and-filegroups.md)  
  
  
