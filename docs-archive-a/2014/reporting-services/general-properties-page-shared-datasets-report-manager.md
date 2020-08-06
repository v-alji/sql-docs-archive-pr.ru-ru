---
title: Страница «Общие свойства», общие наборы данных (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10798e41-24c3-4e69-893b-7ee6af7fc958
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 31825e61cb40505e9167cc2b930a5b79e5aaa013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669282"
---
# <a name="general-properties-page-shared-datasets-report-manager"></a><span data-ttu-id="dd9a9-102">Страница «Общие свойства» — «Общие наборы данных» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="dd9a9-102">General Properties Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="dd9a9-103">Страница «Общий набор данных» используется для просмотра и управления свойствами элемента общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-103">Use the Shared Dataset page to view and manage properties for a shared dataset item.</span></span>  
  
 <span data-ttu-id="dd9a9-104">Диспетчер отчетов не поддерживает просмотр или изменение определения общего набора данных, в том числе и запроса.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-104">From Report Manager, you cannot view or change the shared dataset definition, including the query.</span></span> <span data-ttu-id="dd9a9-105">Определение отчета необходимо изменить при помощи средства разработки, а затем сохранить на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-105">To change the definition, you must use an authoring tool to open and modify the definition and then save it to the report server.</span></span>  
  
 <span data-ttu-id="dd9a9-106">Общий набор данных позволяет управлять параметрами набора данных независимо от отчетов, компонентов и других элементов каталога, которые этот набор используют.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-106">With a shared dataset, you can manage the settings for a dataset separately from reports, components, and other catalog items that use it.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="dd9a9-107">Навигация</span><span class="sxs-lookup"><span data-stu-id="dd9a9-107">Navigation</span></span>  
 <span data-ttu-id="dd9a9-108">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-108">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-shared-dataset-properties-page-for-a-shared-dataset"></a><span data-ttu-id="dd9a9-109">Открытие страницы свойств общего набора данных для общего набора данных</span><span class="sxs-lookup"><span data-stu-id="dd9a9-109">To open the Shared Dataset properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="dd9a9-110">Откройте диспетчер отчетов и найдите общий набор данных, для которого необходимо настроить свойства.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-110">Open Report Manager, and locate shared dataset for which you want to configure properties.</span></span>  
  
2.  <span data-ttu-id="dd9a9-111">Подведите курсор к общему набору данных и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-111">Hover over the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="dd9a9-112">В раскрывающемся списке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-112">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="dd9a9-113">Откроется страница «Общие свойства».</span><span class="sxs-lookup"><span data-stu-id="dd9a9-113">The General properties page opens.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dd9a9-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd9a9-114">Options</span></span>  
 <span data-ttu-id="dd9a9-115">**имя**;</span><span class="sxs-lookup"><span data-stu-id="dd9a9-115">**Name**</span></span>  
 <span data-ttu-id="dd9a9-116">Введите имя общего набора данных, которое используется для идентификации элемента в иерархии папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-116">Type a name for the shared dataset that is used to identify the item within the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="dd9a9-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dd9a9-117">**Description**</span></span>  
 <span data-ttu-id="dd9a9-118">Введите сведения об общем наборе данных.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-118">Provide information about the shared dataset.</span></span> <span data-ttu-id="dd9a9-119">Данное описание приводится на странице «Содержимое».</span><span class="sxs-lookup"><span data-stu-id="dd9a9-119">This description appears on the Contents page.</span></span>  
  
 <span data-ttu-id="dd9a9-120">**Скрыть при отображении в виде списка**</span><span class="sxs-lookup"><span data-stu-id="dd9a9-120">**Hide in list view**</span></span>  
 <span data-ttu-id="dd9a9-121">Скройте общий набор данных от пользователей, которые работают в диспетчере отчетов в режиме списка.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-121">Hide the shared dataset from users who are using list view mode in Report Manager.</span></span> <span data-ttu-id="dd9a9-122">Режим списка — формат представления по умолчанию при обзоре иерархии папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-122">List view mode is the default view format when browsing the report server folder hierarchy.</span></span> <span data-ttu-id="dd9a9-123">В этом режиме имена элементов и описания выводятся на странице в виде списка.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-123">In list view, item names and descriptions flow across the page.</span></span> <span data-ttu-id="dd9a9-124">Альтернативный формат — представление в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-124">The alternative format is details view.</span></span> <span data-ttu-id="dd9a9-125">В этом формате описания не выводятся, но отображаются другие сведения об элементе.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-125">Details view omits descriptions, but includes other information about the item.</span></span> <span data-ttu-id="dd9a9-126">Элементы можно скрывать в формате списка, но нельзя скрывать в формате таблицы.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-126">Although you can hide an item in list view, you cannot hide an item in details view.</span></span> <span data-ttu-id="dd9a9-127">Чтобы ограничить доступ к элементу, необходимо создать назначение ролей.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-127">If you want to restrict access to an item, you must create a role assignment.</span></span>  
  
 <span data-ttu-id="dd9a9-128">**Время ожидания выполнения запроса**</span><span class="sxs-lookup"><span data-stu-id="dd9a9-128">**Query execution timeout**</span></span>  
 <span data-ttu-id="dd9a9-129">Введите количество секунд до истечения времени ожидания запроса. Если значение равно 0, время ожидания запроса не истекает.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-129">Type the number of seconds until the query times out. If it is 0, the query does not time out.</span></span>  
  
 <span data-ttu-id="dd9a9-130">**Применить**</span><span class="sxs-lookup"><span data-stu-id="dd9a9-130">**Apply**</span></span>  
 <span data-ttu-id="dd9a9-131">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-131">Save your changes.</span></span>  
  
 <span data-ttu-id="dd9a9-132">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="dd9a9-132">**Delete**</span></span>  
 <span data-ttu-id="dd9a9-133">Удалить общий набор данных из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-133">Remove the shared dataset from the report server database.</span></span> <span data-ttu-id="dd9a9-134">Удаление общего набора данных приводит к деактивации всех отчетов или кэшируемых версий.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-134">Deleting a shared dataset deactivates any reports or cached versions.</span></span> <span data-ttu-id="dd9a9-135">Чтобы снова активировать отчеты, необходимо открыть каждый из них в средстве разработки отчетов и указать набор данных с тем же именем и тем же набором полей.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-135">To reactivate a report, you must open each one in a report authoring tool, and specify a dataset with the same name and the same field collection.</span></span> <span data-ttu-id="dd9a9-136">Можно также обновить каждую ссылку на область данных, чтобы использовать другой набор данных с тем же набором полей.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-136">Alternatively, you can update each data region reference to use a different dataset with the same field collection.</span></span>  
  
 <span data-ttu-id="dd9a9-137">**Перемещение**</span><span class="sxs-lookup"><span data-stu-id="dd9a9-137">**Move**</span></span>  
 <span data-ttu-id="dd9a9-138">Перемещение общего набора данных в иерархии папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-138">Relocate a shared dataset within the report server folder hierarchy.</span></span> <span data-ttu-id="dd9a9-139">Нажатие этой кнопки открывает страницу «Перемещение элементов», на которой можно перейти к новому местонахождению папки.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-139">Clicking this button opens the Move Items page, on which you can browse through folders for a new folder location.</span></span> <span data-ttu-id="dd9a9-140">Дополнительные сведения см. в разделе [Страница "перемещение элементов" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/move-items-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dd9a9-140">For more information, see [Move Items Page &#40;Report Manager&#41;](../../2014/reporting-services/move-items-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="dd9a9-141">**Загрузить**</span><span class="sxs-lookup"><span data-stu-id="dd9a9-141">**Download**</span></span>  
 <span data-ttu-id="dd9a9-142">Извлечение копии определения общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-142">Extract a copy of the shared dataset definition.</span></span> <span data-ttu-id="dd9a9-143">В зависимости от того, как на компьютере сопоставлены файлы, файл откроется в среде Visual Studio или в другом приложении.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-143">Depending on the file associations defined on your computer, the file will open in Visual Studio or a different application.</span></span> <span data-ttu-id="dd9a9-144">Чаще всего общий набор данных открывается как XML-файл.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-144">In most cases, the shared dataset opens as an XML file.</span></span>  
  
 <span data-ttu-id="dd9a9-145">**Заменить**</span><span class="sxs-lookup"><span data-stu-id="dd9a9-145">**Replace**</span></span>  
 <span data-ttu-id="dd9a9-146">Замена одного определения общего набора данных другим из RSD-файла, находящегося в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="dd9a9-146">Replace the shared dataset definition with a different one from an .rsd file located on the file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd9a9-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd9a9-147">See Also</span></span>  
 <span data-ttu-id="dd9a9-148">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="dd9a9-148">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="dd9a9-149">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dd9a9-149">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="dd9a9-150">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="dd9a9-150">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="dd9a9-151">[Параметры обновления кэша &#40;диспетчер отчетов&#41;](../../2014/reporting-services/cache-refresh-options-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dd9a9-151">[Cache Refresh Options &#40;Report Manager&#41;](../../2014/reporting-services/cache-refresh-options-report-manager.md) </span></span>  
 <span data-ttu-id="dd9a9-152">[Страница кэширования, общие наборы данных &#40;диспетчер отчетов&#41;](../../2014/reporting-services/caching-page-shared-datasets-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dd9a9-152">[Caching Page, Shared Datasets &#40;Report Manager&#41;](../../2014/reporting-services/caching-page-shared-datasets-report-manager.md) </span></span>  
 <span data-ttu-id="dd9a9-153">[Управление общими наборами данных](report-data/manage-shared-datasets.md) </span><span class="sxs-lookup"><span data-stu-id="dd9a9-153">[Manage Shared Datasets](report-data/manage-shared-datasets.md) </span></span>  
 [<span data-ttu-id="dd9a9-154">Общие наборы данных в кэше (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="dd9a9-154">Cache Shared Datasets &#40;SSRS&#41;</span></span>](report-server/cache-shared-datasets-ssrs.md)  
  
  
