---
title: Рекомендации и ограничения при выполнении групповой загрузки XML (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], about XML Bulk Load
- bulk load [SQLXML], about bulk load
ms.assetid: c5885d14-c7c1-47b3-a389-455e99a7ece1
author: rothja
ms.author: jroth
ms.openlocfilehash: 08c0020ac7b28702f5a573c6158ec9d50c735b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665971"
---
# <a name="guidelines-and-limitations-of-xml-bulk-load-sqlxml-40"></a><span data-ttu-id="dc82c-102">Правила и ограничения массовой загрузки XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="dc82c-102">Guidelines and Limitations of XML Bulk Load (SQLXML 4.0)</span></span>
  <span data-ttu-id="dc82c-103">Использование массовой загрузки XML требует понимания следующих рекомендаций и ограничений.</span><span class="sxs-lookup"><span data-stu-id="dc82c-103">When you use XML Bulk Load, you should be familiar with the following guidelines and limitations:</span></span>  
  
-   <span data-ttu-id="dc82c-104">Встроенные схемы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="dc82c-104">Inline schemas are not supported.</span></span>  
  
     <span data-ttu-id="dc82c-105">Если в исходном XML-документе содержится встроенная схема, при массовой загрузке XML она не учитывается.</span><span class="sxs-lookup"><span data-stu-id="dc82c-105">If you have an inline schema in the source XML document, XML Bulk Load ignores that schema.</span></span> <span data-ttu-id="dc82c-106">Для массовой загрузки XML нужно задать схему сопоставления, внешнюю по отношению к XML-данным.</span><span class="sxs-lookup"><span data-stu-id="dc82c-106">You specify the mapping schema for XML Bulk Load external to the XML data.</span></span> <span data-ttu-id="dc82c-107">Нельзя указать схему сопоставления в узле с помощью атрибута **xmlns = "КС:счема"** .</span><span class="sxs-lookup"><span data-stu-id="dc82c-107">You cannot specify the mapping schema at a node by using the **xmlns="x:schema"** attribute.</span></span>  
  
-   <span data-ttu-id="dc82c-108">Проверяется правильность формата XML-документа, но сам документ не проверяется.</span><span class="sxs-lookup"><span data-stu-id="dc82c-108">An XML document is checked for being well-formed, but it is not validated.</span></span>  
  
     <span data-ttu-id="dc82c-109">При выполнении операции XML-загрузки выполняется проверка XML-документа, чтобы определить, соответствует ли он правильному формату, т. е. чтобы XML-код соответствует требованиям, предъявляемым к синтаксису XML-1,0 консорциум W3C.</span><span class="sxs-lookup"><span data-stu-id="dc82c-109">XML Bulk Load checks the XML document to determine whether it is well-formed-that is, to ensure that the XML conforms to the syntax requirements of the World Wide Web Consortium's XML 1.0 recommendation.</span></span> <span data-ttu-id="dc82c-110">Если формат документа содержит ошибки, массовая загрузка XML прекращается и возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="dc82c-110">If the document is not well-formed, XML Bulk Load cancels processing and returns an error.</span></span> <span data-ttu-id="dc82c-111">Единственное исключение — когда документ является фрагментом (например, когда у него не один корневой элемент), в этом случае массовая загрузка XML загружает документ.</span><span class="sxs-lookup"><span data-stu-id="dc82c-111">The only exception to this is when the document is a fragment (for example, the document has no single root element), in which case XML Bulk Load will load the document.</span></span>  
  
     <span data-ttu-id="dc82c-112">Массовая загрузка XML не проверяет документ на соответствие какой-либо схеме DTD или XML-Data, которую содержит или на которую ссылается файл XML-данных.</span><span class="sxs-lookup"><span data-stu-id="dc82c-112">XML Bulk Load does not validate the document with respect to any XML-Data or DTD schema that is defined or referenced within the XML data file.</span></span> <span data-ttu-id="dc82c-113">Кроме того, массовая загрузка XML-данных не проверяет файл XML-данных на соответствие переданной схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="dc82c-113">In addition, XML Bulk Load does not validate the XML data file against the mapping schema supplied.</span></span>  
  
-   <span data-ttu-id="dc82c-114">Никакая информация из пролога XML-документа не учитывается.</span><span class="sxs-lookup"><span data-stu-id="dc82c-114">Any XML prolog information is ignored.</span></span>  
  
     <span data-ttu-id="dc82c-115">При выполнении операции XML-загрузки вся информация пропускается до и после \<root> элемента в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="dc82c-115">XML Bulk Load ignores all the information before and after the \<root> element in the XML document.</span></span> <span data-ttu-id="dc82c-116">В частности, массовая загрузка XML не учитывает никаких XML-деклараций, внутренних определений DTD, ссылок на внешние DTD, комментариев и тому подобное.</span><span class="sxs-lookup"><span data-stu-id="dc82c-116">For example, XML Bulk Load ignores any XML declarations, internal DTD definitions, external DTD references, comments, and so on.</span></span>  
  
-   <span data-ttu-id="dc82c-117">При наличии схемы сопоставления, задающей связь «первичный ключ — внешний ключ» между двумя таблицами (например, между таблицами Customer и CustOrder), таблица, содержащая первичный ключ, должна описываться в схеме первой.</span><span class="sxs-lookup"><span data-stu-id="dc82c-117">If you have a mapping schema that defines a primary key/foreign key relationship between two tables (such as between Customer and CustOrder), the table with the primary key must be described first in the schema.</span></span> <span data-ttu-id="dc82c-118">Таблица с внешним ключевым столбцом должна располагаться после нее.</span><span class="sxs-lookup"><span data-stu-id="dc82c-118">The table with the foreign key column must appear later in the schema.</span></span> <span data-ttu-id="dc82c-119">Причина заключается в том, что порядок, в котором таблицы определяются в схеме, является порядком, который используется для их загрузки в базу данных. Например, следующая схема XDR выдаст ошибку при выполнении групповой загрузки XML, так как **\<Order>** элемент описан перед **\<Customer>** элементом.</span><span class="sxs-lookup"><span data-stu-id="dc82c-119">The reason for this is that the order in which the tables are identified in the schema is the order that is used to load them into the database.For example, the following XDR schema will produce an error when it is used in XML Bulk Load because the **\<Order>** element is described before the **\<Customer>** element.</span></span> <span data-ttu-id="dc82c-120">Столбец CustomerID в таблице CustOrder представляет собой внешний ключевой столбец, ссылающийся на первичный ключевой столбец CustomerID в таблице Cust.</span><span class="sxs-lookup"><span data-stu-id="dc82c-120">The CustomerID column in CustOrder is a foreign key column that refers to the CustomerID primary key column in the Cust table.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
        <ElementType name="Order" sql:relation="CustOrder" >  
          <AttributeType name="OrderID" />  
          <AttributeType name="CustomerID" />  
          <attribute type="OrderID" />  
          <attribute type="CustomerID" />  
        </ElementType>  
  
       <ElementType name="CustomerID" dt:type="int" />  
       <ElementType name="CompanyName" dt:type="string" />  
       <ElementType name="City" dt:type="string" />  
  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
       <ElementType name="Customers" sql:relation="Cust"   
                         sql:overflow-field="OverflowColumn"  >  
          <element type="CustomerID" sql:field="CustomerID" />  
          <element type="CompanyName" sql:field="CompanyName" />  
          <element type="City" sql:field="City" />  
          <element type="Order" >   
               <sql:relationship  
                   key-relation="Cust"  
                    key="CustomerID"  
                    foreign-key="CustomerID"  
                    foreign-relation="CustOrder" />  
          </element>  
       </ElementType>  
    </Schema>  
    ```  
  
-   <span data-ttu-id="dc82c-121">Если в схеме не задан явным образом столбец переполнения с помощью заметки `sql:overflow-field`, массовая загрузка XML пропускает любые данные, которые присутствуют в XML-документе, но не описаны в схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="dc82c-121">If the schema does not specify overflow columns by using the `sql:overflow-field` annotation, XML Bulk Load ignores any data that is present in the XML document but is not described in the mapping schema.</span></span>  
  
     <span data-ttu-id="dc82c-122">Массовая загрузка XML применяет заданную схему сопоставления каждый раз, как в потоке XML-данных попадаются известные теги.</span><span class="sxs-lookup"><span data-stu-id="dc82c-122">XML Bulk Load applies the mapping schema that you have specified whenever it encounters known tags in the XML data stream.</span></span> <span data-ttu-id="dc82c-123">Данные, которые присутствуют в XML-документе, но не описаны в схеме, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="dc82c-123">It ignores data that is present in the XML document but is not described in the schema.</span></span> <span data-ttu-id="dc82c-124">Например, предположим, что имеется схема сопоставления, описывающая **\<Customer>** элемент.</span><span class="sxs-lookup"><span data-stu-id="dc82c-124">For example, assume you have a mapping schema that describes a **\<Customer>** element.</span></span> <span data-ttu-id="dc82c-125">Файл данных XML содержит **\<AllCustomers>** корневой тег (не описанный в схеме), включающий все **\<Customer>** элементы:</span><span class="sxs-lookup"><span data-stu-id="dc82c-125">The XML data file has an **\<AllCustomers>** root tag (which is not described in the schema) that encloses all the **\<Customer>** elements:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
      <Customer>...</Customer>  
       ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="dc82c-126">В этом случае при выполнении операции XML с массовым загрузкой элемент не учитывается **\<AllCustomers>** и начинается сопоставление в **\<Customer>** элементе.</span><span class="sxs-lookup"><span data-stu-id="dc82c-126">In this case, XML Bulk Load ignores the **\<AllCustomers>** element and begins mapping at the **\<Customer>** element.</span></span> <span data-ttu-id="dc82c-127">Массовая загрузка XML пропускает все элементы, не описанные в схеме, но присутствующие в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="dc82c-127">XML Bulk Load ignores the elements that are not described in the schema but are present in the XML document.</span></span>  
  
     <span data-ttu-id="dc82c-128">Рассмотрите другой исходный XML-файл данных, содержащий **\<Order>** элементы.</span><span class="sxs-lookup"><span data-stu-id="dc82c-128">Consider another XML source data file that contains **\<Order>** elements.</span></span> <span data-ttu-id="dc82c-129">Эти элементы не описаны в схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="dc82c-129">These elements are not described in the mapping schema:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="dc82c-130">При выполнении групповой загрузки XML эти **\<Order>** элементы игнорируются.</span><span class="sxs-lookup"><span data-stu-id="dc82c-130">XML Bulk Load ignores these **\<Order>** elements.</span></span> <span data-ttu-id="dc82c-131">Но если вы используете `sql:overflow-field` заметку в схеме для того, чтобы указать столбец в качестве столбца переполнения, при выполнении операции XML-загрузки в этом столбце хранятся все невостребованные данные.</span><span class="sxs-lookup"><span data-stu-id="dc82c-131">But if you use the `sql:overflow-field`annotation in the schema to identify a column as an overflow column, XML Bulk Load stores all unconsumed data in this column.</span></span>  
  
-   <span data-ttu-id="dc82c-132">Разделы CDATA и ссылки на сущности для сохранения их в базе данных преобразуются в эквивалентные строки.</span><span class="sxs-lookup"><span data-stu-id="dc82c-132">CDATA sections and entity references are translated to their string equivalents before they are stored in the database.</span></span>  
  
     <span data-ttu-id="dc82c-133">В этом примере раздел CDATA заключает в оболочку значение для **\<City>** элемента.</span><span class="sxs-lookup"><span data-stu-id="dc82c-133">In this example, a CDATA section wraps the value for the **\<City>** element.</span></span> <span data-ttu-id="dc82c-134">При выполнении групповой загрузки XML извлекается строковое значение ("Нью-Йорк") перед вставкой **\<City>** элемента в базу данных.</span><span class="sxs-lookup"><span data-stu-id="dc82c-134">XML Bulk Load extracts the string value ("NY") before it inserts the **\<City>** element into the database.</span></span>  
  
    ```  
    <City><![CDATA[NY]]> </City>  
    ```  
  
     <span data-ttu-id="dc82c-135">Массовая загрузка XML не сохраняет ссылки на сущности.</span><span class="sxs-lookup"><span data-stu-id="dc82c-135">XML Bulk Load does not preserve entity references.</span></span>  
  
-   <span data-ttu-id="dc82c-136">Если в схеме сопоставления задано значение по умолчанию для атрибута и в исходных XML-данных этот атрибут отсутствует, при массовой загрузке XML будет использовано значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc82c-136">If the mapping schema specifies the default value for an attribute and the XML source data does not contain that attribute, XML Bulk Load uses the default value.</span></span>  
  
     <span data-ttu-id="dc82c-137">Следующий пример схемы XDR присваивает атрибуту **HireDate** значение по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="dc82c-137">The following sample XDR schema assigns a default value to the **HireDate** attribute:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
  
       <ElementType name="Customers" sql:relation="Cust3" >  
          <AttributeType name="CustomerID" dt:type="int"  />  
          <AttributeType name="HireDate"  default="2000-01-01" />  
          <AttributeType name="Salary"   />  
  
          <attribute type="CustomerID" sql:field="CustomerID" />  
          <attribute type="HireDate"   sql:field="HireDate"  />  
          <attribute type="Salary"     sql:field="Salary"    />  
       </ElementType>  
    </Schema>  
    ```  
  
     <span data-ttu-id="dc82c-138">В этих XML-данных атрибут **HireDate** отсутствует во втором **\<Customers>** элементе.</span><span class="sxs-lookup"><span data-stu-id="dc82c-138">In this XML data, the **HireDate** attribute is missing from the second **\<Customers>** element.</span></span> <span data-ttu-id="dc82c-139">Когда при выполнении операции XML-загрузки в базу данных вставляется второй **\<Customers>** элемент, используется значение по умолчанию, указанное в схеме.</span><span class="sxs-lookup"><span data-stu-id="dc82c-139">When XML Bulk Load inserts the second **\<Customers>** element into the database, it uses the default value that is specified in the schema.</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1" HireDate="1999-01-01" Salary="10000" />  
      <Customers CustomerID="2" Salary="10000" />  
    </ROOT>  
    ```  
  
-   <span data-ttu-id="dc82c-140">Заметка `sql:url-encode` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="dc82c-140">The `sql:url-encode` annotation is not supported:</span></span>  
  
     <span data-ttu-id="dc82c-141">Нельзя задать во вводных XML-данных URL-адрес и ждать, что массовая загрузка XML прочтет данные, находящиеся по этому адресу.</span><span class="sxs-lookup"><span data-stu-id="dc82c-141">You cannot specify a URL in the XML data input and expect Bulk Load to read data from that location.</span></span>  
  
     <span data-ttu-id="dc82c-142">Создаются таблицы, заданные в схеме сопоставления (база данных должна существовать).</span><span class="sxs-lookup"><span data-stu-id="dc82c-142">The tables that are identified in the mapping schema are created (the database must exist).</span></span> <span data-ttu-id="dc82c-143">Если одна или несколько таблиц уже существуют в базе данных, свойство Сгдроптаблес определяет, нужно ли удалять и повторно создавать эти предварительно существовавшие таблицы.</span><span class="sxs-lookup"><span data-stu-id="dc82c-143">If one or more of the tables already exists in the database, the SGDropTables property determines whether these preexisting tables are to be dropped and re-created.</span></span>  
  
-   <span data-ttu-id="dc82c-144">Если указать свойство SchemaGen (например, SchemaGen = true), то будут созданы таблицы, определенные в схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="dc82c-144">If you specify the SchemaGen property (for example, SchemaGen = true), the tables that are identified in the mapping schema are created.</span></span> <span data-ttu-id="dc82c-145">Но SchemaGen не создает никаких ограничений (таких как ограничения ПЕРВИЧного и внешнего ключей) в этих таблицах с одним исключением: Если XML-узлы, составляющие первичный ключ в связи, определены как имеющие тип XML ID (то есть `type="xsd:ID"` для XSD), а свойство сгусеид имеет значение true для SchemaGen, то не только первичные ключи создаются из узлов с типом ID, но связи первичного и внешнего ключей создаются из связей схемы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="dc82c-145">But SchemaGen does not create any constraints (such as the PRIMARY KEY/FOREIGN KEY constraints) on these tables with one exception: If the XML nodes that constitute the primary key in a relationship are defined as having an XML type of ID (that is, `type="xsd:ID"` for XSD) AND the SGUseID property is set to True for SchemaGen, then not only are primary keys created from the ID typed nodes, but primary key/foreign key relationships are created from mapping schema relationships.</span></span>  
  
-   <span data-ttu-id="dc82c-146">SchemaGen не использует аспекты и расширения схемы XSD для создания реляционной [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] схемы.</span><span class="sxs-lookup"><span data-stu-id="dc82c-146">SchemaGen does not use XSD schema facets and extensions to generate the relational [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] schema.</span></span>  
  
-   <span data-ttu-id="dc82c-147">Если указать свойство SchemaGen (например, SchemaGen = true) при выполнении групповой загрузки, обновляются только таблицы (а не представления общего имени), которые задаются.</span><span class="sxs-lookup"><span data-stu-id="dc82c-147">If you specify the SchemaGen property (for example, SchemaGen = true) on Bulk Load, only tables (and not views of shared name) that are specified are updated.</span></span>  
  
-   <span data-ttu-id="dc82c-148">SchemaGen предоставляет базовую функциональность только для создания реляционной схемы из аннотации XSD.</span><span class="sxs-lookup"><span data-stu-id="dc82c-148">SchemaGen only provides basic functionality for generating the relational schema from annotated XSD.</span></span> <span data-ttu-id="dc82c-149">При необходимости пользователь должен изменить созданные таблицы вручную.</span><span class="sxs-lookup"><span data-stu-id="dc82c-149">The user should modify the generated tables manually, if needed.</span></span>  
  
-   <span data-ttu-id="dc82c-150">Если между таблицами существует больше связей, SchemaGen пытается создать единую связь, включающую все ключи, участвующие в двух таблицах.</span><span class="sxs-lookup"><span data-stu-id="dc82c-150">Where more than relationship exists between tables,SchemaGen tries to create a single relationship that includes all the keys involved between the two tables.</span></span> <span data-ttu-id="dc82c-151">Это ограничение может вызвать ошибку [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc82c-151">This limitation might be the cause of a [!INCLUDE[tsql](../../../includes/tsql-md.md)] error.</span></span>  
  
-   <span data-ttu-id="dc82c-152">При массовой загрузке XML-данных в базу по меньшей мере один атрибут или дочерний элемент в схеме сопоставления должен быть сопоставлен со столбцом базы данных.</span><span class="sxs-lookup"><span data-stu-id="dc82c-152">When you are bulk loading XML data into a database, there must be at least one attribute or child element in the mapping schema that is mapped to a database column.</span></span>  
  
-   <span data-ttu-id="dc82c-153">Если при массовой загрузке XML происходит вставка значений дат, эти значения должны быть заданы в формате (-)CCYY-MM-DD((+-)TZ).</span><span class="sxs-lookup"><span data-stu-id="dc82c-153">If you are inserting date values by using XML Bulk Load, the values must be specified in the (-)CCYY-MM-DD((+-)TZ) format.</span></span> <span data-ttu-id="dc82c-154">Это стандартный формат даты в XSD.</span><span class="sxs-lookup"><span data-stu-id="dc82c-154">This is the standard XSD format for the date.</span></span>  
  
-   <span data-ttu-id="dc82c-155">Некоторые флаги свойств несовместимы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="dc82c-155">Some property flags are not compatible with other property flags.</span></span> <span data-ttu-id="dc82c-156">Например, при массовой загрузке не поддерживается значение `Ignoreduplicatekeys=true` вместе со значением `Keepidentity=false`.</span><span class="sxs-lookup"><span data-stu-id="dc82c-156">For example, bulk load does not support `Ignoreduplicatekeys=true` together with `Keepidentity=false`.</span></span> <span data-ttu-id="dc82c-157">При использовании значения `Keepidentity=false` в операции массовой загрузки происходит ожидание создания сервером значений ключа.</span><span class="sxs-lookup"><span data-stu-id="dc82c-157">When `Keepidentity=false`, bulk load expects the server to generate the key values.</span></span> <span data-ttu-id="dc82c-158">Таблицы должны иметь ограничение `IDENTITY`, которое распространяется на этот ключ.</span><span class="sxs-lookup"><span data-stu-id="dc82c-158">Tables should have an `IDENTITY` constraint on the key.</span></span> <span data-ttu-id="dc82c-159">Сервер не создает повторяющиеся ключи, поэтому нет необходимости присваивать свойству `Ignoreduplicatekeys` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="dc82c-159">The server will not generate duplicate keys, which means there is no need for `Ignoreduplicatekeys` to be set to `true`.</span></span> <span data-ttu-id="dc82c-160">Свойство `Ignoreduplicatekeys` должно иметь значение `true` только при передаче значений первичного ключа из входящих данных в таблицу, содержащую строки, если существует вероятность конфликта значений первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="dc82c-160">`Ignoreduplicatekeys` should be set to `true` only when uploading primary key values from the incoming data into a table that has rows and there is a potential for conflict of primary key values.</span></span>  
  
  
