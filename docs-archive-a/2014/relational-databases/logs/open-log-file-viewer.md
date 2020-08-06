---
title: Открытие средства просмотра журналов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, opening
ms.assetid: a86b89cb-0432-4648-895a-05ecc5450e45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269ff10275f7463a8a85249a2a0f06fe9bde364a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658247"
---
# <a name="open-log-file-viewer"></a><span data-ttu-id="a3557-102">Открытие средства просмотра файла журнала</span><span class="sxs-lookup"><span data-stu-id="a3557-102">Open Log File Viewer</span></span>
  <span data-ttu-id="a3557-103">Средство просмотра журнала используется в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для доступа к сведениям об ошибках и событиях, записываемых в следующие журналы.</span><span class="sxs-lookup"><span data-stu-id="a3557-103">You can use Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to access information about errors and events that are captured in the following logs:</span></span>  
  
-   <span data-ttu-id="a3557-104">Коллекция аудита</span><span class="sxs-lookup"><span data-stu-id="a3557-104">Audit Collection</span></span>  
  
-   <span data-ttu-id="a3557-105">Сбор данных</span><span class="sxs-lookup"><span data-stu-id="a3557-105">Data Collection</span></span>  
  
-   <span data-ttu-id="a3557-106">Database Mail</span><span class="sxs-lookup"><span data-stu-id="a3557-106">Database Mail</span></span>  
  
-   <span data-ttu-id="a3557-107">Журнал заданий</span><span class="sxs-lookup"><span data-stu-id="a3557-107">Job History</span></span>  
  
-   <span data-ttu-id="a3557-108">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3557-108">SQL Server</span></span>  
  
-   <span data-ttu-id="a3557-109">Агент SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3557-109">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="a3557-110">События Windows (К ним можно получить доступ с помощью программы просмотра событий Windows.)</span><span class="sxs-lookup"><span data-stu-id="a3557-110">Windows events (These Windows events can also be accessed from Event Viewer.)</span></span>  
  
 <span data-ttu-id="a3557-111">Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], в списке «Зарегистрированные серверы» можно просматривать файлы журналов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на локальных и удаленных экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3557-111">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can use Registered Servers to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from local or remote instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a3557-112">В списке «Зарегистрированные серверы» можно просматривать файлы журнала как для экземпляров в сети, так и для экземпляров вне сети.</span><span class="sxs-lookup"><span data-stu-id="a3557-112">By using Registered Servers, you can view the log files when the instances are either online or offline.</span></span> <span data-ttu-id="a3557-113">Дополнительные сведения о доступе в сети см. далее в разделе «Просмотр файлов журнала в сети с зарегистрированных серверов».</span><span class="sxs-lookup"><span data-stu-id="a3557-113">For more information about online access, see the procedure "To view online log files from Registered Servers" later in this topic.</span></span> <span data-ttu-id="a3557-114">Дополнительные сведения о доступе к автономным файлам журнала [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Просмотр автономных файлов журнала](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="a3557-114">For more information about how to access offline [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files, see [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
 <span data-ttu-id="a3557-115">Открыть средство просмотра журнала можно несколькими способами (в зависимости от того, какие сведения нужно просмотреть).</span><span class="sxs-lookup"><span data-stu-id="a3557-115">You can open Log File Viewer in several ways, depending on the information that you want to view.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a3557-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="a3557-116">Permissions</span></span>  
 <span data-ttu-id="a3557-117">Чтобы получить доступ к файлам журнала для экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые находятся в сети, требуется членство в предопределенной роли сервера securityadmin.</span><span class="sxs-lookup"><span data-stu-id="a3557-117">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="a3557-118">Чтобы получить доступ к файлам журнала для экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые находятся вне сети, необходим доступ на чтение к пространству WMI **Root\Microsoft\SqlServer\ComputerManagement10** , а также к папке, в которой хранятся файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="a3557-118">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="a3557-119">Дополнительные сведения см. в подразделе "Безопасность" раздела [Просмотр автономных файлов журнала](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="a3557-119">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
### <a name="security"></a><span data-ttu-id="a3557-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a3557-120">Security</span></span>  
 <span data-ttu-id="a3557-121">Требуется членство в предопределенной роли сервера securityadmin.</span><span class="sxs-lookup"><span data-stu-id="a3557-121">Requires membership in the securityadmin fixed server role.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="a3557-122">Просмотр файлов журнала</span><span class="sxs-lookup"><span data-stu-id="a3557-122">View Log Files</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-general-sql-server-activity"></a><span data-ttu-id="a3557-123">Просмотр журналов, связанных с общими операциями SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3557-123">To view logs that are related to general SQL Server activity</span></span>  
  
1.  <span data-ttu-id="a3557-124">В обозревателе объектов разверните узел **Управление**.</span><span class="sxs-lookup"><span data-stu-id="a3557-124">In Object Explorer, expand **Management**.</span></span>  
  
2.  <span data-ttu-id="a3557-125">Выполните одно из приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a3557-125">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="a3557-126">Щелкните правой кнопкой мыши **Журналы SQL Server**, выберите **Просмотр**, а затем **Журнал SQL Server** или **Журнал SQL Server и Windows**.</span><span class="sxs-lookup"><span data-stu-id="a3557-126">Right-click **SQL Server Logs**, point to **View**, and then click either **SQL Server Log** or **SQL Server and Windows Log**.</span></span>  
  
    -   <span data-ttu-id="a3557-127">Разверните узел **Журналы SQL Server**, щелкните правой кнопкой мыши любой файл журнала и выберите **Просмотреть журнал SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a3557-127">Expand **SQL Server Logs**, right-click any log file, and then click **View SQL Server Log**.</span></span> <span data-ttu-id="a3557-128">Можно также дважды щелкнуть любой файл журнала.</span><span class="sxs-lookup"><span data-stu-id="a3557-128">You can also double-click any log file.</span></span>  
  
     <span data-ttu-id="a3557-129">Доступны журналы **Компонент Database Mail**, **SQL Server**, **Агент SQL Server**и **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="a3557-129">The logs include **Database Mail**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-jobs"></a><span data-ttu-id="a3557-130">Просмотр журналов, связанных с заданиями</span><span class="sxs-lookup"><span data-stu-id="a3557-130">To view logs that are related to jobs</span></span>  
  
-   <span data-ttu-id="a3557-131">В обозревателе объектов откройте **Агент SQL Server**, щелкните правой кнопкой мыши **Задания**и выберите **Просмотр журнала**.</span><span class="sxs-lookup"><span data-stu-id="a3557-131">In Object Explorer, expand **SQL Server Agent**, right-click **Jobs**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="a3557-132">Доступны журналы **Компонент Database Mail**, **Журнал заданий**и **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a3557-132">The logs include **Database Mail**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-maintenance-plans"></a><span data-ttu-id="a3557-133">Просмотр журналов, связанных с планами обслуживания</span><span class="sxs-lookup"><span data-stu-id="a3557-133">To view logs that are related to maintenance plans</span></span>  
  
-   <span data-ttu-id="a3557-134">В обозревателе объектов раскройте узел **Управление**, щелкните правой кнопкой мыши **Планы обслуживания**и выберите **Просмотр журнала**.</span><span class="sxs-lookup"><span data-stu-id="a3557-134">In Object Explorer, expand **Management**, right-click **Maintenance Plans**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="a3557-135">Доступны журналы **Компонент Database Mail**, **Журнал заданий**, **Планы обслуживания**, **План удаленного обслуживания**и **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a3557-135">The logs include **Database Mail**, **Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-data-collection"></a><span data-ttu-id="a3557-136">Просмотр журналов, связанных с коллекциями данных</span><span class="sxs-lookup"><span data-stu-id="a3557-136">To view logs that are related to Data Collection</span></span>  
  
-   <span data-ttu-id="a3557-137">В обозревателе объектов раскройте узел **Управление**, щелкните правой кнопкой мыши **Сбор данных**и выберите команду **Просмотреть журналы**.</span><span class="sxs-lookup"><span data-stu-id="a3557-137">In Object Explorer, expand **Management**, right-click **Data Collection**, and then click **View Logs**.</span></span>  
  
     <span data-ttu-id="a3557-138">Доступны журналы **Сбор данных**, **Журнал заданий**и **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a3557-138">The logs include **Data Collection**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-database-mail"></a><span data-ttu-id="a3557-139">Просмотр журналов, связанных с компонентом Database Mail</span><span class="sxs-lookup"><span data-stu-id="a3557-139">To view logs that are related to Database Mail</span></span>  
  
-   <span data-ttu-id="a3557-140">В обозревателе объектов раскройте узел **Управление**, щелкните правой кнопкой мыши **Компонент Database Mail**и выберите команду **Просмотреть журнал компонента Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="a3557-140">In Object Explorer, expand **Management**, right-click **Database Mail**, and then click **View Database Mail Log**.</span></span>  
  
     <span data-ttu-id="a3557-141">Доступны журналы **Компонент Database Mail, Журнал заданий**, **Планы обслуживания**, **Планы удаленного обслуживания**, **SQL Server**, **Агент SQL Server**и **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="a3557-141">The logs include **Database Mail, Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="a3557-142">Просмотр журналов, связанных с коллекциями аудитов</span><span class="sxs-lookup"><span data-stu-id="a3557-142">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="a3557-143">В обозревателе объектов разверните узел **Безопасность**, затем узел **Аудиты**, щелкните правой кнопкой мыши аудит и выберите команду **Просмотреть журналы**.</span><span class="sxs-lookup"><span data-stu-id="a3557-143">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="a3557-144">Доступны журналы **Коллекция аудитов** и **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="a3557-144">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="a3557-145">Просмотр журналов, связанных с коллекциями аудитов</span><span class="sxs-lookup"><span data-stu-id="a3557-145">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="a3557-146">В обозревателе объектов разверните узел **Безопасность**, затем узел **Аудиты**, щелкните правой кнопкой мыши аудит и выберите команду **Просмотреть журналы**.</span><span class="sxs-lookup"><span data-stu-id="a3557-146">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="a3557-147">Доступны журналы **Коллекция аудитов** и **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="a3557-147">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3557-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="a3557-148">See Also</span></span>  
 <span data-ttu-id="a3557-149">[Средство просмотра файлов журнала](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="a3557-149">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="a3557-150">[Подсистема аудита SQL Server (компонент Database Engine)](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="a3557-150">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="a3557-151">Просмотр автономных файлов журнала</span><span class="sxs-lookup"><span data-stu-id="a3557-151">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
