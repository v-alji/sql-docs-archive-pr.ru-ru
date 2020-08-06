---
title: Пример Указание директивы HIDE | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- HIDE directive
ms.assetid: 87504d87-1cbd-412a-9041-47884b6efcec
author: rothja
ms.author: jroth
ms.openlocfilehash: 423ee36f679467c07a604b9754172f6e261971b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667613"
---
# <a name="example-specifying-the-hide-directive"></a><span data-ttu-id="19507-102">Пример Определение директивы HIDE</span><span class="sxs-lookup"><span data-stu-id="19507-102">Example: Specifying the HIDE Directive</span></span>
  <span data-ttu-id="19507-103">Этот пример демонстрирует использование директивы **HIDE** .</span><span class="sxs-lookup"><span data-stu-id="19507-103">This example illustrates the use of the **HIDE** directive.</span></span> <span data-ttu-id="19507-104">Эта директива полезна, если требуется, чтобы запрос возвращал атрибут сортировки строк в универсальной таблице, возвращаемой запросом, но этот атрибут не должен появиться в конечном XML-документе.</span><span class="sxs-lookup"><span data-stu-id="19507-104">This directive is useful when you want the query to return an attribute for ordering the rows in the universal table that is returned by the query, but you do not want that attribute in the final resulting XML document.</span></span>  
  
 <span data-ttu-id="19507-105">Этот запрос создает соответствующий XML:</span><span class="sxs-lookup"><span data-stu-id="19507-105">This query constructs this XML:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
           <Summary> element from XML stored in CatalogDescription column  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="19507-106">Этот запрос формирует желаемый XML.</span><span class="sxs-lookup"><span data-stu-id="19507-106">This query generates the XML you want.</span></span> <span data-ttu-id="19507-107">В запросе задаются две группы столбцов со значениями Tag, равными 1 и 2, в именах столбцов.</span><span class="sxs-lookup"><span data-stu-id="19507-107">The query identifies two column groups having 1 and 2 as Tag values in the column names.</span></span>  
  
 <span data-ttu-id="19507-108">В этом запросе используется [метод query() (тип данных xml)](/sql/t-sql/xml/query-method-xml-data-type) типа данных **xml** для выполнения запроса к столбцу CatalogDescription типа **xml** с целью получения описания итога.</span><span class="sxs-lookup"><span data-stu-id="19507-108">This query uses the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) of the **xml** data type to query the CatalogDescription column of **xml** type in order to retrieve the summary description.</span></span> <span data-ttu-id="19507-109">В запросе также используется [метод value() (тип данных xml)](/sql/t-sql/xml/value-method-xml-data-type) типа данных **xml** для получения значения ProductModelID из столбца CatalogDescription.</span><span class="sxs-lookup"><span data-stu-id="19507-109">The query also uses the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) of the **xml** data type to retrieve the ProductModelID value from the CatalogDescription column.</span></span> <span data-ttu-id="19507-110">Это значение не должно присутствовать в конечном XML, но оно необходимо для сортировки конечного набора строк.</span><span class="sxs-lookup"><span data-stu-id="19507-110">This value is not required in the resulting XML, but is required to sort the resulting rowset.</span></span> <span data-ttu-id="19507-111">Поэтому имя столбца, `[Summary!2!ProductModelID!HIDE]`, включает директиву **HIDE** .</span><span class="sxs-lookup"><span data-stu-id="19507-111">Therefore, the column name, `[Summary!2!ProductModelID!HIDE]`, includes the **HIDE** directive.</span></span> <span data-ttu-id="19507-112">Если этот столбец не включен в инструкцию SELECT, то набор строк придется отсортировать по столбцам `[ProductModel!1!ProdModelID]` и `[Summary!2!SummaryDescription]` , которые имеют тип **xml** , а использовать столбцы типа **xml** в предложении ORDER BY нельзя.</span><span class="sxs-lookup"><span data-stu-id="19507-112">If this column is not included in the SELECT statement, you will have to sort the rowset by `[ProductModel!1!ProdModelID]` and `[Summary!2!SummaryDescription]` that is **xml** type and you cannot use the **xml** type column in ORDER BY.</span></span> <span data-ttu-id="19507-113">Поэтому добавляется дополнительный столбец `[Summary!2!ProductModelID!HIDE]` , который затем указывается в предложении ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="19507-113">Therefore, the additional `[Summary!2!ProductModelID!HIDE]` column is added and is then specified in the ORDER BY clause.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID     as [ProductModel!1!ProdModelID],  
        Name               as [ProductModel!1!Name],  
        NULL               as [Summary!2!ProductModelID!hide],  
        NULL               as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
        CatalogDescription.value('  
         declare namespace PD="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
       (/PD:ProductDescription/@ProductModelID)[1]', 'int'),  
        CatalogDescription.query('  
         declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
         /pd:ProductDescription/pd:Summary')  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],[Summary!2!ProductModelID!hide]  
FOR XML EXPLICIT  
go  
```  
  
 <span data-ttu-id="19507-114">Результат:</span><span class="sxs-lookup"><span data-stu-id="19507-114">This is the result:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <pd:Summary xmlns:pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription" xmlns="">  
        <p1:p xmlns:p1="http://www.w3.org/1999/xhtml">Our top-of-the-line competition mountain bike. Performance-enhancing options include the innovative HL Frame, super-smooth front suspension, and traction for all terrain. </p1:p>  
      </pd:Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19507-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="19507-115">See Also</span></span>  
 [<span data-ttu-id="19507-116">Использование режима EXPLICIT с предложением FOR XML</span><span class="sxs-lookup"><span data-stu-id="19507-116">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
