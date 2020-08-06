---
title: LOWER (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting uppercase to lowercase
- LOWER function
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: 109328e1-5604-40ff-895e-f2e7c13fff41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 180be8f3cfb5a15eb0fcd6ddd3d63b09fe874af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658914"
---
# <a name="lower-ssis-expression"></a><span data-ttu-id="95389-102">LOWER (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="95389-102">LOWER (SSIS Expression)</span></span>
  <span data-ttu-id="95389-103">Возвращает символьное выражение после преобразования всех символов верхнего регистра в нижний.</span><span class="sxs-lookup"><span data-stu-id="95389-103">Returns a character expression after converting uppercase characters to lowercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95389-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95389-104">Syntax</span></span>  
  
```  
  
LOWER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="95389-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="95389-105">Arguments</span></span>  
 <span data-ttu-id="95389-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="95389-106">*character_expression*</span></span>  
 <span data-ttu-id="95389-107">Символьное выражение для преобразования символов в нижний регистр.</span><span class="sxs-lookup"><span data-stu-id="95389-107">Is a character expression to convert to lowercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="95389-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="95389-108">Result Types</span></span>  
 <span data-ttu-id="95389-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="95389-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95389-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="95389-110">Remarks</span></span>  
 <span data-ttu-id="95389-111">Функция LOWER работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="95389-111">LOWER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="95389-112">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции LOWER.</span><span class="sxs-lookup"><span data-stu-id="95389-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LOWER performs its operation.</span></span> <span data-ttu-id="95389-113">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="95389-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="95389-114">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="95389-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="95389-115">Функция LOWER возвращает NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="95389-115">LOWER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="95389-116">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="95389-116">Expression Examples</span></span>  
 <span data-ttu-id="95389-117">Этот пример преобразует символы строкового литерала в символы нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="95389-117">This example converts a string literal to lowercase characters.</span></span> <span data-ttu-id="95389-118">Возвращенный результат — «new york».</span><span class="sxs-lookup"><span data-stu-id="95389-118">The return result is "new york".</span></span>  
  
```  
LOWER("New York")  
```  
  
 <span data-ttu-id="95389-119">Этот пример преобразует все символы из входного столбца **Color** , кроме первого символа, в символы нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="95389-119">This example converts all characters from the **Color** input column, except the first character, to lowercase characters.</span></span> <span data-ttu-id="95389-120">Если значение Color равно «YELLOW», возвращенный результат будет «Yellow».</span><span class="sxs-lookup"><span data-stu-id="95389-120">If Color is YELLOW, the return result is "Yellow".</span></span> <span data-ttu-id="95389-121">Дополнительные сведения см. в разделе [SUBSTRING (выражение служб SSIS)](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="95389-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
LOWER(SUBSTRING(Color, 2, 15))  
```  
  
 <span data-ttu-id="95389-122">Пример преобразует значение переменной **CityName** в символы нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="95389-122">This example converts the value in the **CityName** variable to lowercase characters.</span></span>  
  
```  
LOWER(@CityName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="95389-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="95389-123">See Also</span></span>  
 <span data-ttu-id="95389-124">[UPPER (выражение служб SSIS)](upper-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="95389-124">[UPPER &#40;SSIS Expression&#41;](upper-ssis-expression.md) </span></span>  
 [<span data-ttu-id="95389-125">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="95389-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
