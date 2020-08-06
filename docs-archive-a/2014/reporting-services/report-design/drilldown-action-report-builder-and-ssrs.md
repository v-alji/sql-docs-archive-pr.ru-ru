---
title: Функция Drilldown (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10249"
- "10186"
- sql12.rtp.rptdesigner.calculatedseriesproperties.visibility.f1
- sql12.rtp.rptdesigner.seriesproperties.visibility.f1
- sql12.rtp.rptdesigner.chartareaproperties.visibility.f1
- "10092"
- sql12.rtp.rptdesigner.textboxproperties.visibility.f1
- sql12.rtp.rptdesigner.charttitleproperties.visibility.f1
- "10167"
- sql12.rtp.rptdesigner.rectangleproperties.visibility.f1
- "10174"
- sql12.rtp.rptdesigner.majorgridlineproperties.visibility.f1
- "10155"
- "10123"
- sql12.rtp.rptdesigner.subreportproperties.visibility.f1
- "10425"
- sql12.rtp.rptdesigner.minorgridlineproperties.visibility.f1
- "10217"
- sql12.rtp.rptdesigner.axisproperties.visibility.f1
- sql12.rtp.rptdesigner.serieslabelproperties.visibility.f1
- "10161"
- sql12.rtp.rptdesigner.chartproperties.visibility.f1
- sql12.rtp.rptdesigner.legendproperties.visibility.f1
- sql12.rtp.rptdesigner.pictureproperties.visibility.f1
- "10215"
- "10258"
- "10144"
- "10062"
- "10053"
ms.assetid: 1f8d1ef2-0daf-40c6-9ba7-3b391249bcd4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fe3d55dc70a606df759c049b7b147820f0e3110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667575"
---
# <a name="drilldown-action-report-builder-and-ssrs"></a><span data-ttu-id="a3eea-102">Действие детализации (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a3eea-102">Drilldown Action (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a3eea-103">Размещение значков плюса и минуса в текстовом поле позволяет пользователям интерактивно скрывать и отображать элементы.</span><span class="sxs-lookup"><span data-stu-id="a3eea-103">B providing plus and minus icons on a text box, you can enable users to hide and display items interactively.</span></span> <span data-ttu-id="a3eea-104">Это действие называется *углубленной детализацией* .</span><span class="sxs-lookup"><span data-stu-id="a3eea-104">This is called a *drilldown* action.</span></span> <span data-ttu-id="a3eea-105">Для таблицы или матрицы можно показывать или скрывать статические строки и столбцы или строки и столбцы, связанные с группами.</span><span class="sxs-lookup"><span data-stu-id="a3eea-105">For a table or matrix, you can show or hide static rows and columns, or rows and columns that are associated with groups.</span></span>  
  
 <span data-ttu-id="a3eea-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span><span class="sxs-lookup"><span data-stu-id="a3eea-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span></span>  
  
 <span data-ttu-id="a3eea-107">На этом рисунке пользователь щелкает в отчете значок плюса (+), чтобы отобразить подробные данные.</span><span class="sxs-lookup"><span data-stu-id="a3eea-107">In this illustration, the user clicks the plus signs (+) in the report to show detail data.</span></span>  
  
 <span data-ttu-id="a3eea-108">Например, можно первоначально скрыть все строки, за исключением строки итогов внешней группы для таблицы с группами строк.</span><span class="sxs-lookup"><span data-stu-id="a3eea-108">For example, you can initially hide all the rows except the outer group summary row for a table with row groups.</span></span> <span data-ttu-id="a3eea-109">Для каждой внутренней группы (включая группу подробностей) следует добавить переключатель в ячейку группирования объемлющей группы.</span><span class="sxs-lookup"><span data-stu-id="a3eea-109">For each inner group (including the details group), add an expand/collapse icon to the grouping cell of the containing group.</span></span> <span data-ttu-id="a3eea-110">После подготовки отчета к просмотру пользователь может щелкать текстовое поле, чтобы раскрыть или свернуть подробные данные.</span><span class="sxs-lookup"><span data-stu-id="a3eea-110">When the report is rendered, the user can click the text box to expand and collapse the detail data.</span></span> <span data-ttu-id="a3eea-111">Дополнительные сведения см. в разделе [Таблицы (построитель отчетов и службы SSRS)](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a3eea-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a3eea-112">Чтобы разрешить пользователям разворачивать и сворачивать элемент, необходимо задать свойства видимости для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="a3eea-112">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3eea-113">При создании отчета с действием углубленной детализации сведения о видимости должны быть заданы для группы, столбца или строки, которые требуется скрыть, а не просто для отдельного текстового поля в строке или столбце.</span><span class="sxs-lookup"><span data-stu-id="a3eea-113">When you create a report with a drilldown action, the visibility information must be set on the group, column, or row that you want to hide, not just a single text box in the row or column.</span></span> <span data-ttu-id="a3eea-114">Кроме того, текстовое поле, используемое для переключателя, должно находиться в области, где расположен элемент, предназначенный для показа или скрытия.</span><span class="sxs-lookup"><span data-stu-id="a3eea-114">In addition, the text box that you use for the toggle must be in a containing scope that controls the item that you want to show or hide.</span></span>  
>   
>  <span data-ttu-id="a3eea-115">Например, чтобы скрыть строку, связанную с вложенной группой, текстовое поле должно находиться в строке, связанной с родительской группой или группой, находящейся выше в иерархии контейнеров.</span><span class="sxs-lookup"><span data-stu-id="a3eea-115">For example, to hide a row associated with a nested group, the text box must be in a row associated with the parent group or higher in the containment hierarchy.</span></span>  
>   
>  <span data-ttu-id="a3eea-116">Сведения о задании сведений о видимости параметров для группы, столбца или строки см. в разделе [Добавление действия "Развернуть" или "Свернуть" к элементу (построитель отчетов и службы SSRS)](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a3eea-116">For information on setting visibility information on the group, column or row, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="a3eea-117">Дополнительные сведения о скрытии элементов отчета см. в разделе [Скрытие элемента (построитель отчетов и службы SSRS)](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a3eea-117">For more information about hiding report items, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="comparing-drilldown-and-drillthrough-reports"></a><span data-ttu-id="a3eea-118">Сравнение детализированных отчетов и отчетов с углубленной детализацией</span><span class="sxs-lookup"><span data-stu-id="a3eea-118">Comparing Drilldown and Drillthrough Reports</span></span>  
 <span data-ttu-id="a3eea-119">В отчете с углубленной детализацией пользователь раскрывает или сворачивает раздел отчета для отображения подробных данных с помощью кнопки «плюс» или «минус».</span><span class="sxs-lookup"><span data-stu-id="a3eea-119">In a drilldown report, a user clicks a plus or minus button to expand or collapse a section of a report to show detail data in place.</span></span> <span data-ttu-id="a3eea-120">В детализированном отчете пользователь переходит по ссылке к сводному значению, при этом открывается отдельный, связанный отчет для отображения подробных данных.</span><span class="sxs-lookup"><span data-stu-id="a3eea-120">In a drillthrough report, the user clicks a link for a summary value, and this opens a separate, related report to show detail data.</span></span> <span data-ttu-id="a3eea-121">Получение подробных данных происходит только при запуске подробного отчета.</span><span class="sxs-lookup"><span data-stu-id="a3eea-121">The detail data is only retrieved when the detail report runs.</span></span> <span data-ttu-id="a3eea-122">Детализированные отчеты обычно требуют меньше ресурсов, чем отчеты с углубленной детализацией.</span><span class="sxs-lookup"><span data-stu-id="a3eea-122">Drillthrough reports typically require fewer resources than drilldown reports.</span></span> <span data-ttu-id="a3eea-123">Дополнительные сведения см. в разделе [Детализация, углубленная детализация, вложенные отчеты и вложенные области данных (построитель отчетов и службы SSRS)](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span><span class="sxs-lookup"><span data-stu-id="a3eea-123">For more information, see [Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span></span>  
  
## <a name="rendering-extension-support-for-hidden-report-items"></a><span data-ttu-id="a3eea-124">Поддержка скрытых элементов отчета модулями подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="a3eea-124">Rendering Extension Support for Hidden Report Items</span></span>  
 <span data-ttu-id="a3eea-125">Переключение «скрыть-показать» для элементов отчета поддерживается только модулями подготовки отчетов, обеспечивающими интерактивное взаимодействие с пользователем, например модулем подготовки отчетов в формате HTML, который используется при создании отчета, например, в построителе или диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="a3eea-125">The show-and-hide toggle on report items is supported only by rendering extensions that support user interactivity, such as the HTML rendering extension that is used when you run a report in Report Builder and in Report Manager, for example.</span></span> <span data-ttu-id="a3eea-126">Другие модули подготовки отчетов отображают скрытые элементы.</span><span class="sxs-lookup"><span data-stu-id="a3eea-126">Other rendering extensions display hidden items.</span></span> <span data-ttu-id="a3eea-127">В следующем списке описана поддержка элементов отчета с условной видимостью:</span><span class="sxs-lookup"><span data-stu-id="a3eea-127">The following list describes support for report items with conditional visibility:</span></span>  
  
-   <span data-ttu-id="a3eea-128">В модуле подготовки HTML скрытые элементы не видны в источнике HTML.</span><span class="sxs-lookup"><span data-stu-id="a3eea-128">In HTML, if items are hidden, they are not visible in the HTML source.</span></span>  
  
-   <span data-ttu-id="a3eea-129">Модули подготовки отчетов в формате XML отображают все элементы отчета, вне зависимости от того, являются ли они скрытыми.</span><span class="sxs-lookup"><span data-stu-id="a3eea-129">The XML rendering extension displays all report items, regardless of whether they are hidden.</span></span>  
  
-   <span data-ttu-id="a3eea-130">Модуль подготовки отчетов в формате Excel отображает и развертывает скрытые строки и столбцы таблицы, матрицы или списка.</span><span class="sxs-lookup"><span data-stu-id="a3eea-130">The Excel rendering extension displays and expands hidden rows and columns for a table, matrix, or list.</span></span> <span data-ttu-id="a3eea-131">Все строки и столбцы являются видимыми.</span><span class="sxs-lookup"><span data-stu-id="a3eea-131">All rows and columns are visible.</span></span>  
  
 <span data-ttu-id="a3eea-132">Дополнительные сведения см. в разделе [Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a3eea-132">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3eea-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="a3eea-133">See Also</span></span>  
 <span data-ttu-id="a3eea-134">[Детализация, углубленная детализация, вложенные отчеты и вложенные области данных (построитель отчетов и службы SSRS)](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span><span class="sxs-lookup"><span data-stu-id="a3eea-134">[Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span></span>  
 <span data-ttu-id="a3eea-135">[Интерактивная сортировка, схемы документов и ссылки (построитель отчетов и службы SSRS)](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3eea-135">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a3eea-136">Примеры выражений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a3eea-136">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
