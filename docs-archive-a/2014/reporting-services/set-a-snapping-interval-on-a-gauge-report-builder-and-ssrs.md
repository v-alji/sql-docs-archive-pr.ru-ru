---
title: Установка интервала привязки на датчике (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0ece7297-6e2f-47fb-835d-b9e9cce53fe2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdc2a621c4406791838d97e93f47cd32fa9d5f94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734949"
---
# <a name="set-a-snapping-interval-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="92a33-102">Установка интервала привязки в датчике (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="92a33-102">Set a Snapping Interval on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="92a33-103">Интервал привязки определяет кратную величину, до которой округляются значения.</span><span class="sxs-lookup"><span data-stu-id="92a33-103">A snapping interval defines the multiple to which values are rounded.</span></span> <span data-ttu-id="92a33-104">По умолчанию датчик указывает на точное значение поля, заданное на панели данных.</span><span class="sxs-lookup"><span data-stu-id="92a33-104">By default, the gauge will point to the exact value of the field you have specified in the data pane.</span></span> <span data-ttu-id="92a33-105">Однако может потребоваться округлить точное значение в ту или иную сторону, чтобы указатель был привязан к заранее заданному интервалу.</span><span class="sxs-lookup"><span data-stu-id="92a33-105">However, you may want to round the exact value up or down so that the pointer will snap to a preset interval.</span></span> <span data-ttu-id="92a33-106">Например, если значение на датчике равно 34,2 и указан интервал привязки 5, указатель датчика будет указывать значение 35.</span><span class="sxs-lookup"><span data-stu-id="92a33-106">For example, if the value on your gauge is 34.2 and you specify a snapping interval of 5, the gauge pointer will point to 35.</span></span> <span data-ttu-id="92a33-107">Если значение на датчике равно 31,2 и указан интервал привязки 5, указатель датчика будет указывать значение 30.</span><span class="sxs-lookup"><span data-stu-id="92a33-107">If the value on your gauge is 31.2 and you specify a snapping interval of 5, the gauge pointer will point to 30.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-snapping-interval-on-a-gauge"></a><span data-ttu-id="92a33-108">Установка интервала привязки в датчике</span><span class="sxs-lookup"><span data-stu-id="92a33-108">To set a snapping interval on a gauge</span></span>  
  
1.  <span data-ttu-id="92a33-109">Щелкните любое число датчика, чтобы выделить шкалу.</span><span class="sxs-lookup"><span data-stu-id="92a33-109">Click anywhere on the numbers of the gauge to highlight the scale.</span></span>  
  
2.  <span data-ttu-id="92a33-110">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="92a33-110">Open the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92a33-111">Если панель свойств не отображается, перейдите на вкладку **вид** и установите флажок **свойства** .</span><span class="sxs-lookup"><span data-stu-id="92a33-111">If you do not see the Properties pane, click the **View** tab and then select the **Properties** checkbox.</span></span>  
  
3.  <span data-ttu-id="92a33-112">В свойстве **указатели** нажмите кнопку (...).</span><span class="sxs-lookup"><span data-stu-id="92a33-112">In the **Pointers** property, click the (...) button.</span></span> <span data-ttu-id="92a33-113">Откроется окно редактора коллекции указателей.</span><span class="sxs-lookup"><span data-stu-id="92a33-113">The Pointer Collection Editor opens.</span></span>  
  
4.  <span data-ttu-id="92a33-114">Задайте для свойства **снаппинженаблед** значение `True` .</span><span class="sxs-lookup"><span data-stu-id="92a33-114">Set the **SnappingEnabled** property to `True`.</span></span>  
  
5.  <span data-ttu-id="92a33-115">Задайте для **снаппингинтервал** значение, представляющее интервал привязки.</span><span class="sxs-lookup"><span data-stu-id="92a33-115">Set the **SnappingInterval** to a value that represents the snapping interval.</span></span> <span data-ttu-id="92a33-116">Указатель будет привязан к ближайшей кратной величине указанного значения.</span><span class="sxs-lookup"><span data-stu-id="92a33-116">The pointer will be snapped to the nearest round multiple of the value that you have specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a33-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="92a33-117">See Also</span></span>  
 <span data-ttu-id="92a33-118">[Форматирование шкалы на &#40;датчика построитель отчетов и SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92a33-118">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="92a33-119">[Форматирование указателей в построитель отчетов &#40;датчика и SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92a33-119">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="92a33-120">Датчики (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="92a33-120">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
