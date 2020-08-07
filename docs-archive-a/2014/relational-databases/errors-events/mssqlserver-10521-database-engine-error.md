---
title: MSSQLSERVER_10521 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10521 (Database Engine error)
ms.assetid: ba2d7e44-207c-4428-b5f0-c975ac122c0d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c034bd13e212b9b39bfd348353d59e23fc748079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731706"
---
# <a name="mssqlserver_10521"></a><span data-ttu-id="b7dcd-102">MSSQLSERVER_10521</span><span class="sxs-lookup"><span data-stu-id="b7dcd-102">MSSQLSERVER_10521</span></span>
    
## <a name="details"></a><span data-ttu-id="b7dcd-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b7dcd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7dcd-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b7dcd-104">Product Name</span></span>|<span data-ttu-id="b7dcd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7dcd-105">SQL Server</span></span>|  
|<span data-ttu-id="b7dcd-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b7dcd-106">Event ID</span></span>|<span data-ttu-id="b7dcd-107">10521</span><span class="sxs-lookup"><span data-stu-id="b7dcd-107">10521</span></span>|  
|<span data-ttu-id="b7dcd-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b7dcd-108">Event Source</span></span>|<span data-ttu-id="b7dcd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b7dcd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b7dcd-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b7dcd-110">Component</span></span>|<span data-ttu-id="b7dcd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b7dcd-111">SQLEngine</span></span>|  
|<span data-ttu-id="b7dcd-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b7dcd-112">Symbolic Name</span></span>|<span data-ttu-id="b7dcd-113">PG_PARAM_NEEDED</span><span class="sxs-lookup"><span data-stu-id="b7dcd-113">PG_PARAM_NEEDED</span></span>|  
|<span data-ttu-id="b7dcd-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b7dcd-114">Message Text</span></span>|<span data-ttu-id="b7dcd-115">Не удалось создать структуру плана "%.\*ls", поскольку значение `@type` указано как "%ls", а параметр "%ls" имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b7dcd-115">Cannot create plan guide '%.\*ls' because `@type` was specified as '%ls' and the parameter '%ls' is NULL.</span></span> <span data-ttu-id="b7dcd-116">Этот тип должен иметь значение, отличное от NULL, для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="b7dcd-116">This type requires a non-NULL value for the parameter.</span></span> <span data-ttu-id="b7dcd-117">Укажите для этого параметра значение, отличное от NULL, либо измените его тип таким образом, чтобы он допускал значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b7dcd-117">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b7dcd-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b7dcd-118">Explanation</span></span>  
 <span data-ttu-id="b7dcd-119">Для типа, указанного в `@type`, требуется значение указанного параметра, отличное от NULL, но задано значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b7dcd-119">The type specified in `@type` requires a non-NULL value for the specified parameter; however a NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b7dcd-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b7dcd-120">User Action</span></span>  
 <span data-ttu-id="b7dcd-121">Укажите для этого параметра значение, отличное от NULL, либо измените его тип таким образом, чтобы он допускал значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b7dcd-121">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7dcd-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7dcd-122">See Also</span></span>  
 <span data-ttu-id="b7dcd-123">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b7dcd-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="b7dcd-124">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="b7dcd-124">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="b7dcd-125">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b7dcd-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
