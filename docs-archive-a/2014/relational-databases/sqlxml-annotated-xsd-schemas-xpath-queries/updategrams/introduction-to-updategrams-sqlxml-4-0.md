---
title: Введение в диаграмм обновления (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- updategrams [SQLXML], mapping schema specifying
- namespaces [SQLXML]
- updategrams [SQLXML], about updategrams
- attribute-centric mapping
- invalid characters [SQLXML]
- element-centric mapping [SQLXML]
- mapping schema [SQLXML], updategrams
- namespaces [SQLXML], updategrams
- executing updategrams [SQLXML]
- implicit schema mapping
ms.assetid: cfe24e82-a645-4f93-ab16-39c21f90cce6
author: rothja
ms.author: jroth
ms.openlocfilehash: eb2f29d7f5d86d28254dacb9c55cceb9b4c72d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732446"
---
# <a name="introduction-to-updategrams-sqlxml-40"></a><span data-ttu-id="4cdb2-102">Общие сведения о диаграммах обновления (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4cdb2-102">Introduction to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="4cdb2-103">Можно изменить (вставить, обновить или удалить) базу данных [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из существующего XML-документа с помощью функции диаграмма обновления или OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cdb2-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="4cdb2-104">Функция OPENXML изменяет базу данных, разделяя существующий XML-документ и формируя набор строк, который можно передавать инструкциям INSERT, UPDATE и DELETE.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-104">The OPENXML function modifies a database by shredding the existing XML document and providing a rowset that can be passed to an INSERT, UPDATE, or DELETE statement.</span></span> <span data-ttu-id="4cdb2-105">С помощью функции OPENXML операции выполняются непосредственно с таблицами базы данных.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-105">With OPENXML, operations are performed directly against the database tables.</span></span> <span data-ttu-id="4cdb2-106">Поэтому использование функции OPENXML является наиболее оптимальным вариантом во всех случаях, когда поставщики наборов строк, например таблицы, могут быть источниками.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-106">Therefore, OPENXML is most appropriate wherever rowset providers, such as a table, can appear as a source.</span></span>  
  
 <span data-ttu-id="4cdb2-107">Диаграммы обновления, подобно функции OPENXML, позволяют вставлять, обновлять и удалять данные в базе данных. Однако диаграммы обновления работают не с таблицами, а с XML-представлениями, создаваемыми аннотированной XSD-схемой (или XDR-схемой); например, обновления применяются к XML-представлению, созданному сопоставляемой схемой.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-107">Like OPENXML, an updategram allows you to insert, update, or delete data in the database; however, an updategram works against the XML views provided by the annotated XSD (or an XDR) schema; for example, the updates are applied to the XML view provided by the mapping schema.</span></span> <span data-ttu-id="4cdb2-108">Схема сопоставления в свою очередь содержит данные, необходимые для сопоставления XML-элементов и атрибутов с соответствующими таблицами и столбцами базы данных.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-108">The mapping schema, in turn, has the necessary information to map XML elements and attributes to the corresponding database tables and columns.</span></span> <span data-ttu-id="4cdb2-109">Диаграмма обновления использует эти данные сопоставления, чтобы выполнить обновление таблиц и столбцов базы данных.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-109">The updategram uses this mapping information to update the database tables and columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4cdb2-110">Настоящая документация предназначена для тех, кто знаком с шаблонами и поддержкой схем сопоставления в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cdb2-110">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4cdb2-111">Дополнительные сведения см. [в разделе Введение в схемы XSD с Заметками &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4cdb2-111">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="4cdb2-112">Дополнительные сведения о устаревших приложениях, использующих XDR, см. [в разделе схемы XDR с Заметками &#40;не рекомендуется в SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4cdb2-112">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="required-namespaces-in-the-updategram"></a><span data-ttu-id="4cdb2-113">Обязательные пространства имен в диаграмме обновления</span><span class="sxs-lookup"><span data-stu-id="4cdb2-113">Required Namespaces in the Updategram</span></span>  
 <span data-ttu-id="4cdb2-114">Ключевые слова в диаграмма обновления, такие как **\<sync>** , **\<before>** и **\<after>** , существуют в `urn:schemas-microsoft-com:xml-updategram` пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-114">The keywords in an updategram, such as **\<sync>**, **\<before>**, and **\<after>**, exist in the `urn:schemas-microsoft-com:xml-updategram` namespace.</span></span> <span data-ttu-id="4cdb2-115">Префикс пространства имен может быть произвольным.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-115">The namespace prefix that you use is arbitrary.</span></span> <span data-ttu-id="4cdb2-116">В этой документации префикс `updg` обозначает пространство имен `updategram`.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-116">In this documentation, the `updg` prefix denotes the `updategram` namespace.</span></span>  
  
## <a name="reviewing-syntax"></a><span data-ttu-id="4cdb2-117">Обзор синтаксиса</span><span class="sxs-lookup"><span data-stu-id="4cdb2-117">Reviewing Syntax</span></span>  
 <span data-ttu-id="4cdb2-118">Диаграмма обновления — это шаблон с **\<sync>** **\<before>** блоками, и **\<after>** , которые формируют синтаксис диаграмма обновления.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-118">An updategram is a template with **\<sync>**, **\<before>**, and **\<after>** blocks that form the syntax of the updategram.</span></span> <span data-ttu-id="4cdb2-119">Следующий код показывает этот синтаксис в его простейшей форме:</span><span class="sxs-lookup"><span data-stu-id="4cdb2-119">The following code shows this syntax in its simplest form:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema= "AnnotatedSchemaFile.xml"] >  
    <updg:before>  
        ...  
    </updg:before>  
    <updg:after>  
        ...  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4cdb2-120">Следующие определения описывают роль каждого блока.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-120">The following definitions describe the role of each of these blocks:</span></span>  
  
 **\<before>**  
 <span data-ttu-id="4cdb2-121">Определяет текущее состояние (называемое также «исходным состоянием») экземпляра записи.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-121">Identifies the existing state (also called "the before state") of the record instance.</span></span>  
  
 **\<after>**  
 <span data-ttu-id="4cdb2-122">Определяет новое состояние изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-122">Identifies the new state to which data is to be changed.</span></span>  
  
 **\<sync>**  
 <span data-ttu-id="4cdb2-123">Содержит **\<before>** блоки и **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="4cdb2-123">Contains the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="4cdb2-124">**\<sync>** Блок может содержать более одного набора **\<before>** **\<after>** блоков и.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-124">A **\<sync>** block can contain more than one set of **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="4cdb2-125">Если имеется более одного набора **\<before>** **\<after>** блоков и, эти блоки (даже если они пусты) должны быть указаны парами.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-125">If there is more than one set of **\<before>** and **\<after>** blocks, these blocks (even if they are empty) must be specified as pairs.</span></span> <span data-ttu-id="4cdb2-126">Более того, диаграмма обновления может иметь более одного **\<sync>** блока.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-126">Furthermore, an updategram can have more than one **\<sync>** block.</span></span> <span data-ttu-id="4cdb2-127">Каждый **\<sync>** блок является одной единицей транзакции (что означает, что все в **\<sync>** блоке выполняется или ничего не происходит).</span><span class="sxs-lookup"><span data-stu-id="4cdb2-127">Each **\<sync>** block is one unit of transaction (which means that either everything in the **\<sync>** block is done or nothing is done).</span></span> <span data-ttu-id="4cdb2-128">При указании нескольких **\<sync>** блоков в диаграмма обновления сбой одного **\<sync>** блока не влияет на другие **\<sync>** блоки.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-128">If you specify multiple **\<sync>** blocks in an updategram, the failure of one **\<sync>** block does not affect the other **\<sync>** blocks.</span></span>  
  
 <span data-ttu-id="4cdb2-129">Будет ли диаграмма обновления удалять, вставлять или обновлять экземпляр записи, зависит от содержимого **\<before>** **\<after>** блоков и:</span><span class="sxs-lookup"><span data-stu-id="4cdb2-129">Whether an updategram deletes, inserts, or updates a record instance depends on the contents of the **\<before>** and **\<after>** blocks:</span></span>  
  
-   <span data-ttu-id="4cdb2-130">Если экземпляр записи отображается только в **\<before>** блоке без соответствующего экземпляра в **\<after>** блоке, диаграмма обновления выполняет операцию удаления.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-130">If a record instance appears only in the **\<before>** block with no corresponding instance in the **\<after>** block, the updategram performs a delete operation.</span></span>  
  
-   <span data-ttu-id="4cdb2-131">Если экземпляр записи отображается только в **\<after>** блоке без соответствующего экземпляра в **\<before>** блоке, это операция вставки.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-131">If a record instance appears only in the **\<after>** block with no corresponding instance in the **\<before>** block, it is an insert operation.</span></span>  
  
-   <span data-ttu-id="4cdb2-132">Если экземпляр записи присутствует в **\<before>** блоке и имеет соответствующий экземпляр в **\<after>** блоке, это операция обновления.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-132">If a record instance appears in the **\<before>** block and has a corresponding instance in the **\<after>** block, it is an update operation.</span></span> <span data-ttu-id="4cdb2-133">В этом случае диаграмма обновления обновляет экземпляр записи на значения, указанные в **\<after>** блоке.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-133">In this case, the updategram updates the record instance to the values that are specified in the **\<after>** block.</span></span>  
  
## <a name="specifying-a-mapping-schema-in-the-updategram"></a><span data-ttu-id="4cdb2-134">Указание сопоставления схемы в диаграмме обновления</span><span class="sxs-lookup"><span data-stu-id="4cdb2-134">Specifying a Mapping Schema in the Updategram</span></span>  
 <span data-ttu-id="4cdb2-135">В диаграмме обновления XML-абстракция, созданная сопоставляемой схемой (поддерживаются схемы XSD и XDR), может быть явной или неявной (то есть диаграмма обновления может работать как с заданной схемой сопоставления, так и без нее).</span><span class="sxs-lookup"><span data-stu-id="4cdb2-135">In an updategram, the XML abstraction that is provided by a mapping schema (both XSD and XDR schemas are supported) can be implicit or explicit (that is, an updategram can work with or without a specified mapping schema).</span></span> <span data-ttu-id="4cdb2-136">Если схема сопоставления не указана, диаграмма обновления предполагает неявное сопоставление (сопоставление по умолчанию), где каждый элемент в **\<before>** блоке или **\<after>** сопоставляется с таблицей, а дочерний элемент или атрибут каждого элемента сопоставляется со столбцом в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-136">If you do not specify a mapping schema, the updategram assumes an implicit mapping (the default mapping), where each element in the **\<before>** block or **\<after>** block maps to a table and each element's child element or attribute maps to a column in the database.</span></span> <span data-ttu-id="4cdb2-137">Если схема сопоставления указана явно, то элементы и атрибуты в диаграмме обновления должны совпадать с элементами и атрибутами сопоставляемой схемы.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-137">If you explicitly specify a mapping schema, the elements and attributes in the updategram must match the elements and attributes in the mapping schema.</span></span>  
  
### <a name="implicit-default-mapping"></a><span data-ttu-id="4cdb2-138">Неявное сопоставление (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4cdb2-138">Implicit (default) Mapping</span></span>  
 <span data-ttu-id="4cdb2-139">В большинстве случаев диаграмма обновления, выполняющая простые обновления, не требует схемы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-139">In most cases, an updategram that performs simple updates might not require a mapping schema.</span></span> <span data-ttu-id="4cdb2-140">В такой ситуации диаграмма обновления полагается на схему сопоставления, принятую по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-140">In this case, the updategram relies on the default mapping schema.</span></span>  
  
 <span data-ttu-id="4cdb2-141">В следующей диаграмме обновления показано неявное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-141">The following updategram demonstrates implicit mapping.</span></span> <span data-ttu-id="4cdb2-142">В этом примере диаграмма обновления применяется для вставки данных нового клиента в таблицу Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-142">In this example, the updategram inserts a new customer in the Sales.Customer table.</span></span> <span data-ttu-id="4cdb2-143">Так как в этом диаграмма обновления используется неявное сопоставление, \<Sales.Customer> элемент сопоставляется с таблицей Sales. Customer, а атрибуты CustomerID и SalesPersonID сопоставляются с соответствующими столбцами в таблице Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-143">Because this updategram uses implicit mapping, the \<Sales.Customer> element maps to the Sales.Customer table, and the CustomerID and SalesPersonID attributes map to the corresponding columns in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
</updg:before>  
<updg:after>  
    <Sales.Customer CustomerID="1" SalesPersonID="277" />  
    </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="explicit-mapping"></a><span data-ttu-id="4cdb2-144">Явное сопоставление</span><span class="sxs-lookup"><span data-stu-id="4cdb2-144">Explicit Mapping</span></span>  
 <span data-ttu-id="4cdb2-145">Если указывается схема сопоставления (XSD или XDR), диаграмма обновления использует эту схему для определения подлежащих обновлению таблиц и столбцов базы данных.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-145">If you specify a mapping schema (either XSD or XDR), the updategram uses the schema to determine the database tables and columns that are to be updated.</span></span>  
  
 <span data-ttu-id="4cdb2-146">Если диаграмма обновления выполняет сложное обновление (например, вставку записей в несколько таблиц на основе связи «родители-потомки», заданной в схеме сопоставления), необходимо явно задать схему сопоставления с помощью атрибута `mapping-schema`, по которому выполняется диаграмма обновления.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-146">If the updategram performs a complex update (for example, inserting records in multiple tables on the basis of the parent-child relationship that is specified in the mapping schema), you must explicitly provide the mapping schema by using the `mapping-schema` attribute against which the updategram executes.</span></span>  
  
 <span data-ttu-id="4cdb2-147">Диаграмма обновления является шаблоном, поэтому заданный в ней путь для схемы сопоставления зависит от расположения файла шаблона (является относительным).</span><span class="sxs-lookup"><span data-stu-id="4cdb2-147">Because an updategram is a template, the path specified for the mapping schema in the updategram is relative to the location of the template file (relative to where the updategram is stored).</span></span> <span data-ttu-id="4cdb2-148">Дополнительные сведения см. [в разделе Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4cdb2-148">For more information, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="element-centric-and-attribute-centric-mapping-in-updategrams"></a><span data-ttu-id="4cdb2-149">Элементная и атрибутивная модель сопоставления в диаграммах обновления</span><span class="sxs-lookup"><span data-stu-id="4cdb2-149">Element-centric and Attribute-centric Mapping in Updategrams</span></span>  
 <span data-ttu-id="4cdb2-150">При сопоставлении по умолчанию (когда сопоставляемая схема не указывается в диаграмме обновления), элементы диаграммы обновления сопоставляются с таблицами и дочерними элементами (в случае элементной модели сопоставления), а атрибуты сопоставляются со столбцами (в случае атрибутивной модели сопоставления).</span><span class="sxs-lookup"><span data-stu-id="4cdb2-150">With default mapping (when the mapping schema is not specified in the updategram), the updategram elements map to tables and the  child elements (in the case of element-centric mapping) and the attributes (in the case of attribute-centric mapping) map to columns.</span></span>  
  
### <a name="element-centric-mapping"></a><span data-ttu-id="4cdb2-151">Сопоставление, ориентированное на элементы</span><span class="sxs-lookup"><span data-stu-id="4cdb2-151">Element-centric Mapping</span></span>  
 <span data-ttu-id="4cdb2-152">В диаграмме обновления, основанной на элементах, элемент содержит дочерние элементы, обозначающие свойства этого элемента.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-152">In an element-centric updategram, an element contains child elements that denote the properties of the element.</span></span> <span data-ttu-id="4cdb2-153">В качестве примера см. следующую диаграмму обновления.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-153">As an example, refer to the following updategram.</span></span> <span data-ttu-id="4cdb2-154">**\<Person.Contact>** Элемент содержит **\<FirstName>** **\<LastName>** дочерние элементы и.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-154">The **\<Person.Contact>** element contains the **\<FirstName>** and **\<LastName>** child elements.</span></span> <span data-ttu-id="4cdb2-155">Эти дочерние элементы являются свойствами **\<Person.Contact>** элемента.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-155">These child elements are properties of the **\<Person.Contact>** element.</span></span>  
  
 <span data-ttu-id="4cdb2-156">Так как в этом диаграмма обновления не указана схема сопоставления, диаграмма обновления использует неявное сопоставление, где **\<Person.Contact>** элемент сопоставляется с таблицей Person. Contact и ее дочерними элементами сопоставляются со столбцами FirstName и LastName.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-156">Because this updategram does not specify a mapping schema, the updategram uses implicit mapping, where the **\<Person.Contact>** element maps to the Person.Contact table and its child elements map to the FirstName and LastName columns.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:after>  
    <Person.Contact>  
       <FirstName>Catherine</FirstName>  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="attribute-centric-mapping"></a><span data-ttu-id="4cdb2-157">атрибутивное сопоставление</span><span class="sxs-lookup"><span data-stu-id="4cdb2-157">Attribute-centric Mapping</span></span>  
 <span data-ttu-id="4cdb2-158">В атрибутивной модели сопоставления элементы имеют атрибуты.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-158">In an attribute-centric mapping, the elements have attributes.</span></span> <span data-ttu-id="4cdb2-159">В следующей диаграмме обновления используется атрибутивная модель сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-159">The following updategram uses attribute-centric mapping.</span></span> <span data-ttu-id="4cdb2-160">В этом примере **\<Person.Contact>** элемент состоит из атрибутов **FirstName** и **LastName** .</span><span class="sxs-lookup"><span data-stu-id="4cdb2-160">In this example, the **\<Person.Contact>** element consists of the **FirstName** and **LastName** attributes.</span></span> <span data-ttu-id="4cdb2-161">Эти атрибуты являются свойствами **\<Person.Contact>** элемента.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-161">These attributes are the properties of the **\<Person.Contact>** element.</span></span> <span data-ttu-id="4cdb2-162">Как и в предыдущем примере, в этом диаграмма обновления не указана схема сопоставления, поэтому она использует неявное сопоставление для сопоставления **\<Person.Contact>** элемента с таблицей Person. Contact и атрибутами элемента с соответствующими столбцами в таблице.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-162">As in the previous example, this updategram specifies no mapping schema, so it relies on implicit mapping to map the **\<Person.Contact>** element to the Person.Contact table and the element's attributes to the respective columns in the table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" LastName="Abel" />  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="using-both-element-centric-and-attribute-centric-mapping"></a><span data-ttu-id="4cdb2-163">Одновременное использование элементной и атрибутивной моделей сопоставления</span><span class="sxs-lookup"><span data-stu-id="4cdb2-163">Using Both Element-centric and Attribute-centric Mapping</span></span>  
 <span data-ttu-id="4cdb2-164">Можно использовать сочетание элементной и атрибутивной моделей сопоставления, как показано в следующей диаграмме обновления.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-164">You can specify a mix of element-centric and attribute-centric mapping, as shown in the following updategram.</span></span> <span data-ttu-id="4cdb2-165">Обратите внимание, что **\<Person.Contact>** элемент содержит как атрибут, так и дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-165">Notice that the **\<Person.Contact>** element contains both an attribute and a child element.</span></span> <span data-ttu-id="4cdb2-166">Кроме того, в этой диаграмме обновления используется неявное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-166">Also, this updategram relies on implicit mapping.</span></span> <span data-ttu-id="4cdb2-167">Таким образом, атрибут **FirstName** и **\<LastName>** дочерний элемент сопоставляются с соответствующими столбцами в таблице Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-167">Thus, the **FirstName** attribute and the **\<LastName>** child element map to corresponding columns in the Person.Contact table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" >  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="working-with-characters-valid-in-sql-server-but-not-valid-in-xml"></a><span data-ttu-id="4cdb2-168">Работа с символами, допустимыми в SQL Server, но не допустимыми в XML</span><span class="sxs-lookup"><span data-stu-id="4cdb2-168">Working with Characters Valid in SQL Server but Not Valid in XML</span></span>  
 <span data-ttu-id="4cdb2-169">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] имена таблиц могут содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-169">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space.</span></span> <span data-ttu-id="4cdb2-170">Но в XML имена таблиц такого типа не допускаются.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-170">However, this type of table name is not valid in XML.</span></span>  
  
 <span data-ttu-id="4cdb2-171">Для кодирования символов, которые являются допустимыми [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] идентификаторами, но не являются допустимыми XML-идентификаторами, используйте "__xHHHH \_ \_ " в качестве значения кодировки, где HHHH означает шестнадцатеричный код UCS-2 для символа в наиболее значительном порядке.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-171">To encode characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but are not valid XML identifiers, use '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="4cdb2-172">При использовании этой схемы кодирования символ пробела заменяется на x0020 (шестнадцатеричный код из четырех цифр для символа пробела); Таким же именем таблица [Order Details] в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] _x005B_Order_x0020_Details_x005Dся \_ в XML.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-172">Using this encoding scheme, a space character gets replaced with x0020 (the four-digit hexadecimal code for a space character); thus, the table name [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] becomes _x005B_Order_x0020_Details_x005D\_ in XML.</span></span>  
  
 <span data-ttu-id="4cdb2-173">Аналогичным образом может потребоваться указать имена элементов из трех частей, например \<[database].[owner].[table]> .</span><span class="sxs-lookup"><span data-stu-id="4cdb2-173">Similarly, you might need to specify three-part element names, such as \<[database].[owner].[table]>.</span></span> <span data-ttu-id="4cdb2-174">Поскольку символы квадратной скобки ([и]) недопустимы в XML, необходимо указать этот параметр как \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_> , где _x005B \_ — это кодировка для левой квадратной скобки ([), а _x005D — это \_ Кодировка правой квадратной скобки (]).</span><span class="sxs-lookup"><span data-stu-id="4cdb2-174">Because the bracket characters ([ and ]) are not valid in XML, you must specify this as \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_>, where _x005B\_ is the encoding for the left bracket ([) and _x005D\_ is the encoding for the right bracket (]).</span></span>  
  
## <a name="executing-updategrams"></a><span data-ttu-id="4cdb2-175">Выполнение диаграмм обновления</span><span class="sxs-lookup"><span data-stu-id="4cdb2-175">Executing Updategrams</span></span>  
 <span data-ttu-id="4cdb2-176">Диаграмма обновления является шаблоном, поэтому к ней применяются все механизмы обработки шаблона.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-176">Because an updategram is a template, all the processing mechanisms of a template apply to the updategram.</span></span> <span data-ttu-id="4cdb2-177">В SQLXML 4.0 диаграмму обновления можно выполнить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="4cdb2-177">For SQLXML 4.0, you can execute an updategram in either of the following ways:</span></span>  
  
-   <span data-ttu-id="4cdb2-178">с помощью команды ADO;</span><span class="sxs-lookup"><span data-stu-id="4cdb2-178">By submitting it in an ADO command.</span></span>  
  
-   <span data-ttu-id="4cdb2-179">с помощью команды OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-179">By submitting it as an OLE DB command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cdb2-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="4cdb2-180">See Also</span></span>  
 [<span data-ttu-id="4cdb2-181">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4cdb2-181">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
