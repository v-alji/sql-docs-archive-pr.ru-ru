---
title: Примеры уравнений фильтра (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- filtering data [Reporting Services], filter equation examples
ms.assetid: 66bec93d-7c3b-4d4a-8cb6-7a7bb2f34ec6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b4d7c7c561c9185c141190e26f37bc29fe52eb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658105"
---
# <a name="filter-equation-examples-report-builder-and-ssrs"></a><span data-ttu-id="ae7da-102">Примеры уравнений фильтра (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="ae7da-102">Filter Equation Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ae7da-103">Чтобы создать фильтр, необходимо указать одно или несколько уравнений фильтра.</span><span class="sxs-lookup"><span data-stu-id="ae7da-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="ae7da-104">Уравнение фильтра состоит из выражения, типа данных, оператора и значения.</span><span class="sxs-lookup"><span data-stu-id="ae7da-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="ae7da-105">В этом разделе приведены примеры распространенных фильтров.</span><span class="sxs-lookup"><span data-stu-id="ae7da-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="ae7da-106">Примеры фильтров</span><span class="sxs-lookup"><span data-stu-id="ae7da-106">Filter Examples</span></span>  
 <span data-ttu-id="ae7da-107">В следующей таблице перечислены примеры уравнений фильтра, использующих различные типы данных и различные операторы.</span><span class="sxs-lookup"><span data-stu-id="ae7da-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="ae7da-108">Область сравнения определяется элементом отчета, для которого определен фильтр.</span><span class="sxs-lookup"><span data-stu-id="ae7da-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="ae7da-109">Например, для фильтра, определенного для набора данных, **TOP % 10** — это верхние 10% значений в наборе данных; для фильтра, определенного для группы, **TOP % 10** — это верхние 10% значений в группе.</span><span class="sxs-lookup"><span data-stu-id="ae7da-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="ae7da-110">Простое выражение</span><span class="sxs-lookup"><span data-stu-id="ae7da-110">Simple Expression</span></span>|<span data-ttu-id="ae7da-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ae7da-111">Data Type</span></span>|<span data-ttu-id="ae7da-112">Оператор</span><span class="sxs-lookup"><span data-stu-id="ae7da-112">Operator</span></span>|<span data-ttu-id="ae7da-113">Значение</span><span class="sxs-lookup"><span data-stu-id="ae7da-113">Value</span></span>|<span data-ttu-id="ae7da-114">Description</span><span class="sxs-lookup"><span data-stu-id="ae7da-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="ae7da-115">Включает все значения данных, превышающие 7.</span><span class="sxs-lookup"><span data-stu-id="ae7da-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="ae7da-116">Включает 10 верхних значений данных.</span><span class="sxs-lookup"><span data-stu-id="ae7da-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="ae7da-117">Включает верхние 20% значений данных.</span><span class="sxs-lookup"><span data-stu-id="ae7da-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="ae7da-118">Включает все значения типа System.Decimal (тип данных, используемый в SQL для денежных сумм), превышающие 100.</span><span class="sxs-lookup"><span data-stu-id="ae7da-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2008-01-01`|<span data-ttu-id="ae7da-119">Включает все даты с 1 января 2008 года по сегодняшний день.</span><span class="sxs-lookup"><span data-stu-id="ae7da-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="ae7da-120">Включает все даты с 1 января 2008 года до 1 февраля 2008 года включительно.</span><span class="sxs-lookup"><span data-stu-id="ae7da-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="ae7da-121">Все названия территорий, заканчивающиеся словом «east».</span><span class="sxs-lookup"><span data-stu-id="ae7da-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="ae7da-122">Все названия территорий, начинающиеся словами «North» или «South».</span><span class="sxs-lookup"><span data-stu-id="ae7da-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="ae7da-123">Все значения подкатегорий, начинающиеся с букв «В», «C» или «T».</span><span class="sxs-lookup"><span data-stu-id="ae7da-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae7da-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae7da-124">See Also</span></span>  
 <span data-ttu-id="ae7da-125">[Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="ae7da-125">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="ae7da-126">[Добавление фильтров набора данных, фильтров области данных и групповых фильтров &#40;построитель отчетов и SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="ae7da-126">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="ae7da-127">[Типы данных в выражениях &#40;построитель отчетов и SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ae7da-127">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ae7da-128">[Использование выражений в отчетах &#40;построитель отчетов и SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ae7da-128">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ae7da-129">Примеры выражений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="ae7da-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
