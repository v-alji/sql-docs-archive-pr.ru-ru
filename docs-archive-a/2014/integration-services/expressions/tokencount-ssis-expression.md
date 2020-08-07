---
title: TOKENCOUNT (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c0efed1-c2b3-4f20-a3a1-ad91283b7c0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9068e4958570a0222bc8e1a4c90d34acc5bdf3dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732765"
---
# <a name="tokencount-ssis-expression"></a><span data-ttu-id="4a254-102">TOKENCOUNT (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="4a254-102">TOKENCOUNT (SSIS Expression)</span></span>
  <span data-ttu-id="4a254-103">Возвращает несколько токенов в строке, в которой они разделены указанными символами.</span><span class="sxs-lookup"><span data-stu-id="4a254-103">Returns the number of tokens in a string that contains tokens separated by the specified delimiters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a254-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a254-104">Syntax</span></span>  
  
```  
TOKENCOUNT(character_expression, delimiter_string)  
```  
  
## <a name="arguments"></a><span data-ttu-id="4a254-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4a254-105">Arguments</span></span>  
 <span data-ttu-id="4a254-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="4a254-106">*character_expression*</span></span>  
 <span data-ttu-id="4a254-107">Строка, содержащая токены, разделенные соответствующими символами.</span><span class="sxs-lookup"><span data-stu-id="4a254-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="4a254-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="4a254-108">*delimiter_string*</span></span>  
 <span data-ttu-id="4a254-109">Строка, содержащая символы разделения.</span><span class="sxs-lookup"><span data-stu-id="4a254-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="4a254-110">Например, строка "; ," содержит три символа разделения: точку с запятой, пробел и запятую.</span><span class="sxs-lookup"><span data-stu-id="4a254-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4a254-111">Типы результата</span><span class="sxs-lookup"><span data-stu-id="4a254-111">Result Types</span></span>  
 <span data-ttu-id="4a254-112">DT_I4</span><span class="sxs-lookup"><span data-stu-id="4a254-112">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a254-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a254-113">Remarks</span></span>  
 <span data-ttu-id="4a254-114">Следующие примечания относятся к функции TOKEN.</span><span class="sxs-lookup"><span data-stu-id="4a254-114">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="4a254-115">Строка разделения может содержать один или несколько символов разделения.</span><span class="sxs-lookup"><span data-stu-id="4a254-115">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="4a254-116">Первые разделители пропускаются.</span><span class="sxs-lookup"><span data-stu-id="4a254-116">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="4a254-117">TOKENCOUNT работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="4a254-117">TOKENCOUNT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="4a254-118">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции TOKEN.</span><span class="sxs-lookup"><span data-stu-id="4a254-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="4a254-119">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="4a254-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="4a254-120">Функция TOKENCOUNT возвращает результат 0 (нуль), если строка character_expression имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="4a254-120">TOKENCOUNT returns 0 (zero) if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="4a254-121">Переменные и столбцы могут использоваться в качестве аргументов для этого выражения.</span><span class="sxs-lookup"><span data-stu-id="4a254-121">You can use variables and columns as arguments for this expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4a254-122">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="4a254-122">Expression Examples</span></span>  
 <span data-ttu-id="4a254-123">В следующем примере функция TOKENCOUNT возвращает значение 3, потому что строка содержит три токена: "01", "12", "2011".</span><span class="sxs-lookup"><span data-stu-id="4a254-123">In the following example, the TOKENCOUNT function returns 3 because the string contains three tokens: "01", "12", "2011".</span></span>  
  
```  
TOKENCOUNT("01/12/2011", "/")  
```  
  
 <span data-ttu-id="4a254-124">В следующем примере функция TOKENCOUNT возвращает 4, потому что в строке четыре токена ("a", "little", "white", "dog").</span><span class="sxs-lookup"><span data-stu-id="4a254-124">In the following example, the TOKENCOUNT function returns 4 because there are four tokens ("a", "little", "white", "dog").</span></span>  
  
```  
TOKENCOUNT("a little white dog"," ")  
```  
  
 <span data-ttu-id="4a254-125">В следующем примере функция TOKENCOUNT возвращает значение 1.</span><span class="sxs-lookup"><span data-stu-id="4a254-125">In the following example, the TOKENCOUNT function returns 1.</span></span> <span data-ttu-id="4a254-126">Функция выполняет синтаксический анализ входной строки на предмет разделителей, и, поскольку их в строке нет, добавляет всю строку как первый токен.</span><span class="sxs-lookup"><span data-stu-id="4a254-126">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKENCOUNT("a little white dog","|")  
```  
  
 <span data-ttu-id="4a254-127">В следующем примере функция TOKENCOUNT возвращает значение 4.</span><span class="sxs-lookup"><span data-stu-id="4a254-127">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="4a254-128">Строка разделителя в этом примере содержит 5 разделителей.</span><span class="sxs-lookup"><span data-stu-id="4a254-128">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="4a254-129">Входная строка содержит 4 токена: "a", "little", "white", "dog".</span><span class="sxs-lookup"><span data-stu-id="4a254-129">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKENCOUNT("a:little|white dog","| ,.:")  
```  
  
 <span data-ttu-id="4a254-130">В следующем примере функция TOKENCOUNT возвращает значение 4.</span><span class="sxs-lookup"><span data-stu-id="4a254-130">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="4a254-131">Функция пропускает все пробелы в начале строки.</span><span class="sxs-lookup"><span data-stu-id="4a254-131">It ignores all the leading space characters.</span></span>  
  
```  
TOKENCOUNT("        a little white dog", " ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a254-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a254-132">See Also</span></span>  
 [<span data-ttu-id="4a254-133">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="4a254-133">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
