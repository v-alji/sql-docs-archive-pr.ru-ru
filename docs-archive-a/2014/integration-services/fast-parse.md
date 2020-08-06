---
title: Быстрый синтаксический анализ | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- fast parse [Integration Services]
ms.assetid: 6688707d-3c5b-404e-aa2f-e13092ac8d95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 343b8b8b74338512dbf29b3d2efd436df1ffa8ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735477"
---
# <a name="fast-parse"></a><span data-ttu-id="380e0-102">Fast Parse</span><span class="sxs-lookup"><span data-stu-id="380e0-102">Fast Parse</span></span>
  <span data-ttu-id="380e0-103">Быстрый синтаксический анализ обеспечивает быстрый и простой набор процессов для анализа данных.</span><span class="sxs-lookup"><span data-stu-id="380e0-103">Fast parse provides a fast, simple set of routines for parsing data.</span></span> <span data-ttu-id="380e0-104">Эти процедуры не учитывают локали и поддерживают только подмножество форматов дат, времени и целых чисел.</span><span class="sxs-lookup"><span data-stu-id="380e0-104">These routines are not locale-sensitive and they support only a subset of date, time, and integer formats.</span></span>  
  
## <a name="requirements-and-limitations"></a><span data-ttu-id="380e0-105">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="380e0-105">Requirements and Limitations</span></span>  
 <span data-ttu-id="380e0-106">Выполняя быстрый синтаксический анализ, пакет теряет способность интерпретировать дату, время и числовые данные с учетом локали, а также многие часто используемые базовые и расширенные форматы ISO 8601, но производительность пакета увеличивается.</span><span class="sxs-lookup"><span data-stu-id="380e0-106">By implementing fast parse, a package forfeits its ability to interpret date, time, and numeric data in locale-specific formats and many frequently used ISO 8601 basic and extended formats, but the package enhances its performance.</span></span> <span data-ttu-id="380e0-107">Например, быстрый синтаксический анализ поддерживает только наиболее общеупотребительные представления формата даты, такие как ГГГГММДД и ГГГГ-ММ-ДД, он не выполняет анализ, зависящий от локалей, не распознает специальные символы в валютных данных и не преобразует шестнадцатеричное или экспоненциальное представление целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="380e0-107">For example, fast parse supports only the most commonly used date format representations such as YYYYMMDD and YYYY-MM-DD, does not perform locale-specific parsing, does not recognize special characters in currency data, and cannot convert hexadecimal or scientific representation of integers.</span></span>  
  
 <span data-ttu-id="380e0-108">Быстрый синтаксический анализ доступен только при использовании источника неструктурированных файлов или преобразования «Преобразование данных».</span><span class="sxs-lookup"><span data-stu-id="380e0-108">Fast parse is available only when you use the Flat File source or the Data Conversion transformation.</span></span> <span data-ttu-id="380e0-109">Увеличение производительности может иметь значение, поэтому, если возможно, нужно принять во внимание использование быстрого синтаксического анализа в этих компонентах потока данных.</span><span class="sxs-lookup"><span data-stu-id="380e0-109">The increase in performance can be significant, and you should consider using fast parse in these data flow components if you can.</span></span>  
  
 <span data-ttu-id="380e0-110">Если поток данных в пакете запрашивает синтаксический анализ, чувствительный к локалю, то вместо быстрого синтаксического анализа рекомендуется использовать стандартный анализ.</span><span class="sxs-lookup"><span data-stu-id="380e0-110">If the data flow in the package requires locale-sensitive parsing, standard parse is recommended instead of fast parse.</span></span> <span data-ttu-id="380e0-111">Например, быстрый анализ не распознает данные, зависящие от локаля, что включает десятичные символы, такие как запятая, форматы даты (помимо форматов типа год-месяц-день) и символы валют.</span><span class="sxs-lookup"><span data-stu-id="380e0-111">For example, fast parse does not recognize locale-sensitive data that includes decimal symbols such as the comma, date formats other than year-month-date formats, and currency symbols.</span></span>  
  
 <span data-ttu-id="380e0-112">Усеченные представления, которые неявно подразумевают одну или более частей даты, такие как век, год или месяц, не распознаются быстрым синтаксическим анализом.</span><span class="sxs-lookup"><span data-stu-id="380e0-112">Truncated representations that imply one or more date parts, such as a century, a year, or a month, are not recognized by fast parse.</span></span> <span data-ttu-id="380e0-113">Например, быстрый анализ не распознает ни формат "**-ГГММ**", который указывает год и месяц подразумеваемого века, ни формат "**--MM**", который указывает месяц подразумеваемого года.</span><span class="sxs-lookup"><span data-stu-id="380e0-113">For example, fast parse recognizes neither the '**-YYMM**' format, which specifies a year and month in an implied century, nor '**--MM**', which specifies a month in an implied year.</span></span> <span data-ttu-id="380e0-114">Однако распознаются некоторые представления с невысокой точностью.</span><span class="sxs-lookup"><span data-stu-id="380e0-114">However, some representations with reduced precision are recognized.</span></span> <span data-ttu-id="380e0-115">Например, быстрый анализ распознает формат «ччмм;», который указывает только часы и минуты, и формат «**ГГГГ**», который указывает только год.</span><span class="sxs-lookup"><span data-stu-id="380e0-115">For example, fast parse recognizes the 'hhmm;' format, which indicates hour and minute only, and '**YYYY**', which indicates year only.</span></span>  
  
 <span data-ttu-id="380e0-116">Быстрый анализ указывается на уровне столбцов.</span><span class="sxs-lookup"><span data-stu-id="380e0-116">Fast parse is specified at the column level.</span></span> <span data-ttu-id="380e0-117">В источнике неструктурированных файлов и преобразовании «Преобразование данных» можно указать быстрый анализ в выходных столбцах.</span><span class="sxs-lookup"><span data-stu-id="380e0-117">In the Flat File source and the Data Conversion transformation, you can specify Fast parse on output columns.</span></span> <span data-ttu-id="380e0-118">Вход и выход может содержать как чувствительные к локалю, так и нечувствительные к локалю столбцы.</span><span class="sxs-lookup"><span data-stu-id="380e0-118">Inputs and outputs can include both locale-sensitive and locale-insensitive columns.</span></span>  
  
 <span data-ttu-id="380e0-119">Дополнительные сведения о форматах данных, поддерживаемых быстрым синтаксическим разбором, см. в разделах [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) и [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="380e0-119">For more information about the data formats that Fast parse supports, see [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) and [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="380e0-120">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="380e0-120">Related Tasks</span></span>  
 [<span data-ttu-id="380e0-121">Установка быстрого анализа</span><span class="sxs-lookup"><span data-stu-id="380e0-121">Set Fast Parse</span></span>](../../2014/integration-services/set-fast-parse.md)  
  
  
