---
title: MSSQLSERVER_41325 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41325 (Database Engine error)
ms.assetid: 97c6a8bb-139a-44f3-9ed5-f46d047e8ed3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a512d7db6529876259d889d04aabf3d07747cafe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732693"
---
# <a name="mssqlserver_41325"></a><span data-ttu-id="ae2a4-102">MSSQLSERVER_41325</span><span class="sxs-lookup"><span data-stu-id="ae2a4-102">MSSQLSERVER_41325</span></span>
    
## <a name="details"></a><span data-ttu-id="ae2a4-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="ae2a4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae2a4-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ae2a4-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="ae2a4-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ae2a4-105">Event ID</span></span>|<span data-ttu-id="ae2a4-106">41325</span><span class="sxs-lookup"><span data-stu-id="ae2a4-106">41325</span></span>|  
|<span data-ttu-id="ae2a4-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="ae2a4-107">Event Source</span></span>|<span data-ttu-id="ae2a4-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ae2a4-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ae2a4-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="ae2a4-109">Component</span></span>|<span data-ttu-id="ae2a4-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ae2a4-110">SQLEngine</span></span>|  
|<span data-ttu-id="ae2a4-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ae2a4-111">Symbolic Name</span></span>|<span data-ttu-id="ae2a4-112">HK_TX_COMMIT_SR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="ae2a4-112">HK_TX_COMMIT_SR_VALIDATION</span></span>|  
|<span data-ttu-id="ae2a4-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ae2a4-113">Message Text</span></span>|<span data-ttu-id="ae2a4-114">Текущей транзакции не удалось выполнить фиксацию из-за ошибки сериализуемой проверки.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-114">The current transaction failed to commit due to a serializable validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ae2a4-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ae2a4-115">Explanation</span></span>  
 <span data-ttu-id="ae2a4-116">В ходе транзакции произошла ошибка проверки, поэтому транзакция завершается.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae2a4-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ae2a4-117">User Action</span></span>  
 <span data-ttu-id="ae2a4-118">Повторите поврежденную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-118">Retry the failed transaction.</span></span> <span data-ttu-id="ae2a4-119">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="ae2a4-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae2a4-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae2a4-120">See Also</span></span>  
 [<span data-ttu-id="ae2a4-121">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="ae2a4-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
