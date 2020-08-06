---
title: Диалоговое окно "Свойства набора данных" — "Параметры" (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10023"
ms.assetid: 3a0672ad-c969-455b-b952-585164ce1dda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ef038e7cbf113556b11af9a0e6c59aa190b2400b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668661"
---
# <a name="dataset-properties-dialog-box-parameters-report-builder"></a><span data-ttu-id="d33bd-102">Диалоговое окно «Свойства набора данных» — «Настройки» (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="d33bd-102">Dataset Properties Dialog Box, Parameters (Report Builder)</span></span>
  <span data-ttu-id="d33bd-103">Выберите **Параметры** в диалоговом окне **Свойства набора данных** , чтобы добавить, изменить и удалить параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="d33bd-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters.</span></span>  
  
 <span data-ttu-id="d33bd-104">Что касается внедренного набора данных, то параметры применяются к набору данных в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="d33bd-104">For an embedded dataset, options apply to the dataset in the report definition.</span></span>  
  
 <span data-ttu-id="d33bd-105">Если речь идет об общем наборе данных, то параметры применяются к определению общего набора данных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="d33bd-105">For a shared dataset, options apply to the shared dataset definition on the report server.</span></span>  
  
 <span data-ttu-id="d33bd-106">Дополнительные сведения см. в разделе [Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d33bd-106">For more information, see [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d33bd-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d33bd-107">Options</span></span>  
 <span data-ttu-id="d33bd-108">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="d33bd-108">**Add**</span></span>  
 <span data-ttu-id="d33bd-109">Добавить в список новый параметр.</span><span class="sxs-lookup"><span data-stu-id="d33bd-109">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="d33bd-110">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="d33bd-110">**Delete**</span></span>  
 <span data-ttu-id="d33bd-111">Удалить выбранный параметр из списка.</span><span class="sxs-lookup"><span data-stu-id="d33bd-111">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="d33bd-112">**Стрелка вверх**</span><span class="sxs-lookup"><span data-stu-id="d33bd-112">**Up arrow**</span></span>  
 <span data-ttu-id="d33bd-113">Переместить выбранный параметр вверх по списку.</span><span class="sxs-lookup"><span data-stu-id="d33bd-113">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="d33bd-114">**Стрелка вниз**</span><span class="sxs-lookup"><span data-stu-id="d33bd-114">**Down arrow**</span></span>  
 <span data-ttu-id="d33bd-115">Переместить выбранный параметр вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="d33bd-115">Move the selected parameter down in the list.</span></span>  
  
 <span data-ttu-id="d33bd-116">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="d33bd-116">**Parameter name**</span></span>  
 <span data-ttu-id="d33bd-117">Введите имя параметра запроса, добавленного к набору данных на вкладке **Запрос** диалогового окна **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="d33bd-117">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="d33bd-118">**Значение параметра**</span><span class="sxs-lookup"><span data-stu-id="d33bd-118">**Parameter value**</span></span>  
 <span data-ttu-id="d33bd-119">Относится только к внедренным наборам данных.</span><span class="sxs-lookup"><span data-stu-id="d33bd-119">For embedded datasets only.</span></span>  
  
 <span data-ttu-id="d33bd-120">Введите значение параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="d33bd-120">Enter a value for the query parameter.</span></span> <span data-ttu-id="d33bd-121">Это может быть статическое значение или выражение, которое может ссылаться на объект в отчете, но не на любой элемент или поле отчета.</span><span class="sxs-lookup"><span data-stu-id="d33bd-121">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="d33bd-122">По умолчанию в поле **Значение** содержится выражение, указывающее параметр отчета.</span><span class="sxs-lookup"><span data-stu-id="d33bd-122">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="d33bd-123">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="d33bd-123">**Default value**</span></span>  
 <span data-ttu-id="d33bd-124">Относится только к общим наборам данных.</span><span class="sxs-lookup"><span data-stu-id="d33bd-124">For shared datasets only.</span></span>  
  
 <span data-ttu-id="d33bd-125">Установите этот флажок, чтобы задать значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d33bd-125">Select the check box to specify a default value.</span></span>  
  
 <span data-ttu-id="d33bd-126">Введите значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d33bd-126">Enter a default value.</span></span> <span data-ttu-id="d33bd-127">Это может быть статическое значение или выражение со ссылкой на какой-либо объект в отчете.</span><span class="sxs-lookup"><span data-stu-id="d33bd-127">This can be a static value or an expression that refers to an object within the report.</span></span> <span data-ttu-id="d33bd-128">В этом выражении не может быть ссылок на элементы отчета, параметры отчета или поля.</span><span class="sxs-lookup"><span data-stu-id="d33bd-128">The expression cannot refer to report items, report parameters, or fields.</span></span>  
  
 <span data-ttu-id="d33bd-129">Чтобы задать пустое значение, оставьте текстовое поле незаполненным.</span><span class="sxs-lookup"><span data-stu-id="d33bd-129">To specify a blank, leave the text box empty.</span></span>  
  
 <span data-ttu-id="d33bd-130">Чтобы задать значение NULL, выберите параметр «Допускает значение NULL».</span><span class="sxs-lookup"><span data-stu-id="d33bd-130">To specify a null, select the Nullable option.</span></span>  
  
 <span data-ttu-id="d33bd-131">**Только чтение**</span><span class="sxs-lookup"><span data-stu-id="d33bd-131">**Read Only**</span></span>  
 <span data-ttu-id="d33bd-132">Относится только к общим наборам данных.</span><span class="sxs-lookup"><span data-stu-id="d33bd-132">For shared datasets only.</span></span>  
  
 <span data-ttu-id="d33bd-133">Выберите этот вариант, чтобы отметить данный параметр в определении общего набора данных как предназначенный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d33bd-133">Select this option to mark this parameter read only in the shared dataset definition.</span></span> <span data-ttu-id="d33bd-134">После добавления общего набора данных к отчету этот параметр не появляется в свойствах.</span><span class="sxs-lookup"><span data-stu-id="d33bd-134">When the shared dataset is added to a report, the parameter does not appear in the properties.</span></span> <span data-ttu-id="d33bd-135">Если общий набор данных кэширован на сервере отчетов, то это значение изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="d33bd-135">When the shared dataset is cached on the report server, the value cannot be changed.</span></span>  
  
 <span data-ttu-id="d33bd-136">**Допускает значения NULL**</span><span class="sxs-lookup"><span data-stu-id="d33bd-136">**Nullable**</span></span>  
 <span data-ttu-id="d33bd-137">Относится только к общим наборам данных.</span><span class="sxs-lookup"><span data-stu-id="d33bd-137">For shared datasets only.</span></span>  
  
 <span data-ttu-id="d33bd-138">Выберите этот параметр, чтобы применение значения NULL стало допустимым.</span><span class="sxs-lookup"><span data-stu-id="d33bd-138">Select this option to allow a null value.</span></span>  
  
 <span data-ttu-id="d33bd-139">**Пропустить в запросе**</span><span class="sxs-lookup"><span data-stu-id="d33bd-139">**Omit From Query**</span></span>  
 <span data-ttu-id="d33bd-140">Относится только к общим наборам данных.</span><span class="sxs-lookup"><span data-stu-id="d33bd-140">For shared datasets only.</span></span>  
  
 <span data-ttu-id="d33bd-141">Выберите этот вариант, если ссылка на параметр отчета находится в выражении фильтра общего набора данных, а не в запросе.</span><span class="sxs-lookup"><span data-stu-id="d33bd-141">Select this option when a reference to a report parameter is in an expression in the shared dataset filter and not in the query.</span></span> <span data-ttu-id="d33bd-142">После выбора этого варианта отпадает необходимость задавать значение по умолчанию для данного параметра при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="d33bd-142">When you select this option, you do not need to specify a default value for this parameter when the query runs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33bd-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="d33bd-143">See Also</span></span>  
 <span data-ttu-id="d33bd-144">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="d33bd-144">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="d33bd-145">[Диалоговое окно "Свойства набора данных", построитель отчетов &#40;запросов&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d33bd-145">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="d33bd-146">[Выражения (построитель отчетов и службы SSRS)](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d33bd-146">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d33bd-147">[Учебник. Добавление параметра в отчет &#40;построитель отчетов&#41;](tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d33bd-147">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="d33bd-148">[Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="d33bd-148">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="d33bd-149">[Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d33bd-149">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d33bd-150">[Конструкторы запросов &#40;построитель отчетов&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d33bd-150">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="d33bd-151">[Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d33bd-151">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d33bd-152">Создание общего или внедренного набора данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d33bd-152">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
  
