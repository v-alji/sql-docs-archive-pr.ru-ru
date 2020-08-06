---
title: Удаление XML-индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- dropping indexes
- XML indexes [SQL Server], dropping
ms.assetid: 7591ebea-34af-4925-8553-b2adb5b487c2
author: rothja
ms.author: jroth
ms.openlocfilehash: b7d4621cf2182b4587b12665a1cfe10ddbe0db3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654946"
---
# <a name="drop-xml-indexes"></a><span data-ttu-id="ca757-102">Удаление XML-индексов</span><span class="sxs-lookup"><span data-stu-id="ca757-102">Drop XML Indexes</span></span>
  <span data-ttu-id="ca757-103">Инструкция [DROP INDEX (Transact-SQL)](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] позволяет удалить существующие первичные и вторичные XML-индексы и индексы других типов.</span><span class="sxs-lookup"><span data-stu-id="ca757-103">The [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be used to drop existing primary or secondary XML and non-XML indexes.</span></span> <span data-ttu-id="ca757-104">Однако к XML-индексам не применяется ни один из параметров DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="ca757-104">However, no options of DROP INDEX apply to XML indexes.</span></span> <span data-ttu-id="ca757-105">Если удаляется первичный XML-индекс, то вместе с ним удаляются также и все имеющиеся вторичные индексы.</span><span class="sxs-lookup"><span data-stu-id="ca757-105">If you drop the primary XML index, any secondary indexes that are present are also deleted.</span></span>  
  
 <span data-ttu-id="ca757-106">Синтаксис инструкции DROP для *TableName.IndexName* постепенно вытесняется и для XML-индексов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ca757-106">The DROP syntax with *TableName.IndexName* is being phased out and is not supported for XML indexes.</span></span>  
  
## <a name="example-creating-and-dropping-a-primary-xml-index"></a><span data-ttu-id="ca757-107">Пример Создание и удаление первичного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="ca757-107">Example: Creating and Dropping a Primary XML Index</span></span>  
 <span data-ttu-id="ca757-108">В следующем примере создается XML-индекс для столбца типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="ca757-108">In the following example, an XML index is created on an `xml` type column.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create Primary XML index   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Verify the index creation.   
-- Note index type is 3 for xml indexes.  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'   
-- Drop the index.  
DROP INDEX PIdx_T_XmlCol ON T  
```  
  
 <span data-ttu-id="ca757-109">При удалении таблицы автоматически удаляются все созданные для нее XML-индексы.</span><span class="sxs-lookup"><span data-stu-id="ca757-109">When a table is dropped, all the XML indexes on it are also automatically dropped.</span></span> <span data-ttu-id="ca757-110">Однако столбец XML не может быть удален из таблицы, если для него существует XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="ca757-110">However, an XML column cannot be dropped from a table if an XML index exists on the column.</span></span>  
  
 <span data-ttu-id="ca757-111">В следующем примере создается XML-индекс для столбца типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="ca757-111">In the following example, an XML index is created on an `xml` type column.</span></span> <span data-ttu-id="ca757-112">Дополнительные сведения см. в статье [Сравнение типизированного и нетипизированного XML](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ca757-112">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
```  
CREATE TABLE TestTable(  
 Col1 int primary key,   
 Col2 xml (Production.ProductDescriptionSchemaCollection))   
GO  
```  
  
 <span data-ttu-id="ca757-113">Теперь можно создать первичный XML-индекс для столбца `Co12`.</span><span class="sxs-lookup"><span data-stu-id="ca757-113">Now, you can create a primary XML index on `Co12`.</span></span>  
  
```  
CREATE PRIMARY XML INDEX PIdx_TestTable_Col2   
ON TestTable(Col2)  
GO  
```  
  
## <a name="example-creating-an-xml-index-by-using-the-drop_existing-index-option"></a><span data-ttu-id="ca757-114">Пример Создание XML-индекса с помощью параметра DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="ca757-114">Example: Creating an XML Index by Using the DROP_EXISTING Index Option</span></span>  
 <span data-ttu-id="ca757-115">В следующем примере XML-индекс создается для столбца`XmlColx`.</span><span class="sxs-lookup"><span data-stu-id="ca757-115">In the following example, an XML index is created on a column (`XmlColx`).</span></span> <span data-ttu-id="ca757-116">Затем для другого столбца (`XmlColy`) создается другой XML-индекс с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="ca757-116">Then, another XML index with the same name is created on a different column, (`XmlColy`).</span></span> <span data-ttu-id="ca757-117">Так как задан параметр `DROP_EXISTING` , существующий XML-индекс для столбца (`XmlColx)` ) удаляется и вместо него создается новый XML-индекс для столбца (`XmlColy`).</span><span class="sxs-lookup"><span data-stu-id="ca757-117">Because the `DROP_EXISTING` option is specified, the existing XML index on (`XmlColx)` is dropped and a new XML index on (`XmlColy`) is created.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T(Col1 int primary key, XmlColx xml, XmlColy xml)  
GO  
-- Create XML index on XmlColx.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColx)  
GO  
-- Create same name XML index on XmlColy.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColy)   
WITH (DROP_EXISTING = ON)  
-- Verify the index is created on XmlColy.d.  
SELECT sc.name   
FROM   sys.xml_indexes si inner join sys.index_columns sic   
ON     sic.object_id=si.object_id and sic.index_id=si.index_id  
INNER  join sys.columns sc on sc.object_id=sic.object_id   
AND    sc.column_id=sic.column_id  
WHERE  si.name='PIdx_T_XmlCol'   
AND    si.object_id=object_id('T')  
```  
  
 <span data-ttu-id="ca757-118">Запрос возвращает имя столбца, для которого создан XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="ca757-118">This query returns the column name on which the specified XML index is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca757-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca757-119">See Also</span></span>  
 [<span data-ttu-id="ca757-120">XML-индексы (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ca757-120">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
