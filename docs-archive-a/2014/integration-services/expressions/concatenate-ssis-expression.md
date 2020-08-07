---
title: + (объединение) (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- concatenation [Integration Services]
- + (concatenate operator)
- concatenate operator (+)
ms.assetid: 0fed6334-7a4f-42dc-a611-191fcaa0e443
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1c01f82a50962f42862db836171b0ad683c97453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732865"
---
# <a name="-concatenate-ssis-expression"></a><span data-ttu-id="63ef3-102">+ (объединение) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="63ef3-102">+ (Concatenate) (SSIS Expression)</span></span>
  <span data-ttu-id="63ef3-103">Сцепляют два выражения в одно.</span><span class="sxs-lookup"><span data-stu-id="63ef3-103">Concatenates two expressions into one expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ef3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63ef3-104">Syntax</span></span>  
  
```  
  
character_expression1 + character_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="63ef3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="63ef3-105">Arguments</span></span>  
 <span data-ttu-id="63ef3-106">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="63ef3-106">*expression1, expression2*</span></span>  
 <span data-ttu-id="63ef3-107">Допустимые типы данных выражения: DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT, или DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="63ef3-107">Is any valid DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="63ef3-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="63ef3-108">Result Types</span></span>  
 <span data-ttu-id="63ef3-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="63ef3-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ef3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="63ef3-110">Remarks</span></span>  
 <span data-ttu-id="63ef3-111">Выражение может использовать любой из типов данных — DT_STR, DT_WSTR или оба сразу.</span><span class="sxs-lookup"><span data-stu-id="63ef3-111">The expression can use either or both of the DT_STR and DT_WSTR data types.</span></span>  
  
 <span data-ttu-id="63ef3-112">Объединение типов данных DT_STR и DT_WSTR возвращает результат в формате DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="63ef3-112">The concatenation of the DT_STR and DT_WSTR data types returns a result of the DT_WSTR type.</span></span> <span data-ttu-id="63ef3-113">Длина строки — это сумма длин первоначальных строк в символах.</span><span class="sxs-lookup"><span data-stu-id="63ef3-113">The length of the string is the sum of the lengths of the original strings expressed in characters.</span></span>  
  
 <span data-ttu-id="63ef3-114">Могут быть сцеплены только данные со строковым типом данных (DT_STR и DT_WSTR) или данные большого двоичного объекта (BLOB) и типы данных DT_TEXT, DT_NTEXT и DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="63ef3-114">Only data with the string data types DT_STR and DT_WSTR or the Binary Large Object Block (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE can be concatenated.</span></span> <span data-ttu-id="63ef3-115">Другие типы данных перед объединением должны быть преобразованы в один из этих типов данных.</span><span class="sxs-lookup"><span data-stu-id="63ef3-115">Other data types must be explicitly converted to one of these data types before concatenation occurs.</span></span> <span data-ttu-id="63ef3-116">Дополнительные сведения о допустимых приведениях типов данных см. в разделе [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="63ef3-116">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="63ef3-117">Оба выражения должны состоять из одного типа данных, или должна быть возможность преобразовать тип данных одного выражения в тип данных другого выражения.</span><span class="sxs-lookup"><span data-stu-id="63ef3-117">Both expressions must be of the same data type, or one expression must be implicitly convertible to the data type of the other expression.</span></span> <span data-ttu-id="63ef3-118">Например, если строка «Дата заказа: » и столбец **OrderDate** объединены, значения в **OrderDate** будут преобразованы в строковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="63ef3-118">For example, if the string "Order date is " and the column **OrderDate** are concatenated, the values in **OrderDate** are implicitly converted to a string data type.</span></span> <span data-ttu-id="63ef3-119">Для объединения двух числовых значений оба числовых значения должны быть приведены к строковому типу данных.</span><span class="sxs-lookup"><span data-stu-id="63ef3-119">To concatenate two numeric values, both numeric values must be explicitly cast to a string data type.</span></span>  
  
 <span data-ttu-id="63ef3-120">Объединение может использовать только один тип данных BLOB: DT_TEXT, DT_NTEXT или DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="63ef3-120">A concatenation can use only one BLOB data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="63ef3-121">Если любой из элементов равен NULL, результат будет NULL.</span><span class="sxs-lookup"><span data-stu-id="63ef3-121">If either element is null, the result is null.</span></span>  
  
 <span data-ttu-id="63ef3-122">Строковые литералы должны заключаться в кавычки.</span><span class="sxs-lookup"><span data-stu-id="63ef3-122">String literals must be enclosed in quotation marks.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="63ef3-123">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="63ef3-123">Expression Examples</span></span>  
 <span data-ttu-id="63ef3-124">Пример объединяет значения в столбцах **FirstName** и **LastName** и вставляет символ пробела между ними.</span><span class="sxs-lookup"><span data-stu-id="63ef3-124">This example concatenates the values in the **FirstName** and **LastName** columns and inserts a space between them.</span></span>  
  
```  
FirstName + ' ' + LastName  
```  
  
 <span data-ttu-id="63ef3-125">Этот пример сцепляет переменные **ZIPCode** и **ZIPCode+4**.</span><span class="sxs-lookup"><span data-stu-id="63ef3-125">This example concatenates the variables **ZIPCode** and **ZIPCode+4**.</span></span> <span data-ttu-id="63ef3-126">Обе переменные имеют строковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="63ef3-126">Both variables have a string data type.</span></span> <span data-ttu-id="63ef3-127">**ZIPCode+4** должна быть заключена в квадратные скобки, поскольку имя переменной включает символ "+".</span><span class="sxs-lookup"><span data-stu-id="63ef3-127">**ZIPCode+4** must be enclosed in brackets because the variable name includes the + character.</span></span>  
  
```  
@ZIPCcode + "-" + @[ZipCode+4]  
```  
  
## <a name="see-also"></a><span data-ttu-id="63ef3-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="63ef3-128">See Also</span></span>  
 <span data-ttu-id="63ef3-129">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="63ef3-129">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="63ef3-130">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="63ef3-130">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
