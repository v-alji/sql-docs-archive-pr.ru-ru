---
title: MSSQLSERVER_3314 | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3314 (Database Engine error)
ms.assetid: f3a5ca6a-b502-4cab-b3b1-4bc753763fa9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3b891b438f71d70f5dd62174eae2c5a07d29a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667125"
---
# <a name="mssqlserver_3314"></a><span data-ttu-id="c9b0e-102">MSSQLSERVER_3314</span><span class="sxs-lookup"><span data-stu-id="c9b0e-102">MSSQLSERVER_3314</span></span>
    
## <a name="details"></a><span data-ttu-id="c9b0e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="c9b0e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9b0e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c9b0e-104">Product Name</span></span>|<span data-ttu-id="c9b0e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9b0e-105">SQL Server</span></span>|  
|<span data-ttu-id="c9b0e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c9b0e-106">Event ID</span></span>|<span data-ttu-id="c9b0e-107">3314</span><span class="sxs-lookup"><span data-stu-id="c9b0e-107">3314</span></span>|  
|<span data-ttu-id="c9b0e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c9b0e-108">Event Source</span></span>|<span data-ttu-id="c9b0e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c9b0e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c9b0e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c9b0e-110">Component</span></span>|<span data-ttu-id="c9b0e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c9b0e-111">SQLEngine</span></span>|  
|<span data-ttu-id="c9b0e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c9b0e-112">Symbolic Name</span></span>|<span data-ttu-id="c9b0e-113">ERR_LOG_RID2</span><span class="sxs-lookup"><span data-stu-id="c9b0e-113">ERR_LOG_RID2</span></span>|  
|<span data-ttu-id="c9b0e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c9b0e-114">Message Text</span></span>|<span data-ttu-id="c9b0e-115">При выполнении отката записанной в журнал операции в базе данных «%.\*ls» произошла ошибка при работе с записью, идентификатор которой %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-115">During undoing of a logged operation in database '%.\*ls', an error occurred at log record ID %S_LSN.</span></span> <span data-ttu-id="c9b0e-116">Как правило, конкретный сбой регистрируется как ошибка в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-116">Typically, the specific failure is logged previously as an error in the Windows Event Log service.</span></span> <span data-ttu-id="c9b0e-117">Восстановите базу данных из полной резервной копии или исправьте ее.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-117">Restore the database or file from a backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9b0e-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c9b0e-118">Explanation</span></span>  
 <span data-ttu-id="c9b0e-119">Это ошибка свертки при восстановлении откатом.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-119">This is a rollup error for undo recovery.</span></span> <span data-ttu-id="c9b0e-120">В результате этой ошибки состояние базы данных изменилось на SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="c9b0e-121">Первичная файловая группа и, возможно, другие файловые группы могут быть повреждены.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="c9b0e-122">Эта база данных не может быть восстановлена во время загрузки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и поэтому недоступна.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="c9b0e-123">Для разрешения этой проблемы требуется вмешательство пользователя.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="c9b0e-124">Следует отметить, что если эта ошибка возникает для базы данных **tempdb**, экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] завершает работу.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9b0e-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c9b0e-125">User Action</span></span>  
 <span data-ttu-id="c9b0e-126">Эта ошибка может вызываться временным состоянием, существовавшим в системе во время данной попытки запуска экземпляра сервера или восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="c9b0e-127">Эта ошибка может быть также вызвана неустранимым сбоем, который возникает при каждой попытке запуска базы данных.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="c9b0e-128">Для выяснения причины проверьте журнал событий Windows, в котором должна содержаться предшествующая ошибка, которая указывает на конкретный сбой.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="c9b0e-129">Для получения сведений о причине возникновения ошибки 3314 проверьте журнал событий Windows на наличие предыдущего сообщения об ошибке, в котором указан конкретный сбой.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-129">For information about the cause of this occurrence of error 3314, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="c9b0e-130">Соответствующее действие пользователя зависит от того, что указывают сведения в журнале событий Windows: ошибка [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] была вызвана временным состоянием или неустранимым сбоем.</span><span class="sxs-lookup"><span data-stu-id="c9b0e-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="c9b0e-131">Сведения о действиях пользователя по устранению ошибки 3314 приведены в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9b0e-131">For information about the user actions for troubleshooting error 3314, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b0e-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9b0e-132">See Also</span></span>  
 <span data-ttu-id="c9b0e-133">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b0e-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="c9b0e-134">[DBCC CHECKDB &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b0e-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="c9b0e-135">[Выполнение полного восстановления базы данных (простая модель восстановления)](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="c9b0e-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="c9b0e-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="c9b0e-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="c9b0e-137">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c9b0e-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
