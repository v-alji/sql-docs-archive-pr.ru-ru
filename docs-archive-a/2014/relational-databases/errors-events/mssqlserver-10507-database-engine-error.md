---
title: MSSQLSERVER_10507 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10507 (Database Engine error)
ms.assetid: cd83fa81-ac37-4eda-a3c3-17610b051de2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a80e48948c03b370c07742fabbb3cf8eb3e74315
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738450"
---
# <a name="mssqlserver_10507"></a><span data-ttu-id="a03d1-102">MSSQLSERVER_10507</span><span class="sxs-lookup"><span data-stu-id="a03d1-102">MSSQLSERVER_10507</span></span>
    
## <a name="details"></a><span data-ttu-id="a03d1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a03d1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a03d1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a03d1-104">Product Name</span></span>|<span data-ttu-id="a03d1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a03d1-105">SQL Server</span></span>|  
|<span data-ttu-id="a03d1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a03d1-106">Event ID</span></span>|<span data-ttu-id="a03d1-107">10507</span><span class="sxs-lookup"><span data-stu-id="a03d1-107">10507</span></span>|  
|<span data-ttu-id="a03d1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a03d1-108">Event Source</span></span>|<span data-ttu-id="a03d1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a03d1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a03d1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a03d1-110">Component</span></span>|<span data-ttu-id="a03d1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a03d1-111">SQLEngine</span></span>|  
|<span data-ttu-id="a03d1-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a03d1-112">Symbolic Name</span></span>|<span data-ttu-id="a03d1-113">PG_STMT_DOES_NOT_MATCH</span><span class="sxs-lookup"><span data-stu-id="a03d1-113">PG_STMT_DOES_NOT_MATCH</span></span>|  
|<span data-ttu-id="a03d1-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a03d1-114">Message Text</span></span>|<span data-ttu-id="a03d1-115">Не удалось создать структуру плана "%.\*ls", поскольку инструкция, указанная параметрами `@stmt` и `@module_or_batch` или параметрами `@plan_handle` и `@statement_start_offset`, не соответствует ни одной инструкции в указанном модуле или пакете.</span><span class="sxs-lookup"><span data-stu-id="a03d1-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` and `@module_or_batch`, or by `@plan_handle` and `@statement_start_offset`, does not match any statement in the specified module or batch.</span></span> <span data-ttu-id="a03d1-116">Измените значения параметров таким образом, чтобы они соответствовали инструкции в модуле или пакете.</span><span class="sxs-lookup"><span data-stu-id="a03d1-116">Modify the values to match a statement in the module or batch.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a03d1-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a03d1-117">Explanation</span></span>  
 <span data-ttu-id="a03d1-118">Инструкция в указанном модуле или пакете не соответствует указанной инструкцией или с величиной смещения инструкции.</span><span class="sxs-lookup"><span data-stu-id="a03d1-118">A statement in the specified module or batch could not be matched to the specified statement or statement offset value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a03d1-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a03d1-119">User Action</span></span>  
 <span data-ttu-id="a03d1-120">Измените указанные значения параметров, чтобы они соответствовали инструкции в модуле или пакете.</span><span class="sxs-lookup"><span data-stu-id="a03d1-120">Modify the specified parameter values to match a statement in the module or batch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a03d1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="a03d1-121">See Also</span></span>  
 <span data-ttu-id="a03d1-122">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="a03d1-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="a03d1-123">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a03d1-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="a03d1-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a03d1-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
