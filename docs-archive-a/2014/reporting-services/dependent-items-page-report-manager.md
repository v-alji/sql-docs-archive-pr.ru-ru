---
title: Страница "зависимые элементы" (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dcfb311-e9c3-4c5d-b2e0-018d79f37d2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488b10d7d7985972274340897ee3975618a12639
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656246"
---
# <a name="dependent-items-page-report-manager"></a><span data-ttu-id="93aec-102">Страница «Зависимые элементы» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="93aec-102">Dependent Items Page (Report Manager)</span></span>
  <span data-ttu-id="93aec-103">Страница «Зависимые элементы» позволяет просмотреть список отчетов и моделей, ссылающихся на общий источник данных.</span><span class="sxs-lookup"><span data-stu-id="93aec-103">Use the Dependent Items page to view a list of reports and models that reference a shared data source.</span></span> <span data-ttu-id="93aec-104">Значок типа элемента показывает, отчет это или модель.</span><span class="sxs-lookup"><span data-stu-id="93aec-104">The icon for each item type indicates whether it is a report or a model.</span></span> <span data-ttu-id="93aec-105">Данную страницу можно просматривать в режиме списка или подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="93aec-105">This page can be viewed in list view or details view.</span></span> <span data-ttu-id="93aec-106">Режим подробных сведений позволяет отображать больше данных об элементе.</span><span class="sxs-lookup"><span data-stu-id="93aec-106">Use details view to show more information about each item.</span></span> <span data-ttu-id="93aec-107">Также в нем доступны дополнительные параметры страницы.</span><span class="sxs-lookup"><span data-stu-id="93aec-107">Additional page options are available in details view.</span></span> <span data-ttu-id="93aec-108">Для помощи в управлении общим источником данных на этой странице содержатся ссылки на отчеты и модели, использующие источник данных, данные о последнем запуске или последних изменениях отчета или модели, а также кнопки «Удалить» и «Переместить», которые позволяют удалить неиспользуемые отчеты и модели либо переместить их в другое расположение на время, пока определяется потребность в них.</span><span class="sxs-lookup"><span data-stu-id="93aec-108">To help you manage the shared data source, this page provides links to reports and models that use the data source, metrics on when the report or model was last run or modified, and Delete and Move buttons so that you can easily remove reports and models that are no longer used, or move them to a different location while you determine whether they are still needed.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="93aec-109">Навигация</span><span class="sxs-lookup"><span data-stu-id="93aec-109">Navigation</span></span>  
 <span data-ttu-id="93aec-110">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="93aec-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-dependent-items-page"></a><span data-ttu-id="93aec-111">Открытие страницы «Зависимые элементы»</span><span class="sxs-lookup"><span data-stu-id="93aec-111">To open the Dependent Items page</span></span>  
  
1.  <span data-ttu-id="93aec-112">Откройте диспетчер отчетов и найдите общий источник данных, для которого необходимо просмотреть зависимые элементы.</span><span class="sxs-lookup"><span data-stu-id="93aec-112">Open Report Manager, and locate the shared data source for which you want to view dependent items.</span></span>  
  
2.  <span data-ttu-id="93aec-113">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="93aec-113">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="93aec-114">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="93aec-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="93aec-115">Открывается страница «Общие свойства» источника данных.</span><span class="sxs-lookup"><span data-stu-id="93aec-115">This opens the General properties page for the data source.</span></span>  
  
4.  <span data-ttu-id="93aec-116">Перейдите на вкладку **Зависимые элементы** .</span><span class="sxs-lookup"><span data-stu-id="93aec-116">Select the **Dependent Items** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="93aec-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="93aec-117">Options</span></span>  
 <span data-ttu-id="93aec-118">**имя**;</span><span class="sxs-lookup"><span data-stu-id="93aec-118">**Name**</span></span>  
 <span data-ttu-id="93aec-119">Отображается имя отчета или модели.</span><span class="sxs-lookup"><span data-stu-id="93aec-119">Shows the name of the report or model.</span></span> <span data-ttu-id="93aec-120">Щелкните имя отчета для открытия.</span><span class="sxs-lookup"><span data-stu-id="93aec-120">Click the name of the report to open it.</span></span> <span data-ttu-id="93aec-121">Щелкните имя модели, чтобы открыть страницу ее свойств.</span><span class="sxs-lookup"><span data-stu-id="93aec-121">Click the name of the model to open its property pages.</span></span>  
  
 <span data-ttu-id="93aec-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="93aec-122">**Description**</span></span>  
 <span data-ttu-id="93aec-123">Отображается описание отчета или модели.</span><span class="sxs-lookup"><span data-stu-id="93aec-123">Shows the description of the report or model.</span></span>  
  
 <span data-ttu-id="93aec-124">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="93aec-124">**Delete**</span></span>  
 <span data-ttu-id="93aec-125">Нажмите, чтобы удалить отчет или модель из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="93aec-125">Click to delete the report or model from the report server database.</span></span> <span data-ttu-id="93aec-126">Перед нажатием кнопки **Удалить**установите флажок рядом с каждым элементом, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="93aec-126">Before clicking **Delete**, select the check box next to each item that you want to delete.</span></span>  
  
 <span data-ttu-id="93aec-127">**Перемещение**</span><span class="sxs-lookup"><span data-stu-id="93aec-127">**Move**</span></span>  
 <span data-ttu-id="93aec-128">Нажмите, чтобы переместить отчет или модель в иерархии папок.</span><span class="sxs-lookup"><span data-stu-id="93aec-128">Click to relocate a report or model within the folder hierarchy.</span></span> <span data-ttu-id="93aec-129">Перед нажатием кнопки **Переместить**установите флажок рядом с каждым элементом, который нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="93aec-129">Before clicking **Move**, select the check box next to each item that you want to move.</span></span> <span data-ttu-id="93aec-130">После этого открывается страница «Перемещение элементов», на которой можно просмотреть папки и выбрать новое местоположение.</span><span class="sxs-lookup"><span data-stu-id="93aec-130">This opens the Move Items page, where you can browse through folders to select a new location.</span></span>  
  
 <span data-ttu-id="93aec-131">**Правка**</span><span class="sxs-lookup"><span data-stu-id="93aec-131">**Edit**</span></span>  
 <span data-ttu-id="93aec-132">Щелкните значок свойств для открытия страницы «Свойства» отчета или модели.</span><span class="sxs-lookup"><span data-stu-id="93aec-132">Click the Property icon to access the property pages of a report, or model.</span></span>  
  
 <span data-ttu-id="93aec-133">**Тип**</span><span class="sxs-lookup"><span data-stu-id="93aec-133">**Type**</span></span>  
 <span data-ttu-id="93aec-134">Отображает значок типа элемента.</span><span class="sxs-lookup"><span data-stu-id="93aec-134">Shows the icon of the item type.</span></span>  
  
 <span data-ttu-id="93aec-135">**Дата изменения**</span><span class="sxs-lookup"><span data-stu-id="93aec-135">**Modified Date**</span></span>  
 <span data-ttu-id="93aec-136">Отображает дату и время последнего изменения отчета или модели.</span><span class="sxs-lookup"><span data-stu-id="93aec-136">Shows the date and time when the report or model was last modified.</span></span>  
  
 <span data-ttu-id="93aec-137">**Кем изменено**</span><span class="sxs-lookup"><span data-stu-id="93aec-137">**Modified By**</span></span>  
 <span data-ttu-id="93aec-138">Отображает имя пользователя, который последним изменил свойства элемента.</span><span class="sxs-lookup"><span data-stu-id="93aec-138">Shows the name of the user who last modified the item properties.</span></span>  
  
 <span data-ttu-id="93aec-139">**Время запуска**</span><span class="sxs-lookup"><span data-stu-id="93aec-139">**When Run**</span></span>  
 <span data-ttu-id="93aec-140">Для отчетов, которые выполняются в виде снимков состояния выполнения отчетов, отображаются дата и время последнего обновления отчета.</span><span class="sxs-lookup"><span data-stu-id="93aec-140">For reports that run as report execution snapshots, displays the date and time at which the report was last refreshed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93aec-141">См. также</span><span class="sxs-lookup"><span data-stu-id="93aec-141">See Also</span></span>  
 <span data-ttu-id="93aec-142">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="93aec-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="93aec-143">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="93aec-143">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="93aec-144">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="93aec-144">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="93aec-145">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="93aec-145">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
