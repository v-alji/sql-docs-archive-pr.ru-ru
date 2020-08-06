---
title: Стандартный синтаксический анализ | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- standard parse [Integration Services]
- locales [Integration Services]
ms.assetid: dfe835b1-ea52-4e18-a23a-5188c5b6f013
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cacff710870d372d6bbf8345e05397857c13a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734306"
---
# <a name="standard-parse"></a><span data-ttu-id="0d4aa-102">Standard Parse</span><span class="sxs-lookup"><span data-stu-id="0d4aa-102">Standard Parse</span></span>
  <span data-ttu-id="0d4aa-103">Стандартный синтаксический анализ является зависящим от локалей набором процедур синтаксического анализа, которые поддерживают все преобразования типов данных, предоставляемые API-интерфейсами автоматизации преобразования типов данных, доступными в библиотеках Oleaut32.dll и Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="0d4aa-103">Standard parse is a locale-sensitive set of parsing routines that support all the data type conversions provided by the Automation data type conversion APIs that are available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="0d4aa-104">Стандартный синтаксический анализ является эквивалентом API-интерфейсов синтаксического анализа OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0d4aa-104">Standard parse is equivalent to the OLE DB parsing APIs.</span></span>  
  
 <span data-ttu-id="0d4aa-105">Стандартный синтаксический анализ поддерживает преобразование международных типов данных, которое нужно использовать, если формат данных не поддерживается быстрым синтаксическим анализом.</span><span class="sxs-lookup"><span data-stu-id="0d4aa-105">Standard parse provides support for data type conversion of international data, and it should be used if the data format is not supported by Fast parse.</span></span> <span data-ttu-id="0d4aa-106">Дополнительные сведения об API-интерфейсе автоматизации преобразования типов данных см. в статье «API-интерфейсы преобразования типов данных» в [библиотеке MSDN](https://go.microsoft.com/fwlink/?LinkId=79427).</span><span class="sxs-lookup"><span data-stu-id="0d4aa-106">For more information about the Automation data type conversion API, see "Data Type Conversion APIs" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=79427).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4aa-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d4aa-107">See Also</span></span>  
 [<span data-ttu-id="0d4aa-108">Fast Parse</span><span class="sxs-lookup"><span data-stu-id="0d4aa-108">Fast Parse</span></span>](../../2014/integration-services/fast-parse.md)  
  
  
