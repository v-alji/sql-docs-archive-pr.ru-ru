---
title: Добавление в отчет закладки (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f130562e-5673-40e3-8e01-de7227a21d41
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fae543dd1b071ff38853637a3da57ffd2410c3a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739377"
---
# <a name="add-a-bookmark-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="8dd6c-102">Добавление в отчет закладки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8dd6c-102">Add a Bookmark to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8dd6c-103">Закладки и ссылки на закладки следует добавлять в отчет, если необходимо создать пользовательское оглавление или внутренние ссылки для навигации по отчету.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-103">Add bookmarks and bookmark links to a report when you want to provide a customized table of contents or to provide customized internal navigation links in the report.</span></span> <span data-ttu-id="8dd6c-104">Обычно закладки создаются в тех местах отчета, к которым следует направить пользователей, например к таблицам или графикам, либо к уникальным групповым значениям, отображаемым в таблице или матрице.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-104">Typically, you add bookmarks to locations in the report to which you want to direct users, such as to each table or chart or to the unique group values displayed in a table or matrix.</span></span> <span data-ttu-id="8dd6c-105">Можно создать собственные строки и использовать их в качестве закладок, либо, при работе с группами, можно установить закладку на выражение группы.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-105">You can create your own strings to use as bookmarks, or, for groups, you can set the bookmark to the group expression.</span></span>  
  
 <span data-ttu-id="8dd6c-106">После создания закладок можно создать элементы отчета, щелкнув по которым пользователи смогут перейти к закладкам.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-106">After you create bookmarks, you can add report items that the user can click to go to each bookmark.</span></span> <span data-ttu-id="8dd6c-107">Обычно такими элементами являются текстовые поля или изображения.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-107">These items are typically text boxes or images.</span></span>  
  
 <span data-ttu-id="8dd6c-108">Например, если в отчете отображается таблица с группировкой по цветам, то можно добавить в заголовок группы закладку, основанную на выражении группы.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-108">For example, if your report displays a table grouped by color, you would add a bookmark based on the group expression to the group header.</span></span> <span data-ttu-id="8dd6c-109">Затем в начало отчета, отображающего значения цвета, добавляется таблица с одним текстовым полем, на которое устанавливается закладка.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-109">Then you would add a table with a single text box at the beginning of the report that displayed the color values, and set the bookmark link on that text box.</span></span> <span data-ttu-id="8dd6c-110">При щелчке этого цвета в отчете выполняется переход к странице, на которой отображается строка заголовка группы данного цвета.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-110">When you click the color, the report jumps to the page that displays the group header row for that color.</span></span>  
  
 <span data-ttu-id="8dd6c-111">Закладку можно добавить к любому элементу отчета; ссылку на закладку можно добавить к любому элементу, имеющему свойство **Action** , например текстовому полю, изображению или вычисляемому ряду в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-111">You can add a bookmark to any report item and add a bookmark link to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="8dd6c-112">Дополнительные сведения см. в разделе [Диалоговое окно "Свойства действия" (построитель отчетов и службы SSRS)](../action-properties-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8dd6c-112">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-bookmark"></a><span data-ttu-id="8dd6c-113">Добавление закладки</span><span class="sxs-lookup"><span data-stu-id="8dd6c-113">To add a bookmark</span></span>  
  
1.  <span data-ttu-id="8dd6c-114">В режиме конструктора отчетов выберите текстовое поле, изображение, диаграмму или другой элемент отчета, к которому необходимо добавить закладку.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-114">In report design view, select the text box, image, chart, or other report item to which you want to add a bookmark.</span></span> <span data-ttu-id="8dd6c-115">В панели «Свойства» будут отображены свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-115">The properties for the selected item appear in the Properties pane.</span></span>  
  
2.  <span data-ttu-id="8dd6c-116">В текстовом поле рядом с **Закладкой**введите строку, являющуюся меткой для данной закладки.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-116">In the text box next to **Bookmark**, type a string that is the label for this bookmark.</span></span> <span data-ttu-id="8dd6c-117">Например, в качестве закладки для изображения в отчете можно ввести: **BikePhoto** .</span><span class="sxs-lookup"><span data-stu-id="8dd6c-117">For example, you could type **BikePhoto** as the bookmark for an image in your report.</span></span> <span data-ttu-id="8dd6c-118">Также можно щелкнуть кнопку выражения (**fx**), чтобы открыть диалоговое окно **Выражение** , и ввести выражение, результатом которого будет метка.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-118">Alternatively, click the Expression (**fx**) button to open the **Expression** dialog box to specify an expression that evaluates to a label.</span></span> <span data-ttu-id="8dd6c-119">При работе с группами следует вводить выражения группы.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-119">For a group, the expression you type should be the group expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8dd6c-120">Закладкой может быть любая строка, но она должна быть уникальной для всего отчета.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-120">The bookmark can be any string, but it must be unique in the report.</span></span> <span data-ttu-id="8dd6c-121">Если закладка не уникальна, то ссылка на закладку будет находить первую совпадающую закладку.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-121">If the bookmark is not unique, a link to the bookmark finds the first matching bookmark.</span></span>  
  
### <a name="to-add-a-bookmark-link"></a><span data-ttu-id="8dd6c-122">Добавление ссылки на закладку</span><span class="sxs-lookup"><span data-stu-id="8dd6c-122">To add a bookmark link</span></span>  
  
1.  <span data-ttu-id="8dd6c-123">В режиме конструктора щелкните правой кнопкой мыши текстовое поле, изображение или диаграмму, к которой нужно добавить ссылку, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-123">In Design view, right-click the text box, image, chart, to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8dd6c-124">В диалоговом окне **Свойства** этого элемента отчета нажмите кнопку **Действие**.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-124">In The **Properties** dialog box for that report item, click **Action**.</span></span>  
  
3.  <span data-ttu-id="8dd6c-125">Выберите **Перейти к закладке**.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-125">Select **Go to bookmark**.</span></span> <span data-ttu-id="8dd6c-126">В диалоговом окне появится дополнительная область для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-126">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="8dd6c-127">В поле **Выберите закладку** введите или выберите закладку или выражение, результатом которого является закладка.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-127">In the **Select bookmark** box, type or select a bookmark or an expression that evaluates to a bookmark.</span></span> <span data-ttu-id="8dd6c-128">Используя предыдущий пример, введите **BikePhoto** , чтобы создать ссылку на изображение в вашем отчете.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-128">Using the previous example, type **BikePhoto** to create a link to the image in your report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8dd6c-129">(Необязательно) Автоматическое форматирование текста в ссылку не производится.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-129">(Optional) The text is not automatically formatted like a link.</span></span> <span data-ttu-id="8dd6c-130">Если ссылка установлена в тексте, будет полезно изменить цвет и стиль текста, чтобы показать, что текст является ссылкой.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-130">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="8dd6c-131">Например, измените цвет на синий, а эффект на подчеркивание в разделе **Шрифт** на вкладке «Главная» ленты.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-131">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="8dd6c-132">Для проверки ссылки нажмите кнопку **Запустить** , чтобы выполнить предварительный просмотр отчета, а затем щелкните элемент отчета, для которого была задана ссылка.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-132">To test the link, click **Run** to preview the report, and then click the report item that you set this link on..</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd6c-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="8dd6c-133">See Also</span></span>  
 <span data-ttu-id="8dd6c-134">[Интерактивная сортировка, схемы документов и ссылки (построитель отчетов и службы SSRS)](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8dd6c-134">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8dd6c-135">[Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8dd6c-135">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8dd6c-136">Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8dd6c-136">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
