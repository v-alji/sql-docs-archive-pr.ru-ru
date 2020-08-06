---
title: Выравнивание данных в диаграмме в таблице или матрице (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 75137575-d1bf-46d6-8527-5afc85eea5e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3e4278cd9f0dd5526770b43d2c6d94a8b87158cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667600"
---
# <a name="align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs"></a><span data-ttu-id="edbb1-102">Выравнивание данных в диаграмме в таблице или матрице (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="edbb1-102">Align the Data in a Chart in a Table or Matrix (Report Builder and SSRS)</span></span>
  <span data-ttu-id="edbb1-103">Sparkline-графики и гистограммы — это маленькие, простые диаграммы, которые передают большой объем данных без ненужных подробностей.</span><span class="sxs-lookup"><span data-stu-id="edbb1-103">Sparklines and data bars are small, simple charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="edbb1-104">Если выбрать этот параметр, то значения в sparkline-графиках и гистограммах будут выравниваться по различным ячейкам в таблице или матрице даже в случае, если в базовых данных отсутствуют некоторые значения.</span><span class="sxs-lookup"><span data-stu-id="edbb1-104">When you check this option, the values in your sparklines and data bars will align across the different cells in the table or matrix, even if there are missing values in the data they are based on.</span></span>  
  
 <span data-ttu-id="edbb1-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span><span class="sxs-lookup"><span data-stu-id="edbb1-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span></span>  
  
 <span data-ttu-id="edbb1-106">На этом изображении на гистограмме отображаются значения продаж за день для всех сотрудников.</span><span class="sxs-lookup"><span data-stu-id="edbb1-106">In this image, the column chart shows daily sales for each employee.</span></span> <span data-ttu-id="edbb1-107">Обратите внимание, что для дней, когда у сотрудников нет продаж, на гистограмме остается пустая область и последующие дни выравниваются по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="edbb1-107">Note that for days that an employee has no sales, the chart leaves a blank and aligns subsequent days horizontally.</span></span> <span data-ttu-id="edbb1-108">Диаграммы выравниваются также по вертикали путем изменения размеров других диаграмм по отношению друг к другу.</span><span class="sxs-lookup"><span data-stu-id="edbb1-108">It also aligns the charts vertically by making the sizes of the different charts relative to each other.</span></span> <span data-ttu-id="edbb1-109">Дополнительные сведения см. в разделе [Спарклайны и гистограммы (построитель отчетов и службы SSRS)](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="edbb1-109">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="align-the-data-in-a-sparkline-or-data-bar"></a><span data-ttu-id="edbb1-110">Выравнивание данных в спарклайн-графиках и гистограммах</span><span class="sxs-lookup"><span data-stu-id="edbb1-110">Align the data in a sparkline or data bar</span></span>  
  
1.  <span data-ttu-id="edbb1-111">Щелкните спарклайн-график или гистограмму и выберите **Свойства горизонтальных осей** или **Свойства вертикальных осей**.</span><span class="sxs-lookup"><span data-stu-id="edbb1-111">Click in the sparkline or data bar, and then click **Horizontal Axis Properties** or **Vertical Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="edbb1-112">На вкладке **Параметры осей** установите флажок **Выровнять оси в** , затем в раскрывающемся списке выберите группу, для которой необходимо выровнять оси.</span><span class="sxs-lookup"><span data-stu-id="edbb1-112">On the **Axis Options** tab, check the **Align axes in** box, and then in the dropdown box, select the group on which to align the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="edbb1-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="edbb1-113">See Also</span></span>  
 <span data-ttu-id="edbb1-114">[Диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edbb1-114">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="edbb1-115">Добавление спарклайнов и гистограмм (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="edbb1-115">Add Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](add-sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
