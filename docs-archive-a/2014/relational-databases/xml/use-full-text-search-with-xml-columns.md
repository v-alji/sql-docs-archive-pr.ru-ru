---
title: Полнотекстовый поиск в столбцах XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml columns [full-text search]
- indexes [full-text search]
ms.assetid: 8096cfc6-1836-4ed5-a769-a5d63b137171
author: rothja
ms.author: jroth
ms.openlocfilehash: 2b6b23933fde6a09d043c7055b0daa7c07035cdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730226"
---
# <a name="use-full-text-search-with-xml-columns"></a><span data-ttu-id="4e1ee-102">Полнотекстовый поиск в XML-столбцах</span><span class="sxs-lookup"><span data-stu-id="4e1ee-102">Use Full-Text Search with XML Columns</span></span>
  <span data-ttu-id="4e1ee-103">Для XML-столбцов можно создавать полнотекстовые индексы, индексирующие XML-значения, но игнорирующие XML-разметку.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-103">You can create a full-text index on XML columns that indexes the content of the XML values, but ignores the XML markup.</span></span> <span data-ttu-id="4e1ee-104">Теги элементов используются в качестве границ токенов.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-104">Element tags are used as token boundaries.</span></span> <span data-ttu-id="4e1ee-105">Индексируются следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="4e1ee-105">The following items are indexed:</span></span>  
  
-   <span data-ttu-id="4e1ee-106">Содержимое XML-элементов.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-106">The content of XML elements.</span></span>  
  
-   <span data-ttu-id="4e1ee-107">Только содержимое XML-атрибутов элемента на высшем уровне, за исключением случаев, когда эти значения являются числовыми.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-107">The content of XML attributes of the top-level element only, unless those values are numeric values.</span></span>  
  
 <span data-ttu-id="4e1ee-108">Иногда можно совместно пользоваться полнотекстовым поиском и XML-индексом следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-108">When possible, you can combine full-text search with XML index in the following way:</span></span>  
  
1.  <span data-ttu-id="4e1ee-109">Сначала отфильтруйте интересующие XML-значения, используя механизм полнотекстового поиска SQL.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-109">First, filter the XML values of interest by using SQL full-text search.</span></span>  
  
2.  <span data-ttu-id="4e1ee-110">Затем запросите XML-значения, которые используют XML-индекс, связанный с XML-столбцом.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-110">Next, query those XML values that use XML index on the XML column.</span></span>  
  
## <a name="example-combining-full-text-search-with-xml-querying"></a><span data-ttu-id="4e1ee-111">Пример Комбинирование полнотекстового поиска с запросами XML-данных</span><span class="sxs-lookup"><span data-stu-id="4e1ee-111">Example: Combining Full-text Search with XML Querying</span></span>  
 <span data-ttu-id="4e1ee-112">После создания полнотекстового индекса для XML-столбца следующий запрос проверяет, что название книги содержит слово «custom»:</span><span class="sxs-lookup"><span data-stu-id="4e1ee-112">After the full-text index has been created on the XML column, the following query checks that an XML value contains the word "custom" in the title of a book:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'custom')   
AND    xCol.exist('/book/title/text()[contains(.,"custom")]') =1  
```  
  
 <span data-ttu-id="4e1ee-113">В методе **contains()** полнотекстовый индекс используется для выделения всех XML-значений, содержащих слово "custom".</span><span class="sxs-lookup"><span data-stu-id="4e1ee-113">The **contains()** method uses the full-text index to subset the XML values that contain the word "custom" anywhere in the document.</span></span> <span data-ttu-id="4e1ee-114">Предложение **exist()** гарантирует, что это слово входит в название книги.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-114">The **exist()** clause ensures that the word "custom" occurs in the title of a book.</span></span>  
  
 <span data-ttu-id="4e1ee-115">Инструкции полнотекстового поиска, в которых используются методы **contains()** и **contains()** языка XQuery, имеют различную семантику.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-115">A full-text search that uses **contains()** and XQuery **contains()** has different semantics.</span></span> <span data-ttu-id="4e1ee-116">Во втором случае выполняется сопоставление подстрок, а в первом — сопоставление токенов с применением лемматизации.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-116">The latter is a substring match and the former is a token match that uses stemming.</span></span> <span data-ttu-id="4e1ee-117">Таким образом, если искать строку, содержащую в заголовке слово "run", в число найденных вариантов войдут "run", "runs" и "running", потому что они соответствуют требованиям как метода **contains()** механизма полнотекстового поиска, так и метода **contains()** языка XQuery.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-117">Therefore, if the search is for the string that has "run" in the title, the matches will include "run", "runs", and "running", because both the full-text **contains()** and the Xquery **contains()** are satisfied.</span></span> <span data-ttu-id="4e1ee-118">Однако условия нашего запроса не соответствуют слову customizable в заголовке, что вызывает сбой **contains()** , хотя условия метода **contains()** языка XQuery были бы удовлетворены.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-118">However, the query does not match the word "customizable" in the title in that the full-text **contains()** fails, but the Xquery **contains()** is satisfied.</span></span> <span data-ttu-id="4e1ee-119">Как правило, чтобы провести истинное сопоставление подстрок, метод **contains()** механизма полнотекстового поиска использовать не следует.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-119">Generally, for pure substring match, the full-text **contains()** clause should be removed.</span></span>  
  
 <span data-ttu-id="4e1ee-120">Кроме того, при полнотекстовом поиске выполняется лемматизация, а метод **contains()** языка XQuery осуществляет буквальное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-120">Additionally, full-text search uses word stemming, but XQuery **contains()** is a literal match.</span></span> <span data-ttu-id="4e1ee-121">Это различие поясняет следующий пример.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-121">This difference is illustrated in the next example.</span></span>  
  
## <a name="example-full-text-search-on-xml-values-using-stemming"></a><span data-ttu-id="4e1ee-122">Пример Полнотекстовый поиск XML-значений с использованием парадигматического модуля</span><span class="sxs-lookup"><span data-stu-id="4e1ee-122">Example: Full-text Search on XML Values Using Stemming</span></span>  
 <span data-ttu-id="4e1ee-123">Проверку **contains()** языка XQuery, выполненную в предыдущем примере, обычно устранить нельзя.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-123">The XQuery **contains()** check that was performed in the previous example generally cannot be eliminated.</span></span> <span data-ttu-id="4e1ee-124">Рассмотрим следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="4e1ee-124">Consider this query:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'run')   
```  
  
 <span data-ttu-id="4e1ee-125">Слово «run» в документе соответствует условию поиска, потому что при этом осуществляется лемматизация.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-125">The word "ran" in the document matches the search condition because of stemming.</span></span> <span data-ttu-id="4e1ee-126">Кроме того, при использовании XQuery не проверяется контекст поиска.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-126">Additionally, the search context is not checked by using XQuery.</span></span>  
  
 <span data-ttu-id="4e1ee-127">Если при помощи схем XML-данные распределены по реляционным столбцам, для которых выполнено полнотекстовое индексирование, при обработке запросов XPath, адресованных XML-представлению, полнотекстовый поиск в базовых таблицах не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4e1ee-127">When XML is decomposed into relational columns by using AXSD that are full-text indexed, XPath queries that occur over the XML view do not perform full-text search on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e1ee-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e1ee-128">See Also</span></span>  
 [<span data-ttu-id="4e1ee-129">XML-индексы (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e1ee-129">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
