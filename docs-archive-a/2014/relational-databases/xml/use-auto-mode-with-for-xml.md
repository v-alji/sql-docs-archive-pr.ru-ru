---
title: Использование режима AUTO для FOR XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, AUTO mode
- ELEMENTS option
- FOR XML AUTO mode
- AUTO FOR XML mode
ms.assetid: 7140d656-1d42-4f01-a533-5251429f4450
author: rothja
ms.author: jroth
ms.openlocfilehash: 232cc046667c6d31cb9657a7abdc862204507d23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664782"
---
# <a name="use-auto-mode-with-for-xml"></a><span data-ttu-id="e4fa9-102">Использование с AUTO Mode для FOR XML</span><span class="sxs-lookup"><span data-stu-id="e4fa9-102">Use AUTO Mode with FOR XML</span></span>
  <span data-ttu-id="e4fa9-103">Как описано в статье [FOR XML (SQL Server)](for-xml-sql-server.md), в режиме AUTO результаты запросов возвращаются в виде вложенных XML-элементов.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-103">As described in [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), AUTO mode returns query results as nested XML elements.</span></span> <span data-ttu-id="e4fa9-104">Такой механизм не обеспечивает достаточное управление структурой XML, формируемой из результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-104">This does not provide much control over the shape of the XML generated from a query result.</span></span> <span data-ttu-id="e4fa9-105">Запросы в режиме AUTO полезны, если необходимо формировать простые иерархии.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-105">The AUTO mode queries are useful if you want to generate simple hierarchies.</span></span> <span data-ttu-id="e4fa9-106">При этом [использование режима EXPLICIT совместно с предложением FOR XML](use-explicit-mode-with-for-xml.md) и [использование режима PATH совместно с FOR XML](use-path-mode-with-for-xml.md) дают больше контроля и гибкости при выборе формы XML из результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-106">However, [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) and [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) provide more control and flexibility in deciding the shape of the XML from a query result.</span></span>  
  
 <span data-ttu-id="e4fa9-107">Каждая таблица в предложении FROM, из которой по крайней мере один столбец присутствует в предложении SELECT, представляется как элемент XML.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-107">Each table in the FROM clause, from which at least one column is listed in the SELECT clause, is represented as an XML element.</span></span> <span data-ttu-id="e4fa9-108">Столбцы, перечисляемые в предложении SELECT, сопоставляются атрибутам или подчиненным элементам, если в предложении FOR XML указан необязательный аргумент ELEMENTS.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-108">The columns listed in the SELECT clause are mapped to attributes or subelements, if the optional ELEMENTS option is specified in the FOR XML clause.</span></span>  
  
 <span data-ttu-id="e4fa9-109">XML-иерархия (порядок вложенности элементов) в результирующих XML-данных основана на порядке таблиц, определяемых столбцами, которые указаны в предложении SELECT.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-109">The XML hierarchy, nesting of the elements, in the resulting XML is based on the order of tables identified by the columns specified in the SELECT clause.</span></span> <span data-ttu-id="e4fa9-110">Поэтому важен порядок, в котором в предложении SELECT указываются имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-110">Therefore, the order in which column names are specified in the SELECT clause is significant.</span></span> <span data-ttu-id="e4fa9-111">Первая, самая левая идентифицируемая таблица образует верхний элемент в результирующем XML-документе.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-111">The first, leftmost table that is identified forms the top element in the resulting XML document.</span></span> <span data-ttu-id="e4fa9-112">Вторая слева таблица, идентифицируемая столбцами в инструкции SELECT, образует элемент, подчиненный верхнему элементу и т. д.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-112">The second leftmost table, identified by columns in the SELECT statement, forms a subelement within the top element, and so on.</span></span>  
  
 <span data-ttu-id="e4fa9-113">Если столбец, имя которого указывается в предложении SELECT, принадлежит таблице, уже идентифицируемой столбцом, заданным до этого в предложении SELECT, вместо открытия нового уровня иерархии этот столбец добавляется как атрибут уже созданного элемента.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-113">If a column name listed in the SELECT clause is from a table that is already identified by a previously specified column in the SELECT clause, the column is added as an attribute of the element already created, instead of opening a new level of hierarchy.</span></span> <span data-ttu-id="e4fa9-114">Если указан аргумент ELEMENTS, столбец добавляется как атрибут.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-114">If the ELEMENTS option is specified, the column is added as an attribute.</span></span>  
  
 <span data-ttu-id="e4fa9-115">В качестве примера рассмотрим выполнение следующего запроса:</span><span class="sxs-lookup"><span data-stu-id="e4fa9-115">For example, execute this query:</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO  
```  
  
 <span data-ttu-id="e4fa9-116">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="e4fa9-116">This is the partial result:</span></span>  
  
```  
<Cust CustomerID="1" CustomerType="S">  
  <OrderHeader CustomerID="1" SalesOrderID="43860" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="44501" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="45283" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="46042" Status="5" />  
</Cust>  
...  
```  
  
 <span data-ttu-id="e4fa9-117">В предложении SELECT следует отметить следующее.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-117">Note the following in the SELECT clause:</span></span>  
  
-   <span data-ttu-id="e4fa9-118">Идентификатор CustomerID ссылается на таблицу «Cust».</span><span class="sxs-lookup"><span data-stu-id="e4fa9-118">The CustomerID references the Cust table.</span></span> <span data-ttu-id="e4fa9-119">Поэтому создается элемент <`Cust`>, а CustomerID добавляется как его атрибут.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-119">Therefore, a <`Cust`> element is created and CustomerID is added as its attribute.</span></span>  
  
-   <span data-ttu-id="e4fa9-120">Далее три столбца, OrderHeader.CustomerID, OrderHeader.SaleOrderID и OrderHeader.Status ссылаются на таблицу OrderHeader.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-120">Next, three columns, OrderHeader.CustomerID, OrderHeader.SaleOrderID, and OrderHeader.Status, reference the OrderHeader table.</span></span> <span data-ttu-id="e4fa9-121">Поэтому элемент <`OrderHeader`> добавляется как подчиненный элемент элемента <`Cust`>, и три столбца добавляются как атрибуты <`OrderHeader`>.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-121">Therefore, an <`OrderHeader`> element is added as a subelement of the <`Cust`> element and the three columns are added as attributes of <`OrderHeader`>.</span></span>  
  
-   <span data-ttu-id="e4fa9-122">Далее, столбец Cust.CustomerType вновь ссылается на таблицу «Cust», которая уже была идентифицирована столбцом Cust.CustomerID.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-122">Next, the Cust.CustomerType column again references the Cust table that was already identified by the Cust.CustomerID column.</span></span> <span data-ttu-id="e4fa9-123">Поэтому никакого нового элемента не создается.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-123">Therefore, no new element is created.</span></span> <span data-ttu-id="e4fa9-124">Вместо этого атрибут CustomerType добавляется к созданному до этого элементу <`Cust`>.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-124">Instead, the CustomerType attribute is added to the <`Cust`> element that was previously created.</span></span>  
  
-   <span data-ttu-id="e4fa9-125">Запрос задает псевдонимы для имен таблиц.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-125">The query specifies aliases for the table names.</span></span> <span data-ttu-id="e4fa9-126">Эти псевдонимы представляются как имена соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-126">These aliases appear as corresponding element names.</span></span>  
  
-   <span data-ttu-id="e4fa9-127">Для группирования всех дочерних элементов одного родителя необходимо предложение ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-127">ORDER BY is required to group all children under one parent.</span></span>  
  
 <span data-ttu-id="e4fa9-128">Следующий запрос аналогичен предыдущему, за исключением того, что предложение SELECT задает столбцы в таблице OrderHeader перед столбцами в таблице «Cust».</span><span class="sxs-lookup"><span data-stu-id="e4fa9-128">This query is similar to the previous one, except the SELECT clause specifies columns in the OrderHeader table before the columns in the Cust table.</span></span> <span data-ttu-id="e4fa9-129">Поэтому первым создается элемент <`OrderHeader`>, а к нему добавляется дочерний элемент <`Cust`>.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-129">Therefore, first <`OrderHeader`> element is created and then the <`Cust`> child element is added to it.</span></span>  
  
```  
select OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerID,   
       Cust.CustomerType  
from Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
where Cust.CustomerID = OrderHeader.CustomerID  
for xml auto  
```  
  
 <span data-ttu-id="e4fa9-130">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="e4fa9-130">This is the partial result:</span></span>  
  
```  
<OrderHeader CustomerID="1" SalesOrderID="43860" Status="5">  
  <Cust CustomerID="1" CustomerType="S" />  
</OrderHeader>  
...  
```  
  
 <span data-ttu-id="e4fa9-131">Если в предложение FOR XML добавляется аргумент ELEMENTS, происходит возврат кода XML, основанного на элементах.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-131">If the ELEMENTS option is added in the FOR XML clause, element-centric XML is returned.</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="e4fa9-132">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="e4fa9-132">This is the partial result:</span></span>  
  
```  
<Cust>  
  <CustomerID>1</CustomerID>  
  <CustomerType>S</CustomerType>  
  <OrderHeader>  
    <CustomerID>1</CustomerID>  
    <SalesOrderID>43860</SalesOrderID>  
    <Status>5</Status>  
  </OrderHeader>  
   ...  
</Cust>  
...  
```  
  
 <span data-ttu-id="e4fa9-133">В этом запросе при создании элементов \<Cust> значение идентификатора CustomerID из одной строки сравнивается со значением этого идентификатора из следующей строки, так как CustomerID является первичным ключом таблицы.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-133">In this query, the CustomerID values are compared from one row to the next in creating the \<Cust> elements, because CustomerID is the primary key of the table.</span></span> <span data-ttu-id="e4fa9-134">Если CustomerID не идентифицирован для таблицы как первичный ключ, во всех столбцах (CustomerID и CustomerType в этом запросе) проводится сравнение каждой строки со следующей строкой.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-134">If CustomerID is not identified as the primary key for the table, all the column values (CustomerID, CustomerType in this query) are compared from one row to the next.</span></span> <span data-ttu-id="e4fa9-135">Если значения строк различаются, в XML добавляется новый элемент \<Cust>.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-135">If the values differ, a new \<Cust> element is added to the XML.</span></span>  
  
 <span data-ttu-id="e4fa9-136">Если сравниваемые столбцы имеют тип данных **text**, **ntext**, **image**или **xml**, при сравнении значений соответствующих строк использование FOR XML предполагает, что значения различаются, поэтому они не сравниваются, даже если могут быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-136">When comparing these column values, if any of the columns to be compared are of type **text**, **ntext**, **image**, or **xml**, FOR XML assumes that the values are different and not compared, even though they may be the same.</span></span> <span data-ttu-id="e4fa9-137">Причиной этого является то, что сравнение больших объектов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-137">This is because comparing large objects is not supported.</span></span> <span data-ttu-id="e4fa9-138">Элементы добавляются в результат для каждой выбранной строки.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-138">Elements are added to the result for each row selected.</span></span> <span data-ttu-id="e4fa9-139">Обратите внимание на то, что столбцы типа **(n)varchar(max)** и **varbinary(max)** сравниваются.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-139">Note that columns of **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="e4fa9-140">Если столбец в предложении SELECT не может быть сопоставлен ни с одной таблицей, идентифицируемой в предложении FROM, как в случае столбца со статистическими выражениями или вычисляемого столбца, столбец добавляется в XML-документ на самый глубокий уровень вложенности, если он присутствует в списке.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-140">When a column in the SELECT clause cannot be associated with any of the tables identified in the FROM clause, as in the case of an aggregate column or computed column, the column is added in the XML document in the deepest nesting level in place when it is encountered in the list.</span></span> <span data-ttu-id="e4fa9-141">Если такой столбец является первым столбцом в предложении SELECT, столбец добавляется к верхнему элементу.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-141">If such a column appears as the first column in the SELECT clause, the column is added to the top element.</span></span>  
  
 <span data-ttu-id="e4fa9-142">Если в предложении SELECT задается символ-шаблон «\*», вложенность определяется таким же образом, как это описано выше, на основании порядка, в котором строки возвращаются механизмом запроса.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-142">If the asterisk (\*) wildcard character is specified in the SELECT clause, the nesting is determined in the same way as previously described, based on the order that the rows are returned by the query engine.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4fa9-143">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e4fa9-143">In This Section</span></span>  
 <span data-ttu-id="e4fa9-144">В следующих подразделах представлены дополнительные сведения о режиме AUTO.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-144">The following topics provide more information about AUTO mode:</span></span>  
  
-   [<span data-ttu-id="e4fa9-145">Использование параметра BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="e4fa9-145">Use the BINARY BASE64 Option</span></span>](use-the-binary-base64-option.md)  
  
-   [<span data-ttu-id="e4fa9-146">Эвристические методы режима AUTO, используемые при формировании возвращаемого XML-кода</span><span class="sxs-lookup"><span data-stu-id="e4fa9-146">AUTO Mode Heuristics in Shaping Returned XML</span></span>](auto-mode-heuristics-in-shaping-returned-xml.md)  
  
-   [<span data-ttu-id="e4fa9-147">Примеры. Использование режима AUTO</span><span class="sxs-lookup"><span data-stu-id="e4fa9-147">Examples: Using AUTO Mode</span></span>](examples-using-auto-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="e4fa9-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="e4fa9-148">See Also</span></span>  
 <span data-ttu-id="e4fa9-149">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e4fa9-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="e4fa9-150">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e4fa9-150">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
