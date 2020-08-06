---
title: Инструкции DDL, функции, хранимые процедуры и представления для FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
ms.assetid: 9ecb49ee-f64e-4d30-a803-e4064a21950a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dffcc454d21a0a8dea0e98c4db2c19a4af29e948
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654348"
---
# <a name="filestream-ddl-functions-stored-procedures-and-views"></a><span data-ttu-id="f8a87-102">FILESTREAM DDL, функции, хранимые процедуры и представления</span><span class="sxs-lookup"><span data-stu-id="f8a87-102">FILESTREAM DDL, Functions, Stored Procedures, and Views</span></span>
  <span data-ttu-id="f8a87-103">Содержит список инструкций Transact-SQL и объектов базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , поддерживающих FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="f8a87-103">Lists the Transact-SQL statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that support FILESTREAM.</span></span>  
  
 <span data-ttu-id="f8a87-104">Список объектов базы данных, которые поддерживают функцию FileTable, см. в разделе [FileTable DDL, Functions, Stored Procedures, and Views](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="f8a87-104">For the list of database objects that support the FileTable feature, see [FileTable DDL, Functions, Stored Procedures, and Views](../views/views.md).</span></span>  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> <span data-ttu-id="f8a87-105">Инструкции языка описания данных (DDL) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f8a87-105">Transact-SQL Data Definition Language (DDL) Statements</span></span>  
  
-   [<span data-ttu-id="f8a87-106">CREATE DATABASE (SQL Server Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-106">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="f8a87-107">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-107">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="f8a87-108">CREATE TABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-108">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
-   [<span data-ttu-id="f8a87-109">ALTER TABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-109">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
-   [<span data-ttu-id="f8a87-110">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f8a87-110">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
-   <span data-ttu-id="f8a87-111">[DROP INDEX (Transact-SQL)](/sql/t-sql/statements/drop-index-transact-sql)DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="f8a87-111">[DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)DROP INDEX</span></span>  
  
##  <a name="system-functions"></a><a name="func"></a> <span data-ttu-id="f8a87-112">Системные функции</span><span class="sxs-lookup"><span data-stu-id="f8a87-112">System Functions</span></span>  
  
-   [<span data-ttu-id="f8a87-113">GET_FILESTREAM_TRANSACTION_CONTEXT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-113">GET_FILESTREAM_TRANSACTION_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/get-filestream-transaction-context-transact-sql)  
  
-   [<span data-ttu-id="f8a87-114">PathName (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-114">PathName &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/pathname-transact-sql)  
  
##  <a name="system-stored-procedures"></a><a name="proc"></a> <span data-ttu-id="f8a87-115">Системные хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="f8a87-115">System Stored Procedures</span></span>  
  
-   [<span data-ttu-id="f8a87-116">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="f8a87-117">sp_filestream_force_garbage_collection (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-117">sp_filestream_force_garbage_collection &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-filestream-force-garbage-collection)  
  
##  <a name="system-views---catalog-views"></a><a name="cat"></a> <span data-ttu-id="f8a87-118">Системные представления — представления каталога</span><span class="sxs-lookup"><span data-stu-id="f8a87-118">System Views - Catalog Views</span></span>  
  
-   [<span data-ttu-id="f8a87-119">sys.database_filestream_options (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-119">sys.database_filestream_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql)  
  
##  <a name="system-views---dynamic-management-views"></a><a name="dmv"></a> <span data-ttu-id="f8a87-120">Системные представления — динамические административные представления</span><span class="sxs-lookup"><span data-stu-id="f8a87-120">System Views - Dynamic Management Views</span></span>  
  
-   [<span data-ttu-id="f8a87-121">sys.dm_filestream_file_io_handles (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-121">sys.dm_filestream_file_io_handles &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-handles-transact-sql)  
  
-   [<span data-ttu-id="f8a87-122">sys.dm_filestream_file_io_requests (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a87-122">sys.dm_filestream_file_io_requests &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-requests-transact-sql)  
  
##  <a name="programming-apis"></a><a name="api"></a> <span data-ttu-id="f8a87-123">Программные API</span><span class="sxs-lookup"><span data-stu-id="f8a87-123">Programming APIs</span></span>  
  
-   [<span data-ttu-id="f8a87-124">Доступ к данным FILESTREAM с OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="f8a87-124">Access FILESTREAM Data with OpenSqlFilestream</span></span>](access-filestream-data-with-opensqlfilestream.md)  
  
-   [<span data-ttu-id="f8a87-125">Управляемый API — класс SqlFileStream</span><span class="sxs-lookup"><span data-stu-id="f8a87-125">Managed API - SqlFileStream Class</span></span>](https://go.microsoft.com/fwlink/?LinkId=220875)  
  
  
