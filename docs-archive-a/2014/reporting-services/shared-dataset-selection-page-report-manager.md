---
title: Страница выбора общего набора данных (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a67dc03e-f838-4ec2-9ef6-f04895bab3c7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad26246f04c741c186b61967e3e71aa4d5dd55f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730069"
---
# <a name="shared-dataset-selection-page-report-manager"></a><span data-ttu-id="6ce56-102">Страница «Выбор общего набора данных» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="6ce56-102">Shared Dataset Selection Page (Report Manager)</span></span>
  <span data-ttu-id="6ce56-103">Страница «Выбор общего набора данных» используется для просмотра и изменения общих наборов данных, которые в настоящее время связаны с отчетом.</span><span class="sxs-lookup"><span data-stu-id="6ce56-103">Use the Shared Dataset Selection page to review and modify the shared datasets that are currently associated with a report.</span></span>  
  
 <span data-ttu-id="6ce56-104">Нельзя использовать эту страницу для добавления общих наборов данных в отчет и удаления общих наборов данных из отчета.</span><span class="sxs-lookup"><span data-stu-id="6ce56-104">You cannot use this page to add more shared datasets to a report or remove shared datasets from a report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="6ce56-105">Навигация</span><span class="sxs-lookup"><span data-stu-id="6ce56-105">Navigation</span></span>  
 <span data-ttu-id="6ce56-106">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="6ce56-106">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-shared-dataset-selection-page"></a><span data-ttu-id="6ce56-107">Открытие страницы «Выбор общего набора данных»</span><span class="sxs-lookup"><span data-stu-id="6ce56-107">To open the Shared Dataset Selection page</span></span>  
  
1.  <span data-ttu-id="6ce56-108">Откройте диспетчер отчетов и найдите отчет, для которого нужно просмотреть общие наборы данных.</span><span class="sxs-lookup"><span data-stu-id="6ce56-108">Open Report Manager, and locate the report for which you want to review the shared datasets.</span></span>  
  
2.  <span data-ttu-id="6ce56-109">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="6ce56-109">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="6ce56-110">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="6ce56-110">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="6ce56-111">Откроется страница свойств отчета «Общие».</span><span class="sxs-lookup"><span data-stu-id="6ce56-111">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="6ce56-112">Откройте вкладку **Общие наборы данных** .</span><span class="sxs-lookup"><span data-stu-id="6ce56-112">Select the **Shared Datasets** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ce56-113">Варианты</span><span class="sxs-lookup"><span data-stu-id="6ce56-113">Options</span></span>  
 <span data-ttu-id="6ce56-114">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="6ce56-114">**Browse**</span></span>  
 <span data-ttu-id="6ce56-115">Для каждого имени общего набора данных в отчете можно просматривать текущий путь к папке и имя целевого общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="6ce56-115">For each shared dataset name in a report, you can review the current folder path and name for the target shared dataset.</span></span>  
  
 <span data-ttu-id="6ce56-116">Чтобы изменить общий набор данных, соответствующий имени набора данных, нажмите кнопку **Обзор** .</span><span class="sxs-lookup"><span data-stu-id="6ce56-116">To change the shared dataset referenced by a dataset name, click the **Browse** button.</span></span>  
  
 <span data-ttu-id="6ce56-117">Кнопка **Обзор** раскрывает структуру папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="6ce56-117">The **Browse** button opens the folder structure of the report server.</span></span> <span data-ttu-id="6ce56-118">Чтобы добавить в поле **Расположение** полный путь к папке, щелкните общий набор данных.</span><span class="sxs-lookup"><span data-stu-id="6ce56-118">Click a shared dataset to add the full path to the **Location** field.</span></span>  
  
 <span data-ttu-id="6ce56-119">Нажмите кнопку **ОК** , чтобы завершить выбор общего набора данных, или кнопку **Отмена** для отмены обзора, связанного с поиском общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="6ce56-119">Click the **OK** button to finish selecting a shared dataset or click **Cancel** to cancel browsing for a shared dataset.</span></span>  
  
 <span data-ttu-id="6ce56-120">**Применить**</span><span class="sxs-lookup"><span data-stu-id="6ce56-120">**Apply**</span></span>  
 <span data-ttu-id="6ce56-121">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="6ce56-121">Save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce56-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="6ce56-122">See Also</span></span>  
 <span data-ttu-id="6ce56-123">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="6ce56-123">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="6ce56-124">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="6ce56-124">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="6ce56-125">[Управление общими наборами данных](report-data/manage-shared-datasets.md) </span><span class="sxs-lookup"><span data-stu-id="6ce56-125">[Manage Shared Datasets](report-data/manage-shared-datasets.md) </span></span>  
 <span data-ttu-id="6ce56-126">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="6ce56-126">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="6ce56-127">[Элементы отчета и наборы данных в построитель отчетов](report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="6ce56-127">[Report Parts and Datasets in Report Builder](report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 [<span data-ttu-id="6ce56-128">Внедренные и общие наборы данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6ce56-128">Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
