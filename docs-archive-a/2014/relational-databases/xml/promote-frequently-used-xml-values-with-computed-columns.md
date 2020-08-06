---
title: Продвижение часто используемых значений XML с помощью вычисляемых столбцов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- promoting properties [XML in SQL Server]
- property promotion [XML in SQL Server]
ms.assetid: f5111896-c2fd-4209-b500-f2baa45489ad
author: rothja
ms.author: jroth
ms.openlocfilehash: bfb83b7772ffd92eab7087db11e4c3ffd96afa47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733670"
---
# <a name="promote-frequently-used-xml-values-with-computed-columns"></a><span data-ttu-id="18b79-102">Продвижение часто используемых XML-значений с помощью вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="18b79-102">Promote Frequently Used XML Values with Computed Columns</span></span>
  <span data-ttu-id="18b79-103">Если часто запрашивается небольшое количество значений элементов и атрибутов, можно выполнить их продвижение до реляционных столбцов.</span><span class="sxs-lookup"><span data-stu-id="18b79-103">If queries are made principally on a small number of element and attribute values, you may want to promote those quantities into relational columns.</span></span> <span data-ttu-id="18b79-104">Это полезно, если запрос выполняется для небольшой части XML-данных, тогда как извлекается весь экземпляр XML.</span><span class="sxs-lookup"><span data-stu-id="18b79-104">This is helpful when queries are issued on a small part of the XML data while the whole XML instance is retrieved.</span></span> <span data-ttu-id="18b79-105">Создавать XML-индекс для XML-столбца не требуется.</span><span class="sxs-lookup"><span data-stu-id="18b79-105">Creating an XML index on the XML column is not required.</span></span> <span data-ttu-id="18b79-106">Вместо этого можно проиндексировать столбец, созданный на основе свойства.</span><span class="sxs-lookup"><span data-stu-id="18b79-106">Instead, the promoted column can be indexed.</span></span> <span data-ttu-id="18b79-107">В запросах необходимо использовать этот столбец,</span><span class="sxs-lookup"><span data-stu-id="18b79-107">Queries must be written to use the promoted column.</span></span> <span data-ttu-id="18b79-108">потому что оптимизатор запросов не перенаправляет запросы XML-столбца столбцу, созданному на основе свойства.</span><span class="sxs-lookup"><span data-stu-id="18b79-108">That is, the query optimizer does not target again the queries on the XML column to the promoted column.</span></span>  
  
 <span data-ttu-id="18b79-109">Столбец, созданный на основе свойства, может быть вычисляемым столбцом в той же таблице или отдельным пользовательским столбцом таблицы.</span><span class="sxs-lookup"><span data-stu-id="18b79-109">The promoted column can be a computed column in the same table or it can be a separate, user-maintained column in a table.</span></span> <span data-ttu-id="18b79-110">Если для каждого экземпляра XML выполняется продвижение одинарных значений, этого достаточно.</span><span class="sxs-lookup"><span data-stu-id="18b79-110">This is sufficient when singleton values are promoted from each XML instance.</span></span> <span data-ttu-id="18b79-111">Однако в случае многозначных свойств необходимо создать для свойства отдельную таблицу. Это описывается в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="18b79-111">However, for multi-valued properties, you have to create a separate table for the property, as described in the following section.</span></span>  
  
## <a name="computed-column-based-on-the-xml-data-type"></a><span data-ttu-id="18b79-112">Вычисляемый столбец, основанный на типе данных xml</span><span class="sxs-lookup"><span data-stu-id="18b79-112">Computed Column Based on the xml Data Type</span></span>  
 <span data-ttu-id="18b79-113">Вычисляемый столбец можно создать с помощью определяемой пользователем функции, которая вызывает `xml` методы типа данных.</span><span class="sxs-lookup"><span data-stu-id="18b79-113">A computed column can be created by using a user-defined function that invokes `xml` data type methods.</span></span> <span data-ttu-id="18b79-114">Вычисляемый столбец может иметь любой тип SQL, в том числе XML.</span><span class="sxs-lookup"><span data-stu-id="18b79-114">The type of the computed column can be any SQL type, including XML.</span></span> <span data-ttu-id="18b79-115">Это продемонстрировано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="18b79-115">This is illustrated in the following example.</span></span>  
  
### <a name="example-computed-column-based-on-the-xml-data-type-method"></a><span data-ttu-id="18b79-116">Пример Вычисляемый столбец, основанный на методе типа данных xml</span><span class="sxs-lookup"><span data-stu-id="18b79-116">Example: Computed Column Based on the xml Data Type Method</span></span>  
 <span data-ttu-id="18b79-117">Создание пользовательской функции, возвращающей ISBN-номер книги:</span><span class="sxs-lookup"><span data-stu-id="18b79-117">Create the user-defined function for a book ISBN number:</span></span>  
  
```  
CREATE FUNCTION udf_get_book_ISBN (@xData xml)  
RETURNS varchar(20)  
BEGIN  
   DECLARE @ISBN   varchar(20)  
   SELECT @ISBN = @xData.value('/book[1]/@ISBN', 'varchar(20)')  
   RETURN @ISBN   
END  
```  
  
 <span data-ttu-id="18b79-118">Добавление в таблицу вычисляемого столбца для хранения значений ISBN:</span><span class="sxs-lookup"><span data-stu-id="18b79-118">Add a computed column to the table for the ISBN:</span></span>  
  
```  
ALTER TABLE      T  
ADD   ISBN AS dbo.udf_get_book_ISBN(xCol)  
```  
  
 <span data-ttu-id="18b79-119">Теперь вычисляемый столбец можно проиндексировать обычным способом.</span><span class="sxs-lookup"><span data-stu-id="18b79-119">The computed column can be indexed in the usual way.</span></span>  
  
### <a name="example-queries-on-a-computed-column-based-on-xml-data-type-methods"></a><span data-ttu-id="18b79-120">Пример Запросы данных из вычисляемого столбца на основе методов типа данных xml</span><span class="sxs-lookup"><span data-stu-id="18b79-120">Example: Queries on a Computed Column Based on xml Data Type Methods</span></span>  
 <span data-ttu-id="18b79-121">Чтобы получить элемент <`book`> с ISBN-номером 0-7356-1588-2, можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="18b79-121">To obtain the <`book`> whose ISBN is 0-7356-1588-2:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  xCol.exist('/book/@ISBN[. = "0-7356-1588-2"]') = 1  
```  
  
 <span data-ttu-id="18b79-122">Запрос данных из XML-столбца можно переписать так, чтобы в нем использовался вычисляемый столбец:</span><span class="sxs-lookup"><span data-stu-id="18b79-122">The query on the XML column can be rewritten to use the computed column as follows:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  ISBN = '0-7356-1588-2'  
```  
  
 <span data-ttu-id="18b79-123">Можно создать определяемую пользователем функцию для возврата `xml` типа данных и вычисляемого столбца с помощью определяемой пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="18b79-123">You can create a user-defined function to return the `xml` data type and a computed column by using the user-defined function.</span></span> <span data-ttu-id="18b79-124">Однако создать XML-индекс для вычисляемого XML-столбца нельзя.</span><span class="sxs-lookup"><span data-stu-id="18b79-124">However, you cannot create an XML index on the computed, XML column.</span></span>  
  
## <a name="creating-property-tables"></a><span data-ttu-id="18b79-125">Создание таблиц свойств</span><span class="sxs-lookup"><span data-stu-id="18b79-125">Creating Property Tables</span></span>  
 <span data-ttu-id="18b79-126">Иногда целесообразно выполнить продвижение некоторых многозначных свойств XML-данных до одной или нескольких таблиц, создать индексы для этих таблиц и перенаправить запросы к этим таблицам.</span><span class="sxs-lookup"><span data-stu-id="18b79-126">You may want to promote some of the multivalued properties from your XML data into one or more tables, create indexes on those tables, and target again your queries to use them.</span></span> <span data-ttu-id="18b79-127">Типичная ситуация, когда это полезно, имеет место тогда, когда в большинстве запросов обращение происходит к небольшому числу свойств.</span><span class="sxs-lookup"><span data-stu-id="18b79-127">A typical scenario is one in which a small number of properties covers most of your query workload.</span></span> <span data-ttu-id="18b79-128">Можно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="18b79-128">You can do the following:</span></span>  
  
-   <span data-ttu-id="18b79-129">Создать одну или несколько таблиц для хранения многозначных свойств.</span><span class="sxs-lookup"><span data-stu-id="18b79-129">Create one or more tables to hold the multivalued properties.</span></span> <span data-ttu-id="18b79-130">Иногда удобно хранить одно свойство в каждой таблице и продублировать первичный ключ базовой таблицы в таблицах свойств для их соединения с базовой таблицей.</span><span class="sxs-lookup"><span data-stu-id="18b79-130">You may find it convenient to store one property per table and duplicate the primary key of the base table in the property tables for back joining with the base table.</span></span>  
  
-   <span data-ttu-id="18b79-131">Если требуется сохранить относительный порядок свойств, для этого нужно создать отдельный столбец.</span><span class="sxs-lookup"><span data-stu-id="18b79-131">If you want to maintain the relative order of the properties, you have to introduce a separate column for the relative order.</span></span>  
  
-   <span data-ttu-id="18b79-132">Создать триггеры для XML-столбца с целью обслуживания таблиц свойств.</span><span class="sxs-lookup"><span data-stu-id="18b79-132">Create triggers on the XML column to maintain the property tables.</span></span> <span data-ttu-id="18b79-133">В триггерах сделайте что-либо одно из следующего перечисленного ниже.</span><span class="sxs-lookup"><span data-stu-id="18b79-133">Within the triggers, do one of the following:</span></span>  
  
    -   <span data-ttu-id="18b79-134">`xml`Для вставки и удаления строк таблиц свойств используются методы типа данных, такие как **nodes ()** и **value ()**.</span><span class="sxs-lookup"><span data-stu-id="18b79-134">Use `xml` data type methods, such as **nodes()** and **value()**, to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="18b79-135">Создайте в среде CLR потоковые возвращающие табличное значение функции для вставки строк в таблицы свойств и их удаления.</span><span class="sxs-lookup"><span data-stu-id="18b79-135">Create streaming table-valued functions in the common language runtime (CLR) to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="18b79-136">Напишите запросы, осуществляющие основанный на SQL доступ к таблицам свойств и основанный на XML доступ к XML-столбцу базовой таблицы, соединяя таблицы с использованием их первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="18b79-136">Write queries for SQL access to the property tables and for XML access to the XML column in the base table, with joins between the tables by using their primary key.</span></span>  
  
### <a name="example-create-a-property-table"></a><span data-ttu-id="18b79-137">Пример Создание таблицы свойств</span><span class="sxs-lookup"><span data-stu-id="18b79-137">Example: Create a Property Table</span></span>  
 <span data-ttu-id="18b79-138">Предположим, что требуется выполнить продвижение свойства, представляющего имена авторов.</span><span class="sxs-lookup"><span data-stu-id="18b79-138">For illustration, assume that you want to promote the first name of the authors.</span></span> <span data-ttu-id="18b79-139">У книги может быть несколько авторов, поэтому данное свойство является многозначным.</span><span class="sxs-lookup"><span data-stu-id="18b79-139">Books have one or more authors, so that first name is a multivalued property.</span></span> <span data-ttu-id="18b79-140">Каждое имя хранится в отдельной строке таблицы свойств.</span><span class="sxs-lookup"><span data-stu-id="18b79-140">Each first name is stored in a separate row of a property table.</span></span> <span data-ttu-id="18b79-141">Первичный ключ базовой таблицы дублируется в таблице свойств ради обратного соединения таблиц.</span><span class="sxs-lookup"><span data-stu-id="18b79-141">The primary key of the base table is duplicated in the property table for back join.</span></span>  
  
```  
create table tblPropAuthor (propPK int, propAuthor varchar(max))  
```  
  
### <a name="example-create-a-user-defined-function-to-generate-a-rowset-from-an-xml-instance"></a><span data-ttu-id="18b79-142">Пример Создание пользовательской функции для создания набора строк на основе экземпляра XML</span><span class="sxs-lookup"><span data-stu-id="18b79-142">Example: Create a User-defined Function to Generate a Rowset from an XML Instance</span></span>  
 <span data-ttu-id="18b79-143">Следующая возвращающая табличное значение функция, udf_XML2Table, принимает значение первичного ключа и экземпляр XML.</span><span class="sxs-lookup"><span data-stu-id="18b79-143">The following table-valued function, udf_XML2Table, accepts a primary key value and an XML instance.</span></span> <span data-ttu-id="18b79-144">Она извлекает имена всех авторов из элемента <`book`> и возвращает набор строк, состоящий из пар (первичный ключ / имя).</span><span class="sxs-lookup"><span data-stu-id="18b79-144">It retrieves the first name of all authors of the <`book`> elements and returns a rowset of primary key, first name pairs.</span></span>  
  
```  
create function udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (propPK int, propAuthor varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
      select @pk, nref.value('.', 'varchar(max)')  
      from   @xCol.nodes('/book/author/first-name') R(nref)  
      return  
end  
```  
  
### <a name="example-create-triggers-to-populate-a-property-table"></a><span data-ttu-id="18b79-145">Пример Создание триггеров для заполнения таблицы свойств</span><span class="sxs-lookup"><span data-stu-id="18b79-145">Example: Create Triggers to Populate a Property Table</span></span>  
 <span data-ttu-id="18b79-146">Триггер вставки вставляет строки в таблицу свойств:</span><span class="sxs-lookup"><span data-stu-id="18b79-146">The insert trigger inserts rows into the property table:</span></span>  
  
```  
create trigger trg_docs_INS on T for insert  
as  
      declare @wantedXML xml  
      declare @FK int  
      select @wantedXML = xCol from inserted  
      select @FK = PK from inserted  
  
   insert into tblPropAuthor  
   select * from dbo.udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="18b79-147">Триггер удаления удаляет строки из таблицы свойств на основе значения первичного ключа:</span><span class="sxs-lookup"><span data-stu-id="18b79-147">The delete trigger deletes the rows from the property table based on the primary key value of the deleted rows:</span></span>  
  
```  
create trigger trg_docs_DEL on T for delete  
as  
   declare @FK int  
   select @FK = PK from deleted  
   delete tblPropAuthor where propPK = @FK  
```  
  
 <span data-ttu-id="18b79-148">Триггер обновления удаляет строки из таблицы свойств в соответствии с обновленным экземпляром XML и вставляет в таблицу свойств новые строки:</span><span class="sxs-lookup"><span data-stu-id="18b79-148">The update trigger deletes the existing rows in the property table corresponding to the updated XML instance and inserts new rows into the property table:</span></span>  
  
```  
create trigger trg_docs_UPD  
on T  
for update  
as  
if update(xCol) or update(pk)  
begin  
      declare @FK int  
      declare @wantedXML xml  
      select @FK = PK from deleted  
      delete tblPropAuthor where propPK = @FK  
  
   select @wantedXML = xCol from inserted  
   select @FK = pk from inserted  
  
   insert into tblPropAuthor   
      select * from dbo.udf_XML2Table(@FK, @wantedXML)  
end  
```  
  
### <a name="example-find-xml-instances-whose-authors-have-the-same-first-name"></a><span data-ttu-id="18b79-149">Пример Поиск экземпляров XML, включающих авторов с именем "David"</span><span class="sxs-lookup"><span data-stu-id="18b79-149">Example: Find XML Instances Whose Authors Have the Same First Name</span></span>  
 <span data-ttu-id="18b79-150">Можно составить такой запрос для XML-столбца</span><span class="sxs-lookup"><span data-stu-id="18b79-150">The query can be formed on the XML column.</span></span> <span data-ttu-id="18b79-151">или найти в таблице свойств записи с именами David и выполнить обратное соединение с базовой таблицей для возврата экземпляра XML.</span><span class="sxs-lookup"><span data-stu-id="18b79-151">Alternatively, it can search the property table for first name "David" and perform a back join with the base table to return the XML instance.</span></span> <span data-ttu-id="18b79-152">Пример:</span><span class="sxs-lookup"><span data-stu-id="18b79-152">For example:</span></span>  
  
```  
SELECT xCol   
FROM     T JOIN tblPropAuthor ON T.pk = tblPropAuthor.propPK  
WHERE    tblPropAuthor.propAuthor = 'David'  
```  
  
### <a name="example-solution-using-the-clr-streaming-table-valued-function"></a><span data-ttu-id="18b79-153">Пример Решение, основанное на использовании потоковой функции CLR с табличным значением</span><span class="sxs-lookup"><span data-stu-id="18b79-153">Example: Solution Using the CLR Streaming Table-valued Function</span></span>  
 <span data-ttu-id="18b79-154">Данное решение состоит из следующих шагов:</span><span class="sxs-lookup"><span data-stu-id="18b79-154">This solution is made up of the following steps:</span></span>  
  
1.  <span data-ttu-id="18b79-155">определение CLR-класса SqlReaderBase, реализующего интерфейс ISqlReader и формирующего потоковый возвращающий табличное значение выход путем применения выражения пути к экземпляру XML;</span><span class="sxs-lookup"><span data-stu-id="18b79-155">Define a CLR class, SqlReaderBase, that implements ISqlReader and generates a streaming, table-valued output by applying a path expression on an XML instance.</span></span>  
  
2.  <span data-ttu-id="18b79-156">создание сборки и пользовательской функции языка Transact-SQL, запускающей класс CLR;</span><span class="sxs-lookup"><span data-stu-id="18b79-156">Create an assembly and a Transact-SQL user-defined function to start the CLR class.</span></span>  
  
3.  <span data-ttu-id="18b79-157">определение с помощью пользовательской функции триггеров вставки, обновления и удаления для обслуживания таблиц свойств.</span><span class="sxs-lookup"><span data-stu-id="18b79-157">Define the insert, update, and delete triggers by using the user-defined function to maintain a property tables.</span></span>  
  
 <span data-ttu-id="18b79-158">Чтобы реализовать это решение, создайте сначала потоковую функцию CLR.</span><span class="sxs-lookup"><span data-stu-id="18b79-158">To do this, you first create the streaming CLR function.</span></span> <span data-ttu-id="18b79-159">`xml`Тип данных предоставляется как управляемый класс SQLXML в ADO.NET и поддерживает метод **CreateReader ()** , возвращающий XmlReader.</span><span class="sxs-lookup"><span data-stu-id="18b79-159">The `xml` data type is exposed as a managed class SqlXml in ADO.NET and supports the **CreateReader()** method that returns an XmlReader.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18b79-160">В примере данного раздела используются классы XPathDocument и XPathNavigator,</span><span class="sxs-lookup"><span data-stu-id="18b79-160">The example code in this section uses XPathDocument and XPathNavigator.</span></span> <span data-ttu-id="18b79-161">которые вынуждают программиста загрузить в память все XML-документы.</span><span class="sxs-lookup"><span data-stu-id="18b79-161">These force you to load all the XML documents into memory.</span></span> <span data-ttu-id="18b79-162">Используя подобный код в своих приложениях для обработки нескольких крупных XML-документов, знайте, что он плохо масштабируется.</span><span class="sxs-lookup"><span data-stu-id="18b79-162">If you are using similar code in your application to process several large XML documents, this code is not scalable.</span></span> <span data-ttu-id="18b79-163">Старайтесь свести к минимуму число операций выделения памяти и используйте во всех возможных случаях потоковые интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="18b79-163">Instead, keep memory allocations small and use streaming interfaces whenever possible.</span></span> <span data-ttu-id="18b79-164">Дополнительные сведения о производительности см. в разделе [Архитектура интеграции со средой CLR](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span><span class="sxs-lookup"><span data-stu-id="18b79-164">For more information about performance, see [Architecture of CLR Integration](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span></span>  
  
```  
public class c_streaming_xml_tvf {  
   public static ISqlReader streaming_xml_tvf   
(SqlXml xmlDoc, string pathExpression) {  
      return (new TestSqlReaderBase (xmlDoc, pathExpression));  
   }  
}  
  
// Class that implements ISqlReader  
public class TestSqlReaderBase : ISqlReader {  
XPathNodeIterator m_iterator;           
   public SqlChars FirstName;  
// Metadata for current resultset  
private SqlMetaData[] m_rgSqlMetaData;        
  
   public TestSqlReaderBase (SqlXml xmlDoc, string pathExpression) {     
      // Variables for XPath navigation  
      XPathDocument xDoc;  
      XPathNavigator xNav;  
      XPathExpression xPath;  
  
      // Set sql metadata  
      m_rgSqlMetaData = new SqlMetaData[1];  
      m_rgSqlMetaData[0] = new SqlMetaData ("FirstName",    
SqlDbType.NVarChar,50);     
  
      //Set up the Navigator  
      if (!xmlDoc.IsNull)  
          xDoc = new XPathDocument (xmlDoc.CreateReader());  
      else  
          xDoc = new XPathDocument ();  
      xNav = xDoc.CreateNavigator();  
      xPath = xNav.Compile (pathExpression);  
      m_iterator = xNav.Select(xPath);  
   }  
   public bool Read() {  
      bool moreRows = true;  
      if (moreRows = m_iterator.MoveNext())  
         FirstName = new SqlChars (m_iterator.Current.Value);  
      return moreRows;  
   }  
}  
```  
  
 <span data-ttu-id="18b79-165">Затем создайте сборку и пользовательскую функцию [!INCLUDE[tsql](../../includes/tsql-md.md)] с именем SQL_streaming_xml_tvf (не показана), соответствующую функции CLR streaming_xml_tvf.</span><span class="sxs-lookup"><span data-stu-id="18b79-165">Next, create an assembly and a [!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined function, SQL_streaming_xml_tvf (not shown), that corresponds to the CLR function, streaming_xml_tvf.</span></span> <span data-ttu-id="18b79-166">Пользовательская функция применяется для определения возвращающей табличное значение функции CLR_udf_XML2Table с целью создания набора строк:</span><span class="sxs-lookup"><span data-stu-id="18b79-166">The user-defined function is used to define the table-valued function, CLR_udf_XML2Table, for rowset generation:</span></span>  
  
```  
create function CLR_udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (FK int, FirstName varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
   select @pk, FirstName   
   FROM   SQL_streaming_xml_tvf (@xCol, '/book/author/first-name')  
      return  
end  
```  
  
 <span data-ttu-id="18b79-167">Наконец, определите триггеры так, как показано в разделе «Создание триггеров для заполнения таблицы свойств», заменив при этом функцию udf_XML2Table функцией CLR_udf_XML2Table.</span><span class="sxs-lookup"><span data-stu-id="18b79-167">Finally, define triggers as shown in the example, "Create triggers to populate a property table", but replace udf_XML2Table with the CLR_udf_XML2Table function.</span></span> <span data-ttu-id="18b79-168">Триггер вставки показан в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="18b79-168">The insert trigger is shown in the following example:</span></span>  
  
```  
create trigger CLR_trg_docs_INS on T for insert  
as  
   declare @wantedXML xml  
   declare @FK int  
   select @wantedXML = xCol from inserted  
   select @FK = PK from inserted  
  
   insert into tblPropAuthor  
      select *  
   from    dbo.CLR_udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="18b79-169">Триггер удаления идентичен версии, не использующей среду CLR.</span><span class="sxs-lookup"><span data-stu-id="18b79-169">The delete trigger is identical to the non-CLR version.</span></span> <span data-ttu-id="18b79-170">Однако триггер обновления просто заменяет функцию udf_XML2Table() функцией CLR_udf_XML2Table().</span><span class="sxs-lookup"><span data-stu-id="18b79-170">However, the update trigger just replaces the function udf_XML2Table() with CLR_udf_XML2Table().</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b79-171">См. также:</span><span class="sxs-lookup"><span data-stu-id="18b79-171">See Also</span></span>  
 [<span data-ttu-id="18b79-172">Использование XML в вычисляемых столбцах</span><span class="sxs-lookup"><span data-stu-id="18b79-172">Use XML in Computed Columns</span></span>](use-xml-in-computed-columns.md)  
  
  
