---
title: Пример Запросы к столбцам XMLType | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, querying XML example
ms.assetid: d9f3710d-7a2e-4abe-9c02-3e3c0df4d620
author: rothja
ms.author: jroth
ms.openlocfilehash: 0eedfa5a5a265f3715a76a6ca80d489bbec199bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654942"
---
# <a name="example-querying-xmltype-columns"></a><span data-ttu-id="cccac-102">Пример Запросы к столбцам XMLType</span><span class="sxs-lookup"><span data-stu-id="cccac-102">Example: Querying XMLType Columns</span></span>
  <span data-ttu-id="cccac-103">В следующий запрос включены столбцы типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="cccac-103">The following query includes columns of `xml` type.</span></span> <span data-ttu-id="cccac-104">Запрос возвращает идентификатор модели продукта, имя и шаги производства в первом месте из столбца `Instructions` типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="cccac-104">The query retrieves product model ID, name, and manufacturing steps at the first location from the `Instructions` column of the `xml` type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cccac-105">Пример</span><span class="sxs-lookup"><span data-stu-id="cccac-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
')   
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
GO  
```  
  
 <span data-ttu-id="cccac-106">Ниже показан результат.</span><span class="sxs-lookup"><span data-stu-id="cccac-106">The following is the result.</span></span> <span data-ttu-id="cccac-107">Следует заметить, что в таблице содержатся инструкции по производству продукта только для некоторых моделей продукта.</span><span class="sxs-lookup"><span data-stu-id="cccac-107">Note that the table stores manufacturing instructions for only some product models.</span></span> <span data-ttu-id="cccac-108">Этапы производства возвращаются в качества подэлементов элемента <`ProductModelData`> в итоговом документе.</span><span class="sxs-lookup"><span data-stu-id="cccac-108">The manufacturing steps are returned as subelements of the <`ProductModelData`> element in the result.</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
    <MI:step> ... </MI:step>  
    <MI:step> ... </MI:step>  
 </ProductModelData>  
```  
  
 <span data-ttu-id="cccac-109">Если в запросе задано имя столбца для XML-документа, возвращаемого XQuery, так как это задано в следующей инструкции `SELECT` , то шаги производства помещаются в элемент, имеющий указанное имя.</span><span class="sxs-lookup"><span data-stu-id="cccac-109">If the query specifies a column name for the XML returned by the XQuery, as specified in the following `SELECT` statement, the manufacturing steps are wrapped in the element that has the specified name.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
go  
```  
  
 <span data-ttu-id="cccac-110">Результат:</span><span class="sxs-lookup"><span data-stu-id="cccac-110">This is the result:</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
  <ManuSteps>  
    <MI:step ... </MI:step>  
    <MI:step ... </MI:step>  
  </ManuSteps>  
</ProductModelData>  
```  
  
 <span data-ttu-id="cccac-111">В следующем запросе задана директива `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="cccac-111">The following query specifies the `ELEMENTS` directive.</span></span> <span data-ttu-id="cccac-112">Поэтому результат будет состоять из элементов.</span><span class="sxs-lookup"><span data-stu-id="cccac-112">Therefore, the result returned is element-centric.</span></span> <span data-ttu-id="cccac-113">Параметр `XSINIL`, заданный вместе с директивой `ELEMENTS`, возвращает элементы <`ManuSteps`>, даже если соответствующий столбец в наборе строк имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="cccac-113">The `XSINIL` option specified with the `ELEMENTS` directive returns the <`ManuSteps`> elements, even if the corresponding column in the rowset is NULL.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData'), root('MyRoot'), ELEMENTS XSINIL  
go  
```  
  
 <span data-ttu-id="cccac-114">Результат:</span><span class="sxs-lookup"><span data-stu-id="cccac-114">This is the result:</span></span>  
  
```  
<MyRoot xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   ...  
  <ProductModelData>  
    <ProductModelID>6</ProductModelID>  
    <Name>HL Road Frame</Name>  
    <ManuSteps xsi:nil="true" />  
  </ProductModelData>  
  <ProductModelData>  
    <ProductModelID>7</ProductModelID>  
    <Name>HL Touring Frame</Name>  
    <ManuSteps>  
      <MI:step ... </MI:step>  
      <MI:step ...</MI:step>  
       ...  
    </ManuSteps>  
  </ProductModelData>  
</MyRoot>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cccac-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="cccac-115">See Also</span></span>  
 [<span data-ttu-id="cccac-116">Использование RAW Mode с FOR XML</span><span class="sxs-lookup"><span data-stu-id="cccac-116">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
