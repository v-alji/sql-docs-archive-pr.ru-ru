---
title: Большие таблицы журнала резервного копирования или восстановления делают обновление неотвечающим | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- backup history tables
- history tables
ms.assetid: f88d86ec-324b-4518-b6d7-1af7e7265812
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 918c20f58c00c535d8ed41d887e9671f5e821a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655536"
---
# <a name="large-backup-or-restore-history-tables-make-upgrade-appear-to-not-respond"></a><span data-ttu-id="c62c8-102">Резервное копирование или восстановление больших таблиц журналов может привести к кажущемуся отсутствию ответа от процесса обновления</span><span class="sxs-lookup"><span data-stu-id="c62c8-102">Large backup or restore history tables make upgrade appear to not respond</span></span>
  <span data-ttu-id="c62c8-103">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] в некоторые таблицы журнала резервного копирования и восстановления были добавлены новые столбцы.</span><span class="sxs-lookup"><span data-stu-id="c62c8-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], new columns were added to some of the backup and restore history tables.</span></span> <span data-ttu-id="c62c8-104">При обновлении этих таблиц требуется изменить их для добавления новых столбцов.</span><span class="sxs-lookup"><span data-stu-id="c62c8-104">Upgrading these tables requires altering them to add the new columns.</span></span> <span data-ttu-id="c62c8-105">Если одна или несколько из этих таблиц содержит большое количество строк, обновление задержится на длительное время на инструкции ALTER TABLE, которая добавляет столбцы в эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="c62c8-105">If one or more of these tables contains a large number of rows, the upgrade will stall for a substantial amount of time on the ALTER TABLE statement that adds columns to that table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c62c8-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="c62c8-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c62c8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c62c8-107">Description</span></span>  
 <span data-ttu-id="c62c8-108">Обновление может перестать отвечать, если любая из следующих таблиц резервного копирования или восстановления содержит большое количество строк:</span><span class="sxs-lookup"><span data-stu-id="c62c8-108">Upgrade can appear to stop responding if any of the following backup or restore history tables contains a large number of rows:</span></span>  
  
-   <span data-ttu-id="c62c8-109">**backupfile;**</span><span class="sxs-lookup"><span data-stu-id="c62c8-109">**backupfile**</span></span>  
  
-   <span data-ttu-id="c62c8-110">**backupmediafamily;**</span><span class="sxs-lookup"><span data-stu-id="c62c8-110">**backupmediafamily**</span></span>  
  
-   <span data-ttu-id="c62c8-111">**backupmediaset;**</span><span class="sxs-lookup"><span data-stu-id="c62c8-111">**backupmediaset**</span></span>  
  
-   <span data-ttu-id="c62c8-112">**backupset;**</span><span class="sxs-lookup"><span data-stu-id="c62c8-112">**backupset**</span></span>  
  
-   <span data-ttu-id="c62c8-113">**restorefile;**</span><span class="sxs-lookup"><span data-stu-id="c62c8-113">**restorefile**</span></span>  
  
-   <span data-ttu-id="c62c8-114">**restorefilegroup;**</span><span class="sxs-lookup"><span data-stu-id="c62c8-114">**restorefilegroup**</span></span>  
  
-   <span data-ttu-id="c62c8-115">**restorehistory.**</span><span class="sxs-lookup"><span data-stu-id="c62c8-115">**restorehistory**</span></span>  
  
 <span data-ttu-id="c62c8-116">Если любая из этих таблиц содержит 10 000 или более строк, то помощник по обновлению сообщает об ошибке несоответствия.</span><span class="sxs-lookup"><span data-stu-id="c62c8-116">If any of these tables has 10,000 or more rows, Upgrade Advisor reports a noncompliance failure.</span></span> <span data-ttu-id="c62c8-117">Не сообщается, какая таблица превысила разрешенное число строк.</span><span class="sxs-lookup"><span data-stu-id="c62c8-117">It does not report which table exceeds the allowed number of rows.</span></span> <span data-ttu-id="c62c8-118">Первая таблица, число строк в которой превышает 10 000, вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="c62c8-118">The first table that exceeds 10,000 rows causes the failure.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c62c8-119">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="c62c8-119">Corrective Action</span></span>  
 <span data-ttu-id="c62c8-120">Если какая-либо таблица содержит более 10 000 строк, то, прежде чем обновить базу данных, рекомендуется уменьшить число строк так, чтобы оно стало меньше 10 000.</span><span class="sxs-lookup"><span data-stu-id="c62c8-120">Before you upgrade a database, if any of these tables exceeds 10,000 rows, we recommend that you reduce the number to less than 10,000.</span></span> <span data-ttu-id="c62c8-121">Чтобы сократить количество строк во всех этих таблицах, можно запустить хранимую процедуру **sp_delete_backuphistory** .</span><span class="sxs-lookup"><span data-stu-id="c62c8-121">To reduce rows in all of these tables, you can run the **sp_delete_backuphistory** stored procedure.</span></span> <span data-ttu-id="c62c8-122">Эта процедура удаляет из всех таблиц журнала резервного копирования и восстановления записи, относящиеся к резервным наборам данных, которые старше указанной даты.</span><span class="sxs-lookup"><span data-stu-id="c62c8-122">This procedure deletes the entries in all of the backup and restore history tables for backup sets older than a specified date.</span></span> <span data-ttu-id="c62c8-123">Дополнительные сведения см. в разделе [sp_delete_backuphistory (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c62c8-123">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c62c8-124">Можно обновить базу данных, таблицы журнала резервного копирования и восстановления которой содержат более 10 000 строк.</span><span class="sxs-lookup"><span data-stu-id="c62c8-124">You can upgrade a database whose backup and restore history tables are larger than 10,000 rows.</span></span> <span data-ttu-id="c62c8-125">Однако при изменении больших таблиц может показаться, что процесс обновления остановился.</span><span class="sxs-lookup"><span data-stu-id="c62c8-125">But the upgrade may appear to stall while large tables are being altered.</span></span> <span data-ttu-id="c62c8-126">Чем больше таблица, тем больше времени требуется для завершения программы установки.</span><span class="sxs-lookup"><span data-stu-id="c62c8-126">The larger the tables, the longer that Setup takes to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c62c8-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="c62c8-127">See Also</span></span>  
 <span data-ttu-id="c62c8-128">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c62c8-128">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c62c8-129">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="c62c8-129">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
