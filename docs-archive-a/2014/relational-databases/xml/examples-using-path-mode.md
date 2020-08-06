---
title: 'Примеры: Использование режима PATH | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, examples
ms.assetid: 3564e13b-9b97-49ef-8cf9-6a78677b09a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0876d93ffe246b6129a3838f8dbae47f3be7ffaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752000"
---
# <a name="examples-using-path-mode"></a><span data-ttu-id="27882-102">Примеры: Использование режима PATH</span><span class="sxs-lookup"><span data-stu-id="27882-102">Examples: Using PATH Mode</span></span>
  <span data-ttu-id="27882-103">В следующих примерах показано использование режима PATH при формировании XML из запроса SELECT.</span><span class="sxs-lookup"><span data-stu-id="27882-103">The following examples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="27882-104">Многие из этих запросов являются запросами к XML-документам с инструкциями по производству велосипедов, хранящимся в столбце Instructions таблицы ProductModel.</span><span class="sxs-lookup"><span data-stu-id="27882-104">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="specifying-a-simple-path-mode-query"></a><span data-ttu-id="27882-105">Указание простого запроса в режиме PATH</span><span class="sxs-lookup"><span data-stu-id="27882-105">Specifying a simple PATH mode query</span></span>  
 <span data-ttu-id="27882-106">Этот запрос указывает режим FOR XML PATH.</span><span class="sxs-lookup"><span data-stu-id="27882-106">This query specifies a FOR XML PATH mode.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   
       ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH;  
GO  
```  
  
 <span data-ttu-id="27882-107">Следующий результат представляет собой элементный XML, в котором значение каждого столбца в итоговом наборе строк образует элемент.</span><span class="sxs-lookup"><span data-stu-id="27882-107">The following result is element-centric XML where each column value in the resulting rowset is wrapped in an element.</span></span> <span data-ttu-id="27882-108">Поскольку предложение `SELECT` не указывает псевдонимы для имен столбцов, формируются имена дочерних элементов, совпадающие с именами соответствующих столбцов в предложении `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="27882-108">Because the `SELECT` clause does not specify any aliases for the column names, the child element names generated are the same as the corresponding column names in the `SELECT` clause.</span></span> <span data-ttu-id="27882-109">Для каждой строки в наборе строк добавляется тег <`row`>.</span><span class="sxs-lookup"><span data-stu-id="27882-109">For each row in the rowset a <`row`> tag is added.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</row>`  
  
 `<row>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</row>`  
  
 <span data-ttu-id="27882-110">Следующий результат совпадает с результатом запроса в режиме `RAW` с указанным параметром `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="27882-110">The following result is the same as the `RAW` mode query with the `ELEMENTS` option specified.</span></span> <span data-ttu-id="27882-111">Запрос возвращает элементный XML с установленным по умолчанию элементом <`row`> для каждой строки в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="27882-111">It returns element-centric XML with a default <`row`> element for each row in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML RAW, ELEMENTS;  
```  
  
 <span data-ttu-id="27882-112">Дополнительно можно указать имя элемента строки, которое переопределит значение по умолчанию <`row`>.</span><span class="sxs-lookup"><span data-stu-id="27882-112">You can optionally specify the row element name to overwrite the default <`row`>.</span></span> <span data-ttu-id="27882-113">Например, следующий запрос возвращает элемент <`ProductModel`> для каждой строки в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="27882-113">For example, the following query returns the <`ProductModel`> element for each row in the rowset.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModel');  
GO  
```  
  
 <span data-ttu-id="27882-114">Итоговый XML-документ будет иметь указанное имя элемента строки.</span><span class="sxs-lookup"><span data-stu-id="27882-114">The resulting XML will have a specified row element name.</span></span>  
  
 `<ProductModel>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ProductModel>`  
  
 `<ProductModel>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ProductModel>`  
  
 <span data-ttu-id="27882-115">Если задана строка нулевой длины, закрывающий тег не формируется.</span><span class="sxs-lookup"><span data-stu-id="27882-115">If you specify a zero-length string, the wrapping element is not produced.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('');  
GO  
```  
  
 <span data-ttu-id="27882-116">Результат:</span><span class="sxs-lookup"><span data-stu-id="27882-116">This is the result:</span></span>  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
## <a name="specifying-xpath-like-column-names"></a><span data-ttu-id="27882-117">Указание имен столбцов, подобных синтаксису языка XPath</span><span class="sxs-lookup"><span data-stu-id="27882-117">Specifying XPath-like column names</span></span>  
 <span data-ttu-id="27882-118">В следующем запросе указанное имя столбца `ProductModelID` начинается с символа \@ и не содержит косой черты (/).</span><span class="sxs-lookup"><span data-stu-id="27882-118">In the following query the `ProductModelID` column name specified starts with '\@' and does not contain a slash mark ('/').</span></span> <span data-ttu-id="27882-119">Поэтому в итоговом XML-документе создается атрибут элемента <`row`>, имеющий соответствующее значение столбца.</span><span class="sxs-lookup"><span data-stu-id="27882-119">Therefore, an attribute of the <`row`> element that has the corresponding column value is created in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('ProductModelData');  
GO  
```  
  
 <span data-ttu-id="27882-120">Результат:</span><span class="sxs-lookup"><span data-stu-id="27882-120">This is the result:</span></span>  
  
 `< ProductModelData id="122">`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ ProductModelData >`  
  
 `< ProductModelData id="119">`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ ProductModelData >`  
  
 <span data-ttu-id="27882-121">Указав в запросе `root` параметр `FOR XML`, можно добавить один элемент верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="27882-121">You can add a single top-level element by specifying the `root` option in `FOR XML`.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="27882-122">Для формирования иерархии можно добавить синтаксис, подобный PATH.</span><span class="sxs-lookup"><span data-stu-id="27882-122">To generate a hierarchy, you can include PATH-like syntax.</span></span> <span data-ttu-id="27882-123">Если, например, изменить имя столбца `Name` на «SomeChild/ModelName», можно получить XML-документ с иерархией, показанной в следующем результате:</span><span class="sxs-lookup"><span data-stu-id="27882-123">For example, change the column name for the `Name` column to "SomeChild/ModelName" and you will obtain XML with hierarchy, as shown in this result:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="122">`  
  
 `<SomeChild>`  
  
 `<ModelName>All-Purpose Bike Stand</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData id="119">`  
  
 `<SomeChild>`  
  
 `<ModelName>Bike Wash</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="27882-124">Следующий запрос извлекает не только код модели продукта и его имя, но и расположения производственных инструкций для модели продукции.</span><span class="sxs-lookup"><span data-stu-id="27882-124">Besides the product model ID and name, the following query retrieves the manufacturing instruction locations for the product model.</span></span> <span data-ttu-id="27882-125">Поскольку столбец «Instructions» имеет тип `xml`, то для получения расположения указывается метод `query()` типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="27882-125">Because the Instructions column is of `xml` type, the `query()` method of `xml` data type is specified to retrieve the location.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') AS ManuInstr  
FROM Production.ProductModel  
WHERE ProductModelID = 7  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="27882-126">Частичный результат.</span><span class="sxs-lookup"><span data-stu-id="27882-126">This is the partial result.</span></span> <span data-ttu-id="27882-127">Так как запрос указывает Мануинстр в качестве имени столбца, XML-код, возвращаемый `query()` методом, упаковывается в `ManuInstr` тег <>, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="27882-127">Because the query specifies ManuInstr as the column name, the XML returned by the `query()` method is wrapped in a <`ManuInstr`> tag as shown in the following:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="7">`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<ManuInstr>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `<MI:step>...</MI:step>...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ManuInstr>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="27882-128">В предыдущий запрос FOR XML можно было включить пространства имен для элементов <`Root`> и <`ProductModelData`>.</span><span class="sxs-lookup"><span data-stu-id="27882-128">In the previous FOR XML query, you may want to include namespaces for the <`Root`> and <`ProductModelData`> elements.</span></span> <span data-ttu-id="27882-129">Для этого следовало сначала определить префикс пространства имен, создать привязку с помощью предложения WITH XMLNAMESPACES и затем использовать префиксы в запросе FOR XML.</span><span class="sxs-lookup"><span data-stu-id="27882-129">You can do this by first defining the prefix to namespace binding by using WITH XMLNAMESPACES and using prefixes in the FOR XML query.</span></span> <span data-ttu-id="27882-130">Дополнительные сведения с. в разделе [Добавление пространств имен в запросы с помощью WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="27882-130">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES (  
   'uri1' AS ns1,    
   'uri2' AS ns2,  
   'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions' as MI)  
SELECT ProductModelID AS "ns1:ProductModelID",  
       Name           AS "ns1:Name",  
       Instructions.query('  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ('ns2:ProductInfo'), root('ns1:root');  
GO  
```  
  
 <span data-ttu-id="27882-131">Обратите внимание, что префикс `MI` также определяется в предложении `WITH XMLNAMESPACES`.</span><span class="sxs-lookup"><span data-stu-id="27882-131">Note that the `MI` prefix is also defined in the `WITH XMLNAMESPACES`.</span></span> <span data-ttu-id="27882-132">В результате метод `query()` типа `xml` не определяет префикс в прологе запроса.</span><span class="sxs-lookup"><span data-stu-id="27882-132">As a result, the `query()` method of the `xml` type specified does not define the prefix in the query prolog.</span></span> <span data-ttu-id="27882-133">Результат:</span><span class="sxs-lookup"><span data-stu-id="27882-133">This is the result:</span></span>  
  
 `<ns1:root xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">`  
  
 `<ns2:ProductInfo>`  
  
 `<ns1:ProductModelID>7</ns1:ProductModelID>`  
  
 `<ns1:Name>HL Touring Frame</ns1:Name>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `LaborHours="2.5" LotSize="100" MachineHours="3" SetupHours="0.5" LocationID="10" xmlns="">`  
  
 `<MI:step>`  
  
 `Insert <MI:material>aluminum sheet MS-2341</MI:material> into the <MI:tool>T-85A framing tool</MI:tool>.`  
  
 `</MI:step>`  
  
 `...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ns2:ProductInfo>`  
  
 `</ns1:root>`  
  
## <a name="generating-a-value-list-using-path-mode"></a><span data-ttu-id="27882-134">Формирование списка значений с помощью режима PATH</span><span class="sxs-lookup"><span data-stu-id="27882-134">Generating a value list using PATH mode</span></span>  
 <span data-ttu-id="27882-135">Данный запрос строит список значений кодов продуктов для каждой модели продукции.</span><span class="sxs-lookup"><span data-stu-id="27882-135">For each product model, this query constructs a value list of product IDs.</span></span> <span data-ttu-id="27882-136">Кроме того, для каждого кода продукта запрос создает вложенные элементы <`ProductName`>, как показано в следующем фрагменте XML:</span><span class="sxs-lookup"><span data-stu-id="27882-136">For each product ID, the query also constructs <`ProductName`> nested elements, as shown in this XML fragment:</span></span>  
  
 `<ProductModelData ProductModelID="7" ProductModelName="..."`  
  
 `ProductIDs="product id list in the product model" >`  
  
 `<ProductName>...</ProductName>`  
  
 `<ProductName>...</ProductName>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="27882-137">Это запрос, создающий желаемый XML:</span><span class="sxs-lookup"><span data-stu-id="27882-137">This is the query that produces the XML you want:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID     AS "@ProductModelID",  
       Name               S "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')) S "@ProductIDs",  
       (SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
        FOR XML PATH ('')) as "ProductNames"  
FROM   Production.ProductModel  
WHERE  ProductModelID= 7 or ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="27882-138">Обратите внимание на следующие данные из предыдущего запроса:</span><span class="sxs-lookup"><span data-stu-id="27882-138">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="27882-139">Первая вложенная инструкция `SELECT` возвращает список ProductID, для чего использует значение `data()` в качестве имени столбца.</span><span class="sxs-lookup"><span data-stu-id="27882-139">The first nested `SELECT` returns a list of ProductIDs by using `data()` as the column name.</span></span> <span data-ttu-id="27882-140">Поскольку в режиме `FOR XML PATH`запрос указывает для имени элемента строки пустую строку, формирование элемента не происходит.</span><span class="sxs-lookup"><span data-stu-id="27882-140">Because the query specifies an empty string as the row element name in `FOR XML PATH`, no element is generated.</span></span> <span data-ttu-id="27882-141">Вместо этого список значений назначается атрибуту `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="27882-141">Instead, the value list is assigned to the `ProductID` attribute.</span></span>  
  
-   <span data-ttu-id="27882-142">Вторая вложенная инструкция `SELECT` извлекает названия продуктов для модели продукта.</span><span class="sxs-lookup"><span data-stu-id="27882-142">The second nested `SELECT` retrieves product names for products in the product model.</span></span> <span data-ttu-id="27882-143">Запрос формирует элементы <`ProductName`>, которые возвращаются в виде элементов <`ProductNames`>, поскольку в качестве имени столбца в запросе указано `ProductNames`.</span><span class="sxs-lookup"><span data-stu-id="27882-143">It generates <`ProductName`> elements that are returned wrapped in the <`ProductNames`> element, because the query specifies `ProductNames` as the column name.</span></span>  
  
 <span data-ttu-id="27882-144">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="27882-144">This is the partial result:</span></span>  
  
 `<ProductModelData PId="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>HL Touring Frame - Yellow, 60</ProductName>`  
  
 `<ProductName>HL Touring Frame - Yellow, 46</ProductName></ProductNames>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 `<ProductModelData PId="9"`  
  
 `ProductModelName="LL Road Frame"`  
  
 `ProductIDs="722 723 724 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>LL Road Frame - Black, 58</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 60</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 62</ProductName>`  
  
 `...`  
  
 `</ProductNames>`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="27882-145">Вложенный запрос, формирующий имена продуктов, возвращает результат в виде строки, которая преобразуется в сущность и затем добавляется в XML-документ.</span><span class="sxs-lookup"><span data-stu-id="27882-145">The subquery constructing the product names returns the result as a string that is entitized and then added to the XML.</span></span> <span data-ttu-id="27882-146">Если добавить директиву типа `FOR XML PATH (''), type`, вложенный запрос возвращает результат как тип `xml`, а преобразования в сущность не происходит.</span><span class="sxs-lookup"><span data-stu-id="27882-146">If you add the type directive, `FOR XML PATH (''), type`, the subquery returns the result as `xml` type and no entitization occurs.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@ProductModelID",  
      Name AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ProductIDs",  
       (  
       SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH (''), type  
       ) AS "ProductNames"  
  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
## <a name="adding-namespaces-in-the-resulting-xml"></a><span data-ttu-id="27882-147">Добавление пространств имен в итоговый XML-документ</span><span class="sxs-lookup"><span data-stu-id="27882-147">Adding namespaces in the resulting XML</span></span>  
 <span data-ttu-id="27882-148">Как описано в разделе [Добавление пространств имен с помощью предложения WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), предложение WITH XMLNAMESPACES может использоваться для включения пространств имен в запросы в режиме PATH.</span><span class="sxs-lookup"><span data-stu-id="27882-148">As described in [Adding Namespaces Using WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), you can use WITH XMLNAMESPACES to include namespaces in the PATH mode queries.</span></span> <span data-ttu-id="27882-149">Например, имена, указанные в предложении SELECT, имеют префиксы пространства имен.</span><span class="sxs-lookup"><span data-stu-id="27882-149">For example, names specified in the SELECT clause include namespace prefixes.</span></span> <span data-ttu-id="27882-150">Следующий запрос в режиме `PATH` строит XML-документ с пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="27882-150">The following `PATH` mode query constructs XML with namespaces.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
GO  
```  
  
 <span data-ttu-id="27882-151">Атрибут `@xml:lang`, добавляемый к элементу <`English`>, определяется в стандартном пространстве имен xml.</span><span class="sxs-lookup"><span data-stu-id="27882-151">The `@xml:lang` attribute added to the <`English`> element is defined in the predefined xml namespace.</span></span>  
  
 <span data-ttu-id="27882-152">Результат:</span><span class="sxs-lookup"><span data-stu-id="27882-152">This is the result:</span></span>  
  
 `<Translation>`  
  
 `<English xml:lang="en">food</English>`  
  
 `<German xml:lang="ger">Essen</German>`  
  
 `</Translation>`  
  
 <span data-ttu-id="27882-153">Следующий запрос похож на приведенный в примере В, отличаясь тем, что в нем пространства имен добавляются в результирующий XML-документ с помощью предложения `WITH XMLNAMESPACES` .</span><span class="sxs-lookup"><span data-stu-id="27882-153">The following query is similar to example C, except that it uses `WITH XMLNAMESPACES` to include namespaces in the XML result.</span></span> <span data-ttu-id="27882-154">Дополнительные сведения с. в разделе [Добавление пространств имен в запросы с помощью WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="27882-154">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES ('uri1' AS ns1,  DEFAULT 'uri2')  
SELECT ProductModelID AS "@ns1:ProductModelID",  
      Name AS "@ns1:ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ns1:ProductIDs",  
       (  
       SELECT ProductID AS "@ns1:ProductID",   
              Name AS "@ns1:ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH , type   
       ) AS "ns1:ProductNames"  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData'), root('root');  
```  
  
 <span data-ttu-id="27882-155">Результат:</span><span class="sxs-lookup"><span data-stu-id="27882-155">This is the result:</span></span>  
  
 `<root xmlns="uri2" xmlns:ns1="uri1">`  
  
 `<ProductModelData ns1:ProductModelID="7" ns1:ProductModelName="HL Touring Frame" ns1:ProductIDs="885 887 888 889 890 891 892 893">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="885" ns1:ProductName="HL Touring Frame - Yellow, 60" />`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="887" ns1:ProductName="HL Touring Frame - Yellow, 46" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData ns1:ProductModelID="9" ns1:ProductModelName="LL Road Frame" ns1:ProductIDs="722 723 724 725 726 727 728 729 730 736 737 738">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="722" ns1:ProductName="LL Road Frame - Black, 58" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `</root>`  
  
## <a name="see-also"></a><span data-ttu-id="27882-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="27882-156">See Also</span></span>  
 [<span data-ttu-id="27882-157">Использование режима PATH совместно с FOR XML</span><span class="sxs-lookup"><span data-stu-id="27882-157">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
