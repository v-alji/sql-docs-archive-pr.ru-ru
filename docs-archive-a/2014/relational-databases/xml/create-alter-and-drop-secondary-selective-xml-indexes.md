---
title: Создание, изменение и удаление вторичных селективных XML-индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 45128105-833b-40a9-9cc9-1ae03ac0b52b
author: rothja
ms.author: jroth
ms.openlocfilehash: e6f7296896b6421db5329565403cdcbaf10b26a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730250"
---
# <a name="create-alter-and-drop-secondary-selective-xml-indexes"></a><span data-ttu-id="f776c-102">Создание, изменение и удаление вторичных селективных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="f776c-102">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>
  <span data-ttu-id="f776c-103">Описание создания нового вторичного селективного XML-индекса, а также изменения или удаления существующего вторичного селективного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="f776c-103">Describes how to create a new secondary selective XML index, or alter or drop an existing secondary selective XML index.</span></span>  
  
##  <a name="creating-a-secondary-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="f776c-104">Создание вторичного селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="f776c-104">Creating a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-create-a-secondary-selective-xml-index"></a><span data-ttu-id="f776c-105">Руководство. Создание вторичного селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="f776c-105">How to: Create a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="f776c-106">**Создание вторичного селективного XML-индекса с использованием Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="f776c-106">**Create a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="f776c-107">Создание вторичного селективного XML-индекса путем вызова инструкции CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="f776c-107">Create a secondary selective XML index by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="f776c-108">Дополнительные сведения см. в разделе [создание XML-индекса &#40;селективные XML-индексы&#41;] (~/т-скл/статементс/креате-ксмл-индекс-селективе-ксмл-индексес.</span><span class="sxs-lookup"><span data-stu-id="f776c-108">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="f776c-109">**Пример**</span><span class="sxs-lookup"><span data-stu-id="f776c-109">**Example**</span></span>  
  
 <span data-ttu-id="f776c-110">В следующем примере создается вторичный селективный XML-индекс с путем `'pathabc'`.</span><span class="sxs-lookup"><span data-stu-id="f776c-110">The following example creates a secondary selective XML index on the path `'pathabc'`.</span></span> <span data-ttu-id="f776c-111">Путь к индексу определяется по имени, заданному для него при создании с помощью инструкции CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="f776c-111">The path to index is identified by the name that was given to it when it was created with the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="f776c-112">Дополнительные сведения см. в разделе [CREATE SELECTIVE XML INDEX (Transact-SQL)](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f776c-112">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
```sql  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="altering-a-secondary-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="f776c-113">Изменение вторичного селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="f776c-113">Altering a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="f776c-114">Инструкция ALTER не поддерживается для вторичных селективных XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="f776c-114">The ALTER statement is not supported for secondary selective XML indexes.</span></span> <span data-ttu-id="f776c-115">Чтобы изменить вторичный селективный XML-индекс, удалите существующий индекс и создайте его повторно.</span><span class="sxs-lookup"><span data-stu-id="f776c-115">To change a secondary selective XML index, drop the existing index and recreate it.</span></span>  
  
### <a name="how-to-alter-a-secondary-selective-xml-index"></a><span data-ttu-id="f776c-116">Руководство. Изменение вторичного селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="f776c-116">How to: Alter a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="f776c-117">**Изменение вторичного селективного XML-индекса с использованием Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="f776c-117">**Alter a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 1.  <span data-ttu-id="f776c-118">Удаление существующего вторичного селективного XML-индекса путем вызова инструкции DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="f776c-118">Drop the existing secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="f776c-119">Дополнительные сведения см. в разделе [DROP INDEX (селективные XML-индексы)](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="f776c-119">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
2.  <span data-ttu-id="f776c-120">Повторное создание индекса с требуемыми параметрами путем вызова инструкции CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="f776c-120">Recreate the index with the desired options by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="f776c-121">Дополнительные сведения см. в разделе [создание XML-индекса &#40;селективные XML-индексы&#41;] (~/т-скл/статементс/креате-ксмл-индекс-селективе-ксмл-индексес.</span><span class="sxs-lookup"><span data-stu-id="f776c-121">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="f776c-122">**Пример**</span><span class="sxs-lookup"><span data-stu-id="f776c-122">**Example**</span></span>  
  
 <span data-ttu-id="f776c-123">В следующем примере показан способ изменения вторичного селективного XML-индекса путем его удаления и повторного создания.</span><span class="sxs-lookup"><span data-stu-id="f776c-123">The following example changes a secondary selective XML index by dropping it and recreating it.</span></span>  
  
```sql  
DROP INDEX filt_sxi_index_c  
  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="dropping-a-secondary-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="f776c-124">Удаление вторичного селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="f776c-124">Dropping a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-secondary-selective-xml-index"></a><span data-ttu-id="f776c-125">Руководство. Удаление вторичного селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="f776c-125">How to: Drop a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="f776c-126">**Удаление вторичного селективного XML-индекса с использованием Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="f776c-126">**Drop a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="f776c-127">Удаление вторичного селективного XML-индекса путем вызова инструкции DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="f776c-127">Drop a secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="f776c-128">Дополнительные сведения см. в разделе [DROP INDEX (селективные XML-индексы)](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="f776c-128">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="f776c-129">**Пример**</span><span class="sxs-lookup"><span data-stu-id="f776c-129">**Example**</span></span>  
  
 <span data-ttu-id="f776c-130">В следующем примере показана инструкция DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="f776c-130">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX ssxi_index  
ON tbl  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="f776c-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="f776c-131">See Also</span></span>  
 [<span data-ttu-id="f776c-132">Выборочный XML-индекс (SXI)</span><span class="sxs-lookup"><span data-stu-id="f776c-132">Selective XML Indexes &#40;SXI&#41;</span></span>](selective-xml-indexes-sxi.md)  
  
  
