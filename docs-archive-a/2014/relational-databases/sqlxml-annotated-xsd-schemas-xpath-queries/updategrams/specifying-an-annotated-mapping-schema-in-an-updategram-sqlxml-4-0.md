---
title: Указание схемы сопоставления с заметками в диаграмма обновления (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, updategrams
- data types [SQLXML], mapping schema in updategrams
- updategrams [SQLXML], annotated mapping schemas
- annotated XDR schemas, updategrams
- inverse attribute
- parent-child relationships [SQLXML]
- mapping-schema attribute
- mapping schema [SQLXML], updategrams
- sql:inverse
ms.assetid: 2e266ed9-4cfb-434a-af55-d0839f64bb9a
author: rothja
ms.author: jroth
ms.openlocfilehash: a181b3081b51cca160709703364c248e495e0214
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665957"
---
# <a name="specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-40"></a><span data-ttu-id="791ff-102">Определение схемы с заметками сопоставления в диаграмме обновления (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="791ff-102">Specifying an Annotated Mapping Schema in an Updategram (SQLXML 4.0)</span></span>
  <span data-ttu-id="791ff-103">В этом разделе описывается использование схемы сопоставления (XSD или XDR), указанной в диаграмме обновления, для обработки обновлений.</span><span class="sxs-lookup"><span data-stu-id="791ff-103">This topic explains how the mapping schema (XSD or XDR) that is specified in an updategram is used to process the updates.</span></span> <span data-ttu-id="791ff-104">В диаграмма обновления можно указать имя схемы сопоставления с заметками для использования при сопоставлении элементов и атрибутов в диаграмма обновления с таблицами и столбцами в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="791ff-104">In an updategram, you can provide the name of an annotated mapping schema to use in mapping the elements and attributes in the updategram to tables and columns in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="791ff-105">Если в диаграмме обновления указана схема сопоставления, имена элементов и атрибутов, которые указаны в этой диаграмме обновления, должны сопоставляться с элементами и атрибутами в схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="791ff-105">When a mapping schema is specified in an updategram, the element and attribute names that are specified in the updategram must map to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="791ff-106">Чтобы указать схему сопоставления, используйте `mapping-schema` атрибут **\<sync>** элемента.</span><span class="sxs-lookup"><span data-stu-id="791ff-106">To specify a mapping schema, you use the `mapping-schema` attribute of the **\<sync>** element.</span></span> <span data-ttu-id="791ff-107">В следующих примерах показаны две диаграммы обновления: в одной используется простая схема сопоставления, а в другой — более сложная схема сопоставления.</span><span class="sxs-lookup"><span data-stu-id="791ff-107">The following examples show two updategrams: one that uses a simple mapping schema, and one that uses a more complex schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="791ff-108">Настоящая документация предназначена для тех, кто знаком с шаблонами и поддержкой схем сопоставления в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="791ff-108">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="791ff-109">Дополнительные сведения см. [в разделе Введение в схемы XSD с Заметками &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="791ff-109">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="791ff-110">Дополнительные сведения о устаревших приложениях, использующих XDR, см. [в разделе схемы XDR с Заметками &#40;не рекомендуется в SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="791ff-110">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="dealing-with-data-types"></a><span data-ttu-id="791ff-111">Работа с типами данных</span><span class="sxs-lookup"><span data-stu-id="791ff-111">Dealing with Data Types</span></span>  
 <span data-ttu-id="791ff-112">Если схема задает `image` `binary` `varbinary` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] тип данных, или (с помощью `sql:datatype` ) и не указывает тип данных XML, диаграмма обновления ПРЕДПОЛАГАЕТ, что тип данных XML — `binary base 64` .</span><span class="sxs-lookup"><span data-stu-id="791ff-112">If the schema specifies the `image`, `binary`, or `varbinary`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (by using `sql:datatype`) and does not specify an XML data type, the updategram assumes that the XML data type is `binary base 64`.</span></span> <span data-ttu-id="791ff-113">Если данные имеют тип `bin.base`, следует явно указать этот тип (`dt:type=bin.base` или `type="xsd:hexBinary"`).</span><span class="sxs-lookup"><span data-stu-id="791ff-113">If your data is `bin.base` type, you must explicitly specify the type (`dt:type=bin.base` or `type="xsd:hexBinary"`).</span></span>  
  
 <span data-ttu-id="791ff-114">Если в схеме указан тип данных XSD `dateTime`, `date` или `time`, то также необходимо указать соответствующий тип данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при помощи `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="791ff-114">If the schema specifies the `dateTime`, `date`, or `time` XSD data type, you must also specify the corresponding [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type by using `sql:datatype="dateTime"`.</span></span>  
  
 <span data-ttu-id="791ff-115">При обработке параметров [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` типа необходимо явно указать `sql:datatype="money"` на соответствующем узле в схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="791ff-115">When handling parameters of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` type, you must explicitly specify `sql:datatype="money"` on the appropriate node in the mapping schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="791ff-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="791ff-116">Examples</span></span>  
 <span data-ttu-id="791ff-117">Чтобы создать рабочие образцы с помощью следующих примеров, необходимо выполнить требования, указанные в [требованиях к запуску примеров SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="791ff-117">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-creating-an-updategram-with-a-simple-mapping-schema"></a><span data-ttu-id="791ff-118">A.</span><span class="sxs-lookup"><span data-stu-id="791ff-118">A.</span></span> <span data-ttu-id="791ff-119">Создание диаграммы обновления с простой схемой сопоставления</span><span class="sxs-lookup"><span data-stu-id="791ff-119">Creating an updategram with a simple mapping schema</span></span>  
 <span data-ttu-id="791ff-120">Следующая схема XSD (SampleSchema.xml) — это схема сопоставления, которая сопоставляет **\<Customer>** элемент с таблицей Sales. Customer:</span><span class="sxs-lookup"><span data-stu-id="791ff-120">The following XSD schema (SampleSchema.xml) is a mapping schema that maps the **\<Customer>** element to the Sales.Customer table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
        <xsd:attribute name="CustID"    
                       sql:field="CustomerID"   
                       type="xsd:string" />  
        <xsd:attribute name="RegionID"    
                       sql:field="TerritoryID"    
                       type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="791ff-121">Следующая диаграмма обновления вставляет запись в таблицу Sales.Customer и использует предыдущую схему сопоставления для сопоставления этих данных с таблицей.</span><span class="sxs-lookup"><span data-stu-id="791ff-121">The following updategram inserts a record into the Sales.Customer table and relies on the previous mapping schema to properly map this data to the table.</span></span> <span data-ttu-id="791ff-122">Обратите внимание, что диаграмма обновления использует то же имя элемента, **\<Customer>** что определено в схеме.</span><span class="sxs-lookup"><span data-stu-id="791ff-122">Notice that the updategram uses the same element name, **\<Customer>**, as defined in the schema.</span></span> <span data-ttu-id="791ff-123">Это является обязательным, поскольку диаграмма обновления указывает конкретную схему.</span><span class="sxs-lookup"><span data-stu-id="791ff-123">This is mandatory because the updategram specifies a particular schema.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="791ff-124">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="791ff-124">To test the updategram</span></span>  
  
1.  <span data-ttu-id="791ff-125">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="791ff-125">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="791ff-126">Сохраните файл под именем SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="791ff-126">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="791ff-127">Скопируйте приведенный ниже шаблон диаграммы обновления и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="791ff-127">Copy the updategram template below and paste it into a text file.</span></span> <span data-ttu-id="791ff-128">Сохраните файл под именем SampleUpdategram.xml в том же каталоге, где был сохранен файл SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="791ff-128">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleUpdateSchema.xml">  
        <updg:before>  
          <Customer CustID="1" RegionID="1"  />  
        </updg:before>  
        <updg:after>  
          <Customer CustID="1" RegionID="2" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="791ff-129">Путь к каталогу задается для схемы сопоставления (SampleUpdateSchema.xml) относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="791ff-129">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="791ff-130">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="791ff-130">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="791ff-131">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="791ff-131">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="791ff-132">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="791ff-132">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="791ff-133">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="791ff-133">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
   <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
         xmlns:dt="urn:schemas-microsoft-com:datatypes"   
         xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
     <ElementType name="Customer" sql:relation="Sales.Customer" >  
       <AttributeType name="CustID" />  
       <AttributeType name="RegionID" />  
  
       <attribute type="CustID" sql:field="CustomerID" />  
       <attribute type="RegionID" sql:field="TerritoryID" />  
     </ElementType>  
   </Schema>   
```  
  
### <a name="b-inserting-a-record-by-using-the-parent-child-relationship-specified-in-the-mapping-schema"></a><span data-ttu-id="791ff-134">Б.</span><span class="sxs-lookup"><span data-stu-id="791ff-134">B.</span></span> <span data-ttu-id="791ff-135">Вставка записи с помощью связи «родители-потомки», указанной в схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="791ff-135">Inserting a record by using the parent-child relationship specified in the mapping schema</span></span>  
 <span data-ttu-id="791ff-136">Между элементами схемы можно устанавливать связь.</span><span class="sxs-lookup"><span data-stu-id="791ff-136">Schema elements can be related.</span></span> <span data-ttu-id="791ff-137">**\<sql:relationship>** Элемент указывает связь "родители-потомки" между элементами схемы.</span><span class="sxs-lookup"><span data-stu-id="791ff-137">The **\<sql:relationship>** element specifies the parent-child relationship between the schema elements.</span></span> <span data-ttu-id="791ff-138">Эти данные используются для обновления соответствующих таблиц, между которыми установлена связь «первичный-внешний ключ».</span><span class="sxs-lookup"><span data-stu-id="791ff-138">This information is used to update corresponding tables that have primary-key/foreign-key relationship.</span></span>  
  
 <span data-ttu-id="791ff-139">Следующая схема сопоставления (SampleSchema.xml) состоит из двух элементов **\<Order>** и **\<OD>** :</span><span class="sxs-lookup"><span data-stu-id="791ff-139">The following mapping schema (SampleSchema.xml) consists of two elements, **\<Order>** and **\<OD>**:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="OD"   
                     sql:relation="Sales.SalesOrderDetail"  
                     sql:relationship="OrderOD" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID"   type="xsd:integer" />  
              <xsd:attribute name="ProductID" type="xsd:integer" />  
             <xsd:attribute name="UnitPrice"  type="xsd:decimal" />  
             <xsd:attribute name="OrderQty"   type="xsd:integer" />  
             <xsd:attribute name="UnitPriceDiscount"   type="xsd:decimal" />  
  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesOrderID"  type="xsd:integer" />  
        <xsd:attribute name="OrderDate"  type="xsd:date" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="791ff-140">Следующая диаграмма обновления использует эту схему XSD для добавления новой записи с подробными сведениями о заказе ( **\<OD>** элемент в **\<after>** блоке) для заказа 43860.</span><span class="sxs-lookup"><span data-stu-id="791ff-140">The following updategram uses this XSD schema to add a new order detail record (an **\<OD>** element in the **\<after>** block) for order 43860.</span></span> <span data-ttu-id="791ff-141">Атрибут `mapping-schema` служит для указания схемы сопоставления, которая будет использоваться диаграммой обновления.</span><span class="sxs-lookup"><span data-stu-id="791ff-141">The `mapping-schema` attribute is used to specify the mapping schema in the updategram.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43860" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43860" >  
           <OD ProductID="753" UnitPrice="$10.00"  
               Quantity="5" Discount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="791ff-142">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="791ff-142">To test the updategram</span></span>  
  
1.  <span data-ttu-id="791ff-143">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="791ff-143">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="791ff-144">Сохраните файл под именем SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="791ff-144">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="791ff-145">Скопируйте приведенный выше шаблон диаграммы обновления и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="791ff-145">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="791ff-146">Сохраните файл под именем SampleUpdategram.xml в том же каталоге, где был сохранен файл SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="791ff-146">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="791ff-147">Путь к каталогу задается для схемы сопоставления (SampleUpdateSchema.xml) относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="791ff-147">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="791ff-148">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="791ff-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="791ff-149">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="791ff-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="791ff-150">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="791ff-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="791ff-151">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="791ff-151">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="OD" sql:relation="Sales.SalesOrderDetail" >  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="ProductID" />  
    <AttributeType name="UnitPrice"  dt:type="fixed.14.4" />  
    <AttributeType name="OrderQty" />  
    <AttributeType name="UnitPriceDiscount" />  
  
    <attribute type="SalesOrderID" />  
    <attribute type="ProductID" />  
    <attribute type="UnitPrice" />  
    <attribute type="OrderQty" />  
    <attribute type="UnitPriceDiscount" />  
</ElementType>  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="OrderDate" />  
  
    <attribute type="CustomerID" />  
    <attribute type="SalesOrderID" />  
    <attribute type="OrderDate" />  
    <element type="OD" >  
             <sql:relationship   
                   key-relation="Sales.SalesOrderHeader"  
                   key="SalesOrderID"  
                   foreign-key="SalesOrderID"  
                   foreign-relation="Sales.SalesOrderDetail" />  
    </element>  
</ElementType>  
</Schema>  
```  
  
### <a name="c-inserting-a-record-by-using-the-parent-child-relationship-and-inverse-annotation-specified-in-the-xsd-schema"></a><span data-ttu-id="791ff-152">В.</span><span class="sxs-lookup"><span data-stu-id="791ff-152">C.</span></span> <span data-ttu-id="791ff-153">Вставка записи с помощью связи «родители-потомки» и заметки INVERSE, указанных в схеме XSD</span><span class="sxs-lookup"><span data-stu-id="791ff-153">Inserting a record by using the parent-child relationship and inverse annotation specified in the XSD schema</span></span>  
 <span data-ttu-id="791ff-154">В этом примере иллюстрируется использование связи «родители-потомки», указанной в XSD, в логике диаграммы обновления для обработки обновлений, а также использование заметки `inverse`.</span><span class="sxs-lookup"><span data-stu-id="791ff-154">This example illustrates how the updategram logic uses the parent-child relationship specified in the XSD to process updates, and how the `inverse` annotation is used.</span></span> <span data-ttu-id="791ff-155">Дополнительные сведения о `inverse` аннотации см. в разделе [Указание атрибута SQL: инверсии в SQL: RELATIONSHIP &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="791ff-155">For more information about the `inverse` annotation, see [Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="791ff-156">В этом примере предполагается, что в базе данных **tempdb** находятся следующие таблицы:</span><span class="sxs-lookup"><span data-stu-id="791ff-156">This example assumes that the following tables are in the **tempdb** database:</span></span>  
  
-   <span data-ttu-id="791ff-157">`Cust (CustomerID, CompanyName)`, где `CustomerID` — это первичный ключ;</span><span class="sxs-lookup"><span data-stu-id="791ff-157">`Cust (CustomerID, CompanyName)`, where `CustomerID` is the primary key</span></span>  
  
-   <span data-ttu-id="791ff-158">`Ord (OrderID, CustomerID)`, где `CustomerID` — это внешний ключ, который ссылается на первичный ключ `CustomerID` из таблицы `Cust`.</span><span class="sxs-lookup"><span data-stu-id="791ff-158">`Ord (OrderID, CustomerID)`, where `CustomerID` is a foreign key that refers to the `CustomerID` primary key in the `Cust` table.</span></span>  
  
 <span data-ttu-id="791ff-159">Для вставки записей в таблицы Cust и Ord в диаграмме обновления используется следующая схема XSD:</span><span class="sxs-lookup"><span data-stu-id="791ff-159">The updategram uses the following XSD schema to insert records into the Cust and Ord tables :</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
       <sql:relationship name="OrdCust" inverse="true"  
                  parent="Ord"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Cust"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
<xsd:element name="Order" sql:relation="Ord">  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customer" sql:relationship="OrdCust"/>  
    </xsd:sequence>  
    <xsd:attribute name="OrderID"   type="xsd:int"/>  
    <xsd:attribute name="CustomerID" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
<xsd:element name="Customer" sql:relation="Cust">  
  <xsd:complexType>  
     <xsd:attribute name="CustomerID"  type="xsd:string"/>  
    <xsd:attribute name="CompanyName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="791ff-160">Схема XSD в этом примере содержит **\<Customer>** элементы и **\<Order>** , а также указывает связь типа «родители-потомки» между двумя элементами.</span><span class="sxs-lookup"><span data-stu-id="791ff-160">The XSD schema in this example has **\<Customer>** and **\<Order>** elements, and it specifies a parent-child relationship between the two elements.</span></span> <span data-ttu-id="791ff-161">Он определяет **\<Order>** как родительский элемент и **\<Customer>** как дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="791ff-161">It identifies **\<Order>** as the parent element and **\<Customer>** as the child element.</span></span>  
  
 <span data-ttu-id="791ff-162">Логика обработки диаграммы обновления использует данные о связи «родители-потомки» для определения порядка вставки записей в таблицы.</span><span class="sxs-lookup"><span data-stu-id="791ff-162">The updategram processing logic uses the information about the parent-child relationship to determine the order in which records are inserted into tables.</span></span> <span data-ttu-id="791ff-163">В этом примере логика диаграмма обновления сначала пытается вставить запись в таблицу (поскольку **\<Order>** является родительским элементом), а затем пытается вставить запись в таблицу Cust (поскольку **\<Customer>** является дочерним элементом).</span><span class="sxs-lookup"><span data-stu-id="791ff-163">In this example, the updategram logic first attempts to insert a record into the Ord table (because **\<Order>** is the parent) and then attempts to insert a record into the Cust table (because **\<Customer>** is the child).</span></span> <span data-ttu-id="791ff-164">Однако из-за данных «первичный-внешний ключ», которые содержатся в схеме таблицы базы данных, эта операция вставки ведет к нарушению внешнего ключа в базе данных и завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="791ff-164">However, because of the primary key/foreign key information that is contained in the database table schema, this insert operation causes a foreign key violation in the database and the insert fails.</span></span>  
  
 <span data-ttu-id="791ff-165">Чтобы указать логике диаграмма обновления на обратную связь «родители-потомки» во время операции обновления, `inverse` заметка задается для **\<relationship>** элемента.</span><span class="sxs-lookup"><span data-stu-id="791ff-165">To instruct the updategram logic to reverse the parent-child relationship during the update operation, the `inverse` annotation is specified on the **\<relationship>** element.</span></span> <span data-ttu-id="791ff-166">В итоге записи будут сначала добавляться в таблицу Cust, а затем в таблицу Ord, и операция завершится успешно.</span><span class="sxs-lookup"><span data-stu-id="791ff-166">As a result, records are added first in the Cust table and then in the Ord table, and the operation succeeds.</span></span>  
  
 <span data-ttu-id="791ff-167">Следующая диаграмма обновления вставляет заказ (OrderID=2) в таблицу Ord, а клиента (CustomerID='AAAAA') — в таблицу Cust при помощи указанной схемы XSD:</span><span class="sxs-lookup"><span data-stu-id="791ff-167">The following updategram inserts an order (OrderID=2) in the Ord table and a customer (CustomerID='AAAAA') in the Cust table by using the specified XSD schema:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before/>  
    <updg:after>  
      <Order OrderID="2" CustomerID="AAAAA" >  
        <Customer CustomerID="AAAAA" CompanyName="AAAAA Company" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="791ff-168">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="791ff-168">To test the updategram</span></span>  
  
1.  <span data-ttu-id="791ff-169">Создайте следующие таблицы в базе данных **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="791ff-169">Create these tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust(CustomerID varchar(5) primary key,   
                      CompanyName varchar(20))  
    GO  
    CREATE TABLE Ord (OrderID int primary key,   
                      CustomerID varchar(5) references Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="791ff-170">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="791ff-170">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="791ff-171">Сохраните файл под именем SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="791ff-171">Save the file as SampleUpdateSchema.xml.</span></span>  
  
3.  <span data-ttu-id="791ff-172">Скопируйте приведенный выше шаблон диаграммы обновления и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="791ff-172">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="791ff-173">Сохраните файл под именем SampleUpdategram.xml в том же каталоге, где был сохранен файл SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="791ff-173">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="791ff-174">Путь к каталогу задается для схемы сопоставления (SampleUpdateSchema.xml) относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="791ff-174">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="791ff-175">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="791ff-175">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
4.  <span data-ttu-id="791ff-176">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="791ff-176">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="791ff-177">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="791ff-177">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791ff-178">См. также:</span><span class="sxs-lookup"><span data-stu-id="791ff-178">See Also</span></span>  
 [<span data-ttu-id="791ff-179">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="791ff-179">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
