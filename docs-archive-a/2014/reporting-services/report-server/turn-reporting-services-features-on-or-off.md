---
title: Включение и отключение компонентов Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, configuration
- security [Reporting Services], strategies
ms.assetid: b69db02a-43a7-4fdc-ad9b-438d817a7f83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f56f9984b5b02431db23b782652e5575af557bdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659334"
---
# <a name="turn-reporting-services-features-on-or-off"></a><span data-ttu-id="9c711-102">Включение и отключение компонентов служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9c711-102">Turn Reporting Services Features On or Off</span></span>
  <span data-ttu-id="9c711-103">Неиспользуемые функции сервера отчетов можно отключить в рамках блокирующей стратегии, позволяющей снизить риск атак на рабочий сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="9c711-103">You can turn off report server features that you do not use as part of a lockdown strategy for reducing the attack surface of a production report server.</span></span> <span data-ttu-id="9c711-104">В большинстве случаев рекомендуется использовать функции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] параллельно; это позволит использовать все функциональные возможности, предоставляемые службами [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c711-104">In most cases, you will want to run [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features concurrently to use all of the functionality provided in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9c711-105">Однако в зависимости от используемой модели развертывания можно отключить неиспользуемые функции.</span><span class="sxs-lookup"><span data-stu-id="9c711-105">However, depending on your deployment model, you can disable the features that you do not require.</span></span> <span data-ttu-id="9c711-106">Например, если вся обработка отчетов производится с использованием операций по расписанию, то можно разрешить только фоновую обработку.</span><span class="sxs-lookup"><span data-stu-id="9c711-106">For example, you can enable only the background processing if all report processing is configured as scheduled operations.</span></span> <span data-ttu-id="9c711-107">Подобным же образом можно ограничиться запуском веб-службы сервера отчетов, если необходимо только интерактивное получение отчетов по требованию.</span><span class="sxs-lookup"><span data-stu-id="9c711-107">Similarly, you can run just the Report Server Web service if you only want interactive, on-demand reporting.</span></span>  
  
 <span data-ttu-id="9c711-108">В процедурах, приведенных в данном разделе, показывается, как можно отключать функции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="9c711-108">The procedures in this topic show you how to turn off native mode [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="9c711-109">Настройку функций можно выполнить разными способами, например, напрямую изменив файл `RsReportServer.config` или используя аспект **Настройка контактной зоны для служб Reporting Services** управления на основе политик в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c711-109">Features can be configured in different ways, such as by editing the `RsReportServer.config` file directly or by using the **Surface Area Configuration for Reporting Services** facet of Policy-Based Management in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="9c711-110">Используйте ссылки, чтобы найти одну или несколько процедур, в которых объясняется, как можно включить или выключить функцию.</span><span class="sxs-lookup"><span data-stu-id="9c711-110">Use the links to locate the procedure or procedures that explain how to turn a feature on or off:</span></span>  
  
-   [<span data-ttu-id="9c711-111">Веб-служба сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="9c711-111">Report Server Web service</span></span>](#RSWebSvc)  
  
-   [<span data-ttu-id="9c711-112">запланированные события и обработка;</span><span class="sxs-lookup"><span data-stu-id="9c711-112">Scheduled events and processing</span></span>](#Sched)  
  
-   [<span data-ttu-id="9c711-113">Диспетчер отчетов</span><span class="sxs-lookup"><span data-stu-id="9c711-113">Report Manager</span></span>](#ReportManager)  
  
-   [<span data-ttu-id="9c711-114">построитель отчетов</span><span class="sxs-lookup"><span data-stu-id="9c711-114">Report Builder</span></span>](#ReportBuilder)  
  
-   [<span data-ttu-id="9c711-115">Встроенная безопасность Windows для источников данных для отчетов</span><span class="sxs-lookup"><span data-stu-id="9c711-115">Windows Integrated security for report data sources</span></span>](#WinIntSec)  
  
##  <a name="report-server-web-service"></a><a name="RSWebSvc"></a><span data-ttu-id="9c711-116">Веб-служба сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="9c711-116">Report Server Web Service</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-editing-configuration"></a><span data-ttu-id="9c711-117">Включение или выключение веб-службы сервера отчетов методом изменения конфигурации</span><span class="sxs-lookup"><span data-stu-id="9c711-117">To turn on or off the Report Server Web service by editing configuration</span></span>  
  
1.  <span data-ttu-id="9c711-118">Откройте файл `RsReportServer.config` в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="9c711-118">Open the `RsReportServer.config` file in a text editor.</span></span> <span data-ttu-id="9c711-119">Дополнительные сведения см. в разделе [Изменение файла конфигурации служб Reporting Services (RSreportserver.config)](modify-a-reporting-services-configuration-file-rsreportserver-config.md) в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c711-119">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="9c711-120">Для включения веб-службы сервера отчетов установите для свойства `IsWebServiceEnabled` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9c711-120">To turn on the Report Server Web service, set `IsWebServiceEnabled` to `true`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>true</IsWebServiceEnabled>  
    ```  
  
3.  <span data-ttu-id="9c711-121">Для выключения веб-службы сервера отчетов установите для свойства `IsWebServiceEnabled` значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9c711-121">To turn off the Report Server Web service, set `IsWebServiceEnabled` to `false`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>false</IsWebServiceEnabled>  
    ```  
  
4.  <span data-ttu-id="9c711-122">Сохраните внесенные изменения и закройте файл.</span><span class="sxs-lookup"><span data-stu-id="9c711-122">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-using-sql-server-management-studio"></a><span data-ttu-id="9c711-123">Включение или выключение веб-службы сервера отчетов с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c711-123">To turn on or off the Report Server Web service by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="9c711-124">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , который следует настроить.</span><span class="sxs-lookup"><span data-stu-id="9c711-124">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="9c711-125">В обозревателе объектов щелкните правой кнопкой мыши [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] узел, укажите пункт **политики**и выберите пункт **аспекты**.</span><span class="sxs-lookup"><span data-stu-id="9c711-125">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="9c711-126">В списке **Аспект** выберите **Настройка контактной зоны для служб Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="9c711-126">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="9c711-127">В разделе **Свойства аспекта**можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9c711-127">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="9c711-128">Чтобы включить веб-службу сервера отчетов, задайте для **webserviceandhttpaccessenabled присвоено** значение `True` .</span><span class="sxs-lookup"><span data-stu-id="9c711-128">To turn on the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="9c711-129">Чтобы отключить веб-службу сервера отчетов, задайте для **webserviceandhttpaccessenabled присвоено** значение `False` .</span><span class="sxs-lookup"><span data-stu-id="9c711-129">To turn off the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="scheduled-events-and-delivery"></a><a name="Sched"></a> <span data-ttu-id="9c711-130">Запланированные события и доставка</span><span class="sxs-lookup"><span data-stu-id="9c711-130">Scheduled Events and Delivery</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-editing-configuration"></a><span data-ttu-id="9c711-131">Включение или выключение запланированных событий и доставки методом изменения конфигурации</span><span class="sxs-lookup"><span data-stu-id="9c711-131">To turn on or off scheduled events and delivery by editing configuration</span></span>  
  
1.  <span data-ttu-id="9c711-132">Откройте файл RsReportServer.config в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="9c711-132">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="9c711-133">Дополнительные сведения см. в разделе [Изменение файла конфигурации служб Reporting Services (RSreportserver.config)](modify-a-reporting-services-configuration-file-rsreportserver-config.md) в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c711-133">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="9c711-134">Чтобы включить запланированные операции по обработке и доставке отчетов, присвойте значение `IsSchedulingService` свойствам `IsNotificationService`, `IsEventService` и `true`:</span><span class="sxs-lookup"><span data-stu-id="9c711-134">To turn on scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `true`:</span></span>  
  
    ```  
    <IsSchedulingService>true</IsSchedulingService>  
    <IsNotificationService>true</IsNotificationService>  
    <IsEventService>true</IsEventService>  
    ```  
  
3.  <span data-ttu-id="9c711-135">Чтобы отключить запланированные операции по обработке и доставке отчетов, присвойте значение `IsSchedulingService` свойствам `IsNotificationService`, `IsEventService` и `false`:</span><span class="sxs-lookup"><span data-stu-id="9c711-135">To turn off scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `false`:</span></span>  
  
    ```  
    <IsSchedulingService>false</IsSchedulingService>  
    <IsNotificationService>false</IsNotificationService>  
    <IsEventService>false</IsEventService>  
    ```  
  
4.  <span data-ttu-id="9c711-136">Сохраните внесенные изменения и закройте файл.</span><span class="sxs-lookup"><span data-stu-id="9c711-136">Save your changes and then close the file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c711-137">Фоновую обработку нельзя отключить полностью, поскольку она обеспечивает функциональные возможности обслуживания базы данных, необходимые для операций сервера.</span><span class="sxs-lookup"><span data-stu-id="9c711-137">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-using-sql-server-management-studio"></a><span data-ttu-id="9c711-138">Включение или отключение запланированных событий и доставки с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c711-138">To turn on or off scheduled events and delivery by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="9c711-139">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , который следует настроить.</span><span class="sxs-lookup"><span data-stu-id="9c711-139">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="9c711-140">В обозревателе объектов щелкните правой кнопкой мыши [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] узел, укажите пункт **политики**и выберите пункт **аспекты**.</span><span class="sxs-lookup"><span data-stu-id="9c711-140">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="9c711-141">В списке **Аспект** выберите **Настройка контактной зоны для служб Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="9c711-141">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="9c711-142">В разделе **Свойства аспекта**можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9c711-142">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="9c711-143">Чтобы включить запланированные события и доставку, задайте для **присвойте scheduleeventsandreportdeliveryenabled** значение `True` .</span><span class="sxs-lookup"><span data-stu-id="9c711-143">To turn on scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="9c711-144">Чтобы отключить запланированные события и доставку, задайте для **присвойте scheduleeventsandreportdeliveryenabled** значение `False` .</span><span class="sxs-lookup"><span data-stu-id="9c711-144">To turn off scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="9c711-145">Фоновую обработку нельзя отключить полностью, поскольку она обеспечивает функциональные возможности обслуживания базы данных, необходимые для операций сервера.</span><span class="sxs-lookup"><span data-stu-id="9c711-145">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
##  <a name="report-manager"></a><a name="ReportManager"></a><span data-ttu-id="9c711-146">диспетчер отчетов</span><span class="sxs-lookup"><span data-stu-id="9c711-146">Report Manager</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-editing-configuration"></a><span data-ttu-id="9c711-147">Включение или отключение диспетчера отчетов методом изменения конфигурации</span><span class="sxs-lookup"><span data-stu-id="9c711-147">To turn on or off Report Manager by editing configuration</span></span>  
  
1.  <span data-ttu-id="9c711-148">Откройте файл RsReportServer.config в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="9c711-148">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="9c711-149">Инструкции см. в разделе [Изменение файла конфигурации служб Reporting Services (RSreportserver.config)](modify-a-reporting-services-configuration-file-rsreportserver-config.md) в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c711-149">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="9c711-150">Чтобы включить диспетчер отчетов, присвойте свойству `IsReportManagerEnabled` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9c711-150">To turn on Report Manager, set `IsReportManagerEnabled` to `true`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>true</IsReportManagerEnabled>  
    ```  
  
3.  <span data-ttu-id="9c711-151">Чтобы отключить диспетчер отчетов, присвойте свойству `IsReportManagerEnabled` значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9c711-151">To turn off Report Manager, set `IsReportManagerEnabled` to `false`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>false</IsReportManagerEnabled>  
    ```  
  
4.  <span data-ttu-id="9c711-152">Сохраните внесенные изменения и закройте файл.</span><span class="sxs-lookup"><span data-stu-id="9c711-152">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-using-sql-server-management-studio"></a><span data-ttu-id="9c711-153">Включение или отключение диспетчера отчетов с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c711-153">To turn on or off Report Manager by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="9c711-154">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , который следует настроить.</span><span class="sxs-lookup"><span data-stu-id="9c711-154">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="9c711-155">В **обозревателе объектов**щелкните правой кнопкой узел служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , укажите пункт **Политики**и выберите **Аспекты**.</span><span class="sxs-lookup"><span data-stu-id="9c711-155">In **Object Explorer**, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="9c711-156">В списке **Аспект** выберите **Настройка контактной зоны для служб Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="9c711-156">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="9c711-157">В разделе **Свойства аспекта**можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9c711-157">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="9c711-158">Чтобы включить диспетчер отчетов, задайте для **присвойте reportmanagerenabled** значение `True` .</span><span class="sxs-lookup"><span data-stu-id="9c711-158">To turn on Report Manager, set **ReportManagerEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="9c711-159">Чтобы отключить диспетчер отчетов, задайте для **присвойте reportmanagerenabled** значение `False` .</span><span class="sxs-lookup"><span data-stu-id="9c711-159">To turn off Report Manager, set **ReportManagerEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="report-builder"></a><span data-ttu-id="9c711-160">Построитель отчетов <a name="ReportBuilder"></a></span><span class="sxs-lookup"><span data-stu-id="9c711-160"><a name="ReportBuilder"></a> Report Builder</span></span>  
  
#### <a name="to-turn-on-or-off-report-builder-by-using-sql-server-management-studio"></a><span data-ttu-id="9c711-161">Включение или отключение построителя отчетов с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c711-161">To turn on or off Report Builder by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="9c711-162">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , который следует настроить.</span><span class="sxs-lookup"><span data-stu-id="9c711-162">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="9c711-163">В обозревателе объектов щелкните правой кнопкой мыши узел служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9c711-163">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9c711-164">В диалоговом окне **Свойства сервера** в области **Выбор страницы**щелкните **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="9c711-164">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="9c711-165">Чтобы включить построитель отчетов, установите флажок **Разрешить выполнение нерегламентированных отчетов** .</span><span class="sxs-lookup"><span data-stu-id="9c711-165">To turn on Report Builder, select the **Enable ad hoc report executions** option.</span></span>  
  
    -   <span data-ttu-id="9c711-166">Чтобы отключить построитель отчетов, снимите флажок **Разрешить выполнение нерегламентированных отчетов** .</span><span class="sxs-lookup"><span data-stu-id="9c711-166">To turn off Report Builder, unselect the **Enable ad hoc report executions** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="windows-integrated-security"></a><a name="WinIntSec"></a> <span data-ttu-id="9c711-167">Встроенная безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="9c711-167">Windows Integrated Security</span></span>  
  
#### <a name="to-turn-on-or-off-windows-integrated-security-by-using-sql-server-management-studio"></a><span data-ttu-id="9c711-168">Включение или отключение встроенной безопасности Windows с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c711-168">To turn on or off Windows Integrated security by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="9c711-169">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , который следует настроить.</span><span class="sxs-lookup"><span data-stu-id="9c711-169">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="9c711-170">В обозревателе объектов щелкните правой кнопкой мыши узел служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9c711-170">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9c711-171">В диалоговом окне **Свойства сервера** в области **Выбор страницы**щелкните **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="9c711-171">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="9c711-172">Чтобы включить встроенную безопасность Windows, установите флажок **Использовать встроенную безопасность Windows для источников данных для отчетов** .</span><span class="sxs-lookup"><span data-stu-id="9c711-172">To turn on Windows Integrated security, select the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
    -   <span data-ttu-id="9c711-173">Чтобы отключить встроенную безопасность Windows, снимите флажок **Использовать встроенную безопасность Windows для источников данных для отчетов** .</span><span class="sxs-lookup"><span data-stu-id="9c711-173">To turn off Windows integrated security, unselect the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9c711-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c711-174">See Also</span></span>  
 [<span data-ttu-id="9c711-175">Использование диспетчера конфигурации служб Reporting Services (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="9c711-175">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
