---
title: Просмотр данных (SQL Server надстроек интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- histogram [data mining]
- data visualization
ms.assetid: 714845a9-4c27-461a-9ba3-149e1e818386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2572c11e92dcf99dfa3adf661603e8f65f05116e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734558"
---
# <a name="explore-data-sql-server-data-mining-add-ins"></a><span data-ttu-id="124ab-102">Просмотр данных (надстройки интеллектуального анализа данных SQL Server)</span><span class="sxs-lookup"><span data-stu-id="124ab-102">Explore Data (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="124ab-103">![Мастер просмотра данных](media/dmc-explore.gif "Мастер просмотра данных")</span><span class="sxs-lookup"><span data-stu-id="124ab-103">![Explore Data wizard](media/dmc-explore.gif "Explore Data wizard")</span></span>  
  
 <span data-ttu-id="124ab-104">Мастер **просмотра данных** помогает понять тип и объем данных в таблице данных.</span><span class="sxs-lookup"><span data-stu-id="124ab-104">The **Explore Data** wizard helps you understand the type and amount of data in your data table.</span></span> <span data-ttu-id="124ab-105">Мастер наносит на диаграмму распределение и значения для выбранных столбцов поочередно.</span><span class="sxs-lookup"><span data-stu-id="124ab-105">The wizard graphs the distribution and values for the selected columns, one column at a time.</span></span> <span data-ttu-id="124ab-106">Можно поэкспериментировать с изменением числа сегментов, способом группировки данных или скопировать диаграмму с содержимым в книгу Excel для просмотра.</span><span class="sxs-lookup"><span data-stu-id="124ab-106">You can then experiment with changing the way that data is grouped, or copy the chart that shows the content to an Excel workbook for review.</span></span>  
  
 <span data-ttu-id="124ab-107">Если в данных содержатся непрерывные числовые данные, можно переключаться между следующими двумя представлениями.</span><span class="sxs-lookup"><span data-stu-id="124ab-107">If your data contains continuous numeric data, you can toggle between these two views:</span></span>  
  
-   <span data-ttu-id="124ab-108">**Линейный график.**</span><span class="sxs-lookup"><span data-stu-id="124ab-108">**Line graph.**</span></span> <span data-ttu-id="124ab-109">На этом графике значения данных расположены на оси X, а число вариантов — на оси Y.</span><span class="sxs-lookup"><span data-stu-id="124ab-109">This graph charts the data values on the X-axis and the number of cases on the y-axis.</span></span>  
  
-   <span data-ttu-id="124ab-110">**Линейчатая диаграмма.**</span><span class="sxs-lookup"><span data-stu-id="124ab-110">**Bar chart.**</span></span> <span data-ttu-id="124ab-111">Эта диаграмма группирует значения по числу случаев для каждого значения.</span><span class="sxs-lookup"><span data-stu-id="124ab-111">This graph groups values by the number of cases for each value.</span></span>  
  
 <span data-ttu-id="124ab-112">Если мастер обнаруживает в данных группы, он использует реальное распределение значений данных.</span><span class="sxs-lookup"><span data-stu-id="124ab-112">When the wizard finds groups in the data, it uses the actual distribution of data values.</span></span> <span data-ttu-id="124ab-113">Вследствие этого в линейчатой диаграмме не отображаются маркеры обычной целочисленной числовой оси, например 10 или 100.</span><span class="sxs-lookup"><span data-stu-id="124ab-113">Therefore, the bar chart does not show typical whole-number numeric axis markers such as 10 or 100.</span></span> <span data-ttu-id="124ab-114">Вместо этого диапазоны на линейчатой диаграмме могут быть, например, 43 521–55 603 (в столбце дохода).</span><span class="sxs-lookup"><span data-stu-id="124ab-114">Instead, the ranges shown in the bar chart might be something like 43521-55603 (for the Income column).</span></span>  
  
 <span data-ttu-id="124ab-115">Если необходимо группировать данные в другие диапазоны, это следует выполнить в Excel перед выполнением анализа данных.</span><span class="sxs-lookup"><span data-stu-id="124ab-115">If you want to group your data into other ranges, you should do this in Excel before analyzing the data.</span></span> <span data-ttu-id="124ab-116">Можно также переметить данные с помощью мастера [переразметки](relabel-sql-server-data-mining-add-ins.md) .</span><span class="sxs-lookup"><span data-stu-id="124ab-116">Or, you can relabel the data by using the [Relabel](relabel-sql-server-data-mining-add-ins.md) wizard.</span></span>  
  
## <a name="using-the-explore-data-wizard"></a><span data-ttu-id="124ab-117">Использование мастера просмотра данных</span><span class="sxs-lookup"><span data-stu-id="124ab-117">Using the Explore Data Wizard</span></span>  
  
1.  <span data-ttu-id="124ab-118">На ленте **интеллектуальный анализ данных** нажмите кнопку **Просмотр данных**.</span><span class="sxs-lookup"><span data-stu-id="124ab-118">In the **Data Mining** ribbon, click **Explore Data**.</span></span>  
  
2.  <span data-ttu-id="124ab-119">В диалоговом окне **Выбор источника** выберите таблицу или диапазон ячеек, содержащих данные.</span><span class="sxs-lookup"><span data-stu-id="124ab-119">In the **Select Source** dialog box, select the table or range of cells that contains your data.</span></span>  
  
3.  <span data-ttu-id="124ab-120">В диалоговом окне **Выбор столбца** выберите столбец для анализа из демонстрационных данных, отображаемых на панели.</span><span class="sxs-lookup"><span data-stu-id="124ab-120">In the **Select Column** dialog box, choose the column to analyze, from the sample data displayed in the pane.</span></span>  
  
4.  <span data-ttu-id="124ab-121">В диалоговом окне **Просмотр данных** выберите типы диаграмм для отображения распределения данных.</span><span class="sxs-lookup"><span data-stu-id="124ab-121">In the **Explore Data** dialog box, choose the chart types for displaying the distribution of data.</span></span>  
  
5.  <span data-ttu-id="124ab-122">Можно дополнительно добавить новые столбцы к данным, изменить порядок сегментации данных или скопировать диаграмму в Excel.</span><span class="sxs-lookup"><span data-stu-id="124ab-122">Optionally, you can add new columns to the data, change the way that the data is segmented, or copy the chart to Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="124ab-123">Требования</span><span class="sxs-lookup"><span data-stu-id="124ab-123">Requirements</span></span>  
 <span data-ttu-id="124ab-124">Чтобы использовать мастер **просмотра данных** , данные должны находиться в таблице данных Excel.</span><span class="sxs-lookup"><span data-stu-id="124ab-124">To use the **Explore Data** wizard, your data must be in an Excel data table.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="124ab-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="124ab-125">See Also</span></span>  
 [<span data-ttu-id="124ab-126">Контрольный список для подготовки к интеллектуальному анализу данных</span><span class="sxs-lookup"><span data-stu-id="124ab-126">Checklist of Preparation for Data Mining</span></span>](checklist-of-preparation-for-data-mining.md)  
  
  
