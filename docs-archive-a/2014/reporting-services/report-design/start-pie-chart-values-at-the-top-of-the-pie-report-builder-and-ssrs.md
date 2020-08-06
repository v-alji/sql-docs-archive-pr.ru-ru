---
title: Вывод значений круговой диаграммы в верхней части диаграммы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0e6fb59-ca4e-4d70-97cb-0ad183da21d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed010eeaf3e4d581cce2f7242144c4f73ec2895b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654775"
---
# <a name="start-pie-chart-values-at-the-top-of-the-pie-report-builder-and-ssrs"></a><span data-ttu-id="2dd13-102">Вывод значений круговой диаграммы в верхней части диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2dd13-102">Start Pie Chart Values at the Top of the Pie (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2dd13-103">По умолчанию в круговых диаграммах первое значение набора данных отсчитывается с 90-го градуса от верхней части диаграммы.</span><span class="sxs-lookup"><span data-stu-id="2dd13-103">By default in pie charts, the first value in the dataset starts at 90 degrees from the top of the pie.</span></span> <span data-ttu-id="2dd13-104">Можно указать, чтобы первое значение отсчитывалось от верхней части диаграммы.</span><span class="sxs-lookup"><span data-stu-id="2dd13-104">You may prefer that the first value start from the top.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-start-the-pie-chart-at-the-top-of-the-pie"></a><span data-ttu-id="2dd13-105">Отсчет значений круговой диаграммы от верхней части диаграммы</span><span class="sxs-lookup"><span data-stu-id="2dd13-105">To Start the Pie Chart at the Top of the Pie</span></span>  
  
1.  <span data-ttu-id="2dd13-106">Щелкните круговую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="2dd13-106">Click the pie itself.</span></span>  
  
2.  <span data-ttu-id="2dd13-107">Если панель **Свойства** не отображается, выберите на вкладке **Вид** пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2dd13-107">If the **Properties** pane is not open, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2dd13-108">В области **Свойства** в разделе **настраиваемые атрибуты**измените значение **пиестартангле** с **0** на **270**.</span><span class="sxs-lookup"><span data-stu-id="2dd13-108">In the **Properties** pane, under **Custom Attributes**, change **PieStartAngle** from **0** to **270**.</span></span>  
  
4.  <span data-ttu-id="2dd13-109">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="2dd13-109">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="2dd13-110">Теперь первое значение круговой диаграммы отсчитывается от верхней части диаграммы.</span><span class="sxs-lookup"><span data-stu-id="2dd13-110">The first value now starts at the top of the pie chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd13-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="2dd13-111">See Also</span></span>  
 <span data-ttu-id="2dd13-112">[Форматирование построитель отчетов &#40;диаграммы и SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2dd13-112">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2dd13-113">Круговые диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2dd13-113">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
