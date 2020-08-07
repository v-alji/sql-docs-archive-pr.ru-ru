---
title: Построение данных на вспомогательной оси (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 094f39bf-3634-4852-9fc3-3adec4b266e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cec58820e0373bb1e9ef2d50d022e5b4ef7e962b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727933"
---
# <a name="plot-data-on-a-secondary-axis-report-builder-and-ssrs"></a><span data-ttu-id="6163b-102">Построение данных на вспомогательной оси (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6163b-102">Plot Data on a Secondary Axis (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6163b-103">Диаграмма имеет оси двух типов: основную и вспомогательную.</span><span class="sxs-lookup"><span data-stu-id="6163b-103">The chart has two axis types: primary and secondary.</span></span> <span data-ttu-id="6163b-104">Вспомогательная ось полезна при сравнении двух наборов значений с двумя различающимися диапазонами данных с общей категорией.</span><span class="sxs-lookup"><span data-stu-id="6163b-104">The secondary axis is useful when comparing two value sets with two distinct data ranges that share a common category.</span></span>  
  
 <span data-ttu-id="6163b-105">Например, предположим, что имеется диаграмма, вычисляющая доходы за 2008 год в зависимости от налогов.</span><span class="sxs-lookup"><span data-stu-id="6163b-105">For example, suppose you have a chart that calculates Revenue vs. Tax for the year 2008.</span></span> <span data-ttu-id="6163b-106">В этом случае период времени в течение 2008 года является общим для обоих наборов данных.</span><span class="sxs-lookup"><span data-stu-id="6163b-106">In this case, the 2008 time period is common to both value sets.</span></span> <span data-ttu-id="6163b-107">Однако, если оба ряда построить на одной оси Y, нельзя сделать полезное сравнение, т. к. шкала оси Y оптимизирована для самых больших значений в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="6163b-107">However, when both series are plotted on the same y-axis, we cannot make a useful comparison because the scale of the y-axis is optimized for the largest values in the dataset.</span></span> <span data-ttu-id="6163b-108">Если показать доход на первичной оси, а налог на вторичной, можно отобразить каждый ряд на своей собственной оси Y со своей собственной шкалой значений.</span><span class="sxs-lookup"><span data-stu-id="6163b-108">If we show Revenue on the primary axis, and Tax on the secondary axis, we can display each series on its own y-axis with its own scale of values.</span></span> <span data-ttu-id="6163b-109">Ряды продолжают использовать общую ось X.</span><span class="sxs-lookup"><span data-stu-id="6163b-109">The series still share a common x-axis.</span></span>  
  
 <span data-ttu-id="6163b-110">Если сравнивается более двух рядов, необходимо использовать другой подход для сравнения и отображения на диаграмме нескольких рядов.</span><span class="sxs-lookup"><span data-stu-id="6163b-110">In situations where there are more than two series to be compared, consider a different approach for comparing and displaying multiple series in a chart.</span></span> <span data-ttu-id="6163b-111">Дополнительные сведения см. в разделе [несколько рядов на диаграмме &#40;построитель отчетов и службы SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6163b-111">For more information, see [Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="6163b-112">Пример этой диаграммы доступен в виде образца отчета.</span><span class="sxs-lookup"><span data-stu-id="6163b-112">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="6163b-113">Дополнительные сведения о скачивании этого и других примеров отчетов см. в статье [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="6163b-113">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-plot-a-series-on-the-secondary-axis"></a><span data-ttu-id="6163b-114">Построение ряда на вторичной оси</span><span class="sxs-lookup"><span data-stu-id="6163b-114">To plot a series on the secondary axis</span></span>  
  
1.  <span data-ttu-id="6163b-115">Щелкните правой кнопкой мыши ряды в диаграмме или поле в области **Значения** , которую нужно отобразить на вспомогательной оси, и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="6163b-115">Right-click the series in the chart or right-click on a field in the **Values** area that you want to display on the secondary axis and click **Series Properties**.</span></span> <span data-ttu-id="6163b-116">Откроется диалоговое окно **Свойства ряда** .</span><span class="sxs-lookup"><span data-stu-id="6163b-116">The **Series Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="6163b-117">Перейдите на вкладку **Оси и область диаграммы**и выберите, какую из вторичных осей необходимо включить: ось значений или ось категорий.</span><span class="sxs-lookup"><span data-stu-id="6163b-117">Click **Axes and Chart Area**, and select which of the secondary axes you want to enable, the value axis or the category axis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6163b-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="6163b-118">See Also</span></span>  
 <span data-ttu-id="6163b-119">[Форматирование меток оси на построитель отчетов &#40;диаграммы и SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6163b-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6163b-120">Задание интервала оси (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6163b-120">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
