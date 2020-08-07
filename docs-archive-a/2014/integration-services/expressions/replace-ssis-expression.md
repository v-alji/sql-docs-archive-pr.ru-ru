---
title: REPLACE (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- replacing string expression
- REPLACE function
ms.assetid: a6837043-ea70-4c6a-9c7a-6868b02b2adc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e483ba6c9c72cb777f2955929a717c6c2e17a8c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732822"
---
# <a name="replace-ssis-expression"></a><span data-ttu-id="42fa2-102">REPLACE (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="42fa2-102">REPLACE (SSIS Expression)</span></span>
  <span data-ttu-id="42fa2-103">Возвращает символьное выражение после замены символьной строки в выражении другой символьной строкой или пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="42fa2-103">Returns a character expression after replacing a character string within the expression with either a different character string or an empty string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42fa2-104">Функция REPLACE часто использует длинные строки.</span><span class="sxs-lookup"><span data-stu-id="42fa2-104">The REPLACE function frequently uses long strings.</span></span> <span data-ttu-id="42fa2-105">Последствия усечения могут быть корректно обработаны или могут вызвать предупреждение или ошибку.</span><span class="sxs-lookup"><span data-stu-id="42fa2-105">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="42fa2-106">Дополнительные сведения см. в разделе [Синтаксис (службы SSIS)](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="42fa2-106">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42fa2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42fa2-107">Syntax</span></span>  
  
```  
  
REPLACE(character_expression,searchstring,replacementstring)  
```  
  
## <a name="arguments"></a><span data-ttu-id="42fa2-108">Аргументы</span><span class="sxs-lookup"><span data-stu-id="42fa2-108">Arguments</span></span>  
 <span data-ttu-id="42fa2-109">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="42fa2-109">*character_expression*</span></span>  
 <span data-ttu-id="42fa2-110">Допустимое символьное выражение, в котором будет выполняться поиск.</span><span class="sxs-lookup"><span data-stu-id="42fa2-110">Is a valid character expression that the function searches.</span></span>  
  
 <span data-ttu-id="42fa2-111">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="42fa2-111">*searchstring*</span></span>  
 <span data-ttu-id="42fa2-112">Допустимое символьное выражение, которое функция пытается найти.</span><span class="sxs-lookup"><span data-stu-id="42fa2-112">Is a valid character expression that the function attempts to locate.</span></span>  
  
 <span data-ttu-id="42fa2-113">*replacementstring*</span><span class="sxs-lookup"><span data-stu-id="42fa2-113">*replacementstring*</span></span>  
 <span data-ttu-id="42fa2-114">Допустимое символьное выражение, являющееся строкой замены.</span><span class="sxs-lookup"><span data-stu-id="42fa2-114">Is a valid character expression that is the replacement expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="42fa2-115">Типы результата</span><span class="sxs-lookup"><span data-stu-id="42fa2-115">Result Types</span></span>  
 <span data-ttu-id="42fa2-116">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="42fa2-116">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42fa2-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="42fa2-117">Remarks</span></span>  
 <span data-ttu-id="42fa2-118">Длина *searchstring* должна быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="42fa2-118">The length of *searchstring* must not be zero.</span></span>  
  
 <span data-ttu-id="42fa2-119">Длина *replacementstring* может быть нулевой.</span><span class="sxs-lookup"><span data-stu-id="42fa2-119">The length of *replacementstring* may be zero.</span></span>  
  
 <span data-ttu-id="42fa2-120">Аргументы *searchstring* и *replacementstring* могут использовать переменные и столбцы.</span><span class="sxs-lookup"><span data-stu-id="42fa2-120">The *searchstring* and *replacementstring* arguments can use variables and columns.</span></span>  
  
 <span data-ttu-id="42fa2-121">Функция REPLАCE работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="42fa2-121">REPLACE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="42fa2-122">Аргументы*character_expression1, character_expression2* и *character_expression3* , которые являются строковыми литералами или столбцами данных, содержащими данные типа DT_STR, неявно приводятся к типу данных DT_WSTR до того, как функция REPLACE выполнит свою операцию.</span><span class="sxs-lookup"><span data-stu-id="42fa2-122">*character_expression1, character_expression2,* and *character_expression3* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before REPLACE performs its operation.</span></span> <span data-ttu-id="42fa2-123">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="42fa2-123">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="42fa2-124">Дополнительные сведения см. в разделе [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="42fa2-124">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="42fa2-125">Функция REPLACE возвращает NULL, если значение любого из аргументов равно NULL.</span><span class="sxs-lookup"><span data-stu-id="42fa2-125">REPLACE returns a null result if any argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="42fa2-126">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="42fa2-126">Expression Examples</span></span>  
 <span data-ttu-id="42fa2-127">В данном примере используется строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="42fa2-127">This example uses a string literal.</span></span> <span data-ttu-id="42fa2-128">Результат — «All Terrain Bike».</span><span class="sxs-lookup"><span data-stu-id="42fa2-128">The return result is "All Terrain Bike".</span></span>  
  
```  
REPLACE("Mountain Bike", "Mountain","All Terrain")  
```  
  
 <span data-ttu-id="42fa2-129">Этот пример удаляет строку «Bike» из столбца **Product** .</span><span class="sxs-lookup"><span data-stu-id="42fa2-129">This example removes the string "Bike" from the **Product** column.</span></span>  
  
```  
REPLACE(Product, "Bike","")  
```  
  
 <span data-ttu-id="42fa2-130">Этот пример заменяет значения в столбце **DaysToManufacture** .</span><span class="sxs-lookup"><span data-stu-id="42fa2-130">This example replaces values in the **DaysToManufacture** column.</span></span> <span data-ttu-id="42fa2-131">Эта столбец содержит целочисленный тип данных, а выражение включает приведение значений столбца **DaysToManufacture** к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="42fa2-131">The column has an integer data type and the expression includes casting **DaysToManufacture** to the DT_WSTR data type.</span></span>  
  
```  
REPLACE((DT_WSTR,8)DaysToManufacture,"6","5")  
```  
  
## <a name="see-also"></a><span data-ttu-id="42fa2-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="42fa2-132">See Also</span></span>  
 <span data-ttu-id="42fa2-133">[SUBSTRING (выражение служб SSIS)](substring-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="42fa2-133">[SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md) </span></span>  
 [<span data-ttu-id="42fa2-134">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="42fa2-134">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
