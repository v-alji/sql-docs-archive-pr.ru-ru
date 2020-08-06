---
title: Отображение меток точек данных за пределами круговой диаграммы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 959b7574-cf43-470b-b592-4944d8a9948f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dd4f38f24d2729acacfa3520635b93d8af2e9433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736097"
---
# <a name="display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="fdb88-102">Отображение меток точек данных за пределами круговой диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="fdb88-102">Display Data Point Labels Outside a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fdb88-103">В службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]присваивание меток круговой диаграммы оптимизируется для отображения меток только для некоторых срезов данных.</span><span class="sxs-lookup"><span data-stu-id="fdb88-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], pie chart labeling is optimized to display labels on only several slices of data.</span></span> <span data-ttu-id="fdb88-104">Метки могут перекрываться, если круговая диаграмма содержит слишком много срезов.</span><span class="sxs-lookup"><span data-stu-id="fdb88-104">Labels may overlap if the pie chart contains too many slices.</span></span> <span data-ttu-id="fdb88-105">Решением проблемы является отображение меток за пределами круговой диаграммы, что создает больше пространства для нанесения дальнейших меток данных.</span><span class="sxs-lookup"><span data-stu-id="fdb88-105">One solution is to display the labels outside the pie chart, which may create more room for longer data labels.</span></span> <span data-ttu-id="fdb88-106">Если метки все еще перекрывают друг друга, можно создать для них больше места путем включения объемных эффектов.</span><span class="sxs-lookup"><span data-stu-id="fdb88-106">If you find that your labels still overlap, you can create more space for them by enabling 3D.</span></span> <span data-ttu-id="fdb88-107">Это снижает диаметр круговой диаграммы, создавая больше пространства вокруг диаграммы.</span><span class="sxs-lookup"><span data-stu-id="fdb88-107">This reduces the diameter of the pie chart, creating more space around the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-data-point-labels-inside-a-pie-chart"></a><span data-ttu-id="fdb88-108">Отображение меток точек данных внутри круговой диаграммы</span><span class="sxs-lookup"><span data-stu-id="fdb88-108">To display data point labels inside a pie chart</span></span>  
  
1.  <span data-ttu-id="fdb88-109">Добавьте в отчет круговую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="fdb88-109">Add a pie chart to your report.</span></span> <span data-ttu-id="fdb88-110">Дополнительные сведения см. в разделе [Добавление диаграммы в отчет (построитель отчетов и службы SSRS)](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fdb88-110">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="fdb88-111">Щелкните правой кнопкой мыши на диаграмме в области конструктора и выберите пункт **Отобразить метки данных**.</span><span class="sxs-lookup"><span data-stu-id="fdb88-111">On the design surface, right-click on the chart and select **Show Data Labels**.</span></span>  
  
### <a name="to-display-data-point-labels-outside-a-pie-chart"></a><span data-ttu-id="fdb88-112">Отображение меток точек данных за пределами круговой диаграммы</span><span class="sxs-lookup"><span data-stu-id="fdb88-112">To display data point labels outside a pie chart</span></span>  
  
1.  <span data-ttu-id="fdb88-113">Создайте круговую диаграмму и отобразите метки данных.</span><span class="sxs-lookup"><span data-stu-id="fdb88-113">Create a pie chart and display the data labels.</span></span>  
  
2.  <span data-ttu-id="fdb88-114">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="fdb88-114">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="fdb88-115">В области конструктора щелкните круговую диаграмму, чтобы отобразить свойства **Категория** на панели свойств.</span><span class="sxs-lookup"><span data-stu-id="fdb88-115">On the design surface, click on the pie itself to display the **Category** properties in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="fdb88-116">Разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="fdb88-116">Expand the **CustomAttributes** node.</span></span> <span data-ttu-id="fdb88-117">Отобразится список атрибутов круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="fdb88-117">A list of attributes for the pie chart is displayed.</span></span>  
  
5.  <span data-ttu-id="fdb88-118">Установите свойство **PieLabelStyle** в значение **За пределами**.</span><span class="sxs-lookup"><span data-stu-id="fdb88-118">Set the **PieLabelStyle** property to **Outside**.</span></span>  
  
6.  <span data-ttu-id="fdb88-119">Присвойте `PieLineColor` свойству значение **Black**.</span><span class="sxs-lookup"><span data-stu-id="fdb88-119">Set the `PieLineColor` property to **Black**.</span></span> <span data-ttu-id="fdb88-120">Свойство PieLineColor определяет линии выноски для каждой метки точки данных.</span><span class="sxs-lookup"><span data-stu-id="fdb88-120">The PieLineColor property defines callout lines for each data point label.</span></span>  
  
### <a name="to-prevent-overlapping-labels-displayed-outside-a-pie-chart"></a><span data-ttu-id="fdb88-121">Предотвращение перекрывания меток, отображаемых за пределами круговой диаграммы</span><span class="sxs-lookup"><span data-stu-id="fdb88-121">To prevent overlapping labels displayed outside a pie chart</span></span>  
  
1.  <span data-ttu-id="fdb88-122">Создайте круговую диаграмму с внешними метками.</span><span class="sxs-lookup"><span data-stu-id="fdb88-122">Create a pie chart with external labels.</span></span>  
  
2.  <span data-ttu-id="fdb88-123">Щелкните правой кнопкой мыши за пределами круговой диаграммы, но внутри ее границ в рабочей области конструирования и выберите **Свойства области диаграммы**. Откроется диалоговое окно **Свойства области диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="fdb88-123">On the design surface, right-click outside the pie chart but inside the chart borders and select **Chart Area Properties**.The **Chart AreaProperties** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="fdb88-124">На вкладке **Параметры объемного отображения** выберите параметр **Разрешить объемные эффекты**.</span><span class="sxs-lookup"><span data-stu-id="fdb88-124">On the **3D Options** tab, select **Enable 3D**.</span></span>  
  
4.  <span data-ttu-id="fdb88-125">Если необходимо предоставить большее пространство для меток в диаграмме, при этом оставив ее двухмерной, то в поле **Вращение** и **Наклон** установите свойства на значение **0**.</span><span class="sxs-lookup"><span data-stu-id="fdb88-125">If you want the chart to have more room for labels but still appear two-dimensional, set the **Rotation** and **Inclination** properties to **0**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb88-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="fdb88-126">See Also</span></span>  
 <span data-ttu-id="fdb88-127">[Круговые диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fdb88-127">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fdb88-128">[Сбор мелких срезов на круговой диаграмме (построитель отчетов и службы SSRS)](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fdb88-128">[Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fdb88-129">Отображение процентных значений на круговой диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="fdb88-129">Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
