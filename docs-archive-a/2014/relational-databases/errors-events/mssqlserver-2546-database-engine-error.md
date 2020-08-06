---
title: MSSQLSERVER_2546 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2546 (Database Engine error)
ms.assetid: c8f0e1b4-c7c4-45f2-9221-746714172313
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c1c5f64ca0daba413f2b71c05f5b8e57b2d55df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729513"
---
# <a name="mssqlserver_2546"></a><span data-ttu-id="2ddba-102">MSSQLSERVER_2546</span><span class="sxs-lookup"><span data-stu-id="2ddba-102">MSSQLSERVER_2546</span></span>
    
## <a name="details"></a><span data-ttu-id="2ddba-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="2ddba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ddba-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="2ddba-104">Product Name</span></span>|<span data-ttu-id="2ddba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ddba-105">SQL Server</span></span>|  
|<span data-ttu-id="2ddba-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="2ddba-106">Event ID</span></span>|<span data-ttu-id="2ddba-107">2546</span><span class="sxs-lookup"><span data-stu-id="2ddba-107">2546</span></span>|  
|<span data-ttu-id="2ddba-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="2ddba-108">Event Source</span></span>|<span data-ttu-id="2ddba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2ddba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2ddba-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="2ddba-110">Component</span></span>|<span data-ttu-id="2ddba-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2ddba-111">SQLEngine</span></span>|  
|<span data-ttu-id="2ddba-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="2ddba-112">Symbolic Name</span></span>|<span data-ttu-id="2ddba-113">DBCC_INDEX_MARKED_DISABLED</span><span class="sxs-lookup"><span data-stu-id="2ddba-113">DBCC_INDEX_MARKED_DISABLED</span></span>|  
|<span data-ttu-id="2ddba-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="2ddba-114">Message Text</span></span>|<span data-ttu-id="2ddba-115">Индекс «INDEX_NAME» для таблицы «OBJECT_NAME» помечен как отключенный.</span><span class="sxs-lookup"><span data-stu-id="2ddba-115">Index 'INDEX_NAME' on table 'OBJECT_NAME' is marked as disabled.</span></span> <span data-ttu-id="2ddba-116">Перестройте индекс и переведите его в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="2ddba-116">Rebuild the index to bring it online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ddba-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="2ddba-117">Explanation</span></span>  
 <span data-ttu-id="2ddba-118">Указанный индекс помечен как находящийся в режиме «вне сети» или как отключенный.</span><span class="sxs-lookup"><span data-stu-id="2ddba-118">The specified index is marked as offline or is disabled.</span></span> <span data-ttu-id="2ddba-119">Таким образом, данный индекс не может быть проверен.</span><span class="sxs-lookup"><span data-stu-id="2ddba-119">Therefore, this index cannot be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ddba-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="2ddba-120">User Action</span></span>  
 <span data-ttu-id="2ddba-121">Перестройте индекс с помощью оператора ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="2ddba-121">Rebuild the index by using ALTER INDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ddba-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ddba-122">See Also</span></span>  
 <span data-ttu-id="2ddba-123">[ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ddba-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="2ddba-124">Реорганизация и перестроение индексов</span><span class="sxs-lookup"><span data-stu-id="2ddba-124">Reorganize and Rebuild Indexes</span></span>](../indexes/indexes.md)  
  
  
