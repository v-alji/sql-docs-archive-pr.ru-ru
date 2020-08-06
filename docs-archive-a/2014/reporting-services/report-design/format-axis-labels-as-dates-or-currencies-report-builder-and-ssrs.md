---
title: Форматирование меток оси в виде значений даты или валюты (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9a01a74-2f51-4b35-be3a-a6138568f6cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ffe9d903a2271db95d4b1c2ef6201d2b0f3edab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658100"
---
# <a name="format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs"></a><span data-ttu-id="f387a-102">Форматирование меток оси в виде значений даты или валюты (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f387a-102">Format Axis Labels as Dates or Currencies (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f387a-103">Если на оси отображаются правильно отформатированные значения типа DateTime, диаграмма автоматически отобразит эти значения как дни.</span><span class="sxs-lookup"><span data-stu-id="f387a-103">When you show properly formatted DateTime values on an axis, a chart will automatically display these values as days.</span></span> <span data-ttu-id="f387a-104">Чтобы указать интервал даты-времени для оси X, такой как интервал в месяцах или интервал в часах, необходимо отформатировать метки оси и задать в качестве типа интервала оси допустимый интервал значений даты или времени.</span><span class="sxs-lookup"><span data-stu-id="f387a-104">To specify a date/time interval for the x-axis, such as an interval of months or an interval of hours, you must format the axis labels and set the type of axis interval to a valid date or time interval.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f387a-105">В гистограммах и точечных диаграммах осью категорий является горизонтальная ось (или ось X).</span><span class="sxs-lookup"><span data-stu-id="f387a-105">In column and scatter charts, the horizontal, or x-axis, is the category axis.</span></span> <span data-ttu-id="f387a-106">Однако для линейчатых диаграмм осью категорий является вертикальная (ось Y).</span><span class="sxs-lookup"><span data-stu-id="f387a-106">In bar charts, the vertical, or y-axis, is the category axis.</span></span>  
  
 <span data-ttu-id="f387a-107">Чтобы правильно отформатировать интервалы времени, необходимо обеспечить приведение значений, отображаемых на оси X, к типу данных <xref:System.DateTime> .</span><span class="sxs-lookup"><span data-stu-id="f387a-107">In order to format time intervals correctly, the values displayed on the x-axis must evaluate to a <xref:System.DateTime> data type.</span></span> <span data-ttu-id="f387a-108">Если поле содержит данные типа <xref:System.String>, то на диаграмме не вычисляются интервалы как значения даты или времени.</span><span class="sxs-lookup"><span data-stu-id="f387a-108">If your field has a data type of <xref:System.String>, the chart will not calculate intervals as dates or times.</span></span> <span data-ttu-id="f387a-109">Дополнительные сведения см. в разделе [Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f387a-109">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f387a-110">Если к оси Y добавляется числовое значение, то, по умолчанию, на диаграмме это число не форматируется перед его отображением.</span><span class="sxs-lookup"><span data-stu-id="f387a-110">When a numeric value is added to the y-axis, by default, the chart does not format the number before displaying it.</span></span> <span data-ttu-id="f387a-111">Если числовое поле содержит данные о продаже, можно отформатировать эти числа как значения валюты, чтобы повысить удобство чтения диаграммы.</span><span class="sxs-lookup"><span data-stu-id="f387a-111">If your numeric field is a sales figure, consider formatting the numbers as currencies to increase the readability of the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-format-x-axis-labels-as-monthly-intervals"></a><span data-ttu-id="f387a-112">Форматирование меток оси X как месячных интервалов</span><span class="sxs-lookup"><span data-stu-id="f387a-112">To format x-axis labels as monthly intervals</span></span>  
  
1.  <span data-ttu-id="f387a-113">Щелкните правой кнопкой мыши горизонтальную ось (ось X) диаграммы и выберите **Свойства горизонтальной оси**.</span><span class="sxs-lookup"><span data-stu-id="f387a-113">Right-click the horizontal, or x-axis, of the chart, and select **HorizontalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="f387a-114">В диалоговом окне **Свойства горизонтальной оси** выберите **Число**.</span><span class="sxs-lookup"><span data-stu-id="f387a-114">In the **HorizontalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="f387a-115">В списке **Категория** выберите **Дата**.</span><span class="sxs-lookup"><span data-stu-id="f387a-115">From the **Category** list, select **Date**.</span></span> <span data-ttu-id="f387a-116">В списке **Тип** выберите формат даты, применяемый к меткам оси X.</span><span class="sxs-lookup"><span data-stu-id="f387a-116">From the **Type** list, select a date format to apply to the x-axis labels.</span></span>  
  
4.  <span data-ttu-id="f387a-117">Выберите **Параметры оси**.</span><span class="sxs-lookup"><span data-stu-id="f387a-117">Select **Axis Options.**</span></span>  
  
5.  <span data-ttu-id="f387a-118">В поле **Интервал**введите **1**.</span><span class="sxs-lookup"><span data-stu-id="f387a-118">In **Interval**, type **1**.</span></span> <span data-ttu-id="f387a-119">Для свойства **Тип интервала** выберите значение **Месяцы**.</span><span class="sxs-lookup"><span data-stu-id="f387a-119">In **Interval type** property, select **Months**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f387a-120">Если тип интервала не указан, диаграмма вычисляет интервалы в днях.</span><span class="sxs-lookup"><span data-stu-id="f387a-120">If you do not specify an interval type, the chart will calculate intervals in terms of days.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-format-y-axis-labels-using-a-currency-format"></a><span data-ttu-id="f387a-121">Форматирование меток оси Y с помощью формата валюты</span><span class="sxs-lookup"><span data-stu-id="f387a-121">To format y-axis labels using a currency format</span></span>  
  
1.  <span data-ttu-id="f387a-122">Щелкните правой кнопкой мыши вертикальную ось (ось Y) диаграммы и выберите **Свойства вертикальной оси**.</span><span class="sxs-lookup"><span data-stu-id="f387a-122">Right-click the vertical, or y-axis, of the chart, and select **VerticalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="f387a-123">В диалоговом окне **Свойства вертикальной оси** выберите **Число**.</span><span class="sxs-lookup"><span data-stu-id="f387a-123">In the **VerticalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="f387a-124">В списке **Категория** выберите **Валюта**.</span><span class="sxs-lookup"><span data-stu-id="f387a-124">From the **Category** list, select **Currency**.</span></span> <span data-ttu-id="f387a-125">В списке **Символ** выберите формат валюты, применяемый к меткам оси Y.</span><span class="sxs-lookup"><span data-stu-id="f387a-125">From the **Symbol** list, select a currency format to apply to the y-axis labels.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f387a-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="f387a-126">See Also</span></span>  
 <span data-ttu-id="f387a-127">[Форматирование меток оси на диаграмме (построитель отчетов и службы SSRS)](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f387a-127">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f387a-128">[Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f387a-128">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f387a-129">[Задание логарифмической шкалы (построитель отчетов и службы SSRS)](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f387a-129">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f387a-130">Задание интервала оси (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f387a-130">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
