---
title: MSSQLSERVER_10509 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10509 (Database Engine error)
ms.assetid: e9dd5357-ee3d-420a-9a89-d12ab5404e73
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73194c7da553bf27acb78d8c4e7d71bc93f457d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749959"
---
# <a name="mssqlserver_10509"></a><span data-ttu-id="91bc7-102">MSSQLSERVER_10509</span><span class="sxs-lookup"><span data-stu-id="91bc7-102">MSSQLSERVER_10509</span></span>
    
## <a name="details"></a><span data-ttu-id="91bc7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="91bc7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="91bc7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="91bc7-104">Product Name</span></span>|<span data-ttu-id="91bc7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="91bc7-105">SQL Server</span></span>|  
|<span data-ttu-id="91bc7-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="91bc7-106">Event ID</span></span>|<span data-ttu-id="91bc7-107">10509</span><span class="sxs-lookup"><span data-stu-id="91bc7-107">10509</span></span>|  
|<span data-ttu-id="91bc7-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="91bc7-108">Event Source</span></span>|<span data-ttu-id="91bc7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="91bc7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="91bc7-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="91bc7-110">Component</span></span>|<span data-ttu-id="91bc7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="91bc7-111">SQLEngine</span></span>|  
|<span data-ttu-id="91bc7-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="91bc7-112">Symbolic Name</span></span>|<span data-ttu-id="91bc7-113">PG_INVALID_STMT</span><span class="sxs-lookup"><span data-stu-id="91bc7-113">PG_INVALID_STMT</span></span>|  
|<span data-ttu-id="91bc7-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="91bc7-114">Message Text</span></span>|<span data-ttu-id="91bc7-115">Не удалось создать структуру плана '%.\*ls', поскольку инструкция, указанная параметром `@stmt` или `@statement_start_offset`, содержит синтаксическую ошибку или недопустима для использования в структуре плана.</span><span class="sxs-lookup"><span data-stu-id="91bc7-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span> <span data-ttu-id="91bc7-116">Задайте одну допустимую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] или допустимую начальную позицию инструкции внутри пакета.</span><span class="sxs-lookup"><span data-stu-id="91bc7-116">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="91bc7-117">Допустимую начальную позицию можно запросить из столбца statement_start_offset функции динамического управления sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="91bc7-117">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="91bc7-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="91bc7-118">Explanation</span></span>  
 <span data-ttu-id="91bc7-119">Инструкция, указанная параметром `@stmt` или `@statement_start_offset`, содержит синтаксическую ошибку или недопустима для использования в структуре плана.</span><span class="sxs-lookup"><span data-stu-id="91bc7-119">The statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="91bc7-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="91bc7-120">User Action</span></span>  
 <span data-ttu-id="91bc7-121">Задайте одну допустимую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] или допустимую начальную позицию инструкции внутри пакета.</span><span class="sxs-lookup"><span data-stu-id="91bc7-121">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="91bc7-122">Допустимую начальную позицию можно запросить из столбца statement_start_offset функции динамического управления sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="91bc7-122">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91bc7-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="91bc7-123">See Also</span></span>  
 <span data-ttu-id="91bc7-124">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="91bc7-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="91bc7-125">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="91bc7-125">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="91bc7-126">[sys. dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="91bc7-126">[sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span></span>  
 [<span data-ttu-id="91bc7-127">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="91bc7-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
