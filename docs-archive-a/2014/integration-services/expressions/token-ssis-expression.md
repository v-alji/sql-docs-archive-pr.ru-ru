---
title: TOKEN (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9fdd06bf-5bc9-445c-95bf-709e0ca5989b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5c0598c3832e4bf6f838087be4fee541663c8bff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732773"
---
# <a name="token--ssis-expression"></a><span data-ttu-id="7f813-102">TOKEN (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="7f813-102">TOKEN  (SSIS Expression)</span></span>
  <span data-ttu-id="7f813-103">Возвращает токен (подстроку) из строки с учетом заданных разделителей токенов строки и номера токена, определяющего, какой токен следует возвратить.</span><span class="sxs-lookup"><span data-stu-id="7f813-103">Returns a token (substring) from a string based on the specified delimiters that separate tokens in the string and the number of the token that denotes which token to be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f813-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f813-104">Syntax</span></span>  
  
```  
TOKEN(character_expression, delimiter_string, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f813-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7f813-105">Arguments</span></span>  
 <span data-ttu-id="7f813-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="7f813-106">*character_expression*</span></span>  
 <span data-ttu-id="7f813-107">Строка, содержащая токены, разделенные соответствующими символами.</span><span class="sxs-lookup"><span data-stu-id="7f813-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="7f813-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="7f813-108">*delimiter_string*</span></span>  
 <span data-ttu-id="7f813-109">Строка, содержащая символы разделения.</span><span class="sxs-lookup"><span data-stu-id="7f813-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="7f813-110">Например, строка "; ," содержит три символа разделения: точку с запятой, пробел и запятую.</span><span class="sxs-lookup"><span data-stu-id="7f813-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
 <span data-ttu-id="7f813-111">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="7f813-111">*occurrence*</span></span>  
 <span data-ttu-id="7f813-112">Целое число со знаком или без знака, указывающее возвращаемый токен.</span><span class="sxs-lookup"><span data-stu-id="7f813-112">A signed or unsigned integer that specifies the token to be returned.</span></span> <span data-ttu-id="7f813-113">Например, если для параметра указать значение 3, из строки будет возвращен третий токен.</span><span class="sxs-lookup"><span data-stu-id="7f813-113">For example, if you specify 3 as a value for this parameter, the third token in the string is returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7f813-114">Типы результата</span><span class="sxs-lookup"><span data-stu-id="7f813-114">Result Types</span></span>  
 <span data-ttu-id="7f813-115">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="7f813-115">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f813-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="7f813-116">Remarks</span></span>  
 <span data-ttu-id="7f813-117">Эта функция делит строку <character_expression> на набор токенов, разделенных символами, которые заданы в строке <delimiter_string>, а затем возвращает токен N, где N — это порядковый номер токена, заданный параметром \<occurrence>.</span><span class="sxs-lookup"><span data-stu-id="7f813-117">This function splits up the <character_expression> string into a set of tokens separated by the delimiters specified in the <delimiter_string> and then returns the Nth token where N is the number of occurrence of the token specified by the \<occurrence> parameter.</span></span> <span data-ttu-id="7f813-118">Примеры использования этой функции см. в разделе «Примеры».</span><span class="sxs-lookup"><span data-stu-id="7f813-118">See Examples section for sample usages of this function.</span></span>  
  
 <span data-ttu-id="7f813-119">Следующие примечания относятся к функции TOKEN.</span><span class="sxs-lookup"><span data-stu-id="7f813-119">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="7f813-120">Строка разделения может содержать один или несколько символов разделения.</span><span class="sxs-lookup"><span data-stu-id="7f813-120">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="7f813-121">Если значение параметра \<occurrence> больше общего числа токенов в строке, функция возвращает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="7f813-121">If the value of \<occurrence> parameter is higher than the total number of tokens in the string, the function returns NULL.</span></span>  
  
-   <span data-ttu-id="7f813-122">Первые разделители пропускаются.</span><span class="sxs-lookup"><span data-stu-id="7f813-122">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="7f813-123">Функция TOKEN работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7f813-123">TOKEN works only with the DT_WSTR data type.</span></span> <span data-ttu-id="7f813-124">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции TOKEN.</span><span class="sxs-lookup"><span data-stu-id="7f813-124">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="7f813-125">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7f813-125">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="7f813-126">Функция TOKEN возвращает значение NULL, если строка character_expression имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="7f813-126">TOKEN returns a null result if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="7f813-127">Переменные и столбцы могут использоваться в качестве значений всех аргументов в выражении.</span><span class="sxs-lookup"><span data-stu-id="7f813-127">You can use variables and columns as values of all arguments in the expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7f813-128">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="7f813-128">Expression Examples</span></span>  
 <span data-ttu-id="7f813-129">В следующем примере функция TOKEN возвращает значение «a».</span><span class="sxs-lookup"><span data-stu-id="7f813-129">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="7f813-130">Строка "a little white dog" состоит из 4 токенов: "a", "little", "white" и "dog", разделенных символом " " (символ пробела).</span><span class="sxs-lookup"><span data-stu-id="7f813-130">The string "a little white dog" has 4 tokens "a", "little", "white", "dog" separated by the delimiter " " (space character).</span></span> <span data-ttu-id="7f813-131">Второй аргумент — строка разделителя, задает только один разделитель, символ пробела, который используется для разбития входной строки на токены.</span><span class="sxs-lookup"><span data-stu-id="7f813-131">The second argument, a delimiter string, specifies only one delimiter, the space character, to be used in splitting the input string into tokens.</span></span> <span data-ttu-id="7f813-132">Последний аргумент — 1, указывает, что возвращаться должен первый токен.</span><span class="sxs-lookup"><span data-stu-id="7f813-132">The last argument, 1, specifies that the first token to be returned.</span></span> <span data-ttu-id="7f813-133">В этом образце строки первый токен — "а".</span><span class="sxs-lookup"><span data-stu-id="7f813-133">The first token is "a" in this sample string.</span></span>  
  
```  
TOKEN("a little white dog"," ",1)  
```  
  
 <span data-ttu-id="7f813-134">В следующем примере функция TOKEN возвращает значение «dog».</span><span class="sxs-lookup"><span data-stu-id="7f813-134">In the following example, the TOKEN function returns "dog".</span></span> <span data-ttu-id="7f813-135">Строка разделителя в этом примере содержит 5 разделителей.</span><span class="sxs-lookup"><span data-stu-id="7f813-135">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="7f813-136">Входная строка содержит 4 токена: "a", "little", "white", "dog".</span><span class="sxs-lookup"><span data-stu-id="7f813-136">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKEN("a:little|white dog","| ,.:",4)  
```  
  
 <span data-ttu-id="7f813-137">В следующем примере функция TOKEN возвращает «» (пустая строка) потому, что в строке нет 99 токенов.</span><span class="sxs-lookup"><span data-stu-id="7f813-137">In the following example, the TOKEN function returns "" (an empty string) because there are no 99 tokens in the string.</span></span>  
  
```  
TOKEN("a little white dog"," ",99)  
```  
  
 <span data-ttu-id="7f813-138">В следующем примере функция TOKEN возвращает полную строку.</span><span class="sxs-lookup"><span data-stu-id="7f813-138">In the following example, the TOKEN function returns the full string.</span></span> <span data-ttu-id="7f813-139">Функция выполняет синтаксический анализ входной строки на предмет разделителей, и, поскольку их в строке нет, добавляет всю строку как первый токен.</span><span class="sxs-lookup"><span data-stu-id="7f813-139">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKEN("a little white dog","|",1)  
```  
  
 <span data-ttu-id="7f813-140">В следующем примере функция TOKEN возвращает значение «a».</span><span class="sxs-lookup"><span data-stu-id="7f813-140">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="7f813-141">Функция пропускает все пробелы в начале строки.</span><span class="sxs-lookup"><span data-stu-id="7f813-141">It ignores all the leading space characters.</span></span>  
  
```  
TOKEN("        a little white dog", " ", 1)  
```  
  
 <span data-ttu-id="7f813-142">В следующем примере функция TOKEN возвращает год из строки даты.</span><span class="sxs-lookup"><span data-stu-id="7f813-142">In the following example, the TOKEN function returns the year from a date string.</span></span>  
  
```  
TOKEN("2009/01/01", "/"), 1  
```  
  
 <span data-ttu-id="7f813-143">В следующем примере функция TOKEN возвращает имя файла из указанного пути.</span><span class="sxs-lookup"><span data-stu-id="7f813-143">In the following example, the TOKEN function returns the file name from the specified path.</span></span> <span data-ttu-id="7f813-144">Например, если значение параметра User::Path равно "c:\program files\data\myfile.txt", функция TOKEN возвращает строку "myfile.txt".</span><span class="sxs-lookup"><span data-stu-id="7f813-144">For example, if the value of User::Path is "c:\program files\data\myfile.txt", the TOKEN function returns "myfile.txt".</span></span> <span data-ttu-id="7f813-145">Функция TOKENCOUNT возвращает 4, а функция TOKEN возвращает четвертый токен — "myfile.txt".</span><span class="sxs-lookup"><span data-stu-id="7f813-145">The TOKENCOUNT function returns 4 and the TOKEN function return the 4th token, "myfile.txt".</span></span>  
  
```  
TOKEN(@[User::Path], "\\", TOKENCOUNT(@[User::Path], "\\"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f813-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f813-146">See Also</span></span>  
 [<span data-ttu-id="7f813-147">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="7f813-147">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
