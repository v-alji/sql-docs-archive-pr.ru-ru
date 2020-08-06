---
title: MSSQLSERVER_8649 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8649 (Database Engine error)
ms.assetid: 992dbc74-7c3a-498b-9f1b-b28387640677
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b39ed0d8ffe5f7f601b6cb1393596d0d6546e557
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666072"
---
# <a name="mssqlserver_8649"></a><span data-ttu-id="08a69-102">MSSQLSERVER_8649</span><span class="sxs-lookup"><span data-stu-id="08a69-102">MSSQLSERVER_8649</span></span>
    
## <a name="details"></a><span data-ttu-id="08a69-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="08a69-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08a69-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="08a69-104">Product Name</span></span>|<span data-ttu-id="08a69-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="08a69-105">SQL Server</span></span>|  
|<span data-ttu-id="08a69-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="08a69-106">Event ID</span></span>|<span data-ttu-id="08a69-107">8649</span><span class="sxs-lookup"><span data-stu-id="08a69-107">8649</span></span>|  
|<span data-ttu-id="08a69-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="08a69-108">Event Source</span></span>|<span data-ttu-id="08a69-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="08a69-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="08a69-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="08a69-110">Component</span></span>|<span data-ttu-id="08a69-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="08a69-111">SQLEngine</span></span>|  
|<span data-ttu-id="08a69-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="08a69-112">Symbolic Name</span></span>|<span data-ttu-id="08a69-113">COST_TOO_HIGH</span><span class="sxs-lookup"><span data-stu-id="08a69-113">COST_TOO_HIGH</span></span>|  
|<span data-ttu-id="08a69-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="08a69-114">Message Text</span></span>|<span data-ttu-id="08a69-115">Запрос %d был отменен, потому что расчетные затраты на его выполнение превышают установленный порог в %d.</span><span class="sxs-lookup"><span data-stu-id="08a69-115">The query has been canceled because the estimated cost of this query (%d) exceeds the configured threshold of %d.</span></span> <span data-ttu-id="08a69-116">Свяжитесь с системным администратором.</span><span class="sxs-lookup"><span data-stu-id="08a69-116">Contact the system administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08a69-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="08a69-117">Explanation</span></span>  
 <span data-ttu-id="08a69-118">Запрос был отменен, потому что расчетные затраты на его выполнение превысили установленный параметром QUERY_GOVERNOR_COST_LIMIT порог.</span><span class="sxs-lookup"><span data-stu-id="08a69-118">The query was canceled because the estimated cost of this query exceeds the configured threshold set for the QUERY_GOVERNOR_COST_LIMIT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08a69-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="08a69-119">User Action</span></span>  
 <span data-ttu-id="08a69-120">Установите более высокое значение параметра QUERY_GOVERNOR_COST_LIMIT.</span><span class="sxs-lookup"><span data-stu-id="08a69-120">Set the QUERY_GOVERNOR_COST_LIMIT option to a higher value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a69-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="08a69-121">See Also</span></span>  
 [<span data-ttu-id="08a69-122">SET QUERY_GOVERNOR_COST_LIMIT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="08a69-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql)  
  
  
