---
title: Создание элементов для значений NULL с помощью параметра XSINIL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, null values
- null values [SQL Server], XML
- ELEMENTS directive
- XSINIL parameter
ms.assetid: 2dbc4e48-1cae-4d83-b371-3265da9687cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 602de12b5aa9be8997fbd49a2f23e0b73444aac0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751960"
---
# <a name="generate-elements-for-null-values-with-the-xsinil-parameter"></a><span data-ttu-id="5962e-102">Создание элементов для значений NULL с помощью параметра XSINIL</span><span class="sxs-lookup"><span data-stu-id="5962e-102">Generate Elements for NULL Values with the XSINIL Parameter</span></span>
  <span data-ttu-id="5962e-103">Директива **ELEMENTS** формирует XML, в котором каждое значение в столбце соответствует элементу XML.</span><span class="sxs-lookup"><span data-stu-id="5962e-103">The **ELEMENTS** directive constructs XML in which each column value maps to an element in the XML.</span></span> <span data-ttu-id="5962e-104">Если этот значение в столбце имеет значение NULL, элемент не добавляется.</span><span class="sxs-lookup"><span data-stu-id="5962e-104">If the column value is NULL, no element is added.</span></span> <span data-ttu-id="5962e-105">Указав в директиве ELEMENTS необязательный параметр **XSINIL** , можно запросить, чтобы для значений NULL тоже создавались элементы.</span><span class="sxs-lookup"><span data-stu-id="5962e-105">By specifying the optional **XSINIL** parameter on the ELEMENTS directive, you can request that an element also be created for the NULL value.</span></span> <span data-ttu-id="5962e-106">В этом случае атрибут **xsi:nil** этого элемента имеет значение TRUE для каждого значения NULL в столбце.</span><span class="sxs-lookup"><span data-stu-id="5962e-106">In this case, an element that has the **xsi:nil** attribute set to TRUE is returned for each NULL column value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5962e-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="5962e-107">See Also</span></span>  
 [<span data-ttu-id="5962e-108">Использование RAW Mode с FOR XML</span><span class="sxs-lookup"><span data-stu-id="5962e-108">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
