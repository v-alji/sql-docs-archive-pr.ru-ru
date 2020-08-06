---
title: Категория событий Stored Procedures | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Stored Procedures event category [SQL Server]
- SQL Server event classes, Stored Procedures event category
- event classes [SQL Server], Stored Procedures event category
ms.assetid: 71bebaa3-a05a-4695-b349-078cecd0949a
author: stevestein
ms.author: sstein
ms.openlocfilehash: df2e0d9a4c077ff16eba09bc5ebb6447d5d27595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752184"
---
# <a name="stored-procedures-event-category"></a><span data-ttu-id="36c7b-102">Категория событий Stored Procedures</span><span class="sxs-lookup"><span data-stu-id="36c7b-102">Stored Procedures Event Category</span></span>
  <span data-ttu-id="36c7b-103">Категория событий **Stored Procedures** содержит общие события хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="36c7b-103">The **Stored Procedures** event category contains general stored procedure events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36c7b-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="36c7b-104">In This Section</span></span>  
  
|<span data-ttu-id="36c7b-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="36c7b-105">Topic</span></span>|<span data-ttu-id="36c7b-106">Description</span><span class="sxs-lookup"><span data-stu-id="36c7b-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="36c7b-107">Класс событий RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="36c7b-107">RPC:Completed Event Class</span></span>](rpc-completed-event-class.md)|<span data-ttu-id="36c7b-108">Указывает на завершение удаленного вызова процедуры (RPC).</span><span class="sxs-lookup"><span data-stu-id="36c7b-108">Indicates that a remote procedure call (RPC) has been completed.</span></span>|  
|[<span data-ttu-id="36c7b-109">Класс событий PreConnect:Completed</span><span class="sxs-lookup"><span data-stu-id="36c7b-109">PreConnect:Completed Event Class</span></span>](preconnect-completed-event-class.md)|<span data-ttu-id="36c7b-110">Указывает, что функция-классификатор регулятора ресурсов завершает выполнение.</span><span class="sxs-lookup"><span data-stu-id="36c7b-110">Indicates when the Resource Governor classifier function finishes execution.</span></span>|  
|[<span data-ttu-id="36c7b-111">PreConnect:Starting, класс событий</span><span class="sxs-lookup"><span data-stu-id="36c7b-111">PreConnect:Starting Event Class</span></span>](preconnect-starting-event-class.md)|<span data-ttu-id="36c7b-112">Указывает, что запускается функция-классификатор регулятора ресурсов.</span><span class="sxs-lookup"><span data-stu-id="36c7b-112">Indicates when the Resource Governor classifier function starts execution.</span></span>|  
|[<span data-ttu-id="36c7b-113">Класс событий RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="36c7b-113">RPC Output Parameter Event Class</span></span>](rpc-output-parameter-event-class.md)|<span data-ttu-id="36c7b-114">Отслеживает выходные значения параметров удаленного вызова процедуры после выполнения.</span><span class="sxs-lookup"><span data-stu-id="36c7b-114">Traces the output parameter values of remote procedure calls after execution.</span></span>|  
|[<span data-ttu-id="36c7b-115">Класс событий RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="36c7b-115">RPC:Starting Event Class</span></span>](rpc-starting-event-class.md)|<span data-ttu-id="36c7b-116">Указывает на начало удаленного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="36c7b-116">Indicates that a remote procedure call is starting.</span></span>|  
|[<span data-ttu-id="36c7b-117">Класс событий SP:CacheHit</span><span class="sxs-lookup"><span data-stu-id="36c7b-117">SP:CacheHit Event Class</span></span>](sp-cachehit-event-class.md)|<span data-ttu-id="36c7b-118">Указывает, что хранимая процедура хранится в кэше.</span><span class="sxs-lookup"><span data-stu-id="36c7b-118">Indicates that the stored procedure is in the cache.</span></span>|  
|[<span data-ttu-id="36c7b-119">Класс событий SP:CacheInsert</span><span class="sxs-lookup"><span data-stu-id="36c7b-119">SP:CacheInsert Event Class</span></span>](sp-cacheinsert-event-class.md)|<span data-ttu-id="36c7b-120">Указывает, что хранимая процедура была помещена в кэш.</span><span class="sxs-lookup"><span data-stu-id="36c7b-120">Indicates that the stored procedure has been brought into the cache.</span></span>|  
|[<span data-ttu-id="36c7b-121">Класс событий SP:CacheMiss</span><span class="sxs-lookup"><span data-stu-id="36c7b-121">SP:CacheMiss Event Class</span></span>](sp-cachemiss-event-class.md)|<span data-ttu-id="36c7b-122">Указывает, что хранимую процедуру не удалось найти в кэше.</span><span class="sxs-lookup"><span data-stu-id="36c7b-122">Indicates that the stored procedure was not found in the cache.</span></span>|  
|[<span data-ttu-id="36c7b-123">Класс событий SP:CacheRemove</span><span class="sxs-lookup"><span data-stu-id="36c7b-123">SP:CacheRemove Event Class</span></span>](sp-cacheremove-event-class.md)|<span data-ttu-id="36c7b-124">Указывает, что хранимая процедура была удалена из кэша.</span><span class="sxs-lookup"><span data-stu-id="36c7b-124">Indicates that the stored procedure has been removed from the cache.</span></span>|  
|[<span data-ttu-id="36c7b-125">Класс событий SP:Completed</span><span class="sxs-lookup"><span data-stu-id="36c7b-125">SP:Completed Event Class</span></span>](sp-completed-event-class.md)|<span data-ttu-id="36c7b-126">Указывает, что выполнение хранимой процедуры завершено.</span><span class="sxs-lookup"><span data-stu-id="36c7b-126">Indicates that execution of the stored procedure has completed.</span></span>|  
|[<span data-ttu-id="36c7b-127">Класс событий SP:Recompile</span><span class="sxs-lookup"><span data-stu-id="36c7b-127">SP:Recompile Event Class</span></span>](sp-recompile-event-class.md)|<span data-ttu-id="36c7b-128">Указывает, что осуществляется повторная компиляция хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="36c7b-128">Indicates that the stored procedure has been recompiled.</span></span>|  
|[<span data-ttu-id="36c7b-129">Класс событий SP:Starting</span><span class="sxs-lookup"><span data-stu-id="36c7b-129">SP:Starting Event Class</span></span>](sp-starting-event-class.md)|<span data-ttu-id="36c7b-130">Указывает на начало выполнения хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="36c7b-130">Indicates that execution of the stored procedure is starting.</span></span>|  
|[<span data-ttu-id="36c7b-131">Класс событий SP:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="36c7b-131">SP:StmtCompleted Event Class</span></span>](sp-stmtcompleted-event-class.md)|<span data-ttu-id="36c7b-132">Указывает, что завершено выполнение инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] в хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="36c7b-132">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has completed.</span></span>|  
|[<span data-ttu-id="36c7b-133">Класс событий SP:StmtStarting</span><span class="sxs-lookup"><span data-stu-id="36c7b-133">SP:StmtStarting Event Class</span></span>](sp-stmtstarting-event-class.md)|<span data-ttu-id="36c7b-134">Указывает на начало выполнения инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] в хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="36c7b-134">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has started.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36c7b-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="36c7b-135">See Also</span></span>  
 <span data-ttu-id="36c7b-136">[Расширенные события](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="36c7b-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="36c7b-137">Хранимая процедура sp_trace_setevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="36c7b-137">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
