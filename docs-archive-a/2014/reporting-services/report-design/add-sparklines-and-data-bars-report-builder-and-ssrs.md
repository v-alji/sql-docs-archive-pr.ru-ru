---
title: Добавление спарклайнов и гистограмм (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0b297c2e-d48b-41b0-aabd-29680cdcdb05
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55ec15354cdc78dd9678b9466f30d2fca0a73adc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656167"
---
# <a name="add-sparklines-and-data-bars-report-builder-and-ssrs"></a><span data-ttu-id="a9f82-102">Добавление спарклайнов и гистограмм (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a9f82-102">Add Sparklines and Data Bars (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a9f82-103">Sparkline-графики и гистограммы — это маленькие, не требовательные к ресурсам диаграммы, которые передают большой объем данных без ненужных подробностей.</span><span class="sxs-lookup"><span data-stu-id="a9f82-103">Sparklines and data bars are small, spare charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="a9f82-104">Дополнительные сведения см. в разделе [Спарклайны и гистограммы (построитель отчетов и службы SSRS)](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9f82-104">For more information about them, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a9f82-105">Sparkline-графики и гистограммы обычно размещаются в ячейках в таблице или матрице.</span><span class="sxs-lookup"><span data-stu-id="a9f82-105">Sparklines and data bars are most commonly placed in cells in a table or matrix.</span></span> <span data-ttu-id="a9f82-106">Sparkline-графики обычно показывают только одну последовательность.</span><span class="sxs-lookup"><span data-stu-id="a9f82-106">Sparklines usually display only one series each.</span></span> <span data-ttu-id="a9f82-107">Гистограммы могут содержать одну или несколько точек данных.</span><span class="sxs-lookup"><span data-stu-id="a9f82-107">Data bars can contain one or more data points.</span></span> <span data-ttu-id="a9f82-108">Как sparkline-графики, так и гистограммы представляют результат повтора рядов для всех строк в таблице или матрице.</span><span class="sxs-lookup"><span data-stu-id="a9f82-108">Both sparklines and data bars derive their impact from repeating the series information for each row in the table or matrix.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-sparkline-or-data-bar-to-a-table-or-matrix"></a><span data-ttu-id="a9f82-109">Добавление в таблицу или матрицу спарклайн-графика или гистограммы</span><span class="sxs-lookup"><span data-stu-id="a9f82-109">To add a sparkline or data bar to a table or matrix</span></span>  
  
1.  <span data-ttu-id="a9f82-110">Если это еще не сделано, создайте таблицу или матрицу с данными, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="a9f82-110">If you have not done so already, create a table or matrix with the data you want to display.</span></span> <span data-ttu-id="a9f82-111">Дополнительные сведения см. в разделах [Таблицы (построитель отчетов и службы SSRS)](tables-report-builder-and-ssrs.md) и [Матрицы (построитель отчетов и службы SSRS)](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9f82-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="a9f82-112">Вставьте столбец в таблицу или матрицу.</span><span class="sxs-lookup"><span data-stu-id="a9f82-112">Insert a column in your table or matrix.</span></span> <span data-ttu-id="a9f82-113">Дополнительные сведения см. в разделе [Вставка или удаление столбца (построитель отчетов и службы SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9f82-113">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="a9f82-114">На вкладке **Вставка** выберите **Спарклайн-график** или **Гистограмма**, а затем щелкните ячейку в новом столбце.</span><span class="sxs-lookup"><span data-stu-id="a9f82-114">On the **Insert** tab, click **Sparkline** or **Data Bar**, and then click in a cell in the new column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9f82-115">Возможность добавления sparkline-графика в группу сведений таблицы не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="a9f82-115">You cannot place sparklines in a detail group in a table.</span></span> <span data-ttu-id="a9f82-116">Sparkline-график должен находиться в ячейке, связанной с группой.</span><span class="sxs-lookup"><span data-stu-id="a9f82-116">They must go in a cell associated with a group.</span></span>  
  
4.  <span data-ttu-id="a9f82-117">В диалоговом окне **Изменение типа спарклайна или гистограммы** выберите необходимый тип спарклайна и гистограммы, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9f82-117">In the **Change Sparkline/Data Bar Type** dialog box, click the kind of sparkline or data bar you want, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="a9f82-118">Щелкните спарклайн-график или гистограмму.</span><span class="sxs-lookup"><span data-stu-id="a9f82-118">Click the sparkline or data bar.</span></span>  
  
     <span data-ttu-id="a9f82-119">Откроется панель **Данные гистограммы** .</span><span class="sxs-lookup"><span data-stu-id="a9f82-119">The **Chart Data** pane opens.</span></span>  
  
6.  <span data-ttu-id="a9f82-120">В области **Значения** щелкните **Добавить поля** символ "плюс" (**+**), а затем щелкните поле, для значений которого необходимо создать диаграмму.</span><span class="sxs-lookup"><span data-stu-id="a9f82-120">In the **Values** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want charted.</span></span>  
  
7.  <span data-ttu-id="a9f82-121">В области **Группы категорий** щелкните **Добавить поля** символ "плюс" (**+**), а затем щелкните поле, значения которого необходимо сгруппировать.</span><span class="sxs-lookup"><span data-stu-id="a9f82-121">In the **Category Groups** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want to group by.</span></span>  
  
     <span data-ttu-id="a9f82-122">Обычно для sparkline-графиков и гистограмм к области **Группа рядов** не добавляются поля, поскольку для каждой строки необходим один ряд.</span><span class="sxs-lookup"><span data-stu-id="a9f82-122">Typically for sparklines and data bars, you will not add a field to the **Series Group** area because you only want one series for each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f82-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a9f82-123">See Also</span></span>  
 <span data-ttu-id="a9f82-124">[Диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a9f82-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a9f82-125">Выравнивание данных в диаграмме в таблице или матрице (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a9f82-125">Align the Data in a Chart in a Table or Matrix &#40;Report Builder and SSRS&#41;</span></span>](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
  
