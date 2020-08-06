---
title: Столбцы без имени | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns without
ms.assetid: 440de44e-3a56-4531-b4e4-1533ca933cac
author: rothja
ms.author: jroth
ms.openlocfilehash: 43d1cbce816e4666e6dab52fdffe5850e65740e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730258"
---
# <a name="columns-without-a-name"></a><span data-ttu-id="a1e79-102">Столбцы без имени</span><span class="sxs-lookup"><span data-stu-id="a1e79-102">Columns without a Name</span></span>
  <span data-ttu-id="a1e79-103">Любой столбец, не имеющий имени, будет встроенным.</span><span class="sxs-lookup"><span data-stu-id="a1e79-103">Any column without a name will be inlined.</span></span> <span data-ttu-id="a1e79-104">Например, вычисляемые столбцы или вложенные скалярные запросы, в которых не задан псевдоним столбца, формируют столбцы без имени.</span><span class="sxs-lookup"><span data-stu-id="a1e79-104">For example, computed columns or nested scalar queries that do not specify column alias will generate columns without any name.</span></span> <span data-ttu-id="a1e79-105">Если столбец имеет тип данных `xml`, в него помещается содержимое экземпляра этого типа данных.</span><span class="sxs-lookup"><span data-stu-id="a1e79-105">If the column is of `xml` type, the content of that data type instance is inserted.</span></span> <span data-ttu-id="a1e79-106">В противном случае содержимое столбца вставляется как текстовый узел.</span><span class="sxs-lookup"><span data-stu-id="a1e79-106">Otherwise, the column content is inserted as a text node.</span></span>  
  
```  
SELECT 2+2  
FOR XML PATH  
```  
  
 <span data-ttu-id="a1e79-107">Создание этого XML.</span><span class="sxs-lookup"><span data-stu-id="a1e79-107">Produce this XML.</span></span> <span data-ttu-id="a1e79-108">По умолчанию для каждой строки в наборе строк в итоговом XML-документе формируется элемент <`row`>.</span><span class="sxs-lookup"><span data-stu-id="a1e79-108">By default, for each row in the rowset, a <`row`> element is generated in the resulting XML.</span></span> <span data-ttu-id="a1e79-109">То же самое происходит в режиме RAW.</span><span class="sxs-lookup"><span data-stu-id="a1e79-109">This is the same as RAW mode.</span></span>  
  
 `<row>4</row>`  
  
 <span data-ttu-id="a1e79-110">Следующий запрос возвращает набор строк с тремя столбцами.</span><span class="sxs-lookup"><span data-stu-id="a1e79-110">The following query returns a three-column rowset.</span></span> <span data-ttu-id="a1e79-111">Третий столбец, без названия, содержит XML-данные.</span><span class="sxs-lookup"><span data-stu-id="a1e79-111">The third column without a name has XML data.</span></span> <span data-ttu-id="a1e79-112">Режим PATH вставляет экземпляр типа xml.</span><span class="sxs-lookup"><span data-stu-id="a1e79-112">The PATH mode inserts an instance of the xml type.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ;  
GO  
```  
  
 <span data-ttu-id="a1e79-113">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="a1e79-113">This is the partial result:</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location ...LocationID="10" ...></MI:Location>`  
  
 `<MI:Location ...LocationID="20" ...></MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="a1e79-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1e79-114">See Also</span></span>  
 [<span data-ttu-id="a1e79-115">Использование режима PATH совместно с FOR XML</span><span class="sxs-lookup"><span data-stu-id="a1e79-115">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
