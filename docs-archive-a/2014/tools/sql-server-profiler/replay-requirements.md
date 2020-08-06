---
title: Требования к воспроизведению | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event classes [SQL Server], replaying traces
- traces [SQL Server], replaying
- replaying traces
- TSQL_Replay template [SQL Server]
ms.assetid: 0e01dfc7-84b9-47f6-8bf7-b0656df4fa7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65546f6820765286b558d2043e0155a79a07eb58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737238"
---
# <a name="replay-requirements"></a><span data-ttu-id="4e2a7-102">Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="4e2a7-102">Replay Requirements</span></span>
  <span data-ttu-id="4e2a7-103">Для воспроизведения данных трассировки с помощью [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] или программы распределенного воспроизведения в трассировке должен быть записан определенный набор классов событий и столбцов.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-103">In order to replay trace data with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or the Distributed Replay Utility, a specific set of event classes and columns must be captured in the trace.</span></span> <span data-ttu-id="4e2a7-104">Если для настройки трассировки, которая в дальнейшем будет использоваться для воспроизведения, применяется шаблон трассировки **TSQL_Replay** , то по умолчанию эти параметры включены.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-104">These settings are enabled by default if the **TSQL_Replay** trace template is used to configure a trace that is later used for replay.</span></span> <span data-ttu-id="4e2a7-105">В этом разделе приводится описание этих параметров и других требований к воспроизведению.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-105">This topic describes these settings and other replay requirements.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e2a7-106">Для воспроизведения ресурсоемких приложений OLTP (с множеством одновременных активных соединений или высокой пропускной способностью) рекомендуется пользоваться программой распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-106">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="4e2a7-107">Программа распределенного воспроизведения воспроизводит данные трассировки с нескольких компьютеров и лучше имитирует важную рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-107">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="4e2a7-108">Дополнительные сведения см. в статье [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="4e2a7-108">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="event-classes-required-for-replay"></a><span data-ttu-id="4e2a7-109">Классы событий, необходимые для воспроизведения</span><span class="sxs-lookup"><span data-stu-id="4e2a7-109">Event Classes Required for Replay</span></span>  
 <span data-ttu-id="4e2a7-110">Чтобы воспроизведение можно было выполнить с помощью [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], в трассировке помимо классов событий, отобранных для наблюдения, необходимо фиксировать следующий набор классов событий.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-110">To be replayed by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], the following set of event classes, in addition to any other event classes you want to monitor, must be captured in the trace:</span></span>  
  
-   <span data-ttu-id="4e2a7-111">**CursorClose**(требуется только при воспроизведении курсоров со стороны сервера);</span><span class="sxs-lookup"><span data-stu-id="4e2a7-111">**CursorClose (** only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4e2a7-112">**CursorExecute** (требуется только при воспроизведении курсоров со стороны сервера);</span><span class="sxs-lookup"><span data-stu-id="4e2a7-112">**CursorExecute** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4e2a7-113">**CursorOpen** (требуется только при воспроизведении курсоров со стороны сервера);</span><span class="sxs-lookup"><span data-stu-id="4e2a7-113">**CursorOpen** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4e2a7-114">**CursorPrepare** (требуется только при воспроизведении курсоров со стороны сервера);</span><span class="sxs-lookup"><span data-stu-id="4e2a7-114">**CursorPrepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4e2a7-115">**CursorUnprepare** (требуется только при воспроизведении курсоров со стороны сервера);</span><span class="sxs-lookup"><span data-stu-id="4e2a7-115">**CursorUnprepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4e2a7-116">**Аудит входа в систему**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-116">**Audit Login**</span></span>  
  
-   <span data-ttu-id="4e2a7-117">**Аудит выхода из системы**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-117">**Audit Logout**</span></span>  
  
-   <span data-ttu-id="4e2a7-118">**ExistingConnection**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-118">**ExistingConnection**</span></span>  
  
-   <span data-ttu-id="4e2a7-119">**RPC Output Parameter**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-119">**RPC Output Parameter**</span></span>  
  
-   <span data-ttu-id="4e2a7-120">**RPC:Completed**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-120">**RPC:Completed**</span></span>  
  
-   <span data-ttu-id="4e2a7-121">**RPC:Starting**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-121">**RPC:Starting**</span></span>  
  
-   <span data-ttu-id="4e2a7-122">**Exec Prepared SQL** (требуется только при воспроизведении подготовленных инструкций SQL на стороне сервера);</span><span class="sxs-lookup"><span data-stu-id="4e2a7-122">**Exec Prepared SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="4e2a7-123">**Prepare SQL** (требуется только при воспроизведении подготовленных инструкций SQL на стороне сервера).</span><span class="sxs-lookup"><span data-stu-id="4e2a7-123">**Prepare SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="4e2a7-124">**SQL:BatchCompleted**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-124">**SQL:BatchCompleted**</span></span>  
  
-   <span data-ttu-id="4e2a7-125">**SQL:BatchStarting**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-125">**SQL:BatchStarting**</span></span>  
  
## <a name="data-columns-required-for-replay"></a><span data-ttu-id="4e2a7-126">Столбцы данных, необходимые для воспроизведения</span><span class="sxs-lookup"><span data-stu-id="4e2a7-126">Data Columns Required for Replay</span></span>  
 <span data-ttu-id="4e2a7-127">Чтобы обеспечить воспроизведение трассировки, в дополнение к любым захватываемым столбцам данных должны захватываться следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="4e2a7-127">In addition to any other data columns you want to capture, the following data columns must be captured in a trace to allow the trace to be replayed:</span></span>  
  
-   <span data-ttu-id="4e2a7-128">**Класс событий**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-128">**Event Class**</span></span>  
  
-   <span data-ttu-id="4e2a7-129">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-129">**EventSequence**</span></span>  
  
-   <span data-ttu-id="4e2a7-130">**TextData**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-130">**TextData**</span></span>  
  
-   <span data-ttu-id="4e2a7-131">**Имя приложения**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-131">**Application Name**</span></span>  
  
-   <span data-ttu-id="4e2a7-132">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-132">**LoginName**</span></span>  
  
-   <span data-ttu-id="4e2a7-133">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-133">**DatabaseName**</span></span>  
  
-   <span data-ttu-id="4e2a7-134">**Идентификатор базы данных**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-134">**Database ID**</span></span>  
  
-   <span data-ttu-id="4e2a7-135">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-135">**ClientProcessID**</span></span>  
  
-   <span data-ttu-id="4e2a7-136">**HostName**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-136">**HostName**</span></span>  
  
-   <span data-ttu-id="4e2a7-137">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-137">**ServerName**</span></span>  
  
-   <span data-ttu-id="4e2a7-138">**Binary Data**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-138">**Binary Data**</span></span>  
  
-   <span data-ttu-id="4e2a7-139">**SPID**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-139">**SPID**</span></span>  
  
-   <span data-ttu-id="4e2a7-140">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-140">**Start Time**</span></span>  
  
-   <span data-ttu-id="4e2a7-141">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-141">**EndTime**</span></span>  
  
-   <span data-ttu-id="4e2a7-142">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-142">**IsSystem**</span></span>  
  
-   <span data-ttu-id="4e2a7-143">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-143">**NTDomainName**</span></span>  
  
-   <span data-ttu-id="4e2a7-144">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-144">**NTUserName**</span></span>  
  
-   <span data-ttu-id="4e2a7-145">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="4e2a7-145">**Error**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e2a7-146">В трассировках, захватывающих данные для воспроизведения, следует использовать шаблон **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="4e2a7-146">Use the trace template **TSQL_Replay** for traces that capture data for replay.</span></span>  
  
## <a name="other-replay-requirements"></a><span data-ttu-id="4e2a7-147">Другие требования к воспроизведению</span><span class="sxs-lookup"><span data-stu-id="4e2a7-147">Other Replay Requirements</span></span>  
 <span data-ttu-id="4e2a7-148">В Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]при воспроизведении проверяется наличие обязательных событий и столбцов.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-148">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], replay checks for the presence of required events and columns.</span></span> <span data-ttu-id="4e2a7-149">Это помогает повысить точность воспроизведения и избавляет от необходимости строить предположения при устранении неполадок воспроизведения, если необходимые данные отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-149">This change helps improve the accuracy of replay and takes the guesswork out of troubleshooting replay when required data is missing.</span></span> <span data-ttu-id="4e2a7-150">Если в трассировке отсутствуют необходимые данные, то воспроизведение возвращает ошибку и завершается неуспешно.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-150">Replay returns an error and stops replaying a file when required data is missing from a trace.</span></span>  
  
 <span data-ttu-id="4e2a7-151">Для воспроизведения трассировки на целевом сервере, на котором запущен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , отличном от исходного сервера, где первоначально выполнялась трассировка, убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4e2a7-151">To replay a trace against a server (the target) on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running other than the server originally traced (the source), make sure the following has been done:</span></span>  
  
-   <span data-ttu-id="4e2a7-152">На целевом сервере в той же базе данных, что и на исходном сервере, должны быть созданы все имена входа и пользователи, содержащиеся в трассировке.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-152">All logins and users contained in the trace must be created already on the target and in the same database as the source.</span></span>  
  
-   <span data-ttu-id="4e2a7-153">Все имена входа и пользователи на целевом сервере должны обладать теми же разрешениями, что были у них на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-153">All logins and users in the target must have the same permissions they had in the source.</span></span>  
  
-   <span data-ttu-id="4e2a7-154">Все пароли должны совпадать с паролями пользователя, выполняющего воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-154">All login passwords must be the same as those of the user that executes the replay.</span></span>  
  
-   <span data-ttu-id="4e2a7-155">Желательно, чтобы идентификаторы баз данных на целевом и на исходном серверах совпадали.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-155">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="4e2a7-156">Впрочем, если они не совпадают, соответствие можно установить по параметру **DatabaseName** , если он есть в трассировке.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-156">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="4e2a7-157">Для каждого имени входа в трассировке должна быть задана база данных по умолчанию, соответствующая целевой базе данных имени входа.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-157">The default database for each login contained in the trace must be set (on the target) to the respective target database of the login.</span></span> <span data-ttu-id="4e2a7-158">Например, на исходном сервере в базе данных **Fred_Db**трассировка для воспроизведения содержит операцию для имени входа **Fred** .</span><span class="sxs-lookup"><span data-stu-id="4e2a7-158">For example, the trace to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the source.</span></span> <span data-ttu-id="4e2a7-159">Таким образом, на целевом сервере необходимо задать базу данных по умолчанию для имени входа **Fred**, соответствующую базе данных **Fred_Db** (даже если имена баз данных различаются).</span><span class="sxs-lookup"><span data-stu-id="4e2a7-159">Therefore, on the target, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="4e2a7-160">Базу данных по умолчанию для имени входа можно задать с помощью хранимой процедуры **sp_defaultdb** .</span><span class="sxs-lookup"><span data-stu-id="4e2a7-160">To set the default database of the login, use the **sp_defaultdb** system stored procedure.</span></span>  
  
 <span data-ttu-id="4e2a7-161">В результате воспроизведения событий, связанных с отсутствующими или неверными именами входа, будут возникать ошибки воспроизведения, но сама операция воспроизведения будет продолжена.</span><span class="sxs-lookup"><span data-stu-id="4e2a7-161">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
 <span data-ttu-id="4e2a7-162">Сведения о разрешениях, необходимых для воспроизведения трассировки, см. в разделе [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="4e2a7-162">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2a7-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e2a7-163">See Also</span></span>  
 <span data-ttu-id="4e2a7-164">[Воспроизведение таблицы трассировки (приложение SQL Server Profiler)](replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4e2a7-164">[Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4e2a7-165">[Воспроизведение файла трассировки (приложение SQL Server Profiler)](replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4e2a7-165">[Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4e2a7-166">[Справочник по классам событий SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4e2a7-166">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="4e2a7-167">[sp_defaultdb (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4e2a7-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span></span>  
 [<span data-ttu-id="4e2a7-168">Распределенное воспроизведение SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e2a7-168">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
