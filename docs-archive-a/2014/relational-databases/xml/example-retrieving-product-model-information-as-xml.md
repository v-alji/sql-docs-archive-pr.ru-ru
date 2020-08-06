---
title: Пример Получение сведений о модели продукта в формате XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, retrieving XML information example
ms.assetid: 3828b4ca-3ab2-444f-9c58-8be6e7f064a6
author: rothja
ms.author: jroth
ms.openlocfilehash: d580f53c4b5185a8b1b1467c75a08fc6929bdcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664793"
---
# <a name="example-retrieving-product-model-information-as-xml"></a><span data-ttu-id="807d7-102">Пример Получение сведений о модели продукта в формате XML</span><span class="sxs-lookup"><span data-stu-id="807d7-102">Example: Retrieving Product Model Information as XML</span></span>
  <span data-ttu-id="807d7-103">Приведенный ниже пример запроса выводит сведения о модели продукта.</span><span class="sxs-lookup"><span data-stu-id="807d7-103">The following query returns product model information.</span></span> <span data-ttu-id="807d7-104">`RAW` указывается в приложении `FOR XML` .</span><span class="sxs-lookup"><span data-stu-id="807d7-104">`RAW` mode is specified in the `FOR XML` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="807d7-105">Пример</span><span class="sxs-lookup"><span data-stu-id="807d7-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW;  
GO  
```  
  
 <span data-ttu-id="807d7-106">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="807d7-106">This is the partial result:</span></span>  
  
 `<row ProductModelID="122" Name="All-Purpose Bike Stand" />`  
  
 `<row ProductModelID="119" Name="Bike Wash" />`  
  
 <span data-ttu-id="807d7-107">Есть возможность получить XML-документ с данными по элементам при помощи определения директивы `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="807d7-107">You can retrieve element-centric XML by specifying the `ELEMENTS` directive.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="807d7-108">Результат:</span><span class="sxs-lookup"><span data-stu-id="807d7-108">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</row>  
<row>  
  <ProductModelID>119</ProductModelID>  
  <Name>Bike Wash</Name>  
</row>  
```  
  
 <span data-ttu-id="807d7-109">При необходимости можно задать директиву `TYPE` для получения результатов в виде `xml`.</span><span class="sxs-lookup"><span data-stu-id="807d7-109">You can optionally specify the `TYPE` directive to retrieve the results as `xml` type.</span></span> <span data-ttu-id="807d7-110">Директива `TYPE` не изменяет содержимое результата.</span><span class="sxs-lookup"><span data-stu-id="807d7-110">The `TYPE` directive does not change the content of the results.</span></span> <span data-ttu-id="807d7-111">Изменяется только тип данных результата.</span><span class="sxs-lookup"><span data-stu-id="807d7-111">Only the data type of the results is affected.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, TYPE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="807d7-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="807d7-112">See Also</span></span>  
 [<span data-ttu-id="807d7-113">Использование RAW Mode с FOR XML</span><span class="sxs-lookup"><span data-stu-id="807d7-113">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
