---
title: Страница "перемещение элементов" (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fc83b8d2-bc79-4b56-8970-34a1cbbcc176
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98ff306caf634a5f0478e2eba03c2313b24be274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739527"
---
# <a name="move-items-page-report-manager"></a><span data-ttu-id="80bc9-102">Страница «Перемещение элементов» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="80bc9-102">Move Items Page (Report Manager)</span></span>
  <span data-ttu-id="80bc9-103">Используйте страницу «Перемещение элементов», чтобы переместить отчет, папку или другой элемент в новое местоположение на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="80bc9-103">Use the Move Items page to move a report, folder, or other item to a new location on the report server.</span></span> <span data-ttu-id="80bc9-104">Можно ввести путь нового местоположения или использовать представление дерева для указания нового местоположения в пространстве имен сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="80bc9-104">You can type the path of the new location or use a tree view to browse to a new location in the report server namespace.</span></span> <span data-ttu-id="80bc9-105">Переместить можно только те элементы, на перемещение которых есть разрешение и которые хранятся на текущем сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="80bc9-105">You can only move items that you have permission to move and that are stored on the current report server.</span></span>  
  
 <span data-ttu-id="80bc9-106">При перемещении элемента, на который ссылается другой элемент (например, общего источника данных или модели, на которые ссылаются многие отчеты), сведения о пути к нему обновляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="80bc9-106">When you move an item that is referenced by another item (for example, a shared data source or model that is referenced by many reports), the path information for that item is updated automatically.</span></span> <span data-ttu-id="80bc9-107">Перемещение общего источника данных не разрывает соединения источника данных с использующими его отчетами и моделями.</span><span class="sxs-lookup"><span data-stu-id="80bc9-107">Moving a shared data source does not disrupt a data source connection to the reports and models that use it.</span></span> <span data-ttu-id="80bc9-108">Если общий источник данных или модель перемещается в папку, для которой у пользователя отсутствуют разрешение, он все равно сможет выполнять любые отчеты, ссылающиеся на этот источник данных или модель, хотя этот элемент не будет виден пользователю в иерархии папок.</span><span class="sxs-lookup"><span data-stu-id="80bc9-108">If you move a shared data source or model to a folder for which users do not have permission, they will still be able to run any report that references the data source or model, however the item will not be visible to them in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="80bc9-109">Для **Расположения**задайте полный путь к папке, начиная с имени корневой папки.</span><span class="sxs-lookup"><span data-stu-id="80bc9-109">For **Location**, specify the full path to folder, beginning with the root folder name.</span></span> <span data-ttu-id="80bc9-110">Можно ввести имя пути или использовать представление дерева, чтобы указать нужную папку.</span><span class="sxs-lookup"><span data-stu-id="80bc9-110">You can type the path name or use the tree view to navigate to the folder you want.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80bc9-111">Перемещение возможно не для всех элементов.</span><span class="sxs-lookup"><span data-stu-id="80bc9-111">Not all items are movable.</span></span> <span data-ttu-id="80bc9-112">Нельзя переместить такие зарезервированные папки, как «Корневая папка», «Мои отчеты» или «Папки пользователей».</span><span class="sxs-lookup"><span data-stu-id="80bc9-112">You cannot move reserved folders such as Home, My Reports, or Users Folders.</span></span> <span data-ttu-id="80bc9-113">Нельзя переместить журнал отчета или моментальные снимки в другое место.</span><span class="sxs-lookup"><span data-stu-id="80bc9-113">You cannot move report history or snapshots to different locations.</span></span> <span data-ttu-id="80bc9-114">Журнал и моментальные снимки всегда располагаются вместе с отчетом, на котором они основаны. Доступ к ним также осуществляется через этот отчет.</span><span class="sxs-lookup"><span data-stu-id="80bc9-114">History and snapshots are always located with, and accessed through, the report on which they are based.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="80bc9-115">Навигация</span><span class="sxs-lookup"><span data-stu-id="80bc9-115">Navigation</span></span>  
 <span data-ttu-id="80bc9-116">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="80bc9-116">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-details-view"></a><span data-ttu-id="80bc9-117">Открытие страницы «Перемещение элементов» из страницы «Содержимое» в «Просмотр подробностей»</span><span class="sxs-lookup"><span data-stu-id="80bc9-117">To open the Move Items page from the Contents page in Details View</span></span>  
  
1.  <span data-ttu-id="80bc9-118">Откройте диспетчер отчетов и перейдите к папке, содержащей элемент, который нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="80bc9-118">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="80bc9-119">Также можно перемещать элементы с домашней страницы диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="80bc9-119">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="80bc9-120">На панели инструментов нажмите кнопку **Просмотр подробностей**.</span><span class="sxs-lookup"><span data-stu-id="80bc9-120">In the toolbar, click **Details View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80bc9-121"> Если отображается только **Представление мозаики**, это означает, что текущим местоположением является **Просмотр подробностей**.</span><span class="sxs-lookup"><span data-stu-id="80bc9-121">If you see only **Tiles View**, you are already in **Details View**.</span></span>  
  
3.  <span data-ttu-id="80bc9-122">Установите флажок рядом с элементом, а затем на панели инструментов щелкните **Переместить** .</span><span class="sxs-lookup"><span data-stu-id="80bc9-122">Select the box next to an item, and then click **Move** in the toolbar.</span></span> <span data-ttu-id="80bc9-123">Можно установить несколько флажков, если необходимо переместить несколько элементов в одно новое местоположение.</span><span class="sxs-lookup"><span data-stu-id="80bc9-123">You can select more than one box if you want to move multiple items to the same new location.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-tiles-view"></a><span data-ttu-id="80bc9-124">Открытие страницы «Перемещение элементов» из страницы «Содержимое» в «Представление мозаики»</span><span class="sxs-lookup"><span data-stu-id="80bc9-124">To open the Move Items page from the Contents page in Tiles View</span></span>  
  
1.  <span data-ttu-id="80bc9-125">Откройте диспетчер отчетов и перейдите к папке, содержащей элемент, который нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="80bc9-125">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="80bc9-126">Также можно перемещать элементы с домашней страницы диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="80bc9-126">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="80bc9-127">На панели инструментов нажмите кнопку **Представление мозаики**.</span><span class="sxs-lookup"><span data-stu-id="80bc9-127">In the toolbar, click **Tiles View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80bc9-128"> Если отображается только **Просмотр подробностей**, это означает, что текущим местоположением является **Представление мозаики**.</span><span class="sxs-lookup"><span data-stu-id="80bc9-128">If you see only **Details View**, you are already in **Tiles View**.</span></span>  
  
3.  <span data-ttu-id="80bc9-129">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="80bc9-129">Hover over an item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="80bc9-130">В раскрывающемся меню выберите **Переместить**.</span><span class="sxs-lookup"><span data-stu-id="80bc9-130">In the drop-down menu, click **Move**.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-general-properties-page-of-an-item"></a><span data-ttu-id="80bc9-131">Открытие страницы «Перемещение элементов» из страницы элемента «Общие свойства»</span><span class="sxs-lookup"><span data-stu-id="80bc9-131">To open the Move Items page from the General Properties page of an item</span></span>  
  
1.  <span data-ttu-id="80bc9-132">Откройте диспетчер отчетов и перейдите к папке, содержащей элемент, который нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="80bc9-132">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="80bc9-133">Также можно перемещать элементы с домашней страницы диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="80bc9-133">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="80bc9-134">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="80bc9-134">Hover over an item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="80bc9-135">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="80bc9-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="80bc9-136">Откроется страница свойств элемента «Общие».</span><span class="sxs-lookup"><span data-stu-id="80bc9-136">This opens the General properties page for an item.</span></span>  
  
4.  <span data-ttu-id="80bc9-137">На панели инструментов элемента нажмите кнопку **Переместить**.</span><span class="sxs-lookup"><span data-stu-id="80bc9-137">In the item toolbar, click **Move**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80bc9-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="80bc9-138">See Also</span></span>  
 <span data-ttu-id="80bc9-139">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="80bc9-139">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="80bc9-140">[Страница «Общие свойства», папки &#40;диспетчер отчетов&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="80bc9-140">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="80bc9-141">[Страница «Общие свойства», отчеты &#40;диспетчер отчетов&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="80bc9-141">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="80bc9-142">[Страница «Общие свойства», ресурсы &#40;диспетчер отчетов&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="80bc9-142">[General Properties Page, Resources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span></span>  
 <span data-ttu-id="80bc9-143">[Страница «Общие свойства», общие источники данных &#40;диспетчер отчетов&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="80bc9-143">[General Properties Page, Shared Data Sources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span></span>  
 [<span data-ttu-id="80bc9-144">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="80bc9-144">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
