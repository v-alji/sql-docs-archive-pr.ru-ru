---
title: LEFT (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5634dbfb-740d-4c93-8fd5-2854cc741327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f21d134988414c7d8579d720877feec45383270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667282"
---
# <a name="left-ssis-expression"></a><span data-ttu-id="b74ea-102">LEFT (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="b74ea-102">LEFT (SSIS Expression)</span></span>
  <span data-ttu-id="b74ea-103">Возвращает указанное количество символов из крайней левой части заданного символьного выражения.</span><span class="sxs-lookup"><span data-stu-id="b74ea-103">Returns the specified number of characters from the leftmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b74ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b74ea-104">Syntax</span></span>  
  
```  
  
LEFT(character_expression,number)  
```  
  
## <a name="arguments"></a><span data-ttu-id="b74ea-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b74ea-105">Arguments</span></span>  
 <span data-ttu-id="b74ea-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="b74ea-106">*character_expression*</span></span>  
 <span data-ttu-id="b74ea-107">Символьное выражение, из которого извлекаются символы.</span><span class="sxs-lookup"><span data-stu-id="b74ea-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="b74ea-108">*number*</span><span class="sxs-lookup"><span data-stu-id="b74ea-108">*number*</span></span>  
 <span data-ttu-id="b74ea-109">Является целочисленным выражением, которое указывает количество возвращаемых символов.</span><span class="sxs-lookup"><span data-stu-id="b74ea-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b74ea-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="b74ea-110">Result Types</span></span>  
 <span data-ttu-id="b74ea-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="b74ea-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b74ea-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="b74ea-112">Remarks</span></span>  
 <span data-ttu-id="b74ea-113">Если *number* длиннее, чем *character_expression*, функция возвращает *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="b74ea-113">If *number* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="b74ea-114">Если *number* равен нулю, функция возвращает строку нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="b74ea-114">If *number* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="b74ea-115">Если *number* является отрицательным числом, то функция возвратит ошибку.</span><span class="sxs-lookup"><span data-stu-id="b74ea-115">If *number* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="b74ea-116">Аргумент *number* может принимать переменные и столбцы.</span><span class="sxs-lookup"><span data-stu-id="b74ea-116">The *number* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="b74ea-117">Функция LEFT работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="b74ea-117">LEFT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="b74ea-118">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции LEFT.</span><span class="sxs-lookup"><span data-stu-id="b74ea-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LEFT performs its operation.</span></span> <span data-ttu-id="b74ea-119">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="b74ea-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="b74ea-120">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b74ea-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="b74ea-121">LEFT возвращает результат NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b74ea-121">LEFT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b74ea-122">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="b74ea-122">Expression Examples</span></span>  
 <span data-ttu-id="b74ea-123">В следующем примере используется строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="b74ea-123">The following example uses a string literal.</span></span> <span data-ttu-id="b74ea-124">Возвращаемым результатом является `"Mountain"`.</span><span class="sxs-lookup"><span data-stu-id="b74ea-124">The return result is `"Mountain"`.</span></span>  
  
```  
LEFT("Mountain Bike", 8)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b74ea-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="b74ea-125">See Also</span></span>  
 <span data-ttu-id="b74ea-126">[RIGHT (выражение служб SSIS)](right-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b74ea-126">[RIGHT &#40;SSIS Expression&#41;](right-ssis-expression.md) </span></span>  
 [<span data-ttu-id="b74ea-127">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="b74ea-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
