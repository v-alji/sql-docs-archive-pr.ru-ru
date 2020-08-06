---
title: MSSQLSERVER_41332 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41332 (Database Engine error)
ms.assetid: d3403c3e-d178-4006-b6c9-c18609562db5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72a87838673f07f7a40596517ab54533d944e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666094"
---
# <a name="mssqlserver_41332"></a><span data-ttu-id="63cd3-102">MSSQLSERVER_41332</span><span class="sxs-lookup"><span data-stu-id="63cd3-102">MSSQLSERVER_41332</span></span>
    
## <a name="details"></a><span data-ttu-id="63cd3-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="63cd3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63cd3-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="63cd3-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="63cd3-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="63cd3-105">Event ID</span></span>|<span data-ttu-id="63cd3-106">41332</span><span class="sxs-lookup"><span data-stu-id="63cd3-106">41332</span></span>|  
|<span data-ttu-id="63cd3-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="63cd3-107">Event Source</span></span>|<span data-ttu-id="63cd3-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="63cd3-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="63cd3-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="63cd3-109">Component</span></span>|<span data-ttu-id="63cd3-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="63cd3-110">SQLEngine</span></span>|  
|<span data-ttu-id="63cd3-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="63cd3-111">Symbolic Name</span></span>|<span data-ttu-id="63cd3-112">SQL_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="63cd3-112">SQL_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="63cd3-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="63cd3-113">Message Text</span></span>|<span data-ttu-id="63cd3-114">Если для сеанса TRANSACTION ISOLATION LEVEL задано значение SNAPSHOT, нельзя создать оптимизированные для памяти таблицы и скомпилированные в собственном коде хранимые процедуры или получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="63cd3-114">Memory optimized tables and natively compiled stored procedures cannot be accessed or created when the session TRANSACTION ISOLATION LEVEL is set to SNAPSHOT.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="63cd3-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="63cd3-115">Explanation</span></span>  
 <span data-ttu-id="63cd3-116">Транзакция была запущена на уровне изоляции моментального снимка, а затем попыталась использовать несовместимую функцию.</span><span class="sxs-lookup"><span data-stu-id="63cd3-116">The transaction was started in snapshot isolation level and then attempted to use an incompatible feature.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="63cd3-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="63cd3-117">User Action</span></span>  
 <span data-ttu-id="63cd3-118">Запустите транзакцию с другим уровнем изоляции.</span><span class="sxs-lookup"><span data-stu-id="63cd3-118">Start the transaction with a different isolation level.</span></span> <span data-ttu-id="63cd3-119">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="63cd3-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63cd3-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="63cd3-120">See Also</span></span>  
 [<span data-ttu-id="63cd3-121">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="63cd3-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
