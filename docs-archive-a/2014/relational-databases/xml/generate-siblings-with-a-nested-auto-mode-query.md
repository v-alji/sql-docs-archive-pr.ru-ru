---
title: Формирование одноуровневых элементов с помощью вложенного запроса в режиме AUTO | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- queries [XML in SQL Server], nested AUTO mode
- nested AUTO mode query
ms.assetid: 748d9899-589d-4420-8048-1258e9e67c20
author: rothja
ms.author: jroth
ms.openlocfilehash: 20362942bdd0f7e7537433b664e5e63461ded499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751959"
---
# <a name="generate-siblings-with-a-nested-auto-mode-query"></a><span data-ttu-id="44e61-102">Формирование одноуровневых элементов с помощью вложенного запроса в режиме AUTO</span><span class="sxs-lookup"><span data-stu-id="44e61-102">Generate Siblings with a Nested AUTO Mode Query</span></span>
  <span data-ttu-id="44e61-103">В следующем примере показано, как создавать элементы с общим родителем при помощи вложенного запроса в режиме AUTO.</span><span class="sxs-lookup"><span data-stu-id="44e61-103">The following example shows how to generate siblings by using a nested AUTO mode query.</span></span> <span data-ttu-id="44e61-104">Единственный способ создать такой XML — использовать режим EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="44e61-104">The only other way to generate such XML is to use the EXPLICIT mode.</span></span> <span data-ttu-id="44e61-105">Однако пользоваться этим способом не всегда удобно.</span><span class="sxs-lookup"><span data-stu-id="44e61-105">However, this can be cumbersome.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44e61-106">Пример</span><span class="sxs-lookup"><span data-stu-id="44e61-106">Example</span></span>  
 <span data-ttu-id="44e61-107">Этот запрос создает XML, который предоставляет сведения о заказах на продажу.</span><span class="sxs-lookup"><span data-stu-id="44e61-107">This query constructs XML that provides sales order information.</span></span> <span data-ttu-id="44e61-108">Это включает следующие действия.</span><span class="sxs-lookup"><span data-stu-id="44e61-108">This includes the following:</span></span>  
  
-   <span data-ttu-id="44e61-109">Данные заголовка заказа на продажу, `SalesOrderID`, `SalesPersonID`и `OrderDate`.</span><span class="sxs-lookup"><span data-stu-id="44e61-109">Sales order header information, `SalesOrderID`, `SalesPersonID`, and `OrderDate`.</span></span> [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="44e61-110">сохраняет эти данные в таблице `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="44e61-110">stores this information in the `SalesOrderHeader` table.</span></span>  
  
-   <span data-ttu-id="44e61-111">Дополнительные сведения о заказе на продажу.</span><span class="sxs-lookup"><span data-stu-id="44e61-111">Sales order detail information.</span></span> <span data-ttu-id="44e61-112">Она включает один или несколько заказанных продуктов, цену за штуку и заказанное количество.</span><span class="sxs-lookup"><span data-stu-id="44e61-112">This includes one or more products ordered, the unit price, and the quantity ordered.</span></span> <span data-ttu-id="44e61-113">Эти сведения хранятся в таблице `SalesOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="44e61-113">This information is stored in the `SalesOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="44e61-114">Сведения о менеджере по продажам.</span><span class="sxs-lookup"><span data-stu-id="44e61-114">Sales person information.</span></span> <span data-ttu-id="44e61-115">Сведения о менеджере по продажам, принявшем заказ.</span><span class="sxs-lookup"><span data-stu-id="44e61-115">This is the salesperson who took the order.</span></span> <span data-ttu-id="44e61-116">В таблице `SalesPerson` хранятся идентификаторы `SalesPersonID`.</span><span class="sxs-lookup"><span data-stu-id="44e61-116">The `SalesPerson` table provides the `SalesPersonID`.</span></span> <span data-ttu-id="44e61-117">Чтобы найти имя менеджера по продажам, в этом запросе данную таблицу необходимо соединить с таблицей `Employee` .</span><span class="sxs-lookup"><span data-stu-id="44e61-117">For this query, you have to join this table to the `Employee` table to find the name of the sales person.</span></span>  
  
 <span data-ttu-id="44e61-118">Два отдельных запроса `SELECT`, показанных ниже, создают XML-документ с небольшими различиями в формате данных.</span><span class="sxs-lookup"><span data-stu-id="44e61-118">The two distinct `SELECT` queries that follow generate XML with a small difference in shape.</span></span>  
  
 <span data-ttu-id="44e61-119">Первый запрос создает XML, в котором <`SalesPerson`> и <`SalesOrderHeader`> появляются как потомки общего родителя <`SalesOrder`>:</span><span class="sxs-lookup"><span data-stu-id="44e61-119">The first query generates XML in which <`SalesPerson`> and <`SalesOrderHeader`> appear as sibling children of <`SalesOrder`>:</span></span>  
  
```  
SELECT   
      (SELECT top 2 SalesOrderID, SalesPersonID, CustomerID,  
         (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
           from Sales.SalesOrderDetail  
            WHERE  SalesOrderDetail.SalesOrderID =   
                   SalesOrderHeader.SalesOrderID  
            FOR XML AUTO, TYPE)  
        FROM  Sales.SalesOrderHeader  
        WHERE SalesOrderHeader.SalesOrderID = SalesOrder.SalesOrderID  
        for xml auto, type),  
        (SELECT *   
         FROM  (SELECT SalesPersonID, EmployeeID  
              FROM Sales.SalesPerson, HumanResources.Employee  
              WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As   
                     SalesPerson  
         WHERE  SalesPerson.SalesPersonID = SalesOrder.SalesPersonID  
       FOR XML AUTO, TYPE)  
FROM (SELECT SalesOrderHeader.SalesOrderID, SalesOrderHeader.SalesPersonID  
      FROM Sales.SalesOrderHeader, Sales.SalesPerson  
      WHERE SalesOrderHeader.SalesPersonID = SalesPerson.SalesPersonID  
     ) as SalesOrder  
ORDER BY SalesOrder.SalesOrderID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="44e61-120">В предшествующем запросе самая внешняя инструкция `SELECT` выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="44e61-120">In the previous query, the outermost `SELECT` statement does the following:</span></span>  
  
-   <span data-ttu-id="44e61-121">Запрашивает набор строк `SalesOrder`, указанный в предложении `FROM`.</span><span class="sxs-lookup"><span data-stu-id="44e61-121">Queries the rowset, `SalesOrder`, specified in the `FROM` clause.</span></span> <span data-ttu-id="44e61-122">Результат — XML с одним или несколькими элементами <`SalesOrder`>.</span><span class="sxs-lookup"><span data-stu-id="44e61-122">The result is an XML with one or more <`SalesOrder`> elements.</span></span>  
  
-   <span data-ttu-id="44e61-123">Указывает режим `AUTO` и директиву `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="44e61-123">Specifies `AUTO` mode and the `TYPE` directive.</span></span> <span data-ttu-id="44e61-124">`AUTO`режим преобразует результат запроса в XML, а `TYPE` директива возвращает результат в виде `xml` типа.</span><span class="sxs-lookup"><span data-stu-id="44e61-124">`AUTO` mode transforms the query result into XML, and the `TYPE` directive returns the result as `xml` type.</span></span>  
  
-   <span data-ttu-id="44e61-125">Содержит две вложенные инструкции `SELECT` , разделенные запятой.</span><span class="sxs-lookup"><span data-stu-id="44e61-125">Includes two nested `SELECT` statements separated by a comma.</span></span> <span data-ttu-id="44e61-126">Первая вложенная инструкция `SELECT` получает сведения о заказе на продажу, заголовок и дополнительные сведения, а вторая инструкция `SELECT` получает сведения о менеджере по продажам.</span><span class="sxs-lookup"><span data-stu-id="44e61-126">The first nested `SELECT` retrieves sales order information, header and details, and the second nested `SELECT` statement retrieves salesperson information.</span></span>  
  
    -   <span data-ttu-id="44e61-127">Инструкция `SELECT` , получающая `SalesOrderID`, `SalesPersonID`и `CustomerID` , содержит вложенную инструкцию `SELECT ... FOR XML` (с режимом `AUTO` и директивой `TYPE` ), возвращающую подробные данные о заказе на продажу.</span><span class="sxs-lookup"><span data-stu-id="44e61-127">The `SELECT` statement that retrieves `SalesOrderID`, `SalesPersonID`, and `CustomerID` itself includes another nested `SELECT ... FOR XML` statement (with `AUTO` mode and `TYPE` directive) that returns sales order detail information.</span></span>  
  
 <span data-ttu-id="44e61-128">Инструкция `SELECT` , которая получает сведения о менеджере по продажам, запрашивает набор строк `SalesPerson`, созданный в предложении `FROM` .</span><span class="sxs-lookup"><span data-stu-id="44e61-128">The `SELECT` statement that retrieves the sales person information queries a rowset, `SalesPerson`, created in the `FROM` clause.</span></span> <span data-ttu-id="44e61-129">Для работы запросов `FOR XML` необходимо указать имя для анонимного набора строк, создаваемого в предложении `FROM` .</span><span class="sxs-lookup"><span data-stu-id="44e61-129">For `FOR XML` queries to work, you must provide a name for the anonymous rowset generated in the `FROM` clause.</span></span> <span data-ttu-id="44e61-130">В данном случае указано имя `SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="44e61-130">In this case, the name provided is `SalesPerson`.</span></span>  
  
 <span data-ttu-id="44e61-131">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="44e61-131">This is the partial result:</span></span>  
  
```  
<SalesOrder>  
  <Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  </Sales.SalesOrderHeader>  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</SalesOrder>  
...  
```  
  
 <span data-ttu-id="44e61-132">Следующий запрос формирует те же сведения о заказе, за исключением результирующего XML; <`SalesPerson`> представляет собой элемент, имеющий общего родителя с <`SalesOrderDetail`>:</span><span class="sxs-lookup"><span data-stu-id="44e61-132">The following query generates the same sales order information, except that in the resulting XML, the <`SalesPerson`> appears as a sibling of <`SalesOrderDetail`>:</span></span>  
  
```  
<SalesOrder>  
    <SalesOrderHeader ...>  
          <SalesOrderDetail .../>  
          <SalesOrderDetail .../>  
          ...  
          <SalesPerson .../>  
    </SalesOrderHeader>  
  
</SalesOrder>  
<SalesOrder>  
  ...  
</SalesOrder>  
```  
  
 <span data-ttu-id="44e61-133">Запрос является таковым:</span><span class="sxs-lookup"><span data-stu-id="44e61-133">This is the query:</span></span>  
  
```  
SELECT SalesOrderID, SalesPersonID, CustomerID,  
             (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
              from Sales.SalesOrderDetail  
              WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
              FOR XML AUTO, TYPE),  
              (SELECT *   
               FROM  (SELECT SalesPersonID, EmployeeID  
                    FROM Sales.SalesPerson, HumanResources.Employee  
                    WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
               WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
         FOR XML AUTO, TYPE)  
FROM Sales.SalesOrderHeader  
WHERE SalesOrderID=43659 or SalesOrderID=43660  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="44e61-134">Результат:</span><span class="sxs-lookup"><span data-stu-id="44e61-134">This is the result:</span></span>  
  
```  
<Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
<Sales.SalesOrderHeader SalesOrderID="43660" SalesPersonID="279" CustomerID="117">  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="762" OrderQty="1" UnitPrice="419.4589" />  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="758" OrderQty="1" UnitPrice="874.7940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
```  
  
 <span data-ttu-id="44e61-135">Директива `TYPE` возвращает результат запроса как тип данных `xml`, поэтому можно выполнять запросы к результирующему XML с использованием различных методов типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="44e61-135">Because the `TYPE` directive returns a query result as `xml` type, you can query the resulting XML by using various `xml` data type methods.</span></span> <span data-ttu-id="44e61-136">Дополнительные сведения см. в разделе [Методы типа данных xml](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="44e61-136">For more information, see [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span> <span data-ttu-id="44e61-137">В приведенном далее запросе обратите внимание на следующее.</span><span class="sxs-lookup"><span data-stu-id="44e61-137">In the following query, note the following:</span></span>  
  
-   <span data-ttu-id="44e61-138">Предшествующий запрос добавлен в предложении `FROM` .</span><span class="sxs-lookup"><span data-stu-id="44e61-138">The previous query is added in the `FROM` clause.</span></span> <span data-ttu-id="44e61-139">Результат запроса возвращается в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="44e61-139">The query result is returned as a table.</span></span> <span data-ttu-id="44e61-140">Следует обратить внимание, что добавлен псевдоним `XmlCol` .</span><span class="sxs-lookup"><span data-stu-id="44e61-140">Note the `XmlCol` alias that is added.</span></span>  
  
-   <span data-ttu-id="44e61-141">Предложение `SELECT` определяет запрос XQuery к `XmlCol` , возвращаемому в предложении `FROM` .</span><span class="sxs-lookup"><span data-stu-id="44e61-141">The `SELECT` clause specifies an XQuery against the `XmlCol` returned in the `FROM` clause.</span></span> <span data-ttu-id="44e61-142">Для указания запроса XQuery применяется метод `query()` типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="44e61-142">The `query()` method of the `xml` data type is used in specifying the XQuery.</span></span> <span data-ttu-id="44e61-143">Дополнительные сведения см. в разделе [Метод query&#40;&#41;&#40;тип данных xml&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="44e61-143">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
    ```  
    SELECT XmlCol.query('<Root> { /* } </Root>')  
    FROM (  
    SELECT SalesOrderID, SalesPersonID, CustomerID,  
                 (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
                  from Sales.SalesOrderDetail  
                  WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
                  FOR XML AUTO, TYPE),  
                  (SELECT *   
                   FROM  (SELECT SalesPersonID, EmployeeID  
                        FROM Sales.SalesPerson, HumanResources.Employee  
                        WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
                   WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
             FOR XML AUTO, TYPE)  
    FROM Sales.SalesOrderHeader  
    WHERE SalesOrderID='43659' or SalesOrderID='43660'  
    FOR XML AUTO, TYPE ) as T(XmlCol)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="44e61-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="44e61-144">See Also</span></span>  
 [<span data-ttu-id="44e61-145">Использование вложенных запросов FOR XML</span><span class="sxs-lookup"><span data-stu-id="44e61-145">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
