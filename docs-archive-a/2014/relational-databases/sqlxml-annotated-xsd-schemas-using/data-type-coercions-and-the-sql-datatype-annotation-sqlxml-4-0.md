---
title: 'Приведение типов данных и аннотация SQL: DataType (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping data types [SQLXML]
- type attribute
- sql:datatype
- data types [SQLXML], converting
- annotated XSD schemas, mapping data types
- xsd:type
- datatype annotation
- converting data types [SQLXML]
- data types [SQLXML], mapping data types
- XSD schemas [SQLXML], mapping data types
ms.assetid: db192105-e8aa-4392-b812-9d727918c005
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f1b0af93e3b596d74bc107ab6947b9855a2cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664122"
---
# <a name="data-type-coercions-and-the-sqldatatype-annotation-sqlxml-40"></a><span data-ttu-id="82829-102">Приведение типов данных и заметка sql:datatype (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="82829-102">Data Type Coercions and the sql:datatype Annotation (SQLXML 4.0)</span></span>
  <span data-ttu-id="82829-103">В схеме XSD атрибут `xsd:type` указывает тип XSD-данных элемента или атрибута.</span><span class="sxs-lookup"><span data-stu-id="82829-103">In an XSD schema, the `xsd:type` attribute specifies the XSD data type of an element or attribute.</span></span> <span data-ttu-id="82829-104">Если схема XSD используется для получения данных из базы данных, указанный тип данных используется для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="82829-104">When an XSD schema is used to extract data from the database, the data type specified is used to format the data.</span></span>  
  
 <span data-ttu-id="82829-105">Кроме указания XSD-типа в схеме, можно также указать тип данных Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью заметки `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="82829-105">In addition to specifying an XSD type in a schema, you can also specify a Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type by using the `sql:datatype` annotation.</span></span> <span data-ttu-id="82829-106">Атрибуты `xsd:type` и `sql:datatype` управляют сопоставлением между типами данных XSD и типами данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82829-106">The `xsd:type` and `sql:datatype` attributes control the mapping between XSD data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
## <a name="xsdtype-attribute"></a><span data-ttu-id="82829-107">Атрибут xsd:type</span><span class="sxs-lookup"><span data-stu-id="82829-107">xsd:type Attribute</span></span>  
 <span data-ttu-id="82829-108">Атрибут `xsd:type` позволяет задать тип данных XML атрибута или элемента, сопоставляемого со столбцом.</span><span class="sxs-lookup"><span data-stu-id="82829-108">You can use the `xsd:type` attribute to specify the XML data type of an attribute or element that maps to a column.</span></span> <span data-ttu-id="82829-109">Атрибут `xsd:type` влияет на документ, возвращаемый сервером, а также на выполняемый запрос XPath.</span><span class="sxs-lookup"><span data-stu-id="82829-109">The `xsd:type` affects the document that is returned from the server and also the XPath query that is executed.</span></span> <span data-ttu-id="82829-110">При выполнении запроса XPath к схеме сопоставления, которая содержит атрибут `xsd:type`, XPath использует указанный тип данных при обработке запроса.</span><span class="sxs-lookup"><span data-stu-id="82829-110">When an XPath query is executed against a mapping schema that contains `xsd:type`, XPath uses the specified data type when it processes the query.</span></span> <span data-ttu-id="82829-111">Дополнительные сведения об использовании XPath `xsd:type` см. в разделе [Сопоставление типов данных XSD с типами данных XPath &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="82829-111">For more information about how XPath uses `xsd:type`, see [Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="82829-112">В возвращенном документе все типы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] преобразуются в строковые представления.</span><span class="sxs-lookup"><span data-stu-id="82829-112">In a returned document, all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types are converted into string representations.</span></span> <span data-ttu-id="82829-113">Для некоторых типов данных необходимо дополнительное преобразование.</span><span class="sxs-lookup"><span data-stu-id="82829-113">Some data types require additional conversions.</span></span> <span data-ttu-id="82829-114">В следующей таблице перечислены виды преобразования, которые применяются для различных значений `xsd:type`.</span><span class="sxs-lookup"><span data-stu-id="82829-114">The following table lists the conversions that are used for various `xsd:type` values.</span></span>  
  
|<span data-ttu-id="82829-115">Тип данных XSD</span><span class="sxs-lookup"><span data-stu-id="82829-115">XSD data type</span></span>|<span data-ttu-id="82829-116">Преобразование SQL Server</span><span class="sxs-lookup"><span data-stu-id="82829-116">SQL Server conversion</span></span>|  
|-------------------|---------------------------|  
|<span data-ttu-id="82829-117">Логическое</span><span class="sxs-lookup"><span data-stu-id="82829-117">Boolean</span></span>|<span data-ttu-id="82829-118">CONVERT(bit, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="82829-118">CONVERT(bit, COLUMN)</span></span>|  
|<span data-ttu-id="82829-119">Дата</span><span class="sxs-lookup"><span data-stu-id="82829-119">Date</span></span>|<span data-ttu-id="82829-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span><span class="sxs-lookup"><span data-stu-id="82829-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span></span>|  
|<span data-ttu-id="82829-121">Decimal</span><span class="sxs-lookup"><span data-stu-id="82829-121">decimal</span></span>|<span data-ttu-id="82829-122">CONVERT(money, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="82829-122">CONVERT(money, COLUMN)</span></span>|  
|<span data-ttu-id="82829-123">id/idref/idrefs</span><span class="sxs-lookup"><span data-stu-id="82829-123">id/idref/idrefs</span></span>|<span data-ttu-id="82829-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="82829-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="82829-125">nmtoken/nmtokens</span><span class="sxs-lookup"><span data-stu-id="82829-125">nmtoken/nmtokens</span></span>|<span data-ttu-id="82829-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="82829-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="82829-127">Time</span><span class="sxs-lookup"><span data-stu-id="82829-127">Time</span></span>|<span data-ttu-id="82829-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span><span class="sxs-lookup"><span data-stu-id="82829-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span></span>|  
|<span data-ttu-id="82829-129">Все остальные</span><span class="sxs-lookup"><span data-stu-id="82829-129">All others</span></span>|<span data-ttu-id="82829-130">Дополнительное преобразование не выполняется</span><span class="sxs-lookup"><span data-stu-id="82829-130">No additional conversion</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="82829-131">Некоторые значения, возвращаемые [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], могут быть несовместимыми с типами данных XML, указанными с помощью атрибута `xsd:type`, из-за невозможности преобразования (например, преобразование «XYZ» в тип данных `decimal`) или из-за превышения диапазона этого типа данных (например, преобразование -100000 в XSD-тип `UnsignedShort`).</span><span class="sxs-lookup"><span data-stu-id="82829-131">Some of the values returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might not be compatible with the XML data types that are specified by using `xsd:type`, either because the conversion is not possible (for example, converting "XYZ" to a `decimal` data type) or because the value exceeds the range of that data type (for example, -100000 converted to an `UnsignedShort` XSD type).</span></span> <span data-ttu-id="82829-132">Преобразования несовместимых типов может привести к недопустимым XML-документам или ошибкам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82829-132">Incompatible type conversions might result in XML documents that are not valid, or in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] errors.</span></span>  
  
## <a name="mapping-from-sql-server-data-types-to-xsd-data-types"></a><span data-ttu-id="82829-133">Сопоставление типов данных SQL Server с типами данных XSD</span><span class="sxs-lookup"><span data-stu-id="82829-133">Mapping from SQL Server Data Types to XSD Data Types</span></span>  
 <span data-ttu-id="82829-134">Следующая таблица показывает очевидные сопоставления типов данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типам данных XSD.</span><span class="sxs-lookup"><span data-stu-id="82829-134">The following table shows an obvious mapping from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types to XSD data types.</span></span> <span data-ttu-id="82829-135">Если известен тип [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], в данной таблице показан соответствующий XSD-тип, который можно указать в схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="82829-135">If you know the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type, this table provides the corresponding XSD type that you can specify in the XSD schema.</span></span>  
  
|<span data-ttu-id="82829-136">Тип данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="82829-136">SQL Server data type</span></span>|<span data-ttu-id="82829-137">Тип данных XSD</span><span class="sxs-lookup"><span data-stu-id="82829-137">XSD data type</span></span>|  
|--------------------------|-------------------|  
|`bigint`|`long`|  
|`binary`|`base64Binary`|  
|`bit`|`boolean`|  
|`char`|`string`|  
|`datetime`|`dateTime`|  
|`decimal`|`decimal`|  
|`float`|`double`|  
|`image`|`base64Binary`|  
|`int`|`int`|  
|`money`|`decimal`|  
|`nchar`|`string`|  
|`ntext`|`string`|  
|`nvarchar`|`string`|  
|`numeric`|`decimal`|  
|`real`|`float`|  
|`smalldatetime`|`dateTime`|  
|`smallint`|`short`|  
|`smallmoney`|`decimal`|  
|`sql_variant`|`string`|  
|`sysname`|`string`|  
|`text`|`string`|  
|`timestamp`|`dateTime`|  
|`tinyint`|`unsignedByte`|  
|`varbinary`|`base64Binary`|  
|`varchar`|`string`|  
|`uniqueidentifier`|`string`|  
  
## <a name="sqldatatype-annotation"></a><span data-ttu-id="82829-138">Заметка sql:datatype</span><span class="sxs-lookup"><span data-stu-id="82829-138">sql:datatype Annotation</span></span>  
 <span data-ttu-id="82829-139">Заметка `sql:datatype` используется, чтобы указать тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Эта заметка должна быть указана в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="82829-139">The `sql:datatype` annotation is used to specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type; this annotation must be specified when:</span></span>  
  
-   <span data-ttu-id="82829-140">Выполняется операция загрузки в `dateTime` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] столбец из XSD `dateTime` , `date` или `time` типа.</span><span class="sxs-lookup"><span data-stu-id="82829-140">You are bulk loading into a `dateTime`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column from an XSD `dateTime`, `date`, or `time` type.</span></span> <span data-ttu-id="82829-141">В этом случае необходимо определить тип данных столбца [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью заметки `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="82829-141">In this case, you must identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column data type by using `sql:datatype="dateTime"`.</span></span> <span data-ttu-id="82829-142">Это правило применяется только для диаграмм обновления.</span><span class="sxs-lookup"><span data-stu-id="82829-142">This rule also applies to updategrams.</span></span>  
  
-   <span data-ttu-id="82829-143">Выполняется массовый запуск в столбец [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` типа, а значение XSD — это идентификатор GUID, включающий фигурные скобки ({и}).</span><span class="sxs-lookup"><span data-stu-id="82829-143">You are bulk loading into a column of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` type and the XSD value is a GUID that includes braces ({ and }).</span></span> <span data-ttu-id="82829-144">Если указана заметка `sql:datatype="uniqueidentifier"`, фигурные скобки удаляются из значения прежде, чем оно вставляется в столбец.</span><span class="sxs-lookup"><span data-stu-id="82829-144">When you specify `sql:datatype="uniqueidentifier"`, the braces are removed from the value before it is inserted in the column.</span></span> <span data-ttu-id="82829-145">Если заметка `sql:datatype` не указана, значение пересылается с фигурными скобками, и вставка или обновление завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="82829-145">If `sql:datatype` is not specified, the value is sent with the braces, and the insert or update fails.</span></span>  
  
-   <span data-ttu-id="82829-146">Тип данных XML `base64Binary` сопоставляется различным типам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (`binary`, `image` или `varbinary`).</span><span class="sxs-lookup"><span data-stu-id="82829-146">The XML data type `base64Binary` maps to various [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types (`binary`, `image`, or `varbinary`).</span></span> <span data-ttu-id="82829-147">Чтобы сопоставить тип данных XML `base64Binary` различным типам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], используйте заметку `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="82829-147">To map the XML data type `base64Binary` to a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, use the `sql:datatype` annotation.</span></span> <span data-ttu-id="82829-148">Эта заметка указывает явный тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] столбца, которому сопоставляется атрибут.</span><span class="sxs-lookup"><span data-stu-id="82829-148">This annotation specifies the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the column to which the attribute maps.</span></span> <span data-ttu-id="82829-149">Это полезно, если данные сохраняются в базах данных.</span><span class="sxs-lookup"><span data-stu-id="82829-149">This is useful when data is being stored in the databases.</span></span> <span data-ttu-id="82829-150">Указав заметку `sql:datatype`, можно явным образом указать тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82829-150">By specifying the `sql:datatype` annotation, you can identify the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="82829-151">В основном рекомендуется указывать заметку `sql:datatype` в схеме.</span><span class="sxs-lookup"><span data-stu-id="82829-151">It is generally recommended that you specify `sql:datatype` in the schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="82829-152">Примеры</span><span class="sxs-lookup"><span data-stu-id="82829-152">Examples</span></span>  
 <span data-ttu-id="82829-153">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="82829-153">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="82829-154">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="82829-154">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-xsdtype"></a><span data-ttu-id="82829-155">A.</span><span class="sxs-lookup"><span data-stu-id="82829-155">A.</span></span> <span data-ttu-id="82829-156">Указание заметки xsd:type</span><span class="sxs-lookup"><span data-stu-id="82829-156">Specifying xsd:type</span></span>  
 <span data-ttu-id="82829-157">Этот пример показывает, как XSD-тип `date`, указанный с помощью атрибута `xsd:type` в схеме, влияет на результирующий XML-документ.</span><span class="sxs-lookup"><span data-stu-id="82829-157">This example shows how an XSD `date` type that is specified by using the `xsd:type` attribute in the schema affects the resulting XML document.</span></span> <span data-ttu-id="82829-158">Схема обеспечивает XML-представление таблицы Sales.SalesOrderHeader в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="82829-158">The schema provides an XML view of the Sales.SalesOrderHeader table in the AdventureWorks database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader">  
     <xsd:complexType>  
       <xsd:attribute name="SalesOrderID" type="xsd:string" />   
       <xsd:attribute name="CustomerID"   type="xsd:string" />   
       <xsd:attribute name="OrderDate"    type="xsd:date" />   
       <xsd:attribute name="DueDate"  />   
       <xsd:attribute name="ShipDate"  type="xsd:time" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="82829-159">В этой схеме XSD существует три атрибута, которые возвращают значение данных из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82829-159">In this XSD schema, there are three attributes that return a date value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="82829-160">Если схема:</span><span class="sxs-lookup"><span data-stu-id="82829-160">When the schema:</span></span>  
  
-   <span data-ttu-id="82829-161">Указывает `xsd:type=date` , что для атрибута **OrderDate** отображается часть значения даты, возвращаемая [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для атрибута **OrderDate** .</span><span class="sxs-lookup"><span data-stu-id="82829-161">Specifies `xsd:type=date` on the **OrderDate** attribute, the date part of the value returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **OrderDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="82829-162">Задает `xsd:type=time` значение для атрибута **ShipDate** , в котором отображается время, возвращаемое [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для атрибута **ShipDate** .</span><span class="sxs-lookup"><span data-stu-id="82829-162">Specifies `xsd:type=time` on the **ShipDate** attribute, the time part of the value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **ShipDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="82829-163">Не указывает `xsd:type` на атрибут **DueDate** , отображается то же значение, которое возвращается функцией [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82829-163">Does not specify `xsd:type` on the **DueDate** attribute, the same value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is displayed.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="82829-164">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="82829-164">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="82829-165">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="82829-165">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="82829-166">Сохраните файл с именем xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="82829-166">Save the file as xsdType.xml.</span></span>  
  
2.  <span data-ttu-id="82829-167">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="82829-167">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="82829-168">Сохраните файл под именем xsdTypeT.xml в том же каталоге, где был сохранен файл xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="82829-168">Save the file as xsdTypeT.xml in the same directory where you saved xsdType.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="xsdType.xml">  
        /Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="82829-169">Путь к каталогу схемы сопоставления (файл xsdType.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="82829-169">The directory path specified for the mapping schema (xsdType.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="82829-170">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="82829-170">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\xsdType.xml"  
    ```  
  
3.  <span data-ttu-id="82829-171">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="82829-171">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="82829-172">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="82829-172">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="82829-173">Частичный результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="82829-173">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43659"   
         CustomerID="676"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
  <Order SalesOrderID="43660"   
         CustomerID="117"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
 ...  
</ROOT>  
```  
  
 <span data-ttu-id="82829-174">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="82829-174">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader">  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="CustomerID"  />  
    <AttributeType name="OrderDate" dt:type="date" />  
    <AttributeType name="DueDate" />  
    <AttributeType name="ShipDate" dt:type="time" />  
  
    <attribute type="SalesOrderID" sql:field="OrderID" />  
    <attribute type="CustomerID" sql:field="CustomerID" />  
    <attribute type="OrderDate" sql:field="OrderDate" />  
    <attribute type="DueDate" sql:field="DueDate" />  
    <attribute type="ShipDate" sql:field="ShipDate" />  
</ElementType>  
</Schema>  
```  
  
### <a name="b-specifying-sql-data-type-using-sqldatatype"></a><span data-ttu-id="82829-175">Б.</span><span class="sxs-lookup"><span data-stu-id="82829-175">B.</span></span> <span data-ttu-id="82829-176">Указание типа данных SQL с помощью заметки sql:datatype</span><span class="sxs-lookup"><span data-stu-id="82829-176">Specifying SQL data type using sql:datatype</span></span>  
 <span data-ttu-id="82829-177">Рабочий пример см. в разделе пример инструкции для [групповой загрузки XML &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="82829-177">For a working sample, see Example G in [XML Bulk Load Examples &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span></span> <span data-ttu-id="82829-178">В этом примере выполняется массовая загрузка значения идентификатора GUID, включая "{" и "}".</span><span class="sxs-lookup"><span data-stu-id="82829-178">In this example, a GUID value including "{" and "}" is bulk loaded.</span></span> <span data-ttu-id="82829-179">Схема в этом примере указывает заметку `sql:datatype`, чтобы определить тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] как `uniqueidentifier`.</span><span class="sxs-lookup"><span data-stu-id="82829-179">The schema in this example specifies `sql:datatype` to identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as `uniqueidentifier`.</span></span> <span data-ttu-id="82829-180">В этом примере показано, когда необходимо указать `sql:datatype` в схеме.</span><span class="sxs-lookup"><span data-stu-id="82829-180">This example illustrate when `sql:datatype` must be specified in the schema.</span></span>  
  
  
