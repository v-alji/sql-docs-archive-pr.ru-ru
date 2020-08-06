---
title: Отображение заголовков строк и столбцов на нескольких страницах (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2422b1e2-822f-4379-9d7f-9afebb350e3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e3b38aa0faab267a0cd71feafe600829237b55c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736090"
---
# <a name="display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs"></a><span data-ttu-id="8dee2-102">Отображение заголовков строк и столбцов на нескольких страницах (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8dee2-102">Display Row and Column Headers on Multiple Pages (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8dee2-103">Пользователь может указать, следует ли повторять заголовки строк и столбцов на каждой странице области данных табликса, которая занимает несколько страниц.</span><span class="sxs-lookup"><span data-stu-id="8dee2-103">You can control whether to repeat row and column headers on every page for a tablix data region that spans multiple pages.</span></span> <span data-ttu-id="8dee2-104">Областью данных табликса может быть таблица, матрица или список.</span><span class="sxs-lookup"><span data-stu-id="8dee2-104">A tablix data region can be a table, matrix, or list.</span></span>  
  
 <span data-ttu-id="8dee2-105">Управление строками и столбцами зависит от того, имеет ли область данных табликса заголовки групп.</span><span class="sxs-lookup"><span data-stu-id="8dee2-105">How you control the rows and columns depends on whether the tablix data region has group headers.</span></span> <span data-ttu-id="8dee2-106">Если щелкнуть область данных табликса, имеющую заголовки групп, пунктирная линия отобразит области табликса, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="8dee2-106">When you click in a tablix data region that has group headers, a dotted line shows the tablix areas, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="8dee2-107">![Области данных табликса](../media/rs-tablixareas.gif "Области данных табликса")</span><span class="sxs-lookup"><span data-stu-id="8dee2-107">![Tablix data region areas](../media/rs-tablixareas.gif "Tablix data region areas")</span></span>  
  
 <span data-ttu-id="8dee2-108">Заголовки групп строк и столбцов создаются автоматически во время добавления групп с помощью мастера создания таблицы или матрицы, мастера создания диаграммы, путем добавления полей на панель группирования или с помощью контекстных меню.</span><span class="sxs-lookup"><span data-stu-id="8dee2-108">Row and column group headers are created automatically when you add groups by using the New Table or Matrix wizard or the New Chart wizard, by adding fields to the Grouping pane, or by using context menus.</span></span> <span data-ttu-id="8dee2-109">Если область данных табликса содержит только область текста табликса и не содержит заголовков групп, строки и столбцы являются элементами табликса.</span><span class="sxs-lookup"><span data-stu-id="8dee2-109">If the tablix data region has only a tablix body area and no group headers, the rows and columns are tablix members.</span></span>  
  
 <span data-ttu-id="8dee2-110">Для статических элементов можно отобразить строки, прилегающие к верхней части или столбцы, прилегающие к боковой части, на нескольких страниц.</span><span class="sxs-lookup"><span data-stu-id="8dee2-110">For static members, you can display the top adjacent rows or the side adjacent columns on multiple pages.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-row-headers-on-multiple-pages"></a><span data-ttu-id="8dee2-111">Отображение заголовков строк на нескольких страницах</span><span class="sxs-lookup"><span data-stu-id="8dee2-111">To display row headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="8dee2-112">Щелкните правой кнопкой мыши маркер строки или столбца либо угловой маркер области данных табликса, а затем выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="8dee2-112">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="8dee2-113">В разделе **Заголовки строк**выберите пункт **Повторять строки заголовка на каждой странице**.</span><span class="sxs-lookup"><span data-stu-id="8dee2-113">In **Row Headers**, select **Repeat header rows on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-column-headers-on-multiple-pages"></a><span data-ttu-id="8dee2-114">Отображение заголовков столбцов на нескольких страницах</span><span class="sxs-lookup"><span data-stu-id="8dee2-114">To display column headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="8dee2-115">Щелкните правой кнопкой мыши маркер строки или столбца либо угловой маркер области данных табликса, а затем выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="8dee2-115">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="8dee2-116">В разделе **Заголовки столбцов**выберите пункт **Повторять столбцы заголовка на каждой странице**.</span><span class="sxs-lookup"><span data-stu-id="8dee2-116">In **Column Headers**, select **Repeat header columns on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-a-static-tablix-member-row-or-column-on-multiple-pages"></a><span data-ttu-id="8dee2-117">Отображение статического элемента табликса (строки или столбца) на множестве страниц</span><span class="sxs-lookup"><span data-stu-id="8dee2-117">To display a static tablix member (row or column) on multiple pages</span></span>  
  
1.  <span data-ttu-id="8dee2-118">В области конструктора щелкните маркер строки или столбца области данных табликса, чтобы выделить этот дескриптор.</span><span class="sxs-lookup"><span data-stu-id="8dee2-118">On the design surface, click the row or column handle of the tablix data region to select it.</span></span> <span data-ttu-id="8dee2-119">На панели группирования будут отображены группы столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="8dee2-119">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="8dee2-120">На правой стороне панели группирования щелкните стрелку вниз и нажмите кнопку **Расширенный режим**.</span><span class="sxs-lookup"><span data-stu-id="8dee2-120">On the right side of the Grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span> <span data-ttu-id="8dee2-121">В панели «Группы строк» отображаются иерархические статические и динамические члены для иерархии групп строк, а в панели «Группы столбцов» аналогично отображается иерархия групп столбцов.</span><span class="sxs-lookup"><span data-stu-id="8dee2-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
3.  <span data-ttu-id="8dee2-122">Щелкните статический элемент, соответствующий статическому элементу (строке или столбцу), который необходимо оставить видимым во время прокрутки.</span><span class="sxs-lookup"><span data-stu-id="8dee2-122">Click the static member that corresponds to the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="8dee2-123">В панели «Свойства» отображаются свойства **Элемент табликса** .</span><span class="sxs-lookup"><span data-stu-id="8dee2-123">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="8dee2-124">Если панель свойств не отображается, перейдите на вкладку **Вид** в верхней части окна построителя отчетов и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8dee2-124">If you don't see the Properties pane, click the **View** tab at the top of the Report Builder window and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8dee2-125">В панели «Свойства» присвойте параметру **RepeatOnNewPage** значение True.</span><span class="sxs-lookup"><span data-stu-id="8dee2-125">In the Properties pane, set **RepeatOnNewPage** to True.</span></span>  
  
5.  <span data-ttu-id="8dee2-126">Задайте для поля **KeepWithGroup** значение «После».</span><span class="sxs-lookup"><span data-stu-id="8dee2-126">Set **KeepWithGroup** to After.</span></span>  
  
6.  <span data-ttu-id="8dee2-127">Повторите эту процедуру для всех элементов, которые нужно повторить.</span><span class="sxs-lookup"><span data-stu-id="8dee2-127">Repeat this for as many adjacent members as you want to repeat.</span></span>  
  
7.  <span data-ttu-id="8dee2-128">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="8dee2-128">Preview the report.</span></span>  
  
 <span data-ttu-id="8dee2-129">При просмотре страницы отчета, которую занимает область данных табликса, статические элементы табликса повторяются на каждой странице.</span><span class="sxs-lookup"><span data-stu-id="8dee2-129">As you view each page of the report that the tablix data region spans, the static tablix members repeat on each page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dee2-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="8dee2-130">See Also</span></span>  
 <span data-ttu-id="8dee2-131">[Поиск, просмотр отчетов и управление ими (построитель отчетов и службы SSRS)](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8dee2-131">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8dee2-132">[Экспорт отчетов &#40;построитель отчетов и SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8dee2-132">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8dee2-133">[Управление разрывами страниц, заголовками, столбцами и строками (построитель отчетов и службы SSRS)](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8dee2-133">[Controlling Page Breaks, Headings, Columns, and Rows &#40;Report Builder and SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8dee2-134">[Отображение верхних и нижних колонтитулов в группе (построитель отчетов и службы SSRS)](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8dee2-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8dee2-135">Сохранение заголовков видимыми при прокрутке отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8dee2-135">Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;</span></span>](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)  
  
  
