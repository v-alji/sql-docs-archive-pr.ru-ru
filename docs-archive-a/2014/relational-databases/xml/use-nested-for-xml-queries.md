---
title: Использование вложенных запросов FOR XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], nested FOR XML
- nested FOR XML queries
ms.assetid: 7604161a-a958-446d-b102-7dee432979d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 60c4198697f8d19c9b2e5bc1b415e0787861d40a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738057"
---
# <a name="use-nested-for-xml-queries"></a><span data-ttu-id="8b4ae-102">Использование вложенных запросов FOR XML</span><span class="sxs-lookup"><span data-stu-id="8b4ae-102">Use Nested FOR XML Queries</span></span>
  <span data-ttu-id="8b4ae-103">`xml`Тип данных и [директива TYPE в ЗАПРОСАХ for XML](type-directive-in-for-xml-queries.md) позволяют обрабатывать XML-запросы, ВОЗВРАЩАЕМЫЕ запросами FOR XML, на сервере, а также на клиенте.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-103">The `xml` data type and the [TYPE directive in FOR XML queries](type-directive-in-for-xml-queries.md) enable the XML returned by the FOR XML queries to be processed on the server as well as on the client.</span></span>  
  
## <a name="processing-with-xml-type-variables"></a><span data-ttu-id="8b4ae-104">Обработка переменных типа XML</span><span class="sxs-lookup"><span data-stu-id="8b4ae-104">Processing with xml Type Variables</span></span>  
 <span data-ttu-id="8b4ae-105">Результат запроса FOR XML можно присвоить переменной типа `xml` или воспользоваться языком XQuery, чтобы выполнить к нему запрос, после чего присвоить полученный результат переменной типа `xml` для дополнительной обработки.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-105">You can assign the FOR XML query result to an `xml` type variable, or use XQuery to query the result, and assign that result to an `xml` type variable for more processing.</span></span>  
  
```  
DECLARE @x xml  
SET @x=(SELECT ProductModelID, Name  
        FROM Production.ProductModel  
        WHERE ProductModelID=122 or ProductModelID=119  
        FOR XML RAW, TYPE)  
SELECT @x  
-- Result  
--<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
--<row ProductModelID="119" Name="Bike Wash" />  
```  
  
 <span data-ttu-id="8b4ae-106">XML-данные, возвращаемые в переменной `@x`, можно дополнительно обработать с применением методов типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-106">You can additionally process the XML returned in the variable, `@x`, by using one of the `xml` data type methods.</span></span> <span data-ttu-id="8b4ae-107">Например, с помощью метода `ProductModelID` value() [можно получить значение атрибута](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="8b4ae-107">For example, you can retrieve the `ProductModelID` attribute value by using the [value() method](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
DECLARE @i int;  
SET @i = (SELECT @x.value('/row[1]/@ProductModelID[1]', 'int'));  
SELECT @i;  
```  
  
 <span data-ttu-id="8b4ae-108">В следующем примере результат запроса `FOR XML` возвращается в виде типа данных `xml`, так как в предложении `TYPE` указана директива `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-108">In the following example, the `FOR XML` query result is returned as an `xml` type, because the `TYPE` directive is specified in the `FOR XML` clause.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=119 or ProductModelID=122  
FOR XML RAW, TYPE,ROOT('myRoot');  
  
```  
  
 <span data-ttu-id="8b4ae-109">Результат:</span><span class="sxs-lookup"><span data-stu-id="8b4ae-109">This is the result:</span></span>  
  
```  
<myRoot>  
  <row ProductModelID="122" Name="All-Purpose Bike Stand" />  
  <row ProductModelID="119" Name="Bike Wash" />  
</myRoot>  
```  
  
 <span data-ttu-id="8b4ae-110">Поскольку результат имеет тип `xml`, непосредственно к нему можно применить один из методов типа данных `xml`, как показано в следующем запросе.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-110">Because the result is of `xml` type, you can specify one of the `xml` data type methods directly against this XML, as shown in the following query.</span></span> <span data-ttu-id="8b4ae-111">В запросе [метод query() (тип данных xml)](/sql/t-sql/xml/query-method-xml-data-type) используется для получения первого дочернего элемента <`row`> элемента <`myRoot`>.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-111">In the query, the [query() method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) is used to retrieve the first <`row`> element child of the <`myRoot`> element.</span></span>  
  
```  
SELECT  (SELECT ProductModelID, Name  
         FROM Production.ProductModel  
         WHERE ProductModelID=119 or ProductModelID=122  
         FOR XML RAW, TYPE,ROOT('myRoot')).query('/myRoot[1]/row[1]');  
  
```  
  
 <span data-ttu-id="8b4ae-112">Результат:</span><span class="sxs-lookup"><span data-stu-id="8b4ae-112">This is the result:</span></span>  
  
```  
<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
```  
  
## <a name="returning-inner-for-xml-query-results-to-outer-queries-as-xml-type-instances"></a><span data-ttu-id="8b4ae-113">Передача результатов внутреннего запроса FOR XML внешним запросам в виде экземпляров типа xml</span><span class="sxs-lookup"><span data-stu-id="8b4ae-113">Returning Inner FOR XML Query Results to Outer Queries as xml Type Instances</span></span>  
 <span data-ttu-id="8b4ae-114">Можно создать вложенные запросы `FOR XML`, в которых результат внутреннего запроса возвращает внешнему запросу данные типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-114">You can write nested `FOR XML` queries where the result of the inner query is returned as an `xml` type to the outer query.</span></span> <span data-ttu-id="8b4ae-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="8b4ae-115">For example:</span></span>  
  
```  
SELECT Col1,   
       Col2,   
       ( SELECT Col3, Col4   
        FROM  T2  
        WHERE T2.Col = T1.Col  
        ...  
        FOR XML AUTO, TYPE )  
FROM T1  
WHERE ...  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="8b4ae-116">Обратите внимание на следующие данные из предыдущего запроса:</span><span class="sxs-lookup"><span data-stu-id="8b4ae-116">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="8b4ae-117">XML-данные, сформированные внутренним запросом `FOR XML` , добавляются к XML-результату внешнего запроса `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-117">The XML generated by the inner `FOR XML` query is added to the XML generated by the outer `FOR XML`.</span></span>  
  
-   <span data-ttu-id="8b4ae-118">Во внутреннем запросе указана директива `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="8b4ae-118">The inner query specifies the `TYPE` directive.</span></span> <span data-ttu-id="8b4ae-119">Таким образом, возвращаемые внутренним запросом XML-данные имеют тип `xml`.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-119">Therefore, the XML data returned by the inner query is of `xml` type.</span></span> <span data-ttu-id="8b4ae-120">Если директива TYPE не указана, внутренний запрос `FOR XML` возвращает результат типа `nvarchar(max)` и XML-данные преобразуются в сущности.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-120">If the TYPE directive is not specified, the result of the inner `FOR XML` query is returned as `nvarchar(max)` and the XML data is entitized.</span></span>  
  
## <a name="controlling-the-shape-of-resulting-xml-data"></a><span data-ttu-id="8b4ae-121">Управление формой результирующих XML-данных</span><span class="sxs-lookup"><span data-stu-id="8b4ae-121">Controlling the Shape of Resulting XML Data</span></span>  
 <span data-ttu-id="8b4ae-122">Вложенные запросы FOR XML предоставляют больше возможностей управления формой результирующих XML-данных.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-122">Nested FOR XML queries give you more control in defining the shape of the resulting XML data.</span></span> <span data-ttu-id="8b4ae-123">При помощи вложенных запросов FOR XML можно конструировать XML-данные, сочетающие в себе атрибутивную и элементную модели.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-123">You can use nested FOR XML queries to construct XML that is partly attribute-centric and partly element-centric.</span></span>  
  
 <span data-ttu-id="8b4ae-124">Дополнительные сведения об указании атрибутивного и элементного XML с помощью вложенных запросов FOR XML см. в разделах [Сравнение запросов FOR XML и вложенных запросов FOR XML](../xml/for-xml-query-compared-to-nested-for-xml-query.md) и [Формирование XML-кода с вложенными запросами FOR XML](../xml/shape-xml-with-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8b4ae-124">For more information about specifying both attribute-centric and element-centric XML with nested FOR XML queries, see [FOR XML Query Compared to Nested FOR XML Query](../xml/for-xml-query-compared-to-nested-for-xml-query.md) and [Shape XML with Nested FOR XML Queries](../xml/shape-xml-with-nested-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="8b4ae-125">С помощью вложенных запросов FOR XML в режиме AUTO можно формировать XML-иерархии, содержащие одноуровневые элементы.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-125">You can generate XML hierarchies that include siblings by specifying nested AUTO mode FOR XML queries.</span></span> <span data-ttu-id="8b4ae-126">Дополнительные сведения см. в разделе [Формирование одноуровневых элементов с помощью вложенного запроса в режиме AUTO](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span><span class="sxs-lookup"><span data-stu-id="8b4ae-126">For more information, see [Generate Siblings with a Nested AUTO Mode Query](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span></span>  
  
 <span data-ttu-id="8b4ae-127">Независимо от используемого режима вложенные запросы FOR XML предоставляют больший контроль при описании формата результирующих XML-данных.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-127">Regardless of which mode you use, nested FOR XML queries provide more control in describing the shape of the resulting XML.</span></span> <span data-ttu-id="8b4ae-128">Их можно использовать вместо запросов в режиме EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-128">They can be used in the place of EXPLICIT mode queries.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8b4ae-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="8b4ae-129">Examples</span></span>  
 <span data-ttu-id="8b4ae-130">В следующих разделах содержатся примеры использования запросов FOR XML.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-130">The following topics provide examples of nested FOR XML queries.</span></span>  
  
 [<span data-ttu-id="8b4ae-131">Сравнение запросов FOR XML и вложенных запросов FOR XML</span><span class="sxs-lookup"><span data-stu-id="8b4ae-131">FOR XML Query Compared to Nested FOR XML Query</span></span>](../xml/for-xml-query-compared-to-nested-for-xml-query.md)  
 <span data-ttu-id="8b4ae-132">Сравнение одноуровневого запроса FOR XML с вложенным запросом FOR XML.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-132">Compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="8b4ae-133">Данный пример включает в себя демонстрацию того, как для результата запросов можно указать и атрибутивную, и элементную модели XML.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-133">This example includes a demonstration of how to specify both attribute-centric and element-centric XML as the result of the query.</span></span>  
  
 [<span data-ttu-id="8b4ae-134">Формирование одноуровневых элементов с помощью вложенного запроса в режиме AUTO</span><span class="sxs-lookup"><span data-stu-id="8b4ae-134">Generate Siblings with a Nested AUTO Mode Query</span></span>](../xml/generate-siblings-with-a-nested-auto-mode-query.md)  
 <span data-ttu-id="8b4ae-135">Демонстрирует создание одноуровневых элементов с помощью вложенного запроса в режиме AUTO.</span><span class="sxs-lookup"><span data-stu-id="8b4ae-135">Shows how to generate siblings by using a nested AUTO mode query</span></span>  
  
 [<span data-ttu-id="8b4ae-136">Использование вложенных запросов FOR XML в ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8b4ae-136">Use Nested FOR XML Queries in ASP.NET</span></span>](use-nested-for-xml-queries-in-asp-net.md)  
 <span data-ttu-id="8b4ae-137">Демонстрирует использование предложения FOR XML в приложении ASPX с целью возврата XML-документа из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b4ae-137">Demonstrates how an ASPX application can use FOR XML to return XML from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="8b4ae-138">Формирование XML-кода с вложенными запросами FOR XML</span><span class="sxs-lookup"><span data-stu-id="8b4ae-138">Shape XML with Nested FOR XML Queries</span></span>](../xml/shape-xml-with-nested-for-xml-queries.md)  
 <span data-ttu-id="8b4ae-139">Показывает применение вложенных запросов FOR XML для управления структурой XML-документов, создаваемых [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b4ae-139">Shows how to use nested FOR XML queries to control the structure of an XML document created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
