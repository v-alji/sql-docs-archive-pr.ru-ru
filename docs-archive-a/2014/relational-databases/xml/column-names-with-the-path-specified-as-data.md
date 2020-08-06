---
title: Имена столбцов с путем, указанным как data() | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: 0b738e44-6108-4417-a9a4-abeb7680d899
author: rothja
ms.author: jroth
ms.openlocfilehash: 61aa7f85c7ee2358ddcf99f81c87c1295fac8fb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654950"
---
# <a name="column-names-with-the-path-specified-as-data"></a><span data-ttu-id="0df4e-102">Имена столбцов с путем, указанным как data()</span><span class="sxs-lookup"><span data-stu-id="0df4e-102">Column Names with the Path Specified as data()</span></span>
  <span data-ttu-id="0df4e-103">Если путь для имени столбца указан как «data()», то в сформированном XML-документе его значение обрабатывается как атомарное.</span><span class="sxs-lookup"><span data-stu-id="0df4e-103">If the path specified as column name is "data()", the value is treated as an atomic value in the generated XML.</span></span> <span data-ttu-id="0df4e-104">Если следующий элемент последовательности также является элементарным значением, в XML-документ добавляется символ пробела.</span><span class="sxs-lookup"><span data-stu-id="0df4e-104">A space character is added to the XML if the next item in the serialization is also an atomic value.</span></span> <span data-ttu-id="0df4e-105">Это может пригодиться при создании списка типизированных элементов и значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="0df4e-105">This is useful when you are creating list typed element and attribute values.</span></span> <span data-ttu-id="0df4e-106">Следующий запрос извлекает код модели продукции, ее имя и список продуктов этой модели.</span><span class="sxs-lookup"><span data-stu-id="0df4e-106">The following query retrieves the product model ID, name, and list of products in that product model.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID       AS "@ProductModelID",  
       Name                 AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
      FOR XML PATH (''))    AS "@ProductIDs"  
FROM  Production.ProductModel  
WHERE ProductModelID= 7   
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="0df4e-107">Вложенная инструкция SELECT извлекает список кодов продуктов.</span><span class="sxs-lookup"><span data-stu-id="0df4e-107">The nested SELECT retrieves a list of product IDs.</span></span> <span data-ttu-id="0df4e-108">Имя столбца для кодов продуктов в нем указано как «data()».</span><span class="sxs-lookup"><span data-stu-id="0df4e-108">It specifies "data()" as the column name for product IDs.</span></span> <span data-ttu-id="0df4e-109">Поскольку режим PATH указывает для имени элемента строки пустую строку, формирования элемента строки не происходит.</span><span class="sxs-lookup"><span data-stu-id="0df4e-109">Because PATH mode specifies an empty string for the row element name, there is no row element generated.</span></span> <span data-ttu-id="0df4e-110">Вместо этого возвращаются значения, назначенные атрибуту ProductIDs элемента строки <`ProductModelData`> в родительской инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="0df4e-110">Instead, the values are returned as assigned to a ProductIDs attribute of the <`ProductModelData`> row element of the parent SELECT.</span></span> <span data-ttu-id="0df4e-111">Результат:</span><span class="sxs-lookup"><span data-stu-id="0df4e-111">This is the result:</span></span>  
  
 `<ProductModelData ProductModelID="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 888 889 890 891 892 893" />`  
  
## <a name="see-also"></a><span data-ttu-id="0df4e-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="0df4e-112">See Also</span></span>  
 [<span data-ttu-id="0df4e-113">Использование режима PATH совместно с FOR XML</span><span class="sxs-lookup"><span data-stu-id="0df4e-113">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
