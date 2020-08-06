---
title: Домены приложений для приложений сервера отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- application domains [Reporting Services]
- recycling application domains
ms.assetid: a455e2e6-8764-493d-a1bc-abe80829f543
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5f52ee48c5a5f9113b277271320b649ed8e7dd79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665841"
---
# <a name="application-domains-for-report-server-applications"></a><span data-ttu-id="63b83-102">Домены приложений для приложений сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-102">Application Domains for Report Server Applications</span></span>
  <span data-ttu-id="63b83-103">В службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]сервер отчетов реализован как единственная служба, включающая веб-службу сервера отчетов, диспетчер отчетов и приложение фоновой обработки.</span><span class="sxs-lookup"><span data-stu-id="63b83-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], the report server is implemented as a single service that contains the Report Server Web service, Report Manager, and a background processing application.</span></span> <span data-ttu-id="63b83-104">Каждое приложение эксплуатируется в собственном домене приложения, в составе общего процесса сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="63b83-104">Each application runs in its own application domain within the single report server process.</span></span> <span data-ttu-id="63b83-105">Создание, настройка и управление доменами приложений обычно осуществляются внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="63b83-105">For the most part, application domains are created, configured, and managed internally.</span></span> <span data-ttu-id="63b83-106">Однако знание того, как происходят операции очистки для доменов приложений сервера отчетов, может быть полезным при исследовании проблем производительности или использования памяти и при устранении неполадок в работе службы.</span><span class="sxs-lookup"><span data-stu-id="63b83-106">However, knowing how recycle operations occur for report server application domains can be helpful if you are investigating performance or memory issues or troubleshooting service disruptions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63b83-107">При настройке доступа к построителю отчетов на сервере отчетов, который использует обычную проверку подлинности, построитель отчетов выполняется в своем собственном домене приложений.</span><span class="sxs-lookup"><span data-stu-id="63b83-107">If you configure Report Builder access on a report server that uses Basic authentication, Report Builder will run in its own application domain.</span></span> <span data-ttu-id="63b83-108">Это домен приложений, отличный от других доменов приложений, которые запускаются в процессе сервера.</span><span class="sxs-lookup"><span data-stu-id="63b83-108">This application domain is different from other application domains that run in the server process.</span></span> <span data-ttu-id="63b83-109">Он управляется контроллером служб и не зависит от функций управления памятью, которые перераспределяют память в процессе ее активного использования на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="63b83-109">It is managed by the Service Controller and is not subject memory management features that re-adjust memory allocation in response to memory pressure on the to report server.</span></span>  
  
 <span data-ttu-id="63b83-110">В следующем списке описаны события, которые становятся причиной выполнения операций очистки домена приложений служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63b83-110">The following list describes the events that cause application domain recycle operations for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applications:</span></span>  
  
-   <span data-ttu-id="63b83-111">Плановые операции очистки, выполняемые через стандартные интервалы времени.</span><span class="sxs-lookup"><span data-stu-id="63b83-111">Scheduled recycle operations that occur at predefined intervals.</span></span>  
  
-   <span data-ttu-id="63b83-112">Изменения конфигурации на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="63b83-112">Configuration changes on the report server.</span></span>  
  
-   [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="63b83-113">.</span><span class="sxs-lookup"><span data-stu-id="63b83-113">configuration changes.</span></span>  
  
-   <span data-ttu-id="63b83-114">Сбой выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="63b83-114">Memory allocation failures.</span></span>  
  
 <span data-ttu-id="63b83-115">В следующей таблице приведены итоговые сведения о том, как происходит очистка домена приложений в ответ на эти события.</span><span class="sxs-lookup"><span data-stu-id="63b83-115">The following table summarizes application domain recycling behavior in response to these events:</span></span>  
  
|<span data-ttu-id="63b83-116">Событие</span><span class="sxs-lookup"><span data-stu-id="63b83-116">Event</span></span>|<span data-ttu-id="63b83-117">Описание события</span><span class="sxs-lookup"><span data-stu-id="63b83-117">Event description</span></span>|<span data-ttu-id="63b83-118">Применяется к</span><span class="sxs-lookup"><span data-stu-id="63b83-118">Applies to</span></span>|<span data-ttu-id="63b83-119">Настраивается</span><span class="sxs-lookup"><span data-stu-id="63b83-119">Configurable</span></span>|<span data-ttu-id="63b83-120">Описание операции очистки</span><span class="sxs-lookup"><span data-stu-id="63b83-120">Recycle operation description</span></span>|  
|-----------|-----------------------|----------------|------------------|-----------------------------------|  
|<span data-ttu-id="63b83-121">Плановые операции очистки, выполняемые через стандартные интервалы времени</span><span class="sxs-lookup"><span data-stu-id="63b83-121">Scheduled recycle operations that occur at predefined intervals</span></span>|<span data-ttu-id="63b83-122">По умолчанию, домены приложений очищаются через каждые 12 часов.</span><span class="sxs-lookup"><span data-stu-id="63b83-122">By default, application domains are recycled every 12 hours.</span></span><br /><br /> <span data-ttu-id="63b83-123">Плановые операции очистки чаще всего выполняются применительно к приложениям [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] , обеспечивающих общую исправность процесса.</span><span class="sxs-lookup"><span data-stu-id="63b83-123">Scheduled recycle operations are a common practice for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications that promote overall process health.</span></span>|<span data-ttu-id="63b83-124">Веб-служба сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-124">Report server Web service</span></span><br /><br /> <span data-ttu-id="63b83-125">Диспетчер отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-125">Report Manager</span></span><br /><br /> <span data-ttu-id="63b83-126">Приложение фоновой обработки</span><span class="sxs-lookup"><span data-stu-id="63b83-126">Background processing application</span></span>|<span data-ttu-id="63b83-127">Да.</span><span class="sxs-lookup"><span data-stu-id="63b83-127">Yes.</span></span> <span data-ttu-id="63b83-128">Значение параметра конфигурации `RecycleTime` в файле RSReportServer.config определяет интервал очистки.</span><span class="sxs-lookup"><span data-stu-id="63b83-128">`RecycleTime` configuration setting in the RSReportServer.config file determines the recycle interval.</span></span><br /><br /> <span data-ttu-id="63b83-129">Параметр `MaxAppDomainUnloadTime` задает время ожидания, в течение которого допускается завершение фоновой обработки.</span><span class="sxs-lookup"><span data-stu-id="63b83-129">`MaxAppDomainUnloadTime` sets the wait time during which background processing is allowed to complete.</span></span>|[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="63b83-130">управляет операцией очистки для веб-службы и диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="63b83-130">manages the recycle operation for the Web service and Report Manager.</span></span><br /><br /> <span data-ttu-id="63b83-131">Для приложения фоновой обработки сервер отчетов создает новый домен приложения для новых заданий, инициированных по расписанию.</span><span class="sxs-lookup"><span data-stu-id="63b83-131">For the background processing application, the report server creates a new application domain for new jobs that are initiated from schedules.</span></span> <span data-ttu-id="63b83-132">Завершение уже выполняемых заданий в текущем домене приложения допускается до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="63b83-132">Jobs already in progress are allowed to complete in the current application domain until the wait time expires.</span></span>|  
|<span data-ttu-id="63b83-133">Изменения конфигурации на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-133">Configuration changes on the report server</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="63b83-134">очищают домены приложений в ответ на изменения в файле RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="63b83-134">will recycle application domains in response to changes in the RSReportServer.config file.</span></span>|<span data-ttu-id="63b83-135">Веб-служба сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-135">Report server Web service</span></span><br /><br /> <span data-ttu-id="63b83-136">Диспетчер отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-136">Report Manager</span></span><br /><br /> <span data-ttu-id="63b83-137">Приложение фоновой обработки</span><span class="sxs-lookup"><span data-stu-id="63b83-137">Background processing application</span></span>|<span data-ttu-id="63b83-138">Нет.</span><span class="sxs-lookup"><span data-stu-id="63b83-138">No.</span></span>|<span data-ttu-id="63b83-139">Остановить операции очистки невозможно.</span><span class="sxs-lookup"><span data-stu-id="63b83-139">You cannot stop recycle operations from occurring.</span></span> <span data-ttu-id="63b83-140">Тем не менее, операции очистки, выполняемые в ответ на изменения конфигурации, осуществляются таким же образом, как и плановые операции очистки.</span><span class="sxs-lookup"><span data-stu-id="63b83-140">However, recycle operations that occur in response to configuration changes are handled the same way as the scheduled recycle operations.</span></span> <span data-ttu-id="63b83-141">Для новых запросов создаются новые домены приложений, в то время как текущие запросы и задания завершаются в текущем домене приложения.</span><span class="sxs-lookup"><span data-stu-id="63b83-141">New application domains are created for new requests while current requests and jobs complete in the current application domain.</span></span>|  
|[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="63b83-142">изменения конфигурации</span><span class="sxs-lookup"><span data-stu-id="63b83-142">configuration changes</span></span>|[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="63b83-143">осуществляет очистку доменов приложений, если происходят изменения в отслеживаемых им файлах (например, в файлах machine.config и Web.config, а также в программных файлах [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="63b83-143">will recycle application domains if there are changes to the files that it monitors (for example, machine.config and Web.config files, and [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] program files).</span></span>|<span data-ttu-id="63b83-144">Веб-служба сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-144">Report server Web service</span></span><br /><br /> <span data-ttu-id="63b83-145">Диспетчер отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-145">Report Manager</span></span>|<span data-ttu-id="63b83-146">Нет.</span><span class="sxs-lookup"><span data-stu-id="63b83-146">No.</span></span>|[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="63b83-147">управляет работой.</span><span class="sxs-lookup"><span data-stu-id="63b83-147">manages the operation.</span></span><br /><br /> <span data-ttu-id="63b83-148">Операции очистки, инициированные [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] , не затрагивают домен приложения фоновой обработки.</span><span class="sxs-lookup"><span data-stu-id="63b83-148">Recycle operations that are initiated by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] do not affect the background processing application domain.</span></span>|  
|<span data-ttu-id="63b83-149">Нехватка памяти и ошибки при выделении памяти</span><span class="sxs-lookup"><span data-stu-id="63b83-149">Memory pressure and memory allocation failures</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="63b83-150">немедленно происходит очистка доменов приложений в случае ошибки при выделении памяти или в условиях значительной нехватки памяти на сервере.</span><span class="sxs-lookup"><span data-stu-id="63b83-150">CLR will immediately recycle application domains in the event of a memory allocation failure or when the server is under high memory pressure conditions.</span></span>|<span data-ttu-id="63b83-151">Веб-служба сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-151">Report server Web service</span></span><br /><br /> <span data-ttu-id="63b83-152">Диспетчер отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-152">Report Manager</span></span><br /><br /> <span data-ttu-id="63b83-153">Приложение фоновой обработки</span><span class="sxs-lookup"><span data-stu-id="63b83-153">Background processing application</span></span>|<span data-ttu-id="63b83-154">Нет.</span><span class="sxs-lookup"><span data-stu-id="63b83-154">No.</span></span>|<span data-ttu-id="63b83-155">При значительной нехватке памяти сервер отчетов не принимает новые запросы в текущем домене приложения.</span><span class="sxs-lookup"><span data-stu-id="63b83-155">Under high memory pressure, the report server will not accept new requests in the current application domain.</span></span> <span data-ttu-id="63b83-156">Пока сервер отклоняет новые запросы, происходят ошибки HTTP 503.</span><span class="sxs-lookup"><span data-stu-id="63b83-156">During the period in which the server denies new requests, HTTP 503 errors occur.</span></span> <span data-ttu-id="63b83-157">Новые домены приложений не создаются до тех пор, пока не произойдет выгрузка старого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="63b83-157">New application domains will not be created until the old application domain is unloaded.</span></span> <span data-ttu-id="63b83-158">Это означает, что в случае внесения изменений в файл конфигурации в условиях значительной нехватки памяти на сервере, выполняемые запросы и задания могут не запускаться или не завершаться.</span><span class="sxs-lookup"><span data-stu-id="63b83-158">This means that if you make a configuration file change while the server is under high memory pressure, requests and jobs that are in progress might not start or complete.</span></span><br /><br /> <span data-ttu-id="63b83-159">В случае ошибки при выполнении операции выделения памяти происходит немедленный перезапуск всех доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="63b83-159">In the event of memory allocation failure, all application domains are immediately restarted.</span></span> <span data-ttu-id="63b83-160">Выполняемые задания и запросы уничтожаются.</span><span class="sxs-lookup"><span data-stu-id="63b83-160">Jobs and requests that were in progress are dropped.</span></span> <span data-ttu-id="63b83-161">Необходимо перезапустить эти задания и запросы вручную.</span><span class="sxs-lookup"><span data-stu-id="63b83-161">You must restart those jobs and requests manually.</span></span>|  
  
## <a name="planned-and-unplanned-recycle-operations"></a><span data-ttu-id="63b83-162">Запланированные и незапланированные операции очистки</span><span class="sxs-lookup"><span data-stu-id="63b83-162">Planned and Unplanned Recycle Operations</span></span>  
 <span data-ttu-id="63b83-163">Операции очистки могут быть либо запланированными, либо незапланированными, в зависимости от условий, которые приводят к выполнению операции.</span><span class="sxs-lookup"><span data-stu-id="63b83-163">Recycle operations are either planned or unplanned depending on the conditions that bring about the operation:</span></span>  
  
-   <span data-ttu-id="63b83-164">Запланированные операции очистки происходят через постоянные интервалы, которые определены в файле RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="63b83-164">Planned recycle operations occur at regular intervals that are defined in the RSReportServer.config file.</span></span> <span data-ttu-id="63b83-165">По умолчанию— через каждые 12 часов.</span><span class="sxs-lookup"><span data-stu-id="63b83-165">The default is every 12 hours.</span></span> <span data-ttu-id="63b83-166">Это характерно для приложений [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] , обеспечивающих общую исправность процесса.</span><span class="sxs-lookup"><span data-stu-id="63b83-166">This is a common practice for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications that promote overall process health.</span></span> <span data-ttu-id="63b83-167">Для запланированных операций очистки сервер отчетов создает дополнительные домены приложений для новых запросов.</span><span class="sxs-lookup"><span data-stu-id="63b83-167">For planned recycle operations, the report server creates additional application domains for new requests.</span></span> <span data-ttu-id="63b83-168">Завершение уже выполняемых запросов в текущем домене приложения допускается до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="63b83-168">Requests already in progress are allowed to complete in the current application domain until the wait time expires.</span></span> <span data-ttu-id="63b83-169">Значения параметров конфигурации, которые управляют запланированными операциями очистки, задаются для всего сервера в целом.</span><span class="sxs-lookup"><span data-stu-id="63b83-169">Configuration settings that govern planned recycle operations are set for the server as a whole.</span></span> <span data-ttu-id="63b83-170">Возможность настроить отдельное расписание очистки или пороговое значение памяти для каждого приложения отсутствует.</span><span class="sxs-lookup"><span data-stu-id="63b83-170">You cannot configure a different recycle schedule or memory threshold for each application.</span></span>  
  
-   <span data-ttu-id="63b83-171">Незапланированные операции очистки происходят в произвольные моменты времени в ответ на изменения конфигурации, нехватку памяти и ошибки при выполнении операций выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="63b83-171">Unplanned recycle operations occur at arbitrary times in response to configuration changes, memory pressure, and memory allocation failures:</span></span>  
  
    -   <span data-ttu-id="63b83-172">При изменениях конфигурации сервер отчетов предпринимает попытку использовать мягкую очистку, при которой выполняется перенаправление новых запросов на новый экземпляр домена приложения.</span><span class="sxs-lookup"><span data-stu-id="63b83-172">For configuration changes, the report server will try to use a soft recycle that redirects new requests to a new instance of the application domain.</span></span> <span data-ttu-id="63b83-173">Если мягкая очистка оканчивается неудачей, сервер инициирует жесткую очистку домена приложения, которая предусматривает отмену всех выполняемых запросов, останов текущих доменов приложений и перезапуск доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="63b83-173">If the soft recycle fails, the server initiates a hard application domain recycle that cancels all in-progress requests, shuts down the current application domains, and restarts the application domains.</span></span>  
  
    -   <span data-ttu-id="63b83-174">Возникновение ошибок при осуществлении операций выделения памяти указывает на то, что системные ресурсы являются недостаточными для объема обработки отчетов, выполняемого сервером.</span><span class="sxs-lookup"><span data-stu-id="63b83-174">Memory allocation failures indicate that system resources are insufficient for the amount of report processing performed by the server.</span></span> <span data-ttu-id="63b83-175">Операция жесткой очистки для всех доменов приложений происходит в ответ на ошибку операции выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="63b83-175">A hard recycle operation for all application domains occurs in response to a memory allocation failure.</span></span> <span data-ttu-id="63b83-176">Все очереди запросов очищаются.</span><span class="sxs-lookup"><span data-stu-id="63b83-176">All request queues are cleared.</span></span> <span data-ttu-id="63b83-177">Отмененные запросы не перезапускаются.</span><span class="sxs-lookup"><span data-stu-id="63b83-177">Canceled requests are not restarted.</span></span> <span data-ttu-id="63b83-178">Пользователи, которые просматривали отчет в оперативном режиме, должны обновить или повторно открыть отчет.</span><span class="sxs-lookup"><span data-stu-id="63b83-178">Users who were interactively viewing a report must refresh or reopen the report.</span></span> <span data-ttu-id="63b83-179">Плановая обработка произойдет в следующий запланированный момент времени.</span><span class="sxs-lookup"><span data-stu-id="63b83-179">Scheduled processing will occur at the next scheduled time.</span></span> <span data-ttu-id="63b83-180">Если связанная с этим задержка недопустима, то можно обновить моментальный снимок отчета вручную, либо изменить расписание подписки или расписание моментальных снимков отчетов, чтобы требуемая обработка была выполнена немедленно.</span><span class="sxs-lookup"><span data-stu-id="63b83-180">If the delay is unacceptable, you can refresh a report snapshot manually or modify a subscription schedule or report snapshot schedule so that it runs immediately.</span></span>  
  
 <span data-ttu-id="63b83-181">Очистка доменов приложений для веб-службы сервера отчетов, диспетчера отчетов и приложения фоновой обработки может осуществляться вместе или отдельно, в зависимости от обстоятельств, которые приводят к выполнению очистки.</span><span class="sxs-lookup"><span data-stu-id="63b83-181">The application domains for the Report Server Web service, Report Manager, and the background processing application might be recycled together or individually, depending on the circumstances that cause the recycling to occur:</span></span>  
  
-   <span data-ttu-id="63b83-182">Операции очистки, инициированные [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)], затрагивают только приложения [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]: Веб-служба сервера отчетов и диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="63b83-182">Recycle operations initiated by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] affect only the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications: Report Server Web service and Report Manager.</span></span> [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="63b83-183">очистка доменов приложений зависит от того, имеются ли изменения в отслеживаемых файлах.</span><span class="sxs-lookup"><span data-stu-id="63b83-183">will recycle application domains based if there are changes to the files that it monitors.</span></span> <span data-ttu-id="63b83-184">Операции очистки, которые инициированы [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] , как правило, являются независимыми от операций очистки, относящихся к приложениям фоновой обработки.</span><span class="sxs-lookup"><span data-stu-id="63b83-184">Recycle operations that are initiated by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] are typically independent of recycle operations for the background processing application.</span></span>  
  
-   <span data-ttu-id="63b83-185">Операции очистки, инициированные сервером отчетов, обычно затрагивают веб-службу сервера отчетов, диспетчер отчетов и приложение фоновой обработки.</span><span class="sxs-lookup"><span data-stu-id="63b83-185">Recycle operations initiated by the report server typically affect Report Server Web service, Report Manager, and the background processing application.</span></span> <span data-ttu-id="63b83-186">Операции очистки происходят в ответ на изменения значений параметров конфигурации и перезапуска службы.</span><span class="sxs-lookup"><span data-stu-id="63b83-186">Recycle operations occur in response to changes to the configuration settings and service restarts.</span></span>  
  
## <a name="rsreportserver-configuration-settings-for-application-domains"></a><span data-ttu-id="63b83-187">Значения параметров конфигурации RSReportServer для доменов приложений</span><span class="sxs-lookup"><span data-stu-id="63b83-187">RSReportServer Configuration Settings for Application Domains</span></span>  
 <span data-ttu-id="63b83-188">Параметры конфигурации задаются в файле [RSReportServer.config](rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="63b83-188">Configuration settings are specified in the in the [RSReportServer.config file](rsreportserver-config-configuration-file.md).</span></span> <span data-ttu-id="63b83-189">В следующем примере показаны параметры конфигурации по умолчанию, относящиеся к запланированному выполнению очистки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="63b83-189">The following example shows the default configuration settings for planned application domain recycling behavior.</span></span>  
  
 `<RecycleTime>720</RecycleTime>`  
  
 `<MaxAppDomainUnloadTime>30</MaxAppDomainUnloadTime>`  
  
 <span data-ttu-id="63b83-190">Эти элементы описываются в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="63b83-190">The following table describes these elements.</span></span>  
  
|<span data-ttu-id="63b83-191">Элемент</span><span class="sxs-lookup"><span data-stu-id="63b83-191">Element</span></span>|<span data-ttu-id="63b83-192">Применяется к</span><span class="sxs-lookup"><span data-stu-id="63b83-192">Applies to</span></span>|<span data-ttu-id="63b83-193">Определение</span><span class="sxs-lookup"><span data-stu-id="63b83-193">Definition</span></span>|  
|-------------|----------------|----------------|  
|`RecycleTime`|<span data-ttu-id="63b83-194">Все три домена приложений служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63b83-194">All three [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] application domains</span></span>|<span data-ttu-id="63b83-195">Указывает, как часто происходит очистка доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="63b83-195">Specifies how often the application domains are recycled.</span></span> <span data-ttu-id="63b83-196">По умолчанию расписание очистки соответствует 12-часовой схеме, обычно применяемой для очистки домена приложения [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63b83-196">The default recycle schedule conforms to the 12-hour pattern typically followed for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application domain recycling.</span></span> <span data-ttu-id="63b83-197">С указанного в расписании времени все новые запросы перенаправляются новому экземпляру домена приложений.</span><span class="sxs-lookup"><span data-stu-id="63b83-197">At the scheduled time, all new requests are forwarded to a new instance of the application domain.</span></span> <span data-ttu-id="63b83-198">Запросы, которые в данный момент выполняются на исходном экземпляре, отрабатывают до завершения.</span><span class="sxs-lookup"><span data-stu-id="63b83-198">Requests that are currently in progress in the original instance are allowed to complete.</span></span> <span data-ttu-id="63b83-199">После завершения всех процессов исходный экземпляр удаляется, а новый экземпляр становится единственным активным экземпляром домена приложений.</span><span class="sxs-lookup"><span data-stu-id="63b83-199">Once all processes are complete, the original instance is deleted and the new instance becomes the sole active application domain instance.</span></span><br /><br /> <span data-ttu-id="63b83-200">Значение по умолчанию составляет 720 минут.</span><span class="sxs-lookup"><span data-stu-id="63b83-200">The default value is 720 minutes.</span></span>|  
|`MaxAppDomainUnloadTime`|<span data-ttu-id="63b83-201">Только домен приложения фоновой обработки</span><span class="sxs-lookup"><span data-stu-id="63b83-201">Background processing application domain only</span></span>|<span data-ttu-id="63b83-202">По умолчанию сервер отчетов предоставляет 30 минут для завершения работы домена приложения во время операции очистки.</span><span class="sxs-lookup"><span data-stu-id="63b83-202">By default, a report server allocates a wait time of 30 minutes, during which an application domain is allowed to shut down during a recycle operation.</span></span> <span data-ttu-id="63b83-203">Если выполняемые задания не могут быть завершены в течение предоставленного времени (или если задание занимает больше времени, чем позволяет период ожидания), экземпляр домена приложения немедленно перезапускается.</span><span class="sxs-lookup"><span data-stu-id="63b83-203">If the jobs that are currently in process cannot be completed during the allotted time (or if a job is taking longer than the wait time allows), the application domain instance is restarted immediately.</span></span> <span data-ttu-id="63b83-204">Все незавершенные задания прерываются.</span><span class="sxs-lookup"><span data-stu-id="63b83-204">All incomplete jobs are terminated.</span></span><br /><br /> <span data-ttu-id="63b83-205">Дополнительные сведения о просмотре состояния или отмене заданий, выполняемых на сервере отчетов, см. в разделе [Отмена заданий сервера отчетов (среда Management Studio)](../tools/cancel-report-server-jobs-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="63b83-205">For more information about how to view status or cancel jobs that running on the report server, see [Cancel Report Server Jobs &#40;Management Studio&#41;](../tools/cancel-report-server-jobs-management-studio.md).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="63b83-206">Хотя веб-служба сервера отчетов и диспетчер отчетов являются приложениями [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] , они не реагируют на плановую очистку домена приложений, которая может быть указана в файле machine.config для приложений [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] , развернутых на сервере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="63b83-206">Although the Report Server Web service and Report Manager are [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications, neither application responds to scheduled application domain recycling that might be specified in machine.config for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b83-207">См. также:</span><span class="sxs-lookup"><span data-stu-id="63b83-207">See Also</span></span>  
 <span data-ttu-id="63b83-208">[Файл конфигурации RSReportServer](rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="63b83-208">[RSReportServer Configuration File](rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="63b83-209">[Изменение файла конфигурации служб Reporting Services (RSreportserver.config)](modify-a-reporting-services-configuration-file-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="63b83-209">[Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="63b83-210">Настройка доступной памяти для приложений сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="63b83-210">Configure Available Memory for Report Server Applications</span></span>](../report-server/configure-available-memory-for-report-server-applications.md)  
  
  