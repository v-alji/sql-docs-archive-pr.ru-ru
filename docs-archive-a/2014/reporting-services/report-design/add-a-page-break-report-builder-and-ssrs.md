---
title: Добавление разрыва страницы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3846cd48-2787-47e9-b13b-7fc45a205f68
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55d6be3ae47827c5a8ff4a5b36e3ff2ce80e1034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654809"
---
# <a name="add-a-page-break-report-builder-and-ssrs"></a><span data-ttu-id="10927-102">Добавление разрыва страницы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="10927-102">Add a Page Break (Report Builder and SSRS)</span></span>
  <span data-ttu-id="10927-103">Разрыв страницы можно добавить в прямоугольники, области данных или в группы в областях данных, чтобы управлять количеством информации на каждой странице.</span><span class="sxs-lookup"><span data-stu-id="10927-103">You can add a page break to rectangles, data regions, or groups within data regions to control the amount of information on each page.</span></span> <span data-ttu-id="10927-104">Добавление разрывов страницы может повысить производительность опубликованных отчетов, т. к. при просмотре отчета будут обрабатываться только элементы на каждой странице.</span><span class="sxs-lookup"><span data-stu-id="10927-104">Adding page breaks can improve the performance of published reports because only the items on each page have to be processed as you view the report.</span></span> <span data-ttu-id="10927-105">Если отчет содержит одну страницу, все элементы должны быть обработаны перед просмотром отчета.</span><span class="sxs-lookup"><span data-stu-id="10927-105">When the whole report is a single page, all items must be processed before you can view the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-break-to-a-data-region"></a><span data-ttu-id="10927-106">Добавление разрыва страницы к области данных</span><span class="sxs-lookup"><span data-stu-id="10927-106">To add a page break to a data region</span></span>  
  
1.  <span data-ttu-id="10927-107">В области конструктора щелкните правой кнопкой мыши угловой маркер области данных и выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="10927-107">On the design surface, right-click the corner handle of the data region and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="10927-108">На вкладке **Общие** в разделе **Параметры разрыва страниц**выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="10927-108">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="10927-109">**Вставить разрыв страницы до**.</span><span class="sxs-lookup"><span data-stu-id="10927-109">**Add a page break before**.</span></span> <span data-ttu-id="10927-110">Выберите этот параметр, если нужно добавить разрыв страницы до таблицы.</span><span class="sxs-lookup"><span data-stu-id="10927-110">Select this option when you want to add a page break before the table.</span></span>  
  
    -   <span data-ttu-id="10927-111">**Вставить разрыв страницы после**.</span><span class="sxs-lookup"><span data-stu-id="10927-111">**Add a page break after**.</span></span> <span data-ttu-id="10927-112">Выберите этот параметр, если нужно добавить разрыв страницы после таблицы.</span><span class="sxs-lookup"><span data-stu-id="10927-112">Select this option when you want to add a page break after the table.</span></span>  
  
    -   <span data-ttu-id="10927-113">**По возможности поместить таблицу на одной странице**.</span><span class="sxs-lookup"><span data-stu-id="10927-113">**Fit table on one page if possible**.</span></span> <span data-ttu-id="10927-114">Выберите этот параметр, если нужно, чтобы данные оставались на одной странице.</span><span class="sxs-lookup"><span data-stu-id="10927-114">Select this option when you want the data to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-rectangle"></a><span data-ttu-id="10927-115">Добавление разрыва страницы в прямоугольник</span><span class="sxs-lookup"><span data-stu-id="10927-115">To add a page break to a rectangle</span></span>  
  
1.  <span data-ttu-id="10927-116">В области конструктора щелкните правой кнопкой мыши прямоугольник, куда нужно добавить разрыв страницы, затем выберите пункт **Свойства прямоугольника**.</span><span class="sxs-lookup"><span data-stu-id="10927-116">On the design surface, right-click the rectangle where you want to add a page break, and then click **Rectangle Properties**.</span></span>  
  
2.  <span data-ttu-id="10927-117">На вкладке **Общие** в разделе **Параметры разрыва страниц**выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="10927-117">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="10927-118">**Вставить разрыв страницы до**.</span><span class="sxs-lookup"><span data-stu-id="10927-118">**Add a page break before**.</span></span> <span data-ttu-id="10927-119">Выберите этот параметр, если нужно добавить разрыв страницы до прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="10927-119">Select this option when you want to add a page break before the rectangle.</span></span>  
  
    -   <span data-ttu-id="10927-120">**Вставить разрыв страницы после**.</span><span class="sxs-lookup"><span data-stu-id="10927-120">**Add a page break after**.</span></span> <span data-ttu-id="10927-121">Выберите этот параметр, если нужно добавить разрыв страницы после прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="10927-121">Select this option when you want to add a page break after the rectangle.</span></span>  
  
    -   <span data-ttu-id="10927-122">**Пропустить границу на разрыве страницы**.</span><span class="sxs-lookup"><span data-stu-id="10927-122">**Omit border on page break**.</span></span> <span data-ttu-id="10927-123">Выберите этот параметр, если разрыв страницы не должен попадать на границу.</span><span class="sxs-lookup"><span data-stu-id="10927-123">Select this option when you do not want a border on the page break.</span></span>  
  
    -   <span data-ttu-id="10927-124">**По возможности сохранять содержимое на одной странице**.</span><span class="sxs-lookup"><span data-stu-id="10927-124">**Keep contents together on a single page, if possible**.</span></span> <span data-ttu-id="10927-125">Выберите этот параметр, если нужно, чтобы содержимое внутри прямоугольника оставалось на одной странице.</span><span class="sxs-lookup"><span data-stu-id="10927-125">Select this option when you want contents inside the rectangle to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-row-group-in-a-table-matrix-or-list"></a><span data-ttu-id="10927-126">Добавление разрыва страницы к группе строк в таблице, матрице или списке</span><span class="sxs-lookup"><span data-stu-id="10927-126">To add a page break to a row group in a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="10927-127">В панели группирования щелкните правой кнопкой мыши группу строк и выберите команду **Свойства группы**.</span><span class="sxs-lookup"><span data-stu-id="10927-127">In the Grouping pane, right-click a row group, and then click **Group Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="10927-128">Разрывы страницы, установленные на группах столбцов, не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="10927-128">Page breaks are ignored on column groups.</span></span>  
  
2.  <span data-ttu-id="10927-129">На вкладке **Разрывы страницы** выберите **Между всеми экземплярами группы** , чтобы добавить разрыв страницы между всеми экземплярами группы в таблице.</span><span class="sxs-lookup"><span data-stu-id="10927-129">On the **Page Breaks** tab, select **Between each instance of a group** to add a page break between each instance of a group in the table.</span></span>  
  
3.  <span data-ttu-id="10927-130">Кроме того, можно выбрать параметр **Также в начале группы** или **Также в конце группы** , чтобы указать, что разрыв страницы должен добавляться, когда группа в таблице начинается или заканчивается.</span><span class="sxs-lookup"><span data-stu-id="10927-130">Optionally, select **Also at the start of a group** or **Also at the end of a group** to specify that a page break be added when a group starts or ends in the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10927-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="10927-131">See Also</span></span>  
 <span data-ttu-id="10927-132">[Разбиение на страницы в службах Reporting Services (построитель отчетов и службы SSRS)](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10927-132">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10927-133">[Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)](rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10927-133">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="10927-134">Верхние и нижние колонтитулы страницы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="10927-134">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
