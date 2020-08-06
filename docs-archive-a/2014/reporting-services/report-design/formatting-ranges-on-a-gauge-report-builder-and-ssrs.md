---
title: Форматирование диапазонов на датчике (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ffdec8ca-3e95-41cd-850b-9e8c83be4b49
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29574c58eef6f18d685b48dd8d695a5fc42c3e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728006"
---
# <a name="formatting-ranges-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="3f754-102">Форматирование диапазонов на датчике (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3f754-102">Formatting Ranges on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3f754-103">Диапазон датчика — это зона или область на шкале датчика, которая указывает важный подраздел значений в датчике.</span><span class="sxs-lookup"><span data-stu-id="3f754-103">A gauge range is a zone or area on the gauge scale that indicates an important subsection of values on the gauge.</span></span> <span data-ttu-id="3f754-104">Используя диапазон датчика, можно визуально отобразить момент, когда значение указателя датчика перемещается в определенную область значений.</span><span class="sxs-lookup"><span data-stu-id="3f754-104">Using a gauge range, you can visually indicate when the pointer value has gone into a certain span of values.</span></span> <span data-ttu-id="3f754-105">Диапазоны определяются начальным значением и конечным значением.</span><span class="sxs-lookup"><span data-stu-id="3f754-105">Ranges are defined by a start value and an end value.</span></span>  
  
 <span data-ttu-id="3f754-106">Диапазоны также используются для определения различных разделов датчика.</span><span class="sxs-lookup"><span data-stu-id="3f754-106">You can also use ranges to define different sections of a gauge.</span></span> <span data-ttu-id="3f754-107">Например, в датчике со значениями от 0 до 10 можно определить красный диапазон со значениями от 0 до 3, желтый диапазон со значениями от 4 до 7 и зеленый диапазон со значениями от 8 до 10.</span><span class="sxs-lookup"><span data-stu-id="3f754-107">For example, on a gauge with values from 0 to 10, you can define a red range that has a value from 0 to 3, a yellow range that has a value from 4 to 7 and a green range that has a value from 8 to 10.</span></span> <span data-ttu-id="3f754-108">Если заданное начальное значение больше конечного, эти значения меняются местами, и начальное значение становится конечным, а конечное — начальным.</span><span class="sxs-lookup"><span data-stu-id="3f754-108">If the start value that you specified is greater than the end value that you specified, the values are swapped so that the start value is the end value and the end value is the start value.</span></span>  
  
 <span data-ttu-id="3f754-109">Диапазон можно размещать точно так же, как размещается указатель на шкале.</span><span class="sxs-lookup"><span data-stu-id="3f754-109">You can position the range in the same way that you position pointers on a scale.</span></span> <span data-ttu-id="3f754-110">Свойства **Положение** и **Расстояние от шкалы** определяют положение диапазона.</span><span class="sxs-lookup"><span data-stu-id="3f754-110">The **Position** and **Distance from scale** properties determine the position of the range.</span></span> <span data-ttu-id="3f754-111">Дополнительные сведения см. в разделе [Датчики (построитель отчетов и службы SSRS)](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3f754-111">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f754-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f754-112">See Also</span></span>  
 <span data-ttu-id="3f754-113">[Форматирование шкал на датчике (построитель отчетов и службы SSRS)](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3f754-113">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3f754-114">[Форматирование указателей на датчике &#40;построитель отчетов и службы SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3f754-114">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3f754-115">[Установка минимума и максимума на датчике (построитель отчетов и службы SSRS)](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3f754-115">[Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3f754-116">[Учебник. Добавление в отчет ключевого показателя эффективности (построитель отчетов)](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3f754-116">[Tutorial: Adding a KPI to Your Report &#40;Report Builder&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span></span>  
 [<span data-ttu-id="3f754-117">Датчики (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3f754-117">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
