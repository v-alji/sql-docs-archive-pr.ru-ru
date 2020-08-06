---
title: '* (Умножение) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '* (multiply operator)'
- multiply operator (*)
ms.assetid: d457f052-ffbb-4485-833f-f4bed4349b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16d8429a869b60be31a94244a2ce47d515770c6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658910"
---
# <a name="-multiply-ssis-expression"></a><span data-ttu-id="1bad8-102">\* (умножение) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="1bad8-102">\* (Multiply) (SSIS Expression)</span></span>
  <span data-ttu-id="1bad8-103">Умножает два числовых выражения.</span><span class="sxs-lookup"><span data-stu-id="1bad8-103">Multiplies two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bad8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bad8-104">Syntax</span></span>  
  
```  
  
numeric_expression1 * numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1bad8-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1bad8-105">Arguments</span></span>  
 <span data-ttu-id="1bad8-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="1bad8-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="1bad8-107">Любое допустимое выражение числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="1bad8-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="1bad8-108">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1bad8-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1bad8-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="1bad8-109">Result Types</span></span>  
 <span data-ttu-id="1bad8-110">Определяются типами данных обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="1bad8-110">Determined by data types of the two arguments.</span></span> <span data-ttu-id="1bad8-111">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1bad8-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bad8-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bad8-112">Remarks</span></span>  
 <span data-ttu-id="1bad8-113">Если один из операндов равен NULL, то результатом является значение NULL.</span><span class="sxs-lookup"><span data-stu-id="1bad8-113">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="1bad8-114">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="1bad8-114">Expression Examples</span></span>  
 <span data-ttu-id="1bad8-115">Этот пример умножает числовые литералы.</span><span class="sxs-lookup"><span data-stu-id="1bad8-115">This example multiplies numeric literals.</span></span>  
  
```  
5 * 6.09  
```  
  
 <span data-ttu-id="1bad8-116">Этот пример увеличивает значения столбца **ListPrice** на 10 процентов.</span><span class="sxs-lookup"><span data-stu-id="1bad8-116">This example multiplies values in the **ListPrice** column by 10 percent.</span></span>  
  
```  
ListPrice * .10  
```  
  
 <span data-ttu-id="1bad8-117">Этот пример вычитает результат выражения из столбца **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="1bad8-117">This example subtracts the result of an expression from the **ListPrice** column.</span></span> <span data-ttu-id="1bad8-118">Переменная **Discount%** должна быть заключена в квадратные скобки, поскольку имя включает символ %.</span><span class="sxs-lookup"><span data-stu-id="1bad8-118">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="1bad8-119">Дополнительные сведения см. в разделе [Идентификаторы (службы SSIS)](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="1bad8-119">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bad8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bad8-120">See Also</span></span>  
 <span data-ttu-id="1bad8-121">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="1bad8-121">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="1bad8-122">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="1bad8-122">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
