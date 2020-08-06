---
title: Использование заметок в схемах XSD (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, about annotated XSD schemas
- annotations [SQLXML]
- relationships [SQLXML]
- relationships [SQLXML], hierarchical relationships
- hierarchical relationships [SQLXML]
- mapping schema [SQLXML], scenarios for using
ms.assetid: 78f318a4-7a36-473b-9852-a4bae6940ce5
author: rothja
ms.author: jroth
ms.openlocfilehash: e2be94aa5815593d7a5a2e0c00bcd8849e81484e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664115"
---
# <a name="using-annotations-in-xsd-schemas-sqlxml-40"></a><span data-ttu-id="6b2de-102">Использование заметок в схемах XSD (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="6b2de-102">Using Annotations in XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="6b2de-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0 язык схем XSD поддерживает заметки аналогично заметкам, введенным в языке схем XDR.</span><span class="sxs-lookup"><span data-stu-id="6b2de-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports annotations in a manner similar to the annotations introduced in the XML-Data Reduced (XDR) schema language.</span></span> <span data-ttu-id="6b2de-104">В XSD введены дополнительные заметки, не поддерживаемые в XDR.</span><span class="sxs-lookup"><span data-stu-id="6b2de-104">There are additional annotations introduced in XSD that are not supported in XDR.</span></span>  
  
 <span data-ttu-id="6b2de-105">Их можно использовать в схеме XSD для задания сопоставлений данных XML c реляционными данными.</span><span class="sxs-lookup"><span data-stu-id="6b2de-105">These annotations can be used within the XSD schema to specify XML-to-relational mapping.</span></span> <span data-ttu-id="6b2de-106">Сюда входит сопоставление элементов и атрибутов схемы XSD с таблицами (представлениями) и столбцами базы данных.</span><span class="sxs-lookup"><span data-stu-id="6b2de-106">This includes mapping between elements and attributes in the XSD schema to tables (views) and columns in the databases.</span></span>  
  
 <span data-ttu-id="6b2de-107">Если заметки не заданы, будет использоваться сопоставление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b2de-107">If you do not specify the annotations, default mapping takes place.</span></span> <span data-ttu-id="6b2de-108">По умолчанию элемент XSD сложного типа сопоставляется имени таблицы или представления в заданной базе данных, а элемент или атрибут простого типа — одноименному столбцу.</span><span class="sxs-lookup"><span data-stu-id="6b2de-108">By default, an XSD element with a complex type maps to a table (view) name in the specified database, and an element or attribute with a simple type maps to the column with the same name as the element or attribute.</span></span>  
  
 <span data-ttu-id="6b2de-109">Эти заметки также можно использовать для указания иерархических связей в формате XML, представляющих связи в базе данных, поскольку схема XSD представляет собой просто XML-представление реляционных данных.</span><span class="sxs-lookup"><span data-stu-id="6b2de-109">These annotations can also be used to specify the hierarchical relationships in XML-thus representing the relationships in the database, because an XSD schema is simply an XML view of relational data.</span></span>  
  
 <span data-ttu-id="6b2de-110">Этот раздел представляет описания заметок, которые можно использовать со схемами XSD, и примеры их использования.</span><span class="sxs-lookup"><span data-stu-id="6b2de-110">This section provides descriptions of the annotations you can use with XSD schemas and examples of their usage.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b2de-111">Все примеры в этом разделе задают простые запросы XPath к схеме XSD с заметками, описанной в каждом из примеров.</span><span class="sxs-lookup"><span data-stu-id="6b2de-111">All the examples in this section specify simple XPath queries against the annotated XSD schema described in each example.</span></span> <span data-ttu-id="6b2de-112">Предполагается, что читатель знаком с языком XPath.</span><span class="sxs-lookup"><span data-stu-id="6b2de-112">Familiarity with the XPath language is assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b2de-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="6b2de-113">In This Section</span></span>  
 [<span data-ttu-id="6b2de-114">Аннотации XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-114">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](xsd-annotations-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-115">Перечисление заметок, которые можно использовать со схемами XSD, и эквивалентных им заметок для XDR.</span><span class="sxs-lookup"><span data-stu-id="6b2de-115">Lists the annotations you can use with XSD schemas, their descriptions, and the equivalent annotations for XDR.</span></span>  
  
 [<span data-ttu-id="6b2de-116">Сопоставление элементов и атрибутов XSD с таблицами и столбцами по умолчанию &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-116">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-117">Рассказ о сопоставлении по умолчанию и примеры задач, использующих такое сопоставление.</span><span class="sxs-lookup"><span data-stu-id="6b2de-117">Explains default mapping and provides examples of tasks related to default mapping.</span></span>  
  
 [<span data-ttu-id="6b2de-118">Явное сопоставление элементов и атрибутов XSD с таблицами и столбцами &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-118">Explicit Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](explicit-mapping-xsd-elements-and-attributes-to-tables-and-columns.md)  
 <span data-ttu-id="6b2de-119">Содержит объяснение явного сопоставления с заметками `sql:relation` и `sql:field`, а также примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-119">Explains explicit mapping with the `sql:relation` and `sql:field` annotations, and provides examples.</span></span>  
  
 [<span data-ttu-id="6b2de-120">Указание связей с помощью SQL: relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-120">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-121">Содержит описание заметок `sql:relationship` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-121">Describes and provides examples of the `sql:relationship` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-122">Указание атрибута SQL: инверсии в SQL: relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-122">Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-123">Описание заметки `sql:inverse`.</span><span class="sxs-lookup"><span data-stu-id="6b2de-123">Describes the `sql:inverse` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-124">Создание элементов констант с помощью SQL: является константой &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-124">Creating Constant Elements Using sql:is-constant &#40;SQLXML 4.0&#41;</span></span>](creating-constant-elements-using-sql-is-constant-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-125">Содержит описание заметок `sql:is-constant` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-125">Describes and provides examples of the `sql:is-constant` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-126">Исключение элементов схемы из результирующего XML-документа с помощью SQL: сопоставлено &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-126">Excluding Schema Elements from the Resulting XML Document Using sql:mapped &#40;SQLXML 4.0&#41;</span></span>](excluding-schema-elements-from-the-xml-document-using-sql-mapped.md)  
 <span data-ttu-id="6b2de-127">Содержит описание заметок `sql:mapped` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-127">Describes and provides examples of the `sql:mapped` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-128">Фильтрация значений с помощью SQL: limit-field и SQL: limit-value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-128">Filtering Values Using sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="6b2de-129">Содержит описание заметок `sql:limit-field` и `sql:limit-value`, а также примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-129">Describes and provides examples of the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 [<span data-ttu-id="6b2de-130">Определение ключевых столбцов с помощью SQL: Key-Fields &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-130">Identifying Key Columns Using sql:key-fields &#40;SQLXML 4.0&#41;</span></span>](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-131">Содержит описание заметок `sql:key-fields` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-131">Describes and provides examples of the `sql:key-fields` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-132">Указание целевого пространства имен с помощью атрибута targetNamespace &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-132">Specifying a Target Namespace Using the targetNamespace Attribute &#40;SQLXML 4.0&#41;</span></span>](specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-133">Описывает и предоставляет примеры атрибута **targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="6b2de-133">Describes and provides examples of the **targetNamespace** attribute.</span></span>  
  
 [<span data-ttu-id="6b2de-134">Создание допустимых атрибутов типа ID, IDREF и IDREFS с помощью SQL: prefix &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-134">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix &#40;SQLXML 4.0&#41;</span></span>](creating-valid-id-idref-and-idrefs-type-attributes-using-sql-prefix-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-135">Содержит описание заметок `sql:prefix` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-135">Describes and provides examples of the `sql:prefix` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-136">Приведение типов данных и аннотация SQL: DataType &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-136">Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;</span></span>](data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-137">Содержит описание заметок `sql:datatype` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-137">Describes and provides examples of the `sql:datatype` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-138">Сопоставление типов данных XSD с типами данных XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-138">Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-139">Содержит таблицу сравнения типов данных XSD, XDR и XPath с перечислением соответствующих преобразований [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b2de-139">Provides a table that compares XSD, XDR, and XPath datatypes and lists the relevant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conversions.</span></span>  
  
 [<span data-ttu-id="6b2de-140">Создание разделов CDATA с помощью SQL: use-CDATA &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-140">Creating CDATA Sections Using sql:use-cdata &#40;SQLXML 4.0&#41;</span></span>](creating-cdata-sections-using-sql-use-cdata-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-141">Содержит описание заметок `sql:use-data` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-141">Describes and provides examples of the `sql:use-data` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-142">Запрос URL-ссылок на данные большого двоичного объекта с помощью SQL: Encoded &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-142">Requesting URL References to BLOB Data Using sql:encode &#40;SQLXML 4.0&#41;</span></span>](requesting-url-references-to-blob-data-using-sql-encode-sqlxml-4-0.md)  
 <span data-ttu-id="6b2de-143">Содержит описание заметок `sql:encode` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-143">Describes and provides examples of the `sql:encode` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-144">Получение невостребованных данных с помощью SQL: overflow-поля &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-144">Retrieving Unconsumed Data Using the sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="6b2de-145">Содержит описание заметок `sql:overflow-field` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-145">Describes and provides examples of the `sql:overflow-field` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-146">Скрытие элементов и атрибутов с помощью sql:hide</span><span class="sxs-lookup"><span data-stu-id="6b2de-146">Hiding Elements and Attributes by Using sql:hide</span></span>](hiding-elements-and-attributes-by-using-sql-hide.md)  
 <span data-ttu-id="6b2de-147">Содержит описание заметок `sql:hide` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-147">Describes and provides examples of the `sql:hide` annotation.</span></span>  
  
 [<span data-ttu-id="6b2de-148">Использование заметок sql:identity и sql:guid</span><span class="sxs-lookup"><span data-stu-id="6b2de-148">Using the sql:identity and sql:guid Annotations</span></span>](using-the-sql-identity-and-sql-guid-annotations.md)  
 <span data-ttu-id="6b2de-149">Содержит описание заметок `sql:identity` и `sql:guid`, а также примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-149">Describes and provides examples of the `sql:identity` and `sql:guid` annotations.</span></span>  
  
 [<span data-ttu-id="6b2de-150">Задание глубины рекурсивных связей с использованием sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="6b2de-150">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>](specifying-depth-in-recursive-relationships-by-using-sql-max-depth.md)  
 <span data-ttu-id="6b2de-151">Содержит описание заметок `sql:max-depth` и примеры.</span><span class="sxs-lookup"><span data-stu-id="6b2de-151">Describes and provides examples of the `sql:max-depth` annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b2de-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b2de-152">See Also</span></span>  
 [<span data-ttu-id="6b2de-153">Рекомендации по безопасности схемы с заметками &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-153">Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md)  
  
  
