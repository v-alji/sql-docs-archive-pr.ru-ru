---
title: Отображение процентных значений на круговой диаграмме (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb905fc1-5235-4773-a27e-b07be9318be5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2dee9017d34f2751b790b2e4928571160b597f1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663953"
---
# <a name="display-percentage-values-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="233c5-102">Отображение процентных значений на круговой диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="233c5-102">Display Percentage Values on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="233c5-103">По умолчанию категории отображаются в условных обозначениях для идентификации каждого значения.</span><span class="sxs-lookup"><span data-stu-id="233c5-103">By default, categories are shown in the legend to identify each value.</span></span> <span data-ttu-id="233c5-104">Если круговая диаграмма отмечена метками категорий, в условных обозначениях можно показать проценты.</span><span class="sxs-lookup"><span data-stu-id="233c5-104">If you have labeled the pie chart using category labels, you may want show percentages in the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="233c5-105">Отображение на круговой диаграмме значений в процентах в качестве меток</span><span class="sxs-lookup"><span data-stu-id="233c5-105">To display percentage values as labels on a pie chart</span></span>  
  
1.  <span data-ttu-id="233c5-106">Добавьте в отчет круговую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="233c5-106">Add a pie chart to your report.</span></span> <span data-ttu-id="233c5-107">Дополнительные сведения см. в разделе [Добавление диаграммы в отчет (построитель отчетов и службы SSRS)](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="233c5-107">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="233c5-108">В области конструктора щелкните правой кнопкой мыши круговую диаграмму и выберите пункт **Отобразить метки данных**.</span><span class="sxs-lookup"><span data-stu-id="233c5-108">On the design surface, right-click on the pie and select **Show Data Labels**.</span></span> <span data-ttu-id="233c5-109">Метки данных должны появиться в каждом срезе круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="233c5-109">The data labels should appear within each slice on the pie chart.</span></span>  
  
3.  <span data-ttu-id="233c5-110">В области конструктора щелкните правой кнопкой мыши метки и выберите пункт **Свойства метки ряда**.</span><span class="sxs-lookup"><span data-stu-id="233c5-110">On the design surface, right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="233c5-111">Появится диалоговое окно **Свойства метки ряда** .</span><span class="sxs-lookup"><span data-stu-id="233c5-111">The **Series Label Properties** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="233c5-112">Введите `#PERCENT` для параметра **данных метки** .</span><span class="sxs-lookup"><span data-stu-id="233c5-112">Type `#PERCENT` for the **Label data** option.</span></span>  
  
5.  <span data-ttu-id="233c5-113">(Необязательно) Чтобы указать для метки количество десятичных разрядов, введите значение #PERCENT{P*n*}, где *n* — число десятичных разрядов.</span><span class="sxs-lookup"><span data-stu-id="233c5-113">(Optional) To specify how many decimal places the label shows, type "#PERCENT{P*n*}" where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="233c5-114">Например, чтобы не отображать десятичные разряды, введите «#PERCENT{P0}».</span><span class="sxs-lookup"><span data-stu-id="233c5-114">For example, to display no decimal places, type "#PERCENT{P0}".</span></span>  
  
### <a name="to-display-percentage-values-in-the-legend-of-a-pie-chart"></a><span data-ttu-id="233c5-115">Отображение в условных обозначениях круговой диаграммы значений в процентах</span><span class="sxs-lookup"><span data-stu-id="233c5-115">To display percentage values in the legend of a pie chart</span></span>  
  
1.  <span data-ttu-id="233c5-116">В области конструктора щелкните правой кнопкой мыши круговую диаграмму и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="233c5-116">On the design surface, right-click on the pie chart and select **Series Properties**.</span></span> <span data-ttu-id="233c5-117">Откроется диалоговое окно **Свойства ряда** .</span><span class="sxs-lookup"><span data-stu-id="233c5-117">The **Series Properties** dialog box displays.</span></span>  
  
2.  <span data-ttu-id="233c5-118">В поле **Условные обозначения**введите `#PERCENT` для свойства **Пользовательский текст условных обозначений** .</span><span class="sxs-lookup"><span data-stu-id="233c5-118">In **Legend**, type `#PERCENT` for the **Custom legend text** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="233c5-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="233c5-119">See Also</span></span>  
 <span data-ttu-id="233c5-120">[Круговые диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="233c5-120">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="233c5-121">[Форматирование условных обозначений на диаграмме &#40;построитель отчетов и SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="233c5-121">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="233c5-122">[Отображение меток точек данных за пределами круговой диаграммы &#40;построитель отчетов и SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="233c5-122">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="233c5-123">Сбор мелких срезов на круговой диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="233c5-123">Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
