---
title: Категория событий TSQL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, TSQL event category
- TSQL event category [SQL Server]
- event classes [SQL Server], TSQL event category
ms.assetid: 215f8747-64b5-4bf3-9845-d476b10cda3a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 763d5f31fd3562f54b274a74324ed4715b623a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728282"
---
# <a name="tsql-event-category"></a><span data-ttu-id="92296-102">Категория событий TSQL</span><span class="sxs-lookup"><span data-stu-id="92296-102">TSQL Event Category</span></span>
  <span data-ttu-id="92296-103">Категория событий **TSQL** включает общие события TSQL.</span><span class="sxs-lookup"><span data-stu-id="92296-103">The **TSQL** event category contains general TSQL events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92296-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="92296-104">In This Section</span></span>  
  
|<span data-ttu-id="92296-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="92296-105">Topic</span></span>|<span data-ttu-id="92296-106">Description</span><span class="sxs-lookup"><span data-stu-id="92296-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="92296-107">Класс событий Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="92296-107">Exec Prepared SQL Event Class</span></span>](exec-prepared-sql-event-class.md)|<span data-ttu-id="92296-108">Указывает, что SqlClient, ODBC, OLE DB или DB-Library выполнили подготовленные инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92296-108">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has executed a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="92296-109">Класс событий Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="92296-109">Prepare SQL Event Class</span></span>](prepare-sql-event-class.md)|<span data-ttu-id="92296-110">Указывает, что SqlClient, ODBC, OLE DB или DB-Library подготовили для использования инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92296-110">Indicates that SqlClient, ODBC, OLE DB, or DB-Library has prepared a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements for use.</span></span>|  
|[<span data-ttu-id="92296-111">Класс событий SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="92296-111">SQL:BatchCompleted Event Class</span></span>](sql-batchcompleted-event-class.md)|<span data-ttu-id="92296-112">Указывает, что выполнение пакета языка [!INCLUDE[tsql](../../includes/tsql-md.md)] завершено.</span><span class="sxs-lookup"><span data-stu-id="92296-112">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch has completed.</span></span>|  
|[<span data-ttu-id="92296-113">Класс событий SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="92296-113">SQL:BatchStarting Event Class</span></span>](sql-batchstarting-event-class.md)|<span data-ttu-id="92296-114">Указывает, что выполнение пакета языка [!INCLUDE[tsql](../../includes/tsql-md.md)] начато.</span><span class="sxs-lookup"><span data-stu-id="92296-114">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch is starting.</span></span>|  
|[<span data-ttu-id="92296-115">Класс событий SQL:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="92296-115">SQL:StmtCompleted Event Class</span></span>](sql-stmtcompleted-event-class.md)|<span data-ttu-id="92296-116">Указывает, что выполнение инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] завершено.</span><span class="sxs-lookup"><span data-stu-id="92296-116">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement has completed.</span></span>|  
|[<span data-ttu-id="92296-117">Класс событий SQL:StmtRecompile</span><span class="sxs-lookup"><span data-stu-id="92296-117">SQL:StmtRecompile Event Class</span></span>](sql-stmtrecompile-event-class.md)|<span data-ttu-id="92296-118">Указывает на повторные компиляции уровня инструкций, инициированные всеми типами пакетов: хранимыми процедурами, триггерами, нерегламентированными пакетами и запросами.</span><span class="sxs-lookup"><span data-stu-id="92296-118">Indicates statement-level recompilations caused by all types of batches: stored procedures, triggers, ad hoc batches, and queries.</span></span>|  
|[<span data-ttu-id="92296-119">Класс событий SQL:StmtStarting</span><span class="sxs-lookup"><span data-stu-id="92296-119">SQL:StmtStarting Event Class</span></span>](sql-stmtstarting-event-class.md)|<span data-ttu-id="92296-120">Указывает, что выполнение инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] начато.</span><span class="sxs-lookup"><span data-stu-id="92296-120">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is starting.</span></span>|  
|[<span data-ttu-id="92296-121">Класс событий Unprepare SQL</span><span class="sxs-lookup"><span data-stu-id="92296-121">Unprepare SQL Event Class</span></span>](unprepare-sql-event-class.md)|<span data-ttu-id="92296-122">Указывает, что SqlClient, ODBC, OLE DB или DB-Library удалили подготовленные инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92296-122">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has deleted a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="92296-123">Класс событий XQuery Static Type</span><span class="sxs-lookup"><span data-stu-id="92296-123">XQuery Static Type Event Class</span></span>](xquery-static-type-event-class.md)|<span data-ttu-id="92296-124">Возникает, если сервер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет выражение XQuery.</span><span class="sxs-lookup"><span data-stu-id="92296-124">Occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes an XQuery expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92296-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="92296-125">See Also</span></span>  
 [<span data-ttu-id="92296-126">Справочник по Transact-SQL (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="92296-126">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
