---
title: '&lt; (меньше) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- less than (<)
- < (less than operator)
ms.assetid: 8674afdc-4276-46cb-be08-5aadfe8b9624
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d8367e337fe92667d5bdc39638d03af390797b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735494"
---
# <a name="lt-less-than-ssis-expression"></a><span data-ttu-id="8bad7-102">&lt; (меньше) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="8bad7-102">&lt; (Less Than) (SSIS Expression)</span></span>
  <span data-ttu-id="8bad7-103">Выполняет сравнение с целью определения, является ли первое выражение меньше второго.</span><span class="sxs-lookup"><span data-stu-id="8bad7-103">Performs a comparison to determine if the first expression is less than the second one.</span></span> <span data-ttu-id="8bad7-104">Перед проведением сравнения средство оценки выражений автоматически преобразует большинство типов данных.</span><span class="sxs-lookup"><span data-stu-id="8bad7-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8bad7-105">Данный оператор не поддерживает сравнение с использованием типов данных DT_TEXT, DT_NTEXT и DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="8bad7-105">This operator does not support comparisons that use the DT_TEXT, DT_NTEXT, or DT_IMAGE data types.</span></span>  
  
 <span data-ttu-id="8bad7-106">Однако для успешного выполнения выражения некоторые типы данных требуют, чтобы выражение включало в себя явное приведение.</span><span class="sxs-lookup"><span data-stu-id="8bad7-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="8bad7-107">Дополнительные сведения о допустимых приведениях типов данных см. в разделе [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="8bad7-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bad7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bad7-108">Syntax</span></span>  
  
```  
  
expression1 < expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="8bad7-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8bad7-109">Arguments</span></span>  
 <span data-ttu-id="8bad7-110">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="8bad7-110">*expression1, expression2*</span></span>  
 <span data-ttu-id="8bad7-111">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="8bad7-111">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8bad7-112">Типы результата</span><span class="sxs-lookup"><span data-stu-id="8bad7-112">Result Types</span></span>  
 <span data-ttu-id="8bad7-113">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="8bad7-113">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bad7-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="8bad7-114">Remarks</span></span>  
 <span data-ttu-id="8bad7-115">Если какое-нибудь выражение имеет значение NULL, то результат сравнения будет NULL.</span><span class="sxs-lookup"><span data-stu-id="8bad7-115">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="8bad7-116">Если оба выражения имеют значение NULL, то результат будет NULL.</span><span class="sxs-lookup"><span data-stu-id="8bad7-116">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="8bad7-117">Наборы выражений *expression1* и *expression2*должны удовлетворять одному из следующих правил:</span><span class="sxs-lookup"><span data-stu-id="8bad7-117">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="8bad7-118">**Числовой** Как *expression1* , так и *expression2* должны иметь числовой тип данных.</span><span class="sxs-lookup"><span data-stu-id="8bad7-118">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="8bad7-119">В соответствии с правилами неявных числовых преобразований, выполняемых средством оценки выражений, пересечением типов данных должен быть числовой тип данных.</span><span class="sxs-lookup"><span data-stu-id="8bad7-119">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="8bad7-120">NULL не может быть значением пересечения двух числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="8bad7-120">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="8bad7-121">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8bad7-121">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="8bad7-122">**Символьный** . Значения выражений *expression1* и *expression2* должны иметь тип данных DT_STR или DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8bad7-122">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="8bad7-123">Вычисленные значения этих двух выражений могут иметь различные строковые типы данных.</span><span class="sxs-lookup"><span data-stu-id="8bad7-123">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bad7-124">Сравнения строк производятся с учетом регистра, диакритических знаков, японской азбуки и ширины символов.</span><span class="sxs-lookup"><span data-stu-id="8bad7-124">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="8bad7-125">**Дата, время или дата-время** . Значения выражений *expression1* и *expression2* должны иметь один из следующих типов данных: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET и DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="8bad7-125">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bad7-126">Система не поддерживает сравнения выражений, значения которых имеют тип данных даты, времени или даты-времени.</span><span class="sxs-lookup"><span data-stu-id="8bad7-126">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="8bad7-127">Возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="8bad7-127">The system generates an error.</span></span>  
  
     <span data-ttu-id="8bad7-128">При сравнении выражений система применяет следующие правила преобразования (в порядке их перечисления).</span><span class="sxs-lookup"><span data-stu-id="8bad7-128">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="8bad7-129">Если значения двух выражений имеют один и тот же тип данных, выполняется сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="8bad7-129">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="8bad7-130">Если значение одного из выражений имеет тип данных DT_DBTIMESTAMPOFFSET, то другое будет неявно преобразовано в тип данных DT_DBTIMESTAMPOFFSET, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="8bad7-130">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="8bad7-131">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8bad7-131">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="8bad7-132">Если значение одного из выражений имеет тип данных DT_DBTIMESTAMP2, то другое будет неявно преобразовано в тип данных DT_DBTIMESTAMP2, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="8bad7-132">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="8bad7-133">Если значение одного из выражений имеет тип данных DT_DBTIME2, то другое будет неявно преобразовано в тип данных DT_DBTIME2, после чего будет произведено сравнение для этого типа.</span><span class="sxs-lookup"><span data-stu-id="8bad7-133">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="8bad7-134">Если значение одного из выражений имеет тип данных, отличный от DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 или DT_DBTIME2, то перед началом сравнения значения будут преобразованы в тип данных DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="8bad7-134">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="8bad7-135">При сравнении выражений система исходит из следующих предположений.</span><span class="sxs-lookup"><span data-stu-id="8bad7-135">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="8bad7-136">Если оба выражения имеют тип данных, включающий доли секунды, то предполагается, что для типа, имеющего меньшее число разрядов, в недостающих разрядах содержатся нули.</span><span class="sxs-lookup"><span data-stu-id="8bad7-136">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="8bad7-137">Если оба выражения имеют тип даты, но смещение часового пояса присутствует только у одного из них, то предполагается, что дата без смещения выражена по Гринвичу (UTC).</span><span class="sxs-lookup"><span data-stu-id="8bad7-137">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="8bad7-138">Дополнительные сведения о типах данных см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="8bad7-138">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="8bad7-139">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="8bad7-139">Expression Examples</span></span>  
 <span data-ttu-id="8bad7-140">Этот пример возвращает значение TRUE, если текущая дата равна 4 июля 2003 года или позже.</span><span class="sxs-lookup"><span data-stu-id="8bad7-140">This example evaluates to TRUE if the current date is later than July 4, 2003.</span></span> <span data-ttu-id="8bad7-141">Дополнительные сведения см. в разделе [GETDATE (выражение служб SSIS)](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="8bad7-141">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" < GETDATE()  
```  
  
 <span data-ttu-id="8bad7-142">Результат вычисления данного примера равен TRUE, если значение в столбце **ListPrice** меньше 500.</span><span class="sxs-lookup"><span data-stu-id="8bad7-142">This example evaluates to TRUE if the value in the **ListPrice** column is less than 500.</span></span>  
  
```  
ListPrice < 500  
```  
  
 <span data-ttu-id="8bad7-143">В данном примере используется переменная **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="8bad7-143">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="8bad7-144">Он возвращает TRUE, если значение **LPrice** меньше 500.</span><span class="sxs-lookup"><span data-stu-id="8bad7-144">It evaluates to TRUE if the value of **LPrice** is less than 500.</span></span> <span data-ttu-id="8bad7-145">Чтобы выполнился синтаксический анализ выражения, тип данных этой переменной должен быть числовым.</span><span class="sxs-lookup"><span data-stu-id="8bad7-145">The data type of the variable must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice < 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bad7-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="8bad7-146">See Also</span></span>  
 <span data-ttu-id="8bad7-147">[&#62; (больше чем) (выражение служб SSIS)](greater-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8bad7-147">[&#62; &#40;Greater Than&#41; &#40;SSIS Expression&#41;](greater-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="8bad7-148">[&#62;= (больше или равно) (выражение служб SSIS)](greater-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8bad7-148">[&#62;= &#40;Greater Than or Equal To&#41; &#40;SSIS Expression&#41;](greater-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="8bad7-149">[&#60;= (меньше или равно) (выражение служб SSIS)](less-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8bad7-149">[&#60;= &#40;Less Than or Equal To&#41; &#40;SSIS Expression&#41;](less-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="8bad7-150">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="8bad7-150">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="8bad7-151">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="8bad7-151">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
