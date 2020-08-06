---
title: Диалоговое окно «Выбор цвета» (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.selectcolor.f1
- "10090"
helpviewer_keywords:
- Select Color dialog box
ms.assetid: ac7089a3-5c7b-4f53-8348-180610e86da2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a2526b755fd4e08faf79998d351e824371fac2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739143"
---
# <a name="select-color-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="955ba-102">Диалоговое окно «Выбор цвета» (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="955ba-102">Select Color Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="955ba-103">Используйте диалоговое окно **Выбор цвета** , чтобы указать параметры цвета для фона одной или нескольких ячеек в области данных или текстовом поле либо для всей диаграммы.</span><span class="sxs-lookup"><span data-stu-id="955ba-103">Use the **Select Color** dialog box to specify color options for the background of a single cell or multiple cells within a data region or a text box, or for a chart.</span></span>  
  
## <a name="options"></a><span data-ttu-id="955ba-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="955ba-104">Options</span></span>  
 <span data-ttu-id="955ba-105">**Средство выбора цвета**</span><span class="sxs-lookup"><span data-stu-id="955ba-105">**Color selector**</span></span>  
 <span data-ttu-id="955ba-106">Выберите один из трех параметров, указывающих способ выбора цветов.</span><span class="sxs-lookup"><span data-stu-id="955ba-106">Choose from three options that specify how you want to select colors:</span></span>  
  
-   <span data-ttu-id="955ba-107">**Выбор цвета — цветовая окружность** : выбирает цвет с использованием цветовых значений цветового тона, насыщенности и яркости (HSB).</span><span class="sxs-lookup"><span data-stu-id="955ba-107">**Picker - Color circle** Choose a color using Hue/Saturation/Brightness (HSB) color values.</span></span>  
  
-   <span data-ttu-id="955ba-108">**Выбор цвета — цветовой квадрат** : выбирает цвет с использованием цветовых значений красного, зеленого и синего (RGB).</span><span class="sxs-lookup"><span data-stu-id="955ba-108">**Picker - Color square** Choose a color using Red/Green/Blue (RGB) color values.</span></span>  
  
-   <span data-ttu-id="955ba-109">**Палитра — стандартные цвета** : позволяет выбрать цвет из заранее определенного списка цветовых значений.</span><span class="sxs-lookup"><span data-stu-id="955ba-109">**Palette - Standard colors** Choose a color from a predefined list of color values.</span></span>  
  
 <span data-ttu-id="955ba-110">**Цветовая окружность**</span><span class="sxs-lookup"><span data-stu-id="955ba-110">**Color circle**</span></span>  
 <span data-ttu-id="955ba-111">Используется для цветов HSB, поскольку значения HSB сопоставляются со значениями в цилиндрической системе координат.</span><span class="sxs-lookup"><span data-stu-id="955ba-111">Use for HSB colors because HSB values are mapped onto a cylindrical coordinate system.</span></span> <span data-ttu-id="955ba-112">Цветовым тоном является фактический цвет, насыщенность рассматривается как чистота цвета, а яркость — как относительная яркость или затемнение.</span><span class="sxs-lookup"><span data-stu-id="955ba-112">Hue is the actual color, saturation is purity of color, brightness is relative brightness or darkness.</span></span>  
  
 <span data-ttu-id="955ba-113">Выбор цвета определяется цветом в центре круга.</span><span class="sxs-lookup"><span data-stu-id="955ba-113">When you pick a color, the center of the circle determines the color.</span></span> <span data-ttu-id="955ba-114">Используйте ползунок шкалы цвета, чтобы изменить цветовой тон.</span><span class="sxs-lookup"><span data-stu-id="955ba-114">Use the color slider to change the hue.</span></span> <span data-ttu-id="955ba-115">Координаты X и Y представляют, соответственно, значения насыщенности и яркости.</span><span class="sxs-lookup"><span data-stu-id="955ba-115">The x and y coordinates represent saturation and brightness values respectively.</span></span>  
  
 <span data-ttu-id="955ba-116">**Цветовой квадрат**</span><span class="sxs-lookup"><span data-stu-id="955ba-116">**Color square**</span></span>  
 <span data-ttu-id="955ba-117">Используется для цветов RGB, поскольку значения RGB сопоставляются со значениями в декартовой системе координат.</span><span class="sxs-lookup"><span data-stu-id="955ba-117">Use for RGB colors because RGB values are mapped to a Cartesian coordinate system.</span></span> <span data-ttu-id="955ba-118">R — значение для красного, G — значение для зеленого, B — значение для синего.</span><span class="sxs-lookup"><span data-stu-id="955ba-118">R is the value for Red, G is the value for Green, B is the value for Blue.</span></span>  
  
 <span data-ttu-id="955ba-119">Цвет определяется цветом в центре квадрата.</span><span class="sxs-lookup"><span data-stu-id="955ba-119">When you pick a color, the center of the square determines the color.</span></span> <span data-ttu-id="955ba-120">Используйте ползунок шкалы цвета, чтобы изменить диапазон выбранного цвета.</span><span class="sxs-lookup"><span data-stu-id="955ba-120">Use the color slider to change the range of the chosen color.</span></span> <span data-ttu-id="955ba-121">Координаты X и Y представляют другие два цвета.</span><span class="sxs-lookup"><span data-stu-id="955ba-121">The x and y coordinates represent the other two colors.</span></span> <span data-ttu-id="955ba-122">Например, если выбран зеленый компонент, ползунок отображает диапазон значений зеленого, а координаты X и Y представляют, соответственно, значения красного и синего.</span><span class="sxs-lookup"><span data-stu-id="955ba-122">For example, if you pick green, the slider shows the range of green values, the x and y coordinates represent red and blue values respectively.</span></span>  
  
 <span data-ttu-id="955ba-123">**Цвет из стандартной палитры**</span><span class="sxs-lookup"><span data-stu-id="955ba-123">**Standard palette color**</span></span>  
 <span data-ttu-id="955ba-124">Используйте для именованных цветов из [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` перечисления.</span><span class="sxs-lookup"><span data-stu-id="955ba-124">Use for named colors from the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` enumeration.</span></span>  
  
 <span data-ttu-id="955ba-125">**Цветовая система**</span><span class="sxs-lookup"><span data-stu-id="955ba-125">**Color system**</span></span>  
 <span data-ttu-id="955ba-126">Укажите цвета HSB или RGB.</span><span class="sxs-lookup"><span data-stu-id="955ba-126">Specify RGB or HSB colors.</span></span> <span data-ttu-id="955ba-127">В этом варианте изменяется отображение, чтобы в нем были показаны значения RGB или HSB, которые обновляются в интерактивном режиме при использовании цветовой окружности или цветового квадрата в качестве **средства выбора цвета**.</span><span class="sxs-lookup"><span data-stu-id="955ba-127">This choice changes the display to show RGB or HSB values, which are updated interactively when you use a color circle or color square for the **Color selector**.</span></span>  
  
 <span data-ttu-id="955ba-128">Для некоторых свойств отображается значение коэффициента **альфа** , если цвет может включать значение прозрачности.</span><span class="sxs-lookup"><span data-stu-id="955ba-128">The **Alpha** value displays for some properties when a color can include a transparency value.</span></span> <span data-ttu-id="955ba-129">Примером является заливка ряда диаграммы.</span><span class="sxs-lookup"><span data-stu-id="955ba-129">For example, Chart series fill.</span></span> <span data-ttu-id="955ba-130">Применительно к свойствам, которые не поддерживают прозрачность, это значение отключено.</span><span class="sxs-lookup"><span data-stu-id="955ba-130">For properties that do not support transparency, this value is disabled.</span></span>  
  
 <span data-ttu-id="955ba-131">**Красный**</span><span class="sxs-lookup"><span data-stu-id="955ba-131">**Red**</span></span>  
 <span data-ttu-id="955ba-132">Десятичное значение для красного компонента цвета RGB.</span><span class="sxs-lookup"><span data-stu-id="955ba-132">The decimal value for the red part of the RGB color.</span></span> <span data-ttu-id="955ba-133">Введите или задайте с помощью счетчика значение в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="955ba-133">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="955ba-134">**Зеленый**</span><span class="sxs-lookup"><span data-stu-id="955ba-134">**Green**</span></span>  
 <span data-ttu-id="955ba-135">Десятичное значение для зеленого компонента цвета RGB.</span><span class="sxs-lookup"><span data-stu-id="955ba-135">The decimal value for the green part of the RGB color.</span></span> <span data-ttu-id="955ba-136">Введите или задайте с помощью счетчика значение в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="955ba-136">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="955ba-137">**Синий**</span><span class="sxs-lookup"><span data-stu-id="955ba-137">**Blue**</span></span>  
 <span data-ttu-id="955ba-138">Десятичное значение для синего компонента цвета RGB.</span><span class="sxs-lookup"><span data-stu-id="955ba-138">The decimal value for the blue part of the RGB color.</span></span> <span data-ttu-id="955ba-139">Введите или задайте с помощью счетчика значение в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="955ba-139">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="955ba-140">**Коэффициент альфа**</span><span class="sxs-lookup"><span data-stu-id="955ba-140">**Alpha**</span></span>  
 <span data-ttu-id="955ba-141">Десятичное значение для компонента цвета, определяющего коэффициент альфа или прозрачность.</span><span class="sxs-lookup"><span data-stu-id="955ba-141">The decimal value for the alpha or transparency part of the color.</span></span> <span data-ttu-id="955ba-142">Если применение этого значения разрешено, можно использовать переключатель в виде ползунка для настройки требуемой степени прозрачности.</span><span class="sxs-lookup"><span data-stu-id="955ba-142">When this value is enabled, you can use the slider switch to adjust the degree of transparency you want.</span></span>  
  
 <span data-ttu-id="955ba-143">**Hue**</span><span class="sxs-lookup"><span data-stu-id="955ba-143">**Hue**</span></span>  
 <span data-ttu-id="955ba-144">Десятичное значение для цветового тона цвета HSB.</span><span class="sxs-lookup"><span data-stu-id="955ba-144">The decimal value for the hue of the HSB color.</span></span> <span data-ttu-id="955ba-145">Введите или задайте с помощью счетчика значение в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="955ba-145">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="955ba-146">**Насыщенность**</span><span class="sxs-lookup"><span data-stu-id="955ba-146">**Saturation**</span></span>  
 <span data-ttu-id="955ba-147">Десятичное значение для насыщенности цвета HSB.</span><span class="sxs-lookup"><span data-stu-id="955ba-147">The decimal value for the saturation of the HSB color.</span></span> <span data-ttu-id="955ba-148">Введите или задайте с помощью счетчика значение в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="955ba-148">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="955ba-149">**Яркость**</span><span class="sxs-lookup"><span data-stu-id="955ba-149">**Brightness**</span></span>  
 <span data-ttu-id="955ba-150">Десятичное значение для яркости цвета HSB.</span><span class="sxs-lookup"><span data-stu-id="955ba-150">The decimal value for the brightness of the HSB color.</span></span> <span data-ttu-id="955ba-151">Введите или задайте с помощью счетчика значение в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="955ba-151">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="955ba-152">**Образец цвета**</span><span class="sxs-lookup"><span data-stu-id="955ba-152">**Color sample**</span></span>  
 <span data-ttu-id="955ba-153">Отображает текущий цвет в левой половине панели и в интерактивном режиме отображает новый выбранный цвет в правой половине панели.</span><span class="sxs-lookup"><span data-stu-id="955ba-153">Shows the current color on the left half of the pane and interactively shows the new color you are choosing on the right half of the pane.</span></span> <span data-ttu-id="955ba-154">Если цвет по умолчанию отсутствует, то в левой половине панели отображается белый цвет.</span><span class="sxs-lookup"><span data-stu-id="955ba-154">If there is no default color, the left half of the pane is white.</span></span> <span data-ttu-id="955ba-155">У большинства свойств языка определения отчетов цвет по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="955ba-155">Most RDL properties have no default color.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="955ba-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="955ba-156">See Also</span></span>  
 <span data-ttu-id="955ba-157">[Форматирование элементов отчета &#40;построитель отчетов и SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="955ba-157">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="955ba-158">Форматирование текста и заполнителей (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="955ba-158">Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;</span></span>](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md)  
  
  
