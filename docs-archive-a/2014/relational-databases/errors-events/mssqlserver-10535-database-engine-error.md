---
title: MSSQLSERVER_10535 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10535 (Database Engine error)
ms.assetid: 478fd978-11d9-4155-8329-f599fdbec14b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 439d282f18490a4353d6528276eaf7e4231c503b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731694"
---
# <a name="mssqlserver_10535"></a><span data-ttu-id="45e10-102">MSSQLSERVER_10535</span><span class="sxs-lookup"><span data-stu-id="45e10-102">MSSQLSERVER_10535</span></span>
    
## <a name="details"></a><span data-ttu-id="45e10-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="45e10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45e10-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="45e10-104">Product Name</span></span>|<span data-ttu-id="45e10-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="45e10-105">SQL Server</span></span>|  
|<span data-ttu-id="45e10-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="45e10-106">Event ID</span></span>|<span data-ttu-id="45e10-107">10535</span><span class="sxs-lookup"><span data-stu-id="45e10-107">10535</span></span>|  
|<span data-ttu-id="45e10-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="45e10-108">Event Source</span></span>|<span data-ttu-id="45e10-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="45e10-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="45e10-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="45e10-110">Component</span></span>|<span data-ttu-id="45e10-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="45e10-111">SQLEngine</span></span>|  
|<span data-ttu-id="45e10-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="45e10-112">Symbolic Name</span></span>|<span data-ttu-id="45e10-113">PG_NO_PLAN</span><span class="sxs-lookup"><span data-stu-id="45e10-113">PG_NO_PLAN</span></span>|  
|<span data-ttu-id="45e10-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="45e10-114">Message Text</span></span>|<span data-ttu-id="45e10-115">Не удается создать структуру плана «%.\*ls», поскольку план не найден в кэше планов, соответствующем указанному дескриптору плана.</span><span class="sxs-lookup"><span data-stu-id="45e10-115">Cannot create plan guide '%.\*ls' because a plan was not found in the plan cache that corresponds to the specified plan handle.</span></span> <span data-ttu-id="45e10-116">Укажите дескриптор плана в кэше.</span><span class="sxs-lookup"><span data-stu-id="45e10-116">Specify a cached plan handle.</span></span> <span data-ttu-id="45e10-117">Список дескрипторов планов, находящихся в кэше, можно получить с помощью запроса к динамическому административному представлению sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="45e10-117">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="45e10-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="45e10-118">Explanation</span></span>  
 <span data-ttu-id="45e10-119">План не был найден в кэше планов, который соответствует указанному дескриптору плана.</span><span class="sxs-lookup"><span data-stu-id="45e10-119">A plan was not found in the plan cache that corresponds to the specified plan handle.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45e10-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="45e10-120">User Action</span></span>  
 <span data-ttu-id="45e10-121">Укажите дескриптор плана в кэше.</span><span class="sxs-lookup"><span data-stu-id="45e10-121">Specify a cached plan handle.</span></span> <span data-ttu-id="45e10-122">Список дескрипторов планов, находящихся в кэше, можно получить с помощью запроса к динамическому административному представлению sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="45e10-122">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e10-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="45e10-123">See Also</span></span>  
 <span data-ttu-id="45e10-124">[sp_create_plan_guide_from_handle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="45e10-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span></span>  
 [<span data-ttu-id="45e10-125">sys.dm_exec_query_stats (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="45e10-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql)  
  
  
