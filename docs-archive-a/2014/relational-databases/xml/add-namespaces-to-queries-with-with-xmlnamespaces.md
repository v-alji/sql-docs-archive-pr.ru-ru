---
title: Добавление пространств имен в запросы с помощью WITH XMLNAMESPACES | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENTS XSINIL directive
- adding namespaces
- XSINIL directive
- default namespaces
- queries [XML in SQL Server], WITH XMLNAMESPACES clause
- predefined namespaces [XML in SQL Server]
- FOR XML clause, WITH XMLNAMESPACES clause
- namespaces [XML in SQL Server]
- xml data type [SQL Server], WITH XMLNAMESPACES clause
- WITH XMLNAMESPACES clause
ms.assetid: 2189cb5e-4460-46c5-a254-20c833ebbfec
author: rothja
ms.author: jroth
ms.openlocfilehash: ed5d719a845996215fffc18af64401779f848cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654963"
---
# <a name="add-namespaces-to-queries-with-with-xmlnamespaces"></a><span data-ttu-id="3a93d-102">Добавление пространств имен в запросы с WITH XMLNAMESPACES</span><span class="sxs-lookup"><span data-stu-id="3a93d-102">Add Namespaces to Queries with WITH XMLNAMESPACES</span></span>
  <span data-ttu-id="3a93d-103">Предложение[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) поддерживает пространство имен URI следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3a93d-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) provides namespace URI support in the following way:</span></span>  
  
-   <span data-ttu-id="3a93d-104">Разрешается сопоставление префикса пространства имен с адресом URI при [создании XML с помощью предложения FOR XML](for-xml-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="3a93d-104">It makes the namespace prefix to URI mapping available when [Constructing XML Using FOR XML](for-xml-sql-server.md) queries.</span></span>  
  
-   <span data-ttu-id="3a93d-105">Разрешается сопоставление пространства имен с адресом URI в статическом контексте пространств имен [методов типа данных xml](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="3a93d-105">It makes the namespace to URI mapping available to the static namespace context of the [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span>  
  
## <a name="using-with-xmlnamespaces-in-the-for-xml-queries"></a><span data-ttu-id="3a93d-106">Использование предложения WITH XMLNAMESPACES в запросах FOR XML</span><span class="sxs-lookup"><span data-stu-id="3a93d-106">Using WITH XMLNAMESPACES in the FOR XML Queries</span></span>  
 <span data-ttu-id="3a93d-107">Использование предложения WITH XMLNAMESPACES позволяет включать пространства имен XML в запросы FOR XML.</span><span class="sxs-lookup"><span data-stu-id="3a93d-107">WITH XMLNAMESPACES lets you include XML namespaces in FOR XML queries.</span></span> <span data-ttu-id="3a93d-108">Например, рассмотрим следующий запрос FOR XML:</span><span class="sxs-lookup"><span data-stu-id="3a93d-108">For example, consider the following FOR XML query:</span></span>  
  
```  
SELECT ProductID, Name, Color  
FROM   Production.Product  
WHERE  ProductID=316 or ProductID=317  
FOR XML RAW  
```  
  
 <span data-ttu-id="3a93d-109">Результат:</span><span class="sxs-lookup"><span data-stu-id="3a93d-109">This is the result:</span></span>  
  
```  
<row ProductID="316" Name="Blade" />  
<row ProductID="317" Name="LL Crankarm" Color="Black" />  
  
```  
  
 <span data-ttu-id="3a93d-110">Чтобы добавить пространства имен в XML-документ, созданный с помощью запроса FOR XML, вначале с помощью предложения WITH NAMESPACES укажите префикс пространства имен для сопоставления с адресом URI.</span><span class="sxs-lookup"><span data-stu-id="3a93d-110">To add namespaces to the XML constructed by the FOR XML query, first specify the namespace prefix to URI mappings by using the WITH NAMESPACES clause.</span></span> <span data-ttu-id="3a93d-111">Затем используйте эти префиксы пространств имен для указания имен в запросе, как показано в следующем измененном запросе.</span><span class="sxs-lookup"><span data-stu-id="3a93d-111">Then, use the namespace prefixes in specifying the names in the query as shown in the following modified query.</span></span> <span data-ttu-id="3a93d-112">Обратите внимание, что предложение WITH XMLNAMESPACES указывает префикс пространства имен (`ns1`) для сопоставления с адресом URI (`uri`).</span><span class="sxs-lookup"><span data-stu-id="3a93d-112">Note that the WITH XMLNAMESPACES clause specifies the namespace prefix (`ns1`) to URI (`uri`) mapping.</span></span> <span data-ttu-id="3a93d-113">Затем префикс `ns1` используется для указания создаваемого элемента и имен атрибутов в запросе FOR XML.</span><span class="sxs-lookup"><span data-stu-id="3a93d-113">The `ns1` prefix is then used in specifying the element and attribute names to be constructed by the FOR XML query.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Prod'), ELEMENTS  
  
```  
  
 <span data-ttu-id="3a93d-114">Результирующий XML-документ содержит префиксы пространства имен:</span><span class="sxs-lookup"><span data-stu-id="3a93d-114">The XML result includes the namespace prefixes:</span></span>  
  
```  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
</ns1:Prod>  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>317</ns1:ProductID>  
  <ns1:Name>LL Crankarm</ns1:Name>  
  <ns1:Color>Black</ns1:Color>  
</ns1:Prod>  
  
```  
  
 <span data-ttu-id="3a93d-115">Предложение WITH XMLNAMESPACES имеет следующее применение:</span><span class="sxs-lookup"><span data-stu-id="3a93d-115">The following applies to the WITH XMLNAMESPACES clause:</span></span>  
  
-   <span data-ttu-id="3a93d-116">Оно может быть использовано в запросах FOR XML только в режимах RAW, AUTO и PATH.</span><span class="sxs-lookup"><span data-stu-id="3a93d-116">It is supported only on the RAW, AUTO, and PATH modes of the FOR XML queries.</span></span> <span data-ttu-id="3a93d-117">Режим EXPLICIT не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3a93d-117">The EXPLICIT mode is not supported.</span></span>  
  
-   <span data-ttu-id="3a93d-118">Оно влияет только на префиксы пространств имен в запросах FOR XML и методах типа данных **xml** , но не на синтаксический анализатор XML.</span><span class="sxs-lookup"><span data-stu-id="3a93d-118">It only affects the namespace prefixes of FOR XML queries and the **xml** data type methods, but not the XML parser.</span></span> <span data-ttu-id="3a93d-119">Например, в результате выполнения следующего запроса будет получена ошибка, так как в XML-документе не содержится пространства имени, связанного с префиксом myNS.</span><span class="sxs-lookup"><span data-stu-id="3a93d-119">For example, the following query returns an error, because the XML document has no namespace declaration for the myNS prefix.</span></span>  
  
-   <span data-ttu-id="3a93d-120">Такие директивы FOR XML, как XMLSCHEMA и XMLDATA, не могут быть использованы в предложении WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="3a93d-120">The FOR XML directives, XMLSCHEMA and XMLDATA cannot be used when a WITH XMLNAMESPACES clause is being used.</span></span>  
  
    ```  
    CREATE TABLE T (x xml)  
    go  
    WITH XMLNAMESPACES ('http://abc' as myNS )  
    INSERT INTO T VALUES('<myNS:root/>')  
    ```  
  
## <a name="using-the-xsinil-directive"></a><span data-ttu-id="3a93d-121">Использование директивы XSINIL</span><span class="sxs-lookup"><span data-stu-id="3a93d-121">Using the XSINIL Directive</span></span>  
 <span data-ttu-id="3a93d-122">При использовании директивы ELEMENTS XSINIL xsi-префиксы в предложении WITH XMLNAMESPACES использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="3a93d-122">You cannot define the xsi prefix in the WITH XMLNAMESPACES clause if you are using the ELEMENTS XSINIL directive.</span></span> <span data-ttu-id="3a93d-123">При использовании директивы ELEMENTS XSINIL префиксы добавляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="3a93d-123">Instead, it is added automatically when you use ELEMENTS XSINIL.</span></span> <span data-ttu-id="3a93d-124">В следующем запросе используется директива ELEMENTS XSINIL, формирующая ориентированный на элементы XML-документ, в котором пустые значения сопоставляются с элементами, для которых атрибут **xsi:nil** имеет значение True.</span><span class="sxs-lookup"><span data-stu-id="3a93d-124">The following query uses ELEMENTS XSINIL that generates element-centric XML where null values are mapped to elements that have the **xsi:nil** attribute set to True.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316   
FOR XML RAW, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="3a93d-125">Результат:</span><span class="sxs-lookup"><span data-stu-id="3a93d-125">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
  <ns1:Color xsi:nil="true" />  
</row>  
```  
  
## <a name="specifying-default-namespaces"></a><span data-ttu-id="3a93d-126">Указание пространств имен по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3a93d-126">Specifying Default Namespaces</span></span>  
 <span data-ttu-id="3a93d-127">Вместо объявления префикса пространства имени можно объявить пространство имени с помощью ключевого слова DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="3a93d-127">Instead of declaring a namespace prefix, you can declare a default namespace by using a DEFAULT keyword.</span></span> <span data-ttu-id="3a93d-128">В запросе FOR XML таким образом происходит привязка пространства имен по умолчанию к XML-узлам результирующего XML-документа.</span><span class="sxs-lookup"><span data-stu-id="3a93d-128">In the FOR XML query, it will bind the default namespace to XML nodes in the resulting XML.</span></span> <span data-ttu-id="3a93d-129">В представленном ниже примере с помощью предложения WITH XMLNAMESPACES задается два префикса пространства имен, которые определяются вместе с пространством имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3a93d-129">In the following example, the WITH XMLNAMESPACES defines two namespace prefixes that are defined together with a default namespace.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,   
                    'uri2' as ns2,  
                    DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product   
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Product'), ROOT('ns2:root'), ELEMENTS  
```  
  
 <span data-ttu-id="3a93d-130">В результате выполнения запроса FOR XML формируется ориентированный на элементы XML-документ.</span><span class="sxs-lookup"><span data-stu-id="3a93d-130">The FOR XML query generates element-centric XML.</span></span> <span data-ttu-id="3a93d-131">Заметим, что в запросе используются оба префикса пространства имен в узле имен.</span><span class="sxs-lookup"><span data-stu-id="3a93d-131">Note that the query uses both the namespace prefixes in naming nodes.</span></span> <span data-ttu-id="3a93d-132">В предложении SELECT параметры ProductID, Name и Color не указывают имен с какими-либо префиксами.</span><span class="sxs-lookup"><span data-stu-id="3a93d-132">In the SELECT clause, the ProductID, Name, and Color do not specify a name with any prefix.</span></span> <span data-ttu-id="3a93d-133">Поэтому соответствующие элементы в результирующем XML-документе принадлежат к пространству имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3a93d-133">Therefore, the corresponding elements in the resulting XML belong to the default namespace.</span></span>  
  
```  
<ns2:root xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">  
  <ns1:Product>  
    <ProductID>316</ProductID>  
    <Name>Blade</Name>  
  </ns1:Product>  
  <ns1:Product>  
    <ProductID>317</ProductID>  
    <Name>LL Crankarm</Name>  
    <Color>Black</Color>  
  </ns1:Product>  
</ns2:root>  
```  
  
 <span data-ttu-id="3a93d-134">Приведенный ниже запрос повторяет предыдущий за исключением указания режима FOR XML AUTO.</span><span class="sxs-lookup"><span data-stu-id="3a93d-134">The following query is similar to the previous one, except that the FOR XML AUTO mode is specified.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,  'uri2' as ns2,DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product as "ns1:Product"  
WHERE ProductID=316 or ProductID=317  
FOR XML AUTO, ROOT('ns2:root'), ELEMENTS  
```  
  
## <a name="using-predefined-namespaces"></a><span data-ttu-id="3a93d-135">Использование предопределенных пространств имен</span><span class="sxs-lookup"><span data-stu-id="3a93d-135">Using Predefined Namespaces</span></span>  
 <span data-ttu-id="3a93d-136">При использовании предопределенных пространств имен, кроме случаев использования пространств имен xml и xsi в директиве ELEMENTS XSINIL, необходимо явно указывать привязку пространств имен в предложении WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="3a93d-136">When you use predefined namespaces, except the xml namespace and the xsi namespace when ELEMENTS XSINIL is used, you must explicitly specify the namespace binding by using WITH XMLNAMESPACES.</span></span> <span data-ttu-id="3a93d-137">В следующем запросе происходит задание префикса пространства имен для привязки к адресу URI для предопределенного пространства имен (`urn:schemas-microsoft-com:xml-sql`).</span><span class="sxs-lookup"><span data-stu-id="3a93d-137">The following query explicitly defines the namespace prefix to URI binding for the predefined namespace (`urn:schemas-microsoft-com:xml-sql`).</span></span>  
  
```  
WITH XMLNAMESPACES ('urn:schemas-microsoft-com:xml-sql' as sql)  
SELECT 'SELECT * FROM Customers FOR XML AUTO, ROOT("a")' AS "sql:query"  
FOR XML PATH('sql:root')  
```  
  
 <span data-ttu-id="3a93d-138">Результат.</span><span class="sxs-lookup"><span data-stu-id="3a93d-138">This is the result.</span></span> <span data-ttu-id="3a93d-139">Данный XML-шаблон известен пользователям SQLXML.</span><span class="sxs-lookup"><span data-stu-id="3a93d-139">SQLXML users are familiar with this XML template.</span></span> <span data-ttu-id="3a93d-140">Дополнительные сведения см. в статье [Основные понятия о программировании для SQLXML 4.0](../sqlxml/sqlxml-4-0-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="3a93d-140">For more information, see [SQLXML 4.0 Programming Concepts](../sqlxml/sqlxml-4-0-programming-concepts.md).</span></span>  
  
```  
<sql:root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>SELECT * FROM Customers FOR XML AUTO, ROOT("a")</sql:query>  
</sql:root>  
```  
  
 <span data-ttu-id="3a93d-141">Только XML-префикс пространства имен может быть использован без явного задания в предложении WITH XMLNAMESPACES, как показано в следующем примере запроса в режиме PATH.</span><span class="sxs-lookup"><span data-stu-id="3a93d-141">Only the xml namespace prefix can be used without explicitly defining it in WITH XMLNAMESPACES, as shown in the following PATH mode query.</span></span> <span data-ttu-id="3a93d-142">Также при объявлении префикса его необходимо привязать к пространству имен http://www.w3.org/XML/1998/namespace.</span><span class="sxs-lookup"><span data-stu-id="3a93d-142">Also, if the prefix is declared, it has to be bound to the namespace http://www.w3.org/XML/1998/namespace.</span></span> <span data-ttu-id="3a93d-143">Имена, указанные в предложении SELECT, ссылаются на XML-префикс пространства имен, который не был явно задан с помощью предложения WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="3a93d-143">The names specified in the SELECT clause refer to the xml namespace prefix that is not explicitly defined by using WITH XMLNAMESPACES.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
go  
```  
  
 <span data-ttu-id="3a93d-144">Атрибуты @xml:lang используют предопределенное пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="3a93d-144">The @xml:lang attributes use the predefined xml namespace.</span></span> <span data-ttu-id="3a93d-145">Так как в XML версии 1.0 нет необходимости явно задавать привязку пространства имен XML, то она не включается в результат.</span><span class="sxs-lookup"><span data-stu-id="3a93d-145">Because XML version 1.0 does not require the explicit declaration of the xml namespace binding, the result will not include an explicit declaration of the namespace binding.</span></span>  
  
 <span data-ttu-id="3a93d-146">Результат:</span><span class="sxs-lookup"><span data-stu-id="3a93d-146">This is the result:</span></span>  
  
```  
<Translation>  
  <English xml:lang="en">food</English>  
  <German xml:lang="ger">Essen</German>  
</Translation>  
```  
  
## <a name="using-with-xmlnamespaces-with-the-xml-data-type-methods"></a><span data-ttu-id="3a93d-147">Использование предложения WITH XMLNAMESPACES с методами типа данных xml</span><span class="sxs-lookup"><span data-stu-id="3a93d-147">Using WITH XMLNAMESPACES with the xml Data Type Methods</span></span>  
 <span data-ttu-id="3a93d-148">Все [методы типа данных xml](/sql/t-sql/xml/xml-data-type-methods) , указанные в запросе SELECT (или UPDATE в случае метода **modify()** ), должны повторять в своем прологе объявление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="3a93d-148">The [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) specified in a SELECT query, or in UPDATE when it is the **modify()** method, all have to repeat the namespace declaration in their prolog.</span></span> <span data-ttu-id="3a93d-149">Это может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="3a93d-149">This can be time-consuming.</span></span> <span data-ttu-id="3a93d-150">Например, в результате выполнения следующего запроса получаются идентификаторы моделей, в описание каталогов которых включены спецификации.</span><span class="sxs-lookup"><span data-stu-id="3a93d-150">For example, the following query retrieves product model IDs whose catalog descriptions do include specification.</span></span> <span data-ttu-id="3a93d-151">То есть те, для которых существует элемент <`Specifications`>.</span><span class="sxs-lookup"><span data-stu-id="3a93d-151">That is, the <`Specifications`> element exists.</span></span>  
  
```  
SELECT ProductModelID, CatalogDescription.query('  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
    declare namespace  pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
```  
  
 <span data-ttu-id="3a93d-152">В представленном выше запросе в прологах обоих методов ( **query()** и **exist()** ) объявляются одинаковые пространства имен.</span><span class="sxs-lookup"><span data-stu-id="3a93d-152">In the previous query, both the **query()** and **exist()** methods declare the same namespace in their prolog.</span></span> <span data-ttu-id="3a93d-153">Пример:</span><span class="sxs-lookup"><span data-stu-id="3a93d-153">For example:</span></span>  
  
```  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
```  
  
 <span data-ttu-id="3a93d-154">Того же результата можно достичь, если вначале объявить предложение WITH XMLNAMESPACES, а затем использовать указанные в нем префиксы пространства имен в запросе.</span><span class="sxs-lookup"><span data-stu-id="3a93d-154">Alternatively, you can declare WITH XMLNAMESPACES first and use the namespace prefixes in the query.</span></span> <span data-ttu-id="3a93d-155">В таком случае в прологах обоих методов ( **query()** и **exist()** ) пространства имен не объявляются.</span><span class="sxs-lookup"><span data-stu-id="3a93d-155">In this case, the **query()** and **exist()** methods  do not have to include namespace declarations in their prolog.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' as pd)  
SELECT ProductModelID, CatalogDescription.query('  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
Go  
```  
  
 <span data-ttu-id="3a93d-156">Обратите внимание, что при явном объявлении в прологе запроса на языке XQuery, указанные в нем префиксы пространства имен переопределяют все указанные ранее и заданные по умолчанию с помощью предложения WITH префиксы.</span><span class="sxs-lookup"><span data-stu-id="3a93d-156">Note that an explicit declaration in the XQuery prolog overrides the namespace prefix and the default element namespace that are defined in the WITH clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a93d-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a93d-157">See Also</span></span>  
 <span data-ttu-id="3a93d-158">[методов типа данных xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="3a93d-158">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="3a93d-159">[Справочник по языку XQuery (SQL Server)](/sql/xquery/xquery-language-reference-sql-server) </span><span class="sxs-lookup"><span data-stu-id="3a93d-159">[XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span></span>  
 <span data-ttu-id="3a93d-160">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) </span><span class="sxs-lookup"><span data-stu-id="3a93d-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span></span>  
 [<span data-ttu-id="3a93d-161">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3a93d-161">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
