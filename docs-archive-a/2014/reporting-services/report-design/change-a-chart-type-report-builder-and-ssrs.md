---
title: Изменение типа диаграммы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fff24978-e3bd-4fac-8cd7-d6aa81f3cc25
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb466bed475b27206bf6837a60d0867f5fb745be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728046"
---
# <a name="change-a-chart-type-report-builder-and-ssrs"></a><span data-ttu-id="5f65e-102">Изменение типа диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="5f65e-102">Change a Chart Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5f65e-103">При первом создании диаграммы в отчете появляется диалоговое окно **Выбор типа диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="5f65e-103">When you first insert a chart into a report, the **Select Chart Type** dialog appears.</span></span> <span data-ttu-id="5f65e-104">Если закрыть это диалоговое окно, по умолчанию будет создана диаграмма в виде гистограммы.</span><span class="sxs-lookup"><span data-stu-id="5f65e-104">If you cancel this dialog, a Column chart type is added by default.</span></span>  
  
 <span data-ttu-id="5f65e-105">В любой момент при создании отчета можно изменить тип диаграммы на другой, более подходящий.</span><span class="sxs-lookup"><span data-stu-id="5f65e-105">At any point when designing the report, you can change the chart type to something more suitable to the report.</span></span> <span data-ttu-id="5f65e-106">Выбор типа диаграммы влияет на правильность интерпретации имеющихся данных.</span><span class="sxs-lookup"><span data-stu-id="5f65e-106">It is important to select the correct chart type for your data so that it can be interpreted correctly.</span></span> <span data-ttu-id="5f65e-107">Чтобы правильно выбрать диаграмму для конкретных данных, нужно знать характеристики всех типов диаграмм.</span><span class="sxs-lookup"><span data-stu-id="5f65e-107">You should understand each chart type's characteristics to determine what chart type is best suited for your data.</span></span> <span data-ttu-id="5f65e-108">Дополнительные сведения см. в разделе [Типы диаграмм (построитель отчетов и службы SSRS)](chart-types-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5f65e-108">For more information, see [Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="5f65e-109">При выводе нескольких рядов данных иногда нужно использовать для одного из рядов иной тип диаграммы.</span><span class="sxs-lookup"><span data-stu-id="5f65e-109">When multiple series are displayed on a chart, you may want to change the chart type of an individual series.</span></span> <span data-ttu-id="5f65e-110">Тип диаграммы для отдельного ряда можно изменить только для диаграммы одного из следующих типов: диаграмма с областями, гистограмма, линейчатая или точечная диаграмма.</span><span class="sxs-lookup"><span data-stu-id="5f65e-110">You can only change the chart type of an individual series if the chart type is Area, Column, Line, or Scatter.</span></span> <span data-ttu-id="5f65e-111">У всех остальных диаграмм изменится тип диаграммы для всех рядов одновременно.</span><span class="sxs-lookup"><span data-stu-id="5f65e-111">For all other chart types, all series in your chart will be changed to the selected chart type.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-chart-type"></a><span data-ttu-id="5f65e-112">Изменение типа диаграммы</span><span class="sxs-lookup"><span data-stu-id="5f65e-112">To change the chart type</span></span>  
  
1.  <span data-ttu-id="5f65e-113">В построителе отчетов щелкните правой кнопкой мыши диаграмму в режиме конструктора и выберите пункт **Изменить тип диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="5f65e-113">In Design view, right-click the chart and then click **Change Chart Type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f65e-114">Если на диаграмме имеется несколько рядов, щелкните правой кнопкой мыши ряд, который нужно изменить, а не саму диаграмму.</span><span class="sxs-lookup"><span data-stu-id="5f65e-114">When there are multiple series on a chart, you must right-click on the series, not the chart, which you want to change.</span></span>  
  
2.  <span data-ttu-id="5f65e-115">В диалоговом окне **Выбрать тип диаграммы** выберите тип из списка.</span><span class="sxs-lookup"><span data-stu-id="5f65e-115">In the **SelectChart Type** dialog box, select a chart type from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f65e-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f65e-116">See Also</span></span>  
 <span data-ttu-id="5f65e-117">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5f65e-117">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5f65e-118">[Датчики (построитель отчетов и службы SSRS)](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5f65e-118">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5f65e-119">Добавление диаграммы в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="5f65e-119">Add a Chart to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-chart-to-a-report-report-builder-and-ssrs.md)  
  
  
