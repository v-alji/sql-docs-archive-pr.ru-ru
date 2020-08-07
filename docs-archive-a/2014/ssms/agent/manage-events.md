---
title: Управление событиями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- event-triggered jobs [SQL Server]
- forwarding events [SQL Server]
- alerts [SQL Server], forwarded events
- alerts [SQL Server], management servers
- SQL Server Agent alerts, management servers
ms.assetid: 8f4ee7f5-80df-49fd-b2b8-d020e04b6e1b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ca6d56440b06d285cbb90f8d92325d59a452c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727898"
---
# <a name="manage-events"></a><span data-ttu-id="27bca-102">Управление событиями</span><span class="sxs-lookup"><span data-stu-id="27bca-102">Manage Events</span></span>
  <span data-ttu-id="27bca-103">Все сообщения об ошибках, удовлетворяющие заданному уровню серьезности либо превышающие его, могут быть перенаправлены экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27bca-103">You can forward to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all event messages that meet or exceed a specific error severity level.</span></span> <span data-ttu-id="27bca-104">Данное действие называется *пересылкой событий*.</span><span class="sxs-lookup"><span data-stu-id="27bca-104">This is called *event forwarding*.</span></span> <span data-ttu-id="27bca-105">Сервер пересылки является выделенным сервером, который может также являться главным.</span><span class="sxs-lookup"><span data-stu-id="27bca-105">The forwarding server is a dedicated server that can also be a master server.</span></span> <span data-ttu-id="27bca-106">Пересылка событий может быть использована для централизации управления предупреждениями в группе серверов, что позволяет снизить рабочую нагрузку на сильно загруженные серверы.</span><span class="sxs-lookup"><span data-stu-id="27bca-106">You can use event forwarding to centralize alert management for a group of servers, thereby reducing the workload on heavily used servers.</span></span>  
  
 <span data-ttu-id="27bca-107">Сервер, предназначенный для получения событий на всю группу серверов, называется *сервером управления предупреждениями*.</span><span class="sxs-lookup"><span data-stu-id="27bca-107">When one server receives events for a group of other servers, the server that receives events is called an *alerts management server*.</span></span> <span data-ttu-id="27bca-108">В многосерверной среде сервером управления предупреждениями должен быть главный сервер.</span><span class="sxs-lookup"><span data-stu-id="27bca-108">In a multiserver environment, you designate the master server as the alerts management server.</span></span>  
  
## <a name="advantages-of-using-an-alerts-management-server"></a><span data-ttu-id="27bca-109">Преимущества использования сервера управления предупреждениями</span><span class="sxs-lookup"><span data-stu-id="27bca-109">Advantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="27bca-110">Преимущества настройки сервера управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="27bca-110">The advantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="27bca-111">**Централизация**.</span><span class="sxs-lookup"><span data-stu-id="27bca-111">**Centralization**.</span></span> <span data-ttu-id="27bca-112">Централизованное управление и обобщенное представление событий нескольких экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с одиночного сервера.</span><span class="sxs-lookup"><span data-stu-id="27bca-112">Centralized control and a consolidated view of the events of several instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are possible from a single server.</span></span>  
  
-   <span data-ttu-id="27bca-113">**Масштабируемость**.</span><span class="sxs-lookup"><span data-stu-id="27bca-113">**Scalability**.</span></span> <span data-ttu-id="27bca-114">Представление совокупности отдельных серверов в виде одного логического сервера.</span><span class="sxs-lookup"><span data-stu-id="27bca-114">Many physical servers can be administered as one logical server.</span></span> <span data-ttu-id="27bca-115">При необходимости в указанную группу можно добавлять и удалять физические серверы.</span><span class="sxs-lookup"><span data-stu-id="27bca-115">You can add or remove servers to this physical server group as needed.</span></span>  
  
-   <span data-ttu-id="27bca-116">**Эффективность**.</span><span class="sxs-lookup"><span data-stu-id="27bca-116">**Efficiency**.</span></span> <span data-ttu-id="27bca-117">Требуется меньшее количество времени для конфигурирования, так как настройка предупреждений и операторов производится только один раз.</span><span class="sxs-lookup"><span data-stu-id="27bca-117">Configuration time is reduced, because you need to define alerts and operators only once.</span></span>  
  
## <a name="disadvantages-of-using-an-alerts-management-server"></a><span data-ttu-id="27bca-118">Недостатки использования сервера управления предупреждениями</span><span class="sxs-lookup"><span data-stu-id="27bca-118">Disadvantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="27bca-119">Недостатки настройки сервера управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="27bca-119">The disadvantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="27bca-120">**Увеличение трафика**.</span><span class="sxs-lookup"><span data-stu-id="27bca-120">**Increased traffic**.</span></span> <span data-ttu-id="27bca-121">Пересылка событий на сервер управления предупреждениями может привести к увеличению сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="27bca-121">Forwarding events to an alerts management server can increase network traffic.</span></span> <span data-ttu-id="27bca-122">Чтобы избежать этого, необходимо ограничить количество пересылаемых событий. При этом будут пересылаться только события, уровень серьезности которых превышает заданный.</span><span class="sxs-lookup"><span data-stu-id="27bca-122">This increase can be moderated by restricting event forwarding to events that are above a designated severity level.</span></span>  
  
-   <span data-ttu-id="27bca-123">**Единственная точка сбоя**.</span><span class="sxs-lookup"><span data-stu-id="27bca-123">**Single point of failure**.</span></span> <span data-ttu-id="27bca-124">Другие серверы группы не получают уведомления в случае отключения сервера управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="27bca-124">If the alerts management server goes offline, no alerts are issued for any event on the managed group of servers.</span></span>  
  
-   <span data-ttu-id="27bca-125">**Загрузка сервера**.</span><span class="sxs-lookup"><span data-stu-id="27bca-125">**Server load**.</span></span> <span data-ttu-id="27bca-126">Управление предупреждениями о перенаправленных событиях повышает загруженность сервера управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="27bca-126">Handling alerts for the forwarded events causes an increased processing load on the alerts management server.</span></span>  
  
## <a name="guidelines-for-using-an-alerts-management-server"></a><span data-ttu-id="27bca-127">Инструкции по использованию сервера управления предупреждениями</span><span class="sxs-lookup"><span data-stu-id="27bca-127">Guidelines for Using an Alerts Management Server</span></span>  
 <span data-ttu-id="27bca-128">При настройке сервера управления предупреждениями необходимо следовать представленным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="27bca-128">When configuring an alerts management server, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="27bca-129">Для получения перенаправленных событий сервер управления предупреждениями должен быть экземпляром SQL Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27bca-129">In order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="27bca-130">Не следует запускать ресурсоемкие приложения на сервере управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="27bca-130">Avoid running critical or heavily used applications on the alerts management server.</span></span>  
  
-   <span data-ttu-id="27bca-131">Необходимо строго отслеживать вовлечение сетевого трафика при использовании общего сервера управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="27bca-131">Carefully plan for the network traffic involved in configuring many servers to share the same alerts management server.</span></span> <span data-ttu-id="27bca-132">При чрезмерном увеличении нагрузки необходимо уменьшить количество серверов, использующих данный сервер управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="27bca-132">If congestion results, reduce the number of servers that use a particular alerts management server.</span></span>  
  
     <span data-ttu-id="27bca-133">Серверы, зарегистрированные в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , могут быть использованы ею в качестве серверов пересылки предупреждений.</span><span class="sxs-lookup"><span data-stu-id="27bca-133">The servers that are registered within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] constitute the list of servers available to be chosen by that server as the alerts-forwarding server.</span></span>  
  
-   <span data-ttu-id="27bca-134">Локальные предупреждения предпочтительнее задавать внутри локального экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Не рекомендуется пересылать их на сервер управления предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="27bca-134">Define alerts on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that require a server-specific response, instead of forwarding the alerts to the alerts management server.</span></span>  
  
     <span data-ttu-id="27bca-135">Ответы сервера управления предупреждениями одинаковы для всех серверов, пересылающих ему предупреждения.</span><span class="sxs-lookup"><span data-stu-id="27bca-135">The alerts management server views all the servers forwarding to it as a logical whole.</span></span> <span data-ttu-id="27bca-136">Например, ответы сервера управления предупреждениями на события с кодом 605, поступившие от серверов А и Б, совпадают.</span><span class="sxs-lookup"><span data-stu-id="27bca-136">For example, an alerts management server responds in the same way to a 605 event from server A and a 605 event from server B.</span></span>  
  
-   <span data-ttu-id="27bca-137">После настройки системы предупреждений необходимо периодически просматривать события агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в журнале приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="27bca-137">After configuring your alert system, periodically check the Microsoft Windows application log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events.</span></span>  
  
     <span data-ttu-id="27bca-138">Сбои, обнаруженные ядром предупреждений, записываются в журнал приложений Windows, при этом в качестве имени источника указывается «Агент SQL Server».</span><span class="sxs-lookup"><span data-stu-id="27bca-138">Failure conditions encountered by the alerts engine are written to the local Windows application log with a source name of "SQL Server Agent."</span></span> <span data-ttu-id="27bca-139">Например, если агенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается отправить уведомление по электронной почте, то указанное событие записывается в журнал приложений.</span><span class="sxs-lookup"><span data-stu-id="27bca-139">For example, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot send an e-mail notification as it has been defined, an event is logged in the application log.</span></span>  
  
 <span data-ttu-id="27bca-140">Если локально заданное предупреждение неактивно, то при возникновении соответствующего ему события оно будет перенаправлено на сервер управления предупреждениями (в случае, если выполняется условие пересылки).</span><span class="sxs-lookup"><span data-stu-id="27bca-140">If a locally defined alert is inactivated, and an event occurs that would have caused the alert to fire, the event is forwarded to the alerts management server (if it satisfies the alert-forwarding condition).</span></span> <span data-ttu-id="27bca-141">Такой способ пересылки позволяет включать и выключать переопределение предупреждений по требованию пользователя локального веб-сайта (для случаев, когда предупреждения заданы и локально, и на сервере управления предупреждениями).</span><span class="sxs-lookup"><span data-stu-id="27bca-141">This forwarding allows local overrides (alerts defined locally that are also defined on the alerts management server) to be turned off and on as needed by the user at the local site.</span></span> <span data-ttu-id="27bca-142">Также можно задать, чтобы события пересылались в любом случае, даже если они связаны с предупреждениями, заданными локально.</span><span class="sxs-lookup"><span data-stu-id="27bca-142">You can also request that events always be forwarded, even if they are also handled by local alerts.</span></span>  
  
 <span data-ttu-id="27bca-143">Ниже представлен список наиболее типичных задач, используемых для управления событиями в многосерверной среде.</span><span class="sxs-lookup"><span data-stu-id="27bca-143">The following are common tasks for managing events in a multiserver environment:</span></span>  
  
 <span data-ttu-id="27bca-144">**Назначение сервера управления предупреждениями**</span><span class="sxs-lookup"><span data-stu-id="27bca-144">**To designate an alerts management server**</span></span>  
  
-   [<span data-ttu-id="27bca-145">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27bca-145">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
 <span data-ttu-id="27bca-146">**Определение ответа на предупреждение**</span><span class="sxs-lookup"><span data-stu-id="27bca-146">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="27bca-147">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27bca-147">SQL Server Management Studio</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="27bca-148">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27bca-148">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
## <a name="running-event-triggered-jobs"></a><span data-ttu-id="27bca-149">Выполнение заданий, запускаемых событиями</span><span class="sxs-lookup"><span data-stu-id="27bca-149">Running Event-Triggered Jobs</span></span>  
 <span data-ttu-id="27bca-150">Можно определить задание, выполняемое при получении предупреждения.</span><span class="sxs-lookup"><span data-stu-id="27bca-150">You can define a job to be executed in response to an alert.</span></span> <span data-ttu-id="27bca-151">Например, в качестве такого задания можно указать операцию, которая проводит диагностику или исправление проблемы, выдавшей предупреждение.</span><span class="sxs-lookup"><span data-stu-id="27bca-151">For example, you can execute a job that corrects or further diagnoses a problem detected by the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27bca-152">Так как в результате выполнения задания может возникнуть событие, необходимо строго следить за тем, чтобы не образовался рекурсивный цикл, выдающий предупреждение.</span><span class="sxs-lookup"><span data-stu-id="27bca-152">Because a job can raise an event, be careful not to create a recursive alert-job loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27bca-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="27bca-153">See Also</span></span>  
 [<span data-ttu-id="27bca-154">sys.sysсообщения &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27bca-154">sys.sysmessages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysmessages-transact-sql)  
  
  
