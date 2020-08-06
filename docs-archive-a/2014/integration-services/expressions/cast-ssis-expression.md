---
title: Приведение (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CAST function
- cast operator
- converting data types [Integration Services]
- data types [Integration Services], expressions
- data types [Integration Services], converting
ms.assetid: d4e915cc-1c7b-4b2e-93b0-13a8b0cb9242
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65d60eca4340b65b8a82855c3f2b29a6cda56e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736665"
---
# <a name="cast-ssis-expression"></a><span data-ttu-id="0dd60-102">Приведение (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="0dd60-102">Cast (SSIS Expression)</span></span>
  <span data-ttu-id="0dd60-103">Явно приводит выражение одного типа данных к другому типу.</span><span class="sxs-lookup"><span data-stu-id="0dd60-103">Explicitly converts an expression from one data type to a different data type.</span></span> <span data-ttu-id="0dd60-104">Оператор приведения может также выполнять функцию оператора усечения.</span><span class="sxs-lookup"><span data-stu-id="0dd60-104">The cast operator can also function as a truncation operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="0dd60-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0dd60-105">Syntax</span></span>

```

(type_spec) expression

```

## <a name="arguments"></a><span data-ttu-id="0dd60-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0dd60-106">Arguments</span></span>
 <span data-ttu-id="0dd60-107">*type_spec* Является допустимым [!INCLUDE[ssIS](../../includes/ssis-md.md)] типом данных.</span><span class="sxs-lookup"><span data-stu-id="0dd60-107">*type_spec* Is a valid [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span>

 <span data-ttu-id="0dd60-108">*выражение* Является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="0dd60-108">*expression* Is a valid expression.</span></span>

## <a name="result-types"></a><span data-ttu-id="0dd60-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="0dd60-109">Result Types</span></span>
 <span data-ttu-id="0dd60-110">Тип данных *type_spec*.</span><span class="sxs-lookup"><span data-stu-id="0dd60-110">The data type of *type_spec*.</span></span> <span data-ttu-id="0dd60-111">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0dd60-111">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="0dd60-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="0dd60-112">Remarks</span></span>
 <span data-ttu-id="0dd60-113">На следующей диаграмме перечислены допустимые операторы приведения.</span><span class="sxs-lookup"><span data-stu-id="0dd60-113">The following diagram shows legal cast operations.</span></span>

 <span data-ttu-id="0dd60-114">![Допустимые и недопустимые приведения между типами данных](../media/data-conversion.gif "Допустимые и недопустимые приведения между типами данных")</span><span class="sxs-lookup"><span data-stu-id="0dd60-114">![Legal and not legal casts between data types](../media/data-conversion.gif "Legal and not legal casts between data types")</span></span>

 <span data-ttu-id="0dd60-115">Для приведения к некоторым типам данных необходимо задавать определенные параметры.</span><span class="sxs-lookup"><span data-stu-id="0dd60-115">Casting to some data types requires parameters.</span></span> <span data-ttu-id="0dd60-116">В следующей таблице приведены эти типы данных и их параметры.</span><span class="sxs-lookup"><span data-stu-id="0dd60-116">The following table lists these data types and their parameters.</span></span>

|<span data-ttu-id="0dd60-117">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0dd60-117">Data type</span></span>|<span data-ttu-id="0dd60-118">Параметр</span><span class="sxs-lookup"><span data-stu-id="0dd60-118">Parameter</span></span>|<span data-ttu-id="0dd60-119">Пример</span><span class="sxs-lookup"><span data-stu-id="0dd60-119">Example</span></span>|
|---------------|---------------|-------------|
|<span data-ttu-id="0dd60-120">DT_STR</span><span class="sxs-lookup"><span data-stu-id="0dd60-120">DT_STR</span></span>|<span data-ttu-id="0dd60-121">*параметра charCount*</span><span class="sxs-lookup"><span data-stu-id="0dd60-121">*charcount*</span></span><br /><br /> <span data-ttu-id="0dd60-122">*страница*</span><span class="sxs-lookup"><span data-stu-id="0dd60-122">*codepage*</span></span>|<span data-ttu-id="0dd60-123">Команда (DT_STR,30,1252) приводит 30 байт (или 30 символов) к значению типа DT_STR, используя кодовую страницу 1252.</span><span class="sxs-lookup"><span data-stu-id="0dd60-123">(DT_STR,30,1252) casts 30 bytes, or 30 single characters, to the DT_STR data type using the 1252 code page.</span></span>|
|<span data-ttu-id="0dd60-124">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="0dd60-124">DT_WSTR</span></span>|<span data-ttu-id="0dd60-125">*Параметра charCount*</span><span class="sxs-lookup"><span data-stu-id="0dd60-125">*Charcount*</span></span>|<span data-ttu-id="0dd60-126">Команда (DT_WSTR,20) приводит 20 пар байт (или символов в формате Юникод) к значению типа DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="0dd60-126">(DT_WSTR,20) casts 20 byte pairs, or 20 Unicode characters, to the DT_WSTR data type.</span></span>|
|<span data-ttu-id="0dd60-127">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="0dd60-127">DT_BYTES</span></span>|<span data-ttu-id="0dd60-128">*ByteCount*</span><span class="sxs-lookup"><span data-stu-id="0dd60-128">*Bytecount*</span></span>|<span data-ttu-id="0dd60-129">(DT_BYTES,50) приводит 50 байт к типу данных DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="0dd60-129">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|
|<span data-ttu-id="0dd60-130">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="0dd60-130">DT_DECIMAL</span></span>|<span data-ttu-id="0dd60-131">*Масштаб*</span><span class="sxs-lookup"><span data-stu-id="0dd60-131">*Scale*</span></span>|<span data-ttu-id="0dd60-132">(DT_DECIMAL,2) приводит числовое значение к типу данных DT_DECIMAL, используя масштаб 2.</span><span class="sxs-lookup"><span data-stu-id="0dd60-132">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|
|<span data-ttu-id="0dd60-133">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="0dd60-133">DT_NUMERIC</span></span>|<span data-ttu-id="0dd60-134">*Точность*</span><span class="sxs-lookup"><span data-stu-id="0dd60-134">*Precision*</span></span><br /><br /> <span data-ttu-id="0dd60-135">*Масштаб*</span><span class="sxs-lookup"><span data-stu-id="0dd60-135">*Scale*</span></span>|<span data-ttu-id="0dd60-136">(DT_NUMERIC,10,3) приводит числовое значение к типу данных DT_NUMERIC, используя точность 10 и масштаб 3.</span><span class="sxs-lookup"><span data-stu-id="0dd60-136">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|
|<span data-ttu-id="0dd60-137">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="0dd60-137">DT_TEXT</span></span>|<span data-ttu-id="0dd60-138">*Страница*</span><span class="sxs-lookup"><span data-stu-id="0dd60-138">*Codepage*</span></span>|<span data-ttu-id="0dd60-139">(DT_TEXT,1252) приводит значение к типу данных DT_TEXT, используя кодовую страницу 1252.</span><span class="sxs-lookup"><span data-stu-id="0dd60-139">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|

 <span data-ttu-id="0dd60-140">При приведении строки к значению типа DT_DATE (или обратно) используется локаль преобразования.</span><span class="sxs-lookup"><span data-stu-id="0dd60-140">When a string is cast to a DT_DATE, or vice versa, the locale of the transformation is used.</span></span> <span data-ttu-id="0dd60-141">Однако дата задается в формате ISO (ГГГГ-ММ-ДД) вне зависимости от того, используется ли в локали формат ISO.</span><span class="sxs-lookup"><span data-stu-id="0dd60-141">However, the date is in the ISO format of YYYY-MM-DD, regardless of whether the locale preference uses the ISO format.</span></span>

> [!NOTE]
>  <span data-ttu-id="0dd60-142">Инструкции по преобразованию строк в тип даты, отличный от DT_DATE, см. в разделе [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0dd60-142">To convert a string to a date data type other than DT_DATE, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="0dd60-143">Если кодовая страница является многобайтовой, число байт и символов может не совпадать.</span><span class="sxs-lookup"><span data-stu-id="0dd60-143">If the code page is a multibyte character code page, the number of bytes and characters may differ.</span></span> <span data-ttu-id="0dd60-144">При приведении преобразования данных типа DT_WSTR к данным типа DT_STR с одинаковым значением параметра *charcount* может произойти усечение символов в результирующей строке.</span><span class="sxs-lookup"><span data-stu-id="0dd60-144">Casting from a DT_WSTR to a DT_STR with the same *charcount* value may cause truncation of the final characters in the converted string.</span></span> <span data-ttu-id="0dd60-145">При наличии соответствующего места в столбце целевой таблицы присвойте параметру *charcount* значение, равное числу байт, требующихся для многобайтовой кодовой страницы.</span><span class="sxs-lookup"><span data-stu-id="0dd60-145">If sufficient storage is available in the column of the destination table, set the value of the *charcount* parameter to reflect the number of bytes that the multibyte code page requires.</span></span> <span data-ttu-id="0dd60-146">Например, при приведении символьных данных к формату DT_STR с использованием кодовой страницы 936 необходимо задать значение параметра *charcount* в два раза большее, чем количество символов в исходных данных. При преобразовании символьных данных с использованием кодовой страницы UTF-8 необходимо задать значение параметра *charcount* в четыре раза большее.</span><span class="sxs-lookup"><span data-stu-id="0dd60-146">For example, if you cast character data to a DT_STR data type using the 936 code page, you should set *charcount* to a value up to two times greater than the number of characters that you expect the data to contain; if you cast character data using the UTF-8 code page, you should set *charcount* to a value up to four times greater.</span></span>

 <span data-ttu-id="0dd60-147">Дополнительные сведения о структуре типов данных «date» см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0dd60-147">For more information about the structure of date data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="ssis-expression-examples"></a><span data-ttu-id="0dd60-148">Примеры выражений служб SSIS</span><span class="sxs-lookup"><span data-stu-id="0dd60-148">SSIS Expression Examples</span></span>
 <span data-ttu-id="0dd60-149">В данном примере числовое значение приводится к целому.</span><span class="sxs-lookup"><span data-stu-id="0dd60-149">This example casts a numeric value to an integer.</span></span>

```
(DT_I4) 3.57
```

 <span data-ttu-id="0dd60-150">В данном примере целое число приводится в символьную строку, используя кодовую страницу 1252.</span><span class="sxs-lookup"><span data-stu-id="0dd60-150">This example casts an integer to a character string using the 1252 code page.</span></span>

```
(DT_STR,1,1252)5
```

 <span data-ttu-id="0dd60-151">В данном примере строка, состоящая из трех символов, преобразуется в двухбайтовые символы.</span><span class="sxs-lookup"><span data-stu-id="0dd60-151">This example casts a three-character string to double-byte characters.</span></span>

```
(DT_WSTR,3)"Cat"
```

 <span data-ttu-id="0dd60-152">В данном примере целое число преобразуется в десятичное с масштабом 2.</span><span class="sxs-lookup"><span data-stu-id="0dd60-152">This example casts an integer to a decimal with a scale of two.</span></span>

```
(DT_DECIMAl,2)500
```

 <span data-ttu-id="0dd60-153">В данном примере целое число преобразуется в число с точностью 7 и масштабом 3.</span><span class="sxs-lookup"><span data-stu-id="0dd60-153">This example casts an integer to a numeric with a precision of seven and scale of three.</span></span>

```
(DT_NUMERIC,7,3)4000
```

 <span data-ttu-id="0dd60-154">В данном примере значения столбца **FirstName** преобразуются из формата **nvarchar** длиной 50 в символьную строку, используя кодовую страницу 1252.</span><span class="sxs-lookup"><span data-stu-id="0dd60-154">This example casts values in the **FirstName** column, defined with an **nvarchar** data type and a length of 50, to a character string using the 1252 code page.</span></span>

```
(DT_STR,50,1252)FirstName
```

 <span data-ttu-id="0dd60-155">В этом примере значения в столбце **DateFirstPurchase** типа DT_DBDATE приводятся к строке в Юникоде длиной 20 символов.</span><span class="sxs-lookup"><span data-stu-id="0dd60-155">This example casts values in the **DateFirstPurchase** column of type DT_DBDATE, to a Unicode character string with a length of 20.</span></span>

```
(DT_WSTR,20)DateFirstPurchase
```

 <span data-ttu-id="0dd60-156">В данном примере строковый литерал «True» преобразуется в логическое значение.</span><span class="sxs-lookup"><span data-stu-id="0dd60-156">This example casts the string literal "True" to a Boolean.</span></span>

```
(DT_BOOL)"True"
```

 <span data-ttu-id="0dd60-157">В данном примере строковый литерал приводится к типу DT_DBDATE.</span><span class="sxs-lookup"><span data-stu-id="0dd60-157">This example casts a string literal to DT_DBDATE.</span></span>

```
(DT_DBDATE) "1999-10-11"
```

 <span data-ttu-id="0dd60-158">В данном примере строковый литерал приводится к типу данных DT_DBTIME2 с 5 цифрами для представления долей секунды.</span><span class="sxs-lookup"><span data-stu-id="0dd60-158">This example casts a string literal to the DT_DBTIME2 data type that uses 5 digits for fractional seconds.</span></span> <span data-ttu-id="0dd60-159">(Тип данных DT_DBTIME2 допускает использование от 0 до 7 цифр, выделенных на представление долей секунд).</span><span class="sxs-lookup"><span data-stu-id="0dd60-159">(The DT_DBTIME2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIME2, 5) "16:34:52.12345"
```

 <span data-ttu-id="0dd60-160">В данном примере строковый литерал приводится к типу данных DT_DBTIMESTAMP2 с 4 цифрами для представления долей секунды.</span><span class="sxs-lookup"><span data-stu-id="0dd60-160">This example casts a string literal to the DT_DBTIMESTAMP2 data type that uses 4 digits for fractional seconds.</span></span> <span data-ttu-id="0dd60-161">(Тип данных DT_DBTIMESTAMP2 допускает использование от 0 до 7 цифр, выделенных на представление долей секунд).</span><span class="sxs-lookup"><span data-stu-id="0dd60-161">(The DT_DBTIMESTAMP2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMP2, 4) "1999-10-11 16:34:52.1234"
```

 <span data-ttu-id="0dd60-162">В данном примере строковый литерал приводится к типу данных DT_DBTIMESTAMPOFFSET с 7 цифрами для представления долей секунды.</span><span class="sxs-lookup"><span data-stu-id="0dd60-162">This example casts a string literal to the DT_DBTIMESTAMPOFFSET data type that uses 7 digits for fractional seconds.</span></span> <span data-ttu-id="0dd60-163">(Тип данных DT_DBTIMESTAMPOFFSET допускает использование от 0 до 7 цифр, выделенных на представление долей секунд).</span><span class="sxs-lookup"><span data-stu-id="0dd60-163">(The DT_DBTIMESTAMPOFFSET data typecan have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMPOFFSET, 7) "1999-10-11 16:34:52.1234567 + 5:35"
```

## <a name="see-also"></a><span data-ttu-id="0dd60-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="0dd60-164">See Also</span></span>
 <span data-ttu-id="0dd60-165">Операторы [очередности и ассоциативности](operator-precedence-and-associativity.md) операторов [&#40;выражение служб ssis&#41;](operators-ssis-expression.md) [Integration Services &#40;SSIS&#41; выражения](integration-services-ssis-expressions.md) [Integration Services типы данных в выражениях](integration-services-data-types-in-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="0dd60-165">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md)</span></span>


