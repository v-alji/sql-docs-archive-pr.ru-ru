---
title: '&gt;= (больше или равно) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- <= (less than or equal to operator)
- greater than or equal to (>=)
ms.assetid: 52ad504d-2f54-44de-b5e2-620577c0e289
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb7766d07f32bd4e63b8f39100a81206cee7d7f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732857"
---
# <a name="gt-greater-than-or-equal-to-ssis-expression"></a><span data-ttu-id="e7568-102">&gt;= (больше или равно) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="e7568-102">&gt;= (Greater Than or Equal To) (SSIS Expression)</span></span>
  <span data-ttu-id="e7568-103">Выполняет сравнение с целью определения, является ли первое выражение больше второго или равно ему.</span><span class="sxs-lookup"><span data-stu-id="e7568-103">Performs a comparison to determine if the first expression is greater than or equal to the second one.</span></span> <span data-ttu-id="e7568-104">Перед проведением сравнения средство оценки выражений автоматически преобразует большинство типов данных.</span><span class="sxs-lookup"><span data-stu-id="e7568-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7568-105">Данный оператор не поддерживает сравнение с использованием типов данных DT_TEXT, DT_NTEXT и DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="e7568-105">This operator does not support comparisons that use the DT_TEXT, DT_NTEXT, or DT_IMAGE data types.</span></span>  
  
 <span data-ttu-id="e7568-106">Однако для успешного выполнения выражения некоторые типы данных требуют, чтобы выражение включало в себя явное приведение.</span><span class="sxs-lookup"><span data-stu-id="e7568-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="e7568-107">Дополнительные сведения о допустимых приведениях типов данных см. в разделе [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e7568-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7568-108">Пробелов между двумя символами в этом операторе быть не должно.</span><span class="sxs-lookup"><span data-stu-id="e7568-108">There are no spaces between the two characters in this operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7568-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7568-109">Syntax</span></span>  
  
```  
  
expression1 >= expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7568-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e7568-110">Arguments</span></span>  
 <span data-ttu-id="e7568-111">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="e7568-111">*expression1, expression2*</span></span>  
 <span data-ttu-id="e7568-112">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="e7568-112">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e7568-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="e7568-113">Result Types</span></span>  
 <span data-ttu-id="e7568-114">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="e7568-114">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7568-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="e7568-115">Remarks</span></span>  
 <span data-ttu-id="e7568-116">Если какое-нибудь выражение имеет значение NULL, то результат сравнения будет NULL.</span><span class="sxs-lookup"><span data-stu-id="e7568-116">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="e7568-117">Если оба выражения имеют значение NULL, то результат будет NULL.</span><span class="sxs-lookup"><span data-stu-id="e7568-117">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="e7568-118">Наборы выражений *expression1* и *expression2*должны удовлетворять одному из следующих правил:</span><span class="sxs-lookup"><span data-stu-id="e7568-118">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="e7568-119">**Числовой** Как *expression1* , так и *expression2* должны иметь числовой тип данных.</span><span class="sxs-lookup"><span data-stu-id="e7568-119">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="e7568-120">В соответствии с правилами неявных числовых преобразований, выполняемых средством оценки выражений, пересечением типов данных должен быть числовой тип данных.</span><span class="sxs-lookup"><span data-stu-id="e7568-120">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="e7568-121">NULL не может быть значением пересечения двух числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="e7568-121">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="e7568-122">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e7568-122">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="e7568-123">**Символьный** . Значения выражений *expression1* и *expression2* должны иметь тип данных DT_STR или DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e7568-123">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="e7568-124">Вычисленные значения этих двух выражений могут иметь различные строковые типы данных.</span><span class="sxs-lookup"><span data-stu-id="e7568-124">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e7568-125">Сравнения строк производятся с учетом регистра, диакритических знаков, японской азбуки и ширины символов.</span><span class="sxs-lookup"><span data-stu-id="e7568-125">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="e7568-126">**Дата, время или дата-время** . Значения выражений *expression1* и *expression2* должны иметь один из следующих типов данных: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET и DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="e7568-126">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e7568-127">Система не поддерживает сравнения выражений, значения которых имеют тип данных даты, времени или даты-времени.</span><span class="sxs-lookup"><span data-stu-id="e7568-127">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="e7568-128">Возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="e7568-128">The system generates an error.</span></span>  
  
     <span data-ttu-id="e7568-129">При сравнении выражений система применяет следующие правила преобразования (в порядке их перечисления).</span><span class="sxs-lookup"><span data-stu-id="e7568-129">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="e7568-130">Если значения двух выражений имеют один и тот же тип данных, выполняется сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="e7568-130">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="e7568-131">Если значение одного из выражений имеет тип данных DT_DBTIMESTAMPOFFSET, то другое будет неявно преобразовано в тип данных DT_DBTIMESTAMPOFFSET, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="e7568-131">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="e7568-132">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e7568-132">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="e7568-133">Если значение одного из выражений имеет тип данных DT_DBTIMESTAMP2, то другое будет неявно преобразовано в тип данных DT_DBTIMESTAMP2, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="e7568-133">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="e7568-134">Если значение одного из выражений имеет тип данных DT_DBTIME2, то другое будет неявно преобразовано в тип данных DT_DBTIME2, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="e7568-134">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="e7568-135">Если значение одного из выражений имеет тип данных, отличный от DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 или DT_DBTIME2, то перед началом сравнения значения будут преобразованы в тип данных DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="e7568-135">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="e7568-136">При сравнении выражений система исходит из следующих предположений.</span><span class="sxs-lookup"><span data-stu-id="e7568-136">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="e7568-137">Если оба выражения имеют тип данных, включающий доли секунды, то предполагается, что для типа, имеющего меньшее число разрядов, в недостающих разрядах содержатся нули.</span><span class="sxs-lookup"><span data-stu-id="e7568-137">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="e7568-138">Если оба выражения имеют тип даты, но смещение часового пояса присутствует только у одного из них, то предполагается, что дата без смещения выражена по Гринвичу (UTC).</span><span class="sxs-lookup"><span data-stu-id="e7568-138">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="e7568-139">Дополнительные сведения о типах данных см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e7568-139">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e7568-140">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="e7568-140">Expression Examples</span></span>  
 <span data-ttu-id="e7568-141">При вычислении данного примера образуется значение TRUE, если текущая дата — 4 июля 2003 или более ранняя.</span><span class="sxs-lookup"><span data-stu-id="e7568-141">This example evaluates to TRUE if the current date is July 4, 2003 or earlier.</span></span> <span data-ttu-id="e7568-142">Дополнительные сведения см. в разделе [GETDATE (выражение служб SSIS)](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e7568-142">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" >= GETDATE()  
```  
  
 <span data-ttu-id="e7568-143">Данный пример оценивается как TRUE, если значение столбца **ListPrice** больше или равно 500.</span><span class="sxs-lookup"><span data-stu-id="e7568-143">This example evaluates to TRUE if the value in the **ListPrice** column is greater than or equal to 500.</span></span>  
  
```  
ListPrice >= 500  
```  
  
 <span data-ttu-id="e7568-144">В данном примере используется переменная **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="e7568-144">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="e7568-145">Он возвращает TRUE, если значение **LPrice** больше или равно 500.</span><span class="sxs-lookup"><span data-stu-id="e7568-145">It evaluates to TRUE if the value of **LPrice** is greater than or equal to 500.</span></span> <span data-ttu-id="e7568-146">Чтобы выполнился синтаксический анализ выражения, тип данных этой переменной должен быть числовым.</span><span class="sxs-lookup"><span data-stu-id="e7568-146">The data type of the variable must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice >= 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7568-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="e7568-147">See Also</span></span>  
 <span data-ttu-id="e7568-148">[&#62; (больше чем) (выражение служб SSIS)](greater-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e7568-148">[&#62; &#40;Greater Than&#41; &#40;SSIS Expression&#41;](greater-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="e7568-149">[&#60; (меньше чем) (выражение служб SSIS)](less-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e7568-149">[&#60; &#40;Less Than&#41; &#40;SSIS Expression&#41;](less-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="e7568-150">[&#60;= (меньше или равно) (выражение служб SSIS)](less-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e7568-150">[&#60;= &#40;Less Than or Equal To&#41; &#40;SSIS Expression&#41;](less-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="e7568-151">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="e7568-151">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="e7568-152">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="e7568-152">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
