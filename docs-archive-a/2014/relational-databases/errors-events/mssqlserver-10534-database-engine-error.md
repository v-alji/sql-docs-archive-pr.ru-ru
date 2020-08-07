---
title: MSSQLSERVER_10534 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10534 (Database Engine error)
ms.assetid: e65bb118-99d5-4fdb-b1d5-0ec70f0a677b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 793bb0bf5048e30624d9566f65e7c6752bd14386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731701"
---
# <a name="mssqlserver_10534"></a><span data-ttu-id="54776-102">MSSQLSERVER_10534</span><span class="sxs-lookup"><span data-stu-id="54776-102">MSSQLSERVER_10534</span></span>
    
## <a name="details"></a><span data-ttu-id="54776-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="54776-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54776-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="54776-104">Product Name</span></span>|<span data-ttu-id="54776-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="54776-105">SQL Server</span></span>|  
|<span data-ttu-id="54776-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="54776-106">Event ID</span></span>|<span data-ttu-id="54776-107">10534</span><span class="sxs-lookup"><span data-stu-id="54776-107">10534</span></span>|  
|<span data-ttu-id="54776-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="54776-108">Event Source</span></span>|<span data-ttu-id="54776-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="54776-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="54776-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="54776-110">Component</span></span>|<span data-ttu-id="54776-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="54776-111">SQLEngine</span></span>|  
|<span data-ttu-id="54776-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="54776-112">Symbolic Name</span></span>|<span data-ttu-id="54776-113">PG_INVALID_PARAMS</span><span class="sxs-lookup"><span data-stu-id="54776-113">PG_INVALID_PARAMS</span></span>|  
|<span data-ttu-id="54776-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="54776-114">Message Text</span></span>|<span data-ttu-id="54776-115">Не удается создать структуру плана "%.\*ls", поскольку задано недопустимое значение параметра `@params`.</span><span class="sxs-lookup"><span data-stu-id="54776-115">Cannot create plan guide '%.\*ls' because the value specified for `@params` is invalid.</span></span> <span data-ttu-id="54776-116">Задайте значение в форме *имя_параметра тип_параметра* или укажите значение NULL.</span><span class="sxs-lookup"><span data-stu-id="54776-116">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="54776-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="54776-117">Explanation</span></span>  
 <span data-ttu-id="54776-118">Значение, указанное для `@params`, недопустимо.</span><span class="sxs-lookup"><span data-stu-id="54776-118">The value specified for `@params` is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54776-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="54776-119">User Action</span></span>  
 <span data-ttu-id="54776-120">Задайте значение в форме *имя_параметра тип_параметра* или укажите значение NULL.</span><span class="sxs-lookup"><span data-stu-id="54776-120">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54776-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="54776-121">See Also</span></span>  
 <span data-ttu-id="54776-122">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="54776-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="54776-123">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54776-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="54776-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="54776-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
