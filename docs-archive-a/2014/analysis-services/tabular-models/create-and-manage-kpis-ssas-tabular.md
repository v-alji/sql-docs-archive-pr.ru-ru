---
title: Создание ключевых показателей эффективности и управление ими (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.kpi.f1
ms.assetid: c96026c2-4394-4c3c-986b-4c95a4421900
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8e9d7ef77939efe407ed6ab0d725a6d788c58b49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657924"
---
# <a name="create-and-manage-kpis-ssas-tabular"></a><span data-ttu-id="46299-102">Создание ключевых показателей эффективности и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="46299-102">Create and Manage KPIs (SSAS Tabular)</span></span>
  <span data-ttu-id="46299-103">В этом разделе описывается создание, изменение и удаление ключевого показателя эффективности (KPI) в табличной модели.</span><span class="sxs-lookup"><span data-stu-id="46299-103">This topic describes how to create, edit, or delete a KPI (Key Performance Indicator) in a tabular model.</span></span> <span data-ttu-id="46299-104">Чтобы создать ключевой показатель эффективности, выберите меру, результатом которой является базовое значение ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="46299-104">To create a KPI, you select a measure that evaluates to the KPI's Base value.</span></span> <span data-ttu-id="46299-105">Затем в диалоговом окне «Ключевой показатель эффективности» необходимо выбрать вторую меру или абсолютное значение, на основании которого будет вычисляться целевое значение.</span><span class="sxs-lookup"><span data-stu-id="46299-105">You then use the Key Performance Indicator dialog box to select a second measure or an absolute value that evaluates to a target value.</span></span> <span data-ttu-id="46299-106">Затем можно определить пороговые значения состояний, которые определяют эффективность между базовой и целевой мерами.</span><span class="sxs-lookup"><span data-stu-id="46299-106">You can then define status thresholds that measure the performance between the Base and Target measures.</span></span>  
  
 <span data-ttu-id="46299-107">В этот раздел включены следующее задачи:</span><span class="sxs-lookup"><span data-stu-id="46299-107">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="46299-108">Создание ключевого показателя эффективности</span><span class="sxs-lookup"><span data-stu-id="46299-108">To create a KPI</span></span>](#bkmk_create_KPI)  
  
-   [<span data-ttu-id="46299-109">Изменение ключевого показателя эффективности</span><span class="sxs-lookup"><span data-stu-id="46299-109">To edit a KPI</span></span>](#bkmk_edit_KPI)  
  
-   [<span data-ttu-id="46299-110">Удаление ключевого показателя эффективности и базовой меры</span><span class="sxs-lookup"><span data-stu-id="46299-110">To delete a KPI and the base measure</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="46299-111">Удаление ключевого показателя эффективности с сохранением базовой меры</span><span class="sxs-lookup"><span data-stu-id="46299-111">To delete a KPI, but keep the base measure</span></span>](#bkmk_delete_KPI)  
  
## <a name="tasks"></a><span data-ttu-id="46299-112">Задания</span><span class="sxs-lookup"><span data-stu-id="46299-112">Tasks</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="46299-113">Перед тем как создать ключевой показатель эффективности, необходимо создать базовую меру, оценивающую значение.</span><span class="sxs-lookup"><span data-stu-id="46299-113">Before creating a KPI, you must first create a Base measure that evaluates to value.</span></span> <span data-ttu-id="46299-114">Затем базовую меру можно расширить до ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="46299-114">You then extend the Base measure to a KPI.</span></span> <span data-ttu-id="46299-115">Процесс создания меры описывается в разделе [Создание мер и управление ими (табличные службы SSAS)](measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="46299-115">How to create measures are described in another topic, [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md).</span></span> <span data-ttu-id="46299-116">Для KPI необходимо целевое значение.</span><span class="sxs-lookup"><span data-stu-id="46299-116">A KPI also requires a target value.</span></span> <span data-ttu-id="46299-117">В качестве этого значения можно использовать другую, определенную ранее меру или абсолютное значение.</span><span class="sxs-lookup"><span data-stu-id="46299-117">This value can be from another pre-defined measure or an absolute value.</span></span> <span data-ttu-id="46299-118">После расширения базовой меры до KPI можно выбрать целевое значение и определить пороги состояния в диалоговом окне ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="46299-118">Once you have extended a Base measure to a KPI, you can then select the target value and define status thresholds in the Key Performance Indicator dialog box.</span></span>  
  
###  <a name="to-create-a-kpi"></a><a name="bkmk_create_KPI"></a> <span data-ttu-id="46299-119">Создание ключевого показателя эффективности</span><span class="sxs-lookup"><span data-stu-id="46299-119">To create a KPI</span></span>  
  
1.  <span data-ttu-id="46299-120">В сетке мер щелкните правой кнопкой мыши меру, которая будет являться базовой (значение), а затем выберите пункт **Создать ключевой показатель эффективности**.</span><span class="sxs-lookup"><span data-stu-id="46299-120">In the measure grid, right-click the measure that will serve as the Base measure (value), and then click **Create KPI**.</span></span>  
  
2.  <span data-ttu-id="46299-121">В диалоговом окне **Ключевой показатель эффективности** в поле **Определение целевого значения**выберите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="46299-121">In the **Key Performance Indicator** dialog box, in **Define target value**, select from one of the following:</span></span>  
  
     <span data-ttu-id="46299-122">Выберите пункт **Мера**, а затем выберите целевую меру из списка.</span><span class="sxs-lookup"><span data-stu-id="46299-122">Select **Measure**, and then select a target measure from the listbox.</span></span>  
  
     <span data-ttu-id="46299-123">Выберите **Абсолютное значение**и введите числовое значение.</span><span class="sxs-lookup"><span data-stu-id="46299-123">Select **Absolute value**, and then type a numerical value.</span></span>  
  
3.  <span data-ttu-id="46299-124">В окне **Определение состояния порогов**установите значения нижнего и верхнего порогов.</span><span class="sxs-lookup"><span data-stu-id="46299-124">In **Define status thresholds**, click and slide the low and high threshold values.</span></span>  
  
4.  <span data-ttu-id="46299-125">В окне **Выбор стиля значка**выберите тип изображения.</span><span class="sxs-lookup"><span data-stu-id="46299-125">In **Select icon style**, click an image type.</span></span>  
  
5.  <span data-ttu-id="46299-126">Нажмите кнопку **Описания**и введите описания для ключевого показателя эффективности, «Значения», «Состояния» и «Цели».</span><span class="sxs-lookup"><span data-stu-id="46299-126">Click on **Descriptions**, and then type descriptions for KPI, Value, Status, and Target.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="46299-127">Проверить ключевой показатель эффективности можно с помощью функции анализа в Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="46299-127">You can use the Analyze in Excel feature to test your KPI.</span></span> <span data-ttu-id="46299-128">Дополнительные сведения см. далее в подразделе [Анализ в Excel (табличные службы SSAS)](analyze-in-excel-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="46299-128">For more information, see [Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md).</span></span>  
  
###  <a name="to-edit-a-kpi"></a><a name="bkmk_edit_KPI"></a> <span data-ttu-id="46299-129">Изменение ключевого показателя эффективности</span><span class="sxs-lookup"><span data-stu-id="46299-129">To edit a KPI</span></span>  
  
-   <span data-ttu-id="46299-130">В сетке мер щелкните правой кнопкой мыши меру, являющуюся базовой мерой (значением) ключевого показателя эффективности, и выберите пункт **Изменить параметры ключевого показателя эффективности**.</span><span class="sxs-lookup"><span data-stu-id="46299-130">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Edit KPI Settings**.</span></span>  
  
###  <a name="to-delete-a-kpi-and-the-base-measure"></a><a name="bkmk_delete"></a> <span data-ttu-id="46299-131">Удаление ключевого показателя эффективности и базовой меры</span><span class="sxs-lookup"><span data-stu-id="46299-131">To delete a KPI and the base measure</span></span>  
  
-   <span data-ttu-id="46299-132">В сетке мер щелкните правой кнопкой мыши меру, являющуюся базовой мерой (значением) ключевого показателя эффективности, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="46299-132">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete**.</span></span>  
  
###  <a name="to-delete-a-kpi-but-keep-the-base-measure"></a><a name="bkmk_delete_KPI"></a><span data-ttu-id="46299-133">Удаление ключевого показателя эффективности без сохранения базовой меры</span><span class="sxs-lookup"><span data-stu-id="46299-133">To delete a KPI, but keep the base measure</span></span>  
  
-   <span data-ttu-id="46299-134">В сетке мер щелкните правой кнопкой мыши меру, являющуюся базовой мерой (значением) ключевого показателя эффективности, и выберите пункт **Удалить ключевой показатель эффективности**.</span><span class="sxs-lookup"><span data-stu-id="46299-134">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete KPI**.</span></span>  
  
## <a name="alt-shortcuts"></a><span data-ttu-id="46299-135">Сочетания клавиш с ALT</span><span class="sxs-lookup"><span data-stu-id="46299-135">ALT Shortcuts</span></span>  
  
|<span data-ttu-id="46299-136">Раздел пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="46299-136">UI section</span></span>|<span data-ttu-id="46299-137">Команда клавиши</span><span class="sxs-lookup"><span data-stu-id="46299-137">Key command</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="46299-138">Базовая мера ключевого показателя эффективности</span><span class="sxs-lookup"><span data-stu-id="46299-138">KPI base measure</span></span>|<span data-ttu-id="46299-139">ALT+B</span><span class="sxs-lookup"><span data-stu-id="46299-139">ALT+B</span></span>|  
|<span data-ttu-id="46299-140">Состояние ключевого показателя эффективности</span><span class="sxs-lookup"><span data-stu-id="46299-140">KPI Status</span></span>|<span data-ttu-id="46299-141">ALT + S</span><span class="sxs-lookup"><span data-stu-id="46299-141">ALT+S</span></span>|  
|<span data-ttu-id="46299-142">Measure</span><span class="sxs-lookup"><span data-stu-id="46299-142">Measure</span></span>|<span data-ttu-id="46299-143">ALT+M</span><span class="sxs-lookup"><span data-stu-id="46299-143">ALT+M</span></span>|  
|<span data-ttu-id="46299-144">Абсолютное значение</span><span class="sxs-lookup"><span data-stu-id="46299-144">Absolute value</span></span>|<span data-ttu-id="46299-145">ALT+A</span><span class="sxs-lookup"><span data-stu-id="46299-145">ALT+A</span></span>|  
|<span data-ttu-id="46299-146">Определение состояния порогов</span><span class="sxs-lookup"><span data-stu-id="46299-146">Define status thresholds</span></span>|<span data-ttu-id="46299-147">ALT+U</span><span class="sxs-lookup"><span data-stu-id="46299-147">ALT+U</span></span>|  
|<span data-ttu-id="46299-148">Выбор стиля значка</span><span class="sxs-lookup"><span data-stu-id="46299-148">Select icon style</span></span>|<span data-ttu-id="46299-149">ALT+I</span><span class="sxs-lookup"><span data-stu-id="46299-149">ALT+I</span></span>|  
|<span data-ttu-id="46299-150">Тренд</span><span class="sxs-lookup"><span data-stu-id="46299-150">Trend</span></span>|<span data-ttu-id="46299-151">ALT+T</span><span class="sxs-lookup"><span data-stu-id="46299-151">ALT+T</span></span>|  
|<span data-ttu-id="46299-152">Описания</span><span class="sxs-lookup"><span data-stu-id="46299-152">Descriptions</span></span>|<span data-ttu-id="46299-153">ALT+D</span><span class="sxs-lookup"><span data-stu-id="46299-153">ALT+D</span></span>|  
|<span data-ttu-id="46299-154">Тренд</span><span class="sxs-lookup"><span data-stu-id="46299-154">Trend</span></span>|<span data-ttu-id="46299-155">ALT+T</span><span class="sxs-lookup"><span data-stu-id="46299-155">ALT+T</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46299-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="46299-156">See Also</span></span>  
 <span data-ttu-id="46299-157">[Ключевые показатели эффективности &#40;табличные&#41;SSAS](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="46299-157">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 <span data-ttu-id="46299-158">[Меры &#40;табличных&#41;SSAS](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="46299-158">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="46299-159">Создание мер и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="46299-159">Create and Manage Measures &#40;SSAS Tabular&#41;</span></span>](create-and-manage-measures-ssas-tabular.md)  
  
  
