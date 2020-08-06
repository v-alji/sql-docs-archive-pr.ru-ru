---
title: MSSQLSERVER_8710 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8710 (Database Engine error)
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65fb6b3efb42c282347f560353a2b21edc337859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669426"
---
# <a name="mssqlserver_8710"></a><span data-ttu-id="11ce5-102">MSSQLSERVER_8710</span><span class="sxs-lookup"><span data-stu-id="11ce5-102">MSSQLSERVER_8710</span></span>
    
## <a name="details"></a><span data-ttu-id="11ce5-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="11ce5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11ce5-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="11ce5-104">Product Name</span></span>|<span data-ttu-id="11ce5-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="11ce5-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="11ce5-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="11ce5-106">Event ID</span></span>|<span data-ttu-id="11ce5-107">8710</span><span class="sxs-lookup"><span data-stu-id="11ce5-107">8710</span></span>|  
|<span data-ttu-id="11ce5-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="11ce5-108">Event Source</span></span>|<span data-ttu-id="11ce5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="11ce5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="11ce5-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="11ce5-110">Component</span></span>|<span data-ttu-id="11ce5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="11ce5-111">SQLEngine</span></span>|  
|<span data-ttu-id="11ce5-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="11ce5-112">Symbolic Name</span></span>|<span data-ttu-id="11ce5-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span><span class="sxs-lookup"><span data-stu-id="11ce5-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span></span>|  
|<span data-ttu-id="11ce5-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="11ce5-114">Message Text</span></span>|<span data-ttu-id="11ce5-115">Агрегатные функции, используемые в запросах CUBE, ROLLUP или GROUPING SET, должны обеспечивать возможность слияния подытогов.</span><span class="sxs-lookup"><span data-stu-id="11ce5-115">Aggregate functions that are used with CUBE, ROLLUP, or GROUPING SET queries must provide for the merging of subaggregates.</span></span> <span data-ttu-id="11ce5-116">Чтобы решить эту проблему, удалите агрегатную функцию или напишите запрос UNION ALL с предложениями GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="11ce5-116">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="11ce5-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="11ce5-117">Explanation</span></span>  
 <span data-ttu-id="11ce5-118">В запросе CUBE, ROLLUP или GROUPING SETS была использована агрегатная функция, не предусматривающая метод для слияния подытогов.</span><span class="sxs-lookup"><span data-stu-id="11ce5-118">An aggregate function has been used with CUBE, ROLLUP, or GROUPING SETS that does not provide a method for merging subaggregates.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11ce5-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="11ce5-119">User Action</span></span>  
 <span data-ttu-id="11ce5-120">Чтобы решить эту проблему, удалите агрегатную функцию или напишите запрос UNION ALL с предложениями GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="11ce5-120">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>  
  
  
