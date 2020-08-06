---
title: MSSQLSERVER_41365 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41365 (Database Engine error)
ms.assetid: 4fc7ec15-b722-4e3d-b7f9-3d39d171e96e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1382a6395f1929a5d5552113e07376bcbf80bf35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665360"
---
# <a name="mssqlserver_41365"></a><span data-ttu-id="33ac1-102">MSSQLSERVER_41365</span><span class="sxs-lookup"><span data-stu-id="33ac1-102">MSSQLSERVER_41365</span></span>
    
## <a name="details"></a><span data-ttu-id="33ac1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="33ac1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33ac1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="33ac1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="33ac1-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="33ac1-105">Event ID</span></span>|<span data-ttu-id="33ac1-106">41365</span><span class="sxs-lookup"><span data-stu-id="33ac1-106">41365</span></span>|  
|<span data-ttu-id="33ac1-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="33ac1-107">Event Source</span></span>|<span data-ttu-id="33ac1-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="33ac1-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="33ac1-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="33ac1-109">Component</span></span>|<span data-ttu-id="33ac1-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="33ac1-110">SQLEngine</span></span>|  
|<span data-ttu-id="33ac1-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="33ac1-111">Symbolic Name</span></span>|<span data-ttu-id="33ac1-112">HK_MERGE_SCHEDULE_ERROR</span><span class="sxs-lookup"><span data-stu-id="33ac1-112">HK_MERGE_SCHEDULE_ERROR</span></span>|  
|<span data-ttu-id="33ac1-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="33ac1-113">Message Text</span></span>|<span data-ttu-id="33ac1-114">Запрос на слияние диапазона для транзакции [%ld, %ld] в базе данных %.\*ls не был поставлен в расписание.</span><span class="sxs-lookup"><span data-stu-id="33ac1-114">Merge request for transaction range [%ld, %ld] on database %.\*ls was not scheduled.</span></span> <span data-ttu-id="33ac1-115">Представляющие диапазон файлы контрольных точек недоступны для слияния либо входят в уже выполняемое слияние.</span><span class="sxs-lookup"><span data-stu-id="33ac1-115">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="33ac1-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="33ac1-116">Explanation</span></span>  
 <span data-ttu-id="33ac1-117">Представляющие диапазон файлы контрольных точек недоступны для слияния либо входят в уже выполняемое слияние.</span><span class="sxs-lookup"><span data-stu-id="33ac1-117">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33ac1-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="33ac1-118">User Action</span></span>  
 <span data-ttu-id="33ac1-119">Укажите более подходящий диапазон транзакции для слияния или подождите, а потом еще раз выполните тот же запрос.</span><span class="sxs-lookup"><span data-stu-id="33ac1-119">Provide a better transaction range for merge/wait before issuing the same request again.</span></span> <span data-ttu-id="33ac1-120">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="33ac1-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ac1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="33ac1-121">See Also</span></span>  
 [<span data-ttu-id="33ac1-122">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="33ac1-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
