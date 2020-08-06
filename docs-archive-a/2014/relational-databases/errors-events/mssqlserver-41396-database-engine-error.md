---
title: MSSQLSERVER_41396 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41396 (Database Engine error)
ms.assetid: 4ff04042-8367-46f3-8a16-c94682d6eedb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2386c805b61631c9b843753d74ba6616e7344223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731621"
---
# <a name="mssqlserver_41396"></a><span data-ttu-id="0e1f1-102">MSSQLSERVER_41396</span><span class="sxs-lookup"><span data-stu-id="0e1f1-102">MSSQLSERVER_41396</span></span>
    
## <a name="details"></a><span data-ttu-id="0e1f1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="0e1f1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e1f1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="0e1f1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0e1f1-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0e1f1-105">Event ID</span></span>|<span data-ttu-id="0e1f1-106">41396</span><span class="sxs-lookup"><span data-stu-id="0e1f1-106">41396</span></span>|  
|<span data-ttu-id="0e1f1-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="0e1f1-107">Event Source</span></span>|<span data-ttu-id="0e1f1-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0e1f1-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0e1f1-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="0e1f1-109">Component</span></span>|<span data-ttu-id="0e1f1-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0e1f1-110">SQLEngine</span></span>|  
|<span data-ttu-id="0e1f1-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="0e1f1-111">Symbolic Name</span></span>|<span data-ttu-id="0e1f1-112">MAX_SORT_ROWS_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="0e1f1-112">MAX_SORT_ROWS_EXCEEDED</span></span>|  
|<span data-ttu-id="0e1f1-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="0e1f1-113">Message Text</span></span>|<span data-ttu-id="0e1f1-114">Операция сортировки превысила предел буфера.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-114">The sort operation exceeded the buffer limit.</span></span> <span data-ttu-id="0e1f1-115">Выполнение хранимой процедуры было прервано.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-115">The stored procedure execution was aborted.</span></span> <span data-ttu-id="0e1f1-116">Дополнительные сведения см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-116">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0e1f1-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="0e1f1-117">Explanation</span></span>  
 <span data-ttu-id="0e1f1-118">Изначально скомпилированные хранимые процедуры выполняют операции сортировки в памяти.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-118">Natively compiled stored procedures perform sort operations in memory.</span></span> <span data-ttu-id="0e1f1-119">Существуют ограничения на размер буфера сортировки.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-119">There is a limit on the size of the sort buffer.</span></span> <span data-ttu-id="0e1f1-120">Эта ошибка означает, что размер буфера сортировки превышает это ограничение.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-120">This error means that the size of the sort buffer exceeds this limit.</span></span> <span data-ttu-id="0e1f1-121">Операция сортировки и выполнение хранимой процедуры прерываются.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-121">The sort operation and the stored procedure execution aborted.</span></span>  
  
 <span data-ttu-id="0e1f1-122">Размер каждой строки или записи в буфере сортировки определяется числом отсортированных строк, а также количеством соединений и количеством и типом агрегатных функций в запросе.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-122">The size of each row or entry in the sort buffer is determined by the number of rows sorted as well as the number of joins and the number and type of aggregate functions in the query.</span></span> <span data-ttu-id="0e1f1-123">За счет упрощения запроса можно уменьшить размер каждой строки, таким образом уместив больше строк в буфере сортировки.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-123">By simplifying the query, you can reduce the size of each row thereby fitting more rows in the sort buffer.</span></span> <span data-ttu-id="0e1f1-124">Размер строк в базовых таблицах не влияет на размер каждой строки или записи в буфере сортировки.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-124">The size of the rows in the base tables does not affect the size of each row or entry in the sort buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e1f1-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="0e1f1-125">User Action</span></span>  
 <span data-ttu-id="0e1f1-126">Выберите меньшее количество строк или уменьшите сложность запроса путем удаления соединений или агрегатных функций.</span><span class="sxs-lookup"><span data-stu-id="0e1f1-126">Select fewer rows or decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1f1-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e1f1-127">See Also</span></span>  
 [<span data-ttu-id="0e1f1-128">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="0e1f1-128">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
