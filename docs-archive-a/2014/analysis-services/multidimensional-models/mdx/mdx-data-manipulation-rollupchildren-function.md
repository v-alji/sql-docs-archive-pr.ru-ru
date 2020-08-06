---
title: Работа с функцией RollupChildren (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], RollupChildren function
- RollupChildren function
- custom member properties [MDX]
- IIf function
ms.assetid: 03c624d4-f277-451d-9995-623a07ea2f86
author: minewiskan
ms.author: owend
ms.openlocfilehash: 341468d521cebe1fda33d73ea999f3b6571cb01e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737037"
---
# <a name="working-with-the-rollupchildren-function-mdx"></a><span data-ttu-id="f05fc-102">Работа с функцией RollupChildren (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="f05fc-102">Working with the RollupChildren Function (MDX)</span></span>
  <span data-ttu-id="f05fc-103">Функция МНОГОМЕРных выражений [RollupChildren](/sql/mdx/rollupchildren-mdx) [скрипт для поиска и замена] выполняет сведение дочерних элементов элемента, применяя другой унарный оператор к каждому дочернему элементу, и возвращает значение этой свертки в виде числа.</span><span class="sxs-lookup"><span data-stu-id="f05fc-103">The Multidimensional Expressions (MDX) [RollupChildren](/sql/mdx/rollupchildren-mdx) [Script for Search and Replace] function rolls up the children of a member, applying a different unary operator to each child, and returns the value of this rollup as a number.</span></span> <span data-ttu-id="f05fc-104">Унарный оператор может браться из свойства, связанного с элементом-потомком, или же оператор может быть строковым выражением, непосредственно заданным для этой функции.</span><span class="sxs-lookup"><span data-stu-id="f05fc-104">The unary operator can be supplied by a member property associated with the child member, or the operator can be a string expression provided directly to the function.</span></span>  
  
## <a name="rollupchildren-function-examples"></a><span data-ttu-id="f05fc-105">Примеры функции RollupChildren</span><span class="sxs-lookup"><span data-stu-id="f05fc-105">RollupChildren Function Examples</span></span>  
 <span data-ttu-id="f05fc-106">Применение функции `RollupChildren` в инструкциях многомерных выражений объяснить просто, однако действие этой функции на запросы многомерных выражений может быть разнообразным.</span><span class="sxs-lookup"><span data-stu-id="f05fc-106">The use of the `RollupChildren` function in Multidimensional Expressions (MDX) statements is simple to explain, but the effect of this function on MDX queries can be wide-ranging.</span></span>  
  
 <span data-ttu-id="f05fc-107">Воздействие функции `RollupChildren` осуществляется в запросах многомерных выражений, предназначенных для выполнения выборочного анализа существующих данных куба.</span><span class="sxs-lookup"><span data-stu-id="f05fc-107">The effect of the `RollupChildren` function occurs in MDX queries designed to perform selective analysis on existing cube data.</span></span> <span data-ttu-id="f05fc-108">Например, в следующей таблице перечисляются элементы-потомки для элемента-родителя «Чистая выручка от продаж», а в скобках показаны их унарные операторы (представленные свойством элементов `UNARY_OPERATOR`).</span><span class="sxs-lookup"><span data-stu-id="f05fc-108">For example, the following table contains a list of child members for the Net Sales parent member, with their unary operators (represented by the `UNARY_OPERATOR` member property) shown in parentheses.</span></span>  
  
|<span data-ttu-id="f05fc-109">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="f05fc-109">Parent member</span></span>|<span data-ttu-id="f05fc-110">Дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="f05fc-110">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="f05fc-111">Чистая выручка от продаж</span><span class="sxs-lookup"><span data-stu-id="f05fc-111">Net Sales</span></span>|<span data-ttu-id="f05fc-112">Внутренние продажи (+)</span><span class="sxs-lookup"><span data-stu-id="f05fc-112">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="f05fc-113">Внутренние возвраты (-)</span><span class="sxs-lookup"><span data-stu-id="f05fc-113">Domestic Returns (-)</span></span><br /><br /> <span data-ttu-id="f05fc-114">Зарубежные продажи (+)</span><span class="sxs-lookup"><span data-stu-id="f05fc-114">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="f05fc-115">Зарубежные возвраты (-)</span><span class="sxs-lookup"><span data-stu-id="f05fc-115">Foreign Returns (-)</span></span>|  
  
 <span data-ttu-id="f05fc-116">Родительский элемент «Чистая выручка от продаж» в данный момент предоставляет сумму чистых продаж минус валовые внутренние и внешние продажи, причем вычитание внутренних и внешних возвратов производится как часть выполнения этой свертки.</span><span class="sxs-lookup"><span data-stu-id="f05fc-116">The Net Sales parent member currently provides a total of net sales minus the gross domestic and foreign sales values, with the domestic and foreign returns subtracted as part of the rollup.</span></span>  
  
 <span data-ttu-id="f05fc-117">Однако предположим, что надо быстро получить оценку прироста на 10 % внутренних и внешних валовых продаж без учета внутренних и внешних возвратов.</span><span class="sxs-lookup"><span data-stu-id="f05fc-117">However, you want to provide a quick and easy forecast of domestic and foreign gross sales plus 10%, ignoring the domestic and foreign returns.</span></span> <span data-ttu-id="f05fc-118">Для вычисления этого значения можно воспользоваться функцией `RollupChildren`, одним из двух методов: с помощью пользовательского свойства элемента или функции `IIf`.</span><span class="sxs-lookup"><span data-stu-id="f05fc-118">To calculate this value, you can use the `RollupChildren` function in one of two ways: with a custom member property or with the `IIf` function.</span></span>  
  
### <a name="using-a-custom-member-property"></a><span data-ttu-id="f05fc-119">Применение пользовательского свойства элемента</span><span class="sxs-lookup"><span data-stu-id="f05fc-119">Using a Custom Member Property</span></span>  
 <span data-ttu-id="f05fc-120">Если вычисление свертки надо производить часто, то можно создать свойство элемента, хранящее оператор, который в специальной функции будет применяться к каждому дочернему элементу.</span><span class="sxs-lookup"><span data-stu-id="f05fc-120">If the rollup calculation is to be a frequently performed operation, one method is to create a member property that stores the operator that will be used for each child for a specific function.</span></span> <span data-ttu-id="f05fc-121">В следующей таблице показаны допустимые унарные операторы и ожидаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="f05fc-121">The following table displays valid unary operators and describes the expected result.</span></span>  
  
|<span data-ttu-id="f05fc-122">Оператор</span><span class="sxs-lookup"><span data-stu-id="f05fc-122">Operator</span></span>|<span data-ttu-id="f05fc-123">Результат</span><span class="sxs-lookup"><span data-stu-id="f05fc-123">Result</span></span>|  
|--------------|------------|  
|+|<span data-ttu-id="f05fc-124">сумма = сумма + текущий дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="f05fc-124">total = total + current child</span></span>|  
|-|<span data-ttu-id="f05fc-125">сумма = сумма - текущий дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="f05fc-125">total = total - current child</span></span>|  
|*|<span data-ttu-id="f05fc-126">сумма = сумма \* текущий дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="f05fc-126">total = total \* current child</span></span>|  
|/|<span data-ttu-id="f05fc-127">сумма = сумма / текущий дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="f05fc-127">total = total / current child</span></span>|  
|~|<span data-ttu-id="f05fc-128">Дочерний элемент не используется в свертке.</span><span class="sxs-lookup"><span data-stu-id="f05fc-128">Child is not used in the rollup.</span></span> <span data-ttu-id="f05fc-129">Значение дочернего элемента игнорируется.</span><span class="sxs-lookup"><span data-stu-id="f05fc-129">The child's value is ignored.</span></span>|  
  
 <span data-ttu-id="f05fc-130">Например, можно было бы создать свойство элемента с именем `SALES_OPERATOR`, и этому свойству элемента присваивались бы следующие унарные операторы — см. таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="f05fc-130">For example, a member property called `SALES_OPERATOR` could be created, and the following unary operators would be assigned to that member property, as shown in the following table.</span></span>  
  
|<span data-ttu-id="f05fc-131">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="f05fc-131">Parent member</span></span>|<span data-ttu-id="f05fc-132">Дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="f05fc-132">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="f05fc-133">Чистая выручка от продаж</span><span class="sxs-lookup"><span data-stu-id="f05fc-133">Net Sales</span></span>|<span data-ttu-id="f05fc-134">Внутренние продажи (+)</span><span class="sxs-lookup"><span data-stu-id="f05fc-134">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="f05fc-135">Внутренние возвраты (~)</span><span class="sxs-lookup"><span data-stu-id="f05fc-135">Domestic Returns (~)</span></span><br /><br /> <span data-ttu-id="f05fc-136">Зарубежные продажи (+)</span><span class="sxs-lookup"><span data-stu-id="f05fc-136">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="f05fc-137">Зарубежные возвраты (~)</span><span class="sxs-lookup"><span data-stu-id="f05fc-137">Foreign Returns (~)</span></span>|  
  
 <span data-ttu-id="f05fc-138">С помощью нового свойства элемента следующая инструкция многомерных выражений быстро и эффективно выполнит операцию прогнозирования валовых продаж (без учета внешних и внутренних возвратов):</span><span class="sxs-lookup"><span data-stu-id="f05fc-138">With this new member property, the following MDX statement would perform the gross sales estimate operation quickly and efficiently (ignoring Foreign and Domestic returns):</span></span>  
  
```  
RollupChildren([Net Sales], [Net Sales].CurrentMember.Properties("SALES_OPERATOR")) * 1.1  
```  
  
 <span data-ttu-id="f05fc-139">При вызове этой функции в сумму войдет значение каждого дочернего элемента, к которому будет применен оператор, хранящийся в данном свойстве элемента.</span><span class="sxs-lookup"><span data-stu-id="f05fc-139">When the function is called, the value of each child is applied to a total using the operator stored in the member property.</span></span> <span data-ttu-id="f05fc-140">Элементы для внутренних и внешних возвратов не учитываются, а полное значение свертки вычисляется по функции `RollupChildren`, умноженной на коэффициент 1,1.</span><span class="sxs-lookup"><span data-stu-id="f05fc-140">The members for domestic and foreign returns are ignored, and the rollup total returned by the `RollupChildren` function is multiplied by 1.1.</span></span>  
  
### <a name="using-the-iif-function"></a><span data-ttu-id="f05fc-141">Применение функции IIf</span><span class="sxs-lookup"><span data-stu-id="f05fc-141">Using the IIf Function</span></span>  
 <span data-ttu-id="f05fc-142">Если пример операции не является распространенным или если операция применяется только к одному запросу многомерных выражений, функцию [IIf](/sql/mdx/iif-mdx) можно использовать с `RollupChildren` функцией для предоставления того же результата.</span><span class="sxs-lookup"><span data-stu-id="f05fc-142">If the example operation is not commonplace or if the operation applies only to one MDX query, the [IIf](/sql/mdx/iif-mdx) function can be used with the `RollupChildren` function to provide the same result.</span></span> <span data-ttu-id="f05fc-143">Следующий запрос многомерных выражений дает тот же результат, что и описанный выше запрос многомерных выражений, но данный запрос выполняется без обращения к пользовательскому свойству элемента:</span><span class="sxs-lookup"><span data-stu-id="f05fc-143">The following MDX query provides the same result as the earlier MDX example, but does so without resorting to the use of a custom member property:</span></span>  
  
```  
RollupChildren([Net Sales], IIf([Net Sales].CurrentMember.Properties("UNARY_OPERATOR") = "-", "~", [Net Sales].CurrentMember.Properties("UNARY_OPERATOR))) * 1.1  
```  
  
 <span data-ttu-id="f05fc-144">Инструкция многомерных выражений анализирует унарный оператор дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="f05fc-144">The MDX statement examines the unary operator of the child member.</span></span> <span data-ttu-id="f05fc-145">Если унарный оператор применяется для вычитания (как в случае элементов с внутренними и внешними возвратами), то функция `IIf` заменяет унарный оператор тильду (~).</span><span class="sxs-lookup"><span data-stu-id="f05fc-145">If the unary operator is used for subtraction (as in the case with the domestic and foreign returns members), the `IIf` function substitutes the tilde (~) unary operator.</span></span> <span data-ttu-id="f05fc-146">В противном случае функция `IIf` использует унарный оператор дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="f05fc-146">Otherwise, the `IIf` function uses the unary operator of the child member.</span></span> <span data-ttu-id="f05fc-147">Наконец вычисленное значение суммы свертки умножается на коэффициент 1,1 для получения значения прогнозируемых валовых внутренних и внешних продаж.</span><span class="sxs-lookup"><span data-stu-id="f05fc-147">Finally, the returned rollup total is then multiplied by 1.1 to provide the domestic and foreign gross sales forecast value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05fc-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="f05fc-148">See Also</span></span>  
 [<span data-ttu-id="f05fc-149">Манипулирование данными (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="f05fc-149">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
