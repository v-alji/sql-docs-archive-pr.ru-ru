---
title: Пример Получение сведений о сотрудниках | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- EXPLICIT mode
ms.assetid: 63cd6569-2600-485b-92b4-1f6ba09db219
author: rothja
ms.author: jroth
ms.openlocfilehash: ae4578aedb7dbcc63388d5ef797e3a0bf5d8c306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664785"
---
# <a name="example-retrieving-employee-information"></a><span data-ttu-id="4fc0c-102">Пример Получение сведений о сотрудниках</span><span class="sxs-lookup"><span data-stu-id="4fc0c-102">Example: Retrieving Employee Information</span></span>
  <span data-ttu-id="4fc0c-103">В этом примере извлекаются идентификаторы и имена всех работников.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-103">This example retrieves an employee ID and employee name for each employee.</span></span> <span data-ttu-id="4fc0c-104">В базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] значение employeeID может быть получено из столбца BusinessEntityID таблицы Employee.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-104">In the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, the employeeID can be obtained from the BusinessEntityID column in the Employee table.</span></span> <span data-ttu-id="4fc0c-105">Имена работников могут быть получены из таблицы Person.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-105">Employee names can be obtained from the Person table.</span></span> <span data-ttu-id="4fc0c-106">Столбец BusinessEntityID можно использовать для соединения этих таблиц.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-106">The BusinessEntityID column can be used to join the tables.</span></span>  
  
 <span data-ttu-id="4fc0c-107">Предположим, что требуется произвести преобразование FOR XML EXPLICIT, чтобы сформировать XML так, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="4fc0c-107">Assume that you want FOR XML EXPLICIT transformation to generate XML as shown in the following:</span></span>  
  
```  
<Employee EmpID="1" >  
  <Name FName="Ken" LName="S??nchez" />  
</Employee>  
...  
```  
  
 <span data-ttu-id="4fc0c-108">Так как существует два уровня в иерархии, следует написать два запроса `SELECT` и применить предложение UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-108">Because there are two levels in the hierarchy, you would write two `SELECT` queries and apply UNION ALL.</span></span> <span data-ttu-id="4fc0c-109">Это первый запрос, который извлекает значения для элемента <`Employee`> и его атрибутов.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-109">This is the first query that retrieves values for the <`Employee`> element and its attributes.</span></span> <span data-ttu-id="4fc0c-110">Этот запрос присваивает значение `1` атрибуту `Tag` элемента <`Employee`>, а атрибуту `Parent` значение NULL, так как это элемент верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-110">The query assigns `1` as `Tag` value for the <`Employee`> element and NULL as `Parent`, because it is the top-level element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID AS [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="4fc0c-111">Это второй запрос.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-111">This is the second query.</span></span> <span data-ttu-id="4fc0c-112">Он извлекает значения для элемента <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-112">It retrieves values for the <`Name`> element.</span></span> <span data-ttu-id="4fc0c-113">Присваивает значение `2` атрибуту `Tag` элемента <`Name`> и значение `1` атрибуту `Parent`, определяющее в качестве родителя элемент <`Employee`>.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-113">It assigns `2` as `Tag` value for the <`Name`> element and `1` as `Parent` tag value identifying <`Employee`> as the parent.</span></span>  
  
```  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="4fc0c-114">Объединив эти запросы с помощью инструкции `UNION AL`, примените директиву `FOR XML EXPLICIT`и укажите необходимое предложение `ORDER BY` .</span><span class="sxs-lookup"><span data-stu-id="4fc0c-114">You combine these queries with `UNION AL`L, apply `FOR XML EXPLICIT`, and specify the required `ORDER BY` clause.</span></span> <span data-ttu-id="4fc0c-115">Сначала нужно отсортировать набор строк по значению `BusinessEntityID` , потом по имени, так что значения NULL в именах будут отображаться первыми.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-115">You must sort the rowset first by `BusinessEntityID` and then by name so that the NULL values in the name appear first.</span></span> <span data-ttu-id="4fc0c-116">Выполняя следующий запрос без предложения FOR XML, можно увидеть сформированную универсальную таблицу.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-116">By executing the following query without the FOR XML clause, you can see the universal table generated.</span></span>  
  
 <span data-ttu-id="4fc0c-117">Это окончательный запрос:</span><span class="sxs-lookup"><span data-stu-id="4fc0c-117">This is the final query:</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
ORDER BY [Employee!1!EmpID],[Name!2!FName]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="4fc0c-118">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="4fc0c-118">This is the partial result:</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name FName="Ken" LName="S??nchez" />`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name FName="Terri" LName="Duffy" />`  
  
 `</Employee>`  
  
 `...`  
  
 <span data-ttu-id="4fc0c-119">Первая инструкция `SELECT` указывает имена для столбцов в результирующем наборе строк.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-119">The first `SELECT` specifies names for columns in the resulting rowset.</span></span> <span data-ttu-id="4fc0c-120">Эти имена образуют две группы столбцов.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-120">These names form two column groups.</span></span> <span data-ttu-id="4fc0c-121">Группа со значением `Tag` , равным `1` , в имени столбца задает `Employee` в качестве элемента и `EmpID` в качестве атрибута.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-121">The group that has `Tag` value `1` in the column name identifies `Employee` as an element and `EmpID` as the attribute.</span></span> <span data-ttu-id="4fc0c-122">Другая группа столбцов со значением `Tag`, равным `2`, в имени столбца задает <`Name`> в качестве элемента, а `FName` и `LName` в качестве атрибутов.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-122">The other column group has `Tag` value `2` in the column and identifies <`Name`> as the element and `FName` and `LName` as the attributes.</span></span>  
  
 <span data-ttu-id="4fc0c-123">Следующая таблица показывает частичный набор строк, сформированный запросом:</span><span class="sxs-lookup"><span data-stu-id="4fc0c-123">The following table shows the partial rowset generated by the query:</span></span>  
  
 `Tag Parent  Employee!1!EmpID Name!2!FName Name!2!LName`  
  
 `--- ------  ---------------- ------------ ------------`  
  
 `1   NULL    1                NULL         NULL`  
  
 `2   1       1                Ken          S??nchez`  
  
 `1   NULL    2                NULL         NULL`  
  
 `2   1       2                Terri        Duffy`  
  
 `1   NULL    3                NULL         NULL`  
  
 `2   1       3                Roberto      Tamburello`  
  
 `...`  
  
 <span data-ttu-id="4fc0c-124">Вот как строки универсальной таблицы обрабатываются для создания результирующего дерева XML:</span><span class="sxs-lookup"><span data-stu-id="4fc0c-124">This is how the rows in the universal table are processed to produce the resulting XML tree:</span></span>  
  
 <span data-ttu-id="4fc0c-125">Первая строка задает для атрибута `Tag` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-125">The first row identifies `Tag` value `1`.</span></span> <span data-ttu-id="4fc0c-126">В результате получается группа столбцов, у которых имеется значение `Tag` , равное `1` , `Employee!1!EmpID`.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-126">Therefore, the column group that has the `Tag` value `1` is identified, `Employee!1!EmpID`.</span></span> <span data-ttu-id="4fc0c-127">Этот столбец задает в качестве имени элемент `Employee` .</span><span class="sxs-lookup"><span data-stu-id="4fc0c-127">This column identifies `Employee` as the element name.</span></span> <span data-ttu-id="4fc0c-128">После этого создается элемент <`Employee`> с атрибутами `EmpID`.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-128">An <`Employee`> element is then created that has `EmpID` attributes.</span></span> <span data-ttu-id="4fc0c-129">Соответствующие значения столбца присваиваются этим атрибутам.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-129">Corresponding column values are assigned to these attributes.</span></span>  
  
 <span data-ttu-id="4fc0c-130">Вторая строка имеет атрибут `Tag` со значением `2`.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-130">The second row has the `Tag` value `2`.</span></span> <span data-ttu-id="4fc0c-131">В результате получается группа столбцов, у которых атрибут `Tag` имеет значение `2` в имени столбца, `Name!2!FName`, `Name!2!LName`.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-131">Therefore, the column group that has the `Tag` value `2` in the column name, `Name!2!FName`, `Name!2!LName`, is identified.</span></span> <span data-ttu-id="4fc0c-132">Эти имена столбцов задают в качестве имени элемента `Name` .</span><span class="sxs-lookup"><span data-stu-id="4fc0c-132">These column names identify `Name` as element name.</span></span> <span data-ttu-id="4fc0c-133">После этого создается элемент <`Name`> с атрибутами `FName` и `LName`.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-133">A <`Name`> element is created that has `FName` and `LName` attributes.</span></span> <span data-ttu-id="4fc0c-134">После этого соответствующие значения столбца присваиваются этим атрибутам.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-134">Corresponding column values are then assigned to these attributes.</span></span> <span data-ttu-id="4fc0c-135">Эта строка задает `1` в качестве `Parent`.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-135">This row identifies `1` as `Parent`.</span></span> <span data-ttu-id="4fc0c-136">Этот дочерний элемент добавляется к предыдущему элементу <`Employee`>.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-136">This element child is added to the previous <`Employee`> element.</span></span>  
  
 <span data-ttu-id="4fc0c-137">Процесс повторяется для оставшихся строк набора строк.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-137">This process is repeated for rest of the rows in the rowset.</span></span> <span data-ttu-id="4fc0c-138">Обратите внимание на важность порядка строк в универсальной таблице, чтобы FOR XML EXPLICIT, обработав набор строк по порядку, мог создать желаемый XML.</span><span class="sxs-lookup"><span data-stu-id="4fc0c-138">Note the importance of ordering the rows in the universal table so that FOR XML EXPLICIT can process the rowset in order and generate the XML you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc0c-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="4fc0c-139">See Also</span></span>  
 [<span data-ttu-id="4fc0c-140">Использование режима EXPLICIT с предложением FOR XML</span><span class="sxs-lookup"><span data-stu-id="4fc0c-140">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
