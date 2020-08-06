---
title: MSSQLSERVER_844 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4870d6e43ec12b49033ea3b5f88fa0d0cdd597a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658286"
---
# <a name="mssqlserver_844"></a><span data-ttu-id="44c24-102">MSSQLSERVER_844</span><span class="sxs-lookup"><span data-stu-id="44c24-102">MSSQLSERVER_844</span></span>
    
## <a name="details"></a><span data-ttu-id="44c24-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="44c24-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44c24-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="44c24-104">Product Name</span></span>|<span data-ttu-id="44c24-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="44c24-105">SQL Server</span></span>|  
|<span data-ttu-id="44c24-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="44c24-106">Event ID</span></span>|<span data-ttu-id="44c24-107">844</span><span class="sxs-lookup"><span data-stu-id="44c24-107">844</span></span>|  
|<span data-ttu-id="44c24-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="44c24-108">Event Source</span></span>|<span data-ttu-id="44c24-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="44c24-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="44c24-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="44c24-110">Component</span></span>|<span data-ttu-id="44c24-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="44c24-111">SQLEngine</span></span>|  
|<span data-ttu-id="44c24-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="44c24-112">Symbolic Name</span></span>|<span data-ttu-id="44c24-113">BUFLATCH_TIMEOUT_CONTINUE</span><span class="sxs-lookup"><span data-stu-id="44c24-113">BUFLATCH_TIMEOUT_CONTINUE</span></span>|  
|<span data-ttu-id="44c24-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="44c24-114">Message Text</span></span>|<span data-ttu-id="44c24-115">Истекло время ожидания кратковременной блокировки буфера — тип %d, базовая точка %p, страница %d:%d, stat %#x, идентификатор базы данных: %d, идентификатор единицы распределения: %I64d%ls, задача 0x%p: %d, время ожидания %d, флаги 0x%I64x, задача-владелец 0x%p.</span><span class="sxs-lookup"><span data-stu-id="44c24-115">Time-out occurred while waiting for buffer latch -- type %d, bp %p, page %d:%d, stat %#x, database id: %d, allocation unit id: %I64d%ls, task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span>  <span data-ttu-id="44c24-116">Продолжение ожидания.</span><span class="sxs-lookup"><span data-stu-id="44c24-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44c24-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="44c24-117">Explanation</span></span>  
 <span data-ttu-id="44c24-118">Процесс ожидает получения кратковременной блокировки.</span><span class="sxs-lookup"><span data-stu-id="44c24-118">A process is waiting to acquire a latch.</span></span> <span data-ttu-id="44c24-119">Эта проблема может быть вызвана слишком продолжительной операцией ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="44c24-119">This problem can be caused by an I/O operation taking too long to complete.</span></span> <span data-ttu-id="44c24-120">Как правило, этот тип ошибки возникает в результате блокирования системных процессов другими задачами.</span><span class="sxs-lookup"><span data-stu-id="44c24-120">Typically this type of error is the result of other tasks blocking system processes.</span></span> <span data-ttu-id="44c24-121">В некоторых случаях эта ошибка может возникать в результате сбоя оборудования.</span><span class="sxs-lookup"><span data-stu-id="44c24-121">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44c24-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="44c24-122">User Action</span></span>  
 <span data-ttu-id="44c24-123">Для предотвращения этой ошибки попробуйте предпринять следующее.</span><span class="sxs-lookup"><span data-stu-id="44c24-123">Try the following to prevent this error from occurring:</span></span>  
  
-   <span data-ttu-id="44c24-124">Снизьте рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="44c24-124">Reduce workload.</span></span>  
  
-   <span data-ttu-id="44c24-125">В журнале ошибок или журнале событий проверьте соответствующие сбои операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="44c24-125">Check for associated I/O failures in error log or event log.</span></span> <span data-ttu-id="44c24-126">Сбои операций ввода-вывода обычно указывают на неправильную работу диска.</span><span class="sxs-lookup"><span data-stu-id="44c24-126">I/O failures typically point to a disk malfunction.</span></span>  
  
-   <span data-ttu-id="44c24-127">В журнале ошибок проверьте наличие невыполненных задач и других критических ошибок.</span><span class="sxs-lookup"><span data-stu-id="44c24-127">Check the error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="44c24-128">Если критические ошибки встречаются часто, устраните их причину.</span><span class="sxs-lookup"><span data-stu-id="44c24-128">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="44c24-129">Если ошибка продолжает возникать, обратитесь в службу поддержки пользователей корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="44c24-129">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
