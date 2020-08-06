---
title: Добавление моментального снимка к журналу отчета (диспетчер отчетов) | Документы Майкрософт
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
helpviewer_keywords:
- report history [Reporting Services], adding snapshots
- historical data [Reporting Services]
- snapshots [Reporting Services], adding report snapshots
- adding snapshots to report history
- report snapshots [Reporting Services], adding
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 84d4c264ab0b82fca2a34e6356b53113d63e6994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665845"
---
# <a name="add-a-snapshot-to-report-history-report-manager"></a><span data-ttu-id="bf1f2-102">добавить моментальный снимок к журналу отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="bf1f2-102">Add a Snapshot to Report History (Report Manager)</span></span>

<span data-ttu-id="bf1f2-103">Журнал отчета — это коллекция моментальных снимков отчета, созданных на протяжении определенного времени.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="bf1f2-104">Моментальный снимок отчета — это отчет, содержащий сведения о макете и результаты запроса, полученные в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-104">A report snapshot is a report that contains layout information and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="bf1f2-105">В отличие от отчетов по требованию, при открытии которых производится получение актуальных, действительных на текущий момент данных, моментальные снимки отчета выполняются по расписанию и сохраняются на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-105">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="bf1f2-106">Если для просмотра выбирается моментальный снимок отчета, сервер отчетов извлекает сохраненный отчет из базы данных сервера отчетов и отображает макет и данные, которые были действительны на момент создания моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-106">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
<span data-ttu-id="bf1f2-107">Моментальные снимки отчета не сохраняются в каком-то определенном формате отображения,</span><span class="sxs-lookup"><span data-stu-id="bf1f2-107">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="bf1f2-108">а преобразуются в него (например, в HTML) только при запросе пользователя или приложения.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-108">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="bf1f2-109">Отложенное форматирование делает моментальные снимки отчетов переносимыми,</span><span class="sxs-lookup"><span data-stu-id="bf1f2-109">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="bf1f2-110">поскольку отчет может быть сформирован для просмотра в формате, необходимом для веб-браузера или другого устройства отображения.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-110">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
## <a name="to-manually-add-snapshots-to-report-history"></a><span data-ttu-id="bf1f2-111">Добавление моментальных снимков в журнал отчета вручную</span><span class="sxs-lookup"><span data-stu-id="bf1f2-111">To manually add snapshots to report history</span></span>

1. <span data-ttu-id="bf1f2-112">В диспетчере отчетов перейдите на страницу **Оглавление** , наведите курсор на элемент, журнал которого необходимо просмотреть, и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-112">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>
  
2. <span data-ttu-id="bf1f2-113">В раскрывающемся меню выберите **Просмотр журнала отчета**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-113">In the drop-down menu, click **View Report History**.</span></span>  
  
3. <span data-ttu-id="bf1f2-114">Выберите **Создать моментальный снимок**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-114">Click **New Snapshot**.</span></span> <span data-ttu-id="bf1f2-115">Новый моментальный снимок будет создан в столбце **Время запуска** .</span><span class="sxs-lookup"><span data-stu-id="bf1f2-115">A new snapshot is created in the **When Run** column.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="bf1f2-116">Для данной задачи администратор должен выбрать **Разрешить создание журнала вручную**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-116">In order to do this, the report history must be configured by the administrator to **Allow history to be created manually**.</span></span> <span data-ttu-id="bf1f2-117">Дополнительные сведения см. в разделе [Ограничение размеров журнала отчета (диспетчер отчетов)](../reports/limit-report-history-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="bf1f2-117">For more information, see [Limit Report History &#40;Report Manager&#41;](../reports/limit-report-history-report-manager.md).</span></span>

4. <span data-ttu-id="bf1f2-118">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-118">Click **Apply**.</span></span>

## <a name="to-automatically-add-all-snapshots-to-report-history"></a><span data-ttu-id="bf1f2-119">Автоматическое добавление всех моментальных снимков в журнал отчета</span><span class="sxs-lookup"><span data-stu-id="bf1f2-119">To automatically add all snapshots to report history</span></span>  
  
1. <span data-ttu-id="bf1f2-120">Для отчета, который уже настроен для работы в качестве снимка состояния выполнения отчета, можно установить дополнительные свойства, чтобы сохранять копию моментального снимка в журнал отчета каждый раз при обновлении моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-120">For a report that is already configured to run as a report execution snapshot, you can set additional properties to save a copy of the snapshot to report history each time the snapshot is refreshed.</span></span>  
  
2. <span data-ttu-id="bf1f2-121">В диспетчере отчетов перейдите на страницу **Оглавление** , наведите курсор на элемент, журнал которого необходимо просмотреть, и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-121">In Report Manager, navigate to the **Contents** page, hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
3. <span data-ttu-id="bf1f2-122">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-122">In the drop-down menu, click **Manage**.</span></span>  
  
4. <span data-ttu-id="bf1f2-123">Выберите пункт **Параметры моментального снимка**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-123">Click **Snapshot Options**.</span></span>  
  
5. <span data-ttu-id="bf1f2-124">Установите флажок **Хранить в журнале все снимки состояния выполнения отчета**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-124">Select the check box for **Store all report execution snapshots in history**.</span></span>  
  
6. <span data-ttu-id="bf1f2-125">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-125">Click **Apply**.</span></span>  
  
### <a name="to-automatically-add-snapshots-to-report-history-based-on-a-schedule"></a><span data-ttu-id="bf1f2-126">Автоматическое добавление моментальных снимков в журнал отчета на основе расписания</span><span class="sxs-lookup"><span data-stu-id="bf1f2-126">To automatically add snapshots to report history based on a schedule</span></span>  
  
1. <span data-ttu-id="bf1f2-127">В диспетчере отчетов перейдите на страницу **Оглавление** , наведите курсор на элемент, журнал которого необходимо просмотреть, и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-127">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
2. <span data-ttu-id="bf1f2-128">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-128">In the drop-down menu, click **Manage**.</span></span>  
  
3. <span data-ttu-id="bf1f2-129">Выберите пункт **Параметры моментального снимка**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-129">Click **Snapshot Options**.</span></span>  
  
4. <span data-ttu-id="bf1f2-130">Установите флажок **Применить следующее расписание для добавления моментальных снимков в журнал отчета**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-130">Select the check box for **Use the following schedule to add snapshots to report history**.</span></span> <span data-ttu-id="bf1f2-131">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="bf1f2-131">Perform one of the following:</span></span>  
  
    - <span data-ttu-id="bf1f2-132">Выберите **Расписание отчета**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-132">Select **Report-specific schedule**.</span></span> <span data-ttu-id="bf1f2-133">Укажите параметры расписания, начальную и конечную даты расписания и нажмите кнопку **ОК**;</span><span class="sxs-lookup"><span data-stu-id="bf1f2-133">Fill in the schedule details, select the start and end dates for the schedule, and then click **OK**.</span></span>  
  
    - <span data-ttu-id="bf1f2-134">выберите **Общее расписание**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-134">Select **Shared schedule**.</span></span> <span data-ttu-id="bf1f2-135">Выберите из списка желаемое расписание.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-135">From the list, select the preferred schedule.</span></span>  
  
5. <span data-ttu-id="bf1f2-136">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="bf1f2-136">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf1f2-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf1f2-137">See Also</span></span>

- [<span data-ttu-id="bf1f2-138">Настройка свойств выполнения для отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="bf1f2-138">Configure Execution Properties for a Report  &#40;Report Manager&#41;</span></span>](../reports/configure-execution-properties-for-a-report-report-manager.md)
- [<span data-ttu-id="bf1f2-139">Открытие и закрытие отчетов (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="bf1f2-139">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)
- [<span data-ttu-id="bf1f2-140">Ограничение размеров журнала отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="bf1f2-140">Limit Report History &#40;Report Manager&#41;</span></span>](../reports/limit-report-history-report-manager.md)
- [<span data-ttu-id="bf1f2-141">Расписания</span><span class="sxs-lookup"><span data-stu-id="bf1f2-141">Schedules</span></span>](../subscriptions/schedules.md)   
- [<span data-ttu-id="bf1f2-142">Диспетчер отчетов (службы Reporting Services в основном режиме)</span><span class="sxs-lookup"><span data-stu-id="bf1f2-142">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)