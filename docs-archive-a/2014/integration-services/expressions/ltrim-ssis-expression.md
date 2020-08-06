---
title: LTRIM (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- LTRIM function
ms.assetid: d082f42a-d7e7-49f5-a503-ac44ba630832
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 678d9d93eb1dcd7649d2085b651a08418bbcd6a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658912"
---
# <a name="ltrim-ssis-expression"></a><span data-ttu-id="88538-102">LTRIM (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="88538-102">LTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="88538-103">Возвращает символьное выражение после удаления начальных пробелов.</span><span class="sxs-lookup"><span data-stu-id="88538-103">Returns a character expression after removing leading spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88538-104">Функция LTRIM не удаляет такие пробельные символы, как табуляция или перевод строки.</span><span class="sxs-lookup"><span data-stu-id="88538-104">LTRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="88538-105">Юникод обеспечивает элементы кода для множества различных типов пробелов, однако данная функция распознает только элемент кода 0x0020 в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="88538-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="88538-106">Если строки двухбайтовой кодировки (DBCS) преобразованы в Юникод, они могут включать пробелы, отличные от 0x0020. Тогда функция не в состоянии удалить такие пробелы.</span><span class="sxs-lookup"><span data-stu-id="88538-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="88538-107">Для удаления всех типов пробелов можно использовать метод LTrim Microsoft Visual Basic .NET в скрипте, запускаемом из компонента скриптов.</span><span class="sxs-lookup"><span data-stu-id="88538-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET LTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88538-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88538-108">Syntax</span></span>  
  
```  
  
LTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="88538-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="88538-109">Arguments</span></span>  
 <span data-ttu-id="88538-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="88538-110">*character_expression*</span></span>  
 <span data-ttu-id="88538-111">Символьное выражение, из которого удаляются пробелы.</span><span class="sxs-lookup"><span data-stu-id="88538-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="88538-112">Типы результата</span><span class="sxs-lookup"><span data-stu-id="88538-112">Result Types</span></span>  
 <span data-ttu-id="88538-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="88538-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88538-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="88538-114">Remarks</span></span>  
 <span data-ttu-id="88538-115">Функция LTRIM работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="88538-115">LTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="88538-116">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции LTRIM.</span><span class="sxs-lookup"><span data-stu-id="88538-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LTRIM performs its operation.</span></span> <span data-ttu-id="88538-117">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="88538-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="88538-118">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="88538-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="88538-119">Функция LTRIM возвращает значение NULL, если аргумент принимает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="88538-119">LTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="88538-120">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="88538-120">Expression Examples</span></span>  
 <span data-ttu-id="88538-121">Этот пример удаляет начальные пробелы из строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="88538-121">This example removes leading spaces from a string literal.</span></span> <span data-ttu-id="88538-122">Возвращаемый результат — «Hello».</span><span class="sxs-lookup"><span data-stu-id="88538-122">The return result is "Hello".</span></span>  
  
```  
LTRIM("    Hello")  
```  
  
 <span data-ttu-id="88538-123">Этот пример удаляет начальные пробелы из столбца **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="88538-123">This example removes leading spaces from the **FirstName** column.</span></span>  
  
```  
LTRIM(FirstName)  
```  
  
 <span data-ttu-id="88538-124">Этот пример удаляет начальные пробелы из переменной **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="88538-124">This example removes leading spaces from the **FirstName** variable.</span></span>  
  
```  
LTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="88538-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="88538-125">See Also</span></span>  
 <span data-ttu-id="88538-126">[RTRIM (выражение служб SSIS)](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="88538-126">[RTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="88538-127">[TRIM (выражение служб SSIS)](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="88538-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="88538-128">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="88538-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
