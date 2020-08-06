---
title: Синтаксис пути к элементу для XML-данных отчета (SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ElementPath syntax
- XML [Reporting Services], data retrieval
ms.assetid: 07bd7a4e-fd7a-4a72-9344-3258f7c286d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b7d66b39761dc278abff25a3b22ccd18ca74272b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751779"
---
# <a name="element-path-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="e6bf0-102">Синтаксис пути к элементу для XML-данных отчета (SSRS)</span><span class="sxs-lookup"><span data-stu-id="e6bf0-102">Element Path Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="e6bf0-103">В конструкторе отчетов для определения данных из источника данных XML, которые должны использоваться в отчете, указывается путь к элементу с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-103">In Report Designer, you specify the data to use for a report from an XML data source by defining a case-sensitive element path.</span></span> <span data-ttu-id="e6bf0-104">Путь к элементу — это путь по иерархическим XML-узлам в источнике XML-данных и атрибуты этих узлов.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-104">An element path indicates how to traverse the XML hierarchical nodes and their attributes in the XML data source.</span></span> <span data-ttu-id="e6bf0-105">Чтобы использовать путь к элементу по умолчанию, оставьте пустым запрос набора данных или XML `ElementPath` для XML-`Query`.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-105">To use the default element path, leave the dataset query or the XML `ElementPath` of the XML `Query` empty.</span></span> <span data-ttu-id="e6bf0-106">При получении данных из источника XML-данных узлы элементов, которые имеют текстовые значения и атрибуты узла элемента, преобразуются в столбцы результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-106">When data is retrieved from the XML data source, element nodes that have text values and element node attributes become columns in the result set.</span></span> <span data-ttu-id="e6bf0-107">При выполнении запроса значения этих узлов и атрибуты преобразуются в данные строк.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-107">The values of the nodes and attributes become the row data when you run the query.</span></span> <span data-ttu-id="e6bf0-108">Эти столбцы появляются в качестве коллекции полей набора данных в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-108">The columns appear as the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="e6bf0-109">В этом разделе содержится информация о синтаксисе пути к элементу.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-109">This topic describes the element path syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6bf0-110">Синтаксис пути к элементу не зависит от пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-110">Element path syntax is namespace-independent.</span></span> <span data-ttu-id="e6bf0-111">Чтобы использовать пространства имен в пути к элементу, используйте синтаксис XML-запроса, включающий XML- `ElementPath` элемент, описанный в разделе [синтаксис запроса XML для XML-данных отчета &#40;&#41;SSRS ](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e6bf0-111">To use namespaces in an element path, use the XML query syntax that includes an XML `ElementPath` element described in [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="e6bf0-112">В следующей таблице указаны обозначения, используемые для определения пути к элементу.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-112">The following table describes conventions used to define an element path.</span></span>  
  
|<span data-ttu-id="e6bf0-113">Обозначение</span><span class="sxs-lookup"><span data-stu-id="e6bf0-113">Convention</span></span>|<span data-ttu-id="e6bf0-114">Используется для</span><span class="sxs-lookup"><span data-stu-id="e6bf0-114">Used for</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6bf0-115">**полужирный**</span><span class="sxs-lookup"><span data-stu-id="e6bf0-115">**bold**</span></span>|<span data-ttu-id="e6bf0-116">Текст, который должен вводиться точно так, как показано.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-116">Text that must be typed exactly as shown.</span></span>|  
|<span data-ttu-id="e6bf0-117">&#124; (вертикальная линия)</span><span class="sxs-lookup"><span data-stu-id="e6bf0-117">&#124; (vertical bar)</span></span>|<span data-ttu-id="e6bf0-118">Разделяет элементы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-118">Separates syntax items.</span></span> <span data-ttu-id="e6bf0-119">Можно выбрать только один из элементов.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-119">You can choose only one of the items.</span></span>|  
|`[ ] (brackets)`|<span data-ttu-id="e6bf0-120">Необязательные элементы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-120">Optional syntax items.</span></span> <span data-ttu-id="e6bf0-121">Скобки не вводятся.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-121">Do not type the brackets.</span></span>|  
|<span data-ttu-id="e6bf0-122">**{}** (фигурные скобки)</span><span class="sxs-lookup"><span data-stu-id="e6bf0-122">**{ }** (braces)</span></span>|<span data-ttu-id="e6bf0-123">Разделяют параметры элементов синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-123">Delimits parameters of syntax items.</span></span>|  
|<span data-ttu-id="e6bf0-124">[ **,** ...*n*]</span><span class="sxs-lookup"><span data-stu-id="e6bf0-124">[**,**...*n*]</span></span>|<span data-ttu-id="e6bf0-125">Указывает на то, что предшествующий элемент можно повторить *n* раз.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-125">Indicates the preceding item can be repeated *n* number of times.</span></span> <span data-ttu-id="e6bf0-126">Отдельные вхождения элемента разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-126">The occurrences are separated by commas.</span></span>|  
  
## <a name="syntax"></a><span data-ttu-id="e6bf0-127">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6bf0-127">Syntax</span></span>  
  
```  
  
Element path ::=  
    ElementNode[/Element path]  
ElementNode ::=  
    XMLName[(Encoding)][{[FieldList]}]  
XMLName ::=  
    [NamespacePrefix:]XMLLocalName  
Encoding ::=  
        HTMLEncoded | Base64Encoded  
FieldList ::=  
    Field[,FieldList]  
Field ::=  
    Attribute | Value | Element | ElementNode  
Attribute ::=  
        @XMLName[(Type)]  
Value ::=  
        @[(Type)]  
Element ::=  
    XMLName[(Type)]  
Type ::=  
        String | Integer | Boolean | Float | Decimal | Date | XML   
NamespacePrefix ::=  
    Identifier that specifies the namespace.  
XMLLocalName :: =  
    Identifier in the XML tag.   
```  
  
## <a name="remarks"></a><span data-ttu-id="e6bf0-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6bf0-128">Remarks</span></span>  
 <span data-ttu-id="e6bf0-129">В следующей таблице указаны термины пути к элементу.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-129">The following table summarizes element path terms.</span></span> <span data-ttu-id="e6bf0-130">Примеры в этой таблице ссылаются на учебный XML-документ Customers.xml в подразделе «Примеры» этого раздела.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-130">Examples in the table refer to the example XML document Customers.xml, which is included in the Examples section of this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6bf0-131">В XML-тегах различается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-131">XML tags are case-sensitive.</span></span> <span data-ttu-id="e6bf0-132">Определение ElementNode в пути к элементу должно точно соответствовать XML-тегам в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-132">When you specify an ElementNode in the element path, you must exactly match the XML tags in the data source.</span></span>  
  
|<span data-ttu-id="e6bf0-133">Термин</span><span class="sxs-lookup"><span data-stu-id="e6bf0-133">Term</span></span>|<span data-ttu-id="e6bf0-134">Определение</span><span class="sxs-lookup"><span data-stu-id="e6bf0-134">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e6bf0-135">Путь к элементу</span><span class="sxs-lookup"><span data-stu-id="e6bf0-135">Element path</span></span>|<span data-ttu-id="e6bf0-136">Определяет последовательность узлов, которые необходимо пройти в XML-документе, чтобы получить поля данных для набора данных из источника XML-данных.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-136">Defines the sequence of nodes to traverse within the XML document in order to retrieve field data for a dataset with an XML data source.</span></span>|  
|`ElementNode`|<span data-ttu-id="e6bf0-137">XML-узел в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-137">The XML node in the XML document.</span></span> <span data-ttu-id="e6bf0-138">Узлы обозначаются тегами и находятся в иерархической связи с другими узлами.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-138">Nodes are designated by tags and exist in a hierarchical relationship with other nodes.</span></span> <span data-ttu-id="e6bf0-139">Например, \<Customers> — это корневой узел элемента.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-139">For example, \<Customers> is the root element node.</span></span> <span data-ttu-id="e6bf0-140">\<Customer>является вложенным элементом \<Customers> .</span><span class="sxs-lookup"><span data-stu-id="e6bf0-140">\<Customer> is a subelement of \<Customers>.</span></span>|  
|`XMLName`|<span data-ttu-id="e6bf0-141">Имя узла.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-141">The name of the node.</span></span> <span data-ttu-id="e6bf0-142">Например, именем узла Customers является Customers.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-142">For example, the name of the Customers node is Customers.</span></span> <span data-ttu-id="e6bf0-143">Чтобы дать каждому узлу уникальное имя, `XMLName` может иметь префикс с идентификатором пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-143">An `XMLName` can be prefixed with a namespace identifier to uniquely name every node.</span></span>|  
|`Encoding`|<span data-ttu-id="e6bf0-144">Указывает, что `Value` для этого элемента закодировано на языке XML, требует декодирования и включается как подэлемент этого элемента.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-144">Indicates that the `Value` for this element is encoded XML and needs to be decoded and included as a subelement of this element.</span></span>|  
|`FieldList`|<span data-ttu-id="e6bf0-145">Определяет набор элементов и атрибутов, используемых для получения данных.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-145">Defines the set of elements and attributes to use to retrieve data.</span></span><br /><br /> <span data-ttu-id="e6bf0-146">Если не указано иное, все атрибуты и подэлементы используются в качестве полей.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-146">If not specified, all attributes and subelements are used as fields.</span></span> <span data-ttu-id="e6bf0-147">Если указан пустой список полей ( **{}** ), поля из этого узла не используются.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-147">If the empty field list is specified (**{}**), no fields from this node are used.</span></span><br /><br /> <span data-ttu-id="e6bf0-148">`FieldList` не может одновременно содержать `Value` и `Element` или `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-148">A `FieldList` may not contain both a `Value` and an `Element` or `ElementNode`.</span></span>|  
|`Field`|<span data-ttu-id="e6bf0-149">Определяет данные, извлекаемые как поле набора данных.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-149">Specifies the data that is retrieved as a dataset field.</span></span>|  
|`Attribute`|<span data-ttu-id="e6bf0-150">Пара «имя-значение» в `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-150">A name-value pair within the `ElementNode`.</span></span> <span data-ttu-id="e6bf0-151">Например, в узле element \<Customer ID="1"> `ID` является атрибутом и `@ID(Integer)` возвращает "1" как целочисленный тип в соответствующем поле данных `ID` .</span><span class="sxs-lookup"><span data-stu-id="e6bf0-151">For example, in the element node \<Customer ID="1">, `ID` is an attribute and `@ID(Integer)` returns "1" as an integer type in the corresponding data field `ID`.</span></span>|  
|`Value`|<span data-ttu-id="e6bf0-152">Значение элемента.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-152">The value of the element.</span></span> <span data-ttu-id="e6bf0-153">`Value` может использоваться для последнего `ElementNode` в пути к элементу.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-153">`Value` can only be used on the last `ElementNode` in the element path.</span></span> <span data-ttu-id="e6bf0-154">Например, поскольку \<Return> является конечным узлом, если включить его в конец пути к элементу, значение `Return {@}` равно `Chair` .</span><span class="sxs-lookup"><span data-stu-id="e6bf0-154">For example, because \<Return> is a leaf node, if you include it at the end of an element path, the value of `Return {@}` is `Chair`.</span></span>|  
|`Element`|<span data-ttu-id="e6bf0-155">Значение именованного подэлемента.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-155">The value of the named subelement.</span></span> <span data-ttu-id="e6bf0-156">Например, Customers {}/Customer {}/LastName извлекает значения только для элемента LastName.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-156">For example, Customers {}/Customer {}/LastName retrieves values for only the LastName element.</span></span>|  
|`Type`|<span data-ttu-id="e6bf0-157">Необязательный тип данных, который должен использоваться для поля, созданного из этого элемента.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-157">The optional data type to use for the field created from this element.</span></span>|  
|`NamespacePrefix`|<span data-ttu-id="e6bf0-158">`NamespacePrefix` определяется в элементе XML-запроса.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-158">`NamespacePrefix` is defined in the XML Query element.</span></span> <span data-ttu-id="e6bf0-159">Если элемента XML-запроса не существует, пространства имен в XML `ElementPath` не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-159">If no XML Query element exists, namespaces in the XML `ElementPath` are ignored.</span></span> <span data-ttu-id="e6bf0-160">Если элемент XML-запроса существует, XML `ElementPath` имеет необязательный атрибут `IgnoreNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-160">If there is an XML Query element, the XML `ElementPath` has an optional attribute `IgnoreNamespaces`.</span></span> <span data-ttu-id="e6bf0-161">Если IgnoreNamespaces имеет значение `true` , то пространства имен XML `ElementPath` и XML-документа игнорируются.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-161">If IgnoreNamespaces is `true`, namespaces in the XML `ElementPath` and the XML document are ignored.</span></span> <span data-ttu-id="e6bf0-162">Дополнительные сведения см. в разделе [Синтаксис запроса XML для XML-данных отчета &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e6bf0-162">For more information, see [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>|  
  
## <a name="example---no-namespaces"></a><span data-ttu-id="e6bf0-163">Пример (без пространств имен)</span><span class="sxs-lookup"><span data-stu-id="e6bf0-163">Example - No Namespaces</span></span>  
 <span data-ttu-id="e6bf0-164">В следующих примерах используется XML-документ Customers.XML.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-164">The following examples use the XML document Customers.xml.</span></span> <span data-ttu-id="e6bf0-165">Эта таблица содержит примеры синтаксиса пути к элементу и результаты использования пути в запросе. Источником данных является XML-документ.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-165">This table shows examples of element path syntax and the results of using the element path in a query that defines a dataset, based on the XML document as a data source.</span></span>  
  
 <span data-ttu-id="e6bf0-166">Обратите внимание, что если путь к элементу пуст, запрос использует путь к элементу по умолчанию: первый путь к коллекции конечных узлов.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-166">Note that when the element path is empty, the query uses the default element path: the first path to a leaf node collection.</span></span> <span data-ttu-id="e6bf0-167">В первом примере пустой путь к элементу эквивалентен указанию пути /Customers/Customer/Orders/Order.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-167">In the first example, leaving the element path empty is equivalent to specifying the element path /Customers/Customer/Orders/Order.</span></span> <span data-ttu-id="e6bf0-168">Все значения узлов и атрибуты на этом пути возвращаются в результирующем наборе, а имена узлов и имена атрибутов представляются в качестве полей набора данных.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-168">All node value and attributes along the path are returned in the result set, and the node names and attributes names appear as dataset fields.</span></span>  
  
-   <span data-ttu-id="e6bf0-169">*Пусто*</span><span class="sxs-lookup"><span data-stu-id="e6bf0-169">*Empty*</span></span>  
  
    |<span data-ttu-id="e6bf0-170">Порядок</span><span class="sxs-lookup"><span data-stu-id="e6bf0-170">Order</span></span>|<span data-ttu-id="e6bf0-171">Количество</span><span class="sxs-lookup"><span data-stu-id="e6bf0-171">Qty</span></span>|<span data-ttu-id="e6bf0-172">ID</span><span class="sxs-lookup"><span data-stu-id="e6bf0-172">ID</span></span>|<span data-ttu-id="e6bf0-173">FirstName</span><span class="sxs-lookup"><span data-stu-id="e6bf0-173">FirstName</span></span>|<span data-ttu-id="e6bf0-174">LastName</span><span class="sxs-lookup"><span data-stu-id="e6bf0-174">LastName</span></span>|<span data-ttu-id="e6bf0-175">Customer.ID</span><span class="sxs-lookup"><span data-stu-id="e6bf0-175">Customer.ID</span></span>|<span data-ttu-id="e6bf0-176">xmlns</span><span class="sxs-lookup"><span data-stu-id="e6bf0-176">xmlns</span></span>|  
    |-----------|---------|--------|---------------|--------------|-----------------|-----------|  
    |<span data-ttu-id="e6bf0-177">Chair</span><span class="sxs-lookup"><span data-stu-id="e6bf0-177">Chair</span></span>|<span data-ttu-id="e6bf0-178">6</span><span class="sxs-lookup"><span data-stu-id="e6bf0-178">6</span></span>|<span data-ttu-id="e6bf0-179">1</span><span class="sxs-lookup"><span data-stu-id="e6bf0-179">1</span></span>|<span data-ttu-id="e6bf0-180">Bobby</span><span class="sxs-lookup"><span data-stu-id="e6bf0-180">Bobby</span></span>|<span data-ttu-id="e6bf0-181">Moore</span><span class="sxs-lookup"><span data-stu-id="e6bf0-181">Moore</span></span>|<span data-ttu-id="e6bf0-182">11</span><span class="sxs-lookup"><span data-stu-id="e6bf0-182">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="e6bf0-183">Таблица</span><span class="sxs-lookup"><span data-stu-id="e6bf0-183">Table</span></span>|<span data-ttu-id="e6bf0-184">1</span><span class="sxs-lookup"><span data-stu-id="e6bf0-184">1</span></span>|<span data-ttu-id="e6bf0-185">2</span><span class="sxs-lookup"><span data-stu-id="e6bf0-185">2</span></span>|<span data-ttu-id="e6bf0-186">Bobby</span><span class="sxs-lookup"><span data-stu-id="e6bf0-186">Bobby</span></span>|<span data-ttu-id="e6bf0-187">Moore</span><span class="sxs-lookup"><span data-stu-id="e6bf0-187">Moore</span></span>|<span data-ttu-id="e6bf0-188">11</span><span class="sxs-lookup"><span data-stu-id="e6bf0-188">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="e6bf0-189">Sofa</span><span class="sxs-lookup"><span data-stu-id="e6bf0-189">Sofa</span></span>|<span data-ttu-id="e6bf0-190">2</span><span class="sxs-lookup"><span data-stu-id="e6bf0-190">2</span></span>|<span data-ttu-id="e6bf0-191">8</span><span class="sxs-lookup"><span data-stu-id="e6bf0-191">8</span></span>|<span data-ttu-id="e6bf0-192">Crystal</span><span class="sxs-lookup"><span data-stu-id="e6bf0-192">Crystal</span></span>|<span data-ttu-id="e6bf0-193">Hu</span><span class="sxs-lookup"><span data-stu-id="e6bf0-193">Hu</span></span>|<span data-ttu-id="e6bf0-194">20</span><span class="sxs-lookup"><span data-stu-id="e6bf0-194">20</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="e6bf0-195">EndTables</span><span class="sxs-lookup"><span data-stu-id="e6bf0-195">EndTables</span></span>|<span data-ttu-id="e6bf0-196">2</span><span class="sxs-lookup"><span data-stu-id="e6bf0-196">2</span></span>|<span data-ttu-id="e6bf0-197">15</span><span class="sxs-lookup"><span data-stu-id="e6bf0-197">15</span></span>|<span data-ttu-id="e6bf0-198">Wyatt</span><span class="sxs-lookup"><span data-stu-id="e6bf0-198">Wyatt</span></span>|<span data-ttu-id="e6bf0-199">Diaz</span><span class="sxs-lookup"><span data-stu-id="e6bf0-199">Diaz</span></span>|<span data-ttu-id="e6bf0-200">33</span><span class="sxs-lookup"><span data-stu-id="e6bf0-200">33</span></span>|http://www.adventure-works.com|  
  
-   `Customers {}/Customer`  
  
    |<span data-ttu-id="e6bf0-201">FirstName</span><span class="sxs-lookup"><span data-stu-id="e6bf0-201">FirstName</span></span>|<span data-ttu-id="e6bf0-202">LastName</span><span class="sxs-lookup"><span data-stu-id="e6bf0-202">LastName</span></span>|<span data-ttu-id="e6bf0-203">ID</span><span class="sxs-lookup"><span data-stu-id="e6bf0-203">ID</span></span>|  
    |---------------|--------------|--------|  
    |<span data-ttu-id="e6bf0-204">Bobby</span><span class="sxs-lookup"><span data-stu-id="e6bf0-204">Bobby</span></span>|<span data-ttu-id="e6bf0-205">Moore</span><span class="sxs-lookup"><span data-stu-id="e6bf0-205">Moore</span></span>|<span data-ttu-id="e6bf0-206">11</span><span class="sxs-lookup"><span data-stu-id="e6bf0-206">11</span></span>|  
    |<span data-ttu-id="e6bf0-207">Crystal</span><span class="sxs-lookup"><span data-stu-id="e6bf0-207">Crystal</span></span>|<span data-ttu-id="e6bf0-208">Hu</span><span class="sxs-lookup"><span data-stu-id="e6bf0-208">Hu</span></span>|<span data-ttu-id="e6bf0-209">20</span><span class="sxs-lookup"><span data-stu-id="e6bf0-209">20</span></span>|  
    |<span data-ttu-id="e6bf0-210">Wyatt</span><span class="sxs-lookup"><span data-stu-id="e6bf0-210">Wyatt</span></span>|<span data-ttu-id="e6bf0-211">Diaz</span><span class="sxs-lookup"><span data-stu-id="e6bf0-211">Diaz</span></span>|<span data-ttu-id="e6bf0-212">33</span><span class="sxs-lookup"><span data-stu-id="e6bf0-212">33</span></span>|  
  
-   `Customers {}/Customer {}/LastName`  
  
    |<span data-ttu-id="e6bf0-213">LastName</span><span class="sxs-lookup"><span data-stu-id="e6bf0-213">LastName</span></span>|  
    |--------------|  
    |<span data-ttu-id="e6bf0-214">Moore</span><span class="sxs-lookup"><span data-stu-id="e6bf0-214">Moore</span></span>|  
    |<span data-ttu-id="e6bf0-215">Hu</span><span class="sxs-lookup"><span data-stu-id="e6bf0-215">Hu</span></span>|  
    |<span data-ttu-id="e6bf0-216">Diaz</span><span class="sxs-lookup"><span data-stu-id="e6bf0-216">Diaz</span></span>|  
  
-   `Customers {}/Customer {}/Orders/Order {@,@Qty}`  
  
    |<span data-ttu-id="e6bf0-217">Порядок</span><span class="sxs-lookup"><span data-stu-id="e6bf0-217">Order</span></span>|<span data-ttu-id="e6bf0-218">Количество</span><span class="sxs-lookup"><span data-stu-id="e6bf0-218">Qty</span></span>|  
    |-----------|---------|  
    |<span data-ttu-id="e6bf0-219">Chair</span><span class="sxs-lookup"><span data-stu-id="e6bf0-219">Chair</span></span>|<span data-ttu-id="e6bf0-220">6</span><span class="sxs-lookup"><span data-stu-id="e6bf0-220">6</span></span>|  
    |<span data-ttu-id="e6bf0-221">Таблица</span><span class="sxs-lookup"><span data-stu-id="e6bf0-221">Table</span></span>|<span data-ttu-id="e6bf0-222">1</span><span class="sxs-lookup"><span data-stu-id="e6bf0-222">1</span></span>|  
    |<span data-ttu-id="e6bf0-223">Sofa</span><span class="sxs-lookup"><span data-stu-id="e6bf0-223">Sofa</span></span>|<span data-ttu-id="e6bf0-224">2</span><span class="sxs-lookup"><span data-stu-id="e6bf0-224">2</span></span>|  
    |<span data-ttu-id="e6bf0-225">EndTables</span><span class="sxs-lookup"><span data-stu-id="e6bf0-225">EndTables</span></span>|<span data-ttu-id="e6bf0-226">2</span><span class="sxs-lookup"><span data-stu-id="e6bf0-226">2</span></span>|  
  
-   `Customers {}/Customer/Orders/Order{ @ID(Integer)}`  
  
    |<span data-ttu-id="e6bf0-227">Order.ID</span><span class="sxs-lookup"><span data-stu-id="e6bf0-227">Order.ID</span></span>|<span data-ttu-id="e6bf0-228">FirstName</span><span class="sxs-lookup"><span data-stu-id="e6bf0-228">FirstName</span></span>|<span data-ttu-id="e6bf0-229">LastName</span><span class="sxs-lookup"><span data-stu-id="e6bf0-229">LastName</span></span>|<span data-ttu-id="e6bf0-230">ID</span><span class="sxs-lookup"><span data-stu-id="e6bf0-230">ID</span></span>|  
    |--------------|---------------|--------------|--------|  
    |<span data-ttu-id="e6bf0-231">1</span><span class="sxs-lookup"><span data-stu-id="e6bf0-231">1</span></span>|<span data-ttu-id="e6bf0-232">Bobby</span><span class="sxs-lookup"><span data-stu-id="e6bf0-232">Bobby</span></span>|<span data-ttu-id="e6bf0-233">Moore</span><span class="sxs-lookup"><span data-stu-id="e6bf0-233">Moore</span></span>|<span data-ttu-id="e6bf0-234">11</span><span class="sxs-lookup"><span data-stu-id="e6bf0-234">11</span></span>|  
    |<span data-ttu-id="e6bf0-235">2</span><span class="sxs-lookup"><span data-stu-id="e6bf0-235">2</span></span>|<span data-ttu-id="e6bf0-236">Bobby</span><span class="sxs-lookup"><span data-stu-id="e6bf0-236">Bobby</span></span>|<span data-ttu-id="e6bf0-237">Moore</span><span class="sxs-lookup"><span data-stu-id="e6bf0-237">Moore</span></span>|<span data-ttu-id="e6bf0-238">11</span><span class="sxs-lookup"><span data-stu-id="e6bf0-238">11</span></span>|  
    |<span data-ttu-id="e6bf0-239">8</span><span class="sxs-lookup"><span data-stu-id="e6bf0-239">8</span></span>|<span data-ttu-id="e6bf0-240">Crystal</span><span class="sxs-lookup"><span data-stu-id="e6bf0-240">Crystal</span></span>|<span data-ttu-id="e6bf0-241">Hu</span><span class="sxs-lookup"><span data-stu-id="e6bf0-241">Hu</span></span>|<span data-ttu-id="e6bf0-242">20</span><span class="sxs-lookup"><span data-stu-id="e6bf0-242">20</span></span>|  
    |<span data-ttu-id="e6bf0-243">15</span><span class="sxs-lookup"><span data-stu-id="e6bf0-243">15</span></span>|<span data-ttu-id="e6bf0-244">Wyatt</span><span class="sxs-lookup"><span data-stu-id="e6bf0-244">Wyatt</span></span>|<span data-ttu-id="e6bf0-245">Diaz</span><span class="sxs-lookup"><span data-stu-id="e6bf0-245">Diaz</span></span>|<span data-ttu-id="e6bf0-246">33</span><span class="sxs-lookup"><span data-stu-id="e6bf0-246">33</span></span>|  
  
#### <a name="xml-document-customersxml"></a><span data-ttu-id="e6bf0-247">XML-документ: Customers.xml</span><span class="sxs-lookup"><span data-stu-id="e6bf0-247">XML document: Customers.xml</span></span>  
 <span data-ttu-id="e6bf0-248">Чтобы проверить примеры пути к элементу из предыдущего раздела, можно скопировать этот XML-документ и сохранить его в URL-адресе, доступном из конструктора отчетов, а затем использовать этот XML-документ в качестве источника XML-данных, например `http://localhost/Customers.xml`.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-248">To try out the element path examples in the previous section, you can copy this XML and save it to a URL that is accessible by Report Designer, and then use the XML document as an XML data source: for example, `http://localhost/Customers.xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<Customers xmlns="http://www.adventure-works.com">  
   <Customer ID="11">  
      <FirstName>Bobby</FirstName>  
      <LastName>Moore</LastName>  
      <Orders>  
         <Order ID="1" Qty="6">Chair</Order>  
         <Order ID="2" Qty="1">Table</Order>  
      </Orders>  
      <Returns>  
         <Return ID="1" Qty="2">Chair</Return>  
      </Returns>  
   </Customer>  
   <Customer ID="20">  
      <FirstName>Crystal</FirstName>  
      <LastName>Hu</LastName>  
      <Orders>  
         <Order ID="8" Qty="2">Sofa</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
   <Customer ID="33">  
      <FirstName>Wyatt</FirstName>  
      <LastName>Diaz</LastName>  
      <Orders>  
         <Order ID="15" Qty="2">EndTables</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
</Customers>  
```  
  
 <span data-ttu-id="e6bf0-249">В качестве альтернативы можно создать источник XML-данных без строки соединения и внедрить документ Customers.XML в запрос с помощью следующей процедуры:</span><span class="sxs-lookup"><span data-stu-id="e6bf0-249">Alternatively, you can create an XML data source that has no connection string and embed Customers.XML in the query, using the following procedure:</span></span>  
  
###### <a name="to-embed-customersxml-in-a-query"></a><span data-ttu-id="e6bf0-250">Внедрение документа Customers.XML в запрос</span><span class="sxs-lookup"><span data-stu-id="e6bf0-250">To embed Customers.XML in a query</span></span>  
  
1.  <span data-ttu-id="e6bf0-251">Создайте источник XML-данных с пустой строкой соединения.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-251">Create an XML data source with a blank connection string.</span></span>  
  
2.  <span data-ttu-id="e6bf0-252">Создайте новый набор данных для источника XML-данных.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-252">Create a new dataset for the XML data source.</span></span>  
  
3.  <span data-ttu-id="e6bf0-253">В диалоговом окне **Свойства набора данных** нажмите кнопку **Конструктор запросов**.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-253">In the **Dataset Properties** dialog box, click **Query Designer**.</span></span> <span data-ttu-id="e6bf0-254">Откроется текстовое диалоговое окно конструктора запросов.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-254">The text-based query designer dialog box opens.</span></span>  
  
4.  <span data-ttu-id="e6bf0-255">На панели запросов введите следующие две строки:</span><span class="sxs-lookup"><span data-stu-id="e6bf0-255">In the query pane, enter the following two lines:</span></span>  
  
     `<Query>`  
  
     `<XmlData>`  
  
5.  <span data-ttu-id="e6bf0-256">Скопируйте содержимое документа Customers.XML и вставьте его на панель запроса после `<XmlData>`.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-256">Copy Customers.XML and paste the text in the query pane after `<XmlData>`.</span></span>  
  
6.  <span data-ttu-id="e6bf0-257">На панели запроса удалите первую строку, скопированную из документа Customers.XML: `<?xml version="1.0"?>`</span><span class="sxs-lookup"><span data-stu-id="e6bf0-257">In the query pane, delete the first line that you copied from Customers.XML: `<?xml version="1.0"?>`</span></span>  
  
7.  <span data-ttu-id="e6bf0-258">В конце запроса добавьте две следующие строки:</span><span class="sxs-lookup"><span data-stu-id="e6bf0-258">At the end of the query, add the following two lines:</span></span>  
  
     `<XmlData>`  
  
     `<Query>`  
  
8.  <span data-ttu-id="e6bf0-259">Нажмите кнопку **Выполнить запрос** (!).</span><span class="sxs-lookup"><span data-stu-id="e6bf0-259">Click **Run Query** (!).</span></span>  
  
     <span data-ttu-id="e6bf0-260">Результирующий набор отображает 4 строки данных со следующими столбцами: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span><span class="sxs-lookup"><span data-stu-id="e6bf0-260">The result set displays 4 lines of data with the following columns: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6bf0-261">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6bf0-261">See Also</span></span>  
 <span data-ttu-id="e6bf0-262">[Тип подключения XML &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6bf0-262">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 <span data-ttu-id="e6bf0-263">[Reporting Services учебники &#40;службы SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6bf0-263">[Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span></span>  
 [<span data-ttu-id="e6bf0-264">Добавление, изменение и обновление полей в области данных отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="e6bf0-264">Add, Edit, Refresh Fields in the Report Data Pane &#40;Report Builder and SSRS&#41;</span></span>](add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md)  
  
  
