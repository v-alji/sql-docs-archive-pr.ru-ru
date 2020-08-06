---
title: Сохранение отчетов на сервере отчетов (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48dfef01-ed8c-4f23-90c3-de67c90a97dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d80e35c447593e89d422e72ea31ec6be34c3619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739431"
---
# <a name="save-reports-to-a-report-server-report-builder"></a><span data-ttu-id="bb44d-102">Сохранение отчетов на сервере отчетов (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="bb44d-102">Save Reports to a Report Server (Report Builder)</span></span>
  <span data-ttu-id="bb44d-103">В построителе отчетов можно сохранить определение отчета на сервере отчетов (также называется публикацией отчета).</span><span class="sxs-lookup"><span data-stu-id="bb44d-103">In Report Builder, you can save a report definition to a report server (also known as publishing a report).</span></span> <span data-ttu-id="bb44d-104">Если отчет сохранен на сервере отчетов, его могут просматривать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="bb44d-104">When the report is saved to a report server, other users can view the report.</span></span> <span data-ttu-id="bb44d-105">При каждом запуске опубликованного отчета будут получены самые последние данные.</span><span class="sxs-lookup"><span data-stu-id="bb44d-105">Each time you run the published report, you will retrieve the most current data.</span></span> <span data-ttu-id="bb44d-106">Чтобы сохранить статическую копию отчета, готового к просмотру, экспортируйте отчет в другой формат файла и сохраните его или используйте функцию журнала отчета, чтобы сохранить версию отчета, готового к просмотру.</span><span class="sxs-lookup"><span data-stu-id="bb44d-106">To save a static copy of a rendered report, export the report to a different file format and save it or use the report history feature to save versions of rendered reports.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb44d-107">Расположение сохраненного определения отчета не влияет на место обработки отчета (на сервере или локально) во время просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="bb44d-107">The location of the saved report definition does not affect whether the report is processed on the server or processed locally when you preview the report.</span></span>  
  
### <a name="to-save-a-report-to-a-report-server"></a><span data-ttu-id="bb44d-108">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="bb44d-108">To save a report to a report server</span></span>  
  
1.  <span data-ttu-id="bb44d-109">В построителе отчетов нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bb44d-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="bb44d-110">**Save As** _\<Report Item\>_ Откроется диалоговое окно Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="bb44d-110">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb44d-111">Во время повторного сохранения отчет автоматически сохраняется в предыдущем расположении.</span><span class="sxs-lookup"><span data-stu-id="bb44d-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="bb44d-112">Чтобы изменить расположение, используйте параметр «Сохранить как».</span><span class="sxs-lookup"><span data-stu-id="bb44d-112">Use the Save As option to change location.</span></span>  
  
2.  <span data-ttu-id="bb44d-113">Также можно щелкнуть ссылку **Последние сайты и серверы** , чтобы вывести список недавно использовавшихся серверов отчета и сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb44d-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="bb44d-114">Перейдите в папку на сервере отчетов, в которой необходимо сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="bb44d-114">Browse to the report server location where you want to save the report.</span></span>  
  
4.  <span data-ttu-id="bb44d-115">В поле **Имя**введите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="bb44d-115">In **Name**, type the name of the report.</span></span>  
  
5.  <span data-ttu-id="bb44d-116">В поле **Элементы типа**выберите тип сохраняемого элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bb44d-116">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="bb44d-117">Для отчетов используется тип «Отчеты» (RDL).</span><span class="sxs-lookup"><span data-stu-id="bb44d-117">The type for reports is Reports(\*.rdl).</span></span>  
  
### <a name="to-save-a-report-as-a-different-name"></a><span data-ttu-id="bb44d-118">Сохранение отчета с другим именем</span><span class="sxs-lookup"><span data-stu-id="bb44d-118">To save a report as a different name</span></span>  
  
1.  <span data-ttu-id="bb44d-119">Нажмите кнопку «Построитель отчетов» и выберите **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="bb44d-119">From the Report Builder button, click **Save As**.</span></span> <span data-ttu-id="bb44d-120">**Save As** _\<Report Item\>_ Откроется диалоговое окно Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="bb44d-120">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
2.  <span data-ttu-id="bb44d-121">Перейдите к расположению сервера отчетов или в общую папку, где нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="bb44d-121">Browse to the report server location or to the file share where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="bb44d-122">В поле **Имя**введите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="bb44d-122">In **Name**, type the name of the report.</span></span>  
  
4.  <span data-ttu-id="bb44d-123">В поле **Элементы типа**выберите тип сохраняемого элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bb44d-123">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="bb44d-124">Для отчетов используется тип «Отчеты» (RDL).</span><span class="sxs-lookup"><span data-stu-id="bb44d-124">The type for reports is Reports(\*.rdl).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb44d-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb44d-125">See Also</span></span>  
 <span data-ttu-id="bb44d-126">[Поиск, просмотр отчетов и управление ими &#40;построитель отчетов и SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb44d-126">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bb44d-127">[Экспорт отчетов &#40;построитель отчетов и SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb44d-127">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bb44d-128">[Сохранение отчетов &#40;построитель отчетов&#41;](saving-reports-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="bb44d-128">[Saving Reports &#40;Report Builder&#41;](saving-reports-report-builder.md) </span></span>  
 [<span data-ttu-id="bb44d-129">Экспорт отчета в файл другого типа (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="bb44d-129">Export a Report as Another File Type &#40;Report Builder and SSRS&#41;</span></span>](../export-a-report-as-another-file-type-report-builder-and-ssrs.md)  
  
  
