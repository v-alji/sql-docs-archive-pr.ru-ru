---
title: Страница "расписания" (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ef19d96e-9f00-4434-950e-152dda9c1ced
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e31bc25473aad23ecd2654f74ee3e837e65b65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658093"
---
# <a name="schedules-page-report-manager"></a><span data-ttu-id="9f726-102">Страница «Расписания» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="9f726-102">Schedules Page (Report Manager)</span></span>
  <span data-ttu-id="9f726-103">Страница «Расписания» используется для создания, изменения, удаления, приостановки или возобновления общих расписаний.</span><span class="sxs-lookup"><span data-stu-id="9f726-103">Use the Schedules page to create, modify, delete, pause, or resume shared schedules.</span></span> <span data-ttu-id="9f726-104">Общее расписание — это именованное расписание, которое можно создать и которым можно управлять отдельно от отчетов, подписок и других процессов, требующих сведений расписания.</span><span class="sxs-lookup"><span data-stu-id="9f726-104">A shared schedule is a named schedule that you can create and manage separately from reports, subscriptions, and other processes that consume schedule information.</span></span> <span data-ttu-id="9f726-105">Назначенные общие расписания могут выбираться другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="9f726-105">Users can select shared schedules that you provide.</span></span>  
  
 <span data-ttu-id="9f726-106">Чтобы удалить, приостановить или возобновить выполнение общего расписания, установите флажок рядом с общим расписанием, которое следует изменить.</span><span class="sxs-lookup"><span data-stu-id="9f726-106">To delete, pause, or resume a shared schedule, select the check box next to the shared schedule that you want to modify.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f726-107">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f726-107">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9f726-108">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="9f726-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="9f726-109">Навигация</span><span class="sxs-lookup"><span data-stu-id="9f726-109">Navigation</span></span>  
 <span data-ttu-id="9f726-110">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="9f726-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-schedules-page"></a><span data-ttu-id="9f726-111">Открытие страницы «Расписания»</span><span class="sxs-lookup"><span data-stu-id="9f726-111">To open the Schedules page</span></span>  
  
1.  <span data-ttu-id="9f726-112">Откройте диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="9f726-112">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="9f726-113">В верхнем правом углу страницы нажмите кнопку **Настройки сайта**.</span><span class="sxs-lookup"><span data-stu-id="9f726-113">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="9f726-114">Откроется страница свойств сайта «Общие».</span><span class="sxs-lookup"><span data-stu-id="9f726-114">This opens the General Properties page of the site.</span></span>  
  
3.  <span data-ttu-id="9f726-115">Выберите вкладку **Расписания** .</span><span class="sxs-lookup"><span data-stu-id="9f726-115">Select the **Schedules** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9f726-116">Варианты</span><span class="sxs-lookup"><span data-stu-id="9f726-116">Options</span></span>  
 <span data-ttu-id="9f726-117">**Новое расписание**</span><span class="sxs-lookup"><span data-stu-id="9f726-117">**New Schedule**</span></span>  
 <span data-ttu-id="9f726-118">Нажмите кнопку, чтобы открыть страницу «Расписания», которая используется для указания сведений о частоте.</span><span class="sxs-lookup"><span data-stu-id="9f726-118">Click to open the Scheduling page, which is used to specify frequency information.</span></span>  
  
 <span data-ttu-id="9f726-119">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="9f726-119">**Delete**</span></span>  
 <span data-ttu-id="9f726-120">Нажмите кнопку, чтобы удалить общее расписание.</span><span class="sxs-lookup"><span data-stu-id="9f726-120">Click to remove a shared schedule.</span></span>  
  
 <span data-ttu-id="9f726-121">**Пауза**</span><span class="sxs-lookup"><span data-stu-id="9f726-121">**Pause**</span></span>  
 <span data-ttu-id="9f726-122">Нажмите кнопку, чтобы приостановить выполнение общего расписания.</span><span class="sxs-lookup"><span data-stu-id="9f726-122">Click to stop a shared schedule from running temporarily.</span></span> <span data-ttu-id="9f726-123">Остановка расписания прекращает выполнение подписок и других запланированных процессов.</span><span class="sxs-lookup"><span data-stu-id="9f726-123">Pausing a schedule prevents subscriptions and other scheduled processes from running.</span></span>  
  
 <span data-ttu-id="9f726-124">**Возобновить**;</span><span class="sxs-lookup"><span data-stu-id="9f726-124">**Resume**</span></span>  
 <span data-ttu-id="9f726-125">Нажмите кнопку, чтобы восстановить общее расписание.</span><span class="sxs-lookup"><span data-stu-id="9f726-125">Click to reinstate a shared schedule.</span></span> <span data-ttu-id="9f726-126">Если расписание приостановлено, пропущенные процессы, запланированные на выполнение, не выполняются.</span><span class="sxs-lookup"><span data-stu-id="9f726-126">Lapsed processes that were scheduled to run while the schedule was paused are not made up.</span></span>  
  
 <span data-ttu-id="9f726-127">**Расписание**</span><span class="sxs-lookup"><span data-stu-id="9f726-127">**Schedule**</span></span>  
 <span data-ttu-id="9f726-128">Показывает заданные на данный момент общие расписания.</span><span class="sxs-lookup"><span data-stu-id="9f726-128">Shows the shared schedules that are currently defined.</span></span> <span data-ttu-id="9f726-129">Нажмите общее расписание для просмотра или редактирования сведений о частоте.</span><span class="sxs-lookup"><span data-stu-id="9f726-129">Click a shared schedule to view or edit frequency information.</span></span>  
  
 <span data-ttu-id="9f726-130">**Автор**</span><span class="sxs-lookup"><span data-stu-id="9f726-130">**Creator**</span></span>  
 <span data-ttu-id="9f726-131">Показывает имя пользователя, создавшего общее расписание.</span><span class="sxs-lookup"><span data-stu-id="9f726-131">Shows the name of the user who created the shared schedule.</span></span>  
  
 <span data-ttu-id="9f726-132">**Последний запуск, Следующий запуск**</span><span class="sxs-lookup"><span data-stu-id="9f726-132">**Last Run, Next Run**</span></span>  
 <span data-ttu-id="9f726-133">Показывает, когда общее расписание было запущено последний раз и когда оно будет запущено в следующий раз.</span><span class="sxs-lookup"><span data-stu-id="9f726-133">Shows when the shared schedule was last run and when it will run next.</span></span>  
  
 <span data-ttu-id="9f726-134">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="9f726-134">**Status**</span></span>  
 <span data-ttu-id="9f726-135">Показывает, активно общее расписание или приостановлено.</span><span class="sxs-lookup"><span data-stu-id="9f726-135">Shows whether a shared schedule is paused or active.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f726-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f726-136">See Also</span></span>  
 <span data-ttu-id="9f726-137">[Создание, изменение и удаление расписаний](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="9f726-137">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="9f726-138">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="9f726-138">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
