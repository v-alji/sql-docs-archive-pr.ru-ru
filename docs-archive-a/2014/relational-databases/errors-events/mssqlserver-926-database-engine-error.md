---
title: MSSQLSERVER_926 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 926 (Database Engine error)
ms.assetid: 57e01668-883b-4be4-84a8-a111caaf0486
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae6796c9f4869d45223ab1283a68fc2bfe78aa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658754"
---
# <a name="mssqlserver_926"></a><span data-ttu-id="be3b8-102">MSSQLSERVER_926</span><span class="sxs-lookup"><span data-stu-id="be3b8-102">MSSQLSERVER_926</span></span>
    
## <a name="details"></a><span data-ttu-id="be3b8-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="be3b8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be3b8-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="be3b8-104">Product Name</span></span>|<span data-ttu-id="be3b8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="be3b8-105">SQL Server</span></span>|  
|<span data-ttu-id="be3b8-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="be3b8-106">Event ID</span></span>|<span data-ttu-id="be3b8-107">926</span><span class="sxs-lookup"><span data-stu-id="be3b8-107">926</span></span>|  
|<span data-ttu-id="be3b8-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="be3b8-108">Event Source</span></span>|<span data-ttu-id="be3b8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="be3b8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="be3b8-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="be3b8-110">Component</span></span>|<span data-ttu-id="be3b8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="be3b8-111">SQLEngine</span></span>|  
|<span data-ttu-id="be3b8-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="be3b8-112">Symbolic Name</span></span>|<span data-ttu-id="be3b8-113">DB_SUSPECT</span><span class="sxs-lookup"><span data-stu-id="be3b8-113">DB_SUSPECT</span></span>|  
|<span data-ttu-id="be3b8-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="be3b8-114">Message Text</span></span>|<span data-ttu-id="be3b8-115">Невозможно открыть базу данных «%.\*ls».</span><span class="sxs-lookup"><span data-stu-id="be3b8-115">Database '%.\*ls' cannot be opened.</span></span> <span data-ttu-id="be3b8-116">Она была отмечена как подозрительная (SUSPECT) операцией восстановления.</span><span class="sxs-lookup"><span data-stu-id="be3b8-116">It has been marked SUSPECT by recovery.</span></span> <span data-ttu-id="be3b8-117">Дополнительные сведения см. в журнале ошибок SQL Server.</span><span class="sxs-lookup"><span data-stu-id="be3b8-117">See the SQL Server errorlog for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be3b8-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="be3b8-118">Explanation</span></span>  
 <span data-ttu-id="be3b8-119">База данных помечается как подозрительная из-за ошибки в процессе восстановления, который должен переводить ее в согласованное транзакционное состояние.</span><span class="sxs-lookup"><span data-stu-id="be3b8-119">The database is marked as suspect because it failed the recovery process that brings a database to a consistent transactional state.</span></span> <span data-ttu-id="be3b8-120">Это может происходить во время следующих операций.</span><span class="sxs-lookup"><span data-stu-id="be3b8-120">This can occur during the following operations:</span></span>  
  
-   <span data-ttu-id="be3b8-121">Запуск экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be3b8-121">Starting up an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="be3b8-122">Присоединение базы данных.</span><span class="sxs-lookup"><span data-stu-id="be3b8-122">Attaching a database.</span></span>  
  
-   <span data-ttu-id="be3b8-123">Использование процедур RESTORE и RESTORE LOG.</span><span class="sxs-lookup"><span data-stu-id="be3b8-123">Using the RESTORE database or RESTORE LOG procedures.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be3b8-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="be3b8-124">User Action</span></span>  
 <span data-ttu-id="be3b8-125">Проверьте журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и выясните причину ошибки.</span><span class="sxs-lookup"><span data-stu-id="be3b8-125">Inspect the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and determine the cause of the error.</span></span> <span data-ttu-id="be3b8-126">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перезапускалась после неуспешного завершения восстановления, найдите предыдущие журналы ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и попробуйте отыскать причину ошибки восстановления.</span><span class="sxs-lookup"><span data-stu-id="be3b8-126">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been restarted since the failed recovery, look at previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs to see the reason why recovery failed.</span></span>  
  
 <span data-ttu-id="be3b8-127">Если восстановление завершилось неуспешно из-за постоянной ошибки ввода-вывода, обрыва страницы или другой вероятной неполадки оборудования, устраните проблему, связанную с оборудованием, и восстановите базу данных из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="be3b8-127">If the recovery failed because of a persistent I/O error, a torn page, or other possible hardware problem, resolve the underlying hardware problem and restore the database by using a backup.</span></span> <span data-ttu-id="be3b8-128">Если резервные копии недоступны, воспользуйтесь параметрами исправления инструкции DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="be3b8-128">If no backups are available, consider the repair options of DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="be3b8-129">Если решить проблему невозможно, обратитесь к основному поставщику услуг по технической поддержке.</span><span class="sxs-lookup"><span data-stu-id="be3b8-129">If you are unable to resolve this problem, contact your primary support provider.</span></span> <span data-ttu-id="be3b8-130">Убедитесь в наличии журнала ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be3b8-130">Have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log available for review.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be3b8-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="be3b8-131">See Also</span></span>  
 <span data-ttu-id="be3b8-132">[Резервное копирование и восстановление баз данных SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="be3b8-132">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="be3b8-133">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="be3b8-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="be3b8-134">[sys.sysбазы данных &#40;&#41;Transact-SQL](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="be3b8-134">[sys.sysdatabases &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span></span>  
 [<span data-ttu-id="be3b8-135">Присоединение и отсоединение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="be3b8-135">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/database-detach-and-attach-sql-server.md)  
  
  
