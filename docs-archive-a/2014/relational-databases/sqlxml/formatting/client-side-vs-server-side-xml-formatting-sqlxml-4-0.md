---
title: Клиентское и серверное форматирование XML (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- FOR XML clause, formatting
- client-side XML formatting
- server-side XPath
- server-side XML formatting
- AUTO mode
- client-side XPath
ms.assetid: f807ab7a-c5f8-4e61-9b00-23aebfabc47e
author: rothja
ms.author: jroth
ms.openlocfilehash: fa155fc6d346cb90de54e5599aca1c296623faa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665930"
---
# <a name="client-side-vs-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="1ba6e-102">Форматирование XML-кода на клиенте и на сервере (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1ba6e-102">Client-side vs. Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="1ba6e-103">В этом разделе описываются основные различия между форматированием XML-кода в SQLXML на стороне клиента и на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-103">This topic describes the general differences between client-side and server-side XML formatting in SQLXML.</span></span>  
  
## <a name="multiple-rowset-queries-not-supported-in-client-side-formatting"></a><span data-ttu-id="1ba6e-104">Запросы к нескольким наборам строк не поддерживаются при форматировании на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="1ba6e-104">Multiple Rowset Queries Not Supported in Client-side Formatting</span></span>  
 <span data-ttu-id="1ba6e-105">Запросы, создающие несколько наборов строк, не поддерживаются при использовании форматирования XML-кода на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-105">Queries that generate multiple rowsets are not supported when you use client-side XML formatting.</span></span> <span data-ttu-id="1ba6e-106">Например, предположим, что имеется виртуальный каталог, в котором определено форматирование на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-106">For example, assume you have a virtual directory in which you have client-side formatting specified.</span></span> <span data-ttu-id="1ba6e-107">Рассмотрим этот пример шаблона, который содержит две инструкции SELECT в **\<sql:query>** блоке:</span><span class="sxs-lookup"><span data-stu-id="1ba6e-107">Consider this sample template, which has two SELECT statements in a **\<sql:query>** block:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
     SELECT FirstName FROM Person.Contact FOR XML Nested;   
     SELECT LastName FROM Person.Contact FOR XML Nested    
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-108">При выполнении данного шаблона в коде приложения возвращается ошибка, так как форматирование XML-кода на стороне клиента не поддерживает форматирование нескольких наборов строк.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-108">You can execute this template in application code and an error is returned, because client-side XML formatting does not support formatting of multiple rowsets.</span></span> <span data-ttu-id="1ba6e-109">При указании запросов в двух отдельных **\<sql:query>** блоках будут получены нужные результаты.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-109">If you specify the queries in two separate **\<sql:query>** blocks, you will get the desired results.</span></span>  
  
## <a name="timestamp-maps-differently-in-client--vs-server-side-formatting"></a><span data-ttu-id="1ba6e-110">Различное сопоставление типа timestamp при форматировании на стороне клиента и на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="1ba6e-110">timestamp Maps Differently in Client- vs. Server-side Formatting</span></span>  
 <span data-ttu-id="1ba6e-111">При форматировании XML-кода на стороне сервера столбец базы данных типа `timestamp` сопоставляется с типом XDR i8 (если параметр XMLDATA указан в запросе).</span><span class="sxs-lookup"><span data-stu-id="1ba6e-111">In server-side XML formatting, the database column of `timestamp` type maps to the i8 XDR type (when the XMLDATA option is specified in the query).</span></span>  
  
 <span data-ttu-id="1ba6e-112">При форматировании XML-кода на стороне клиента столбец базы данных типа `timestamp` сопоставляется либо с типом XDR `uri`, либо `bin.base64` (в зависимости от того, указан ли в запросе параметр «binary base64»).</span><span class="sxs-lookup"><span data-stu-id="1ba6e-112">In client-side XML formatting, the database column of `timestamp` type maps to either the `uri` or the `bin.base64` XDR type (depending on whether the binary base64 option is specified in the query).</span></span> <span data-ttu-id="1ba6e-113">`bin.base64`Тип XDR полезен при использовании функций диаграмма обновления и Bulkload, так как этот тип преобразуется в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` тип.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-113">The `bin.base64` XDR type is useful if you use the updategram and bulkload features, because this type is converted to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` type.</span></span> <span data-ttu-id="1ba6e-114">Таким образом, операции вставки, обновления или удаления выполняются успешно.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-114">This way, the insert, update, or delete operation succeeds.</span></span>  
  
## <a name="deep-variants-are-used-in-server-side-formatting"></a><span data-ttu-id="1ba6e-115">При форматировании на стороне сервера используются глубокие типы VARIANT</span><span class="sxs-lookup"><span data-stu-id="1ba6e-115">Deep VARIANTs Are Used in Server-side Formatting</span></span>  
 <span data-ttu-id="1ba6e-116">При форматировании XML-кода на стороне сервера используются глубокие типы VARIANT.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-116">In server-side XML formatting, the deep types of a VARIANT type are used.</span></span> <span data-ttu-id="1ba6e-117">При форматировании XML-кода на стороне клиента подтипы VARIANT преобразуются в строку в Юникоде, а вложенные типы VARIANT не используются.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-117">If you use client-side XML formatting, the variants are converted to Unicode string, and the subtypes of VARIANT are not used.</span></span>  
  
## <a name="nested-mode-vs-auto-mode"></a><span data-ttu-id="1ba6e-118">Режим NESTED и режим AUTO</span><span class="sxs-lookup"><span data-stu-id="1ba6e-118">NESTED Mode vs. AUTO Mode</span></span>  
 <span data-ttu-id="1ba6e-119">Режим NESTED предложения FOR XML на стороне клиента аналогичен режиму AUTO предложения FOR XML на стороне сервера, за исключением следующих моментов.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-119">The NESTED mode of the client-side FOR XML is similar to the AUTO mode of server-side FOR XML, with the following exceptions:</span></span>  
  
### <a name="when-you-query-views-using-auto-mode-on-the-server-side-the-view-name-is-returned-as-the-element-name-in-the-resulting-xml"></a><span data-ttu-id="1ba6e-120">При представлении запроса с помощью режима AUTO на стороне сервера имя представления возвращается в виде имени элемента в результирующем XML-коде</span><span class="sxs-lookup"><span data-stu-id="1ba6e-120">When you query views using AUTO mode on the server-side, the view name is returned as the element name in the resulting XML.</span></span>  
 <span data-ttu-id="1ba6e-121">Например, предположим, что в таблице Person. Contact в Адвентуреворксдатабасе создается следующее представление:</span><span class="sxs-lookup"><span data-stu-id="1ba6e-121">For example, assume that the following view is created on the Person.Contact table in the AdventureWorksdatabase:</span></span>  
  
```  
CREATE VIEW ContactView AS (SELECT ContactID as CID,  
                               FirstName  as FName,  
                               LastName  as LName  
                        FROM Person.Contact)  
```  
  
 <span data-ttu-id="1ba6e-122">Следующий шаблон указывает запрос к представлению ContactView, а также форматирование XML-кода на стороне сервера:</span><span class="sxs-lookup"><span data-stu-id="1ba6e-122">The following template specifies a query against the ContactView view, and also specifies server-side XML formatting:</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT *  
    FROM   ContactView  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-123">После применения этого шаблона возвращается следующий XML-код</span><span class="sxs-lookup"><span data-stu-id="1ba6e-123">When you execute the template, the following XML is returned.</span></span> <span data-ttu-id="1ba6e-124">(Отображаются только частичные результаты.) Обратите внимание, что имена элементов — это имена представлений, в которых выполняется запрос.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-124">(Only partial results are shown.) Note that the element names are the names of the views against which the query is executed.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ContactView CID="1" FName="Gustavo" LName="Achong" />   
  <ContactView CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-125">При форматировании XML-кода на стороне сервера в режиме NESTED имена базовой таблицы возвращаются в виде имен элементов в результирующем XML-коде.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-125">When you specify client-side XML formatting by using the corresponding NESTED mode, the base table name(s) are returned as the element name(s) in the resulting XML.</span></span> <span data-ttu-id="1ba6e-126">Например, следующий измененный шаблон выполняет ту же инструкцию SELECT, но форматирование XML выполняется на стороне клиента (т. е. **клиентский XML-файл** имеет значение true в шаблоне):</span><span class="sxs-lookup"><span data-stu-id="1ba6e-126">For example, the following revised template executes the same SELECT statement, but the XML formatting is performed on the client-side (that is, **client-side-xml** is set to true in the template):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT *  
    FROM   ContactView  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-127">В результате применения этого шаблона создается следующий XML-код.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-127">Executing this template produces the following XML.</span></span> <span data-ttu-id="1ba6e-128">Обратите внимание, что именем элемента в этом случае является имя базовой таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-128">Note that the element name is the base table name in this case.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact CID="1" FName="Gustavo" LName="Achong" />   
  <Person.Contact CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
### <a name="when-you-use-auto-mode-of-the-server-side-for-xml-the-table-aliases-specified-in-the-query-are-returned-as-element-names-in-the-resulting-xml"></a><span data-ttu-id="1ba6e-129">При использовании режима AUTO предложения FOR XML на стороне сервера, псевдонимы таблиц, указанные в запросе, возвращаются в виде имен элементов в результирующем XML-коде</span><span class="sxs-lookup"><span data-stu-id="1ba6e-129">When you use AUTO mode of the server-side FOR XML, the table aliases specified in the query are returned as element names in the resulting XML.</span></span>  
 <span data-ttu-id="1ba6e-130">Например, рассмотрим следующий шаблон.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-130">For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-131">В результате выполнения этого шаблона создается следующий XML-код.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-131">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <C fname="Gustavo" lname="Achong" />   
  <C fname="Catherine" lname="Abel" />   
...  
</ROOT>   
```  
  
 <span data-ttu-id="1ba6e-132">При использовании режима NESTED предложения FOR XML на стороне клиента, имена таблиц возвращаются в виде имен элементов в результирующем XML-коде.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-132">When you use the NESTED mode of the client-side FOR XML, the table names are returned as element names in the resulting XML.</span></span> <span data-ttu-id="1ba6e-133">(Псевдонимы таблиц, указанные в запросе, не используются.) Например, рассмотрим следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="1ba6e-133">(Table aliases that are specified in the query are not used.) For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-134">В результате выполнения этого шаблона создается следующий XML-код.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-134">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact fname="Gustavo" lname="Achong" />   
  <Person.Contact fname="Catherine" lname="Abel" />   
...  
</ROOT>  
```  
  
### <a name="if-you-have-a-query-that-returns-columns-as-dbobject-queries-you-cannot-use-aliases-for-these-columns"></a><span data-ttu-id="1ba6e-135">При наличии запроса, возвращающего столбцы в виде запросов объектов базы данных, использовать псевдонимы для этих столбцов нельзя</span><span class="sxs-lookup"><span data-stu-id="1ba6e-135">If you have a query that returns columns as dbobject queries, you cannot use aliases for these columns.</span></span>  
 <span data-ttu-id="1ba6e-136">Например, рассмотрим следующий шаблон, выполняющий запрос, который возвращает идентификатор и фотографию сотрудника.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-136">For example, consider the following template, which executes a query that returns an employee ID and a photo.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query client-side-xml="1">  
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML NESTED, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-137">Выполнение этого шаблона возвращает столбец Photo в виде запроса объекта базы данных.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-137">Executing this template returns the Photo column as a dbobject query.</span></span> <span data-ttu-id="1ba6e-138">В запросе объекта базы данных `@P` ссылается на имя несуществующего столбца.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-138">In this dbobject query, `@P` refers to a column name that does not exist.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@P</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-139">Если форматирование XML выполняется на сервере (**Клиент-Side-XML = "0"**), можно использовать псевдоним для столбцов, возвращающих DBOBJECT запросы, в которых возвращаются фактические имена таблиц и столбцов (даже если указаны псевдонимы).</span><span class="sxs-lookup"><span data-stu-id="1ba6e-139">If the XML formatting is done on the server (**client-side-xml="0"**), you can use the alias for the columns that return dbobject queries in which actual table and column names are returned (even if you have aliases specified).</span></span> <span data-ttu-id="1ba6e-140">Например, следующий шаблон выполняет запрос, и форматирование XML выполняется на сервере (параметр **Client-Side-XML** не указан, а параметр **выполнить на клиенте** не выбран для виртуального корневого каталога).</span><span class="sxs-lookup"><span data-stu-id="1ba6e-140">For example, the following template executes a query, and the XML formatting is done on the server (the **client-side-xml** option is not specified and the **Run On Client** option is not selected for the virtual root).</span></span> <span data-ttu-id="1ba6e-141">Запрос также указывает режим AUTO (а не режим NESTED на стороне клиента).</span><span class="sxs-lookup"><span data-stu-id="1ba6e-141">The query also specifies AUTO mode (not the client-side NESTED mode).</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query   
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML AUTO, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="1ba6e-142">При применении этого шаблона возвращается следующий XML-документ (обратите внимание, что псевдонимы в запросе объектов базы данных для столбца LargePhoto не используются):</span><span class="sxs-lookup"><span data-stu-id="1ba6e-142">When this template is executed, the following XML document is returned (note that aliases are not used in the dbobject query for the LargePhoto column):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@LargePhoto</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
### <a name="client-side-vs-server-side-xpath"></a><span data-ttu-id="1ba6e-143">Запросы XPath на стороне клиента и на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="1ba6e-143">Client-side vs. Server-side XPath</span></span>  
 <span data-ttu-id="1ba6e-144">Запросы XPath на стороне клиента и на стороне сервера работают аналогично, за исключением следующих моментов.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-144">Client-side XPath and server-side XPath work the same except for these differences:</span></span>  
  
-   <span data-ttu-id="1ba6e-145">Преобразования данных, применяемые при использовании запросов XPath на стороне клиента, отличаются от применяемых при использовании запросов XPath на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-145">The data conversions that are applied when you use client-side XPath queries are different from those that are applied when you use server-side XPath queries.</span></span> <span data-ttu-id="1ba6e-146">Запрос XPath на стороне клиента использует функцию CAST вместо CONVERT mode 126.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-146">Client-side XPath uses CAST instead of CONVERT mode 126.</span></span>  
  
-   <span data-ttu-id="1ba6e-147">При указании в шаблоне типа **Client-Side-XML = "0"** (false) выполняется запрос форматирования XML на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-147">When you specify **client-side-xml="0"** (false) in a template, you are requesting server-side XML formatting.</span></span> <span data-ttu-id="1ba6e-148">Таким образом, нельзя указать предложение FOR XML NESTED, так как сервер не распознает параметр NESTED.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-148">Therefore, you cannot specify FOR XML NESTED because the server does not recognize the NESTED option.</span></span> <span data-ttu-id="1ba6e-149">Это приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-149">This generates an error.</span></span> <span data-ttu-id="1ba6e-150">Необходимо использовать режимы AUTO, RAW или EXPLICIT, которые сервер распознает.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-150">You must use the AUTO, RAW, or EXPLICIT modes, which the server does recognize.</span></span>  
  
-   <span data-ttu-id="1ba6e-151">При указании **Client-Side-XML = "1"** (true) в шаблоне выполняется запрос форматирования XML на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-151">When you specify **client-side-xml="1"** (true) in a template, you are requesting client-side XML formatting.</span></span> <span data-ttu-id="1ba6e-152">В этом случае можно указать предложение FOR XML NESTED.</span><span class="sxs-lookup"><span data-stu-id="1ba6e-152">In this case, you can specify FOR XML NESTED.</span></span> <span data-ttu-id="1ba6e-153">Если для XML AUTO задано значение, то форматирование XML происходит на стороне сервера, хотя в шаблоне указан параметр **Client-Side-XML = "1"** .</span><span class="sxs-lookup"><span data-stu-id="1ba6e-153">If you specify FOR XML AUTO, the XML formatting occurs on the server side although **client-side-xml="1"** is specified in the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba6e-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ba6e-154">See Also</span></span>  
 <span data-ttu-id="1ba6e-155">[Рекомендации по безопасности XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="1ba6e-155">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="1ba6e-156">[Форматирование XML на стороне клиента &#40;SQLXML 4,0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="1ba6e-156">[Client-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="1ba6e-157">Форматирование XML на стороне сервера &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1ba6e-157">Server-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](server-side-xml-formatting-sqlxml-4-0.md)  
  
  
