---
title: MSSQLSERVER_ 10532 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10532 (Database Engine error)
ms.assetid: 01da29ee-bf67-433f-8148-587a7e8d1d76
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26ab34c319eff62737eae337828247fdfd7e901b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740010"
---
# <a name="mssqlserver_10532"></a><span data-ttu-id="cfa42-102">MSSQLSERVER_10532</span><span class="sxs-lookup"><span data-stu-id="cfa42-102">MSSQLSERVER_10532</span></span>
    
## <a name="details"></a><span data-ttu-id="cfa42-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="cfa42-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfa42-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="cfa42-104">Product Name</span></span>|<span data-ttu-id="cfa42-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfa42-105">SQL Server</span></span>|  
|<span data-ttu-id="cfa42-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="cfa42-106">Event ID</span></span>|<span data-ttu-id="cfa42-107">10532</span><span class="sxs-lookup"><span data-stu-id="cfa42-107">10532</span></span>|  
|<span data-ttu-id="cfa42-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="cfa42-108">Event Source</span></span>|<span data-ttu-id="cfa42-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cfa42-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cfa42-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="cfa42-110">Component</span></span>|<span data-ttu-id="cfa42-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cfa42-111">SQLEngine</span></span>|  
|<span data-ttu-id="cfa42-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="cfa42-112">Symbolic Name</span></span>|<span data-ttu-id="cfa42-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="cfa42-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="cfa42-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="cfa42-114">Message Text</span></span>|<span data-ttu-id="cfa42-115">Не удается создать структуру плана '%.\*ls', поскольку пакет или модуль, заданный параметром `@plan_handle`, не содержит инструкций, допустимых для структуры плана.</span><span class="sxs-lookup"><span data-stu-id="cfa42-115">Cannot create plan guide '%.\*ls' because the batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span> <span data-ttu-id="cfa42-116">Укажите другое значение для параметра `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="cfa42-116">Specify a different value for `@plan_handle`.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cfa42-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="cfa42-117">Explanation</span></span>  
 <span data-ttu-id="cfa42-118">Пакет или модуль, указанный в `@plan_handle`, не содержит инструкцию, подходящую для структуры плана.</span><span class="sxs-lookup"><span data-stu-id="cfa42-118">The batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cfa42-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="cfa42-119">User Action</span></span>  
 <span data-ttu-id="cfa42-120">Укажите другое значение для параметра `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="cfa42-120">Specify a different value for `@plan_handle`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa42-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfa42-121">See Also</span></span>  
 <span data-ttu-id="cfa42-122">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="cfa42-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="cfa42-123">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfa42-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="cfa42-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cfa42-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
