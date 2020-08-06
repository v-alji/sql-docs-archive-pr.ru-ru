---
title: MSSQL_ENG003165 | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003165 error
ms.assetid: 707d33dd-644e-4cc9-ac51-dddd49031530
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1702588ba6ac1beeb33b87a7afc7fc330271559
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654193"
---
# <a name="mssql_eng003165"></a><span data-ttu-id="14359-102">MSSQL_ENG003165</span><span class="sxs-lookup"><span data-stu-id="14359-102">MSSQL_ENG003165</span></span>
    
## <a name="message-details"></a><span data-ttu-id="14359-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="14359-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14359-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="14359-104">Product Name</span></span>|<span data-ttu-id="14359-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="14359-105">SQL Server</span></span>|  
|<span data-ttu-id="14359-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="14359-106">Event ID</span></span>|<span data-ttu-id="14359-107">3165</span><span class="sxs-lookup"><span data-stu-id="14359-107">3165</span></span>|  
|<span data-ttu-id="14359-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="14359-108">Event Source</span></span>|<span data-ttu-id="14359-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="14359-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="14359-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="14359-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="14359-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="14359-111">Symbolic Name</span></span>||  
|<span data-ttu-id="14359-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="14359-112">Message Text</span></span>|<span data-ttu-id="14359-113">База данных '%ls' восстановлена, однако во время восстановления/удаления репликации произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="14359-113">Database '%ls' was restored; however, an error was encountered while replication was being restored/removed.</span></span> <span data-ttu-id="14359-114">База данных находится в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="14359-114">The database has been left offline.</span></span> <span data-ttu-id="14359-115">См. раздел MSSQL_ENG003165 в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="14359-115">See the topic MSSQL_ENG003165 in SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14359-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="14359-116">Explanation</span></span>  
 <span data-ttu-id="14359-117">Эта ошибка возникает, если возникает проблема восстановления резервной копии реплицированной базы данных:</span><span class="sxs-lookup"><span data-stu-id="14359-117">This error is raised if a problem occurs restoring a backup of a replicated database:</span></span>  
  
-   <span data-ttu-id="14359-118">Если резервная копия восстанавливается в ту же базу данных на том же сервере, где создавалась эта резервная копия, ошибка указывает на то, что не удалось должным образом восстановить настройки репликации.</span><span class="sxs-lookup"><span data-stu-id="14359-118">If the backup is being restored to the same database and server on which it was taken, the error indicates that replication settings could not be restored properly.</span></span>  
  
-   <span data-ttu-id="14359-119">Если резервная копия восстанавливается в другую базу данных или на другой сервер, ошибка указывает на то, что не удалось должным образом удалить настройки репликации (если база данных или сервер иные, настройки репликации удаляются по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="14359-119">If the backup is being restored to a different database or server, the error indicates that replication settings could not be removed properly (by default, replication settings are removed if the database or server is different).</span></span>  
  
 <span data-ttu-id="14359-120">Возможно, ошибка возникла в результате несовпадения состояний восстановленной базы данных и одной или нескольких системных баз данных, содержащих метаданные репликации: **msdb**, **master**или базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="14359-120">The error is probably the result of a mismatch between the state of the restored database and one or more system databases that contain replication metadata: **msdb**, **master**, or the distribution database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14359-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="14359-121">User Action</span></span>  
 <span data-ttu-id="14359-122">Для разрешения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="14359-122">To resolve this issue:</span></span>  
  
1.  <span data-ttu-id="14359-123">Выполните команду ALTER DATABASE для перевода базы данных в режим "в сети", например, `ALTER DATABASE AdventureWorks SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="14359-123">Execute ALTER DATABASE to bring the database online; for example: `ALTER DATABASE AdventureWorks SET ONLINE`.</span></span> <span data-ttu-id="14359-124">Дополнительные сведения см. в разделе [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="14359-124">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span> <span data-ttu-id="14359-125">Если требуется сохранить настройки репликации, перейдите к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="14359-125">If you want to preserve replication settings, go to step 2.</span></span> <span data-ttu-id="14359-126">Если нет, перейдите к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="14359-126">If not, go to step 3.</span></span>  
  
2.  <span data-ttu-id="14359-127">Выполните процедуру [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="14359-127">Execute [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span></span> <span data-ttu-id="14359-128">Если эта хранимая процедура выполнена успешно, восстановление завершено.</span><span class="sxs-lookup"><span data-stu-id="14359-128">If this stored procedure executes successfully, the restore is complete.</span></span> <span data-ttu-id="14359-129">Если она не будет выполнена успешно, перейдите к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="14359-129">If it does not execute successfully, go to step 3.</span></span>  
  
3.  <span data-ttu-id="14359-130">Выполните процедуру [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql), чтобы удалить все настройки репликации.</span><span class="sxs-lookup"><span data-stu-id="14359-130">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove all replication settings.</span></span>  
  
     <span data-ttu-id="14359-131">При необходимости произведите повторную настройку репликации.</span><span class="sxs-lookup"><span data-stu-id="14359-131">Reconfigure replication if necessary.</span></span> <span data-ttu-id="14359-132">Если скрипты топологии репликации были составлены в соответствии с рекомендациями, для повторной настройки топологии воспользуйтесь скриптами.</span><span class="sxs-lookup"><span data-stu-id="14359-132">If you have scripted the replication topology as recommended, use scripts to reconfigure the topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14359-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="14359-133">See Also</span></span>  
 <span data-ttu-id="14359-134">[Резервное копирование и восстановление баз данных SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="14359-134">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="14359-135">[Создание резервной копии и восстановление из копий реплицируемых баз данных](administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="14359-135">[Back Up and Restore Replicated Databases](administration/back-up-and-restore-replicated-databases.md) </span></span>  
 [<span data-ttu-id="14359-136">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="14359-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
