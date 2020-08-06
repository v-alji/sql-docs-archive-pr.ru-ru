---
title: MSSQLSERVER_2518 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2518 (Database Engine error)
ms.assetid: 54a13abc-4c33-43f0-b55d-e2e74a1381c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5f5517458c1014d7830c4813b95e1120bef452e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657801"
---
# <a name="mssqlserver_2518"></a><span data-ttu-id="5e5ba-102">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="5e5ba-102">MSSQLSERVER_2518</span></span>
    
## <a name="details"></a><span data-ttu-id="5e5ba-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5e5ba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e5ba-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5e5ba-104">Product Name</span></span>|<span data-ttu-id="5e5ba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e5ba-105">SQL Server</span></span>|  
|<span data-ttu-id="5e5ba-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5e5ba-106">Event ID</span></span>|<span data-ttu-id="5e5ba-107">2518</span><span class="sxs-lookup"><span data-stu-id="5e5ba-107">2518</span></span>|  
|<span data-ttu-id="5e5ba-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5e5ba-108">Event Source</span></span>|<span data-ttu-id="5e5ba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5e5ba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5e5ba-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5e5ba-110">Component</span></span>|<span data-ttu-id="5e5ba-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5e5ba-111">SQLEngine</span></span>|  
|<span data-ttu-id="5e5ba-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5e5ba-112">Symbolic Name</span></span>|<span data-ttu-id="5e5ba-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span><span class="sxs-lookup"><span data-stu-id="5e5ba-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span></span>|  
|<span data-ttu-id="5e5ba-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5e5ba-114">Message Text</span></span>|<span data-ttu-id="5e5ba-115">Объект с идентификатором O_ID (объект "O_NAME"). Вычисляемые столбцы и определяемые пользователем типы нельзя проверить для данного объекта, поскольку отключена среда CLR.</span><span class="sxs-lookup"><span data-stu-id="5e5ba-115">Object ID O_ID (object "O_NAME"): Computed columns and user-defined types cannot be checked for this object because the common language runtime (CLR) is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5e5ba-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5e5ba-116">Explanation</span></span>  
 <span data-ttu-id="5e5ba-117">Это информационное сообщение указывает, что обработчик запросов не смог обеспечить команду DBCC внутренним объектом, с помощью которого можно оценить вычисляемые столбцы и определяемые пользователем типы среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5e5ba-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for computed columns and common language runtime (CLR) user-defined types to be evaluated.</span></span> <span data-ttu-id="5e5ba-118">Ошибка произошла, потому что одному из столбцов требовалась среда CLR, но она была отключена.</span><span class="sxs-lookup"><span data-stu-id="5e5ba-118">This problem occurred because one of the columns involved the CLR, but the CLR is not enabled.</span></span> <span data-ttu-id="5e5ba-119">Внутренний объект охватывает все столбцы.</span><span class="sxs-lookup"><span data-stu-id="5e5ba-119">The internal object covers all columns.</span></span> <span data-ttu-id="5e5ba-120">Следовательно, невозможность вычислить один столбец препятствует созданию внутреннего объекта.</span><span class="sxs-lookup"><span data-stu-id="5e5ba-120">Therefore, the inability to evaluate a single column prevents creating the internal object.</span></span> <span data-ttu-id="5e5ba-121">Это означает, что вычисляемые столбцы не будут проверены командой DBCC на корректность и согласованность индексов и базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="5e5ba-121">This means that computed columns will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e5ba-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5e5ba-122">User Action</span></span>  
 <span data-ttu-id="5e5ba-123">Включите CLR и повторите инструкцию DBCC.</span><span class="sxs-lookup"><span data-stu-id="5e5ba-123">Enable CLR and rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5ba-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e5ba-124">See Also</span></span>  
 [<span data-ttu-id="5e5ba-125">Включение интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="5e5ba-125">Enabling CLR Integration</span></span>](../clr-integration/clr-integration-enabling.md)  
  
  
