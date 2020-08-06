---
title: LEN (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LEN function
- number of characters
ms.assetid: d961398b-e4d0-4936-be17-8f4c5882a640
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8863864168295a3a9a924df588312ee65b6f7fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658311"
---
# <a name="len-ssis-expression"></a><span data-ttu-id="2420f-102">LEN (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="2420f-102">LEN (SSIS Expression)</span></span>
  <span data-ttu-id="2420f-103">Возвращает число символов в символьном выражении.</span><span class="sxs-lookup"><span data-stu-id="2420f-103">Returns the number of characters in a character expression.</span></span> <span data-ttu-id="2420f-104">Функция учитывает начальные и завершающие пробелы, содержащиеся в строке.</span><span class="sxs-lookup"><span data-stu-id="2420f-104">If the string includes leading and trailing blanks, the function includes them in the count.</span></span> <span data-ttu-id="2420f-105">Результат выполнения функции LEN одинаков для строк из одно- и двухбайтовых символов.</span><span class="sxs-lookup"><span data-stu-id="2420f-105">LEN returns identical values for the same string of single and double byte characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2420f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2420f-106">Syntax</span></span>  
  
```  
  
LEN(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="2420f-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2420f-107">Arguments</span></span>  
 <span data-ttu-id="2420f-108">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="2420f-108">*character_expression*</span></span>  
 <span data-ttu-id="2420f-109">Вычисляемое выражение.</span><span class="sxs-lookup"><span data-stu-id="2420f-109">Is the expression to evaluate.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2420f-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="2420f-110">Result Types</span></span>  
 <span data-ttu-id="2420f-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="2420f-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2420f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="2420f-112">Remarks</span></span>  
 <span data-ttu-id="2420f-113">Аргумент *character_expression* может иметь следующий тип данных: DT_WSTR, DT_TEXT, DT_NTEXT или DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="2420f-113">The *character_expression* argument can be a DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="2420f-114">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2420f-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="2420f-115">Если параметр *character_expression* является строковым литералом либо столбцом данных типа DT_STR, перед выполнением функции LEN он автоматически приводится к типу DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="2420f-115">If *character_expression* is a string literal or a data column with the DT_STR data type, it is implicitly cast to the DT_WSTR data type before LEN performs its operation.</span></span> <span data-ttu-id="2420f-116">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="2420f-116">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="2420f-117">Дополнительные сведения см. в разделе [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2420f-117">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="2420f-118">Если функции LEN подается аргумент, имеющий тип данных BLOB, например DT_TEXT, DT_NTEXT или DT_IMAGE, результатом ее выполнения будет размер входного объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="2420f-118">If the argument passed to the LEN function has a Binary Large Object Block (BLOB) data type, such as DT_TEXT, DT_NTEXT, or DT_IMAGE, the function returns a byte count.</span></span>  
  
 <span data-ttu-id="2420f-119">Функция LEN возвращает значение NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="2420f-119">LEN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2420f-120">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="2420f-120">Expression Examples</span></span>  
 <span data-ttu-id="2420f-121">В данном примере функция возвращает длину строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="2420f-121">This example returns the length of a string literal.</span></span> <span data-ttu-id="2420f-122">Возвращается значение 12.</span><span class="sxs-lookup"><span data-stu-id="2420f-122">The return result is 12.</span></span>  
  
```  
LEN("Ball Bearing")  
```  
  
 <span data-ttu-id="2420f-123">В данном примере функция возвращает разницу между длиной значений в столбцах **FirstName** и **LastName** .</span><span class="sxs-lookup"><span data-stu-id="2420f-123">This example returns the difference between the length of values in the **FirstName** and **LastName** columns.</span></span>  
  
```  
LEN(FirstName) - LEN(LastName)  
```  
  
 <span data-ttu-id="2420f-124">Возвращает длину имени компьютера, хранящегося в системной переменной **MachineName**.</span><span class="sxs-lookup"><span data-stu-id="2420f-124">Returns the length of a computer name using the System variable **MachineName**.</span></span>  
  
```  
LEN(@MachineName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2420f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="2420f-125">See Also</span></span>  
 [<span data-ttu-id="2420f-126">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="2420f-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
