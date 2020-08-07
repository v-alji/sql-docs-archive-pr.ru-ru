---
title: TRIM (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- TRIM function
- trailing blanks
ms.assetid: 7dd9081d-a3d4-483a-bf7e-bf2bd7692d39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 42cef8a816f399e39ac99061f34c394156bde45f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732761"
---
# <a name="trim-ssis-expression"></a><span data-ttu-id="13159-102">TRIM (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="13159-102">TRIM (SSIS Expression)</span></span>
  <span data-ttu-id="13159-103">Возвращает символьное выражение после удаления начальных и конечных пробелов.</span><span class="sxs-lookup"><span data-stu-id="13159-103">Returns a character expression after removing leading and trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13159-104">Функция TRIM не удаляет символы-разделители, такие как знаки табуляции или перевода строки.</span><span class="sxs-lookup"><span data-stu-id="13159-104">TRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="13159-105">Юникод обеспечивает элементы кода для множества различных типов пробелов, однако данная функция распознает только элемент кода 0x0020 в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="13159-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="13159-106">Если строки двухбайтовой кодировки (DBCS) преобразованы в Юникод, они могут включать пробелы, отличные от 0x0020. Тогда функция не в состоянии удалить такие пробелы.</span><span class="sxs-lookup"><span data-stu-id="13159-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="13159-107">Чтобы удалить все типы пробелов, можно использовать метод обрезки Microsoft Visual Basic .NET в скрипте, запускаемом из компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="13159-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET Trim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13159-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13159-108">Syntax</span></span>  
  
```  
  
TRIM(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="13159-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="13159-109">Arguments</span></span>  
 <span data-ttu-id="13159-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="13159-110">*character_expression*</span></span>  
 <span data-ttu-id="13159-111">Символьное выражение, из которого удаляются пробелы.</span><span class="sxs-lookup"><span data-stu-id="13159-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="13159-112">Типы результата</span><span class="sxs-lookup"><span data-stu-id="13159-112">Result Types</span></span>  
 <span data-ttu-id="13159-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="13159-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13159-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="13159-114">Remarks</span></span>  
 <span data-ttu-id="13159-115">Функция TRIM возвращает результат NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="13159-115">TRIM returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="13159-116">Функция TRIM работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="13159-116">TRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="13159-117">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции TRIM.</span><span class="sxs-lookup"><span data-stu-id="13159-117">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TRIM performs its operation.</span></span> <span data-ttu-id="13159-118">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="13159-118">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="13159-119">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="13159-119">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="13159-120">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="13159-120">Expression Examples</span></span>  
 <span data-ttu-id="13159-121">В данном примере удаляются начальные и конечные пробелы из строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="13159-121">This example removes leading and trailing spaces from a string literal.</span></span> <span data-ttu-id="13159-122">Возвращаемый результат — «New York».</span><span class="sxs-lookup"><span data-stu-id="13159-122">The return result is "New York".</span></span>  
  
```  
TRIM("   New York   ")  
```  
  
 <span data-ttu-id="13159-123">Данный пример удаляет начальные и конечные пробелы из результата сцепления столбцов **FirstName** и **LastName** .</span><span class="sxs-lookup"><span data-stu-id="13159-123">This example removes leading and trailing spaces from the result of concatenating the **FirstName** and **LastName** columns.</span></span> <span data-ttu-id="13159-124">Пустая строка между столбцами **FirstName** и **LastName** не удалена.</span><span class="sxs-lookup"><span data-stu-id="13159-124">The empty string between **FirstName** and **LastName** is not removed.</span></span>  
  
```  
TRIM(FirstName + " "+ LastName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="13159-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="13159-125">See Also</span></span>  
 <span data-ttu-id="13159-126">[LTRIM (выражение служб SSIS)](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="13159-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="13159-127">[RTRIM (выражение служб SSIS)](rtrim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="13159-127">[RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="13159-128">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="13159-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
