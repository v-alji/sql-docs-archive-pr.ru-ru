---
title: Создание общего расписания (среда Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newschedule.f1
ms.assetid: b2c69586-d98e-4933-827d-f5e6c15c5203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6afd406730f815d3ab61e59cdebd21d564daa74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657510"
---
# <a name="new-shared-schedule-management-studio"></a><span data-ttu-id="1417b-102">Создание общего расписания (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1417b-102">New Shared Schedule (Management Studio)</span></span>
  <span data-ttu-id="1417b-103">Используйте эту страницу для создания общего расписания для выполнения опубликованных отчетов и подписок.</span><span class="sxs-lookup"><span data-stu-id="1417b-103">Use this page to create a shared schedule to run published reports and subscriptions.</span></span> <span data-ttu-id="1417b-104">Общие расписания могут использоваться вместо расписаний отчетов или подписок.</span><span class="sxs-lookup"><span data-stu-id="1417b-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="1417b-105">Двумя основными особенностями, которые отличают общие расписания от расписаний, относящихся к конкретным элементам, являются централизация данных расписания и возможность приостанавливать и возобновлять запланированные операции.</span><span class="sxs-lookup"><span data-stu-id="1417b-105">Centralized schedule information and the ability to pause and resume scheduled operations are two key features that distinguish shared schedules from item-specific schedules.</span></span>  
  
 <span data-ttu-id="1417b-106">В одном расписании могут поддерживаться не все комбинации частоты событий.</span><span class="sxs-lookup"><span data-stu-id="1417b-106">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="1417b-107">Например, если требуется запускать отчет в 12:00</span><span class="sxs-lookup"><span data-stu-id="1417b-107">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="1417b-108">и в 16:00</span><span class="sxs-lookup"><span data-stu-id="1417b-108">and 4:00 P.M.</span></span> <span data-ttu-id="1417b-109">каждую пятницу, необходимо создать два ежедневных расписания, запускаемых в пятницу, и для одного указать время запуска 12:00,</span><span class="sxs-lookup"><span data-stu-id="1417b-109">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="1417b-110">а для другого — 16:00.</span><span class="sxs-lookup"><span data-stu-id="1417b-110">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="1417b-111">Обработка по расписанию проводится на базе местного времени сервера отчетов, на котором размещается и обрабатывается расписание.</span><span class="sxs-lookup"><span data-stu-id="1417b-111">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="1417b-112">Чтобы открыть эту страницу, запустите среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], подключитесь к серверу отчетов, щелкните правой кнопкой мыши элемент **Общее расписание**и выберите **Создать расписание**.</span><span class="sxs-lookup"><span data-stu-id="1417b-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Shared Schedule**, and select **New Schedule**.</span></span> <span data-ttu-id="1417b-113">Сохранить расписание можно только при запущенной службе агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1417b-113">To save the schedule, SQL Server Agent service must be running.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1417b-114">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1417b-114">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1417b-115">Дополнительные сведения о функциях, поддерживаемых выпусками [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в статье [Возможности, поддерживаемые выпусками SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span><span class="sxs-lookup"><span data-stu-id="1417b-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1417b-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="1417b-116">Options</span></span>  
 <span data-ttu-id="1417b-117">**Название**</span><span class="sxs-lookup"><span data-stu-id="1417b-117">**Name**</span></span>  
 <span data-ttu-id="1417b-118">Введите имя общего расписания.</span><span class="sxs-lookup"><span data-stu-id="1417b-118">Type a name for the shared schedule.</span></span> <span data-ttu-id="1417b-119">Это имя отображается в раскрывающихся списках, если пользователи выбирают общее расписание для отчетов и подписок.</span><span class="sxs-lookup"><span data-stu-id="1417b-119">This name appears in drop-down lists when users select a shared schedule for reports and subscriptions.</span></span> <span data-ttu-id="1417b-120">Укажите описательное имя, которое умещается в списке по ширине и позволяет легко отличить одно общее расписание от другого.</span><span class="sxs-lookup"><span data-stu-id="1417b-120">Be sure to provide a descriptive name that fits easily within a list and that easily distinguishes one shared schedule from another.</span></span> <span data-ttu-id="1417b-121">Имя должно содержать хотя бы одну букву или цифру.</span><span class="sxs-lookup"><span data-stu-id="1417b-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="1417b-122">В него могут также входить пробелы и другие символы.</span><span class="sxs-lookup"><span data-stu-id="1417b-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="1417b-123">При задании имени нельзя использовать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="1417b-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="1417b-124">; ?</span><span class="sxs-lookup"><span data-stu-id="1417b-124">; ?</span></span> <span data-ttu-id="1417b-125">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="1417b-125">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="1417b-126">" /</span><span class="sxs-lookup"><span data-stu-id="1417b-126">" /</span></span>  
  
 <span data-ttu-id="1417b-127">**Начать выполнение расписания**</span><span class="sxs-lookup"><span data-stu-id="1417b-127">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="1417b-128">Задайте дату запуска этого расписания.</span><span class="sxs-lookup"><span data-stu-id="1417b-128">Specify a start date for this schedule.</span></span>  
  
 <span data-ttu-id="1417b-129">**Остановить выполнения расписания**</span><span class="sxs-lookup"><span data-stu-id="1417b-129">**Stop this schedule on**</span></span>  
 <span data-ttu-id="1417b-130">Задайте дату истечения срока действия этого расписания.</span><span class="sxs-lookup"><span data-stu-id="1417b-130">Specify an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="1417b-131">**Тип**</span><span class="sxs-lookup"><span data-stu-id="1417b-131">**Type**</span></span>  
 <span data-ttu-id="1417b-132">Указывает, основан ли шаблон повторений главным образом на таких единицах измерения времени, как часы, сутки, недели или месяцы.</span><span class="sxs-lookup"><span data-stu-id="1417b-132">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, or months.</span></span>  
  
 <span data-ttu-id="1417b-133">**Час (шаблон повторений)**</span><span class="sxs-lookup"><span data-stu-id="1417b-133">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="1417b-134">Выберите параметры для выполнения запланированной операции в интервалах, кратных часу (например, запускать отчет каждые шесть часов).</span><span class="sxs-lookup"><span data-stu-id="1417b-134">Select options to run a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="1417b-135">Интервал можно указывать в часах и минутах.</span><span class="sxs-lookup"><span data-stu-id="1417b-135">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="1417b-136">**День (шаблон повторений)**</span><span class="sxs-lookup"><span data-stu-id="1417b-136">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="1417b-137">Выберите параметры для выполнения запланированной операции в интервалах, кратных дню (например, запускать отчет каждые два дня).</span><span class="sxs-lookup"><span data-stu-id="1417b-137">Select options to run a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="1417b-138">Интервал может определяться в днях, с указанием часа и минуты запуска расписания.</span><span class="sxs-lookup"><span data-stu-id="1417b-138">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="1417b-139">**Неделя (шаблон повторений)**</span><span class="sxs-lookup"><span data-stu-id="1417b-139">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="1417b-140">Выберите параметры для выполнения запланированной операции в недельных интервалах или согласно шаблону повторения на основании недель (например, запускать отчет каждую вторую неделю).</span><span class="sxs-lookup"><span data-stu-id="1417b-140">Select options to run a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="1417b-141">В недельном расписании время запуска расписания может задаваться с указанием дня, часа и минут.</span><span class="sxs-lookup"><span data-stu-id="1417b-141">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="1417b-142">**Месяц (шаблон повторений)**</span><span class="sxs-lookup"><span data-stu-id="1417b-142">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="1417b-143">Выберите параметры для выполнения запланированной операции с интервалом в месяц или согласно шаблону повторения на основании месяцев.</span><span class="sxs-lookup"><span data-stu-id="1417b-143">Select options to run a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="1417b-144">В ежемесячном расписании время его запуска может задаваться с указанием дня, часа и минут.</span><span class="sxs-lookup"><span data-stu-id="1417b-144">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="1417b-145">Отдельные месяцы могут исключаться из расписания.</span><span class="sxs-lookup"><span data-stu-id="1417b-145">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="1417b-146">**Однократно**</span><span class="sxs-lookup"><span data-stu-id="1417b-146">**Once**</span></span>  
 <span data-ttu-id="1417b-147">Этот параметр выбирается для создания расписания, выполняющегося только один раз, в определенную дату и в определенное время.</span><span class="sxs-lookup"><span data-stu-id="1417b-147">Select this option to create a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1417b-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="1417b-148">See Also</span></span>  
 <span data-ttu-id="1417b-149">[Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1417b-149">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="1417b-150">[Подключение к серверу отчетов в среде Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1417b-150">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="1417b-151">[Создание, изменение и удаление расписаний](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="1417b-151">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="1417b-152">[Расписания](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="1417b-152">[Schedules](../subscriptions/schedules.md) </span></span>  
 [<span data-ttu-id="1417b-153">Справка F1 по использованию сервера отчетов среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="1417b-153">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
