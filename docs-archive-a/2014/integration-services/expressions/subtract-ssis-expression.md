---
title: '- (вычитание) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (subtract)'
- subtract operator (-)
ms.assetid: b48da086-37dd-460a-8a4b-912f52c9b158
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 79c47689baf47c33952c6b208ac622e9920d05fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732774"
---
# <a name="--subtract-ssis-expression"></a><span data-ttu-id="3a649-102">- (вычитание) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="3a649-102">- (Subtract) (SSIS Expression)</span></span>
  <span data-ttu-id="3a649-103">Вычитает второе числовое выражение из первого.</span><span class="sxs-lookup"><span data-stu-id="3a649-103">Subtracts the second numeric expression from the first one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a649-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a649-104">Syntax</span></span>  
  
```  
  
numeric_expression1 - numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3a649-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3a649-105">Arguments</span></span>  
 <span data-ttu-id="3a649-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="3a649-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="3a649-107">Любое допустимое выражение числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="3a649-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="3a649-108">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3a649-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3a649-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="3a649-109">Result Types</span></span>  
 <span data-ttu-id="3a649-110">Определяется типом данных двух аргументов.</span><span class="sxs-lookup"><span data-stu-id="3a649-110">Determined by the data types of the two arguments.</span></span> <span data-ttu-id="3a649-111">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3a649-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a649-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a649-112">Remarks</span></span>  
 <span data-ttu-id="3a649-113">Заключите унарное отрицательное выражение в скобки для того, чтобы выражение было вычислено в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="3a649-113">Enclose the minus unary expression in parenthesis to ensure that the expression is evaluated in the correct order</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a649-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a649-114">Remarks</span></span>  
 <span data-ttu-id="3a649-115">Если один из операндов равен NULL, то результатом является значение NULL.</span><span class="sxs-lookup"><span data-stu-id="3a649-115">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3a649-116">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="3a649-116">Expression Examples</span></span>  
 <span data-ttu-id="3a649-117">Этот пример вычитает числовые литералы.</span><span class="sxs-lookup"><span data-stu-id="3a649-117">This example subtracts numeric literals.</span></span>  
  
```  
5 - 6.09  
```  
  
 <span data-ttu-id="3a649-118">Этот пример вычитает значение столбца **StandardCost** из значения столбца **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="3a649-118">This example subtracts the value in the **StandardCost** column from the value in the **ListPrice** column.</span></span>  
  
```  
ListPrice - StandardCost  
```  
  
 <span data-ttu-id="3a649-119">Этот пример вычитает вычисленное значение из значения столбца **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="3a649-119">This example subtracts a calculated value from the **ListPrice** column.</span></span> <span data-ttu-id="3a649-120">Переменная **Discount%** должна быть заключена в квадратные скобки, поскольку имя включает символ %.</span><span class="sxs-lookup"><span data-stu-id="3a649-120">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="3a649-121">Дополнительные сведения см. в разделе [Идентификаторы (службы SSIS)](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="3a649-121">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a649-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a649-122">See Also</span></span>  
 <span data-ttu-id="3a649-123">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="3a649-123">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="3a649-124">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="3a649-124">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
