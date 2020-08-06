---
title: MSSQLSERVER_10537 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10537 (Database Engine error)
ms.assetid: 728469a4-6523-4a37-925f-a950d75420fa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b1baccad5236bd8c1a71024b7dd542cc9d11cbd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734129"
---
# <a name="mssqlserver_10537"></a><span data-ttu-id="5c067-102">MSSQLSERVER_10537</span><span class="sxs-lookup"><span data-stu-id="5c067-102">MSSQLSERVER_10537</span></span>
    
## <a name="details"></a><span data-ttu-id="5c067-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5c067-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c067-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5c067-104">Product Name</span></span>|<span data-ttu-id="5c067-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c067-105">SQL Server</span></span>|  
|<span data-ttu-id="5c067-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5c067-106">Event ID</span></span>|<span data-ttu-id="5c067-107">10537</span><span class="sxs-lookup"><span data-stu-id="5c067-107">10537</span></span>|  
|<span data-ttu-id="5c067-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5c067-108">Event Source</span></span>|<span data-ttu-id="5c067-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5c067-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5c067-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5c067-110">Component</span></span>|<span data-ttu-id="5c067-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5c067-111">SQLEngine</span></span>|  
|<span data-ttu-id="5c067-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5c067-112">Symbolic Name</span></span>|<span data-ttu-id="5c067-113">PG_DUP_ENABLED</span><span class="sxs-lookup"><span data-stu-id="5c067-113">PG_DUP_ENABLED</span></span>|  
|<span data-ttu-id="5c067-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5c067-114">Message Text</span></span>|<span data-ttu-id="5c067-115">Не удается включить структуру плана '%.\*ls', поскольку включенная структура плана '%.\*ls' содержит ту же область и то же значение начального смещения для инструкции.</span><span class="sxs-lookup"><span data-stu-id="5c067-115">Cannot enable plan guide '%.\*ls' because the enabled plan guide '%.\*ls' contains the same scope and starting offset value as the statement.</span></span> <span data-ttu-id="5c067-116">Отключите существующую структуру плана перед включением указанной структуры.</span><span class="sxs-lookup"><span data-stu-id="5c067-116">Disable the existing plan guide before enabling the specified plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5c067-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5c067-117">Explanation</span></span>  
 <span data-ttu-id="5c067-118">Существующая структура плана содержит ту же область и то же значение начального смещения, что и инструкция в указанной структуре плана.</span><span class="sxs-lookup"><span data-stu-id="5c067-118">An existing plan guide contains the same scope and starting offset value as the statement in the specified plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5c067-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5c067-119">User Action</span></span>  
 <span data-ttu-id="5c067-120">Отключите существующую структуру плана перед включением указанной структуры.</span><span class="sxs-lookup"><span data-stu-id="5c067-120">Disable the existing plan guide before enabling the specified plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c067-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c067-121">See Also</span></span>  
 <span data-ttu-id="5c067-122">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5c067-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="5c067-123">[Структуры планов](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="5c067-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="5c067-124">sp_create_plan_guide_from_handle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5c067-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
