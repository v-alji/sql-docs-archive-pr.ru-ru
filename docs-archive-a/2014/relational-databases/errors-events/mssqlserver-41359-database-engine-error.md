---
title: MSSQLSERVER_41359 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41359 (Database Engine error)
ms.assetid: 02b717c7-9170-4676-b0f6-4dec9eb5b5d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cf45a117dcda0827672c6072c603a1fc0866a33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667726"
---
# <a name="mssqlserver_41359"></a><span data-ttu-id="bf710-102">MSSQLSERVER_41359</span><span class="sxs-lookup"><span data-stu-id="bf710-102">MSSQLSERVER_41359</span></span>
    
## <a name="details"></a><span data-ttu-id="bf710-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bf710-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf710-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bf710-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="bf710-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bf710-105">Event ID</span></span>|<span data-ttu-id="bf710-106">41359</span><span class="sxs-lookup"><span data-stu-id="bf710-106">41359</span></span>|  
|<span data-ttu-id="bf710-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="bf710-107">Event Source</span></span>|<span data-ttu-id="bf710-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bf710-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bf710-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="bf710-109">Component</span></span>|<span data-ttu-id="bf710-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bf710-110">SQLEngine</span></span>|  
|<span data-ttu-id="bf710-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="bf710-111">Symbolic Name</span></span>|<span data-ttu-id="bf710-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="bf710-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="bf710-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bf710-113">Message Text</span></span>|<span data-ttu-id="bf710-114">Запрос, который обращается к оптимизированной для памяти таблице с использованием уровня изоляции READ COMMITTED, не может обратиться к дисковой таблице, если для параметра базы данных READ_COMMITTED_SNAPSHOT установлено значение ON.</span><span class="sxs-lookup"><span data-stu-id="bf710-114">A query that accesses memory optimized tables using the READ COMMITTED isolation level, cannot access disk based tables when the database option READ_COMMITTED_SNAPSHOT is set to ON.</span></span> <span data-ttu-id="bf710-115">Обеспечьте поддерживаемый уровень изоляции для оптимизированной для памяти таблицы с помощью табличного указания, например WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="bf710-115">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bf710-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bf710-116">Explanation</span></span>  
 <span data-ttu-id="bf710-117">База данных с параметром READ_COMMITTED_SNAPSHOT=ON не поддерживает транзакции, требующие доступа и к таблицам, оптимизированным для памяти, и к дисковым таблицам.</span><span class="sxs-lookup"><span data-stu-id="bf710-117">The database with READ_COMMITTED_SNAPSHOT=ON does not support the transactions that access both memory-optimized tables and disk based tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf710-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bf710-118">User Action</span></span>  
 <span data-ttu-id="bf710-119">Установите для параметра READ_COMMITTED_SNAPSHOT значение OFF или укажите поддерживаемый уровень изоляции для оптимизированной для памяти таблицы с помощью табличного указания, например WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="bf710-119">Set READ_COMMITTED_SNAPSHOT to OFF or supply a supported isolation level for the memory-optimized table using a table-level hint, such as WITH (SNAPSHOT).</span></span> <span data-ttu-id="bf710-120">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="bf710-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf710-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf710-121">See Also</span></span>  
 [<span data-ttu-id="bf710-122">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="bf710-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
