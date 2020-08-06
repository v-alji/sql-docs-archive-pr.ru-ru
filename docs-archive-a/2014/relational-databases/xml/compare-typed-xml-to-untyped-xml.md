---
title: Сравнение типизированного и нетипизированного XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- parameters [XML in SQL Server]
- facets [XML in SQL Server]
- xml data type [SQL Server], columns
- untyped XML
- xml data type [SQL Server], typed xml
- XML [SQL Server], typed
- variables [XML in SQL Server], creating
- xml data type [SQL Server], untyped xml
- columns [XML in SQL Server], creating
- typed XML
- document mode processing [SQL Server]
- XML [SQL Server], untyped
- xml data type [SQL Server], parameters
ms.assetid: 4bc50af9-2f7d-49df-bb01-854d080c72c7
author: rothja
ms.author: jroth
ms.openlocfilehash: fae9ca930bd8741a1332b61c8272f2133590483e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730257"
---
# <a name="compare-typed-xml-to-untyped-xml"></a><span data-ttu-id="c093b-102">Сравнение типизированного и нетипизированного XML</span><span class="sxs-lookup"><span data-stu-id="c093b-102">Compare Typed XML to Untyped XML</span></span>
  <span data-ttu-id="c093b-103">Можно создать переменные, параметры и столбцы типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="c093b-103">You can create variables, parameters, and columns of the `xml` type.</span></span> <span data-ttu-id="c093b-104">При необходимости можно связать коллекцию XML-схем с переменной, параметром или столбцом типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="c093b-104">You can optionally associate a collection of XML schemas with a variable, parameter, or column of `xml` type.</span></span> <span data-ttu-id="c093b-105">В этом случае `xml` экземпляр типа данных называется *типизированным*.</span><span class="sxs-lookup"><span data-stu-id="c093b-105">In this case, the `xml` data type instance is called *typed*.</span></span> <span data-ttu-id="c093b-106">В противном случае экземпляр XML называется *нетипизированным*.</span><span class="sxs-lookup"><span data-stu-id="c093b-106">Otherwise, the XML instance is called *untyped*.</span></span>  
  
## <a name="well-formed-xml-and-the-xml-data-type"></a><span data-ttu-id="c093b-107">XML-документы правильного формата и тип данных XML</span><span class="sxs-lookup"><span data-stu-id="c093b-107">Well-formed XML and the xml Data Type</span></span>  
 <span data-ttu-id="c093b-108">Тип данных `xml` соответствует типу данных `xml` стандарта ISO.</span><span class="sxs-lookup"><span data-stu-id="c093b-108">The `xml` data type implements the ISO standard `xml` data type.</span></span> <span data-ttu-id="c093b-109">Таким образом, он позволяет хранить синтаксически корректные документы XML 1.0, а также так называемые фрагменты XML-содержимого с текстовыми узлами и произвольным числом элементов верхнего уровня в нетипизированном XML-столбце.</span><span class="sxs-lookup"><span data-stu-id="c093b-109">Therefore, it can store well-formed XML version 1.0 documents and also so-called XML content fragments with text nodes and an arbitrary number of top-level elements in an untyped XML column.</span></span> <span data-ttu-id="c093b-110">Система, осуществляющая проверку правильности формата данных, не требует, чтобы столбец был связан с XML-схемами, и отклоняет данные, имеющие неправильный формат в общепринятом смысле.</span><span class="sxs-lookup"><span data-stu-id="c093b-110">The system checks that the data is well-formed, does not require the column to be bound to XML schemas, and rejects data that is not well-formed in the extended sense.</span></span> <span data-ttu-id="c093b-111">Это также верно для нетипизированных переменных и параметров типа XML.</span><span class="sxs-lookup"><span data-stu-id="c093b-111">This is true also of untyped XML variables and parameters.</span></span>  
  
## <a name="xml-schemas"></a><span data-ttu-id="c093b-112">XML-схемы</span><span class="sxs-lookup"><span data-stu-id="c093b-112">XML Schemas</span></span>  
 <span data-ttu-id="c093b-113">XML-схема предоставляет следующее.</span><span class="sxs-lookup"><span data-stu-id="c093b-113">An XML schema provides the following:</span></span>  
  
-   <span data-ttu-id="c093b-114">**Ограничения проверки.**</span><span class="sxs-lookup"><span data-stu-id="c093b-114">**Validation constraints.**</span></span> <span data-ttu-id="c093b-115">SQL Server проверяет типизированный экземпляр XML после каждой операции присвоения или изменения.</span><span class="sxs-lookup"><span data-stu-id="c093b-115">Whenever a typed xml instance is assigned to or modified, SQL Server validates the instance.</span></span>  
  
-   <span data-ttu-id="c093b-116">**Сведения о типе данных.**</span><span class="sxs-lookup"><span data-stu-id="c093b-116">**Data type information.**</span></span> <span data-ttu-id="c093b-117">Схемы предоставляют сведения о типах атрибутов и элементов в экземпляре типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="c093b-117">Schemas provide information about the types of attributes and elements in the `xml` data type instance.</span></span> <span data-ttu-id="c093b-118">Сведения о типе позволяют более точно определить семантику операций над значениями, содержащимися в экземпляре, по сравнению с нетипизированным `xml`.</span><span class="sxs-lookup"><span data-stu-id="c093b-118">The type information provides more precise operational semantics to the values contained in the instance than is possible with untyped `xml`.</span></span> <span data-ttu-id="c093b-119">Например, десятичные арифметические действия могут выполняться над десятичными значениями, но не могут выполняться над строками.</span><span class="sxs-lookup"><span data-stu-id="c093b-119">For example, decimal arithmetic operations can be performed on a decimal value, but not on a string value.</span></span> <span data-ttu-id="c093b-120">По этой причине типизированное XML-хранилище может занимать значительно меньше места, чем нетипизированное.</span><span class="sxs-lookup"><span data-stu-id="c093b-120">Because of this, typed XML storage can be made significantly more compact than untyped XML.</span></span>  
  
## <a name="choosing-typed-or-untyped-xml"></a><span data-ttu-id="c093b-121">Выбор между типизированным и нетипизированным XML</span><span class="sxs-lookup"><span data-stu-id="c093b-121">Choosing Typed or Untyped XML</span></span>  
 <span data-ttu-id="c093b-122">В следующих ситуациях следует использовать нетипизированный тип данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="c093b-122">Use untyped `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="c093b-123">Нет схемы XML-данных.</span><span class="sxs-lookup"><span data-stu-id="c093b-123">You do not have a schema for your XML data.</span></span>  
  
-   <span data-ttu-id="c093b-124">Есть схемы, но нежелательно, чтобы сервер проверял данные.</span><span class="sxs-lookup"><span data-stu-id="c093b-124">You have schemas, but you do not want the server to validate the data.</span></span> <span data-ttu-id="c093b-125">Это может иметь место в тех случаях, когда приложение перед сохранением данных на сервере проверяет их на стороне клиента или если приложение временно сохраняет XML-данные, которые не соответствуют схеме, или использует компоненты схемы, не поддерживаемые сервером.</span><span class="sxs-lookup"><span data-stu-id="c093b-125">This is sometimes the case when an application performs client-side validation before storing the data at the server, or temporarily stores XML data that is invalid according to the schema, or uses schema components that are not supported at the server.</span></span>  
  
 <span data-ttu-id="c093b-126">Используйте типизированный `xml` тип данных в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="c093b-126">Use typed `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="c093b-127">есть схемы XML-данных и требуется, чтобы сервер проверял соответствие данных этим схемам;</span><span class="sxs-lookup"><span data-stu-id="c093b-127">You have schemas for your XML data and you want the server to validate your XML data according to the XML schemas.</span></span>  
  
-   <span data-ttu-id="c093b-128">требуется оптимизировать хранение данных и обработку запросов на основе информации о типах;</span><span class="sxs-lookup"><span data-stu-id="c093b-128">You want to take advantage of storage and query optimizations based on type information.</span></span>  
  
-   <span data-ttu-id="c093b-129">требуется в более полной мере использовать информацию о типах при компиляции запросов.</span><span class="sxs-lookup"><span data-stu-id="c093b-129">You want to take better advantage of type information during compilation of your queries.</span></span>  
  
 <span data-ttu-id="c093b-130">В типизированных XML-столбцах, параметрах и переменных можно хранить XML-документы или содержимое.</span><span class="sxs-lookup"><span data-stu-id="c093b-130">Typed XML columns, parameters, and variables can store XML documents or content.</span></span> <span data-ttu-id="c093b-131">Во время объявления необходимо указать при помощи флага, что хранится: документ или содержимое.</span><span class="sxs-lookup"><span data-stu-id="c093b-131">However, you have to specify with a flag whether you are storing a document or content at the time of declaration.</span></span> <span data-ttu-id="c093b-132">Кроме того, необходимо предоставить системе коллекцию XML-схем.</span><span class="sxs-lookup"><span data-stu-id="c093b-132">Additionally, you have to provide the collection of XML schemas.</span></span> <span data-ttu-id="c093b-133">Укажите флаг DOCUMENT, если каждый экземпляр XML имеет ровно один элемент верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="c093b-133">Specify DOCUMENT if each XML instance has exactly one top-level element.</span></span> <span data-ttu-id="c093b-134">В противном случае укажите флаг CONTENT.</span><span class="sxs-lookup"><span data-stu-id="c093b-134">Otherwise, use CONTENT.</span></span> <span data-ttu-id="c093b-135">Компилятор запросов использует флаг DOCUMENT при проверке типов во время компиляции запросов для определения одинарных элементов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="c093b-135">The query compiler uses the DOCUMENT flag in type checks during query compilation to infer singleton top-level elements.</span></span>  
  
## <a name="creating-typed-xml"></a><span data-ttu-id="c093b-136">Создание типизированного XML</span><span class="sxs-lookup"><span data-stu-id="c093b-136">Creating Typed XML</span></span>  
 <span data-ttu-id="c093b-137">Перед созданием типизированных `xml` переменных, параметров или столбцов необходимо сначала зарегистрировать коллекцию XML-схем с помощью [инструкции CREATE XML schema Collection &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c093b-137">Before you can create typed `xml` variables, parameters, or columns, you must first register the XML schema collection by using [CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span> <span data-ttu-id="c093b-138">Затем коллекцию XML-схем можно связать с переменными, параметрами или столбцами типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="c093b-138">You can then associate the XML schema collection with variables, parameters, or columns of the `xml` data type.</span></span>  
  
 <span data-ttu-id="c093b-139">В следующих примерах для указания имени коллекции XML-схем используется обозначение, состоящее из двух частей.</span><span class="sxs-lookup"><span data-stu-id="c093b-139">In the following examples, a two-part naming convention is used for specifying the XML schema collection name.</span></span> <span data-ttu-id="c093b-140">Первая часть — это имя схемы, вторая часть — имя коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="c093b-140">The first part is the schema name, and the second part is the XML schema collection name.</span></span>  
  
### <a name="example-associating-a-schema-collection-with-an-xml-type-variable"></a><span data-ttu-id="c093b-141">Пример Связывание коллекции схем с переменными типа xml</span><span class="sxs-lookup"><span data-stu-id="c093b-141">Example: Associating a Schema Collection with an xml Type Variable</span></span>  
 <span data-ttu-id="c093b-142">В следующем примере создается `xml` переменная типа и связывается с ней коллекция схем.</span><span class="sxs-lookup"><span data-stu-id="c093b-142">The following example creates an`xml` type variable and associates a schema collection with it.</span></span> <span data-ttu-id="c093b-143">Коллекция схем, указанная в примере, уже импортирована в базу данных **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="c093b-143">The schema collection specified in the example is already imported in the **AdventureWorks** database.</span></span>  
  
```  
DECLARE @x xml (Production.ProductDescriptionSchemaCollection);   
```  
  
### <a name="example-specifying-a-schema-for-an-xml-type-column"></a><span data-ttu-id="c093b-144">Пример Указание схемы для столбца типа xml</span><span class="sxs-lookup"><span data-stu-id="c093b-144">Example: Specifying a Schema for an xml Type Column</span></span>  
 <span data-ttu-id="c093b-145">В следующем примере создается таблица со столбцом типа `xml` и указывается схема для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="c093b-145">The following example creates a table with an `xml` type column and specifies a schema for the column:</span></span>  
  
```  
CREATE TABLE T1(  
 Col1 int,   
 Col2 xml (Production.ProductDescriptionSchemaCollection)) ;  
```  
  
### <a name="example-passing-an-xml-type-parameter-to-a-stored-procedure"></a><span data-ttu-id="c093b-146">Пример Передача параметра типа xml в хранимую процедуру</span><span class="sxs-lookup"><span data-stu-id="c093b-146">Example: Passing an xml Type Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="c093b-147">В следующем примере параметр типа `xml` передается хранимой процедуре и указывается схема для переменной.</span><span class="sxs-lookup"><span data-stu-id="c093b-147">The following example passes an `xml` type parameter to a stored procedure and specifies a schema for the variable:</span></span>  
  
```  
CREATE PROCEDURE SampleProc   
  @ProdDescription xml (Production.ProductDescriptionSchemaCollection)   
AS   
...  
```  
  
 <span data-ttu-id="c093b-148">Обратите внимание на следующие сведения о коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="c093b-148">Note the following about the XML schema collection:</span></span>  
  
-   <span data-ttu-id="c093b-149">Коллекция схем XML доступна только в базе данных, в которой она была зарегистрирована с помощью [создания коллекции схем XML](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c093b-149">An XML schema collection is available only in the database in which it was registered by using [Creating an XML Schema Collection](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span>  
  
-   <span data-ttu-id="c093b-150">При приведении строки к типизированному `xml` во время синтаксического анализа также выполняются проверка и типизация на основании пространств имен XML-схем в указанной коллекции.</span><span class="sxs-lookup"><span data-stu-id="c093b-150">If you cast from a string to a typed `xml` data type, the parsing also performs validation and typing, based on the XML schema namespaces in the collection specified.</span></span>  
  
-   <span data-ttu-id="c093b-151">Данные можно приводить из типизированного `xml` в нетипизированный `xml` и наоборот.</span><span class="sxs-lookup"><span data-stu-id="c093b-151">You can cast from a typed `xml` data type to an untyped `xml` data type, and vice versa.</span></span>  
  
 <span data-ttu-id="c093b-152">Дополнительные сведения о других способах формирования XML в SQL Server см. в разделе [Создание экземпляров XML-данных](create-instances-of-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="c093b-152">For more information about other ways to generate XML in SQL Server, see [Create Instances of XML Data](create-instances-of-xml-data.md).</span></span> <span data-ttu-id="c093b-153">После формирования XML-документ может быть связан с переменной типа `xml` или сохранен в столбце типа `xml` для дополнительной обработки.</span><span class="sxs-lookup"><span data-stu-id="c093b-153">After XML is generated, it can be assigned either to an `xml` data type variable or stored in `xml` type columns for additional processing.</span></span>  
  
 <span data-ttu-id="c093b-154">В иерархии типов данных данные `xml` отображаются ниже `sql_variant` и определяемых пользователем типов, но выше всех встроенных типов.</span><span class="sxs-lookup"><span data-stu-id="c093b-154">In the data type hierarchy, the `xml` data type appears below `sql_variant` and user-defined types, but above any of the built-in types.</span></span>  
  
### <a name="example-specifying-facets-to-constrain-a-typed-xml-column"></a><span data-ttu-id="c093b-155">Пример Указание аспектов для ограничения типизированного XML-столбца</span><span class="sxs-lookup"><span data-stu-id="c093b-155">Example: Specifying Facets to Constrain a Typed xml Column</span></span>  
 <span data-ttu-id="c093b-156">На типизированные `xml`-столбцы можно наложить ограничение, допускающее в них только отдельные элементы высшего уровня для каждого сохраненного в них экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c093b-156">For typed `xml` columns, you can constrain the column to allow only single, top-level elements for each instance stored in it.</span></span> <span data-ttu-id="c093b-157">, для указания дополнительного аспекта `DOCUMENT` при создании таблицы, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="c093b-157">You do this by specifying the optional `DOCUMENT` facet when a table is created, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml   
   (DOCUMENT Production.ProductDescriptionSchemaCollection));  
GO  
DROP TABLE T;  
GO  
```  
  
 <span data-ttu-id="c093b-158">По умолчанию, экземпляры, хранимые в типизированном столбце `xml`, сохраняются в виде XML-содержимого, а не XML-документов.</span><span class="sxs-lookup"><span data-stu-id="c093b-158">By default, instances stored in the typed `xml` column are stored as XML content and not as XML documents.</span></span> <span data-ttu-id="c093b-159">Это позволяет использовать:</span><span class="sxs-lookup"><span data-stu-id="c093b-159">This allows for the following:</span></span>  
  
-   <span data-ttu-id="c093b-160">ноль или несколько элементов верхнего уровня;</span><span class="sxs-lookup"><span data-stu-id="c093b-160">Zero or many top-level elements</span></span>  
  
-   <span data-ttu-id="c093b-161">текстовые узлы в элементах верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="c093b-161">Text nodes in top-level elements</span></span>  
  
 <span data-ttu-id="c093b-162">Также можно явно указать данное поведение, добавив аспект `CONTENT` , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c093b-162">You can also explicitly specify this behavior by adding `CONTENT` facet, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml(CONTENT Production.ProductDescriptionSchemaCollection));  
GO -- Default  
```  
  
 <span data-ttu-id="c093b-163">Обратите внимание, что дополнительные аспекты DOCUMENT/CONTENT можно указать везде, где определен тип `xml` (типизированный XML).</span><span class="sxs-lookup"><span data-stu-id="c093b-163">Note that you can specify the optional DOCUMENT/CONTENT facets anywhere you define `xml` type (typed xml).</span></span> <span data-ttu-id="c093b-164">Например, при создании типизированной `xml`-переменной аспект DOCUMENT/CONTENT можно добавить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c093b-164">For example, when you create a typed `xml` variable, you can add the DOCUMENT/CONTENT facet, as shown in the following:</span></span>  
  
```  
declare @x xml (DOCUMENT Production.ProductDescriptionSchemaCollection);  
```  
  
## <a name="document-type-definition-dtd"></a><span data-ttu-id="c093b-165">Определение типа документа (DTD)</span><span class="sxs-lookup"><span data-stu-id="c093b-165">Document Type Definition (DTD)</span></span>  
 <span data-ttu-id="c093b-166">Типизацию столбцов, переменных и параметров типа `xml` можно выполнять с использованием XML-схемы, но без использования DTD.</span><span class="sxs-lookup"><span data-stu-id="c093b-166">The `xml` data type columns, variables, and parameters can be typed by using XML schema, but not by using DTD.</span></span> <span data-ttu-id="c093b-167">Однако и с нетипизированными, и с типизированными XML-данными можно использовать встроенное определение DTD для указания значений по умолчанию и замены ссылок на сущности их расширенными формами.</span><span class="sxs-lookup"><span data-stu-id="c093b-167">However, inline DTD can be used for both untyped and typed XML to supply default values and to replace entity references with their expanded form.</span></span>  
  
 <span data-ttu-id="c093b-168">Можно преобразовывать определения DTD в документы схемы XML при помощи инструментов других компаний и загружать эти схемы XML в базу данных.</span><span class="sxs-lookup"><span data-stu-id="c093b-168">You can convert DTDs to XML schema documents by using third-party tools, and load the XML schemas into the database.</span></span>  
  
## <a name="upgrading-typed-xml-from-sql-server-2005"></a><span data-ttu-id="c093b-169">Обновление типизированного XML с SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="c093b-169">Upgrading Typed XML from SQL Server 2005</span></span>  
 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="c093b-170">содержит несколько расширений для поддержки схем XML, включая поддержку нестрогой проверки, улучшенную обработку данных экземпляров **xs:date**, **xs:time** и **xs:dateTime** . Кроме того, добавлена поддержка типов списков и объединений.</span><span class="sxs-lookup"><span data-stu-id="c093b-170">made several extensions to the XML Schema support, including support for lax validation, improved handling of **xs:date**, **xs:time** and **xs:dateTime** instance data, and added support for list and union types.</span></span> <span data-ttu-id="c093b-171">В большинстве случаев эти изменения не влияют на вопросы обновления.</span><span class="sxs-lookup"><span data-stu-id="c093b-171">In most cases the changes do not affect the upgrade experience.</span></span> <span data-ttu-id="c093b-172">Однако если в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] используется коллекция схем XML, допускающая значения типов **xs:date**, **xs:time**или **xs:dateTime** (или любых их подтипов), то при присоединении базы данных [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] к более поздней версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]потребуется выполнить указанные ниже шаги обновления.</span><span class="sxs-lookup"><span data-stu-id="c093b-172">However if you used an XML Schema collection in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] that allowed values of type **xs:date**, **xs:time**, or **xs:dateTime** (or any subtype) then the following upgrade steps occur when you attach your [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database to a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="c093b-173">Со всеми столбцами XML, введенными с коллекцией схем XML, в которой содержатся элементы или атрибуты, относящиеся к типам **xs:anyType**, **xs:anySimpleType**, **xs:date** или любым их подтипам, **xs:time** или любым его подтипам, **xs:dateTime** или любым его подтипам либо являющиеся объединениями или списками с элементами любых из перечисленных типов, происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="c093b-173">For every XML column, that is typed with an XML Schema Collection that contains elements or attributes that are typed as either **xs:anyType**, **xs:anySimpleType**, **xs:date** or any of its subtypes, **xs:time** or any subtype thereof, or **xs:dateTime** or any of its subtypes, or are union or list types containing any of these types the following occurs:</span></span>  
  
    1.  <span data-ttu-id="c093b-174">отключаются все XML-индексы столбца;</span><span class="sxs-lookup"><span data-stu-id="c093b-174">All XML indices on the column will be disabled.</span></span>  
  
    2.  <span data-ttu-id="c093b-175">все значения [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] продолжают отображаться в часовом поясе Z, поскольку они были нормализованы по часовому поясу Z;</span><span class="sxs-lookup"><span data-stu-id="c093b-175">All [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] values will continue to be represented in the Z timezone, because they have been normalized to the Z timezone.</span></span>  
  
    3.  <span data-ttu-id="c093b-176">все значения **xs:date** или **xs:dateTime** , предшествующие дате "1 января 1 года", приведут к ошибке выполнения при перестроении индекса или применении инструкции XQuery или XML-DML к данным XML, содержащим такие значения;</span><span class="sxs-lookup"><span data-stu-id="c093b-176">Any **xs:date** or **xs:dateTime** values that are smaller than January 1st of year 1 will lead to a runtime error when the index gets rebuild or an XQuery or XML-DML statements gets executed against the XML data type containing that value.</span></span>  
  
2.  <span data-ttu-id="c093b-177">все отрицательные значения года в аспектах **xs:date** или **xs:dateTime** или значения по умолчанию в коллекции схем XML автоматически обновляются до наименьшего значения, допустимого базовым типом **xs:date** или **xs:dateTime** (например, 0001-01-01T00:00:00.0000000Z для **xs:dateTime**).</span><span class="sxs-lookup"><span data-stu-id="c093b-177">Any negative years in **xs:date** or **xs:dateTime** facets or default values in an XML Schema collection will automatically be updated to the smallest value allowed by the base **xs:date** or **xs:dateTime** type (e.g., 0001-01-01T00:00:00.0000000Z for **xs:dateTime**).</span></span>  
  
 <span data-ttu-id="c093b-178">Обратите внимание, что при помощи простой SQL-инструкции SELECT можно получить весь тип XML-данных, даже если в нем содержатся отрицательные значения года.</span><span class="sxs-lookup"><span data-stu-id="c093b-178">Note that you can still use a simple SQL select statement to retrieve the whole XML data type, even if it contains negative years.</span></span> <span data-ttu-id="c093b-179">Отрицательные значения года рекомендуется заменить значением года в обновленном поддерживаемом диапазоне; кроме того, можно изменить тип элемента или атрибута на **xs:string**.</span><span class="sxs-lookup"><span data-stu-id="c093b-179">It is recommended that you replace negative years with a year within the newly supported range or change the type of the element or attribute to **xs:string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c093b-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="c093b-180">See Also</span></span>  
 <span data-ttu-id="c093b-181">[Создание экземпляров XML-данных](create-instances-of-xml-data.md) </span><span class="sxs-lookup"><span data-stu-id="c093b-181">[Create Instances of XML Data](create-instances-of-xml-data.md) </span></span>  
 <span data-ttu-id="c093b-182">[методов типа данных xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="c093b-182">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="c093b-183">[Язык модификации XML-данных (XML DML)](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="c093b-183">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="c093b-184">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c093b-184">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
