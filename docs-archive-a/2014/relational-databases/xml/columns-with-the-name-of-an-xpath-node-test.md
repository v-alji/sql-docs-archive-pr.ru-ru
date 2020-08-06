---
title: Столбцы с именем XPath-функции проверки узла | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
- XPath node test
ms.assetid: b48adccd-3b6b-486a-b326-20f57170186f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6555815d97308bed6e70d9fedb9858fc3abe7685
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730261"
---
# <a name="columns-with-the-name-of-an-xpath-node-test"></a><span data-ttu-id="1d2fc-102">Столбцы с именем XPath-функции проверки узла</span><span class="sxs-lookup"><span data-stu-id="1d2fc-102">Columns with the Name of an XPath Node Test</span></span>
  <span data-ttu-id="1d2fc-103">Если имя столбца является одной из XPath-функций проверки узла, сопоставление содержимого производится, как указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-103">If the column name is one of the XPath node tests, the content is mapped as shown in the following table.</span></span> <span data-ttu-id="1d2fc-104">Когда имя столбца является XPath-функцией проверки узла, содержимое сопоставляется с соответствующим узлом.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-104">When the column name is an XPath node test, the content is mapped to the corresponding node.</span></span> <span data-ttu-id="1d2fc-105">Если столбец имеет SQL-тип `xml`, возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-105">If the SQL type of the column is `xml`, an error is returned.</span></span>  
  
|<span data-ttu-id="1d2fc-106">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="1d2fc-106">Column Name</span></span>|<span data-ttu-id="1d2fc-107">Поведение</span><span class="sxs-lookup"><span data-stu-id="1d2fc-107">Behavior</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="1d2fc-108">text()</span><span class="sxs-lookup"><span data-stu-id="1d2fc-108">text()</span></span>|<span data-ttu-id="1d2fc-109">Строковое значение столбца с именем text() добавляется в качестве текстового узла.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-109">For a column with the name of text(), the string value in that column is added as a text node.</span></span>|  
|<span data-ttu-id="1d2fc-110">comment()</span><span class="sxs-lookup"><span data-stu-id="1d2fc-110">comment()</span></span>|<span data-ttu-id="1d2fc-111">Строковое значение столбца с именем text() добавляется в качестве комментария XML.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-111">For a column with the name of comment(), the string value in that column is added as an XML comment.</span></span>|  
|<span data-ttu-id="1d2fc-112">node()</span><span class="sxs-lookup"><span data-stu-id="1d2fc-112">node()</span></span>|<span data-ttu-id="1d2fc-113">Для столбца с именем node() результат аналогичен результату, получаемому для столбца с символом-шаблоном (\*) в качестве имени.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-113">For a column with the name of node(), the result is the same as it is when the column name is a wildcard character (\*).</span></span>|  
|<span data-ttu-id="1d2fc-114">processing-instruction(name)</span><span class="sxs-lookup"><span data-stu-id="1d2fc-114">processing-instruction(name)</span></span>|<span data-ttu-id="1d2fc-115">Строковое значение столбца с именем инструкции по обработке добавляется в качестве значения инструкции для целевого имени инструкции по обработке.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-115">For a column with the name of a processing instruction, the string value in that column is added as the PI value for the processing instruction target name.</span></span>|  
  
 <span data-ttu-id="1d2fc-116">В следующем запросе показано использование проверочных узлов в качестве имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-116">The following query shows the use of the node tests as column names.</span></span> <span data-ttu-id="1d2fc-117">При этом текстовые узлы и комментарии добавляются в результирующий XML-документ.</span><span class="sxs-lookup"><span data-stu-id="1d2fc-117">It adds text nodes and comments in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
        'Example of using node tests such as text(), comment(), processing-instruction()'                as "comment()",  
        'Some PI'                   as "processing-instruction(PI)",  
        'Employee name and address data' as "text()",  
        'middle name is optional'        as "EmpName/text()",  
        FirstName                        as "EmpName/First",   
        MiddleName                       as "EmpName/Middle",   
        LastName                         as "EmpName/Last",  
        AddressLine1                     as "Address/AddrLine1",  
        AddressLine2                     as "Address/AddrLIne2",  
        City                             as "Address/City"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P   
    ON P.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS BAE  
    ON BAE.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.Address AS A  
    ON BAE.AddressID = A.AddressID  
WHERE  E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="1d2fc-118">Результат:</span><span class="sxs-lookup"><span data-stu-id="1d2fc-118">This is the result:</span></span>  
  
 `<row EmpID="1">`  
  
 `<!--Example of using node tests such as text(), comment(), processing-instruction() -->`  
  
 `<?PI Some PI?>`  
  
 `Employee name and address data`  
  
 `<EmpName>middle name is optional`  
  
 `<First>Ken</First>`  
  
 `<Last>S??nchez</Last>`  
  
 `</EmpName>`  
  
 `<Address>`  
  
 `<AddrLine1>4350 Minute Dr.</AddrLine1>`  
  
 `<City>Minneapolis</City>`  
  
 `</Address>`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="1d2fc-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="1d2fc-119">See Also</span></span>  
 [<span data-ttu-id="1d2fc-120">Использование режима PATH совместно с FOR XML</span><span class="sxs-lookup"><span data-stu-id="1d2fc-120">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
