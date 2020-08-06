---
title: Занятие 4. Добавление таблицы в отчет (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ddf2914-bcdd-427d-8cba-0ccb8342f819
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52694168bd60b8e3807db6204f33a89815573093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656231"
---
# <a name="lesson-4-adding-a-table-to-the-report-reporting-services"></a><span data-ttu-id="1fc7b-102">Занятие 4. Добавление таблицы в отчет (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="1fc7b-102">Lesson 4: Adding a Table to the Report (Reporting Services)</span></span>
  <span data-ttu-id="1fc7b-103">После определения набора данных вы можете приступать к конструированию отчета.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-103">After the dataset is defined, you can start designing the report.</span></span> <span data-ttu-id="1fc7b-104">Макет отчета создается путем перетаскивания в область конструктора областей данных, текстовых полей, изображений и других элементов, которые необходимо включить в отчет.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-104">You create a report layout by dragging and dropping data regions, text boxes, images, and other items that you want to include in your report to the design surface.</span></span>  
  
 <span data-ttu-id="1fc7b-105">Элементы, содержащие повторяющиеся строки данных из базовых наборов данных, называются *областями данных*.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-105">Items that contain repeated rows of data from underlying datasets are called *data regions*.</span></span> <span data-ttu-id="1fc7b-106">Простые отчеты имеют только одну область данных, но можно добавить больше, например, если требуется добавить диаграмму в табличный отчет.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-106">A basic report will have only one data region, but you can add more, for example, if you want to add a chart to your tabular report.</span></span> <span data-ttu-id="1fc7b-107">После добавления области данных можно добавлять в нее поля.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-107">After you add a data region, you can add fields to the data region.</span></span>  
  
### <a name="to-add-a-table-data-region-and-fields-to-a-report-layout"></a><span data-ttu-id="1fc7b-108">Добавление табличной области данных и полей в макет отчета</span><span class="sxs-lookup"><span data-stu-id="1fc7b-108">To add a Table data region and fields to a report layout</span></span>  
  
1.  <span data-ttu-id="1fc7b-109">В окне **Панель элементов**щелкните элемент **Таблица**, а затем щелкните область конструктора и выполните перетаскивание мышью.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-109">In the **Toolbox**, click **Table**, and then click on the design surface and drag the mouse.</span></span> <span data-ttu-id="1fc7b-110">В конструкторе отчетов будет отображена табличная область данных с тремя столбцами, расположенными по центру области конструктора.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-110">Report Designer draws a table data region with three columns in the center of the design surface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fc7b-111">Окно **Панель элементов** может выглядеть как вкладка в левой стороне области **Данные отчета** .</span><span class="sxs-lookup"><span data-stu-id="1fc7b-111">The **Toolbox** may appear as a tab on the left side of the **Report Data** pane.</span></span> <span data-ttu-id="1fc7b-112">Чтобы открыть **панель элементов**, наведите указатель на вкладку **панель элементов** . Если **панель элементов** не отображается, в меню **вид** выберите пункт **область элементов**.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-112">To open the **Toolbox**, move the pointer over the **Toolbox** tab. If the **Toolbox** is not visible, from the **View** menu, click **Toolbox**.</span></span>  
  
2.  <span data-ttu-id="1fc7b-113">В области **данных отчета** разверните набор данных **AdventureWorksDataset** , чтобы отобразить поля.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-113">In the **Report Data** pane, expand the **AdventureWorksDataset** dataset to display the fields.</span></span>  
  
3.  <span data-ttu-id="1fc7b-114">Перетащите поле Date с панели **Данные отчета** в первый столбец таблицы.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-114">Drag the Date field from the **Report Data** pane to the first column in the table.</span></span>  
  
     <span data-ttu-id="1fc7b-115">После такого перетаскивания происходят два действия.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-115">When you drop the field into the first column, two things happen.</span></span> <span data-ttu-id="1fc7b-116">Во-первых, в ячейке данных отображается в квадратных скобках имя поля, называемое *выражением поля*: `[Date]`.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-116">First, the data cell will display the field name, known as the *field expression*, in brackets: `[Date]`.</span></span> <span data-ttu-id="1fc7b-117">Во-вторых, заголовок столбца автоматически добавляется в строку заголовка непосредственно над выражением поля.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-117">Second, a column header value is automatically added to Header row, just above the field expression.</span></span> <span data-ttu-id="1fc7b-118">По умолчанию заголовком столбца становится имя поля.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-118">By default, the column is the name of the field.</span></span> <span data-ttu-id="1fc7b-119">Текст строки заголовка можно выделить и ввести новое имя.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-119">You can select the Header row text and type a new name.</span></span>  
  
4.  <span data-ttu-id="1fc7b-120">Перетащите поле Order с панели **Данные отчета** во второй столбец таблицы.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-120">Drag the Order field from the **Report Data** pane to the second column in the table.</span></span>  
  
5.  <span data-ttu-id="1fc7b-121">Перетащите поле Product с панели **Данные отчета** в третий столбец таблицы.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-121">Drag the Product field from the **Report Data** pane to the third column in the table.</span></span>  
  
6.  <span data-ttu-id="1fc7b-122">Перетаскивайте поле «Qty» в правый край третьего столбца, пока не возникнет вертикальный курсор и на указателе мыши не появится знак «плюс» [+].</span><span class="sxs-lookup"><span data-stu-id="1fc7b-122">Drag the Qty field to the right edge of the third column until you get a vertical cursor and the mouse pointer has a plus sign [+].</span></span> <span data-ttu-id="1fc7b-123">После отпускания кнопки мыши для `[Qty]`создается четвертый столбец.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-123">When you release the mouse button, a fourth column is created for `[Qty]`.</span></span>  
  
7.  <span data-ttu-id="1fc7b-124">Добавьте поле «LineTotal» тем же способом, создав пятый столбец.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-124">Add the LineTotal field in the same way, creating a fifth column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fc7b-125">Заголовок столбца «Линейный итог».</span><span class="sxs-lookup"><span data-stu-id="1fc7b-125">The column header is Line Total.</span></span> <span data-ttu-id="1fc7b-126">Конструктор отчетов автоматически создает понятное имя для столбца, разбивая LineTotal на два слова.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-126">Report Designer automatically creates a friendly name for the column by splitting LineTotal into two words.</span></span>  
  
     <span data-ttu-id="1fc7b-127">На приведенной ниже диаграмме показана табличная область данных с заполненными полями "Дата", "Заказ", "Продукт", "Количество" и "Линейный итог".</span><span class="sxs-lookup"><span data-stu-id="1fc7b-127">The following diagram shows a table data region that has been populated with these fields: Date, Order, Product, Qty, and Line Total.</span></span>  
  
     <span data-ttu-id="1fc7b-128">![Конструктор, таблица со строкой заголовка и строкой детализации](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Конструктор, таблица со строкой заголовка и строкой детализации")</span><span class="sxs-lookup"><span data-stu-id="1fc7b-128">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
## <a name="preview-your-report"></a><span data-ttu-id="1fc7b-129">Просмотр отчета</span><span class="sxs-lookup"><span data-stu-id="1fc7b-129">Preview Your Report</span></span>  
 <span data-ttu-id="1fc7b-130">Предварительный просмотр отчета позволяет просматривать подготовленный отчет без его предварительной публикации на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-130">Previewing a report enables you to view the rendered report without having to first publish it to a report server.</span></span> <span data-ttu-id="1fc7b-131">Во время разработки потребуется часто просматривать отчет.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-131">You will probably want to preview your report frequently during design time.</span></span> <span data-ttu-id="1fc7b-132">При просмотре отчета также выполняется проверка конструкции и подключений к данным, что позволяет исправить ошибки и проблемы перед публикацией отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-132">Previewing the report will also run validation on the design and data connections so you can correct errors and issues before publishing the report to a report server.</span></span>  
  
#### <a name="to-preview-a-report"></a><span data-ttu-id="1fc7b-133">Предварительный просмотр отчета</span><span class="sxs-lookup"><span data-stu-id="1fc7b-133">To preview a report</span></span>  
  
-   <span data-ttu-id="1fc7b-134">Перейдите на вкладку **Предварительный просмотр** . конструктор отчетов запускает отчет и отображает его в представлении предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-134">Click the **Preview** tab. Report Designer runs the report and displays it in Preview view.</span></span>  
  
     <span data-ttu-id="1fc7b-135">Следующая диаграмма показывает часть отчета в представлении предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-135">The following diagram shows part of the report in Preview view.</span></span>  
  
     <span data-ttu-id="1fc7b-136">![Просмотр, строки детализации таблицы с 5 столбцами](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Просмотр, строки детализации таблицы с 5 столбцами")</span><span class="sxs-lookup"><span data-stu-id="1fc7b-136">![Preview, Detail rows of table with 5 columns](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Preview, Detail rows of table with 5 columns")</span></span>  
  
     <span data-ttu-id="1fc7b-137">Обратите внимание, что валюта (в столбце Line Total) имеет шесть знаков после запятой, а дата содержит отметку времени.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-137">Notice that the currency (in the Line Total column) has six places after the decimal, and the date has includes a time stamp.</span></span> <span data-ttu-id="1fc7b-138">Данное форматирование будет исправлено в следующем занятии.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-138">You're going to fix that formatting in the next lesson.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1fc7b-139">Чтобы сохранить отчет, в меню **Файл** выберите команду **Сохранить все** .</span><span class="sxs-lookup"><span data-stu-id="1fc7b-139">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1fc7b-140">Next Steps</span><span class="sxs-lookup"><span data-stu-id="1fc7b-140">Next Steps</span></span>  
 <span data-ttu-id="1fc7b-141">Табличная область данных успешно добавлена в отчет, поля добавлены в область данных и отчет просмотрен.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-141">You have successfully added a Table data region to your report, added fields to the data region, and previewed your report.</span></span> <span data-ttu-id="1fc7b-142">Далее форматируются заголовки столбцов и значения даты и валюты.</span><span class="sxs-lookup"><span data-stu-id="1fc7b-142">Next, you will format column headers and date and currency values.</span></span> <span data-ttu-id="1fc7b-143">См. [Занятие 5. Форматирование отчета (службы Reporting Services)](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="1fc7b-143">See [Lesson 5: Formatting a Report &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc7b-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="1fc7b-144">See Also</span></span>  
 <span data-ttu-id="1fc7b-145">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1fc7b-145">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1fc7b-146">Коллекция полей набора данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="1fc7b-146">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
  
  
