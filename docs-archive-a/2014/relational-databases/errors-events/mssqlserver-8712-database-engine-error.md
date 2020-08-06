---
title: MSSQLSERVER_8712 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8712 (Database Engine error)
ms.assetid: 292fb3bc-062e-41e4-a566-b5d3d0b21977
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9285d4846cac5af2dd6e87ab55d5fd0610586d07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669422"
---
# <a name="mssqlserver_8712"></a><span data-ttu-id="535f3-102">MSSQLSERVER_8712</span><span class="sxs-lookup"><span data-stu-id="535f3-102">MSSQLSERVER_8712</span></span>
    
## <a name="details"></a><span data-ttu-id="535f3-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="535f3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="535f3-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="535f3-104">Product Name</span></span>|<span data-ttu-id="535f3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="535f3-105">SQL Server</span></span>|  
|<span data-ttu-id="535f3-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="535f3-106">Event ID</span></span>|<span data-ttu-id="535f3-107">8712</span><span class="sxs-lookup"><span data-stu-id="535f3-107">8712</span></span>|  
|<span data-ttu-id="535f3-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="535f3-108">Event Source</span></span>|<span data-ttu-id="535f3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="535f3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="535f3-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="535f3-110">Component</span></span>|<span data-ttu-id="535f3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="535f3-111">SQLEngine</span></span>|  
|<span data-ttu-id="535f3-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="535f3-112">Symbolic Name</span></span>|<span data-ttu-id="535f3-113">USEPLAN_ERR_NO_INDEX</span><span class="sxs-lookup"><span data-stu-id="535f3-113">USEPLAN_ERR_NO_INDEX</span></span>|  
|<span data-ttu-id="535f3-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="535f3-114">Message Text</span></span>|<span data-ttu-id="535f3-115">Индекс «%.\*ls», заданный в указании USE PLAN, не существует.</span><span class="sxs-lookup"><span data-stu-id="535f3-115">Index '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="535f3-116">Укажите существующий индекс или создайте индекс с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="535f3-116">Specify an existing index, or create an index with the specified name.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="535f3-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="535f3-117">Explanation</span></span>  
 <span data-ttu-id="535f3-118">Индекс, заданный в указании USE PLAN, не существует.</span><span class="sxs-lookup"><span data-stu-id="535f3-118">An index that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="535f3-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="535f3-119">User Action</span></span>  
 <span data-ttu-id="535f3-120">Убедитесь в том, что существуют все индексы, которые заданы в указании USE PLAN.</span><span class="sxs-lookup"><span data-stu-id="535f3-120">Ensure all indexes that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535f3-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="535f3-121">See Also</span></span>  
 <span data-ttu-id="535f3-122">[Указания запросов (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="535f3-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="535f3-123">Руководства планов</span><span class="sxs-lookup"><span data-stu-id="535f3-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
