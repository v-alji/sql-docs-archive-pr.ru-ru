---
title: Общие сведения о схемах XSD с заметками (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- mapping schema [SQLXML], about mapping schema
- views [SQLXML]
- valid XSD schemas [SQLXML]
- annotations [SQLXML]
- XSD schemas [SQLXML], creating XML views
- annotated XSD schemas, creating XML views
- minimum XSD schema
- annotated XSD schemas, examples
- XML views [SQLXML]
ms.assetid: 15282db1-65c4-43be-bdb7-e9ef49cb33a2
author: rothja
ms.author: jroth
ms.openlocfilehash: b91be71569daa9e5bf4143be9f652617ba7c5b01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665939"
---
# <a name="introduction-to-annotated-xsd-schemas-sqlxml-40"></a><span data-ttu-id="1bad2-102">Введение в схемы XSD с заметками (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1bad2-102">Introduction to Annotated XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="1bad2-103">Можно создавать представления схем XML реляционных данных при помощи языка XSD.</span><span class="sxs-lookup"><span data-stu-id="1bad2-103">You can create XML views of relational data by using the XML Schema Definition (XSD) language.</span></span> <span data-ttu-id="1bad2-104">Затем можно выполнять запросы к этим представлениям при помощи языка XPath (XML Path).</span><span class="sxs-lookup"><span data-stu-id="1bad2-104">These views can then be queried by using XML Path language (XPath) queries.</span></span> <span data-ttu-id="1bad2-105">Это аналогично созданию представлений с помощью инструкции CREATE VIEW с последующим указанием запросов SQL к представлению.</span><span class="sxs-lookup"><span data-stu-id="1bad2-105">This is similar to creating views by using CREATE VIEW statements and then specifying SQL queries against the view.</span></span>  
  
 <span data-ttu-id="1bad2-106">Схема XML описывает структуру XML-документа, а также описывает различные ограничения на данные, содержащиеся в документе.</span><span class="sxs-lookup"><span data-stu-id="1bad2-106">An XML schema describes the structure of an XML document and also describes the various constraints on the data in the document.</span></span> <span data-ttu-id="1bad2-107">При задании запросов XPath по схеме структура возвращаемого XML-документа определяется согласно схеме, по которой выполняется запрос XPath.</span><span class="sxs-lookup"><span data-stu-id="1bad2-107">When you specify XPath queries against the schema, the structure of the XML document returned is determined by the schema against which the XPath query is executed.</span></span>  
  
 <span data-ttu-id="1bad2-108">В схеме XSD **\<xsd:schema>** элемент включает всю схему; все объявления элементов должны содержаться внутри **\<xsd:schema>** элемента.</span><span class="sxs-lookup"><span data-stu-id="1bad2-108">In an XSD schema, the **\<xsd:schema>** element encloses the entire schema; all element declarations must be contained within the **\<xsd:schema>** element.</span></span> <span data-ttu-id="1bad2-109">Можно описать атрибуты, определяющие пространство имен, в котором находится схема, и пространства имен, используемые в схеме в качестве свойств **\<xsd:schema>** элемента.</span><span class="sxs-lookup"><span data-stu-id="1bad2-109">You can describe attributes that define the namespace in which the schema resides and the namespaces that are used in the schema as properties of the **\<xsd:schema>** element.</span></span>  
  
 <span data-ttu-id="1bad2-110">Допустимая схема XSD должна содержать **\<xsd:schema>** элемент, определенный следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1bad2-110">A valid XSD schema must contain the **\<xsd:schema>** element defined as follows:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<!-- additional schema definitions here -->  
</xsd:schema>  
```  
  
 <span data-ttu-id="1bad2-111">**\<xsd:schema>** Элемент является производным от спецификации пространства имен схемы XML в http://www.w3.org/2001/XMLSchema .</span><span class="sxs-lookup"><span data-stu-id="1bad2-111">The **\<xsd:schema>** element is derived from the XML Schema namespace specification at http://www.w3.org/2001/XMLSchema.</span></span>  
  
## <a name="annotations-to-the-xsd-schema"></a><span data-ttu-id="1bad2-112">Заметки к схеме XSD</span><span class="sxs-lookup"><span data-stu-id="1bad2-112">Annotations to the XSD Schema</span></span>  
 <span data-ttu-id="1bad2-113">Можно использовать схему XSD с заметками, которые описывают сопоставление с базой данных, запрашивают базу данных, а затем возвращают результаты в форме XML-документа.</span><span class="sxs-lookup"><span data-stu-id="1bad2-113">You can use an XSD schema with annotations that describe the mapping to a database, query the database, and return the results in the form of an XML document.</span></span> <span data-ttu-id="1bad2-114">Заметки служат для сопоставления схемы XSD с таблицами и столбцами базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bad2-114">Annotations are provided to map an XSD schema to database tables and columns.</span></span> <span data-ttu-id="1bad2-115">Можно указывать запросы XPath к представлениям XML, созданным на основе схемы XSD, для запроса базы данных и получения результатов в виде XML.</span><span class="sxs-lookup"><span data-stu-id="1bad2-115">XPath queries can be specified against the XML view created by the XSD schema to query the database and obtain results as an XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bad2-116">В [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 язык схем XSD поддерживает заметки, введенные в языке схем XDR в [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bad2-116">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports the annotations introduced with annotated XML-Data Reduced (XDR) schema language in [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="1bad2-117">Схемы XDR с заметками в SQLXML 4.0 считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="1bad2-117">Annotated XDR is deprecated in SQLXML 4.0.</span></span>  
  
 <span data-ttu-id="1bad2-118">В контексте реляционной базы данных полезно сопоставить произвольную схему XSD с реляционным хранилищем.</span><span class="sxs-lookup"><span data-stu-id="1bad2-118">In the context of the relational database, it is useful to map the arbitrary XSD schema to a relational store.</span></span> <span data-ttu-id="1bad2-119">Один из способов достижения этого состоит в создании аннотированной схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="1bad2-119">One way to achieve this is to annotate the XSD schema.</span></span> <span data-ttu-id="1bad2-120">Схема XSD с заметками называется *схемой сопоставления*, которая предоставляет сведения о том, как данные XML должны сопоставляться с реляционным хранилищем.</span><span class="sxs-lookup"><span data-stu-id="1bad2-120">An XSD schema with the annotations is referred to as a *mapping schema*, which provides information pertaining to how XML data is to be mapped to the relational store.</span></span> <span data-ttu-id="1bad2-121">По сути, схема сопоставления является XML-представлением реляционных данных.</span><span class="sxs-lookup"><span data-stu-id="1bad2-121">A mapping schema is, in effect, an XML view of the relational data.</span></span> <span data-ttu-id="1bad2-122">Эти сопоставления позволяют получать реляционные данные в виде XML-документа.</span><span class="sxs-lookup"><span data-stu-id="1bad2-122">These mappings can be used to retrieve relational data as an XML document.</span></span>  
  
## <a name="namespace-for-annotations"></a><span data-ttu-id="1bad2-123">Пространства имен для заметок</span><span class="sxs-lookup"><span data-stu-id="1bad2-123">Namespace for Annotations</span></span>  
 <span data-ttu-id="1bad2-124">В схеме XSD заметки задаются с помощью пространства имен **urn: schemas-microsoft-com: Mapping-Schema**.</span><span class="sxs-lookup"><span data-stu-id="1bad2-124">In an XSD schema, annotations are specified by using the namespace **urn:schemas-microsoft-com:mapping-schema**.</span></span> <span data-ttu-id="1bad2-125">Как показано в следующем примере, проще всего указать пространство имен в **\<xsd:schema>** теге.</span><span class="sxs-lookup"><span data-stu-id="1bad2-125">As shown in the following example, the easiest way to specify the namespace is to specify it in the **\<xsd:schema>** tag.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
...  
</xsd:schema>  
```  
  
 <span data-ttu-id="1bad2-126">Префикс пространства имен может быть произвольным.</span><span class="sxs-lookup"><span data-stu-id="1bad2-126">The namespace prefix that is used is arbitrary.</span></span> <span data-ttu-id="1bad2-127">В этой документации префикс **SQL** используется для обозначения пространства имен annotation и для различения заметок в этом пространстве имен от других пространств имен.</span><span class="sxs-lookup"><span data-stu-id="1bad2-127">In this documentation, the **sql** prefix is used to denote the annotation namespace and to distinguish annotations in this namespace from those in other namespaces.</span></span>  
  
## <a name="example-of-an-annotated-xsd-schema"></a><span data-ttu-id="1bad2-128">Пример схемы XSD с заметками</span><span class="sxs-lookup"><span data-stu-id="1bad2-128">Example of an Annotated XSD Schema</span></span>  
 <span data-ttu-id="1bad2-129">В следующем примере схема XSD состоит из **\<Person.Contact>** элемента.</span><span class="sxs-lookup"><span data-stu-id="1bad2-129">In the following example, the XSD schema consists of an **\<Person.Contact>** element.</span></span> <span data-ttu-id="1bad2-130">**\<Employee>** Элемент имеет атрибут **ContactID** и **\<FirstName>** **\<LastName>** дочерние элементы:</span><span class="sxs-lookup"><span data-stu-id="1bad2-130">The **\<Employee>** element has a **ContactID** attribute and **\<FirstName>** and **\<LastName>** child elements:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <xsd:element name="Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"    
                     type="xsd:string" />   
        <xsd:element name="LName"  
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID" type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="1bad2-131">К схеме XSD добавляются заметки, что позволяет сопоставить ее элементы и атрибуты с именами таблиц и столбцов базы данных:</span><span class="sxs-lookup"><span data-stu-id="1bad2-131">Annotations are added to this XSD schema to map its elements and attributes to the database tables and columns:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID"   
                       sql:field="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="1bad2-132">В схеме сопоставления **\<Contact>** элемент сопоставляется с таблицей Person. Contact в образце базы данных AdventureWorks с помощью `sql:relation` аннотации.</span><span class="sxs-lookup"><span data-stu-id="1bad2-132">In the mapping schema, the **\<Contact>** element is mapped to the Person.Contact table in the sample AdventureWorks database by using the `sql:relation` annotation.</span></span> <span data-ttu-id="1bad2-133">Атрибуты ConID, FName и LName сопоставлены столбцам ContactID, FirstName и LastName таблицы Person.Contact с помощью заметок `sql:field`.</span><span class="sxs-lookup"><span data-stu-id="1bad2-133">The attributes ConID, FName, and LName are mapped to the ContactID, FirstName, and LastName columns in the Person.Contact table by using the `sql:field` annotations.</span></span>  
  
 <span data-ttu-id="1bad2-134">Эта аннотированная схема XSD создает XML-представление реляционных данных.</span><span class="sxs-lookup"><span data-stu-id="1bad2-134">This annotated XSD schema provides the XML view of the relational data.</span></span> <span data-ttu-id="1bad2-135">Затем можно выполнять запросы XPath к этому XML-представлению.</span><span class="sxs-lookup"><span data-stu-id="1bad2-135">This XML view can be queried using the XPath language.</span></span> <span data-ttu-id="1bad2-136">Запрос XPath возвращает в качестве результата XML-документ в отличие от запросов SQL, которые возвращают наборы строк.</span><span class="sxs-lookup"><span data-stu-id="1bad2-136">An XPath query returns an XML document as a result, instead of the rowset that is returned by SQL queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bad2-137">В схеме сопоставления чувствительность к регистру для указанных реляционных значений (таких как имя таблицы или столбца) зависит от того, использует ли SQL Server чувствительные к регистру параметры сортировки.</span><span class="sxs-lookup"><span data-stu-id="1bad2-137">In the mapping schema, case-sensitivity for the specified relational values (such as table name and column name) depends upon if SQL Server is using case-sensitive collation settings.</span></span> <span data-ttu-id="1bad2-138">Дополнительные сведения см. в статье [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="1bad2-138">For more information, see [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="1bad2-139">Другие ресурсы</span><span class="sxs-lookup"><span data-stu-id="1bad2-139">Other Resources</span></span>  
 <span data-ttu-id="1bad2-140">Дополнительные сведения о языке XSD, языке XPath и преобразованиях XSLT находятся на следующих веб-сайтах.</span><span class="sxs-lookup"><span data-stu-id="1bad2-140">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="1bad2-141">XML-схема, часть 0: учебник, рекомендация консорциума W3C (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="1bad2-141">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="1bad2-142">XML-схема, часть 1: структуры, рекомендация консорциума W3C (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="1bad2-142">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="1bad2-143">XML-схема, часть 2: типы типов, рекомендация консорциума W3C (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="1bad2-143">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="1bad2-144">Язык XML Path (XPath) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="1bad2-144">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="1bad2-145">Преобразования XSL (XSLT) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="1bad2-145">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bad2-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bad2-146">See Also</span></span>  
 <span data-ttu-id="1bad2-147">[Рекомендации по безопасности схемы с заметками &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="1bad2-147">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="1bad2-148">Схемы XDR с заметками &#40;нерекомендуемые в SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1bad2-148">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
  
  
