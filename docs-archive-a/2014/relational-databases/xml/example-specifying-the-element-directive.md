---
title: Пример Указание директивы ELEMENT | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
ms.assetid: 80dd5d1f-fa90-4f97-a186-8fa3f460a7f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a03d1049fa9df23eff759634bcd74f88f842a8e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728102"
---
# <a name="example-specifying-the-element-directive"></a><span data-ttu-id="c953a-102">Пример Определение директивы ELEMENT</span><span class="sxs-lookup"><span data-stu-id="c953a-102">Example: Specifying the ELEMENT Directive</span></span>
  <span data-ttu-id="c953a-103">Это приводит к получению сведений о сотрудниках и созданию элементного XML, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="c953a-103">This retrieves employee information and generates element-centric XML as shown in the following:</span></span>  
  
```  
<Employee EmpID=...>  
  <Name>  
    <FName>...</FName>  
    <LName>...</LName>  
  </Name>  
</Employee>  
```  
  
 <span data-ttu-id="c953a-104">Запрос остается тем же, за исключением того, что в имена столбцов добавлена директива `ELEMENT`.</span><span class="sxs-lookup"><span data-stu-id="c953a-104">The query remains the same, except you add the `ELEMENT` directive in the column names.</span></span> <span data-ttu-id="c953a-105">Поэтому вместо атрибутов будут добавлены дочерние элементы <`FName`> и <`LName`> к элементу <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="c953a-105">Therefore, instead of attributes, the <`FName`> and <`LName`> element children are added to the <`Name`> element.</span></span> <span data-ttu-id="c953a-106">Так как столбец `Employee!1!EmpID` не указывает директиву `ELEMENT`, `EmpID` добавляется в качестве атрибута элемента <`Employee`>.</span><span class="sxs-lookup"><span data-stu-id="c953a-106">Because the `Employee!1!EmpID` column does not specify the `ELEMENT` directive, `EmpID` is added as the attribute of the <`Employee`> element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName!ELEMENT],  
       NULL       as [Name!2!LName!ELEMENT]  
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
ORDER BY [Employee!1!EmpID],[Name!2!FName!ELEMENT]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="c953a-107">Частичный результат.</span><span class="sxs-lookup"><span data-stu-id="c953a-107">This is the partial result.</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name>`  
  
 `<FName>Ken</FName>`  
  
 `<LName>S??nchez</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name>`  
  
 `<FName>Terri</FName>`  
  
 `<LName>Duffy</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `...`  
  
## <a name="see-also"></a><span data-ttu-id="c953a-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="c953a-108">See Also</span></span>  
 [<span data-ttu-id="c953a-109">Использование режима EXPLICIT с предложением FOR XML</span><span class="sxs-lookup"><span data-stu-id="c953a-109">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
