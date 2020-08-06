---
title: MSSQLSERVER_845 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 845 (Database Engine error)
ms.assetid: 8fff6ad4-234c-44be-b123-e25d5e1cd63e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 24bfb8b3758d0656dad96e4af4ed3b94aa51e07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658282"
---
# <a name="mssqlserver_845"></a><span data-ttu-id="4621d-102">MSSQLSERVER_845</span><span class="sxs-lookup"><span data-stu-id="4621d-102">MSSQLSERVER_845</span></span>
    
## <a name="details"></a><span data-ttu-id="4621d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="4621d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4621d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="4621d-104">Product Name</span></span>|<span data-ttu-id="4621d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4621d-105">SQL Server</span></span>|  
|<span data-ttu-id="4621d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4621d-106">Event ID</span></span>|<span data-ttu-id="4621d-107">845</span><span class="sxs-lookup"><span data-stu-id="4621d-107">845</span></span>|  
|<span data-ttu-id="4621d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="4621d-108">Event Source</span></span>|<span data-ttu-id="4621d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4621d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4621d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4621d-110">Component</span></span>|<span data-ttu-id="4621d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4621d-111">SQLEngine</span></span>|  
|<span data-ttu-id="4621d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="4621d-112">Symbolic Name</span></span>|<span data-ttu-id="4621d-113">BUFLATCH_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4621d-113">BUFLATCH_TIMEOUT</span></span>|  
|<span data-ttu-id="4621d-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="4621d-114">Message Text</span></span>|<span data-ttu-id="4621d-115">Истекло время ожидания кратковременной блокировки буфера — тип %d, страница %S_PGID, идентификатор базы данных %d.</span><span class="sxs-lookup"><span data-stu-id="4621d-115">Time-out occurred while waiting for buffer latch type %d for page %S_PGID, database ID %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4621d-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="4621d-116">Explanation</span></span>  
 <span data-ttu-id="4621d-117">Процесс ожидал получения кратковременной блокировки, но время ожидания истекло, и блокировку не удалось получить.</span><span class="sxs-lookup"><span data-stu-id="4621d-117">A process was waiting to acquire a latch, but the process waited until the time limit expired and failed to acquire one.</span></span> <span data-ttu-id="4621d-118">Это может произойти, если операциях ввода-вывода выполняется слишком долго. Обычно это происходит в результате блокировки системных процессов другими задачами.</span><span class="sxs-lookup"><span data-stu-id="4621d-118">This can occur if an I/O operation takes too long to complete, usually as a result of other tasks blocking system processes.</span></span> <span data-ttu-id="4621d-119">В некоторых случаях эта ошибка может возникать в результате сбоя оборудования.</span><span class="sxs-lookup"><span data-stu-id="4621d-119">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4621d-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="4621d-120">User Action</span></span>  
 <span data-ttu-id="4621d-121">Для того чтобы предотвратить эту ошибку, выполните следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4621d-121">Performing the following tasks may prevent this error:</span></span>  
  
-   <span data-ttu-id="4621d-122">Уменьшите рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="4621d-122">Reduce the workload.</span></span>  
  
-   <span data-ttu-id="4621d-123">Убедитесь, что в журнале событий или журнале ошибок присутствуют взаимосвязанные сбои операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4621d-123">Verify whether there are associated I/O failures in the error log or event log.</span></span> <span data-ttu-id="4621d-124">Сбои операций ввода-вывода обычно вызваны неправильной работой диска.</span><span class="sxs-lookup"><span data-stu-id="4621d-124">I/O failures are typically caused by disk malfunction.</span></span>  
  
-   <span data-ttu-id="4621d-125">Проверьте наличие невыполненных задач и других критических ошибок в журнале ошибок.</span><span class="sxs-lookup"><span data-stu-id="4621d-125">Check error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="4621d-126">Если критические ошибки встречаются часто, устраните их причину.</span><span class="sxs-lookup"><span data-stu-id="4621d-126">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="4621d-127">Если ошибка продолжает возникать, обратитесь в службу поддержки пользователей корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4621d-127">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
