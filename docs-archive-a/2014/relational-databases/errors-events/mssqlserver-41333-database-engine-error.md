---
title: MSSQLSERVER_41333 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41333 (Database Engine error)
ms.assetid: c3c3ae9a-1e4c-4de6-ba72-2f393375b053
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ba3cfc9627b4b44c3c9eccc620fb16bb94b861b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732694"
---
# <a name="mssqlserver_41333"></a><span data-ttu-id="53974-102">MSSQLSERVER_41333</span><span class="sxs-lookup"><span data-stu-id="53974-102">MSSQLSERVER_41333</span></span>
    
## <a name="details"></a><span data-ttu-id="53974-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="53974-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53974-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="53974-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="53974-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="53974-105">Event ID</span></span>|<span data-ttu-id="53974-106">41333</span><span class="sxs-lookup"><span data-stu-id="53974-106">41333</span></span>|  
|<span data-ttu-id="53974-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="53974-107">Event Source</span></span>|<span data-ttu-id="53974-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53974-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53974-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="53974-109">Component</span></span>|<span data-ttu-id="53974-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53974-110">SQLEngine</span></span>|  
|<span data-ttu-id="53974-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="53974-111">Symbolic Name</span></span>|<span data-ttu-id="53974-112">CROSS_CONTAINER_ISOLATION_FAILURE</span><span class="sxs-lookup"><span data-stu-id="53974-112">CROSS_CONTAINER_ISOLATION_FAILURE</span></span>|  
|<span data-ttu-id="53974-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="53974-113">Message Text</span></span>|<span data-ttu-id="53974-114">Следующие транзакции должны обращаться к таблицам, оптимизируемым для памяти, и к скомпилированным в собственном коде хранимым процедурам с уровнем изоляции моментального снимка: транзакции RepeatableRead, транзакции Serializable и транзакции, которые обращаются к не оптимизированным для памяти таблицам с уровнем изоляции RepeatableRead или Serializable.</span><span class="sxs-lookup"><span data-stu-id="53974-114">The following transactions must access memory optimized tables and natively compiled stored procedures under snapshot isolation: RepeatableRead transactions, Serializable transactions, and transactions that access tables that are not memory optimized in RepeatableRead or Serializable isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53974-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="53974-115">Explanation</span></span>  
 <span data-ttu-id="53974-116">Между дисковыми транзакциями и XTP-транзакциями существуют ограничения для пользователей на более высоких уровнях изоляции.</span><span class="sxs-lookup"><span data-stu-id="53974-116">There are restrictions against the user of the higher isolation levels between disk based transactions and XTP transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53974-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="53974-117">User Action</span></span>  
 <span data-ttu-id="53974-118">Не пытайтесь выполнять операции с высоким уровнем изоляции в оптимизируемых для памяти (и хранимым процедурам, оптимизированным в собственном коде) и дисковых таблицах.</span><span class="sxs-lookup"><span data-stu-id="53974-118">Don't attempt high level isolation operations on memory-optimized tables (and natively compiled procedures) and disk based tables.</span></span>  
  
 <span data-ttu-id="53974-119">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="53974-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53974-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="53974-120">See Also</span></span>  
 [<span data-ttu-id="53974-121">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="53974-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
