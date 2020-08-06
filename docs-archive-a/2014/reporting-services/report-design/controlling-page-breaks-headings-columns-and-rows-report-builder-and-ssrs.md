---
title: Управление разрывами страниц, заголовками, столбцами и строками (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b8fa41f-a727-4f23-8efb-fd9bb0d4cd1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7dae06129ee5dc9962538e8d025dca9966325f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666428"
---
# <a name="controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs"></a><span data-ttu-id="147d5-102">Управление разрывами страниц, заголовками, столбцами и строками (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="147d5-102">Controlling Page Breaks, Headings, Columns, and Rows (Report Builder and SSRS)</span></span>
  <span data-ttu-id="147d5-103">Разрыв страницы разделяет отчет на отдельные страницы для просмотра и печати.</span><span class="sxs-lookup"><span data-stu-id="147d5-103">A page break divides a report into separate pages for viewing and printing.</span></span> <span data-ttu-id="147d5-104">Разрывы страниц определяют, как содержимое соответствует странице отчета для оптимального представления, когда выполняется предварительный просмотр отчета или экспорт в другой формат файла.</span><span class="sxs-lookup"><span data-stu-id="147d5-104">Page breaks determine how the content is fitted to a report page for optimal viewing when you preview a report or export it to a different file format.</span></span>  
  
 <span data-ttu-id="147d5-105">Добавление разрывов страниц также повышает производительность обработки крупных отчетов.</span><span class="sxs-lookup"><span data-stu-id="147d5-105">Adding page breaks also improves the performance of large reports when the are processed.</span></span> <span data-ttu-id="147d5-106">Подготовленная к просмотру страница отображается, а остальные страницы подготавливаются в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="147d5-106">A rendered page is displayed while the rest of the pages are rendered in the background.</span></span> <span data-ttu-id="147d5-107">Это позволяет начать просмотр первых страниц отчета, пока недоступны остальные.</span><span class="sxs-lookup"><span data-stu-id="147d5-107">This allows you to begin viewing the initial pages of the report while waiting for additional pages to become available.</span></span>  
  
 <span data-ttu-id="147d5-108">Можно добавлять разрывы страниц в элементы отчета, такие как таблицы, матрицы, списки, диаграммы, датчики и изображения.</span><span class="sxs-lookup"><span data-stu-id="147d5-108">Page breaks can be added to report items such as a table, matrix, list, chart, gauge, or image.</span></span> <span data-ttu-id="147d5-109">Также можно добавлять разрывы страниц в группы в составе таблицы, матрицы или списка.</span><span class="sxs-lookup"><span data-stu-id="147d5-109">You can also add page breaks to groups in a table, matrix, or list.</span></span> <span data-ttu-id="147d5-110">Разрывы страниц можно добавлять перед группами, после групп и между группами.</span><span class="sxs-lookup"><span data-stu-id="147d5-110">Page breaks can be added before, after, and between groups.</span></span> <span data-ttu-id="147d5-111">Разрывы страницы между группами по умолчанию в отчет не добавляются.</span><span class="sxs-lookup"><span data-stu-id="147d5-111">Page breaks between groups are not added to the report by default.</span></span>  
  
 <span data-ttu-id="147d5-112">Дополнительные сведения см. в разделах [Отображение заголовков строк и столбцов на нескольких страницах (построитель отчетов и службы SSRS)](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) и [Сохранение заголовков видимыми при прокрутке отчета (построитель отчетов и службы SSRS)](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="147d5-112">For more information, see [Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) and [Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="147d5-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="147d5-113">See Also</span></span>  
 <span data-ttu-id="147d5-114">[Содержит &#40;построитель отчетов и SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="147d5-114">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="147d5-115">[Управление отображением области данных табликса на странице отчетов (построитель отчетов и службы SSRS)](controlling-the-tablix-data-region-display-on-a-report-page.md) </span><span class="sxs-lookup"><span data-stu-id="147d5-115">[Controlling the Tablix Data Region Display on a Report Page &#40;Report Builder and SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span></span>  
 <span data-ttu-id="147d5-116">[Панель группировки (построитель отчетов)](grouping-pane-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="147d5-116">[Grouping Pane &#40;Report Builder&#41;](grouping-pane-report-builder.md) </span></span>  
 [<span data-ttu-id="147d5-117">Отображение верхних и нижних колонтитулов в группе (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="147d5-117">Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;</span></span>](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md)  
  
  
