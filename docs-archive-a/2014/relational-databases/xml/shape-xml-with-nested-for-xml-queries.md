---
title: Формирование XML-кода с вложенными запросами FOR XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], nested FOR XML
- XML [SQL Server], FOR XML queries
ms.assetid: 8dc42c05-16e8-4b7b-a5d3-550b55acae26
author: rothja
ms.author: jroth
ms.openlocfilehash: 738b5b3ec67dada90c851d284ccc8b3009a51aa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665895"
---
# <a name="shape-xml-with-nested-for-xml-queries"></a><span data-ttu-id="dffce-102">Формирование XML-кода с вложенными запросами FOR XML</span><span class="sxs-lookup"><span data-stu-id="dffce-102">Shape XML with Nested FOR XML Queries</span></span>
  <span data-ttu-id="dffce-103">В следующем примере к таблице `Production.Product` выполняется запрос, чтобы получить значения `ListPrice` и `StandardCost` указанного продукта.</span><span class="sxs-lookup"><span data-stu-id="dffce-103">The following example queries the `Production.Product` table to retrieve the `ListPrice` and `StandardCost` values of a specific product.</span></span> <span data-ttu-id="dffce-104">Чтобы сделать пример более информативным, обе цены возвращаются как элемент <`Price`> и у каждого элемента <`Price`> имеется атрибут `PriceType`.</span><span class="sxs-lookup"><span data-stu-id="dffce-104">To make the query interesting, both prices are returned in a <`Price`> element, and each <`Price`> element has a `PriceType` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dffce-105">Пример</span><span class="sxs-lookup"><span data-stu-id="dffce-105">Example</span></span>  
 <span data-ttu-id="dffce-106">Это прогнозируемая форма XML:</span><span class="sxs-lookup"><span data-stu-id="dffce-106">This is the expected shape of the XML:</span></span>  
  
```  
<xsd:schema xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet2" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet2" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.Product" type="xsd:anyType" />  
</xsd:schema>  
<Production.Product xmlns="urn:schemas-microsoft-com:sql:SqlRowSet2" ProductID="520">  
  <Price xmlns="" PriceType="ListPrice">133.34</Price>  
  <Price xmlns="" PriceType="StandardCost">98.77</Price>  
</Production.Product>  
```  
  
 <span data-ttu-id="dffce-107">Это вложенный запрос FOR XML:</span><span class="sxs-lookup"><span data-stu-id="dffce-107">This is the nested FOR XML query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Product.ProductID,   
          (SELECT 'ListPrice' as PriceType,   
                   CAST(CAST(ListPrice as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE),  
          (SELECT  'StandardCost' as PriceType,   
                   CAST(CAST(StandardCost as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE)  
FROM Production.Product  
WHERE ProductID=520  
for XML AUTO, TYPE, XMLSCHEMA  
```  
  
 <span data-ttu-id="dffce-108">Обратите внимание на следующие данные из предыдущего запроса:</span><span class="sxs-lookup"><span data-stu-id="dffce-108">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="dffce-109">Внешняя инструкция SELECT строит элемент <`Product`>, который имеет атрибут **ProductID** и два дочерних элемента <`Price`>.</span><span class="sxs-lookup"><span data-stu-id="dffce-109">The outer SELECT statement constructs the <`Product`> element that has a **ProductID** attribute and two <`Price`> child elements.</span></span>  
  
-   <span data-ttu-id="dffce-110">Две внутренние инструкции SELECT создают два элемента <`Price`>, каждый с атрибутом **PriceType**, а также XML, который возвращает цену продукта.</span><span class="sxs-lookup"><span data-stu-id="dffce-110">The two inner SELECT statements construct two <`Price`> elements, each with a **PriceType** attribute and XML that returns the product price.</span></span>  
  
-   <span data-ttu-id="dffce-111">Директива XMLSCHEMA во внешней инструкции SELECT создает встроенную XSD-схему, которая описывает форму результирующего XML.</span><span class="sxs-lookup"><span data-stu-id="dffce-111">The XMLSCHEMA directive in the outer SELECT statement generates the inline XSD schema that describes the shape of the resulting XML.</span></span>  
  
 <span data-ttu-id="dffce-112">Чтобы сделать запрос более информативным, можно составить запрос FOR XML, а затем подготовить запрос XQuery к результату для переформирования XML, как показано в следующем запросе:</span><span class="sxs-lookup"><span data-stu-id="dffce-112">To make the query interesting, you can write the FOR XML query and then write an XQuery against the result to reshape the XML, as shown in the following query:</span></span>  
  
```  
SELECT ProductID,   
 ( SELECT p2.ListPrice, p2.StandardCost  
   FROM Production.Product p2   
   WHERE Product.ProductID = p2.ProductID  
   FOR XML AUTO, ELEMENTS XSINIL, type ).query('  
                                   for $p in /p2/*  
                                   return   
                                    <Price PriceType = "{local-name($p)}">  
                                     { data($p) }  
                                    </Price>  
                                  ')  
FROM Production.Product  
WHERE ProductID = 520  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="dffce-113">В предыдущем примере метод `query()` типа данных `xml` используется, чтобы запросить XML, возвращаемый внутренним запросом FOR XML, и построить прогнозируемый результат.</span><span class="sxs-lookup"><span data-stu-id="dffce-113">The previous example uses the `query()` method of the `xml` data type to query the XML returned by the inner FOR XML query and construct the expected result.</span></span>  
  
 <span data-ttu-id="dffce-114">Результат:</span><span class="sxs-lookup"><span data-stu-id="dffce-114">This is the result:</span></span>  
  
```  
<Production.Product ProductID="520">  
  <Price PriceType="ListPrice">133.3400</Price>  
  <Price PriceType="StandardCost">98.7700</Price>  
</Production.Product>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dffce-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="dffce-115">See Also</span></span>  
 [<span data-ttu-id="dffce-116">Использование вложенных запросов FOR XML</span><span class="sxs-lookup"><span data-stu-id="dffce-116">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
