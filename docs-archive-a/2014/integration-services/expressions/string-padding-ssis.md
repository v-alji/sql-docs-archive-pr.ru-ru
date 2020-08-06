---
title: Дополнение строк (службы SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- padding strings [Integration Services]
- expressions [Integration Services], string padding
- string padding
ms.assetid: d3fed73d-e0d4-4c67-9355-fb7083a72dd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3985fd1b2f29260e2313a761797d2528f5d0e328
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732785"
---
# <a name="string-padding-ssis"></a><span data-ttu-id="25297-102">Дополнение строк (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="25297-102">String Padding (SSIS)</span></span>
  <span data-ttu-id="25297-103">Средство оценки выражений не проверяет, содержит ли строка начальные и конечные пробелы, и не приводит строки к одинаковой длине перед их сравнением.</span><span class="sxs-lookup"><span data-stu-id="25297-103">The expression evaluator does not check if a string contains leading and trailing spaces, and it does not pad strings to make them the same length before it compares them.</span></span> <span data-ttu-id="25297-104">Если выражения требуют дополнения строк, можно использовать оператор + для сцепления значений столбцов и пустых строк.</span><span class="sxs-lookup"><span data-stu-id="25297-104">If expressions requires string padding, you can use the + operator to concatenate column values and blank strings.</span></span> <span data-ttu-id="25297-105">Дополнительные сведения см. в разделе [+ (Объединение) (выражение SSIS)](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="25297-105">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="25297-106">С другой стороны, если надо удалить лишние пробелы, средство оценки выражений предоставляет функции LTRIM, RTRIM и TRIM, которые удаляют начальные либо конечные пробелы, либо и те и другие.</span><span class="sxs-lookup"><span data-stu-id="25297-106">On the other hand, if you want to remove spaces, the expression evaluator provides the LTRIM, RTRIM, and TRIM functions, which remove leading or trailing spaces, or both.</span></span> <span data-ttu-id="25297-107">Дополнительные сведения см. в разделах [LTRIM (выражение служб SSIS)](trim-ssis-expression.md), [RTRIM (выражение служб SSIS)](rtrim-ssis-expression.md) и [TRIM (выражение служб SSIS)](trim-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="25297-107">For more information, see [LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md), [RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md), and [TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25297-108">Функция LEN включает в счет начальные и завершающие пробелы.</span><span class="sxs-lookup"><span data-stu-id="25297-108">The LEN function includes leading and trailing blanks in its count.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="25297-109">См. также</span><span class="sxs-lookup"><span data-stu-id="25297-109">Related Content</span></span>  
 <span data-ttu-id="25297-110">Техническая статья [Памятка выражений служб SSIS](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
)на сайте pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="25297-110">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), on pragmaticworks.com</span></span>  
  
  
