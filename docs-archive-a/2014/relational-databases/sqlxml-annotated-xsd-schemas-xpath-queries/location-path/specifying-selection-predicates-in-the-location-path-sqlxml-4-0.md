---
title: Указание предикатов выбора в пути расположения (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- predicates [SQLXML]
- position-based filtering [SQLXML]
- XPath queries [SQLXML], location paths
- filtering [SQLXML]
- location path for XPath query
ms.assetid: dbef4cf4-a89b-4d7e-b72b-4062f7b29a80
author: rothja
ms.author: jroth
ms.openlocfilehash: d323558556fb05d350e48ea9218a8e9b8dc9b5c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664800"
---
# <a name="specifying-selection-predicates-in-the-location-path-sqlxml-40"></a><span data-ttu-id="bb730-102">Указание предикатов выбора в пути доступа (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="bb730-102">Specifying Selection Predicates in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="bb730-103">Предикат фильтрует набор узлов по отношению к оси (аналогично предложению WHERE в инструкции SELECT).</span><span class="sxs-lookup"><span data-stu-id="bb730-103">A predicate filters a node-set with respect to an axis (similar to a WHERE clause in a SELECT statement).</span></span> <span data-ttu-id="bb730-104">Предикат указывается в квадратных скобках.</span><span class="sxs-lookup"><span data-stu-id="bb730-104">The predicate is specified between brackets.</span></span> <span data-ttu-id="bb730-105">Для каждого узла в фильтруемом наборе узлов выражение предиката вычисляется с этим узлом в качестве узла контекста, а количество узлов в наборе определяет размер контекста.</span><span class="sxs-lookup"><span data-stu-id="bb730-105">For each node in the node-set to be filtered, the predicate expression is evaluated with that node as the context node, with the number of nodes in the node-set as context size.</span></span> <span data-ttu-id="bb730-106">Если для данного узла выражение предиката дает значение TRUE, то узел включается в результирующий набор узлов.</span><span class="sxs-lookup"><span data-stu-id="bb730-106">If the predicate expression evaluates to TRUE for that node, the node is included in the resulting node-set.</span></span>  
  
 <span data-ttu-id="bb730-107">XPath также позволяет выполнять фильтрацию в зависимости от позиции.</span><span class="sxs-lookup"><span data-stu-id="bb730-107">XPath also allows position-based filtering.</span></span> <span data-ttu-id="bb730-108">Выражение предиката, результатом оценки которого является число, выбирает этот исходный узел.</span><span class="sxs-lookup"><span data-stu-id="bb730-108">A predicate expression evaluating to a number selects that ordinal node.</span></span> <span data-ttu-id="bb730-109">Например, путь доступа `Customer[3]` возвращает третьего клиента.</span><span class="sxs-lookup"><span data-stu-id="bb730-109">For example, the location path `Customer[3]` returns the third customer.</span></span> <span data-ttu-id="bb730-110">Такие числовые предикаты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bb730-110">Such numeric predicates are not supported.</span></span> <span data-ttu-id="bb730-111">Поддерживаются только предикаты, которые возвращают логический результат.</span><span class="sxs-lookup"><span data-stu-id="bb730-111">Only predicate expressions that return a Boolean result are supported.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb730-112">Дополнительные сведения об ограничениях этой реализации XPath и различиях между ней и спецификацией W3C см. [в статье Введение в использование XPath запросов &#40;SQLXML 4,0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="bb730-112">For information about the limitations of this XPath implementation of XPath and the differences between it and the W3C specification, see [Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span></span>  
  
## <a name="selection-predicate-example-1"></a><span data-ttu-id="bb730-113">Предикат выбора: Пример 1</span><span class="sxs-lookup"><span data-stu-id="bb730-113">Selection Predicate: Example 1</span></span>  
 <span data-ttu-id="bb730-114">Следующее выражение XPath (путь расположения) выбирает из текущего контекстного узла все **\<Customer>** дочерние элементы, имеющие атрибут **CustomerID** со значением ALFKI:</span><span class="sxs-lookup"><span data-stu-id="bb730-114">The following XPath expression (location path) selects from the current context node all the **\<Customer>** element children that have the **CustomerID** attribute with value of ALFKI:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="ALFKI"]  
```  
  
 <span data-ttu-id="bb730-115">В этом запросе XPath `child` и `attribute` являются именами осей.</span><span class="sxs-lookup"><span data-stu-id="bb730-115">In this XPath query, `child` and `attribute` are axis names.</span></span> <span data-ttu-id="bb730-116">`Customer`является тестом узла (значение TRUE `Customer` , если является **\<element node>** , поскольку **\<element>** является типом основного узла для `child` оси).</span><span class="sxs-lookup"><span data-stu-id="bb730-116">`Customer` is the node test (TRUE if `Customer` is an **\<element node>**, because **\<element>** is the principal node type for the `child` axis).</span></span> <span data-ttu-id="bb730-117">`attribute::CustomerID="ALFKI"` является предикатом.</span><span class="sxs-lookup"><span data-stu-id="bb730-117">`attribute::CustomerID="ALFKI"` is the predicate.</span></span> <span data-ttu-id="bb730-118">В предикате `attribute` является осью и `CustomerID` является тестом узла (значение true, если **CustomerID** является атрибутом контекстного узла, поскольку **\<attribute>** является типом основного узла `attribute` оси).</span><span class="sxs-lookup"><span data-stu-id="bb730-118">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an attribute of the context node, because **\<attribute>** is the principal node type of `attribute` axis).</span></span>  
  
 <span data-ttu-id="bb730-119">Запрос XPath также можно задать с использованием сокращенного синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="bb730-119">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer[@CustomerID="ALFKI"]  
```  
  
## <a name="selection-predicate-example-2"></a><span data-ttu-id="bb730-120">Предикат выбора: пример 2</span><span class="sxs-lookup"><span data-stu-id="bb730-120">Selection Predicate: Example 2</span></span>  
 <span data-ttu-id="bb730-121">Следующее выражение XPath (путь расположения) выбирает из текущего контекстного узла все **\<Order>** внуками, имеющие атрибут **SalesOrderID** со значением 1:</span><span class="sxs-lookup"><span data-stu-id="bb730-121">The following XPath expression (location path) selects from the current context node all the **\<Order>** grandchildren that have the **SalesOrderID** attribute with the value 1:</span></span>  
  
```  
/child::Customer/child::Order[attribute::SalesOrderID="1"]  
```  
  
 <span data-ttu-id="bb730-122">В этом выражении XPath `child` и `attribute` являются именами осей.</span><span class="sxs-lookup"><span data-stu-id="bb730-122">In this XPath expression, `child` and `attribute` are the axis names.</span></span> <span data-ttu-id="bb730-123">`Customer`, `Order` и `SalesOrderID` являются проверками узла.</span><span class="sxs-lookup"><span data-stu-id="bb730-123">`Customer`, `Order`, and `SalesOrderID` are the node tests.</span></span> <span data-ttu-id="bb730-124">`attribute::OrderID="1"` является предикатом.</span><span class="sxs-lookup"><span data-stu-id="bb730-124">`attribute::OrderID="1"` is the predicate.</span></span>  
  
 <span data-ttu-id="bb730-125">Запрос XPath также можно задать с использованием сокращенного синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="bb730-125">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer/Order[@SalesOrderID="1"]  
```  
  
## <a name="selection-predicate-example-3"></a><span data-ttu-id="bb730-126">Предикат выбора: пример 3</span><span class="sxs-lookup"><span data-stu-id="bb730-126">Selection Predicate: Example 3</span></span>  
 <span data-ttu-id="bb730-127">Следующее выражение XPath (путь расположения) выбирает из текущего контекстного узла все **\<Customer>** дочерние элементы, имеющие один или несколько **\<ContactName>** дочерних элементов:</span><span class="sxs-lookup"><span data-stu-id="bb730-127">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children that have one or more **\<ContactName>** children:</span></span>  
  
```  
child::Customer[child::ContactName]  
```  
  
 <span data-ttu-id="bb730-128">В этом примере предполагается, что **\<ContactName>** является дочерним элементом **\<Customer>** элемента в XML-документе, который называется *сопоставлением с использованием элементов* в схеме XSD с заметками.</span><span class="sxs-lookup"><span data-stu-id="bb730-128">This example assumes that the **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, which is referred to as *element-centric mapping* in an annotated XSD schema.</span></span>  
  
 <span data-ttu-id="bb730-129">В этом выражении XPath `child` является именем оси.</span><span class="sxs-lookup"><span data-stu-id="bb730-129">In this XPath expression, `child` is the axis name.</span></span> <span data-ttu-id="bb730-130">`Customer`— Это проверка узла (значение TRUE `Customer` , если является **\<element>** узлом, поскольку **\<element>** является типом основного узла для `child` оси).</span><span class="sxs-lookup"><span data-stu-id="bb730-130">`Customer` is the node test (TRUE if `Customer` is an **\<element>** node, because **\<element>** is the principal node type for `child` axis).</span></span> <span data-ttu-id="bb730-131">`child::ContactName` является предикатом.</span><span class="sxs-lookup"><span data-stu-id="bb730-131">`child::ContactName` is the predicate.</span></span> <span data-ttu-id="bb730-132">В предикате `child` является осью и `ContactName` является тестом узла (значение true, если `ContactName` является **\<element>** узлом).</span><span class="sxs-lookup"><span data-stu-id="bb730-132">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an **\<element>** node).</span></span>  
  
 <span data-ttu-id="bb730-133">Это выражение возвращает только **\<Customer>** дочерние элементы узла контекста, которые имеют **\<ContactName>** дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="bb730-133">This expression returns only the **\<Customer>** element children of the context node that have **\<ContactName>** element children.</span></span>  
  
 <span data-ttu-id="bb730-134">Запрос XPath также можно задать с использованием сокращенного синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="bb730-134">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[ContactName]  
```  
  
## <a name="selection-predicate-example-4"></a><span data-ttu-id="bb730-135">Предикат выбора: пример 4</span><span class="sxs-lookup"><span data-stu-id="bb730-135">Selection Predicate: Example 4</span></span>  
 <span data-ttu-id="bb730-136">Следующее выражение XPath выбирает **\<Customer>** дочерние элементы узла контекста, не имеющие **\<ContactName>** дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="bb730-136">The following XPath expression selects **\<Customer>** element children of the context node that do not have **\<ContactName>** element children:</span></span>  
  
```  
child::Customer[not(child::ContactName)]  
```  
  
 <span data-ttu-id="bb730-137">В этом примере предполагается, что **\<ContactName>** является дочерним элементом **\<Customer>** элемента в XML-документе, а поле ContactName не является обязательным в базе данных.</span><span class="sxs-lookup"><span data-stu-id="bb730-137">This example assumes that **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, and the ContactName field is not required in the database.</span></span>  
  
 <span data-ttu-id="bb730-138">В этом примере `child` является осью.</span><span class="sxs-lookup"><span data-stu-id="bb730-138">In this example, `child` is the axis.</span></span> <span data-ttu-id="bb730-139">`Customer`является тестом узла (значение TRUE, если `Customer` является \<element> узлом).</span><span class="sxs-lookup"><span data-stu-id="bb730-139">`Customer` is the node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="bb730-140">`not(child::ContactName)` является предикатом.</span><span class="sxs-lookup"><span data-stu-id="bb730-140">`not(child::ContactName)` is the predicate.</span></span> <span data-ttu-id="bb730-141">В предикате `child` является осью и `ContactName` является тестом узла (значение true, если `ContactName` является \<element> узлом).</span><span class="sxs-lookup"><span data-stu-id="bb730-141">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an \<element> node).</span></span>  
  
 <span data-ttu-id="bb730-142">Запрос XPath также можно задать с использованием сокращенного синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="bb730-142">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[not(ContactName)]  
```  
  
## <a name="selection-predicate-example-5"></a><span data-ttu-id="bb730-143">Предикат выбора: пример 5</span><span class="sxs-lookup"><span data-stu-id="bb730-143">Selection Predicate: Example 5</span></span>  
 <span data-ttu-id="bb730-144">Следующее выражение XPath выбирает из текущего контекстного узла все **\<Customer>** дочерние элементы, имеющие атрибут **CustomerID** :</span><span class="sxs-lookup"><span data-stu-id="bb730-144">The following XPath expression selects from the current context node all the **\<Customer>** children that have the **CustomerID** attribute:</span></span>  
  
```  
child::Customer[attribute::CustomerID]  
```  
  
 <span data-ttu-id="bb730-145">В этом примере `child` — это ось, а `Customer` — Проверка узла (значение true, если `Customer` является \<element> узлом).</span><span class="sxs-lookup"><span data-stu-id="bb730-145">In this example, `child` is the axis and `Customer` is node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="bb730-146">`attribute::CustomerID` является предикатом.</span><span class="sxs-lookup"><span data-stu-id="bb730-146">`attribute::CustomerID` is the predicate.</span></span> <span data-ttu-id="bb730-147">В предикате `attribute` — это ось, а `CustomerID` — ПРЕДИКАТ (true, если `CustomerID` является **\<attribute>** узлом).</span><span class="sxs-lookup"><span data-stu-id="bb730-147">In the predicate, `attribute` is the axis and `CustomerID` is the predicate (TRUE if `CustomerID` is an **\<attribute>** node).</span></span>  
  
 <span data-ttu-id="bb730-148">Запрос XPath также можно задать с использованием сокращенного синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="bb730-148">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[@CustomerID]  
```  
  
## <a name="selection-predicate-example-6"></a><span data-ttu-id="bb730-149">Предикат выбора: пример 6</span><span class="sxs-lookup"><span data-stu-id="bb730-149">Selection Predicate: Example 6</span></span>  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="bb730-150">SQLXML 4.0 включает поддержку запросов XPath, которые содержат в предикате перекрестное произведение, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bb730-150">SQLXML 4.0 includes support for XPath queries that contain a cross-product in the predicate, as shown in the following example:</span></span>  
  
```  
Customer[Order/@OrderDate=Order/@ShipDate]  
```  
  
 <span data-ttu-id="bb730-151">Этот запрос выбирает всех клиентов с элементом `Order`, для которого `OrderDate` равен `ShipDate``Order`.</span><span class="sxs-lookup"><span data-stu-id="bb730-151">This query selects all customers with any `Order` for which the `OrderDate` equals the `ShipDate` of any `Order`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb730-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb730-152">See Also</span></span>  
 <span data-ttu-id="bb730-153">[Общие сведения о схемах XSD с заметками &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="bb730-153">[Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="bb730-154">Форматирование XML на стороне клиента &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="bb730-154">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
