---
title: == (равно) (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- equal operator (==)
- == (equal operator)
ms.assetid: 36fd2354-7b93-4c95-9cf3-51ee24568950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12f92a267543c366dee4905010aeb84d93c4f408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732858"
---
# <a name="-equal-ssis-expression"></a><span data-ttu-id="a03ab-102">== (равно) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a03ab-102">== (Equal) (SSIS Expression)</span></span>
  <span data-ttu-id="a03ab-103">Выполняет сравнение с целью определения равенства двух выражений.</span><span class="sxs-lookup"><span data-stu-id="a03ab-103">Performs a comparison to determine if two expressions are equal.</span></span> <span data-ttu-id="a03ab-104">Перед проведением сравнения средство оценки выражений автоматически преобразует большинство типов данных.</span><span class="sxs-lookup"><span data-stu-id="a03ab-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span> <span data-ttu-id="a03ab-105">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a03ab-105">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
 <span data-ttu-id="a03ab-106">Однако для успешного выполнения выражения некоторые типы данных требуют, чтобы выражение включало в себя явное приведение.</span><span class="sxs-lookup"><span data-stu-id="a03ab-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="a03ab-107">Дополнительные сведения о допустимых приведениях типов данных см. в разделе [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="a03ab-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a03ab-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a03ab-108">Syntax</span></span>  
  
```  
  
expression1 == expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a03ab-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a03ab-109">Arguments</span></span>  
 <span data-ttu-id="a03ab-110">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="a03ab-110">*expression1, expression2*</span></span>  
 <span data-ttu-id="a03ab-111">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="a03ab-111">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a03ab-112">Типы результата</span><span class="sxs-lookup"><span data-stu-id="a03ab-112">Result Types</span></span>  
 <span data-ttu-id="a03ab-113">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="a03ab-113">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a03ab-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="a03ab-114">Remarks</span></span>  
 <span data-ttu-id="a03ab-115">Если какое-нибудь выражение имеет значение NULL, то результат сравнения будет NULL.</span><span class="sxs-lookup"><span data-stu-id="a03ab-115">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="a03ab-116">Если оба выражения имеют значение NULL, то результат будет NULL.</span><span class="sxs-lookup"><span data-stu-id="a03ab-116">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="a03ab-117">Наборы выражений *expression1* и *expression2*должны удовлетворять одному из следующих правил:</span><span class="sxs-lookup"><span data-stu-id="a03ab-117">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="a03ab-118">**Числовой** Как *expression1* , так и *expression2* должны иметь числовой тип данных.</span><span class="sxs-lookup"><span data-stu-id="a03ab-118">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="a03ab-119">В соответствии с правилами неявных числовых преобразований, выполняемых средством оценки выражений, пересечением типов данных должен быть целочисленный тип данных.</span><span class="sxs-lookup"><span data-stu-id="a03ab-119">The intersection of the data types must be a numeric data type, as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="a03ab-120">NULL не может быть значением пересечения двух числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="a03ab-120">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="a03ab-121">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a03ab-121">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="a03ab-122">**Символьный** . Значения выражений *expression1* и *expression2* должны иметь тип данных DT_STR или DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="a03ab-122">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="a03ab-123">Вычисленные значения этих двух выражений могут иметь различные строковые типы данных.</span><span class="sxs-lookup"><span data-stu-id="a03ab-123">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a03ab-124">Сравнения строк производятся с учетом регистра, диакритических знаков, японской азбуки и ширины символов.</span><span class="sxs-lookup"><span data-stu-id="a03ab-124">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="a03ab-125">**Дата, время или дата-время** . Значения выражений *expression1* и *expression2* должны иметь один из следующих типов данных: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET и DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="a03ab-125">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a03ab-126">Система не поддерживает сравнения выражений, значения которых имеют тип данных даты, времени или даты-времени.</span><span class="sxs-lookup"><span data-stu-id="a03ab-126">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="a03ab-127">Возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="a03ab-127">The system generates an error.</span></span>  
  
     <span data-ttu-id="a03ab-128">При сравнении выражений система применяет следующие правила преобразования (в порядке их перечисления).</span><span class="sxs-lookup"><span data-stu-id="a03ab-128">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="a03ab-129">Если значения двух выражений имеют один и тот же тип данных, выполняется сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="a03ab-129">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="a03ab-130">Если значение одного из выражений имеет тип данных DT_DBTIMESTAMPOFFSET, то другое будет неявно преобразовано в тип данных DT_DBTIMESTAMPOFFSET, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="a03ab-130">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="a03ab-131">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a03ab-131">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="a03ab-132">Если значение одного из выражений имеет тип данных DT_DBTIMESTAMP2, то другое будет неявно преобразовано в тип данных DT_DBTIMESTAMP2, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="a03ab-132">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="a03ab-133">Если значение одного из выражений имеет тип данных DT_DBTIME2, то другое будет неявно преобразовано в тип данных DT_DBTIME2, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="a03ab-133">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="a03ab-134">Если значение одного из выражений имеет тип данных, отличный от DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 или DT_DBTIME2, то перед началом сравнения значения будут преобразованы в тип данных DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="a03ab-134">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="a03ab-135">При сравнении выражений система исходит из следующих предположений.</span><span class="sxs-lookup"><span data-stu-id="a03ab-135">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="a03ab-136">Если оба выражения имеют тип данных, включающий доли секунды, то предполагается, что для типа, имеющего меньшее число разрядов, в недостающих разрядах содержатся нули.</span><span class="sxs-lookup"><span data-stu-id="a03ab-136">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="a03ab-137">Если оба выражения имеют тип даты, но смещение часового пояса присутствует только у одного из них, то предполагается, что дата без смещения выражена по Гринвичу (UTC).</span><span class="sxs-lookup"><span data-stu-id="a03ab-137">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
-   <span data-ttu-id="a03ab-138">**Логический** Значения *expression1* и *expression2* должны иметь логический тип данных.</span><span class="sxs-lookup"><span data-stu-id="a03ab-138">**Logical** Both *expression1* and *expression2* must evaluate to a Boolean.</span></span>  
  
-   <span data-ttu-id="a03ab-139">**GUID** . Значения выражений *expression1* и *expression2* должны иметь тип данных DT_GUID.</span><span class="sxs-lookup"><span data-stu-id="a03ab-139">**GUID** Both *expression1* and *expression2* must evaluate to the DT_GUID data type.</span></span>  
  
-   <span data-ttu-id="a03ab-140">**Двоичный** . Значения выражений *expression1* и *expression2* должны иметь тип данных DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="a03ab-140">**Binary** Both *expression1* and *expression2* must evaluate to the DT_BYTES data type.</span></span>  
  
-   <span data-ttu-id="a03ab-141">**BLOB** . Значения *expression1* и *expression2* должны иметь один и тот же тип данных больших двоичных объектов (BLOB): DT_TEXT, DT_NTEXT или DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="a03ab-141">**BLOB** Both *expression1* and *expression2* must evaluate to the same Binary Large Object Block (BLOB) data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="a03ab-142">Дополнительные сведения о типах данных см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a03ab-142">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="a03ab-143">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="a03ab-143">Expression Examples</span></span>  
 <span data-ttu-id="a03ab-144">Этот пример возвращает значение TRUE, если текущая дата равна 4 июля 2003 года.</span><span class="sxs-lookup"><span data-stu-id="a03ab-144">This example evaluates to TRUE if the current date is July 4, 2003.</span></span> <span data-ttu-id="a03ab-145">Дополнительные сведения см. в разделе [GETDATE (выражение служб SSIS)](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="a03ab-145">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="a03ab-146">"7/4/2003" == GETDATE()</span><span class="sxs-lookup"><span data-stu-id="a03ab-146">"7/4/2003" == GETDATE()</span></span>  
  
 <span data-ttu-id="a03ab-147">Этот пример вычисляет, что значение равно TRUE, если значение столбца **ListPrice** равно 500.</span><span class="sxs-lookup"><span data-stu-id="a03ab-147">This example evaluates to TRUE if the value in the **ListPrice** column is 500.</span></span>  
  
```  
ListPrice == 500  
```  
  
 <span data-ttu-id="a03ab-148">В данном примере используется переменная **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="a03ab-148">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="a03ab-149">Он возвращает TRUE, если значение **LPrice** равно 500.</span><span class="sxs-lookup"><span data-stu-id="a03ab-149">It evaluates to TRUE if the value of **LPrice** is 500.</span></span> <span data-ttu-id="a03ab-150">Чтобы выполнился синтаксический анализ выражения, тип данных этой переменной должен быть числовым.</span><span class="sxs-lookup"><span data-stu-id="a03ab-150">The data type of the variable must be numeric for the expression to parse successfully.</span></span>  
  
```  
@LPrice == 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="a03ab-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="a03ab-151">See Also</span></span>  
 <span data-ttu-id="a03ab-152">[\!= (не равно) (выражение служб SSIS)](equal-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a03ab-152">[!= &#40;Unequal&#41; &#40;SSIS Expression&#41;](equal-ssis-expression.md) </span></span>  
 <span data-ttu-id="a03ab-153">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="a03ab-153">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="a03ab-154">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a03ab-154">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
