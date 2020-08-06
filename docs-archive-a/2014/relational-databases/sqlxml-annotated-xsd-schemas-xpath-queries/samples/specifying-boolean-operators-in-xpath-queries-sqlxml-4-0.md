---
title: Указание логических операторов в запросах XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath operators [SQLXML]
- OR operator
- Boolean operators
- XPath queries [SQLXML], Boolean operators
- operators [SQLXML]
ms.assetid: 9928cff5-62ac-42aa-96bf-2e09a1df0bc3
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dd6e1f120b53382ce984684ea352b36d34b768
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655000"
---
# <a name="specifying-boolean-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="bca16-102">Указание логических операторов в запросах XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="bca16-102">Specifying Boolean Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="bca16-103">В следующем примере показано, каким образом логические операторы задаются в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="bca16-103">The following example shows how Boolean operators are specified in XPath queries.</span></span> <span data-ttu-id="bca16-104">В этом примере задается запрос XPath к схеме сопоставления, содержащейся в файле SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="bca16-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="bca16-105">Дополнительные сведения об этом образце схемы см. в разделе [Пример схемы XSD с заметками для XPath-примеров &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="bca16-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="bca16-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="bca16-106">Examples</span></span>  
  
### <a name="a-specify-the-or-boolean-operator"></a><span data-ttu-id="bca16-107">A.</span><span class="sxs-lookup"><span data-stu-id="bca16-107">A.</span></span> <span data-ttu-id="bca16-108">Указание логического оператора OR</span><span class="sxs-lookup"><span data-stu-id="bca16-108">Specify the OR Boolean operator</span></span>  
 <span data-ttu-id="bca16-109">Этот запрос XPath возвращает **\<Customer>** дочерние элементы узла контекста с атрибутом **CustomerID** со значением 13 или 31:</span><span class="sxs-lookup"><span data-stu-id="bca16-109">This XPath query returns the **\<Customer>** element children of the context node with the **CustomerID** attribute value of 13 or 31:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="13" or attribute::CustomerID="31"]  
```  
  
 <span data-ttu-id="bca16-110">Может быть указан ярлык для оси `attribute` (@), поскольку ось `child` является осью по умолчанию и может не указываться.</span><span class="sxs-lookup"><span data-stu-id="bca16-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted:</span></span>  
  
```  
/Customer[@CustomerID="13" or @CustomerID="31"]  
```  
  
 <span data-ttu-id="bca16-111">В предикате `attribute` является осью и `CustomerID` является тестом узла (значение true, если **CustomerID** является **\<attribute>** узлом, поскольку **\<attribute>** узел является основным узлом для `attribute` оси).</span><span class="sxs-lookup"><span data-stu-id="bca16-111">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an **\<attribute>** node, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span> <span data-ttu-id="bca16-112">Предикат фильтрует **\<Customer>** элементы и возвращает только те, которые соответствуют условию, указанному в предикате.</span><span class="sxs-lookup"><span data-stu-id="bca16-112">The predicate filters the **\<Customer>** elements and returns only those that satisfy the condition specified in the predicate.</span></span>  
  
##### <a name="to-test-the-xpath-queries-against-the-mapping-schema"></a><span data-ttu-id="bca16-113">Проверка запросов XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="bca16-113">To test the XPath queries against the mapping schema</span></span>  
  
1.  <span data-ttu-id="bca16-114">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="bca16-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="bca16-115">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="bca16-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="bca16-116">Создайте следующий шаблон (BooleanOperatorsA.xml) и сохраните его в каталоге, в котором сохранен файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="bca16-116">Create the following template (BooleanOperatorsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="13" or @CustomerID="31"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="bca16-117">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="bca16-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="bca16-118">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="bca16-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="bca16-119">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="bca16-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="bca16-120">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bca16-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="bca16-121">Далее приведен результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="bca16-121">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="31" SalesPersonID="286" TerritoryID="7" AccountNumber="31" CustomerType="S" Orders="Ord-51803 Ord-69427">  
    <Order SalesOrderID="Ord-51803" SalesPersonID="286" OrderDate="2003-08-01T00:00:00" DueDate="2003-08-13T00:00:00" ShipDate="2003-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-718" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-838" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    <Order SalesOrderID="Ord-69427" SalesPersonID="286" OrderDate="2004-05-01T00:00:00" DueDate="2004-05-13T00:00:00" ShipDate="2004-05-08T00:00:00">  
      <OrderDetail ProductID="Prod-835" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
  </Customer>  
</ROOT>  
```  
  
  
