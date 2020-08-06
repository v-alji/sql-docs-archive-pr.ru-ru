---
title: 'Примеры: Использование инструкции OPENXML | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ColPattern [XML in SQL Server]
- XML [SQL Server], mapping data
- OPENXML statement, about OPENXML statement
- overflow in XML document [SQL Server]
- mapping XML data [SQL Server]
- combining attribute-centric and element centric mapping
- unconsumed data
- attribute-centric mapping
- column patterns [XML in SQL Server]
- XML [SQL Server], overflow handling
- row patterns [XML in SQL Server]
- rowpattern [XML in SQL Server]
- flags parameter
- element-centric mapping [SQL Server]
- edge tables
ms.assetid: 689297f3-adb0-4d8d-bf62-cfda26210164
author: rothja
ms.author: jroth
ms.openlocfilehash: 09fc6ad073b12df2f9fbd8ebc6a59149f6154ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752011"
---
# <a name="examples-using-openxml"></a><span data-ttu-id="41d06-102">Примеры: Использование OPENXML</span><span class="sxs-lookup"><span data-stu-id="41d06-102">Examples: Using OPENXML</span></span>
  <span data-ttu-id="41d06-103">Примеры в этом подразделе иллюстрируют использование инструкции OPENXML для создания представления наборов строк XML-документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-103">The examples in this topic show how OPENXML is used to create a rowset view of an XML document.</span></span> <span data-ttu-id="41d06-104">Дополнительные сведения о синтаксисе инструкции OPENXML см. в разделе [OPENXML (Transact-SQL)](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="41d06-104">For information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span> <span data-ttu-id="41d06-105">Примеры показывают все аспекты инструкции OPENXML, но не определяют метасвойства в ней.</span><span class="sxs-lookup"><span data-stu-id="41d06-105">The examples show all aspects of OPENXML, but do not specify metaproperties in OPENXML.</span></span> <span data-ttu-id="41d06-106">Дополнительные сведения о том, как использовать метасвойства в OPENXML, см. в статье [Определение метасвойств в инструкции OPENXML](specify-metaproperties-in-openxml.md).</span><span class="sxs-lookup"><span data-stu-id="41d06-106">For more information about how to specify metaproperties in OPENXML, see [Specify Metaproperties in OPENXML](specify-metaproperties-in-openxml.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="41d06-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="41d06-107">Examples</span></span>  
 <span data-ttu-id="41d06-108">При получении данных шаблон *rowpattern* используется для определения узлов в XML-документе, которые определяют строки.</span><span class="sxs-lookup"><span data-stu-id="41d06-108">In retrieving the data, *rowpattern* is used to identify the nodes in the XML document that determine the rows.</span></span> <span data-ttu-id="41d06-109">Кроме того, шаблон *rowpattern* выражен на языке шаблонов XPath, который используется в реализации языка XPath в MSXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-109">Additionally, *rowpattern* is expressed in the XPath pattern language that is used in the MSXML XPath implementation.</span></span> <span data-ttu-id="41d06-110">Например, если шаблон заканчивается элементом или атрибутом, то строка создается для каждого узла элемента или атрибута, который выбран шаблоном *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="41d06-110">For example, if the pattern ends in an element or an attribute, a row is created for each element or attribute node that is selected by *rowpattern*.</span></span>  
  
 <span data-ttu-id="41d06-111">Значение параметра *flags* предоставляет сопоставление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41d06-111">The *flags* value provides default mapping.</span></span> <span data-ttu-id="41d06-112">Если параметр *ColPattern* не задан в элементе *SchemaDeclaration*, то предполагается сопоставление, указанное в параметре *flags* .</span><span class="sxs-lookup"><span data-stu-id="41d06-112">If no *ColPattern* is specified in the *SchemaDeclaration*, the mapping specified in *flags* is assumed.</span></span> <span data-ttu-id="41d06-113">Значение параметра *flags* игнорируется, если параметр *ColPattern* определен в элементе *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="41d06-113">The *flags* value is ignored if *ColPattern* is specified in *SchemaDeclaration*.</span></span> <span data-ttu-id="41d06-114">Задание параметра *ColPattern* определяет атрибутивное или элементное сопоставление, а также характер обработки переполнения и невостребованных данных.</span><span class="sxs-lookup"><span data-stu-id="41d06-114">The specified *ColPattern* determines the mapping, attribute-centric or element-centric, and also the behavior in dealing with overflow and unconsumed data.</span></span>  
  
### <a name="a-executing-a-simple-select-statement-with-openxml"></a><span data-ttu-id="41d06-115">A.</span><span class="sxs-lookup"><span data-stu-id="41d06-115">A.</span></span> <span data-ttu-id="41d06-116">Выполнение простой инструкции SELECT с предложением OPENXML</span><span class="sxs-lookup"><span data-stu-id="41d06-116">Executing a simple SELECT statement with OPENXML</span></span>  
 <span data-ttu-id="41d06-117">XML-документ в этом примере состоит из элементов <`Customer`>, <`Order`> и <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-117">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="41d06-118">Инструкция OPENXML получает из XML-документа сведения о заказчике в наборе строк из двух столбцов — **CustomerID** и **ContactName**.</span><span class="sxs-lookup"><span data-stu-id="41d06-118">The OPENXML statement retrieves customer information in a two-column rowset, **CustomerID** and **ContactName**, from the XML document.</span></span>  
  
 <span data-ttu-id="41d06-119">Сначала вызывается хранимая процедура **sp_xml_preparedocument** , чтобы получить дескриптор документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-119">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="41d06-120">Дескриптор документа передается инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-120">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="41d06-121">Инструкция OPENXML иллюстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="41d06-121">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="41d06-122">шаблон *rowpattern* (/ROOT/Customer) определяет, что следует обрабатывать узлы <`Customer`>;</span><span class="sxs-lookup"><span data-stu-id="41d06-122">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="41d06-123">параметр *flags* имеет значение **1** , которое указывает на сопоставление с использованием атрибутивной модели;</span><span class="sxs-lookup"><span data-stu-id="41d06-123">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="41d06-124">В результате XML-атрибуты сопоставляются со столбцами в наборе строк, определенном в элементе *SchemaDeclaration*;</span><span class="sxs-lookup"><span data-stu-id="41d06-124">As a result, the XML attributes map to the columns in the rowset defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="41d06-125">в элементе *SchemaDeclaration*предложения WITH заданные значения параметра *ColName* совпадают с соответствующими именами XML-атрибутов.</span><span class="sxs-lookup"><span data-stu-id="41d06-125">In *SchemaDeclaration*, in the WITH clause, the specified *ColName* values match the corresponding XML attribute names.</span></span> <span data-ttu-id="41d06-126">Поэтому параметр *ColPattern* не указывается в элементе *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="41d06-126">Therefore, the *ColPattern* parameter is not specified in *SchemaDeclaration*.</span></span>  
  
 <span data-ttu-id="41d06-127">Затем инструкция SELECT извлекает все столбцы из набора строк, предоставленного инструкцией OPENXML:</span><span class="sxs-lookup"><span data-stu-id="41d06-127">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @DocHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @DocHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@DocHandle, '/ROOT/Customer',1)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @DocHandle  
```  
  
 <span data-ttu-id="41d06-128">Результат:</span><span class="sxs-lookup"><span data-stu-id="41d06-128">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="41d06-129">Поскольку элементы <`Customer`> не имеют подэлементов, то выполнение той же самой инструкции SELECT с параметром *flags* со значением **2**, которое указывает на сопоставление с использованием элементов, возвращает значения NULL столбцов **CustomerID** и **ContactName** для обоих пользователей.</span><span class="sxs-lookup"><span data-stu-id="41d06-129">Because the <`Customer`> elements do not have any subelements, if the same SELECT statement is executed with *flags* set to **2** to indicate element-centric mapping, the values of **CustomerID** and **ContactName** for both the customers are returned as NULL.</span></span>  
  
 <span data-ttu-id="41d06-130">Аргумент @xmlDocument может также иметь тип **xml** или **(n)varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="41d06-130">The @xmlDocument can also be of **xml** type or of **(n)varchar(max)** type.</span></span>  
  
 <span data-ttu-id="41d06-131">Если <`CustomerID`> и <`ContactName`> в XML-документе являются подэлементами, то сопоставление с использованием элементов возвращает значения:</span><span class="sxs-lookup"><span data-stu-id="41d06-131">If <`CustomerID`> and <`ContactName`> in the XML document are subelements, the element-centric mapping retrieves the values.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer>  
   <CustomerID>VINET</CustomerID>  
   <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer>     
   <CustomerID>LILAS</CustomerID>  
   <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT    *  
FROM      OPENXML (@XmlDocumentHandle, '/ROOT/Customer',2)  
           WITH (CustomerID  varchar(10),  
                 ContactName varchar(20))  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="41d06-132">Результат:</span><span class="sxs-lookup"><span data-stu-id="41d06-132">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="41d06-133">Обратите внимание, что дескриптор документа, возвращенного хранимой процедурой **sp_xml_preparedocument** , действителен в течение выполнения пакета, но не в течение сеанса.</span><span class="sxs-lookup"><span data-stu-id="41d06-133">Note that the document handle returned by **sp_xml_preparedocument** is valid for the duration of the batch and not the session.</span></span>  
  
### <a name="b-specifying-colpattern-for-mapping-between-rowset-columns-and-the-xml-attributes-and-elements"></a><span data-ttu-id="41d06-134">Б.</span><span class="sxs-lookup"><span data-stu-id="41d06-134">B.</span></span> <span data-ttu-id="41d06-135">Задание параметра ColPattern для сопоставления столбцов набора строк с XML-атрибутами и элементами</span><span class="sxs-lookup"><span data-stu-id="41d06-135">Specifying ColPattern for mapping between rowset columns and the XML attributes and elements</span></span>  
 <span data-ttu-id="41d06-136">Данный пример показывает, как задается шаблон XPath в необязательном параметре *ColPattern* для сопоставления столбцов набора строк с XML-атрибутами и элементами.</span><span class="sxs-lookup"><span data-stu-id="41d06-136">This example shows how the XPath pattern is specified in the optional *ColPattern* parameter to provide mapping between rowset columns and the XML attributes and elements.</span></span>  
  
 <span data-ttu-id="41d06-137">XML-документ в этом примере состоит из элементов <`Customer`>, <`Order`> и <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-137">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="41d06-138">Инструкция OPENXML получает из XML-документа сведения о заказчике и заказе в виде набора строк (**CustomerID**, **OrderDate**, **ProdID**и **Qty**).</span><span class="sxs-lookup"><span data-stu-id="41d06-138">The OPENXML statement retrieves customer and order information as a rowset (**CustomerID**, **OrderDate**, **ProdID**, and **Qty**) from the XML document.</span></span>  
  
 <span data-ttu-id="41d06-139">Сначала вызывается хранимая процедура **sp_xml_preparedocument** , чтобы получить дескриптор документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-139">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="41d06-140">Дескриптор документа передается инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-140">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="41d06-141">Инструкция OPENXML иллюстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="41d06-141">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="41d06-142">шаблон *rowpattern* (/ROOT/Customer/Order) определяет, что следует обрабатывать узлы элемента <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifies the <`OrderDetail`> nodes to process.</span></span>  
  
 <span data-ttu-id="41d06-143">В примере параметр *flags* имеет значение **2** , которое указывает на сопоставление с использованием элементов.</span><span class="sxs-lookup"><span data-stu-id="41d06-143">For illustration, the *flags* parameter value is set to **2** and indicates element-centric mapping.</span></span> <span data-ttu-id="41d06-144">Однако сопоставление, указанное в параметре *ColPattern* , перекрывает данное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="41d06-144">However, the mapping specified in *ColPattern* overwrites this mapping.</span></span> <span data-ttu-id="41d06-145">То есть шаблон XPath, заданный в параметре *ColPattern* , сопоставляет столбцы набора строк с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="41d06-145">That is, the XPath pattern specified in *ColPattern* maps the columns in the rowset to attributes.</span></span> <span data-ttu-id="41d06-146">Результатом является атрибутивное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="41d06-146">This results in attribute-centric mapping.</span></span>  
  
 <span data-ttu-id="41d06-147">В элементе *SchemaDeclaration*предложения WITH параметр *ColPattern* также задается параметрами *ColName* и *ColType* .</span><span class="sxs-lookup"><span data-stu-id="41d06-147">In *SchemaDeclaration*, in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="41d06-148">Необязательный параметр *ColPattern* является заданным шаблоном XPath и указывает следующее:</span><span class="sxs-lookup"><span data-stu-id="41d06-148">The optional *ColPattern* is the XPath pattern specified and indicates the following:</span></span>  
  
-   <span data-ttu-id="41d06-149">Столбцы **OrderID**, **CustomerID** и **OrderDate** в наборе строк сопоставляются с атрибутами родителя узлов, заданных шаблоном *rowpattern*, а шаблон *rowpattern* определяет узлы <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-149">The **OrderID**, **CustomerID**, and **OrderDate** columns in the rowset map to the attributes of the parent of the nodes identified by *rowpattern*, and *rowpattern* identifies the <`OrderDetail`> nodes.</span></span> <span data-ttu-id="41d06-150">Следовательно, столбцы **CustomerID** и **OrderDate** сопоставляются с атрибутами **CustomerID** и **OrderDate** элемента <`Order`>;</span><span class="sxs-lookup"><span data-stu-id="41d06-150">Therefore, the **CustomerID** and **OrderDate** columns map to **CustomerID** and **OrderDate** attributes of the <`Order`> element.</span></span>  
  
-   <span data-ttu-id="41d06-151">столбцы **ProdID** и **Qty** в наборе строк сопоставляются с атрибутами **ProductID** и **Quantity** узлов, заданных в шаблоне *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="41d06-151">The **ProdID** and **Qty** columns in the rowset map to the **ProductID** and **Quantity** attributes of the nodes identified in *rowpattern*.</span></span>  
  
 <span data-ttu-id="41d06-152">Затем инструкция SELECT извлекает все столбцы из набора строк, предоставленного инструкцией OPENXML:</span><span class="sxs-lookup"><span data-stu-id="41d06-152">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
           OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
           OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT stmt using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@XmlDocumentHandle, '/ROOT/Customer/Order/OrderDetail',2)  
WITH (OrderID     int         '../@OrderID',  
      CustomerID  varchar(10) '../@CustomerID',  
      OrderDate   datetime    '../@OrderDate',  
      ProdID      int         '@ProductID',  
      Qty         int         '@Quantity')  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="41d06-153">Результат:</span><span class="sxs-lookup"><span data-stu-id="41d06-153">This is the result:</span></span>  
  
```  
OrderID CustomerID        OrderDate          ProdID    Qty  
-------------------------------------------------------------  
10248    VINET     1996-07-04 00:00:00.000     11       12  
10248    VINET     1996-07-04 00:00:00.000     42       10  
10283    LILAS     1996-08-16 00:00:00.000     72        3  
```  
  
 <span data-ttu-id="41d06-154">Шаблон XPath, заданный как параметр *ColPattern* , может также быть указан для сопоставления XML-элементов со столбцами набора строк.</span><span class="sxs-lookup"><span data-stu-id="41d06-154">The XPath pattern specified as *ColPattern* can also be specified to map the XML elements to the rowset columns.</span></span> <span data-ttu-id="41d06-155">Результатом является сопоставление с использованием атрибутов.</span><span class="sxs-lookup"><span data-stu-id="41d06-155">This results in element-centric mapping.</span></span> <span data-ttu-id="41d06-156">В следующем примере элементы <`CustomerID`> и <`OrderDate`> XML-документа являются подэлементами элемента <`Orders`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-156">In the following example, the XML document <`CustomerID`> and <`OrderDate`> are subelements of the <`Orders`> element.</span></span> <span data-ttu-id="41d06-157">Поскольку параметр *ColPattern* перезаписывает сопоставление, заданное в параметре *flags* , то параметр *flags* не указывается в инструкции OPENXML:</span><span class="sxs-lookup"><span data-stu-id="41d06-157">Because *ColPattern* overwrites the mapping specified in the *flags* parameter, the *flags* parameter is not specified in OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order EmployeeID="5" >  
      <OrderID>10248</OrderID>  
      <CustomerID>VINET</CustomerID>  
      <OrderDate>1996-07-04T00:00:00</OrderDate>  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order  EmployeeID="3" >  
      <OrderID>10283</OrderID>  
      <CustomerID>LILAS</CustomerID>  
      <OrderDate>1996-08-16T00:00:00</OrderDate>  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail')  
WITH (CustomerID  varchar(10)   '../CustomerID',  
      OrderDate   datetime      '../OrderDate',  
      ProdID      int           '@ProductID',  
      Qty         int           '@Quantity')  
EXEC sp_xml_removedocument @docHandle  
```  
  
### <a name="c-combining-attribute-centric-and-element-centric-mapping"></a><span data-ttu-id="41d06-158">В.</span><span class="sxs-lookup"><span data-stu-id="41d06-158">C.</span></span> <span data-ttu-id="41d06-159">Совместное применение атрибутивной и элементной моделей сопоставления</span><span class="sxs-lookup"><span data-stu-id="41d06-159">Combining attribute-centric and element-centric mapping</span></span>  
 <span data-ttu-id="41d06-160">В этом примере параметр *flags* имеет значение **3** и указывает на применение как атрибутивного, так и элементного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="41d06-160">In this example, the *flags* parameter is set to **3** and indicates that both attribute-centric and element-centric mapping will be applied.</span></span> <span data-ttu-id="41d06-161">В этом случае сначала применяется атрибутивное сопоставление, а затем элементное сопоставление для всех столбцов, которые еще не обработаны:</span><span class="sxs-lookup"><span data-stu-id="41d06-161">In this case, the attribute-centric mapping is applied first, and then element-centric mapping is applied for all the columns not yet dealt with.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument =N'<ROOT>  
<Customer CustomerID="VINET"  >  
     <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" >   
     <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer',3)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="41d06-162">Результат:</span><span class="sxs-lookup"><span data-stu-id="41d06-162">This is the result</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="41d06-163">Атрибутивное сопоставление применяется к столбцу **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="41d06-163">The attribute-centric mapping is applied for **CustomerID**.</span></span> <span data-ttu-id="41d06-164">Атрибут **ContactName** отсутствует в элементе <`Customer`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-164">There is no **ContactName** attribute in the <`Customer`> element.</span></span> <span data-ttu-id="41d06-165">поэтому применяется элементное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="41d06-165">Therefore, element-centric mapping is applied.</span></span>  
  
### <a name="d-specifying-the-text-xpath-function-as-colpattern"></a><span data-ttu-id="41d06-166">Г.</span><span class="sxs-lookup"><span data-stu-id="41d06-166">D.</span></span> <span data-ttu-id="41d06-167">Задание функции text() языка XPath вместо параметра ColPattern</span><span class="sxs-lookup"><span data-stu-id="41d06-167">Specifying the text() XPath function as ColPattern</span></span>  
 <span data-ttu-id="41d06-168">XML-документ в этом примере состоит из элементов <`Customer`> и <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-168">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="41d06-169">Инструкция OPENXML возвращает набор строк, который состоит из атрибута **oid** элемента <`Order`>, идентификатора родителя узла, заданного шаблоном *rowpattern*, и строки конечных значений содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="41d06-169">The OPENXML statement retrieves a rowset that is made up of the **oid** attribute from the <`Order`> element, the ID of the parent of the node identified by *rowpattern*, and the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="41d06-170">Сначала вызывается хранимая процедура **sp_xml_preparedocument** , чтобы получить дескриптор документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-170">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="41d06-171">Дескриптор документа передается инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-171">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="41d06-172">Инструкция OPENXML иллюстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="41d06-172">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="41d06-173">шаблон *rowpattern* (/ROOT/Customer/Order) определяет, что следует обрабатывать узлы <`Order`>;</span><span class="sxs-lookup"><span data-stu-id="41d06-173">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="41d06-174">параметр *flags* имеет значение **1** , которое указывает на сопоставление с использованием атрибутивной модели;</span><span class="sxs-lookup"><span data-stu-id="41d06-174">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="41d06-175">В результате XML-атрибуты сопоставляются со столбцами в наборе строк, определенном в элементе *SchemaDeclaration*;</span><span class="sxs-lookup"><span data-stu-id="41d06-175">As a result, the XML attributes map to the rowset columns defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="41d06-176">в элементе *SchemaDeclaration* предложения WITH имена столбцов **oid** и **amount** в наборе строк совпадают с соответствующими именами XML-атрибутов.</span><span class="sxs-lookup"><span data-stu-id="41d06-176">In *SchemaDeclaration* in the WITH clause, the **oid** and **amount** rowset column names match the corresponding XML attribute names.</span></span> <span data-ttu-id="41d06-177">Поэтому параметр *ColPattern* не указывается.</span><span class="sxs-lookup"><span data-stu-id="41d06-177">Therefore, the *ColPattern* parameter is not specified.</span></span> <span data-ttu-id="41d06-178">Для столбца **comment** в наборе строк функция XPath **text()** задается в виде параметра *ColPattern*.</span><span class="sxs-lookup"><span data-stu-id="41d06-178">For the **comment** column in the rowset, the XPath function, **text()**, is specified as *ColPattern*.</span></span> <span data-ttu-id="41d06-179">Это перезаписывает сопоставление с использованием атрибутивной модели, заданное в параметре *flags*, и столбец содержит строку конечных значений содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="41d06-179">This overwrites the attribute-centric mapping specified in *flags*, and the column contains the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="41d06-180">Затем инструкция SELECT извлекает все столбцы из набора строк, предоставленного инструкцией OPENXML:</span><span class="sxs-lookup"><span data-stu-id="41d06-180">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied  
      </Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
            <Urgency>Important</Urgency>  
            Happy Customer.  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH (oid     char(5),   
           amount  float,   
           comment ntext 'text()')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="41d06-181">Результат:</span><span class="sxs-lookup"><span data-stu-id="41d06-181">This is the result:</span></span>  
  
```  
oid   amount        comment  
----- -----------   -----------------------------  
O1    3.5           NULL  
O2    13.4          Customer was very satisfied  
O3    100.0         Happy Customer.  
O4    10000.0       NULL  
```  
  
### <a name="e-specifying-tablename-in-the-with-clause"></a><span data-ttu-id="41d06-182">Д.</span><span class="sxs-lookup"><span data-stu-id="41d06-182">E.</span></span> <span data-ttu-id="41d06-183">Задание элемента TableName в предложении WITH</span><span class="sxs-lookup"><span data-stu-id="41d06-183">Specifying TableName in the WITH clause</span></span>  
 <span data-ttu-id="41d06-184">Этот пример задает элемент *TableName* в предложении WITH вместо элемента *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="41d06-184">This example specifies *TableName* in the WITH clause instead of *SchemaDeclaration*.</span></span> <span data-ttu-id="41d06-185">Это полезно, если таблица имеет нужную структуру и не требуются шаблоны столбцов (параметр *ColPattern* ).</span><span class="sxs-lookup"><span data-stu-id="41d06-185">This is useful if you have a table that has the structure you want and no column patterns, *ColPattern* parameter, are required.</span></span>  
  
 <span data-ttu-id="41d06-186">XML-документ в этом примере состоит из элементов <`Customer`> и <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-186">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="41d06-187">Инструкция OPENXML возвращает сведения о заказе в наборе строк из трех столбцов (**oid**, **date**и **amount**), полученные из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-187">The OPENXML statement retrieves order information in a three-column rowset (**oid**, **date**, and **amount**) from the XML document.</span></span>  
  
 <span data-ttu-id="41d06-188">Сначала вызывается хранимая процедура **sp_xml_preparedocument** , чтобы получить дескриптор документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-188">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="41d06-189">Дескриптор документа передается инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-189">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="41d06-190">Инструкция OPENXML иллюстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="41d06-190">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="41d06-191">шаблон *rowpattern* (/ROOT/Customer/Order) определяет, что следует обрабатывать узлы <`Order`>;</span><span class="sxs-lookup"><span data-stu-id="41d06-191">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="41d06-192">в предложении WITH отсутствует элемент *SchemaDeclaration* ,</span><span class="sxs-lookup"><span data-stu-id="41d06-192">There is no *SchemaDeclaration* in the WITH clause.</span></span> <span data-ttu-id="41d06-193">вместо него задано имя таблицы;</span><span class="sxs-lookup"><span data-stu-id="41d06-193">Instead, a table name is specified.</span></span> <span data-ttu-id="41d06-194">поэтому схема таблицы используется в качестве схемы набора строк;</span><span class="sxs-lookup"><span data-stu-id="41d06-194">Therefore, the table schema is used as the rowset schema.</span></span>  
  
-   <span data-ttu-id="41d06-195">параметр *flags* имеет значение **1** , которое указывает на сопоставление с использованием атрибутивной модели;</span><span class="sxs-lookup"><span data-stu-id="41d06-195">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="41d06-196">поэтому атрибуты элементов, заданные шаблоном *rowpattern*, сопоставляются со столбцами набора строк с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="41d06-196">Therefore, attributes of the elements, identified by *rowpattern*, map to the rowset columns with the same name.</span></span>  
  
 <span data-ttu-id="41d06-197">Затем инструкция SELECT извлекает все столбцы из набора строк, предоставленного инструкцией OPENXML:</span><span class="sxs-lookup"><span data-stu-id="41d06-197">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
-- Create a test table. This table schema is used by OPENXML as the  
-- rowset schema.  
CREATE TABLE T1(oid char(5), date datetime, amount float)  
GO  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
-- Sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH T1  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="41d06-198">Результат:</span><span class="sxs-lookup"><span data-stu-id="41d06-198">This is the result:</span></span>  
  
```  
oid   date                        amount  
----- --------------------------- ----------  
O1    1996-01-20 00:00:00.000     3.5  
O2    1997-04-30 00:00:00.000     13.4  
O3    1999-07-14 00:00:00.000     100.0  
O4    1996-01-20 00:00:00.000     10000.0  
```  
  
### <a name="f-obtaining-the-result-in-an-edge-table-format"></a><span data-ttu-id="41d06-199">Е.</span><span class="sxs-lookup"><span data-stu-id="41d06-199">F.</span></span> <span data-ttu-id="41d06-200">Получение результата в формате краевой таблицы</span><span class="sxs-lookup"><span data-stu-id="41d06-200">Obtaining the result in an edge table format</span></span>  
 <span data-ttu-id="41d06-201">В этом примере предложение WITH не задано в инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-201">In this example, the WITH clause is not specified in the OPENXML statement.</span></span> <span data-ttu-id="41d06-202">В результате набор строк, сформированный инструкцией OPENXML, имеет формат краевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="41d06-202">As a result, the rowset generated by OPENXML has an edge table format.</span></span> <span data-ttu-id="41d06-203">Инструкция SELECT возвращает все столбцы в краевой таблице.</span><span class="sxs-lookup"><span data-stu-id="41d06-203">The SELECT statement returns all the columns in the edge table.</span></span>  
  
 <span data-ttu-id="41d06-204">Образец XML-документа в этом примере состоит из элементов <`Customer`>, <`Order`> и <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-204">The sample XML document in the example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span>  
  
 <span data-ttu-id="41d06-205">Сначала вызывается хранимая процедура **sp_xml_preparedocument** , чтобы получить дескриптор документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-205">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="41d06-206">Дескриптор документа передается инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-206">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="41d06-207">Инструкция OPENXML иллюстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="41d06-207">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="41d06-208">шаблон *rowpattern* (/ROOT/Customer) определяет, что следует обрабатывать узлы <`Customer`>;</span><span class="sxs-lookup"><span data-stu-id="41d06-208">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="41d06-209">предложение WITH не задано,</span><span class="sxs-lookup"><span data-stu-id="41d06-209">The WITH clause is not provided.</span></span> <span data-ttu-id="41d06-210">поэтому инструкция OPENXML возвращает набор строк в формате краевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="41d06-210">Therefore, OPENXML returns the rowset in an edge table format.</span></span>  
  
 <span data-ttu-id="41d06-211">Затем инструкция SELECT возвращает все столбцы в краевой таблице.</span><span class="sxs-lookup"><span data-stu-id="41d06-211">The SELECT statement then retrieves all the columns in the edge table.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
SET @xmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail OrderID="10248" ProductID="11" Quantity="12"/>  
      <OrderDetail OrderID="10248" ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail OrderID="10283" ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer')  
  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="41d06-212">Результат возвращается в виде краевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="41d06-212">The result is returned as an edge table.</span></span> <span data-ttu-id="41d06-213">Можно написать запрос к краевой таблице для получения данных.</span><span class="sxs-lookup"><span data-stu-id="41d06-213">You can write queries against the edge table to obtain information.</span></span> <span data-ttu-id="41d06-214">Пример:</span><span class="sxs-lookup"><span data-stu-id="41d06-214">For example:</span></span>  
  
-   <span data-ttu-id="41d06-215">следующий запрос возвращает количество узлов **Customer** в документе.</span><span class="sxs-lookup"><span data-stu-id="41d06-215">The following query returns the number of **Customer** nodes in the document.</span></span> <span data-ttu-id="41d06-216">Поскольку предложение WITH не используется, инструкция OPENXML возвращает краевую таблицу.</span><span class="sxs-lookup"><span data-stu-id="41d06-216">Because the WITH clause is not specified, OPENXML returns an edge table.</span></span> <span data-ttu-id="41d06-217">Инструкция SELECT запрашивает краевую таблицу:</span><span class="sxs-lookup"><span data-stu-id="41d06-217">The SELECT statement queries the edge table.</span></span>  
  
    ```  
    SELECT count(*)  
    FROM OPENXML(@docHandle, '/')  
    WHERE localname = 'Customer'  
    ```  
  
-   <span data-ttu-id="41d06-218">следующий запрос возвращает локальные имена XML-узлов типа элементов:</span><span class="sxs-lookup"><span data-stu-id="41d06-218">The following query returns the local names of XML nodes of element type.</span></span>  
  
    ```  
    SELECT distinct localname   
    FROM OPENXML(@docHandle, '/')   
    WHERE nodetype = 1   
    ORDER BY localname  
    ```  
  
### <a name="g-specifying-rowpattern-ending-with-an-attribute"></a><span data-ttu-id="41d06-219">Ж.</span><span class="sxs-lookup"><span data-stu-id="41d06-219">G.</span></span> <span data-ttu-id="41d06-220">Задание шаблона rowpattern, заканчивающегося атрибутом</span><span class="sxs-lookup"><span data-stu-id="41d06-220">Specifying rowpattern ending with an attribute</span></span>  
 <span data-ttu-id="41d06-221">XML-документ в этом примере состоит из элементов <`Customer`>, <`Order`> и <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-221">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="41d06-222">Инструкция OPENXML возвращает сведения о заказе в наборе строк из трех столбцов (**ProductID**, **Quantity**и **OrderID**) из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-222">The OPENXML statement retrieves information about the order details in a three-column rowset (**ProductID**, **Quantity**, and **OrderID**) from the XML document.</span></span>  
  
 <span data-ttu-id="41d06-223">Сначала вызывается хранимая процедура **sp_xml_preparedocument** , чтобы получить дескриптор документа.</span><span class="sxs-lookup"><span data-stu-id="41d06-223">First, the **sp_xml_preparedocument** is called to obtain a document handle.</span></span> <span data-ttu-id="41d06-224">Дескриптор документа передается инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-224">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="41d06-225">Инструкция OPENXML иллюстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="41d06-225">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="41d06-226">шаблон *rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) заканчивается атрибутом XML — **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="41d06-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) ends with an XML attribute, **ProductID**.</span></span> <span data-ttu-id="41d06-227">В результирующем наборе строк для каждого выбранного в XML-документе узла атрибута создается строка;</span><span class="sxs-lookup"><span data-stu-id="41d06-227">In the resulting rowset, a row is created for each attribute node selected in the XML document.</span></span>  
  
-   <span data-ttu-id="41d06-228">в этом примере параметр *flags* не задан;</span><span class="sxs-lookup"><span data-stu-id="41d06-228">In this example, the *flags* parameter is not specified.</span></span> <span data-ttu-id="41d06-229">вместо него для указания сопоставлений используется параметр *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="41d06-229">Instead, the mappings are specified by the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="41d06-230">В элементе *SchemaDeclaration* предложения WITH параметр *ColPattern* также задан с параметрами *ColName* и *ColType* .</span><span class="sxs-lookup"><span data-stu-id="41d06-230">In *SchemaDeclaration* in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="41d06-231">Необязательный параметр *ColPattern* является заданным шаблоном XPath и указывает следующее:</span><span class="sxs-lookup"><span data-stu-id="41d06-231">The optional *ColPattern* is the XPath pattern specified to indicate the following:</span></span>  
  
-   <span data-ttu-id="41d06-232">шаблон XPath ( **.** ), указанный в виде параметра *ColPattern* для столбца **ProdID** в наборе строк, определяет контекстный узел — текущий узел.</span><span class="sxs-lookup"><span data-stu-id="41d06-232">The XPath pattern (**.**) specified as *ColPattern* for the **ProdID** column in the rowset identifies the context node, current node.</span></span> <span data-ttu-id="41d06-233">Согласно заданному шаблону *rowpattern*, он является атрибутом **ProductID** элемента <`OrderDetail`>;</span><span class="sxs-lookup"><span data-stu-id="41d06-233">As per the *rowpattern* specified, it is the **ProductID** attribute of the <`OrderDetail`> element.</span></span>  
  
-   <span data-ttu-id="41d06-234">шаблон *ColPattern*, **../\@Quantity**, заданный для столбца **Qty** в наборе строк, определяет атрибут **Quantity** родительского узла <`OrderDetail`> контекстного узла \<ProductID>;</span><span class="sxs-lookup"><span data-stu-id="41d06-234">The *ColPattern*, **../\@Quantity**, specified for the **Qty** column in the rowset identifies the **Quantity** attribute of the parent, <`OrderDetail`>, node of the context node, \<ProductID>.</span></span>  
  
-   <span data-ttu-id="41d06-235">аналогично шаблон *ColPattern*, **../../\@OrderID**, заданный для столбца **OID** в наборе строк, определяет атрибут **OrderID** родительского элемента, <`Order`>, родительского узла контекстного узла.</span><span class="sxs-lookup"><span data-stu-id="41d06-235">Similarly, the *ColPattern*, **../../\@OrderID**, specified for the **OID** column in the rowset identifies the **OrderID** attribute of the parent, <`Order`>, of the parent node of the context node.</span></span> <span data-ttu-id="41d06-236">Узлом родителя является <`OrderDetail`>, а контекстным узлом является <`ProductID`>.</span><span class="sxs-lookup"><span data-stu-id="41d06-236">The parent node is <`OrderDetail`>, and the context node is <`ProductID`>.</span></span>  
  
 <span data-ttu-id="41d06-237">Затем инструкция SELECT извлекает все столбцы из набора строк, предоставленного инструкцией OPENXML:</span><span class="sxs-lookup"><span data-stu-id="41d06-237">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--Sample XML document  
SET @xmlDocument =N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail/@ProductID')  
       WITH ( ProdID  int '.',  
              Qty     int '../@Quantity',  
              OID     int '../../@OrderID')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="41d06-238">Результат:</span><span class="sxs-lookup"><span data-stu-id="41d06-238">This is the result:</span></span>  
  
```  
ProdID      Qty         OID  
----------- ----------- -------   
11          12          10248  
42          10          10248  
72          3           10283  
```  
  
### <a name="h-specifying-an-xml-document-that-has-multiple-text-nodes"></a><span data-ttu-id="41d06-239">З.</span><span class="sxs-lookup"><span data-stu-id="41d06-239">H.</span></span> <span data-ttu-id="41d06-240">Задание XML-документа, имеющего несколько текстовых узлов</span><span class="sxs-lookup"><span data-stu-id="41d06-240">Specifying an XML document that has multiple text nodes</span></span>  
 <span data-ttu-id="41d06-241">При наличии нескольких текстовых узлов в XML-документе инструкция SELECT с параметром *ColPattern*, **text()** , возвращает только первый текстовый узел, а не все.</span><span class="sxs-lookup"><span data-stu-id="41d06-241">If you have multiple text nodes in an XML document, a SELECT statement with a *ColPattern*, **text()**, returns only the first text node, instead of all of them.</span></span> <span data-ttu-id="41d06-242">Пример:</span><span class="sxs-lookup"><span data-stu-id="41d06-242">For example:</span></span>  
  
```  
DECLARE @h int  
EXEC sp_xml_preparedocument @h OUTPUT,  
         N'<root xmlns:a="urn:1">  
           <a:Elem abar="asdf">  
             T<a>a</a>U  
           </a:Elem>  
         </root>',  
         '<ns xmlns:b="urn:1" />'  
  
SELECT * FROM openxml(@h, '/root/b:Elem')  
      WITH (Col1 varchar(20) 'text()')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="41d06-243">Инструкция SELECT возвращает в качестве результата таблицу **T** , а не **TaU**.</span><span class="sxs-lookup"><span data-stu-id="41d06-243">The SELECT statement returns **T** as the result, and not **TaU**.</span></span>  
  
### <a name="i-specifying-the-xml-data-type-in-the-with-clause"></a><span data-ttu-id="41d06-244">И.</span><span class="sxs-lookup"><span data-stu-id="41d06-244">I.</span></span> <span data-ttu-id="41d06-245">Задание типа данных XML в предложении WITH</span><span class="sxs-lookup"><span data-stu-id="41d06-245">Specifying the xml data type in the WITH clause</span></span>  
 <span data-ttu-id="41d06-246">В предложении WITH шаблон столбца, который сопоставлен со столбцом типа данных **xml** , типизированным или нетипизированным, должен вернуть либо пустую последовательность, либо последовательность элементов, инструкций обработки, текстовых узлов и комментариев.</span><span class="sxs-lookup"><span data-stu-id="41d06-246">In the WITH clause, a column pattern that is mapped to the **xml** data type column, whether typed or untyped, must return either an empty sequence or a sequence of elements, processing instructions, text nodes, and comments.</span></span> <span data-ttu-id="41d06-247">Данные приводятся к типу **xml** .</span><span class="sxs-lookup"><span data-stu-id="41d06-247">The data is cast to an **xml** data type.</span></span>  
  
 <span data-ttu-id="41d06-248">В следующем примере объявление схемы таблицы в предложении WITH включает столбцы типа **xml** :</span><span class="sxs-lookup"><span data-stu-id="41d06-248">In the following example, the table schema declaration in the WITH clause includes **xml** type columns.</span></span>  
  
```  
DECLARE @h int  
DECLARE @x xml  
set @x = '<Root>  
  <row id="1"><lname>Duffy</lname>  
   <Address>  
            <Street>111 Maple</Street>  
            <City>Seattle</City>  
   </Address>  
  </row>  
  <row id="2"><lname>Wang</lname>  
   <Address>  
            <Street>222 Pine</Street>  
            <City>Bothell</City>  
   </Address>  
  </row>  
</Root>'  
  
EXEC sp_xml_preparedocument @h output, @x  
SELECT *  
FROM   OPENXML (@h, '/Root/row', 10)  
      WITH (id int '@id',  
  
            lname    varchar(30),  
            xmlname  xml 'lname',  
            OverFlow xml '@mp:xmltext')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="41d06-249">А именно, переменная (\@x) типа **xml** передается функции **sp_xml_preparedocument()** .</span><span class="sxs-lookup"><span data-stu-id="41d06-249">Specifically, you are passing an **xml** type variable (\@x) to the **sp_xml_preparedocument()** function.</span></span>  
  
 <span data-ttu-id="41d06-250">Результат:</span><span class="sxs-lookup"><span data-stu-id="41d06-250">This is the result:</span></span>  
  
```  
id  lname   xmlname                   OverFlow  
--- ------- ------------------------------ -------------------------------  
1   Duffy   <lname>Duffy</lname>  <row><Address>  
                                   <Street>111 Maple</Street>  
                                   <City>Seattle</City>  
                                  </Address></row>  
2   Wang    <lname>Wang</lname>   <row><Address>  
                                    <Street>222 Pine</Street>  
                                    <City>Bothell</City>  
                                   </Address></row>  
```  
  
 <span data-ttu-id="41d06-251">Обратите внимание на следующие факты:</span><span class="sxs-lookup"><span data-stu-id="41d06-251">Note the following from the result:</span></span>  
  
-   <span data-ttu-id="41d06-252">для столбца **lname** типа **varchar(30)** его значение получено из соответствующего элемента <`lname`>;</span><span class="sxs-lookup"><span data-stu-id="41d06-252">For the **lname** column of **varchar(30)** type, its value is retrieved from the corresponding <`lname`> element.</span></span>  
  
-   <span data-ttu-id="41d06-253">для столбца **xmlname** типа **xml** в качестве значения возвращается элемент с таким же именем;</span><span class="sxs-lookup"><span data-stu-id="41d06-253">For the **xmlname** column of **xml** type, the same name element is returned as its value.</span></span>  
  
-   <span data-ttu-id="41d06-254">флаг принимает значение 10,</span><span class="sxs-lookup"><span data-stu-id="41d06-254">The flag is set to 10.</span></span> <span data-ttu-id="41d06-255">означающее 2 + 8, где 2 указывает на элементное сопоставление, а 8 — на то, что к столбцу OverFlow, заданному в предложении WITH, должны быть добавлены только невостребованные XML-данные.</span><span class="sxs-lookup"><span data-stu-id="41d06-255">The 10 means 2 + 8, where 2 indicates element-centric mapping and 8 indicates that only unconsumed XML data should be added to the OverFlow column defined in the WITH clause.</span></span> <span data-ttu-id="41d06-256">Если флаг устанавливается в значение 2, то в столбец OverFlow, заданный в предложении WITH, копируется весь XML-документ;</span><span class="sxs-lookup"><span data-stu-id="41d06-256">If you set the flag to 2, the whole XML document is copied to the OverFlow column that is specified in the WITH clause.</span></span>  
  
-   <span data-ttu-id="41d06-257">если столбец в предложении WITH является типизированным XML-столбцом, а экземпляр XML-документа не соответствует схеме, то возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="41d06-257">In case the column in the WITH clause is a typed XML column and the XML instance does not confirm to the schema, an error is returned.</span></span>  
  
### <a name="j-retrieving-individual-values-from-multivalued-attributes"></a><span data-ttu-id="41d06-258">К.</span><span class="sxs-lookup"><span data-stu-id="41d06-258">J.</span></span> <span data-ttu-id="41d06-259">Получение отдельных значений из многозначных атрибутов</span><span class="sxs-lookup"><span data-stu-id="41d06-259">Retrieving individual values from multivalued attributes</span></span>  
 <span data-ttu-id="41d06-260">XML-документ может иметь многозначные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="41d06-260">An XML document can have attributes that are multivalued.</span></span> <span data-ttu-id="41d06-261">Например, атрибут **IDREFS** может быть многозначным.</span><span class="sxs-lookup"><span data-stu-id="41d06-261">For example, the **IDREFS** attribute can be multivalued.</span></span> <span data-ttu-id="41d06-262">В XML-документе значения многозначных атрибутов задаются в виде строки со значениями, разделенными пробелом.</span><span class="sxs-lookup"><span data-stu-id="41d06-262">In an XML document, the multivalued attribute values are specified as a string, with the values separated by a space.</span></span> <span data-ttu-id="41d06-263">В следующем XML-документе атрибут **attends** элемента \<Student> и атрибут **attendedBy** элемента \<Class> являются многозначными.</span><span class="sxs-lookup"><span data-stu-id="41d06-263">In the following XML document, the **attends** attribute of the \<Student> element and the **attendedBy** attribute of \<Class> are multivalued.</span></span> <span data-ttu-id="41d06-264">Получение отдельных значений из многозначных XML-атрибутов и сохранение каждого значения в отдельной строке базы данных требуют дополнительных операций.</span><span class="sxs-lookup"><span data-stu-id="41d06-264">Retrieving individual values from a multivalued XML attribute and storing each value in a separate row in the database requires additional work.</span></span> <span data-ttu-id="41d06-265">Данный пример иллюстрирует процесс.</span><span class="sxs-lookup"><span data-stu-id="41d06-265">This example shows the process.</span></span>  
  
 <span data-ttu-id="41d06-266">Данный образец XML-документа состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="41d06-266">This sample XML document is made up of the following elements:</span></span>  
  
-   \<Student>  
  
     <span data-ttu-id="41d06-267">Атрибуты **id** (идентификатор студента), **name**и **attends** .</span><span class="sxs-lookup"><span data-stu-id="41d06-267">The **id** (student ID), **name**, and **attends** attributes.</span></span> <span data-ttu-id="41d06-268">Атрибут **attends** является многозначным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="41d06-268">The **attends** attribute is a multivalued attribute.</span></span>  
  
-   \<Class>  
  
     <span data-ttu-id="41d06-269">Атрибуты **id** (идентификатор класса), **name**и **attendedBy** .</span><span class="sxs-lookup"><span data-stu-id="41d06-269">The **id** (class ID), **name**, and **attendedBy** attributes.</span></span> <span data-ttu-id="41d06-270">Атрибут **attendedBy** является многозначным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="41d06-270">The **attendedBy** attribute is a multivalued attribute.</span></span>  
  
 <span data-ttu-id="41d06-271">Атрибут **attends** элемента \<Student> и атрибут **attendedBy** элемента \<Class> представляют отношение **m : n** между таблицами Student и Class.</span><span class="sxs-lookup"><span data-stu-id="41d06-271">The **attends** attribute in \<Student> and the **attendedBy** attribute in \<Class> represent a **m:n** relationship between the Student and Class tables.</span></span> <span data-ttu-id="41d06-272">Студент может посещать множество классов, а класс может иметь множество студентов.</span><span class="sxs-lookup"><span data-stu-id="41d06-272">A student can take many classes and a class can have many students.</span></span>  
  
 <span data-ttu-id="41d06-273">Предположим, что нужно взять часть этого документа и сохранить ее в базе данных, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="41d06-273">Assume that you want to shred this document and save it in the database as shown in the following:</span></span>  
  
-   <span data-ttu-id="41d06-274">Сохраните данные \<Student> в таблице Students.</span><span class="sxs-lookup"><span data-stu-id="41d06-274">Save the \<Student> data in the Students table.</span></span>  
  
-   <span data-ttu-id="41d06-275">Сохраните данные \<Class> в таблице Courses.</span><span class="sxs-lookup"><span data-stu-id="41d06-275">Save the \<Class> data in the Courses table.</span></span>  
  
-   <span data-ttu-id="41d06-276">Сохраните данные связи **m:n** между таблицами Student и Class в таблице CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="41d06-276">Save the **m:n** relationship data, between Student and Class, in the CourseAttendence table.</span></span> <span data-ttu-id="41d06-277">Для извлечения значений требуются дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="41d06-277">Additional work is required to extract the values.</span></span> <span data-ttu-id="41d06-278">Для получения этих сведений и их сохранения в таблице используйте следующие хранимые процедуры:</span><span class="sxs-lookup"><span data-stu-id="41d06-278">To retrieve this information and store it in the table, use these stored procedures:</span></span>  
  
    -   <span data-ttu-id="41d06-279">**Insert_Idrefs_Values**</span><span class="sxs-lookup"><span data-stu-id="41d06-279">**Insert_Idrefs_Values**</span></span>  
  
         <span data-ttu-id="41d06-280">Вставляет значения идентификатора курса и идентификатора студента в таблицу CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="41d06-280">Inserts the values of course ID and student ID in the CourseAttendence table.</span></span>  
  
    -   <span data-ttu-id="41d06-281">**Extract_idrefs_values**</span><span class="sxs-lookup"><span data-stu-id="41d06-281">**Extract_idrefs_values**</span></span>  
  
         <span data-ttu-id="41d06-282">Извлекает идентификаторы отдельных студентов из каждого элемента \<Course>.</span><span class="sxs-lookup"><span data-stu-id="41d06-282">Extracts the individual student IDs from each \<Course> element.</span></span> <span data-ttu-id="41d06-283">Краевая таблица используется для получения этих значений.</span><span class="sxs-lookup"><span data-stu-id="41d06-283">An edge table is used to retrieve these values.</span></span>  
  
 <span data-ttu-id="41d06-284">Ниже приводятся шаги:</span><span class="sxs-lookup"><span data-stu-id="41d06-284">Here are the steps:</span></span>  
  
```  
-- Create these tables:  
DROP TABLE CourseAttendance  
DROP TABLE Students  
DROP TABLE Courses  
GO  
CREATE TABLE Students(  
                id   varchar(5) primary key,  
                name varchar(30)  
                )  
GO  
CREATE TABLE Courses(  
               id       varchar(5) primary key,  
               name     varchar(30),  
               taughtBy varchar(5)  
)  
GO  
CREATE TABLE CourseAttendance(  
             id         varchar(5) references Courses(id),  
             attendedBy varchar(5) references Students(id),  
             constraint CourseAttendance_PK primary key (id, attendedBy)  
)  
go  
-- Create these stored procedures:  
DROP PROCEDURE f_idrefs  
GO  
CREATE PROCEDURE f_idrefs  
    @t      varchar(500),  
    @idtab  varchar(50),  
    @id     varchar(5)  
AS  
DECLARE @sp int  
DECLARE @att varchar(5)  
SET @sp = 0  
WHILE (LEN(@t) > 0)  
BEGIN   
    SET @sp = CHARINDEX(' ', @t+ ' ')  
    SET @att = LEFT(@t, @sp-1)  
    EXEC('INSERT INTO '+@idtab+' VALUES ('''+@id+''', '''+@att+''')')  
    SET @t = SUBSTRING(@t+ ' ', @sp+1, LEN(@t)+1-@sp)  
END  
Go  
  
DROP PROCEDURE fill_idrefs  
GO  
CREATE PROCEDURE fill_idrefs   
    @xmldoc     int,  
    @xpath      varchar(100),  
    @from       varchar(50),  
    @to         varchar(50),  
    @idtable    varchar(100)  
AS  
DECLARE @t varchar(500)  
DECLARE @id varchar(5)  
  
/* Temporary edge table */  
SELECT *   
INTO #TempEdge   
FROM OPENXML(@xmldoc, @xpath)  
  
DECLARE fillidrefs_cursor CURSOR FOR  
    SELECT CAST(iv.text AS nvarchar(200)) AS id,  
           CAST(av.text AS nvarchar(4000)) AS refs  
    FROM   #TempEdge c, #TempEdge i,  
           #TempEdge iv, #TempEdge a, #TempEdge av  
    WHERE  c.id = i.parentid  
    AND    UPPER(i.localname) = UPPER(@from)  
    AND    i.id = iv.parentid  
    AND    c.id = a.parentid  
    AND    UPPER(a.localname) = UPPER(@to)  
    AND    a.id = av.parentid  
  
OPEN fillidrefs_cursor  
FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
WHILE (@@FETCH_STATUS <> -1)  
BEGIN  
    IF (@@FETCH_STATUS <> -2)  
    BEGIN  
        execute f_idrefs @t, @idtable, @id  
    END  
    FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
END  
CLOSE fillidrefs_cursor  
DEALLOCATE fillidrefs_cursor  
Go  
-- This is the sample document that is shredded and the data is stored in the preceding tables.  
DECLARE @h int  
EXECUTE sp_xml_preparedocument @h OUTPUT, N'<Data>  
  <Student id = "s1" name = "Student1"  attends = "c1 c3 c6"  />  
  <Student id = "s2" name = "Student2"  attends = "c2 c4" />  
  <Student id = "s3" name = "Student3"  attends = "c2 c4 c6" />  
  <Student id = "s4" name = "Student4"  attends = "c1 c3 c5" />  
  <Student id = "s5" name = "Student5"  attends = "c1 c3 c5 c6" />  
  <Student id = "s6" name = "Student6" />  
  
  <Class id = "c1" name = "Intro to Programming"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c2" name = "Databases"   
         attendedBy = "s2 s3" />  
  <Class id = "c3" name = "Operating Systems"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c4" name = "Networks" attendedBy = "s2 s3" />  
  <Class id = "c5" name = "Algorithms and Graphs"   
         attendedBy =  "s4 s5"/>  
  <Class id = "c6" name = "Power and Pragmatism"   
         attendedBy = "s1 s3 s5" />  
</Data>'  
  
INSERT INTO Students SELECT * FROM OPENXML(@h, '//Student') WITH Students  
  
INSERT INTO Courses SELECT * FROM OPENXML(@h, '//Class') WITH Courses  
/* Using the edge table */  
EXECUTE fill_idrefs @h, '//Class', 'id', 'attendedby', 'CourseAttendance'  
  
SELECT * FROM Students  
SELECT * FROM Courses  
SELECT * FROM CourseAttendance  
  
EXECUTE sp_xml_removedocument @h  
```  
  
### <a name="k-retrieving-binary-from-base64-encoded-data-in-xml"></a><span data-ttu-id="41d06-285">Л.</span><span class="sxs-lookup"><span data-stu-id="41d06-285">K.</span></span> <span data-ttu-id="41d06-286">Получение двоичных данных из данных в XML, закодированных методом base64</span><span class="sxs-lookup"><span data-stu-id="41d06-286">Retrieving binary from base64 encoded data in XML</span></span>  
 <span data-ttu-id="41d06-287">Двоичные данные часто включаются в XML с использованием метода кодировки base64.</span><span class="sxs-lookup"><span data-stu-id="41d06-287">Binary data is frequently included in XML using base64 encoding.</span></span> <span data-ttu-id="41d06-288">Если взять часть этого XML с помощью инструкции OPENXML, то будут получены данные, закодированные методом base64.</span><span class="sxs-lookup"><span data-stu-id="41d06-288">When you shred this XML by using OPENXML, you receive the base64 encoded data.</span></span> <span data-ttu-id="41d06-289">Этот пример показывает, как можно преобразовать данные в кодировке Base 64 обратно в двоичные.</span><span class="sxs-lookup"><span data-stu-id="41d06-289">This example shows how you can convert the base64 encoded data back to binary.</span></span>  
  
-   <span data-ttu-id="41d06-290">создайте таблицу с образцами двоичных данных;</span><span class="sxs-lookup"><span data-stu-id="41d06-290">Create a table with sample binary data.</span></span>  
  
-   <span data-ttu-id="41d06-291">используйте запрос FOR XML и параметр BINARY BASE64 для формирования XML, который содержит двоичные данные, закодированные методом base64;</span><span class="sxs-lookup"><span data-stu-id="41d06-291">Use a FOR XML query and the BINARY BASE64 option to construct XML that has the binary data encoded as base64.</span></span>  
  
-   <span data-ttu-id="41d06-292">возьмите часть XML с помощью инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="41d06-292">Shred the XML by using OPENXML.</span></span> <span data-ttu-id="41d06-293">Данные, возвращенные инструкцией OPENXML, будут данными, закодированными методом base64.</span><span class="sxs-lookup"><span data-stu-id="41d06-293">The data returned by OPENXML will be base64 encoded data.</span></span> <span data-ttu-id="41d06-294">Затем вызовите функцию .value для преобразования этих данных в двоичные.</span><span class="sxs-lookup"><span data-stu-id="41d06-294">Next, call the .value function to convert it back to binary.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 varbinary(100))  
go  
-- Insert sample binary data  
INSERT T VALUES(1, 0x1234567890)   
go  
 -- Create test XML document that has base64 encoded binary data (use FOR XML query and specify BINARY BASE64 option)  
SELECT * FROM T  
FOR XML AUTO, BINARY BASE64  
go  
-- result  
-- <T Col1="1" Col2="EjRWeJA="/>  
  
-- Now shredd the sample XML using OPENXML.   
-- Call the .value function to convert   
-- the base64 encoded data returned by OPENXML to binary.  
DECLARE @h int ;  
EXEC sp_xml_preparedocument @h OUTPUT, '<T Col1="1" Col2="EjRWeJA="/>' ;  
SELECT Col1,   
CAST('<binary>' + Col2 + '</binary>' AS XML).value('.', 'varbinary(max)') AS BinaryCol   
FROM openxml(@h, '/T')   
WITH (Col1 integer, Col2 varchar(max)) ;  
EXEC sp_xml_removedocument @h ;  
GO  
```  
  
 Результат. <span data-ttu-id="41d06-296">возвращенные двоичные данные являются исходными двоичными данными таблицы T:</span><span class="sxs-lookup"><span data-stu-id="41d06-296">The binary data returned is the original binary data in table T.</span></span>  
  
```  
Col1        BinaryCol  
----------- ---------------------  
1           0x1234567890  
```  
  
## <a name="see-also"></a><span data-ttu-id="41d06-297">См. также:</span><span class="sxs-lookup"><span data-stu-id="41d06-297">See Also</span></span>  
 <span data-ttu-id="41d06-298">[sp_xml_preparedocument (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41d06-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span></span>  
 <span data-ttu-id="41d06-299">[sp_xml_removedocument (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41d06-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span></span>  
 <span data-ttu-id="41d06-300">[OPENXML (Transact-SQL)](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41d06-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="41d06-301">OPENXML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41d06-301">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
