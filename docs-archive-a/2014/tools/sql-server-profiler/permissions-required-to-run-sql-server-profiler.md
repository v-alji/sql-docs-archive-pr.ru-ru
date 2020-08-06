---
title: Разрешения, необходимые для запуска приложения SQL Server Profiler | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], permissions
- traces [SQL Server], replaying
- replaying traces
- SQL Server Profiler, permissions
- security [SQL Server], SQL Server Profiler
ms.assetid: 5c580a87-88ae-4314-8fe1-54ade83f227f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e73ffe2e127299db9a9e37e48f089aab2cccca52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737280"
---
# <a name="permissions-required-to-run-sql-server-profiler"></a><span data-ttu-id="9a45f-102">Разрешения, необходимые для запуска приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9a45f-102">Permissions Required to Run SQL Server Profiler</span></span>
  <span data-ttu-id="9a45f-103">По умолчанию для запуска приложения [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] требуются такие же разрешения, что и для хранимых процедур языка Transact-SQL, используемых для создания трассировок.</span><span class="sxs-lookup"><span data-stu-id="9a45f-103">By default, running [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] requires the same user permissions as the Transact-SQL stored procedures that are used to create traces.</span></span> <span data-ttu-id="9a45f-104">Для запуска приложения [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)]пользователь должен обладать разрешением ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="9a45f-104">To run [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], users must be granted the ALTER TRACE permission.</span></span> <span data-ttu-id="9a45f-105">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений на сервер (Transact-SQL)](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a45f-105">For more information, see [GRANT Server Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="9a45f-106">Пользователи, которые имеют разрешение SHOWPLAN, ALTER TRACE или VIEW SERVER STATE, могут просматривать запросы, захваченные выходом Showplan.</span><span class="sxs-lookup"><span data-stu-id="9a45f-106">Users who have the SHOWPLAN, the ALTER TRACE, or the VIEW SERVER STATE permission can view queries that are captured in Showplan output.</span></span> <span data-ttu-id="9a45f-107">Эти запросы могут содержать конфиденциальные сведения, такие как пароли.</span><span class="sxs-lookup"><span data-stu-id="9a45f-107">These queries may contain sensitive information such as passwords.</span></span> <span data-ttu-id="9a45f-108">В связи с этим рекомендуется предоставлять данные разрешения только пользователям, которые имеют право просмотра конфиденциальных данных, например членам предопределенной роли базы данных db_owner или членам предопределенной роли сервера sysadmin.</span><span class="sxs-lookup"><span data-stu-id="9a45f-108">Therefore, we recommend that you only grant these permissions to users who are authorized to view sensitive information, such as members of the db_owner fixed database role, or members of the sysadmin fixed server role.</span></span> <span data-ttu-id="9a45f-109">Также рекомендуется сохранять файлы Showplan или файлы трассировки, содержащие события, связанные с инструкцией Showplan, только в каталог, расположенный в файловой системе NTFS, для которого есть возможность ограничить доступ, предоставляя его только пользователям, имеющим право просмотра конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="9a45f-109">Additionally, we recommend that you only save Showplan files or trace files that contain Showplan-related events to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view sensitive information.</span></span>

## <a name="permissions-used-to-replay-traces"></a><span data-ttu-id="9a45f-110">Разрешения на воспроизведение трассировок</span><span class="sxs-lookup"><span data-stu-id="9a45f-110">Permissions Used to Replay Traces</span></span>
 <span data-ttu-id="9a45f-111">Для воспроизведения трассировок пользователю требуется разрешение ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="9a45f-111">Replaying traces also requires that the user who is replaying the trace have the ALTER TRACE permission.</span></span>

 <span data-ttu-id="9a45f-112">Однако если во время воспроизведения трассировки возникло событие «Audit Login», приложение [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] использует команду EXECUTE AS.</span><span class="sxs-lookup"><span data-stu-id="9a45f-112">However, during replay, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] uses the EXECUTE AS command if an Audit Login event is encountered in the trace that is being replayed.</span></span> [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="9a45f-113">использует для олицетворения пользователя, связанного с событием входа в систему.</span><span class="sxs-lookup"><span data-stu-id="9a45f-113">uses the EXECUTE AS command to impersonate the user who is associated with the login event.</span></span>

 <span data-ttu-id="9a45f-114">Если в воспроизводимой трассировке приложение [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] обнаруживает событие входа в систему, то производятся проверки следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="9a45f-114">If [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] encounters a login event in a trace that is being replayed, the following permission checks are performed:</span></span>

1.  <span data-ttu-id="9a45f-115">Пользователь1, имеющий разрешение ALTER TRACE, запускает воспроизведение трассировки.</span><span class="sxs-lookup"><span data-stu-id="9a45f-115">User1, who has the ALTER TRACE permission, starts replaying a trace.</span></span>

2.  <span data-ttu-id="9a45f-116">В воспроизводимой трассировке возникло событие входа в систему для Пользователя2.</span><span class="sxs-lookup"><span data-stu-id="9a45f-116">A login event for User2 is encountered in the replayed trace.</span></span>

3.  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="9a45f-117">олицетворяет Пользователя2 командой EXECUTE AS.</span><span class="sxs-lookup"><span data-stu-id="9a45f-117">uses the EXECUTE AS command to impersonate User2.</span></span>

4.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9a45f-118">пытается проверить подлинность Пользователя2, и, в зависимости от результатов, происходят следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9a45f-118">attempts to authenticate User2, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="9a45f-119">Если проверить подлинность Пользователя2 невозможно, приложение [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] возвращает ошибку и продолжает воспроизведение трассировки от имени Пользователя1.</span><span class="sxs-lookup"><span data-stu-id="9a45f-119">If User2 cannot be authenticated, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] returns an error, and continues replaying the trace as User1.</span></span>

    2.  <span data-ttu-id="9a45f-120">Если проверка подлинности Пользователя2 прошла успешно, воспроизведение трассировки продолжается от имени Пользователя2.</span><span class="sxs-lookup"><span data-stu-id="9a45f-120">If User2 is successfully authenticated, replaying the trace as User2 continues.</span></span>

5.  <span data-ttu-id="9a45f-121">Разрешения для Пользователя2 проверяются в базе данных назначения, и, в зависимости от результата, происходят следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9a45f-121">Permissions for User2 are checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="9a45f-122">Если у Пользователя2 есть разрешения на целевую базу данных, то олицетворение проходит успешно и трассировка воспроизводится от имени Пользователя2.</span><span class="sxs-lookup"><span data-stu-id="9a45f-122">If User2 has permissions on the target database, impersonation has succeeded, and the trace is replayed as User2.</span></span>

    2.  <span data-ttu-id="9a45f-123">Если у Пользователя2 нет разрешений на целевую базу данных, сервер проверяет существование пользователя Guest в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="9a45f-123">If User2 does not have permissions on the target database, the server checks for a Guest user on that database.</span></span>

6.  <span data-ttu-id="9a45f-124">В целевой базе данных проверяется существование пользователя Guest, и, в зависимости от результата, происходят следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9a45f-124">Existence of a Guest user is checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="9a45f-125">Если учетная запись «Guest» существует, трассировка воспроизводится от ее имени.</span><span class="sxs-lookup"><span data-stu-id="9a45f-125">If a Guest account exists, the trace is replayed as the Guest account.</span></span>

    2.  <span data-ttu-id="9a45f-126">Если в базе данных назначения отсутствует учетная запись «Guest», возвращается ошибка и трассировка воспроизводится от имени Пользователя1.</span><span class="sxs-lookup"><span data-stu-id="9a45f-126">If no Guest account exists on the target database, an error is returned and the trace is replayed as User1.</span></span>

 <span data-ttu-id="9a45f-127">На следующей диаграмме показан процесс проверки разрешений во время воспроизведения трассировок:</span><span class="sxs-lookup"><span data-stu-id="9a45f-127">The following diagram shows this process of checking permission when replaying traces:</span></span>

 <span data-ttu-id="9a45f-128">![Разрешения на воспроизведение трассировки SQL Server Profiler](../../database-engine/media/replaytracedecisiontree.gif "Разрешения на воспроизведение трассировки SQL Server Profiler")</span><span class="sxs-lookup"><span data-stu-id="9a45f-128">![SQL Server Profiler replay trace permissions](../../database-engine/media/replaytracedecisiontree.gif "SQL Server Profiler replay trace permissions")</span></span>

## <a name="see-also"></a><span data-ttu-id="9a45f-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a45f-129">See Also</span></span>
 <span data-ttu-id="9a45f-130">[SQL Server Profiler хранимых процедур &#40;Transact-SQL&#41;отслеживания](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [воспроизведения](replay-traces.md) [создают трассировку &#40;SQL Server Profiler](create-a-trace-sql-server-profiler.md)&#41;[воспроизведения таблицы трассировки](replay-a-trace-table-sql-server-profiler.md) &#40;SQL Server Profiler&#41;[воспроизведения файла трассировки](replay-a-trace-file-sql-server-profiler.md) &#40;SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9a45f-130">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [Replay Traces](replay-traces.md) [Create a Trace &#40;SQL Server Profiler&#41;](create-a-trace-sql-server-profiler.md) [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md)</span></span>


