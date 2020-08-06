---
title: Приостановка и возобновление общих расписаний | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- report-specific schedules [Reporting Services]
- shared schedules [Reporting Services], resuming
- resuming schedules
- continuing schedules
- schedules [Reporting Services], resuming
- schedules [Reporting Services], pausing
ms.assetid: e416be75-5234-4aa6-a3de-77f60f25169a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f525a15b07b79b5c0d37f9a88ed9483b351af326
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664681"
---
# <a name="pause-and-resume-shared-schedules"></a><span data-ttu-id="fec50-102">Приостановка и возобновление общих расписаний</span><span class="sxs-lookup"><span data-stu-id="fec50-102">Pause and Resume Shared Schedules</span></span>
  <span data-ttu-id="fec50-103">Можно приостановить и возобновить общее расписание, используемое в данное время.</span><span class="sxs-lookup"><span data-stu-id="fec50-103">You can pause and resume a shared schedule that is in use.</span></span> <span data-ttu-id="fec50-104">Приостановка выполнения общего расписания позволяет временно приостановить действие расписания, инициирующего обработку отчетов и подписок.</span><span class="sxs-lookup"><span data-stu-id="fec50-104">Pausing a shared schedule provides a way to temporarily freeze a schedule that is used to trigger report processing and subscriptions.</span></span> <span data-ttu-id="fec50-105">Приостанавливать и возобновлять можно только общие расписания.</span><span class="sxs-lookup"><span data-stu-id="fec50-105">Only shared schedules can be paused and resumed.</span></span> <span data-ttu-id="fec50-106">Расписания конкретных отчетов приостанавливать нельзя.</span><span class="sxs-lookup"><span data-stu-id="fec50-106">You cannot pause report-specific schedules.</span></span>  
  
 <span data-ttu-id="fec50-107">Нельзя приостанавливать и возобновлять обработку отчетов, которая выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="fec50-107">You cannot pause and resume report processing that is in progress.</span></span> <span data-ttu-id="fec50-108">Приостанавливать и возобновлять можно лишь расписания, находящиеся в очереди расписаний службы агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fec50-108">You can only pause and resume schedules that are in the scheduling queue of SQL Server Agent service.</span></span> <span data-ttu-id="fec50-109">Подсистема расписаний не может управлять выполняемыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="fec50-109">A job that is in progress is outside the scope of the scheduling engine.</span></span> <span data-ttu-id="fec50-110">Дополнительные сведения см. в разделе [Управление запущенным процессом](manage-a-running-process.md).</span><span class="sxs-lookup"><span data-stu-id="fec50-110">For more information, see [Manage a Running Process](manage-a-running-process.md)</span></span>  
  
 <span data-ttu-id="fec50-111">Пока общее расписание приостановлено, все операции, которые должны были произойти, прекращаются.</span><span class="sxs-lookup"><span data-stu-id="fec50-111">While a shared schedule is paused, any operations that would have occurred are allowed to lapse.</span></span> <span data-ttu-id="fec50-112">После возобновления общего расписания обработка отчетов и подписок начнется в следующее указанное в расписании время, при этом используется локальное время сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fec50-112">After you resume a shared schedule, report and subscription processing occurs at the next scheduled time, using the local time of the server.</span></span> <span data-ttu-id="fec50-113">Сервер отчетов, работающий в собственном режиме, или приложения служб SharePoint не составляют запланированные операции, которые выполнялись бы, если бы расписание не было приостановлено.</span><span class="sxs-lookup"><span data-stu-id="fec50-113">The native mode report server or SharePoint service applications, do not make up scheduled operations that would have occurred had the schedule not been paused.</span></span>  
  
 <span data-ttu-id="fec50-114">В этом разделе.</span><span class="sxs-lookup"><span data-stu-id="fec50-114">In this Topic:</span></span>  
  
-   [<span data-ttu-id="fec50-115">Приостановка и возобновление общих расписаний (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="fec50-115">Pause and Resume Shared Schedules (Native Mode)</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="fec50-116">Приостановка и возобновление общих расписаний (режим интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="fec50-116">Pause and Resume Shared Schedules (SharePoint mode)</span></span>](#bkmk_sharepoint)  
  
##  <a name="pause-and-resume-shared-schedules-native-mode"></a><a name="bkmk_native"></a> <span data-ttu-id="fec50-117">Приостановка и возобновление общих расписаний (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="fec50-117">Pause and Resume Shared Schedules (Native Mode)</span></span>  
 <span data-ttu-id="fec50-118">Чтобы приостанавливать и возобновлять выполнение общих расписаний, используйте страницу «Общие расписания» диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fec50-118">To pause and resume a shared schedule, use the Schedules page in Report Manager.</span></span> <span data-ttu-id="fec50-119">В среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] это невозможно, она не предоставляет возможность приостанавливать и возобновлять выполнение расписаний.</span><span class="sxs-lookup"><span data-stu-id="fec50-119">You cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]; it does not provide options for pausing and resuming schedules.</span></span> <span data-ttu-id="fec50-120">Дополнительные сведения см. в статье [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="fec50-120">For more information, see [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="fec50-121">Остановка и возобновление общего расписания</span><span class="sxs-lookup"><span data-stu-id="fec50-121">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="fec50-122">В диспетчере отчетов щелкните **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="fec50-122">From Report Manager Click, **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="fec50-123">Нажмите кнопку **Расписания**.</span><span class="sxs-lookup"><span data-stu-id="fec50-123">Click **Schedules**.</span></span>  
  
3.  <span data-ttu-id="fec50-124">Выберите расписание и на ленте нажмите кнопку **Приостановить** или **Возобновить** .</span><span class="sxs-lookup"><span data-stu-id="fec50-124">Select the schedule, and click **Pause** or **Resume** in the ribbon.</span></span> <span data-ttu-id="fec50-125">Если в настоящее время расписание приостановлено, то в столбце **Состояние** будет указано **Приостановлено**.</span><span class="sxs-lookup"><span data-stu-id="fec50-125">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
##  <a name="pause-and-resume-shared-schedules-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="fec50-126">Приостановка и возобновление общих расписаний (режим интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="fec50-126">Pause and Resume Shared Schedules (SharePoint mode)</span></span>  
 <span data-ttu-id="fec50-127">Для приостановки и возобновление общего расписания используется страница «Параметры сайта» или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fec50-127">To pause and resume a shared schedule, use the Site Settings page or PowerShell.</span></span> <span data-ttu-id="fec50-128">Управление расписаниями выполняется для каждого сайта SharePoint отдельно.</span><span class="sxs-lookup"><span data-stu-id="fec50-128">Schedules are managed per SharePoint site.</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="fec50-129">Остановка и возобновление общего расписания</span><span class="sxs-lookup"><span data-stu-id="fec50-129">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="fec50-130">Щелкните **Действия сайта**.</span><span class="sxs-lookup"><span data-stu-id="fec50-130">Click **Site Actions**.</span></span>  
  
2.  <span data-ttu-id="fec50-131">Щелкните элемент **Настройки сайта**.</span><span class="sxs-lookup"><span data-stu-id="fec50-131">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="fec50-132">В разделе служб Reporting Services щелкните **Управление общими расписаниями**.</span><span class="sxs-lookup"><span data-stu-id="fec50-132">In the Reporting Services section, click **Manage Shared Schedules**.</span></span>  
  
4.  <span data-ttu-id="fec50-133">Выберите расписание, затем нажмите кнопку **Приостановить выбранные расписания** или **Запустить выбранные расписания**.</span><span class="sxs-lookup"><span data-stu-id="fec50-133">Select the schedule, and click **Pause Selected Schedules** or **Run Selected Schedules**.</span></span> <span data-ttu-id="fec50-134">Если в настоящее время расписание приостановлено, то в столбце **Состояние** будет указано **Приостановлено**.</span><span class="sxs-lookup"><span data-stu-id="fec50-134">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec50-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="fec50-135">See Also</span></span>  
 <span data-ttu-id="fec50-136">[Расписания](schedules.md) </span><span class="sxs-lookup"><span data-stu-id="fec50-136">[Schedules](schedules.md) </span></span>  
 <span data-ttu-id="fec50-137">[Создание, изменение и удаление расписаний](create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="fec50-137">[Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="fec50-138">[Изменение часовых поясов и параметров часов на сервере отчетов](change-time-zones-and-clock-settings-on-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="fec50-138">[Change Time Zones and Clock Settings on a Report Server](change-time-zones-and-clock-settings-on-a-report-server.md) </span></span>  
 [<span data-ttu-id="fec50-139">Управление запущенным процессом</span><span class="sxs-lookup"><span data-stu-id="fec50-139">Manage a Running Process</span></span>](manage-a-running-process.md)  
  
  
