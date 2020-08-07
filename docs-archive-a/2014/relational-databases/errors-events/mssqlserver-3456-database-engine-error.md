---
title: MSSQLSERVER_3456 | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3456 (Database Engine error)
ms.assetid: d11b2b2c-3ae4-4023-b82f-05b561bfacce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f13316bdd3147bb0ad63c8d4a2fb18f1fce74006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732705"
---
# <a name="mssqlserver_3456"></a><span data-ttu-id="96411-102">MSSQLSERVER_3456</span><span class="sxs-lookup"><span data-stu-id="96411-102">MSSQLSERVER_3456</span></span>
    
## <a name="details"></a><span data-ttu-id="96411-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="96411-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96411-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="96411-104">Product Name</span></span>|<span data-ttu-id="96411-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="96411-105">SQL Server</span></span>|  
|<span data-ttu-id="96411-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="96411-106">Event ID</span></span>|<span data-ttu-id="96411-107">3456</span><span class="sxs-lookup"><span data-stu-id="96411-107">3456</span></span>|  
|<span data-ttu-id="96411-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="96411-108">Event Source</span></span>|<span data-ttu-id="96411-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="96411-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="96411-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="96411-110">Component</span></span>|<span data-ttu-id="96411-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="96411-111">SQLEngine</span></span>|  
|<span data-ttu-id="96411-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="96411-112">Symbolic Name</span></span>|<span data-ttu-id="96411-113">REC_REDOLSNMISMATCH</span><span class="sxs-lookup"><span data-stu-id="96411-113">REC_REDOLSNMISMATCH</span></span>|  
|<span data-ttu-id="96411-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="96411-114">Message Text</span></span>|<span data-ttu-id="96411-115">Не удалось повторить запись журнала %S_LSN для идентификатора транзакции %S_XID на странице %S_PGID базы данных "%.\*ls" (идентификатор базы данных %d).</span><span class="sxs-lookup"><span data-stu-id="96411-115">Could not redo log record %S_LSN, for transaction ID %S_XID, on page %S_PGID, database '%.\*ls' (database ID %d).</span></span> <span data-ttu-id="96411-116">Страница: номер LSN = %S_LSN, тип = %ld.</span><span class="sxs-lookup"><span data-stu-id="96411-116">Page: LSN = %S_LSN, type = %ld.</span></span> <span data-ttu-id="96411-117">Журнал: OpCode = %ld, контекст %ld, PrevPageLSN: %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="96411-117">Log: OpCode = %ld, context %ld, PrevPageLSN: %S_LSN.</span></span> <span data-ttu-id="96411-118">Восстановите базу данных из резервной копии или исправьте ее.</span><span class="sxs-lookup"><span data-stu-id="96411-118">Restore from a backup of the database, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="96411-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="96411-119">Explanation</span></span>  
 <span data-ttu-id="96411-120">Операции восстановления не удалось выполнить повтор журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="96411-120">The restore operation was unable to redo the transaction log.</span></span> <span data-ttu-id="96411-121">В результате этой ошибки состояние базы данных изменилось на SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="96411-121">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="96411-122">Первичная файловая группа и, возможно, другие файловые группы могут быть повреждены.</span><span class="sxs-lookup"><span data-stu-id="96411-122">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="96411-123">Эта база данных не может быть восстановлена во время загрузки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и поэтому недоступна.</span><span class="sxs-lookup"><span data-stu-id="96411-123">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="96411-124">Для разрешения этой проблемы требуется вмешательство пользователя.</span><span class="sxs-lookup"><span data-stu-id="96411-124">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="96411-125">Следует отметить, что если эта ошибка возникает для базы данных **tempdb**, экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] завершает работу.</span><span class="sxs-lookup"><span data-stu-id="96411-125">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96411-126">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="96411-126">User Action</span></span>  
 <span data-ttu-id="96411-127">Эта ошибка может вызываться временным состоянием, существовавшим в системе во время данной попытки запуска экземпляра сервера или восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="96411-127">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="96411-128">Эта ошибка может быть также вызвана неустранимым сбоем, который возникает при каждой попытке запуска базы данных.</span><span class="sxs-lookup"><span data-stu-id="96411-128">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="96411-129">Для выяснения причины проверьте журнал событий Windows, в котором должна содержаться предшествующая ошибка, которая указывает на конкретный сбой.</span><span class="sxs-lookup"><span data-stu-id="96411-129">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="96411-130">Чтобы получить сведения о причине возникновения ошибки 3456, изучите в журнале событий Windows предшествующее сообщение об ошибке, в котором указан конкретный сбой.</span><span class="sxs-lookup"><span data-stu-id="96411-130">For information about the cause of this occurrence of error 3456, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="96411-131">Соответствующее действие пользователя зависит от того, что указывают сведения в журнале событий Windows: ошибка [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] была вызвана временным состоянием или неустранимым сбоем.</span><span class="sxs-lookup"><span data-stu-id="96411-131">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="96411-132">Сведения о действиях пользователя по устранению ошибки 3456 приведены в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96411-132">For information about the user actions for troubleshooting error 3456, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96411-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="96411-133">See Also</span></span>  
 <span data-ttu-id="96411-134">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="96411-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="96411-135">[DBCC CHECKDB &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="96411-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="96411-136">[Выполнение полного восстановления базы данных (простая модель восстановления)](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="96411-136">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="96411-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="96411-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="96411-138">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="96411-138">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
