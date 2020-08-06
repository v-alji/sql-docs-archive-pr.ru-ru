---
title: Функция InScope (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8cd209a-e5d3-4dce-ab2d-f271f6c54955
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62c4ad5de7af1ac0762df29deaa17953a8a378db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659429"
---
# <a name="inscope-function-report-builder-and-ssrs"></a><span data-ttu-id="c5cfc-102">Функция InScope (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c5cfc-102">InScope Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c5cfc-103">Указывает, входит ли текущий экземпляр элемента в указанную область.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-103">Indicates whether the current instance of an item is in the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="c5cfc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5cfc-104">Syntax</span></span>  
  
```  
InScope(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5cfc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5cfc-105">Parameters</span></span>  
 <span data-ttu-id="c5cfc-106">*область*</span><span class="sxs-lookup"><span data-stu-id="c5cfc-106">*scope*</span></span>  
 <span data-ttu-id="c5cfc-107">(`String`) — имя набора данных, области данных или группы, определяющей область.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-107">(`String`) The name of a dataset, data region, or group that specifies a scope.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="c5cfc-108">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="c5cfc-108">Return Type</span></span>  
 <span data-ttu-id="c5cfc-109">Возвращает значение типа `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-109">Returns a `Boolean`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5cfc-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5cfc-110">Remarks</span></span>  
 <span data-ttu-id="c5cfc-111">`InScope`Функция проверяет область текущего экземпляра элемента отчета на членство в области, заданной параметром *Scope*.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-111">The `InScope` function tests the scope of the current instance of a report item for membership in the scope specified by the *scope*parameter.</span></span>  
  
 <span data-ttu-id="c5cfc-112">Значением*Scope* не может быть выражение.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-112">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="c5cfc-113">Обычно функция `InScope` применяется в областях данных с динамическим определением области действия.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-113">A typical use for the `InScope` function is in data regions that have dynamic scoping.</span></span> <span data-ttu-id="c5cfc-114">Например, функция `InScope` может использоваться в ссылке детализации в ячейках области данных, чтобы предоставить другое название отчета и другие наборы параметров в зависимости от выбранной ячейки.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-114">For example, `InScope` can be used in a drillthrough link in a data region cells to provide a different report name and different sets of parameters depending on which cell is clicked.</span></span> <span data-ttu-id="c5cfc-115">Далее приведен пример.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-115">An example of this is as follows:</span></span>  
  
-   <span data-ttu-id="c5cfc-116">Следующее выражение, используемое в качестве названия отчета в ссылке детализации, открывает отчет `ProductDetail` , если выбранная ячейка находится в группе `Month` , и отчет `ProductSummary` — в противном случае.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-116">The following expression, used as the report name in a drillthrough link, opens the `ProductDetail` report if the clicked cell is in the `Month` group, and the `ProductSummary` report if it is not.</span></span>  
  
    ```  
    =Iif(InScope("Month"), "ProductDetail", "ProductSummary")  
    ```  
  
-   <span data-ttu-id="c5cfc-117">Следующее выражение, используемое в свойстве `Omit` параметра детализированного отчета, передает параметр целевому отчету только в том случае, если выбранная ячейка находится в группе `Product`.</span><span class="sxs-lookup"><span data-stu-id="c5cfc-117">The following expression, used in the `Omit` property of a drillthrough report parameter, will pass the parameter to the target report only if the clicked cell is in the `Product` group.</span></span>  
  
    ```  
    =Not(InScope("Product"))  
    ```  
  
 <span data-ttu-id="c5cfc-118">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="c5cfc-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5cfc-119">Пример</span><span class="sxs-lookup"><span data-stu-id="c5cfc-119">Example</span></span>  
 <span data-ttu-id="c5cfc-120">Следующий пример кода показывает, находится ли данный экземпляр элемента в пределах набора данных, области данных или в области группы `Product` .</span><span class="sxs-lookup"><span data-stu-id="c5cfc-120">The following code example indicates whether the current instance of the item is in the `Product` dataset, data region, or group scope.</span></span>  
  
```  
=InScope("Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5cfc-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5cfc-121">See Also</span></span>  
 <span data-ttu-id="c5cfc-122">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c5cfc-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c5cfc-123">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c5cfc-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c5cfc-124">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c5cfc-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c5cfc-125">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c5cfc-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
