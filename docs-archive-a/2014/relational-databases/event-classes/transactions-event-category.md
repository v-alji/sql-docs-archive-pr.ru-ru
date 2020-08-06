---
title: Категория событий TransactionLog | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Transactions event category
- event classes [SQL Server], Transactions event category
- Transactions event category [SQL Server]
ms.assetid: bfc75c5b-7115-49d8-9148-a0c84ee66a9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b68a91fb166797c220cb0c4f5cf2607ca267538
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666629"
---
# <a name="transactions-event-category"></a><span data-ttu-id="9441a-102">Категория событий Transactions</span><span class="sxs-lookup"><span data-stu-id="9441a-102">Transactions Event Category</span></span>
  <span data-ttu-id="9441a-103">Классы событий **Transactions** могут использоваться для наблюдения за состоянием транзакций.</span><span class="sxs-lookup"><span data-stu-id="9441a-103">The **Transactions** event classes can be used to monitor the status of transactions.</span></span> <span data-ttu-id="9441a-104">Имена классов событий с префиксом **TM:** используются для отслеживания операций, связанных с транзакциями и передающихся через интерфейс управления транзакциями.</span><span class="sxs-lookup"><span data-stu-id="9441a-104">The event class names that are prefixed with **TM:** are used to track the transaction-related operations that are sent through the transaction management interface.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9441a-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="9441a-105">In This Section</span></span>  
  
|<span data-ttu-id="9441a-106">Раздел</span><span class="sxs-lookup"><span data-stu-id="9441a-106">Topic</span></span>|<span data-ttu-id="9441a-107">Description</span><span class="sxs-lookup"><span data-stu-id="9441a-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9441a-108">Класс событий DTCTransaction</span><span class="sxs-lookup"><span data-stu-id="9441a-108">DTCTransaction Event Class</span></span>](dtctransaction-event-class.md)|<span data-ttu-id="9441a-109">Отслеживает транзакции, управляемые координатором распределенных транзакций ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="9441a-109">Tracks transactions coordinated by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="9441a-110">Эти транзакции распределяются между двумя или более экземплярами компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9441a-110">These are transactions distributed between two or more databases or instances of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>|  
|[<span data-ttu-id="9441a-111">Класс событий SQLTransaction</span><span class="sxs-lookup"><span data-stu-id="9441a-111">SQLTransaction Event Class</span></span>](sqltransaction-event-class.md)|<span data-ttu-id="9441a-112">Отслеживает инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN и ROLLBACK TRAN.</span><span class="sxs-lookup"><span data-stu-id="9441a-112">Tracks [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN, and ROLLBACK TRAN statements.</span></span>|  
|[<span data-ttu-id="9441a-113">Класс событий TM: Begin Tran Completed</span><span class="sxs-lookup"><span data-stu-id="9441a-113">TM: Begin Tran Completed Event Class</span></span>](tm-begin-tran-completed-event-class.md)|<span data-ttu-id="9441a-114">Указывает, что запрос BEGIN TRANSACTION завершен.</span><span class="sxs-lookup"><span data-stu-id="9441a-114">Indicates that a BEGIN TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="9441a-115">Класс событий TM: Begin Tran Starting</span><span class="sxs-lookup"><span data-stu-id="9441a-115">TM: Begin Tran Starting Event Class</span></span>](tm-begin-tran-starting-event-class.md)|<span data-ttu-id="9441a-116">Указывает, что запрос BEGIN TRANSACTION начался.</span><span class="sxs-lookup"><span data-stu-id="9441a-116">Indicates that a BEGIN TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="9441a-117">Класс событий TM: Commit Tran Completed</span><span class="sxs-lookup"><span data-stu-id="9441a-117">TM: Commit Tran Completed Event Class</span></span>](tm-commit-tran-completed-event-class.md)|<span data-ttu-id="9441a-118">Указывает, что запрос COMMIT TRANSACTION завершен.</span><span class="sxs-lookup"><span data-stu-id="9441a-118">Indicates that a COMMIT TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="9441a-119">Класс событий TM: Commit Tran Starting</span><span class="sxs-lookup"><span data-stu-id="9441a-119">TM: Commit Tran Starting Event Class</span></span>](tm-commit-tran-starting-event-class.md)|<span data-ttu-id="9441a-120">Указывает, что запрос COMMIT TRANSACTION начался.</span><span class="sxs-lookup"><span data-stu-id="9441a-120">Indicates that a COMMIT TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="9441a-121">Класс событий TM: Promote Tran Completed</span><span class="sxs-lookup"><span data-stu-id="9441a-121">TM: Promote Tran Completed Event Class</span></span>](tm-promote-tran-completed-event-class.md)|<span data-ttu-id="9441a-122">Указывает, что запрос PROMOTE TRANSACTION завершен.</span><span class="sxs-lookup"><span data-stu-id="9441a-122">Indicates that a PROMOTE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="9441a-123">Класс событий TM: Promote Tran Starting</span><span class="sxs-lookup"><span data-stu-id="9441a-123">TM: Promote Tran Starting Event Class</span></span>](tm-promote-tran-starting-event-class.md)|<span data-ttu-id="9441a-124">Указывает, что запрос PROMOTE TRANSACTION начался.</span><span class="sxs-lookup"><span data-stu-id="9441a-124">Indicates that a PROMOTE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="9441a-125">Класс событий TM: Rollback Tran Completed</span><span class="sxs-lookup"><span data-stu-id="9441a-125">TM: Rollback Tran Completed Event Class</span></span>](tm-rollback-tran-completed-event-class.md)|<span data-ttu-id="9441a-126">Указывает, что запрос ROLLBACK TRANSACTION завершен.</span><span class="sxs-lookup"><span data-stu-id="9441a-126">Indicates that a ROLLBACK TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="9441a-127">Класс событий TM: Rollback Tran Starting</span><span class="sxs-lookup"><span data-stu-id="9441a-127">TM: Rollback Tran Starting Event Class</span></span>](tm-rollback-tran-starting-event-class.md)|<span data-ttu-id="9441a-128">Указывает, что запрос ROLLBACK TRANSACTION начался.</span><span class="sxs-lookup"><span data-stu-id="9441a-128">Indicates that a ROLLBACK TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="9441a-129">Класс событий TM: Save Tran Completed</span><span class="sxs-lookup"><span data-stu-id="9441a-129">TM: Save Tran Completed Event Class</span></span>](tm-save-tran-completed-event-class.md)|<span data-ttu-id="9441a-130">Указывает, что запрос SAVE TRANSACTION завершен.</span><span class="sxs-lookup"><span data-stu-id="9441a-130">Indicates that a SAVE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="9441a-131">Класс событий TM: Save Tran Starting</span><span class="sxs-lookup"><span data-stu-id="9441a-131">TM: Save Tran Starting Event Class</span></span>](tm-save-tran-starting-event-class.md)|<span data-ttu-id="9441a-132">Указывает, что запрос SAVE TRANSACTION начался.</span><span class="sxs-lookup"><span data-stu-id="9441a-132">Indicates that a SAVE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="9441a-133">Класс событий TransactionLog</span><span class="sxs-lookup"><span data-stu-id="9441a-133">TransactionLog Event Class</span></span>](transactionlog-event-class.md)|<span data-ttu-id="9441a-134">Отслеживает, когда записи о транзакциях появляются в журнале транзакций базы данных.</span><span class="sxs-lookup"><span data-stu-id="9441a-134">Tracks when transactions are written to a database transaction log.</span></span>|  
  
  
