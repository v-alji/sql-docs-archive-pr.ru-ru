---
title: MSSQLSERVER_41399 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e134cbc8b39a3c65d9c515183243f0b4caed434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658287"
---
# <a name="mssqlserver_41399"></a><span data-ttu-id="8954f-102">MSSQLSERVER_41399</span><span class="sxs-lookup"><span data-stu-id="8954f-102">MSSQLSERVER_41399</span></span>
    
## <a name="details"></a><span data-ttu-id="8954f-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="8954f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8954f-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="8954f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8954f-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="8954f-105">Event ID</span></span>|<span data-ttu-id="8954f-106">41399</span><span class="sxs-lookup"><span data-stu-id="8954f-106">41399</span></span>|  
|<span data-ttu-id="8954f-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="8954f-107">Event Source</span></span>|<span data-ttu-id="8954f-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8954f-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8954f-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="8954f-109">Component</span></span>|<span data-ttu-id="8954f-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8954f-110">SQLEngine</span></span>|  
|<span data-ttu-id="8954f-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="8954f-111">Symbolic Name</span></span>|<span data-ttu-id="8954f-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="8954f-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span></span>|  
|<span data-ttu-id="8954f-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="8954f-113">Message Text</span></span>|<span data-ttu-id="8954f-114">Слишком сложная операция сортировки.</span><span class="sxs-lookup"><span data-stu-id="8954f-114">The sort operation is too complex.</span></span> <span data-ttu-id="8954f-115">Дополнительные сведения см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8954f-115">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8954f-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="8954f-116">Explanation</span></span>  
 <span data-ttu-id="8954f-117">Сортировка результата операций соединения и агрегации увеличивает сложность операции сортировки за счет увеличения размера строки в буфере сортировки.</span><span class="sxs-lookup"><span data-stu-id="8954f-117">Sorting the result of join and aggregation operations increases the complexity of the sort operation by increasing the size of the row in the sort buffer.</span></span> <span data-ttu-id="8954f-118">Эта ошибка означает, что размер строки превышает максимальный размер, поддерживаемый оператором сортировки в изначально скомпилированных хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="8954f-118">This error means that the size of the row is larger than the maximum size supported by the sort operator in natively compiled stored procedures.</span></span> <span data-ttu-id="8954f-119">Обратите внимание, что размер строки в буфере сортировки определяется только количеством соединений и количеством и типом агрегатных функций.</span><span class="sxs-lookup"><span data-stu-id="8954f-119">Note that the size of a row in the sort buffer is determined solely by the number of joins and the number and type of aggregate functions.</span></span> <span data-ttu-id="8954f-120">Размер строк в базовых таблицах не влияет на размер строки в буфере.</span><span class="sxs-lookup"><span data-stu-id="8954f-120">The size of the rows in the base tables does not affect the size of the row in the buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8954f-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="8954f-121">User Action</span></span>  
 <span data-ttu-id="8954f-122">Уменьшить сложность запроса путем удаления соединений или агрегатных функций.</span><span class="sxs-lookup"><span data-stu-id="8954f-122">Decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8954f-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="8954f-123">See Also</span></span>  
 [<span data-ttu-id="8954f-124">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="8954f-124">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
