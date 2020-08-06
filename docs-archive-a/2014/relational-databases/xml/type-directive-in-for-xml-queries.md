---
title: Директива TYPE в запросах FOR XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, TYPE directive
- TYPE directive
ms.assetid: a3df6c30-1f25-45dc-b5a9-bd0e41921293
author: rothja
ms.author: jroth
ms.openlocfilehash: cddce90718ef5edfcf161ddc6cc52b617825a2e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668669"
---
# <a name="type-directive-in-for-xml-queries"></a><span data-ttu-id="05918-102">Директива TYPE в запросах FOR XML</span><span class="sxs-lookup"><span data-stu-id="05918-102">TYPE Directive in FOR XML Queries</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="05918-103">поддержка [&#40;xml&#41;Transact-SQL](/sql/t-sql/xml/xml-transact-sql) позволяет при необходимости вернуть результат запроса FOR XML в качестве `xml` типа данных, УКАЗАВ директиву Type.</span><span class="sxs-lookup"><span data-stu-id="05918-103">support for the [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) enables you to optionally request that the result of a FOR XML query be returned as `xml` data type by specifying the TYPE directive.</span></span> <span data-ttu-id="05918-104">Это позволяет обрабатывать результат запроса FOR XML на сервере.</span><span class="sxs-lookup"><span data-stu-id="05918-104">This allows you to process the result of a FOR XML query on the server.</span></span> <span data-ttu-id="05918-105">Например, можно указать для него запрос XQuery, присвоить результат `xml` переменной типа или написать [вложенные запросы FOR XML](use-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="05918-105">For example, you can specify an XQuery against it, assign the result to an `xml` type variable, or write [Nested FOR XML queries](use-nested-for-xml-queries.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="05918-106">возвращает клиенту тип данных XML экземпляра, представляющий собой результат различных серверных конструкций, таких как запросы FOR XML, использующие директиву TYPE или тип данных `xml` для получения значений XML-данных экземпляра из столбцов таблицы и выходных параметров SQL.</span><span class="sxs-lookup"><span data-stu-id="05918-106">returns XML data type instance data to the client as a result of different server-constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML instance data values from SQL table columns and output parameters.</span></span> <span data-ttu-id="05918-107">В коде клиентского приложения поставщик ADO.NET запрашивает эти XML-данные для отправки с сервера в двоичной кодировке.</span><span class="sxs-lookup"><span data-stu-id="05918-107">In client application code, the ADO.NET provider requests this XML data type information to be sent in a binary encoding from the server.</span></span> <span data-ttu-id="05918-108">Однако при использовании предложения FOR XML без директивы TYPE XML-данные возвращаются как данные строкового типа.</span><span class="sxs-lookup"><span data-stu-id="05918-108">However, if you are using FOR XML without the TYPE directive, the XML data comes back as a string type.</span></span> <span data-ttu-id="05918-109">В любом случае поставщик клиента всегда будет иметь возможность обрабатывать XML-данные в любом из форматов.</span><span class="sxs-lookup"><span data-stu-id="05918-109">In any case, the client provider will always be able to handle either form of XML.</span></span> <span data-ttu-id="05918-110">Обратите внимание на то, что предложение FOR XML верхнего уровня без директивы TYPE не может быть использовано с курсорами.</span><span class="sxs-lookup"><span data-stu-id="05918-110">Note that top-level FOR XML without the TYPE directive cannot be used with cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="05918-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="05918-111">Examples</span></span>  
 <span data-ttu-id="05918-112">В следующих примерах показано использование директивы TYPE в запросах FOR XML.</span><span class="sxs-lookup"><span data-stu-id="05918-112">The following examples illustrate the use of the TYPE directive with FOR XML queries.</span></span>  
  
### <a name="retrieving-for-xml-query-results-as-xml-type"></a><span data-ttu-id="05918-113">Получение результатов запроса FOR XML в виде XML-данных</span><span class="sxs-lookup"><span data-stu-id="05918-113">Retrieving FOR XML query results as xml type</span></span>  
 <span data-ttu-id="05918-114">Следующий запрос используется для получения контактной информации о клиенте из таблицы `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="05918-114">The following query retrieves customer contact information from the `Contacts` table.</span></span> <span data-ttu-id="05918-115">Поскольку в запросе `TYPE` указана директива `FOR XML`, результат возвращается в виде `xml`-данных.</span><span class="sxs-lookup"><span data-stu-id="05918-115">Because the `TYPE` directive is specified in `FOR XML`, the result is returned as `xml` type.</span></span>  
  
```  
USE AdventureWorks2012;  
Go  
SELECT BusinessEntityID, FirstName, LastName  
FROM Person.Person  
ORDER BY BusinessEntityID  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="05918-116">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="05918-116">This is the partial result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez"/>`  
  
 `<Person.Person BusinessEntityID="2" FirstName="Terri" LastName="Duffy"/>`  
  
 `...`  
  
### <a name="assigning-for-xml-query-results-to-an-xml-type-variable"></a><span data-ttu-id="05918-117">Назначение результатов запроса FOR XML переменной типа xml</span><span class="sxs-lookup"><span data-stu-id="05918-117">Assigning FOR XML query results to an xml type variable</span></span>  
 <span data-ttu-id="05918-118">В следующем примере результат инструкции FOR XML присваивается переменной `@x` типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="05918-118">In the following example, a FOR XML result is assigned to an `xml` type variable, `@x`.</span></span> <span data-ttu-id="05918-119">Запрос получает контактные данные, например,, `BusinessEntityID` `FirstName` `LastName` и дополнительные телефонные номера, из `AdditionalContactInfo` столбца `xml``TYPE` .</span><span class="sxs-lookup"><span data-stu-id="05918-119">The query retrieves contact information, such as the `BusinessEntityID`, `FirstName`, `LastName`, and additional telephone numbers, from the `AdditionalContactInfo` column of `xml``TYPE`.</span></span> <span data-ttu-id="05918-120">Поскольку в предложении `FOR XML` указана директива `TYPE`, результат возвращается в виде типа `xml` и присваивается переменной.</span><span class="sxs-lookup"><span data-stu-id="05918-120">Because the `FOR XML` clause specifies `TYPE` directive, the XML is returned as `xml` type and is assigned to a variable.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @x xml;  
SET @x = (  
   SELECT BusinessEntityID,   
          FirstName,   
          LastName,   
          AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
              //act:telephoneNumber/act:number') as MorePhoneNumbers  
   FROM Person.Person  
   FOR XML AUTO, TYPE);  
SELECT @x;  
GO  
```  
  
### <a name="querying-results-of-a-for-xml-query"></a><span data-ttu-id="05918-121">Запрос к результатам запроса FOR XML</span><span class="sxs-lookup"><span data-stu-id="05918-121">Querying results of a FOR XML query</span></span>  
 <span data-ttu-id="05918-122">Запросы FOR XML возвращают XML-данные.</span><span class="sxs-lookup"><span data-stu-id="05918-122">The FOR XML queries return XML.</span></span> <span data-ttu-id="05918-123">Таким образом, можно применить методы типа `xml`, например `query()` и `value()`, к XML-данным, возвращенным запросами FOR XML.</span><span class="sxs-lookup"><span data-stu-id="05918-123">Therefore, you can apply `xml` type methods, such as `query()` and `value()`, to the XML result returned by FOR XML queries.</span></span>  
  
 <span data-ttu-id="05918-124">В следующем запросе метод `query()` для типа данных `xml` используется с целью запроса к результатам запроса `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="05918-124">In the following query, the `query()` method of the `xml` data type is used to query the result of the `FOR XML` query.</span></span> <span data-ttu-id="05918-125">Дополнительные сведения см. в разделе [Метод query&#40;&#41;&#40;тип данных xml&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="05918-125">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT (SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
DECLARE namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
DECLARE namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
 //act:telephoneNumber/act:number  
') AS PhoneNumbers  
FROM Person.Person  
FOR XML AUTO, TYPE).query('/Person.Person[1]');  
```  
  
 <span data-ttu-id="05918-126">В следующем внутреннем запросе `SELECT ... FOR XML` возвращается результат типа `xml`, к которому внешняя инструкция `SELECT` применяет метод `query()` к типу `xml`.</span><span class="sxs-lookup"><span data-stu-id="05918-126">The inner `SELECT ... FOR XML` query returns an `xml` type result to which the outer `SELECT` applies the `query()` method to the `xml` type.</span></span> <span data-ttu-id="05918-127">Обратите внимание на указанную директиву `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="05918-127">Note the `TYPE` directive specified.</span></span>  
  
 <span data-ttu-id="05918-128">Результат:</span><span class="sxs-lookup"><span data-stu-id="05918-128">This is the result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez">`  
  
 `<PhoneNumbers>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">111-111-1111</act:number>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">112-111-1111</act:number>`  
  
 `</PhoneNumbers>`  
  
 `</Person.Person>`  
  
 <span data-ttu-id="05918-129">В следующем запросе метод `value()` для типа данных `xml` используется с целью извлечения значения из результирующего XML-документа, возвращенного запросом `SELECT...FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="05918-129">In the following query, the `value()` method of the `xml` data type is used to retrieve a value from the XML result returned by the `SELECT...FOR XML` query.</span></span> <span data-ttu-id="05918-130">Дополнительные сведения см. в разделе [Метод value (тип данных xml)](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="05918-130">For more information, see [value&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @FirstPhoneFromAdditionalContactInfo varchar(40);  
SELECT @FirstPhoneFromAdditionalContactInfo =   
 ( SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
   //act:telephoneNumber/act:number  
   ') AS PhoneNumbers  
   FROM Person.Person Contact  
   FOR XML AUTO, TYPE).value('  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
  /Contact[@BusinessEntityID="1"][1]/PhoneNumbers[1]/act:number[1]', 'varchar(40)'  
 )  
SELECT @FirstPhoneFromAdditionalContactInfo;  
```  
  
 <span data-ttu-id="05918-131">Выражение пути XQuery в методе `value()` извлекает из контактных сведений первый номер телефона заказчика с идентификатором `BusinessEntityID` , равным `1`.</span><span class="sxs-lookup"><span data-stu-id="05918-131">The XQuery path expression in the `value()` method retrieves the first telephone number of a customer contact whose `BusinessEntityID` is `1`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05918-132">Если директива TYPE не указана, результат запроса FOR XML возвращается в виде значения типа `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="05918-132">If the TYPE directive is not specified, the FOR XML query result is returned as type `nvarchar(max)`.</span></span>  
  
### <a name="using-for-xml-query-results-in-insert-update-and-delete-transact-sql-dml"></a><span data-ttu-id="05918-133">Использование результатов запроса FOR XML в инструкциях INSERT, UPDATE и DELETE (Transact-SQL DML)</span><span class="sxs-lookup"><span data-stu-id="05918-133">Using FOR XML query results in INSERT, UPDATE, and DELETE (Transact-SQL DML)</span></span>  
 <span data-ttu-id="05918-134">В следующем примере показано использование запросов FOR XML в инструкциях языка DML.</span><span class="sxs-lookup"><span data-stu-id="05918-134">The following example demonstrates how FOR XML queries can be used in Data Manipulation Language (DML) statements.</span></span> <span data-ttu-id="05918-135">В данном примере запрос `FOR XML` возвращает экземпляр типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="05918-135">In the example, the `FOR XML` returns an instance of `xml` type.</span></span> <span data-ttu-id="05918-136">Инструкция `INSERT` вставляет этот экземпляр XML в таблицу.</span><span class="sxs-lookup"><span data-stu-id="05918-136">The `INSERT` statement inserts this XML into a table.</span></span>  
  
```  
CREATE TABLE T1(intCol int, XmlCol xml);  
GO  
INSERT INTO T1   
VALUES(1, '<Root><ProductDescription ProductModelID="1" /></Root>');  
GO  
  
CREATE TABLE T2(XmlCol xml)  
GO  
INSERT INTO T2(XmlCol)   
SELECT (SELECT XmlCol.query('/Root')   
        FROM T1   
        FOR XML AUTO,TYPE);   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="05918-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="05918-137">See Also</span></span>  
 [<span data-ttu-id="05918-138">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="05918-138">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
