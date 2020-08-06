---
title: Сохранение заголовков видимыми при прокрутке отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6d9192a4-fd5c-41ad-b9ef-f88f9496afed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d37fcd38a402dc0f88ac002c679c1046d5b0b583
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739281"
---
# <a name="keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs"></a><span data-ttu-id="773e2-102">Сохранение заголовков видимыми при прокрутке отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="773e2-102">Keep Headers Visible When Scrolling Through a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="773e2-103">Чтобы предотвратить исчезновение заголовков строк и столбцов из поля видимости при прокрутке после подготовки отчета к просмотру, можно закрепить заголовок строки или столбца.</span><span class="sxs-lookup"><span data-stu-id="773e2-103">To prevent row and column labels from scrolling out of view after rendering a report, you can freeze the row or column headings.</span></span>  
  
 <span data-ttu-id="773e2-104">Способ управления строками и столбцами зависит от того, используется ли таблица или матрица.</span><span class="sxs-lookup"><span data-stu-id="773e2-104">How you control the rows and columns depends on whether you have a table or a matrix.</span></span> <span data-ttu-id="773e2-105">Если имеется таблица, то в качестве видимых настраиваются статические элементы (заголовки строк и столбцов).</span><span class="sxs-lookup"><span data-stu-id="773e2-105">If you have a table, you configure static members (row and column headings) to remain visible.</span></span> <span data-ttu-id="773e2-106">Если же имеется матрица, то в качестве видимых настраиваются заголовки групп строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="773e2-106">If you have a matrix, you configure row and column group headers to remain visible.</span></span>  
  
 <span data-ttu-id="773e2-107">Если вы экспортируете отчет в Excel, заголовок не будет автоматически зафиксирован.</span><span class="sxs-lookup"><span data-stu-id="773e2-107">If you export the report to Excel, the header will not be frozen automatically.</span></span> <span data-ttu-id="773e2-108">Вы можете зафиксировать вкладку в Excel.</span><span class="sxs-lookup"><span data-stu-id="773e2-108">You can freeze the pane in Excel.</span></span> <span data-ttu-id="773e2-109">Дополнительные сведения см. в подразделе **Верхние и нижние колонтитулы страницы** раздела [Экспорт в Microsoft Excel (построитель отчетов и службы SSRS)](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="773e2-109">For more information see the **Page Headers and Footers** section of [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="773e2-110">Даже если в таблице есть группы строк и столбцов, сохранить видимость этих заголовков групп при прокрутке нельзя.</span><span class="sxs-lookup"><span data-stu-id="773e2-110">Even if a table has row and column groups, you cannot keep those group headers visible while scrolling</span></span>  
  
 <span data-ttu-id="773e2-111">На следующем рисунке показана таблица.</span><span class="sxs-lookup"><span data-stu-id="773e2-111">The following image shows a table.</span></span>  
  
 <span data-ttu-id="773e2-112">![Таблица](../media/table.png "Таблица")</span><span class="sxs-lookup"><span data-stu-id="773e2-112">![Table](../media/table.png "Table")</span></span>  
  
 <span data-ttu-id="773e2-113">На следующем рисунке показана матрица.</span><span class="sxs-lookup"><span data-stu-id="773e2-113">The following image shows a matrix.</span></span>  
  
 <span data-ttu-id="773e2-114">![Матрица](../media/matrix.png "Матрица")</span><span class="sxs-lookup"><span data-stu-id="773e2-114">![Matrix](../media/matrix.png "Matrix")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-keep-matrix-group-headers-visible-while-scrolling"></a><span data-ttu-id="773e2-115">Сохранение заголовков групп матрицы видимыми при прокрутке</span><span class="sxs-lookup"><span data-stu-id="773e2-115">To keep matrix group headers visible while scrolling</span></span>  
  
1.  <span data-ttu-id="773e2-116">Щелкните правой кнопкой мыши маркер строки или столбца либо угловой маркер области данных табликса, а затем выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="773e2-116">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="773e2-117">На вкладке **Общие** в области **Заголовки строк** или **Заголовки столбцов**установите флажок **Всегда отображать заголовок**.</span><span class="sxs-lookup"><span data-stu-id="773e2-117">On the **General** tab, under **Row Headers** or **Column Headers**, select **Header should remain visible while scrolling**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-keep-a-static-tablix-member-row-or-column-visible-while-scrolling"></a><span data-ttu-id="773e2-118">Сохранение статического элемента табликса (строки или столбца) видимым при прокрутке</span><span class="sxs-lookup"><span data-stu-id="773e2-118">To keep a static tablix member (row or column) visible while scrolling</span></span>  
  
1.  <span data-ttu-id="773e2-119">В области конструктора щелкните в любом месте таблицы, чтобы открыть статические элементы и группы на панели группирования.</span><span class="sxs-lookup"><span data-stu-id="773e2-119">On the design surface, click anywhere in the table to display static members, as well as groups, in the grouping pane.</span></span>  
  
     <span data-ttu-id="773e2-120">![Панель группировки](../media/grouppane-updated.png "Панель группировки")</span><span class="sxs-lookup"><span data-stu-id="773e2-120">![Grouping pane](../media/grouppane-updated.png "Grouping pane")</span></span>  
  
     <span data-ttu-id="773e2-121">На панели «Группы строк» отображаются иерархические статические и динамические элементы иерархии групп строк, а на панели «Группы столбцов» аналогично отображается иерархия групп столбцов.</span><span class="sxs-lookup"><span data-stu-id="773e2-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy, and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
2.  <span data-ttu-id="773e2-122">В правой части панели группирования щелкните стрелку вниз и нажмите кнопку **Расширенный режим**.</span><span class="sxs-lookup"><span data-stu-id="773e2-122">On the right side of the grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span>  
  
3.  <span data-ttu-id="773e2-123">Щелкните статический член (строку или столбец), который нужно оставить видимым при прокрутке.</span><span class="sxs-lookup"><span data-stu-id="773e2-123">Click the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="773e2-124">В панели «Свойства» отображаются свойства **Элемент табликса** .</span><span class="sxs-lookup"><span data-stu-id="773e2-124">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="773e2-125">![Свойства элемента табликса](../media/grouppane-tablixmember-updated.png "Свойства элемента табликса")</span><span class="sxs-lookup"><span data-stu-id="773e2-125">![Tablix Member properties](../media/grouppane-tablixmember-updated.png "Tablix Member properties")</span></span>  
  
4.  <span data-ttu-id="773e2-126">В области Свойства задайте для параметра **фикседдата** значение `True` .</span><span class="sxs-lookup"><span data-stu-id="773e2-126">In the Properties pane, set **FixedData** to `True`.</span></span>  
  
5.  <span data-ttu-id="773e2-127">Повторите это действие для всех смежных членов, для которых должна сохраняться видимость при прокрутке.</span><span class="sxs-lookup"><span data-stu-id="773e2-127">Repeat this for as many adjacent members as you want to keep visible while scrolling.</span></span>  
  
6.  <span data-ttu-id="773e2-128">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="773e2-128">Preview the report.</span></span>  
  
 <span data-ttu-id="773e2-129">При переходе на страницу вниз или по отчету статические элементы табликса остаются в поле зрения.</span><span class="sxs-lookup"><span data-stu-id="773e2-129">As you page down or across the report, the static tablix members remain in view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="773e2-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="773e2-130">See Also</span></span>  
 <span data-ttu-id="773e2-131">[Область данных табликса (построитель отчетов и службы SSRS)](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="773e2-131">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="773e2-132">[Поиск, просмотр отчетов и управление ими (построитель отчетов и службы SSRS)](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="773e2-132">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="773e2-133">[Экспорт отчетов &#40;построитель отчетов и SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="773e2-133">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="773e2-134">[Отображение верхних и нижних колонтитулов в группе (построитель отчетов и службы SSRS)](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="773e2-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="773e2-135">[Отображение заголовков строк и столбцов на нескольких страницах (построитель отчетов и службы SSRS)](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="773e2-135">[Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="773e2-136">Панель группировки (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="773e2-136">Grouping Pane &#40;Report Builder&#41;</span></span>](grouping-pane-report-builder.md)  
  
  
