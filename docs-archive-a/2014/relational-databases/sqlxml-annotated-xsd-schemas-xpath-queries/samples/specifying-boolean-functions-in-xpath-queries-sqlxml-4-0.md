---
title: Указание логических функций в запросах XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], Boolean functions
- false function
- not function [SQLXML]
- true function
- Boolean functions
ms.assetid: c72cd333-9294-4d41-84f2-1748bf20e3eb
author: rothja
ms.author: jroth
ms.openlocfilehash: d230c7cd8792066732085b9ce501c0794687d17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655001"
---
# <a name="specifying-boolean-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="dcb28-102">Указание логических функций в запросах XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="dcb28-102">Specifying Boolean Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="dcb28-103">В следующих примерах показано, как задаются логические функции в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="dcb28-103">The following examples show how Boolean functions are specified in XPath queries.</span></span> <span data-ttu-id="dcb28-104">В данных примерах запросы XPath определены в соответствии со схемой сопоставления, которая содержится в файле SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="dcb28-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="dcb28-105">Дополнительные сведения об этом образце схемы см. в разделе [Пример схемы XSD с заметками для XPath-примеров &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="dcb28-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="dcb28-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="dcb28-106">Examples</span></span>  
  
## <a name="a-specify-the-not-boolean-function"></a><span data-ttu-id="dcb28-107">A.</span><span class="sxs-lookup"><span data-stu-id="dcb28-107">A.</span></span> <span data-ttu-id="dcb28-108">Задание логической функции not()</span><span class="sxs-lookup"><span data-stu-id="dcb28-108">Specify the not() Boolean function</span></span>  
 <span data-ttu-id="dcb28-109">Этот запрос возвращает все **\<Customer>** дочерние элементы контекстного узла, не имеющие **\<Order>** дочерних элементов:</span><span class="sxs-lookup"><span data-stu-id="dcb28-109">This query returns all the **\<Customer>** child elements of the context node that do not have **\<Order>** child elements:</span></span>  
  
```  
/child::Customer[not(child::Order)]  
```  
  
 <span data-ttu-id="dcb28-110">Ось `child` является осью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dcb28-110">The `child` axis is the default.</span></span> <span data-ttu-id="dcb28-111">Поэтому запрос можно определить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="dcb28-111">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="dcb28-112">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="dcb28-112">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="dcb28-113">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dcb28-113">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="dcb28-114">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="dcb28-114">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="dcb28-115">Создайте следующий шаблон (BooleanFunctionsA.xml) и сохраните его в каталоге, где находится файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="dcb28-115">Create the following template (BooleanFunctionsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[not(Order)]  
    </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="dcb28-116">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="dcb28-116">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="dcb28-117">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="dcb28-117">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="dcb28-118">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="dcb28-118">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="dcb28-119">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="dcb28-119">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="dcb28-120">Далее приведен частичный результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="dcb28-120">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
## <a name="b-specify-the-true-and-false-boolean-functions"></a><span data-ttu-id="dcb28-121">Б.</span><span class="sxs-lookup"><span data-stu-id="dcb28-121">B.</span></span> <span data-ttu-id="dcb28-122">Задание логических функций true() и false()</span><span class="sxs-lookup"><span data-stu-id="dcb28-122">Specify the true() and false() Boolean functions</span></span>  
 <span data-ttu-id="dcb28-123">Этот запрос возвращает все **\<Customer>** дочерние элементы узла контекста, не имеющие **\<Order>** дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="dcb28-123">This query returns all **\<Customer>** element children of the context node that do not have **\<Order>** child elements.</span></span> <span data-ttu-id="dcb28-124">В реляционных терминах этот запрос возвращает всех заказчиков, не разместивших ни одного заказа.</span><span class="sxs-lookup"><span data-stu-id="dcb28-124">In relational terms, this query returns all customers who have not placed any orders.</span></span>  
  
```  
/child::Customer[child::Order=false()]  
```  
  
 <span data-ttu-id="dcb28-125">Ось `child` является осью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dcb28-125">The `child` axis is the default.</span></span> <span data-ttu-id="dcb28-126">Поэтому запрос можно определить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="dcb28-126">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order=false()]  
```  
  
 <span data-ttu-id="dcb28-127">Этот запрос эквивалентен следующему:</span><span class="sxs-lookup"><span data-stu-id="dcb28-127">This query is equivalent to the following:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
 <span data-ttu-id="dcb28-128">Следующий запрос возвращает всех заказчиков, разместивших хотя бы один заказ:</span><span class="sxs-lookup"><span data-stu-id="dcb28-128">The following query returns all the customers who have placed at least one order:</span></span>  
  
```  
/Customer[Order=true()]  
```  
  
 <span data-ttu-id="dcb28-129">Этот запрос эквивалентен приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="dcb28-129">This query is equivalent to this one:</span></span>  
  
```  
/Customer[Order]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="dcb28-130">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="dcb28-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="dcb28-131">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dcb28-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="dcb28-132">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="dcb28-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="dcb28-133">Создайте следующий шаблон (BooleanFunctionsB.xml) и сохраните его в каталоге, где находится файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="dcb28-133">Create the following template (BooleanFunctionsB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order=false()]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="dcb28-134">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="dcb28-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="dcb28-135">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="dcb28-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="dcb28-136">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="dcb28-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="dcb28-137">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="dcb28-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="dcb28-138">Далее приведен частичный результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="dcb28-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
  
