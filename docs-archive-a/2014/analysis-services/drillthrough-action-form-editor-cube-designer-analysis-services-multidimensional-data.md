---
title: Редактор формы действия детализации (вкладка "действия", конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.actionexpression.drillthroughaction.f1
ms.assetid: 225fd818-b5ea-494f-b67b-66e09798274a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 546448bd05f3af45b7093acb2dbb9d1e1a8f1bd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667464"
---
# <a name="drillthrough-action-form-editor-actions-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="aad6c-102">Редактор формы действия детализации (вкладка «Действия» конструктора кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="aad6c-102">Drillthrough Action Form Editor (Actions Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="aad6c-103">Панель **Редактор форм действия детализации** на вкладке **Действия** конструктора кубов предназначена для изменения действия детализации, выбранного на панели **Организатор действий** .</span><span class="sxs-lookup"><span data-stu-id="aad6c-103">Use the **Drillthrough Action Form Editor** pane on the **Actions** tab in Cube Designer to modify the drillthrough action selected in the **Action Organizer** pane.</span></span> <span data-ttu-id="aad6c-104">Дополнительные сведения о действиях детализации см. в разделе [Действия (службы Analysis Services — многомерные данные)](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="aad6c-104">For more information about drillthrough actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aad6c-105">Действия детализации больше не углубляются до базового хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="aad6c-105">Drillthrough actions no longer drill down to the underlying data store.</span></span> <span data-ttu-id="aad6c-106">Сведения, к которым обращаются действия детализации, необходимо моделировать внутри куба, используя измерения и элементы иерархии.</span><span class="sxs-lookup"><span data-stu-id="aad6c-106">The information that drillthrough actions access must be modeled within the cube by using dimension or hierarchy members.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aad6c-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="aad6c-107">Options</span></span>  
 <span data-ttu-id="aad6c-108">**name**</span><span class="sxs-lookup"><span data-stu-id="aad6c-108">**name**</span></span>  
 <span data-ttu-id="aad6c-109">Введите имя действия.</span><span class="sxs-lookup"><span data-stu-id="aad6c-109">Type the name of the action.</span></span>  
  
 <span data-ttu-id="aad6c-110">**Цель действия**</span><span class="sxs-lookup"><span data-stu-id="aad6c-110">**Action Target**</span></span>  
 <span data-ttu-id="aad6c-111">Разверните, чтобы получить доступ к параметру **Элементы группы мер** .</span><span class="sxs-lookup"><span data-stu-id="aad6c-111">Expand to view the **Measure group members** option.</span></span>  
  
 <span data-ttu-id="aad6c-112">**Элементы группы мер**</span><span class="sxs-lookup"><span data-stu-id="aad6c-112">**Measure group members**</span></span>  
 <span data-ttu-id="aad6c-113">Выберите группу мер, с которой нужно связать действие детализации.</span><span class="sxs-lookup"><span data-stu-id="aad6c-113">Select the measure group to which the drillthrough action is to be associated.</span></span>  
  
 <span data-ttu-id="aad6c-114">**Условие (необязательно)**</span><span class="sxs-lookup"><span data-stu-id="aad6c-114">**Condition (Optional)**</span></span>  
 <span data-ttu-id="aad6c-115">Введите многомерное выражение, описывающее дополнительное условие, которое используется вместе с параметром **Элементы группы мер**и еще более ограничивает доступность действия.</span><span class="sxs-lookup"><span data-stu-id="aad6c-115">Enter the Multidimensional Expressions (MDX) expression that describes an optional condition, used in conjunction with **Measure group members**, which further restricts when the action is available.</span></span> <span data-ttu-id="aad6c-116">Выражение должно возвращать логическое значение; значение true означает, что действие доступно.</span><span class="sxs-lookup"><span data-stu-id="aad6c-116">The expression must return a Boolean value that, if true, indicates the action is available.</span></span>  
  
 <span data-ttu-id="aad6c-117">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="aad6c-117">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="aad6c-118">**Столбцы детализации**</span><span class="sxs-lookup"><span data-stu-id="aad6c-118">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="aad6c-119">Раскройте, чтобы отобразить сетку, позволяющую определить атрибуты, которые возвращаются, когда пользователь запускает действие.</span><span class="sxs-lookup"><span data-stu-id="aad6c-119">Expand to display a grid in which to indicate the attributes that are returned when the user runs this action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aad6c-120">Можно выбрать несколько измерений, но каждое из них нельзя использовать более одного раза в действии детализации.</span><span class="sxs-lookup"><span data-stu-id="aad6c-120">You can select more than one dimension, but no dimension can be used more than once in a drillthrough action.</span></span>  
  
 <span data-ttu-id="aad6c-121">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="aad6c-121">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="aad6c-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="aad6c-122">Column</span></span>|<span data-ttu-id="aad6c-123">Описание</span><span class="sxs-lookup"><span data-stu-id="aad6c-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="aad6c-124">**Измерения**</span><span class="sxs-lookup"><span data-stu-id="aad6c-124">**Dimensions**</span></span>|<span data-ttu-id="aad6c-125">Выберите измерение, в котором находится возвращаемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="aad6c-125">Select the dimension from which the returned attribute is derived.</span></span> <span data-ttu-id="aad6c-126">Выберите MEASURES для детализации по мерам.</span><span class="sxs-lookup"><span data-stu-id="aad6c-126">Select MEASURES to drillthrough on measures.</span></span>|  
|<span data-ttu-id="aad6c-127">**Возвращаемые столбцы**</span><span class="sxs-lookup"><span data-stu-id="aad6c-127">**Return Columns**</span></span>|<span data-ttu-id="aad6c-128">Укажите атрибут или меру из выбранного измерения, который должен возвращаться при выполнении действия.</span><span class="sxs-lookup"><span data-stu-id="aad6c-128">Select the attribute or measure from the selected dimension to be returned when the action is run.</span></span>|  
  
 <span data-ttu-id="aad6c-129">**Дополнительные свойства**</span><span class="sxs-lookup"><span data-stu-id="aad6c-129">**Additional Properties**</span></span>  
 <span data-ttu-id="aad6c-130">Разверните, чтобы получить доступ к параметрам **По умолчанию**, **Максимальное количество строк**, **Вызов**, **Приложение**, **Описание**, **Заголовок**и **Заголовок — многомерное выражение** .</span><span class="sxs-lookup"><span data-stu-id="aad6c-130">Expand to view the **Default**, **Maximum rows**, **Invocation**, **Application**, **Description**, **Caption**, and **Caption Is MDX** options.</span></span>  
  
 <span data-ttu-id="aad6c-131">**Default**</span><span class="sxs-lookup"><span data-stu-id="aad6c-131">**Default**</span></span>  
 <span data-ttu-id="aad6c-132">Выберите **True** , если хотите включить действие в список действий детализации по умолчанию, в противном случае выберите **False**.</span><span class="sxs-lookup"><span data-stu-id="aad6c-132">Select **True** to include this drillthrough action as a default drillthrough action, otherwise, select **False**.</span></span>  
  
 <span data-ttu-id="aad6c-133">Если `RETURN` предложение не указано в инструкции многомерных выражений `DRILLTHROUGH` , выполняемом клиентским приложением, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] экземпляр оценивает все действия детализации по умолчанию и запускает первое действие детализации по умолчанию, которое возвращает непустой набор.</span><span class="sxs-lookup"><span data-stu-id="aad6c-133">If the `RETURN` clause is omitted from an MDX `DRILLTHROUGH` statement executed by a client application, the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance evaluates all default drillthrough actions and runs the first default drillthrough action that returns a non-empty set.</span></span> <span data-ttu-id="aad6c-134">Дополнительные сведения об инструкции многомерных выражений `DRILLTHROUGH` см. в разделе [инструкция детализации &#40;&#41;многомерных выражений ](/sql/mdx/mdx-data-manipulation-drillthrough).</span><span class="sxs-lookup"><span data-stu-id="aad6c-134">For more information about the MDX `DRILLTHROUGH` statement, see [DRILLTHROUGH Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aad6c-135">Данный параметр обеспечивает обратную совместимость.</span><span class="sxs-lookup"><span data-stu-id="aad6c-135">This option is used for backwards compatibility purposes.</span></span>  
  
 <span data-ttu-id="aad6c-136">**Максимальное число строк**</span><span class="sxs-lookup"><span data-stu-id="aad6c-136">**Maximum rows**</span></span>  
 <span data-ttu-id="aad6c-137">Введите максимальное число строк, которое может возвращать действие детализации.</span><span class="sxs-lookup"><span data-stu-id="aad6c-137">Type the maximum number of rows to be returned by the drillthrough action.</span></span> <span data-ttu-id="aad6c-138">Значение данного параметра, равное 0 или пустому значению, означает, что действие детализации возвращает все полученные строки клиентскому приложению.</span><span class="sxs-lookup"><span data-stu-id="aad6c-138">Setting this option to zero or an empty value indicates that the drillthrough action returns all rows retrieved by the action to the client application.</span></span>  
  
 <span data-ttu-id="aad6c-139">**Вызов**</span><span class="sxs-lookup"><span data-stu-id="aad6c-139">**Invocation**</span></span>  
 <span data-ttu-id="aad6c-140">Выберите настройку, указывающую, когда действие должно быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="aad6c-140">Select the setting that indicates when the action should be carried out.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aad6c-141">Этот параметр только рекомендует клиентскому приложению, когда следует выполнить действие, однако непосредственно вызов действия он не контролирует.</span><span class="sxs-lookup"><span data-stu-id="aad6c-141">This option only provides a recommendation to a client application as to when to execute an action, and does not directly control the invocation of the action.</span></span>  
  
 <span data-ttu-id="aad6c-142">В следующей таблице описываются доступные настройки.</span><span class="sxs-lookup"><span data-stu-id="aad6c-142">The following table describes the available settings.</span></span>  
  
|<span data-ttu-id="aad6c-143">Значение</span><span class="sxs-lookup"><span data-stu-id="aad6c-143">Value</span></span>|<span data-ttu-id="aad6c-144">Описание</span><span class="sxs-lookup"><span data-stu-id="aad6c-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aad6c-145">Пакетная служба</span><span class="sxs-lookup"><span data-stu-id="aad6c-145">Batch</span></span>|<span data-ttu-id="aad6c-146">Действие должно выполняться в составе пакетной операции или задачи служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aad6c-146">The action should run as part of a batch operation or an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] task.</span></span>|  
|<span data-ttu-id="aad6c-147">Интерактивно</span><span class="sxs-lookup"><span data-stu-id="aad6c-147">Interactive</span></span>|<span data-ttu-id="aad6c-148">Действие запускается при вызове его пользователем.</span><span class="sxs-lookup"><span data-stu-id="aad6c-148">The action runs when the user invokes the action.</span></span>|  
|<span data-ttu-id="aad6c-149">При открытии</span><span class="sxs-lookup"><span data-stu-id="aad6c-149">On Open</span></span>|<span data-ttu-id="aad6c-150">Действие запускается при первом открытии куба.</span><span class="sxs-lookup"><span data-stu-id="aad6c-150">The action runs when the cube is first opened.</span></span>|  
  
 <span data-ttu-id="aad6c-151">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="aad6c-151">**Application**</span></span>  
 <span data-ttu-id="aad6c-152">Введите имя приложения, которое может выполнять действие детализации.</span><span class="sxs-lookup"><span data-stu-id="aad6c-152">Type the name of the application that can execute the drillthrough action.</span></span>  
  
 <span data-ttu-id="aad6c-153">Помимо этого, данный параметр может использоваться для определения клиентского приложения, которое вызывает данное действие чаще всего, а также для отображения соответствующих значков возле действия во всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="aad6c-153">You can also use this option to identify which client application most commonly uses this action, as well as to display appropriate icons next to the action in a pop-up menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aad6c-154">Этот параметр только рекомендует клиентскому приложению, какое клиентское приложение должно выполнять действие, однако непосредственно доступ к действию он не контролирует.</span><span class="sxs-lookup"><span data-stu-id="aad6c-154">This option only provides a recommendation to a client application as to what client application should execute an action, and does not directly control access to the action.</span></span> <span data-ttu-id="aad6c-155">Клиентские приложения должны скрывать все связанные с другими приложениями действия.</span><span class="sxs-lookup"><span data-stu-id="aad6c-155">Client applications should hide any actions that are associated with other client applications.</span></span>  
  
 <span data-ttu-id="aad6c-156">**Описание**</span><span class="sxs-lookup"><span data-stu-id="aad6c-156">**Description**</span></span>  
 <span data-ttu-id="aad6c-157">Введите необязательное описание действия.</span><span class="sxs-lookup"><span data-stu-id="aad6c-157">Type the optional description of the action.</span></span>  
  
 <span data-ttu-id="aad6c-158">**Caption**</span><span class="sxs-lookup"><span data-stu-id="aad6c-158">**Caption**</span></span>  
 <span data-ttu-id="aad6c-159">Введите заголовок, под которым действие будет отображаться в клиентском приложении в случае, если параметру **Заголовок — многомерное выражение** присвоено значение **False**.</span><span class="sxs-lookup"><span data-stu-id="aad6c-159">Type the caption to be displayed for the action in the client application if **Caption Is MDX** is set to **False**.</span></span>  
  
 <span data-ttu-id="aad6c-160">Введите многомерное выражение, которое будет возвращать строку для заголовка, если в качестве значения **Заголовок является многомерным выражением** указано **True**.</span><span class="sxs-lookup"><span data-stu-id="aad6c-160">Type the Multidimensional Expressions (MDX) expression that returns a string for the caption if **Caption Is MDX** is set to **True**.</span></span>  
  
 <span data-ttu-id="aad6c-161">**Заголовок — многомерное выражение**</span><span class="sxs-lookup"><span data-stu-id="aad6c-161">**Caption Is MDX**</span></span>  
 <span data-ttu-id="aad6c-162">Выберите значение **False** , чтобы указать, что **Заголовок** содержит буквенную строку, представляющую собой заголовок, под которым действие будет отображаться в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="aad6c-162">Select **False** to indicate that **Caption** contains a literal string representing a caption to be displayed for the action in the client application.</span></span>  
  
 <span data-ttu-id="aad6c-163">Выберите значение **True** , чтобы указать, что **Заголовок** содержит многомерное выражение, возвращающее строку заголовка, под которым действие будет отображаться в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="aad6c-163">Select **True** to indicate that **Caption** contains an MDX expression that returns a string representing a caption to be displayed for the action in the client application.</span></span> <span data-ttu-id="aad6c-164">Многомерное выражение должно быть вычислено до возврата действия клиентскому приложению.</span><span class="sxs-lookup"><span data-stu-id="aad6c-164">The MDX expression must be resolved before the action is returned to the client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad6c-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="aad6c-165">See Also</span></span>  
 <span data-ttu-id="aad6c-166">[Многомерные выражения &#40;Справочник по&#41; MDX](/sql/mdx/multidimensional-expressions-mdx-reference) </span><span class="sxs-lookup"><span data-stu-id="aad6c-166">[Multidimensional Expressions &#40;MDX&#41; Reference](/sql/mdx/multidimensional-expressions-mdx-reference) </span></span>  
 <span data-ttu-id="aad6c-167">[Действия &#40;конструкторе кубов&#41; &#40;Analysis Services многомерных данных&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="aad6c-167">[Actions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="aad6c-168">[Панель инструментов &#40;вкладка "действия" конструктора кубов&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="aad6c-168">[Toolbar &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="aad6c-169">[Организатор действий &#40;вкладка "действия", конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="aad6c-169">[Action Organizer &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="aad6c-170">[Средства вычисления &#40;вкладка «действия», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="aad6c-170">[Calculation Tools &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="aad6c-171">[Редактор формы действия &#40;вкладка "действия", конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="aad6c-171">[Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="aad6c-172">Редактор формы действия отчета &#40;вкладка "действия", конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="aad6c-172">Report Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](report-action-form-editor-cube-designer-analysis-services-multidimensional-data.md)  
  
  
