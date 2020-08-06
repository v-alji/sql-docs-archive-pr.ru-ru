---
title: Задание интервала оси (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46712d-a5bf-44c0-9929-e30ccc1e7e33
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b64b824933753a8482360f193ca4ccf71e8d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654782"
---
# <a name="specify-an-axis-interval-report-builder-and-ssrs"></a><span data-ttu-id="7d2fe-102">Задание интервала оси (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7d2fe-102">Specify an Axis Interval (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7d2fe-103">Интервал оси определяет количество меток и дополняет деления на оси.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-103">The axis interval defines the number of labels and accompanying tick marks on an axis.</span></span> <span data-ttu-id="7d2fe-104">Интервалы на оси значений обеспечивают согласованное измерение точек данных на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-104">On the value axis, axis intervals provide a consistent measure of the data points on the chart.</span></span> <span data-ttu-id="7d2fe-105">Однако на оси категорий эта функция возможность может вызвать отображение некоторых категорий без меток на оси.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-105">However, on the category axis, this functionality can cause categories to appear without axis labels.</span></span> <span data-ttu-id="7d2fe-106">Можно указать необходимое количество интервалов в свойстве оси Interval.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-106">You can specify the number of intervals you want in the axis Interval property.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="7d2fe-107">вычисляют количество интервалов во время выполнения в зависимости от данных результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-107">calculates the number of intervals at run time, based on the data in the result set.</span></span> <span data-ttu-id="7d2fe-108">Дополнительные сведения в вычислениях интервалов оси см. в разделе [Форматирование меток оси на диаграмме (построитель отчетов и службы SSRS)](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7d2fe-108">For more information about how axis intervals are calculated, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="7d2fe-109">Этот раздел неприменим для значений данных или времени на оси категорий.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-109">This topic is not applicable for date or time values on the category axis.</span></span> <span data-ttu-id="7d2fe-110">Значения `DateTime` по умолчанию отображаются как дни.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-110">Be default, `DateTime` values appear as days.</span></span> <span data-ttu-id="7d2fe-111">Для определения различных интервалов данных или времени, например интервал месяца или времени, необходимо отформатировать метки оси и установить отображение экземпляров типов `DateTime` вместо типов `String`.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-111">To specify a different date or time interval, such as a month or time interval, you must format the axis labels and set the axis to display instances of `DateTime` types instead of `String` types.</span></span> <span data-ttu-id="7d2fe-112">Кроме того, необходимо задать свойство Interval.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-112">In addition, you must set the Interval property.</span></span> <span data-ttu-id="7d2fe-113">Дополнительные сведения см. в разделе [Форматирование меток оси в виде значений даты или валюты (построитель отчетов и службы SSRS)](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7d2fe-113">For more information, see [Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="7d2fe-114">Это раздел неприменим к круговым, кольцевым, воронкообразным или пирамидальным диаграммам, которые не имеют осей.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-114">This topic does not apply to pie, doughnut, funnel or pyramid charts, which do not have axes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d2fe-115">Ось категорий обычно является горизонтальной осью (осью X).</span><span class="sxs-lookup"><span data-stu-id="7d2fe-115">The category axis is usually the horizontal or x-axis.</span></span> <span data-ttu-id="7d2fe-116">Однако для линейчатых диаграмм ось категорий является вертикальной (осью Y).</span><span class="sxs-lookup"><span data-stu-id="7d2fe-116">However, for bar charts, the category axis is the vertical or y-axis.</span></span>  
  
 <span data-ttu-id="7d2fe-117">Пример диаграммы с различными интервалами осей доступен в виде образца отчета.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-117">An example of a chart specifying different axis intervals is available as a sample report.</span></span> <span data-ttu-id="7d2fe-118">Дополнительные сведения о скачивании этого и других примеров отчетов см. в статье [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="7d2fe-118">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-show-all-category-labels-on-the-x-axis"></a><span data-ttu-id="7d2fe-119">Отображение всех меток категории на оси X</span><span class="sxs-lookup"><span data-stu-id="7d2fe-119">To show all category labels on the x-axis</span></span>  
  
1.  <span data-ttu-id="7d2fe-120">Щелкните правой кнопкой мыши ось категорий и выберите **Свойства оси**.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-120">Right-click the category axis and click **Axis Properties**.</span></span> <span data-ttu-id="7d2fe-121">Откроется диалоговое окно **Свойства оси** .</span><span class="sxs-lookup"><span data-stu-id="7d2fe-121">The **Axis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7d2fe-122">В окне **Параметры оси**задайте `Interval` значение **1**.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-122">In **Axis Options**, set `Interval` to **1**.</span></span> <span data-ttu-id="7d2fe-123">Отобразится каждая метка группы категории.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-123">Every category group label is displayed.</span></span> <span data-ttu-id="7d2fe-124">Если требуется отобразить каждую метку группы другой категории на оси X, введите значение **2**.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-124">If you want to show every other category group label on the x-axis, type **2**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d2fe-125">После установки интервала оси автоматическое присваивание меток отключается.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-125">When an axis interval is set, all automatic labeling is disabled.</span></span> <span data-ttu-id="7d2fe-126">При указании значения для интервала оси может возникнуть непредсказуемое поведение при присваивании меток в зависимости от количества категорий на оси категорий.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-126">If you specify a value for the axis interval, you may experience unpredictable labeling behavior depending on how many categories are on the category axis.</span></span>  
  
### <a name="to-enable-a-variable-interval-calculation-on-an-axis"></a><span data-ttu-id="7d2fe-127">Включение вычисления переменного интервала на оси</span><span class="sxs-lookup"><span data-stu-id="7d2fe-127">To enable a variable interval calculation on an axis</span></span>  
  
1.  <span data-ttu-id="7d2fe-128">Щелкните правой кнопкой мыши по оси диаграммы, которую необходимо изменить, и выберите пункт **Свойства оси**.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-128">Right-click the chart axis that you want to change, and then click **Axis Properties**.</span></span> <span data-ttu-id="7d2fe-129">Откроется диалоговое окно **Свойства оси** .</span><span class="sxs-lookup"><span data-stu-id="7d2fe-129">The **Axis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7d2fe-130">В окне **Параметры оси**задайте `Interval` значение **Авто**. На диаграмме будет отображено оптимальное число меток категорий, которые могут помещаться вдоль оси.</span><span class="sxs-lookup"><span data-stu-id="7d2fe-130">In **Axis Options**, set `Interval` to **Auto**. The chart will display the optimal number of category labels that can fit along the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7d2fe-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d2fe-131">See Also</span></span>  
 <span data-ttu-id="7d2fe-132">[Форматирование построитель отчетов &#40;диаграммы и SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7d2fe-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7d2fe-133">[Форматирование точек данных на диаграмме &#40;построитель отчетов и SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7d2fe-133">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7d2fe-134">[Сортировка данных в области данных &#40;построитель отчетов и SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7d2fe-134">[Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7d2fe-135">[Диалоговое окно "Свойства оси" Параметры оси &#40;построитель отчетов и службы SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7d2fe-135">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7d2fe-136">[Укажите построитель отчетов &#40;логарифмической шкалы и службы SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7d2fe-136">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7d2fe-137">Построение данных на вспомогательной оси (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7d2fe-137">Plot Data on a Secondary Axis &#40;Report Builder and SSRS&#41;</span></span>](plot-data-on-a-secondary-axis-report-builder-and-ssrs.md)  
  
  
