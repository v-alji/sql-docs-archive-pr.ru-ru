---
title: Мониторинг SQL Server управляемого резервного копирования в Azure | Документация Майкрософт
description: В этой статье описываются средства, которые можно использовать для определения общей работоспособности резервных копий с помощью SQL Server управляемого резервного копирования в Azure и выявления ошибок.
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: cfb9e431-7d4c-457c-b090-6f2528b2f315
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: baec99e63c70befde0cfce76e42dd6202ebc0bad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667888"
---
# <a name="monitor-sql-server-managed-backup-to-azure"></a><span data-ttu-id="ae38d-103">Мониторинг управляемого резервного копирования SQL Server в Azure</span><span class="sxs-lookup"><span data-stu-id="ae38d-103">Monitor SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="ae38d-104">В [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] предусмотрены встроенные меры по определению неполадок и ошибок в процессе резервного копирования, а также действия по исправлению, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="ae38d-104">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has built-in measures to identify problems and errors during backup processes and remedy with corrective action when possible.</span></span>  <span data-ttu-id="ae38d-105">Однако есть некоторые решения, для которых требуется участие пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae38d-105">However there are certain situations where user intervention is required.</span></span> <span data-ttu-id="ae38d-106">В этом разделе описаны средства, с помощью которых можно определять общее состояние исправности резервных копий, а также определять любые ошибки, которые требуют устранения.</span><span class="sxs-lookup"><span data-stu-id="ae38d-106">This topic describes the tools that you can use to determine the overall health status of backups, and identify any errors that need to be addressed.</span></span>  
  
## <a name="overview-of-ss_smartbackup-built-in-debugging"></a><span data-ttu-id="ae38d-107">Обзор встроенной отладки [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae38d-107">Overview of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Built-in Debugging</span></span>  
 <span data-ttu-id="ae38d-108">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] периодически просматривает запланированные сеансы резервного копирования и пытается повторно запланировать те, что завершились с ошибками.</span><span class="sxs-lookup"><span data-stu-id="ae38d-108">The [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] periodically reviews scheduled backups and attempts to reschedule any failed backups.</span></span> <span data-ttu-id="ae38d-109">Он периодически опрашивает учетную запись хранения, чтобы найти разрыв в цепочке журналов, влияющий на восстанавливаемость базы данных, и планирует соответствующим образом новое резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="ae38d-109">It polls the storage account periodically to identify breaks in log chains affecting recoverability of the database, and schedules new backups accordingly.</span></span> <span data-ttu-id="ae38d-110">Он также учитывает политики регулирования Azure и имеет механизмы для управления несколькими резервными копиями баз данных.</span><span class="sxs-lookup"><span data-stu-id="ae38d-110">It also takes into account Azure throttling policies, and has mechanisms in place to manage multiple database backups.</span></span> <span data-ttu-id="ae38d-111">Служба [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] использует расширенные события для отслеживания всех действий.</span><span class="sxs-lookup"><span data-stu-id="ae38d-111">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] uses extended events to track all activity.</span></span> <span data-ttu-id="ae38d-112">Далее перечислены каналы расширенных событий, используемые агентом [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]: Admin, Operational, Analytical и Debug.</span><span class="sxs-lookup"><span data-stu-id="ae38d-112">The Extended Event channels used by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent include, Admin, Operational, Analytical, and Debug.</span></span> <span data-ttu-id="ae38d-113">События, относящиеся к категории Admin, обычно связаны с ошибками, требуют вмешательства пользователя и включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae38d-113">Events that fall under the Admin category usually are related to errors and require user intervention and are enabled by default.</span></span> <span data-ttu-id="ae38d-114">События Analytical также включены по умолчанию, но обычно не связаны с ошибками, требующими вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae38d-114">Analytical events are also turned on by default, but usually are not related to errors that require user intervention.</span></span> <span data-ttu-id="ae38d-115">События операций обычно информационные.</span><span class="sxs-lookup"><span data-stu-id="ae38d-115">Operation events are typically informational.</span></span> <span data-ttu-id="ae38d-116">Например, рабочие события включают в себя планирование резервного копирования, успешное завершение резервного копирования и т. д. Отладка является наиболее подробным и используется для внутренних целей, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] чтобы определить проблемы и исправить их при необходимости.</span><span class="sxs-lookup"><span data-stu-id="ae38d-116">For example, operational events include scheduling a backup, a successful completion of backup, etc. The Debug is the most verbose and is used internally by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] to determine issues and correct them if required.</span></span>  
  
### <a name="configure-monitoring-parameters-for-ss_smartbackup"></a><span data-ttu-id="ae38d-117">Настройка параметров наблюдения для [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae38d-117">Configure Monitoring Parameters for [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span></span>  
 <span data-ttu-id="ae38d-118">Системная хранимая процедура **smart_admin. sp_set_parameter** позволяет указать параметры мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ae38d-118">The **smart_admin.sp_set_parameter** system stored procedure allows you to specify monitoring settings.</span></span> <span data-ttu-id="ae38d-119">В следующих разделах даны пошаговые инструкции по процедуре включения расширенных событий, а также по включению уведомления по электронной почте об ошибках и предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="ae38d-119">The following sections walks through the process of enabling Extended Events,  and enabling email notification for errors and warnings.</span></span>  
  
 <span data-ttu-id="ae38d-120">Функцию **smart_admin. fn_get_parameter** можно использовать для получения текущей настройки для конкретного параметра или всех настроенных параметров.</span><span class="sxs-lookup"><span data-stu-id="ae38d-120">The **smart_admin.fn_get_parameter** function can be used to get the current setting for a specific parameter or all configured parameters.</span></span> <span data-ttu-id="ae38d-121">Если параметры не были настроены, функция не возвращает значения.</span><span class="sxs-lookup"><span data-stu-id="ae38d-121">If the parameters have never been configured, the function does not return any values.</span></span>  
  
1.  <span data-ttu-id="ae38d-122">Установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae38d-122">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ae38d-123">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ae38d-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ae38d-124">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ae38d-124">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="ae38d-125">Будет возвращена текущая конфигурация расширенных событий и уведомлений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="ae38d-125">This will return the current configuration for Extended Events, and e-mail notifications.</span></span>  
  
```sql
Use msdb  
Go  
SELECT * FROM smart_admin.fn_get_parameter (NULL)  
GO  
```  
  
 <span data-ttu-id="ae38d-126">Дополнительные сведения см. в разделе [smart_admin. fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="ae38d-126">For more information, see [smart_admin.fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span></span>  
  
### <a name="extended-events-for-monitoring"></a><span data-ttu-id="ae38d-127">Расширенные события для наблюдения</span><span class="sxs-lookup"><span data-stu-id="ae38d-127">Extended Events for Monitoring</span></span>  
 <span data-ttu-id="ae38d-128">По умолчанию включены события Admin, Operational и Analytical.</span><span class="sxs-lookup"><span data-stu-id="ae38d-128">By default, Admin, Operational and Analytical events are turned on.</span></span> <span data-ttu-id="ae38d-129">События административного канала наиболее важны и полезны при определении ошибок, требующих ручного вмешательства для решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="ae38d-129">Admin events are most critical, useful when identifying errors that require manual intervention to solve the problem.</span></span> <span data-ttu-id="ae38d-130">Возможно, необходимо включить операционные события и события отладки, однако следует иметь в виду, что эти события весьма подробны и могут потребовать фильтрации.</span><span class="sxs-lookup"><span data-stu-id="ae38d-130">You may want to turn on the operational and debug events but consider that these events are verbose and may require some filtering.</span></span> <span data-ttu-id="ae38d-131">В следующих процедурах описывается наблюдение за событиями, занесенными в журнал с помощью расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="ae38d-131">The following procedures describe how to monitor events logged through Extended Events.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ae38d-132">В отличие от расширенных событий для SQL Engine в [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] не поддерживаются сеансы расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="ae38d-132">Unlike Extended Events for SQL Engine, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] does not support Extended Event session concepts.</span></span> <span data-ttu-id="ae38d-133">Системные хранимые процедуры и функции используются для взаимодействия с расширенными событиями.</span><span class="sxs-lookup"><span data-stu-id="ae38d-133">System stored procedures and functions are the tools used to interact with extended events.</span></span> <span data-ttu-id="ae38d-134">Кроме того, можно просматривать журнал расширенных событий из каталога журналов.</span><span class="sxs-lookup"><span data-stu-id="ae38d-134">You can also view the extended event log from the log directory.</span></span>  
  
##### <a name="to-configure-and-view-extended-events"></a><span data-ttu-id="ae38d-135">Настройка и просмотр расширенных событий</span><span class="sxs-lookup"><span data-stu-id="ae38d-135">To Configure and View Extended Events</span></span>  
  
1.  <span data-ttu-id="ae38d-136">Чтобы просмотреть доступные каналы расширенных событий и их текущее состояние, выполните следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="ae38d-136">To view available Extended Event channels and their current status by running the following query:</span></span>  
  
    ```sql
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="ae38d-137">В выходных данных этого запроса отобразится параметр event_name, его доступность для настройки, а также будет показано, включен ли он в данный момент.</span><span class="sxs-lookup"><span data-stu-id="ae38d-137">The output from this query will display the event_name, whether it is configurable or not, and whether it is currently enabled.</span></span>  <span data-ttu-id="ae38d-138">Дополнительные сведения см. в разделе [smart_admin. fn_get_current_xevent_settings &#40;&#41;Transact-SQL ](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae38d-138">For more information, see [smart_admin.fn_get_current_xevent_settings &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span></span>  
  
2.  <span data-ttu-id="ae38d-139">Чтобы включить события отладки, выполните следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="ae38d-139">To enable debug events, run the following query:</span></span>  
  
    ```sql
    --  to enable debug events  
    Use msdb;  
    GO 
    EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
    ```  
  
     <span data-ttu-id="ae38d-140">Дополнительные сведения о хранимой процедуре см. в разделе [smart_admin. sp_set_parameter &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae38d-140">For more information about the stored procedure, see [smart_admin.sp_set_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span></span>  
  
3.  <span data-ttu-id="ae38d-141">Чтобы просмотреть зарегистрированные события, выполните следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="ae38d-141">To view the logged events run the following query:</span></span>  
  
    ```sql
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;
    ```  
  
    ```sql
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'
    ```  
  
### <a name="aggregated-error-countshealth-status"></a><span data-ttu-id="ae38d-142">Суммарное количество ошибок или состояние работоспособности</span><span class="sxs-lookup"><span data-stu-id="ae38d-142">Aggregated Error Counts/Health Status</span></span>  
 <span data-ttu-id="ae38d-143">Функция **smart_admin. fn_get_health_status** возвращает таблицу агрегированных счетчиков ошибок для каждой категории, которая может использоваться для наблюдения за состоянием работоспособности [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae38d-143">The **smart_admin.fn_get_health_status** function returns a table of aggregated error counts for each category that can be used to monitor the health status of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="ae38d-144">Та же функция используется настроенным системой механизмом уведомления по электронной почте, который описывается далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ae38d-144">This same function is also used by the system configured e-mail notification mechanism described later in this topic.</span></span>   
<span data-ttu-id="ae38d-145">Эти суммарные значения можно использовать для контроля состояния работоспособности системы.</span><span class="sxs-lookup"><span data-stu-id="ae38d-145">These aggregated counts can be used to monitor system health.</span></span> <span data-ttu-id="ae38d-146">Например, если столбец «number_ of_retention_loops» имеет значение 0 за 30 минут, то, возможно, управление хранением работает слишком долго или неправильно.</span><span class="sxs-lookup"><span data-stu-id="ae38d-146">For example, if the number_ of_retention_loops column is 0 in 30 minutes, it is possible that retention management is taking long time or even not working correctly.</span></span> <span data-ttu-id="ae38d-147">Ненулевые столбцы ошибок могут означать неполадки, и для обнаружения проблемы следует проверить журналы расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="ae38d-147">Non-zero error columns may indicate problems and Extended Events logs should be checked to discover the problem.</span></span> <span data-ttu-id="ae38d-148">Кроме того, для поиска сведений об ошибке вызовите хранимую процедуру **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="ae38d-148">Alternatively, call **smart_admin.sp_get_backup_diagnostics** stored procedure to find the details of the error.</span></span>  
  
### <a name="using-agent-notification-for-assessing-backup-status-and-health"></a><span data-ttu-id="ae38d-149">Использование уведомлений агента для оценки состояния и работоспособности резервного копирования</span><span class="sxs-lookup"><span data-stu-id="ae38d-149">Using Agent Notification for Assessing Backup Status and Health</span></span>  
 <span data-ttu-id="ae38d-150">В состав [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] входит механизм уведомлений, который базируется на правилах управления SQL Server на основе политик.</span><span class="sxs-lookup"><span data-stu-id="ae38d-150">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] includes a notification mechanism that is based on SQL Server policy based management policies.</span></span>  
  
 <span data-ttu-id="ae38d-151">**Предварительные условия.**</span><span class="sxs-lookup"><span data-stu-id="ae38d-151">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="ae38d-152">Для работы этой функции необходим компонент Database Mail.</span><span class="sxs-lookup"><span data-stu-id="ae38d-152">Database Mail is required to use this functionality.</span></span> <span data-ttu-id="ae38d-153">Дополнительные сведения о включении компонента Database Mail для экземпляра SQL Server см. в разделе [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="ae38d-153">For more information, about how to enable DB Mail for the instance of SQL Server, see [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
-   <span data-ttu-id="ae38d-154">Чтобы использовать компонент Database Mail, необходимо задать свойства системы предупреждений агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae38d-154">SQL Server Agent Alert System properties should be set to use Database Mail.</span></span>  
  
 <span data-ttu-id="ae38d-155">**Архитектура уведомлений**</span><span class="sxs-lookup"><span data-stu-id="ae38d-155">**Notification Architecture:**</span></span>  
  
-   <span data-ttu-id="ae38d-156">**Управление на основе политик:** Установлены две политики для наблюдения за работоспособностью резервного копирования: **политика работоспособности системы интеллектуального администрирования**и **Политика исправности пользователя интеллектуального администратора**.</span><span class="sxs-lookup"><span data-stu-id="ae38d-156">**Policy Based Management:** Two policies are set to monitor backup health: **Smart Admin System Health Policy**, and the **Smart Admin User Action Health Policy**.</span></span> <span data-ttu-id="ae38d-157">Политика работоспособности системы Smart Admin оценивает критические ошибки, например отсутствие учетных данных SQL или неправильные данные, а также ошибки связи и сообщает о работоспособности системы.</span><span class="sxs-lookup"><span data-stu-id="ae38d-157">The Smart Admin System Health Policy evaluates critical errors like lack of or invalid SQL Credentials, connectivity errors and reports the health of the system.</span></span> <span data-ttu-id="ae38d-158">В таких случаях для исправления основной проблемы требуется выполнять действия вручную.</span><span class="sxs-lookup"><span data-stu-id="ae38d-158">These typically require a manual action to correct the underlying issue.</span></span> <span data-ttu-id="ae38d-159">Политика действий пользователя Smart Admin оценивает предупреждения, например о поврежденных резервных копиях и т. п.</span><span class="sxs-lookup"><span data-stu-id="ae38d-159">The Smart Admin User Action Health Policy evaluates warnings such as corrupted backups, and such.</span></span>  <span data-ttu-id="ae38d-160">Здесь может не потребоваться никаких действий, это просто предупреждение о событии.</span><span class="sxs-lookup"><span data-stu-id="ae38d-160">These may not require any action but just a warning of an event.</span></span> <span data-ttu-id="ae38d-161">Предполагается, что подобные проблемы будет автоматически решать агент [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae38d-161">It is expected that such issues will be automatically taken care of by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent.</span></span>  
  
-   <span data-ttu-id="ae38d-162">**Агент SQL Server** Задание. Уведомление выполняется с помощью задания агент SQL Server, которое содержит три шага задания.</span><span class="sxs-lookup"><span data-stu-id="ae38d-162">**SQL Server Agent** Job: The notification is performed using a SQL Server Agent job that has three job steps.</span></span> <span data-ttu-id="ae38d-163">На первом этапе задания определяется, для чего настроен агент [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]: для базы данных или для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ae38d-163">In the first job step it detects to see whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured for a database or instance.</span></span> <span data-ttu-id="ae38d-164">Если обнаруживается [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] включенный и настроенный, он выполняет второй шаг: выполняет командлет PowerShell, который оценивает состояние работоспособности, оценивая политики управления на основе политик SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae38d-164">If it finds [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled and configured, it executes the second step: executes a PowerShell cmdlet that assess the health status by evaluating the SQL Server policy based management policies.</span></span> <span data-ttu-id="ae38d-165">Если обнаруживается ошибка или предупреждение, происходит сбой, после чего запускается третий шаг: Третий шаг отправляет уведомление по электронной почте с отчетом об ошибках и предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="ae38d-165">If it finds either an error or warning, it fails which then triggers the third step: The third step sends out an e-mail notification with the error/warning report.</span></span>  <span data-ttu-id="ae38d-166">Однако это задание агента SQL Server не включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae38d-166">However this SQL Server Agent job is not enabled by default.</span></span> <span data-ttu-id="ae38d-167">Чтобы включить задание уведомления по электронной почте, используйте системную хранимую процедуру **smart_admin. sp_set_backup_parameter** .</span><span class="sxs-lookup"><span data-stu-id="ae38d-167">To enable the e-mail notification job, use the **smart_admin.sp_set_backup_parameter** system stored procedure.</span></span>  <span data-ttu-id="ae38d-168">Следующая процедура описывает эти шаги более подробно.</span><span class="sxs-lookup"><span data-stu-id="ae38d-168">The following procedure describes the steps in more detail:</span></span>  
  
##### <a name="enabling-email-notification"></a><span data-ttu-id="ae38d-169">Включение уведомления по электронной почте</span><span class="sxs-lookup"><span data-stu-id="ae38d-169">Enabling Email Notification</span></span>  
  
1.  <span data-ttu-id="ae38d-170">Если Database Mail еще не настроена, выполните действия, описанные в разделе [настройка Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="ae38d-170">If Database Mail is not already configured, use the steps described in [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
2.  <span data-ttu-id="ae38d-171">Установите базу данных в качестве почтовой системы для SQL Server системы предупреждений: щелкните правой кнопкой мыши **Агент SQL Server**, выберите **система предупреждений**, установите флажок **включить почтовый профиль** , выберите пункт **Database Mail** в качестве **почтовой системы**и выберите ранее созданный профиль электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ae38d-171">Set database as the Mail System for SQL Server Alert System: Right Click on **SQL Server Agent**, select **Alert System**, check the **Enable mail profile** box, Select **Database Mail** as the **Mail System**, and select a previously created Mail profile.</span></span>  
  
3.  <span data-ttu-id="ae38d-172">Запустите приведенный ниже запрос в окне запросов и укажите адрес электронной почты, на который должны отправляться уведомления.</span><span class="sxs-lookup"><span data-stu-id="ae38d-172">Run the following query in a query window and provide the e-mail address where you want the notification to be sent to:</span></span>  
  
    ```sql
    Use msdb  
    Go  
    EXEC smart_admin.sp_set_parameter @parameter_name = 'SSMBackup2WANotificationEmailIds', @parameter_value = '<email address>'
    ```  
  
     <span data-ttu-id="ae38d-173">Будет создано задание агента SQL Server, используемое для сбора сведений о состоянии работоспособности и отправки уведомлений при наличии ошибок или проблем резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ae38d-173">This creates a SQL Server Agent job that is used to gather health status and send notifications when there is an error or an issue with backups.</span></span>  
  
 <span data-ttu-id="ae38d-174">Далее приведен образец скрипта для включения компонента DB Mail и отправки уведомления по электронной почте с помощью задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae38d-174">Following is a sample script  to enable DB Mail and set up the e-mail notification through SQL Server Agent Job</span></span>  
  
```sql
-- Prereq: Make sure that SQL Server service runs in a service account that has  
--  access to SMTP Server   
-- set SQL Server service account as domain account   
  
EXEC sp_configure 'show advanced', 1  
RECONFIGURE  
GO  
  
-- Enable DBMail  
EXEC sp_configure 'Database Mail XPs',1  
GO  
RECONFIGURE  
GO  
  
-- Configure DBMail  
DECLARE @emailid NVARCHAR(255)  
-- Note: change this email to your own email id  
SET @emailid = N'emailalias@mycompany.com'  
  
DECLARE @smtpserver NVARCHAR(255)  
SET @smtpserver = N'smtphost.domainname.com'  
  
DECLARE @mailprofile NVARCHAR(255)  
SET @mailprofile = N'my_profile'  
  
EXEC msdb.dbo.sysmail_add_account_sp @account_name=N'myaccount',  
                @email_address = @emailid,  
                @replyto_address = @emailid,  
                @mailserver_name = @smtpserver,  
                @use_default_credentials = 1  
  
EXEC msdb.dbo.sysmail_add_profile_sp @profile_name=@mailprofile  
EXEC msdb.dbo.sysmail_add_profileaccount_sp @profile_name=@mailprofile, @account_name=N'myaccount', @sequence_number=1  
  
-- Set SQL Agent to use DBMail profile  
EXEC msdb.dbo.sp_set_sqlagent_properties @databasemail_profile = @mailprofile  
  
-- Configure Notifications   
EXEC msdb.smart_admin.sp_set_parameter  
@parameter_name = 'SSMBackup2WANotificationEmailIds',  
@parameter_value = @emailid  
  
-- To test is you are receiving notifications  
-- delete few backup files from your storage container, Wait for 15 minutes & see if you get any email notification
```  
  
### <a name="using-powershell-to-setup-custom-health-monitoring"></a><span data-ttu-id="ae38d-175">Настройка пользовательского наблюдения за работоспособностью с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae38d-175">Using PowerShell to Setup Custom Health Monitoring</span></span>  
 <span data-ttu-id="ae38d-176">Командлет **Test-SqlSmartAdmin** можно использовать для создания настраиваемого мониторинга работоспособности.</span><span class="sxs-lookup"><span data-stu-id="ae38d-176">The **Test-SqlSmartAdmin** cmdlet can be used to create custom health monitoring.</span></span> <span data-ttu-id="ae38d-177">Например, параметр уведомлений, описанный в предыдущем разделе, можно настроить на уровне экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ae38d-177">For example, the notification option described in the previous section can be configured at the instance level.</span></span>  <span data-ttu-id="ae38d-178">Если автоматическое резервное копирование с помощью [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] настроено в нескольких экземплярах SQL Server, командлет PowerShell можно использовать для создания скриптов для сбора сведений о состоянии и работоспособности сеансов резервного копирования для всех экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ae38d-178">If you have several instances of SQL Server configured to use [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], the PowerShell cmdlet can be used to create scripts in gather the status and health of backups for all the instances.</span></span>  
  
 <span data-ttu-id="ae38d-179">Командлет **Test-SqlSmartAdmin** оценивает ошибки и предупреждения, возвращаемые политиками управления на основе политики SQL Server и выводит сведенное состояние.</span><span class="sxs-lookup"><span data-stu-id="ae38d-179">The **Test-SqlSmartAdmin** cmdlet assesses the errors and warnings returned by the SQL Server Policy Based Management policies and reports out a rolled up status.</span></span>  <span data-ttu-id="ae38d-180">По умолчанию этот командлет использует системные политики.</span><span class="sxs-lookup"><span data-stu-id="ae38d-180">By default this cmdlet uses the system policies.</span></span> <span data-ttu-id="ae38d-181">Чтобы включить пользовательскую политику, воспользуйтесь параметром `-AllowUserPolicies`.</span><span class="sxs-lookup"><span data-stu-id="ae38d-181">To include any custom policy use the `-AllowUserPolicies` parameter.</span></span>  
  
 <span data-ttu-id="ae38d-182">Далее приведен образец скрипта PowerShell, который возвращает отчет об ошибках и предупреждениях на основе системных политик и любых политик, созданных пользователем.</span><span class="sxs-lookup"><span data-stu-id="ae38d-182">Following is a sample PowerShell script that returns a report of errors and warnings based on the system policies and any user policies created:</span></span>  
  
```powershell
$policyResults = Get-SqlSmartAdmin | Test-SqlSmartAdmin -AllowUserPolicies  
$policyResults.PolicyEvaluationDetails | Select Name, Category, Expression, Result, Exception | fl
```  
  
 <span data-ttu-id="ae38d-183">Следующий скрипт возвращает подробный отчет об ошибках и предупреждениях для экземпляра по умолчанию ( `\SQL\COMPUTER\DEFAULT` ):</span><span class="sxs-lookup"><span data-stu-id="ae38d-183">The following script returns a detailed report of the errors and warnings for the default instance (`\SQL\COMPUTER\DEFAULT`):</span></span>  
  
```powershell
(Get-SqlSmartAdmin ).EnumHealthStatus()  
```  
  
### <a name="objects-in-msdb-database"></a><span data-ttu-id="ae38d-184">Объекты в базе данных MSDB</span><span class="sxs-lookup"><span data-stu-id="ae38d-184">Objects in MSDB database</span></span>  
 <span data-ttu-id="ae38d-185">Это объекты, установленные для реализации функций MSDB.</span><span class="sxs-lookup"><span data-stu-id="ae38d-185">There are objects that are installed to implement the functionality.</span></span> <span data-ttu-id="ae38d-186">Они зарезервированы для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="ae38d-186">These objects are reserved for internal use.</span></span> <span data-ttu-id="ae38d-187">Однако существует одна системная таблица, которая может быть полезна при наблюдении за состоянием резервного копирования: smart_backup_files.</span><span class="sxs-lookup"><span data-stu-id="ae38d-187">However, there is one system table that can be useful in monitoring the backup status: smart_backup_files.</span></span> <span data-ttu-id="ae38d-188">Большая часть информации, хранящейся в этой таблице, относится к мониторингу, например к типу резервной копии, имени базы данных, первому и последнему номеру LSN, даты истечения срока действия резервной копии предоставляются через системную функцию [smart_admin. fn_available_backups &#40;&#41;Transact-SQL ](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae38d-188">Most of the Information   stored in this table relevant to monitoring like the type of backup, database name, first and last lsn, backup expiry dates are exposed through the system function [smart_admin.fn_available_backups &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span></span> <span data-ttu-id="ae38d-189">Однако столбец состояния в таблице smart_backup_files, указывающий состояние файла резервной копии, через данную функцию недоступен.</span><span class="sxs-lookup"><span data-stu-id="ae38d-189">However the status column in the smart_backup_files table which indicates the status of the backup file is not available using the function.</span></span> <span data-ttu-id="ae38d-190">Далее приведен пример запроса, который можно использовать для получения некоторых сведений из системной таблицы, включая состояние.</span><span class="sxs-lookup"><span data-stu-id="ae38d-190">Following is a sample query you can use to retrieve the some information including the status from the system table:</span></span>  
  
```sql
USE msdb  
GO  
SELECT  
 database_name AS [Database Name] ,backup_path AS [Backup Destination and File]  
,[Backup Type] =  
CASE backup_type  
WHEN 1 THEN 'FULL'  
WHEN 2 THEN 'LOG'  
END  
,[Backup Status] =  
CASE [status]  
WHEN 'A' THEN 'Available'  
WHEN 'B' THEN 'Copy In Progress'  
WHEN 'C' THEN 'Corrupted'  
WHEN 'D' THEN 'Deleted'  
WHEN 'F' THEN 'Copy Failed'  
WHEN 'U' THEN 'Unknown'  
END  
,first_lsn AS [First LSN]  
,last_lsn AS [Last LSN]  
,backup_start_date AS [Backup Start Time]  
,backup_finish_date AS [Backup Completion Time]  
,expiration_date AS [Backup Expiry Date/Time]  
FROM  
smart_backup_files;
```  
  
 <span data-ttu-id="ae38d-191">Далее дается подробное описание различных значений кода состояния.</span><span class="sxs-lookup"><span data-stu-id="ae38d-191">Following is a detailed explanation of the different status returned:</span></span>  
  
-   <span data-ttu-id="ae38d-192">**Доступно:** Это стандартный файл резервной копии.</span><span class="sxs-lookup"><span data-stu-id="ae38d-192">**Available - A:** This is a normal backup file.</span></span> <span data-ttu-id="ae38d-193">Резервное копирование завершено, а также проверено, что она доступна в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="ae38d-193">The backup has been completed, and also verified that it is available in the Azure storage.</span></span>  
  
-   <span data-ttu-id="ae38d-194">**Копирование выполняется — б:** Это состояние предназначено для баз данных групп доступности.</span><span class="sxs-lookup"><span data-stu-id="ae38d-194">**Copy in Progress -B:** This status is specifically for Availability Group databases.</span></span> <span data-ttu-id="ae38d-195">Если [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] обнаружит разрыв в цепочке резервного копирования журнала, сначала будет сделана попытка определить операцию копирования, вызвавшую этот разрыв.</span><span class="sxs-lookup"><span data-stu-id="ae38d-195">If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] detects a break in the backup log chain, it will first attempt identify the  backup that might have caused the break in backup chain.</span></span> <span data-ttu-id="ae38d-196">При поиске файла резервной копии он пытается скопировать файл в службу хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="ae38d-196">On finding the backup file it attempts to copy the file to Azure storage.</span></span> <span data-ttu-id="ae38d-197">Данное состояние отображается при выполнении операции копирования.</span><span class="sxs-lookup"><span data-stu-id="ae38d-197">When the copying process is in progress it will display this status.</span></span>  
  
-   <span data-ttu-id="ae38d-198">**Сбой копирования — F:** Как и в процессе копирования, это конкретные базы данных групп доступности t.</span><span class="sxs-lookup"><span data-stu-id="ae38d-198">**Copy Failed - F:** Similar to Copy In Progress, this is specific t Availability Group databases.</span></span> <span data-ttu-id="ae38d-199">Если процесс копирования завершается ошибкой, состояние отмечается как F.</span><span class="sxs-lookup"><span data-stu-id="ae38d-199">If the copy process fails, the status is marked as F.</span></span>  
  
-   <span data-ttu-id="ae38d-200">**Повреждено — C:** Если [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] не удается проверить файл резервной копии в хранилище, выполнив команду RESTORE HEADER_ONLY, даже после нескольких попыток, этот файл помечается как поврежденный.</span><span class="sxs-lookup"><span data-stu-id="ae38d-200">**Corrupted - C:** If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is unable to verify the backup file in the storage by performing a RESTORE HEADER_ONLY command even after multiple attempts, it marks this file as corrupted.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="ae38d-201">запланирует резервное копирование, чтобы поврежденный файл не привел к разрыву в цепочке резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ae38d-201">will schedule a backup to ensure that the corrupted file does not result in a break of the backup chain.</span></span>  
  
-   <span data-ttu-id="ae38d-202">**Удалено-D:** Соответствующий файл не найден в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="ae38d-202">**Deleted - D:** The corresponding file cannot be found in the Azure storage.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="ae38d-203">запланирует резервное копирование, если удаленный файл приведет к разрыву в цепочке резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ae38d-203">will schedule a backup if the deleted file results in a break in the backup chain.</span></span>  
  
-   <span data-ttu-id="ae38d-204">**Неизвестный-U:** Это состояние указывает, что [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] еще не удалось проверить существование файла и его свойства в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="ae38d-204">**Unknown - U:** This status indicated that [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has not yet been able to verify file existence and its properties in the Azure storage.</span></span> <span data-ttu-id="ae38d-205">При следующем запуске процесса, что обычно происходит через каждые 15 минут, это состояние будет обновлено.</span><span class="sxs-lookup"><span data-stu-id="ae38d-205">The next time the process runs, which is approximately every 15 minutes, this status will be updated.</span></span>  
