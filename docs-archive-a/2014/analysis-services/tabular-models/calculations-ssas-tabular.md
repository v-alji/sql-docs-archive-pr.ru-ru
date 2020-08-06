---
title: Вычисления (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 738816e3-0e1d-44a5-8d1b-81068dce8ac0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2da86ae5c5652c8b2614cae4bbb721802700d973
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658427"
---
# <a name="calculations-ssas-tabular"></a><span data-ttu-id="94152-102">Вычисления (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="94152-102">Calculations (SSAS Tabular)</span></span>
  <span data-ttu-id="94152-103">После импорта данных в модель можно добавить вычисления для агрегации, фильтрации, расширения, объединения и защиты этих данных.</span><span class="sxs-lookup"><span data-stu-id="94152-103">After you have imported data into your model, you can add calculations to aggregate, filter, extend, combine, and secure that data.</span></span> <span data-ttu-id="94152-104">В табличных моделях используется язык выражений анализа данных (DAX) — новый язык формул для создания пользовательских вычислений.</span><span class="sxs-lookup"><span data-stu-id="94152-104">Tabular models use Data Analysis Expressions (DAX), a formula language for creating custom calculations.</span></span> <span data-ttu-id="94152-105">В табличных моделях вычисления, которые можно создать с помощью формул DAX, используются в *вычисляемых столбцах*, *мерах*и *фильтрах строк*.</span><span class="sxs-lookup"><span data-stu-id="94152-105">In tabular models, the calculations you create by using DAX formulas are used in *Calculated Columns*, *Measures*, and *Row Filters*.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94152-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="94152-106">In This Section</span></span>  
  
|<span data-ttu-id="94152-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="94152-107">Topic</span></span>|<span data-ttu-id="94152-108">Описание</span><span class="sxs-lookup"><span data-stu-id="94152-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="94152-109">Основные сведения о DAX в табличных моделях (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="94152-109">Understanding DAX in Tabular Models &#40;SSAS Tabular&#41;</span></span>](understanding-dax-in-tabular-models-ssas-tabular.md)|<span data-ttu-id="94152-110">Описывает язык формул выражений анализа данных (DAX), используемый для создания вычислений для вычисляемых столбцов, мер и фильтров строк в табличных моделях.</span><span class="sxs-lookup"><span data-stu-id="94152-110">Describes the Data Analysis Expressions (DAX) formula language used to create calculations for calculated columns, measures, and row filters in tabular models.</span></span>|  
|[<span data-ttu-id="94152-111">Совместимость формул в режиме DirectQuery</span><span class="sxs-lookup"><span data-stu-id="94152-111">Formula Compatibility in DirectQuery Mode</span></span>](../dax-formula-compatibility-in-directquery-mode-ssas-2014.md)|<span data-ttu-id="94152-112">Описывает различия, перечисляет функции, неподдерживаемые в режиме DirectQuery, а также функции, которые поддерживаются, но могут возвратить отличающиеся результаты.</span><span class="sxs-lookup"><span data-stu-id="94152-112">Describes the differences, lists the functions that are not supported in DirectQuery mode, and lists the functions that are supported but could return different results.</span></span>|  
|[<span data-ttu-id="94152-113">Выражения анализа данных &#40;Справочник по DAX&#41;</span><span class="sxs-lookup"><span data-stu-id="94152-113">Data Analysis Expressions &#40;DAX&#41; Reference</span></span>](/dax/data-analysis-expressions-dax-reference)|<span data-ttu-id="94152-114">Этот раздел содержит подробное описание синтаксиса языка выражений анализа данных (DAX), операторов и функций.</span><span class="sxs-lookup"><span data-stu-id="94152-114">This section provides detailed descriptions of DAX syntax, operators, and functions.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="94152-115">В этом разделе не содержатся пошаговые примеры создания вычислений.</span><span class="sxs-lookup"><span data-stu-id="94152-115">Step-by-step tasks for creating calculations are not provided in this section.</span></span> <span data-ttu-id="94152-116">Так как вычисления задаются в вычисляемых столбцах, мерах и фильтрах строк (в ролях), указания по созданию формул DAX приведены в связанных с этими элементами задачах.</span><span class="sxs-lookup"><span data-stu-id="94152-116">Because calculations are specified in calculated columns, measures, and row filters (in roles), instructions on where to create DAX formulas are provided in tasks related to those features.</span></span> <span data-ttu-id="94152-117">Дополнительные сведения см. в разделе [Создание вычисляемого столбца (табличные службы SSAS)](ssas-calculated-columns-create-a-calculated-column.md), [Создание мер и управление ими (табличные службы SSAS)](measures-ssas-tabular.md) и [Создание ролей и управление ими (табличные службы SSAS)](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="94152-117">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md), and [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94152-118">Хотя выражения DAX могут использоваться для осуществления запросов к табличной модели служб, тематика этого раздела связана именно с использованием формул DAX при создании вычислений.</span><span class="sxs-lookup"><span data-stu-id="94152-118">While DAX can also be used to query a tabular model, topics in this section focus specifically on using DAX formulas to create calculations.</span></span>  
  
  
