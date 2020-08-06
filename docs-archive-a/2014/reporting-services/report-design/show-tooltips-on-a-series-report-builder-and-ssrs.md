---
title: Отображение всплывающих подсказок для ряда (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4c9606ff-e1c3-4cf7-a4e7-bb16f1a9e8ab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9113ec843b3b9255f380b17ee1ab6b360fa1f60d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667564"
---
# <a name="show-tooltips-on-a-series-report-builder-and-ssrs"></a><span data-ttu-id="92dcf-102">Отображение всплывающих подсказок для ряда (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="92dcf-102">Show ToolTips on a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="92dcf-103">К каждой точке данных ряда диаграммы можно добавить подсказку со сведениями, относящимися к точке данных, например имя группы, значение точки данных, значение точки данных в процентах от всего ряда; она отображается при удержании указателя над точкой данных отображаемого отчета.</span><span class="sxs-lookup"><span data-stu-id="92dcf-103">You can add a ToolTip to each data point on the series of a chart to display information related to the data point, such as the group name, the value of the data point, or the percentage of the data point relative to the series total when users hover over the data point in a rendered report.</span></span>  
  
 <span data-ttu-id="92dcf-104">Невозможно добавить подсказку к вычисляемому ряду.</span><span class="sxs-lookup"><span data-stu-id="92dcf-104">You cannot add a ToolTip to a calculated series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-tooltip-on-each-data-point"></a><span data-ttu-id="92dcf-105">Добавление подсказки к каждой точке данных</span><span class="sxs-lookup"><span data-stu-id="92dcf-105">To specify a ToolTip on each data point</span></span>  
  
1.  <span data-ttu-id="92dcf-106">Щелкните правой кнопкой мыши ряд или поле в области **Значения** и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="92dcf-106">Right-click on the series or right-click on the field in the **Values** area, and click **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="92dcf-107">Щелкните **Ряд данных** и введите строку или выражение для свойства **Подсказка** .</span><span class="sxs-lookup"><span data-stu-id="92dcf-107">Click **Series Data** and, for the **ToolTip** property, type in a string or expression.</span></span> <span data-ttu-id="92dcf-108">Можно использовать любое ключевое слово, относящееся к конкретной диаграмме, чтобы представить на диаграмме другое ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="92dcf-108">You can use any chart-specific keyword to represent another element on the chart.</span></span> <span data-ttu-id="92dcf-109">Дополнительные сведения см. в разделе [Форматирование точек данных на диаграмме (построитель отчетов и службы SSRS)](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92dcf-109">For more information, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92dcf-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="92dcf-110">See Also</span></span>  
 <span data-ttu-id="92dcf-111">[Форматирование точек данных на диаграмме &#40;построитель отчетов и SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92dcf-111">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="92dcf-112">[Изменение текста элемента условных обозначений &#40;построитель отчетов и SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="92dcf-112">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="92dcf-113">[Форматирование цветов рядов на диаграмме &#40;построитель отчетов и SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92dcf-113">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="92dcf-114">Добавление действия детализации в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="92dcf-114">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
