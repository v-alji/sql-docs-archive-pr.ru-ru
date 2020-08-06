---
title: Создание, изменение и удаление селективных XML-индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: c398f396-f630-4a2d-a264-f243c5346de1
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4123a46cc13359c936e6f9cfc0db3dcfdaa175
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730249"
---
# <a name="create-alter-and-drop-selective-xml-indexes"></a><span data-ttu-id="cdf2a-102">Создание, изменение и удаление селективных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="cdf2a-102">Create, Alter, and Drop Selective XML Indexes</span></span>
  <span data-ttu-id="cdf2a-103">Описывает способы создания нового селективного XML-индекса, изменения или удаления существующего селективного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-103">Describes how to create a new selective XML index, or alter or drop an existing selective XML index.</span></span>  
  
 <span data-ttu-id="cdf2a-104">Дополнительные сведения о селективных XML-индексах см. в разделе [Выборочный XML-индекс (SXI)](selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="cdf2a-104">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="creating-a-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="cdf2a-105">Создание селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="cdf2a-105">Creating a Selective XML Index</span></span>  
  
### <a name="how-to-create-a-selective-xml-index"></a><span data-ttu-id="cdf2a-106">Руководство. Создание селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="cdf2a-106">How to: Create a Selective XML Index</span></span>  
 <span data-ttu-id="cdf2a-107">**Создание нового селективного XML-индекса с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="cdf2a-107">**Create a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="cdf2a-108">Создание селективного XML-индекса путем вызова инструкции CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-108">Create a selective XML index by calling the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="cdf2a-109">Дополнительные сведения см. в разделе [CREATE SELECTIVE XML INDEX (Transact-SQL)](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cdf2a-109">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
 <span data-ttu-id="cdf2a-110">**Пример**</span><span class="sxs-lookup"><span data-stu-id="cdf2a-110">**Example**</span></span>  
  
 <span data-ttu-id="cdf2a-111">В следующем примере показан синтаксис для создания селективного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-111">The following example shows the syntax for creating a selective XML index.</span></span> <span data-ttu-id="cdf2a-112">Он также содержит несколько вариантов синтаксиса для описания индексируемых путей с указаниями по оптимизации.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-112">It also shows several variations of the syntax for describing the paths to be indexed, with optional optimization hints.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX sxi_index  
ON Tbl(xmlcol)  
  
FOR(  
    pathab   = '/a/b' as XQUERY 'node()'  
    pathabc  = '/a/b/c' as XQUERY 'xs:double',   
    pathdtext = '/a/b/d/text()' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
    pathabe = '/a/b/e' as SQL NVARCHAR(100)  
)  
```  
  
  
  
##  <a name="altering-a-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="cdf2a-113">Изменение селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="cdf2a-113">Altering a Selective XML Index</span></span>  
  
### <a name="how-to-alter-a-selective-xml-index"></a><span data-ttu-id="cdf2a-114">Руководство. Изменение селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="cdf2a-114">How to: Alter a Selective XML Index</span></span>  
 <span data-ttu-id="cdf2a-115">**изменить селективный XML-индекс с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="cdf2a-115">**Alter a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="cdf2a-116">Измените существующий селективный XML-индекс с помощью инструкции ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-116">Alter an existing selective XML index by calling the ALTER INDEX statement.</span></span> <span data-ttu-id="cdf2a-117">Дополнительные сведения см. в разделе [ALTER INDEX (селективные XML-индексы)](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="cdf2a-117">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="cdf2a-118">**Пример**</span><span class="sxs-lookup"><span data-stu-id="cdf2a-118">**Example**</span></span>  
  
 <span data-ttu-id="cdf2a-119">В следующем примере показана инструкция ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-119">The following example shows an ALTER INDEX statement.</span></span> <span data-ttu-id="cdf2a-120">Эта инструкция добавляет путь `'/a/b/m'` в часть XQuery индекса и удаляет путь `'/a/b/e'` из части SQL индекса, созданного в примере в разделе [CREATE SELECTIVE XML INDEX (Transact-SQL)](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cdf2a-120">This statement adds the path `'/a/b/m'` to the XQuery part of the index and deletes the path `'/a/b/e'` from the SQL part of the index created in the example in the topic [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span> <span data-ttu-id="cdf2a-121">Путь для удаления определяется по имени, указанному при его создании.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-121">The path to delete is identified by the name that was given to it when it was created.</span></span>  
  
```sql  
ALTER INDEX sxi_index  
ON Tbl  
FOR   
(  
    ADD pathm = '/a/b/m' as XQUERY 'node()' ,  
    REMOVE pathabe  
)  
```  
  
  
  
##  <a name="dropping-a-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="cdf2a-122">Удаление селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="cdf2a-122">Dropping a Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-selective-xml-index"></a><span data-ttu-id="cdf2a-123">Руководство. Удаление селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="cdf2a-123">How to: Drop a Selective XML Index</span></span>  
 <span data-ttu-id="cdf2a-124">**Удаление селективного XML-индекса с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="cdf2a-124">**Drop a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="cdf2a-125">Удалите селективный XML-индекс с помощью инструкции DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-125">Drop a selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="cdf2a-126">Дополнительные сведения см. в разделе [DROP INDEX (селективные XML-индексы)](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span><span class="sxs-lookup"><span data-stu-id="cdf2a-126">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span></span>  
  
 <span data-ttu-id="cdf2a-127">**Пример**</span><span class="sxs-lookup"><span data-stu-id="cdf2a-127">**Example**</span></span>  
  
 <span data-ttu-id="cdf2a-128">В следующем примере показана инструкция DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="cdf2a-128">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX sxi_index ON tbl  
```  
  
 
  
  
