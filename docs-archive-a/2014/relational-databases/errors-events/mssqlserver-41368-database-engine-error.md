---
title: MSSQLSERVER_41368 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41368 (Database Engine error)
ms.assetid: abc71559-4c4d-4cce-a08f-3299dd167842
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 10e187223a3f35b4b21ede6965e3c9efea2e30c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731629"
---
# <a name="mssqlserver_41368"></a><span data-ttu-id="bfc9c-102">MSSQLSERVER_41368</span><span class="sxs-lookup"><span data-stu-id="bfc9c-102">MSSQLSERVER_41368</span></span>
    
## <a name="details"></a><span data-ttu-id="bfc9c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bfc9c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bfc9c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bfc9c-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="bfc9c-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bfc9c-105">Event ID</span></span>|<span data-ttu-id="bfc9c-106">41368</span><span class="sxs-lookup"><span data-stu-id="bfc9c-106">41368</span></span>|  
|<span data-ttu-id="bfc9c-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="bfc9c-107">Event Source</span></span>|<span data-ttu-id="bfc9c-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bfc9c-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bfc9c-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="bfc9c-109">Component</span></span>|<span data-ttu-id="bfc9c-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bfc9c-110">SQLEngine</span></span>|  
|<span data-ttu-id="bfc9c-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="bfc9c-111">Symbolic Name</span></span>|<span data-ttu-id="bfc9c-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="bfc9c-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="bfc9c-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bfc9c-113">Message Text</span></span>|<span data-ttu-id="bfc9c-114">Доступ к оптимизированным для памяти таблицам с уровнем изоляции READ COMMITTED поддерживается только для транзакций с автоматической фиксацией.</span><span class="sxs-lookup"><span data-stu-id="bfc9c-114">Accessing memory optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="bfc9c-115">Он не поддерживается для явных или неявных транзакций.</span><span class="sxs-lookup"><span data-stu-id="bfc9c-115">It is not supported for explicit or implicit transactions.</span></span> <span data-ttu-id="bfc9c-116">Обеспечьте поддерживаемый уровень изоляции для оптимизированной для памяти таблицы с помощью табличного указания, например WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="bfc9c-116">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bfc9c-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bfc9c-117">Explanation</span></span>  
 <span data-ttu-id="bfc9c-118">Доступ к оптимизированным для памяти таблицам с уровнем изоляции READ COMMITTED поддерживается только для транзакций с автоматической фиксацией.</span><span class="sxs-lookup"><span data-stu-id="bfc9c-118">Accessing memory-optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="bfc9c-119">Дополнительные сведения см. в разделе [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="bfc9c-119">For more information, see [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span></span>  
  
 <span data-ttu-id="bfc9c-120">При доступе к оптимизированной для памяти таблицы из явной транзакции, начатой с помощью BEGIN TRANSACTION, или из неявной транзакции, если параметр IMPLICIT_TRANSACTIONS имеет значение ON, уровень изоляции READ COMMITTED не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bfc9c-120">When accessing a memory-optimized table from an explicit transaction that was started with BEGIN TRANSACTION, or from an implicit transaction, if IMPLICIT_TRANSACTIONS is set to ON, the READ COMMITTED isolation level is not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bfc9c-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bfc9c-121">User Action</span></span>  
 <span data-ttu-id="bfc9c-122">При доступе к оптимизированной для памяти таблице из явной или неявной транзакции с изоляцией READ COMMITTED, используйте для доступа к таблице моментальный снимок (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="bfc9c-122">When accessing a memory-optimized table from an explicit or implicit READ COMMITTED transaction, use SNAPSHOT to access the table.</span></span> <span data-ttu-id="bfc9c-123">Это можно сделать с помощью табличной подсказки WITH (МОМЕНТАЛЬный снимок) (Дополнительные сведения см. в разделе [рекомендации по уровню изоляции транзакций с оптимизированными для памяти таблицами](../in-memory-oltp/memory-optimized-tables.md)) или при установке параметра базы данных MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT в значение On (Дополнительные сведения см. в разделе [Параметры ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span><span class="sxs-lookup"><span data-stu-id="bfc9c-123">This can be achieved by using the table hint WITH (SNAPSHOT) (for more information, see [Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md)) or by setting the database option MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT to ON (for more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc9c-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="bfc9c-124">See Also</span></span>  
 [<span data-ttu-id="bfc9c-125">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="bfc9c-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
