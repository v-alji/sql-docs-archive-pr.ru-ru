---
title: Экспорт отчета в файл другого типа (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b577568b-ecbd-44c3-be88-31dab6fc38a2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 240d3266b7b8c9a445658a9fd21fb9ea18a4c113
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728081"
---
# <a name="export-a-report-as-another-file-type-report-builder-and-ssrs"></a><span data-ttu-id="47ae3-102">Экспорт отчета в файл другого типа (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="47ae3-102">Export a Report as Another File Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="47ae3-103">Во время предварительного просмотра отчета с помощью построителя отчетов или конструктора отчетов можно выполнить подготовку отчета в другом формате, например CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)]или [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]. Это можно сделать и при просмотре отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="47ae3-103">You can render a report to another file format, such as CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)], or [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], while previewing your report in Report Builder or Report Designer, or you can render the report while viewing the report on the report server.</span></span> <span data-ttu-id="47ae3-104">Подготовка отчета в определенном формате удобна в тех случаях, когда требуется сохранить отчет в файле другого типа сразу, не выполняя перед этим публикацию на сервере отчетов. Также это может понадобиться, если нужно проверить, как будет выглядеть отчет в том или ином формате после доставки получателям.</span><span class="sxs-lookup"><span data-stu-id="47ae3-104">Rendering the report in a specific format in is helpful when you want to immediately save the report as another file type without publishing the report to the report server or when you want to see how your report design will appear when delivered to your report readers in a specific format.</span></span> <span data-ttu-id="47ae3-105">Подготовка отчета на сервере отчетов может быть полезной, если необходимо настроить подписки или доставить отчеты по электронной почте, а также в случае, если необходимо сохранить отчет, доступный на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="47ae3-105">Rendering the report on the report server is useful when you set up subscriptions or deliver your reports via e-mail, or if you want to save a report that is available on the report server.</span></span> <span data-ttu-id="47ae3-106">Дополнительные сведения см. в разделе [Подписки и доставка (службы Reporting Services)](subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="47ae3-106">For more information, see [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-export-a-report-as-another-file-type-in-report-builder"></a><span data-ttu-id="47ae3-107">Экспорт отчета в файл другого типа с помощью построителя отчетов</span><span class="sxs-lookup"><span data-stu-id="47ae3-107">To export a report as another file type in Report Builder</span></span>  
  
1.  <span data-ttu-id="47ae3-108">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="47ae3-108">Preview the report.</span></span>  
  
2.  <span data-ttu-id="47ae3-109">На ленте нажмите кнопку **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="47ae3-109">On the ribbon, click **Export**.</span></span>  
  
3.  <span data-ttu-id="47ae3-110">Выберите нужный формат.</span><span class="sxs-lookup"><span data-stu-id="47ae3-110">Select the format that you want to use.</span></span>  
  
     <span data-ttu-id="47ae3-111">Откроется диалоговое окно **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="47ae3-111">The **Save As** dialog box opens.</span></span> <span data-ttu-id="47ae3-112">По умолчанию именем файла является имя экспортируемого отчета.</span><span class="sxs-lookup"><span data-stu-id="47ae3-112">By default, the file name is that of the report that you exported.</span></span> <span data-ttu-id="47ae3-113">При необходимости имя файла можно изменить.</span><span class="sxs-lookup"><span data-stu-id="47ae3-113">Optionally, you can change the file name.</span></span>  
  
4.  <span data-ttu-id="47ae3-114">Перейдите в папку, где сохранен экспортированный отчет, и откройте его.</span><span class="sxs-lookup"><span data-stu-id="47ae3-114">Navigate to the location where you saved the exported report and open it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47ae3-115">Если открыть отчет в выбранном формате не удается, поскольку с этим типом файла не связана ни одна программа, будет предложено сохранить отчет или найти в сети программу для его открытия.</span><span class="sxs-lookup"><span data-stu-id="47ae3-115">If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-report-manager"></a><span data-ttu-id="47ae3-116">Экспорт отчета в файл другого типа с помощью диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="47ae3-116">To export a report as another file type in Report Manager</span></span>  
  
1.  <span data-ttu-id="47ae3-117">В диспетчере отчетов, начав с **домашней** страницы, перейдите к отчету, который необходимо экспортировать.</span><span class="sxs-lookup"><span data-stu-id="47ae3-117">From the Report Manager **Home** page, navigate to the report that you want to export.</span></span>  
  
2.  <span data-ttu-id="47ae3-118">Щелкните отчет.</span><span class="sxs-lookup"><span data-stu-id="47ae3-118">Click the report.</span></span>  
  
     <span data-ttu-id="47ae3-119">Отчет будет сформирован.</span><span class="sxs-lookup"><span data-stu-id="47ae3-119">The report is generated.</span></span>  
  
3.  <span data-ttu-id="47ae3-120">Щелкните стрелку раскрывающегося списка **Выберите формат** на панели инструментов средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="47ae3-120">On the Report Viewer toolbar, click the **Select a format** drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="47ae3-121">Выберите нужный формат.</span><span class="sxs-lookup"><span data-stu-id="47ae3-121">Select the format that you want to use.</span></span>  
  
5.  <span data-ttu-id="47ae3-122">Щелкните **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="47ae3-122">Click **Export**.</span></span>  
  
     <span data-ttu-id="47ae3-123">Появится запрос, что нужно сделать с файлом: открыть или сохранить.</span><span class="sxs-lookup"><span data-stu-id="47ae3-123">A message appears asking you if you want to open or save the file.</span></span>  
  
6.  <span data-ttu-id="47ae3-124">Чтобы просмотреть отчет в выбранном для экспорта формате, выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="47ae3-124">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="47ae3-125">\- или -</span><span class="sxs-lookup"><span data-stu-id="47ae3-125">\- or -</span></span>  
  
     <span data-ttu-id="47ae3-126">Чтобы сразу сохранить отчет в выбранном для экспорта формате, выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="47ae3-126">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="47ae3-127">Отчет выводится или сохраняется с помощью приложения, связанного с выбранным форматом.</span><span class="sxs-lookup"><span data-stu-id="47ae3-127">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="47ae3-128">При выборе **Сохранить**потребуется ввести путь для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="47ae3-128">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="47ae3-129">**Примечание.** Если открыть отчет в выбранном формате не удается из-за того, что с этим типом файла не связана ни одна программа, будет предложено сохранить отчет или найти в сети программу для его открытия.</span><span class="sxs-lookup"><span data-stu-id="47ae3-129">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-a-sharepoint-library"></a><span data-ttu-id="47ae3-130">Экспорт отчета в файл другого типа с помощью библиотеки SharePoint</span><span class="sxs-lookup"><span data-stu-id="47ae3-130">To export a report as another file type in a SharePoint library</span></span>  
  
1.  <span data-ttu-id="47ae3-131">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="47ae3-131">Preview the report.</span></span>  
  
2.  <span data-ttu-id="47ae3-132">На панели инструментов выберите **Действия**, далее выберите **Экспорт**, затем выберите нужный формат.</span><span class="sxs-lookup"><span data-stu-id="47ae3-132">On the toolbar, click **Actions**, point to **Export**, and then select the format that you want to use.</span></span>  
  
     <span data-ttu-id="47ae3-133">Откроется диалоговое окно **Загрузка файла** .</span><span class="sxs-lookup"><span data-stu-id="47ae3-133">The **File Download** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="47ae3-134">Чтобы просмотреть отчет в выбранном для экспорта формате, выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="47ae3-134">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="47ae3-135">\- или -</span><span class="sxs-lookup"><span data-stu-id="47ae3-135">\- or -</span></span>  
  
     <span data-ttu-id="47ae3-136">Чтобы сразу сохранить отчет в выбранном для экспорта формате, выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="47ae3-136">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="47ae3-137">Отчет выводится или сохраняется с помощью приложения, связанного с выбранным форматом.</span><span class="sxs-lookup"><span data-stu-id="47ae3-137">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="47ae3-138">При выборе **Сохранить**потребуется ввести путь для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="47ae3-138">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="47ae3-139">При необходимости измените имя файла экспортируемого отчета.</span><span class="sxs-lookup"><span data-stu-id="47ae3-139">Optionally, change the file name of the exported report.</span></span>  
  
     <span data-ttu-id="47ae3-140">**Примечание.** Если открыть отчет в выбранном формате не удается из-за того, что с этим типом файла не связана ни одна программа, будет предложено сохранить отчет или найти в сети программу для его открытия.</span><span class="sxs-lookup"><span data-stu-id="47ae3-140">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ae3-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="47ae3-141">See Also</span></span>  
 <span data-ttu-id="47ae3-142">[Экспорт отчетов &#40;построитель отчетов и SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47ae3-142">[Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47ae3-143">[Разбиение на страницы в Reporting Services &#40;построитель отчетов и SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47ae3-143">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="47ae3-144">Интерактивные возможности различных модулей подготовки отчетов к просмотру (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="47ae3-144">Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;</span></span>](report-builder/interactive-functionality-different-report-rendering-extensions.md)  
  
  
