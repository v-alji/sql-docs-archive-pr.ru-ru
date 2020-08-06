---
title: Усечение данных (службы SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- truncating data
- data truncation [Integration Services]
- expressions [Integration Services], data truncation
- truncate options [Integration Services]
ms.assetid: 02461e15-49ca-445b-abb3-5c369c283ec2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0c4280c9eacd22ebf84bf1570d485de51cab09b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668447"
---
# <a name="data-truncation-ssis"></a><span data-ttu-id="4ebbb-102">Усечение данных (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="4ebbb-102">Data Truncation (SSIS)</span></span>
  <span data-ttu-id="4ebbb-103">Выражение может непреднамеренно усекать данные.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-103">An expression may inadvertently cause data to be truncated.</span></span> <span data-ttu-id="4ebbb-104">Усечение может произойти при следующих обстоятельствах:</span><span class="sxs-lookup"><span data-stu-id="4ebbb-104">Truncation can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="4ebbb-105">Строки.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-105">Strings.</span></span> <span data-ttu-id="4ebbb-106">Например, перевод строк типа данных DT_WSTR в строки той же длины, измеренной в символах, типа данных DT_STR приводит к потере данных в том случае, если исходная строка содержит двухбайтовые символы.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-106">For example, translating string data with a DT_WSTR data type to the same length string, measured in characters, with a DT_STR data type causes data loss if the original string contains double-byte characters.</span></span>  
  
-   <span data-ttu-id="4ebbb-107">Значимые цифры.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-107">Significant digits.</span></span> <span data-ttu-id="4ebbb-108">Например, приведение целого числа с типом данных DT_I4 к типу данных DT_I2 или целого числа без знака к целому числу со знаком.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-108">For example, casting an integer from a DT_I4 data type to a DT_I2 data type or an unsigned integer to a signed integer.</span></span>  
  
-   <span data-ttu-id="4ebbb-109">Незначимые цифры.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-109">Insignificant digits.</span></span> <span data-ttu-id="4ebbb-110">Например, приведение действительного числа с типом данных DT_R8 к типу данных DT_R4 или целого числа с типом данных DT_I4 к типу данных DT_R4.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-110">For example, casting a real number from a DT_R8 to a DT_R4 or an integer from a DT_I4 data type to a DT_R4 data type.</span></span>  
  
 <span data-ttu-id="4ebbb-111">Средство оценки выражений определяет явные приведения, которые могут привести к усечению, и выдает предупреждение, если выражение прошло синтаксический анализ.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-111">The expression evaluator identifies explicit casts that may cause truncation and issues a warning when the expression is parsed.</span></span> <span data-ttu-id="4ebbb-112">Например, средство оценки выражений выдаст предупреждение, если строка, состоящая из 30 символов, будет преобразована в строку, состоящую из 20 символов.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-112">For example, the expression evaluator warns you if a 30-character string is cast into a 20-character string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ebbb-113">Во время выполнения программы проверка на усечение данных не происходит, данные усекаются без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-113">Truncation is not checked at run time; data is truncated without warning.</span></span> <span data-ttu-id="4ebbb-114">Однако большинство адаптеров обработки данных и преобразований поддерживают сообщения об ошибках, что позволяет обработать неправильно расположенные ошибочные строки.</span><span class="sxs-lookup"><span data-stu-id="4ebbb-114">However, most data adapters and transformations support error outputs that can handle the disposition of error rows.</span></span> <span data-ttu-id="4ebbb-115">Дополнительные сведения об обработке усечения данных см. [в разделе Обработка ошибок в данных](../data-flow/error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="4ebbb-115">For more information about handling truncation of data, see [Error Handling in Data](../data-flow/error-handling-in-data.md).</span></span>  
  
  
