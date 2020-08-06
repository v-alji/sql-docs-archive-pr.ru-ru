---
title: Свойства расписания (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.general.f1
ms.assetid: 20e43966-6caf-4972-a2e2-0d9131ac8f51
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a61837cd977526021be948d8c74a93eba6506e67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658080"
---
# <a name="schedule-properties-general-page"></a><span data-ttu-id="431dd-102">Свойства расписания (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="431dd-102">Schedule Properties (General Page)</span></span>
  <span data-ttu-id="431dd-103">Чтобы создать или изменить общее расписание, воспользуйтесь этой страницей.</span><span class="sxs-lookup"><span data-stu-id="431dd-103">Use this page to view or modify a shared schedule.</span></span> <span data-ttu-id="431dd-104">Общие расписания могут использоваться вместо расписаний отчетов или подписок.</span><span class="sxs-lookup"><span data-stu-id="431dd-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="431dd-105">Изменения, внесенные в расписания, применяются после сохранения расписания.</span><span class="sxs-lookup"><span data-stu-id="431dd-105">Changes to the schedule are applied after you save the schedule.</span></span> <span data-ttu-id="431dd-106">Изменение расписания не оказывает воздействия на выполняемые задания.</span><span class="sxs-lookup"><span data-stu-id="431dd-106">Editing a schedule has no effect on jobs that are currently in progress.</span></span> <span data-ttu-id="431dd-107">Если какое-то расписание изменяется во время его использования, всем выполняемым в данный момент отчетам и подпискам, запущенным на основе этого расписания, будет разрешено завершение.</span><span class="sxs-lookup"><span data-stu-id="431dd-107">If you edit a schedule while it is being used, all currently processing reports and subscriptions triggered from that schedule will be allowed to finish.</span></span>  
  
 <span data-ttu-id="431dd-108">В одном расписании могут поддерживаться не все комбинации частоты событий.</span><span class="sxs-lookup"><span data-stu-id="431dd-108">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="431dd-109">Например, если требуется запускать отчет в 12:00</span><span class="sxs-lookup"><span data-stu-id="431dd-109">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="431dd-110">и в 16:00</span><span class="sxs-lookup"><span data-stu-id="431dd-110">and 4:00 P.M.</span></span> <span data-ttu-id="431dd-111">каждую пятницу, необходимо создать два ежедневных расписания, запускаемых в пятницу, и для одного указать время запуска 12:00,</span><span class="sxs-lookup"><span data-stu-id="431dd-111">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="431dd-112">а для другого — 16:00.</span><span class="sxs-lookup"><span data-stu-id="431dd-112">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="431dd-113">Обработка по расписанию проводится на базе местного времени сервера отчетов, на котором размещается и обрабатывается расписание.</span><span class="sxs-lookup"><span data-stu-id="431dd-113">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="431dd-114">Чтобы открыть эту страницу, запустите среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], подключитесь к серверу отчетов, откройте папку **Общие расписания** , щелкните одно из общих расписаний правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="431dd-114">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="431dd-115">Эта функция доступна не во всех выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и данная страница не открывается при работе с выпуском, в котором отсутствует эта функция.</span><span class="sxs-lookup"><span data-stu-id="431dd-115">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and this page does not appear when you are running an edition which does not have this feature.</span></span> <span data-ttu-id="431dd-116">Список функций, поддерживаемых различными выпусками [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , см. [в разделе функции, поддерживаемые различными выпусками SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="431dd-116">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="431dd-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="431dd-117">Options</span></span>  
 <span data-ttu-id="431dd-118">**имя**;</span><span class="sxs-lookup"><span data-stu-id="431dd-118">**Name**</span></span>  
 <span data-ttu-id="431dd-119">Указывает имя общего расписания.</span><span class="sxs-lookup"><span data-stu-id="431dd-119">Specifies the name for the shared schedule.</span></span>  
  
 <span data-ttu-id="431dd-120">**Начать выполнение расписания**</span><span class="sxs-lookup"><span data-stu-id="431dd-120">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="431dd-121">Задает начальную дату этого расписания.</span><span class="sxs-lookup"><span data-stu-id="431dd-121">Specifies a start date for this schedule.</span></span>  
  
 <span data-ttu-id="431dd-122">**Остановить выполнения расписания**</span><span class="sxs-lookup"><span data-stu-id="431dd-122">**Stop this schedule on**</span></span>  
 <span data-ttu-id="431dd-123">Задает конечную дату этого расписания.</span><span class="sxs-lookup"><span data-stu-id="431dd-123">Specifies an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="431dd-124">**Тип**</span><span class="sxs-lookup"><span data-stu-id="431dd-124">**Type**</span></span>  
 <span data-ttu-id="431dd-125">Задает шаблон повторения, основанный главным образом на часах, днях, неделях или месяцах, либо определяет разовый запуск.</span><span class="sxs-lookup"><span data-stu-id="431dd-125">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, months, or only runs once.</span></span>  
  
 <span data-ttu-id="431dd-126">**Час (шаблон повторений)**</span><span class="sxs-lookup"><span data-stu-id="431dd-126">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="431dd-127">Указывает параметры запуска запланированной операции через определенные интервалы в часах (например, запускать отчет каждые 6 часов).</span><span class="sxs-lookup"><span data-stu-id="431dd-127">Specifies options for running a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="431dd-128">Интервал можно указывать в часах и минутах.</span><span class="sxs-lookup"><span data-stu-id="431dd-128">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="431dd-129">**День (шаблон повторений)**</span><span class="sxs-lookup"><span data-stu-id="431dd-129">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="431dd-130">Указывает параметры запуска запланированной операции через определенные интервалы в днях (например, запускать отчет каждые 2 дня).</span><span class="sxs-lookup"><span data-stu-id="431dd-130">Specifies options for running a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="431dd-131">Интервал может определяться в днях, с указанием часа и минуты запуска расписания.</span><span class="sxs-lookup"><span data-stu-id="431dd-131">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="431dd-132">**Неделя (шаблон повторений)**</span><span class="sxs-lookup"><span data-stu-id="431dd-132">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="431dd-133">Указывает параметры запуска запланированной операции через определенный интервал в неделях или когда шаблон повторения основан на неделях (например, запускать отчет через неделю).</span><span class="sxs-lookup"><span data-stu-id="431dd-133">Specifies options for running a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="431dd-134">В недельном расписании время запуска расписания может задаваться с указанием дня, часа и минут.</span><span class="sxs-lookup"><span data-stu-id="431dd-134">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="431dd-135">**Месяц (шаблон повторений)**</span><span class="sxs-lookup"><span data-stu-id="431dd-135">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="431dd-136">Указывает параметры запуска запланированной операции через определенный интервал в месяцах или когда шаблон повторения основан на месяцах.</span><span class="sxs-lookup"><span data-stu-id="431dd-136">Specifies options for running a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="431dd-137">В ежемесячном расписании время его запуска может задаваться с указанием дня, часа и минут.</span><span class="sxs-lookup"><span data-stu-id="431dd-137">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="431dd-138">Отдельные месяцы могут исключаться из расписания.</span><span class="sxs-lookup"><span data-stu-id="431dd-138">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="431dd-139">**Однократно**</span><span class="sxs-lookup"><span data-stu-id="431dd-139">**Once**</span></span>  
 <span data-ttu-id="431dd-140">Указывает расписание, выполняемое один раз в заданные дату и время.</span><span class="sxs-lookup"><span data-stu-id="431dd-140">Specifies a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431dd-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="431dd-141">See Also</span></span>  
 <span data-ttu-id="431dd-142">[Сервер отчетов в справке Management Studio F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="431dd-142">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="431dd-143">[Соединение с сервером отчетов в Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="431dd-143">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="431dd-144">[Создание, изменение и удаление расписаний](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="431dd-144">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="431dd-145">Расписания</span><span class="sxs-lookup"><span data-stu-id="431dd-145">Schedules</span></span>](../subscriptions/schedules.md)  
  
  
