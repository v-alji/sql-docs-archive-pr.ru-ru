---
title: MSSQLSERVER_10502 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10502 (Database Engine error)
ms.assetid: 26d9b64d-4299-4b55-92d0-0a32a3688c0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eeec3a3adf318cadc96501938f8a5565f1c07670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655256"
---
# <a name="mssqlserver_10502"></a><span data-ttu-id="82f5e-102">MSSQLSERVER_10502</span><span class="sxs-lookup"><span data-stu-id="82f5e-102">MSSQLSERVER_10502</span></span>
    
## <a name="details"></a><span data-ttu-id="82f5e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="82f5e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82f5e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="82f5e-104">Product Name</span></span>|<span data-ttu-id="82f5e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="82f5e-105">SQL Server</span></span>|  
|<span data-ttu-id="82f5e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="82f5e-106">Event ID</span></span>|<span data-ttu-id="82f5e-107">10502</span><span class="sxs-lookup"><span data-stu-id="82f5e-107">10502</span></span>|  
|<span data-ttu-id="82f5e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="82f5e-108">Event Source</span></span>|<span data-ttu-id="82f5e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="82f5e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="82f5e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="82f5e-110">Component</span></span>|<span data-ttu-id="82f5e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="82f5e-111">SQLEngine</span></span>|  
|<span data-ttu-id="82f5e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="82f5e-112">Symbolic Name</span></span>|<span data-ttu-id="82f5e-113">PG_DUP_FOUND</span><span class="sxs-lookup"><span data-stu-id="82f5e-113">PG_DUP_FOUND</span></span>|  
|<span data-ttu-id="82f5e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="82f5e-114">Message Text</span></span>|<span data-ttu-id="82f5e-115">Не удается создать структуру плана "%.\*ls", так как инструкция, указанная параметрами @stmt и @module_or_batch или параметрами @plan_handle и @statement_start_offset, соответствует существующей структуре плана "%.\*ls" в базе данных.</span><span class="sxs-lookup"><span data-stu-id="82f5e-115">Cannot create plan guide '%.\*ls' because the statement specified by @stmt and @module_or_batch, or by @plan_handle and @statement_start_offset, matches the existing plan guide '%.\*ls' in the database.</span></span> <span data-ttu-id="82f5e-116">Перед созданием новой структуры плана удалите существующую.</span><span class="sxs-lookup"><span data-stu-id="82f5e-116">Drop the existing plan guide before creating the new plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82f5e-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="82f5e-117">Explanation</span></span>  
 <span data-ttu-id="82f5e-118">Для указанной инструкции существует структура плана.</span><span class="sxs-lookup"><span data-stu-id="82f5e-118">A plan guide exists for the specified statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82f5e-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="82f5e-119">User Action</span></span>  
 <span data-ttu-id="82f5e-120">Перед созданием новой структуры плана удалите существующую.</span><span class="sxs-lookup"><span data-stu-id="82f5e-120">Drop the existing plan guide before creating the new plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f5e-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="82f5e-121">See Also</span></span>  
 <span data-ttu-id="82f5e-122">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="82f5e-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="82f5e-123">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="82f5e-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="82f5e-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="82f5e-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
