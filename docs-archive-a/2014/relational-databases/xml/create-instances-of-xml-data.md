---
title: Создание экземпляров XML-данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- type casting string instances [XML in SQL Server]
- XML [SQL Server], typed
- xml data type [SQL Server], generating instances
- casting string instances [XML in SQL Server]
- typed XML
- generating XML instances [SQL Server]
- XML [SQL Server], generating instances
- white space [XML in SQL Server]
ms.assetid: dbd6c06f-db6e-44a7-855a-6a55bf374907
author: rothja
ms.author: jroth
ms.openlocfilehash: c857b9ebbe559de34fdac925642f9270d9cbf936
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752012"
---
# <a name="create-instances-of-xml-data"></a><span data-ttu-id="e9cf5-102">Создание экземпляров XML-данных</span><span class="sxs-lookup"><span data-stu-id="e9cf5-102">Create Instances of XML Data</span></span>
  <span data-ttu-id="e9cf5-103">В этом разделе описывается формирование XML-экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-103">This topic describes how to generate XML instances.</span></span>  
  
 <span data-ttu-id="e9cf5-104">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]сформировать XML-экземпляры можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can generate XML instances in the following ways:</span></span>  
  
-   <span data-ttu-id="e9cf5-105">тип экземпляров приведения строки;</span><span class="sxs-lookup"><span data-stu-id="e9cf5-105">Type casting string instances.</span></span>  
  
-   <span data-ttu-id="e9cf5-106">использование инструкции SELECT с предложением FOR XML;</span><span class="sxs-lookup"><span data-stu-id="e9cf5-106">Using the SELECT statement with the FOR XML clause.</span></span>  
  
-   <span data-ttu-id="e9cf5-107">использование постоянных назначений;</span><span class="sxs-lookup"><span data-stu-id="e9cf5-107">Using constant assignments.</span></span>  
  
-   <span data-ttu-id="e9cf5-108">использование массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-108">Using bulk load.</span></span>  
  
## <a name="type-casting-string-and-binary-instances"></a><span data-ttu-id="e9cf5-109">Строка приведения типа и двоичные экземпляры</span><span class="sxs-lookup"><span data-stu-id="e9cf5-109">Type Casting String and Binary Instances</span></span>  
 <span data-ttu-id="e9cf5-110">Можно выполнить синтаксический анализ любых [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] строковых типов данных, например [**n**] [**var**]**char**, **[n] text**, **varbinary**и **Image**, в `xml` тип данных путем приведения (приведения) или преобразования (преобразования) строки в `xml` тип данных.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-110">You can parse any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] string data types, such as [**n**][**var**]**char**, **[n]text**, **varbinary**,and **image**, into the `xml` data type by casting (CAST) or converting (CONVERT) the string to the `xml` data type.</span></span> <span data-ttu-id="e9cf5-111">Проверка нетипизированного XML подтверждает, что он сформирован правильно.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-111">Untyped XML is checked to confirm that it is well formed.</span></span> <span data-ttu-id="e9cf5-112">При наличии схемы, связанной с `xml` типом, также выполняется проверка.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-112">If there is a schema associated with the `xml` type, validation is also performed.</span></span> <span data-ttu-id="e9cf5-113">Дополнительные сведения см. в статье [Сравнение типизированного и нетипизированного XML](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-113">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
 <span data-ttu-id="e9cf5-114">XML-документы могут быть кодированы различными кодировками (например, UTF-8, UTF-16, windows-1252).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-114">XML documents can be encoded with different encodings (for example, UTF-8, UTF-16, windows-1252).</span></span> <span data-ttu-id="e9cf5-115">Следующие правила дают сведения о том, как строка и двоичный источник взаимодействуют с кодировкой XML-документа, и как ведет себя синтаксический анализатор.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-115">The following outlines the rules on how the string and binary source types interact with the XML document encoding and how the parser behaves.</span></span>  
  
 <span data-ttu-id="e9cf5-116">Так как тип **nvarchar** предполагает двухбайтовую кодировку Юникод, например UTF-16 или UCS-2, синтаксический XML-анализатор сочтет значение строки за XML-документ или фрагмент в двухбайтовой кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-116">Since **nvarchar** assumes a two-byte unicode encoding such as UTF-16 or UCS-2, the XML parser will treat the string value as a two-byte Unicode encoded XML document or fragment.</span></span> <span data-ttu-id="e9cf5-117">Это значит, что XML-документ должен быть закодирован в двухбайтовой кодировке Юникод, а также совмещен с типом данных источника.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-117">This means that the XML document needs to be encoded in a two-byte Unicode encoding as well to be compatible with the source data type.</span></span> <span data-ttu-id="e9cf5-118">XML-документ в кодировке UTF-16 может иметь отметку порядка байтов (BOM) UTF-16, но не обязан, так как контекст типа источника уточняет, что он может быть документом, закодированным только в двухбайтовой кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-118">A UTF-16 encoded XML document can have a UTF-16 byte order mark (BOM), but it does not need to, since the context of the source type makes it clear that it can only be a two-byte Unicode encoded document.</span></span>  
  
 <span data-ttu-id="e9cf5-119">Содержимое строки **varchar** синтаксический XML-анализатор принимает за однобайтовый XML-документ/фрагмент.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-119">The content of a **varchar** string is treated as a one-byte encoded XML document/fragment by the XML parser.</span></span> <span data-ttu-id="e9cf5-120">Так как строка источника **varchar** имеет связанную кодовую страницу, синтаксический анализатор будет использовать эту кодовую страницу для кодирования, если явно не была указана кодировка в самом XML. Если XML-экземпляр имеет отметку BOM или декларацию кодирования, отметка BOM или декларация должна быть согласована с кодовой страницей, иначе синтаксический анализатор выдаст ошибку.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-120">Since the **varchar** source string has a code page associated, the parser will use that code page for the encoding if no explicit encoding is specified in the XML itself If an XML instance has a BOM or an encoding declaration, the BOM or declaration needs to be consistent with the code page, otherwise the parser will report an error.</span></span>  
  
 <span data-ttu-id="e9cf5-121">Содержимое строки **varbinary** принимается за поток кодовых точек, который передается непосредственно синтаксическому XML-анализатору.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-121">The content of **varbinary** is treated as a codepoint stream that is passed directly to the XML parser.</span></span> <span data-ttu-id="e9cf5-122">Таким образом, XML-документ или фрагмент должен содержать встроенную отметку BOM или другие сведения о кодировании.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-122">Thus, the XML document or fragment needs to provide the BOM or other encoding information inline.</span></span> <span data-ttu-id="e9cf5-123">Чтобы определить кодировку, синтаксическому анализатору достаточно будет просто просмотреть поток.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-123">The parser will only look at the stream to determine the encoding.</span></span> <span data-ttu-id="e9cf5-124">Это значит, что XML в кодировке UTF-16 должен содержать отметку UTF-16 BOM, а экземпляр без отметки BOM и без декларации о кодировании будет интерпретироваться как UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-124">This means that UTF-16 encoded XML needs to provide the UTF-16 BOM and an instance without BOM and without a declaration encoding will be interpreted as UTF-8.</span></span>  
  
 <span data-ttu-id="e9cf5-125">Если кодировка XML-документа не известна заранее, а данные вместо XML передаются как строка или двоичные данные до приведения в XML, рекомендуется рассматривать данные как **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-125">If the encoding of the XML document is not known in advance and the data is passed as string or binary data instead of XML data before casting to XML, it is recommended to treat the data as **varbinary**.</span></span> <span data-ttu-id="e9cf5-126">Например, при считывании данных из XML-файла с помощью функции OpenRowset() необходимо указать данные для считывания как значения **varbinary(max)** :</span><span class="sxs-lookup"><span data-stu-id="e9cf5-126">For example, when reading data from an XML file using OpenRowset(), one should specify the data to be read as a **varbinary(max)** value:</span></span>  
  
```  
select CAST(x as XML)   
from OpenRowset(BULK 'filename.xml', SINGLE_BLOB) R(x)  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e9cf5-127">внутренне представляет XML в эффективном двоичном представлении, использующем кодировку UTF-16.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-127">internally represents XML in an efficient binary representation that uses UTF-16 encoding.</span></span> <span data-ttu-id="e9cf5-128">Пользовательская кодировка не сохранена, но она учитывается в процессе синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-128">User-provided encoding is not preserved, but is considered during the parse process.</span></span>  
  
### <a name="type-casting-clr-user-defined-types"></a><span data-ttu-id="e9cf5-129">Приведение определяемых пользователем типов CLR</span><span class="sxs-lookup"><span data-stu-id="e9cf5-129">Type Casting CLR user-defined types</span></span>  
 <span data-ttu-id="e9cf5-130">Если определяемый пользователем тип данных CLR имеет XML-сериализацию, экземпляры этого типа могут быть явно приведены к типу данных XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-130">If a CLR user-defined type has an XML Serialization, instances of that type can be explicitly cast to an XML datatype.</span></span> <span data-ttu-id="e9cf5-131">Более подробные сведения о XML-сериализации определяемого пользователем типа данных CLR см. в статье [Сериализация XML из объектов базы данных CLR](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-131">For more details about the XML serialization of a CLR user-defined typed, see [XML Serialization from CLR Database Objects](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span></span>  
  
### <a name="white-space-handling-in-typed-xml"></a><span data-ttu-id="e9cf5-132">Обработка пробела в типизированном XML</span><span class="sxs-lookup"><span data-stu-id="e9cf5-132">White Space Handling in Typed XML</span></span>  
 <span data-ttu-id="e9cf5-133">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]пробел внутри содержимого элемента считается незначащим, если он появляется внутри последовательности данных, содержащей только пробельные символы, разделенных разметкой, например начальными и конечными тегами. Такой пробел не преобразуется в сущность.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], white space inside element content is considered insignificant if it occurs inside a sequence of white-space-only character data delimited by markup, such as begin or end tags, and is not entitized.</span></span> <span data-ttu-id="e9cf5-134">(секции CDATA игнорируются). Данная обработка пробела отличается от пробела, описанного в спецификации XML 1.0, опубликованной консорциумом World Wide Web (W3C).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-134">(CDATA sections are ignored.) This handling of white space handling is different from how white space is described in the XML 1.0 specification published by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="e9cf5-135">Это происходит потому, что в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] средство синтаксического анализа XML распознает только ограниченное число подмножеств DTD, как указано в XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-135">This is because the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recognizes only a limited number of DTD subsets, as defined in XML 1.0.</span></span> <span data-ttu-id="e9cf5-136">Дополнительные сведения об ограниченных подмножествах DTD, поддерживаемых в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в статье [CAST и CONVERT (Transact-SQL)](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-136">For more information about the limited DTD subsets supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
 <span data-ttu-id="e9cf5-137">Синтаксический XML-анализатор отменяет незначащие пробелы при преобразовании строковых данных в XML по умолчанию, если выполняется одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-137">By default, the XML parser discards insignificant white space when it converts string data to XML if either of the following is true:</span></span>  
  
-   <span data-ttu-id="e9cf5-138">`The xml:space` не определен на элементе или его родителях;</span><span class="sxs-lookup"><span data-stu-id="e9cf5-138">`The xml:space` attribute is not defined on an element or its ancestor elements.</span></span>  
  
-   <span data-ttu-id="e9cf5-139">атрибут `xml:space` , действующий на элемент или на одного из его родителей, имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-139">The `xml:space` attribute in effect on an element, or one of its ancestor elements, has the value of default.</span></span>  
  
 <span data-ttu-id="e9cf5-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-140">For example:</span></span>  
  
```  
declare @x xml  
set @x = '<root>      <child/>     </root>'  
select @x   
```  
  
 <span data-ttu-id="e9cf5-141">Результат:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-141">This is the result:</span></span>  
  
```  
<root><child/></root>  
```  
  
 <span data-ttu-id="e9cf5-142">Однако можно изменить это поведение.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-142">However, you can change this behavior.</span></span> <span data-ttu-id="e9cf5-143">Чтобы сохранить пробел для экземпляра xml DT, необходимо использовать оператор CONVERT и его дополнительный параметр *style* , установленный в значение 1.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-143">To preserve white space for an xml DT instance, use the CONVERT operator and its optional *style* parameter set to a value of 1.</span></span> <span data-ttu-id="e9cf5-144">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-144">For example:</span></span>  
  
```  
SELECT CONVERT(xml, N'<root>      <child/>     </root>', 1)  
```  
  
 <span data-ttu-id="e9cf5-145">Если параметр *style* не используется или его значение установлено в 0, незначащий пробел не сохраняется для преобразования экземпляра xml DT.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-145">If the *style* parameter is either not used or its value is set to 0, insignificant white space is not preserved for the conversion of the xml DT instance.</span></span> <span data-ttu-id="e9cf5-146">Дополнительные сведения о том, как использовать оператор CONVERT и его параметр *style* при преобразовании строковых данных в экземпляр xml DT, см. в статье [CAST и CONVERT (Transact-SQL)](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-146">For more information about how to use the CONVERT operator and its *style* parameter when converting string data to xml DT instances, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
### <a name="example-cast-a-string-value-to-typed-xml-and-assign-it-to-a-column"></a><span data-ttu-id="e9cf5-147">Пример Приведение строкового значения к типизированному XML и назначение его столбцу</span><span class="sxs-lookup"><span data-stu-id="e9cf5-147">Example: Cast a string value to typed xml and assign it to a column</span></span>  
 <span data-ttu-id="e9cf5-148">В следующем примере приведена строковая переменная, содержащая фрагмент XML, в `xml` тип данных, а затем она сохраняется в `xml` столбце Type:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-148">The following example casts a string variable that contains an XML fragment to the `xml` data type and then stores it in the `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
go  
DECLARE  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
```  
  
 <span data-ttu-id="e9cf5-149">Следующая операция вставки неявно преобразовывает строку в `xml` Тип:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-149">The following insert operation implicitly converts from a string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, @s)   
```  
  
 <span data-ttu-id="e9cf5-150">Можно явно привести строку () к `xml` типу:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-150">You can explicitly cast() the string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, cast (@s as xml))  
```  
  
 <span data-ttu-id="e9cf5-151">Или можно использовать функцию convert(), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-151">Or you can use convert(), as shown in the following:</span></span>  
  
```  
INSERT INTO T VALUES (3, convert (xml, @s))   
```  
  
### <a name="example-convert-a-string-to-typed-xml-and-assign-it-to-a-variable"></a><span data-ttu-id="e9cf5-152">Пример Преобразование строкового значения в типизированный XML и присвоение его переменной</span><span class="sxs-lookup"><span data-stu-id="e9cf5-152">Example: Convert a string to typed xml and assign it to a variable</span></span>  
 <span data-ttu-id="e9cf5-153">В следующем примере строка преобразуется в `xml` тип и присваивается переменной `xml` типа данных:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-153">In the following example, a string is converted to `xml` type and assigned to a variable of the `xml` data type:</span></span>  
  
```  
declare @x xml  
declare  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
set @x =convert (xml, @s)  
select @x  
```  
  
## <a name="using-the-select-statement-with-a-for-xml-clause"></a><span data-ttu-id="e9cf5-154">Использование инструкции SELECT с предложением FOR XML</span><span class="sxs-lookup"><span data-stu-id="e9cf5-154">Using the SELECT Statement with a FOR XML Clause</span></span>  
 <span data-ttu-id="e9cf5-155">Чтобы получить результаты в виде XML, можно использовать предложение FOR XML в инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-155">You can use the FOR XML clause in a SELECT statement to return results as XML.</span></span> <span data-ttu-id="e9cf5-156">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-156">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = (SELECT Column1, Column2  
               FROM   Table1, Table2  
               WHERE   Some condition  
               FOR XML AUTO)  
 ...  
```  
  
 <span data-ttu-id="e9cf5-157">Инструкция SELECT возвращает текстовый XML-фрагмент, который затем анализируется во время присваивания `xml` переменной типа данных.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-157">The SELECT statement returns a textual XML fragment that is then parsed during the assignment to the `xml` data type variable.</span></span>  
  
 <span data-ttu-id="e9cf5-158">Можно также использовать [директиву Type](type-directive-in-for-xml-queries.md) в предложении FOR XML, которая напрямую возвращает результат запроса FOR XML в виде `xml` типа:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-158">You can also use the [TYPE directive](type-directive-in-for-xml-queries.md) in the FOR XML clause that directly returns a FOR XML query result as `xml` type:</span></span>  
  
```  
Declare @xmlDoc xml  
SET @xmlDoc = (SELECT ProductModelID, Name  
               FROM   Production.ProductModel  
               WHERE  ProductModelID=19  
               FOR XML AUTO, TYPE)  
SELECT @xmlDoc  
```  
  
 <span data-ttu-id="e9cf5-159">Результат:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-159">This is the result:</span></span>  
  
```  
<Production.ProductModel ProductModelID="19" Name="Mountain-100" />...  
```  
  
 <span data-ttu-id="e9cf5-160">В следующем примере типизированный `xml` результат запроса FOR XML вставляется в `xml` столбец типа:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-160">In the following example, the typed `xml` result of a FOR XML query is inserted into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T1 (c1 int, c2 xml)  
go  
INSERT T1(c1, c2)  
SELECT 1, (SELECT ProductModelID, Name  
           FROM Production.ProductModel  
           WHERE ProductModelID=19  
           FOR XML AUTO, TYPE)  
SELECT * FROM T1  
go  
```  
  
 <span data-ttu-id="e9cf5-161">Дополнительные сведения о предложении FOR XML см. в статье [FOR XML (SQL Server)](for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-161">For more information about FOR XML, see [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e9cf5-162">возвращает экземпляры типа данных `xml` клиенту в результате выполнения различных серверных конструкций, таких как запросы FOR XML с директивой TYPE или запросы, в которых тип данных `xml` используется для возвращения XML из столбцов, переменных и выходных параметров SQL.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-162">returns `xml` data type instances to the client as a result of different server constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML from SQL columns, variables, and output parameters.</span></span> <span data-ttu-id="e9cf5-163">В коде клиентского приложения поставщик ADO.NET требует, чтобы информация типа данных `xml` отправлялась сервером в двоичном представлении.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-163">In client application code, the ADO.NET provider requests that this `xml` data type information be sent in a binary encoding from the server.</span></span> <span data-ttu-id="e9cf5-164">Однако в запросах FOR XML без директивы TYPE XML-данные возвращаются в строковом формате.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-164">However, if you are using FOR XML without the TYPE directive, the XML data returns as a string type.</span></span> <span data-ttu-id="e9cf5-165">В любом случае поставщик клиента всегда будет иметь возможность обрабатывать XML-данные в любом из форматов.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-165">In any case, the client provider will always be able to handle either form of XML.</span></span>  
  
## <a name="using-constant-assignments"></a><span data-ttu-id="e9cf5-166">Использование постоянных назначений</span><span class="sxs-lookup"><span data-stu-id="e9cf5-166">Using Constant Assignments</span></span>  
 <span data-ttu-id="e9cf5-167">Строковая константа может использоваться там, где ожидается экземпляр `xml` типа данных.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-167">A string constant can be used where an instance of the `xml` data type is expected.</span></span> <span data-ttu-id="e9cf5-168">Это то же самое, что и неявное приведение (CAST) строки в XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-168">This is the same as an implied CAST of string to XML.</span></span> <span data-ttu-id="e9cf5-169">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-169">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
-- Or  
SET @xmlDoc = N'<?xml version="1.0" encoding="ucs-2"?><doc/>'  
```  
  
 <span data-ttu-id="e9cf5-170">Предыдущий пример неявно преобразует строку в `xml` тип данных и присваивает ее `xml` переменной типа.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-170">The previous example implicitly converts the string to the `xml` data type and assigns it to an `xml` type variable.</span></span>  
  
 <span data-ttu-id="e9cf5-171">В следующем примере константная строка вставляется в `xml` столбец типа:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-171">The following example inserts a constant string into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
INSERT INTO T VALUES (3, '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>')   
```  
  
> [!NOTE]  
>  <span data-ttu-id="e9cf5-172">Для типизированного XML подлинность XML проверяется в отношении указанной схемы.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-172">For typed XML, the XML is validated against the specified schema.</span></span> <span data-ttu-id="e9cf5-173">Дополнительные сведения см. в статье [Сравнение типизированного и нетипизированного XML](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-173">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
## <a name="using-bulk-load"></a><span data-ttu-id="e9cf5-174">Использование массовой загрузки</span><span class="sxs-lookup"><span data-stu-id="e9cf5-174">Using Bulk Load</span></span>  
 <span data-ttu-id="e9cf5-175">Улучшенная функциональность [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) позволяет произвести массовую загрузку XML-документов в базу данных.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-175">The enhanced [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) functionality allows you to bulk load XML documents in the database.</span></span> <span data-ttu-id="e9cf5-176">Можно выполнить массовый загрузку экземпляров XML из файлов в `xml` столбцы типа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-176">You can bulk load XML instances from files into the `xml` type columns in the database.</span></span> <span data-ttu-id="e9cf5-177">Дополнительные сведения см. в статье [Примеры массового импорта и экспорта XML-документов (SQL Server)](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-177">For working samples, see [Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span></span> <span data-ttu-id="e9cf5-178">Дополнительные сведения о загрузке XML-документов см. в статье [Загрузка XML-данных](load-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="e9cf5-178">For more information about loading XML documents, see [Load XML Data](load-xml-data.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9cf5-179">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e9cf5-179">In This Section</span></span>  
  
|<span data-ttu-id="e9cf5-180">Раздел</span><span class="sxs-lookup"><span data-stu-id="e9cf5-180">Topic</span></span>|<span data-ttu-id="e9cf5-181">Описание</span><span class="sxs-lookup"><span data-stu-id="e9cf5-181">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e9cf5-182">Получение и запрос данных XML</span><span class="sxs-lookup"><span data-stu-id="e9cf5-182">Retrieve and Query XML Data</span></span>](retrieve-and-query-xml-data.md)|<span data-ttu-id="e9cf5-183">Описывает компоненты экземпляров XML, не фиксируемых при сохранении экземпляров в базах данных.</span><span class="sxs-lookup"><span data-stu-id="e9cf5-183">Describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9cf5-184">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9cf5-184">See Also</span></span>  
 <span data-ttu-id="e9cf5-185">[Сравнение типизированного и нетипизированного XML](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e9cf5-185">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="e9cf5-186">[методов типа данных xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="e9cf5-186">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="e9cf5-187">[Язык модификации XML-данных (XML DML)](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="e9cf5-187">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="e9cf5-188">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e9cf5-188">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
