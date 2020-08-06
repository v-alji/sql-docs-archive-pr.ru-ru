---
title: Редактор форм вычисляемых элементов (вкладка «вычисления», конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationexpression.calculatedmember.f1
ms.assetid: f7719b9e-b1e6-4792-90a6-30d9d8eb1196
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dd45ece03fd81e0e7356e7bdcd0ec8dc53287bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656805"
---
# <a name="calculated-member-form-editor-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="56e6b-102">Редактор форм вычисляемых элементов (вкладка «Вычисления», конструктор кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="56e6b-102">Calculated Member Form Editor (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="56e6b-103">Используйте панель **Редактор форм вычисляемых элементов** на вкладке **Вычисления** в конструкторе кубов для создания или изменения вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-103">Use the **Calculated Member Form Editor** pane on the **Calculations** tab in Cube Designer to create or modify a calculated member.</span></span>  
  
 <span data-ttu-id="56e6b-104">**Примечание.** Данная панель отображается только в представлении формы.</span><span class="sxs-lookup"><span data-stu-id="56e6b-104">**Note** This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="56e6b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="56e6b-105">Options</span></span>  
 <span data-ttu-id="56e6b-106">**имя**;</span><span class="sxs-lookup"><span data-stu-id="56e6b-106">**Name**</span></span>  
 <span data-ttu-id="56e6b-107">Введите имя вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-107">Type the name of the calculated member.</span></span>  
  
 <span data-ttu-id="56e6b-108">**Свойства родителя**</span><span class="sxs-lookup"><span data-stu-id="56e6b-108">**Parent Properties**</span></span>  
 <span data-ttu-id="56e6b-109">Разверните параметры **Родительская иерархия**, **Родительский элемент**и **Изменить** .</span><span class="sxs-lookup"><span data-stu-id="56e6b-109">Expand to view the **Parent hierarchy**, **Parent member**, and **Change** options.</span></span>  
  
 <span data-ttu-id="56e6b-110">**Родительская иерархия**</span><span class="sxs-lookup"><span data-stu-id="56e6b-110">**Parent hierarchy**</span></span>  
 <span data-ttu-id="56e6b-111">Выберите измерение и иерархию выбранного куба для включения в вычисляемый элемент.</span><span class="sxs-lookup"><span data-stu-id="56e6b-111">Select the dimension and hierarchy in the selected cube that is to include the calculated member.</span></span> <span data-ttu-id="56e6b-112">Выберите MEASURES для определения вычисляемой меры.</span><span class="sxs-lookup"><span data-stu-id="56e6b-112">Select MEASURES to define a calculated measure.</span></span>  
  
 <span data-ttu-id="56e6b-113">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="56e6b-113">**Parent member**</span></span>  
 <span data-ttu-id="56e6b-114">Выберите элемент, под которым должен отобразиться вычисляемый элемент.</span><span class="sxs-lookup"><span data-stu-id="56e6b-114">Select the member beneath which the calculated member is to appear.</span></span>  
  
 <span data-ttu-id="56e6b-115">**Примечание.** Этот параметр доступен, если **Родительская иерархия** определяет иерархию, отличную от MEASURES.</span><span class="sxs-lookup"><span data-stu-id="56e6b-115">**Note** This option is available if **Parent hierarchy** specifies a hierarchy other than MEASURES.</span></span>  
  
 <span data-ttu-id="56e6b-116">**Изменение**</span><span class="sxs-lookup"><span data-stu-id="56e6b-116">**Change**</span></span>  
 <span data-ttu-id="56e6b-117">Выберите для отображения диалоговое окно **Выбор родительского элемента** и выберите **Родительский элемент**.</span><span class="sxs-lookup"><span data-stu-id="56e6b-117">Select to display the **Select Parent Member** dialog box and choose a member for **Parent member**.</span></span> <span data-ttu-id="56e6b-118">Дополнительные сведения о диалоговом окне **Выбор родительского элемента** см. в разделе [Диалоговое окно "Выбор родительского элемента" (службы Analysis Services — многомерные данные)](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="56e6b-118">For more information about the **Select Parent Member** dialog box, see [Select Parent Member Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="56e6b-119">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="56e6b-119">**Expression**</span></span>  
 <span data-ttu-id="56e6b-120">Разверните для просмотра или редактирования многомерного выражения для вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-120">Expand to view or edit the Multidimensional Expressions (MDX) expression for the calculated member.</span></span>  
  
 <span data-ttu-id="56e6b-121">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-121">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56e6b-122">Рекомендуется, чтобы результат этого выражения был строкой или числовым значением.</span><span class="sxs-lookup"><span data-stu-id="56e6b-122">It is recommended that this expression evaluate to a string or to a numeric value.</span></span>  
  
 <span data-ttu-id="56e6b-123">**Дополнительные свойства**</span><span class="sxs-lookup"><span data-stu-id="56e6b-123">**Additional Properties**</span></span>  
 <span data-ttu-id="56e6b-124">Разверните для просмотра параметров **Строка форматирования**, **Видимый**, **Установленное поведение**, **Выражения цвета**и **Выражения шрифта** .</span><span class="sxs-lookup"><span data-stu-id="56e6b-124">Expand to view the **Format string**, **Visible**, **Non-empty behavior**, **Color Expressions**, and **Font Expressions** options.</span></span>  
  
 <span data-ttu-id="56e6b-125">**Строка форматирования**</span><span class="sxs-lookup"><span data-stu-id="56e6b-125">**Format string**</span></span>  
 <span data-ttu-id="56e6b-126">Введите строку формата многомерного выражения для форматирования значения, возвращаемого вычисляемым элементом, или выберите стандартную строку формата.</span><span class="sxs-lookup"><span data-stu-id="56e6b-126">Type the MDX format string used to format the value returned by the calculated member, or select a predefined format string.</span></span>  
  
 <span data-ttu-id="56e6b-127">Дополнительные сведения о строках форматирования многомерных выражений см. в разделе [Строка формата FORMAT_STRING (многомерные выражения)](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span><span class="sxs-lookup"><span data-stu-id="56e6b-127">For more information about MDX format strings, see [FORMAT_STRING Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span></span>  
  
 <span data-ttu-id="56e6b-128">**Видимый**</span><span class="sxs-lookup"><span data-stu-id="56e6b-128">**Visible**</span></span>  
 <span data-ttu-id="56e6b-129">Выберите значение **True** , чтобы сделать видимым вычисляемый элемент для клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="56e6b-129">Select **True** to allow the calculated member to be visible to client applications.</span></span>  
  
 <span data-ttu-id="56e6b-130">**Установленное поведение**</span><span class="sxs-lookup"><span data-stu-id="56e6b-130">**Non-empty behavior**</span></span>  
 <span data-ttu-id="56e6b-131">Выберите имя меры, используемого для разрешения запросов NON EMPTY в многомерных выражениях для вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-131">Select the name of the measure used to resolve NON EMPTY queries in MDX for the calculated member.</span></span> <span data-ttu-id="56e6b-132">Если свойство **Установленное поведение** пусто, вычисляемые элементы должны быть повторно получены для определения того, что элемент пуст.</span><span class="sxs-lookup"><span data-stu-id="56e6b-132">If the **Non Empty Behavior** property is blank, the calculated member must be evaluated repeatedly to determine if a member is empty.</span></span> <span data-ttu-id="56e6b-133">Если свойство **Установленное поведение** содержит имя меры, вычисляемый элемент обрабатывается как пустой, если данное измерение пусто.</span><span class="sxs-lookup"><span data-stu-id="56e6b-133">If the **Non Empty Behavior** property contains the name of a measure, the calculated member is treated as empty if the specified measure is empty.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="56e6b-134">Это свойство использовать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="56e6b-134">This property is deprecated.</span></span> <span data-ttu-id="56e6b-135">Не задавайте его.</span><span class="sxs-lookup"><span data-stu-id="56e6b-135">Avoid setting it.</span></span> <span data-ttu-id="56e6b-136">Дополнительные сведения см. [в статье нерекомендуемые Analysis Services функции в SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) .</span><span class="sxs-lookup"><span data-stu-id="56e6b-136">See [Deprecated Analysis Services Features in SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) for details.</span></span>  
  
 <span data-ttu-id="56e6b-137">**Выражения цвета**</span><span class="sxs-lookup"><span data-stu-id="56e6b-137">**Color Expressions**</span></span>  
 <span data-ttu-id="56e6b-138">Развернуть для просмотра параметров **Цвет текста** и **Цвет фона** .</span><span class="sxs-lookup"><span data-stu-id="56e6b-138">Expand to view the **Fore color** and **Back color** options.</span></span>  
  
 <span data-ttu-id="56e6b-139">**Цвет текста**</span><span class="sxs-lookup"><span data-stu-id="56e6b-139">**Fore color**</span></span>  
 <span data-ttu-id="56e6b-140">Введите многомерное выражение, которое отражает цвет переднего плана для вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-140">Type the MDX expression that provides the foreground color of the calculated member.</span></span>  
  
 <span data-ttu-id="56e6b-141">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-141">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56e6b-142">Нажмите кнопку выбора цвета, чтобы открыть диалоговое окно **Цвет** , и введите значение RGB (красный, зеленый, синий) для выбранного цвета в многомерное выражение.</span><span class="sxs-lookup"><span data-stu-id="56e6b-142">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="56e6b-143">Дополнительные сведения о значениях RGB см. в разделе [Свойства ячеек FORE_COLOR и BACK_COLOR (многомерные выражения)](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="56e6b-143">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="56e6b-144">**Цвет фона**</span><span class="sxs-lookup"><span data-stu-id="56e6b-144">**Back color**</span></span>  
 <span data-ttu-id="56e6b-145">Введите многомерное выражение, которое задает цвет фона для вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-145">Type the MDX expression that provides the background color of the calculated member.</span></span>  
  
 <span data-ttu-id="56e6b-146">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-146">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56e6b-147">Нажмите кнопку выбора цвета, чтобы открыть диалоговое окно **Цвет** , и введите значение RGB (красный, зеленый, синий) для выбранного цвета в многомерное выражение.</span><span class="sxs-lookup"><span data-stu-id="56e6b-147">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="56e6b-148">Дополнительные сведения о значениях RGB см. в разделе [Свойства ячеек FORE_COLOR и BACK_COLOR (многомерные выражения)](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="56e6b-148">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="56e6b-149">**Выражения шрифта**</span><span class="sxs-lookup"><span data-stu-id="56e6b-149">**Font Expressions**</span></span>  
 <span data-ttu-id="56e6b-150">Разверните для просмотра параметры **Имя шрифта**, **Размер шрифта**и **Стили начертания** .</span><span class="sxs-lookup"><span data-stu-id="56e6b-150">Expand to view the **Font name**, **Font size**, and **Font flags** options.</span></span>  
  
 <span data-ttu-id="56e6b-151">**Имя шрифта**</span><span class="sxs-lookup"><span data-stu-id="56e6b-151">**Font name**</span></span>  
 <span data-ttu-id="56e6b-152">Введите многомерное выражение, которое отражает имя шрифта для вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-152">Type the MDX expression that provides the name of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="56e6b-153">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56e6b-154">Нажмите кнопку выбора шрифта, чтобы открыть диалоговое окно **Шрифт** , и введите значения параметров выбранного шрифта в многомерное выражение.</span><span class="sxs-lookup"><span data-stu-id="56e6b-154">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="56e6b-155">Дополнительные сведения о значениях свойств см. в разделе [Создание и использование значений свойств (многомерные выражения)](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="56e6b-155">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="56e6b-156">**Размер шрифта**</span><span class="sxs-lookup"><span data-stu-id="56e6b-156">**Font size**</span></span>  
 <span data-ttu-id="56e6b-157">Введите многомерное выражение, которое отражает размер шрифта для вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-157">Type the MDX expression that provides the size of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="56e6b-158">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-158">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56e6b-159">Нажмите кнопку выбора шрифта, чтобы открыть диалоговое окно **Шрифт** , и введите значения параметров выбранного шрифта в многомерное выражение.</span><span class="sxs-lookup"><span data-stu-id="56e6b-159">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="56e6b-160">Дополнительные сведения о значениях свойств см. в разделе [Создание и использование значений свойств (многомерные выражения)](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="56e6b-160">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="56e6b-161">**Стили начертания**</span><span class="sxs-lookup"><span data-stu-id="56e6b-161">**Font flags**</span></span>  
 <span data-ttu-id="56e6b-162">Введите многомерное выражение, которое отражает растровое значение, содержащее стили начертания шрифта, такие как подчеркивание или выделение полужирным шрифтом, для вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-162">Type the MDX expression that provides the bitmapped value containing the font flags, such as underline or bold, of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="56e6b-163">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="56e6b-163">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56e6b-164">Нажмите кнопку выбора шрифта, чтобы открыть диалоговое окно **Шрифт** , и введите значения параметров выбранного шрифта в многомерное выражение.</span><span class="sxs-lookup"><span data-stu-id="56e6b-164">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="56e6b-165">Дополнительные сведения о значениях свойств см. в разделе [Создание и использование значений свойств (многомерные выражения)](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="56e6b-165">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e6b-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="56e6b-166">See Also</span></span>  
 <span data-ttu-id="56e6b-167">[Времен](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="56e6b-167">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="56e6b-168">[Создание вычисляемых элементов](multidimensional-models/create-calculated-members.md) </span><span class="sxs-lookup"><span data-stu-id="56e6b-168">[Create Calculated Members](multidimensional-models/create-calculated-members.md) </span></span>  
 <span data-ttu-id="56e6b-169">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="56e6b-169">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="56e6b-170">[Вычисления &#40;конструкторе кубов&#41; &#40;Analysis Services многомерных данных&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="56e6b-170">[Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="56e6b-171">[Панель инструментов &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="56e6b-171">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="56e6b-172">[Коллекция скриптов &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="56e6b-172">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="56e6b-173">[Средства вычисления &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="56e6b-173">[Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="56e6b-174">[Редактор формы именованных наборов &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="56e6b-174">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="56e6b-175">Редактор скриптов &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="56e6b-175">Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
