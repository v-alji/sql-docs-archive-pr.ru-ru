---
title: '? : (условный) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- conditional operator (?:)
- '?: (conditional operator)'
ms.assetid: d38e6890-7338-4ce0-a837-2dbb41823a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e607f9ed495184ef47ac2e4f1139b9a9566055ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668448"
---
# <a name="--conditional-ssis-expression"></a><span data-ttu-id="ce82a-103">?</span><span class="sxs-lookup"><span data-stu-id="ce82a-103">?</span></span> <span data-ttu-id="ce82a-104">: (условный) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ce82a-104">: (Conditional) (SSIS Expression)</span></span>
  <span data-ttu-id="ce82a-105">Возвращает одно из двух выражений на основе вычисления логического выражения.</span><span class="sxs-lookup"><span data-stu-id="ce82a-105">Returns one of two expressions based on the evaluation of a Boolean expression.</span></span> <span data-ttu-id="ce82a-106">Если логическое выражение принимает значение TRUE, то возвращается результат вычисления первого выражения.</span><span class="sxs-lookup"><span data-stu-id="ce82a-106">If the Boolean expression evaluates to TRUE, then the first expression is evaluated and the result is the expression result.</span></span> <span data-ttu-id="ce82a-107">Если логическое выражение принимает значение FALSE, возвращается результат вычисления второго выражения.</span><span class="sxs-lookup"><span data-stu-id="ce82a-107">If the Boolean expression evaluates to FALSE then the second expression is evaluated and its result is the expression result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce82a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce82a-108">Syntax</span></span>  
  
```  
  
boolean_expression?expression1:expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ce82a-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ce82a-109">Arguments</span></span>  
 <span data-ttu-id="ce82a-110">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="ce82a-110">*boolean_expression*</span></span>  
 <span data-ttu-id="ce82a-111">Любое допустимое выражение, результатом которого являются TRUE, FALSE или NULL</span><span class="sxs-lookup"><span data-stu-id="ce82a-111">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
 <span data-ttu-id="ce82a-112">*expression1*</span><span class="sxs-lookup"><span data-stu-id="ce82a-112">*expression1*</span></span>  
 <span data-ttu-id="ce82a-113">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="ce82a-113">Is any valid expression.</span></span>  
  
 <span data-ttu-id="ce82a-114">*expression2*</span><span class="sxs-lookup"><span data-stu-id="ce82a-114">*expression2*</span></span>  
 <span data-ttu-id="ce82a-115">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="ce82a-115">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ce82a-116">Типы результата</span><span class="sxs-lookup"><span data-stu-id="ce82a-116">Result Types</span></span>  
 <span data-ttu-id="ce82a-117">Тип данных *expression1* или *expression2*.</span><span class="sxs-lookup"><span data-stu-id="ce82a-117">The data type of *expression1* or *expression2*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce82a-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="ce82a-118">Remarks</span></span>  
 <span data-ttu-id="ce82a-119">Если выражение *boolean_expression* имеет значение NULL, результат тоже будет иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="ce82a-119">If the *boolean_expression* evaluates to NULL, the expression result is NULL.</span></span> <span data-ttu-id="ce82a-120">Если выбранное выражение, будь то *expression1* или *expression2* , принимает значение NULL, результат также примет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="ce82a-120">If a selected expression, either *expression1* or *expression2* is NULL, the result is NULL.</span></span> <span data-ttu-id="ce82a-121">Если выбранное выражение не равно NULL, а невыбранное равно NULL, результатом будет значение выбранного выражения.</span><span class="sxs-lookup"><span data-stu-id="ce82a-121">If a selected expression is not NULL, but the one not selected is NULL, the result is the value of the selected expression.</span></span>  
  
 <span data-ttu-id="ce82a-122">Если *expression1* и *expression2* имеют одинаковый тип данных, у результата тоже будет этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="ce82a-122">If *expression1* and *expression2* have the same data type, the result is that data type.</span></span> <span data-ttu-id="ce82a-123">Следующие дополнительные правила применяются к типам результатов:</span><span class="sxs-lookup"><span data-stu-id="ce82a-123">The following additional rules apply to result types:</span></span>  
  
-   <span data-ttu-id="ce82a-124">Тип данных DT_TEXT требует, чтобы *expression1* и *expression2* имели одну и ту же кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="ce82a-124">The DT_TEXT data type requires that *expression1* and *expression2* have the same code page.</span></span>  
  
-   <span data-ttu-id="ce82a-125">Длина результата типа DT_BYTES равна длине более длинного аргумента.</span><span class="sxs-lookup"><span data-stu-id="ce82a-125">The length of a result with the DT_BYTES data type is the length of the longer argument.</span></span>  
  
 <span data-ttu-id="ce82a-126">Выражения *expression1* и *expression2*должны иметь допустимый тип данных и должны удовлетворять одному из приведенных ниже правил.</span><span class="sxs-lookup"><span data-stu-id="ce82a-126">The expression set, *expression1* and *expression2*, must evaluate to valid data types and follow one of these rules:</span></span>  
  
-   <span data-ttu-id="ce82a-127">**Числовой** Как *expression1* , так и *expression2* должны иметь числовой тип данных.</span><span class="sxs-lookup"><span data-stu-id="ce82a-127">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="ce82a-128">В соответствии с правилами неявных числовых преобразований, выполняемых средством оценки выражений, пересечением типов данных должен быть числовой тип данных.</span><span class="sxs-lookup"><span data-stu-id="ce82a-128">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="ce82a-129">NULL не может быть значением пересечения двух числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="ce82a-129">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="ce82a-130">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ce82a-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="ce82a-131">**Строковый** . Значения выражений *expression1* и *expression2* должны иметь строковый тип: DT_STR или DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="ce82a-131">**String** Both *expression1* and *expression2* must be a string data type: DT_STR or DT_WSTR.</span></span> <span data-ttu-id="ce82a-132">Вычисленные значения этих двух выражений могут иметь различные строковые типы данных.</span><span class="sxs-lookup"><span data-stu-id="ce82a-132">The two expressions can evaluate to different string data types.</span></span> <span data-ttu-id="ce82a-133">Результат будет иметь тип данных DT_WSTR с длиной более длинного аргумента.</span><span class="sxs-lookup"><span data-stu-id="ce82a-133">The result has the DT_WSTR data type with a length of the longer argument.</span></span>  
  
-   <span data-ttu-id="ce82a-134">**Дата, время или дата-время** . Значения выражений *expression1* и *expression2* должны иметь один из следующих типов данных: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET и DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="ce82a-134">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce82a-135">Система не поддерживает сравнения выражений, значения которых имеют тип данных даты, времени или даты-времени.</span><span class="sxs-lookup"><span data-stu-id="ce82a-135">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="ce82a-136">Возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="ce82a-136">The system generates an error.</span></span>  
  
     <span data-ttu-id="ce82a-137">При сравнении выражений система применяет следующие правила преобразования (в порядке их перечисления).</span><span class="sxs-lookup"><span data-stu-id="ce82a-137">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="ce82a-138">Если значения двух выражений имеют один и тот же тип данных, выполняется сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="ce82a-138">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="ce82a-139">Если значение одного из выражений имеет тип данных DT_DBTIMESTAMPOFFSET, то другое будет неявно преобразовано в тип данных DT_DBTIMESTAMPOFFSET, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="ce82a-139">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="ce82a-140">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ce82a-140">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="ce82a-141">Если значение одного из выражений имеет тип данных DT_DBTIMESTAMP2, то другое будет неявно преобразовано в тип данных DT_DBTIMESTAMP2, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="ce82a-141">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="ce82a-142">Если значение одного из выражений имеет тип данных DT_DBTIME2, то другое будет неявно преобразовано в тип данных DT_DBTIME2, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="ce82a-142">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="ce82a-143">Если значение одного из выражений имеет тип данных, отличный от DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 или DT_DBTIME2, то перед началом сравнения значения будут преобразованы в тип данных DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="ce82a-143">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="ce82a-144">При сравнении выражений система исходит из следующих предположений.</span><span class="sxs-lookup"><span data-stu-id="ce82a-144">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="ce82a-145">Если оба выражения имеют тип данных, включающий доли секунды, то предполагается, что для типа, имеющего меньшее число разрядов, в недостающих разрядах содержатся нули.</span><span class="sxs-lookup"><span data-stu-id="ce82a-145">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="ce82a-146">Если оба выражения имеют тип даты, но смещение часового пояса присутствует только у одного из них, то предполагается, что дата без смещения выражена по Гринвичу (UTC).</span><span class="sxs-lookup"><span data-stu-id="ce82a-146">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="ce82a-147">Дополнительные сведения о типах данных см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ce82a-147">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ce82a-148">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="ce82a-148">Expression Examples</span></span>  
 <span data-ttu-id="ce82a-149">Этот пример показывает выражение, принимающее значение `savannah` или `unknown`в зависимости от условия.</span><span class="sxs-lookup"><span data-stu-id="ce82a-149">This example shows an expression that conditionally evaluates to `savannah` or `unknown`.</span></span>  
  
```  
@AnimalName == "Elephant"? "savannah": "unknown"  
```  
  
 <span data-ttu-id="ce82a-150">Этот пример показывает выражение, ссылающееся на столбец **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="ce82a-150">This example shows an expression that references a **ListPrice** column.</span></span> <span data-ttu-id="ce82a-151">**ListPrice** имеет тип данных DT_CY.</span><span class="sxs-lookup"><span data-stu-id="ce82a-151">**ListPrice** has the DT_CY data type.</span></span> <span data-ttu-id="ce82a-152">В выражении по условию происходит умножение **ListPrice** на 0,2 или 0,1.</span><span class="sxs-lookup"><span data-stu-id="ce82a-152">The expression conditionally multiplies **ListPrice** by .2 or .1.</span></span>  
  
```  
ListPrice < 350.00 ? ListPrice * .2 : ListPrice * .1  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce82a-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce82a-153">See Also</span></span>  
 <span data-ttu-id="ce82a-154">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="ce82a-154">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="ce82a-155">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ce82a-155">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
