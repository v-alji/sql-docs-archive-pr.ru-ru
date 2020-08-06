---
title: Пример Переименование элемента &lt;row&gt; | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, renaming <row> example
ms.assetid: b042292a-0b6e-40a3-b254-71c06e626706
author: rothja
ms.author: jroth
ms.openlocfilehash: 39375fa125f451f21d936b3a6897b93928fa2f02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654941"
---
# <a name="example-renaming-the-ltrowgt-element"></a><span data-ttu-id="70fd4-102">Пример Переименование элемента &lt;row&gt;</span><span class="sxs-lookup"><span data-stu-id="70fd4-102">Example: Renaming the &lt;row&gt; Element</span></span>
  <span data-ttu-id="70fd4-103">Для каждой строки результирующего набора режим RAW создает элемент `<row>`.</span><span class="sxs-lookup"><span data-stu-id="70fd4-103">For each row in the result set, the RAW mode generates an element `<row>`.</span></span> <span data-ttu-id="70fd4-104">При необходимости можно задать другое имя для этого элемента путем определения дополнительного аргумента в режиме RAW, как показано в данном запросе.</span><span class="sxs-lookup"><span data-stu-id="70fd4-104">You can optionally specify another name for this element by specifying an optional argument to the RAW mode, as shown in this query.</span></span> <span data-ttu-id="70fd4-105">Запрос возвращает элемент <`ProductModel`> для каждой строки из набора строк.</span><span class="sxs-lookup"><span data-stu-id="70fd4-105">The query returns a <`ProductModel`> element for each row in the rowset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70fd4-106">Пример</span><span class="sxs-lookup"><span data-stu-id="70fd4-106">Example</span></span>  
  
```  
SELECT ProductModelID, Name   
FROM Production.ProductModel  
WHERE ProductModelID=122  
FOR XML RAW ('ProductModel'), ELEMENTS  
GO  
```  
  
 <span data-ttu-id="70fd4-107">Результат.</span><span class="sxs-lookup"><span data-stu-id="70fd4-107">This is the result.</span></span> <span data-ttu-id="70fd4-108">Из-за того, что в запрос добавлена директива `ELEMENTS` , результат состоит из элементов.</span><span class="sxs-lookup"><span data-stu-id="70fd4-108">Because the `ELEMENTS` directive is added in the query, the result is element-centric.</span></span>  
  
```  
<ProductModel>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</ProductModel>   
```  
  
## <a name="see-also"></a><span data-ttu-id="70fd4-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="70fd4-109">See Also</span></span>  
 [<span data-ttu-id="70fd4-110">Использование RAW Mode с FOR XML</span><span class="sxs-lookup"><span data-stu-id="70fd4-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
