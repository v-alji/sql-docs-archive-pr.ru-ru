---
title: MSSQLSERVER_1904 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1904 (Database Engine error)
ms.assetid: 2a35d57d-74e2-45a2-8f67-3f2e51d69712
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 568cfe7499c041c2ee6a8ac3698b31698171bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658790"
---
# <a name="mssqlserver_1904"></a><span data-ttu-id="ede34-102">MSSQLSERVER_1904</span><span class="sxs-lookup"><span data-stu-id="ede34-102">MSSQLSERVER_1904</span></span>
    
## <a name="details"></a><span data-ttu-id="ede34-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="ede34-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ede34-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ede34-104">Product Name</span></span>|<span data-ttu-id="ede34-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ede34-105">SQL Server</span></span>|  
|<span data-ttu-id="ede34-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ede34-106">Event ID</span></span>|<span data-ttu-id="ede34-107">1904</span><span class="sxs-lookup"><span data-stu-id="ede34-107">1904</span></span>|  
|<span data-ttu-id="ede34-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ede34-108">Event Source</span></span>|<span data-ttu-id="ede34-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ede34-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ede34-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ede34-110">Component</span></span>|<span data-ttu-id="ede34-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ede34-111">SQLEngine</span></span>|  
|<span data-ttu-id="ede34-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ede34-112">Symbolic Name</span></span>|<span data-ttu-id="ede34-113">KEYCOUNT</span><span class="sxs-lookup"><span data-stu-id="ede34-113">KEYCOUNT</span></span>|  
|<span data-ttu-id="ede34-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ede34-114">Message Text</span></span>|<span data-ttu-id="ede34-115">Сообщение %S_MSG "%.\*ls", касающееся таблицы "%.\*ls", содержит %d имен столбцов в списке ключей %S_MSG.</span><span class="sxs-lookup"><span data-stu-id="ede34-115">The %S_MSG '%.\*ls' on table '%.\*ls' has %d column names in %S_MSG key list.</span></span> <span data-ttu-id="ede34-116">Максимальный предел для индекса или списка ключевых столбцов статистики равен %d.</span><span class="sxs-lookup"><span data-stu-id="ede34-116">The maximum limit for index or statistics key column list is %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ede34-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ede34-117">Explanation</span></span>  
 <span data-ttu-id="ede34-118">Список ключевых столбцов для указанного индекса или статистики данных превышает максимально допустимое количество столбцов.</span><span class="sxs-lookup"><span data-stu-id="ede34-118">The key column list for the specified index or statistics exceeds the maximum number of columns allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ede34-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ede34-119">User Action</span></span>  
 <span data-ttu-id="ede34-120">Измените список ключевых столбцов, чтобы он включал не больше указанного максимального количества столбцов.</span><span class="sxs-lookup"><span data-stu-id="ede34-120">Modify the key column list to include no more than the specified maximum number of columns.</span></span>  
  
 <span data-ttu-id="ede34-121">Применительно к некластеризованным индексам рассмотрите возможность использования предложения INCLUDE в инструкции CREATE INDEX для добавления столбцов к индексу в качестве неключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="ede34-121">For nonclustered indexes, consider using the INCLUDE clause in the CREATE INDEX statement to add columns to the index as nonkey columns.</span></span> <span data-ttu-id="ede34-122">Этот метод позволяет предотвратить превышение текущего ограничения на размер индекса, которое составляет максимум 16 ключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="ede34-122">This method avoids exceeding the current index size limitation of a maximum of 16 key columns.</span></span> <span data-ttu-id="ede34-123">Дополнительные сведения см. в статье [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="ede34-123">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede34-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ede34-124">See Also</span></span>  
 <span data-ttu-id="ede34-125">[CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ede34-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="ede34-126">CREATE STATISTICS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ede34-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-statistics-transact-sql)  
  
  
