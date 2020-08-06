---
title: Вопросы воспроизведения трассировки (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 73fa339f-b71a-4be4-97ca-d4ae84c8b90b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c2f030a0191596e40ef1ee9e2b0b2d4da34c773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727602"
---
# <a name="considerations-for-replaying-traces-sql-server-profiler"></a><span data-ttu-id="0f18b-102">Вопросы воспроизведения трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="0f18b-102">Considerations for Replaying Traces (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="0f18b-103">не может воспроизводить следующие виды трассировки.</span><span class="sxs-lookup"><span data-stu-id="0f18b-103">cannot replay the following kinds of traces:</span></span>  
  
-   <span data-ttu-id="0f18b-104">Трассировки, содержащие репликацию транзакций и другие виды деятельности, связанной с журналами транзакций.</span><span class="sxs-lookup"><span data-stu-id="0f18b-104">Traces that contain transactional replication and other transaction log activity.</span></span> <span data-ttu-id="0f18b-105">Эти события пропускаются.</span><span class="sxs-lookup"><span data-stu-id="0f18b-105">These events are skipped.</span></span> <span data-ttu-id="0f18b-106">Другие типы репликации не затрагивают журнала транзакций, поэтому это к ним не относится.</span><span class="sxs-lookup"><span data-stu-id="0f18b-106">Other types of replication do not mark the transaction log so they are not affected.</span></span>  
  
-   <span data-ttu-id="0f18b-107">Трассировки, содержащие операции, в которых используются идентификаторы GUID.</span><span class="sxs-lookup"><span data-stu-id="0f18b-107">Traces that contain operations that involve globally unique identifiers (GUID).</span></span> <span data-ttu-id="0f18b-108">Эти события пропускаются.</span><span class="sxs-lookup"><span data-stu-id="0f18b-108">These events will be skipped.</span></span>  
  
-   <span data-ttu-id="0f18b-109">Трассировки, содержащие операции в столбцах типов данных **text**, **ntext**и **image** и использующие программу **bcp** , инструкции BULK INSERT, READTEXT, WRITETEXT и UPDATETEXT, а также полнотекстовые операции.</span><span class="sxs-lookup"><span data-stu-id="0f18b-109">Traces that contain operations on **text**, **ntext**, and **image** columns involving the **bcp** utility, the BULK INSERT, READTEXT, WRITETEXT, and UPDATETEXT statements, and full-text operations.</span></span> <span data-ttu-id="0f18b-110">Эти события пропускаются.</span><span class="sxs-lookup"><span data-stu-id="0f18b-110">These events are skipped.</span></span>  
  
-   <span data-ttu-id="0f18b-111">Трассировки, включающие в себя привязку сеансов: системные хранимые процедуры **sp_getbindtoken** и **sp_bindsession** .</span><span class="sxs-lookup"><span data-stu-id="0f18b-111">Traces that contain session binding: **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span> <span data-ttu-id="0f18b-112">Эти события пропускаются.</span><span class="sxs-lookup"><span data-stu-id="0f18b-112">These events are skipped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f18b-113">Если не используется предварительно настроенный шаблон воспроизведения (**TSQL_Replay**) и не выполняется сбор всех необходимых данных, приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] не воспроизводит трассировку.</span><span class="sxs-lookup"><span data-stu-id="0f18b-113">If you do not use the preconfigured replay template (**TSQL_Replay**), and do not capture all required data, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] does not replay the trace.</span></span> <span data-ttu-id="0f18b-114">Дополнительные сведения см. в разделе [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f18b-114">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
 <span data-ttu-id="0f18b-115">Сведения о разрешениях, необходимых для воспроизведения трассировки, см. в разделе [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="0f18b-115">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f18b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f18b-116">See Also</span></span>  
 <span data-ttu-id="0f18b-117">[bcp Utility](../bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0f18b-117">[bcp Utility](../bcp-utility.md) </span></span>  
 <span data-ttu-id="0f18b-118">[Справочник по классам событий SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0f18b-118">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="0f18b-119">[sp_getbindtoken (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f18b-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span></span>  
 <span data-ttu-id="0f18b-120">[sp_bindsession (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f18b-120">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 <span data-ttu-id="0f18b-121">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f18b-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="0f18b-122">[READTEXT (Transact-SQL)](/sql/t-sql/queries/readtext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f18b-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span></span>  
 <span data-ttu-id="0f18b-123">[WRITETEXT (Transact-SQL)](/sql/t-sql/queries/writetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f18b-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span></span>  
 [<span data-ttu-id="0f18b-124">UPDATETEXT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0f18b-124">UPDATETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/updatetext-transact-sql)  
  
  
