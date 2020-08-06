---
title: MSSQLSERVER_10531 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10531 (Database Engine error)
ms.assetid: bb40e994-231c-44ce-933f-8d767fb2f450
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6230c046a9eb7b900377888c59a3a492f2b89f73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731705"
---
# <a name="mssqlserver_10531"></a><span data-ttu-id="772ca-102">MSSQLSERVER_10531</span><span class="sxs-lookup"><span data-stu-id="772ca-102">MSSQLSERVER_10531</span></span>
    
## <a name="details"></a><span data-ttu-id="772ca-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="772ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="772ca-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="772ca-104">Product Name</span></span>|<span data-ttu-id="772ca-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="772ca-105">SQL Server</span></span>|  
|<span data-ttu-id="772ca-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="772ca-106">Event ID</span></span>|<span data-ttu-id="772ca-107">10531</span><span class="sxs-lookup"><span data-stu-id="772ca-107">10531</span></span>|  
|<span data-ttu-id="772ca-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="772ca-108">Event Source</span></span>|<span data-ttu-id="772ca-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="772ca-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="772ca-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="772ca-110">Component</span></span>|<span data-ttu-id="772ca-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="772ca-111">SQLEngine</span></span>|  
|<span data-ttu-id="772ca-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="772ca-112">Symbolic Name</span></span>|<span data-ttu-id="772ca-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="772ca-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="772ca-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="772ca-114">Message Text</span></span>|<span data-ttu-id="772ca-115">Не удалось создать структуру плана «%.\*ls» из кэша, поскольку пользователь не имеет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="772ca-115">Cannot create plan guide '%.\*ls' from cache because the user does not have adequate permissions.</span></span> <span data-ttu-id="772ca-116">Предоставьте разрешение VIEW SERVER STATE пользователю, создающему структуру плана.</span><span class="sxs-lookup"><span data-stu-id="772ca-116">Grant the VIEW SERVER STATE permission to the user creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="772ca-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="772ca-117">Explanation</span></span>  
 <span data-ttu-id="772ca-118">Пользователь не имеет разрешений, необходимых для создания указанной структуры плана из кэша планов.</span><span class="sxs-lookup"><span data-stu-id="772ca-118">The user does not have adequate permissions to create the specified plan guide from the plan cache.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="772ca-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="772ca-119">User Action</span></span>  
 <span data-ttu-id="772ca-120">Предоставьте разрешение VIEW SERVER STATE пользователю, создающему структуру плана.</span><span class="sxs-lookup"><span data-stu-id="772ca-120">Grant VIEW SERVER STATE permission to the user creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772ca-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="772ca-121">See Also</span></span>  
 <span data-ttu-id="772ca-122">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="772ca-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="772ca-123">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="772ca-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="772ca-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="772ca-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
