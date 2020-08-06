---
title: Столбцы с именем | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: c994e089-4cfc-4e9b-b7fc-e74f6014b51a
author: rothja
ms.author: jroth
ms.openlocfilehash: 32cfe617b80ed216374249961b85eae401011a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729169"
---
# <a name="columns-with-a-name"></a><span data-ttu-id="c2ec7-102">Столбцы с именем</span><span class="sxs-lookup"><span data-stu-id="c2ec7-102">Columns with a Name</span></span>
  <span data-ttu-id="c2ec7-103">Ниже приведены условия, при которых столбцы наборов строк с соответствующим именем сопоставляются с итоговым XML-документом с учетом регистра:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-103">The following are the specific conditions in which rowset columns with a name are mapped, case-sensitive, to the resulting XML:</span></span>  
  
-   <span data-ttu-id="c2ec7-104">имя столбца начинается с символа \@;</span><span class="sxs-lookup"><span data-stu-id="c2ec7-104">The column name starts with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="c2ec7-105">имя столбца не начинается с символа \@;</span><span class="sxs-lookup"><span data-stu-id="c2ec7-105">The column name does not start with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="c2ec7-106">имя столбца не начинается с символа \@ и содержит косую черту (/);</span><span class="sxs-lookup"><span data-stu-id="c2ec7-106">The column name does not start with an at sign\@ and contains a slash mark (/).</span></span>  
  
-   <span data-ttu-id="c2ec7-107">несколько столбцов имеют одинаковый префикс;</span><span class="sxs-lookup"><span data-stu-id="c2ec7-107">Several columns share the same prefix.</span></span>  
  
-   <span data-ttu-id="c2ec7-108">один из столбцов имеет другое имя.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-108">One column has a different name.</span></span>  
  
## <a name="column-name-starts-with-an-at-sign-"></a><span data-ttu-id="c2ec7-109">Имя столбца начинается с символа \@</span><span class="sxs-lookup"><span data-stu-id="c2ec7-109">Column Name Starts with an At Sign (\@)</span></span>  
 <span data-ttu-id="c2ec7-110">Если имя столбца начинается с символа ( \@ ) и не содержит косой черты (/), то `row` создается атрибут элемента <>, имеющего соответствующее значение столбца.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-110">If the column name starts with an at sign (\@) and does not contain a slash mark (/), an attribute of the <`row`> element that has the corresponding column value is created.</span></span> <span data-ttu-id="c2ec7-111">Например, следующий запрос возвращает набор строк с двумя столбцами (\@PmId, Name).</span><span class="sxs-lookup"><span data-stu-id="c2ec7-111">For example, the following query returns a two-column (\@PmId, Name) rowset.</span></span> <span data-ttu-id="c2ec7-112">В итоговом XML-документе атрибут **PmId** добавляется к соответствующему элементу <`row`>, и ему присваивается значение столбца ProductModelID.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-112">In the resulting XML, a **PmId** attribute is added to the corresponding <`row`> element and a value of ProductModelID is assigned to it.</span></span>  
  
```  
  
SELECT ProductModelID as "@PmId",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
  
```  
  
 <span data-ttu-id="c2ec7-113">Результат:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-113">This is the result:</span></span>  
  
```  
<row PmId="7">  
  <Name>HL Touring Frame</Name>  
</row>  
```  
  
 <span data-ttu-id="c2ec7-114">Обратите внимание, что на одном уровне атрибуты должны располагаться перед любыми другими типами узлов, например, перед узлами элементов и текстовыми узлами.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-114">Note that attributes must come before any other node types, such as element nodes and text nodes, in the same level.</span></span> <span data-ttu-id="c2ec7-115">Следующий запрос возвращает ошибку:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-115">The following query will return an error:</span></span>  
  
```  
SELECT Name,  
       ProductModelID as "@PmId"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign-"></a><span data-ttu-id="c2ec7-116">Имя столбца не начинается с символа \@</span><span class="sxs-lookup"><span data-stu-id="c2ec7-116">Column Name Does Not Start with an At Sign (\@)</span></span>  
 <span data-ttu-id="c2ec7-117">Если имя столбца не начинается с символа @ \@ , не является одним из проверок узла XPath и не содержит косую черту (/), то создается элемент XML, который является вложенным элементом элемента Row, <`row`> по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-117">If the column name does not start with an at sign (\@), is not one of the XPath node tests, and does not contain a slash mark (/), an XML element that is a subelement of the row element, <`row`> by default, is created.</span></span>  
  
 <span data-ttu-id="c2ec7-118">В результате следующего запроса указывается имя столбца.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-118">The following query specifies the column name, the result.</span></span> <span data-ttu-id="c2ec7-119">Дочерний элемент <`result`> добавляется к элементу <`row`>.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-119">Therefore, a <`result`> element child is added to the <`row`> element.</span></span>  
  
```  
SELECT 2+2 as result  
for xml PATH  
```  
  
 <span data-ttu-id="c2ec7-120">Результат:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-120">This is the result:</span></span>  
  
```  
<row>  
  <result>4</result>  
</row>  
```  
  
 <span data-ttu-id="c2ec7-121">Следующий запрос указывает имя столбца ManuWorkCenterInformation для XML-данных, возвращенных запросом XQuery, указанным по отношению к столбцу Instructions типа **xml** .</span><span class="sxs-lookup"><span data-stu-id="c2ec7-121">The following query specifies the column name, ManuWorkCenterInformation, for the XML returned by the XQuery specified against Instructions column of **xml** type.</span></span> <span data-ttu-id="c2ec7-122">Элемент <`ManuWorkCenterInformation`> добавляется в качестве дочернего к элементу <`row`>.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-122">Therefore, a <`ManuWorkCenterInformation`> element is added as a child of the <`row`> element.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') as ManuWorkCenterInformation  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
 <span data-ttu-id="c2ec7-123">Результат:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-123">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>7</ProductModelID>  
  <Name>HL Touring Frame</Name>  
  <ManuWorkCenterInformation>  
    <MI:Location ...LocationID="10" ...></MI:Location>  
    <MI:Location ...LocationID="20" ...></MI:Location>  
     ...  
  </ManuWorkCenterInformation>  
</row>  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign--and-contains-a-slash-mark-"></a><span data-ttu-id="c2ec7-124">Имя столбца не начинается с символа \@ и содержит косую черту (/)</span><span class="sxs-lookup"><span data-stu-id="c2ec7-124">Column Name Does Not Start with an At Sign (\@) and Contains a Slash Mark (/)</span></span>  
 <span data-ttu-id="c2ec7-125">Если имя столбца не начинается с символа \@, но содержит косую черту (/), оно является признаком иерархии XML.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-125">If the column name does not start with an at sign (\@), but contains a slash mark (/), the column name indicates an XML hierarchy.</span></span> <span data-ttu-id="c2ec7-126">Например, если столбец имеет имя "Имя1/Имя2/Имя3.../Имя***n*** ", каждое Имя***i*** представляет имя элемента, вложенного в элемент текущей строки (для i=1) или расположенного под элементом Имя***i-1***.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-126">For example, if the column name is "Name1/Name2/Name3.../Name***n*** ", each Name***i*** represents an element name that is nested in the current row element (for i=1) or that is under the element that has the name Name***i-1***.</span></span> <span data-ttu-id="c2ec7-127">Если Имя***n*** начинается с символа \@, оно сопоставляется с атрибутом элемента Имя***n-1***.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-127">If Name***n*** starts with '\@', it is mapped to an attribute of Name***n-1*** element.</span></span>  
  
 <span data-ttu-id="c2ec7-128">Например, следующий запрос возвращает идентификатор работника и имя, представленное сложным элементом EmpName, который включает в себя имя, отчество и фамилию работника.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-128">For example, the following query returns an employee ID and name that are represented as a complex element EmpName that contains a First, Middle, and Last name.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="c2ec7-129">Имена столбцов используются в качестве пути при построении XML-документа в режиме PATH.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-129">The column names are used as a path in constructing XML in the PATH mode.</span></span> <span data-ttu-id="c2ec7-130">Имя столбца, содержащего значения идентификатора сотрудника, начинается с " \@ ". Таким образом, атрибут **EmpID**добавляется к `row` элементу> <.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-130">The column name that contains employee ID values, starts with '\@'.Therefore, an attribute, **EmpID**, is added to the <`row`> element.</span></span> <span data-ttu-id="c2ec7-131">Имена всех других столбцов содержат символ косой черты (/), являющийся признаком иерархии.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-131">All other columns include a slash mark ('/') in the column name that indicates hierarchy.</span></span> <span data-ttu-id="c2ec7-132">В итоговом XML-документе будет присутствовать дочерний элемент <`EmpName`> внутри элемента <`row`>, а элемент <`EmpName`> будет в свою очередь содержать дочерние элементы <`First`>, <`Middle`> и <`Last`>.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-132">The resulting XML will have the <`EmpName`> child under the <`row`> element, and the <`EmpName`> child will have <`First`>, <`Middle`> and <`Last`> element children.</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="c2ec7-133">Отчество работника имеет значение NULL, которое по умолчанию сопоставляется с отсутствием элемента или атрибута.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-133">The employee middle name is null and, by default, the null value maps to the absence of the element or attribute.</span></span> <span data-ttu-id="c2ec7-134">Если необходимо сформировать элементы для значений NULL, укажите директиву ELEMENTS с ключевым словом XSINIL, как показано в данном запросе.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-134">If you want elements generated for the NULL values, you can specify the ELEMENTS directive with XSINIL as shown in this query.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="c2ec7-135">Результат:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-135">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
      EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="c2ec7-136">По умолчанию в режиме PATH формируется элементно-ориентированный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-136">By default, the PATH mode generates element-centric XML.</span></span> <span data-ttu-id="c2ec7-137">Поэтому указание директивы ELEMENTS в режиме PATH не имеет никакого смысла.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-137">Therefore, specifying the ELEMENTS directive in a PATH mode query has no effect.</span></span> <span data-ttu-id="c2ec7-138">Однако как показано в предыдущем примере, директива ELEMENTS с ключевым словом XSINIL может быть полезна при формировании элементов для значений NULL.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-138">However, as shown in the previous example, the ELEMENTS directive is useful with XSINIL to generate elements for null values.</span></span>  
  
 <span data-ttu-id="c2ec7-139">Следующий запрос кроме идентификатора и имени возвращает еще и адрес работника.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-139">Besides the ID and name, the following query retrieves an employee address.</span></span> <span data-ttu-id="c2ec7-140">В соответствии с путем, указанным в именах столбцов адресов, дочерний элемент <`Address`> добавляется к элементу <`row`>, а подробные сведения об адресе добавляются в качестве дочерних элементов к элементу <`Address`>.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-140">As per the path in the column names for address columns, an <`Address`> element child is added to the <`row`> element and the address details are added as element children of the <`Address`> element.</span></span>  
  
```  
SELECT EmployeeID   "@EmpID",   
       FirstName    "EmpName/First",   
       MiddleName   "EmpName/Middle",   
       LastName     "EmpName/Last",  
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City         "Address/City"  
FROM   HumanResources.Employee E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="c2ec7-141">Результат:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-141">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
</row>  
```  
  
## <a name="several-columns-share-the-same-path-prefix"></a><span data-ttu-id="c2ec7-142">Несколько столбцов имеют одинаковый префикс пути</span><span class="sxs-lookup"><span data-stu-id="c2ec7-142">Several Columns Share the Same Path Prefix</span></span>  
 <span data-ttu-id="c2ec7-143">Если несколько последовательных столбцов имеют одинаковый префикс пути, производится их группировка под одним именем.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-143">If several subsequent columns share the same path prefix, they are grouped together under the same name.</span></span> <span data-ttu-id="c2ec7-144">Если используется одно и то же пространство имен, но разные префиксы пространства имен, путь считается отличающимся.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-144">If different namespace prefixes are being used even if they are bound to the same namespace, a path is considered different.</span></span> <span data-ttu-id="c2ec7-145">В предыдущем запросе столбцы FirstName, MiddleName и LastName имеют один и тот же префикс EmpName. Поэтому они добавляются как дочерние элементы элемента <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-145">In the previous query, the FirstName, MiddleName, and LastName columns share the same EmpName prefix.Therefore, they are added as children of the <`EmpName`> element.</span></span> <span data-ttu-id="c2ec7-146">Это справедливо также для случая создания элемента <`Address`>, показанного в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-146">This is also the case when you were creating the <`Address`> element in the previous example.</span></span>  
  
## <a name="one-column-has-a-different-name"></a><span data-ttu-id="c2ec7-147">Один из столбцов имеет другое имя</span><span class="sxs-lookup"><span data-stu-id="c2ec7-147">One Column Has a Different Name</span></span>  
 <span data-ttu-id="c2ec7-148">Если между столбцами встречается столбец с другим именем, группирование будет нарушено, как это показано в следующем измененном запросе.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-148">If a column with a different name appears in between, it will break the grouping, as shown in the following modified query.</span></span> <span data-ttu-id="c2ec7-149">Добавляя столбцы с адресом между столбцами FirstName и MiddleName, данный запрос нарушает группирование столбцов FirstName, MiddleName и LastName, указанное в предыдущем запросе.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-149">The query breaks the grouping of FirstName, MiddleName, and LastName, as specified in the previous query, by adding address columns in between the FirstName and MiddleName columns.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName "EmpName/First",   
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City "Address/City",  
       MiddleName "EmpName/Middle",   
       LastName "EmpName/Last"  
FROM   HumanResources.EmployeeAddress E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="c2ec7-150">В результате запрос создает два элемента <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-150">As a result, the query creates two <`EmpName`> elements.</span></span> <span data-ttu-id="c2ec7-151">Первый элемент <`EmpName`> имеет дочерний элемент <`FirstName`>, а второй элемент <`EmpName`> имеет дочерние элементы <`MiddleName`> и <`LastName`>.</span><span class="sxs-lookup"><span data-stu-id="c2ec7-151">The first <`EmpName`> element has the <`FirstName`> element child and the second <`EmpName`> element has the <`MiddleName`> and <`LastName`> element children.</span></span>  
  
 <span data-ttu-id="c2ec7-152">Результат:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-152">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
  <EmpName>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2ec7-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="c2ec7-153">See Also</span></span>  
 [<span data-ttu-id="c2ec7-154">Использование режима PATH совместно с FOR XML</span><span class="sxs-lookup"><span data-stu-id="c2ec7-154">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
