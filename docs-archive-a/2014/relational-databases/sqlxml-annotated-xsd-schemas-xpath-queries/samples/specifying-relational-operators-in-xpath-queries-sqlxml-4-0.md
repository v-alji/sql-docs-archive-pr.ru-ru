---
title: Указание реляционных операторов в запросах XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], relational operators
- relational operators [SQLXML]
- XPath operators [SQLXML]
- operators [SQLXML]
ms.assetid: 177a0eb2-11ef-4459-a317-485a433ee769
author: rothja
ms.author: jroth
ms.openlocfilehash: 50d59ebd3a776386c61f4c3a8a1e892d30981d1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654992"
---
# <a name="specifying-relational-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="ad8d3-102">Применение реляционных операторов в запросах XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ad8d3-102">Specifying Relational Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="ad8d3-103">В следующих примерах показано, как задаются реляционные операторы в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-103">The following examples show how relational operators are specified in XPath queries.</span></span> <span data-ttu-id="ad8d3-104">В данных примерах запросы XPath определены в соответствии со схемой сопоставления, которая содержится в файле SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="ad8d3-105">Дополнительные сведения об этом образце схемы см. в разделе [Пример схемы XSD с заметками для XPath-примеров &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ad8d3-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ad8d3-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="ad8d3-106">Examples</span></span>  
  
### <a name="a-specify-relational-operator"></a><span data-ttu-id="ad8d3-107">A.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-107">A.</span></span> <span data-ttu-id="ad8d3-108">Укажите реляционный оператор</span><span class="sxs-lookup"><span data-stu-id="ad8d3-108">Specify relational operator</span></span>  
 <span data-ttu-id="ad8d3-109">Этот запрос XPath возвращает дочерние элементы **\<Customer>** элемента, где значение атрибута **CustomerID** равно "1", а все дочерние **\<Order>** элементы содержат **\<OrderDetail>** дочерний элемент с атрибутом **OrderQty** со значением больше 3:</span><span class="sxs-lookup"><span data-stu-id="ad8d3-109">This XPath query returns the child elements of the **\<Customer>** element where the **CustomerID** attribute value is "1" and where any child **\<Order>** elements contain an **\<OrderDetail>** child with a **OrderQty** attribute with a value greater than 3:</span></span>  
  
```  
/child::Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
 <span data-ttu-id="ad8d3-110">Предикат, указанный в квадратных скобках, фильтрует **\<Customer>** элементы.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-110">The predicate specified in the brackets filters the **\<Customer>** elements.</span></span> <span data-ttu-id="ad8d3-111">Возвращаются только те **\<Customer>** элементы, у которых есть хотя бы один **\<OrderDetail>** внучатый с атрибутом OrderQty со значением больше 3.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-111">Only the **\<Customer>** elements that have at least one **\<OrderDetail>** grandchild with a OrderQty attribute value greater than 3 are returned.</span></span>  
  
 <span data-ttu-id="ad8d3-112">Ось `child` является осью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-112">The `child` axis is the default.</span></span> <span data-ttu-id="ad8d3-113">Поэтому запрос можно определить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-113">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="ad8d3-114">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="ad8d3-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="ad8d3-115">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="ad8d3-116">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="ad8d3-117">Создайте следующий шаблон (SpecifyRelationalA.xml) и сохраните его в каталоге, в котором сохранен файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-117">Create the following template (SpecifyRelationalA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="ad8d3-118">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="ad8d3-119">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="ad8d3-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="ad8d3-120">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="ad8d3-121">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ad8d3-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="ad8d3-122">Далее приведен результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-122">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-760" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-766" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-757" UnitPrice="1049.7528" OrderQty="4" UnitPriceDiscount="0" />   
</ROOT>  
```  
  
### <a name="b-specify-relational-operator-in-the-xpath-query-and-use-boolean-function-to-compare-the-result"></a><span data-ttu-id="ad8d3-123">Б.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-123">B.</span></span> <span data-ttu-id="ad8d3-124">Укажите реляционный оператор в запросе XPath и используйте логическую функцию для сравнения результатов</span><span class="sxs-lookup"><span data-stu-id="ad8d3-124">Specify relational operator in the XPath query and use Boolean function to compare the result</span></span>  
 <span data-ttu-id="ad8d3-125">Этот запрос возвращает все **\<Order>** дочерние элементы узла контекста, у которых значение атрибута **SalesPersonID** меньше 270:</span><span class="sxs-lookup"><span data-stu-id="ad8d3-125">This query returns all the **\<Order>** element children of the context node that have an **SalesPersonID** attribute value that is less than 270:</span></span>  
  
```  
/child::Customer/child::Order[(attribute::SalesPersonID < 270)=true()]  
```  
  
 <span data-ttu-id="ad8d3-126">Может быть задано сокращенное обозначение оси `attribute` (@), а поскольку ось `child` является осью по умолчанию, в запросе ее можно опустить.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-126">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer/Order[(@SalesPersonID < 270)=true()]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ad8d3-127">Если этот запрос указан в шаблоне, < символ должен быть закодирован в кодировке Entity, так как < символ имеет специальное значение в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-127">When this query is specified in a template, the < character must be entity encoded because the < character has special meaning in an XML document.</span></span> <span data-ttu-id="ad8d3-128">В шаблоне используйте `<` для указания < символа.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-128">In a template, use `<` to specify the < character.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="ad8d3-129">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="ad8d3-129">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="ad8d3-130">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-130">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="ad8d3-131">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-131">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="ad8d3-132">Создайте следующий шаблон (SpecifyRelationalB.xml) и сохраните его в том же каталоге, в котором сохранен файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-132">Create the following template (SpecifyRelationalB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="SampleSchema1.xml">  
            /Customer/Order[(@SalesPersonID<270)=true()]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="ad8d3-133">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-133">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="ad8d3-134">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="ad8d3-134">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="ad8d3-135">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-135">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="ad8d3-136">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ad8d3-136">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="ad8d3-137">Далее приведен частичный результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="ad8d3-137">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-46613" SalesPersonID="268"   
         OrderDate="2002-07-01T00:00:00"   
         DueDate="2002-07-13T00:00:00"   
         ShipDate="2002-07-08T00:00:00">  
    <OrderDetail ProductID="Prod-739" UnitPrice="917.9363"   
                 OrderQty="2" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-779" UnitPrice="1491.4221"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-825" UnitPrice="242.1391"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  <Order SalesOrderID="Ord-71919" SalesPersonID="268"  
         OrderDate="2004-06-01T00:00:00"   
         DueDate="2004-06-13T00:00:00"   
         ShipDate="2004-06-08T00:00:00">  
    <OrderDetail ProductID="Prod-961" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-965" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-966" UnitPrice="1716.5304"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  ...  
</ROOT>  
```  
  
  
