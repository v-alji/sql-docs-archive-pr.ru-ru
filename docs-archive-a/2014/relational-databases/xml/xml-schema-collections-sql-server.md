---
title: Коллекции схем XML (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- xml_schema_namespace function
- XML schema collections [SQL Server], about XML schema collections
- metadata [SQL Server], XML schema collections
- queries [XML in SQL Server], XML schema collections
- schema collections [SQL Server]
- schemas [SQL Server], XML
- XML [SQL Server], schema collections
- XML schema collections [SQL Server]
- schema collections [SQL Server], about XML schema collections
ms.assetid: 659d41aa-ccec-4554-804a-722a96ef25c2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ee4757f1353278447ee55e97c8d4ba23aa2d649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665893"
---
# <a name="xml-schema-collections-sql-server"></a><span data-ttu-id="9fe6c-102">Коллекции XML-схем (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9fe6c-102">XML Schema Collections (SQL Server)</span></span>
  <span data-ttu-id="9fe6c-103">Как описано в разделе [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server предоставляет собственное хранилище XML-данных через `xml` тип данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-103">As described in the topic, [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server provides native storage of XML data through the `xml` data type.</span></span> <span data-ttu-id="9fe6c-104">При необходимости можно связать схемы XSD с переменной или столбцом `xml` типа с помощью коллекции схем XML.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-104">You can optionally associate XSD schemas with a variable or a column of `xml` type through an XML schema collection.</span></span> <span data-ttu-id="9fe6c-105">Коллекция XML-схем хранит импортированные XML-схемы и используется для решения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-105">The XML schema collection stores the imported XML schemas and is then used to do the following:</span></span>  
  
-   <span data-ttu-id="9fe6c-106">проверка экземпляров XML;</span><span class="sxs-lookup"><span data-stu-id="9fe6c-106">Validate XML instances</span></span>  
  
-   <span data-ttu-id="9fe6c-107">типизация XML-данных, хранимых в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-107">Type the XML data as it is stored in the database</span></span>  
  
 <span data-ttu-id="9fe6c-108">Коллекция XML-схем — это сущность класса метаданных, подобная таблице в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-108">Note that the XML schema collection is a metadata entity like a table in the database.</span></span> <span data-ttu-id="9fe6c-109">Можно создавать, изменять и удалять эти схемы.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-109">You can create, modify, and drop them.</span></span> <span data-ttu-id="9fe6c-110">Схемы, указанные в инструкции [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) , автоматически импортируются в создаваемую коллекцию XML-схем.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-110">Schemas specified in a [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) statement are automatically imported into the newly created XML schema collection object.</span></span> <span data-ttu-id="9fe6c-111">Можно импортировать дополнительные схемы или компоненты схем в существующую в базе данных коллекцию при помощи инструкции [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9fe6c-111">You can import additional schemas or schema components into an existing collection object in the database by using the [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="9fe6c-112">Как описано в разделе [Сравнение типизированного и нетипизированного XML](../xml/compare-typed-xml-to-untyped-xml.md), код XML, хранимый в столбце или переменной, с которой связана схема, называется **типизированным**, потому что схема предоставляет необходимую информацию о типах данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-112">As described in the topic, [Typed vs. Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md), the XML stored in a column or variable that a schema is associated with is referred to as **typed** XML, because the schema provides the necessary data type information for the instance data.</span></span> <span data-ttu-id="9fe6c-113">В SQL Server эта информация о типах используется для оптимизации хранения данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-113">SQL Server uses this type information to optimize data storage.</span></span>  
  
 <span data-ttu-id="9fe6c-114">Механизм обработки запросов применяет схемы для проверки типов, а также оптимизации запросов и изменения данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-114">The query-processing engine also uses the schema for type checking and to optimize queries and data modification.</span></span>  
  
 <span data-ttu-id="9fe6c-115">Кроме того, SQL Server использует связанную коллекцию XML-схем (в случае типизированной) `xml` для проверки экземпляра XML.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-115">Also, SQL Server uses the associated XML schema collection, in the case of typed `xml`, to validate the XML instance.</span></span> <span data-ttu-id="9fe6c-116">Если экземпляр XML соответствует схеме, база данных позволяет сохранить его в системе с информацией о его типах.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-116">If the XML instance complies with the schema, the database allows the instance to be stored in the system with their type information.</span></span> <span data-ttu-id="9fe6c-117">В противном случае она отклоняет экземпляр.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-117">Otherwise, it rejects the instance.</span></span>  
  
 <span data-ttu-id="9fe6c-118">Встроенная функция XML_SCHEMA_NAMESPACE позволяет получить коллекцию схем, хранимую в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-118">You can use the intrinsic function XML_SCHEMA_NAMESPACE to retrieve the schema collection that is stored in the database.</span></span> <span data-ttu-id="9fe6c-119">Дополнительные сведения см. в разделе [Просмотр хранимой коллекции схем XML](../xml/view-a-stored-xml-schema-collection.md).</span><span class="sxs-lookup"><span data-stu-id="9fe6c-119">For more information, see [View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md).</span></span>  
  
 <span data-ttu-id="9fe6c-120">Кроме того, можно использовать коллекцию схем XML для типизации переменных, параметров и столбцов типа XML.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-120">You can also use the XML schema collection to type XML variables, parameters, and columns.</span></span>  
  
##  <a name="ddl-for-managing-schema-collections"></a><a name="ddl"></a> <span data-ttu-id="9fe6c-121">DDL для управления коллекциями схем</span><span class="sxs-lookup"><span data-stu-id="9fe6c-121">DDL for Managing Schema Collections</span></span>  
 <span data-ttu-id="9fe6c-122">В базе данных можно создавать коллекции схем XML и связывать их с переменными и столбцами типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-122">You can create XML schema collections in the database and associate them with variables and columns of `xml` type.</span></span> <span data-ttu-id="9fe6c-123">Для управления коллекциями схем в базе данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предусмотрены следующие инструкции DDL:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-123">To manage schema collections in the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following DDL statements:</span></span>  
  
-   <span data-ttu-id="9fe6c-124">[CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) импортирует компоненты схемы в базу данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Imports schema components into a database.</span></span>  
  
-   <span data-ttu-id="9fe6c-125">[ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) изменяет компоненты схемы в существующей коллекции схем XML.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifies the schema components in an existing XML schema collection.</span></span>  
  
-   <span data-ttu-id="9fe6c-126">[DROP XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) полностью удаляет коллекцию схем XML и все ее компоненты.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Deletes a complete XML schema collection and all its components.</span></span>  
  
 <span data-ttu-id="9fe6c-127">Чтобы использовать коллекцию XML-схем и содержащиеся в ней схемы, следует сначала создать коллекцию и схемы с помощью инструкции CREATE XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-127">To use an XML schema collection and the schemas it contains, you must first create the collection and the schemas by using the CREATE XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="9fe6c-128">После создания коллекции схемы можно создавать переменные и столбцы типа `xml` и связать с ними коллекцию схем.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-128">After the schema collection is created, you can then create variables and columns of `xml` type and associate the schema collection with them.</span></span> <span data-ttu-id="9fe6c-129">Обратите внимание, что после создания коллекции различные компоненты схем будут храниться в метаданных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-129">Note that after a schema collection is created, various schema components are stored in the metadata.</span></span> <span data-ttu-id="9fe6c-130">Кроме того, добавлять большие компоненты в существующие схемы или новые схемы в существующую коллекцию можно с помощью инструкции ALTER XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-130">You can also use the ALTER XML SCHEMA COLLECTION to add more components to the existing schemas or add new schemas to an existing collection.</span></span>  
  
 <span data-ttu-id="9fe6c-131">Удалить коллекцию схем можно с помощью инструкции DROP XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-131">To drop the schema collection, use the DROP XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="9fe6c-132">При этом удаляются все схемы в коллекции и сам объект коллекции.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-132">This drops all schemas that are contained in the collection and removes the collection object.</span></span> <span data-ttu-id="9fe6c-133">Обратите внимание, что для удаления коллекции схем должны выполняться условия, описанные в разделе [DROP XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9fe6c-133">Note that before you can drop a schema collection, the conditions described in [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql)must be met.</span></span>  
  
##  <a name="understanding-schema-components"></a><a name="components"></a> <span data-ttu-id="9fe6c-134">Основные сведения о компонентах схемы</span><span class="sxs-lookup"><span data-stu-id="9fe6c-134">Understanding Schema Components</span></span>  
 <span data-ttu-id="9fe6c-135">При использовании инструкции CREATE XML SCHEMA COLLECTION в базу данных импортируются различные компоненты схемы.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-135">When you use the CREATE XML SCHEMA COLLECTION statement, various schema components are imported into the database.</span></span> <span data-ttu-id="9fe6c-136">К компонентам схемы относятся ее элементы, атрибуты и определения типов.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-136">Schema components include schema elements, attributes, and type definitions.</span></span> <span data-ttu-id="9fe6c-137">При использовании инструкции DROP XML SCHEMA COLLECTION коллекция удаляется целиком.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-137">When you use the DROP XML SCHEMA COLLECTION statement, you remove the complete collection.</span></span>  
  
 <span data-ttu-id="9fe6c-138">Инструкция CREATE XML SCHEMA COLLECTION сохраняет компоненты схемы в различных системных таблицах.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-138">CREATE XML SCHEMA COLLECTION saves the schema components into various system tables.</span></span>  
  
 <span data-ttu-id="9fe6c-139">Например, рассмотрим следующую схему:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-139">For example, consider the following schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            targetNamespace="uri:Cust_Orders2"  
            xmlns="uri:Cust_Orders2" >  
  <xsd:attribute name="SomeAttribute" type="xsd:int" />  
  <xsd:complexType name="SomeType" />  
  <xsd:complexType name="OrderType" >  
    <xsd:sequence>  
      <xsd:element name="OrderDate" type="xsd:date" />  
      <xsd:element name="RequiredDate" type="xsd:date" />  
      <xsd:element name="ShippedDate" type="xsd:date" />  
    </xsd:sequence>  
    <xsd:attribute name="OrderID" type="xsd:ID" />  
    <xsd:attribute name="CustomerID"  />  
    <xsd:attribute name="EmployeeID"  />  
  </xsd:complexType>  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order" type="OrderType"  
                     maxOccurs="unbounded" />  
       </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
      <xsd:attribute name="OrderIDList" type="xsd:IDREFS" />  
  </xsd:complexType>  
  <xsd:element name="Customer" type="CustomerType" />  
</xsd:schema>  
```  
  
 <span data-ttu-id="9fe6c-140">В приведенной выше схеме показаны различные типы компонентов, которые могут храниться в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-140">The previous schema shows the different types of components that can be stored in the database.</span></span> <span data-ttu-id="9fe6c-141">Это компоненты `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`и `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-141">These include `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`, and `ShippedDate`.</span></span>  
  
### <a name="component-categories"></a><span data-ttu-id="9fe6c-142">Категории компонентов</span><span class="sxs-lookup"><span data-stu-id="9fe6c-142">Component Categories</span></span>  
 <span data-ttu-id="9fe6c-143">Компоненты схемы, хранящиеся в базе данных, делятся на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-143">The Schema components stored in the database fall into the following categories:</span></span>  
  
-   <span data-ttu-id="9fe6c-144">ELEMENT</span><span class="sxs-lookup"><span data-stu-id="9fe6c-144">ELEMENT</span></span>  
  
-   <span data-ttu-id="9fe6c-145">ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="9fe6c-145">ATTRIBUTE</span></span>  
  
-   <span data-ttu-id="9fe6c-146">TYPE (для простых и сложных типов);</span><span class="sxs-lookup"><span data-stu-id="9fe6c-146">TYPE (for simple or complex types)</span></span>  
  
-   <span data-ttu-id="9fe6c-147">ATTRIBUTEGROUP;</span><span class="sxs-lookup"><span data-stu-id="9fe6c-147">ATTRIBUTEGROUP</span></span>  
  
-   <span data-ttu-id="9fe6c-148">MODELGROUP.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-148">MODELGROUP</span></span>  
  
 <span data-ttu-id="9fe6c-149">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-149">For example:</span></span>  
  
-   <span data-ttu-id="9fe6c-150">**SomeAttribute** является компонентом ATTRIBUTE.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-150">**SomeAttribute** is an ATTRIBUTE component.</span></span>  
  
-   <span data-ttu-id="9fe6c-151">**SomeType**, **OrderType**и **CustomerType** — это компоненты TYPE.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-151">**SomeType**, **OrderType**, and **CustomerType** are TYPE components.</span></span>  
  
-   <span data-ttu-id="9fe6c-152">**Customer** является компонентом ELEMENT.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-152">**Customer** is an ELEMENT component.</span></span>  
  
 <span data-ttu-id="9fe6c-153">При импорте схемы в базу данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не сохраняет саму схему.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-153">When you import a schema into the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not store the schema itself.</span></span> <span data-ttu-id="9fe6c-154">Вместо этого [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сохраняет различные отдельные компоненты.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-154">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stores the various individual components.</span></span> <span data-ttu-id="9fe6c-155">Таким образом, тег \<Schema> не сохраняется, а сохраняются только компоненты, заданные внутри него.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-155">That is, the \<Schema> tag is not stored, only the components that are defined within it are preserved.</span></span> <span data-ttu-id="9fe6c-156">Все элементы схемы не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-156">All schema elements are not preserved.</span></span> <span data-ttu-id="9fe6c-157">Если тег \<Schema> содержит атрибуты, которые задают поведение по умолчанию для его компонентов, то во время импорта эти атрибуты перемещаются в компоненты схемы внутри нее, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-157">If the \<Schema> tag contains attributes that specify default behavior of its components, these attributes are moved to the schema components within it during the import process, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9fe6c-158">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="9fe6c-158">Attribute name</span></span>|<span data-ttu-id="9fe6c-159">Поведение</span><span class="sxs-lookup"><span data-stu-id="9fe6c-159">Behavior</span></span>|  
|--------------------|--------------|  
|<span data-ttu-id="9fe6c-160">**attributeFormDefault**</span><span class="sxs-lookup"><span data-stu-id="9fe6c-160">**attributeFormDefault**</span></span>|<span data-ttu-id="9fe6c-161">Атрибут **form** применяется ко всем объявлениям атрибутов в схеме, где его еще нет. Ему присваивается значение, равное значению атрибута **attributeFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="9fe6c-161">The **form** attribute applied to all attribute declarations in the schema where it is not already present and the value is set to the value of the **attributeFormDefault** attribute.</span></span>|  
|<span data-ttu-id="9fe6c-162">**elementFormDefault**</span><span class="sxs-lookup"><span data-stu-id="9fe6c-162">**elementFormDefault**</span></span>|<span data-ttu-id="9fe6c-163">Атрибут **form** применяется ко всем объявлениям элементов в схеме, где его еще нет. Ему присваивается значение, равное значению атрибута **elementFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="9fe6c-163">The **form** attribute applied to all element declarations in the schema where it is not already present and the value is set to the value of the **elementFormDefault** attribute.</span></span>|  
|<span data-ttu-id="9fe6c-164">**blockDefault**</span><span class="sxs-lookup"><span data-stu-id="9fe6c-164">**blockDefault**</span></span>|<span data-ttu-id="9fe6c-165">Атрибут **block** применяется ко всем объявлениям элементов и определениям типов в схеме, где его еще нет. Ему присваивается значение, равное значению атрибута **blockDefault** .</span><span class="sxs-lookup"><span data-stu-id="9fe6c-165">The **block** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **blockDefault** attribute.</span></span>|  
|<span data-ttu-id="9fe6c-166">**finalDefault**</span><span class="sxs-lookup"><span data-stu-id="9fe6c-166">**finalDefault**</span></span>|<span data-ttu-id="9fe6c-167">Атрибут **final** применяется ко всем объявлениям элементов и определениям типов в схеме, где его еще нет. Ему присваивается значение, равное значению атрибута **finalDefault** .</span><span class="sxs-lookup"><span data-stu-id="9fe6c-167">The **final** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **finalDefault** attribute.</span></span>|  
|<span data-ttu-id="9fe6c-168">**targetNamespace**</span><span class="sxs-lookup"><span data-stu-id="9fe6c-168">**targetNamespace**</span></span>|<span data-ttu-id="9fe6c-169">Сведения о компонентах, принадлежащих целевому пространству имен, хранятся в метаданных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-169">Information about the components that belong to the target namespace is stored in the metadata.</span></span>|  
  
##  <a name="permissions-on-an-xml-schema-collection"></a><a name="perms"></a> <span data-ttu-id="9fe6c-170">Разрешения на коллекцию схем XML</span><span class="sxs-lookup"><span data-stu-id="9fe6c-170">Permissions on an XML Schema Collection</span></span>  
 <span data-ttu-id="9fe6c-171">При этом требуется иметь соответствующие разрешения на выполнение следующих операций:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-171">You must have the necessary permissions to do the following:</span></span>  
  
-   <span data-ttu-id="9fe6c-172">создание и загрузка коллекции XML-схем;</span><span class="sxs-lookup"><span data-stu-id="9fe6c-172">Create/load the XML schema collection</span></span>  
  
-   <span data-ttu-id="9fe6c-173">модификация коллекции XML-схем;</span><span class="sxs-lookup"><span data-stu-id="9fe6c-173">Modify the XML schema collection</span></span>  
  
-   <span data-ttu-id="9fe6c-174">удаление коллекции XML-схем;</span><span class="sxs-lookup"><span data-stu-id="9fe6c-174">Drop the XML schema collection</span></span>  
  
-   <span data-ttu-id="9fe6c-175">Коллекция XML-схем используется для типа `xml` столбцов, переменных и параметров, а также для использования в ограничениях таблиц и столбцов.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-175">Use the XML schema collection to type `xml` type columns, variables, and parameters, or use it in table or column constraints</span></span>  
  
 <span data-ttu-id="9fe6c-176">Модель безопасности SQL Server предусматривает разрешение CONTROL для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-176">The SQL Server security model allows CONTROL permission on every object.</span></span> <span data-ttu-id="9fe6c-177">Обладателю этого разрешения предоставляются все остальные разрешения для данного объекта.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-177">The grantee of this permission obtains all other permissions on the object.</span></span> <span data-ttu-id="9fe6c-178">Владелец объекта также имеет все разрешения для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-178">The owner of the object also has all the permissions on the object.</span></span>  
  
 <span data-ttu-id="9fe6c-179">Владелец и обладатель разрешения CONTROL для объекта могут давать любые разрешения на этот объект.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-179">The owner and the grantee of the CONTROL permission on an object can grant any permission on the object.</span></span> <span data-ttu-id="9fe6c-180">Пользователь, не являющийся владельцем и не имеющий разрешения CONTROL, может давать разрешения на объект при использовании параметра WITH GRANT OPTION.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-180">A user who is not the owner and does not have CONTROL permission can still grant permission on an object when WITH GRANT OPTION is specified.</span></span> <span data-ttu-id="9fe6c-181">Допустим, что пользователь A имеет предоставленное с помощью настройки WITH GRANT OPTION разрешение REFERENCES на коллекцию XML-схем S, но не имеет других разрешений на коллекцию S. В этом случае пользователь A может предоставить пользователю Б разрешение REFERENCES на коллекцию схем S.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-181">For example, assume User A has REFERENCES permission on XML schema collection S, through WITH GRANT OPTION, but no other permissions on S. User A could grant User B REFERENCES permission on schema collection S.</span></span>  
  
 <span data-ttu-id="9fe6c-182">Кроме того, модель безопасности допускает создание и использование разрешениями коллекций XML-схем или передачу данных о принадлежности от одного пользователя другому.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-182">The security model also allows permissions to create and use XML schema collections or transfer ownership from one user to another.</span></span> <span data-ttu-id="9fe6c-183">Разрешения на коллекции XML-схем описываются в следующих подразделах.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-183">The following topics describe the XML schema collection permissions.</span></span>  
  
-   [<span data-ttu-id="9fe6c-184">Предоставление разрешений на коллекции схем XML</span><span class="sxs-lookup"><span data-stu-id="9fe6c-184">Grant Permissions on an XML Schema Collection</span></span>](../xml/grant-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="9fe6c-185">В этом подразделе речь идет о том, каким образом предоставляются разрешения на создание коллекции XML-схем и разрешения на объекты коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-185">This topic discussess how to grant permissions to create an XML schema collection and how to grant permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="9fe6c-186">Отмена разрешений на коллекцию схем XML</span><span class="sxs-lookup"><span data-stu-id="9fe6c-186">Revoke Permissions on an XML Schema Collection</span></span>](../xml/revoke-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="9fe6c-187">В этом подразделе речь идет о том, каким образом можно использовать отмену разрешений для предотвращения создания коллекции XML-схем и как отменять разрешения на объекты коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-187">This topic discusses how revoking permissions can be used to prevent the creation of an XML schema collection and how to revoke permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="9fe6c-188">Запрет разрешения на коллекцию схем XML</span><span class="sxs-lookup"><span data-stu-id="9fe6c-188">Deny Permissions on an XML Schema Collection</span></span>](../xml/deny-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="9fe6c-189">В этом подразделе речь идет о том, каким образом запрещаются разрешения на создание коллекции XML-схем и разрешения на объекты коллекции схем XML.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-189">This topic discusses how to deny permissions to create an XML schema collection and deny permission on an XML schema collection object.</span></span>  
  
##  <a name="getting-information-about-xml-schemas-and-schema-collections"></a><a name="info"></a> <span data-ttu-id="9fe6c-190">Получение информации о схемах XML и коллекциях схем</span><span class="sxs-lookup"><span data-stu-id="9fe6c-190">Getting Information about XML Schemas and Schema Collections</span></span>  
 <span data-ttu-id="9fe6c-191">Коллекции XML-схем перечислены в представлении каталога sys.xml_schema_collections.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-191">XML schema collections are enumerated in the catalog view, sys.xml_schema_collections.</span></span> <span data-ttu-id="9fe6c-192">Коллекция XML-схем «sys» определяется системой.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-192">The XML schema collection "sys" is defined by the system.</span></span> <span data-ttu-id="9fe6c-193">Она содержит предопределенные пространства имен, которые можно использовать во всех пользовательских коллекциях XML-схем, не загружая их явно.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-193">It contains the predefined namespaces that can be used in all user-defined XML schema collections without having to load them explicitly.</span></span> <span data-ttu-id="9fe6c-194">Этот список содержит пространства имен xml, xs, xsi, fn и xdt.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-194">This list contains the namespaces for xml, xs, xsi, fn, and xdt.</span></span> <span data-ttu-id="9fe6c-195">Двумя другими представлениями каталога являются sys.xml_schema_namespaces, в котором перечислены все пространства имен каждой коллекции XML-схем и sys.xml_components, в котором перечислены все компоненты каждой XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-195">Two other catalog views are sys.xml_schema_namespaces, which enumerates all namespaces within each XML schema collection, and sys.xml_components, which enumerates all XML schema components within each XML schema.</span></span>  
  
 <span data-ttu-id="9fe6c-196">Встроенная функция **xml_schema_namespace**, *schemaName, XmlSchemacollectionName, Namespace-URI*, возвращает `xml` экземпляр типа данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-196">The built-in function **XML_SCHEMA_NAMESPACE**, *schemaName, XmlSchemacollectionName, namespace-uri*, yields an `xml` data type instance..</span></span> <span data-ttu-id="9fe6c-197">Этот экземпляр содержит фрагменты для XML-схем, содержащихся в коллекции XML-схем, за исключением предопределенных XML-схем.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-197">This instance contains XML schema fragments for schemas that are contained in an XML schema collection, except the predefined XML schemas.</span></span>  
  
 <span data-ttu-id="9fe6c-198">Перечислить содержимое коллекции XML-схем можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-198">You can enumerate the contents of an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="9fe6c-199">написать запросы Transact-SQL, адресованные соответствующим представлениям каталога, связанным с коллекциями XML-схем;</span><span class="sxs-lookup"><span data-stu-id="9fe6c-199">Write Transact-SQL queries on the appropriate catalog views for XML schema collections.</span></span>  
  
-   <span data-ttu-id="9fe6c-200">Используйте встроенную функцию **XML_SCHEMA_NAMESPACE()** .</span><span class="sxs-lookup"><span data-stu-id="9fe6c-200">Use the built-in function **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="9fe6c-201">К `xml` выходным данным этой функции можно применить методы типа данных.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-201">You can apply `xml` data type methods on the output of this function.</span></span> <span data-ttu-id="9fe6c-202">Однако изменять базовые XML-схемы нельзя.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-202">However, you cannot modify the underlying XML schemas.</span></span>  
  
 <span data-ttu-id="9fe6c-203">Все это поясняют следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-203">These are illustrated in the following examples.</span></span>  
  
### <a name="example-enumerate-the-xml-namespaces-in-an-xml-schema-collection"></a><span data-ttu-id="9fe6c-204">Пример Перечисление пространств имен XML, входящих в коллекцию XML-схем</span><span class="sxs-lookup"><span data-stu-id="9fe6c-204">Example: Enumerate the XML Namespaces in an XML Schema Collection</span></span>  
 <span data-ttu-id="9fe6c-205">Выполните следующий запрос для коллекции XML-схем «myCollection»:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-205">Use the following query for the XML schema collection "myCollection":</span></span>  
  
```  
SELECT XSN.name  
FROM    sys.xml_schema_collections XSC JOIN sys.xml_schema_namespaces XSN  
    ON (XSC.xml_collection_id = XSN.xml_collection_id)  
WHERE    XSC.name = 'myCollection'     
```  
  
### <a name="example-enumerate-the-contents-of-an-xml-schema-collection"></a><span data-ttu-id="9fe6c-206">Пример Перечисление содержимого коллекции XML-схем</span><span class="sxs-lookup"><span data-stu-id="9fe6c-206">Example: Enumerate the Contents of an XML Schema Collection</span></span>  
 <span data-ttu-id="9fe6c-207">Следующая инструкция перебирает содержимое коллекции XML-схем «myCollection» реляционной схемы dbo.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-207">The following statement enumerates the contents of the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection')  
```  
  
 <span data-ttu-id="9fe6c-208">Отдельные XML-схемы в коллекции можно получить в виде `xml` экземпляров типа данных, указав целевое пространство имен в качестве третьего аргумента для **xml_schema_namespace ()**.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-208">Individual XML schemas within the collection can be obtained as `xml` data type instances by specifying the target namespace as the third argument to **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="9fe6c-209">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-209">This is shown in the following example.</span></span>  
  
### <a name="example-output-a-specified-schema-from-an-xml-schema-collection"></a><span data-ttu-id="9fe6c-210">Пример Вывод конкретной схемы из коллекции XML-схем</span><span class="sxs-lookup"><span data-stu-id="9fe6c-210">Example: Output a Specified Schema from an XML Schema Collection</span></span>  
 <span data-ttu-id="9fe6c-211">Следующая инструкция выводит XML-схему с целевым пространством имен "<https://www.microsoft.com/books>" из коллекции XML-схем "myCollection" реляционной схемы dbo.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-211">The following statement outputs the XML schema with the target namespace "<https://www.microsoft.com/books>" from the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection',   
N'https://www.microsoft.com/books')  
```  
  
### <a name="querying-xml-schemas"></a><span data-ttu-id="9fe6c-212">Запросы XML-схем</span><span class="sxs-lookup"><span data-stu-id="9fe6c-212">Querying XML Schemas</span></span>  
 <span data-ttu-id="9fe6c-213">Запрашивать XML-схемы, загруженные в коллекцию XML-схем, можно перечисленными ниже способами.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-213">You can query XML schemas that you have loaded into XML schema collections in the following ways:</span></span>  
  
-   <span data-ttu-id="9fe6c-214">Написать адресованные представлениям каталога запросы Transact-SQL о получении пространств имен XML-схем.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-214">Write Transact-SQL queries on catalog views for XML schema namespaces.</span></span>  
  
-   <span data-ttu-id="9fe6c-215">Создать таблицу со столбцом данных типа `xml` для хранения XML-схем и их загрузки в систему типов XML.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-215">Create a table that contains an `xml` data type column to store your XML schemas and also load them into the XML type system.</span></span> <span data-ttu-id="9fe6c-216">Данные из XML-столбца можно запросить при помощи методов типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-216">You can query the XML column by using the `xml` data type methods.</span></span> <span data-ttu-id="9fe6c-217">Кроме того, можно создать для этого столбца XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-217">Also, you can build an XML index on this column.</span></span> <span data-ttu-id="9fe6c-218">Однако при этом подходе в приложении нужно поддерживать согласованность между XML-схемами, хранимыми в XML-столбце, и системой типов XML.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-218">However, with this approach, the application must maintain consistency between the XML schemas stored in the XML column and the XML type system.</span></span> <span data-ttu-id="9fe6c-219">Например, при удалении пространства имен XML-схемы из системы типов XML для сохранения согласованности необходимо будет удалить его и из таблицы.</span><span class="sxs-lookup"><span data-stu-id="9fe6c-219">For example, if you drop the XML schema namespace from the XML type system, you also have to drop it from the table in order to preserve consistency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe6c-220">См. также:</span><span class="sxs-lookup"><span data-stu-id="9fe6c-220">See Also</span></span>  
 <span data-ttu-id="9fe6c-221">[Просмотр хранимой коллекции схем XML](../xml/view-a-stored-xml-schema-collection.md) </span><span class="sxs-lookup"><span data-stu-id="9fe6c-221">[View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md) </span></span>  
 <span data-ttu-id="9fe6c-222">[Предпроцессор схемы для слияния включаемых схем](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="9fe6c-222">[Preprocess a Schema to Merge Included Schemas](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span></span>  
 [<span data-ttu-id="9fe6c-223">Требования и ограничения для коллекций схем XML на сервере</span><span class="sxs-lookup"><span data-stu-id="9fe6c-223">Requirements and Limitations for XML Schema Collections on the Server</span></span>](../xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
