---
title: MSSQLSERVER_10533 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10533 (Database Engine error)
ms.assetid: cc2fbdab-7b90-415f-a1f9-066824344283
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccef25bc8f594cb6ea0b60aefab838ef27cda6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664276"
---
# <a name="mssqlserver_10533"></a><span data-ttu-id="30cc2-102">MSSQLSERVER_10533</span><span class="sxs-lookup"><span data-stu-id="30cc2-102">MSSQLSERVER_10533</span></span>
    
## <a name="details"></a><span data-ttu-id="30cc2-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="30cc2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30cc2-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="30cc2-104">Product Name</span></span>|<span data-ttu-id="30cc2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="30cc2-105">SQL Server</span></span>|  
|<span data-ttu-id="30cc2-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="30cc2-106">Event ID</span></span>|<span data-ttu-id="30cc2-107">10533</span><span class="sxs-lookup"><span data-stu-id="30cc2-107">10533</span></span>|  
|<span data-ttu-id="30cc2-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="30cc2-108">Event Source</span></span>|<span data-ttu-id="30cc2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="30cc2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="30cc2-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="30cc2-110">Component</span></span>|<span data-ttu-id="30cc2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="30cc2-111">SQLEngine</span></span>|  
|<span data-ttu-id="30cc2-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="30cc2-112">Symbolic Name</span></span>|<span data-ttu-id="30cc2-113">PG_NAME_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="30cc2-113">PG_NAME_TOO_BIG</span></span>|  
|<span data-ttu-id="30cc2-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="30cc2-114">Message Text</span></span>|<span data-ttu-id="30cc2-115">Не удалось создать структуру плана «%.\*ls», поскольку имя структуры плана превышает по длине максимально допустимое значение, равное 124 символам.</span><span class="sxs-lookup"><span data-stu-id="30cc2-115">Cannot create plan guide '%.\*ls' because the plan guide name exceeds 124 characters, the maximum number allowed.</span></span> <span data-ttu-id="30cc2-116">Укажите имя, содержащее менее 125 символов.</span><span class="sxs-lookup"><span data-stu-id="30cc2-116">Specify a name that contains fewer than 125 characters.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="30cc2-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="30cc2-117">Explanation</span></span>  
 <span data-ttu-id="30cc2-118">Имя структуры плана превышает по длине максимально допустимое значение, равное 124 символам.</span><span class="sxs-lookup"><span data-stu-id="30cc2-118">The plan guide name exceeds 124 characters, the maximum number allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="30cc2-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="30cc2-119">User Action</span></span>  
 <span data-ttu-id="30cc2-120">Укажите имя, содержащее менее 125 символов.</span><span class="sxs-lookup"><span data-stu-id="30cc2-120">Specify a name that contains fewer than 125 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30cc2-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="30cc2-121">See Also</span></span>  
 <span data-ttu-id="30cc2-122">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="30cc2-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="30cc2-123">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30cc2-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="30cc2-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="30cc2-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
