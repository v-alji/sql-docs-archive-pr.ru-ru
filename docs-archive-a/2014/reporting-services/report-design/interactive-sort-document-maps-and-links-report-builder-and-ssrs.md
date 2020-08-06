---
title: Интерактивная сортировка, схемы документов и ссылки (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cc6ef408-4a76-408a-9d3f-033481fe21cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35d88e89ed14a205153374d44562e6d3fda92e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739296"
---
# <a name="interactive-sort-document-maps-and-links-report-builder-and-ssrs"></a><span data-ttu-id="d49b6-102">Интерактивная сортировка, схемы документов и ссылки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d49b6-102">Interactive Sort, Document Maps, and Links (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d49b6-103">В веб-средах можно добавлять множество функций, обеспечивающих взаимодействие пользователей с отчетами.</span><span class="sxs-lookup"><span data-stu-id="d49b6-103">In Web-based environments, you can add a number of features that let your users interact with reports.</span></span> <span data-ttu-id="d49b6-104">Пользователи могут изменять порядок сортировки значений в отчете, показывать или скрывать элементы отчета, а также щелкать ссылки для перехода к другим отчетам или веб-страницам.</span><span class="sxs-lookup"><span data-stu-id="d49b6-104">Your users can change the sort order of values in your report, show or hide items in the report, or click links that go to other reports or Web pages.</span></span> <span data-ttu-id="d49b6-105">Также можно добавить оглавление или схему документа.</span><span class="sxs-lookup"><span data-stu-id="d49b6-105">You can also add a table of contents or document map.</span></span> <span data-ttu-id="d49b6-106">Пользователи отчета могут переходить к различным областям отчета, щелкая элементы в оглавлении или схеме документа.</span><span class="sxs-lookup"><span data-stu-id="d49b6-106">Your report users can click items in the table of contents or document map to jump to areas within a report.</span></span>  
  
 <span data-ttu-id="d49b6-107">Построитель отчетов и конструктор отчетов поддерживают три типа ссылок со следующими действиями.</span><span class="sxs-lookup"><span data-stu-id="d49b6-107">Report Builder and Report Designer support three types of links with the following actions:</span></span>  
  
-   <span data-ttu-id="d49b6-108">**Ссылки на закладки** — переход к другим областям внутри отчета.</span><span class="sxs-lookup"><span data-stu-id="d49b6-108">**Bookmark links** Jump to other areas within the report.</span></span>  
  
-   <span data-ttu-id="d49b6-109">**Гиперссылки** — переход по URL-адресам веб-страниц или отчетов на сервере отчетов, используя URL-доступ.</span><span class="sxs-lookup"><span data-stu-id="d49b6-109">**Hyperlinks** Jump to URLs that specify the address of Web pages or reports on a report server by using URL access.</span></span>  
  
-   <span data-ttu-id="d49b6-110">**Ссылки на детализованные отчеты** — переход к другим отчетам на том же сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="d49b6-110">**Drillthrough report links** Jump to other reports on the same report server.</span></span> <span data-ttu-id="d49b6-111">Дополнительные сведения см. в разделе [Детализированные отчеты (построитель отчетов и службы SSRS)](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d49b6-111">For more information, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d49b6-112">Ссылки, привязанные к полям набора данных, могут стать мишенью для злонамеренного вторжения.</span><span class="sxs-lookup"><span data-stu-id="d49b6-112">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="d49b6-113">Дополнительные сведения см. в разделе [Защищенные отчеты и ресурсы](../security/secure-reports-and-resources.md)[электронной документации](https://go.microsoft.com/fwlink/?LinkId=154888) по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на сайте msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d49b6-113">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="d49b6-114">Также можно предоставить пользователям возможность управлять отображением отчета и его содержимым, создавая выражения, включающие ссылки на параметры для сортировки, фильтрации и определения видимости.</span><span class="sxs-lookup"><span data-stu-id="d49b6-114">You can also let your users control report display and content by designing expressions that include parameter references for sort, filter, and visibility.</span></span> <span data-ttu-id="d49b6-115">Дополнительные сведения см. в разделах [Параметры отчета (построитель отчетов и конструктор отчетов)](report-parameters-report-builder-and-report-designer.md), [Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)](filter-group-and-sort-data-report-builder-and-ssrs.md) и [Добавление фильтров набора данных, фильтров области данных и групповых фильтров (построитель отчетов и службы SSRS)](add-dataset-filters-data-region-filters-and-group-filters.md).</span><span class="sxs-lookup"><span data-stu-id="d49b6-115">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md), [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md), and [Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="d49b6-116">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d49b6-116">In This Section</span></span>  
 [<span data-ttu-id="d49b6-117">Интерактивная сортировка (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d49b6-117">Interactive Sort &#40;Report Builder and SSRS&#41;</span></span>](interactive-sort-report-builder-and-ssrs.md)  
 <span data-ttu-id="d49b6-118">Содержит описание способов добавления кнопки интерактивной сортировки к заголовкам столбцов.</span><span class="sxs-lookup"><span data-stu-id="d49b6-118">Explains how to add interactive sort buttons to column headers.</span></span>  
  
 [<span data-ttu-id="d49b6-119">Создание схемы документа (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d49b6-119">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
 <span data-ttu-id="d49b6-120">Объясняет, как добавить оглавление для перемещения по большим отчетам.</span><span class="sxs-lookup"><span data-stu-id="d49b6-120">Explains how to add a table of contents to support navigation in a large report.</span></span>  
  
 [<span data-ttu-id="d49b6-121">Добавление в отчет закладки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d49b6-121">Add a Bookmark to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-bookmark-to-a-report-report-builder-and-ssrs.md)  
 <span data-ttu-id="d49b6-122">Объясняет, как добавить закладки, чтобы создать ссылки внутри отчета.</span><span class="sxs-lookup"><span data-stu-id="d49b6-122">Explains how to add bookmarks to create links within a report.</span></span>  
  
 [<span data-ttu-id="d49b6-123">Добавление гиперссылки на URL-адрес (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d49b6-123">Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;</span></span>](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md)  
 <span data-ttu-id="d49b6-124">Объясняет, как добавить в отчет ссылки на URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="d49b6-124">Explains how to add a link from your report to a URL</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d49b6-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d49b6-125">See Also</span></span>  
 [<span data-ttu-id="d49b6-126">Детализация, углубленная детализация, вложенные отчеты и вложенные области данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d49b6-126">Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;</span></span>](drillthrough-drilldown-subreports-and-nested-data-regions.md)  
  
  
