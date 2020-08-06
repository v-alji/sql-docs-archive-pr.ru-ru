---
title: Divide (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- / (divide)
- divide operator (/)
ms.assetid: 5bde9223-872d-443e-8a27-57735e1d8f3d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4541cd4601047770d1bf361077b1c474219e8833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656475"
---
# <a name="divide-ssis-expression"></a><span data-ttu-id="63d62-102">Деление (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="63d62-102">Divide (SSIS Expression)</span></span>
  <span data-ttu-id="63d62-103">Делит первое числовое выражение на второе.</span><span class="sxs-lookup"><span data-stu-id="63d62-103">Divides the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d62-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63d62-104">Syntax</span></span>  
  
```  
  
dividend / divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="63d62-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="63d62-105">Arguments</span></span>  
 <span data-ttu-id="63d62-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="63d62-106">*dividend*</span></span>  
 <span data-ttu-id="63d62-107">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="63d62-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="63d62-108">*dividend* может быть любым допустимым числовым выражением.</span><span class="sxs-lookup"><span data-stu-id="63d62-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="63d62-109">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="63d62-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="63d62-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="63d62-110">*divisor*</span></span>  
 <span data-ttu-id="63d62-111">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="63d62-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="63d62-112">*divisor* может быть любым допустимым числовым выражением, отличным от нуля.</span><span class="sxs-lookup"><span data-stu-id="63d62-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="63d62-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="63d62-113">Result Types</span></span>  
 <span data-ttu-id="63d62-114">Определяются типами данных обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="63d62-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="63d62-115">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="63d62-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63d62-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="63d62-116">Remarks</span></span>  
 <span data-ttu-id="63d62-117">Если один из операндов равен NULL, то результатом является значение NULL.</span><span class="sxs-lookup"><span data-stu-id="63d62-117">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="63d62-118">Деление на ноль недопустимо.</span><span class="sxs-lookup"><span data-stu-id="63d62-118">Dividing by zero is not legal.</span></span> <span data-ttu-id="63d62-119">В зависимости от того, как вычисляется подвыражение *divisor* , возникает одна из следующих ошибок:</span><span class="sxs-lookup"><span data-stu-id="63d62-119">Depending on how the *divisor* subexpression is evaluated, one of following errors occurs:</span></span>  
  
-   <span data-ttu-id="63d62-120">Если подвыражение *divisor* , результатом которого является ноль, является константой, то ошибка появляется во время разработки, и в результате файл не проходит проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="63d62-120">If the *divisor* subexpression that evaluates to zero is a constant, the error appears at design time, causing the expression to fail validation.</span></span>  
  
-   <span data-ttu-id="63d62-121">Если подвыражение *divisor* , результатом которого является ноль, содержит переменные, но не содержит входных столбцов, то компонент, которому принадлежит выражение, прерывает предварительную проверку правильности, которая производится перед выполнением пакета.</span><span class="sxs-lookup"><span data-stu-id="63d62-121">If the *divisor* subexpression that evaluates to zero contains variables, but no input columns, the component to which the expression belongs fails the pre-execution validation that occurs before the package runs.</span></span>  
  
-   <span data-ttu-id="63d62-122">Если вложенное выражение *divisor* , результатом которого является ноль, содержит входные столбцы, то во время выполнения возникает ошибка, которая обрабатывается в соответствии с правилами потока ошибок компонента потока данных.</span><span class="sxs-lookup"><span data-stu-id="63d62-122">If the *divisor* subexpression that evaluates to zero contains input columns, the error appears at run time and is handled according to the error flow rules of the data flow component.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="63d62-123">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="63d62-123">Expression Examples</span></span>  
 <span data-ttu-id="63d62-124">Этот пример делит два числовых литерала.</span><span class="sxs-lookup"><span data-stu-id="63d62-124">This example divides two numeric literals.</span></span>  
  
```  
25 / 5  
```  
  
 <span data-ttu-id="63d62-125">Этот пример делит значения в столбце **ListPrice** на значения в столбце **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="63d62-125">This example divides values in the **ListPrice** column by values in the **StandardCost** column.</span></span>  
  
```  
ListPrice / StandardCost  
```  
  
## <a name="see-also"></a><span data-ttu-id="63d62-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="63d62-126">See Also</span></span>  
 <span data-ttu-id="63d62-127">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="63d62-127">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="63d62-128">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="63d62-128">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
