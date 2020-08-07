---
title: Примеры выражений групп (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data [Reporting Services], grouping
- grouping data
- expressions [Reporting Services], adding
- groups [Reporting Services], expressions
ms.assetid: 34cd0249-fc74-4cf2-ba11-7b072992bfd2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128e3fa7aed189fd00072c2c3e961b80f8137c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727977"
---
# <a name="group-expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="3981e-102">Примеры выражений групп (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3981e-102">Group Expression Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3981e-103">В области данных можно группировать данные по одному полю или создавать более сложные выражения, определяющие данные, по которым выполняется группирование.</span><span class="sxs-lookup"><span data-stu-id="3981e-103">In a data region, you can group data by a single field, or create more complex expressions that identify the data on which to group.</span></span> <span data-ttu-id="3981e-104">Сложные выражения могут включать ссылки на несколько полей или параметров, условные инструкции или пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="3981e-104">Complex expressions include references to multiple fields or parameters, conditional statements, or custom code.</span></span> <span data-ttu-id="3981e-105">При определении группы для области данных эти выражения добавляются к свойству **Группировать** .</span><span class="sxs-lookup"><span data-stu-id="3981e-105">When you define a group for a data region, you add these expressions to the **Group** properties.</span></span> <span data-ttu-id="3981e-106">Дополнительные сведения см. в разделе [Добавление или удаление группы в области данных (построитель отчетов и службы SSRS)](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3981e-106">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="3981e-107">Чтобы выполнить слияние двух или нескольких групп, основанных на простых выражениях поля, добавьте каждое поле к списку выражений группы в определении группы.</span><span class="sxs-lookup"><span data-stu-id="3981e-107">To merge two or more groups that are based on simple field expressions, add each field to the group expressions list in the group definition.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="examples-of-group-expressions"></a><span data-ttu-id="3981e-108">Примеры выражений группы</span><span class="sxs-lookup"><span data-stu-id="3981e-108">Examples of Group Expressions</span></span>  
 <span data-ttu-id="3981e-109">В следующей таблице приведены примеры выражений группы, которые можно использовать для определения группы.</span><span class="sxs-lookup"><span data-stu-id="3981e-109">The following table provides examples of group expressions that you can use to define a group.</span></span>  
  
|<span data-ttu-id="3981e-110">Description</span><span class="sxs-lookup"><span data-stu-id="3981e-110">Description</span></span>|<span data-ttu-id="3981e-111">Выражение</span><span class="sxs-lookup"><span data-stu-id="3981e-111">Expression</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="3981e-112">Группирование по полю `Region` .</span><span class="sxs-lookup"><span data-stu-id="3981e-112">Group by the `Region` field.</span></span>|`=Fields!Region.Value`|  
|<span data-ttu-id="3981e-113">Группирование по фамилии и имени.</span><span class="sxs-lookup"><span data-stu-id="3981e-113">Group by last name and first name.</span></span>|`=Fields!LastName.Value`<br /><br /> `=Fields!FirstName.Value`|  
|<span data-ttu-id="3981e-114">Группирование по первой букве фамилии.</span><span class="sxs-lookup"><span data-stu-id="3981e-114">Group by the first letter of the last name.</span></span>|`=Fields!LastName.Value.Substring(0,1)`|  
|<span data-ttu-id="3981e-115">Группирование по параметру, основанному на выборе пользователя.</span><span class="sxs-lookup"><span data-stu-id="3981e-115">Group by parameter, based on user selection.</span></span><br /><br /> <span data-ttu-id="3981e-116">В этом примере параметр `GroupBy` должен быть основан на списке допустимых значений, которые предоставляет допустимый вариант выбора для группирования.</span><span class="sxs-lookup"><span data-stu-id="3981e-116">In this example, the parameter `GroupBy` must be based on an available values list that provides a valid choice to group on.</span></span>|`=Fields(Parameters!GroupBy.Value).Value`|  
|<span data-ttu-id="3981e-117">Группирование по трем отдельным возрастным диапазонам:</span><span class="sxs-lookup"><span data-stu-id="3981e-117">Group by three separate age ranges:</span></span><br /><br /> <span data-ttu-id="3981e-118">до 20, между 21 и 50, старше 50.</span><span class="sxs-lookup"><span data-stu-id="3981e-118">"Under 21", "Between 21 and 50", and "Over 50".</span></span>|`=IIF(First(Fields!Age.Value)<21,"Under 21",(IIF(First(Fields!Age.Value)>=21 AND First(Fields!Age.Value)<=50,"Between 21 and 50","Over 50")))`|  
|<span data-ttu-id="3981e-119">Группирование по многим возрастным диапазонам.</span><span class="sxs-lookup"><span data-stu-id="3981e-119">Group by many age ranges.</span></span> <span data-ttu-id="3981e-120">В этом примере показан пользовательский код, написанный на языке [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, который возвращает строку, относящуюся к одному из следующих диапазонов:</span><span class="sxs-lookup"><span data-stu-id="3981e-120">This example shows custom code, written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, that returns a string for the following ranges:</span></span><br /><br /> <span data-ttu-id="3981e-121">от 25 и младше,</span><span class="sxs-lookup"><span data-stu-id="3981e-121">25 or Under</span></span><br /><br /> <span data-ttu-id="3981e-122">от 26 до 50;</span><span class="sxs-lookup"><span data-stu-id="3981e-122">26 to 50</span></span><br /><br /> <span data-ttu-id="3981e-123">от 51 до 75;</span><span class="sxs-lookup"><span data-stu-id="3981e-123">51 to 75</span></span><br /><br /> <span data-ttu-id="3981e-124">старше 75.</span><span class="sxs-lookup"><span data-stu-id="3981e-124">Over 75</span></span>|`=Code.GetRangeValueByAge(Fields!Age.Value)`<br /><br /> <span data-ttu-id="3981e-125">Пользовательский код:</span><span class="sxs-lookup"><span data-stu-id="3981e-125">Custom code:</span></span><br /><br /> `Function GetRangeValueByAge(ByVal age As Integer) As String`<br /><br /> `Select Case age`<br /><br /> `Case 0 To 25`<br /><br /> `GetRangeValueByByAge = "25 or Under"`<br /><br /> `Case 26 To 50`<br /><br /> `GetRangeValueByByAge = "26 to 50"`<br /><br /> `Case 51 to 75`<br /><br /> `GetRangeValueByByAge = "51 to 75"`<br /><br /> `Case Else`<br /><br /> `GetRangeValueByByAge = "Over 75"`<br /><br /> `End Select`<br /><br /> `Return GetRangeValueByByAge`<br /><br /> `End Function`|  
  
## <a name="see-also"></a><span data-ttu-id="3981e-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="3981e-126">See Also</span></span>  
 <span data-ttu-id="3981e-127">[Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3981e-127">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3981e-128">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3981e-128">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3981e-129">Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3981e-129">Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;</span></span>](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)  
  
  
