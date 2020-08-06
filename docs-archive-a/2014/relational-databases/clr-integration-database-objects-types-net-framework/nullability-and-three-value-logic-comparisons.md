---
title: Допустимость значений NULL и сравнение логики с тремя значениями | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- precision [CLR integration]
- overflow detections [CLR integration]
- null values [CLR integration]
- three-value logic comparisons [CLR integration]
- data types [CLR integration]
- SqlBoolean data type
ms.assetid: 13da4c7f-1010-4b2d-a63c-c69b6bfd96f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b8000c1c28d5a1d3d129b6e8d01c4ab2fbbbc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751171"
---
# <a name="nullability-and-three-value-logic-comparisons"></a><span data-ttu-id="4f4d3-102">Допустимость значений NULL и трехзначная логика сравнения</span><span class="sxs-lookup"><span data-stu-id="4f4d3-102">Nullability and Three-Value Logic Comparisons</span></span>
  <span data-ttu-id="4f4d3-103">Знакомые с типами данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пользователи найдут сходную семантику и точность в пространстве имен `System.Data.SqlTypes` платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f4d3-103">If you are familiar with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, you will find similar semantics and precision in the `System.Data.SqlTypes` namespace in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="4f4d3-104">Однако существуют определенные различия. В этом разделе описаны самые важные из них.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-104">There are some differences, however, and this topic covers the most important of these differences.</span></span>  
  
## <a name="null-values"></a><span data-ttu-id="4f4d3-105">Значения NULL</span><span class="sxs-lookup"><span data-stu-id="4f4d3-105">NULL Values</span></span>  
 <span data-ttu-id="4f4d3-106">Главное различие между типами данных среды CLR и типами данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заключается в том, что первые не допускают значений NULL, а вторые реализуют полную семантику NULL.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-106">A primary difference between native common language runtime (CLR) data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types is that the former do not allow for NULL values, while the latter provide full NULL semantics.</span></span>  
  
 <span data-ttu-id="4f4d3-107">Значения NULL влияют на результаты сравнений.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-107">Comparisons are affected by NULL values.</span></span> <span data-ttu-id="4f4d3-108">При сравнении двух значений x и y, если x или y имеет значение NULL, то результатом некоторых логических сравнений будет значение UNKNOWN, а не TRUE или FALSE.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-108">When comparing two values x and y, if either x or y is NULL, then some logical comparisons evaluate to an UNKNOWN value rather than true or false.</span></span>  
  
## <a name="sqlboolean-data-type"></a><span data-ttu-id="4f4d3-109">Тип данных SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="4f4d3-109">SqlBoolean Data Type</span></span>  
 <span data-ttu-id="4f4d3-110">Пространство имен `System.Data.SqlTypes` вводит тип `SqlBoolean` для представления трехзначной логики.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-110">The `System.Data.SqlTypes` namespace introduces a `SqlBoolean` type to represent this 3-value logic.</span></span> <span data-ttu-id="4f4d3-111">Сравнения каких-либо `SqlTypes` возвращают значения типа `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-111">Comparisons between any `SqlTypes` return a `SqlBoolean` value type.</span></span> <span data-ttu-id="4f4d3-112">Значение UNKNOWN представлено значением NULL типа `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-112">The UNKNOWN value is represented by the null value of the `SqlBoolean` type.</span></span> <span data-ttu-id="4f4d3-113">Свойства `IsTrue`, `IsFalse` и `IsNull` обеспечивают возможность проверки значения типа `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-113">The properties `IsTrue`, `IsFalse`, and `IsNull` are provided to check the value of a `SqlBoolean` type.</span></span>  
  
## <a name="operations-functions-and-null-values"></a><span data-ttu-id="4f4d3-114">Операции, функции и значения NULL</span><span class="sxs-lookup"><span data-stu-id="4f4d3-114">Operations, Functions, and NULL Values</span></span>  
 <span data-ttu-id="4f4d3-115">Все арифметические операторы (+,-, \* ,/,%), битовые операторы (~, & и |) и большинство функций возвращают значение null, если любой из операндов или аргументов имеет `SqlTypes` значение null.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-115">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, and |), and most functions return NULL if any of the operands or arguments of `SqlTypes` are NULL.</span></span> <span data-ttu-id="4f4d3-116">Свойство `IsNull` всегда возвращает значение TRUE или FALSE.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-116">The `IsNull` property always returns a true or false value.</span></span>  
  
## <a name="precision"></a><span data-ttu-id="4f4d3-117">Точность</span><span class="sxs-lookup"><span data-stu-id="4f4d3-117">Precision</span></span>  
 <span data-ttu-id="4f4d3-118">Максимальные значения типов данных decimal в среде CLR платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] отличаются от максимальных значений числовых типов и типов decimal в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f4d3-118">Decimal data types in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR have different maximum values than those of the numeric and decimal data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4f4d3-119">Кроме того, типы данных decimal в среде CLR платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] предполагают использование максимальной точности.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-119">In addition, in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR decimal data types assume the maximum precision.</span></span> <span data-ttu-id="4f4d3-120">Однако в среде CLR для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] тип `SqlDecimal` обеспечивает такую же максимальную точность и масштаб, а также такую же семантику, как и у типа данных decimal в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f4d3-120">In the CLR for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], however, `SqlDecimal` provides the same maximum precision and scale, and the same semantics as the decimal data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="overflow-detection"></a><span data-ttu-id="4f4d3-121">Обнаружение переполнений</span><span class="sxs-lookup"><span data-stu-id="4f4d3-121">Overflow Detection</span></span>  
 <span data-ttu-id="4f4d3-122">В среде CLR платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] сложение двух очень больших чисел не может вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-122">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, the addition of two very large numbers may not throw an exception.</span></span> <span data-ttu-id="4f4d3-123">При этом если не использовался оператор проверки, возвращенный результат может «обернуться по кругу» и превратиться в отрицательное целое число.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-123">Instead, if no check operator has been used, the returned result may "wrap around" as a negative integer.</span></span> <span data-ttu-id="4f4d3-124">В `System.Data.SqlTypes` исключения возникают для всех ошибок переполнения и потери точности, а также для ошибок деления на ноль.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-124">In `System.Data.SqlTypes`, exceptions are thrown for all overflow and underflow errors, and divide-by-zero errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f4d3-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f4d3-125">See Also</span></span>  
 [<span data-ttu-id="4f4d3-126">Типы данных SQL Server в платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4f4d3-126">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
