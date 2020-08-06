---
title: Создание XML-индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- indexes [XML in SQL Server]
- XML indexes [SQL Server], creating
ms.assetid: 6ecac598-355d-4408-baf7-1b2e8d4cf7c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9e7800193222b8c9060fee1b247cc5585654cde4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738060"
---
# <a name="create-xml-indexes"></a><span data-ttu-id="19e73-102">Создание XML-индексов</span><span class="sxs-lookup"><span data-stu-id="19e73-102">Create XML Indexes</span></span>
  <span data-ttu-id="19e73-103">В данном разделе описано создание первичных и вторичных XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="19e73-103">This topic describes how to create primary and secondary XML indexes.</span></span>  
  
## <a name="creating-a-primary-xml-index"></a><span data-ttu-id="19e73-104">Создание первичного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="19e73-104">Creating a Primary XML Index</span></span>  
 <span data-ttu-id="19e73-105">Для создания первичного XML-индекса используется DDL-инструкция [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19e73-105">To create a primary XML index, use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement.</span></span> <span data-ttu-id="19e73-106">Для XML-индексов поддерживаются не все параметры, доступные для обычных индексов.</span><span class="sxs-lookup"><span data-stu-id="19e73-106">Not all options available for non-XML indexes are supported on XML indexes.</span></span>  
  
 <span data-ttu-id="19e73-107">При создании XML-индекса следует учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="19e73-107">Note the following when you are creating an XML index:</span></span>  
  
-   <span data-ttu-id="19e73-108">Для создания первичного XML-индекса таблица, содержащая индексируемый XML-столбец и называемая базовой таблицей, должна иметь кластеризованный индекс первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="19e73-108">To create a primary XML index, the table that contains the XML column being indexed, called the base table, must have a clustered index on the primary key.</span></span> <span data-ttu-id="19e73-109">Это гарантирует, что в случае секционирования базовой таблицы первичный XML-индекс может быть секционирован при использовании той же схемы и той же функции секционирования.</span><span class="sxs-lookup"><span data-stu-id="19e73-109">This makes sure that if the base table is partitioned, the primary XML index can be partitioned by using the same partitioning scheme and partitioning function.</span></span>  
  
-   <span data-ttu-id="19e73-110">Если XML-индекс уже существует, кластеризованный первичный ключ таблицы не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="19e73-110">If an XML index exists, the clustered, primary key of the table cannot be modified.</span></span> <span data-ttu-id="19e73-111">Перед изменением первичного ключа необходимо удалить все XML-индексы, созданные для таблицы.</span><span class="sxs-lookup"><span data-stu-id="19e73-111">You will have to drop all XML indexes on the table before modifying the primary key.</span></span>  
  
-   <span data-ttu-id="19e73-112">Первичный XML-индекс можно создать только для столбца типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="19e73-112">A primary XML index can be created on a single `xml` type column.</span></span> <span data-ttu-id="19e73-113">Никакой другой тип индекса, в котором столбец типа данных XML является ключевым, создать нельзя.</span><span class="sxs-lookup"><span data-stu-id="19e73-113">You cannot create any other type of index with the XML type column as a key column.</span></span> <span data-ttu-id="19e73-114">Однако столбец типа `xml` может быть включен в обычный (не XML) индекс.</span><span class="sxs-lookup"><span data-stu-id="19e73-114">However, you can include the `xml` L type column in a non-XML index.</span></span> <span data-ttu-id="19e73-115">Каждый столбец типа `xml` в таблице может иметь собственный первичный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="19e73-115">Each `xml` type column in a table can have its own primary XML index.</span></span> <span data-ttu-id="19e73-116">Однако для столбца типа `xml` допустим только один первичный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="19e73-116">However, only one primary XML index per `xml` type column is permitted.</span></span>  
  
-   <span data-ttu-id="19e73-117">XML-индексы существуют в том же пространстве имен, что и обычные индексы.</span><span class="sxs-lookup"><span data-stu-id="19e73-117">XML indexes exist in the same namespace as non-XML indexes.</span></span> <span data-ttu-id="19e73-118">Поэтому для таблицы не могут быть определены обычный и XML-индекс с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="19e73-118">Therefore, you cannot have an XML index and a non-XML index on the same table with the same name.</span></span>  
  
-   <span data-ttu-id="19e73-119">Параметры IGNORE_DUP_KEY и ONLINE для XML-индексов всегда должны устанавливаться в OFF.</span><span class="sxs-lookup"><span data-stu-id="19e73-119">IGNORE_DUP_KEY and ONLINE options of are always set to OFF for XML indexes.</span></span> <span data-ttu-id="19e73-120">Можно указывать эти параметры со значением OFF.</span><span class="sxs-lookup"><span data-stu-id="19e73-120">You can specify these options with a value of OFF.</span></span>  
  
-   <span data-ttu-id="19e73-121">Сведения о файловых группах и секционировании пользовательской таблицы применимы к XML-индексам.</span><span class="sxs-lookup"><span data-stu-id="19e73-121">The filegroup or partitioning information of the user table is applied to the XML index.</span></span> <span data-ttu-id="19e73-122">Однако пользователи не могут задавать их для XML-индекса отдельно.</span><span class="sxs-lookup"><span data-stu-id="19e73-122">Users cannot specify these separately on an XML index.</span></span>  
  
-   <span data-ttu-id="19e73-123">Параметр DROP_EXISTING может использоваться для удаления и создания нового первичного XML-индекса или для удаления и создания нового вторичного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="19e73-123">The DROP_EXISTING index option can drop a primary XML index and create a new primary XML index, or drop a secondary XML index and create a new secondary XML index.</span></span> <span data-ttu-id="19e73-124">Однако нельзя удалить вторичный XML-индекс для создания первичного, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="19e73-124">However, this option cannot drop a secondary XML index to create a new primary XML index or vice versa.</span></span>  
  
-   <span data-ttu-id="19e73-125">На имена первичных XML-индексов накладываются те же ограничения, что и на имена представлений.</span><span class="sxs-lookup"><span data-stu-id="19e73-125">Primary XML index names have the same restrictions as view names.</span></span>  
  
 <span data-ttu-id="19e73-126">Нельзя создать XML-индекс для `xml` столбца типа в представлении, на переменную с **табличным** значением со `xml` столбцами типа или `xml` переменные типа.</span><span class="sxs-lookup"><span data-stu-id="19e73-126">You cannot create an XML index on an `xml` type column in a view, on a **table** valued variable with `xml` type columns, or `xml` type variables.</span></span>  
  
-   <span data-ttu-id="19e73-127">Для изменения столбца типа `xml` с помощью параметра ALTER TABLE ALTER COLUMN с нетипизированного на типизированный XML (или наоборот) для этого столбца не должно быть определено никаких XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="19e73-127">To change an `xml` type column from untyped to typed XML, or vice versa, by using the ALTER TABLE ALTER COLUMN option, no XML index on the column should exist.</span></span> <span data-ttu-id="19e73-128">Если такой индекс существует, он должен быть сначала удален.</span><span class="sxs-lookup"><span data-stu-id="19e73-128">If one does exist, it must be dropped before the column type change is tried.</span></span>  
  
-   <span data-ttu-id="19e73-129">При создании XML-индекса параметр ARITHABORT должен быть установлен в значение ON.</span><span class="sxs-lookup"><span data-stu-id="19e73-129">The option ARITHABORT must be set to ON when an XML index is created.</span></span> <span data-ttu-id="19e73-130">Для запроса, вставки, удаления или обновления значений в столбце XML методами типа данных XML этот параметр должен быть установлен для соединения.</span><span class="sxs-lookup"><span data-stu-id="19e73-130">To query, insert, delete, or update values in the XML column using XML data type methods, the same option must be set on the connection.</span></span> <span data-ttu-id="19e73-131">В противном случае методы типа данных XML будут завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="19e73-131">If it is not, the XML data type methods will fail.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19e73-132">Сведения об XML-индексе доступны через представления каталога,</span><span class="sxs-lookup"><span data-stu-id="19e73-132">Information about an XML index can be found in catalog views.</span></span> <span data-ttu-id="19e73-133">но процедура **sp_helpindex** для них не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="19e73-133">However, **sp_helpindex** is not supported.</span></span> <span data-ttu-id="19e73-134">Ниже в этом подразделе содержатся примеры, которые демонстрируют, какие следует выполнить запросы к представлениям каталога, чтобы получить сведения об XML-индексе.</span><span class="sxs-lookup"><span data-stu-id="19e73-134">Examples provided later in this topic show how to query the catalog views to find XML index information.</span></span>  
  
 <span data-ttu-id="19e73-135">При создании или повторном создании первичного XML-индекса на столбце с типом данных XML, в котором содержатся схемы XML типов **xs:date** или **xs:dateTime** (либо любых подтипов данных типов) со значением года меньше 1, создание индекса завершается ошибкой в [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="19e73-135">When creating or recreating a primary XML index on an XML data type column that contains values of the XML Schema types **xs:date** or **xs:dateTime** (or any subtypes of these types) that have a year of less than 1, the index creation will fail in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="19e73-136">эти значения допускались, поэтому данная проблема может возникнуть при создании индексов в базе данных, сформированной в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19e73-136">allowed these values, so this problem can occur when creating indexes in a database generated in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="19e73-137">Дополнительные сведения см. в статье [Сравнение типизированного и нетипизированного XML](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="19e73-137">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
### <a name="example-creating-a-primary-xml-index"></a><span data-ttu-id="19e73-138">Пример Создание первичного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="19e73-138">Example: Creating a Primary XML Index</span></span>  
 <span data-ttu-id="19e73-139">В большинстве наших примеров используется таблица T (pk INT PRIMARY KEY, xCol XML) с нетипизированным XML-столбцом.</span><span class="sxs-lookup"><span data-stu-id="19e73-139">Table T (pk INT PRIMARY KEY, xCol XML) with an untyped XML column is used in most of the examples.</span></span> <span data-ttu-id="19e73-140">Эти примеры можно легко расширить на типизированный XML.</span><span class="sxs-lookup"><span data-stu-id="19e73-140">These can be extended to typed XML in a straightforward way.</span></span> <span data-ttu-id="19e73-141">Ради простоты запросы XML-данных описываются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="19e73-141">For simplicity, queries are described for XML data instances as shown in the following:</span></span>  
  
```  
<book genre="security" publicationdate="2002" ISBN="0-7356-1588-2">  
   <title>Writing Secure Code</title>  
   <author>  
      <first-name>Michael</first-name>  
      <last-name>Howard</last-name>  
   </author>  
   <author>  
      <first-name>David</first-name>  
      <last-name>LeBlanc</last-name>  
   </author>  
   <price>39.99</price>  
</book>  
```  
  
 <span data-ttu-id="19e73-142">Следующая инструкция создает для XML-столбца xCol таблицы T XML-индекс с именем idx_xCol.</span><span class="sxs-lookup"><span data-stu-id="19e73-142">The following statement creates an XML index, called idx_xCol, on the XML column xCol of table T:</span></span>  
  
```  
CREATE PRIMARY XML INDEX idx_xCol on T (xCol)  
```  
  
## <a name="creating-a-secondary-xml-index"></a><span data-ttu-id="19e73-143">Создание вторичного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="19e73-143">Creating a Secondary XML Index</span></span>  
 <span data-ttu-id="19e73-144">DDL-инструкция [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] позволяет создавать вторичные XML-индексы и указывать их тип.</span><span class="sxs-lookup"><span data-stu-id="19e73-144">Use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement to create secondary XML indexes and specify the type of the secondary XML index that you want.</span></span>  
  
 <span data-ttu-id="19e73-145">При создании вторичных XML-индексов следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="19e73-145">Note the following when you are creating secondary XML indexes:</span></span>  
  
-   <span data-ttu-id="19e73-146">Для вторичных XML-индексов допустимы все параметры, применимые к некластеризованным индексам, за исключением параметров IGNORE_DUP_KEY и ONLINE.</span><span class="sxs-lookup"><span data-stu-id="19e73-146">All indexing options that apply to a nonclustered index, except IGNORE_DUP_KEY and ONLINE, are permitted on secondary XML indexes.</span></span> <span data-ttu-id="19e73-147">Для вторичных XML-индексов эти два параметра должны всегда устанавливаться в OFF.</span><span class="sxs-lookup"><span data-stu-id="19e73-147">The two options must always be set to OFF for secondary XML indexes.</span></span>  
  
-   <span data-ttu-id="19e73-148">Вторичные индексы секционируются так же, как и первичный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="19e73-148">The secondary indexes are partitioned just like the primary XML index.</span></span>  
  
-   <span data-ttu-id="19e73-149">Параметр DROP_EXISTING позволяет удалить вторичный индекс для пользовательской таблицы и создать другой вторичный индекс для той же таблицы.</span><span class="sxs-lookup"><span data-stu-id="19e73-149">DROP_EXISTING can drop a secondary index on the user table and create another secondary index on the user table.</span></span>  
  
 <span data-ttu-id="19e73-150">Для получения сведений об XML-индексе можно выполнить запрос к представлению каталога **sys.xml_indexes** .</span><span class="sxs-lookup"><span data-stu-id="19e73-150">You can query the **sys.xml_indexes** catalog view to retrieve XML index information.</span></span> <span data-ttu-id="19e73-151">Обратите внимание, что столбец **secondary_type_desc** в представлении каталога **sys.xml_indexes** указывает тип вторичного индекса:</span><span class="sxs-lookup"><span data-stu-id="19e73-151">Note that the **secondary_type_desc** column in the **sys.xml_indexes** catalog view provides the type of secondary index:</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="19e73-152">Столбец **secondary_type_desc** может возвращать значения NULL, PATH, VALUE или PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="19e73-152">The values returned in the **secondary_type_desc** column can be NULL, PATH, VALUE, or PROPERTY.</span></span> <span data-ttu-id="19e73-153">Для первичного XML-индекса всегда возвращается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="19e73-153">For the primary XML index, the value returned is NULL.</span></span>  
  
### <a name="example-creating-secondary-xml-indexes"></a><span data-ttu-id="19e73-154">Пример создание вторичных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="19e73-154">Example: Creating Secondary XML Indexes</span></span>  
 <span data-ttu-id="19e73-155">В следующем примере иллюстрируется создание вторичных XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="19e73-155">The following example illustrates how secondary XML indexes are created.</span></span> <span data-ttu-id="19e73-156">Здесь также выводятся сведения о созданных XML-индексах.</span><span class="sxs-lookup"><span data-stu-id="19e73-156">The example also shows information about the XML indexes that you created.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML);  
GO  
-- Create primary index.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol);  
GO  
-- Create secondary indexes (PATH, VALUE, PROPERTY).  
CREATE XML INDEX PIdx_T_XmlCol_PATH ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PATH;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_VALUE ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR VALUE;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_PROPERTY ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PROPERTY;  
GO  
```  
  
 <span data-ttu-id="19e73-157">Для получения сведений об XML-индексах можно выполнить запрос к представлению каталога `sys.xml_indexes` .</span><span class="sxs-lookup"><span data-stu-id="19e73-157">You can query the `sys.xml_indexes` to retrieve XML indexes information.</span></span> <span data-ttu-id="19e73-158">Столбец `secondary_type_desc` содержит тип вторичного индекса.</span><span class="sxs-lookup"><span data-stu-id="19e73-158">The `secondary_type_desc` column provides the secondary index type.</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="19e73-159">Для получения сведений об индексе можно также выполнить запрос к представлению каталога:</span><span class="sxs-lookup"><span data-stu-id="19e73-159">You can also query the catalog view for index information.</span></span>  
  
```  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T');  
```  
  
 <span data-ttu-id="19e73-160">Можно добавить какие-либо данные, а затем просмотреть сведения об XML-индексе.</span><span class="sxs-lookup"><span data-stu-id="19e73-160">You can add sample data and then review the XML index information.</span></span>  
  
```  
INSERT INTO T VALUES (1,  
'<doc id="123">  
<sections>  
<section num="2">  
<heading>Background</heading>  
</section>  
<section num="3">  
<heading>Sort</heading>  
</section>  
<section num="4">  
<heading>Search</heading>  
</section>  
</sections>  
</doc>');  
GO  
-- Check XML index information.  
SELECT *  
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, NULL, 'DETAILED');  
GO  
-- Space usage of primary XML index  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id  
FROM    sys.xml_indexes i   
WHERE   i.name = 'PIdx_T_XmlCol' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
--- Space usage of secondary XML index (for example PATH secondary index)  PIdx_T_XmlCol_PATH  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id   
FROM    sys.xml_indexes i   
WHERE  i.name = 'PIdx_T_XmlCol_PATH' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
  
-- Space usage of all secondary XML indexes for a particular table  
SELECT i.name, object_name(i.object_id), stats.*   
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, DEFAULT, 'DETAILED') stats  
JOIN sys.xml_indexes i ON (stats.object_id = i.object_id and stats.index_id = i.index_id)  
WHERE secondary_type is not null;  
-- Drop secondary indexes.  
DROP INDEX PIdx_T_XmlCol_PATH ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_VALUE ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_PROPERTY ON T;  
GO  
-- Drop primary index.  
DROP INDEX PIdx_T_XmlCol ON T;  
-- Drop table T.  
DROP TABLE T;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="19e73-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="19e73-161">See Also</span></span>  
 <span data-ttu-id="19e73-162">[XML-индексы (SQL Server)](xml-indexes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="19e73-162">[XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span></span>  
 [<span data-ttu-id="19e73-163">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="19e73-163">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
