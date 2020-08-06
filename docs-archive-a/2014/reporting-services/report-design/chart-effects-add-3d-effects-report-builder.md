---
title: Добавление в диаграмму объемных эффектов (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab9625d8-6557-4a4d-8123-eefa7c066ff5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4fcd90452e32b760bc446ac5d085ed00520a2f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667592"
---
# <a name="add-3d-effects-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="874c4-102">Добавление в диаграмму объемных эффектов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="874c4-102">Add 3D Effects to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="874c4-103">Объемные (трехмерные) эффекты можно использовать, чтобы добавить диаграмме глубину и увеличить ее визуальную привлекательность.</span><span class="sxs-lookup"><span data-stu-id="874c4-103">Three-dimensional (3D) effects can be used to provide depth and add visual impact to your chart.</span></span> <span data-ttu-id="874c4-104">Например, если нужно выделить отдельный срез разрезанной круговой диаграммы, можно повернуть диаграмму и изменить перспективу так, что пользователи обратят внимание на этот сегмент в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="874c4-104">For example, if you want to emphasize a particular slice of an exploded pie chart, you can rotate and change the perspective of the chart so that people notice that slice first.</span></span> <span data-ttu-id="874c4-105">После применения объемных эффектов к диаграмме все цвета градиента и стили штриховки отключаются.</span><span class="sxs-lookup"><span data-stu-id="874c4-105">When 3D effects are applied to your chart, all gradient colors and hatching styles are disabled.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-3d-effects-to-a-range-area-line-scatter-or-polar-chart"></a><span data-ttu-id="874c4-106">Применение объемных эффектов к диаграмме диапазона, диаграмме с областями, графику, точечной и полярной диаграмме</span><span class="sxs-lookup"><span data-stu-id="874c4-106">To apply 3D effects to a Range, Area, Line, Scatter or Polar chart</span></span>  
  
1.  <span data-ttu-id="874c4-107">Щелкните правой кнопкой мыши диаграмму и выберите пункт **Объемные эффекты**.</span><span class="sxs-lookup"><span data-stu-id="874c4-107">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="874c4-108">Открывается диалоговое окно **Свойства области диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="874c4-108">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="874c4-109">На вкладке **Параметры объемного отображения**выберите параметр **Разрешить объемные эффекты** .</span><span class="sxs-lookup"><span data-stu-id="874c4-109">In **3D Options**, select the **Enable 3D** option.</span></span>  
  
3.  <span data-ttu-id="874c4-110">На вкладке **Параметры объемного отображения**можно установить различные свойства, относящиеся к трехмерным углам и параметрам объемной сцены (необязательно).</span><span class="sxs-lookup"><span data-stu-id="874c4-110">(Optional) In **3D Options**, you can set a variety of properties relating to 3D angles and scene options.</span></span> <span data-ttu-id="874c4-111">Дополнительные сведения об этих свойствах см. в разделе [Эффекты рельефа, объемные и другие эффекты в диаграмме (построитель отчетов и службы SSRS)](chart-effects-3d-bevel-and-other-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="874c4-111">For more information about these properties, see [3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md).</span></span>  
  
4.  <span data-ttu-id="874c4-112">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="874c4-112">Click **OK**.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-funnel-chart"></a><span data-ttu-id="874c4-113">Применение объемных эффектов к воронкообразной диаграмме</span><span class="sxs-lookup"><span data-stu-id="874c4-113">To apply 3D effects to a Funnel chart</span></span>  
  
1.  <span data-ttu-id="874c4-114">Щелкните правой кнопкой мыши диаграмму и выберите пункт **Объемные эффекты**.</span><span class="sxs-lookup"><span data-stu-id="874c4-114">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="874c4-115">Открывается диалоговое окно **Свойства области диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="874c4-115">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="874c4-116">На вкладке **Параметры объемного отображения**выберите параметр **Разрешить объемные эффекты** .</span><span class="sxs-lookup"><span data-stu-id="874c4-116">In **3D Options**, select the **Enable 3D** option.</span></span> <span data-ttu-id="874c4-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="874c4-117">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="874c4-118">Чтобы настроить внешний вид воронкообразной диаграммы, можно перейти на панель «Свойства» и изменить свойства воронкообразной диаграммы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="874c4-118">(Optional) To customize the funnel chart visual appearance, you can go to the Properties pane and change properties specific to the funnel chart.</span></span>  
  
    1.  <span data-ttu-id="874c4-119">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="874c4-119">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="874c4-120">В области конструктора щелкните воронкообразную диаграмму.</span><span class="sxs-lookup"><span data-stu-id="874c4-120">On the design surface, click anywhere on the funnel.</span></span> <span data-ttu-id="874c4-121">На панели «Свойства» отобразятся свойства рядов воронкообразной диаграммы.</span><span class="sxs-lookup"><span data-stu-id="874c4-121">The properties for the series of the funnel chart are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="874c4-122">В разделе **Общие** разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="874c4-122">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
    4.  <span data-ttu-id="874c4-123">Для свойства **Funnel3DDrawingStyle** выберите, как будет отображаться воронка — с помощью круга или квадрата.</span><span class="sxs-lookup"><span data-stu-id="874c4-123">For the **Funnel3DDrawingStyle** property, select whether the funnel will be shown with as circular or square.</span></span>  
  
    5.  <span data-ttu-id="874c4-124">Для свойства **Funnel3DRotationAngle** задайте значение между -10 и 10.</span><span class="sxs-lookup"><span data-stu-id="874c4-124">For the **Funnel3DRotationAngle** property, set a value between -10 and 10.</span></span> <span data-ttu-id="874c4-125">Оно определяет угол наклона в градусах, отображаемого на объемной воронкообразной диаграмме.</span><span class="sxs-lookup"><span data-stu-id="874c4-125">This will determine the degree of tilt that will be displayed on the 3D funnel chart.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-pie-chart"></a><span data-ttu-id="874c4-126">Применение объемных эффектов к круговой диаграмме</span><span class="sxs-lookup"><span data-stu-id="874c4-126">To apply 3D effects to a Pie chart</span></span>  
  
1.  <span data-ttu-id="874c4-127">Щелкните правой кнопкой мыши диаграмму и выберите пункт «Объемные эффекты».</span><span class="sxs-lookup"><span data-stu-id="874c4-127">Right-click anywhere inside the chart area and select 3D Effects.</span></span> <span data-ttu-id="874c4-128">Открывается диалоговое окно **Свойства области диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="874c4-128">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="874c4-129">На вкладке **Параметры объемного отображения**выберите параметр **Разрешить объемные эффекты** .</span><span class="sxs-lookup"><span data-stu-id="874c4-129">In **3D Options**, select the **Enable 3D** option.</span></span> <span data-ttu-id="874c4-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="874c4-130">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="874c4-131">В поле **Вращение**введите целое число, представляющее поворот круговой диаграммы по горизонтали (необязательно).</span><span class="sxs-lookup"><span data-stu-id="874c4-131">(Optional) In **Rotation**, type an integer value that represents the horizontal rotation of the pie chart.</span></span>  
  
4.  <span data-ttu-id="874c4-132">В поле **Наклон**введите целое число, представляющее наклон круговой диаграммы по вертикали (необязательно).</span><span class="sxs-lookup"><span data-stu-id="874c4-132">(Optional) In **Inclination**, type an integer value that represents the vertical tilt rotation of the pie chart.</span></span>  
  
5.  <span data-ttu-id="874c4-133">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="874c4-133">Click **OK**.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-bar-or-column-chart"></a><span data-ttu-id="874c4-134">Применение объемных эффектов к линейчатой диаграмме или гистограмме</span><span class="sxs-lookup"><span data-stu-id="874c4-134">To apply 3D effects to a Bar or Column chart</span></span>  
  
1.  <span data-ttu-id="874c4-135">Щелкните правой кнопкой мыши диаграмму и выберите пункт **Объемные эффекты**.</span><span class="sxs-lookup"><span data-stu-id="874c4-135">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="874c4-136">Открывается диалоговое окно **Свойства области диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="874c4-136">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="874c4-137">Выберите параметр **Разрешить объемные эффекты** .</span><span class="sxs-lookup"><span data-stu-id="874c4-137">Select the **Enable 3D** option.</span></span> <span data-ttu-id="874c4-138">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="874c4-138">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="874c4-139">Выберите параметр **Включить кластеризацию рядов** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="874c4-139">(Optional) Select the **Enable series clustering** option.</span></span> <span data-ttu-id="874c4-140">Если диаграмма содержит несколько рядов линейчатой диаграммы или гистограммы, этот параметр отобразит кластеризованные ряды.</span><span class="sxs-lookup"><span data-stu-id="874c4-140">If your chart contains multiple bar or column chart series, this option will display the series as clustered.</span></span> <span data-ttu-id="874c4-141">По умолчанию несколько рядов линейчатой диаграммы или гистограммы отображаются параллельно друг другу.</span><span class="sxs-lookup"><span data-stu-id="874c4-141">By default, multiple bar or column series are shown side-by-side.</span></span>  
  
4.  <span data-ttu-id="874c4-142">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="874c4-142">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="874c4-143">(Необязательно.) Чтобы добавить в линейчатую диаграмму или гистограмму эффект отображения в виде цилиндров, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="874c4-143">(Optional) To add cylinder effects to a bar or column chart, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="874c4-144">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="874c4-144">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="874c4-145">В области конструктора щелкните любой столбец в ряде.</span><span class="sxs-lookup"><span data-stu-id="874c4-145">On the design surface, click any of the bars in the series.</span></span> <span data-ttu-id="874c4-146">На панели «Свойства» отображаются свойства ряда.</span><span class="sxs-lookup"><span data-stu-id="874c4-146">The properties for the series are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="874c4-147">В разделе **Общие** разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="874c4-147">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
    4.  <span data-ttu-id="874c4-148">Для свойства **DrawingStyle** укажите значение **Cylinder** .</span><span class="sxs-lookup"><span data-stu-id="874c4-148">For the **DrawingStyle** property, specify the **Cylinder** value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874c4-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="874c4-149">See Also</span></span>  
 <span data-ttu-id="874c4-150">[Эффекты рельефа, объемные и другие эффекты в диаграмме (построитель отчетов и службы SSRS)](chart-effects-3d-bevel-and-other-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="874c4-150">[3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span></span>  
 <span data-ttu-id="874c4-151">[Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="874c4-151">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="874c4-152">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="874c4-152">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
