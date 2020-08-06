---
title: Указание осей в запросах XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- context node [SQLXML]
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- axes [SQLXML]
ms.assetid: d17b8278-da58-4576-95b4-7a92772566d8
author: rothja
ms.author: jroth
ms.openlocfilehash: f6f17404ea109bb0e687f9116b61025bbc411008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655003"
---
# <a name="specifying-axes-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="3af09-102">Указание осей в запросах XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3af09-102">Specifying Axes in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="3af09-103">В следующих примерах показано, как задаются оси в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="3af09-103">The following examples show how axes are specified in XPath queries.</span></span>  
  
 <span data-ttu-id="3af09-104">В данных примерах запросы XPath определены в соответствии со схемой сопоставления, которая содержится в файле SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3af09-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="3af09-105">Дополнительные сведения об этом образце схемы см. в разделе [Пример схемы XSD с заметками для XPath-примеров &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="3af09-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3af09-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="3af09-106">Examples</span></span>  
  
### <a name="a-retrieve-child-elements-of-the-context-node"></a><span data-ttu-id="3af09-107">A.</span><span class="sxs-lookup"><span data-stu-id="3af09-107">A.</span></span> <span data-ttu-id="3af09-108">Получение дочерних элементов контекстного узла</span><span class="sxs-lookup"><span data-stu-id="3af09-108">Retrieve child elements of the context node</span></span>  
 <span data-ttu-id="3af09-109">Следующий запрос XPath выбирает все **\<Contact>** дочерние элементы контекстного узла:</span><span class="sxs-lookup"><span data-stu-id="3af09-109">The following XPath query selects all the **\<Contact>** child elements of the context node:</span></span>  
  
```  
/child::Contact  
```  
  
 <span data-ttu-id="3af09-110">В запросе `child` является осью и `Contact` является тестом узла (значение true `Contact` , если является **\<element>** узлом, поскольку \<element> является типом первичного узла, связанным с `child` осью).</span><span class="sxs-lookup"><span data-stu-id="3af09-110">In the query, `child` is the axis and `Contact` is the node test (TRUE if `Contact` is an **\<element>** node, because \<element> is the primary node type associated with the `child` axis).</span></span>  
  
 <span data-ttu-id="3af09-111">Ось `child` является осью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3af09-111">The `child` axis is the default.</span></span> <span data-ttu-id="3af09-112">Поэтому указанный запрос может быть записан следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3af09-112">Therefore, the query can be written as:</span></span>  
  
```  
/Contact  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="3af09-113">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="3af09-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="3af09-114">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="3af09-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="3af09-115">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3af09-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="3af09-116">Создайте следующий шаблон (XPathAxesSampleA.xml) и сохраните его в том же каталоге, в котором был сохранен файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3af09-116">Create the following template (XPathAxesSampleA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3af09-117">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="3af09-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3af09-118">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="3af09-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="3af09-119">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="3af09-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3af09-120">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3af09-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3af09-121">Далее приведен частичный результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="3af09-121">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Contact ContactID="1" LastName="Achong" FirstName="Gustavo" Title="Mr." />   
  <Contact ContactID="2" LastName="Abel" FirstName="Catherine" Title="Ms." />   
  <Contact ContactID="3" LastName="Abercrombie" FirstName="Kim" Title="Ms." />   
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />  
  ...  
</ROOT>  
```  
  
### <a name="b-retrieve-grandchildren-of-the-context-node"></a><span data-ttu-id="3af09-122">Б.</span><span class="sxs-lookup"><span data-stu-id="3af09-122">B.</span></span> <span data-ttu-id="3af09-123">Получение внучатых элементов контекстного узла</span><span class="sxs-lookup"><span data-stu-id="3af09-123">Retrieve grandchildren of the context node</span></span>  
 <span data-ttu-id="3af09-124">Следующий запрос XPath выбирает все **\<Order>** дочерние элементы дочерних элементов **\<Customer>** узла контекста:</span><span class="sxs-lookup"><span data-stu-id="3af09-124">The following XPath query selects all the **\<Order>** element children of the **\<Customer>** element children of the context node:</span></span>  
  
```  
/child::Customer/child::Order  
```  
  
 <span data-ttu-id="3af09-125">В запросе `child` — это ось, а `Customer` `Order` — тесты узла (эти проверки узлов имеют значение true, если клиент и заказ являются **\<element>** узлами, поскольку **\<element>** узел является основным узлом для `child` оси).</span><span class="sxs-lookup"><span data-stu-id="3af09-125">In the query, `child` is the axis and `Customer` and `Order` are the node tests (these node tests are TRUE if Customer and Order are **\<element>** nodes, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="3af09-126">Для каждого соответствующего узла **\<Customer>** в **\<Orders>** результат добавляются соответствующие узлы.</span><span class="sxs-lookup"><span data-stu-id="3af09-126">For each node matching **\<Customer>**, the nodes matching **\<Orders>** are added to the result.</span></span> <span data-ttu-id="3af09-127">**\<Order>** В результирующем наборе возвращается только.</span><span class="sxs-lookup"><span data-stu-id="3af09-127">Only **\<Order>** is returned in the result set.</span></span>  
  
 <span data-ttu-id="3af09-128">Ось `child` является осью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3af09-128">The `child` axis is the default.</span></span> <span data-ttu-id="3af09-129">Поэтому запрос можно определить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3af09-129">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="3af09-130">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="3af09-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="3af09-131">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="3af09-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="3af09-132">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3af09-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="3af09-133">Создайте следующий шаблон (XPathAxesSampleB.xml) и сохраните его в том же каталоге, в котором представлено:</span><span class="sxs-lookup"><span data-stu-id="3af09-133">Create the following template (XPathAxesSampleB.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3af09-134">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="3af09-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3af09-135">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="3af09-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="3af09-136">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="3af09-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3af09-137">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3af09-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3af09-138">Далее приведен частичный результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="3af09-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</ROOT>  
```  
  
 <span data-ttu-id="3af09-139">Если запрос XPath указан как `Customer/Order/OrderDetail` , от каждого узла, соответствующего **\<Customer>** запросу, осуществляется переход к его **\<Order>** элементам.</span><span class="sxs-lookup"><span data-stu-id="3af09-139">If the XPath query is specified as `Customer/Order/OrderDetail`, from each node matching **\<Customer>** the query navigates to its **\<Order>** elements.</span></span> <span data-ttu-id="3af09-140">И для каждого соответствующего узла **\<Order>** запрос добавляет узлы **\<OrderDetail>** к результату.</span><span class="sxs-lookup"><span data-stu-id="3af09-140">And for each node matching **\<Order>**, the query adds the nodes **\<OrderDetail>** to the result.</span></span> <span data-ttu-id="3af09-141">**\<OrderDetail>** В результирующем наборе возвращается только.</span><span class="sxs-lookup"><span data-stu-id="3af09-141">Only **\<OrderDetail>** is returned in the result set.</span></span>  
  
### <a name="c-use--to-specify-the-parent-axis"></a><span data-ttu-id="3af09-142">В.</span><span class="sxs-lookup"><span data-stu-id="3af09-142">C.</span></span> <span data-ttu-id="3af09-143">Использование символов .</span><span class="sxs-lookup"><span data-stu-id="3af09-143">Use ..</span></span> <span data-ttu-id="3af09-144">для указания родительской оси</span><span class="sxs-lookup"><span data-stu-id="3af09-144">to specify the parent axis</span></span>  
 <span data-ttu-id="3af09-145">Следующий запрос получает все **\<Order>** элементы с родительским **\<Customer>** элементом со значением атрибута **CustomerID** , равным 1.</span><span class="sxs-lookup"><span data-stu-id="3af09-145">The following query retrieves all the **\<Order>** elements with a parent **\<Customer>** element with a **CustomerID** attribute value of 1.</span></span> <span data-ttu-id="3af09-146">В запросе используется `child` ось в предикате для поиска родителя **\<Order>** элемента.</span><span class="sxs-lookup"><span data-stu-id="3af09-146">The query uses the `child` axis in the predicate to find the parent of the **\<Order>** element.</span></span>  
  
```  
/child::Customer/child::Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="3af09-147">Ось `child` является осью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3af09-147">The `child` axis is the default axis.</span></span> <span data-ttu-id="3af09-148">Поэтому запрос можно определить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3af09-148">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="3af09-149">Этот запрос XPath эквивалентен следующему:</span><span class="sxs-lookup"><span data-stu-id="3af09-149">The XPath query is equivalent to:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3af09-150">Запрос XPath `/Order[../@CustomerID="1"]` возвратит ошибку, так как отсутствует родительский элемент **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="3af09-150">The XPath query `/Order[../@CustomerID="1"]` will return an error because there is no parent of **\<Order>**.</span></span> <span data-ttu-id="3af09-151">Хотя в схеме сопоставления могут быть элементы, которые содержат **\<Order>** , XPath не начался ни в одном из них; следовательно, **\<Order>** считается типом элемента верхнего уровня в документе.</span><span class="sxs-lookup"><span data-stu-id="3af09-151">Although there may be elements in the mapping schema that contain **\<Order>**, the XPath did not begin at any of them; consequently, **\<Order>** is considered to be the top-level element type in the document.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="3af09-152">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="3af09-152">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="3af09-153">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="3af09-153">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="3af09-154">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3af09-154">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="3af09-155">Создайте следующий шаблон (XPathAxesSampleC.xml) и сохраните его в том же каталоге, в котором представлено:</span><span class="sxs-lookup"><span data-stu-id="3af09-155">Create the following template (XPathAxesSampleC.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order[../@CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3af09-156">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="3af09-156">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3af09-157">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="3af09-157">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="3af09-158">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="3af09-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3af09-159">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3af09-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3af09-160">Далее приведен частичный результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="3af09-160">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</Order>  
</ROOT>  
```  
  
### <a name="d-specify-the-attribute-axis"></a><span data-ttu-id="3af09-161">Г.</span><span class="sxs-lookup"><span data-stu-id="3af09-161">D.</span></span> <span data-ttu-id="3af09-162">Указание оси атрибутов</span><span class="sxs-lookup"><span data-stu-id="3af09-162">Specify the attribute axis</span></span>  
 <span data-ttu-id="3af09-163">Следующий запрос XPath выбирает все **\<Customer>** дочерние элементы контекстного узла с атрибутом **CustomerID** со значением 1:</span><span class="sxs-lookup"><span data-stu-id="3af09-163">The following XPath query selects all the **\<Customer>** child elements of the context node with a **CustomerID** attribute value of 1:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]  
```  
  
 <span data-ttu-id="3af09-164">В предикате `attribute::CustomerID` `attribute` является осью и `CustomerID` является тестом узла (если `CustomerID` является атрибутом, проверяемым узлом является true, так как **\<attribute>** узел является основным узлом для `attribute` оси).</span><span class="sxs-lookup"><span data-stu-id="3af09-164">In the predicate `attribute::CustomerID`, `attribute` is the axis and `CustomerID` is the node test (if `CustomerID` is an attribute the node test is TRUE, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span>  
  
 <span data-ttu-id="3af09-165">Можно задать сокращенное обозначение оси `attribute` (@), а поскольку ось `child` является осью по умолчанию, в запросе ее можно опустить.</span><span class="sxs-lookup"><span data-stu-id="3af09-165">A shortcut to the `attribute` axis (@) can be specified, and because `child` is the default axis, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="3af09-166">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="3af09-166">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="3af09-167">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="3af09-167">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="3af09-168">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3af09-168">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="3af09-169">Создайте следующий шаблон (XPathAxesSampleD.xml) и сохраните его в том же каталоге, в котором был сохранен файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3af09-169">Create the following template (XPathAxesSampleD.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        child::Customer[attribute::CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3af09-170">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="3af09-170">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3af09-171">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="3af09-171">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="3af09-172">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="3af09-172">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3af09-173">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3af09-173">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3af09-174">Далее приведен частичный результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="3af09-174">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280"   
            TerritoryID="1" AccountNumber="1"   
            CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
       <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
                    OrderQty="1" UnitPriceDiscount="0" />   
      ...   
    </Order>  
   ...  
  </Customer>  
</ROOT>  
```  
  
  
