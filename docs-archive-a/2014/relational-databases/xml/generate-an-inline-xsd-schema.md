---
title: Создание встроенных схем XSD | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- XMLSCHEMA option
- schemas [SQL Server], XML
- XDR schemas
- FOR XML clause, inline XSD schema generation
- inline XSD schema generation [SQL Server]
- XMLDATA option
ms.assetid: 04b35145-1cca-45f4-9eb7-990abf2e647d
author: rothja
ms.author: jroth
ms.openlocfilehash: 2af748d4fc6ae67f57568be58ec7f59876098f52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751971"
---
# <a name="generate-an-inline-xsd-schema"></a><span data-ttu-id="40cbf-102">Создание встроенных схем XSD</span><span class="sxs-lookup"><span data-stu-id="40cbf-102">Generate an Inline XSD Schema</span></span>
  <span data-ttu-id="40cbf-103">В предложении FOR XML можно запросить, чтобы запрос возвращал встроенную схему вместе с результатами запроса.</span><span class="sxs-lookup"><span data-stu-id="40cbf-103">In a FOR XML clause, you can request that your query return an inline schema together with the query results.</span></span> <span data-ttu-id="40cbf-104">Если нужно получить XDR-схему, то в предложении FOR XML следует использовать ключевое слово XMLDATA.</span><span class="sxs-lookup"><span data-stu-id="40cbf-104">If you want an XDR schema, you use the XMLDATA keyword in the FOR XML clause.</span></span> <span data-ttu-id="40cbf-105">Если нужно получить XSD-схему, то тогда следует использовать ключевое слово XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="40cbf-105">If you want an XSD schema, you use the XMLSCHEMA keyword.</span></span>  
  
 <span data-ttu-id="40cbf-106">В этом разделе описывается ключевое слово XMLSCHEMA и объясняется структура результирующей встроенной XSD-схемы.</span><span class="sxs-lookup"><span data-stu-id="40cbf-106">This topic describes the XMLSCHEMA keyword and explains the structure of the resulting inline XSD schema.</span></span> <span data-ttu-id="40cbf-107">Далее приведены ограничения, возникающие при запросе встроенных схем.</span><span class="sxs-lookup"><span data-stu-id="40cbf-107">Following are the limitations when you are requesting inline schemas:</span></span>  
  
-   <span data-ttu-id="40cbf-108">Параметр XMLSCHEMA можно задать только в режимах RAW и AUTO, этого нельзя сделать в режиме EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="40cbf-108">You can specify XMLSCHEMA only in RAW and AUTO mode, not in EXPLICIT mode.</span></span>  
  
-   <span data-ttu-id="40cbf-109">Если во вложенном запросе FOR XML определена директива TYPE, результат запроса будет иметь тип данных `xml` и передаваться за экземпляр нетипизированных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="40cbf-109">If a nested FOR XML query specifies the TYPE directive, the query result is of `xml` type, and this result is treated as an instance of untyped XML data.</span></span> <span data-ttu-id="40cbf-110">Дополнительные сведения см в разделе [Данные XML (SQL Server)](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="40cbf-110">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="40cbf-111">Если в запросе FOR XML задан параметр XMLSCHEMA, то в результат запроса входит и схема, и XML-данные.</span><span class="sxs-lookup"><span data-stu-id="40cbf-111">When you specify XMLSCHEMA in a FOR XML query, you receive both a schema and XML data, the query result.</span></span> <span data-ttu-id="40cbf-112">Каждый элемент данных высшего уровня ссылается на предыдущую схему посредством заданного по умолчанию объявления пространства имен, которое, в свою очередь, ссылается на целевое пространство имен встроенной схемы.</span><span class="sxs-lookup"><span data-stu-id="40cbf-112">Each top-level element of the data refers to the previous schema by using a default namespace declaration that, in turn, refers to the target namespace of the inline schema.</span></span>  
  
 <span data-ttu-id="40cbf-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="40cbf-113">For example:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks2012].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<Production.ProductModel xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="1" Name="Classic Vest" />  
```  
  
 <span data-ttu-id="40cbf-114">В результат входит XML-схема и XML-результат.</span><span class="sxs-lookup"><span data-stu-id="40cbf-114">The result includes XML schema and the XML result.</span></span> <span data-ttu-id="40cbf-115">Элемент результата высшего уровня <`ProductModel`> ссылается на схему посредством заданного по умолчанию объявления пространства имен, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1".</span><span class="sxs-lookup"><span data-stu-id="40cbf-115">The <`ProductModel`> top-level element in the result refers to the schema by using the default namespace declaration, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" .</span></span>  
  
 <span data-ttu-id="40cbf-116">В присутствующей в результате схеме может находиться множество документов схемы, описывающих различные пространства имен.</span><span class="sxs-lookup"><span data-stu-id="40cbf-116">The schema part of the result may contain multiple schema documents that describe multiple namespaces.</span></span> <span data-ttu-id="40cbf-117">Возвращаться должны, как минимум, следующие две схемы.</span><span class="sxs-lookup"><span data-stu-id="40cbf-117">At a minimum, the following two schema documents are returned:</span></span>  
  
-   <span data-ttu-id="40cbf-118">Один документ схемы для пространства имен **Sqltypes** , для которого возвращаются базовые типы SQL.</span><span class="sxs-lookup"><span data-stu-id="40cbf-118">One schema document for the **Sqltypes** namespace, and for which the base SQL types are being returned.</span></span>  
  
-   <span data-ttu-id="40cbf-119">Другой документ схемы, описывающий форму результата запроса FOR XML.</span><span class="sxs-lookup"><span data-stu-id="40cbf-119">Another schema document that describes the shape of the FOR XML query result.</span></span>  
  
 <span data-ttu-id="40cbf-120">Кроме того, если в результат запроса входят какие-либо типизированные типы данных `xml`, то возвращаются схемы, связанные с этими типами данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="40cbf-120">Also, if any typed `xml` data types are included in the query result, the schemas associated with those typed `xml` data types are included.</span></span>  
  
 <span data-ttu-id="40cbf-121">Целевое пространство имен документа схемы, описывающее форму результата FOR XML, содержит фиксированную часть и числовую часть, которая автоматически увеличивается.</span><span class="sxs-lookup"><span data-stu-id="40cbf-121">The target namespace of the schema document that describes the shape of the FOR XML result contains a fixed portion and a numeric portion that increments automatically.</span></span> <span data-ttu-id="40cbf-122">Далее показан формат данного пространства имен, где *n* является положительным целым числом.</span><span class="sxs-lookup"><span data-stu-id="40cbf-122">The format of this namespace is shown in the following where *n* is a positive integer.</span></span> <span data-ttu-id="40cbf-123">Например, в предыдущем запросе целевым пространством имен было urn:schemas-microsoft-com:sql:SqlRowSet1.</span><span class="sxs-lookup"><span data-stu-id="40cbf-123">For example, in the previous query, urn:schemas-microsoft-com:sql:SqlRowSet1 is the target namespace.</span></span>  
  
```  
urn:schemas-microsoft-com:sql:SqlRowSetn  
```  
  
 <span data-ttu-id="40cbf-124">Изменения в целевых пространствах имен в результате, произошедшем между двумя выполнениями, могут быть нежелательны.</span><span class="sxs-lookup"><span data-stu-id="40cbf-124">The change in the target namespaces in the result that occurred from one execution to another may not be desirable.</span></span> <span data-ttu-id="40cbf-125">Например, если запрашивается результирующий XML, то при изменении в целевых пространствах имен необходимо обновить запрос.</span><span class="sxs-lookup"><span data-stu-id="40cbf-125">For example, if you query the resulting XML, the change in target namespace will require that you update your query.</span></span> <span data-ttu-id="40cbf-126">При необходимости можно задать целевое пространство имен, когда в предложение FOR XML добавлен параметр XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="40cbf-126">You can optionally specify a target namespace when the XMLSCHEMA option is added in the FOR XML clause.</span></span> <span data-ttu-id="40cbf-127">Результирующий XML будет содержать указанное пространство имен и оставаться неизменным независимо от того, сколько раз выполняли запрос.</span><span class="sxs-lookup"><span data-stu-id="40cbf-127">The resulting XML will include the namespace you provided and will remain the same, regardless of how many times you run the query.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM   Production.ProductModel  
WHERE ProductModelID=1  
FOR XML AUTO, XMLSCHEMA ('MyURI')  
```  
  
## <a name="entity-elements"></a><span data-ttu-id="40cbf-128">Элементы сущности</span><span class="sxs-lookup"><span data-stu-id="40cbf-128">Entity Elements</span></span>  
 <span data-ttu-id="40cbf-129">Для описания особенностей создания структуры XSD-схемы для результата запроса необходимо вначале привести общие сведения про элемент сущности.</span><span class="sxs-lookup"><span data-stu-id="40cbf-129">In order to discuss the details of the XSD schema structure generated for the query result, the entity element has to first be described</span></span>  
  
 <span data-ttu-id="40cbf-130">Элемент сущности XML-данных, возвращаемых запросом FOR XML, является элементом, создаваемым таблицей, а не столбцом.</span><span class="sxs-lookup"><span data-stu-id="40cbf-130">An entity element in the XML data returned by FOR XML query is an element that is generated from a table and not from a column.</span></span> <span data-ttu-id="40cbf-131">Например, следующий запрос FOR XML возвращает контактную информацию из таблицы `Person` базы данных `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="40cbf-131">For example, the following FOR XML query returns contact information from the `Person` table in the `AdventureWorks2012` database.</span></span>  
  
```  
SELECT BusinessEntityID, FirstName  
FROM Person.Person  
WHERE BusinessEntityID = 1  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="40cbf-132">Результат:</span><span class="sxs-lookup"><span data-stu-id="40cbf-132">This is the result:</span></span>  
  
 `<Person>`  
  
 `<BusinessEntityID>1</BusinessEntityID>`  
  
 `<FirstName>Ken</FirstName>`  
  
 `</Person>`  
  
 <span data-ttu-id="40cbf-133">В этом результате элементом сущности является <`Person`>.</span><span class="sxs-lookup"><span data-stu-id="40cbf-133">In this result, <`Person`> is the entity element.</span></span> <span data-ttu-id="40cbf-134">В XML-результате может быть множество элементов сущности, и каждый из них должен обладать глобальным объявлением во встроенной XSD-схеме.</span><span class="sxs-lookup"><span data-stu-id="40cbf-134">There can be multiple entity elements in the XML result and each of these has a global declaration in the inline XSD schema.</span></span> <span data-ttu-id="40cbf-135">Например, следующий запрос извлекает из заголовка сведения о заказах на продажу, а также получает подробные данные о конкретном заказе.</span><span class="sxs-lookup"><span data-stu-id="40cbf-135">For example, the following query retrieves sales order header and detail information for a specific order.</span></span>  
  
```  
SELECT  SalesOrderHeader.SalesOrderID, ProductID, OrderQty  
FROM    Sales.SalesOrderHeader, Sales.SalesOrderDetail  
WHERE   SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
AND     SalesOrderHeader.SalesOrderID=5001  
FOR XML AUTO, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="40cbf-136">Из-за того, что в запрос добавлена директива ELEMENTS, XML-результат формируется с использованием элементов.</span><span class="sxs-lookup"><span data-stu-id="40cbf-136">Because the query specifies the ELEMENTS directive, the resulting XML is element-centric.</span></span> <span data-ttu-id="40cbf-137">Также в этом запросе задана директива XMLSCHEMA,</span><span class="sxs-lookup"><span data-stu-id="40cbf-137">The query also specifies the XMLSCHEMA directive.</span></span> <span data-ttu-id="40cbf-138">поэтому возвращается встроенная XSD-схема.</span><span class="sxs-lookup"><span data-stu-id="40cbf-138">Therefore, an inline XSD schema is returned.</span></span> <span data-ttu-id="40cbf-139">Результат:</span><span class="sxs-lookup"><span data-stu-id="40cbf-139">This is the result:</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="Sales.SalesOrderHeader">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="SalesOrderID" type="sqltypes:int" />`  
  
 `<xsd:element ref="schema:Sales.SalesOrderDetail" minOccurs="0" maxOccurs="unbounded" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `<xsd:element name="Sales.SalesOrderDetail">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="OrderQty" type="sqltypes:smallint" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 <span data-ttu-id="40cbf-140">Обратите внимание на следующие данные из предыдущего запроса:</span><span class="sxs-lookup"><span data-stu-id="40cbf-140">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="40cbf-141">В этом результате элементами сущности являются <`SalesOrderHeader`> и <`SalesOrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="40cbf-141">In the result, <`SalesOrderHeader`> and <`SalesOrderDetail`> are entity elements.</span></span> <span data-ttu-id="40cbf-142">Из-за этого они глобально объявлены в схеме.</span><span class="sxs-lookup"><span data-stu-id="40cbf-142">Because of this, they are globally declared in the schema.</span></span> <span data-ttu-id="40cbf-143">То есть объявление появляется на высшем уровне элемента <`Schema`>.</span><span class="sxs-lookup"><span data-stu-id="40cbf-143">That is, the declaration appears at the top level inside the <`Schema`> element.</span></span>  
  
-   <span data-ttu-id="40cbf-144"><`SalesOrderID`>, <`ProductID`> и <`OrderQty`> не являются элементами сущности, так как они сопоставлены столбцам.</span><span class="sxs-lookup"><span data-stu-id="40cbf-144">The <`SalesOrderID`>, <`ProductID`>, and <`OrderQty`> are not entity elements, because they map to columns.</span></span> <span data-ttu-id="40cbf-145">Из-за директивы ELEMENTS данные столбца возвращаются в виде элементов в XML.</span><span class="sxs-lookup"><span data-stu-id="40cbf-145">The column data is returned as elements in the XML, because of the ELEMENTS directive.</span></span> <span data-ttu-id="40cbf-146">Они сопоставлены локальным элементам сложного типа элемента сущности.</span><span class="sxs-lookup"><span data-stu-id="40cbf-146">These are mapped to local elements of the entity element's complex type.</span></span> <span data-ttu-id="40cbf-147">Заметьте, что если директива ELEMENTS не задана, то значения `SalesOrderID`, `ProductID` и `OrderQty` сопоставляются с локальными атрибутами соответствующего сложного типа элемента сущности.</span><span class="sxs-lookup"><span data-stu-id="40cbf-147">Note that if the ELEMENTS directive is not specified, the `SalesOrderID`, `ProductID` and `OrderQty` values are mapped to local attributes of the corresponding entity element's complex type.</span></span>  
  
## <a name="attribute-name-clashes"></a><span data-ttu-id="40cbf-148">Конфликты имен атрибутов</span><span class="sxs-lookup"><span data-stu-id="40cbf-148">Attribute Name Clashes</span></span>  
 <span data-ttu-id="40cbf-149">В следующих рассуждениях используются таблицы `CustOrder` и `CustOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="40cbf-149">The following discussion is based on the `CustOrder` and `CustOrderDetail` tables.</span></span> <span data-ttu-id="40cbf-150">Для проверки следующих образцов создайте такие же таблицы и добавьте собственные образцы данных:</span><span class="sxs-lookup"><span data-stu-id="40cbf-150">To test the following samples, create these tables and add your own sample data:</span></span>  
  
```  
CREATE TABLE CustOrder (OrderID int primary key, CustomerID int)  
GO  
CREATE TABLE CustOrderDetail (OrderID int, ProductID int, Qty int)  
GO  
```  
  
 <span data-ttu-id="40cbf-151">В предложении FOR XML одинаковые имена иногда соответствуют различным свойствам и атрибутам.</span><span class="sxs-lookup"><span data-stu-id="40cbf-151">In FOR XML, the same name is sometimes used to indicate different properties, attributes.</span></span> <span data-ttu-id="40cbf-152">Например, следующий атрибутивный запрос режима RAW создает два атрибута с одним и тем же именем — OrderID.</span><span class="sxs-lookup"><span data-stu-id="40cbf-152">For example, the following attribute-centric RAW mode query generates two attributes that have the same name, OrderID.</span></span> <span data-ttu-id="40cbf-153">Это приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="40cbf-153">This generates an error.</span></span>  
  
```  
SELECT CustOrder.OrderID,   
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
FROM   dbo.CustOrder, dbo.CustOrderDetail  
WHERE  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA  
```  
  
 <span data-ttu-id="40cbf-154">Однако так как двум элементам допустимо иметь одно и то же имя, можно решить проблему добавлением директивы ELEMENTS:</span><span class="sxs-lookup"><span data-stu-id="40cbf-154">However, because it is acceptable to have two elements that have the same name, you can eliminate the problem by adding the ELEMENTS directive:</span></span>  
  
```  
SELECT CustOrder.OrderID,  
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
from   dbo.CustOrder, dbo.CustOrderDetail  
where  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA, ELEMENTS  
```  
  
 <span data-ttu-id="40cbf-155">Результат.</span><span class="sxs-lookup"><span data-stu-id="40cbf-155">This is the result.</span></span> <span data-ttu-id="40cbf-156">Обратите внимание, что во встроенной XSD-схеме элемент OrderID определяется два раза.</span><span class="sxs-lookup"><span data-stu-id="40cbf-156">Note in the inline XSD schema, the OrderID element is defined two times.</span></span> <span data-ttu-id="40cbf-157">В одной из деклараций атрибуту minOccurs присваивается значение 0, соответствующее столбцу OrderID таблицы CustOrderDetail, во второй декларации устанавливается соответствие первичному ключевому столбцу OrderID таблицы `CustOrder` , и этот атрибут имеет значение 1 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40cbf-157">One of the declarations has minOccurs set to 0, corresponding to the OrderID from the CustOrderDetail table, and the second one maps to the OrderID primary key column of the `CustOrder` table where minOccurs is 1 by default.</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" />`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" minOccurs="0" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
## <a name="element-name-clashes"></a><span data-ttu-id="40cbf-158">Конфликты имен элементов</span><span class="sxs-lookup"><span data-stu-id="40cbf-158">Element Name Clashes</span></span>  
 <span data-ttu-id="40cbf-159">В предложении FOR XML одинаковые имена иногда соответствуют различным подэлементам.</span><span class="sxs-lookup"><span data-stu-id="40cbf-159">In FOR XML, the same name can be used to indicate two subelements.</span></span> <span data-ttu-id="40cbf-160">Например, следующий запрос получает значения продуктов ListPrice и DealerPrice, но определяет для этих двух столбцов один и тот же псевдоним Price.</span><span class="sxs-lookup"><span data-stu-id="40cbf-160">For example, the following query retrieves ListPrice and DealerPrice values of products, but the query specifies the same alias, Price, for these two columns.</span></span> <span data-ttu-id="40cbf-161">Поэтому в результирующем наборе строк будут присутствовать два столбца с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="40cbf-161">Therefore, the resulting rowset will have two columns with same name.</span></span>  
  
### <a name="case-1-both-subelements-are-nonkey-columns-of-the-same-type-and-can-be-null"></a><span data-ttu-id="40cbf-162">Вариант 1. Оба подэлемента являются неключевыми столбцами одинакового типа и могут иметь значение NULL</span><span class="sxs-lookup"><span data-stu-id="40cbf-162">Case 1: Both subelements are nonkey columns of the same type and can be NULL</span></span>  
 <span data-ttu-id="40cbf-163">В следующем запросе оба подэлемента являются неключевыми столбцами одинакового типа и могут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="40cbf-163">In the following query, both subelements are nonkey columns of the same type and can be NULL.</span></span>  
  
```  
DROP TABLE T  
go  
CREATE TABLE T (ProductID int primary key, ListPrice money, DealerPrice money)  
go  
INSERT INTO T values (1, 1.25, null)  
go  
  
SELECT ProductID, ListPrice Price, DealerPrice Price  
FROM   T  
for    XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="40cbf-164">Это получаемый в результате XML.</span><span class="sxs-lookup"><span data-stu-id="40cbf-164">This is the corresponding XML generated.</span></span> <span data-ttu-id="40cbf-165">Показана только часть встроенной XSD:</span><span class="sxs-lookup"><span data-stu-id="40cbf-165">Only a fraction of the inline XSD is shown:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" minOccurs="0" maxOccurs="2" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `</row>`  
  
 <span data-ttu-id="40cbf-166">Обратите внимание на следующее во встроенной XSD-схеме.</span><span class="sxs-lookup"><span data-stu-id="40cbf-166">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="40cbf-167">Оба значения, ListPrice и DealerPrice, имеют один и тот же тип данных, `money`, и оба могут иметь в таблице значение NULL.</span><span class="sxs-lookup"><span data-stu-id="40cbf-167">Both the ListPrice and DealerPrice are of the same type, `money`, and both can be NULL in the table.</span></span> <span data-ttu-id="40cbf-168">Таким образом, из-за того, что они могут не возвращаться в результирующем XML, в декларации сложного типа элемента <`row`> может быть только один дочерний элемент <`Price`> с параметрами minOccurs=0 и maxOccurs=2.</span><span class="sxs-lookup"><span data-stu-id="40cbf-168">Therefore, because they may not be returned in the resulting XML, there is only one <`Price`> child element in the complex type declaration of the <`row`> element that has minOccurs=0 and maxOccurs=2.</span></span>  
  
-   <span data-ttu-id="40cbf-169">В результате из-за того, что значение `DealerPrice` в таблице равно NULL, в качестве элемента <`Price`> возвращается только значение `ListPrice`.</span><span class="sxs-lookup"><span data-stu-id="40cbf-169">In the result, because the `DealerPrice` value is NULL in the table, only `ListPrice` is returned as a <`Price`> element.</span></span> <span data-ttu-id="40cbf-170">При добавлении параметра `XSINIL` к директиве ELEMENTS будут получены оба элемента со значением `xsi:nil`, равным TRUE, для элемента <`Price`>, соответствующего DealerPrice.</span><span class="sxs-lookup"><span data-stu-id="40cbf-170">If you add the `XSINIL` parameter to the ELEMENTS directive, you will receive both of the elements that have the `xsi:nil` value set to TRUE for the<`Price`> element that corresponds to DealerPrice.</span></span> <span data-ttu-id="40cbf-171">Также будут получены два дочерних элемента <`Price`> в определении сложного типа <`row`> во встроенной схеме XSD. Для обоих атрибут `nillable` будет установлен в значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="40cbf-171">You will also receive two <`Price`> child elements in the <`row`> complex type definition in the inline XSD schema with the `nillable` attribute set to TRUE for both.</span></span> <span data-ttu-id="40cbf-172">Это промежуточный результат:</span><span class="sxs-lookup"><span data-stu-id="40cbf-172">This fragment is a partial result:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `<Price xsi:nil="true" />`  
  
 `</row>`  
  
### <a name="case-2-one-key-and-one-nonkey-column-of-the-same-type"></a><span data-ttu-id="40cbf-173">Вариант 2. Один ключевой столбец и один неключевой столбец одинакового типа</span><span class="sxs-lookup"><span data-stu-id="40cbf-173">Case 2: One key and one nonkey column of the same type</span></span>  
 <span data-ttu-id="40cbf-174">В следующем запросе находится один ключевой столбец и один неключевой столбец одинакового типа.</span><span class="sxs-lookup"><span data-stu-id="40cbf-174">The following query illustrates one key and one nonkey column of the same type.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 int, Col3 nvarchar(20))  
go  
INSERT INTO T VALUES (1, 1, 'test')  
go   
```  
  
 <span data-ttu-id="40cbf-175">Следующий запрос по отношению к таблице **T** задает один и тот же псевдоним для Col1 и Col2, где Col1 является столбцом первичного ключа и не может быть нулевым, а Col2 может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="40cbf-175">The following query against table **T** specifies the same alias for Col1 and Col2, where Col1 is a primary key and cannot be null, and Col2 can be null.</span></span> <span data-ttu-id="40cbf-176">Это приводит к созданию двух элементов, являющихся дочерними элементами элемента <`row`>.</span><span class="sxs-lookup"><span data-stu-id="40cbf-176">This generates two sibling elements that are children of the <`row`> element.</span></span>  
  
```  
SELECT Col1 as Col, Col2 as Col, Col3  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="40cbf-177">Результат.</span><span class="sxs-lookup"><span data-stu-id="40cbf-177">This is the result.</span></span> <span data-ttu-id="40cbf-178">Показана только часть встроенной XSD-схемы:</span><span class="sxs-lookup"><span data-stu-id="40cbf-178">Only a fragment of the inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="Col3" minOccurs="0">`  
  
 `<xsd:simpleType>`  
  
 `<xsd:restriction base="sqltypes:nvarchar"`  
  
 `sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth"`  
  
 `sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `</xsd:element>`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col>1</Col>`  
  
 `<Col>1</Col>`  
  
 `<Col3>test</Col3>`  
  
 `</row>`  
  
 <span data-ttu-id="40cbf-179">Обратите внимание, что во встроенной XSD-схеме элемент <`Col`> соответствует столбцу Col2 с параметром minOccurs, равным 0.</span><span class="sxs-lookup"><span data-stu-id="40cbf-179">Note in the inline XSD schema that the <`Col`> element corresponding to the Col2 has minOccurs set to 0.</span></span>  
  
### <a name="case-3-both-elements-of-different-types-and-corresponding-columns-can-be-null"></a><span data-ttu-id="40cbf-180">Случай 3. Оба элемента разных типов и соответствующие столбцы могут иметь значение NULL</span><span class="sxs-lookup"><span data-stu-id="40cbf-180">Case 3: Both elements of different types and corresponding columns can be NULL</span></span>  
 <span data-ttu-id="40cbf-181">Для случая 2 показан следующий запрос, заданный относительно таблицы-образца:</span><span class="sxs-lookup"><span data-stu-id="40cbf-181">The following query is specified against the sample table shown in case 2:</span></span>  
  
```  
SELECT Col1, Col2 as Col, Col3 as Col  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="40cbf-182">В этом запросе Col2 и Col3 обладают одинаковыми псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="40cbf-182">In the following query, Col2 and Col3 are given the same aliases.</span></span> <span data-ttu-id="40cbf-183">Это приводит к появлению двух элементов с одинаковыми именами, являющихся дочерними элементами элемента <`raw`> в результате.</span><span class="sxs-lookup"><span data-stu-id="40cbf-183">This generates two sibling elements that have the same name and that are both children of the <`raw`> element in the result.</span></span> <span data-ttu-id="40cbf-184">Оба столбца принадлежат различным типам и могут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="40cbf-184">Both of these columns are of different types and both can be NULL.</span></span> <span data-ttu-id="40cbf-185">Результат.</span><span class="sxs-lookup"><span data-stu-id="40cbf-185">This is the result.</span></span> <span data-ttu-id="40cbf-186">Показана только часть встроенной XSD-схемы.</span><span class="sxs-lookup"><span data-stu-id="40cbf-186">Only partial inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:simpleType name="Col1">`  
  
 `<xsd:restriction base="sqltypes:int" />`  
  
 `</xsd:simpleType>`  
  
 `<xsd:simpleType name="Col2">`  
  
 `<xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col1" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" minOccurs="0" maxOccurs="2" type="xsd:anySimpleType" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col1>1</Col1>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col1">1</Col>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col2">test</Col>`  
  
 `</row>`  
  
 <span data-ttu-id="40cbf-187">Обратите внимание на следующее во встроенной XSD-схеме.</span><span class="sxs-lookup"><span data-stu-id="40cbf-187">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="40cbf-188">Так как Col2 и Col3 могут иметь значение NULL, то объявление элемента <`Col`> определяет minOccurs равным 0, а maxOccurs равным 2.</span><span class="sxs-lookup"><span data-stu-id="40cbf-188">Because both Col2 and Col3 can be NULL, the <`Col`> element declaration specifies the minOccurs as 0 and maxOccurs as 2.</span></span>  
  
-   <span data-ttu-id="40cbf-189">Из-за того, что элементы <`Col`> имеют общего родителя, в схеме присутствует только одно объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="40cbf-189">Because both the <`Col`> elements are siblings, there is one element declaration in the schema.</span></span> <span data-ttu-id="40cbf-190">Также из-за того, что оба элемента относятся к различным типам (хотя оба эти типа простые), типом элемента в схеме является `xsd:anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="40cbf-190">Also, because both of the elements are also of different types, though both are simple types, the type of the element in the schema is `xsd:anySimpleType`.</span></span> <span data-ttu-id="40cbf-191">В результате тип каждого экземпляра определяется атрибутом `xsi:type` .</span><span class="sxs-lookup"><span data-stu-id="40cbf-191">In the result, each instance type is identified by the `xsi:type` attribute.</span></span>  
  
-   <span data-ttu-id="40cbf-192">В результате каждый экземпляр элемента <`Col`> ссылается на свой тип экземпляра при помощи атрибута `xsi:type`.</span><span class="sxs-lookup"><span data-stu-id="40cbf-192">In the result, every instance of the <`Col`> element refers to its instance type by using the `xsi:type` attribute.</span></span>  
  
  
