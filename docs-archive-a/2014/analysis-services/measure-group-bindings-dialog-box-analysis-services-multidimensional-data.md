---
title: Диалоговое окно «привязки группы мер» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.dimensionusage.definerelationship.measuregroupbindings.f1
helpviewer_keywords:
- Measure Group Bindings dialog box
ms.assetid: ed642780-5350-438e-af73-b9ceab3f876d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 78693901a5898b140d6efeed16b6f0eaa7577e69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750363"
---
# <a name="measure-group-bindings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="0ace7-102">Диалоговое окно «Привязки группы мер» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="0ace7-102">Measure Group Bindings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="0ace7-103">Используйте диалоговое окно **Привязки группы мер** для создания и изменения прямых связей между негранулярными атрибутами в измерении куба и столбцами в группе мер для связи обычного измерения, а также для указания параметров обработки значений NULL любого из атрибутов в измерении куба из диалогового окна **Задание связи** .</span><span class="sxs-lookup"><span data-stu-id="0ace7-103">Use the **Measure Group Bindings** dialog box to create and modify direct relationships between non-granularity attributes in a cube dimension and columns in a measure group for a regular dimension relationship, as well as to specify null processing options for any attribute in a cube dimension, from the **Define Relationship** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ace7-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="0ace7-104">Options</span></span>  
 <span data-ttu-id="0ace7-105">**Таблица группы мер**</span><span class="sxs-lookup"><span data-stu-id="0ace7-105">**Measure group table**</span></span>  
 <span data-ttu-id="0ace7-106">Отображает имя таблицы фактов для выбранной группы мер.</span><span class="sxs-lookup"><span data-stu-id="0ace7-106">Displays the name of the fact table for the selected measure group.</span></span>  
  
 <span data-ttu-id="0ace7-107">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="0ace7-107">**Attributes**</span></span>  
 <span data-ttu-id="0ace7-108">Отображает сетку атрибутов и таблиц измерений.</span><span class="sxs-lookup"><span data-stu-id="0ace7-108">Displays a grid of attributes and dimension tables.</span></span> <span data-ttu-id="0ace7-109">Выберите атрибут для создания или изменения свойств на панели **Связь** для выбранного атрибута.</span><span class="sxs-lookup"><span data-stu-id="0ace7-109">Select an attribute to create or modify properties in **Relationship** for the selected attribute.</span></span> <span data-ttu-id="0ace7-110">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="0ace7-110">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="0ace7-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="0ace7-111">Option</span></span>|<span data-ttu-id="0ace7-112">Определение</span><span class="sxs-lookup"><span data-stu-id="0ace7-112">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="0ace7-113">**Имя атрибута**</span><span class="sxs-lookup"><span data-stu-id="0ace7-113">**Attribute Name**</span></span>|<span data-ttu-id="0ace7-114">Показывает имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="0ace7-114">Displays the name of the attribute.</span></span>|  
|<span data-ttu-id="0ace7-115">**Таблица измерений**</span><span class="sxs-lookup"><span data-stu-id="0ace7-115">**Dimension Table**</span></span>|<span data-ttu-id="0ace7-116">Отображает имя таблицы измерений, на которой основан атрибут.</span><span class="sxs-lookup"><span data-stu-id="0ace7-116">Displays the name of the dimension table on which the attribute is based.</span></span>|  
  
 <span data-ttu-id="0ace7-117">**Связь**</span><span class="sxs-lookup"><span data-stu-id="0ace7-117">**Relationship**</span></span>  
 <span data-ttu-id="0ace7-118">Отображает сетку связей между столбцами таблицы измерений для выбранного атрибута и столбцами таблицы фактов для выбранной группы мер, а также параметр обработки NULL для связи.</span><span class="sxs-lookup"><span data-stu-id="0ace7-118">Displays a grid of relationships between dimension table columns for the selected attribute and fact table columns for the selected measure group as well as the null processing option for the relationship.</span></span> <span data-ttu-id="0ace7-119">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="0ace7-119">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="0ace7-120">Параметр</span><span class="sxs-lookup"><span data-stu-id="0ace7-120">Option</span></span>|<span data-ttu-id="0ace7-121">Определение</span><span class="sxs-lookup"><span data-stu-id="0ace7-121">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="0ace7-122">**Столбцы измерений**</span><span class="sxs-lookup"><span data-stu-id="0ace7-122">**Dimension Columns**</span></span>|<span data-ttu-id="0ace7-123">Отображает столбцы таблицы измерений, на которой основан атрибут, выбранный на панели **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="0ace7-123">Displays the columns from the dimension table on which the attribute selected in **Attributes** is based.</span></span>|  
|<span data-ttu-id="0ace7-124">**Столбцы группы мер**</span><span class="sxs-lookup"><span data-stu-id="0ace7-124">**Measure Group Columns**</span></span>|<span data-ttu-id="0ace7-125">Выберите параметр **Унаследован от измерения** , чтобы использовать связь группы мер, унаследованную от измерения, или столбец из таблицы фактов, на котором основана группа мер, чтобы явно определить связь.</span><span class="sxs-lookup"><span data-stu-id="0ace7-125">Select either **Inherited from dimension** to use the measure group relationship inherited from the dimension, or select a column from the fact table on which the measure group is based to explicitly define a relationship.</span></span>|  
|<span data-ttu-id="0ace7-126">**Обработка NULL**</span><span class="sxs-lookup"><span data-stu-id="0ace7-126">**Null Processing**</span></span>|<span data-ttu-id="0ace7-127">Выберите параметр обработки значения NULL ‎для атрибута.</span><span class="sxs-lookup"><span data-stu-id="0ace7-127">Select a null processing option for the attribute.</span></span> <span data-ttu-id="0ace7-128">Дополнительные сведения о параметрах обработки значений NULL см. в разделе [Элемент NullProcessing (ASSL)](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span><span class="sxs-lookup"><span data-stu-id="0ace7-128">For more information about null processing options, see [NullProcessing Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ace7-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ace7-129">See Also</span></span>  
 <span data-ttu-id="0ace7-130">[Диалоговое окно «Определение связи» &#40;Analysis Services многомерных данных&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0ace7-130">[Define Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="0ace7-131">Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="0ace7-131">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
