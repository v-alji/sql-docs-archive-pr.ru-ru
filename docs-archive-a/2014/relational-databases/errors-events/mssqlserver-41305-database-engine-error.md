---
title: MSSQLSERVER_41305 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41305 (Database Engine error)
ms.assetid: a96e5083-ff97-4003-a900-07942454151d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9c00e20ec220d7fcee0da4e99c2ef35817dae67f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665361"
---
# <a name="mssqlserver_41305"></a><span data-ttu-id="a58a4-102">MSSQLSERVER_41305</span><span class="sxs-lookup"><span data-stu-id="a58a4-102">MSSQLSERVER_41305</span></span>
    
## <a name="details"></a><span data-ttu-id="a58a4-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a58a4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a58a4-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a58a4-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a58a4-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a58a4-105">Event ID</span></span>|<span data-ttu-id="a58a4-106">41305</span><span class="sxs-lookup"><span data-stu-id="a58a4-106">41305</span></span>|  
|<span data-ttu-id="a58a4-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="a58a4-107">Event Source</span></span>|<span data-ttu-id="a58a4-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a58a4-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a58a4-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="a58a4-109">Component</span></span>|<span data-ttu-id="a58a4-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a58a4-110">SQLEngine</span></span>|  
|<span data-ttu-id="a58a4-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a58a4-111">Symbolic Name</span></span>|<span data-ttu-id="a58a4-112">HK_TX_COMMIT_RR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="a58a4-112">HK_TX_COMMIT_RR_VALIDATION</span></span>|  
|<span data-ttu-id="a58a4-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a58a4-113">Message Text</span></span>|<span data-ttu-id="a58a4-114">Текущей транзакции не удалось выполнить фиксацию из-за ошибки проверки уровня изоляции REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="a58a4-114">The current transaction failed to commit due to a repeatable read validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a58a4-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a58a4-115">Explanation</span></span>  
 <span data-ttu-id="a58a4-116">В ходе транзакции произошла ошибка проверки, поэтому транзакция завершается.</span><span class="sxs-lookup"><span data-stu-id="a58a4-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
 <span data-ttu-id="a58a4-117">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="a58a4-117">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a58a4-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a58a4-118">User Action</span></span>  
 <span data-ttu-id="a58a4-119">Повторите поврежденную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="a58a4-119">Retry the failed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a58a4-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a58a4-120">See Also</span></span>  
 [<span data-ttu-id="a58a4-121">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="a58a4-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
