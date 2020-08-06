---
title: MSSQLSERVER_41307 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41307 (Database Engine error)
ms.assetid: 56f56410-b07d-4379-b01c-702c95761070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 98407a65d5529fd73bccc638df11167131bd9f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734101"
---
# <a name="mssqlserver_41307"></a><span data-ttu-id="2b7c6-102">MSSQLSERVER_41307</span><span class="sxs-lookup"><span data-stu-id="2b7c6-102">MSSQLSERVER_41307</span></span>
    
## <a name="details"></a><span data-ttu-id="2b7c6-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="2b7c6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b7c6-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="2b7c6-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="2b7c6-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="2b7c6-105">Event ID</span></span>|<span data-ttu-id="2b7c6-106">41307</span><span class="sxs-lookup"><span data-stu-id="2b7c6-106">41307</span></span>|  
|<span data-ttu-id="2b7c6-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="2b7c6-107">Event Source</span></span>|<span data-ttu-id="2b7c6-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2b7c6-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2b7c6-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="2b7c6-109">Component</span></span>|<span data-ttu-id="2b7c6-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2b7c6-110">SQLEngine</span></span>|  
|<span data-ttu-id="2b7c6-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="2b7c6-111">Symbolic Name</span></span>|<span data-ttu-id="2b7c6-112">HK_HEKATON_ROW_LIMIT</span><span class="sxs-lookup"><span data-stu-id="2b7c6-112">HK_HEKATON_ROW_LIMIT</span></span>|  
|<span data-ttu-id="2b7c6-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="2b7c6-113">Message Text</span></span>|<span data-ttu-id="2b7c6-114">Был превышен максимальный размер строки (*число* байт) для оптимизируемых для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="2b7c6-114">The row size limit of *number* bytes for memory optimized tables has been exceeded.</span></span> <span data-ttu-id="2b7c6-115">Упростите определение таблицы.</span><span class="sxs-lookup"><span data-stu-id="2b7c6-115">Please simplify the table definition.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2b7c6-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="2b7c6-116">Explanation</span></span>  
 <span data-ttu-id="2b7c6-117">Максимальный размер строки оптимизированной для памяти таблицы составляет 8060 байт.</span><span class="sxs-lookup"><span data-stu-id="2b7c6-117">The row size limit for memory optimized tables is 8,060 bytes.</span></span> <span data-ttu-id="2b7c6-118">Дополнительные сведения см. в статье [Размер строк и таблицы для таблиц, оптимизированных для памяти](../in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2b7c6-118">For more information, see [Table and Row Size in Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md).</span></span> <span data-ttu-id="2b7c6-119">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="2b7c6-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7c6-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b7c6-120">See Also</span></span>  
 [<span data-ttu-id="2b7c6-121">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="2b7c6-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
