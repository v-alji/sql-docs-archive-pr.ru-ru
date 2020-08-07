---
title: MSSQLSERVER_10539 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10539 (Database Engine error)
ms.assetid: 49c26ff7-18b8-4f07-a087-f45f63463b3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd1f190b8f5d3ab9755409bdd034fa374ea5314
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731682"
---
# <a name="mssqlserver_10539"></a><span data-ttu-id="319dc-102">MSSQLSERVER_10539</span><span class="sxs-lookup"><span data-stu-id="319dc-102">MSSQLSERVER_10539</span></span>
    
## <a name="details"></a><span data-ttu-id="319dc-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="319dc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="319dc-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="319dc-104">Product Name</span></span>|<span data-ttu-id="319dc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="319dc-105">SQL Server</span></span>|  
|<span data-ttu-id="319dc-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="319dc-106">Event ID</span></span>|<span data-ttu-id="319dc-107">10539</span><span class="sxs-lookup"><span data-stu-id="319dc-107">10539</span></span>|  
|<span data-ttu-id="319dc-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="319dc-108">Event Source</span></span>|<span data-ttu-id="319dc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="319dc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="319dc-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="319dc-110">Component</span></span>|<span data-ttu-id="319dc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="319dc-111">SQLEngine</span></span>|  
|<span data-ttu-id="319dc-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="319dc-112">Symbolic Name</span></span>|<span data-ttu-id="319dc-113">PG_NO_PLAN_FOR_STMT</span><span class="sxs-lookup"><span data-stu-id="319dc-113">PG_NO_PLAN_FOR_STMT</span></span>|  
|<span data-ttu-id="319dc-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="319dc-114">Message Text</span></span>|<span data-ttu-id="319dc-115">Не удается создать структуру плана «%.\*ls» из кэша, поскольку план запроса для инструкции с начальным смещением %d недоступен.</span><span class="sxs-lookup"><span data-stu-id="319dc-115">Cannot create plan guide '%.\*ls' from cache because a query plan is not available for the statement with start offset %d.</span></span> <span data-ttu-id="319dc-116">Эта ошибка может произойти, если инструкция зависит от объектов базы данных, которые еще не были созданы.</span><span class="sxs-lookup"><span data-stu-id="319dc-116">This problem can occur if the statement depends on database objects that have not yet been created.</span></span> <span data-ttu-id="319dc-117">Убедитесь, что существуют все необходимые объекты базы данных, и выполните инструкцию перед созданием структуры плана.</span><span class="sxs-lookup"><span data-stu-id="319dc-117">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="319dc-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="319dc-118">Explanation</span></span>  
 <span data-ttu-id="319dc-119">В кэше планов недоступен план запроса для инструкции с указанным начальным смещением.</span><span class="sxs-lookup"><span data-stu-id="319dc-119">A query plan is not available in the plan cache for the statement with the specified starting offset.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="319dc-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="319dc-120">User Action</span></span>  
 <span data-ttu-id="319dc-121">Убедитесь, что существуют все необходимые объекты базы данных, и выполните инструкцию перед созданием структуры плана.</span><span class="sxs-lookup"><span data-stu-id="319dc-121">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="319dc-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="319dc-122">See Also</span></span>  
 [<span data-ttu-id="319dc-123">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="319dc-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
