---
title: Функция CountRows (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5b1c403d-6afd-44c8-b5f6-5ecff2a29a45
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d5311dfc5dfcb89449a4039fdac4100fc5a3b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659436"
---
# <a name="countrows-function-report-builder-and-ssrs"></a><span data-ttu-id="61e4b-102">Функция CountRows (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="61e4b-102">CountRows Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="61e4b-103">Возвращает число строк в указанной области, включая строки со значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="61e4b-103">Returns the number of rows in the specified scope, including rows with null values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="61e4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61e4b-104">Syntax</span></span>  
  
```  
  
CountRows(scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61e4b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="61e4b-105">Parameters</span></span>  
 <span data-ttu-id="61e4b-106">*область*</span><span class="sxs-lookup"><span data-stu-id="61e4b-106">*scope*</span></span>  
 <span data-ttu-id="61e4b-107">(`String`) — имя набора данных, области данных или группы, содержащих подсчитываемые элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="61e4b-107">(`String`) The name of a dataset, data region, or group that contains the report items to count.</span></span>  
  
 <span data-ttu-id="61e4b-108">*рекурсивные*</span><span class="sxs-lookup"><span data-stu-id="61e4b-108">*recursive*</span></span>  
 <span data-ttu-id="61e4b-109">(**Перечислимый тип**) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="61e4b-109">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="61e4b-110">`Simple` (по умолчанию) или `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="61e4b-110">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="61e4b-111">Указывает, нужно ли выполнять статистическую обработку рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="61e4b-111">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="61e4b-112">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="61e4b-112">Return Type</span></span>  
 <span data-ttu-id="61e4b-113">Возвращает значение типа `Integer`.</span><span class="sxs-lookup"><span data-stu-id="61e4b-113">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61e4b-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="61e4b-114">Remarks</span></span>  
 <span data-ttu-id="61e4b-115">Функция `CountRows` подсчитывает все строки в указанной области, включая строки со значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="61e4b-115">`CountRows` counts all rows in the specified scope, including rows that have null values.</span></span>  
  
 <span data-ttu-id="61e4b-116">Значение *scope* не может быть выражением и должно указывать на текущую или включающую область.</span><span class="sxs-lookup"><span data-stu-id="61e4b-116">The value of *scope* cannot be an expression and must refer to the current scope or a containing scope.</span></span>  
  
 <span data-ttu-id="61e4b-117">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="61e4b-117">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="61e4b-118">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="61e4b-118">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61e4b-119">Пример</span><span class="sxs-lookup"><span data-stu-id="61e4b-119">Example</span></span>  
 <span data-ttu-id="61e4b-120">В следующем примере кода показано выражение, вычисляющее число строк в группе строк, называемой `GroupbyCategory` (на основании выражения `[Category]`).</span><span class="sxs-lookup"><span data-stu-id="61e4b-120">The following code example shows an expression that calculates the number of rows in a row group named `GroupbyCategory` (based on the expression `[Category]`).</span></span>  
  
```  
="Number of rows: " & CountRows("GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="61e4b-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="61e4b-121">See Also</span></span>  
 <span data-ttu-id="61e4b-122">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61e4b-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="61e4b-123">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61e4b-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="61e4b-124">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61e4b-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="61e4b-125">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="61e4b-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
