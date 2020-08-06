---
title: Определение сериализации данных XML | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- entitization rules [XML in SQL Server]
- serialization
- reparsing serialized XML structures
- encoding [XML in SQL Server]
- XML [SQL Server], serialization
- xml data type [SQL Server], serialization
- typed XML
ms.assetid: 42b0b5a4-bdd6-4a60-b451-c87f14758d4b
author: rothja
ms.author: jroth
ms.openlocfilehash: df87dddd9fd4cf067125314c9d798eaa42523576
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668674"
---
# <a name="define-the-serialization-of-xml-data"></a><span data-ttu-id="1a2dc-102">Определение сериализации XML-данных</span><span class="sxs-lookup"><span data-stu-id="1a2dc-102">Define the Serialization of XML Data</span></span>
  <span data-ttu-id="1a2dc-103">При явном или неявном приведении данных типа XML к строковому или двоичному типу данных SQL они сериализуются в соответствии с правилами, изложенными в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-103">When casting the xml data type explicitly or implicitly to a SQL string or binary type, the content of the xml data type will be serialized according to the rules outlined in this topic.</span></span>  
  
## <a name="serialization-encoding"></a><span data-ttu-id="1a2dc-104">Кодировка сериализации</span><span class="sxs-lookup"><span data-stu-id="1a2dc-104">Serialization Encoding</span></span>  
 <span data-ttu-id="1a2dc-105">Если целевой тип данных — VARBINARY, результат сериализуется в UTF-16 с отметкой порядка байтов UTF-16 в начале, но без XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-105">If the SQL target type is VARBINARY, the result is serialized in UTF-16 with a UTF-16-byte order mark in front, but without an XML declaration.</span></span> <span data-ttu-id="1a2dc-106">Если целевой тип слишком мал, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-106">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="1a2dc-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-107">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARBINARY(MAX))  
```  
  
 <span data-ttu-id="1a2dc-108">Результат:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-108">This is the result:</span></span>  
  
```  
0xFFFE3C0094032F003E00  
```  
  
 <span data-ttu-id="1a2dc-109">Если целевой тип данных — NVARCHAR или NCHAR, результат сериализуется в UTF-16 без отметки порядка байтов UTF-16 в начале и без XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-109">If the SQL target type is NVARCHAR or NCHAR, the result is serialized in UTF-16 without the byte order mark in front and without an XML declaration.</span></span> <span data-ttu-id="1a2dc-110">Если целевой тип слишком мал, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-110">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="1a2dc-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-111">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as NVARCHAR(MAX))  
```  
  
 <span data-ttu-id="1a2dc-112">Результат:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-112">This is the result:</span></span>  
  
```  
<Δ/>  
```  
  
 <span data-ttu-id="1a2dc-113">Если целевой тип данных — VARCHAR или NCHAR, результат сериализуется в кодировке, соответствующей кодовой странице параметров сортировки базы данных без отметки порядка байтов и XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-113">If the SQL target type is VARCHAR or NCHAR, the result is serialized in the encoding that corresponds to the database's collation code page without a byte order mark or XML declaration.</span></span> <span data-ttu-id="1a2dc-114">Если целевой тип слишком мал или значение не может быть отображено на целевую кодовую страницу параметров сортировки, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-114">If the target type is too small or the value cannot be mapped to the target collation code page, an error is raised.</span></span>  
  
 <span data-ttu-id="1a2dc-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-115">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARCHAR(MAX))  
```  
  
 <span data-ttu-id="1a2dc-116">Это может привести к ошибке, если текущая кодовая страница параметров сортировки не может представлять символ Юникода & # x10300; или будет представлять его в конкретной кодировке.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-116">This may result in an error, if the current collation's code page cannot represent the Unicode character &#x10300;, or it will represent it in the specific encoding.</span></span>  
  
 <span data-ttu-id="1a2dc-117">При возврате XML-результатов клиенту данные будут отправлены в кодировке UTF-16.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-117">When returning XML results to the client side, the data will be sent in UTF-16 encoding.</span></span> <span data-ttu-id="1a2dc-118">Поставщик с клиентской стороны, в свою очередь, представит данные в соответствии с правилами своего API.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-118">The client-side provider will then expose the data according to its API rules.</span></span>  
  
## <a name="serialization-of-the-xml-structures"></a><span data-ttu-id="1a2dc-119">Сериализация XML-структур</span><span class="sxs-lookup"><span data-stu-id="1a2dc-119">Serialization of the XML Structures</span></span>  
 <span data-ttu-id="1a2dc-120">Содержимое типа данных **xml** сериализуется обычным образом.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-120">The content of an **xml** data type is serialized in the usual way.</span></span> <span data-ttu-id="1a2dc-121">То есть узлы элементов сопоставляются разметке элементов, а текстовые узлы сопоставляются текстовому содержимому.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-121">Specifically, element nodes are mapped to element markup, and text nodes are mapped to text content.</span></span> <span data-ttu-id="1a2dc-122">При этом условия, в соответствии с которыми символы преобразуются в сущности, и способы сериализации типизированных атомарных значений описаны в последующих разделах.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-122">However, the circumstances under which characters are entitized and how typed atomic values are serialized are described in the following sections.</span></span>  
  
## <a name="entitization-of-xml-characters-during-serialization"></a><span data-ttu-id="1a2dc-123">Преобразование XML-символов в сущности при сериализации</span><span class="sxs-lookup"><span data-stu-id="1a2dc-123">Entitization of XML Characters During Serialization</span></span>  
 <span data-ttu-id="1a2dc-124">Для каждой сериализованной XML-структуры должна быть возможность повторного синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-124">Every serialized XML structure should be capable of being reparsed.</span></span> <span data-ttu-id="1a2dc-125">Поэтому некоторые символы сериализуются в виде сущностей, что позволяет избежать их искажения на стадии нормализации средства анализа XML.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-125">Therefore, some characters have to be serialized in an entitized way to preserve the round-trip capability of the characters through the XML parser's normalization phase .</span></span> <span data-ttu-id="1a2dc-126">Тем не менее чтобы документ стал корректным и мог быть произведен его синтаксический анализ, некоторые символы должны быть преобразованы в сущности.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-126">However, some characters have to be entitized so that the document is well-formed and, therefore, able to be parsed.</span></span> <span data-ttu-id="1a2dc-127">Ниже приведены правила преобразования в сущности, применяемые в процессе сериализации.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-127">Following are the entitization rules that apply during serialization:</span></span>  
  
-   <span data-ttu-id="1a2dc-128">Символы & и \<, and > всегда преобразуются в сущности &amp;, &lt; и &gt; соответственно, если они встречаются внутри значения атрибута или содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-128">The characters &, \<, and > are always entitized to &amp;, &lt;, and &gt; respectively, if they occur inside an attribute value or element content.</span></span>  
  
-   <span data-ttu-id="1a2dc-129">Так как значения атрибутов в SQL Server заключаются в кавычки (U+0022), знак кавычки в значениях атрибутов преобразуется в сущность &quot;.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-129">Because SQL Server uses a quotation mark (U+0022) for enclosing attribute values, the quotation mark in attribute values is entitized as &quot;.</span></span>  
  
-   <span data-ttu-id="1a2dc-130">Суррогатная пара преобразуется в цифровую ссылку (только при приведении на сервере).</span><span class="sxs-lookup"><span data-stu-id="1a2dc-130">A surrogate pair is entitized as a single numeric character reference, when casting on the server only.</span></span> <span data-ttu-id="1a2dc-131">Например, суррогатная пара U+D800 U+DF00 преобразуется в ссылку на символ &\#x00010300;.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-131">For example the surrogate pair U+D800 U+DF00 is entitized to the numeric character reference &\#x00010300;.</span></span>  
  
-   <span data-ttu-id="1a2dc-132">Чтобы при синтаксическом анализе защитить от нормализации символы табуляции (TAB, U+0009) и перевода строки (LF, U+000A), они в значениях атрибутов преобразуются в свои числовые сущности: &\#x9; и &\#xA; соответственно.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-132">To protect a TAB (U+0009) and a linefeed (LF, U+000A) from being normalized during parsing, they are entitized to their numeric character references &\#x9; and &\#xA; respectively, inside attribute values.</span></span>  
  
-   <span data-ttu-id="1a2dc-133">Для предотвращения нормализации при синтаксическом анализе символа возврата каретки (CR, U+000D) он и в значениях атрибутов, и в содержимом элементов преобразуется в числовую ссылку &\#xD;.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-133">To prevent a carriage return (CR, U+000D) from being normalized during parsing, it is entitized to its numeric character reference, &\#xD; inside both attribute values and element content.</span></span>  
  
-   <span data-ttu-id="1a2dc-134">Чтобы защитить текстовые узлы, не содержащие ничего кроме пробелов, один из них, обычно последний, преобразуется к сущности по числовой ссылке.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-134">To protect text nodes that only contain white space, one of the white-space characters, generally the last one, is entitized as its numeric character reference.</span></span> <span data-ttu-id="1a2dc-135">Таким образом, повторный синтаксический анализ сохраняет текстовый узел с пробелами, независимо от установки параметров обработки пробелов во время синтаксического разбора.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-135">In this way, reparsing preserves the white-space text node, regardless of the setting of the white-space handling during parsing.</span></span>  
  
 <span data-ttu-id="1a2dc-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-136">For example:</span></span>  
  
```sql
declare @u NVARCHAR(50)  
set @u = N'<a a="  
    '+NCHAR(0xD800)+NCHAR(0xDF00)+N'>">   '+NCHAR(0xA)+N'</a>'  
select CAST(CONVERT(XML,@u,1) as NVARCHAR(50))  
```  
  
 <span data-ttu-id="1a2dc-137">Результат:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-137">This is the result:</span></span>  
  
```  
<a a="  
    𐌀>">     
</a>  
```  
  
 <span data-ttu-id="1a2dc-138">Если применять правило защиты последнего пробела не нужно, при приведении типа **xml** к строковому или двоичному типу данных можно явно указать CONVERT с параметром 1.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-138">If you do not want to apply the last white-space protection rule, you can use the explicit CONVERT option 1 when casting from **xml** to a string or binary type.</span></span> <span data-ttu-id="1a2dc-139">Например, избежать преобразования сущностей можно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-139">For example, to avoid entitization, you can do the following:</span></span>  
  
```sql
select CONVERT(NVARCHAR(50), CONVERT(XML, '<a>   </a>', 1), 1)  
```  
  
 <span data-ttu-id="1a2dc-140">Обратите внимание, что результатом [метода query() (тип данных xml)](/sql/t-sql/xml/query-method-xml-data-type) будет экземпляр типа данных xml.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-140">Note that, the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) results in an xml data type instance.</span></span> <span data-ttu-id="1a2dc-141">Поэтому любой результат метода **query()** , который приводится к строковому или двоичному типу, преобразуется в сущности в соответствии с описанными выше правилами.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-141">Therefore, any result of the **query()** method that is cast to a string or binary type is entitized according to the previously described rules.</span></span> <span data-ttu-id="1a2dc-142">Если нужно получить строковые значения без преобразования в сущности, пользуйтесь [методом value() (тип данных xml)](/sql/t-sql/xml/value-method-xml-data-type) .</span><span class="sxs-lookup"><span data-stu-id="1a2dc-142">If you want to obtain the string values that are not entitized, you should use the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) instead.</span></span> <span data-ttu-id="1a2dc-143">Ниже приведен пример использования метода **query()** .</span><span class="sxs-lookup"><span data-stu-id="1a2dc-143">Following is an example of using the **query()** method:</span></span>  
  
```sql
declare @x xml  
set @x = N'<a>This example contains an entitized char: <.</a>'  
select @x.query('/a/text()')  
```  
  
 <span data-ttu-id="1a2dc-144">Результат:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-144">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
 <span data-ttu-id="1a2dc-145">А это пример использования метода **value()** :</span><span class="sxs-lookup"><span data-stu-id="1a2dc-145">Following is an example of using the **value()** method:</span></span>  
  
```sql
select @x.value('(/a/text())[1]', 'nvarchar(100)')  
```  
  
 <span data-ttu-id="1a2dc-146">Результат:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-146">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
## <a name="serializing-a-typed-xml-data-type"></a><span data-ttu-id="1a2dc-147">Сериализация типизированных XML-данных</span><span class="sxs-lookup"><span data-stu-id="1a2dc-147">Serializing a Typed xml Data Type</span></span>  
 <span data-ttu-id="1a2dc-148">Экземпляр типизированных **XML** -данных содержит значения, типизированные согласно своему типу XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-148">A typed **xml** data type instance contains values that are typed according to their XML schema types.</span></span> <span data-ttu-id="1a2dc-149">Эти значения сериализуются в соответствии с типом XML-схемы в том же формате, какой получается в результате приведения к типу xs:string в XQuery.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-149">These values are serialized according to their XML schema type in the same format as the XQuery cast to xs:string produces.</span></span> <span data-ttu-id="1a2dc-150">Дополнительные сведения см. в разделе [Правила приведения типов в запросах XQuery](/sql/xquery/type-casting-rules-in-xquery).</span><span class="sxs-lookup"><span data-stu-id="1a2dc-150">For more information, see [Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery).</span></span>  
  
 <span data-ttu-id="1a2dc-151">Например, значение 1.34e1 типа xs:double сериализуется в значение 13.4, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-151">For example, the xs:double value 1.34e1 is serialized to 13.4 as shown in the following example:</span></span>  
  
```sql
declare @x xml  
set @x =''  
select CAST(@x.query('1.34e1') as nvarchar(50))  
```  
  
 <span data-ttu-id="1a2dc-152">Возвращается строковое значение 13.4.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-152">This returns the string value 13.4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a2dc-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a2dc-153">See Also</span></span>  
 <span data-ttu-id="1a2dc-154">[Правила приведения типов в запросах XQuery](/sql/xquery/type-casting-rules-in-xquery) </span><span class="sxs-lookup"><span data-stu-id="1a2dc-154">[Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery) </span></span>  
 [<span data-ttu-id="1a2dc-155">Функции CAST и CONVERT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1a2dc-155">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
