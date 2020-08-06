---
title: MSSQLSERVER_10519 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10519 (Database Engine error)
ms.assetid: 3be393a1-b186-41ae-afb9-a3d07ff354bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0ec584649842f787b1de9d2ea6d161aea6970250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736365"
---
# <a name="mssqlserver_10519"></a><span data-ttu-id="db6d3-102">MSSQLSERVER_10519</span><span class="sxs-lookup"><span data-stu-id="db6d3-102">MSSQLSERVER_10519</span></span>
    
## <a name="details"></a><span data-ttu-id="db6d3-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="db6d3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db6d3-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="db6d3-104">Product Name</span></span>|<span data-ttu-id="db6d3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="db6d3-105">SQL Server</span></span>|  
|<span data-ttu-id="db6d3-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="db6d3-106">Event ID</span></span>|<span data-ttu-id="db6d3-107">10519</span><span class="sxs-lookup"><span data-stu-id="db6d3-107">10519</span></span>|  
|<span data-ttu-id="db6d3-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="db6d3-108">Event Source</span></span>|<span data-ttu-id="db6d3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="db6d3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="db6d3-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="db6d3-110">Component</span></span>|<span data-ttu-id="db6d3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="db6d3-111">SQLEngine</span></span>|  
|<span data-ttu-id="db6d3-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="db6d3-112">Symbolic Name</span></span>|<span data-ttu-id="db6d3-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span><span class="sxs-lookup"><span data-stu-id="db6d3-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span></span>|  
|<span data-ttu-id="db6d3-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="db6d3-114">Message Text</span></span>|<span data-ttu-id="db6d3-115">Не удается создать структуру плана "%.\*ls", поскольку указания, заданные в параметре `@hints`, нельзя применить к инструкции, заданной параметром `@stmt` или `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="db6d3-115">Cannot create plan guide '%.\*ls' because the hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span> <span data-ttu-id="db6d3-116">Убедитесь, что заданные указания можно применить к этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="db6d3-116">Verify that the hints can be applied to the statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="db6d3-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="db6d3-117">Explanation</span></span>  
 <span data-ttu-id="db6d3-118">Указания, заданные в параметре `@hints`, не могут быть применены к инструкции, заданной с помощью `@stmt` или `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="db6d3-118">The hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="db6d3-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="db6d3-119">User Action</span></span>  
 <span data-ttu-id="db6d3-120">Задайте указания, которые могут быть применены к этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="db6d3-120">Specify hints that can be applied to the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6d3-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="db6d3-121">See Also</span></span>  
 <span data-ttu-id="db6d3-122">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db6d3-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="db6d3-123">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="db6d3-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="db6d3-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="db6d3-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
