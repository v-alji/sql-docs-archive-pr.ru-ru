---
title: + (сложение) (службы SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- + (add)
- add operator (+)
- adding expressions
ms.assetid: 44df4154-fed5-4e7f-9995-e703a0164f6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fe1e8f2118e6328582cb24abfd44eef5f3b15f79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666195"
---
# <a name="-add-ssis"></a><span data-ttu-id="0f983-102">+ (Сложение) (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="0f983-102">+ (Add) (SSIS)</span></span>
  <span data-ttu-id="0f983-103">Складывает два числовых выражения.</span><span class="sxs-lookup"><span data-stu-id="0f983-103">Adds two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f983-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f983-104">Syntax</span></span>  
  
```  
  
numeric_expression1 + numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f983-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0f983-105">Arguments</span></span>  
 <span data-ttu-id="0f983-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="0f983-106">*numeric_expression1, numeric_ expression2*</span></span>  
 <span data-ttu-id="0f983-107">Любое допустимое выражение числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="0f983-107">Is any valid expression of a numeric data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0f983-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="0f983-108">Result Types</span></span>  
 <span data-ttu-id="0f983-109">Определяются типами данных обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="0f983-109">Determined by data types of the two arguments.</span></span> <span data-ttu-id="0f983-110">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0f983-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f983-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f983-111">Remarks</span></span>  
 <span data-ttu-id="0f983-112">Если один из операндов равен NULL, то результатом является значение NULL.</span><span class="sxs-lookup"><span data-stu-id="0f983-112">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0f983-113">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="0f983-113">Expression Examples</span></span>  
 <span data-ttu-id="0f983-114">В этом примере суммируются числовые литералы.</span><span class="sxs-lookup"><span data-stu-id="0f983-114">This example adds numeric literals.</span></span>  
  
```  
5 + 6.09 + 7.0  
```  
  
 <span data-ttu-id="0f983-115">В примере суммируются значения столбцов **VacationHours** и **SickLeaveHours** .</span><span class="sxs-lookup"><span data-stu-id="0f983-115">This example adds values in the **VacationHours** and **SickLeaveHours** columns.</span></span>  
  
```  
VacationHours + SickLeaveHours  
```  
  
 <span data-ttu-id="0f983-116">В примере вычисленное значение прибавляется к столбцу **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="0f983-116">This example adds a calculated value to the **StandardCost** column.</span></span> <span data-ttu-id="0f983-117">Переменная **Profit%** должна быть заключена в квадратные скобки, поскольку имя включает символ %.</span><span class="sxs-lookup"><span data-stu-id="0f983-117">The variable **Profit%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="0f983-118">Дополнительные сведения см. в разделе [Идентификаторы (службы SSIS)](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="0f983-118">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
StandardCost + (StandardCost * @[Profit%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f983-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f983-119">See Also</span></span>  
 <span data-ttu-id="0f983-120">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="0f983-120">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="0f983-121">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="0f983-121">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
