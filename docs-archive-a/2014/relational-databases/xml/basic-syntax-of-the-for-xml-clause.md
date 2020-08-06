---
title: Базовый синтаксис предложения FOR XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- BINARY BASE64 directive
- ROOT directive
- FOR XML clause, BINARY BASE64 directive
- FOR XML clause, syntax
- FOR XML clause, ROOT directive
ms.assetid: df19ecbf-d28e-4e9c-aaa3-700f8bbd3be4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc0410e7a54674673f64442d8a3cf9476d250033
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654961"
---
# <a name="basic-syntax-of-the-for-xml-clause"></a><span data-ttu-id="9afd7-102">Базовый синтаксис предложения FOR XML</span><span class="sxs-lookup"><span data-stu-id="9afd7-102">Basic Syntax of the FOR XML Clause</span></span>
  <span data-ttu-id="9afd7-103">Режимом предложения FOR XML может быть RAW, AUTO, EXPLICIT или PATH.</span><span class="sxs-lookup"><span data-stu-id="9afd7-103">The FOR XML mode can be RAW, AUTO, EXPLICIT, or PATH.</span></span> <span data-ttu-id="9afd7-104">Он определяет форму получаемого в результате XML-документа.</span><span class="sxs-lookup"><span data-stu-id="9afd7-104">It determines the shape of the resulting XML.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9afd7-105">Директива XMLDATA для параметра XML FOR является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9afd7-105">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="9afd7-106">В режимах RAW и AUTO следует использовать создание XSD-схем.</span><span class="sxs-lookup"><span data-stu-id="9afd7-106">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="9afd7-107">В режиме EXPLICT для директивы XMLDATA замены нет.</span><span class="sxs-lookup"><span data-stu-id="9afd7-107">There is no replacement for the XMLDATA directive in EXPLICT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="9afd7-108">Ниже приведен базовый синтаксис, описанный в [предложении for (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span><span class="sxs-lookup"><span data-stu-id="9afd7-108">Following is the basic syntax that is described in [FOR Clause (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span></span>  
  
```  
[ FOR { BROWSE | <XML> } ]  
<XML> ::=  
XML   
    {   
      { RAW [ ('ElementName') ] | AUTO }   
        [   
           <CommonDirectives>   
           [ , { XMLDATA | XMLSCHEMA [ ('TargetNameSpaceURI') ]} ]   
           [ , ELEMENTS [ XSINIL | ABSENT ]   
        ]  
      | EXPLICIT   
        [   
           <CommonDirectives>   
           [ , XMLDATA ]   
        ]  
      | PATH [ ('ElementName') ]   
        [   
           <CommonDirectives>   
           [ , ELEMENTS [ XSINIL | ABSENT ] ]  
        ]  
     }   
  
 <CommonDirectives> ::=   
   [ , BINARY BASE64 ]  
   [ , TYPE ]  
   [ , ROOT [ ('RootName') ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9afd7-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9afd7-109">Arguments</span></span>  
 <span data-ttu-id="9afd7-110">RAW[('*ElementName*')]</span><span class="sxs-lookup"><span data-stu-id="9afd7-110">RAW[('*ElementName*')]</span></span>  
 <span data-ttu-id="9afd7-111">Принимает результат запроса и преобразует каждую строку результирующего набора в элемент XML с универсальным идентификатором \<row /> в качестве тега элемента.</span><span class="sxs-lookup"><span data-stu-id="9afd7-111">Takes the query result and transforms each row in the result set into an XML element that has a generic identifier, \<row />, as the element tag.</span></span> <span data-ttu-id="9afd7-112">При использовании этой директивы можно дополнительно указать имя для элемента строки.</span><span class="sxs-lookup"><span data-stu-id="9afd7-112">You can optionally specify a name for the row element when you use this directive.</span></span> <span data-ttu-id="9afd7-113">Полученный в результате XML-документ будет использовать указанное имя *ElementName* в качестве элемента, сформированного для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="9afd7-113">The resulting XML will use the specified *ElementName* as the row element generated for each row.</span></span> <span data-ttu-id="9afd7-114">Дополнительные сведения см. в статье [Использование с RAW Mode для FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-114">For more information, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9afd7-115">AUTO</span><span class="sxs-lookup"><span data-stu-id="9afd7-115">AUTO</span></span>  
 <span data-ttu-id="9afd7-116">Возвращает результаты запроса в виде простого вложенного дерева XML.</span><span class="sxs-lookup"><span data-stu-id="9afd7-116">Returns query results in a simple, nested XML tree.</span></span> <span data-ttu-id="9afd7-117">Каждая таблица в предложении FROM, в которой хотя бы один столбец перечислен в предложении SELECT, представлена в виде элемента XML.</span><span class="sxs-lookup"><span data-stu-id="9afd7-117">Each table in the FROM clause for which at least one column is listed in the SELECT clause is represented as an XML element.</span></span> <span data-ttu-id="9afd7-118">Столбцы, перечисленные в предложении SELECT, сопоставлены с соответствующими атрибутами элемента.</span><span class="sxs-lookup"><span data-stu-id="9afd7-118">The columns listed in the SELECT clause are mapped to the appropriate element attributes.</span></span> <span data-ttu-id="9afd7-119">Дополнительные сведения см. в статье [Использование с AUTO Mode для FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-119">For more information, see [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9afd7-120">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="9afd7-120">EXPLICIT</span></span>  
 <span data-ttu-id="9afd7-121">Указывает, что форма конечного дерева XML определена явно.</span><span class="sxs-lookup"><span data-stu-id="9afd7-121">Specifies that the shape of the resulting XML tree is defined explicitly.</span></span> <span data-ttu-id="9afd7-122">В этом режиме запросы должны быть составлены особым образом, при котором необходимые данные о вложенности определяются явно.</span><span class="sxs-lookup"><span data-stu-id="9afd7-122">By using this mode, queries must be written in a particular way so additional information about the nesting you want is specified explicitly.</span></span> <span data-ttu-id="9afd7-123">Дополнительные сведения см. в статье [Использование с EXPLICIT Mode для FOR XML](use-explicit-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-123">For more information, see [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9afd7-124">PATH</span><span class="sxs-lookup"><span data-stu-id="9afd7-124">PATH</span></span>  
 <span data-ttu-id="9afd7-125">Предоставляет более простой способ смешивания элементов и атрибутов, а также введения дополнительной вложенности для представления сложных свойств.</span><span class="sxs-lookup"><span data-stu-id="9afd7-125">Provides a simpler way to mix elements and attributes, and to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="9afd7-126">Чтобы создать такой тип XML из набора строк, можно использовать запросы режима FOR XML EXPLICIT, однако режим PATH представляет собой более простую альтернативу потенциально громоздким запросам режима EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="9afd7-126">You can use FOR XML EXPLICIT mode queries to construct this kind of XML from a rowset, but the PATH mode provides a simpler alternative to the possibly cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="9afd7-127">Режим PATH дополнительно к возможности записи вложенных запросов FOR XML и возвращения экземпляров типа **xml** с помощью директивы TYPE позволяет писать менее сложные запросы.</span><span class="sxs-lookup"><span data-stu-id="9afd7-127">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span> <span data-ttu-id="9afd7-128">Он является альтернативой написанию большинства запросов в режиме EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="9afd7-128">It provides an alternative to writing most EXPLICIT mode queries.</span></span> <span data-ttu-id="9afd7-129">По умолчанию режим PATH формирует упаковщик элемента \<row> для каждой строки в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="9afd7-129">By default, PATH mode generates a \<row> element wrapper for each row in the result set.</span></span> <span data-ttu-id="9afd7-130">Также можно указать имя элемента.</span><span class="sxs-lookup"><span data-stu-id="9afd7-130">You can optionally specify an element name.</span></span> <span data-ttu-id="9afd7-131">Если имя указывается, оно используется в качестве имени упаковщика элемента.</span><span class="sxs-lookup"><span data-stu-id="9afd7-131">If you do, the specified name is used as the wrapper element name.</span></span> <span data-ttu-id="9afd7-132">При предоставлении пустой строки (FOR XML PATH ('')) упаковщик элемента не формируется.</span><span class="sxs-lookup"><span data-stu-id="9afd7-132">If you provide an empty string (FOR XML PATH ('')), no wrapper element is generated.</span></span> <span data-ttu-id="9afd7-133">Дополнительные сведения см. в статье [Использование с PATH Mode для FOR XML](use-path-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-133">For more information, see [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9afd7-134">XMLDATA</span><span class="sxs-lookup"><span data-stu-id="9afd7-134">XMLDATA</span></span>  
 <span data-ttu-id="9afd7-135">Указывает, что будет возвращена встроенная XDR-схема.</span><span class="sxs-lookup"><span data-stu-id="9afd7-135">Specifies that an inline XML-Data Reduced (XDR) schema should be returned.</span></span> <span data-ttu-id="9afd7-136">Эта схема присоединяется к документу в качестве встроенной схемы.</span><span class="sxs-lookup"><span data-stu-id="9afd7-136">The schema is prepended to the document as an inline schema.</span></span> <span data-ttu-id="9afd7-137">Работающий пример см. в статье [Использование с RAW Mode для FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-137">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9afd7-138">XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="9afd7-138">XMLSCHEMA</span></span>  
 <span data-ttu-id="9afd7-139">Возвращает встроенную XML-схему W3C (XSD).</span><span class="sxs-lookup"><span data-stu-id="9afd7-139">Returns an inline W3C XML Schema (XSD).</span></span> <span data-ttu-id="9afd7-140">Также при определении этой директивы можно указать целевой URI пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9afd7-140">You can optionally specify a target namespace URI when specifying this directive.</span></span> <span data-ttu-id="9afd7-141">При этом в схему возвращается указанное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="9afd7-141">This returns the specified namespace in the schema.</span></span> <span data-ttu-id="9afd7-142">Дополнительные сведения см. в разделе [Создание встроенных схем XSD](generate-an-inline-xsd-schema.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-142">For more information, see [Generate an Inline XSD Schema](generate-an-inline-xsd-schema.md).</span></span> <span data-ttu-id="9afd7-143">Работающий пример см. в статье [Использование с RAW Mode для FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-143">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9afd7-144">ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="9afd7-144">ELEMENTS</span></span>  
 <span data-ttu-id="9afd7-145">Если указан параметр ELEMENTS, столбцы возвращаются в виде вложенных элементов.</span><span class="sxs-lookup"><span data-stu-id="9afd7-145">If the ELEMENTS option is specified, the columns are returned as subelements.</span></span> <span data-ttu-id="9afd7-146">В противном случае они сопоставляются с XML-атрибутами.</span><span class="sxs-lookup"><span data-stu-id="9afd7-146">Otherwise, they are mapped to XML attributes.</span></span> <span data-ttu-id="9afd7-147">Этот параметр поддерживается только режимами RAW, AUTO и PATH.</span><span class="sxs-lookup"><span data-stu-id="9afd7-147">This option is supported in RAW, AUTO, and PATH modes only.</span></span> <span data-ttu-id="9afd7-148">Пи использовании этой директивы можно дополнительно указать ключевые слова XSINIL или ABSENT.</span><span class="sxs-lookup"><span data-stu-id="9afd7-148">You can optionally specify XSINIL or ABSENT when you use this directive.</span></span> <span data-ttu-id="9afd7-149">Ключевое слово XSINIL указывает на то, что элемент имеет атрибут **xsi:nil** , установленный в значение True для столбцов со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="9afd7-149">XSINIL specifies that an element that has an **xsi:nil** attribute set to True be created for NULL column values.</span></span> <span data-ttu-id="9afd7-150">По умолчанию или при указании вместе с параметром ELEMENTS ключевого слова ABSENT, для значений NULL столбцы не создаются.</span><span class="sxs-lookup"><span data-stu-id="9afd7-150">By default or when ABSENT is specified together with ELEMENTS, no elements are created for NULL values.</span></span> <span data-ttu-id="9afd7-151">Работающий пример см. в статьях [Использование с RAW Mode для FOR XML](use-raw-mode-with-for-xml.md) и [Использование режима AUTO совместно с FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-151">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) and [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9afd7-152">BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="9afd7-152">BINARY BASE64</span></span>  
 <span data-ttu-id="9afd7-153">Если указан параметр BINARY Base64, любые двоичные данные, возвращенные запросом, будут представлены в формате base64.</span><span class="sxs-lookup"><span data-stu-id="9afd7-153">If the BINARY Base64 option is specified, any binary data returned by the query is represented in base64-encoded format.</span></span> <span data-ttu-id="9afd7-154">Чтобы получить двоичные данные при помощи режимов RAW и EXPLICIT, необходимо указать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="9afd7-154">To retrieve binary data by using RAW and EXPLICIT mode, this option must be specified.</span></span> <span data-ttu-id="9afd7-155">В режиме AUTO двоичные данные возвращаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9afd7-155">In AUTO mode, binary data is returned as a reference by default.</span></span> <span data-ttu-id="9afd7-156">Работающий пример см. в статье [Использование с RAW Mode для FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-156">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9afd7-157">TYPE</span><span class="sxs-lookup"><span data-stu-id="9afd7-157">TYPE</span></span>  
 <span data-ttu-id="9afd7-158">Указывает на то, что запрос возвращает результаты в виде типа **xml** .</span><span class="sxs-lookup"><span data-stu-id="9afd7-158">Specifies that the query returns the results as the **xml** type.</span></span> <span data-ttu-id="9afd7-159">Дополнительные сведения см. в статье [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9afd7-159">For more information, see [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="9afd7-160">ROOT [('*имя_корневого_элемента*')]</span><span class="sxs-lookup"><span data-stu-id="9afd7-160">ROOT [('*RootName*')]</span></span>  
 <span data-ttu-id="9afd7-161">Указывает, что к результирующему XML-документу будет добавлен один элемент верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="9afd7-161">Specifies that a single, top-level element be added to the resulting XML.</span></span> <span data-ttu-id="9afd7-162">Дополнительно можно указать имя корневого элемента, который необходимо сформировать.</span><span class="sxs-lookup"><span data-stu-id="9afd7-162">You can optionally specify the root element name to generate.</span></span> <span data-ttu-id="9afd7-163">Значение по умолчанию — «root».</span><span class="sxs-lookup"><span data-stu-id="9afd7-163">The default value is "root".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9afd7-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="9afd7-164">See Also</span></span>  
 <span data-ttu-id="9afd7-165">[Использование с RAW Mode для FOR XML](use-raw-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9afd7-165">[Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="9afd7-166">[Использование режима AUTO совместно с FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9afd7-166">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="9afd7-167">[Использование режима EXPLICIT совместно с предложением FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9afd7-167">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="9afd7-168">[Использование режима PATH совместно с FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9afd7-168">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="9afd7-169">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9afd7-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="9afd7-170">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9afd7-170">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
