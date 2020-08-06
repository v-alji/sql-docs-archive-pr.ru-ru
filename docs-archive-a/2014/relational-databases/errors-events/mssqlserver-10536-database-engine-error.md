---
title: MSSQLSERVER_ 10536 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10536 (Database Engine error)
ms.assetid: 9f97b41f-0ef8-4ad2-aec0-906a5d7522ba
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 00d08f4555f38b61661a917ba94c023f9dd6c4a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734126"
---
# <a name="mssqlserver_10536"></a><span data-ttu-id="5ff81-102">MSSQLSERVER_10536</span><span class="sxs-lookup"><span data-stu-id="5ff81-102">MSSQLSERVER_10536</span></span>
    
## <a name="details"></a><span data-ttu-id="5ff81-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5ff81-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ff81-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5ff81-104">Product Name</span></span>|<span data-ttu-id="5ff81-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5ff81-105">SQL Server</span></span>|  
|<span data-ttu-id="5ff81-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5ff81-106">Event ID</span></span>|<span data-ttu-id="5ff81-107">10536</span><span class="sxs-lookup"><span data-stu-id="5ff81-107">10536</span></span>|  
|<span data-ttu-id="5ff81-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5ff81-108">Event Source</span></span>|<span data-ttu-id="5ff81-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5ff81-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5ff81-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5ff81-110">Component</span></span>|<span data-ttu-id="5ff81-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5ff81-111">SQLEngine</span></span>|  
|<span data-ttu-id="5ff81-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5ff81-112">Symbolic Name</span></span>|<span data-ttu-id="5ff81-113">PG_TOO_MANY_STMTS</span><span class="sxs-lookup"><span data-stu-id="5ff81-113">PG_TOO_MANY_STMTS</span></span>|  
|<span data-ttu-id="5ff81-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5ff81-114">Message Text</span></span>|<span data-ttu-id="5ff81-115">Не удалось создать структуру плана "%.\*ls", поскольку пакет или модуль, соответствующий указанному параметру `@plan_handle`, содержит более 1000 подходящих инструкций.</span><span class="sxs-lookup"><span data-stu-id="5ff81-115">Cannot create plan guide '%.\*ls' because the batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span> <span data-ttu-id="5ff81-116">Создайте структуру плана для каждой инструкции в пакете или модуле, указав для каждой инструкции значение `statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="5ff81-116">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5ff81-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5ff81-117">Explanation</span></span>  
 <span data-ttu-id="5ff81-118">Пакет или модуль, соответствующий указанному дескриптору `@plan_handle`, содержит больше 1000 подходящих инструкций.</span><span class="sxs-lookup"><span data-stu-id="5ff81-118">The batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5ff81-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5ff81-119">User Action</span></span>  
 <span data-ttu-id="5ff81-120">Создайте структуру плана для каждой инструкции в пакете или модуле, указав для каждой инструкции значение `statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="5ff81-120">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff81-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ff81-121">See Also</span></span>  
 <span data-ttu-id="5ff81-122">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5ff81-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="5ff81-123">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="5ff81-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="5ff81-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5ff81-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
