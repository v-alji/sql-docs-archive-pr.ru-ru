---
title: XML-индексы (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- deleting indexes
- secondary indexes [XML in SQL Server]
- xml data type [SQL Server], indexes
- dropping indexes
- PATH index
- DROP_EXISTING clause
- XML [SQL Server], indexes
- primary indexes [XML in SQL Server]
- indexes [SQL Server], XML
- XML indexes [SQL Server], secondary
- BLOBs, XML indexes
- disabling indexes
- XML indexes [SQL Server], modifying
- XML indexes [SQL Server]
- XML indexes [SQL Server], primary
- modifying indexes
- XML indexes [SQL Server], dropping
- VALUE index
- XML indexes [SQL Server], xml data type
- PROPERTY index
- XML indexes [SQL Server], creating
ms.assetid: f5c9209d-b3f3-4543-b30b-01365a5e7333
author: rothja
ms.author: jroth
ms.openlocfilehash: bf9a33bc18790bf8821d778746a708f78bbb3d8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665894"
---
# <a name="xml-indexes-sql-server"></a><span data-ttu-id="a2aa7-102">XML-индексы (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a2aa7-102">XML Indexes (SQL Server)</span></span>
  <span data-ttu-id="a2aa7-103">Для столбцов типа `xml` можно создавать XML-индексы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-103">XML indexes can be created on `xml` data type columns.</span></span> <span data-ttu-id="a2aa7-104">При этом индексируются все теги, значения и пути хранимых в столбце экземпляров XML и повышается эффективность обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-104">They index all tags, values and paths over the XML instances in the column and benefit query performance.</span></span> <span data-ttu-id="a2aa7-105">Применение XML-индекса может дать преимущества в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-105">Your application may benefit from an XML index in the following situations:</span></span>  
  
-   <span data-ttu-id="a2aa7-106">Часто выполняются запросы XML-столбцов.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-106">Queries on XML columns are common in your workload.</span></span> <span data-ttu-id="a2aa7-107">При этом нужно учитывать расходы на сопровождение XML-индекса во время модификации данных.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-107">XML index maintenance cost during data modification must be considered.</span></span>  
  
-   <span data-ttu-id="a2aa7-108">XML-значения относительно велики, а извлекаемые XML-данные относительно малы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-108">Your XML values are relatively large and the retrieved parts are relatively small.</span></span> <span data-ttu-id="a2aa7-109">Создание индекса позволяет предотвратить синтаксический анализ всех данных в период выполнения, а также повышает эффективность обработки уточняющих запросов.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-109">Building the index avoids parsing the whole data at run time and benefits index lookups for efficient query processing.</span></span>  
  
 <span data-ttu-id="a2aa7-110">XML-индексы разделяются на следующие категории.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-110">XML indexes fall into the following categories:</span></span>  
  
-   <span data-ttu-id="a2aa7-111">Первичный XML-индекс</span><span class="sxs-lookup"><span data-stu-id="a2aa7-111">Primary XML index</span></span>  
  
-   <span data-ttu-id="a2aa7-112">Вторичные XML-индексы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-112">Secondary XML index</span></span>  
  
 <span data-ttu-id="a2aa7-113">Первым индексом, создаваемым для столбца типа данных `xml`, должен быть первичный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-113">The first index on the `xml` type column must be the primary XML index.</span></span> <span data-ttu-id="a2aa7-114">При наличии первичного XML-индекса поддерживаются вторичные индексы трех типов: PATH, VALUE и PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-114">Using the primary XML index, the following types of secondary indexes are supported: PATH, VALUE, and PROPERTY.</span></span> <span data-ttu-id="a2aa7-115">Эти вторичные индексы могут способствовать повышению производительности выполнения разных типов запросов.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-115">Depending on the type of queries, these secondary indexes might help improve query performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2aa7-116">Создание или изменение XML-индекса невозможно до тех пор, пока параметры базы данных не будут соответствующим образом настроены для работы с типом данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-116">You cannot create or modify an XML index unless the database options are set correctly for working with the `xml` data type.</span></span> <span data-ttu-id="a2aa7-117">Дополнительные сведения см. в разделе [Использование полнотекстового поиска со столбцами XML](use-full-text-search-with-xml-columns.md).</span><span class="sxs-lookup"><span data-stu-id="a2aa7-117">For more information, see [Use Full-Text Search with XML Columns](use-full-text-search-with-xml-columns.md).</span></span>  
  
 <span data-ttu-id="a2aa7-118">Экземпляры XML хранятся в столбцах типа данных `xml` в виде больших двоичных объектов (BLOB).</span><span class="sxs-lookup"><span data-stu-id="a2aa7-118">XML instances are stored in `xml` type columns as large binary objects (BLOBs).</span></span> <span data-ttu-id="a2aa7-119">Размер экземпляров типа `xml` бывает достаточно велик и в двоичном представлении может достигать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-119">These XML instances can be large, and the stored binary representation of `xml` data type instances can be up to 2 GB.</span></span> <span data-ttu-id="a2aa7-120">При отсутствии индекса эти большие двоичные объекты разбираются на этапе выполнения запроса,</span><span class="sxs-lookup"><span data-stu-id="a2aa7-120">Without an index, these binary large objects are shredded at run time to evaluate a query.</span></span> <span data-ttu-id="a2aa7-121">что может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-121">This shredding can be time-consuming.</span></span> <span data-ttu-id="a2aa7-122">Например, рассмотрим следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-122">For example, consider the following query:</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS "PD")  
  
SELECT CatalogDescription.query('  
  /PD:ProductDescription/PD:Summary  
') as Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist ('/PD:ProductDescription/@ProductModelID[.="19"]') = 1  
```  
  
 <span data-ttu-id="a2aa7-123">Чтобы выбрать экземпляры XML, удовлетворяющие условию предложения `WHERE` , большой двоичный объект типа данных XML (объект BLOB) в каждой строке таблицы `Production.ProductModel` разбирается во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-123">To select the XML instances that satisfy the condition in the `WHERE` clause, the XML binary large object (BLOB) in each row of table `Production.ProductModel` is shredded at run time.</span></span> <span data-ttu-id="a2aa7-124">Затем вычисляется выражение `(/PD:ProductDescription/@ProductModelID[.="19"]`) в методе `exist()` .</span><span class="sxs-lookup"><span data-stu-id="a2aa7-124">Then, the expression `(/PD:ProductDescription/@ProductModelID[.="19"]`) in the `exist()` method is evaluated.</span></span> <span data-ttu-id="a2aa7-125">В зависимости от размера и количества экземпляров, содержащихся в столбце, такой разбор на этапе выполнения запроса может потребовать значительных затрат.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-125">This run-time shredding can be costly, depending on the size and number of instances stored in the column.</span></span>  
  
 <span data-ttu-id="a2aa7-126">Если приложение часто обращается к большим двоичным объектам XML (BLOB), индексирование столбцов типа `xml` поможет оптимизировать такие запросы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-126">If querying XML binary large objects (BLOBs) is common in your application environment, it helps to index the `xml` type columns.</span></span> <span data-ttu-id="a2aa7-127">Однако поддержка индекса при изменении данных также связана с дополнительными затратами.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-127">However, there is a cost associated with maintaining the index during data modification.</span></span>  
  
## <a name="primary-xml-index"></a><span data-ttu-id="a2aa7-128">Первичный XML-индекс</span><span class="sxs-lookup"><span data-stu-id="a2aa7-128">Primary XML Index</span></span>  
 <span data-ttu-id="a2aa7-129">При создании первичного XML-индекса индексируются все теги, значения и пути в экземплярах XML, хранимых в XML-столбце.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-129">The primary XML index indexes all tags, values, and paths within the XML instances in an XML column.</span></span> <span data-ttu-id="a2aa7-130">Чтобы создать первичный XML-индекс, таблица, содержащая соответствующий XML-столбец, должна иметь кластеризованный индекс первичного ключа таблицы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-130">To create a primary XML index, the table in which the XML column occurs must have a clustered index on the primary key of the table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a2aa7-131">строки первичного XML-индекса сопоставляются строкам таблицы, в которой содержится XML-столбец.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-131">uses this primary key to correlate rows in the primary XML index with rows in the table that contains the XML column.</span></span>  
  
 <span data-ttu-id="a2aa7-132">Первичный XML-индекс — это разобранное и сохраненное представление XML-объектов BLOB, содержащихся в столбце типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-132">The primary XML index is a shredded and persisted representation of the XML BLOBs in the `xml` data type column.</span></span> <span data-ttu-id="a2aa7-133">Для каждого большого двоичного объекта (BLOB) столбца типа данных xml в индексе создается несколько строк данных,</span><span class="sxs-lookup"><span data-stu-id="a2aa7-133">For each XML binary large object (BLOB) in the column, the index creates several rows of data.</span></span> <span data-ttu-id="a2aa7-134">и их количество приблизительно равно числу узлов в большом двоичном объекте XML.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-134">The number of rows in the index is approximately equal to the number of nodes in the XML binary large object.</span></span> <span data-ttu-id="a2aa7-135">Когда запрос получает полный экземпляр XML, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предоставляет экземпляр из XML-столбца.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-135">When a query retrieves the full XML instance, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the instance from the XML column.</span></span> <span data-ttu-id="a2aa7-136">При обработке запросов в области экземпляров XML применяется первичный XML-индекс, и для возврата скалярных значений или поддеревьев XML может быть использован сам индекс.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-136">Queries within XML instances use the primary XML index, and can return scalar values or XML subtrees by using the index itself.</span></span>  
  
 <span data-ttu-id="a2aa7-137">В каждой строке для узла хранятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-137">Each row stores the following node information:</span></span>  
  
-   <span data-ttu-id="a2aa7-138">имя тега — элемента или атрибута;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-138">Tag name such as an element or attribute name.</span></span>  
  
-   <span data-ttu-id="a2aa7-139">значение узла;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-139">Node value.</span></span>  
  
-   <span data-ttu-id="a2aa7-140">тип узла: узел элемента, атрибута или текстовый узел;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-140">Node type such as an element node, attribute node, or text node.</span></span>  
  
-   <span data-ttu-id="a2aa7-141">сведения о положении в документе, представленные внутренним идентификатором узла;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-141">Document order information, represented by an internal node identifier.</span></span>  
  
-   <span data-ttu-id="a2aa7-142">путь от каждого узла до корня XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-142">Path from each node to the root of the XML tree.</span></span> <span data-ttu-id="a2aa7-143">По этому столбцу в запросе производится поиск выражений пути;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-143">This column is searched for path expressions in the query.</span></span>  
  
-   <span data-ttu-id="a2aa7-144">первичный ключ базовой таблицы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-144">Primary key of the base table.</span></span> <span data-ttu-id="a2aa7-145">Дублируется в первичном XML-индексе для обратного соединения с базовой таблицей, а максимальное количество столбцов в первичном ключе базовой таблицы ограничено значением 15.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-145">The primary key of the base table is duplicated in the primary XML index for a back join with the base table, and the maximum number of columns in the primary key of the base table is limited to 15.</span></span>  
  
 <span data-ttu-id="a2aa7-146">Перечисленные сведения об узле предназначены для вычисления и построения XML-результатов для указанного запроса.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-146">This node information is used to evaluate and construct XML results for a specified query.</span></span> <span data-ttu-id="a2aa7-147">В целях оптимизации имя тега и данные о типе узла кодируются как целые значения, при этом в столбце Path используется такая же кодировка.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-147">For optimization purposes, the tag name and the node type information are encoded as integer values, and the Path column uses the same encoding.</span></span> <span data-ttu-id="a2aa7-148">Кроме того, пути сохраняются в обратном порядке, что позволяет сопоставлять их в тех случаях, когда известен только суффикс пути,</span><span class="sxs-lookup"><span data-stu-id="a2aa7-148">Also, paths are stored in reverse order to allow matching paths when only the path suffix is known.</span></span> <span data-ttu-id="a2aa7-149">Пример:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-149">For example:</span></span>  
  
-   <span data-ttu-id="a2aa7-150">`//ContactRecord/PhoneNumber` , где известны только два последних элемента</span><span class="sxs-lookup"><span data-stu-id="a2aa7-150">`//ContactRecord/PhoneNumber` where only the last two steps are known</span></span>  
  
 <span data-ttu-id="a2aa7-151">OR</span><span class="sxs-lookup"><span data-stu-id="a2aa7-151">OR</span></span>  
  
-   <span data-ttu-id="a2aa7-152">`/Book/*/Title` где в середине выражения указан подстановочный знак (`*`).</span><span class="sxs-lookup"><span data-stu-id="a2aa7-152">`/Book/*/Title` where the wildcard character (`*`) is specified in the middle of the expression.</span></span>  
  
 <span data-ttu-id="a2aa7-153">Обработчик запросов использует первичный XML-индекс для запросов, задействующих [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) , и возвращает либо скалярные значения, либо XML-поддеревья из самого первичного индекса.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-153">The query processor uses the primary XML index for queries that involve [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) and returns either scalar values or the XML subtrees from the primary index itself.</span></span> <span data-ttu-id="a2aa7-154">(В этом индексе хранятся все необходимые данные для реконструкции экземпляра XML.)</span><span class="sxs-lookup"><span data-stu-id="a2aa7-154">(This index stores all the necessary information to reconstruct the XML instance.)</span></span>  
  
 <span data-ttu-id="a2aa7-155">Например, следующий запрос возвращает сводные данные, хранящиеся в `CatalogDescription``xml` столбце Тип в `ProductModel` таблице.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-155">For example, the following query returns summary information stored in the `CatalogDescription``xml` type column in the `ProductModel` table.</span></span> <span data-ttu-id="a2aa7-156">Запрос возвращает данные <`Summary`> только для тех изделий, описания каталога которых содержат также описание <`Features`>.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-156">The query returns <`Summary`> information only for product models whose catalog description also stores the <`Features`> description.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS "PD")SELECT CatalogDescription.query('  /PD:ProductDescription/PD:Summary') as ResultFROM Production.ProductModelWHERE CatalogDescription.exist ('/PD:ProductDescription/PD:Features') = 1  
```  
  
 <span data-ttu-id="a2aa7-157">При использовании первичного XML-индекса вместо того, чтобы разбирать каждый экземпляр большого двоичного объекта типа данных XML в базовой таблице, методом `exist()` производится последовательный поиск заданного выражения в строках индекса, соответствующих данному объекту типа данных XML.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-157">With regard to the primary XML index, instead of shredding each XML binary large object instance in the base table, the rows in the index that correspond to each XML binary large object are searched sequentially for the expression specified in the `exist()` method.</span></span> <span data-ttu-id="a2aa7-158">Если в столбце Path индекса путь найден, элемент <`Summary`> вместе со своими поддеревьями извлекается из первичного XML-индекса и преобразуется в большой двоичный объект типа данных XML, возвращаясь в качестве результата метода `query()`.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-158">If the path is found in the Path column in the index, the <`Summary`> element together with its subtrees is retrieved from the primary XML index and converted into an XML binary large object as the result of the `query()` method.</span></span>  
  
 <span data-ttu-id="a2aa7-159">Обратите внимание, что при извлечении полного экземпляра XML первичный XML-индекс не используется.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-159">Note that the primary XML index is not used when retrieving a full XML instance.</span></span> <span data-ttu-id="a2aa7-160">Например, следующий запрос извлекает из таблицы полный экземпляр XML, описывающий инструкции по изготовлению для определенного изделия.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-160">For example, the following query retrieves from the table the whole XML instance that describes the manufacturing instructions for a specific product model.</span></span>  
  
```  
USE AdventureWorks2012;SELECT InstructionsFROM Production.ProductModel WHERE ProductModelID=7;  
```  
  
## <a name="secondary-xml-indexes"></a><span data-ttu-id="a2aa7-161">Вторичные XML-индексы</span><span class="sxs-lookup"><span data-stu-id="a2aa7-161">Secondary XML Indexes</span></span>  
 <span data-ttu-id="a2aa7-162">Для повышения производительности поиска можно также создать вторичные XML-индексы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-162">To enhance search performance, you can create secondary XML indexes.</span></span> <span data-ttu-id="a2aa7-163">Перед созданием вторичных индексов должен существовать первичный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-163">A primary XML index must first exist before you can create secondary indexes.</span></span> <span data-ttu-id="a2aa7-164">Существуют следующие типы вторичных индексов:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-164">These are the types:</span></span>  
  
-   <span data-ttu-id="a2aa7-165">вторичный индекс PATH типа данных XML;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-165">PATH secondary XML index</span></span>  
  
-   <span data-ttu-id="a2aa7-166">вторичный индекс VALUE типа данных XML;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-166">VALUE secondary XML index</span></span>  
  
-   <span data-ttu-id="a2aa7-167">вторичный индекс PROPERTY типа данных XML.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-167">PROPERTY secondary XML index</span></span>  
  
 <span data-ttu-id="a2aa7-168">Ниже приведены некоторые рекомендации по созданию вторичных индексов.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-168">Following are some guidelines for creating one or more secondary indexes:</span></span>  
  
-   <span data-ttu-id="a2aa7-169">Если при работе с XML-столбцами часто используются выражения пути, вторичный XML-индекс PATH, скорее всего, ускорит обработку данных.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-169">If your workload uses path expressions significantly on XML columns, the PATH secondary XML index is likely to speed up your workload.</span></span> <span data-ttu-id="a2aa7-170">Типичный пример — выполнение метода **exist()** для XML-столбцов в предложении WHERE инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-170">The most common case is the use of the **exist()** method on XML columns in the WHERE clause of Transact-SQL.</span></span>  
  
-   <span data-ttu-id="a2aa7-171">Если с использованием выражений пути извлекаются множественные значения из отдельных экземпляров XML, может принести пользу кластеризация путей в пределах каждого экземпляра XML в индекс PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-171">If your workload retrieves multiple values from individual XML instances by using path expressions, clustering paths within each XML instance in the PROPERTY index may be helpful.</span></span> <span data-ttu-id="a2aa7-172">Этот сценарий обычно имеет место при работе с наборами свойств, когда извлекаются свойства объекта и известно значение его первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-172">This scenario typically occurs in a property bag scenario when properties of an object are fetched and its primary key value is known.</span></span>  
  
-   <span data-ttu-id="a2aa7-173">Если запрашиваются значения экземпляров XML, не зная имен элементов или атрибутов, содержащих эти значения, следует подумать о создании индекса VALUE.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-173">If your workload involves querying for values within XML instances without knowing the element or attribute names that contain those values, you may want to create the VALUE index.</span></span> <span data-ttu-id="a2aa7-174">Как правило, это имеет место при уточняющем запросе по осям нижних уровней, например //author[last-name="Howard"], где элементы \<author> могут встречаться на любом уровне иерархии.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-174">This typically occurs with descendant axes lookups, such as //author[last-name="Howard"], where \<author> elements can occur at any level of the hierarchy.</span></span> <span data-ttu-id="a2aa7-175">Кроме того, такая ситуация встречается при обработке запросов с символами-шаблонами (например, /book [@\* = "novel"], где в запросе выполняется поиск элементов \<book>, имеющих некоторый атрибут со значением novel).</span><span class="sxs-lookup"><span data-stu-id="a2aa7-175">It also occurs in wildcard queries, such as /book [@\* = "novel"], where the query looks for \<book> elements that have some attribute having the value "novel".</span></span>  
  
### <a name="path-secondary-xml-index"></a><span data-ttu-id="a2aa7-176">вторичный индекс PATH типа данных XML;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-176">PATH Secondary XML Index</span></span>  
 <span data-ttu-id="a2aa7-177">Если обычно запросы задают выражения пути для столбцов типа данных `xml`, вторичный индекс PATH может ускорить их поиск.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-177">If your queries generally specify path expressions on `xml` type columns, a PATH secondary index may be able to speed up the search.</span></span> <span data-ttu-id="a2aa7-178">Как ранее отмечалось, первичный индекс полезен в тех запросах, где метод **exist()** указан в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-178">As described earlier in this topic, the primary index is helpful when you have queries that specify **exist()** method in the WHERE clause.</span></span> <span data-ttu-id="a2aa7-179">Добавление вторичного индекса PATH может еще более повысить производительность поиска в таких запросах.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-179">If you add a PATH secondary index, you may also improve the search performance in such queries.</span></span>  
  
 <span data-ttu-id="a2aa7-180">Хотя первичный XML-индекс позволяет избежать на стадии выполнения запроса разбора больших двоичных объектов типа данных XML, он не в состоянии обеспечить максимальную производительность запросов на основе выражений пути.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-180">Although a primary XML index avoids having to shred the XML binary large objects at run time, it may not provide the best performance for queries based on path expressions.</span></span> <span data-ttu-id="a2aa7-181">Так как все строки первичного XML-индекса, соответствующие большому двоичному объекту XML, просматриваются последовательно, такой поиск работает довольно медленно.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-181">Because all rows in the primary XML index corresponding to an XML binary large object are searched sequentially for large XML instances, the sequential search may be slow.</span></span> <span data-ttu-id="a2aa7-182">В таких случаях наличие вторичного индекса, построенного для значений путей и узлов первичного индекса, может существенно ускорить поиск в нем.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-182">In this case, having a secondary index built on the path values and node values in the primary index can significantly speed up the index search.</span></span> <span data-ttu-id="a2aa7-183">Во вторичном индексе PATH значения пути и узлов являются ключевыми столбцами, позволяющими выполнять более эффективный поиск путей.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-183">In the PATH secondary index, the path and node values are key columns that allow for more efficient seeks when searching for paths.</span></span> <span data-ttu-id="a2aa7-184">Оптимизатор запросов может использовать индекс PATH, например для следующих выражений:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-184">The query optimizer may use the PATH index for expressions such as those shown in the following:</span></span>  
  
-   <span data-ttu-id="a2aa7-185">`/root/Location` , что задает только путь</span><span class="sxs-lookup"><span data-stu-id="a2aa7-185">`/root/Location` which specify only a path</span></span>  
  
 <span data-ttu-id="a2aa7-186">OR</span><span class="sxs-lookup"><span data-stu-id="a2aa7-186">OR</span></span>  
  
-   <span data-ttu-id="a2aa7-187">`/root/Location/@LocationID[.="10"]` , где заданы как значение пути, так и значение узла.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-187">`/root/Location/@LocationID[.="10"]` where both the path and the node value are specified.</span></span>  
  
 <span data-ttu-id="a2aa7-188">Следующий запрос демонстрирует, при каких условиях может быть полезен индекс PATH:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-188">The following query shows where the PATH index is helpful:</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS "PD")  
  
SELECT CatalogDescription.query('  
  /PD:ProductDescription/PD:Summary  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist ('/PD:ProductDescription/@ProductModelID[.="19"]') = 1  
```  
  
 <span data-ttu-id="a2aa7-189">В этом запросе в методе `/PD:ProductDescription/@ProductModelID` выражение пути `"19"` и значение `exist()` соответствуют ключевым полям индекса PATH.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-189">In the query, the path expression `/PD:ProductDescription/@ProductModelID` and value `"19"` in the `exist()` method correspond to the key fields of the PATH index.</span></span> <span data-ttu-id="a2aa7-190">Это позволяет выполнять поиск непосредственно в индексе PATH и при этом обеспечивает более высокую производительность, чем при последовательном переборе значений пути в первичном индексе.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-190">This allows for direct seek in the PATH index and provides better search performance than the sequential search for path values in the primary index.</span></span>  
  
### <a name="value-secondary-xml-index"></a><span data-ttu-id="a2aa7-191">вторичный индекс VALUE типа данных XML;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-191">VALUE Secondary XML Index</span></span>  
 <span data-ttu-id="a2aa7-192">Если запрос основан на значении, например: `/Root/ProductDescription/@*[. = "Mountain Bike"]` или `//ProductDescription[@Name = "Mountain Bike"]`, и если путь задан не полностью либо он включает в себя символ-шаблон, скорость выполнения запросов можно повысить, построив вторичный XML-индекс по значениям узлов первичного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-192">If queries are value based, for example, `/Root/ProductDescription/@*[. = "Mountain Bike"]` or `//ProductDescription[@Name = "Mountain Bike"]`, and the path is not fully specified or it includes a wildcard, you might obtain faster results by building a secondary XML index that is built on node values in the primary XML index.</span></span>  
  
 <span data-ttu-id="a2aa7-193">Ключевые столбцы индекса VALUE (значение узла и значение пути) содержатся в первичном XML-индексе.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-193">The key columns of the VALUE index are (node value and path) of the primary XML index.</span></span> <span data-ttu-id="a2aa7-194">Индекс VALUE может оказаться полезным в тех случаях, если рабочая нагрузка включает в себя запросы значений из экземпляров XML, для которых неизвестны имена элементов или атрибутов, содержащих эти значения.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-194">If your workload involves querying for values from XML instances without knowing the element or attribute names that contain the values, a VALUE index may be useful.</span></span> <span data-ttu-id="a2aa7-195">Например, следующее выражение при наличии индекса VALUE выполняется более эффективно:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-195">For example, the following expression will benefit from having a VALUE index:</span></span>  
  
-   <span data-ttu-id="a2aa7-196">`//author[LastName="someName"]`, где известно значение элемента <`LastName`>, но родительский элемент <`author`> может находиться где угодно;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-196">`//author[LastName="someName"]` where you know the value of the <`LastName`> element, but the <`author`> parent can occur anywhere.</span></span>  
  
-   <span data-ttu-id="a2aa7-197">`/book[@* = "someValue"]`, где запрос выполняет поиск элемента <`book`> с каким-либо атрибутом, имеющим значение `"someValue"`.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-197">`/book[@* = "someValue"]` where the query looks for the <`book`> element that has some attribute having the value `"someValue"`.</span></span>  
  
 <span data-ttu-id="a2aa7-198">Следующий запрос возвращает столбец `ContactID` из таблицы `Contact` .</span><span class="sxs-lookup"><span data-stu-id="a2aa7-198">The following query returns `ContactID` from the `Contact` table.</span></span> <span data-ttu-id="a2aa7-199">`WHERE`Предложение задает фильтр, который ищет значения в `AdditionalContactInfo``xml` столбце типа.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-199">The `WHERE` clause specifies a filter that looks for values in the `AdditionalContactInfo``xml` type column.</span></span> <span data-ttu-id="a2aa7-200">Идентификаторы контактов возвращаются только тогда, когда соответствующий большой двоичный объект XML, содержащий дополнительные контактные данные, включает в себя определенный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-200">The contact IDs are returned only if the corresponding additional contact information XML binary large object includes a specific telephone number.</span></span> <span data-ttu-id="a2aa7-201">Поскольку элемент <`telephoneNumber`> может находиться в любом месте XML-документа, выражение пути задает ось descendent-or-self.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-201">Because the <`telephoneNumber`> element may appear anywhere in the XML, the path expression specifies the descendent-or-self axis.</span></span>  
  
```  
WITH XMLNAMESPACES (  
  'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo' AS CI,  
  'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes' AS ACT)  
  
SELECT ContactID   
FROM   Person.Contact  
WHERE  AdditionalContactInfo.exist('//ACT:telephoneNumber/ACT:number[.="111-111-1111"]') = 1  
```  
  
 <span data-ttu-id="a2aa7-202">В этой ситуации искомое значение атрибута <`number`> известно, но оно может находиться в любом месте экземпляра XML как дочерний элемент элемента <`telephoneNumber`>.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-202">In this situation, the search value for <`number`> is known, but it can appear anywhere in the XML instance as a child of the <`telephoneNumber`> element.</span></span> <span data-ttu-id="a2aa7-203">Производительность запроса такого рода может повыситься при поиске указанного значения по индексу.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-203">This kind of query might benefit from an index lookup based on a specific value.</span></span>  
  
### <a name="property-secondary-index"></a><span data-ttu-id="a2aa7-204">Вторичный индекс PROPERTY</span><span class="sxs-lookup"><span data-stu-id="a2aa7-204">PROPERTY Secondary Index</span></span>  
 <span data-ttu-id="a2aa7-205">Производительность запросов, извлекающих одно или несколько значений из отдельных экземпляров XML, может повыситься при использовании индекса PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-205">Queries that retrieve one or more values from individual XML instances might benefit from a PROPERTY index.</span></span> <span data-ttu-id="a2aa7-206">Этот сценарий происходит при извлечении свойств объекта с помощью метода **value ()** `xml` типа и при известном значении первичного ключа объекта.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-206">This scenario occurs when you retrieve object properties by using the **value()** method of the `xml` type and when the primary key value of the object is known.</span></span>  
  
 <span data-ttu-id="a2aa7-207">Индекс PROPERTY строится по столбцам (PK, Path и значении узла) первичного XML-индекса, где PK — это первичный ключ базовой таблицы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-207">The PROPERTY index is built on columns (PK, Path and node value) of the primary XML index where PK is the primary key of the base table.</span></span>  
  
 <span data-ttu-id="a2aa7-208">Например, для модели продукта `19`следующий запрос извлекает значения атрибутов `ProductModelID` и `ProductModelName` при помощи метода `value()` .</span><span class="sxs-lookup"><span data-stu-id="a2aa7-208">For example, for product model `19`, the following query retrieves the `ProductModelID` and `ProductModelName` attribute values using the `value()` method.</span></span> <span data-ttu-id="a2aa7-209">Если вместо первичного или вторичных XML-индексов использовать индекс PROPERTY, это может повысить скорость выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-209">Instead of using the primary XML index or the other secondary XML indexes, the PROPERTY index may provide faster execution.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS "PD")  
  
SELECT CatalogDescription.value('(/PD:ProductDescription/@ProductModelID)[1]', 'int') as ModelID,  
       CatalogDescription.value('(/PD:ProductDescription/@ProductModelName)[1]', 'varchar(30)') as ModelName          
FROM Production.ProductModel     
WHERE ProductModelID = 19  
```  
  
 <span data-ttu-id="a2aa7-210">За исключением различий, описанных далее в этом разделе, создание XML-индекса для `xml` столбца типа похоже на создание индекса для столбца, не являющегося `xml` типом.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-210">Except for the differences described later in this topic, creating an XML index on an`xml` type column is similar to creating an index on a non-`xml` type column.</span></span> <span data-ttu-id="a2aa7-211">Для создания XML-индексов и управления ими могут использоваться следующие DDL-инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a2aa7-211">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statements can be used to create and manage XML indexes:</span></span>  
  
-   [<span data-ttu-id="a2aa7-212">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2aa7-212">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
-   [<span data-ttu-id="a2aa7-213">ALTER INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a2aa7-213">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
-   [<span data-ttu-id="a2aa7-214">DROP INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a2aa7-214">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
## <a name="getting-information-about-xml-indexes"></a><span data-ttu-id="a2aa7-215">Получение сведений о триггерах XML</span><span class="sxs-lookup"><span data-stu-id="a2aa7-215">Getting Information about XML Indexes</span></span>  
 <span data-ttu-id="a2aa7-216">XML-индексы входят в представление каталога sys.indexes с индексом типа 3.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-216">XML index entries appear in the catalog view, sys.indexes, with the index "type" 3.</span></span> <span data-ttu-id="a2aa7-217">Столбец name при этом содержит имя XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-217">The name column contains the name of the XML index.</span></span>  
  
 <span data-ttu-id="a2aa7-218">Кроме того, XML-индексы записываются в представление каталога sys.xml_indexes.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-218">XML indexes are also recorded in the catalog view, sys.xml_indexes.</span></span> <span data-ttu-id="a2aa7-219">Оно содержит все столбцы представления sys.indexes и некоторые специфические столбцы, полезные при работе с XML-индексами.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-219">This contains all the columns of sys.indexes and some specific ones that are useful for XML indexes.</span></span> <span data-ttu-id="a2aa7-220">Значение NULL в столбце secondary_type определяет первичный XML-индекс; значения 'P', 'R' и 'V' определяют соответственно вторичные XML-индексы PATH, PROPERTY и VALUE.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-220">The value NULL in the column, secondary_type, indicates a primary XML index; the values 'P', 'R' and 'V' stand for PATH, PROPERTY, and VALUE secondary XML indexes, respectively.</span></span>  
  
 <span data-ttu-id="a2aa7-221">Информацию о пространстве, занимаемом XML-индексами, можно получить при помощи функции с табличным значением [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a2aa7-221">The space use of XML indexes can be found in the table-valued function [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span></span> <span data-ttu-id="a2aa7-222">Она предоставляет такую информацию об индексах всех типов, как число занимаемых ими страниц на диске, средний размер строки в байтах и число записей.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-222">It provides information, such as the number of disk pages occupied, average row size in bytes, and number of records, for all index types..</span></span> <span data-ttu-id="a2aa7-223">Эта функция поддерживает и XML-индексы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-223">This also includes XML indexes.</span></span> <span data-ttu-id="a2aa7-224">Получить такие данные можно для каждой секции базы данных.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-224">This information is available for each database partition.</span></span> <span data-ttu-id="a2aa7-225">XML-индексы используют ту же схему секционирования и функцию секционирования базовой таблицы.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-225">XML indexes use the same partitioning scheme and partitioning function of the base table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2aa7-226">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-226">See Also</span></span>  
 <span data-ttu-id="a2aa7-227">[sys.dm_db_index_physical_stats (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a2aa7-227">[sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) </span></span>  
 [<span data-ttu-id="a2aa7-228">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a2aa7-228">XML Data &#40;SQL Server&#41;</span></span>](../xml/xml-data-sql-server.md)  
  
  
