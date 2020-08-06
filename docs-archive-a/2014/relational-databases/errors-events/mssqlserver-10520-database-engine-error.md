---
title: MSSQLSERVER_10520 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b8bdf080703fa6bd02fc34b8c31f59407814b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731710"
---
# <a name="mssqlserver_10520"></a><span data-ttu-id="37d20-102">MSSQLSERVER_10520</span><span class="sxs-lookup"><span data-stu-id="37d20-102">MSSQLSERVER_10520</span></span>
    
## <a name="details"></a><span data-ttu-id="37d20-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="37d20-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37d20-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="37d20-104">Product Name</span></span>|<span data-ttu-id="37d20-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="37d20-105">SQL Server</span></span>|  
|<span data-ttu-id="37d20-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="37d20-106">Event ID</span></span>|<span data-ttu-id="37d20-107">10520</span><span class="sxs-lookup"><span data-stu-id="37d20-107">10520</span></span>|  
|<span data-ttu-id="37d20-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="37d20-108">Event Source</span></span>|<span data-ttu-id="37d20-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="37d20-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="37d20-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="37d20-110">Component</span></span>|<span data-ttu-id="37d20-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="37d20-111">SQLEngine</span></span>|  
|<span data-ttu-id="37d20-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="37d20-112">Symbolic Name</span></span>|<span data-ttu-id="37d20-113">PG_PARAM_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="37d20-113">PG_PARAM_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="37d20-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="37d20-114">Message Text</span></span>|<span data-ttu-id="37d20-115">Не удается создать структуру плана '%.\*ls', поскольку для параметра @type указано значение '%!s', а для параметра '%!s' указано значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="37d20-115">Cannot create plan guide '%.\*ls' because @type was specified as '%ls' and a non-NULL value is specified for the parameter '%ls'.</span></span> <span data-ttu-id="37d20-116">Для заданного типа этот параметр должен иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="37d20-116">This type requires a NULL value for the parameter.</span></span> <span data-ttu-id="37d20-117">Укажите для этого параметра значение NULL либо измените его тип таким образом, чтобы он допускал значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="37d20-117">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="37d20-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="37d20-118">Explanation</span></span>  
 <span data-ttu-id="37d20-119">Для типа, указанного в @type, требуется значение NULL, но предоставлено значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="37d20-119">The type specified in @type requires a NULL value for the specified parameter, however a non-NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="37d20-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="37d20-120">User Action</span></span>  
 <span data-ttu-id="37d20-121">Укажите для этого параметра значение NULL либо измените его тип таким образом, чтобы он допускал значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="37d20-121">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d20-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="37d20-122">See Also</span></span>  
 <span data-ttu-id="37d20-123">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="37d20-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="37d20-124">Руководства планов</span><span class="sxs-lookup"><span data-stu-id="37d20-124">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
