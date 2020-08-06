---
title: Скрытие элементов условных обозначений на диаграмме (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92256240-0cd5-4be4-8904-d1e3b93cb6b3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 20444432f580ffaf1c5f4de1320b06319f973a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667577"
---
# <a name="hide-legend-items-on-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="30d6f-102">Скрытие элементов условных обозначений на диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="30d6f-102">Hide Legend Items on the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="30d6f-103">По умолчанию все ряды, добавленные к диаграмме, отличной от фигурной, будут добавлены как элементы в условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="30d6f-103">By default, any series added to a non-Shape chart will be added as an item in the legend.</span></span> <span data-ttu-id="30d6f-104">Для круговых, воронкообразных и пирамидальных диаграмм добавление любого ряда к диаграмме вызовет добавление индивидуальных точек данных к условным обозначениям.</span><span class="sxs-lookup"><span data-stu-id="30d6f-104">For pie, doughnut, funnel, and pyramid charts, any series added to the chart will add individual data points in the legend.</span></span>  
  
 <span data-ttu-id="30d6f-105">Любой элемент условных обозначений можно спрятать.</span><span class="sxs-lookup"><span data-stu-id="30d6f-105">You can hide any item on the legend.</span></span> <span data-ttu-id="30d6f-106">Спрятанный в условных обозначениях элемент по-прежнему будет виден на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="30d6f-106">When you hide a legend item, it will still appear in the chart.</span></span> <span data-ttu-id="30d6f-107">Это полезно в ситуациях, когда для добавленного к диаграмме ряда не нужно выводить дополнительную информацию.</span><span class="sxs-lookup"><span data-stu-id="30d6f-107">This is useful in situations where you do not want to show more information for a series that is added to the chart.</span></span> <span data-ttu-id="30d6f-108">Например, если к диаграмме добавлен вычисляемый ряд (допустим, скользящее среднее), можно спрятать его запись в условных обозначениях, чтобы дополнительная информация выводилась только для первоначальных рядов.</span><span class="sxs-lookup"><span data-stu-id="30d6f-108">For example, if you have added a calculated series like a moving average to the chart, you may want to hide this entry in the legend so that more information is only shown for the original series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-an-item-from-display-in-the-legend"></a><span data-ttu-id="30d6f-109">Переключение видимости элемента условных обозначений</span><span class="sxs-lookup"><span data-stu-id="30d6f-109">To hide an item from display in the legend</span></span>  
  
1.  <span data-ttu-id="30d6f-110">Щелкните правой кнопкой мыши ряд, который нужно скрыть, и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="30d6f-110">Right-click on the series you want to hide and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="30d6f-111">Выберите **Условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="30d6f-111">Click **Legend**.</span></span> <span data-ttu-id="30d6f-112">Выберите **Не показывать этот ряд в условных обозначениях** .</span><span class="sxs-lookup"><span data-stu-id="30d6f-112">Select the **Do not show this series in a legend** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30d6f-113">Нельзя спрятать ряд только для одной группы.</span><span class="sxs-lookup"><span data-stu-id="30d6f-113">You cannot hide a series for one group and not for the others.</span></span> <span data-ttu-id="30d6f-114">Если поле добавлено в область **Группа рядов** , будут скрыты все ряды, принадлежащие этой группе.</span><span class="sxs-lookup"><span data-stu-id="30d6f-114">If you have added a field to the **Series Groups** area, all series belonging to this group will be hidden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d6f-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="30d6f-115">See Also</span></span>  
 <span data-ttu-id="30d6f-116">[Форматирование условных обозначений на диаграмме (построитель отчетов и службы SSRS)](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="30d6f-116">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="30d6f-117">[Форматирование точек данных на диаграмме (построитель отчетов и службы SSRS)](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="30d6f-117">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="30d6f-118">[Изменение текста элемента условных обозначений (построитель отчетов и службы SSRS)](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="30d6f-118">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="30d6f-119">[Добавление скользящего среднего в диаграмму (построитель отчетов и службы SSRS)](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="30d6f-119">[Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="30d6f-120">Диалоговое окно "Свойства условных обозначений" — "Общие" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="30d6f-120">Legend Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../legend-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
