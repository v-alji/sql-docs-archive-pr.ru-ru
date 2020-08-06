---
title: MSSQLSERVER_17084 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17084 (Database Engine error)
ms.assetid: e579d104-3307-4edd-8587-b14ecbc02ed9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59b0fc3e0884ddd89809767a068b937b5c145f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667149"
---
# <a name="mssqlserver_17084"></a><span data-ttu-id="38795-102">MSSQLSERVER_17084</span><span class="sxs-lookup"><span data-stu-id="38795-102">MSSQLSERVER_17084</span></span>
    
## <a name="details"></a><span data-ttu-id="38795-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="38795-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38795-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="38795-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="38795-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="38795-105">Event ID</span></span>|<span data-ttu-id="38795-106">17084</span><span class="sxs-lookup"><span data-stu-id="38795-106">17084</span></span>|  
|<span data-ttu-id="38795-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="38795-107">Event Source</span></span>|<span data-ttu-id="38795-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="38795-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="38795-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="38795-109">Component</span></span>|<span data-ttu-id="38795-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="38795-110">SQLEngine</span></span>|  
|<span data-ttu-id="38795-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="38795-111">Symbolic Name</span></span>|<span data-ttu-id="38795-112">P3_ATOMIC_WITH_MISSING_OPTION</span><span class="sxs-lookup"><span data-stu-id="38795-112">P3_ATOMIC_WITH_MISSING_OPTION</span></span>|  
|<span data-ttu-id="38795-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="38795-113">Message Text</span></span>|<span data-ttu-id="38795-114">Предложение WITH инструкции BEGIN ATOMIC должно задавать значение для параметра «%ls».</span><span class="sxs-lookup"><span data-stu-id="38795-114">The WITH clause of BEGIN ATOMIC statement must specify a value for the option '%ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="38795-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="38795-115">Explanation</span></span>  
 <span data-ttu-id="38795-116">Предложение WITH инструкции BEGIN ATOMIC не задает значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="38795-116">The WITH clause of BEGIN ATOMIC statement did not specify a value for an option.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="38795-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="38795-117">User Action</span></span>  
 <span data-ttu-id="38795-118">Блоки `ATOMIC` требуют значений для параметров `WITH`, `TRANSACTION ISOLATION LEVEL` и `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="38795-118">`ATOMIC` blocks require values for the `WITH` options `TRANSACTION ISOLATION LEVEL` and `LANGUAGE`.</span></span> <span data-ttu-id="38795-119">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="38795-119">For example::</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="38795-120">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="38795-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38795-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="38795-121">See Also</span></span>  
 [<span data-ttu-id="38795-122">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="38795-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
