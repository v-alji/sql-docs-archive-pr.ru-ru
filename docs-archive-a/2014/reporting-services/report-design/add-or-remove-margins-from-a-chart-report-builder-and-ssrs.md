---
title: Добавление или удаление полей из диаграммы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91c43f58-5771-4d33-a54d-0e802d2f5cba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d8bad99591964540bcd14fc5609560a3d324515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735038"
---
# <a name="add-or-remove-margins-from-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="d276f-102">Добавление или удаление полей из диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d276f-102">Add or Remove Margins from a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d276f-103">В гистограмме и точечной диаграмме боковые поля автоматически добавляются по краям оси X.</span><span class="sxs-lookup"><span data-stu-id="d276f-103">In Column and Scatter chart types, the chart automatically adds side margins on the ends of the x-axis.</span></span> <span data-ttu-id="d276f-104">В линейчатой диаграмме боковые поля автоматически добавляются по краям оси X.</span><span class="sxs-lookup"><span data-stu-id="d276f-104">In Bar chart types, the chart automatically adds side margins on the ends of the y-axis.</span></span> <span data-ttu-id="d276f-105">Для всех остальных диаграмм боковые поля не добавляются.</span><span class="sxs-lookup"><span data-stu-id="d276f-105">In all other chart types, the chart does not add side margins.</span></span> <span data-ttu-id="d276f-106">Размер поля изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="d276f-106">You cannot change the size of the margin.</span></span>  
  
 <span data-ttu-id="d276f-107">Этот раздел не относится к круговым, кольцевым, воронкообразным и пирамидальным диаграммам.</span><span class="sxs-lookup"><span data-stu-id="d276f-107">This topic does not apply to pie, doughnut, funnel, or pyramid chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-or-disable-side-margins"></a><span data-ttu-id="d276f-108">Включение или отключение боковых полей</span><span class="sxs-lookup"><span data-stu-id="d276f-108">To enable or disable side margins</span></span>  
  
1.  <span data-ttu-id="d276f-109">Щелкните правой кнопкой мыши ось и выберите пункт **Свойства оси**.</span><span class="sxs-lookup"><span data-stu-id="d276f-109">Right-click the axis and select **Axis Properties**.</span></span> <span data-ttu-id="d276f-110">Отображается диалоговое окно свойств **вертикальных** или **горизонтальных осей** .</span><span class="sxs-lookup"><span data-stu-id="d276f-110">The **Vertical** or **HorizontalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="d276f-111">На странице **Параметры оси** задайте свойство **Боковые поля** :</span><span class="sxs-lookup"><span data-stu-id="d276f-111">On the **Axis Options** page, set the **Side margins** property:</span></span>  
  
    -   <span data-ttu-id="d276f-112">**Автоматически** — боковое поле добавляется в зависимости от типа диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d276f-112">**Auto** The chart will determine whether to add a side margin based on the chart type.</span></span>  
  
    -   <span data-ttu-id="d276f-113">**Отключено** — в линейчатой диаграмме, гистограмме и точечной диаграмме не будет боковых полей.</span><span class="sxs-lookup"><span data-stu-id="d276f-113">**Disabled** Bar, column, and scatter charts will have no side margins.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d276f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="d276f-114">See Also</span></span>  
 <span data-ttu-id="d276f-115">[Форматирование меток оси на диаграмме (построитель отчетов и службы SSRS)](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d276f-115">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d276f-116">[Диалоговое окно "Свойства оси" — "Параметры оси" (построитель отчетов и службы SSRS)](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d276f-116">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d276f-117">[Задание интервала оси (построитель отчетов и службы SSRS)](specify-an-axis-interval-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d276f-117">[Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d276f-118">[Форматирование меток оси в виде значений даты или валюты &#40;построитель отчетов и службы SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d276f-118">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d276f-119">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d276f-119">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
