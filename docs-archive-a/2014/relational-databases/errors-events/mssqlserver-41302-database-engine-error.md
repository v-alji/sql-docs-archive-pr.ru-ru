---
title: MSSQLSERVER_41302 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41302 (Database Engine error)
ms.assetid: 01e75618-afec-4232-ba68-93ab7bc31003
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 751dac91378c002a7e6c6c619ddaf12be8173400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658288"
---
# <a name="mssqlserver_41302"></a><span data-ttu-id="7b659-102">MSSQLSERVER_41302</span><span class="sxs-lookup"><span data-stu-id="7b659-102">MSSQLSERVER_41302</span></span>
    
## <a name="details"></a><span data-ttu-id="7b659-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7b659-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b659-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7b659-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="7b659-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7b659-105">Event ID</span></span>|<span data-ttu-id="7b659-106">41302</span><span class="sxs-lookup"><span data-stu-id="7b659-106">41302</span></span>|  
|<span data-ttu-id="7b659-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="7b659-107">Event Source</span></span>|<span data-ttu-id="7b659-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7b659-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7b659-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="7b659-109">Component</span></span>|<span data-ttu-id="7b659-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7b659-110">SQLEngine</span></span>|  
|<span data-ttu-id="7b659-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7b659-111">Symbolic Name</span></span>|<span data-ttu-id="7b659-112">WRITE_WRITE_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="7b659-112">WRITE_WRITE_CONFLICT</span></span>|  
|<span data-ttu-id="7b659-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7b659-113">Message Text</span></span>|<span data-ttu-id="7b659-114">Текущая транзакция попыталась обновить запись, которая была изменена после начала этой транзакции.</span><span class="sxs-lookup"><span data-stu-id="7b659-114">The current transaction attempted to update a record that has been updated since this transaction started.</span></span> <span data-ttu-id="7b659-115">Транзакция была прервана.</span><span class="sxs-lookup"><span data-stu-id="7b659-115">The transaction was aborted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b659-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7b659-116">Explanation</span></span>  
 <span data-ttu-id="7b659-117">В ходе транзакции произошел конфликт двойной записи, поэтому выполнение инструкции прервано.</span><span class="sxs-lookup"><span data-stu-id="7b659-117">The transaction encountered a write/write conflict and the statement terminated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b659-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7b659-118">User Action</span></span>  
 <span data-ttu-id="7b659-119">Повторите операцию позже в другой транзакции.</span><span class="sxs-lookup"><span data-stu-id="7b659-119">Retry the operation later in a different transaction.</span></span> <span data-ttu-id="7b659-120">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="7b659-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b659-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b659-121">See Also</span></span>  
 [<span data-ttu-id="7b659-122">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="7b659-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
