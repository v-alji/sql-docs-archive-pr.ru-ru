---
title: Создание моментального снимка базы данных (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], creating
ms.assetid: 187fbba3-c555-4030-9bdf-0f01994c5230
author: stevestein
ms.author: sstein
ms.openlocfilehash: bae68c2d507e1dd3809e76a9d842b765d72234e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751123"
---
# <a name="create-a-database-snapshot-transact-sql"></a><span data-ttu-id="d64b7-102">создать моментальный снимок базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d64b7-102">Create a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="d64b7-103">Единственный способ создания моментального снимка базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] состоит в использовании [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d64b7-103">The only way to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot is to use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d64b7-104">не поддерживает создание моментальных снимков базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-104">does not support the creation of database snapshots.</span></span>  
  
-   <span data-ttu-id="d64b7-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d64b7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d64b7-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d64b7-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="d64b7-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d64b7-107">Security</span></span>](#Security)  
  
     [<span data-ttu-id="d64b7-108">Рекомендации. Присвоение имен моментальным снимкам базы данных</span><span class="sxs-lookup"><span data-stu-id="d64b7-108">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   <span data-ttu-id="d64b7-109">**Создание моментального снимка базы данных с помощью:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="d64b7-109">**To create a database snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d64b7-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d64b7-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d64b7-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d64b7-111">Prerequisites</span></span>  
 <span data-ttu-id="d64b7-112">База данных-источник, в которой может применяться любая модель восстановления, должна соответствовать следующим предварительным требованиям.</span><span class="sxs-lookup"><span data-stu-id="d64b7-112">The source database, which can use any recovery model, must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="d64b7-113">На экземпляре сервера должен быть запущен выпуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который поддерживает моментальные снимки баз данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-113">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports database snapshot.</span></span> <span data-ttu-id="d64b7-114">Сведения о поддержке моментальных снимков базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] см. в разделе [функции, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="d64b7-114">For information about support for database snapshots in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="d64b7-115">База данных-источник должна быть в режиме в сети, если база данных не является зеркальной в сеансе зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-115">The source database must be online, unless the database is a mirror database within a database mirroring session.</span></span>  
  
-   <span data-ttu-id="d64b7-116">Для создания моментального снимка в зеркальной базе данных эта база данных должна быть в синхронизированном[состоянии зеркального отображения](../../database-engine/database-mirroring/mirroring-states-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d64b7-116">To create a database snapshot on a mirror database, the database must be in the synchronized[mirroring state](../../database-engine/database-mirroring/mirroring-states-sql-server.md).</span></span>  
  
-   <span data-ttu-id="d64b7-117">База данных-источник не может быть настроена в качестве масштабируемой общей базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-117">The source database cannot be configured as a scalable shared database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d64b7-118">Сведения о других существенных соображениях см. в разделе [Моментальные снимки базы данных (SQL Server)](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d64b7-118">For information about other significant considerations, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d64b7-119">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="d64b7-119">Recommendations</span></span>  
 <span data-ttu-id="d64b7-120">В этом разделе обсуждаются следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="d64b7-120">This section discusses the following best practices:</span></span>  
  
-   [<span data-ttu-id="d64b7-121">Рекомендации. Присвоение имен моментальным снимкам базы данных</span><span class="sxs-lookup"><span data-stu-id="d64b7-121">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   [<span data-ttu-id="d64b7-122">Рекомендации. Ограничение количества моментальных снимков базы данных</span><span class="sxs-lookup"><span data-stu-id="d64b7-122">Best Practice: Limiting the Number of Database Snapshots</span></span>](#Limiting_Number)  
  
-   [<span data-ttu-id="d64b7-123">Рекомендации. Клиентские соединения с моментальным снимком базы данных</span><span class="sxs-lookup"><span data-stu-id="d64b7-123">Best Practice: Client Connections to a Database Snapshot</span></span>](#Client_Connections)  
  
####  <a name="best-practice-naming-database-snapshots"></a><a name="Naming"></a> <span data-ttu-id="d64b7-124">Рекомендации. Присвоение имен моментальным снимкам базы данных</span><span class="sxs-lookup"><span data-stu-id="d64b7-124">Best Practice: Naming Database Snapshots</span></span>  
 <span data-ttu-id="d64b7-125">Перед созданием моментальных снимков важно присвоить им правильные имена.</span><span class="sxs-lookup"><span data-stu-id="d64b7-125">Before creating snapshots, it is important to consider how to name them.</span></span> <span data-ttu-id="d64b7-126">Имя каждого моментального снимка базы данных должно быть уникальным в пределах базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-126">Each database snapshot requires a unique database name.</span></span> <span data-ttu-id="d64b7-127">Чтобы упростить управление, моментальному снимку следует присвоить имя, которое позволяет определить базу данных, например:</span><span class="sxs-lookup"><span data-stu-id="d64b7-127">For administrative ease, the name of a snapshot can incorporate information that identifies the database, such as:</span></span>  
  
-   <span data-ttu-id="d64b7-128">Определяет имя исходной базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-128">The name of the source database.</span></span>  
  
-   <span data-ttu-id="d64b7-129">признак того, что новое имя предназначено для моментального снимка;</span><span class="sxs-lookup"><span data-stu-id="d64b7-129">An indication that the new name is for a snapshot.</span></span>  
  
-   <span data-ttu-id="d64b7-130">дату и время создания моментального снимка, порядковый номер или другие сведения, например время в течение дня, которые позволяют отличить моментальные снимки этой базы данных друг от друга.</span><span class="sxs-lookup"><span data-stu-id="d64b7-130">The creation date and time of the snapshot, a sequence number, or some other information, such as time of day, to distinguish sequential snapshots on a given database.</span></span>  
  
 <span data-ttu-id="d64b7-131">Допустим, требуется создать последовательность моментальных снимков базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d64b7-131">For example, consider a series of snapshots for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="d64b7-132">Три ежесуточных моментальных снимка были созданы через шестичасовые интервалы между 6:00.</span><span class="sxs-lookup"><span data-stu-id="d64b7-132">Three daily snapshots are created at 6-hour intervals between 6 A.M.</span></span> <span data-ttu-id="d64b7-133">и 18:00 на основе 24-часового отсчета времени.</span><span class="sxs-lookup"><span data-stu-id="d64b7-133">and 6 P.M., based on a 24-hour clock.</span></span> <span data-ttu-id="d64b7-134">Каждый моментальный снимок хранится 24 часа, после этого он удаляется и заменяется одноименным снимком.</span><span class="sxs-lookup"><span data-stu-id="d64b7-134">Each daily snapshot is kept for 24 hours before being dropped and replaced by a new snapshot of the same name.</span></span> <span data-ttu-id="d64b7-135">Обратите внимание, что имя моментального снимка обозначает час, но не дату создания:</span><span class="sxs-lookup"><span data-stu-id="d64b7-135">Note that each snapshot name indicates the hour, but not the day:</span></span>  
  
```  
AdventureWorks_snapshot_0600  
AdventureWorks_snapshot_1200  
AdventureWorks_snapshot_1800  
```  
  
 <span data-ttu-id="d64b7-136">Если время создания моментального снимка изменяется, можно использовать менее точные обозначения, например:</span><span class="sxs-lookup"><span data-stu-id="d64b7-136">Alternatively, if the creation time of these daily snapshots varies from day to day, a less precise naming convention might be preferable, for example:</span></span>  
  
```  
AdventureWorks_snapshot_morning  
AdventureWorks_snapshot_noon  
AdventureWorks_snapshot_evening  
```  
  
####  <a name="best-practice-limiting-the-number-of-database-snapshots"></a><a name="Limiting_Number"></a> <span data-ttu-id="d64b7-137">Рекомендации. Ограничение количества моментальных снимков базы данных</span><span class="sxs-lookup"><span data-stu-id="d64b7-137">Best Practice: Limiting the Number of Database Snapshots</span></span>  
 <span data-ttu-id="d64b7-138">Благодаря созданию моментальных снимков через определенные промежутки времени формируется последовательность снимков базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="d64b7-138">Creating a series of snapshots over time captures sequential snapshots of the source database.</span></span> <span data-ttu-id="d64b7-139">Каждый моментальный снимок существует до тех пор, пока явно не удаляется.</span><span class="sxs-lookup"><span data-stu-id="d64b7-139">Each snapshot persists until it is explicitly dropped.</span></span> <span data-ttu-id="d64b7-140">Поскольку каждый моментальный снимок будет продолжать расти по мере обновления первоначальных страниц, возможно, потребуется освободить место на диске для новых снимков за счет удаления старых.</span><span class="sxs-lookup"><span data-stu-id="d64b7-140">Because each snapshot will continue to grow as original pages are updated, you may want to conserve disk space by deleting an older snapshot after creating a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d64b7-141">Чтобы восстановить моментальный снимок базы данных, необходимо удалить все другие снимки из базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-141">If you want to revert to a database snapshot, you need to delete any other snapshots from that database.</span></span>  
  
####  <a name="best-practice-client-connections-to-a-database-snapshot"></a><a name="Client_Connections"></a> <span data-ttu-id="d64b7-142">Рекомендации. Клиентские соединения с моментальным снимком базы данных</span><span class="sxs-lookup"><span data-stu-id="d64b7-142">Best Practice: Client Connections to a Database Snapshot</span></span>  
 <span data-ttu-id="d64b7-143">Чтобы подключиться к моментальному снимку базы данных, клиенты должны знать, где его найти.</span><span class="sxs-lookup"><span data-stu-id="d64b7-143">To use a database snapshot, clients need to know where to find it.</span></span> <span data-ttu-id="d64b7-144">Пользователи могут работать с одним моментальным снимком базы данных во время создания или удаления другого.</span><span class="sxs-lookup"><span data-stu-id="d64b7-144">Users can read from one database snapshot while another is being created or deleted.</span></span> <span data-ttu-id="d64b7-145">Тем не менее при замене существующего снимка новым необходимо перенаправить клиентов на новый снимок.</span><span class="sxs-lookup"><span data-stu-id="d64b7-145">However, when you substitute a new snapshot for an existing one, you need to redirect clients to the new snapshot.</span></span> <span data-ttu-id="d64b7-146">Пользователи могут вручную подключиться к моментальному снимку базы данных средствами среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d64b7-146">Users can manually connect to a database snapshot by means of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d64b7-147">Тем не менее в рабочей среде следует создать программное решение, которое неявным для клиента образом направляет приложения, формирующие отчеты, к последнему моментальному снимку базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-147">However, to support a production environment, you should create a programmatic solution that transparently directs report-writing clients to the latest database snapshot of the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d64b7-148">безопасность</span><span class="sxs-lookup"><span data-stu-id="d64b7-148">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d64b7-149">Permissions</span><span class="sxs-lookup"><span data-stu-id="d64b7-149">Permissions</span></span>  
 <span data-ttu-id="d64b7-150">Любой пользователь, который может создать базу данных, может создать и моментальный снимок базы данных. Однако для создания моментального снимка зеркальной базы данных необходимо быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d64b7-150">Any user who can create a database can create a database snapshot; however, to create a snapshot of a mirror database, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="how-to-create-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d64b7-151">Как создать моментальный снимок базы данных (с использованием языка Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d64b7-151">How to Create a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="d64b7-152">**Создание моментального снимка базы данных**</span><span class="sxs-lookup"><span data-stu-id="d64b7-152">**To create a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d64b7-153">Пример этой процедуры см. в подразделе [Примеры (Transact-SQL)](#TsqlExample)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d64b7-153">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="d64b7-154">На основании текущего размера базы данных-источника убедитесь, что на диске достаточно места для хранения моментального снимка базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-154">Based on the current size of the source database, ensure that you have sufficient disk space to hold the database snapshot.</span></span> <span data-ttu-id="d64b7-155">При создании моментального снимка максимальный размер моментального снимка базы данных равен размеру базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="d64b7-155">The maximum size of a database snapshot is the size of the source database at snapshot creation.</span></span> <span data-ttu-id="d64b7-156">Дополнительные сведения см. в разделе [Просмотр размера разреженного файла снимка базы данных (Transact-SQL)](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d64b7-156">For more information, see [View the Size of the Sparse File of a Database Snapshot &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="d64b7-157">Используйте инструкцию CREATE DATABASE для файлов с помощью предложения AS SNAPSHOT OF.</span><span class="sxs-lookup"><span data-stu-id="d64b7-157">Issue a CREATE DATABASE statement on the files using the AS SNAPSHOT OF clause.</span></span> <span data-ttu-id="d64b7-158">Создание моментального снимка требует указания логического имени каждого файла базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="d64b7-158">Creating a snapshot requires specifying the logical name of every database file of the source database.</span></span> <span data-ttu-id="d64b7-159">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d64b7-159">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="d64b7-160">CREATE DATABASE *имя_снимка_базы_данных*</span><span class="sxs-lookup"><span data-stu-id="d64b7-160">CREATE DATABASE *database_snapshot_name*</span></span>  
  
     <span data-ttu-id="d64b7-161">ON</span><span class="sxs-lookup"><span data-stu-id="d64b7-161">ON</span></span>  
  
     <span data-ttu-id="d64b7-162">(</span><span class="sxs-lookup"><span data-stu-id="d64b7-162">(</span></span>  
  
     <span data-ttu-id="d64b7-163">NAME =*логическое_имя_файла*,</span><span class="sxs-lookup"><span data-stu-id="d64b7-163">NAME =*logical_file_name*,</span></span>  
  
     <span data-ttu-id="d64b7-164">FILENAME ='*имя_файла_ОС*'</span><span class="sxs-lookup"><span data-stu-id="d64b7-164">FILENAME ='*os_file_name*'</span></span>  
  
     <span data-ttu-id="d64b7-165">) [ ,...*n* ]</span><span class="sxs-lookup"><span data-stu-id="d64b7-165">) [ ,...*n* ]</span></span>  
  
     <span data-ttu-id="d64b7-166">AS SNAPSHOT OF *source_database_name*</span><span class="sxs-lookup"><span data-stu-id="d64b7-166">AS SNAPSHOT OF *source_database_name*</span></span>  
  
     <span data-ttu-id="d64b7-167">[;]</span><span class="sxs-lookup"><span data-stu-id="d64b7-167">[;]</span></span>  
  
     <span data-ttu-id="d64b7-168">Здесь *имя_\*\*исходной_базы_данных* — это исходная база данных, *логическое_имя_файла* — это логическое имя, используемое в SQL Server при ссылке на файл, *имя_файла_ОС* — это путь и имя файла, используемые операционной системой при создании файла, а *имя_снимка_базы данных* — это имя снимка, на основе которого требуется восстановить базу данных.</span><span class="sxs-lookup"><span data-stu-id="d64b7-168">Where *source_\*\*database_name* is the source database, *logical_file_name i*s the logical name used in SQL Server when referencing the file, *os_file_name* is the path and file name used by the operating system when you create the file, and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="d64b7-169">Полное описание этого синтаксиса см. в разделе [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d64b7-169">For a full description of this syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d64b7-170">При создании моментального снимка базы данных файлы журнала файлы в режиме вне сети, восстанавливаемые из копии файлы и нефункционирующие файлы являются недопустимыми в инструкции CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="d64b7-170">When you create a database snapshot, log files, offline files, restoring files, and defunct files are not allowed in the CREATE DATABASE statement.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="d64b7-171">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d64b7-171">Examples (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d64b7-172">Расширение `.ss` , используемое в примерах, выбрано произвольно.</span><span class="sxs-lookup"><span data-stu-id="d64b7-172">The `.ss` extension used in the examples is arbitrary.</span></span>  
  
 <span data-ttu-id="d64b7-173">Этот раздел содержит следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="d64b7-173">This section contains the following examples:</span></span>  
  
-   <span data-ttu-id="d64b7-174">A.</span><span class="sxs-lookup"><span data-stu-id="d64b7-174">A.</span></span> [<span data-ttu-id="d64b7-175">Создание моментального снимка по базе данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="d64b7-175">Creating a snapshot on the AdventureWorks database</span></span>](#Creating_on_AW)  
  
-   <span data-ttu-id="d64b7-176">Б.</span><span class="sxs-lookup"><span data-stu-id="d64b7-176">B.</span></span> [<span data-ttu-id="d64b7-177">Создание моментального снимка по базе данных Sales</span><span class="sxs-lookup"><span data-stu-id="d64b7-177">Creating a snapshot on the Sales database</span></span>](#Creating_on_Sales)  
  
####  <a name="a-creating-a-snapshot-on-the-adventureworks-database"></a><a name="Creating_on_AW"></a> <span data-ttu-id="d64b7-178">A.</span><span class="sxs-lookup"><span data-stu-id="d64b7-178">A.</span></span> <span data-ttu-id="d64b7-179">Создание моментального снимка по базе данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="d64b7-179">Creating a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="d64b7-180">В этом примере создается моментальный снимок базы данных по базе данных `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="d64b7-180">This example creates a database snapshot on the `AdventureWorks` database.</span></span> <span data-ttu-id="d64b7-181">Имя моментального снимка `AdventureWorks_dbss_1800`и имя файла его разреженного файла `AdventureWorks_data_1800.ss`указывают на время создания — 18:00.</span><span class="sxs-lookup"><span data-stu-id="d64b7-181">The snapshot name, `AdventureWorks_dbss_1800`, and the file name of its sparse file, `AdventureWorks_data_1800.ss`, indicate the creation time, 6 P.M (1800 hours).</span></span>  
  
```  
CREATE DATABASE AdventureWorks_dbss1800 ON  
( NAME = AdventureWorks_Data, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data\AdventureWorks_data_1800.ss' )  
AS SNAPSHOT OF AdventureWorks;  
GO  
```  
  
####  <a name="b-creating-a-snapshot-on-the-sales-database"></a><a name="Creating_on_Sales"></a> <span data-ttu-id="d64b7-182">Б.</span><span class="sxs-lookup"><span data-stu-id="d64b7-182">B.</span></span> <span data-ttu-id="d64b7-183">Создание моментального снимка по базе данных Sales</span><span class="sxs-lookup"><span data-stu-id="d64b7-183">Creating a snapshot on the Sales database</span></span>  
 <span data-ttu-id="d64b7-184">Этот пример создает моментальный снимок `sales_snapshot1200`базы данных `Sales` .</span><span class="sxs-lookup"><span data-stu-id="d64b7-184">This example creates a database snapshot, `sales_snapshot1200`, on the `Sales` database.</span></span> <span data-ttu-id="d64b7-185">Эта база данных была создана в примере «создание базы данных с файловыми группами» в [&#40;«создание базы данных» SQL Server&#41;Transact-SQL ](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d64b7-185">This database was created in the example, "Creating a database that has filegroups," in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
```  
--Creating sales_snapshot1200 as snapshot of the  
--Sales database:  
CREATE DATABASE sales_snapshot1200 ON  
( NAME = SPri1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri1dat_1200.ss'),  
( NAME = SPri2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri2dt_1200.ss'),  
( NAME = SGrp1Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\mssql\data\SG1Fi1dt_1200.ss'),  
( NAME = SGrp1Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG1Fi2dt_1200.ss'),  
( NAME = SGrp2Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi1dt_1200.ss'),  
( NAME = SGrp2Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi2dt_1200.ss')  
AS SNAPSHOT OF Sales;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d64b7-186">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d64b7-186">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d64b7-187">Просмотр моментального снимка базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d64b7-187">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="d64b7-188">Восстановление базы данных до состояния, сохраненного в моментальном снимке</span><span class="sxs-lookup"><span data-stu-id="d64b7-188">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="d64b7-189">Удаление моментального снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d64b7-189">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="d64b7-190">См. также:</span><span class="sxs-lookup"><span data-stu-id="d64b7-190">See Also</span></span>  
 <span data-ttu-id="d64b7-191">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d64b7-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="d64b7-192">Моментальные снимки базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d64b7-192">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
