---
title: Операторы в выражениях (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d22dc8b6-4353-40e7-91a1-65e8dae6325d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa8042df39e535425a05414c1e39ee6a12ff2f39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663951"
---
# <a name="operators-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="f5f70-102">Операторы в выражениях (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f5f70-102">Operators in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f5f70-103">Оператор — это символ, который означает действия, применяемые к одному или более элементам выражения.</span><span class="sxs-lookup"><span data-stu-id="f5f70-103">An operator is a symbol that represents actions applied to one or more terms in an expression.</span></span> <span data-ttu-id="f5f70-104">В выражениях поддерживаются следующие типы операторов: арифметические, сравнения, объединения, логические (поразрядные) и сдвига.</span><span class="sxs-lookup"><span data-stu-id="f5f70-104">The following categories of operators are supported in an expression: arithmetic, comparison, concatenation, logical or bitwise, and bit shift.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="arithmetic"></a><span data-ttu-id="f5f70-105">Арифметические</span><span class="sxs-lookup"><span data-stu-id="f5f70-105">Arithmetic</span></span>  
 <span data-ttu-id="f5f70-106">Арифметические операторы выполняют математические операции над двумя числовыми элементами выражения.</span><span class="sxs-lookup"><span data-stu-id="f5f70-106">Arithmetic operators perform mathematical operations on two numeric terms in an expression.</span></span>  
  
|<span data-ttu-id="f5f70-107">Оператор</span><span class="sxs-lookup"><span data-stu-id="f5f70-107">Operator</span></span>|<span data-ttu-id="f5f70-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f70-108">Description</span></span>|  
|--------------|-----------------|  
|^|<span data-ttu-id="f5f70-109">Возводит число в степень другого числа.</span><span class="sxs-lookup"><span data-stu-id="f5f70-109">Raises a number to the power of another number.</span></span>|  
|*|<span data-ttu-id="f5f70-110">Перемножает два числа.</span><span class="sxs-lookup"><span data-stu-id="f5f70-110">Multiplies two numbers.</span></span>|  
|/|<span data-ttu-id="f5f70-111">Делит одно число на другое и возвращает результат в виде числа с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="f5f70-111">Divides two numbers and returns a floating-point result.</span></span>|  
|<span data-ttu-id="f5f70-112">\|Делит одно число на другое и возвращает целочисленный результат.</span><span class="sxs-lookup"><span data-stu-id="f5f70-112">\|Divides two numbers and returns an integer result.</span></span>|  
|<span data-ttu-id="f5f70-113">Mod</span><span class="sxs-lookup"><span data-stu-id="f5f70-113">Mod</span></span>|<span data-ttu-id="f5f70-114">Возвращает целочисленный остаток при делении.</span><span class="sxs-lookup"><span data-stu-id="f5f70-114">Returns the integer remainder of a division.</span></span> <span data-ttu-id="f5f70-115">Например, 7 Mod 5 = 2, поскольку остаток от деления 7 на 5 равен 2.</span><span class="sxs-lookup"><span data-stu-id="f5f70-115">For example, 7 Mod 5 = 2 because the remainder of 7 divided by 5 is 2.</span></span>|  
|+|<span data-ttu-id="f5f70-116">Складывает два числа.</span><span class="sxs-lookup"><span data-stu-id="f5f70-116">Adds two numbers together.</span></span>|  
|-|<span data-ttu-id="f5f70-117">Возвращает разность двух чисел или указывает на отрицательное значение числового выражения.</span><span class="sxs-lookup"><span data-stu-id="f5f70-117">Returns the difference between two numbers or indicates the negative value of a numeric term.</span></span>|  
  
### <a name="comparison"></a><span data-ttu-id="f5f70-118">Сравнение</span><span class="sxs-lookup"><span data-stu-id="f5f70-118">Comparison</span></span>  
 <span data-ttu-id="f5f70-119">Операторы сравнения позволяют проверить, одинаковы ли два выражения.</span><span class="sxs-lookup"><span data-stu-id="f5f70-119">Comparison operators test whether two expressions are the same.</span></span>  
  
|<span data-ttu-id="f5f70-120">Оператор</span><span class="sxs-lookup"><span data-stu-id="f5f70-120">Operator</span></span>|<span data-ttu-id="f5f70-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f70-121">Description</span></span>|  
|--------------|-----------------|  
|<|<span data-ttu-id="f5f70-122">Меньше.</span><span class="sxs-lookup"><span data-stu-id="f5f70-122">Less than.</span></span>|  
|\<=|<span data-ttu-id="f5f70-123">Меньше или равно.</span><span class="sxs-lookup"><span data-stu-id="f5f70-123">Less than or equal to.</span></span>|  
|>|<span data-ttu-id="f5f70-124">Больше.</span><span class="sxs-lookup"><span data-stu-id="f5f70-124">Greater than.</span></span>|  
|>=|<span data-ttu-id="f5f70-125">Больше или равно.</span><span class="sxs-lookup"><span data-stu-id="f5f70-125">Greater than or equal to.</span></span>|  
|=|<span data-ttu-id="f5f70-126">Равно.</span><span class="sxs-lookup"><span data-stu-id="f5f70-126">Equal to.</span></span>|  
|<>|<span data-ttu-id="f5f70-127">Не равно.</span><span class="sxs-lookup"><span data-stu-id="f5f70-127">Not equal to.</span></span>|  
|<span data-ttu-id="f5f70-128">Похоже</span><span class="sxs-lookup"><span data-stu-id="f5f70-128">Like</span></span>|<span data-ttu-id="f5f70-129">Определяет, совпадает ли указанная символьная строка с заданным шаблоном.</span><span class="sxs-lookup"><span data-stu-id="f5f70-129">Determines whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="f5f70-130">Шаблон может включать обычные символы и символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="f5f70-130">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="f5f70-131">Во время сравнения с шаблоном необходимо, чтобы его обычные символы в точности совпадали с символами, указанными в строке.</span><span class="sxs-lookup"><span data-stu-id="f5f70-131">During pattern matching, regular characters must exactly match the characters specified in the character string.</span></span> <span data-ttu-id="f5f70-132">Символы-шаблоны могут совпадать с произвольными элементами символьной строки.</span><span class="sxs-lookup"><span data-stu-id="f5f70-132">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="f5f70-133">Использование символов-шаблонов в отличие от использования операторов сравнения строки (= и !=) делает оператор LIKE более гибким.</span><span class="sxs-lookup"><span data-stu-id="f5f70-133">Using wildcard characters makes the LIKE operator more flexible than using the = and != string comparison operators.</span></span><br /><br /> <span data-ttu-id="f5f70-134">Ниже перечислены символы, которые можно использовать в качестве подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="f5f70-134">The following lists characters that can be used as wildcards:</span></span><br /><br /> <span data-ttu-id="f5f70-135">**%**: Любая строка из нуля или более символов.</span><span class="sxs-lookup"><span data-stu-id="f5f70-135">**%**: Any string of zero or more characters.</span></span><br /><br /> <span data-ttu-id="f5f70-136">**_**: Любой отдельный символ.</span><span class="sxs-lookup"><span data-stu-id="f5f70-136">**_**: Any single character.</span></span><br /><br /> <span data-ttu-id="f5f70-137">**[]**: Любой отдельный символ в указанном диапазоне (например, [a-f]) или набор (например, [aeiou]).</span><span class="sxs-lookup"><span data-stu-id="f5f70-137">**[ ]**: Any single character within the specified range (for example, [a-f]) or set (for example, [aeiou]).</span></span><br /><br /> <span data-ttu-id="f5f70-138">**[^]**: Любой отдельный символ, не находящиеся в указанном диапазоне (например, [^ a-f]) или набор (например, [^ aeiou]).</span><span class="sxs-lookup"><span data-stu-id="f5f70-138">**[^]**: Any single character not within the specified range (for example, [^a-f]) or set (for example, [^aeiou]).</span></span>|  
|<span data-ttu-id="f5f70-139">Is</span><span class="sxs-lookup"><span data-stu-id="f5f70-139">Is</span></span>|<span data-ttu-id="f5f70-140">Сравнивает две ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="f5f70-140">Compares two object references.</span></span>|  
  
### <a name="string-concatenation"></a><span data-ttu-id="f5f70-141">Объединение строк</span><span class="sxs-lookup"><span data-stu-id="f5f70-141">String Concatenation</span></span>  
 <span data-ttu-id="f5f70-142">Оператор объединения строк добавляет к первой строке выражения вторую строку.</span><span class="sxs-lookup"><span data-stu-id="f5f70-142">String concatenation appends the second string to the first string in an expression.</span></span> <span data-ttu-id="f5f70-143">Для остальных операций над строками используйте встроенные функции.</span><span class="sxs-lookup"><span data-stu-id="f5f70-143">For other string operations, use built-in functions.</span></span>  
  
|<span data-ttu-id="f5f70-144">Оператор</span><span class="sxs-lookup"><span data-stu-id="f5f70-144">Operator</span></span>|<span data-ttu-id="f5f70-145">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f70-145">Description</span></span>|  
|--------------|-----------------|  
|&|<span data-ttu-id="f5f70-146">Объединяет две строки</span><span class="sxs-lookup"><span data-stu-id="f5f70-146">Concatenates two strings</span></span>|  
|+|<span data-ttu-id="f5f70-147">Объединяет две строки</span><span class="sxs-lookup"><span data-stu-id="f5f70-147">Concatenates two strings</span></span>|  
  
### <a name="logical-and-bitwise"></a><span data-ttu-id="f5f70-148">Логические и битовые</span><span class="sxs-lookup"><span data-stu-id="f5f70-148">Logical and Bitwise</span></span>  
 <span data-ttu-id="f5f70-149">Логические и битовые операторы выполняют логические действия над двумя целочисленными элементами выражения.</span><span class="sxs-lookup"><span data-stu-id="f5f70-149">Logical and bitwise operators perform logical manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="f5f70-150">Оператор</span><span class="sxs-lookup"><span data-stu-id="f5f70-150">Operator</span></span>|<span data-ttu-id="f5f70-151">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f70-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f5f70-152">And</span><span class="sxs-lookup"><span data-stu-id="f5f70-152">And</span></span>|<span data-ttu-id="f5f70-153">Выполняет логическое умножение двух выражений типа Boolean или побитовое логическое умножение двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="f5f70-153">Performs a logical conjunction on two Boolean expressions, or bitwise conjunction on two numeric expressions.</span></span>|  
|<span data-ttu-id="f5f70-154">Not</span><span class="sxs-lookup"><span data-stu-id="f5f70-154">Not</span></span>|<span data-ttu-id="f5f70-155">Выполняет логическое отрицание в выражении типа Boolean или побитовое отрицание в числовом выражении.</span><span class="sxs-lookup"><span data-stu-id="f5f70-155">Performs logical negation on a Boolean expression, or bitwise negation on a numeric expression.</span></span>|  
|<span data-ttu-id="f5f70-156">либо</span><span class="sxs-lookup"><span data-stu-id="f5f70-156">Or</span></span>|<span data-ttu-id="f5f70-157">Выполняет логическое сложение двух выражений типа Boolean или побитовое логическое сложение двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="f5f70-157">Performs a logical disjunction on two Boolean expressions, or bitwise disjunction on two numeric values.</span></span>|  
|<span data-ttu-id="f5f70-158">Xor</span><span class="sxs-lookup"><span data-stu-id="f5f70-158">Xor</span></span>|<span data-ttu-id="f5f70-159">Выполняет операцию логического сложения по модулю двух логических выражений или побитового логического сложения по модулю двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="f5f70-159">Performs a logical exclusion operation on two Boolean expressions, or a bitwise exclusion on two numeric expressions.</span></span>|  
|<span data-ttu-id="f5f70-160">AndAlso</span><span class="sxs-lookup"><span data-stu-id="f5f70-160">AndAlso</span></span>|<span data-ttu-id="f5f70-161">Выполняет логическое умножение двух выражений.</span><span class="sxs-lookup"><span data-stu-id="f5f70-161">Performs logical conjunction on two expressions.</span></span>|  
|<span data-ttu-id="f5f70-162">OrElse</span><span class="sxs-lookup"><span data-stu-id="f5f70-162">OrElse</span></span>|<span data-ttu-id="f5f70-163">Выполняет логическое деление двух выражений.</span><span class="sxs-lookup"><span data-stu-id="f5f70-163">Performs logical disjunction on two expressions.</span></span>|  
  
### <a name="bit-shift"></a><span data-ttu-id="f5f70-164">Сдвиг битов</span><span class="sxs-lookup"><span data-stu-id="f5f70-164">Bit Shift</span></span>  
 <span data-ttu-id="f5f70-165">Логические и битовые операторы выполняют битовую обработку двух целочисленных элементов выражения.</span><span class="sxs-lookup"><span data-stu-id="f5f70-165">Bitwise operators perform bit manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="f5f70-166">Оператор</span><span class="sxs-lookup"><span data-stu-id="f5f70-166">Operator</span></span>|<span data-ttu-id="f5f70-167">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f70-167">Description</span></span>|  
|--------------|-----------------|  
|<\<|<span data-ttu-id="f5f70-168">Выполняет арифметический сдвиг битового шаблона влево.</span><span class="sxs-lookup"><span data-stu-id="f5f70-168">Performs an arithmetic left-shift on a bit pattern.</span></span>|  
|>>|<span data-ttu-id="f5f70-169">Выполняет арифметический сдвиг битового шаблона вправо.</span><span class="sxs-lookup"><span data-stu-id="f5f70-169">Performs an arithmetic right-shift on a bit pattern.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5f70-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5f70-170">See Also</span></span>  
 <span data-ttu-id="f5f70-171">[Диалоговое окно «Выражение»](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="f5f70-171">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="f5f70-172">[Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f5f70-172">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f5f70-173">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f5f70-173">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f5f70-174">[Типы данных в выражениях (построитель отчетов и службы SSRS)](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f5f70-174">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f5f70-175">Диалоговое окно "Выражение" (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="f5f70-175">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
