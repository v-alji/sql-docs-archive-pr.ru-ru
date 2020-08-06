---
title: MSSQLSERVER_360 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 360 (Database Engine error)
ms.assetid: e2b7c1b2-3679-4206-9b25-6bd55ef96a2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b30311d7f55231c1e7a6d5969d49c5d1bc07a848
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658290"
---
# <a name="mssqlserver_360"></a><span data-ttu-id="28d9e-102">MSSQLSERVER_360</span><span class="sxs-lookup"><span data-stu-id="28d9e-102">MSSQLSERVER_360</span></span>
    
## <a name="details"></a><span data-ttu-id="28d9e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="28d9e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28d9e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="28d9e-104">Product Name</span></span>|<span data-ttu-id="28d9e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="28d9e-105">SQL Server</span></span>|  
|<span data-ttu-id="28d9e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="28d9e-106">Event ID</span></span>|<span data-ttu-id="28d9e-107">360</span><span class="sxs-lookup"><span data-stu-id="28d9e-107">360</span></span>|  
|<span data-ttu-id="28d9e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="28d9e-108">Event Source</span></span>|<span data-ttu-id="28d9e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="28d9e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="28d9e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="28d9e-110">Component</span></span>|<span data-ttu-id="28d9e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="28d9e-111">SQLEngine</span></span>|  
|<span data-ttu-id="28d9e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="28d9e-112">Symbolic Name</span></span>|<span data-ttu-id="28d9e-113">DML_UPDATE_SPARSE_AND_COLSET</span><span class="sxs-lookup"><span data-stu-id="28d9e-113">DML_UPDATE_SPARSE_AND_COLSET</span></span>|  
|<span data-ttu-id="28d9e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="28d9e-114">Message Text</span></span>|<span data-ttu-id="28d9e-115">Список целевых столбцов для инструкций INSERT, UPDATE или MERGE не может содержать одновременно разреженный столбец и набор столбцов, в состав которого входит разреженный столбец.</span><span class="sxs-lookup"><span data-stu-id="28d9e-115">The target column list of an INSERT, UPDATE, or MERGE statement cannot contain both a sparse column and the column set that contains the sparse column.</span></span> <span data-ttu-id="28d9e-116">Перепишите запрос таким образом, чтобы список целевых столбцов содержал либо разреженный столбец, либо набор столбцов, но не то и другое сразу.</span><span class="sxs-lookup"><span data-stu-id="28d9e-116">Rewrite the statement to include either the sparse column or the column set, but not both.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28d9e-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="28d9e-117">Explanation</span></span>  
 <span data-ttu-id="28d9e-118">Набор столбцов представляет собой нетипизированное XML-представление, объединяющее несколько столбцов таблицы в виде структурированного вывода.</span><span class="sxs-lookup"><span data-stu-id="28d9e-118">A column set is an untyped XML representation that combines some columns of a table into a structured output.</span></span> <span data-ttu-id="28d9e-119">Была предпринята попытка изменить набор столбцов и столбец, являющийся частью набора столбцов, в результате чего были созданы две ссылки на один и тот же столбец.</span><span class="sxs-lookup"><span data-stu-id="28d9e-119">An attempt was made to modify both the column set and a column that is included in the column set, causing two references to the same column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28d9e-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="28d9e-120">User Action</span></span>  
 <span data-ttu-id="28d9e-121">Перепишите инструкцию таким образом, чтобы в ней содержалась ссылка либо на столбец, либо на набор столбцов, но не на то и другое одновременно.</span><span class="sxs-lookup"><span data-stu-id="28d9e-121">Rewrite the statement to include references to either the column or the column set, but do not include both in the statement.</span></span>  
  
  
