---
title: Добавление скользящего среднего в диаграмму (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166cf9c1-0750-4866-8381-542e4fbfe65a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bc16d0cb45a3240148f931009a836c231b442b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654810"
---
# <a name="add-a-moving-average-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="3f686-102">Добавление скользящего среднего в диаграмму (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3f686-102">Add a Moving Average to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3f686-103">Скользящее среднее — это среднее по данным в ряде, вычисленное за определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="3f686-103">A moving average is an average of the data in your series, calculated over a defined period of time.</span></span> <span data-ttu-id="3f686-104">Скользящее среднее можно отобразить в диаграмме для определения существенных трендов.</span><span class="sxs-lookup"><span data-stu-id="3f686-104">The moving average can be shown on the chart to identify significant trends.</span></span>  
  
 <span data-ttu-id="3f686-105">Формула скользящего среднего является наиболее популярным признаком цены, используемым в техническом анализе.</span><span class="sxs-lookup"><span data-stu-id="3f686-105">The Moving Average formula is the most popular price indicator used in technical analyses.</span></span> <span data-ttu-id="3f686-106">Многие другие формулы, включая среднее, медиану и стандартное отклонение также могут быть производными от ряда на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="3f686-106">Many other formulas, including mean, median and standard deviation, can also be derived from a series on the chart.</span></span> <span data-ttu-id="3f686-107">При указании скользящего среднего каждая формула может иметь один или более параметров, которые необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="3f686-107">When specifying a moving average, each formula may have one or more parameters that must be specified.</span></span>  
  
 <span data-ttu-id="3f686-108">Когда формула скользящего среднего добавляется в режиме конструктора, добавляемый ряд линий является только видимым заполнителем.</span><span class="sxs-lookup"><span data-stu-id="3f686-108">When a moving average formula is added in Design mode, the line series that is added is only a visual placeholder.</span></span> <span data-ttu-id="3f686-109">Диаграмма вычислит точки данных каждой формулы во время обработки отчета.</span><span class="sxs-lookup"><span data-stu-id="3f686-109">The chart will calculate the data points of each formula during report processing.</span></span>  
  
 <span data-ttu-id="3f686-110">Встроенная поддержка линий тренда недоступна в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f686-110">Built-in support for trend lines is not available in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-calculated-moving-average-to-a-series-on-the-chart"></a><span data-ttu-id="3f686-111">Добавление вычисленного скользящего среднего в ряд на диаграмме</span><span class="sxs-lookup"><span data-stu-id="3f686-111">To add a calculated moving average to a series on the chart</span></span>  
  
1.  <span data-ttu-id="3f686-112">Щелкните правой кнопкой мыши поле в области **Значения** и выберите пункт **Добавить вычисляемый ряд**.</span><span class="sxs-lookup"><span data-stu-id="3f686-112">Right-click on a field in the **Values** area and click **Add Calculated Series**.</span></span> <span data-ttu-id="3f686-113">Откроется диалоговое окно **Свойства вычисляемого ряда** .</span><span class="sxs-lookup"><span data-stu-id="3f686-113">The **Calculated Series Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3f686-114">В раскрывающемся списке **Формула** выберите параметр **Скользящее среднее** .</span><span class="sxs-lookup"><span data-stu-id="3f686-114">Select the **Moving average** option from the **Formula** drop-down list.</span></span>  
  
3.  <span data-ttu-id="3f686-115">Укажите целое число для пункта **Период** , представляющего период скользящего среднего.</span><span class="sxs-lookup"><span data-stu-id="3f686-115">Specify an integer value for the **Period** that represents the period of the moving average.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3f686-116">Период — это количество дней, используемых для подсчета скользящего среднего.</span><span class="sxs-lookup"><span data-stu-id="3f686-116">The period is the number of days used to calculate a moving average.</span></span> <span data-ttu-id="3f686-117">Если значения даты-времени не указываются на оси X, период представляется количеством точек данных, используемых для вычисления скользящего среднего.</span><span class="sxs-lookup"><span data-stu-id="3f686-117">If date/time values are not specified on the x-axis, the period is represented by the number of data points used to calculate a moving average.</span></span> <span data-ttu-id="3f686-118">Если есть только одна точка данных, формула скользящего среднего не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="3f686-118">If there is only one data point, the moving average formula does not calculate.</span></span> <span data-ttu-id="3f686-119">Скользящее среднее вычисляется, начиная со второй точки.</span><span class="sxs-lookup"><span data-stu-id="3f686-119">The moving average is calculated starting at the second point.</span></span> <span data-ttu-id="3f686-120">При задании параметра **Начать с первой точки** , диаграмма начнет вычисление скользящего среднего с первой точки.</span><span class="sxs-lookup"><span data-stu-id="3f686-120">If you specify the **Start from first point** option, the chart will start the moving average at the first point.</span></span> <span data-ttu-id="3f686-121">Если существует только одна точка данных, то точка в вычисленном скользящем среднем будет идентична первой точке исходного ряда.</span><span class="sxs-lookup"><span data-stu-id="3f686-121">If there is only one data point, the point in the calculated moving average will be identical to the first point in your original series.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f686-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f686-122">See Also</span></span>  
 <span data-ttu-id="3f686-123">[Форматирование построитель отчетов &#40;диаграммы и SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3f686-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3f686-124">[Диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3f686-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3f686-125">Добавление пустых точек на диаграмму &#40;построитель отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3f686-125">Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;</span></span>](add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
  
