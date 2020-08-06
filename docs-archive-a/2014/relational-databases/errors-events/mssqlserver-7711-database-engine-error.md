---
title: MSSQLSERVER_7711 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7711 (Database Engine error)
ms.assetid: a5c7cd6e-18d6-47ef-902b-db9dd64bba34
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e29b2ea993e8e5332ef03b05f628dc791e20aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664236"
---
# <a name="mssqlserver_7711"></a><span data-ttu-id="95210-102">MSSQLSERVER_7711</span><span class="sxs-lookup"><span data-stu-id="95210-102">MSSQLSERVER_7711</span></span>
    
## <a name="details"></a><span data-ttu-id="95210-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="95210-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95210-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="95210-104">Product Name</span></span>|<span data-ttu-id="95210-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="95210-105">SQL Server</span></span>|  
|<span data-ttu-id="95210-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="95210-106">Event ID</span></span>|<span data-ttu-id="95210-107">7711</span><span class="sxs-lookup"><span data-stu-id="95210-107">7711</span></span>|  
|<span data-ttu-id="95210-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="95210-108">Event Source</span></span>|<span data-ttu-id="95210-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="95210-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="95210-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="95210-110">Component</span></span>|<span data-ttu-id="95210-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="95210-111">SQLEngine</span></span>|  
|<span data-ttu-id="95210-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="95210-112">Symbolic Name</span></span>|<span data-ttu-id="95210-113">PRT_RANGE_OVERLAP</span><span class="sxs-lookup"><span data-stu-id="95210-113">PRT_RANGE_OVERLAP</span></span>|  
|<span data-ttu-id="95210-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="95210-114">Message Text</span></span>|<span data-ttu-id="95210-115">Параметр DATA_COMPRESSION указан более одного раза для таблицы, индекса, либо одной из секций таблицы или индекса.</span><span class="sxs-lookup"><span data-stu-id="95210-115">The DATA_COMPRESSION option was specified more than once for the table or index or one of its partitions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="95210-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="95210-116">Explanation</span></span>  
 <span data-ttu-id="95210-117">В одной из следующих инструкций при обработке параметра DATA_COMPRESSION произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="95210-117">An error occurred in the DATA_COMPRESSION option in one of the following statements:</span></span>  
  
-   <span data-ttu-id="95210-118">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="95210-118">CREATE TABLE</span></span>  
  
-   <span data-ttu-id="95210-119">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="95210-119">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="95210-120">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="95210-120">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="95210-121">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="95210-121">ALTER INDEX</span></span>  
  
 <span data-ttu-id="95210-122">Если указанная таблица (или индекс) секционирована, то по крайней мере для одной из секций параметр DATA_COMPRESSION был указан более одного раза.</span><span class="sxs-lookup"><span data-stu-id="95210-122">If the table or index cited is partitioned, the DATA_COMPRESSION option was listed more than one time for at least one of the partitions.</span></span> <span data-ttu-id="95210-123">Если указанная таблица (или индекс) не секционирована, то параметр DATA_COMPRESSION был указан более одного раза.</span><span class="sxs-lookup"><span data-stu-id="95210-123">If the table or index is not partitioned, the DATA_COMPRESSION option was cited more than one time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95210-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="95210-124">User Action</span></span>  
 <span data-ttu-id="95210-125">Применительно к секционированной таблице (индексу) убедитесь, что параметр DATA_COMPRESSION указан для каждой секции не более одного раза.</span><span class="sxs-lookup"><span data-stu-id="95210-125">For a partitioned table or index, make sure that the DATA_COMPRESSION option is specified only one time for each partition.</span></span> <span data-ttu-id="95210-126">Применительно к несекционированной таблице (индексу), указывайте параметр DATA_COMPRESSION в этой инструкции не более одного раза.</span><span class="sxs-lookup"><span data-stu-id="95210-126">For a table or index that is not partitioned, use the DATA_COMPRESSION option only one time in the statement.</span></span>  
  
  
