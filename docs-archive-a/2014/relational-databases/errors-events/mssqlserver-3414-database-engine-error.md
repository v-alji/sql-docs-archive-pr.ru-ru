---
title: MSSQLSERVER_3414 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3414 (Database Engine error)
ms.assetid: f25852f9-b91c-4356-b817-78bec9ec8db4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: aecaf2a920552b8ea66804600fa8bd4168175e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667118"
---
# <a name="mssqlserver_3414"></a><span data-ttu-id="526c9-102">MSSQLSERVER_3414</span><span class="sxs-lookup"><span data-stu-id="526c9-102">MSSQLSERVER_3414</span></span>
    
## <a name="details"></a><span data-ttu-id="526c9-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="526c9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="526c9-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="526c9-104">Product Name</span></span>|<span data-ttu-id="526c9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="526c9-105">SQL Server</span></span>|  
|<span data-ttu-id="526c9-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="526c9-106">Event ID</span></span>|<span data-ttu-id="526c9-107">3414</span><span class="sxs-lookup"><span data-stu-id="526c9-107">3414</span></span>|  
|<span data-ttu-id="526c9-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="526c9-108">Event Source</span></span>|<span data-ttu-id="526c9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="526c9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="526c9-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="526c9-110">Component</span></span>|<span data-ttu-id="526c9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="526c9-111">SQLEngine</span></span>|  
|<span data-ttu-id="526c9-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="526c9-112">Symbolic Name</span></span>|<span data-ttu-id="526c9-113">REC_GIVEUP</span><span class="sxs-lookup"><span data-stu-id="526c9-113">REC_GIVEUP</span></span>|  
|<span data-ttu-id="526c9-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="526c9-114">Message Text</span></span>|<span data-ttu-id="526c9-115">Во время восстановления произошла ошибка, препятствующая перезапуску базы данных «%.\*ls» (идентификатор базы данных %d).</span><span class="sxs-lookup"><span data-stu-id="526c9-115">An error occurred during recovery, preventing the database '%.\*ls' (database ID %d) from restarting.</span></span> <span data-ttu-id="526c9-116">Проведите диагностику ошибок восстановления и исправьте их, или проведите восстановление из проверенной рабочей резервной копии.</span><span class="sxs-lookup"><span data-stu-id="526c9-116">Diagnose the recovery errors and fix them, or restore from a known good backup.</span></span> <span data-ttu-id="526c9-117">Если ошибки не устранены или ожидаются в будущем, свяжитесь со службой технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="526c9-117">If errors are not corrected or expected, contact Technical Support.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="526c9-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="526c9-118">Explanation</span></span>  
 <span data-ttu-id="526c9-119">Заданная база данных была восстановлена, но не была запущена, так как при восстановлении возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="526c9-119">The specified database was recovered, but failed to start, because errors occurred during recovery.</span></span> <span data-ttu-id="526c9-120">В результате этой ошибки состояние базы данных изменилось на SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="526c9-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="526c9-121">Первичная файловая группа и, возможно, другие файловые группы могут быть повреждены.</span><span class="sxs-lookup"><span data-stu-id="526c9-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="526c9-122">Эта база данных не может быть восстановлена во время загрузки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и поэтому недоступна.</span><span class="sxs-lookup"><span data-stu-id="526c9-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="526c9-123">Для разрешения этой проблемы требуется вмешательство пользователя.</span><span class="sxs-lookup"><span data-stu-id="526c9-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="526c9-124">Следует отметить, что если эта ошибка возникает для базы данных **tempdb**, экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] завершает работу.</span><span class="sxs-lookup"><span data-stu-id="526c9-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="526c9-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="526c9-125">User Action</span></span>  
 <span data-ttu-id="526c9-126">Эта ошибка может вызываться временным состоянием, существовавшим в системе во время данной попытки запуска экземпляра сервера или восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="526c9-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="526c9-127">Эта ошибка может быть также вызвана неустранимым сбоем, который возникает при каждой попытке запуска базы данных.</span><span class="sxs-lookup"><span data-stu-id="526c9-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="526c9-128">Для выяснения причины проверьте журнал событий Windows, в котором должна содержаться предшествующая ошибка, которая указывает на конкретный сбой.</span><span class="sxs-lookup"><span data-stu-id="526c9-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="526c9-129">Чтобы получить сведения о причине возникновения ошибки 3414, проверьте журнал событий Windows на наличие предыдущего сообщения об ошибке, в котором указан конкретный сбой.</span><span class="sxs-lookup"><span data-stu-id="526c9-129">For information about the cause of this occurrence of error 3414, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="526c9-130">Соответствующее действие пользователя зависит от того, что указывают сведения в журнале событий Windows: ошибка [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] была вызвана временным состоянием или неустранимым сбоем.</span><span class="sxs-lookup"><span data-stu-id="526c9-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="526c9-131">Сведения о действиях пользователя по устранению ошибки 3414 приведены в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="526c9-131">For information about the user actions for troubleshooting error 3414, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526c9-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="526c9-132">See Also</span></span>  
 <span data-ttu-id="526c9-133">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="526c9-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="526c9-134">[DBCC CHECKDB &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="526c9-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="526c9-135">[Выполнение полного восстановления базы данных (простая модель восстановления)](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="526c9-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="526c9-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="526c9-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="526c9-137">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="526c9-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
