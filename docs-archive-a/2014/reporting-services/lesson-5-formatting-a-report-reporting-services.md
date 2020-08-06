---
title: Занятие 5. Форматирование отчета (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46efa9-6e04-48ec-afb4-5a2314dcb05a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00f0d780e957fd9ff995fefb1d033275a7da428d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668098"
---
# <a name="lesson-5-formatting-a-report-reporting-services"></a><span data-ttu-id="bb89c-102">Lesson 5: Formatting a Report (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="bb89c-102">Lesson 5: Formatting a Report (Reporting Services)</span></span>
  <span data-ttu-id="bb89c-103">После добавления области данных и нескольких полей к отчету «Заказы на продажу» можно отформатировать поля дат и валют, а затем и заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="bb89c-103">Now that you've added a data region and some fields to the Sales Orders report, you can format the date and currency fields and the column headers.</span></span>  
  
 <span data-ttu-id="bb89c-104">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="bb89c-104">In this topic:</span></span>  
  
-   [<span data-ttu-id="bb89c-105">Форматирование даты</span><span class="sxs-lookup"><span data-stu-id="bb89c-105">Format the Date</span></span>](#bkmk_format_date)  
  
-   [<span data-ttu-id="bb89c-106">Форматирование валюты</span><span class="sxs-lookup"><span data-stu-id="bb89c-106">Format the Currency</span></span>](#bkmk_format_currency)  
  
-   [<span data-ttu-id="bb89c-107">Изменение стиля текста и ширины столбцов</span><span class="sxs-lookup"><span data-stu-id="bb89c-107">Change Text Style and Column Widths</span></span>](#bkmk_change_textstyle)  
  
##  <a name="format-the-date"></a><a name="bkmk_format_date"></a><span data-ttu-id="bb89c-108">Форматирование даты</span><span class="sxs-lookup"><span data-stu-id="bb89c-108">Format the Date</span></span>  
 <span data-ttu-id="bb89c-109">В поле Date по умолчанию отображаются сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="bb89c-109">The Date field displays date and time information by default.</span></span> <span data-ttu-id="bb89c-110">Можно отформатировать его таким образом, чтобы отображалась только дата.</span><span class="sxs-lookup"><span data-stu-id="bb89c-110">You can format it to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field"></a><span data-ttu-id="bb89c-111">Указание форматирования для поля даты</span><span class="sxs-lookup"><span data-stu-id="bb89c-111">To format a date field</span></span>  
  
1.  <span data-ttu-id="bb89c-112">Перейдите на вкладку **Макет** .</span><span class="sxs-lookup"><span data-stu-id="bb89c-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="bb89c-113">Щелкните правой кнопкой мыши ячейку с выражением для поля `[Date]` , а затем выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="bb89c-113">Right-click the cell with the `[Date]` field expression and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="bb89c-114">Щелкните **число**, а затем в поле **Категория** выберите `Date` .</span><span class="sxs-lookup"><span data-stu-id="bb89c-114">Click **Number**, and then in the **Category** field, select `Date`.</span></span>  
  
4.  <span data-ttu-id="bb89c-115">В поле **Тип** введите **31 января 2000 года**.</span><span class="sxs-lookup"><span data-stu-id="bb89c-115">In the **Type** box, select **January 31, 2000**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="bb89c-116">Просмотрите отчеты, чтобы увидеть изменение, внесенное в поле `[Date]` , а затем вернитесь в представление конструктора.</span><span class="sxs-lookup"><span data-stu-id="bb89c-116">Preview the report to see the change to the `[Date]` field and then change back to design view.</span></span>  
  
##  <a name="format-the-currency"></a><a name="bkmk_format_currency"></a><span data-ttu-id="bb89c-117">Форматирование валюты</span><span class="sxs-lookup"><span data-stu-id="bb89c-117">Format the Currency</span></span>  
 <span data-ttu-id="bb89c-118">В поле LineTotal отображается число с общим форматом.</span><span class="sxs-lookup"><span data-stu-id="bb89c-118">The LineTotal field displays a general number.</span></span> <span data-ttu-id="bb89c-119">Отформатируйте его для представления валюты.</span><span class="sxs-lookup"><span data-stu-id="bb89c-119">Format it to display the number as currency.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="bb89c-120">Форматирование поля валюты</span><span class="sxs-lookup"><span data-stu-id="bb89c-120">To format a currency field</span></span>  
  
1.  <span data-ttu-id="bb89c-121">Щелкните правой кнопкой мыши ячейку с выражением для поля `[LineTotal]` , а затем выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="bb89c-121">Right-click the cell with the `[LineTotal]` field expression and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="bb89c-122">Щелкните **Число**и затем в поле **Категория** выберите пункт **Валюта**.</span><span class="sxs-lookup"><span data-stu-id="bb89c-122">Click **Number**, and in the **Category** field, select **Currency**.</span></span>  
  
3.  <span data-ttu-id="bb89c-123">Если региональные настройки компьютера установлены на «Английский (США)», по умолчанию должны применяться следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bb89c-123">If your regional setting is English (United States), the defaults should be:</span></span>  
  
    -   <span data-ttu-id="bb89c-124">**Десятичные разряды: 2**</span><span class="sxs-lookup"><span data-stu-id="bb89c-124">**Decimal places: 2**</span></span>  
  
    -   <span data-ttu-id="bb89c-125">**Отрицательные числа: ($12345.00)**</span><span class="sxs-lookup"><span data-stu-id="bb89c-125">**Negative numbers: ($12345.00)**</span></span>  
  
    -   <span data-ttu-id="bb89c-126">**Символ: $ English (США)**</span><span class="sxs-lookup"><span data-stu-id="bb89c-126">**Symbol: $ English (United States)**</span></span>  
  
4.  <span data-ttu-id="bb89c-127">Выберите **Использовать разделитель разрядов (пробел)**.</span><span class="sxs-lookup"><span data-stu-id="bb89c-127">Select **Use 1000 separator (,)**.</span></span>  
  
     <span data-ttu-id="bb89c-128">Если будет отображен текст:**$12 345,00**, то вы задали правильные параметры.</span><span class="sxs-lookup"><span data-stu-id="bb89c-128">If the sample text is:**$12,345.00**, then your settings are correct.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="bb89c-129">Просмотрите отчеты, чтобы увидеть изменение, внесенное в поле `[LineTotal]` , а затем вернитесь в представление конструктора.</span><span class="sxs-lookup"><span data-stu-id="bb89c-129">Preview the report to see the change to the `[LineTotal]` field and then change back to design view.</span></span>  
  
##  <a name="change-text-style-and-column-widths"></a><a name="bkmk_change_textstyle"></a><span data-ttu-id="bb89c-130">Изменение стиля текста и ширины столбцов</span><span class="sxs-lookup"><span data-stu-id="bb89c-130">Change Text Style and Column Widths</span></span>  
 <span data-ttu-id="bb89c-131">Можно также изменить форматирование заголовка строки, чтобы он отличался от строк данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="bb89c-131">You can also change the formatting of the header row to differentiate it from the rows of data in the report.</span></span> <span data-ttu-id="bb89c-132">Наконец, можно отрегулировать ширину столбцов.</span><span class="sxs-lookup"><span data-stu-id="bb89c-132">Lastly, you will adjust the widths of the columns.</span></span>  
  
#### <a name="to-format-header-rows-and-table-columns"></a><span data-ttu-id="bb89c-133">Форматирование заголовков строк и столбцов таблицы</span><span class="sxs-lookup"><span data-stu-id="bb89c-133">To format header rows and table columns</span></span>  
  
1.  <span data-ttu-id="bb89c-134">Щелкните таблицу, чтобы сбоку и сверху от нее появились маркеры строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="bb89c-134">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="bb89c-135">![Конструктор, таблица со строкой заголовка и строкой детализации](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Конструктор, таблица со строкой заголовка и строкой детализации")</span><span class="sxs-lookup"><span data-stu-id="bb89c-135">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
     <span data-ttu-id="bb89c-136">Серые линии, расположенные вдоль верха и стороны таблицы, — это маркеры столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="bb89c-136">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
2.  <span data-ttu-id="bb89c-137">Установите указатель на линии раздела между маркерами столбцов, чтобы курсор принял вид двойной стрелки.</span><span class="sxs-lookup"><span data-stu-id="bb89c-137">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="bb89c-138">Перетаскиванием установите нужный размер столбцов.</span><span class="sxs-lookup"><span data-stu-id="bb89c-138">Drag the columns to the size you want.</span></span>  
  
3.  <span data-ttu-id="bb89c-139">Выделите строку, содержащую метки заголовков столбцов, и в меню **Форматирование** выберите пункты **Шрифт** и **Полужирный**.</span><span class="sxs-lookup"><span data-stu-id="bb89c-139">Select the row containing column header labels and from the **Format** menu, point to **Font** and then click **Bold**.</span></span>  
  
4.  <span data-ttu-id="bb89c-140">Чтобы просмотреть отчет, перейдите на вкладку **Предварительный просмотр** . Он должен выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="bb89c-140">To preview your report, click the **Preview** tab. It should look something like this:</span></span>  
  
     <span data-ttu-id="bb89c-141">![Просмотр таблицы с заголовками столбцов, выделенными полужирным](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Предварительный просмотр таблицы с заголовками столбцов, выделенными полужирным")</span><span class="sxs-lookup"><span data-stu-id="bb89c-141">![Preview of table with bold column headers](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Preview of table with bold column headers")</span></span>  
  
5.  <span data-ttu-id="bb89c-142">Чтобы сохранить отчет, в меню **Файл** выберите команду **Сохранить все** .</span><span class="sxs-lookup"><span data-stu-id="bb89c-142">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bb89c-143">Next Steps</span><span class="sxs-lookup"><span data-stu-id="bb89c-143">Next Steps</span></span>  
 <span data-ttu-id="bb89c-144">Заголовки столбцов, а также значения дат и денежные значения успешно отформатированы.</span><span class="sxs-lookup"><span data-stu-id="bb89c-144">You have successfully formatted column headers and date and currency values.</span></span> <span data-ttu-id="bb89c-145">Далее предстоит добавить в этот отчет группирование и итоги.</span><span class="sxs-lookup"><span data-stu-id="bb89c-145">Next, you will add grouping and totals to your report.</span></span> <span data-ttu-id="bb89c-146">См. раздел [Занятие 6. Добавление группирования и итогов (службы Reporting Services)](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bb89c-146">See [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb89c-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb89c-147">See Also</span></span>  
 <span data-ttu-id="bb89c-148">[Форматирование чисел и дат &#40;построитель отчетов и SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb89c-148">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bb89c-149">Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="bb89c-149">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](report-design/rendering-behaviors-report-builder-and-ssrs.md)  
  
  
