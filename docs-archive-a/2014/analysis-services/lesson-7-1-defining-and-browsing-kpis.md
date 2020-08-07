---
title: Определение и просмотр ключевых показателей эффективности | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 648b9a02-1278-4f11-b940-6f0de6a4042d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44febe6c6c5d432f0cdee43e8eaaa3401c54a2c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731041"
---
# <a name="defining-and-browsing-kpis"></a><span data-ttu-id="28075-102">Определение и поиск ключевых показателей эффективности</span><span class="sxs-lookup"><span data-stu-id="28075-102">Defining and Browsing KPIs</span></span>
  <span data-ttu-id="28075-103">Чтобы определить ключевые показатели эффективности, сначала задается имя показателя и группа мер, с которой он будет связан.</span><span class="sxs-lookup"><span data-stu-id="28075-103">To define key performance indicators (KPIs), you first define a KPI name and the measure group to which the KPI is associated.</span></span> <span data-ttu-id="28075-104">Ключевой показатель эффективности может быть связан со всеми группами мер или с одной из них.</span><span class="sxs-lookup"><span data-stu-id="28075-104">A KPI can be associated with all measure groups or with a single measure group.</span></span> <span data-ttu-id="28075-105">Затем предстоит определить следующие элементы ключевого показателя эффективности:</span><span class="sxs-lookup"><span data-stu-id="28075-105">You then define the following elements of the KPI:</span></span>

-   <span data-ttu-id="28075-106">Выражение значения</span><span class="sxs-lookup"><span data-stu-id="28075-106">The value expression</span></span>

     <span data-ttu-id="28075-107">Выражение значения представляет собой физическая мера (например, «Продажи»), вычисляемая мера (такая как «Прибыль») или вычисление, которое определено в ключевом показателе эффективности с использованием многомерного выражения.</span><span class="sxs-lookup"><span data-stu-id="28075-107">A value expression is a physical measure such as Sales, a calculated measure such as Profit, or a calculation that is defined within the KPI by using a Multidimensional Expressions (MDX) expression.</span></span>

-   <span data-ttu-id="28075-108">Целевое выражение</span><span class="sxs-lookup"><span data-stu-id="28075-108">The goal expression</span></span>

     <span data-ttu-id="28075-109">Целевое выражение представляет собой константу или многомерное выражение, результатом которого является значение, определяющее цель для меры, которая определяется выражением значения.</span><span class="sxs-lookup"><span data-stu-id="28075-109">A goal expression is a value, or an MDX expression that resolves to a value, that defines the target for the measure that the value expression defines.</span></span> <span data-ttu-id="28075-110">Например, целевое выражение может быть суммой, на которую руководство предприятия хотело бы увеличить продажи или прибыль.</span><span class="sxs-lookup"><span data-stu-id="28075-110">For example, a goal expression could be the amount by which the business managers of a company want to increase sales or profit.</span></span>

-   <span data-ttu-id="28075-111">Выражение состояния</span><span class="sxs-lookup"><span data-stu-id="28075-111">The status expression</span></span>

     <span data-ttu-id="28075-112">Выражение состояния является многомерным выражением, в результате вычисления которого службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] возвращают текущее состояние выражения значения относительно целевого выражения.</span><span class="sxs-lookup"><span data-stu-id="28075-112">A status expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current status of the value expression compared to the goal expression.</span></span> <span data-ttu-id="28075-113">Целевое значение представляет собой нормализованное значение в диапазоне от -1 до +1 (-1 — очень плохо, а +1 — очень хорошо).</span><span class="sxs-lookup"><span data-stu-id="28075-113">A goal expression is a normalized value in the range of -1 to +1, where -1 is very bad, and +1 is very good.</span></span> <span data-ttu-id="28075-114">Выражение состояния отображается в графическом виде, позволяя легко определить состояние выражения значения относительно целевого выражения.</span><span class="sxs-lookup"><span data-stu-id="28075-114">The status expression displays a graphic to help you easily determine the status of the value expression compared to the goal expression.</span></span>

-   <span data-ttu-id="28075-115">Выражение тренда</span><span class="sxs-lookup"><span data-stu-id="28075-115">The trend expression</span></span>

     <span data-ttu-id="28075-116">Выражение тренда является многомерным выражением, которое используется в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для вычисления текущего тренда (тенденции к увеличению или уменьшению) выражения значения по сравнению с целевым выражением.</span><span class="sxs-lookup"><span data-stu-id="28075-116">A trend expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current trend of the value expression compared to the goal expression.</span></span> <span data-ttu-id="28075-117">Выражение тренда помогает пользователю быстро определить, улучшается или ухудшается выражение значения относительно целевого выражения.</span><span class="sxs-lookup"><span data-stu-id="28075-117">The trend expression helps the business user to quickly determine whether the value expression is becoming better or worse relative to the goal expression.</span></span> <span data-ttu-id="28075-118">С выражением тренда может быть связано одно или несколько графических изображений, что помогает пользователям быстро понять текущий тренд.</span><span class="sxs-lookup"><span data-stu-id="28075-118">You can associate one of several graphics with the trend expression to help business users be able to quickly understand the trend.</span></span>

 <span data-ttu-id="28075-119">В дополнение к перечисленным элементам, которые указываются для ключевого показателя эффективности, можно настроить несколько свойств ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="28075-119">In addition to these elements that you define for a KPI, you also define several properties of a KPI.</span></span> <span data-ttu-id="28075-120">К этим свойствам относятся папка отображения, родительский ключевой показатель эффективности, если показатель вычисляется по данным других показателей, текущий элемент времени (при его наличии), вес показателя (при его наличии), а также описание показателя.</span><span class="sxs-lookup"><span data-stu-id="28075-120">These properties include a display folder, a parent KPI if the KPI is computed from other KPIs, the current time member if there is one, the weight of the KPI if it has one, and a description of the KPI.</span></span>

> [!NOTE]
>  <span data-ttu-id="28075-121">Другие примеры ключевых показателей эффективности см. на вкладке "Шаблоны" панели "Средства вычисления" или в примерах для образца хранилища данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="28075-121">For more examples of KPIs, see the KPI examples on the Templates tab in the Calculation Tools pane or in the examples in the **Adventure Works DW 2012** sample data warehouse.</span></span> <span data-ttu-id="28075-122">Дополнительные сведения об установке этой базы данных см. в разделе [Установка образцов данных и проектов для учебника по многомерному моделированию в службах Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="28075-122">For more information about how to install this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

 <span data-ttu-id="28075-123">В задачах этого занятия будут определены ключевые показатели эффективности в проекте [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial и выполнен их просмотр в кубе [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="28075-123">In the task in this lesson, you define  KPIs in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, and you then browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube by using these KPIs.</span></span> <span data-ttu-id="28075-124">Будут определены следующие ключевые показатели эффективности.</span><span class="sxs-lookup"><span data-stu-id="28075-124">You will define the following KPIs:</span></span>

-   <span data-ttu-id="28075-125">Доход от продаж через торгового посредника</span><span class="sxs-lookup"><span data-stu-id="28075-125">Reseller Revenue</span></span>

     <span data-ttu-id="28075-126">С помощью этого показателя можно оценить, как фактический товарооборот посредников соотносится с квотами на продажи через посредников, как близко находится достигнутый объем продаж к целевому и каков тренд достижения цели.</span><span class="sxs-lookup"><span data-stu-id="28075-126">This KPI is used to measure how actual reseller sales compare to sales quotas for reseller sales, how close the sales are to the goal, and what the trend is toward reaching the goal.</span></span>

-   <span data-ttu-id="28075-127">Коэффициент общей валовой прибыли продукта</span><span class="sxs-lookup"><span data-stu-id="28075-127">Product Gross Profit Margin</span></span>

     <span data-ttu-id="28075-128">Этот ключевой показатель эффективности показывает, насколько близок коэффициент общей валовой прибыли для каждого продукта к целевой границе, а также показывает тренд достижения этой цели.</span><span class="sxs-lookup"><span data-stu-id="28075-128">This KPI is used to determine how close the gross profit margin is for each product category to a specified goal for each product category, and also to determine the trend toward reaching this goal.</span></span>

## <a name="defining-the-reseller-revenue-kpi"></a><span data-ttu-id="28075-129">Определение ключевого показателя эффективности «Доход от продаж через торгового посредника»</span><span class="sxs-lookup"><span data-stu-id="28075-129">Defining the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="28075-130">Откройте в конструкторе кубов куб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial и перейдите на вкладку **Ключевые показатели эффективности** .</span><span class="sxs-lookup"><span data-stu-id="28075-130">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **KPIs** tab.</span></span>

     <span data-ttu-id="28075-131">Вкладка **Ключевые показатели эффективности** содержит несколько панелей.</span><span class="sxs-lookup"><span data-stu-id="28075-131">The **KPIs** tab includes several panes.</span></span> <span data-ttu-id="28075-132">В левой части вкладки расположены панели **Организатор ключевых показателей эффективности** и **Средства вычисления** .</span><span class="sxs-lookup"><span data-stu-id="28075-132">On the left side of the tab are the **KPI Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="28075-133">Панель отображения в центре вкладки содержит подробные сведения о показателе, выбранном на панели **Организатор ключевых показателей эффективности** .</span><span class="sxs-lookup"><span data-stu-id="28075-133">The display pane in the middle of the tab contains the details of the KPI that is selected in the **KPI Organizer** pane.</span></span>

     <span data-ttu-id="28075-134">На рисунке ниже показана вкладка **Ключевые показатели эффективности** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="28075-134">The following image shows the **KPIs** tab of Cube Designer.</span></span>

     <span data-ttu-id="28075-135">![Вкладка «Ключевые показатели эффективности» конструктора кубов](../../2014/tutorials/media/l7-kpi-1.gif "Вкладка «Ключевые показатели эффективности» конструктора кубов")</span><span class="sxs-lookup"><span data-stu-id="28075-135">![KPIs tab of Cube Designer](../../2014/tutorials/media/l7-kpi-1.gif "KPIs tab of Cube Designer")</span></span>

2.  <span data-ttu-id="28075-136">На панели инструментов вкладки **Ключевые показатели эффективности** нажмите кнопку **Создать ключевой показатель** .</span><span class="sxs-lookup"><span data-stu-id="28075-136">On the toolbar of the **KPIs** tab, click the **New KPI** button.</span></span>

     <span data-ttu-id="28075-137">На панели отображения будет выведен пустой шаблон показателя, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="28075-137">A blank KPI template appears in the display pane, as shown in the following image.</span></span>

     <span data-ttu-id="28075-138">![Пустой шаблон ключевого показателя эффективности на панели](../../2014/tutorials/media/l7-kpi-2.gif "Пустой шаблон ключевого показателя эффективности на панели")</span><span class="sxs-lookup"><span data-stu-id="28075-138">![Blank KPI template in display pane](../../2014/tutorials/media/l7-kpi-2.gif "Blank KPI template in display pane")</span></span>

3.  <span data-ttu-id="28075-139">В поле **имя** введите `Reseller Revenue` , а затем выберите **Sales торгового посредника** в списке **связанная группа мер** .</span><span class="sxs-lookup"><span data-stu-id="28075-139">In the **Name** box, type `Reseller Revenue`, and then select **Reseller Sales** in the **Associated measure group** list.</span></span>

4.  <span data-ttu-id="28075-140">На вкладке **Метаданные** панели **Средства вычисления** раскройте узлы **Меры**и **Товарооборот посредника**и перетащите меру **Товарооборот посредников — объем продаж** в поле **Выражение значения** .</span><span class="sxs-lookup"><span data-stu-id="28075-140">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Reseller Sales**, and then drag the **Reseller Sales-Sales Amount** measure to the **Value Expression** box.</span></span>

5.  <span data-ttu-id="28075-141">На вкладке **Метаданные** панели **Средства вычисления** раскройте узлы **Меры**и **Квоты продаж**и перетащите меру **Квота объемов продаж** в поле **Целевое выражение** .</span><span class="sxs-lookup"><span data-stu-id="28075-141">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Sales Quotas**, and then drag the **Sales Amount Quota** measure to the **Goal Expression** box.</span></span>

6.  <span data-ttu-id="28075-142">Убедитесь в том, что в списке **Признак состояния** выбрано значение **Шкала** , и введите в поле **Выражение состояния** следующее многомерное выражение:</span><span class="sxs-lookup"><span data-stu-id="28075-142">Verify that **Gauge** is selected in the **Status indicator** list, and then type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
     When 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.95
       Then 1
     When
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")<.95
       And 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.85
       Then 0
      Else-1
    End
    ```

     <span data-ttu-id="28075-143">Многомерное выражение служит основой оценки достижения целевого значения.</span><span class="sxs-lookup"><span data-stu-id="28075-143">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span> <span data-ttu-id="28075-144">Данное многомерное выражение определяет, что если фактический товарооборот посредников составляет более 85 % от целевого объема, то для заполнения графического изображения используется значение 0.</span><span class="sxs-lookup"><span data-stu-id="28075-144">In this MDX expression, if actual reseller sales are more than 85 percent of the goal, a value of 0 is used to populate the chosen graphic.</span></span> <span data-ttu-id="28075-145">Так как в качестве графического символа используется шкала, указатель шкалы находится посередине.</span><span class="sxs-lookup"><span data-stu-id="28075-145">Because a gauge is the chosen graphic, the pointer in the gauge will be half-way between empty and full.</span></span> <span data-ttu-id="28075-146">Если фактический товарооборот посредников составляет более 90 %, указатель будет показывать три четверти шкалы.</span><span class="sxs-lookup"><span data-stu-id="28075-146">If actual reseller sales are more the 90 percent, the pointer on the gauge will be three-fourths of the way between empty and full.</span></span>

7.  <span data-ttu-id="28075-147">Убедитесь в том, что в списке **Признак тренда** выбрано значение **Стандартная стрелка** , и введите в поле **Выражение тренда** следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="28075-147">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following expression in the **Trend expression** box:</span></span>

    ```
    Case
     When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
     When  (
      KpiValue("Reseller Revenue") - 
       (KpiValue("Reseller Revenue"), 
        ParallelPeriod
         ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
          /
          (KpiValue ("Reseller Revenue"),
           ParallelPeriod
            ([Date].[Calendar Date].[Calendar Year],1,
             [Date].[Calendar Date].CurrentMember)))
           >=.02
      Then 1
       When(
        KpiValue("Reseller Revenue") - 
         (KpiValue ( "Reseller Revenue" ),
          ParallelPeriod
           ([Date].[Calendar Date].[Calendar Year],1,
            [Date].[Calendar Date].CurrentMember))
           /
            (KpiValue("Reseller Revenue"),
             ParallelPeriod
              ([Date].[Calendar Date].[Calendar Year],1,
                [Date].[Calendar Date].CurrentMember)))
            <=.02
      Then -1
       Else 0
    End
    ```

     <span data-ttu-id="28075-148">Это многомерное выражение служит основой оценки тренда по достижению заданной цели.</span><span class="sxs-lookup"><span data-stu-id="28075-148">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-reseller-revenue-kpi"></a><span data-ttu-id="28075-149">Просмотр куба с использованием ключевого показателя эффективности «Доход от продаж через торгового посредника»</span><span class="sxs-lookup"><span data-stu-id="28075-149">Browsing the Cube by Using the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="28075-150">В меню **Сборка** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите пункт **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="28075-150">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="28075-151">После успешного завершения развертывания на панели инструментов вкладки **Ключевые показатели эффективности** нажмите кнопку **Представление браузера** , а затем кнопку **Повторное соединение**.</span><span class="sxs-lookup"><span data-stu-id="28075-151">When deployment has successfully completed, on the toolbar of the **KPIs** tab, click the **Browser View** button, and then click **Reconnect**.</span></span>

     <span data-ttu-id="28075-152">На панели **Браузер ключевых показателей эффективности** отображаются шкалы состояния и тренда на основании значений установленного по умолчанию элемента каждого из измерений вместе с текущим и целевым значениями.</span><span class="sxs-lookup"><span data-stu-id="28075-152">The status and trend gauges are displayed in the **KPI Browser** pane for reseller sales based on the values for the default member of each dimension, together with the value for the value and the goal.</span></span> <span data-ttu-id="28075-153">По умолчанию для каждого из измерений задан элемент «Все» уровня «Все», поскольку в качестве элемента по умолчанию не был указан другой элемент измерения.</span><span class="sxs-lookup"><span data-stu-id="28075-153">The default member of each dimension is the All member of the All level, because you have not defined any other member of any dimension as the default member.</span></span>

3.  <span data-ttu-id="28075-154">На панели фильтра в списке **Измерение** выберите **Территория продаж** , в списке **Иерархия** выберите **Территории продаж** , в списке **Оператор** выберите **Равно** , а затем в списке **Критерий фильтра** установите флажок **Северная Америка** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28075-154">In the filter pane, select **Sales Territory** in the **Dimension** list, select **Sales Territories** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **North America** check box in the **Filter Expression** list, and then click **OK**.</span></span>

4.  <span data-ttu-id="28075-155">В следующей строке панели **Фильтр** в списке **Измерение** выберите пункт **Дата** , в списке **Иерархия** выберите пункт **Календарная дата** , в списке **Оператор** выберите пункт **Равно** , а затем в списке **Критерий фильтра** установите флажок **Q3 CY 2007** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28075-155">In the next row in the **Filter** pane, select **Date** in the **Dimension** list, select **Calendar Date** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **Q3 CY 2007** check box in the **Filter Expression** list, and then click **OK**.</span></span>

5.  <span data-ttu-id="28075-156">Щелкните в любом месте панели **Браузер ключевых показателей эффективности** , чтобы обновить значения показателя **Доход от продаж через торгового посредника**.</span><span class="sxs-lookup"><span data-stu-id="28075-156">Click anywhere in the **KPI Browser** pane to update the values for the **Reseller Revenue KPI**.</span></span>

     <span data-ttu-id="28075-157">Обратите внимание, что разделы **Значение**, **Цель**и **Состояние** ключевого показателя эффективности отражают значения для нового периода времени.</span><span class="sxs-lookup"><span data-stu-id="28075-157">Notice that the **Value**, **Goal**, and **Status** sections of the KPI reflect the values for the new time period</span></span>

## <a name="defining-the-product-gross-profit-margin-kpi"></a><span data-ttu-id="28075-158">Определение ключевого показателя эффективности «Коэффициент общей валовой прибыли продукта»</span><span class="sxs-lookup"><span data-stu-id="28075-158">Defining the Product Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="28075-159">Нажмите кнопку **Представление формы** на панели инструментов вкладки **Ключевые показатели эффективности** , а затем кнопку **Создать ключевой показатель эффективности** .</span><span class="sxs-lookup"><span data-stu-id="28075-159">Click the **Form View** button on the toolbar of the **KPIs** tab, and then click the **New KPI** button.</span></span>

2.  <span data-ttu-id="28075-160">В поле **имя** введите `Product Gross Profit Margin` , а затем убедитесь, что **\<All>** оно отображается в списке **связанная группа мер** .</span><span class="sxs-lookup"><span data-stu-id="28075-160">In the **Name** box, type `Product Gross Profit Margin`, and then verify that **\<All>** appears in the **Associated measure group** list.</span></span>

3.  <span data-ttu-id="28075-161">На вкладке **Метаданные** панели **Средства вычисления** перетащите меру **Итоговый коэффициент валовой прибыли** в поле **Выражение значения** .</span><span class="sxs-lookup"><span data-stu-id="28075-161">In the **Metadata** tab in the **Calculation Tools** pane, drag the **Total GPM** measure to the **Value Expression** box.</span></span>

4.  <span data-ttu-id="28075-162">В поле **Целевое выражение** введите следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="28075-162">In the **Goal Expression** box, type the following expression:</span></span>

    ```
    Case
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Accessories]
        Then .40                 
        When [Product].[Category].CurrentMember 
          Is [Product].[Category].[Bikes]
        Then .12                
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Clothing]
        Then .20
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Components]
        Then .10
        Else .12            
    End
    ```

5.  <span data-ttu-id="28075-163">В списке **Признак состояния** выберите **Цилиндр**.</span><span class="sxs-lookup"><span data-stu-id="28075-163">In the **Status indicator** list, select **Cylinder**.</span></span>

6.  <span data-ttu-id="28075-164">Введите следующее многомерное выражение в поле **Выражение состояния** :</span><span class="sxs-lookup"><span data-stu-id="28075-164">Type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .90
        Then 1
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) <  .90
             And 
             KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .80
        Then 0
        Else -1
    End
    ```

     <span data-ttu-id="28075-165">Многомерное выражение служит основой оценки достижения целевого значения.</span><span class="sxs-lookup"><span data-stu-id="28075-165">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span>

7.  <span data-ttu-id="28075-166">Убедитесь в том, что в списке **Признак тренда** выбрано значение **Стандартная стрелка** , и введите в поле **Выражение тренда** следующее многомерное выражение:</span><span class="sxs-lookup"><span data-stu-id="28075-166">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following MDX expression in the **Trend expression** box:</span></span>

    ```
    Case
    When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
       When VBA!Abs
        (
          KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            ) /
            (
              KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            )  
          ) <=.02
      Then 0
      When KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[ Calendar Date].[ Calendar Year],
               1,
               [Date].[ Calendar Date].CurrentMember
             )
           ) /
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[Calendar Date].[Calendar Year],
               1,
               [Date].[Calendar Date].CurrentMember
             )
           )  >.02
      Then 1
      Else -1
    End
    ```

     <span data-ttu-id="28075-167">Это многомерное выражение служит основой оценки тренда по достижению заданной цели.</span><span class="sxs-lookup"><span data-stu-id="28075-167">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-total-gross-profit-margin-kpi"></a><span data-ttu-id="28075-168">Просмотр куба с использованием ключевого показателя эффективности «Итоговый коэффициент валовой прибыли»</span><span class="sxs-lookup"><span data-stu-id="28075-168">Browsing the Cube by Using the Total Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="28075-169">В меню **Сборка** выберите пункт **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="28075-169">On the **Build** menu, click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="28075-170">После успешного завершения развертывания нажмите кнопку **Повторное подключение** на панели инструментов вкладки **Ключевые показатели эффективности** , а затем перейдите на панель **Представление браузера**.</span><span class="sxs-lookup"><span data-stu-id="28075-170">When deployment has successfully completed, click **Reconnect** on the toolbar of the **KPIs** tab, and then click **Browser View**.</span></span>

     <span data-ttu-id="28075-171">`Product Gross Profit Margin`Отобразится KPI и отобразится значение ключевого показателя эффективности для **Q3 CY 2007** и **Северная Америка** территории продаж.</span><span class="sxs-lookup"><span data-stu-id="28075-171">The `Product Gross Profit Margin` KPI appears and displays the KPI value for **Q3 CY 2007** and the **North America** sales territory.</span></span>

3.  <span data-ttu-id="28075-172">На панели **Фильтр** в списке **Измерение** выберите значение **Продукт** , в списке **Иерархия** укажите значение **Категория** , в списке **Оператор** выберите значение **Равно** , а затем в списке **Критерий фильтра** выберите значение **Велосипеды** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28075-172">In the **Filter** pane, select **Product** in the **Dimension** list, select **Category** in the **Hierarchy** list, select **Equal** in the **Operator** list, and then select **Bikes** in the **Filter Expression** list, and then click **OK**.</span></span>

     <span data-ttu-id="28075-173">Выводится коэффициент валовой прибыли для продажи велосипедов через посредников в Северной Америке для Q3 CY 2007.</span><span class="sxs-lookup"><span data-stu-id="28075-173">The gross profit margin for the sale of Bikes by resellers in North America in Q3 CY 2007 appears.</span></span>

## <a name="next-lesson"></a><span data-ttu-id="28075-174">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="28075-174">Next Lesson</span></span>
 [<span data-ttu-id="28075-175">Урок 8. Определение действий</span><span class="sxs-lookup"><span data-stu-id="28075-175">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)


