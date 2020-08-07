---
title: Перемещение или удаление элемента (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- moving items
- items [Reporting Services], moving
ms.assetid: 980a66c7-a18b-4af7-8954-45726fa517d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a61ad56ea9e20e7fdf38d5acf05529b685ee896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727925"
---
# <a name="move-or-delete-an-item-report-manager"></a><span data-ttu-id="3f775-102">Перемещение или удаление элемента (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="3f775-102">Move or Delete an Item (Report Manager)</span></span>
  <span data-ttu-id="3f775-103">Отчеты и связанные с ними элементы, публикуемые на сервере отчетов, хранятся в папках.</span><span class="sxs-lookup"><span data-stu-id="3f775-103">Reports and report-related items that you publish to a report server are stored in folders.</span></span> <span data-ttu-id="3f775-104">Элементы можно переместить в другую папку; ссылки на эти элементы будут автоматически обновлены на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="3f775-104">You can move items to a different folder and references to those items are maintained automatically by the report server.</span></span> <span data-ttu-id="3f775-105">Прежде чем удалить какой-либо элемент, определите, не зависят ли от него другие элементы.</span><span class="sxs-lookup"><span data-stu-id="3f775-105">Before you delete an item, consider whether other items depend on it.</span></span>  
  
## <a name="move-an-item"></a><span data-ttu-id="3f775-106">переместить элемент</span><span class="sxs-lookup"><span data-stu-id="3f775-106">Move an Item</span></span>  
 <span data-ttu-id="3f775-107">Элементы сервера отчетов можно перемещать в другие папки в иерархии папок в сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="3f775-107">You can move report server items to different folder locations in the report server folder hierarchy.</span></span> <span data-ttu-id="3f775-108">При перемещении элемента все его свойства (включая параметры безопасности) перемещаются на новое место вместе с ним.</span><span class="sxs-lookup"><span data-stu-id="3f775-108">When you move an item, all properties (including security settings) move with the item to the new location.</span></span> <span data-ttu-id="3f775-109">При перемещении папки вместе с ней перемещаются все находящиеся в ней элементы.</span><span class="sxs-lookup"><span data-stu-id="3f775-109">When you move a folder, all the items in the folder move with it.</span></span>  
  
 <span data-ttu-id="3f775-110">В иерархии папок диспетчера отчетов отмечены элементы, которые могут быть перемещены.</span><span class="sxs-lookup"><span data-stu-id="3f775-110">In Report Manager, the items that you can move are indicated in the folder hierarchy.</span></span> <span data-ttu-id="3f775-111">В следующей таблице показаны значки для каждого из элементов, доступных для перемещения.</span><span class="sxs-lookup"><span data-stu-id="3f775-111">The following table shows the icon for each movable item.</span></span>  
  
|<span data-ttu-id="3f775-112">Значок</span><span class="sxs-lookup"><span data-stu-id="3f775-112">Icon</span></span>|<span data-ttu-id="3f775-113">Перемещаемый элемент</span><span class="sxs-lookup"><span data-stu-id="3f775-113">Moveable item</span></span>|  
|----------|-------------------|  
|<span data-ttu-id="3f775-114">![Report icon](../media/hlp-16doc.gif "Значок отчета")</span><span class="sxs-lookup"><span data-stu-id="3f775-114">![Report icon](../media/hlp-16doc.gif "Report icon")</span></span>|<span data-ttu-id="3f775-115">Report</span><span class="sxs-lookup"><span data-stu-id="3f775-115">Report</span></span>|  
|<span data-ttu-id="3f775-116">![Значок связанного отчета](../media/hlp-16linked.gif "Значок связанного отчета")</span><span class="sxs-lookup"><span data-stu-id="3f775-116">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>|<span data-ttu-id="3f775-117">Связанный отчет</span><span class="sxs-lookup"><span data-stu-id="3f775-117">Linked report</span></span>|  
|<span data-ttu-id="3f775-118">![Значок папки](../media/hlp-16folder.gif "Значок папки")</span><span class="sxs-lookup"><span data-stu-id="3f775-118">![Folder icon](../media/hlp-16folder.gif "Folder icon")</span></span>|<span data-ttu-id="3f775-119">Папка</span><span class="sxs-lookup"><span data-stu-id="3f775-119">Folder</span></span>|  
|<span data-ttu-id="3f775-120">![универсальный значок ресурса](../media/hlp-16file.gif "универсальный значок ресурса")</span><span class="sxs-lookup"><span data-stu-id="3f775-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon")</span></span>|<span data-ttu-id="3f775-121">Ресурс</span><span class="sxs-lookup"><span data-stu-id="3f775-121">Generic resource</span></span>|  
|<span data-ttu-id="3f775-122">![Shared data source icon](../media/hlp-16datasource.png "Значок общего источника данных")</span><span class="sxs-lookup"><span data-stu-id="3f775-122">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>|<span data-ttu-id="3f775-123">Общий источник данных</span><span class="sxs-lookup"><span data-stu-id="3f775-123">Shared data source</span></span>|  
||<span data-ttu-id="3f775-124">Общий набор данных</span><span class="sxs-lookup"><span data-stu-id="3f775-124">Shared dataset</span></span>|  
  
 <span data-ttu-id="3f775-125">Могут быть перемещены не все элементы.</span><span class="sxs-lookup"><span data-stu-id="3f775-125">Not all items that you work with can be moved.</span></span> <span data-ttu-id="3f775-126">Например, нельзя переместить элемент, связанный с отчетом: подписку или журнал отчета.</span><span class="sxs-lookup"><span data-stu-id="3f775-126">You cannot move items that are associated with a report, such as subscriptions or report history.</span></span> <span data-ttu-id="3f775-127">Такие элементы перемещаются вместе с отчетами, к которым они относятся.</span><span class="sxs-lookup"><span data-stu-id="3f775-127">Those items move with their associated reports.</span></span> <span data-ttu-id="3f775-128">Также нельзя перемещать элементы, которые существуют вне иерархии папок (например, общие расписания).</span><span class="sxs-lookup"><span data-stu-id="3f775-128">Similarly, you cannot move items, such as shared schedules, that exist outside of the folder hierarchy.</span></span> <span data-ttu-id="3f775-129">Перемещение элементов невозможно, если на это недостаточно разрешений.</span><span class="sxs-lookup"><span data-stu-id="3f775-129">You cannot move items if you lack permission to do so.</span></span> <span data-ttu-id="3f775-130">Разрешение на перемещение элемента имеется, если для соответствующего элемента в назначении ролей выбраны следующие задачи: «Управление отчетами», «Управление моделями», «Управление папками» и «Управление источниками данных».</span><span class="sxs-lookup"><span data-stu-id="3f775-130">Permission to move an item is conveyed when the following tasks are selected in your role assignment for the item in question: "Manage reports," "Manage models", "Manage folders," and "Manage data sources."</span></span>  
  
#### <a name="to-move-an-item-from-within-the-contents-page"></a><span data-ttu-id="3f775-131">Перемещение элемента со страницы «Содержимое»</span><span class="sxs-lookup"><span data-stu-id="3f775-131">To move an item from within the Contents page</span></span>  
  
1.  <span data-ttu-id="3f775-132">Start [диспетчер отчетов &#40;служб SSRS в собственном режиме&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3f775-132">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="3f775-133">В диспетчере отчетов перейдите на страницу **Содержимое** и найдите элемент, который необходимо переместить.</span><span class="sxs-lookup"><span data-stu-id="3f775-133">In Report Manager, navigate to the **Contents** page, and locate the item that you want to move.</span></span>  
  
3.  <span data-ttu-id="3f775-134">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="3f775-134">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="3f775-135">В раскрывающемся меню выберите **Переместить**.</span><span class="sxs-lookup"><span data-stu-id="3f775-135">In the drop-down menu, click **Move**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="3f775-136">В окне **Расположение**выберите папку, в которую необходимо переместить элемент.</span><span class="sxs-lookup"><span data-stu-id="3f775-136">For **Location**, specify the folder you want to move the item to.</span></span> <span data-ttu-id="3f775-137">Можно ввести полный путь к папке, либо использовать средство просмотра дерева каталогов.</span><span class="sxs-lookup"><span data-stu-id="3f775-137">You can type the fully qualified folder name or use the tree control to navigate to the folder.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="3f775-138">Либо можно выбрать объект, который необходимо переместить, щелкнуть **Свойства**, а затем щелкнуть вкладку **Переместить** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="3f775-138">Alternatively, you can navigate to the object you want to move, click **Properties**, and then click **Move** at the top of the page.</span></span>  
  
## <a name="delete-an-item"></a><span data-ttu-id="3f775-139">Удаление элемента</span><span class="sxs-lookup"><span data-stu-id="3f775-139">Delete an item</span></span>  
 <span data-ttu-id="3f775-140">Прежде чем удалить какой-либо элемент, следует проверить, не используется ли он другими элементами.</span><span class="sxs-lookup"><span data-stu-id="3f775-140">Before you delete an item, determine if it is used by other items.</span></span> <span data-ttu-id="3f775-141">Например, удаление общего источника данных приведет к тому, что отчеты и модели, которые используют этот источник данных, больше не будут запускаться.</span><span class="sxs-lookup"><span data-stu-id="3f775-141">For example, if you delete a shared data source, reports and models that use that data source will no longer run.</span></span> <span data-ttu-id="3f775-142">В случае удаления отчета удаляются также подписки и журнал отчета, связанные с этим отчетом.</span><span class="sxs-lookup"><span data-stu-id="3f775-142">If you delete a report, subscriptions and report history associated with that report are also deleted.</span></span> <span data-ttu-id="3f775-143">Чтобы найти зависимые элементы для элемента, см. раздел [страница зависимых элементов &#40;диспетчер отчетов&#41;]. /dependent-items-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="3f775-143">To find dependent items for an item, see [Dependent Items Page &#40;Report Manager&#41;]../dependent-items-page-report-manager.md).</span></span>  
  
#### <a name="to-delete-a-report-or-item"></a><span data-ttu-id="3f775-144">Удаление отчета или элемента</span><span class="sxs-lookup"><span data-stu-id="3f775-144">To delete a report or item</span></span>  
  
1.  <span data-ttu-id="3f775-145">Start [диспетчер отчетов &#40;служб SSRS в собственном режиме&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3f775-145">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="3f775-146">В диспетчере отчетов перейдите на страницу **Содержимое** и найдите элемент, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="3f775-146">In Report Manager, navigate to the **Contents** page, and locate the item that you want to delete.</span></span>  
  
3.  <span data-ttu-id="3f775-147">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="3f775-147">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="3f775-148">В раскрывающемся меню выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3f775-148">In the drop-down menu, click **Delete**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f775-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f775-149">See Also</span></span>  
 <span data-ttu-id="3f775-150">[Страница "содержимое" &#40;диспетчер отчетов&#41;].. /contents-page-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="3f775-150">[Contents Page &#40;Report Manager&#41;]../contents-page-report-manager.md)</span></span>   
 [<span data-ttu-id="3f775-151">Поиск, просмотр отчетов и управление ими (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3f775-151">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
