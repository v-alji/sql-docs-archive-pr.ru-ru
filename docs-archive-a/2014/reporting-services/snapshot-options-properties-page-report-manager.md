---
title: Страница "Свойства параметров моментального снимка" (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f6641f59-5267-4f57-8957-63b93d1a9679
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3025b23dfe498a92c2ce1d8535229d8d23dfd429
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729013"
---
# <a name="snapshot-options-properties-page-report-manager"></a><span data-ttu-id="7356d-102">Страница «Свойства параметров моментального снимка» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="7356d-102">Snapshot Options Properties Page (Report Manager)</span></span>
  <span data-ttu-id="7356d-103">На странице свойств «Параметры моментального снимка» можно составить расписание добавления моментальных снимков отчетов в журнал отчетов и установить предел количества снимков отчетов, хранимых в журнале отчетов.</span><span class="sxs-lookup"><span data-stu-id="7356d-103">Use the Snapshot Options properties page to schedule report snapshots to be added to report history, and to set limits on the number of report snapshots that are stored in report history.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7356d-104">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7356d-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7356d-105">Список функций, поддерживаемых различными выпусками [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , см. в разделе [Дополнительные службы баз данных](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span><span class="sxs-lookup"><span data-stu-id="7356d-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Additional Database Services](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="7356d-106">Навигация</span><span class="sxs-lookup"><span data-stu-id="7356d-106">Navigation</span></span>  
 <span data-ttu-id="7356d-107">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="7356d-107">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-snapshot-options-properties-page-for-a-report"></a><span data-ttu-id="7356d-108">Открытие страницы свойств отчета «Параметры моментального снимка»</span><span class="sxs-lookup"><span data-stu-id="7356d-108">To open the Snapshot Options properties page for a report</span></span>  
  
1.  <span data-ttu-id="7356d-109">Откройте диспетчер отчетов и найдите отчет, для которого необходимо настроить свойства параметров моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="7356d-109">Open Report Manager, and locate the report for which you want to configure report snapshot properties.</span></span>  
  
2.  <span data-ttu-id="7356d-110">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7356d-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="7356d-111">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="7356d-111">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="7356d-112">Откроется страница свойств отчета «Общие».</span><span class="sxs-lookup"><span data-stu-id="7356d-112">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="7356d-113">Выберите вкладку **Параметры моментального снимка** .</span><span class="sxs-lookup"><span data-stu-id="7356d-113">Select the **Snapshot Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7356d-114">Варианты</span><span class="sxs-lookup"><span data-stu-id="7356d-114">Options</span></span>  
 <span data-ttu-id="7356d-115">**Разрешить создание журнала отчетов вручную**</span><span class="sxs-lookup"><span data-stu-id="7356d-115">**Allow report history to be created manually**</span></span>  
 <span data-ttu-id="7356d-116">Установите этот флажок, чтобы добавлять моментальные снимки в журнал отчета по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="7356d-116">Select this check box to add snapshots to report history as needed.</span></span> <span data-ttu-id="7356d-117">Установка флажка приведет к появлению кнопки **Создать моментальный снимок** на странице журнала.</span><span class="sxs-lookup"><span data-stu-id="7356d-117">Selecting this check box causes the **New Snapshot** button to appear on the History page.</span></span>  
  
 <span data-ttu-id="7356d-118">**Сохранять все моментальные снимки состояния выполнения отчета в журнале отчетов**</span><span class="sxs-lookup"><span data-stu-id="7356d-118">**Store all report execution snapshots in report history**</span></span>  
 <span data-ttu-id="7356d-119">Установите этот флажок, чтобы скопировать моментальный снимок отчета, сформированный на основе свойств выполнения отчетов в журнал отчетов.</span><span class="sxs-lookup"><span data-stu-id="7356d-119">Select this check box to copy a report snapshot that you generate based on report execution properties to report history.</span></span> <span data-ttu-id="7356d-120">Можно установить свойства выполнения отчетов для запуска отчета из созданного моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="7356d-120">You can set report execution properties to run a report from a generated snapshot.</span></span> <span data-ttu-id="7356d-121">Настраивая это свойство журнала отчетов, можно хранить запись всех созданных моментальных снимков отчетов, размещая их копии в журнале отчетов.</span><span class="sxs-lookup"><span data-stu-id="7356d-121">By setting this report history property, you can keep a record of all reports snapshots that are generated over time by placing copies of them in report history.</span></span>  
  
 <span data-ttu-id="7356d-122">**Чтобы добавлять моментальные снимки в журнал отчета, воспользуйтесь следующим расписанием**</span><span class="sxs-lookup"><span data-stu-id="7356d-122">**Use the following schedule to add snapshots to report history**</span></span>  
 <span data-ttu-id="7356d-123">Установите этот флажок, чтобы добавлять моментальные снимки в журнал отчетов по расписанию.</span><span class="sxs-lookup"><span data-stu-id="7356d-123">Select this check box to add snapshots to report history on a scheduled basis.</span></span> <span data-ttu-id="7356d-124">Можно создать расписание специально для этой цели или выбрать предопределенное общее расписание, если оно содержит необходимые данные.</span><span class="sxs-lookup"><span data-stu-id="7356d-124">You can create a schedule that is used exclusively for this purpose, or you can select a predefined shared schedule if one contains the schedule information you want.</span></span>  
  
 <span data-ttu-id="7356d-125">**Выберите количество моментальных снимков, которые следует оставить**</span><span class="sxs-lookup"><span data-stu-id="7356d-125">**Select the number of snapshots to keep**</span></span>  
 <span data-ttu-id="7356d-126">Чтобы контролировать число отчетов, хранимых в журнале отчетов, выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="7356d-126">Select from the following options to control the number of reports that are kept in report history.</span></span> <span data-ttu-id="7356d-127">Настройки журнала отчетов могут различаться для каждого отчета.</span><span class="sxs-lookup"><span data-stu-id="7356d-127">Report history settings can vary for each report.</span></span>  
  
-   <span data-ttu-id="7356d-128">Чтобы восстановить настройки по умолчанию, выберите **Использовать настройку по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="7356d-128">Select **Use default setting** to retain the default setting.</span></span> <span data-ttu-id="7356d-129">Администратор сервера отчетов контролирует главные настройки хранилища журнала отчетов.</span><span class="sxs-lookup"><span data-stu-id="7356d-129">The report server administrator controls a master setting for report history storage.</span></span> <span data-ttu-id="7356d-130">При выборе этого параметра число хранимых моментальных снимков берется из главных настроек.</span><span class="sxs-lookup"><span data-stu-id="7356d-130">If you choose this option, the number of snapshots that are retained is obtained from this master setting.</span></span>  
  
-   <span data-ttu-id="7356d-131">Для хранения всех моментальных снимков журнала отчетов выберите **Хранить в журнале отчета неограниченное количество моментальных снимков** .</span><span class="sxs-lookup"><span data-stu-id="7356d-131">Select **Keep an unlimited number of snapshots in report history** to retain all report history snapshots.</span></span> <span data-ttu-id="7356d-132">Для уменьшения размера журнала отчетов моментальные снимки нужно удалять вручную.</span><span class="sxs-lookup"><span data-stu-id="7356d-132">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
-   <span data-ttu-id="7356d-133">Чтобы сохранять указанное число моментальных снимков, выберите **Ограничить количество копий журнала отчета** .</span><span class="sxs-lookup"><span data-stu-id="7356d-133">Select **Limit the copies of report history** to retain a set number of snapshots.</span></span> <span data-ttu-id="7356d-134">По достижении предела старые копии будут удаляться из журнала отчетов, чтобы освободить место для новых.</span><span class="sxs-lookup"><span data-stu-id="7356d-134">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="7356d-135">Журнал отчета хранится в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7356d-135">Report history is stored in the report server database.</span></span> <span data-ttu-id="7356d-136">Если имеются отчеты большого размера или большое число отчетов, для которых необходимо ведение журналов, подумайте об ограничении объема журналов отчета, чтобы снизить требования к месту на диске в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7356d-136">If you have large reports or numerous reports for which you want to maintain history, consider limiting the amount of report history to help manage the disk space requirements of the report server database.</span></span>  
  
 <span data-ttu-id="7356d-137">**Применить**</span><span class="sxs-lookup"><span data-stu-id="7356d-137">**Apply**</span></span>  
 <span data-ttu-id="7356d-138">Щелкните, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="7356d-138">Click to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7356d-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="7356d-139">See Also</span></span>  
 <span data-ttu-id="7356d-140">[Добавление моментального снимка в журнал отчета &#40;диспетчер отчетов&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="7356d-140">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="7356d-141">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="7356d-141">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="7356d-142">[Создание, изменение и удаление моментальных снимков в журнале отчетов](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span><span class="sxs-lookup"><span data-stu-id="7356d-142">[Create, Modify, and Delete Snapshots in Report History](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span></span>  
 [<span data-ttu-id="7356d-143">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="7356d-143">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
