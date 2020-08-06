---
title: Выбросы (SQL Server надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exceptions [data mining]
- data preparation
- outliers [data mining]
- data cleaning
ms.assetid: e6fa7c62-4005-4792-9211-3b699377a517
author: minewiskan
ms.author: owend
ms.openlocfilehash: 92dddf3338d15e700576a13476ee364696bfd274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752432"
---
# <a name="outliers-sql-server-data-mining-add-ins"></a><span data-ttu-id="eeaad-102">Выбросы (надстройки интеллектуального анализа данных SQL Server)</span><span class="sxs-lookup"><span data-stu-id="eeaad-102">Outliers (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="eeaad-103">![Мастер удаления выбросов на ленте «Интеллектуальный анализ данных»](media/dmc-outliers.gif "Мастер удаления выбросов на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="eeaad-103">![Outliers wizard in Data Mining ribbon](media/dmc-outliers.gif "Outliers wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="eeaad-104">*Выброс* — это значение данных, которое может быть проблематичным по одной из следующих причин:</span><span class="sxs-lookup"><span data-stu-id="eeaad-104">An *outlier* means a data value that is problematic for any one of the following reasons:</span></span>  
  
-   <span data-ttu-id="eeaad-105">значение находится за пределами ожидаемого диапазона;</span><span class="sxs-lookup"><span data-stu-id="eeaad-105">Value is outside the expected range.</span></span>  
  
-   <span data-ttu-id="eeaad-106">данные были введены неправильно;</span><span class="sxs-lookup"><span data-stu-id="eeaad-106">Data might have been entered incorrectly.</span></span>  
  
-   <span data-ttu-id="eeaad-107">значение отсутствует;</span><span class="sxs-lookup"><span data-stu-id="eeaad-107">Value is missing.</span></span>  
  
-   <span data-ttu-id="eeaad-108">данные представляют собой пробел или пустую строку;</span><span class="sxs-lookup"><span data-stu-id="eeaad-108">Data consists of a space or other null string.</span></span>  
  
-   <span data-ttu-id="eeaad-109">Значение точное, но находится настолько далеко от распределения, что может существенно повлиять на модель.</span><span class="sxs-lookup"><span data-stu-id="eeaad-109">Value is accurate, but is so far outside the distribution that it can significantly affect the model.</span></span>  
  
 <span data-ttu-id="eeaad-110">Клиент интеллектуального анализа данных для Excel позволяет обнаруживать такие данные, а затем обновлять соответствующие значения или подавлять их.</span><span class="sxs-lookup"><span data-stu-id="eeaad-110">The Data Mining Client for Excel helps you detect this data, and then update the values or suppress them.</span></span> <span data-ttu-id="eeaad-111">Например, можно заменить выбросы средним арифметическим или удалять строки, содержащие потенциально неправильные значения.</span><span class="sxs-lookup"><span data-stu-id="eeaad-111">For example, you can replace outliers with an arithmetic mean, or you can delete rows that contain potentially wrong values.</span></span>  
  
## <a name="handling-outliers"></a><span data-ttu-id="eeaad-112">Управление выбросами</span><span class="sxs-lookup"><span data-stu-id="eeaad-112">Handling Outliers</span></span>  
 <span data-ttu-id="eeaad-113">Мастер **удаления выбросов** предоставляет несколько средств для правильной обработки выбросов:</span><span class="sxs-lookup"><span data-stu-id="eeaad-113">The **Remove Outliers** wizard gives you several tools to handle outliers appropriately:</span></span>  
  
-   <span data-ttu-id="eeaad-114">Прежде всего можно исследовать данные, чтобы лучше понять распределение значений и определить, как связаны выбросы с другими данными.</span><span class="sxs-lookup"><span data-stu-id="eeaad-114">First, you can explore the data to better understand the distribution of values and the relationship of the outliers to other data.</span></span>  
  
     <span data-ttu-id="eeaad-115">Например, задачу « **Просмотр данных** » можно использовать для просмотра и исправления значений.</span><span class="sxs-lookup"><span data-stu-id="eeaad-115">For example, you can use the **Explore Data** task to review and fix the values.</span></span> <span data-ttu-id="eeaad-116">Мастер **удаления выбросов** также отображает график или линейчатую диаграмму, помогающие понять распределение всех значений.</span><span class="sxs-lookup"><span data-stu-id="eeaad-116">The **Remove Outliers** wizard also displays a graph, either a line or a bar chart, to help you understand the distribution of all values.</span></span>  
  
-   <span data-ttu-id="eeaad-117">Затем можно использовать мастер **выбросов** для удаления или изменения выбросов.</span><span class="sxs-lookup"><span data-stu-id="eeaad-117">Next, you can use the **Outliers** wizard to remove or change outliers.</span></span> <span data-ttu-id="eeaad-118">Выбор используемого метода зависит от того, являются ли рассматриваемые значения дискретными или непрерывными.</span><span class="sxs-lookup"><span data-stu-id="eeaad-118">The method that you use depends on whether the values are discrete or continuous.</span></span>  
  
     <span data-ttu-id="eeaad-119">В мастере дискретные значения отображаются с помощью линейчатой диаграммы, в которой каждый прямоугольник представляет конкретное значение, а высота прямоугольника обозначает количество случаев появления каждого значения.</span><span class="sxs-lookup"><span data-stu-id="eeaad-119">The wizard displays discrete values in a bar chart, where each bar represents a specific value, and the height of the bar indicates the number of cases for each value.</span></span> <span data-ttu-id="eeaad-120">Передвигая ползунок элемента управления пороговым значением на диаграмме, можно отсечь прямоугольники, представляющие группы с экстремальными или, возможно, неправильными значениями.</span><span class="sxs-lookup"><span data-stu-id="eeaad-120">By sliding the threshold control on the chart, you can cut off bars that represent groups of extreme or potentially bad values.</span></span>  
  
-   <span data-ttu-id="eeaad-121">Непрерывные значения отображаются в мастере с помощью линейчатой диаграммы или линейного графика.</span><span class="sxs-lookup"><span data-stu-id="eeaad-121">The wizard displays continuous values either on a bar chart or line chart.</span></span> <span data-ttu-id="eeaad-122">На графике значение представлено на оси x, а число значений — на оси y.</span><span class="sxs-lookup"><span data-stu-id="eeaad-122">On the line chart, the value is represented on the x-axis and the count of values on the y-axis.</span></span>  
  
     <span data-ttu-id="eeaad-123">Можно контролировать, следует ли удалять или отменять значения на низких и верхних концах диаграммы, изменяя **минимальное** и **Максимальное** значения, а также скользящие полосы.</span><span class="sxs-lookup"><span data-stu-id="eeaad-123">You can control whether to remove or keep values at the low and high ends of the chart by changing the **Minimum** and **Maximum** values, or sliding the bars.</span></span> <span data-ttu-id="eeaad-124">После изменения минимального и максимального значения данные, которые будут отброшены, обозначаются на диаграмме с помощью затенения.</span><span class="sxs-lookup"><span data-stu-id="eeaad-124">As you change the minimum and maximum value settings, the data that will be suppressed is shown by shading in the graph.</span></span>  
  
 <span data-ttu-id="eeaad-125">После выбора выбросов, которые нужно обработать, можно дать указание мастеру, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="eeaad-125">After you have selected which outliers to work with, you tell the wizard how to handle the outliers.</span></span> <span data-ttu-id="eeaad-126">Можно либо удалить строки, содержащие значения выбросов, либо указать заменяющее значение, например среднее значение, значение NULL или другое произвольно взятое значение.</span><span class="sxs-lookup"><span data-stu-id="eeaad-126">You can either delete the rows that contain the outlier values, or you can specify a replacement value, such as a mean, a null, or another value of your choice.</span></span>  
  
 <span data-ttu-id="eeaad-127">Наконец, мастер предоставляет пользователю несколько режимов отображения вновь полученных данных.</span><span class="sxs-lookup"><span data-stu-id="eeaad-127">Finally, the wizard gives you some options for displaying the new data.</span></span> <span data-ttu-id="eeaad-128">Можно заменить исходные данные новыми значениями, добавить новые столбцы в таблицу, содержащую новые значения, или создать новый лист, содержащий обновленные данные.</span><span class="sxs-lookup"><span data-stu-id="eeaad-128">You can replace the original data with the new values, add a new column to the table that contains the new values, or create a new worksheet that contains the updated data.</span></span>  
  
### <a name="using-the-outlier-wizard"></a><span data-ttu-id="eeaad-129">Использование мастера выбросов</span><span class="sxs-lookup"><span data-stu-id="eeaad-129">Using the Outlier Wizard</span></span>  
  
1.  <span data-ttu-id="eeaad-130">На ленте **интеллектуальный анализ данных** нажмите кнопку **Очистить данные**и выберите **выбросы**.</span><span class="sxs-lookup"><span data-stu-id="eeaad-130">In the **Data Mining** ribbon, click **Clean Data**, and select **Outliers**.</span></span>  
  
2.  <span data-ttu-id="eeaad-131">В диалоговом окне **Выбор источника данных** выберите таблицу данных Excel или диапазон ячеек и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eeaad-131">In the **Select Source Data** dialog box, select an Excel data table, or a range of cells, and click **Next**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="eeaad-132">Мастер **выбросов** нельзя использовать для внешних данных, если сначала не скопировать его в Excel.</span><span class="sxs-lookup"><span data-stu-id="eeaad-132">You cannot use the **Outliers** wizard on external data, unless you copy it to Excel first.</span></span>  
  
3.  <span data-ttu-id="eeaad-133">В диалоговом окне **Выбор столбца** выберите **один** столбец.</span><span class="sxs-lookup"><span data-stu-id="eeaad-133">In the **Select Column** dialog box, select a **single** column.</span></span>  
  
     <span data-ttu-id="eeaad-134">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eeaad-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="eeaad-135">В диалоговом окне **задание пороговых значений** Проверьте распределение данных.</span><span class="sxs-lookup"><span data-stu-id="eeaad-135">In the **Specify Thresholds** dialog box, review the distribution of data.</span></span>  
  
    -   <span data-ttu-id="eeaad-136">Если столбец содержит дискретные значения, то мастер отображает гистограмму, содержащую число каждого дискретного значения.</span><span class="sxs-lookup"><span data-stu-id="eeaad-136">If the column contains discrete values, the wizard displays a histogram containing the count for each discrete value.</span></span>  
  
         <span data-ttu-id="eeaad-137">Если выбросы представляют собой редко встречающиеся значения, их можно отфильтровать, изменив **минимальное** значение.</span><span class="sxs-lookup"><span data-stu-id="eeaad-137">Assuming that outliers are rare values, you can filter them out by changing the **Minimum** value.</span></span>  
  
    -   <span data-ttu-id="eeaad-138">Если столбец содержит числовые данные, можно нажать кнопку **вид как дискретная** кнопка или **Просмотреть как числовое** значение, чтобы переключиться между просмотром значений на линейчатой диаграмме или графике.</span><span class="sxs-lookup"><span data-stu-id="eeaad-138">If the column contains numeric data, you can click the **View as Discrete** button or the **View as Numeric** button to toggle between viewing the values in a bar chart or line chart.</span></span>  
  
5.  <span data-ttu-id="eeaad-139">В диалоговом окне **Укажите пороговые** значения выберите диапазон данных, которые нужно удерживать, введя минимальное и максимальное значение или перетащив ползунки.</span><span class="sxs-lookup"><span data-stu-id="eeaad-139">In the **Specify Thresholds** dialog box, choose the range of data you want to keep by typing a minimum and maximum value, or by dragging the slider bars.</span></span> <span data-ttu-id="eeaad-140">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eeaad-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="eeaad-141">В диалоговом окне **Обработка выбросов** укажите, следует ли удалить или заменить значения, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eeaad-141">In the **Outlier Handling** dialog box, specify whether you want the values to be deleted or replaced, and click **Next**.</span></span>  
  
7.  <span data-ttu-id="eeaad-142">В диалоговом окне **Выбор назначения** укажите, где следует сохранять новые данные.</span><span class="sxs-lookup"><span data-stu-id="eeaad-142">In the **Select Destination** dialog box, specify where you want the new data to be saved.</span></span>  
  
### <a name="related-options"></a><span data-ttu-id="eeaad-143">Связанные параметры</span><span class="sxs-lookup"><span data-stu-id="eeaad-143">Related Options</span></span>  
 <span data-ttu-id="eeaad-144">Мастер предоставляет следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="eeaad-144">The wizard provides these options:</span></span>  
  
|<span data-ttu-id="eeaad-145">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="eeaad-145">**Options**</span></span>|<span data-ttu-id="eeaad-146">**Комментарий**</span><span class="sxs-lookup"><span data-stu-id="eeaad-146">**Comment**</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="eeaad-147">**Выбор столбца**</span><span class="sxs-lookup"><span data-stu-id="eeaad-147">**Select Column**</span></span>|<span data-ttu-id="eeaad-148">В каждый момент времени можно работать только с одним столбцом.</span><span class="sxs-lookup"><span data-stu-id="eeaad-148">You can work with only one column at a time.</span></span>|  
|<span data-ttu-id="eeaad-149">**Указание обработки пороговых значений**</span><span class="sxs-lookup"><span data-stu-id="eeaad-149">**Specify Thresholds Handling**</span></span>|<span data-ttu-id="eeaad-150">Установите пороговое значение с помощью параметра **минимум** , чтобы исключить значения, которые находятся в меньшем количестве строк, чем пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="eeaad-150">Set a threshold using **Minimum** to exclude values that are found in fewer rows than the threshold value.</span></span><br /><br /> <span data-ttu-id="eeaad-151">Изначально **минимальное значение** равно значению с наименьшим числом строк, и вы не можете сделать минимальное значение меньше этого значения.</span><span class="sxs-lookup"><span data-stu-id="eeaad-151">Initially the value in **Minimum** is equal to the value with the fewest rows, and you cannot make the minimum lower than that value.</span></span>|  
|<span data-ttu-id="eeaad-152">**Управление выбросами**</span><span class="sxs-lookup"><span data-stu-id="eeaad-152">**Outlier Handling**</span></span>|<span data-ttu-id="eeaad-153">Если вы решили удалить выбросы, можно изменить данные в текущем листе или создать копию данных в новом листе.</span><span class="sxs-lookup"><span data-stu-id="eeaad-153">If you decide to delete outliers, you can either change the data in the current worksheet, or create a copy of the data in a new worksheet.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eeaad-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="eeaad-154">See Also</span></span>  
 [<span data-ttu-id="eeaad-155">Изучите &#40;данных SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="eeaad-155">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
  
