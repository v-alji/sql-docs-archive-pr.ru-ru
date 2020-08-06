---
title: Поддержка пространства имен в режиме PATH | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, namespace support
- namespaces [XML in SQL Server]
ms.assetid: 5f128ea2-0ceb-4b23-bce7-c8b3fd615466
author: rothja
ms.author: jroth
ms.openlocfilehash: abd6cd1f5590bffcd841b07897c9685faed4726f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729153"
---
# <a name="namespace-support-in-path-mode"></a><span data-ttu-id="fa800-102">Поддержка пространства имен в режиме PATH</span><span class="sxs-lookup"><span data-stu-id="fa800-102">Namespace Support in PATH Mode</span></span>
  <span data-ttu-id="fa800-103">Поддержка пространства имен в режиме PATH осуществляется с помощью предложения WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="fa800-103">Namespace support in the PATH mode is provided by using WITH NAMESPACES.</span></span> <span data-ttu-id="fa800-104">Например, в следующем запросе синтаксис WITH NAMESPACES применяется для объявления пространства имен («a:»), которое затем можно использовать в последующей инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="fa800-104">For example, the following query demonstrates the WITH NAMESPACES syntax to declare a namespace ("a:") that can then be used in the subsequent SELECT statement:</span></span>  
  
```  
WITH XMLNAMESPACES('a' as a)  
SELECT 1 as 'a:b'  
FOR XML PATH  
```  
  
## <a name="examples"></a><span data-ttu-id="fa800-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="fa800-105">Examples</span></span>  
 <span data-ttu-id="fa800-106">В этих примерах показано использование режима PATH при формировании XML-документа из запроса SELECT.</span><span class="sxs-lookup"><span data-stu-id="fa800-106">These samples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="fa800-107">Многие из этих запросов являются запросами к XML-документам с инструкциями по производству велосипедов, хранящимся в столбце Instructions таблицы ProductModel.</span><span class="sxs-lookup"><span data-stu-id="fa800-107">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa800-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa800-108">See Also</span></span>  
 [<span data-ttu-id="fa800-109">Использование режима PATH совместно с FOR XML</span><span class="sxs-lookup"><span data-stu-id="fa800-109">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
