---
title: Определение вычисляемых элементов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 07f13e1c-0b20-4f9e-ad62-c438983f2785
author: minewiskan
ms.author: owend
ms.openlocfilehash: f2a054356613ebf3d4cf825c1fa4c238a5362ec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658499"
---
# <a name="defining-calculated-members"></a><span data-ttu-id="2caff-102">Определение вычисляемых элементов</span><span class="sxs-lookup"><span data-stu-id="2caff-102">Defining Calculated Members</span></span>
  <span data-ttu-id="2caff-103">Вычисляемые элементы — это элементы измерения или группы мер, которые определяются на основе сочетания данных куба, арифметических операторов, чисел и функций.</span><span class="sxs-lookup"><span data-stu-id="2caff-103">Calculated members are members of a dimension or a measure group that are defined based on a combination of cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="2caff-104">Например, можно создать вычисляемый элемент для расчета суммы двух физических мер в кубе.</span><span class="sxs-lookup"><span data-stu-id="2caff-104">For example, you can create a calculated member that calculates the sum of two physical measures in the cube.</span></span> <span data-ttu-id="2caff-105">Определения вычисляемых элементов хранятся в кубах, а их значения рассчитываются при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="2caff-105">Calculated member definitions are stored in cubes, but their values are calculated at query time.</span></span>  
  
 <span data-ttu-id="2caff-106">Для создания вычисляемого элемента следует использовать команду **Создать вычисляемый элемент** на вкладке **Вычисления** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="2caff-106">To create a calculated member, use the **New Calculated Member** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="2caff-107">Вычисляемые элементы можно создавать в любом измерении, в том числе в измерении мер.</span><span class="sxs-lookup"><span data-stu-id="2caff-107">You can create a calculated member within any dimension, including the measures dimension.</span></span> <span data-ttu-id="2caff-108">Их также можно разместить в папке отображения из диалогового окна **Calculation Properties** .</span><span class="sxs-lookup"><span data-stu-id="2caff-108">You can also place a calculated member within a display folder in the **Calculation Properties** dialog box.</span></span> <span data-ttu-id="2caff-109">Дополнительные сведения см. в разделах [Вычисления](multidimensional-models-olap-logical-cube-objects/calculations.md), [Вычисления в многомерных моделях](multidimensional-models/calculations-in-multidimensional-models.md)и [Создание вычисляемых элементов](multidimensional-models/create-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="2caff-109">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), [Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md), and [Create Calculated Members](multidimensional-models/create-calculated-members.md).</span></span>  
  
 <span data-ttu-id="2caff-110">В задачах этого раздела определяются вычисляемые меры, чтобы обеспечить пользователям возможность просмотра коэффициента валовой прибыли и показателя продаж для осуществления продаж через Интернет, товарооборота посредников и всех других продаж.</span><span class="sxs-lookup"><span data-stu-id="2caff-110">In the tasks in this topic, you define calculated measures to let users view the gross profit margin percentage and sales ratios for Internet sales, reseller sales, and for all sales.</span></span>  
  
## <a name="defining-calculations-to-aggregate-physical-measures"></a><span data-ttu-id="2caff-111">Определение статистических вычислений для физических мер</span><span class="sxs-lookup"><span data-stu-id="2caff-111">Defining Calculations to Aggregate Physical Measures</span></span>  
  
1.  <span data-ttu-id="2caff-112">Откройте конструктор кубов, выберите куб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial и перейдите на вкладку **Вычисления** .</span><span class="sxs-lookup"><span data-stu-id="2caff-112">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="2caff-113">Обратите внимание, что по умолчанию на панели **Выражения вычисления** и панели **Организатор скриптов** доступна команда CALCULATE.</span><span class="sxs-lookup"><span data-stu-id="2caff-113">Notice the default CALCULATE command in the **Calculation Expressions** pane and in the **Script Organizer** pane.</span></span> <span data-ttu-id="2caff-114">Эта команда указывает, что меры в кубе должны быть вычислены в соответствии со значениями свойства AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="2caff-114">This command specifies that the measures in the cube should be aggregated according to the value that is specified by their AggregateFunction properties.</span></span> <span data-ttu-id="2caff-115">Значения мер обычно суммируются, но могут подсчитываться или статистически обрабатываться другим образом.</span><span class="sxs-lookup"><span data-stu-id="2caff-115">Measure values are generally summed, but may also be counted or aggregated in some other manner.</span></span>  
  
     <span data-ttu-id="2caff-116">На рисунке ниже показана вкладка **Вычисления** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="2caff-116">The following image shows the **Calculations** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="2caff-117">![Вкладка «Вычисления» конструктора кубов](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Вкладка «Вычисления» конструктора кубов")</span><span class="sxs-lookup"><span data-stu-id="2caff-117">![Calculations tab of Cube Designer](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Calculations tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="2caff-118">На панели инструментов вкладки **Вычисления** нажмите кнопку **Создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2caff-118">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="2caff-119">В панели **Выражения вычисления** будет отображена новая форма, в которой следует задать свойства нового вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="2caff-119">A new form appears in the **Calculation Expressions** pane within which you define the properties of this new calculated member.</span></span> <span data-ttu-id="2caff-120">Новый элемент также отображается на панели **Организатор скриптов** .</span><span class="sxs-lookup"><span data-stu-id="2caff-120">The new member also appears in the **Script Organizer** pane.</span></span>  
  
     <span data-ttu-id="2caff-121">На рисунке ниже показана форма, отображаемая в панели **Выражения вычисления** при нажатии кнопки **Создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2caff-121">The following image shows the form that appears in the **Calculation Expressions** pane when you click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="2caff-122">![Форма панели «Выражения вычислений»](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Форма панели «Выражения вычислений»")</span><span class="sxs-lookup"><span data-stu-id="2caff-122">![Calculation Expressions pane form](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Calculation Expressions pane form")</span></span>  
  
3.  <span data-ttu-id="2caff-123">В поле **имя** измените имя вычисляемой меры на `[Total Sales Amount]` .</span><span class="sxs-lookup"><span data-stu-id="2caff-123">In the **Name** box, change the name of the calculated measure to `[Total Sales Amount]`.</span></span>  
  
     <span data-ttu-id="2caff-124">Если имя вычисляемого элемента содержит пробелы, его необходимо заключать в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="2caff-124">If the name of a calculated member contains a space, the calculated member name must be enclosed in square brackets.</span></span>  
  
     <span data-ttu-id="2caff-125">Обратите внимание, что в списке **Родительская иерархия** по умолчанию новый вычисляемый элемент создается в измерении **Меры** .</span><span class="sxs-lookup"><span data-stu-id="2caff-125">Notice in the **Parent hierarchy** list that, by default, a new calculated member is created in the **Measures** dimension.</span></span> <span data-ttu-id="2caff-126">Вычисляемый элемент в измерении мер часто называют вычисляемой мерой.</span><span class="sxs-lookup"><span data-stu-id="2caff-126">A calculated member in the Measures dimension is also frequently called a calculated measure.</span></span>  
  
4.  <span data-ttu-id="2caff-127">На вкладке **Метаданные** панели **Средства вычисления** вкладки **Вычисления** последовательно раскройте узлы **Меры** и **Продажи через Интернет** , чтобы просмотреть метаданные для группы мер **Продажи через Интернет** .</span><span class="sxs-lookup"><span data-stu-id="2caff-127">On the **Metadata** tab in the **Calculation Tools** pane of the **Calculations** tab, expand **Measures** and then expand **Internet Sales** to view the metadata for the **Internet Sales** measure group.</span></span>  
  
     <span data-ttu-id="2caff-128">Элементы метаданных можно перетащить с панели **Средства вычисления** в поле **Выражение** , а затем добавить операторы и другие элементы для создания многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="2caff-128">You can drag metadata elements from the **Calculation Tools** pane into the **Expression** box and then add operators and other elements to create Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="2caff-129">Кроме того, многомерное выражение можно ввести непосредственно в поле **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="2caff-129">Alternatively, you can type the MDX expression directly into the **Expression** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2caff-130">Если в области **Средства вычисления** не отображаются метаданные, нажмите кнопку **Повторное соединение** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="2caff-130">If you cannot view any metadata in the **Calculation Tools** pane, click **Reconnect** on the toolbar.</span></span> <span data-ttu-id="2caff-131">Если это не помогает, возможно, следует выполнить обработку куба или запустить экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2caff-131">If this does not work, you may have to process the cube or start the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="2caff-132">Перетащите показатель **Продажи через Интернет — объем продаж** с вкладки **Метаданные** панели **Средства вычисления** в поле **Выражение** панели **Выражения вычисления** .</span><span class="sxs-lookup"><span data-stu-id="2caff-132">Drag **Internet Sales-Sales Amount** from the **Metadata** tab in the **Calculation Tools** pane into the **Expression** box in the **Calculation Expressions** pane.</span></span>  
  
6.  <span data-ttu-id="2caff-133">В поле **Выражение** после`+`[Меры].[Продажи через Интернет — объем продаж] **введите знак плюс (**).</span><span class="sxs-lookup"><span data-stu-id="2caff-133">In the **Expression** box, type a plus sign (`+`) after **[Measures].[Internet Sales-Sales Amount]**.</span></span>  
  
7.  <span data-ttu-id="2caff-134">На вкладке **Метаданные** панели **Средства вычисления** разверните элемент **Товарооборот посредников**и перетащите показатель **Товарооборот посредников — объем продаж** в поле **Выражение** панели **Выражения вычисления** после знака плюс (+).</span><span class="sxs-lookup"><span data-stu-id="2caff-134">On the **Metadata** tab in the **Calculation Tools** pane, expand **Reseller Sales**, and then drag **Reseller Sales-Sales Amount** into the **Expression** box in the **Calculation Expressions** pane after the plus sign (+).</span></span>  
  
8.  <span data-ttu-id="2caff-135">В списке **строка формата** выберите **"валюта".**</span><span class="sxs-lookup"><span data-stu-id="2caff-135">In the **Format string** list, select **"Currency".**</span></span>  
  
9. <span data-ttu-id="2caff-136">В списке **Установленное поведение** установите флажки для показателей **Продажи через Интернет — объем продаж** и **Товарооборот посредников — объем продаж**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2caff-136">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2caff-137">Меры, указанные в списке **Установленное поведение** , используются для разрешения запросов NON EMPTY в многомерных выражениях.</span><span class="sxs-lookup"><span data-stu-id="2caff-137">The measures you specify in the **Non-empty behavior** list are used to resolve NON EMPTY queries in MDX.</span></span> <span data-ttu-id="2caff-138">Если в списке **Установленное поведение** указана одна или несколько мер, в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] вычисляемый элемент считается пустым, если все указанные меры пусты.</span><span class="sxs-lookup"><span data-stu-id="2caff-138">When you specify one or more measures in the **Non-empty behavior** list, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] treats the calculated member as empty if all the specified measures are empty.</span></span> <span data-ttu-id="2caff-139">Если значение свойства **Установленное поведение** не указано, в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] проводится оценка вычисляемого элемента с целью определения того, является ли он пустым.</span><span class="sxs-lookup"><span data-stu-id="2caff-139">If the **Non-empty behavior** property is blank, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] must evaluate the calculated member itself to determine whether the member is empty.</span></span>  
  
     <span data-ttu-id="2caff-140">На рисунке ниже показана панель **Выражения вычисления** , заполненная параметрами, указанными в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="2caff-140">The following image shows the **Calculation Expressions** pane populated with the settings that you specified in the previous steps.</span></span>  
  
     <span data-ttu-id="2caff-141">![Заполненная панель «Выражения для вычислений»](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Заполненная панель «Выражения для вычислений»")</span><span class="sxs-lookup"><span data-stu-id="2caff-141">![Populated Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Populated Calculation Expressions pane")</span></span>  
  
10. <span data-ttu-id="2caff-142">В области инструментов вкладки **Вычисления** нажмите кнопку **Представление скрипта**и просмотрите скрипт расчета на панели **Выражения вычисления** .</span><span class="sxs-lookup"><span data-stu-id="2caff-142">On the toolbar of the **Calculations** tab, click **Script View**, and then review the calculation script in the **Calculation Expressions** pane.</span></span>  
  
     <span data-ttu-id="2caff-143">Обратите внимание, что новое вычисление добавляется в исходное выражение CALCULATE. Вычисления разделены точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="2caff-143">Notice that the new calculation is added to the initial CALCULATE expression; each individual calculation is separated by a semicolon.</span></span> <span data-ttu-id="2caff-144">Кроме того, обратите внимание, что в начале скрипта вычисления отображается комментарий.</span><span class="sxs-lookup"><span data-stu-id="2caff-144">Notice also that a comment appears at the beginning of the calculation script.</span></span> <span data-ttu-id="2caff-145">Рекомендуется добавлять комментарии в скрипт для групп вычислений, поскольку в дальнейшем они помогут другим разработчикам понимать сложные скрипты вычислений.</span><span class="sxs-lookup"><span data-stu-id="2caff-145">Adding comments within the calculation script for groups of calculations is a good practice, to help you and other developers understand complex calculation scripts.</span></span>  
  
11. <span data-ttu-id="2caff-146">Добавьте новую строку в скрипт вычисления после команды **Calculate;** и перед добавленным скриптом вычислений, а затем введите на отдельной строке скрипта следующий текст:</span><span class="sxs-lookup"><span data-stu-id="2caff-146">Add a new line in the calculation script after the **Calculate;** command and before the newly added calculation script, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to aggregate Internet Sales and Reseller Sales measures */  
    ```  
  
     <span data-ttu-id="2caff-147">На следующем рисунке показаны возможные сценарии вычислений, отображаемые в панели **Выражения вычисления** при выполнении всех заданий учебника.</span><span class="sxs-lookup"><span data-stu-id="2caff-147">The following image shows the calculation scripts as they should appear in the **Calculation Expressions** pane at this point in the tutorial.</span></span>  
  
     <span data-ttu-id="2caff-148">![Скрипты на панели «Выражения для вычислений»](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Скрипты на панели «Выражения для вычислений»")</span><span class="sxs-lookup"><span data-stu-id="2caff-148">![Scripts in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts in Calculation Expressions pane")</span></span>  
  
12. <span data-ttu-id="2caff-149">На панели инструментов вкладки **вычисления** щелкните **представление формы**, убедитесь, что `[Total Sales Amount]` выбрано на панели **Организатор скриптов** , и нажмите кнопку **создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2caff-149">On the toolbar of the **Calculations** tab, click **Form View**, verify that `[Total Sales Amount]` is selected in the **Script Organizer** pane, and then click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="2caff-150">Измените имя нового вычисляемого элемента на `[Total Product Cost]` , а затем создайте следующее выражение в поле **выражение** :</span><span class="sxs-lookup"><span data-stu-id="2caff-150">Change the name of this new calculated member to `[Total Product Cost]`, and then create the following expression in the **Expression** box:</span></span>  
  
    ```  
    [Measures].[Internet Sales-Total Product Cost] + [Measures].[Reseller Sales-Total Product Cost]  
    ```  
  
14. <span data-ttu-id="2caff-151">В списке **Строка форматирования** выберите **Валюта**.</span><span class="sxs-lookup"><span data-stu-id="2caff-151">In the **Format string** list, select **"Currency"**.</span></span>  
  
15. <span data-ttu-id="2caff-152">В списке **Установленное поведение** установите флажки для показателей **Продажи через Интернет — общая стоимость продукции** и **Товарооборот посредников — общая стоимость продукции**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2caff-152">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Total Product Cost** and **Reseller Sales-Total Product Cost**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2caff-153">Заданы два вычисляемых элемента, которые отображаются на панели **Организатор скриптов** .</span><span class="sxs-lookup"><span data-stu-id="2caff-153">You have now defined two calculated members, both of which are visible in the **Script Organizer** pane.</span></span> <span data-ttu-id="2caff-154">Эти вычисляемые элементы можно использовать в других вычислениях, если они будут впоследствии заданы в скрипте вычисления.</span><span class="sxs-lookup"><span data-stu-id="2caff-154">These calculated members can be used by other calculations that you define later in the calculation script.</span></span> <span data-ttu-id="2caff-155">Определение любого вычисляемого элемента можно просмотреть, выбрав его на панели **Организатор скриптов** . Оно отображается на панели **Выражения вычисления** в представлении формы.</span><span class="sxs-lookup"><span data-stu-id="2caff-155">You can view the definition of any calculated member by selecting the calculated member in the **Script Organizer** pane; the definition of the calculated member will appear in the **Calculation Expressions** pane in the Form view.</span></span> <span data-ttu-id="2caff-156">Новые определенные вычисляемые элементы не отображаются в панели **Средства вычисления** , пока не будут развернуты.</span><span class="sxs-lookup"><span data-stu-id="2caff-156">Newly defined calculated members will not appear in the **Calculation Tools** pane until these objects have been deployed.</span></span> <span data-ttu-id="2caff-157">Вычисления не требуют обработки.</span><span class="sxs-lookup"><span data-stu-id="2caff-157">Calculations do not require processing.</span></span>  
  
## <a name="defining-gross-profit-margin-calculations"></a><span data-ttu-id="2caff-158">Создание вычислений коэффициента валовой прибыли</span><span class="sxs-lookup"><span data-stu-id="2caff-158">Defining Gross Profit Margin Calculations</span></span>  
  
1.  <span data-ttu-id="2caff-159">Убедитесь, что на `[Total Product Cost]` панели **Организатор скриптов** выбрана кнопка **создать вычисляемый элемент** на панели инструментов вкладки **вычисления** .</span><span class="sxs-lookup"><span data-stu-id="2caff-159">Verify that `[Total Product Cost]` is selected in the **Script Organizer** pane, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
2.  <span data-ttu-id="2caff-160">В поле **имя** измените имя новой вычисляемой меры на `[Internet GPM]` .</span><span class="sxs-lookup"><span data-stu-id="2caff-160">In the **Name** box, change the name of this new calculated measure to `[Internet GPM]`.</span></span>  
  
3.  <span data-ttu-id="2caff-161">В поле **Выражение** создайте следующее многомерное выражение:</span><span class="sxs-lookup"><span data-stu-id="2caff-161">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Internet Sales-Sales Amount] -   
    [Measures].[Internet Sales-Total Product Cost]) /  
    [Measures].[Internet Sales-Sales Amount]  
    ```  
  
4.  <span data-ttu-id="2caff-162">В списке **Строка форматирования** выберите значение **Проценты**.</span><span class="sxs-lookup"><span data-stu-id="2caff-162">In the **Format string** list, select **"Percent"**.</span></span>  
  
5.  <span data-ttu-id="2caff-163">В списке **Установленное поведение** установите флажок для показателя **Продажи через Интернет — объем продаж**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2caff-163">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="2caff-164">На панели инструментов вкладки **Вычисления** нажмите кнопку **Создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2caff-164">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
7.  <span data-ttu-id="2caff-165">В поле **имя** измените имя новой вычисляемой меры на `[Reseller GPM]` .</span><span class="sxs-lookup"><span data-stu-id="2caff-165">In the **Name** box, change the name of this new calculated measure to `[Reseller GPM]`.</span></span>  
  
8.  <span data-ttu-id="2caff-166">В поле **Выражение** создайте следующее многомерное выражение:</span><span class="sxs-lookup"><span data-stu-id="2caff-166">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Reseller Sales-Sales Amount] -   
    [Measures].[Reseller Sales-Total Product Cost]) /  
    [Measures].[Reseller Sales-Sales Amount]  
    ```  
  
9. <span data-ttu-id="2caff-167">В списке **Строка форматирования** выберите значение **Проценты**.</span><span class="sxs-lookup"><span data-stu-id="2caff-167">In the **Format string** list, select **"Percent"**.</span></span>  
  
10. <span data-ttu-id="2caff-168">В списке **Установленное поведение** установите флажок для показателя **Товарооборот посредников — объем продаж**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2caff-168">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="2caff-169">На панели инструментов вкладки **Вычисления** нажмите кнопку **Создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2caff-169">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
12. <span data-ttu-id="2caff-170">В поле **имя** измените имя вычисляемой меры на `[Total GPM]` .</span><span class="sxs-lookup"><span data-stu-id="2caff-170">In the **Name** box, change the name of this calculated measure to `[Total GPM]`.</span></span>  
  
13. <span data-ttu-id="2caff-171">В поле **Выражение** создайте следующее многомерное выражение:</span><span class="sxs-lookup"><span data-stu-id="2caff-171">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Total Sales Amount] -   
    [Measures].[Total Product Cost]) /  
    [Measures].[Total Sales Amount]  
    ```  
  
     <span data-ttu-id="2caff-172">Обратите внимание, что этот вычисляемый элемент ссылается на другие вычисляемые элементы.</span><span class="sxs-lookup"><span data-stu-id="2caff-172">Notice that this calculated member is referencing other calculated members.</span></span> <span data-ttu-id="2caff-173">Этот вычисляемый элемент является допустимым, поскольку он рассчитывается после вычисляемых элементов, на которые ссылается.</span><span class="sxs-lookup"><span data-stu-id="2caff-173">Because this calculated member will be calculated after the calculated members that it references, this is a valid calculated member.</span></span>  
  
14. <span data-ttu-id="2caff-174">В списке **Строка форматирования** выберите значение **Проценты**.</span><span class="sxs-lookup"><span data-stu-id="2caff-174">In the **Format string** list, select **"Percent"**.</span></span>  
  
15. <span data-ttu-id="2caff-175">В списке **Установленное поведение** установите флажки для показателей **Продажи через Интернет — объем продаж** и **Товарооборот посредников — объем продаж**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2caff-175">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="2caff-176">На панели инструментов вкладки **Вычисления** нажмите кнопку **Представление скрипта** и просмотрите три вычисления, только что добавленные в скрипт вычисления.</span><span class="sxs-lookup"><span data-stu-id="2caff-176">On the toolbar of the **Calculations** tab, click **Script View** and review the three calculations you just added to the calculation script.</span></span>  
  
17. <span data-ttu-id="2caff-177">Добавьте новую строку в скрипт вычисления непосредственно перед `[Internet GPM]` вычислением, а затем добавьте следующий текст в скрипт в отдельной строке:</span><span class="sxs-lookup"><span data-stu-id="2caff-177">Add a new line in the calculation script immediately before the `[Internet GPM]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate gross profit margin */  
    ```  
  
     <span data-ttu-id="2caff-178">На рисунке ниже показана панель **Выражения** с тремя новыми вычислениями.</span><span class="sxs-lookup"><span data-stu-id="2caff-178">The following image shows the **Expressions** pane with the three new calculations.</span></span>  
  
     <span data-ttu-id="2caff-179">![Новые вычисления на панели «Выражения для вычислений»](../../2014/tutorials/media/l6-calculatedmembers-05.gif "Новые вычисления на панели «Выражения для вычислений»")</span><span class="sxs-lookup"><span data-stu-id="2caff-179">![New calculations in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-05.gif "New calculations in Calculation Expressions pane")</span></span>  
  
## <a name="defining-the-percent-of-total-calculations"></a><span data-ttu-id="2caff-180">Создание вычислений «Проценты от общего»</span><span class="sxs-lookup"><span data-stu-id="2caff-180">Defining the Percent of Total Calculations</span></span>  
  
1.  <span data-ttu-id="2caff-181">На панели инструментов вкладки **Вычисления** нажмите кнопку **Представление формы**.</span><span class="sxs-lookup"><span data-stu-id="2caff-181">On the toolbar of the **Calculations** tab, click **Form View**.</span></span>  
  
2.  <span data-ttu-id="2caff-182">На панели **Организатор скриптов** выберите `[Total GPM]` и нажмите кнопку **создать вычисляемый элемент** на панели инструментов вкладки **вычисления** .</span><span class="sxs-lookup"><span data-stu-id="2caff-182">In the **Script Organizer** pane, select `[Total GPM]`, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="2caff-183">Выбор последнего вычисляемого элемента на панели **Организатор скриптов** перед нажатием кнопки **Создать вычисляемый элемент** гарантирует, что новый вычисляемый элемент будет добавлен в конец скрипта.</span><span class="sxs-lookup"><span data-stu-id="2caff-183">Clicking the final calculated member in the **Script Organizer** pane before you click **New Calculated Member** guarantees that the new calculated member will be entered at the end of the script.</span></span> <span data-ttu-id="2caff-184">Скрипты выполняются в том порядке, в котором они отображаются на панели **Организатор скриптов** .</span><span class="sxs-lookup"><span data-stu-id="2caff-184">Scripts execute in the order that they appear in the **Script Organizer** pane.</span></span>  
  
3.  <span data-ttu-id="2caff-185">Измените имя нового вычисляемого элемента на `[Internet Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="2caff-185">Change the name of this new calculated member to `[Internet Sales Ratio to All Products]`.</span></span>  
  
4.  <span data-ttu-id="2caff-186">В поле **Выражение** введите следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="2caff-186">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Internet Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Internet Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Internet Sales-Sales Amount] )  
        End  
    ```  
  
     <span data-ttu-id="2caff-187">В этом многомерном выражении рассчитывается доля каждого из товаров в итоговом значении продаж через Интернет.</span><span class="sxs-lookup"><span data-stu-id="2caff-187">This MDX expression calculates the contribution to total Internet sales of each product.</span></span> <span data-ttu-id="2caff-188">Использование инструкции Case в сочетании с функцией IS EMPTY позволяет избежать ошибки деления на ноль в том случае, если по данному товару отсутствуют продажи.</span><span class="sxs-lookup"><span data-stu-id="2caff-188">The Case statement together with the IS EMPTY function ensures that a divide by zero error does not occur when a product has no sales.</span></span>  
  
5.  <span data-ttu-id="2caff-189">В списке **Строка форматирования** выберите значение **Проценты**.</span><span class="sxs-lookup"><span data-stu-id="2caff-189">In the **Format string** list, select **"Percent"**.</span></span>  
  
6.  <span data-ttu-id="2caff-190">В списке **Установленное поведение** установите флажок для показателя **Продажи через Интернет — объем продаж**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2caff-190">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="2caff-191">На панели инструментов вкладки **Вычисления** нажмите кнопку **Создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2caff-191">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
8.  <span data-ttu-id="2caff-192">Измените имя этого вычисляемого элемента на `[Reseller Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="2caff-192">Change the name of this calculated member to `[Reseller Sales Ratio to All Products]`.</span></span>  
  
9. <span data-ttu-id="2caff-193">В поле **Выражение** введите следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="2caff-193">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Reseller Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Reseller Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Reseller Sales-Sales Amount] )  
        End  
    ```  
  
10. <span data-ttu-id="2caff-194">В списке **Строка форматирования** выберите значение **Проценты**.</span><span class="sxs-lookup"><span data-stu-id="2caff-194">In the **Format string** list, select **"Percent"**.</span></span>  
  
11. <span data-ttu-id="2caff-195">В списке **Установленное поведение** установите флажок для показателя **Товарооборот посредников — объем продаж**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2caff-195">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="2caff-196">На панели инструментов вкладки **Вычисления** нажмите кнопку **Создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2caff-196">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="2caff-197">Измените имя этого вычисляемого элемента на `[Total Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="2caff-197">Change the name of this calculated member to `[Total Sales Ratio to All Products]`.</span></span>  
  
14. <span data-ttu-id="2caff-198">В поле **Выражение** введите следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="2caff-198">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Total Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Total Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Total Sales Amount] )  
        End  
    ```  
  
15. <span data-ttu-id="2caff-199">В списке **Строка форматирования** выберите значение **Проценты**.</span><span class="sxs-lookup"><span data-stu-id="2caff-199">In the **Format string** list, select **"Percent"**.</span></span>  
  
16. <span data-ttu-id="2caff-200">В списке **Установленное поведение** установите флажки для показателей **Продажи через Интернет — объем продаж** и **Товарооборот посредников — объем продаж**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2caff-200">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="2caff-201">На панели инструментов вкладки **Вычисления** нажмите кнопку **Представление скриптов**и просмотрите три вычисления, только что добавленные в скрипт вычисления.</span><span class="sxs-lookup"><span data-stu-id="2caff-201">On the toolbar of the **Calculations** tab, click **Script View**, and then review the three calculations that you just added to the calculation script.</span></span>  
  
18. <span data-ttu-id="2caff-202">Добавьте новую строку в скрипт вычисления непосредственно перед `[Internet Sales Ratio to All Products]` вычислением, а затем добавьте следующий текст в скрипт в отдельной строке:</span><span class="sxs-lookup"><span data-stu-id="2caff-202">Add a new line in the calculation script immediately before the `[Internet Sales Ratio to All Products]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate percentage of product to total product sales */  
    ```  
  
     <span data-ttu-id="2caff-203">Теперь создано восемь вычисляемых элементов, которые отображаются на панели **Организатор скриптов** в представлении формы.</span><span class="sxs-lookup"><span data-stu-id="2caff-203">You have now defined a total of eight calculated members, which are visible in the **Script Organizer** pane when you are in Form view.</span></span>  
  
## <a name="browsing-the-new-calculated-members"></a><span data-ttu-id="2caff-204">Просмотр новых вычисляемых элементов</span><span class="sxs-lookup"><span data-stu-id="2caff-204">Browsing the New Calculated Members</span></span>  
  
1.  <span data-ttu-id="2caff-205">В меню **Построение** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="2caff-205">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="2caff-206">После успешного окончания развертывания перейдите на вкладку **Обозреватель** и нажмите кнопку **Повторное соединение**.</span><span class="sxs-lookup"><span data-stu-id="2caff-206">When deployment has successfully completed, switch to the **Browser** tab, click **Reconnect**.</span></span>  
  
3.  <span data-ttu-id="2caff-207">Щелкните ярлык Excel, а затем выберите **Включить**.</span><span class="sxs-lookup"><span data-stu-id="2caff-207">Click the Excel icon, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="2caff-208">На панели **Список полей сводной таблицы** раскройте папку **Значения** , чтобы отобразить новые вычисляемые элементы в измерении мер.</span><span class="sxs-lookup"><span data-stu-id="2caff-208">In the **PivotTable Field List** pane, expand **Values** folder to view the new calculated members in the Measures dimension.</span></span>  
  
5.  <span data-ttu-id="2caff-209">Перетащите меру **Итоговая сумма продаж** в область значений и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="2caff-209">Drag the **Total Sales Amount** to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="2caff-210">Перетащите меры **Продажи через Интернет — объем продаж** и **Товарооборот посредников — объем продаж** из групп мер **Продажи через Интернет** и **Товарооборот посредников** в область значений.</span><span class="sxs-lookup"><span data-stu-id="2caff-210">Drag **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount** measures from the **Internet Sales** and **Reseller Sales** measure groups to the Values area.</span></span>  
  
     <span data-ttu-id="2caff-211">Обратите внимание, что мера **Итоговая сумма продаж** является суммой мер **Продажи через Интернет — объем продаж** и **Товарооборот посредников — объем продаж** .</span><span class="sxs-lookup"><span data-stu-id="2caff-211">Notice that the **Total Sales Amount** measure is the sum of the **Internet Sales-Sales Amount** measure and the **Reseller Sales-Sales Amount** measure.</span></span>  
  
6.  <span data-ttu-id="2caff-212">Добавьте определяемую пользователем иерархию **Категории товаров** в область фильтра области **Фильтр отчета** и отфильтруйте данные по позиции **Горные велосипеды**.</span><span class="sxs-lookup"><span data-stu-id="2caff-212">Add the **Product Categories** user-defined hierarchy to the filter area of the **Report Filter** area, and then filter the data by **Mountain Bikes**.</span></span>  
  
     <span data-ttu-id="2caff-213">Обратите внимание на то, что мера **Общая сумма продаж** рассчитывается для категории продаж товара **Горные велосипеды** на основе мер **Продажи через Интернет — объем продаж** и **Товарооборот посредников — объем продаж** для позиции **Горные велосипеды**.</span><span class="sxs-lookup"><span data-stu-id="2caff-213">Notice that the **Total Sales Amount** measure is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
7.  <span data-ttu-id="2caff-214">Добавьте определяемую пользователем иерархию **Date.Calendar Date** в область меток строк и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="2caff-214">Add the **Date.Calendar Date** user-defined hierarchy to the Row labels area, and then review the results.</span></span>  
  
     <span data-ttu-id="2caff-215">Обратите внимание на то, что мера **Итоговая сумма продаж** рассчитывается за каждый календарный год для категории продаж товара **Горные велосипеды** на основе мер **Продажи через Интернет — объем продаж** и **Товарооборот посредников — объем продаж** для позиции **Горные велосипеды**.</span><span class="sxs-lookup"><span data-stu-id="2caff-215">Notice that the **Total Sales Amount** measure for each calendar year is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
8.  <span data-ttu-id="2caff-216">Добавьте меры **Итоговый коэффициент валовой прибыли**, **Коэффициент валовой прибыли по продажам через Интернет**и **Коэффициент валовой прибыли по товарообороту посредников** в область значений и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="2caff-216">Add the **Total GPM**, **Internet GPM**, and **Reseller GPM** measures to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="2caff-217">Обратите внимание, что коэффициент валовой прибыли по продажам через торгового посредника значительно ниже, чем по продажам через Интернет, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="2caff-217">Notice that the gross profit margin for reseller sales is significantly lower than for sales over the Internet, as shown in the following image.</span></span>  
  
     <span data-ttu-id="2caff-218">![Панель «Данные» с информацией о продажах посредников](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Панель «Данные» с информацией о продажах посредников")</span><span class="sxs-lookup"><span data-stu-id="2caff-218">![Data pane showing reseller sales](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Data pane showing reseller sales")</span></span>  
  
9. <span data-ttu-id="2caff-219">Добавьте в область значений меры **Общая доля продаж по всей номенклатуре продукции**, **Доля продаж через Интернет по всей номенклатуре продукции**и **Доля продаж через торгового посредника по всей номенклатуре продукции** .</span><span class="sxs-lookup"><span data-stu-id="2caff-219">Add the **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**, and **Reseller Sales Ratio to All Products** measures to the Values area.</span></span>  
  
     <span data-ttu-id="2caff-220">Обратите внимание, что доля продаж горных велосипедов во всей номенклатуре продукции увеличивается с течением времени для продаж через Интернет и уменьшается для продаж через торгового посредника.</span><span class="sxs-lookup"><span data-stu-id="2caff-220">Notice that the ratio of the sales of mountain bikes to all products has increased over time for Internet sales, but is decreasing over time for reseller sales.</span></span> <span data-ttu-id="2caff-221">Кроме того, обратите внимание, что доля продаж горных велосипедов во всей номенклатуре продукции меньше по продажам через торгового посредника, чем по продажам через Интернет.</span><span class="sxs-lookup"><span data-stu-id="2caff-221">Notice also that the ratio of the sale of mountain bikes to all products is lower from sales through resellers than it is for sales over the Internet.</span></span>  
  
10. <span data-ttu-id="2caff-222">Измените фильтр с **Горные велосипеды** на **Велосипеды**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="2caff-222">Change the filter from **Mountain Bikes** to **Bikes**, and review the results.</span></span>  
  
     <span data-ttu-id="2caff-223">Обратите внимание, что коэффициент валовой прибыли по всем велосипедам, проданным через торговых посредников, является отрицательной, поскольку туристические и дорожные велосипеды продаются в убыток.</span><span class="sxs-lookup"><span data-stu-id="2caff-223">Notice that the gross profit margin for all bikes sold through resellers is negative, because touring bikes and road bikes are being sold at a loss.</span></span>  
  
11. <span data-ttu-id="2caff-224">Измените фильтр на **Аксессуары**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="2caff-224">Change the filter to **Accessories**, and then review the results.</span></span>  
  
     <span data-ttu-id="2caff-225">Обратите внимание, что продажа аксессуаров увеличивается с течением времени, но они составляют лишь небольшую часть общей суммы продаж.</span><span class="sxs-lookup"><span data-stu-id="2caff-225">Notice that the sale of accessories is increasing over time, but that these sales make up only a small fraction of total sales.</span></span> <span data-ttu-id="2caff-226">Кроме того, обратите внимание, что коэффициент валовой прибыли для продаж аксессуаров выше, чем для велосипедов.</span><span class="sxs-lookup"><span data-stu-id="2caff-226">Notice also that the gross profit margin for sales of accessories is higher than for bikes.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2caff-227">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="2caff-227">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2caff-228">Определение именованных наборов</span><span class="sxs-lookup"><span data-stu-id="2caff-228">Defining Named Sets</span></span>](lesson-6-2-defining-named-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="2caff-229">См. также:</span><span class="sxs-lookup"><span data-stu-id="2caff-229">See Also</span></span>  
 <span data-ttu-id="2caff-230">[Времен](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="2caff-230">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="2caff-231">[Вычисления в многомерных моделях](multidimensional-models/calculations-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="2caff-231">[Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="2caff-232">Создание вычисляемых элементов</span><span class="sxs-lookup"><span data-stu-id="2caff-232">Create Calculated Members</span></span>](multidimensional-models/create-calculated-members.md)  
  
  
