---
title: Добавление пустых точек к диаграмме (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2b056119-439f-494f-83cf-ee0c05dc6487
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53d891c58210bcd51cd4e49f2f9a691a7729c884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737961"
---
# <a name="add-empty-points-to-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="3faf4-102">Добавление пустых точек на диаграмму (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3faf4-102">Add Empty Points to the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3faf4-103">Значения NULL отображаются на диаграмме в виде пустых мест или промежутков между точками данных в ряде.</span><span class="sxs-lookup"><span data-stu-id="3faf4-103">Null values are shown on the chart as empty spaces or gaps between data points in a series.</span></span> <span data-ttu-id="3faf4-104">Пустые точки представляют собой точки данных, которые можно вставить в пустые места, созданные значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="3faf4-104">Empty points are data points that can be inserted in the empty space created by null values.</span></span>  
  
 <span data-ttu-id="3faf4-105">По умолчанию пустые точки вычисляются как среднее значение предыдущей и последующей точек данных, содержащих значения.</span><span class="sxs-lookup"><span data-stu-id="3faf4-105">By default, empty points are calculated by taking the average of the previous and next data points that contain a value.</span></span> <span data-ttu-id="3faf4-106">Это поведение можно изменить, чтобы вместо пустых точек вставлялись значения нуля.</span><span class="sxs-lookup"><span data-stu-id="3faf4-106">You can change this so that all empty points are inserted at zero.</span></span>  
  
 <span data-ttu-id="3faf4-107">Дополнительные сведения см. в разделе [Точки данных со значением NULL и пустые точки в диаграммах (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3faf4-107">For more information, see [Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-empty-points-on-a-chart"></a><span data-ttu-id="3faf4-108">Указание пустых точек на диаграмме</span><span class="sxs-lookup"><span data-stu-id="3faf4-108">To specify empty points on a chart</span></span>  
  
1.  <span data-ttu-id="3faf4-109">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="3faf4-109">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="3faf4-110">В области конструктора щелкните правой кнопкой мыши ряд, содержащий значения NULL.</span><span class="sxs-lookup"><span data-stu-id="3faf4-110">On the design surface, right-click the series that contains null values.</span></span> <span data-ttu-id="3faf4-111">На панели «Свойства» отображаются свойства ряда.</span><span class="sxs-lookup"><span data-stu-id="3faf4-111">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="3faf4-112">Разверните узел **EmptyPoint** .</span><span class="sxs-lookup"><span data-stu-id="3faf4-112">Expand the **EmptyPoint** node.</span></span>  
  
4.  <span data-ttu-id="3faf4-113">Укажите значение цвета для свойства Color.</span><span class="sxs-lookup"><span data-stu-id="3faf4-113">Select a color value for the Color property.</span></span>  
  
5.  <span data-ttu-id="3faf4-114">В узле **EmptyPoint** разверните узел «Маркер».</span><span class="sxs-lookup"><span data-stu-id="3faf4-114">In the **EmptyPoint** node, expand the Marker node.</span></span>  
  
6.  <span data-ttu-id="3faf4-115">Выберите тип маркера для свойства MarkerType.</span><span class="sxs-lookup"><span data-stu-id="3faf4-115">Select a marker type for the MarkerType property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3faf4-116">Тип маркера необходимо выбрать, чтобы добавить пустые точки на гистограмму, столбчатую или точечную диаграмму.</span><span class="sxs-lookup"><span data-stu-id="3faf4-116">You must select a marker type to add empty points to a bar, column or scatter chart.</span></span> <span data-ttu-id="3faf4-117">Однако для диаграммы с областями, линейчатой и лепестковой диаграммы выбор типа маркера необязателен, поскольку для заполнения пустого пространства или промежутка на этих диаграммах маркер не нужен.</span><span class="sxs-lookup"><span data-stu-id="3faf4-117">However, for area, line and radar charts, selecting a marker type is optional because the chart fills in the empty space or gap without requiring a marker to be specified.</span></span>  
  
7.  <span data-ttu-id="3faf4-118">Задайте значение пустой точки.</span><span class="sxs-lookup"><span data-stu-id="3faf4-118">Set the value of the empty point.</span></span>  
  
    1.  <span data-ttu-id="3faf4-119">На панели «Свойства» разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="3faf4-119">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
    2.  <span data-ttu-id="3faf4-120">Задайте значение для свойства EmptyPointValue.</span><span class="sxs-lookup"><span data-stu-id="3faf4-120">Set the EmptyPointValue property.</span></span> <span data-ttu-id="3faf4-121">Чтобы вставить пустые точки со средним значением предыдущей и последующей точек данных, выберите **Среднее**.</span><span class="sxs-lookup"><span data-stu-id="3faf4-121">To insert empty points at an average of the previous and next data points, select **Average**.</span></span> <span data-ttu-id="3faf4-122">Чтобы вставить пустые точки с нулевым значением, выберите **Ноль**.</span><span class="sxs-lookup"><span data-stu-id="3faf4-122">To insert empty points at zero, select **Zero**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3faf4-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="3faf4-123">See Also</span></span>  
 <span data-ttu-id="3faf4-124">[Добавление фильтров набора данных, фильтров области данных и групповых фильтров (построитель отчетов и службы SSRS)](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="3faf4-124">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="3faf4-125">[Типы диаграмм (построитель отчетов и службы SSRS)](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3faf4-125">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3faf4-126">[Добавление в диаграмму разрывов шкалы (построитель отчетов и службы SSRS)](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3faf4-126">[Add Scale Breaks to a Chart &#40;Report Builder and SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3faf4-127">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3faf4-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
