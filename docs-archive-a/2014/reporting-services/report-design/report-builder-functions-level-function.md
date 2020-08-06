---
title: Функция Level (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 41235402-bb9e-4cb7-b91e-431e77db19cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dedbf00ce8330242c95e9592f649d95171f0987a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659427"
---
# <a name="level-function-report-builder-and-ssrs"></a><span data-ttu-id="05be2-102">Функция Level (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05be2-102">Level Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="05be2-103">Возвращает текущий уровень глубины в рекурсивной иерархии.</span><span class="sxs-lookup"><span data-stu-id="05be2-103">Returns the current level of depth in a recursive hierarchy.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="05be2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05be2-104">Syntax</span></span>  
  
```  
  
Level(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05be2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05be2-105">Parameters</span></span>  
 <span data-ttu-id="05be2-106">*область*</span><span class="sxs-lookup"><span data-stu-id="05be2-106">*scope*</span></span>  
 <span data-ttu-id="05be2-107">(`String`) (Необязательно)</span><span class="sxs-lookup"><span data-stu-id="05be2-107">(`String`) (Optional).</span></span> <span data-ttu-id="05be2-108">Имя набора данных, группы или области данных, содержащих элементы отчета, к которым применяется агрегатная функция.</span><span class="sxs-lookup"><span data-stu-id="05be2-108">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="05be2-109">Если аргумент *scope* не задан, используется текущая область.</span><span class="sxs-lookup"><span data-stu-id="05be2-109">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="05be2-110">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="05be2-110">Return Type</span></span>  
 <span data-ttu-id="05be2-111">Возвращает значение типа `Integer`.</span><span class="sxs-lookup"><span data-stu-id="05be2-111">Returns an `Integer`.</span></span> <span data-ttu-id="05be2-112">Если *область* указывает набор данных или область данных или задает нерекурсивное группирование (то есть группирование без `Parent` элемента), `Level` возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="05be2-112">If *scope* specifies a dataset or data region, or specifies a nonrecursive grouping (that is, a grouping with no `Parent` element), `Level` returns 0.</span></span> <span data-ttu-id="05be2-113">Если параметр *scope* не указан, то возвращается уровень текущей области.</span><span class="sxs-lookup"><span data-stu-id="05be2-113">If *scope* is omitted, it returns the level of the current scope.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05be2-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="05be2-114">Remarks</span></span>  
 <span data-ttu-id="05be2-115">Возвращаемые функцией `Level` значения отсчитываются от нуля, т. е. первым уровнем в иерархии является 0.</span><span class="sxs-lookup"><span data-stu-id="05be2-115">The value returned by the `Level` function is zero based; that is, the first level in a hierarchy is 0.</span></span>  
  
 <span data-ttu-id="05be2-116">Функция `Level` может использоваться для обеспечения автоматического определения отступов в рекурсивной иерархии, такой как список сотрудников.</span><span class="sxs-lookup"><span data-stu-id="05be2-116">The `Level` function can be used to provide indentation in a recursive hierarchy, such as an employee list.</span></span>  
  
 <span data-ttu-id="05be2-117">Дополнительные сведения о рекурсивных иерархиях см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05be2-117">For more information about recursive hierarchies, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05be2-118">Пример</span><span class="sxs-lookup"><span data-stu-id="05be2-118">Example</span></span>  
 <span data-ttu-id="05be2-119">Следующий пример кода показывает уровень строки в группе «Сотрудники»:</span><span class="sxs-lookup"><span data-stu-id="05be2-119">The following code example provides the level of row in the Employees group:</span></span>  
  
```  
=Level("Employees")  
```  
  
## <a name="see-also"></a><span data-ttu-id="05be2-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="05be2-120">See Also</span></span>  
 <span data-ttu-id="05be2-121">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05be2-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="05be2-122">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05be2-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="05be2-123">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05be2-123">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="05be2-124">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05be2-124">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
