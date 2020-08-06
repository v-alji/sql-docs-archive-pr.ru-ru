---
title: Определение новых мер (мастер кубов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubewizard.definenewmeasures.f1
ms.assetid: f97698f8-6f0f-49d8-86b0-5bfac3c4e627
author: minewiskan
ms.author: owend
ms.openlocfilehash: a568cee2c989e24d603f5655ec4ca33faeac5358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734570"
---
# <a name="define-new-measures-cube-wizard"></a><span data-ttu-id="8fb97-102">Определить новые меры (мастер кубов)</span><span class="sxs-lookup"><span data-stu-id="8fb97-102">Define New Measures (Cube Wizard)</span></span>
  <span data-ttu-id="8fb97-103">Используйте страницу **Определение новых мер** для создания новых мер куба, созданного без использования источника данных.</span><span class="sxs-lookup"><span data-stu-id="8fb97-103">Use the **Define New Measures** page to create new measures for a cube that is being created without using a data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fb97-104">Эта страница появляется, только если на странице **Выбор метода создания** выбран параметр **Создать таблицы в источнике данных** .</span><span class="sxs-lookup"><span data-stu-id="8fb97-104">This page will appear only if you have selected **Generate tables in the data source** on the **Select Creation Method** page.</span></span>  
  
## <a name="select-measures-from-template-options"></a><span data-ttu-id="8fb97-105">Выберите меры из шаблона «Параметры»</span><span class="sxs-lookup"><span data-stu-id="8fb97-105">Select measures from template Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fb97-106">Параметры, перечисленные в этом разделе, отображаются, только если на странице **Выбор метода создания** на панели **Шаблон** выбран какой-либо шаблон.</span><span class="sxs-lookup"><span data-stu-id="8fb97-106">The options listed in this section will appear only if you have selected a template from **Template** on the **Select Creation Method** page.</span></span>  
  
 <span data-ttu-id="8fb97-107">**Выбрать меры из шаблона**</span><span class="sxs-lookup"><span data-stu-id="8fb97-107">**Select measures from template**</span></span>  
 <span data-ttu-id="8fb97-108">Выводит на экран меру из шаблона куба для включения в куб.</span><span class="sxs-lookup"><span data-stu-id="8fb97-108">Displays the measures from the cube template to include in the cube.</span></span>  
  
 <span data-ttu-id="8fb97-109">(Столбец с флажками)</span><span class="sxs-lookup"><span data-stu-id="8fb97-109">(Column with check boxes)</span></span>  
 <span data-ttu-id="8fb97-110">Выберите для включения меры из шаблона в куб.</span><span class="sxs-lookup"><span data-stu-id="8fb97-110">Select to include a measure from the template in the cube.</span></span>  
  
 <span data-ttu-id="8fb97-111">Для включения специальной меры из шаблона установите флажок для этой меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-111">To include a specific measure from the template, select the check box for that measure.</span></span>  
  
 <span data-ttu-id="8fb97-112">Для включения всех мер из шаблона в куб установите флажок в заголовке.</span><span class="sxs-lookup"><span data-stu-id="8fb97-112">To include all measures from the template in the cube, select the check box in the header.</span></span>  
  
 <span data-ttu-id="8fb97-113">**Имя меры**</span><span class="sxs-lookup"><span data-stu-id="8fb97-113">**Measure Name**</span></span>  
 <span data-ttu-id="8fb97-114">Выводит список мер, доступных в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="8fb97-114">Lists the measures that are available in the template.</span></span>  
  
 <span data-ttu-id="8fb97-115">Для переименования меры нажмите меру и введите новое имя.</span><span class="sxs-lookup"><span data-stu-id="8fb97-115">To rename a measure, click on that measure and type a new name.</span></span>  
  
 <span data-ttu-id="8fb97-116">**Группа мер**</span><span class="sxs-lookup"><span data-stu-id="8fb97-116">**Measure Group**</span></span>  
 <span data-ttu-id="8fb97-117">Перечисляет группы мер для меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-117">Lists the measure group for the measure.</span></span>  
  
 <span data-ttu-id="8fb97-118">Чтобы изменить группу мер, нажмите ее, а затем введите новую группу мер или выберите уже существующую из списка.</span><span class="sxs-lookup"><span data-stu-id="8fb97-118">To change the measure group, click on the measure group, and then either enter a new measure group or select an existing measure group from the list.</span></span>  
  
 <span data-ttu-id="8fb97-119">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8fb97-119">**Data Type**</span></span>  
 <span data-ttu-id="8fb97-120">Перечисляет типы данных для меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-120">Lists the data type for the measure.</span></span>  
  
 <span data-ttu-id="8fb97-121">Чтобы изменить тип данных, нажмите тип данных, а затем выберите тип данных из списка.</span><span class="sxs-lookup"><span data-stu-id="8fb97-121">To change the data type, click on the data type, and then select a data type from the list.</span></span>  
  
 <span data-ttu-id="8fb97-122">**Статистической обработки**</span><span class="sxs-lookup"><span data-stu-id="8fb97-122">**Aggregation**</span></span>  
 <span data-ttu-id="8fb97-123">Перечисляет статистические функции для меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-123">Lists the aggregation for the measure.</span></span>  
  
 <span data-ttu-id="8fb97-124">Чтобы изменить статистическую функцию, выберите ее, а затем выберите тип данных из списка.</span><span class="sxs-lookup"><span data-stu-id="8fb97-124">To change the aggregation, click on the aggregation, and then select a data type from the list.</span></span>  
  
## <a name="add-new-measures-options"></a><span data-ttu-id="8fb97-125">Добавить новую меру мер</span><span class="sxs-lookup"><span data-stu-id="8fb97-125">Add new measures Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fb97-126">Параметры, перечисленные в этом разделе, всегда отображаются на странице **Определение новых мер** .</span><span class="sxs-lookup"><span data-stu-id="8fb97-126">The options listed in this section always appear on the **Define New Measures** page.</span></span>  
  
 <span data-ttu-id="8fb97-127">**Добавить новые меры**</span><span class="sxs-lookup"><span data-stu-id="8fb97-127">**Add new measures**</span></span>  
 <span data-ttu-id="8fb97-128">Показывает и позволяет определить дополнительные меры для включения в куб.</span><span class="sxs-lookup"><span data-stu-id="8fb97-128">Displays and allows you to define additional measures to be included in the cube.</span></span>  
  
 <span data-ttu-id="8fb97-129">**Имя меры**</span><span class="sxs-lookup"><span data-stu-id="8fb97-129">**Measure Name**</span></span>  
 <span data-ttu-id="8fb97-130">Перечисляет новые меры для включения в куб.</span><span class="sxs-lookup"><span data-stu-id="8fb97-130">Lists the new measures to be included in the cube.</span></span>  
  
 <span data-ttu-id="8fb97-131">Для добавления новых мер щелкните **Добавить новую меру**и введите имя новой меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-131">To add a new measure, click **Add new measure**, and then type the name of the new measure.</span></span>  
  
 <span data-ttu-id="8fb97-132">**Группа мер**</span><span class="sxs-lookup"><span data-stu-id="8fb97-132">**Measure Group**</span></span>  
 <span data-ttu-id="8fb97-133">Перечисляет группы мер для меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-133">Lists the measure group for the measure.</span></span>  
  
 <span data-ttu-id="8fb97-134">Чтобы изменить группу мер, нажмите ее, а затем введите новую группу мер или выберите уже существующую из списка.</span><span class="sxs-lookup"><span data-stu-id="8fb97-134">To change the measure group, click on the measure group, and then either enter a new measure group or select an existing measure group from the list.</span></span>  
  
 <span data-ttu-id="8fb97-135">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8fb97-135">**Data Type**</span></span>  
 <span data-ttu-id="8fb97-136">Перечисляет типы данных для меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-136">Lists the data type for the measure.</span></span>  
  
 <span data-ttu-id="8fb97-137">Чтобы изменить тип данных, нажмите тип данных, а затем выберите тип данных из списка.</span><span class="sxs-lookup"><span data-stu-id="8fb97-137">To change the data type, click on the data type, and then select a data type from the list.</span></span>  
  
 <span data-ttu-id="8fb97-138">**Статистической обработки**</span><span class="sxs-lookup"><span data-stu-id="8fb97-138">**Aggregation**</span></span>  
 <span data-ttu-id="8fb97-139">Перечисляет статистические функции для меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-139">Lists the aggregation for the measure.</span></span>  
  
 <span data-ttu-id="8fb97-140">Чтобы изменить статистическую функцию, выберите ее, а затем выберите тип данных из списка.</span><span class="sxs-lookup"><span data-stu-id="8fb97-140">To change the aggregation, click on the aggregation, and then select a data type from the list.</span></span>  
  
 <span data-ttu-id="8fb97-141">**X**</span><span class="sxs-lookup"><span data-stu-id="8fb97-141">**X**</span></span>  
 <span data-ttu-id="8fb97-142">Удаляет новую меру из куба.</span><span class="sxs-lookup"><span data-stu-id="8fb97-142">Deletes the new measure from the cube.</span></span>  
  
 <span data-ttu-id="8fb97-143">Для удаления новой меры из куба нажмите кнопку **X** для этой меры.</span><span class="sxs-lookup"><span data-stu-id="8fb97-143">To remove a new measure from the cube, click the **X** button for that measure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb97-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="8fb97-144">See Also</span></span>  
 <span data-ttu-id="8fb97-145">[Справка F1 мастера кубов](cube-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="8fb97-145">[Cube Wizard F1 Help](cube-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="8fb97-146">[Объекты куба &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8fb97-146">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="8fb97-147">[Кубы в многомерных моделях](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="8fb97-147">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="8fb97-148">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="8fb97-148">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
