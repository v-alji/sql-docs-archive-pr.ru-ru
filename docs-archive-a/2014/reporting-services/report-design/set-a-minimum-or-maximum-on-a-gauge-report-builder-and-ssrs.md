---
title: Установка минимума и максимума на датчике (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b4c260c0-5a88-4f30-8977-eb5cc78fc146
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 344122dbff647a8c35b838ecce637602f202864b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656152"
---
# <a name="set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="15acc-102">Установка минимума и максимума на датчике (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="15acc-102">Set a Minimum or Maximum on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="15acc-103">В отличие от диаграммы, где определяется несколько групп, датчик выводит только одно значение.</span><span class="sxs-lookup"><span data-stu-id="15acc-103">Unlike the chart, where multiple groups are defined, the gauge only shows one value.</span></span> <span data-ttu-id="15acc-104">Поскольку построитель отчетов и конструктор отчетов определяют контекст или относительную значимость значения, отображаемого на датчике, необходимо определить минимум и максимум шкалы.</span><span class="sxs-lookup"><span data-stu-id="15acc-104">Since Report Builder and Report Designer determine the context or relative significance of the one value that you are trying to show on the gauge, you must define the minimum and maximum of the scale.</span></span> <span data-ttu-id="15acc-105">Например, если значения данных располагаются в диапазоне от 0 до 10, в качестве минимума нужно установить 0, а в качестве максимума — 10.</span><span class="sxs-lookup"><span data-stu-id="15acc-105">For example, if your data values are rankings between 0 and 10, you will want to set the minimum to 0 and maximum to 10.</span></span> <span data-ttu-id="15acc-106">Значения интервала вычисляются автоматически на основе минимального и максимального значений.</span><span class="sxs-lookup"><span data-stu-id="15acc-106">The interval numbers are calculated automatically based on the values specified for the minimum and maximum.</span></span> <span data-ttu-id="15acc-107">По умолчанию значением минимума является 0, а значением максимума — 100, но это произвольное значение, которое нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="15acc-107">By default, the minimum and maximum are set to 0 and 100, but this is an arbitrary value that you should change.</span></span> <span data-ttu-id="15acc-108">Приложение не вычисляет значения в виде процентов.</span><span class="sxs-lookup"><span data-stu-id="15acc-108">The application does not calculate your value as a percentage.</span></span>  
  
 <span data-ttu-id="15acc-109">Если диапазон значений очень широкий, например от 0 до 10000, попробуйте с помощью множителя сократить число нулей в датчике.</span><span class="sxs-lookup"><span data-stu-id="15acc-109">If the range of your values is large, for example from 0 to 10000, consider using a multiplier to reduce the number of zeroes on the gauge.</span></span> <span data-ttu-id="15acc-110">Коэффициент приведет к сужению шкалы значений в датчике, но не уменьшит сами значения.</span><span class="sxs-lookup"><span data-stu-id="15acc-110">The multiplier will only reduce the scale of the numbers on the gauge, not the value itself.</span></span>  
  
 <span data-ttu-id="15acc-111">Можно использовать выражения для задания значений параметров **Минимальное** и **Максимальное** .</span><span class="sxs-lookup"><span data-stu-id="15acc-111">You can use expressions to set the values of the **Minimum** and **Maximum** options.</span></span> <span data-ttu-id="15acc-112">Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="15acc-112">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-minimum-and-maximum-on-the-gauge"></a><span data-ttu-id="15acc-113">Установка минимума и максимума на датчике</span><span class="sxs-lookup"><span data-stu-id="15acc-113">To set the minimum and maximum on the gauge</span></span>  
  
1.  <span data-ttu-id="15acc-114">Щелкните правой кнопкой мыши шкалу и выберите **Свойства шкалы**.</span><span class="sxs-lookup"><span data-stu-id="15acc-114">Right-click on the scale and select **Scale Properties**.</span></span> <span data-ttu-id="15acc-115">Откроется диалоговое окно **Свойства шкалы** .</span><span class="sxs-lookup"><span data-stu-id="15acc-115">The **Scale Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="15acc-116">На вкладке **Общие**задайте значение для параметра **Минимум**.</span><span class="sxs-lookup"><span data-stu-id="15acc-116">In **General**, specify a value for **Minimum**.</span></span> <span data-ttu-id="15acc-117">По умолчанию это значение равно 0.</span><span class="sxs-lookup"><span data-stu-id="15acc-117">By default, this value is 0.</span></span> <span data-ttu-id="15acc-118">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="15acc-118">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
3.  <span data-ttu-id="15acc-119">Укажите значение для параметра **Максимум**.</span><span class="sxs-lookup"><span data-stu-id="15acc-119">Specify a value for **Maximum**.</span></span> <span data-ttu-id="15acc-120">По умолчанию это значение равно 100.</span><span class="sxs-lookup"><span data-stu-id="15acc-120">By default, this value is 100.</span></span> <span data-ttu-id="15acc-121">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="15acc-121">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="15acc-122">Если значения минимума и максимума очень большие, укажите значение для параметра **Умножить значения меток шкалы на** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="15acc-122">(Optional) If the values for your minimum and maximum are large, specify a value for the **Multiply scale labels by** option.</span></span> <span data-ttu-id="15acc-123">Чтобы задать множитель, сокращающий шкалу, используйте десятичное число.</span><span class="sxs-lookup"><span data-stu-id="15acc-123">To specify a multiplier that reduces your scale, use a decimal number.</span></span> <span data-ttu-id="15acc-124">Например, если имеется шкала от 0 до 1000, можно задать значение множителя 0,01, чтобы уменьшить значения шкалы от 0 до 10.</span><span class="sxs-lookup"><span data-stu-id="15acc-124">For example, if you have a scale from 0 to 1000, you can specify a multiplier value of 0.01 to reduce the scale to read 0 to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15acc-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="15acc-125">See Also</span></span>  
 <span data-ttu-id="15acc-126">[Форматирование шкал на датчике (построитель отчетов и службы SSRS)](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="15acc-126">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="15acc-127">[Форматирование указателей на датчике &#40;построитель отчетов и службы SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="15acc-127">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="15acc-128">Датчики (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="15acc-128">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
