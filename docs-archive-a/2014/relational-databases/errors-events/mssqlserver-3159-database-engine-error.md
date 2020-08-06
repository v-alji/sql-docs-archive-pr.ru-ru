---
title: MSSQLSERVER_3159 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3159 (Database Engine error)
ms.assetid: c93c1003-0e3a-40aa-9873-44a0f5b8b57e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b469842b2aab15980c72ea01e46270c55ef29e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664244"
---
# <a name="mssqlserver_3159"></a><span data-ttu-id="295ec-102">MSSQLSERVER_3159</span><span class="sxs-lookup"><span data-stu-id="295ec-102">MSSQLSERVER_3159</span></span>
    
## <a name="details"></a><span data-ttu-id="295ec-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="295ec-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="295ec-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="295ec-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="295ec-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="295ec-105">Event ID</span></span>|<span data-ttu-id="295ec-106">3159</span><span class="sxs-lookup"><span data-stu-id="295ec-106">3159</span></span>|  
|<span data-ttu-id="295ec-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="295ec-107">Event Source</span></span>|<span data-ttu-id="295ec-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="295ec-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="295ec-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="295ec-109">Component</span></span>|<span data-ttu-id="295ec-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="295ec-110">SQLEngine</span></span>|  
|<span data-ttu-id="295ec-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="295ec-111">Symbolic Name</span></span>|<span data-ttu-id="295ec-112">LDDB_LOGNOTBACKEDUP</span><span class="sxs-lookup"><span data-stu-id="295ec-112">LDDB_LOGNOTBACKEDUP</span></span>|  
|<span data-ttu-id="295ec-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="295ec-113">Message Text</span></span>|<span data-ttu-id="295ec-114">Не удалось создать резервную копию заключительного фрагмента журнала базы данных «%s».</span><span class="sxs-lookup"><span data-stu-id="295ec-114">The tail of the log for the database "%ls" has not been backed up.</span></span> <span data-ttu-id="295ec-115">Если журнал содержит работу, потеря которой нежелательна, создайте резервную копию с помощью инструкции BACKUP LOG WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="295ec-115">Use BACKUP LOG WITH NORECOVERY to back up the log if it contains work that you do not want to lose.</span></span> <span data-ttu-id="295ec-116">Чтобы просто перезаписать содержимое журнала, используются предложения WITH REPLACE или WITH STOPAT с инструкцией RESTORE.</span><span class="sxs-lookup"><span data-stu-id="295ec-116">Use the WITH REPLACE or WITH STOPAT clause of the RESTORE statement to just overwrite the contents of the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="295ec-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="295ec-117">Explanation</span></span>  
 <span data-ttu-id="295ec-118">В большинстве случаев при использовании модели восстановления с неполным протоколированием или полной модели в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо создать резервную копию заключительного фрагмента журнала, чтобы захватить записи журнала, резервной копии которых еще нет.</span><span class="sxs-lookup"><span data-stu-id="295ec-118">In most cases, under the full or bulk-logged recovery models, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires that you back up the tail of the log to capture the log records that have not yet been backed up.</span></span> <span data-ttu-id="295ec-119">Резервная копия журнала, созданная для заключительного фрагмента журнала непосредственно перед операцией восстановления, называется резервной копией заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="295ec-119">A log backup taken of the tail of the log just before a restore operation is called a tail-log backup.</span></span>  
  
 <span data-ttu-id="295ec-120">При восстановлении базы данных в состояние на момент сбоя резервная копия заключительного фрагмента журнала является наименее важной в плане восстановления.</span><span class="sxs-lookup"><span data-stu-id="295ec-120">When you are recovering a database to the point of a failure, the tail-log backup is the last backup of interest in the recovery plan.</span></span> <span data-ttu-id="295ec-121">Если резервную копию заключительного фрагмента журнала создать невозможно, то базу данных можно восстановить только до конца последней резервной копии, созданной до сбоя.</span><span class="sxs-lookup"><span data-stu-id="295ec-121">If you cannot back up the tail of the log, you can recover a database only to the end of the last backup that was created before the failure.</span></span>  
  
 <span data-ttu-id="295ec-122">Обычно в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перед восстановлением резервной копии базы данных необходимо создавать резервную копию заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="295ec-122">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usually requires that you take a tail-log backup before you start to restore a database.</span></span> <span data-ttu-id="295ec-123">Резервная копия заключительного фрагмента журнала предотвращает потерю работы и поддерживает целостность цепочки журналов.</span><span class="sxs-lookup"><span data-stu-id="295ec-123">The tail-log backup prevents work loss and keeps the log chain intact.</span></span> <span data-ttu-id="295ec-124">Однако резервная копия заключительного фрагмента журнала требуется не для всех сценариев восстановления.</span><span class="sxs-lookup"><span data-stu-id="295ec-124">However, not all restore scenarios require a tail-log backup.</span></span> <span data-ttu-id="295ec-125">Резервная копия заключительного фрагмента журнала не нужна, если точка восстановления содержится в более ранней резервной копии журнала или если выполняется перемещение или замещение (перезапись) базы данных, когда не нужно восстанавливать ее на определенный момент времени после последней резервной копии.</span><span class="sxs-lookup"><span data-stu-id="295ec-125">You do not have to have a tail-log backup if the recovery point is included in an earlier log backup, or if you are moving or replacing (overwriting) the database and do not need to restore it to a point of time after the most recent backup.</span></span> <span data-ttu-id="295ec-126">Кроме того, если файлы журналов повреждены и невозможно создать резервную копию заключительного фрагмента журнала, то восстанавливать базу данных следует без использования резервной копии заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="295ec-126">Also, if the log files are damaged and a tail-log backup cannot be created, you must restore the database without using a tail-log backup.</span></span> <span data-ttu-id="295ec-127">Будут потеряны любые транзакции, зафиксированные после создания последней резервной копии журнала.</span><span class="sxs-lookup"><span data-stu-id="295ec-127">Any transactions committed after the latest log backup are lost.</span></span> <span data-ttu-id="295ec-128">Дополнительные сведения см. ниже в подразделе «Восстановление без использования резервной копии заключительного фрагмента журнала».</span><span class="sxs-lookup"><span data-stu-id="295ec-128">For more information, see "Restoring Without Using a Tail-Log Backup," later in this topic.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="295ec-129">Параметр REPLACE следует использовать редко и очень аккуратно.</span><span class="sxs-lookup"><span data-stu-id="295ec-129">REPLACE should be used rarely, and only after careful consideration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="295ec-130">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="295ec-130">User Action</span></span>  
 <span data-ttu-id="295ec-131">Создайте резервную копию заключительного фрагмента журнала и повторите операцию восстановления.</span><span class="sxs-lookup"><span data-stu-id="295ec-131">Take a tail-log backup, and retry the restore operation.</span></span>  
  
 <span data-ttu-id="295ec-132">Если не удается создать резервную копию заключительного фрагмента журнала, то следует использовать предложения WITH STOPAT или WITH REPLACE с инструкцией RESTORE.</span><span class="sxs-lookup"><span data-stu-id="295ec-132">If you cannot back up the tail of the log, use WITH STOPAT or WITH REPLACE in your RESTORE statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="295ec-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="295ec-133">See Also</span></span>  
 <span data-ttu-id="295ec-134">[Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="295ec-134">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="295ec-135">[Создайте резервную копию журнала транзакций, если база данных повреждена &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="295ec-135">[Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span></span>  
 <span data-ttu-id="295ec-136">[Создание резервной копии журнала транзакций (SQL Server)](../backup-restore/back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="295ec-136">[Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="295ec-137">Резервные копии заключительного фрагмента журнала (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="295ec-137">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/tail-log-backups-sql-server.md)  
  
  
