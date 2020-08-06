---
title: Браузер ключевых показателей эффективности (вкладка «Ключевые показатели эффективности», конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpibrowserpane.f1
ms.assetid: 2f61bde6-e6ec-4511-8645-c272374014ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 591dfb7c27842e365b78484153dbbde3713b452e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656666"
---
# <a name="kpi-browser-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="d43a7-102">Браузер ключевых показателей эффективности (вкладка «Ключевые показатели эффективности», конструктор кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="d43a7-102">KPI Browser (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d43a7-103">Для просмотра и тестирования результатов ключевых показателей эффективности используется панель **Браузер ключевых показателей эффективности** на вкладке **Ключевые показатели эффективности** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="d43a7-103">Use the **KPI Browser** pane on the **KPIs** tab in Cube Designer to view and test the results of Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="d43a7-104">Прежде чем просматривать ключевые показатели эффективности, их необходимо развернуть в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] экземпляре.</span><span class="sxs-lookup"><span data-stu-id="d43a7-104">KPIs must first be deployed to a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance before browsing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d43a7-105">Данная панель отображается только в представлении браузера.</span><span class="sxs-lookup"><span data-stu-id="d43a7-105">This pane is displayed only in browser view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d43a7-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="d43a7-106">Options</span></span>  
 <span data-ttu-id="d43a7-107">**Сетка вложенного куба**</span><span class="sxs-lookup"><span data-stu-id="d43a7-107">**Subcube grid**</span></span>  
 <span data-ttu-id="d43a7-108">Используется для определения вложенного куба и ограничения результатов ключевых показателей эффективности, отображаемых на панели **Результаты** .</span><span class="sxs-lookup"><span data-stu-id="d43a7-108">Use to define a subcube and restrict the results of the KPIs to be displayed in the **Results** pane.</span></span> <span data-ttu-id="d43a7-109">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="d43a7-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="d43a7-110">**Измерение**</span><span class="sxs-lookup"><span data-stu-id="d43a7-110">**Dimension**</span></span>  
 <span data-ttu-id="d43a7-111">Выберите измерение, к которому применяется данный фильтр.</span><span class="sxs-lookup"><span data-stu-id="d43a7-111">Select the dimension to which this filter applies.</span></span>  
  
 <span data-ttu-id="d43a7-112">**Иерархия**</span><span class="sxs-lookup"><span data-stu-id="d43a7-112">**Hierarchy**</span></span>  
 <span data-ttu-id="d43a7-113">Выберите иерархию, к которой применяется данный фильтр.</span><span class="sxs-lookup"><span data-stu-id="d43a7-113">Select the hierarchy to which this filter applies.</span></span>  
  
 <span data-ttu-id="d43a7-114">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="d43a7-114">**Operator**</span></span>  
 <span data-ttu-id="d43a7-115">Выберите оператор, определяющий, как выражение в поле **Критерии фильтра** применяется к выбранной иерархии.</span><span class="sxs-lookup"><span data-stu-id="d43a7-115">Select the operator that defines how the expression in **Filter Expression** is applied to the selected hierarchy.</span></span> <span data-ttu-id="d43a7-116">Нижеприведенная таблица описывает доступные операторы.</span><span class="sxs-lookup"><span data-stu-id="d43a7-116">The following table describes the available operators.</span></span>  
  
|<span data-ttu-id="d43a7-117">Значение</span><span class="sxs-lookup"><span data-stu-id="d43a7-117">Value</span></span>|<span data-ttu-id="d43a7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d43a7-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d43a7-119">**Равно**</span><span class="sxs-lookup"><span data-stu-id="d43a7-119">**Equal**</span></span>|<span data-ttu-id="d43a7-120">Результаты ограничены набором, определенным в **Критерии фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-120">The results are restricted to the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="d43a7-121">**Не равно**</span><span class="sxs-lookup"><span data-stu-id="d43a7-121">**Not Equal**</span></span>|<span data-ttu-id="d43a7-122">Результаты ограничены элементами, исключенными набором, определенным в **Критерии фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-122">The results are restricted to the members excluded by the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="d43a7-123">**Окне**</span><span class="sxs-lookup"><span data-stu-id="d43a7-123">**In**</span></span>|<span data-ttu-id="d43a7-124">Результаты ограничены именованным набором, выбранным в **Критерии фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-124">The results are restricted to the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="d43a7-125">**Не входит**</span><span class="sxs-lookup"><span data-stu-id="d43a7-125">**Not In**</span></span>|<span data-ttu-id="d43a7-126">Результаты ограничены элементами, исключенными именованным набором, выбранным в **Критерии фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-126">The results are restricted to the members excluded by the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="d43a7-127">**Содержит**</span><span class="sxs-lookup"><span data-stu-id="d43a7-127">**Contains**</span></span>|<span data-ttu-id="d43a7-128">Результаты ограничены элементами, чьи имена содержат строку в **Критерии фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-128">The results are restricted to members whose member names contain the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="d43a7-129">**Начинается с**</span><span class="sxs-lookup"><span data-stu-id="d43a7-129">**Begins With**</span></span>|<span data-ttu-id="d43a7-130">Результаты ограничены элементами, чьи имена начинаются со строки в **Критерии фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-130">The results are restricted to members whose member names begin with the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="d43a7-131">**Диапазон (включая границы)**</span><span class="sxs-lookup"><span data-stu-id="d43a7-131">**Range (Inclusive)**</span></span>|<span data-ttu-id="d43a7-132">Результаты ограничены диапазоном, выбранным в **Критерии фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-132">The results are restricted to the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="d43a7-133">**Диапазон (исключая границы)**</span><span class="sxs-lookup"><span data-stu-id="d43a7-133">**Range (Exclusive)**</span></span>|<span data-ttu-id="d43a7-134">Результаты ограничены элементами, исключенными диапазоном, выбранным в **Критерии фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-134">The results are restricted to the members excluded by the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="d43a7-135">**MDX**</span><span class="sxs-lookup"><span data-stu-id="d43a7-135">**MDX**</span></span>|<span data-ttu-id="d43a7-136">Результаты ограничиваются многомерными выражениями, установленными в поле **Критерий фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-136">The results are restricted to the Multidimensional Expressions (MDX) expression set in **Filter Expression**.</span></span>|  
  
 <span data-ttu-id="d43a7-137">**Критерий фильтра**</span><span class="sxs-lookup"><span data-stu-id="d43a7-137">**Filter Expression**</span></span>  
 <span data-ttu-id="d43a7-138">Введите выражение, которое должен оценить **оператор**, ограничивающий результаты ключевого показателя эффективности для просмотра.</span><span class="sxs-lookup"><span data-stu-id="d43a7-138">Type the expression that is to be evaluated by **Operator**, which restricts the KPI results to be browsed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d43a7-139">Это поле — динамический элемент ввода данных, меняющийся, чтобы отражать типы данных, необходимые для выбранного оператора.</span><span class="sxs-lookup"><span data-stu-id="d43a7-139">This field is a dynamic data entry element, changing appearance to reflect the types of data necessary for the selected operator.</span></span>  
  
 <span data-ttu-id="d43a7-140">**Сетка результатов**</span><span class="sxs-lookup"><span data-stu-id="d43a7-140">**Results grid**</span></span>  
 <span data-ttu-id="d43a7-141">Отображает оцененное значение, целевое значение, состояние и тренд для ключевых показателей эффективности на основании фильтра, определенного в поле **Сетка фильтра**.</span><span class="sxs-lookup"><span data-stu-id="d43a7-141">Displays the evaluated value, goal, status, and trend for the KPIs, based on the filter defined in **Filter grid**.</span></span> <span data-ttu-id="d43a7-142">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="d43a7-142">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="d43a7-143">**Отобразить структуру**</span><span class="sxs-lookup"><span data-stu-id="d43a7-143">**Display Structure**</span></span>  
 <span data-ttu-id="d43a7-144">Отображает ключевые показатели эффективности, содержащиеся в кубе, иерархически организованные в соответствии со значениями полей **Отображать папку** или **Родительский ключевой показатель эффективности** для каждого ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="d43a7-144">Displays the KPIs contained by the cube, hierarchically organized according to the **Display folder** or **Parent KPI** values for each KPI.</span></span>  
  
 <span data-ttu-id="d43a7-145">**Значение**</span><span class="sxs-lookup"><span data-stu-id="d43a7-145">**Value**</span></span>  
 <span data-ttu-id="d43a7-146">Показывает значение ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="d43a7-146">Displays the value of the KPI.</span></span>  
  
 <span data-ttu-id="d43a7-147">**Goal**</span><span class="sxs-lookup"><span data-stu-id="d43a7-147">**Goal**</span></span>  
 <span data-ttu-id="d43a7-148">Показывает целевое значение ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="d43a7-148">Displays the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="d43a7-149">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="d43a7-149">**Status**</span></span>  
 <span data-ttu-id="d43a7-150">Показывает график состояния ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="d43a7-150">Displays the status graphic of the KPI.</span></span>  
  
 <span data-ttu-id="d43a7-151">**Тренд**</span><span class="sxs-lookup"><span data-stu-id="d43a7-151">**Trend**</span></span>  
 <span data-ttu-id="d43a7-152">Показывает график тренда ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="d43a7-152">Displays the trend graphic of the KPI.</span></span>  
  
 <span data-ttu-id="d43a7-153">**Weight**</span><span class="sxs-lookup"><span data-stu-id="d43a7-153">**Weight**</span></span>  
 <span data-ttu-id="d43a7-154">Показывает весовой коэффициент ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="d43a7-154">Displays the weight factor of the KPI.</span></span>  
  
 <span data-ttu-id="d43a7-155">**Nописание**</span><span class="sxs-lookup"><span data-stu-id="d43a7-155">**(Description)**</span></span>  
 <span data-ttu-id="d43a7-156">Отображает значок информации, если для ключевого показателя эффективности имеется описание.</span><span class="sxs-lookup"><span data-stu-id="d43a7-156">Displays an information icon if a description is provided for a KPI.</span></span>  
  
 <span data-ttu-id="d43a7-157">Наведите курсор мыши на значок информации для отображения всплывающей подсказки, содержащей описание для ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="d43a7-157">Hover the mouse over the information icon to display a ToolTip containing the description for the KPI.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d43a7-158">Если при вычислении ключевого показателя эффективности для экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] возникает ошибка, то эта настройка отображает сведения, связанные с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d43a7-158">If an error occurs while calculating a KPI on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, this option displays information associated with the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d43a7-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="d43a7-159">See Also</span></span>  
 [<span data-ttu-id="d43a7-160">Ключевые показатели эффективности &#40;конструктора кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d43a7-160">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
