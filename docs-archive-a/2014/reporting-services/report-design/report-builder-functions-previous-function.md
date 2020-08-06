---
title: Функция Previous (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3891deec3f152cdf46da77a7f2d11d38387c5c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659417"
---
# <a name="previous-function-report-builder-and-ssrs"></a><span data-ttu-id="4ff8e-102">Функция Previous (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4ff8e-102">Previous Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4ff8e-103">Возвращает значение или значение статистического выражения для предыдущего экземпляра элемента внутри заданной области.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-103">Returns the value or the specified aggregate value for the previous instance of an item within the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="4ff8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ff8e-104">Syntax</span></span>  
  
```  
  
Previous(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ff8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ff8e-105">Parameters</span></span>  
 <span data-ttu-id="4ff8e-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="4ff8e-106">*expression*</span></span>  
 <span data-ttu-id="4ff8e-107">(`Variant` или `Binary`) Выражение, используемое для идентификации данных, для которого необходимо получить предыдущее значение, например `Fields!Fieldname.Value` или `Sum(Fields!Fieldname.Value)`.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-107">(`Variant` or `Binary`) The expression to use to identify the data and for which to retrieve the previous value, for example, `Fields!Fieldname.Value` or `Sum(Fields!Fieldname.Value)`.</span></span>  
  
 <span data-ttu-id="4ff8e-108">*область*</span><span class="sxs-lookup"><span data-stu-id="4ff8e-108">*scope*</span></span>  
 <span data-ttu-id="4ff8e-109">(`String`) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-109">(`String`) Optional.</span></span> <span data-ttu-id="4ff8e-110">Имя группы или области данных или значение null ( `Nothing` в [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ), определяющее область, из которой извлекается предыдущее значение, заданное *выражением*.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-110">The name of a group or data region, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the scope from which to retrieve the previous value specified by *expression*.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="4ff8e-111">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="4ff8e-111">Return Type</span></span>  
 <span data-ttu-id="4ff8e-112">Возвращает `Variant` или `Binary`.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-112">Returns a `Variant` or `Binary`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ff8e-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ff8e-113">Remarks</span></span>  
 <span data-ttu-id="4ff8e-114">Функция `Previous` возвращает предыдущее значение для выражения, которое вычисляется в указанной области после применения всех операций сортировки и фильтрации.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-114">The `Previous` function returns the previous value for the expression evaluated in the specified scope after all sorting and filtering have been applied.</span></span>  
  
 <span data-ttu-id="4ff8e-115">Если *выражение* не содержит статистического выражения, `Previous` функция по умолчанию использует текущую область для элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-115">If *expression* does not contain an aggregate, the `Previous` function defaults to the current scope for the report item.</span></span>  
  
 <span data-ttu-id="4ff8e-116">В группе подробностей используйте функцию `Previous`, чтобы задать ссылку на значение поля в предыдущем экземпляре строки детализации.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-116">In a details group, use `Previous` to specify the value of a field reference in the previous instance of the detail row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ff8e-117">`Previous`Функция поддерживает только ссылки на поля в группе подробностей.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-117">The `Previous` function only supports field references in the details group.</span></span> <span data-ttu-id="4ff8e-118">Например, для текстового поля в группе подробностей выражение `=Previous(Fields!Quantity.Value)` возвращает данные для поля `Quantity` из предыдущей строки.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-118">For example, in a text box in the details group, `=Previous(Fields!Quantity.Value)` returns the data for the field `Quantity` from the previous row.</span></span> <span data-ttu-id="4ff8e-119">Это выражение в первой строке возвращает значение NULL (`Nothing` в [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="4ff8e-119">In the first row, this expression returns a null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  
  
 <span data-ttu-id="4ff8e-120">Если *выражение* содержит агрегатную функцию, которая использует область по умолчанию, выполняет `Previous` статистическую обработку данных в предыдущем экземпляре области, указанной в вызове агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-120">If *expression* contains an aggregate function that uses a default scope, `Previous` aggregates the data within the previous instance of the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="4ff8e-121">Если *выражение* содержит агрегатную функцию, задающую область, отличную от используемой по умолчанию, то параметром *области* для `Previous` функции должна быть область, включающая область, указанную в вызове агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-121">If *expression* contains an aggregate function that specifies a scope other than the default, the *scope* parameter for the `Previous` function must be a containing scope for the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="4ff8e-122">Функции, `Level` `InScope` `Aggregate` и `Previous` не могут использоваться в параметре *Expression*.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-122">The functions `Level`, `InScope`, `Aggregate` and `Previous` cannot be used in the *expression*parameter.</span></span> <span data-ttu-id="4ff8e-123">Параметр *recursive* для агрегатных функций не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-123">Specifying the *recursive* parameter for any aggregate function is not supported.</span></span>  
  
 <span data-ttu-id="4ff8e-124">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="4ff8e-124">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4ff8e-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="4ff8e-125">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="4ff8e-126">Description</span><span class="sxs-lookup"><span data-stu-id="4ff8e-126">Description</span></span>  
 <span data-ttu-id="4ff8e-127">Следующий пример кода, помещенный в строку данных по умолчанию для области данных, предоставляет значение для поля `LineTotal` в предыдущей строке.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-127">The following code example, when placed in the default data row of a data region, provides the value for the field `LineTotal` in the previous row.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4ff8e-128">Код</span><span class="sxs-lookup"><span data-stu-id="4ff8e-128">Code</span></span>  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### <a name="description"></a><span data-ttu-id="4ff8e-129">Description</span><span class="sxs-lookup"><span data-stu-id="4ff8e-129">Description</span></span>  
 <span data-ttu-id="4ff8e-130">В следующем примере показано выражение, вычисляющее сумму продаж в указанный день месяца и предыдущее значение в тот же день месяца в прошлом году.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-130">The following example shows an expression that calculates the sum of sales on a specific day of the month and the previous value for that day of the month in a previous year.</span></span> <span data-ttu-id="4ff8e-131">Выражение добавляется в ячейку строки, относящуюся к дочерней группе `GroupbyDay`.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-131">The expression is added to a cell in a row that belongs to the child group `GroupbyDay`.</span></span> <span data-ttu-id="4ff8e-132">Ее родительской группой является `GroupbyMonth`, которая имеет родительскую группу `GroupbyYear`.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-132">Its parent group is `GroupbyMonth`, which has a parent group `GroupbyYear`.</span></span> <span data-ttu-id="4ff8e-133">Выражение отображает результаты для группы GroupbyDay (область по умолчанию) и затем для группы `GroupbyYear` (родитель родительской группы `GroupbyMonth`).</span><span class="sxs-lookup"><span data-stu-id="4ff8e-133">The expression displays the results for GroupbyDay (the default scope) and then for `GroupbyYear` (the parent of the parent group `GroupbyMonth`).</span></span>  
  
 <span data-ttu-id="4ff8e-134">Рассмотрим для примера область данных с родительской группой `Year`и ее дочерней группой `Month`, у которой имеется дочерняя группа `Day` (три вложенных уровня).</span><span class="sxs-lookup"><span data-stu-id="4ff8e-134">For example, for a data region with a parent group named `Year`, its child group named `Month`, and its child group named `Day` (3 nested levels).</span></span> <span data-ttu-id="4ff8e-135">Выражение `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` в строке, связанной с группой `Day` , возвращает значение продаж в тот же день и в тот же месяц прошлого года.</span><span class="sxs-lookup"><span data-stu-id="4ff8e-135">The expression `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in a row associated with the group `Day` returns the sales value for the same day and month for the previous year.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4ff8e-136">Код</span><span class="sxs-lookup"><span data-stu-id="4ff8e-136">Code</span></span>  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ff8e-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ff8e-137">See Also</span></span>  
 <span data-ttu-id="4ff8e-138">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4ff8e-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4ff8e-139">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4ff8e-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4ff8e-140">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4ff8e-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4ff8e-141">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4ff8e-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
