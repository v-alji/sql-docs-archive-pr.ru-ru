---
title: Указание путей к внешним элементам (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4fe513da-f3c5-479c-9fec-8662b91a0d6d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 097a3566f914e7810039ee07bc3d3bf3185d7f06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654778"
---
# <a name="specifying-paths-to-external-items-report-builder-and-ssrs"></a><span data-ttu-id="1cebe-102">Указание путей к внешним элементам (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="1cebe-102">Specifying Paths to External Items (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1cebe-103">В свойствах элемента отчета укажите пути к нужным элементам, таким как детализированные отчеты, вложенные отчеты и файлы изображений, которые являются внешними для файла определения отчета и размещены на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1cebe-103">You specify paths in report item properties to reference items such as drillthrough reports, subreports, and image files that are external to the report definition file and are stored on a report server.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="1cebe-104">В построителе отчетов пути к элементам должны указывать на элементы на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1cebe-104">In Report Builder, paths to items must specify items on a report server.</span></span> <span data-ttu-id="1cebe-105">Пути к элементам в файловой системе не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1cebe-105">Paths to items on a file system are not supported.</span></span> <span data-ttu-id="1cebe-106">Осуществить предварительный просмотр отчета, который использует эти элементы, можно только в случае, если установлено соединение с сервером отчетов, на котором располагаются эти элементы.</span><span class="sxs-lookup"><span data-stu-id="1cebe-106">You can preview a report that uses these items only if you are connected to the report server where the items are located.</span></span>  
  
 <span data-ttu-id="1cebe-107">При указании пути к внешнему элементу в диалоговом окне действий, вложенных отчетов или изображений, можно непосредственно перейти к серверу отчетов и выбрать элемент.</span><span class="sxs-lookup"><span data-stu-id="1cebe-107">When you specify a path for an external item in a dialog box for actions, subreports, or images, you can browse directly to the report server and select the item.</span></span> <span data-ttu-id="1cebe-108">Указывать детализированный отчет или вложенный отчет рекомендуется путем перехода к элементу и выбора его напрямую.</span><span class="sxs-lookup"><span data-stu-id="1cebe-108">Browsing to an item and selecting it directly is the recommended way to specify a drillthrough report or subreport.</span></span> <span data-ttu-id="1cebe-109">При этом правильные имена параметров будут доступны в раскрывающемся списке при указании параметров отчета или вложенного отчета.</span><span class="sxs-lookup"><span data-stu-id="1cebe-109">That way the correct parameter names will be available in a drop-down list when you specify report or subreport parameters.</span></span> <span data-ttu-id="1cebe-110">При замене пути к элементу на путь, указывающий на другой элемент, следует вручную обновить правильные имена параметров и переменные, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="1cebe-110">When you change an item path to point to a different item, you must manually update the correct parameter names and values as needed.</span></span>  
  
 <span data-ttu-id="1cebe-111">На сервере отчетов, работающем в собственном режиме, укажите имя детализированного отчета без расширения файла RDL.</span><span class="sxs-lookup"><span data-stu-id="1cebe-111">On a report server configured in native mode, specify a drillthrough report name without the file extension .rdl.</span></span>  
  
 <span data-ttu-id="1cebe-112">На сервере отчетов, работающем в режиме интеграции с SharePoint, необходимо включить расширение файла RDL.</span><span class="sxs-lookup"><span data-stu-id="1cebe-112">On a report server configured in SharePoint integrated mode, you must include the file extension .rdl.</span></span> <span data-ttu-id="1cebe-113">Путь может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="1cebe-113">The path can be one of the following:</span></span>  
  
-   <span data-ttu-id="1cebe-114">**Относительный путь к элементу из основного отчета.**</span><span class="sxs-lookup"><span data-stu-id="1cebe-114">**A relative path to the item from the main report.**</span></span> <span data-ttu-id="1cebe-115">Например, ../AllSubreports/Subreport1.</span><span class="sxs-lookup"><span data-stu-id="1cebe-115">For example, ../AllSubreports/Subreport1.</span></span> <span data-ttu-id="1cebe-116">В этом примере **..**</span><span class="sxs-lookup"><span data-stu-id="1cebe-116">In this example, the **..**</span></span> <span data-ttu-id="1cebe-117">указывает на родительскую папку для папки, в которой расположен основной отчет.</span><span class="sxs-lookup"><span data-stu-id="1cebe-117">indicates the folder above the folder where the main report is located.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1cebe-118">Относительные пути не поддерживаются, если отчет запускается в построителе отчетов.</span><span class="sxs-lookup"><span data-stu-id="1cebe-118">Relative paths are not supported when the report is run inside Report Builder.</span></span> <span data-ttu-id="1cebe-119">Для просмотра отчета, использующего относительные пути к внешним элементам, необходимо сохранить отчет на сервере отчетов и запустить отчет оттуда.</span><span class="sxs-lookup"><span data-stu-id="1cebe-119">To view a report that uses relative paths to external items, save the report to the report server, and run the report from there</span></span>  
  
-   <span data-ttu-id="1cebe-120">**Полный путь к элементу.**</span><span class="sxs-lookup"><span data-stu-id="1cebe-120">**A full path to the item.**</span></span>  
  
    -   <span data-ttu-id="1cebe-121">**На сервере отчетов** путь начинается с **/** (корневой папки).</span><span class="sxs-lookup"><span data-stu-id="1cebe-121">**On a report server:** The path starts from **/**, the Home folder.</span></span> <span data-ttu-id="1cebe-122">например /Reports/AllSubreports/Subreport1.</span><span class="sxs-lookup"><span data-stu-id="1cebe-122">For example, /Reports/AllSubreports/Subreport1.</span></span>  
  
    -   <span data-ttu-id="1cebe-123">**На сайте SharePoint** необходимо указать в выражении имя отчета с полным URL-адресом элемента и расширением файла RDL.</span><span class="sxs-lookup"><span data-stu-id="1cebe-123">**On a SharePoint site:** You must specify the report name in an expression, with the full URL of the item and the file extension .rdl.</span></span> <span data-ttu-id="1cebe-124">Например, `="http://server/site/library/folder/Report1.rdl"`.</span><span class="sxs-lookup"><span data-stu-id="1cebe-124">For example, `="http://server/site/library/folder/Report1.rdl"`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cebe-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="1cebe-125">See Also</span></span>  
 <span data-ttu-id="1cebe-126">[Добавление внешнего изображения (построитель отчетов и службы SSRS)](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1cebe-126">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1cebe-127">[Добавление вложенного отчета и параметров (построитель отчетов и службы SSRS)](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1cebe-127">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1cebe-128">Добавление действия детализации в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="1cebe-128">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
