---
title: RTRIM (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RTRIM function
- trailing blanks
ms.assetid: 529bd43e-3f8a-4682-a33e-569176aa7fc4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 727c30fd72bfca5676b71f4ba42e936a9b926817
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732805"
---
# <a name="rtrim-ssis-expression"></a><span data-ttu-id="43dfe-102">RTRIM (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="43dfe-102">RTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="43dfe-103">Возвращает символьное выражение после удаления конечных пробелов.</span><span class="sxs-lookup"><span data-stu-id="43dfe-103">Returns a character expression after removing trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43dfe-104">RTRIM не удаляет пробельные символы, такие как символы табуляции и символы перехода на новую строку.</span><span class="sxs-lookup"><span data-stu-id="43dfe-104">RTRIM does not remove white space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="43dfe-105">Юникод обеспечивает элементы кода для множества различных типов пробелов, однако данная функция распознает только элемент кода 0x0020 в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="43dfe-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="43dfe-106">Если строки двухбайтовой кодировки (DBCS) преобразованы в Юникод, они могут включать пробелы, отличные от 0x0020. Тогда функция не в состоянии удалить такие пробелы.</span><span class="sxs-lookup"><span data-stu-id="43dfe-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="43dfe-107">Для удаления всех видов пробелов можно использовать метод Microsoft Visual Basic .NET RTrim в скрипте, выполняемом из компонента скриптов.</span><span class="sxs-lookup"><span data-stu-id="43dfe-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET RTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43dfe-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43dfe-108">Syntax</span></span>  
  
```  
  
RTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="43dfe-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="43dfe-109">Arguments</span></span>  
 <span data-ttu-id="43dfe-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="43dfe-110">*character_expression*</span></span>  
 <span data-ttu-id="43dfe-111">Символьное выражение, из которого удаляются пробелы.</span><span class="sxs-lookup"><span data-stu-id="43dfe-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="43dfe-112">Типы результата</span><span class="sxs-lookup"><span data-stu-id="43dfe-112">Result Types</span></span>  
 <span data-ttu-id="43dfe-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="43dfe-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43dfe-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="43dfe-114">Remarks</span></span>  
 <span data-ttu-id="43dfe-115">Метод RTRIM работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="43dfe-115">RTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="43dfe-116">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции RTRIM.</span><span class="sxs-lookup"><span data-stu-id="43dfe-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RTRIM performs its operation.</span></span> <span data-ttu-id="43dfe-117">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="43dfe-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="43dfe-118">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="43dfe-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="43dfe-119">Метод RTRIM возвращает значение NULL, если значением аргумента является NULL.</span><span class="sxs-lookup"><span data-stu-id="43dfe-119">RTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="43dfe-120">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="43dfe-120">Expression Examples</span></span>  
 <span data-ttu-id="43dfe-121">В этом примере удаляются конечные пробелы из строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="43dfe-121">This example removes trailing spaces from a string literal.</span></span> <span data-ttu-id="43dfe-122">Возвращаемый результат — «Hello».</span><span class="sxs-lookup"><span data-stu-id="43dfe-122">The return result is "Hello".</span></span>  
  
```  
RTRIM("Hello   ")  
```  
  
 <span data-ttu-id="43dfe-123">В этом примере удаляются конечные пробелы из объединения столбцов **FirstName** и **LastName** .</span><span class="sxs-lookup"><span data-stu-id="43dfe-123">This example removes trailing spaces from a concatenation of the **FirstName** and **LastName** columns.</span></span>  
  
```  
RTRIM(FirstName + " " + LastName)  
```  
  
 <span data-ttu-id="43dfe-124">В этом примере удаляются конечные пробелы из переменной **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="43dfe-124">This example removes trailing spaces from the **FirstName** variable.</span></span>  
  
```  
RTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="43dfe-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="43dfe-125">See Also</span></span>  
 <span data-ttu-id="43dfe-126">[LTRIM (выражение служб SSIS)](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="43dfe-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="43dfe-127">[TRIM (выражение служб SSIS)](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="43dfe-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="43dfe-128">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="43dfe-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
