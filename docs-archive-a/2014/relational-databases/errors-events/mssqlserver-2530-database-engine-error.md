---
title: MSSQLSERVER_2530 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 5d4be07a-38a5-4b25-819c-4dcb4636cc15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 30b57aae907d6f0acc4d1c0e6021bf936621c69e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655242"
---
# <a name="mssqlserver_2530"></a><span data-ttu-id="312b5-102">MSSQLSERVER_2530</span><span class="sxs-lookup"><span data-stu-id="312b5-102">MSSQLSERVER_2530</span></span>
    
## <a name="details"></a><span data-ttu-id="312b5-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="312b5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="312b5-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="312b5-104">Product Name</span></span>|<span data-ttu-id="312b5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="312b5-105">SQL Server</span></span>|  
|<span data-ttu-id="312b5-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="312b5-106">Event ID</span></span>|<span data-ttu-id="312b5-107">2530</span><span class="sxs-lookup"><span data-stu-id="312b5-107">2530</span></span>|  
|<span data-ttu-id="312b5-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="312b5-108">Event Source</span></span>|<span data-ttu-id="312b5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="312b5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="312b5-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="312b5-110">Component</span></span>|<span data-ttu-id="312b5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="312b5-111">SQLEngine</span></span>|  
|<span data-ttu-id="312b5-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="312b5-112">Symbolic Name</span></span>|<span data-ttu-id="312b5-113">DBCC_INDEX_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="312b5-113">DBCC_INDEX_IS_OFFLINE</span></span>|  
|<span data-ttu-id="312b5-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="312b5-114">Message Text</span></span>|<span data-ttu-id="312b5-115">Индекс "%.\*ls" для таблицы "%.\*ls" помечен как отключенный.</span><span class="sxs-lookup"><span data-stu-id="312b5-115">The index "%.\*ls" on table "%.\*ls" is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="312b5-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="312b5-116">Explanation</span></span>  
 <span data-ttu-id="312b5-117">Инструкция DBCC не может быть выполнена, так как отключен указанный индекс.</span><span class="sxs-lookup"><span data-stu-id="312b5-117">The DBCC statement cannot proceed because the specified index is disabled.</span></span> <span data-ttu-id="312b5-118">После отключения индекс остается в отключенном состоянии до тех пор, пока он не будет перестроен или удален и создан повторно.</span><span class="sxs-lookup"><span data-stu-id="312b5-118">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped and re-created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="312b5-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="312b5-119">User Action</span></span>  
  
1.  <span data-ttu-id="312b5-120">Включить отключенный индекс одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="312b5-120">Enable the disabled index by using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="312b5-121">Инструкцией ALTER INDEX с предложением REBUILD.</span><span class="sxs-lookup"><span data-stu-id="312b5-121">ALTER INDEX statement with the REBUILD clause</span></span>  
  
    -   <span data-ttu-id="312b5-122">Инструкцией CREATE INDEX с предложением DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="312b5-122">CREATE INDEX with the DROP_EXISTING clause</span></span>  
  
    -   <span data-ttu-id="312b5-123">DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="312b5-123">DBCC DBREINDEX</span></span>  
  
2.  <span data-ttu-id="312b5-124">Перезапустить инструкцию DBCC.</span><span class="sxs-lookup"><span data-stu-id="312b5-124">Rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312b5-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="312b5-125">See Also</span></span>  
 <span data-ttu-id="312b5-126">[Включение индексов и ограничений](../indexes/enable-indexes-and-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="312b5-126">[Enable Indexes and Constraints](../indexes/enable-indexes-and-constraints.md) </span></span>  
 <span data-ttu-id="312b5-127">[ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="312b5-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="312b5-128">[CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="312b5-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="312b5-129">DBCC DBREINDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="312b5-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql)  
  
  
