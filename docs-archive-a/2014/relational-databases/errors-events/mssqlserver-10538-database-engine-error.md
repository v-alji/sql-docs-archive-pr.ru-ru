---
title: MSSQLSERVER_10538 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: edc6abf192a3341f9b84c99e99071343cc882c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731689"
---
# <a name="mssqlserver_10538"></a><span data-ttu-id="81ea7-102">MSSQLSERVER_10538</span><span class="sxs-lookup"><span data-stu-id="81ea7-102">MSSQLSERVER_10538</span></span>
    
## <a name="details"></a><span data-ttu-id="81ea7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="81ea7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81ea7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="81ea7-104">Product Name</span></span>|<span data-ttu-id="81ea7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="81ea7-105">SQL Server</span></span>|  
|<span data-ttu-id="81ea7-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="81ea7-106">Event ID</span></span>|<span data-ttu-id="81ea7-107">10538</span><span class="sxs-lookup"><span data-stu-id="81ea7-107">10538</span></span>|  
|<span data-ttu-id="81ea7-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="81ea7-108">Event Source</span></span>|<span data-ttu-id="81ea7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="81ea7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="81ea7-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="81ea7-110">Component</span></span>|<span data-ttu-id="81ea7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="81ea7-111">SQLEngine</span></span>|  
|<span data-ttu-id="81ea7-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="81ea7-112">Symbolic Name</span></span>|<span data-ttu-id="81ea7-113">PG_INVALID_PLANGUIDE_HANDLE</span><span class="sxs-lookup"><span data-stu-id="81ea7-113">PG_INVALID_PLANGUIDE_HANDLE</span></span>|  
|<span data-ttu-id="81ea7-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="81ea7-114">Message Text</span></span>|<span data-ttu-id="81ea7-115">Не удается найти структуру плана, поскольку указанный идентификатор структуры плана имеет значение NULL или является недопустимым, либо отсутствует разрешение на объект, упоминаемый в структуре плана.</span><span class="sxs-lookup"><span data-stu-id="81ea7-115">Cannot find the plan guide either because the specified plan guide ID is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span> <span data-ttu-id="81ea7-116">Убедитесь, что идентификатор структуры плана является допустимым, текущий сеанс настроен на правильный контекст базы данных и имеется разрешение ALTER DATABASE или разрешение ALTER на объект, упоминаемый в структуре плана.</span><span class="sxs-lookup"><span data-stu-id="81ea7-116">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have either ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81ea7-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="81ea7-117">Explanation</span></span>  
 <span data-ttu-id="81ea7-118">Идентификатор указанной структуры плана имеет значение NULL или является недопустимым, либо отсутствует разрешение на объект, указанный в структуре плана.</span><span class="sxs-lookup"><span data-stu-id="81ea7-118">The ID of the specified plan guide is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81ea7-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="81ea7-119">User Action</span></span>  
 <span data-ttu-id="81ea7-120">Убедитесь, что идентификатор структуры плана допустим, текущий сеанс настроен на правильный контекст базы данных и имеется разрешение ALTER DATABASE или разрешение ALTER на объект, упоминаемый в структуре плана.</span><span class="sxs-lookup"><span data-stu-id="81ea7-120">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ea7-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="81ea7-121">See Also</span></span>  
 <span data-ttu-id="81ea7-122">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81ea7-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="81ea7-123">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="81ea7-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="81ea7-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="81ea7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
