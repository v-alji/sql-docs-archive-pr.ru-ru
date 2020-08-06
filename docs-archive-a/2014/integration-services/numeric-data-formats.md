---
title: Форматы числовых данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- integer data types [Integration Services]
- numeric data formats for fast parse
- locale-sensitive parsing [Integration Services]
- fast parse [Integration Services]
ms.assetid: fa3975ce-9d21-408a-857d-f85e30af27b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc54a331c3762e31ba9d9a431aaca7eda6374d8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664310"
---
# <a name="numeric-data-formats"></a><span data-ttu-id="1fb5d-102">Форматы числовых данных</span><span class="sxs-lookup"><span data-stu-id="1fb5d-102">Numeric Data Formats</span></span>
  <span data-ttu-id="1fb5d-103">Быстрый синтаксический анализ предоставляет набор простых, не зависящих от локалей процедур синтаксического анализа данных.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-103">Fast parse provides a fast, simple, locale-insensitive set of routines for parsing data.</span></span> <span data-ttu-id="1fb5d-104">Он поддерживает только ограниченный набор форматов числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-104">Fast parse supports only a limited set of formats for integer data types.</span></span>  
  
## <a name="integer-data-types"></a><span data-ttu-id="1fb5d-105">Целочисленные типы данных</span><span class="sxs-lookup"><span data-stu-id="1fb5d-105">Integer Data Types</span></span>  
 <span data-ttu-id="1fb5d-106">Службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] предоставляют следующие целочисленные типы данных: DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8 и DT_UI8.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-106">The integer data types that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides are DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8, and DT_UI8.</span></span> <span data-ttu-id="1fb5d-107">Дополнительные сведения см. в разделе [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1fb5d-107">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="1fb5d-108">Быстрый синтаксический анализ поддерживает следующие форматы целочисленных типов данных:</span><span class="sxs-lookup"><span data-stu-id="1fb5d-108">Fast parse supports the following formats for integer data types:</span></span>  
  
-   <span data-ttu-id="1fb5d-109">Ноль или более начальных и конечных пробелов или остановок табулятора.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-109">Zero or more leading and trailing spaces or tab stops.</span></span> <span data-ttu-id="1fb5d-110">Например, допустимым является значение «  123  ».</span><span class="sxs-lookup"><span data-stu-id="1fb5d-110">For example, the value "  123  " is valid.</span></span> <span data-ttu-id="1fb5d-111">в котором все пробелы считаются нулями.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-111">A value that is all spaces evaluates to zero.</span></span>  
  
-   <span data-ttu-id="1fb5d-112">Начальный знак плюс, минус или без знака.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-112">A leading plus sign, minus sign, or neither.</span></span> <span data-ttu-id="1fb5d-113">Например, допустимыми являются значения +123, -123 и 123.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-113">For example, the values +123, -123, and 123 are valid.</span></span>  
  
-   <span data-ttu-id="1fb5d-114">Одна или более арабских цифр (0-9).</span><span class="sxs-lookup"><span data-stu-id="1fb5d-114">One or more Hindu-Arabic numerals (0-9).</span></span> <span data-ttu-id="1fb5d-115">Например, допустимым является значение 345.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-115">For example, the value 345 is valid.</span></span> <span data-ttu-id="1fb5d-116">Цифры других языков не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-116">Other language numerals are not supported.</span></span>  
  
 <span data-ttu-id="1fb5d-117">Не поддерживаются следующие форматы данных:</span><span class="sxs-lookup"><span data-stu-id="1fb5d-117">Non-supported data formats include the following:</span></span>  
  
-   <span data-ttu-id="1fb5d-118">Специальные символы.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-118">Special characters.</span></span> <span data-ttu-id="1fb5d-119">К примеру, денежный символ $ не поддерживается, т.е. синтаксический анализ значения $20 невозможен.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-119">For example, the currency character $ is not supported, and the value $20 cannot be parsed.</span></span>  
  
-   <span data-ttu-id="1fb5d-120">Такие символы пустого пространства, как перевод строки, возврат каретки и неразрывный пробел.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-120">White-space characters such as line feed, carriage returns, and non-breaking spaces.</span></span> <span data-ttu-id="1fb5d-121">Например, синтаксический анализ значения « 123» невозможен.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-121">For example, the value " 123" cannot be parsed.</span></span>  
  
-   <span data-ttu-id="1fb5d-122">Шестнадцатеричное представление целых чисел.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-122">Hexadecimal representations of integers.</span></span> <span data-ttu-id="1fb5d-123">Например, синтаксический анализ значения 2EE невозможен.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-123">For example, the value 2EE cannot be parsed.</span></span>  
  
-   <span data-ttu-id="1fb5d-124">Экспоненциальное представление целых чисел.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-124">Scientific notation representation of integers.</span></span> <span data-ttu-id="1fb5d-125">Например, синтаксический анализ значения 1E+10 невозможен.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-125">For example, the value 1E+10 cannot be parsed.</span></span>  
  
 <span data-ttu-id="1fb5d-126">Для целых чисел используются следующие форматы выходных данных:</span><span class="sxs-lookup"><span data-stu-id="1fb5d-126">The following formats are output data formats for integers:</span></span>  
  
-   <span data-ttu-id="1fb5d-127">Знак минус для отрицательных чисел и отсутствие знака для положительных.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-127">A minus sign for negative numbers and nothing for positive ones.</span></span>  
  
-   <span data-ttu-id="1fb5d-128">Без пробелов.</span><span class="sxs-lookup"><span data-stu-id="1fb5d-128">No white spaces.</span></span>  
  
-   <span data-ttu-id="1fb5d-129">Одна или более арабских цифр (0-9).</span><span class="sxs-lookup"><span data-stu-id="1fb5d-129">One or more Hindu-Arabic numerals (0-9).</span></span>  
  
  
