---
title: MSSQLSERVER_17083 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17083 (Database Engine error)
ms.assetid: 6c83737d-0531-4fd9-88f6-2da5a150532d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 598cf9b0182178aa13a6d8b965ac10bedaaf5d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667154"
---
# <a name="mssqlserver_17083"></a><span data-ttu-id="066d1-102">MSSQLSERVER_17083</span><span class="sxs-lookup"><span data-stu-id="066d1-102">MSSQLSERVER_17083</span></span>
    
## <a name="details"></a><span data-ttu-id="066d1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="066d1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="066d1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="066d1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="066d1-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="066d1-105">Event ID</span></span>|<span data-ttu-id="066d1-106">17083</span><span class="sxs-lookup"><span data-stu-id="066d1-106">17083</span></span>|  
|<span data-ttu-id="066d1-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="066d1-107">Event Source</span></span>|<span data-ttu-id="066d1-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="066d1-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="066d1-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="066d1-109">Component</span></span>|<span data-ttu-id="066d1-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="066d1-110">SQLEngine</span></span>|  
|<span data-ttu-id="066d1-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="066d1-111">Symbolic Name</span></span>|<span data-ttu-id="066d1-112">P3_HEKATON_NOT_ATOMIC</span><span class="sxs-lookup"><span data-stu-id="066d1-112">P3_HEKATON_NOT_ATOMIC</span></span>|  
|<span data-ttu-id="066d1-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="066d1-113">Message Text</span></span>|<span data-ttu-id="066d1-114">Телом хранимой процедуры, скомпилированной в собственном коде, должен быть блок ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="066d1-114">The body of a natively compiled stored procedure must be an ATOMIC block.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="066d1-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="066d1-115">Explanation</span></span>  
 <span data-ttu-id="066d1-116">Тело хранимой процедуры, скомпилированной в собственном коде, не содержало блоков ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="066d1-116">The body of a natively compiled stored procedure did not have an ATOMIC block.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="066d1-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="066d1-117">User Action</span></span>  
 <span data-ttu-id="066d1-118">Скомпилированная в собственном коде хранимая процедура должна содержать блок ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="066d1-118">A natively compiled stored procedure must contain an ATOMIC block.</span></span> <span data-ttu-id="066d1-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="066d1-119">For example:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="066d1-120">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="066d1-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="066d1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="066d1-121">See Also</span></span>  
 [<span data-ttu-id="066d1-122">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="066d1-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
