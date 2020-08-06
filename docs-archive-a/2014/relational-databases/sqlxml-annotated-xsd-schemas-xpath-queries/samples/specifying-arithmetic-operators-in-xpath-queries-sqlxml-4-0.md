---
title: Указание арифметических операторов в запросах XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- arithmetic operators
- XPath operators [SQLXML]
- XPath queries [SQLXML], arithmetic operators
- operators [SQLXML]
ms.assetid: fdfbc87d-759f-4abc-acf5-a21de01f78d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 904f3b920029d45d1b72641a19e2ac07befd4def
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655004"
---
# <a name="specifying-arithmetic-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="da4a4-102">Задание арифметических операторов в запросах XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="da4a4-102">Specifying Arithmetic Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="da4a4-103">В следующем примере показано, как в запросах XPath указывать арифметические операторы.</span><span class="sxs-lookup"><span data-stu-id="da4a4-103">The following example shows how arithmetic operators are specified in XPath queries.</span></span> <span data-ttu-id="da4a4-104">В этом примере задается запрос XPath к схеме сопоставления, содержащейся в файле SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="da4a4-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="da4a4-105">Дополнительные сведения об этом образце схемы см. в разделе [Пример схемы XSD с заметками для XPath-примеров &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="da4a4-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="da4a4-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="da4a4-106">Examples</span></span>  
  
### <a name="a-specify-the--arithmetic-operator"></a><span data-ttu-id="da4a4-107">A.</span><span class="sxs-lookup"><span data-stu-id="da4a4-107">A.</span></span> <span data-ttu-id="da4a4-108">Указание арифметического оператора \*</span><span class="sxs-lookup"><span data-stu-id="da4a4-108">Specify the \* arithmetic operator</span></span>  
 <span data-ttu-id="da4a4-109">Этот запрос XPath возвращает **\<OrderDetail>** элементы, которые соответствуют заданному предикату:</span><span class="sxs-lookup"><span data-stu-id="da4a4-109">This XPath query returns **\<OrderDetail>** elements that satisfy the predicate specified:</span></span>  
  
```  
/child::OrderDetail[@UnitPrice * @Quantity = 12.350]  
```  
  
 <span data-ttu-id="da4a4-110">В запросе `child` — это ось, а `OrderDetail` — Проверка узла (значение true, если **OrderDetail** является **\<element node>** **\<element>** основным узлом для `child` оси).</span><span class="sxs-lookup"><span data-stu-id="da4a4-110">In the query, `child` is the axis and `OrderDetail` is the node test (TRUE if **OrderDetail** is an **\<element node>**, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="da4a4-111">Для всех **\<OrderDetail>** узлов элементов применяется тест в предикате и возвращаются только те узлы, которые соответствуют условию.</span><span class="sxs-lookup"><span data-stu-id="da4a4-111">For all the **\<OrderDetail>** element nodes, the test in the predicate is applied, and only those nodes that satisfy the condition are returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da4a4-112">Числа в языке XPath являются числами с плавающей запятой двойной точности, и сравнение чисел с плавающей запятой, как указано в примере, приводит к округлению.</span><span class="sxs-lookup"><span data-stu-id="da4a4-112">The numbers in XPath are double-precision floating-point numbers, and comparing floating-point numbers as in the example causes rounding.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="da4a4-113">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="da4a4-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="da4a4-114">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="da4a4-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="da4a4-115">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="da4a4-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="da4a4-116">Создайте следующий шаблон (ArithmeticOperatorA.xml) и сохраните его в каталоге, где содержится файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="da4a4-116">Create the following template (ArithmeticOperatorA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /OrderDetail[@UnitPrice * @OrderQty = 12.350]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="da4a4-117">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="da4a4-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="da4a4-118">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="da4a4-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="da4a4-119">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="da4a4-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="da4a4-120">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="da4a4-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
```  
Here is the partial result set of the template execution:    
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-710" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
   ...  
</ROOT>  
```  
  
  
