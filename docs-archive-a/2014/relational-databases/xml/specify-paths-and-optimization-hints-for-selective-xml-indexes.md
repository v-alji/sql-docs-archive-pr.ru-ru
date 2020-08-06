---
title: Задание путей и указания по оптимизации для селективных XML-индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 486ee339-165b-4aeb-b760-d2ba023d7d0a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a9d683fe57d489fdb9922b53d2c5c6825835216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735134"
---
# <a name="specify-paths-and-optimization-hints-for-selective-xml-indexes"></a><span data-ttu-id="36051-102">Задайте путь и указания по оптимизации для селективных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="36051-102">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>
  <span data-ttu-id="36051-103">В данном разделе описывается настройка путей узла для индексирования и задание указаний по оптимизации для индексирования при создании или изменении селективных XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="36051-103">This topic describes how to specify node paths to index and optimization hints for indexing when you create or alter selective XML indexes.</span></span>  
  
 <span data-ttu-id="36051-104">Пути узла и указания по оптимизации задаются одновременно в одной из следующих инструкций:</span><span class="sxs-lookup"><span data-stu-id="36051-104">You specify node paths and optimization hints at the same time in one of the following statements:</span></span>  
  
-   <span data-ttu-id="36051-105">В предложении **FOR** инструкции **CREATE**.</span><span class="sxs-lookup"><span data-stu-id="36051-105">In the **FOR** clause of a **CREATE** statement.</span></span> <span data-ttu-id="36051-106">Дополнительные сведения см. в разделе [CREATE SELECTIVE XML INDEX (Transact-SQL)](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="36051-106">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="36051-107">В предложении **ADD** инструкции **ALTER**.</span><span class="sxs-lookup"><span data-stu-id="36051-107">In the **ADD** clause of an **ALTER** statement.</span></span> <span data-ttu-id="36051-108">Дополнительные сведения см. в разделе [ALTER INDEX (селективные XML-индексы)](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="36051-108">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="36051-109">Дополнительные сведения о селективных XML-индексах см. в разделе [Выборочный XML-индекс (SXI)](../xml/selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="36051-109">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="understanding-xquery-and-sql-server-types-in-untyped-xml"></a><a name="untyped"></a> <span data-ttu-id="36051-110">Основные сведения о типах Xquery и SQL Server в нетипизированном XML</span><span class="sxs-lookup"><span data-stu-id="36051-110">Understanding XQuery and SQL Server Types in Untyped XML</span></span>  
 <span data-ttu-id="36051-111">Селективные XML-индексы поддерживают две системы типов — типы XQuery и типы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36051-111">Selective XML indexes support two type systems: XQuery types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="36051-112">Индексированный путь можно использовать для сопоставления с выражением Xquery или с возвращаемым типом метода value() типа данных XML.</span><span class="sxs-lookup"><span data-stu-id="36051-112">The indexed path can be used either to match an XQuery expression, or to match the return type of the value() method of the XML data type.</span></span>  
  
-   <span data-ttu-id="36051-113">Если путь для индексирования не снабжен заметками или ключевым словом XQUERY, путь будет сопоставляться с выражением Xquery.</span><span class="sxs-lookup"><span data-stu-id="36051-113">When a path to index is not annotated, or is annotated with the XQUERY keyword, the path matches an XQuery expression.</span></span> <span data-ttu-id="36051-114">Есть две вариации путей узла, снабженных ключевым словом XQUERY.</span><span class="sxs-lookup"><span data-stu-id="36051-114">There are two variations for XQUERY-annotated node paths:</span></span>  
  
    -   <span data-ttu-id="36051-115">Если ключевое слово XQUERY и тип данных XQuery не указаны, будут использоваться сопоставления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36051-115">If you do not specify the XQUERY keyword and the XQuery data type, then default mappings are used.</span></span> <span data-ttu-id="36051-116">Обычно производительность и хранение не являются оптимальными.</span><span class="sxs-lookup"><span data-stu-id="36051-116">Typically performance and storage are not optimal.</span></span>  
  
    -   <span data-ttu-id="36051-117">Если было указано ключевое слово XQUERY и тип данных Xquery, а также другие указания по оптимизации (необязательно), вы можете достичь наилучшей возможной производительности и наиболее эффективного хранения.</span><span class="sxs-lookup"><span data-stu-id="36051-117">If you specify the XQUERY keyword and the XQuery data type, and optionally other optimization hints, then you can achieve the best possible performance and the most efficient possible storage.</span></span> <span data-ttu-id="36051-118">Однако приведение может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="36051-118">However, a cast can fail.</span></span>  
  
-   <span data-ttu-id="36051-119">Если путь для индексирования снабжен ключевым словом SQL, путь сопоставляется с возвращаемым типом метода value() типа данных XML.</span><span class="sxs-lookup"><span data-stu-id="36051-119">When a path to index is annotated with the SQL keyword, the path matches the return type of the value() method of the XML data type.</span></span> <span data-ttu-id="36051-120">Укажите подходящий тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , то есть возвращаемый тип, который ожидается от метода value().</span><span class="sxs-lookup"><span data-stu-id="36051-120">Specify the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, which is the return type that you expect from the value() method.</span></span>  
  
 <span data-ttu-id="36051-121">Есть малозаметные различия между системой типов XML выражений Xquery и системой типов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , примененных к методу value() типа данных XML.</span><span class="sxs-lookup"><span data-stu-id="36051-121">There are subtle differences between the XQuery expressions XML type system and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type system applied to the value() method of the XML data type.</span></span> <span data-ttu-id="36051-122">Различия следующие:</span><span class="sxs-lookup"><span data-stu-id="36051-122">These differences include the following:</span></span>  
  
-   <span data-ttu-id="36051-123">Система типов Xquery учитывает конечные пробелы.</span><span class="sxs-lookup"><span data-stu-id="36051-123">The XQuery type system is aware of trailing spaces.</span></span> <span data-ttu-id="36051-124">Например, в соответствии с семантикой типов Xquery строки «abc» и «abc » не равны, тогда как в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] эти строки равны.</span><span class="sxs-lookup"><span data-stu-id="36051-124">For example, according to XQuery type semantics, the strings "abc" and "abc " are not equal, while in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] these strings are equal.</span></span>  
  
-   <span data-ttu-id="36051-125">Типы данных с плавающей запятой Xquery поддерживают специальные значения +/- нуль и +/- бесконечность.</span><span class="sxs-lookup"><span data-stu-id="36051-125">XQuery floating point data types support special values of +/- zero and +/- infinity.</span></span> <span data-ttu-id="36051-126">Эти особые значения не поддерживаются в типах данных с плавающей запятой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36051-126">These special values are not supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] floating point data types.</span></span>  
  
### <a name="xquery-types-in-untyped-xml"></a><span data-ttu-id="36051-127">Типы Xquery в нетипизированном XML</span><span class="sxs-lookup"><span data-stu-id="36051-127">XQuery Types in Untyped XML</span></span>  
  
-   <span data-ttu-id="36051-128">Типы XQuery сопоставляются с выражениями XQuery во всех методах типа данных XML, включая метод value().</span><span class="sxs-lookup"><span data-stu-id="36051-128">XQuery types match XQuery expressions in all methods of the XML data type including the value() method.</span></span>  
  
-   <span data-ttu-id="36051-129">Типы XQuery поддерживают такие указания оптимизации: node(), SINGLETON, DATA TYPE и MAXLENGTH.</span><span class="sxs-lookup"><span data-stu-id="36051-129">XQuery types support these optimization hints: node(), SINGLETON, DATA TYPE, and MAXLENGTH.</span></span>  
  
 <span data-ttu-id="36051-130">В выражениях Xquery с нетипизированным XML вы можете выбрать между двумя режимами работы.</span><span class="sxs-lookup"><span data-stu-id="36051-130">For XQuery expressions over untyped XML, you can choose between two modes of operation:</span></span>  
  
-   <span data-ttu-id="36051-131">**Режим сопоставления по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="36051-131">**Default mapping mode**.</span></span> <span data-ttu-id="36051-132">В этом режиме при создании селективного XML-индекса указывается только путь.</span><span class="sxs-lookup"><span data-stu-id="36051-132">In this mode, you specify only the path when creating a selective XML index.</span></span>  
  
-   <span data-ttu-id="36051-133">**Определяемый пользователем режим сопоставления**.</span><span class="sxs-lookup"><span data-stu-id="36051-133">**User-specified mapping mode**.</span></span> <span data-ttu-id="36051-134">В этом режиме указывается как путь, так и необязательные указания по оптимизации.</span><span class="sxs-lookup"><span data-stu-id="36051-134">In this mode, you specify both the path and optional optimization hints.</span></span>  
  
 <span data-ttu-id="36051-135">Режим сопоставления по умолчанию использует консервативный режим хранения, который всегда безопасен и универсален.</span><span class="sxs-lookup"><span data-stu-id="36051-135">The default mapping mode uses a conservative storage option which is always safe and general.</span></span> <span data-ttu-id="36051-136">Он может быть сопоставлен с любым типом выражения.</span><span class="sxs-lookup"><span data-stu-id="36051-136">It can match any expression type.</span></span> <span data-ttu-id="36051-137">Ограничением режима сопоставления по умолчанию является неоптимальная производительность, поскольку требуется увеличение количества приведений среды выполнения. Также будут недоступны вторичные индексы.</span><span class="sxs-lookup"><span data-stu-id="36051-137">A limitation of the default mapping mode is less than optimal performance, because an increased number of runtime casts are required, and secondary indexes are not available.</span></span>  
  
 <span data-ttu-id="36051-138">Ниже приведен пример селективного XML-индекса, созданного с сопоставлениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36051-138">Here is an example of a selective XML index created with default mappings.</span></span> <span data-ttu-id="36051-139">Для всех трех методов используется тип узла (**xs:untypedAtomic**) и количество элементов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36051-139">For all three paths, the default node type (**xs:untypedAtomic**) and cardinality are used.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_default  
ON Tbl(xmlcol)  
FOR  
(  
mypath01 =  '/a/b',  
mypath02 = '/a/b/c',  
mypath03 = '/a/b/d'  
)  
```  
  
 <span data-ttu-id="36051-140">Определяемый пользователем режим сопоставления позволяет указать тип и количество элементов для узла, чтобы получить более высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="36051-140">The user-specified mapping mode lets you specify a type and cardinality for the node to obtain better performance.</span></span> <span data-ttu-id="36051-141">Однако это повышение производительности достигается за счет снижения безопасности (поскольку приведения могут завершаться с ошибками) и универсальности (поскольку с селективным XML-индексом сопоставляется только заданный тип).</span><span class="sxs-lookup"><span data-stu-id="36051-141">However, this improved performance is achieved by giving up safety - because a cast can fail - and generality - because only the specified type is matched with the selective XML index.</span></span>  
  
 <span data-ttu-id="36051-142">Для нетипизированного XML поддерживаются следующие типы Xquery:</span><span class="sxs-lookup"><span data-stu-id="36051-142">The XQuery types supported for untyped XML case are:</span></span>  
  
-   <span data-ttu-id="36051-143">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="36051-143">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="36051-144">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="36051-144">**xs:double**</span></span>  
  
-   <span data-ttu-id="36051-145">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="36051-145">**xs:string**</span></span>  
  
-   <span data-ttu-id="36051-146">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="36051-146">**xs:date**</span></span>  
  
-   <span data-ttu-id="36051-147">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="36051-147">**xs:time**</span></span>  
  
-   <span data-ttu-id="36051-148">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="36051-148">**xs:dateTime**</span></span>  
  
 <span data-ttu-id="36051-149">Если тип не указан, предполагается, что узел имеет тип данных **xs:untypedAtomic** .</span><span class="sxs-lookup"><span data-stu-id="36051-149">If the type is not specified, the node is assumed to be of the **xs:untypedAtomic** data type.</span></span>  
  
 <span data-ttu-id="36051-150">Отображенный селективный XML-индекс вы можете оптимизировать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="36051-150">You can optimize the selective XML index shown in the following manner:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_optimized  
ON Tbl(xmlcol)  
FOR  
(  
mypath= '/a/b' as XQUERY 'node()',  
pathX = '/a/b/c' as XQUERY 'xs:double' SINGLETON,  
pathY = '/a/b/d' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
)  
-- mypath - Only the node value is needed; storage is saved.  
-- pathX - Performance is improved; secondary indexes are possible.  
-- pathY - Performance is improved; secondary indexes are possible; storage is saved.  
```  
  
### <a name="sql-server-types-in-untyped-xml"></a><span data-ttu-id="36051-151">Типы SQL Server в нетипизированном XML</span><span class="sxs-lookup"><span data-stu-id="36051-151">SQL Server Types in Untyped XML</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="36051-152">соответствуют возвращаемому значению метода value().</span><span class="sxs-lookup"><span data-stu-id="36051-152">types match the return value of the value() method.</span></span>  
  
-   <span data-ttu-id="36051-153">Типы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживают указание оптимизации SINGLETON.</span><span class="sxs-lookup"><span data-stu-id="36051-153">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types support this optimization hint: SINGLETON.</span></span>  
  
 <span data-ttu-id="36051-154">Указание типа обязательно для путей, возвращающих типы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36051-154">Specifying a type is mandatory for paths that return [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="36051-155">Необходимо использовать тот же тип [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который бы использовался в методе value().</span><span class="sxs-lookup"><span data-stu-id="36051-155">Use the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type that you would use in the value() method.</span></span>  
  
 <span data-ttu-id="36051-156">Обратите внимание на следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="36051-156">Consider the following query:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/d)[1]', 'NVARCHAR(200)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="36051-157">Указанный запрос возвращает значение из пути `/a/b/d` , упакованного в тип данных NVARCHAR(200), поэтому тип данных, указываемый для узла, является очевидным.</span><span class="sxs-lookup"><span data-stu-id="36051-157">The specified query returns a value from the path `/a/b/d` packed into an NVARCHAR(200) data type, so the data type to specify for the node is obvious.</span></span> <span data-ttu-id="36051-158">Однако нет схемы, в которой можно было бы указать количество элементов узла в нетипизированном XML.</span><span class="sxs-lookup"><span data-stu-id="36051-158">However there is no schema to specify the cardinality of the node in untyped XML.</span></span> <span data-ttu-id="36051-159">Чтобы указать, что узел `d` должен встречаться не более одного раза в родительском узле `b`, создайте селективный XML-индекс, в котором подсказка оптимизации SINGLETON используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="36051-159">To specify that node `d` appears at most once under its parent node `b`, create a selective XML index that uses the SINGLETON optimization hint as follows:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_US  
ON Tbl(xmlcol)  
FOR  
(  
node1223 = '/a/b/d' as SQL NVARCHAR(200) SINGLETON  
)  
```  
  

  
##  <a name="understanding-selective-xml-index-support-for-typed-xml"></a><a name="typed"></a> <span data-ttu-id="36051-160">Основные сведения о поддержке селективных XML-индексов для типизированного XML</span><span class="sxs-lookup"><span data-stu-id="36051-160">Understanding Selective XML Index support for typed XML</span></span>  
 <span data-ttu-id="36051-161">Типизированный XML в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] — это схема, связанная с данным XML-документом.</span><span class="sxs-lookup"><span data-stu-id="36051-161">Typed XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is a schema associated with a given XML document.</span></span> <span data-ttu-id="36051-162">Схема определяет общую структуру документа и типы узлов.</span><span class="sxs-lookup"><span data-stu-id="36051-162">The schema defines overall document structure and types of nodes.</span></span> <span data-ttu-id="36051-163">Если схема существует, то селективный XML-индекс применяет структуру схемы, когда пользователь повышает пути, поэтому нет необходимости указывать типы XQUERY для путей.</span><span class="sxs-lookup"><span data-stu-id="36051-163">If a schema exists, Selective XML Index applies the schema structure when the user promotes paths, so there is no need to specify the XQUERY types for paths.</span></span>  
  
 <span data-ttu-id="36051-164">Селективные XML-индексы поддерживают следующие типы XSD:</span><span class="sxs-lookup"><span data-stu-id="36051-164">Selective XML Index supports following XSD types:</span></span>  
  
-   <span data-ttu-id="36051-165">**xs:anyUri**</span><span class="sxs-lookup"><span data-stu-id="36051-165">**xs:anyUri**</span></span>  
  
-   <span data-ttu-id="36051-166">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="36051-166">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="36051-167">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="36051-167">**xs:date**</span></span>  
  
-   <span data-ttu-id="36051-168">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="36051-168">**xs:dateTime**</span></span>  
  
-   <span data-ttu-id="36051-169">**xs:day**</span><span class="sxs-lookup"><span data-stu-id="36051-169">**xs:day**</span></span>  
  
-   <span data-ttu-id="36051-170">**xs:decimal**</span><span class="sxs-lookup"><span data-stu-id="36051-170">**xs:decimal**</span></span>  
  
-   <span data-ttu-id="36051-171">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="36051-171">**xs:double**</span></span>  
  
-   <span data-ttu-id="36051-172">**xs:float**</span><span class="sxs-lookup"><span data-stu-id="36051-172">**xs:float**</span></span>  
  
-   <span data-ttu-id="36051-173">**xs:int**</span><span class="sxs-lookup"><span data-stu-id="36051-173">**xs:int**</span></span>  
  
-   <span data-ttu-id="36051-174">**xs:integer**</span><span class="sxs-lookup"><span data-stu-id="36051-174">**xs:integer**</span></span>  
  
-   <span data-ttu-id="36051-175">**xs:language**</span><span class="sxs-lookup"><span data-stu-id="36051-175">**xs:language**</span></span>  
  
-   <span data-ttu-id="36051-176">**xs:long**</span><span class="sxs-lookup"><span data-stu-id="36051-176">**xs:long**</span></span>  
  
-   <span data-ttu-id="36051-177">**xs:name**</span><span class="sxs-lookup"><span data-stu-id="36051-177">**xs:name**</span></span>  
  
-   <span data-ttu-id="36051-178">**xs:NCName**</span><span class="sxs-lookup"><span data-stu-id="36051-178">**xs:NCName**</span></span>  
  
-   <span data-ttu-id="36051-179">**xs:negativeInteger**</span><span class="sxs-lookup"><span data-stu-id="36051-179">**xs:negativeInteger**</span></span>  
  
-   <span data-ttu-id="36051-180">**xs:nmtoken**</span><span class="sxs-lookup"><span data-stu-id="36051-180">**xs:nmtoken**</span></span>  
  
-   <span data-ttu-id="36051-181">**xs:nonNegativeInteger**</span><span class="sxs-lookup"><span data-stu-id="36051-181">**xs:nonNegativeInteger**</span></span>  
  
-   <span data-ttu-id="36051-182">**xs:nonPositiveInteger**</span><span class="sxs-lookup"><span data-stu-id="36051-182">**xs:nonPositiveInteger**</span></span>  
  
-   <span data-ttu-id="36051-183">**xs:positiveInteger**</span><span class="sxs-lookup"><span data-stu-id="36051-183">**xs:positiveInteger**</span></span>  
  
-   <span data-ttu-id="36051-184">**xs:qname**</span><span class="sxs-lookup"><span data-stu-id="36051-184">**xs:qname**</span></span>  
  
-   <span data-ttu-id="36051-185">**xs:short**</span><span class="sxs-lookup"><span data-stu-id="36051-185">**xs:short**</span></span>  
  
-   <span data-ttu-id="36051-186">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="36051-186">**xs:string**</span></span>  
  
-   <span data-ttu-id="36051-187">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="36051-187">**xs:time**</span></span>  
  
-   <span data-ttu-id="36051-188">**xs:token**</span><span class="sxs-lookup"><span data-stu-id="36051-188">**xs:token**</span></span>  
  
-   <span data-ttu-id="36051-189">**xs:unsignedByte**</span><span class="sxs-lookup"><span data-stu-id="36051-189">**xs:unsignedByte**</span></span>  
  
-   <span data-ttu-id="36051-190">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="36051-190">**xs:unsignedInt**</span></span>  
  
-   <span data-ttu-id="36051-191">**xs:unsignedLong**</span><span class="sxs-lookup"><span data-stu-id="36051-191">**xs:unsignedLong**</span></span>  
  
-   <span data-ttu-id="36051-192">**xs:unsignedShort**</span><span class="sxs-lookup"><span data-stu-id="36051-192">**xs:unsignedShort**</span></span>  
  
 <span data-ttu-id="36051-193">Если селективный XML-индекс создается для документа, имеющего связанную с ним схему, то при указании типа XQUERY при создании или изменении индекса будет возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="36051-193">When Selective XML Index is created over a document that has schema associated with it, specifying a XQUERY type at index creation or altering returns an error.</span></span> <span data-ttu-id="36051-194">Пользователь может использовать заметки типов SQL в части повышения пути.</span><span class="sxs-lookup"><span data-stu-id="36051-194">The user can use SQL type annotations in the path promotion part.</span></span> <span data-ttu-id="36051-195">Тип SQL должен быть допустимым преобразованием из типа XSD, определенного в схеме, иначе будет выдана ошибка.</span><span class="sxs-lookup"><span data-stu-id="36051-195">The SQL type must be a valid conversion from the XSD type defined in the schema, or an error is thrown.</span></span> <span data-ttu-id="36051-196">Поддерживаются все типы SQL, имеющие адекватное представление в XSD, за исключением типов данных даты-времени.</span><span class="sxs-lookup"><span data-stu-id="36051-196">All SQL types that have adequate representation in XSD are supported, with an exception of date/time types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36051-197">Селективный индекс используется, если в повышении пути селективного XML-индекса указан тот же тип, что и в возвращаемом значении метода value().</span><span class="sxs-lookup"><span data-stu-id="36051-197">The selective index is used if the type specified in the Selective XML Index path promotion is the same as the value() method return value.</span></span>  
  
 <span data-ttu-id="36051-198">Следующие указания оптимизации можно использовать с типизированными XML-документами.</span><span class="sxs-lookup"><span data-stu-id="36051-198">The following optimization hints can be used with typed XML documents:</span></span>  
  
-   <span data-ttu-id="36051-199">Указание по оптимизации node().</span><span class="sxs-lookup"><span data-stu-id="36051-199">node() optimization hint.</span></span>  
  
-   <span data-ttu-id="36051-200">Указание оптимизации MAXLENGTH можно использовать с типами xs:string, чтобы сократить индексируемое значение.</span><span class="sxs-lookup"><span data-stu-id="36051-200">MAXLENGTH optimization hint can be used with xs:string types to shorten the indexed value.</span></span>  
  
 <span data-ttu-id="36051-201">Дополнительные сведения об указаниях оптимизации см. в разделе [Задание указаний по оптимизации](#hints).</span><span class="sxs-lookup"><span data-stu-id="36051-201">For more information about optimization hints, see [Specifying Optimization Hints](#hints).</span></span>  
  
##  <a name="specifying-paths"></a><a name="paths"></a> <span data-ttu-id="36051-202">Указание путей</span><span class="sxs-lookup"><span data-stu-id="36051-202">Specifying Paths</span></span>  
 <span data-ttu-id="36051-203">Селективный XML-индекс позволяет индексировать только подмножество узлов из сохраненных XML-данных, значимое для запросов, которые планируется выполнять.</span><span class="sxs-lookup"><span data-stu-id="36051-203">A selective XML index lets you index only a subset of nodes from the stored XML data that are relevant for the queries that you expect to run.</span></span> <span data-ttu-id="36051-204">Когда подмножество значимых узлов намного меньше, чем общее количество узлов в XML-документе, селективный XML-индекс сохраняет только значимые узлы.</span><span class="sxs-lookup"><span data-stu-id="36051-204">When the subset of relevant nodes is much smaller than the total number of nodes in the XML document, the selective XML index stores only the relevant nodes.</span></span> <span data-ttu-id="36051-205">Для эффективного использования селективного XML-индекса необходимо определить нужное подмножество узлов для индексирования.</span><span class="sxs-lookup"><span data-stu-id="36051-205">To benefit from a selective XML index, identify the correct subset of nodes to index.</span></span>  
  
### <a name="choosing-the-nodes-to-index"></a><span data-ttu-id="36051-206">Выбор узлов для индексирования</span><span class="sxs-lookup"><span data-stu-id="36051-206">Choosing the nodes to index</span></span>  
 <span data-ttu-id="36051-207">Следующие два простых принципа позволяют определить нужное подмножество узлов, которые необходимо добавить в селективный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="36051-207">You can use the following two simple principles to identify the correct subset of nodes to add to a selective XML index.</span></span>  
  
1.  <span data-ttu-id="36051-208">**Принцип 1**. Чтобы оценить заданное выражение XQuery, необходимо проиндексировать все узлы, подлежащие изучению.</span><span class="sxs-lookup"><span data-stu-id="36051-208">**Principle 1**: To evaluate a given XQuery expression, index all nodes that you need to examine.</span></span>  
  
    -   <span data-ttu-id="36051-209">Индексируйте все узлы, существование или значения которых используются в выражении XQuery.</span><span class="sxs-lookup"><span data-stu-id="36051-209">Index all nodes whose existence or value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="36051-210">Индексируйте все узлы в выражении XQuery, к которым применяются предикаты XQuery.</span><span class="sxs-lookup"><span data-stu-id="36051-210">Index all nodes in the XQuery expression on which XQuery predicates are applied.</span></span>  
  
     <span data-ttu-id="36051-211">Рассмотрим следующий простой запрос к [образцу XML-документа](#sample) в данном разделе:</span><span class="sxs-lookup"><span data-stu-id="36051-211">Consider the following simple query over the [sample XML document](#sample) in this topic:</span></span>  
  
    ```sql  
    SELECT T.record FROM myXMLTable T  
    WHERE T.xmldata.exist('/a/b[./c = "43"]') = 1  
    ```  
  
     <span data-ttu-id="36051-212">Для возвращения экземпляров XML, которые удовлетворяют запросу, селективному XML-индексу необходимо просматривать 2 узла в каждом из экземпляров XML.</span><span class="sxs-lookup"><span data-stu-id="36051-212">In order to return the XML instances that satisfy this query, a selective XML index needs to examine two nodes in every XML instance:</span></span>  
  
    -   <span data-ttu-id="36051-213">Узел `c`, так как его значение используется в выражении XQuery.</span><span class="sxs-lookup"><span data-stu-id="36051-213">Node `c`, because its value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="36051-214">Узел `b`, поскольку предикат применяется на узел`b` в выражении XQuery.</span><span class="sxs-lookup"><span data-stu-id="36051-214">Node `b`, because a predicate is applied over node`b` in the XQuery expression.</span></span>  
  
2.  <span data-ttu-id="36051-215">**Принцип 2**. Для достижения наилучшей производительности рекомендуется индексировать все узлы, необходимые для вычисления заданного выражения XQuery.</span><span class="sxs-lookup"><span data-stu-id="36051-215">**Principle 2**: For best performance, index all nodes that are required to evaluate a given XQuery expression.</span></span> <span data-ttu-id="36051-216">Если индексируются только некоторые узлы, селективный XML-индекс улучшает оценку вложенных выражений, содержащих только индексированные узлы.</span><span class="sxs-lookup"><span data-stu-id="36051-216">If you index only some of the nodes, then the selective XML index improves the evaluation of sub-expressions that include only indexed nodes.</span></span>  
  
 <span data-ttu-id="36051-217">Для улучшения производительности инструкции SELECT, описанной выше, вы можете создать следующий селективный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="36051-217">To improve the performance of the SELECT statement shown above, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX simple_sxi  
ON Tbl(xmlcol)  
FOR  
(  
    path123 =  '/a/b',  
    path124 =  '/a/b/c'  
)  
```  
  
### <a name="indexing-identical-paths"></a><span data-ttu-id="36051-218">Индексирование одинаковых путей</span><span class="sxs-lookup"><span data-stu-id="36051-218">Indexing identical paths</span></span>  
 <span data-ttu-id="36051-219">Невозможно повысить уровень одинаковых путей в качестве того же типа данных с другими именами пути.</span><span class="sxs-lookup"><span data-stu-id="36051-219">You cannot promote identical paths as the same data type under different path names.</span></span> <span data-ttu-id="36051-220">Например, следующий запрос формирует ошибку, поскольку пути `pathOne` и `pathTwo` идентичны:</span><span class="sxs-lookup"><span data-stu-id="36051-220">For example, the following query raises an error, because `pathOne` and `pathTwo` are identical:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:string',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
 <span data-ttu-id="36051-221">Однако вы можете повысить уровень одинаковых путей в качестве различных типов данных с разными именами.</span><span class="sxs-lookup"><span data-stu-id="36051-221">However, you can promote identical paths as different data types with different names.</span></span> <span data-ttu-id="36051-222">Например, следующий запрос теперь является допустимым, поскольку типы данных отличаются:</span><span class="sxs-lookup"><span data-stu-id="36051-222">For example, the following query is now acceptable, because the data types are different:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:double',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
### <a name="examples"></a><span data-ttu-id="36051-223">Примеры</span><span class="sxs-lookup"><span data-stu-id="36051-223">Examples</span></span>  
 <span data-ttu-id="36051-224">Ниже приведены дополнительные примеры выбора правильных узлов для индексации для различных типов XQuery.</span><span class="sxs-lookup"><span data-stu-id="36051-224">Here are some additional examples of selecting the correct nodes to index for different XQuery types.</span></span>  
  
 <span data-ttu-id="36051-225">**Пример 1**</span><span class="sxs-lookup"><span data-stu-id="36051-225">**Example 1**</span></span>  
  
 <span data-ttu-id="36051-226">Вот простой запрос Xquery, в котором используется метод exist():</span><span class="sxs-lookup"><span data-stu-id="36051-226">Here is a simple XQuery that uses the exist() method:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e/h') = 1  
```  
  
 <span data-ttu-id="36051-227">В следующей таблице показаны узлы, которые должны быть индексированы для того, чтобы данный запрос мог использовать селективный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="36051-227">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="36051-228">Узел, который необходимо включить в индекс</span><span class="sxs-lookup"><span data-stu-id="36051-228">Node to include in the index</span></span>|<span data-ttu-id="36051-229">Причина для индексирования этого узла</span><span class="sxs-lookup"><span data-stu-id="36051-229">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="36051-230">**/a/b/c/d/e/h**</span><span class="sxs-lookup"><span data-stu-id="36051-230">**/a/b/c/d/e/h**</span></span>|<span data-ttu-id="36051-231">Наличие узла `h` вычисляется в методе exist().</span><span class="sxs-lookup"><span data-stu-id="36051-231">The existence of node `h` is evaluated in the exist() method.</span></span>|  
  
 <span data-ttu-id="36051-232">**Пример 2**</span><span class="sxs-lookup"><span data-stu-id="36051-232">**Example 2**</span></span>  
  
 <span data-ttu-id="36051-233">Вот более сложный вариант предыдущего запроса XQuery с примененным предикатом:</span><span class="sxs-lookup"><span data-stu-id="36051-233">Here is a more complex variation of the previous XQuery, with a predicate applied:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e[./f = "SQL"]') = 1  
```  
  
 <span data-ttu-id="36051-234">В следующей таблице показаны узлы, которые должны быть индексированы для того, чтобы данный запрос мог использовать селективный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="36051-234">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="36051-235">Узел, который необходимо включить в индекс</span><span class="sxs-lookup"><span data-stu-id="36051-235">Node to include in the index</span></span>|<span data-ttu-id="36051-236">Причина для индексирования этого узла</span><span class="sxs-lookup"><span data-stu-id="36051-236">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="36051-237">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="36051-237">**/a/b/c/d/e**</span></span>|<span data-ttu-id="36051-238">Предикат применяется для узла `e`.</span><span class="sxs-lookup"><span data-stu-id="36051-238">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="36051-239">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="36051-239">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="36051-240">Значение узла `f` вычисляется внутри предиката.</span><span class="sxs-lookup"><span data-stu-id="36051-240">The value of node `f` is evaluated inside the predicate.</span></span>|  
  
 <span data-ttu-id="36051-241">**Пример 3**</span><span class="sxs-lookup"><span data-stu-id="36051-241">**Example 3**</span></span>  
  
 <span data-ttu-id="36051-242">Вот более сложный запрос с предложением value():</span><span class="sxs-lookup"><span data-stu-id="36051-242">Here is a more complex query with a value() clause:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/c/d/e[./f = "SQL"]/g)[1]', 'nvarchar(100)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="36051-243">В следующей таблице показаны узлы, которые должны быть индексированы для того, чтобы данный запрос мог использовать селективный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="36051-243">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="36051-244">Узел, который необходимо включить в индекс</span><span class="sxs-lookup"><span data-stu-id="36051-244">Node to include in the index</span></span>|<span data-ttu-id="36051-245">Причина для индексирования этого узла</span><span class="sxs-lookup"><span data-stu-id="36051-245">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="36051-246">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="36051-246">**/a/b/c/d/e**</span></span>|<span data-ttu-id="36051-247">Предикат применяется для узла `e`.</span><span class="sxs-lookup"><span data-stu-id="36051-247">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="36051-248">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="36051-248">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="36051-249">Значение узла `f` вычисляется внутри предиката.</span><span class="sxs-lookup"><span data-stu-id="36051-249">The value of node `f` is evaluated inside the predicate.</span></span>|  
|<span data-ttu-id="36051-250">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="36051-250">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="36051-251">Значение узла `g` возвращается методом value().</span><span class="sxs-lookup"><span data-stu-id="36051-251">The value of node `g` is returned by the value() method.</span></span>|  
  
 <span data-ttu-id="36051-252">**Пример 4**</span><span class="sxs-lookup"><span data-stu-id="36051-252">**Example 4**</span></span>  
  
 <span data-ttu-id="36051-253">Вот запрос, в котором предложение FLWOR используется внутри предложения exist().</span><span class="sxs-lookup"><span data-stu-id="36051-253">Here is a query that uses a FLWOR clause inside an exist() clause.</span></span> <span data-ttu-id="36051-254">(Имя FLWOR образуется из 5 предложений, которые могут составлять выражение FLWOR в XQuery: for, let, where, order by и return.)</span><span class="sxs-lookup"><span data-stu-id="36051-254">(The name FLWOR comes from the five clauses that can make up an XQuery FLWOR expression: for, let, where, order by, and return.)</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('  
  For $x in /a/b/c/d/e  
  Where $x/f = "SQL"  
  Return $x/g  
') = 1  
```  
  
 <span data-ttu-id="36051-255">В следующей таблице показаны узлы, которые должны быть индексированы для того, чтобы данный запрос мог использовать селективный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="36051-255">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="36051-256">Узел, который необходимо включить в индекс</span><span class="sxs-lookup"><span data-stu-id="36051-256">Node to include in the index</span></span>|<span data-ttu-id="36051-257">Причина для индексирования этого узла</span><span class="sxs-lookup"><span data-stu-id="36051-257">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="36051-258">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="36051-258">**/a/b/c/d/e**</span></span>|<span data-ttu-id="36051-259">Наличие узла `e` вычисляется в предложении FLWOR.</span><span class="sxs-lookup"><span data-stu-id="36051-259">The existence of node `e` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="36051-260">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="36051-260">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="36051-261">Значение узла `f` вычисляется в предложении FLWOR.</span><span class="sxs-lookup"><span data-stu-id="36051-261">The value of node `f` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="36051-262">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="36051-262">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="36051-263">Наличие узла `g` вычисляется методом exist().</span><span class="sxs-lookup"><span data-stu-id="36051-263">The existence of node `g` is evaluated by the exist() method.</span></span>|  
  

  
##  <a name="specifying-optimization-hints"></a><a name="hints"></a> <span data-ttu-id="36051-264">Задание указаний по оптимизации</span><span class="sxs-lookup"><span data-stu-id="36051-264">Specifying Optimization Hints</span></span>  
 <span data-ttu-id="36051-265">Необязательные указания оптимизации вы можете использовать для указания дополнительных подробностей сопоставления для узла, индексированного селективным XML-индексом.</span><span class="sxs-lookup"><span data-stu-id="36051-265">You can use optional optimization hints to specify additional mapping details for a node indexed by a selective XML index.</span></span> <span data-ttu-id="36051-266">Например, вы можете указать тип данных, количество элементов узла, а также некоторые сведения о структуре данных.</span><span class="sxs-lookup"><span data-stu-id="36051-266">For example, you can specify the data type and cardinality of the node, and certain information about the structure of the data.</span></span> <span data-ttu-id="36051-267">Эта дополнительная информация поддерживает более эффективное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="36051-267">This additional information supports better mapping.</span></span> <span data-ttu-id="36051-268">Она также позволяет получить улучшение производительности, эффективности хранения или и того и другого.</span><span class="sxs-lookup"><span data-stu-id="36051-268">It also results in improvements in performance or savings in storage, or both.</span></span>  
  
 <span data-ttu-id="36051-269">Использование указаний оптимизации необязательно.</span><span class="sxs-lookup"><span data-stu-id="36051-269">The use of optimization hints is optional.</span></span> <span data-ttu-id="36051-270">Всегда вы можете принять сопоставления по умолчанию, которые являются надежными, но не обеспечивают оптимальную производительность и эффективность хранения.</span><span class="sxs-lookup"><span data-stu-id="36051-270">You can always accept the default mappings, which are reliable but may not provide optimal performance and storage.</span></span>  
  
 <span data-ttu-id="36051-271">Некоторые указания по оптимизации (например, указание SINGLETON) накладывают ограничения на данные.</span><span class="sxs-lookup"><span data-stu-id="36051-271">Some optimization hints - for example, the SINGLETON hint - introduce constraints over your data.</span></span> <span data-ttu-id="36051-272">В некоторых случаях, когда эти ограничения не выполняются, могут возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="36051-272">In some cases, errors may be raised when those constraints are not met.</span></span>  
  
### <a name="benefits-of-optimization-hints"></a><span data-ttu-id="36051-273">Преимущества использования указаний оптимизации</span><span class="sxs-lookup"><span data-stu-id="36051-273">Benefits of Optimization Hints</span></span>  
 <span data-ttu-id="36051-274">В следующей таблице приведены указания по оптимизации, которые поддерживают более эффективное хранение или улучшение в производительности.</span><span class="sxs-lookup"><span data-stu-id="36051-274">The following table identifies the optimization hints that support more efficient storage or improved performance.</span></span>  
  
|<span data-ttu-id="36051-275">Указание по оптимизации</span><span class="sxs-lookup"><span data-stu-id="36051-275">Optimization hint</span></span>|<span data-ttu-id="36051-276">Более эффективное хранение</span><span class="sxs-lookup"><span data-stu-id="36051-276">More efficient storage</span></span>|<span data-ttu-id="36051-277">повышение производительности.</span><span class="sxs-lookup"><span data-stu-id="36051-277">Improved performance</span></span>|  
|-----------------------|----------------------------|--------------------------|  
|<span data-ttu-id="36051-278">**node()**</span><span class="sxs-lookup"><span data-stu-id="36051-278">**node()**</span></span>|<span data-ttu-id="36051-279">Да</span><span class="sxs-lookup"><span data-stu-id="36051-279">Yes</span></span>|<span data-ttu-id="36051-280">Нет</span><span class="sxs-lookup"><span data-stu-id="36051-280">No</span></span>|  
|<span data-ttu-id="36051-281">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="36051-281">**SINGLETON**</span></span>|<span data-ttu-id="36051-282">Нет</span><span class="sxs-lookup"><span data-stu-id="36051-282">No</span></span>|<span data-ttu-id="36051-283">Да</span><span class="sxs-lookup"><span data-stu-id="36051-283">Yes</span></span>|  
|<span data-ttu-id="36051-284">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="36051-284">**DATA TYPE**</span></span>|<span data-ttu-id="36051-285">Да</span><span class="sxs-lookup"><span data-stu-id="36051-285">Yes</span></span>|<span data-ttu-id="36051-286">Да</span><span class="sxs-lookup"><span data-stu-id="36051-286">Yes</span></span>|  
|<span data-ttu-id="36051-287">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="36051-287">**MAXLENGTH**</span></span>|<span data-ttu-id="36051-288">Да</span><span class="sxs-lookup"><span data-stu-id="36051-288">Yes</span></span>|<span data-ttu-id="36051-289">Да</span><span class="sxs-lookup"><span data-stu-id="36051-289">Yes</span></span>|  
  
### <a name="optimization-hints-and-data-types"></a><span data-ttu-id="36051-290">Указания по оптимизации и типы данных</span><span class="sxs-lookup"><span data-stu-id="36051-290">Optimization Hints and Data Types</span></span>  
 <span data-ttu-id="36051-291">Узлы вы можете индексировать как типы данных XQuery или как типы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36051-291">You can index nodes as XQuery data types or as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="36051-292">В следующей таблице показано, какие указания оптимизации поддерживаются для каждого типа данных.</span><span class="sxs-lookup"><span data-stu-id="36051-292">The following table shows which optimization hints are supported with each data type.</span></span>  
  
|<span data-ttu-id="36051-293">Указание по оптимизации</span><span class="sxs-lookup"><span data-stu-id="36051-293">Optimization hint</span></span>|<span data-ttu-id="36051-294">Типы данных XQuery</span><span class="sxs-lookup"><span data-stu-id="36051-294">XQuery data types</span></span>|<span data-ttu-id="36051-295">Типы данных SQL</span><span class="sxs-lookup"><span data-stu-id="36051-295">SQL data types</span></span>|  
|-----------------------|-----------------------|--------------------|  
|<span data-ttu-id="36051-296">**node()**</span><span class="sxs-lookup"><span data-stu-id="36051-296">**node()**</span></span>|<span data-ttu-id="36051-297">Да</span><span class="sxs-lookup"><span data-stu-id="36051-297">Yes</span></span>|<span data-ttu-id="36051-298">Нет</span><span class="sxs-lookup"><span data-stu-id="36051-298">No</span></span>|  
|<span data-ttu-id="36051-299">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="36051-299">**SINGLETON**</span></span>|<span data-ttu-id="36051-300">Да</span><span class="sxs-lookup"><span data-stu-id="36051-300">Yes</span></span>|<span data-ttu-id="36051-301">Да</span><span class="sxs-lookup"><span data-stu-id="36051-301">Yes</span></span>|  
|<span data-ttu-id="36051-302">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="36051-302">**DATA TYPE**</span></span>|<span data-ttu-id="36051-303">Да</span><span class="sxs-lookup"><span data-stu-id="36051-303">Yes</span></span>|<span data-ttu-id="36051-304">Нет</span><span class="sxs-lookup"><span data-stu-id="36051-304">No</span></span>|  
|<span data-ttu-id="36051-305">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="36051-305">**MAXLENGTH**</span></span>|<span data-ttu-id="36051-306">Да</span><span class="sxs-lookup"><span data-stu-id="36051-306">Yes</span></span>|<span data-ttu-id="36051-307">Нет</span><span class="sxs-lookup"><span data-stu-id="36051-307">No</span></span>|  
  
### <a name="node-optimization-hint"></a><span data-ttu-id="36051-308">Указание по оптимизации node()</span><span class="sxs-lookup"><span data-stu-id="36051-308">node() optimization hint</span></span>  
 <span data-ttu-id="36051-309">Область применения: Типы данных XQuery</span><span class="sxs-lookup"><span data-stu-id="36051-309">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="36051-310">Вы можете использовать оптимизацию node(), чтобы указать узел, значение которого не требуется для вычисления обычного запроса.</span><span class="sxs-lookup"><span data-stu-id="36051-310">You can use the node() optimization to specify a node whose value is not required to evaluate the typical query.</span></span> <span data-ttu-id="36051-311">Это указание снижает требования к хранилищу, поскольку обычному запросу необходимо вычислить только существование узла.</span><span class="sxs-lookup"><span data-stu-id="36051-311">This hint reduces storage requirements when the typical query only has to evaluate the existence of the node.</span></span> <span data-ttu-id="36051-312">(По умолчанию селективный XML-индекс хранит значения всех повышенных узлов, за исключением сложных типов узлов.)</span><span class="sxs-lookup"><span data-stu-id="36051-312">(By default, a selective XML index stores the value for all promoted nodes, except complex node types.)</span></span>  
  
 <span data-ttu-id="36051-313">Рассмотрим следующий пример:</span><span class="sxs-lookup"><span data-stu-id="36051-313">Consider the following example:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b[./c=5]') = 1  
```  
  
 <span data-ttu-id="36051-314">Для использования селективного XML-индекса для оценки этого запроса повысьте узлы `b` и `c`.</span><span class="sxs-lookup"><span data-stu-id="36051-314">To use a selective XML index to evaluate this query, promote nodes `b` and `c`.</span></span> <span data-ttu-id="36051-315">Однако, поскольку значение узла `b` не требуется, вы можете использовать указание node() со следующим синтаксисом:</span><span class="sxs-lookup"><span data-stu-id="36051-315">However, since the value of node `b` is not required, you can use the node() hint with the following syntax:</span></span>  
  
 `/a/b/ as node()`  
  
 <span data-ttu-id="36051-316">Если для запроса необходимо значение узла, который был индексирован с указанием node(), селективный XML-индекс использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="36051-316">If a query requires the value of a node that has been indexed with the node() hint, then the selective XML index cannot be used.</span></span>  
  
### <a name="singleton-optimization-hint"></a><span data-ttu-id="36051-317">Указание по оптимизации SINGLETON</span><span class="sxs-lookup"><span data-stu-id="36051-317">SINGLETON optimization hint</span></span>  
 <span data-ttu-id="36051-318">Область применения: Типы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или XQuery</span><span class="sxs-lookup"><span data-stu-id="36051-318">Applies to: XQuery or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types</span></span>  
  
 <span data-ttu-id="36051-319">Указание по оптимизации SINGLETON указывает количество элементов узла.</span><span class="sxs-lookup"><span data-stu-id="36051-319">The SINGLETON optimization hint specifies the cardinality of a node.</span></span> <span data-ttu-id="36051-320">Это указание повышает производительность запросов, поскольку известно, что узел отображается максимум один раз в его родителе или предке.</span><span class="sxs-lookup"><span data-stu-id="36051-320">This hint improves query performance since it is known in advance that a node appears at most one time within its parent or ancestor.</span></span>  
  
 <span data-ttu-id="36051-321">Рассмотрим [образец XML-документа](#sample) в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="36051-321">Consider the [sample XML document](#sample) in this topic.</span></span>  
  
 <span data-ttu-id="36051-322">Для использования селективного XML-индекса в запросе к этому документу вы можете задать указание SINGLETON для узла `d` , поскольку он встречается максимум один раз в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="36051-322">To use a selective XML index to query this document, you can specify the SINGLETON hint for node `d` since it appears at most one time within its parent.</span></span>  
  
 <span data-ttu-id="36051-323">Если было задано указание SINGLETON, а узел встречается более одного раза в его родителе или предке, то при создании индекса (для существующих данных) или при выполнении запроса (для новых данных) возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="36051-323">If the SINGLETON hint has been specified, but a node appears more than one time within its parent or ancestor, then an error is raised when you create the index (for existing data) or when you run a query (for new data).</span></span>  
  
### <a name="data-type-optimization-hint"></a><span data-ttu-id="36051-324">Указание по оптимизации DATA TYPE</span><span class="sxs-lookup"><span data-stu-id="36051-324">DATA TYPE optimization hint</span></span>  
 <span data-ttu-id="36051-325">Область применения: Типы данных XQuery</span><span class="sxs-lookup"><span data-stu-id="36051-325">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="36051-326">Указание по оптимизации DATA TYPE позволяет задать тип данных XQuery или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для индексированного узла.</span><span class="sxs-lookup"><span data-stu-id="36051-326">The DATA TYPE optimization hint lets you specify an XQuery or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for the indexed node.</span></span> <span data-ttu-id="36051-327">Тип данных используется для столбца в таблице данных селективного XML-индекса, соответствующего индексированному узлу.</span><span class="sxs-lookup"><span data-stu-id="36051-327">The data type is used for the column in the data table of the selective XML index that corresponds to the indexed node.</span></span>  
  
 <span data-ttu-id="36051-328">Если приведение существующего значения в указанный тип данных завершается ошибкой, операция вставки (в индекс) не завершается ошибкой, однако в таблицу данных индекса вставляется значение NULL.</span><span class="sxs-lookup"><span data-stu-id="36051-328">When casting an existing value to the specified data type fails, the insert operation (into the index) does not fail; however, a null value is inserted into the data table of the index.</span></span>  
  
### <a name="maxlength-optimization-hint"></a><span data-ttu-id="36051-329">Указание по оптимизации MAXLENGTH</span><span class="sxs-lookup"><span data-stu-id="36051-329">MAXLENGTH optimization hint</span></span>  
 <span data-ttu-id="36051-330">Область применения: Типы данных XQuery</span><span class="sxs-lookup"><span data-stu-id="36051-330">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="36051-331">Указание по оптимизации MAXLENGTH позволяет ограничить длину данных xs:string.</span><span class="sxs-lookup"><span data-stu-id="36051-331">The MAXLENGTH optimization hint lets you limit the length of xs:string data.</span></span> <span data-ttu-id="36051-332">Указание MAXLENGTH несущественно для типов данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , поскольку длина указывается при указании типов данных VARCHAR или NVARCHAR.</span><span class="sxs-lookup"><span data-stu-id="36051-332">MAXLENGTH is not relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types since you specify the length when you specify the VARCHAR or NVARCHAR date types.</span></span>  
  
 <span data-ttu-id="36051-333">Если существующая строка длиннее значения MAXLENGTH, вставка этого значения в индекс завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="36051-333">When an existing string is longer than the specified MAXLENGTH, then inserting that value into the index fails.</span></span>  
  

  
##  <a name="sample-xml-document-for-examples"></a><a name="sample"></a> <span data-ttu-id="36051-334">Образец XML-документа для примеров</span><span class="sxs-lookup"><span data-stu-id="36051-334">Sample XML Document for Examples</span></span>  
 <span data-ttu-id="36051-335">Следующий образец XML-документа указывается в примерах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="36051-335">The following sample XML document is referenced in the examples in this topic:</span></span>  
  
```xml  
<a>  
    <b>  
         <c atc="aa">10</c>  
         <c atc="bb">15</c>  
         <d atd1="dd" atd2="ddd">md </d>  
    </b>  
     <b>  
        <c></c>  
        <c atc="">117</c>  
     </b>  
</a>  
```  
  

  
## <a name="see-also"></a><span data-ttu-id="36051-336">См. также:</span><span class="sxs-lookup"><span data-stu-id="36051-336">See Also</span></span>  
 <span data-ttu-id="36051-337">[Выборочный XML-индекс (SXI)](../xml/selective-xml-indexes-sxi.md) </span><span class="sxs-lookup"><span data-stu-id="36051-337">[Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span></span>  
 [<span data-ttu-id="36051-338">Создание, изменение и удаление селективных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="36051-338">Create, Alter, and Drop Selective XML Indexes</span></span>](../xml/create-alter-and-drop-selective-xml-indexes.md)  
  
  
