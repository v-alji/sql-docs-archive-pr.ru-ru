---
title: Просмотр размера разреженного файла снимка базы данных (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server database snapshots], sparse files
- space [SQL Server], sparse files
- sparse files [SQL Server]
- size [SQL Server], sparse files
- maximum sparse file size
- database snapshots [SQL Server], sparse files
- space [SQL Server], database snapshots
ms.assetid: 1867c5f8-d57c-46d3-933d-3642ab0a8e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: 424399b9915c8e7e26e1076fd2e553aafe06fcf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735310"
---
# <a name="view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql"></a><span data-ttu-id="ef389-102">Просмотр размера разреженного файла снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ef389-102">View the Size of the Sparse File of a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="ef389-103">В этом разделе описывается использование [!INCLUDE[tsql](../../includes/tsql-md.md)] для проверки того, является ли файл базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разреженным файлом, и для определения фактического и максимального размеров.</span><span class="sxs-lookup"><span data-stu-id="ef389-103">This topic describes how to use [!INCLUDE[tsql](../../includes/tsql-md.md)] to verify that a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database file is a sparse file and to find out its actual and maximum sizes.</span></span> <span data-ttu-id="ef389-104">Разреженные файлы, которые являются средством файловой системы NTFS, используются моментальными снимками базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef389-104">Sparse files, which are a feature of the NTFS file system, are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshots.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef389-105">При создании моментального снимка базы данных разреженные файлы создаются с помощью имен файлов, указанных в инструкции CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="ef389-105">During database snapshot creation, sparse files are created by using the file names in the CREATE DATABASE statement.</span></span> <span data-ttu-id="ef389-106">Эти имена файлов хранятся в таблице **sys.master_files** в столбце **physical_name** .</span><span class="sxs-lookup"><span data-stu-id="ef389-106">These file names are stored in **sys.master_files** in the **physical_name** column.</span></span> <span data-ttu-id="ef389-107">В таблице **sys.database_files** (в базе данных-источнике или в моментальном снимке) столбец **physical_name** всегда содержит имена файлов базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="ef389-107">In **sys.database_files** (whether in the source database or in a snapshot), the **physical_name** column always contains the names of the source database files.</span></span>  
  
## <a name="verify-that-a-database-file-is-a-sparse-file"></a><span data-ttu-id="ef389-108">Убедитесь, что файл базы данных является разреженным файлом</span><span class="sxs-lookup"><span data-stu-id="ef389-108">Verify that a Database File is a Sparse File</span></span>  
  
1.  <span data-ttu-id="ef389-109">В экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef389-109">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="ef389-110">Выберите столбец **is_sparse** в таблице **sys.database_files** в моментальном снимке базы данных или в таблице **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="ef389-110">Select the **is_sparse** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="ef389-111">Значение указывает, является ли файл разреженным, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ef389-111">The value indicates whether the file is a sparse file, as follows:</span></span>  
  
     <span data-ttu-id="ef389-112">1 = разреженный файл.</span><span class="sxs-lookup"><span data-stu-id="ef389-112">1 = File is a sparse file.</span></span>  
  
     <span data-ttu-id="ef389-113">0 = неразреженный файл.</span><span class="sxs-lookup"><span data-stu-id="ef389-113">0 = File is not a sparse file.</span></span>  
  
## <a name="find-out-the-actual-size-of-a-sparse-file"></a><span data-ttu-id="ef389-114">Определение фактического размера разреженного файла</span><span class="sxs-lookup"><span data-stu-id="ef389-114">Find Out the Actual Size of a Sparse File</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef389-115">Разреженные файлы каждый раз увеличиваются в размере на 64 килобайта (КБ); таким образом, размер разреженного файла на диске всегда кратен 64 КБ.</span><span class="sxs-lookup"><span data-stu-id="ef389-115">Sparse files grow in 64-kilobyte (KB) increments; thus, the size of a sparse file on disk is always a multiple of 64 KB.</span></span>  
  
 <span data-ttu-id="ef389-116">Чтобы просмотреть число байтов, которые в настоящее время используются каждым разреженным файлом моментального снимка на диске, запросите столбец **size_on_disk_bytes** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] динамического административного представления [sys. dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ef389-116">To view the number of bytes that each sparse file of a snapshot is currently using on disk, query the **size_on_disk_bytes** column of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][sys.dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) dynamic management view.</span></span>  
  
 <span data-ttu-id="ef389-117">Чтобы увидеть место на диске, занимаемое разреженным файлом, можно щелкнуть правой кнопкой мыши файл в Microsoft Windows, выбрать пункт **Свойства**и просмотреть значение **Место на диске** .</span><span class="sxs-lookup"><span data-stu-id="ef389-117">To view the disk space used by a sparse file, right-click the file in Microsoft Windows, click **Properties**, and look at the **Size on disk** value.</span></span>  
  
## <a name="find-out-the-maximum-size-of-a-sparse-file"></a><span data-ttu-id="ef389-118">Определение максимального размера разреженного файла</span><span class="sxs-lookup"><span data-stu-id="ef389-118">Find Out the Maximum Size of a Sparse File</span></span>  
 <span data-ttu-id="ef389-119">Максимальный размер, до которого может увеличиться разреженный файл, равен размеру соответствующего файла базы данных-источника на момент создания моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="ef389-119">The maximum size to which a sparse can grow is the size of the corresponding source database file at the time of the snapshot creation.</span></span> <span data-ttu-id="ef389-120">Чтобы узнать этот размер, можно использовать один из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="ef389-120">To learn this size, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="ef389-121">Использование командной строки Windows.</span><span class="sxs-lookup"><span data-stu-id="ef389-121">Using Windows Command Prompt:</span></span>  
  
    1.  <span data-ttu-id="ef389-122">Использование команд Windows **dir** .</span><span class="sxs-lookup"><span data-stu-id="ef389-122">Use Windows **dir** commands.</span></span>  
  
    2.  <span data-ttu-id="ef389-123">Выбор разреженного файла, открытие диалогового окна **Свойства** в Windows и просмотр значения **Размер** .</span><span class="sxs-lookup"><span data-stu-id="ef389-123">Select the sparse file, open the file **Properties** dialog box in Windows, and look at the **Size** value.</span></span>  
  
-   <span data-ttu-id="ef389-124">В экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef389-124">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="ef389-125">Выбрать столбец **size** из таблицы **sys.database_files** в моментальном снимке базы данных или из таблицы **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="ef389-125">Select the **size** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="ef389-126">Значение столбца **size** отражает максимальный объем пространства (в страницах SQL), который может когда-либо использоваться моментальным снимком; это значение эквивалентно значению поля Windows **Size** , за исключением того, что оно представлено в терминах количества страниц SQL в файле; размер в байтах равен:</span><span class="sxs-lookup"><span data-stu-id="ef389-126">The value of **size** column reflects the maximum space, in SQL pages, that the snapshot can ever use; this value is equivalent to the Windows **Size** field, except that it is represented in terms of the number of SQL pages in the file; the size in bytes is:</span></span>  
  
     <span data-ttu-id="ef389-127">( *число_страниц* \* 8192)</span><span class="sxs-lookup"><span data-stu-id="ef389-127">( *number_of_pages* \* 8192)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef389-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="ef389-128">See Also</span></span>  
 <span data-ttu-id="ef389-129">[Моментальные снимки базы данных (SQL Server)](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ef389-129">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="ef389-130">[sys.fn_virtualfilestats (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ef389-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span></span>  
 <span data-ttu-id="ef389-131">[sys.database_files (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ef389-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 [<span data-ttu-id="ef389-132">sys.master_files (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ef389-132">sys.master_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)  
  
  
