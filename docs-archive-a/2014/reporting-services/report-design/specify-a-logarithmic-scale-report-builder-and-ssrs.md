---
title: Задание логарифмической шкалы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f3092c1c-b128-433d-9a95-983508b2a8d4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cc422a6f95a420445dc604d08a23e8f8e65c95d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654783"
---
# <a name="specify-a-logarithmic-scale-report-builder-and-ssrs"></a><span data-ttu-id="5d7e9-102">Задание логарифмической шкалы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="5d7e9-102">Specify a Logarithmic Scale (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5d7e9-103">Если данные пропорциональны логарифму, в диаграмме можно использовать логарифмическую шкалу.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-103">If you have data that is logarithmically proportional, you may want to consider using a logarithmic scale on the chart.</span></span> <span data-ttu-id="5d7e9-104">Это может улучшить внешний вид диаграммы и повысить удобство работы с данными.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-104">This helps improve the appearance of the chart by making your data more manageable.</span></span> <span data-ttu-id="5d7e9-105">Большинство логарифмических шкал использует логарифм с основанием 10.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-105">Most logarithmic scales use a base of 10.</span></span>  
  
 <span data-ttu-id="5d7e9-106">Эта функция доступна только для оси значений.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-106">This feature is only available on the value axis.</span></span> <span data-ttu-id="5d7e9-107">Ось значений обычно является вертикальной осью (осью Y).</span><span class="sxs-lookup"><span data-stu-id="5d7e9-107">The value axis is usually the vertical, or y-axis.</span></span> <span data-ttu-id="5d7e9-108">Однако в линейчатых диаграммах это горизонтальная ось (ось X).</span><span class="sxs-lookup"><span data-stu-id="5d7e9-108">On bar charts, however, it is the horizontal, or x-axis.</span></span>  
  
 <span data-ttu-id="5d7e9-109">Если ось логарифмическая, все остальные ее свойства будут логарифмически масштабированы.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-109">If your axis is logarithmic, all other properties relating to the axis will be scaled logarithmically.</span></span> <span data-ttu-id="5d7e9-110">Например, если задать на оси логарифмическую шкалу с основанием 10, установка интервала шкалы, равного 2, на самом деле создаст интервалы, равные 10 в степени 2, то есть 100.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-110">For example, if you specify a base-10 logarithmic scale on your axis, setting an axis interval of 2 will generate intervals in magnitudes of 10 to the power of 2, or 100.</span></span> <span data-ttu-id="5d7e9-111">Это означает, что будут отображены значения осей 1, 100, 10000, а не значения по умолчанию 1, 10, 100, 1000, 10000.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-111">This means your axis values will read 1, 100, 10000, instead of the default result of 1, 10, 100, 1000, 10000.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-logarithmic-scale"></a><span data-ttu-id="5d7e9-112">Задание логарифмической шкалы</span><span class="sxs-lookup"><span data-stu-id="5d7e9-112">To specify a logarithmic scale</span></span>  
  
1.  <span data-ttu-id="5d7e9-113">Щелкните правой кнопкой мыши ось Y диаграммы и выберите пункт **Свойства вертикальной оси**.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-113">Right-click the y-axis of your chart, and click **VerticalAxis Properties**.</span></span> <span data-ttu-id="5d7e9-114">Откроется диалоговое окно **Свойства вертикальной оси** .</span><span class="sxs-lookup"><span data-stu-id="5d7e9-114">The **VerticalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="5d7e9-115">В поле **Свойства оси**выберите **Использовать логарифмическую шкалу**.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-115">In **Axis Options**, select **Uselogarithmic scale**.</span></span>  
  
3.  <span data-ttu-id="5d7e9-116">В текстовом поле **Основание логарифма** введите положительное значение для основания логарифма.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-116">In the **Logbase** text box, type a positive value for the logarithmic base.</span></span> <span data-ttu-id="5d7e9-117">Если значение не задано, по умолчанию берется логарифм с основанием 10.</span><span class="sxs-lookup"><span data-stu-id="5d7e9-117">If no value is specified, the logarithmic base defaults to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d7e9-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d7e9-118">See Also</span></span>  
 <span data-ttu-id="5d7e9-119">[Форматирование меток оси на диаграмме (построитель отчетов и службы SSRS)](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d7e9-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5d7e9-120">[Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d7e9-120">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5d7e9-121">[Форматирование меток оси в виде значений даты или валюты &#40;построитель отчетов и службы SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d7e9-121">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5d7e9-122">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="5d7e9-122">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
