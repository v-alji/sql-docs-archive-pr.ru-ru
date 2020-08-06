---
title: Диалоговое окно "Свойства набора данных" — "фильтры" (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10025"
ms.assetid: 933a6f44-4eb7-4e73-9c40-ac0fd17b23d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7bc13b0eeff1eaf27fb0ec0c4279ff00d0809e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656248"
---
# <a name="dataset-properties-dialog-box-filters-report-builder"></a><span data-ttu-id="b8530-102">Диалоговое окно «Свойства набора данных» — «Фильтры» (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="b8530-102">Dataset Properties Dialog Box, Filters (Report Builder)</span></span>
  <span data-ttu-id="b8530-103">Перейдите на вкладку **Фильтры** диалогового окна **Свойства набора данных** , чтобы определить фильтры для набора данных.</span><span class="sxs-lookup"><span data-stu-id="b8530-103">Select **Filters** on the **Dataset Properties** dialog box to create filters for the dataset.</span></span>  
  
 <span data-ttu-id="b8530-104">Фильтры, являющиеся частью определения общего набора данных на сервере отчетов, влияют на все отчеты, в которых используется общий набор данных.</span><span class="sxs-lookup"><span data-stu-id="b8530-104">Filters that are part of a shared dataset definition on the report server affect all reports that use the shared dataset.</span></span> <span data-ttu-id="b8530-105">Дополнительные фильтры для общего набора данных можно указать после его добавления к отчету.</span><span class="sxs-lookup"><span data-stu-id="b8530-105">Additional filters for the shared dataset can be specified after it is added to a report.</span></span> <span data-ttu-id="b8530-106">Эти фильтры применяются только к отчету, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="b8530-106">These filters affect only the report in which they are defined.</span></span>  
  
 <span data-ttu-id="b8530-107">Фильтры для внедренного набора данных применяются только к отчету, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="b8530-107">Filters for an embedded dataset affect only the report in which they are defined.</span></span>  
  
 <span data-ttu-id="b8530-108">Дополнительные сведения см. в разделе [Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b8530-108">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b8530-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8530-109">Options</span></span>  
 <span data-ttu-id="b8530-110">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="b8530-110">**Add**</span></span>  
 <span data-ttu-id="b8530-111">Добавить в список новое предложение фильтра.</span><span class="sxs-lookup"><span data-stu-id="b8530-111">Add a new filter clause to the list.</span></span>  
  
 <span data-ttu-id="b8530-112">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="b8530-112">**Delete**</span></span>  
 <span data-ttu-id="b8530-113">Удалить из списка выбранное предложение фильтра.</span><span class="sxs-lookup"><span data-stu-id="b8530-113">Delete the selected filter clause from the list.</span></span>  
  
 <span data-ttu-id="b8530-114">**Стрелка вверх**</span><span class="sxs-lookup"><span data-stu-id="b8530-114">**Up arrow**</span></span>  
 <span data-ttu-id="b8530-115">Переместить выбранный фильтр в списке вверх.</span><span class="sxs-lookup"><span data-stu-id="b8530-115">Move the selected filter up in the list.</span></span>  
  
 <span data-ttu-id="b8530-116">**Стрелка вниз**</span><span class="sxs-lookup"><span data-stu-id="b8530-116">**Down arrow**</span></span>  
 <span data-ttu-id="b8530-117">Переместить выбранный фильтр в списке вниз</span><span class="sxs-lookup"><span data-stu-id="b8530-117">Move the selected filter down in the list</span></span>  
  
 <span data-ttu-id="b8530-118">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="b8530-118">**Expression**</span></span>  
 <span data-ttu-id="b8530-119">Введите или выберите выражение, к которому будет применяться фильтр.</span><span class="sxs-lookup"><span data-stu-id="b8530-119">Type or choose the expression to which you want to apply a filter.</span></span> <span data-ttu-id="b8530-120">Нажмите кнопку Выражение (**FX**), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="b8530-120">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
 <span data-ttu-id="b8530-121">**Data type**</span><span class="sxs-lookup"><span data-stu-id="b8530-121">**Data type**</span></span>  
 <span data-ttu-id="b8530-122">Выберите тип данных для поля **Значение**.</span><span class="sxs-lookup"><span data-stu-id="b8530-122">Choose the data type for **Value**.</span></span> <span data-ttu-id="b8530-123">По возможности выбирайте тип данных, который совпадает с типом данных, установленным для поля **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="b8530-123">When possible, choose a data type that matches the data type for **Expression**.</span></span>  
  
 <span data-ttu-id="b8530-124">Значения полей **Выражение** и **Значение** должны иметь один и тот же тип данных.</span><span class="sxs-lookup"><span data-stu-id="b8530-124">The values in **Expression** and **Value** must evaluate to the same data type.</span></span> <span data-ttu-id="b8530-125">Например, если **Выражение** указывает на поле с типом данных System.Int32, а для поля **Значение** установлено значение 7, выберите из раскрывающегося списка пункт **Integer**.</span><span class="sxs-lookup"><span data-stu-id="b8530-125">For example, if **Expression** is set to a field that has the data type System.Int32 and **Value** is set to 7, from the drop-down list, choose **Integer**.</span></span>  
  
 <span data-ttu-id="b8530-126">Если в раскрывающемся списке нет требуемого типа данных, напишите выражение для преобразования значения в правильный тип данных.</span><span class="sxs-lookup"><span data-stu-id="b8530-126">If the data type option you need is not in the drop-down list, write an expression to convert the value to the correct data type.</span></span> <span data-ttu-id="b8530-127">Дополнительные сведения см. в разделе [Примеры уравнений фильтра (построитель отчетов и службы SSRS)](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b8530-127">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="b8530-128">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="b8530-128">**Operator**</span></span>  
 <span data-ttu-id="b8530-129">Выберите оператор для сравнения выражения и значения.</span><span class="sxs-lookup"><span data-stu-id="b8530-129">Choose the operator to use to compare the expression and the value.</span></span>  
  
 <span data-ttu-id="b8530-130">**Значение**</span><span class="sxs-lookup"><span data-stu-id="b8530-130">**Value**</span></span>  
 <span data-ttu-id="b8530-131">Введите выражение или значение, которое будет использовано для вычисления выражения, указанного в поле **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="b8530-131">Type the expression or value to use when evaluating the expression specified in the **Expression** box.</span></span> <span data-ttu-id="b8530-132">Нажмите кнопку Выражение (**FX**), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="b8530-132">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8530-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b8530-133">See Also</span></span>  
 <span data-ttu-id="b8530-134">[Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b8530-134">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b8530-135">[Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b8530-135">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="b8530-136">[Добавление фильтра в набор данных &#40;построитель отчетов и SSRS&#41;](report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b8530-136">[Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b8530-137">Использование выражений в отчетах (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b8530-137">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
