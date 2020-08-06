---
title: Указание предикатов с логическими значениями в запросах XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- nested predicates
- successive predicates
- predicates [SQLXML]
- top-level predicates
- Boolean-valued predicates
- multiple predicates
ms.assetid: 5f6e7219-6911-4bca-a54b-56b95e0b43dd
author: rothja
ms.author: jroth
ms.openlocfilehash: 56f2f94ec895c5b76382d5103ca9d518b78cc899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654999"
---
# <a name="specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="0f45c-102">Определение предикатов с логическим значением в запросах XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="0f45c-102">Specifying Boolean-Valued Predicates in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="0f45c-103">В следующем примере показано, как предикаты с логическим значением указываются в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="0f45c-103">The following examples show how Boolean-valued predicates are specified in XPath queries.</span></span> <span data-ttu-id="0f45c-104">В данных примерах запросы XPath определены в соответствии со схемой сопоставления, которая содержится в файле SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0f45c-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="0f45c-105">Дополнительные сведения об этом образце схемы см. в разделе [Пример схемы XSD с заметками для XPath-примеров &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="0f45c-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0f45c-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="0f45c-106">Examples</span></span>  
  
### <a name="a-specify-multiple-predicates"></a><span data-ttu-id="0f45c-107">A.</span><span class="sxs-lookup"><span data-stu-id="0f45c-107">A.</span></span> <span data-ttu-id="0f45c-108">Указание нескольких предикатов</span><span class="sxs-lookup"><span data-stu-id="0f45c-108">Specify multiple predicates</span></span>  
 <span data-ttu-id="0f45c-109">Следующий запрос XPath использует несколько предикатов для поиска сведений о заказе для данного идентификатора заказа и идентификатора клиента:</span><span class="sxs-lookup"><span data-stu-id="0f45c-109">The following XPath query uses multiple predicates to find order information for a given order ID and a customer ID:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]/child::Order[attribute::OrderID="Ord-43860"]  
```  
  
 <span data-ttu-id="0f45c-110">Может быть задано сокращенное обозначение оси `attribute` (@), а поскольку ось `child` является осью по умолчанию, в запросе ее можно опустить.</span><span class="sxs-lookup"><span data-stu-id="0f45c-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="0f45c-111">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="0f45c-111">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="0f45c-112">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="0f45c-112">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="0f45c-113">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0f45c-113">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="0f45c-114">Создайте следующий шаблон (BooleanValuedPredicatesA.xml) и сохраните его в каталоге, где содержится файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0f45c-114">Create the following template (BooleanValuedPredicatesA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="0f45c-115">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="0f45c-115">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="0f45c-116">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="0f45c-116">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="0f45c-117">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="0f45c-117">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="0f45c-118">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0f45c-118">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
     <span data-ttu-id="0f45c-119">Результат:</span><span class="sxs-lookup"><span data-stu-id="0f45c-119">Here is the result:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
        <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-761" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-762" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-765" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-768" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-770" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
      </Order>  
    </ROOT>  
    ```  
  
### <a name="b-specify-successive-and-nested-predicates"></a><span data-ttu-id="0f45c-120">Б.</span><span class="sxs-lookup"><span data-stu-id="0f45c-120">B.</span></span> <span data-ttu-id="0f45c-121">Указание последовательных и вложенных предикатов</span><span class="sxs-lookup"><span data-stu-id="0f45c-121">Specify successive and nested predicates</span></span>  
 <span data-ttu-id="0f45c-122">В следующем запросе показано использование последовательных предикатов.</span><span class="sxs-lookup"><span data-stu-id="0f45c-122">The following query shows using successive predicates.</span></span> <span data-ttu-id="0f45c-123">Запрос возвращает все **\<Customer>** дочерние элементы контекстного узла, которые имеют атрибут **SalesPersonID** со значением 277 и атрибутом **территорид** со значением 3:</span><span class="sxs-lookup"><span data-stu-id="0f45c-123">The query returns all the **\<Customer>** child elements of the context node that have both a **SalesPersonID** attribute with a value of 277 and a **TerritoryID** attribute with a value of 3:</span></span>  
  
```  
/child::Customer[attribute::SalesPersonID="277"][attribute::TerritoryID="3"]  
```  
  
 <span data-ttu-id="0f45c-124">Запрос возвращает **\<Customer>** элементы, которые соответствуют условиям, заданным в предикатах.</span><span class="sxs-lookup"><span data-stu-id="0f45c-124">The query returns the **\<Customer>** elements that satisfy both the conditions specified in the predicates.</span></span>  
  
 <span data-ttu-id="0f45c-125">Может быть задано сокращенное обозначение оси `attribute` (@), а поскольку ось `child` является осью по умолчанию, в запросе ее можно опустить.</span><span class="sxs-lookup"><span data-stu-id="0f45c-125">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@SalesPersonID="277"][@TerritoryID="3"]  
```  
  
 <span data-ttu-id="0f45c-126">В следующем запросе XPath показано использование вложенных предикатов.</span><span class="sxs-lookup"><span data-stu-id="0f45c-126">The following XPath query illustrates the use of nested predicates.</span></span> <span data-ttu-id="0f45c-127">Запрос возвращает все **\<Customer>** дочерние элементы контекстного узла, которые содержат **\<Order>** дочерние элементы по крайней мере с одним **\<Order>** элементом, имеющим значение атрибута **SalesPersonID** , равное 2.</span><span class="sxs-lookup"><span data-stu-id="0f45c-127">The query returns all the **\<Customer>** child elements of the context node that include **\<Order>** child elements with at least one **\<Order>** element that has a **SalesPersonID** attribute value of 2.</span></span>  
  
```  
/Customer[Order[@SalesPersonID=2]]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="0f45c-128">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="0f45c-128">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="0f45c-129">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="0f45c-129">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="0f45c-130">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0f45c-130">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="0f45c-131">Создайте следующий шаблон (nestedSuccessive.xml) и сохраните его в каталоге, где содержится файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0f45c-131">Create the following template (nestedSuccessive.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
             /Customer[@SalesPersonID="277"][@TerritoryID="3"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="0f45c-132">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="0f45c-132">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="0f45c-133">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="0f45c-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="0f45c-134">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="0f45c-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="0f45c-135">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0f45c-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="0f45c-136">Далее показан частичный результат:</span><span class="sxs-lookup"><span data-stu-id="0f45c-136">The following is a partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="22" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="22" CustomerType="S"   
            Orders="Ord-43874 Ord-44519 Ord-46989 Ord-48013 Ord-49130 Ord-50274 Ord-51807 Ord-57113 Ord-63162 Ord-69495">  
    <Order SalesOrderID="Ord-43874" SalesPersonID="277"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
                   OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    ...  
  </Customer>  
  <Customer CustomerID="39" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="39" CustomerType="S"   
            Orders="Ord-47428 Ord-48367 Ord-49529 Ord-50742 Ord-53591 Ord-59051 Ord-65301 Ord-71912">    <Order SalesOrderID="Ord-47428" SalesPersonID="277"   
           OrderDate="2002-09-01T00:00:00"   
           DueDate="2002-09-13T00:00:00"   
           ShipDate="2002-09-08T00:00:00">  
      <OrderDetail ProductID="Prod-759" UnitPrice="563.7528" OrderQty="2" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-769" UnitPrice="563.7528" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
### <a name="c-specify-a-top-level-predicate"></a><span data-ttu-id="0f45c-137">В.</span><span class="sxs-lookup"><span data-stu-id="0f45c-137">C.</span></span> <span data-ttu-id="0f45c-138">Указание предиката верхнего уровня</span><span class="sxs-lookup"><span data-stu-id="0f45c-138">Specify a top-level predicate</span></span>  
 <span data-ttu-id="0f45c-139">Следующий запрос возвращает **\<Customer>** дочерние узлы элементов контекстного узла, которые имеют **\<Order>** дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="0f45c-139">The following query returns the **\<Customer>** child element nodes of the context node that have **\<Order>** element children.</span></span> <span data-ttu-id="0f45c-140">В этом запросе проверяется, является ли путь доступа предикатом верхнего уровня:</span><span class="sxs-lookup"><span data-stu-id="0f45c-140">The query tests the location path as the top-level predicate:</span></span>  
  
```  
/child::Customer[child::Order]  
```  
  
 <span data-ttu-id="0f45c-141">Ось `child` является осью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0f45c-141">The `child` axis is the default.</span></span> <span data-ttu-id="0f45c-142">Поэтому запрос можно определить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0f45c-142">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="0f45c-143">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="0f45c-143">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="0f45c-144">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="0f45c-144">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="0f45c-145">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0f45c-145">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="0f45c-146">Создайте следующий шаблон (TopLevelPredicate.xml) и сохраните его в каталоге, где содержится файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0f45c-146">Create the following template (TopLevelPredicate.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="0f45c-147">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="0f45c-147">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="0f45c-148">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="0f45c-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="0f45c-149">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="0f45c-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="0f45c-150">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0f45c-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="0f45c-151">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="0f45c-151">Here is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280" TerritoryID="1" AccountNumber="1" CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    <Order SalesOrderID="Ord-44501" SalesPersonID="280" OrderDate="2001-11-01T00:00:00" DueDate="2001-11-13T00:00:00" ShipDate="2001-11-08T00:00:00">  
      <OrderDetail ProductID="Prod-725" UnitPrice="226.8571" OrderQty="3" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-726" UnitPrice="226.8571" OrderQty="2" UnitPriceDiscount="0" />   
      ...  
    </Order>    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
  
