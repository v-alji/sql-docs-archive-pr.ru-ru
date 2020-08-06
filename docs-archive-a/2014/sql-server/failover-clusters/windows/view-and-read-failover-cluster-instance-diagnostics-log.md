---
title: Просмотр и чтение журнала диагностики для экземпляра отказоустойчивого кластера | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 68074bd5-be9d-4487-a320-5b51ef8e2b2d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 774dc4ec4a02c72420d004909cb7e6ee1b31f3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659271"
---
# <a name="view-and-read-failover-cluster-instance-diagnostics-log"></a><span data-ttu-id="6f159-102">Просмотр и чтение журнала диагностики экземпляра отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="6f159-102">View and Read Failover Cluster Instance Diagnostics Log</span></span>
  <span data-ttu-id="6f159-103">Все критические ошибки и события предупреждений для библиотеки ресурсов SQL Server записываются в журнал событий Windows.</span><span class="sxs-lookup"><span data-stu-id="6f159-103">All critical errors and warning events for the SQL Server Resource DLL are written to the Windows event log.</span></span> <span data-ttu-id="6f159-104">Диагностические сведения, связанные с SQL Server и записываемые в журнал, перехватываются хранимой процедурой [sp_server_diagnostics (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) и записываются в файлы журнала диагностики отказоустойчивого кластера SQL Server (также называемые журналами *SQLDIAG*).</span><span class="sxs-lookup"><span data-stu-id="6f159-104">A running log of the diagnostic information specific to SQL Server is captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) system stored procedure and is written to the SQL Server failover cluster diagnostics (also known as the *SQLDIAG* logs) log files.</span></span>  
  
-   <span data-ttu-id="6f159-105">**Перед началом работы**  [рекомендации](#Recommendations), [безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="6f159-105">**Before you begin:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="6f159-106">**Просмотр журнала диагностики с помощью следующих средств**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="6f159-106">**To View the Diagnostic Log, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="6f159-107">**Настройка параметров журнала диагностики с помощью** [Transact-SQL](#TsqlConfigure)</span><span class="sxs-lookup"><span data-stu-id="6f159-107">**To Configure Diagnostic Log settings, using:** [Transact-SQL](#TsqlConfigure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6f159-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6f159-108">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6f159-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="6f159-109">Recommendations</span></span>  
 <span data-ttu-id="6f159-110">По умолчанию SQLDIAG хранится в локальной папке журнала SQL Server каталога экземпляра, например C\Program Files\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\LOG "узла-владельца экземпляра отказоустойчивого кластера AlwaysOn (FCI).</span><span class="sxs-lookup"><span data-stu-id="6f159-110">By default, the SQLDIAG are stored under a local LOG folder of the SQL Server instance directory, for example, 'C\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\LOG' of the owning node of the AlwaysOn Failover Cluster Instance (FCI).</span></span> <span data-ttu-id="6f159-111">Размер каждого файла журнала SQLDIAG ограничен 100 МБ.</span><span class="sxs-lookup"><span data-stu-id="6f159-111">The size of each SQLDIAG log file is fixed at 100 MB.</span></span> <span data-ttu-id="6f159-112">На компьютере сохраняются десять таких файлов журнала, после чего они освобождаются для новых журналов.</span><span class="sxs-lookup"><span data-stu-id="6f159-112">Ten such log files are stored on the computer before they are recycled for new logs.</span></span>  
  
 <span data-ttu-id="6f159-113">В журналах используется формат файлов расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="6f159-113">The logs use the extended events file format.</span></span> <span data-ttu-id="6f159-114">Для чтения файлов, созданных расширенными событиями, можно использовать системную функцию **sys.fn_xe_file_target_read_file** .</span><span class="sxs-lookup"><span data-stu-id="6f159-114">The **sys.fn_xe_file_target_read_file** system function can be used to read the files that are created by Extended Events.</span></span> <span data-ttu-id="6f159-115">Возвращается одно событие в каждой строке в формате XML.</span><span class="sxs-lookup"><span data-stu-id="6f159-115">One event, in XML format, is returned per row.</span></span> <span data-ttu-id="6f159-116">Выполните запрос к системному представлению для синтаксического анализа XML-данных в виде результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="6f159-116">Query the system view to parse the XML data as a result-set.</span></span> <span data-ttu-id="6f159-117">Дополнительные сведения см. в разделе [sys.fn_xe_file_target_read_file (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6f159-117">For more information, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6f159-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="6f159-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6f159-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="6f159-119">Permissions</span></span>  
 <span data-ttu-id="6f159-120">Для запуска **fn_xe_file_target_read_file**требуется разрешение VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="6f159-120">VIEW SERVER STATE permission is needed to run **fn_xe_file_target_read_file**.</span></span>  
  
 <span data-ttu-id="6f159-121">Откройте среду SQL Server Management Studio в качестве администратора</span><span class="sxs-lookup"><span data-stu-id="6f159-121">Open SQL Server Management Studio as Administrator</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6f159-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6f159-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6f159-123">**Просмотр файлов журнала диагностики:**</span><span class="sxs-lookup"><span data-stu-id="6f159-123">**To view the Diagnostic log files:**</span></span>  
  
1.  <span data-ttu-id="6f159-124">В меню **Файл** выберите **Открыть**, **Файл**и выберите файл журнала диагностики для просмотра.</span><span class="sxs-lookup"><span data-stu-id="6f159-124">From the **File** menu, select **Open**, **File**, and choose the diagnostic log file you want to view.</span></span>  
  
2.  <span data-ttu-id="6f159-125">События отображаются в виде строк в правой панели, причем по умолчанию показаны только два столбца, **name**и **timestamp** .</span><span class="sxs-lookup"><span data-stu-id="6f159-125">The events are displayed as rows in the right pane, and by default **name**, and **timestamp** are the only two columns displayed.</span></span>  
  
     <span data-ttu-id="6f159-126">Это также приводит к активации меню **ExtendedEvents** .</span><span class="sxs-lookup"><span data-stu-id="6f159-126">This also activates the **ExtendedEvents** menu.</span></span>  
  
3.  <span data-ttu-id="6f159-127">Для отображения большего числа столбцов перейдите в меню **ExtendedEvents** и укажите **Выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="6f159-127">To see more columns, go the **ExtendedEvents** menu, and select **Choose Columns**.</span></span>  
  
     <span data-ttu-id="6f159-128">Откроется диалоговое окно с доступными столбцами, позволяя выбрать столбцы для отображения.</span><span class="sxs-lookup"><span data-stu-id="6f159-128">A dialog box opens with the available columns allowing you to select the columns for display.</span></span>  
  
4.  <span data-ttu-id="6f159-129">Можно фильтровать и сортировать данные событий, используя меню **ExtendedEvents** и выбирая параметр **Фильтр** .</span><span class="sxs-lookup"><span data-stu-id="6f159-129">You can filter, and sort the event data using the **ExtendedEvents** menu and selecting the **Filter** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6f159-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6f159-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="6f159-131">**Просмотр файлов журнала диагностики:**</span><span class="sxs-lookup"><span data-stu-id="6f159-131">**To view the Diagnostic log files:**</span></span>  
  
 <span data-ttu-id="6f159-132">Для просмотра всех записей в файле журнала SQLDIAG используйте следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="6f159-132">To view all the log items in the SQLDIAG log file, use the following query:</span></span>  
  
```  
SELECT  
xml_data.value('(event/@name)[1]','varchar(max)') AS 'Name'  
,xml_data.value('(event/@package)[1]','varchar(max)') AS 'Package'  
,xml_data.value('(event/@timestamp)[1]','datetime') AS 'Time'  
,xml_data.value('(event/data[@name=''state'']/value)[1]','int') AS 'State'  
,xml_data.value('(event/data[@name=''state_desc'']/text)[1]','varchar(max)') AS 'State Description'  
,xml_data.value('(event/data[@name=''failure_condition_level'']/value)[1]','int') AS 'Failure Conditions'  
,xml_data.value('(event/data[@name=''node_name'']/value)[1]','varchar(max)') AS 'Node_Name'  
,xml_data.value('(event/data[@name=''instancename'']/value)[1]','varchar(max)') AS 'Instance Name'  
,xml_data.value('(event/data[@name=''creation time'']/value)[1]','datetime') AS 'Creation Time'  
,xml_data.value('(event/data[@name=''component'']/value)[1]','varchar(max)') AS 'Component'  
,xml_data.value('(event/data[@name=''data'']/value)[1]','varchar(max)') AS 'Data'  
,xml_data.value('(event/data[@name=''info'']/value)[1]','varchar(max)') AS 'Info'  
FROM  
 ( SELECT object_name AS 'event'  
  ,CONVERT(xml,event_data) AS 'xml_data'  
  FROM sys.fn_xe_file_target_read_file('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log\SQLNODE1_MSSQLSERVER_SQLDIAG_0_129936003752530000.xel',NULL,NULL,NULL)   
)   
AS XEventData  
ORDER BY Time;  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="6f159-133">Можно отфильтровать результаты для определенных компонентов или состояний с помощью предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="6f159-133">You can filter the results for specific components or state using the WHERE clause.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlConfigure"></a> <span data-ttu-id="6f159-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6f159-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="6f159-135">**Настройка свойств журнала диагностики**</span><span class="sxs-lookup"><span data-stu-id="6f159-135">**To configure the Diagnostic Log Properties**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f159-136">Пример этой процедуры см. в подразделе [Примеры (Transact-SQL)](#TsqlExample)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6f159-136">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
 <span data-ttu-id="6f159-137">С помощью инструкции языка описания данных (DDL) `ALTER SERVER CONFIGURATION` можно запускать или прекращать регистрацию диагностических данных, полученных в [sp_server_diagnostics &#40;процедуре&#41;TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) , а также задавать параметры конфигурации журнала SQLdiag, такие как число переключений файла журнала, размер файла журнала и расположение файла.</span><span class="sxs-lookup"><span data-stu-id="6f159-137">Using the Data Definition Language (DDL) statement, `ALTER SERVER CONFIGURATION`, you can start or stop logging diagnostic data captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) procedure, and set SQLDIAG log configuration parameters such as the log file rollover count, log file size, and file location.</span></span> <span data-ttu-id="6f159-138">Дополнительные сведения о синтаксисе см. в разделе [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span><span class="sxs-lookup"><span data-stu-id="6f159-138">For syntax details, see [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="ConfigTsqlExample"></a> <span data-ttu-id="6f159-139">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6f159-139">Examples (Transact-SQL)</span></span>  
  
####  <a name="setting-diagnostic-log-options"></a><a name="TsqlExample"></a> <span data-ttu-id="6f159-140">Setting diagnostic log options</span><span class="sxs-lookup"><span data-stu-id="6f159-140">Setting diagnostic log options</span></span>  
 <span data-ttu-id="6f159-141">В примерах этого раздела показана установка значений параметра журнала диагностики.</span><span class="sxs-lookup"><span data-stu-id="6f159-141">The examples in this section show how to set the values for the diagnostic log option.</span></span>  
  
##### <a name="a-starting-diagnostic-logging"></a><span data-ttu-id="6f159-142">A.</span><span class="sxs-lookup"><span data-stu-id="6f159-142">A.</span></span> <span data-ttu-id="6f159-143">Запуск регистрации диагностических данных в журнале</span><span class="sxs-lookup"><span data-stu-id="6f159-143">Starting diagnostic logging</span></span>  
 <span data-ttu-id="6f159-144">В следующем примере запускается запись в журнал диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="6f159-144">The following example starts the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG ON;  
```  
  
##### <a name="b-stopping-diagnostic-logging"></a><span data-ttu-id="6f159-145">Б.</span><span class="sxs-lookup"><span data-stu-id="6f159-145">B.</span></span> <span data-ttu-id="6f159-146">Останов регистрации диагностических данных в журнале</span><span class="sxs-lookup"><span data-stu-id="6f159-146">Stopping diagnostic logging</span></span>  
 <span data-ttu-id="6f159-147">В следующем примере запись в журнал диагностических данных прекращается.</span><span class="sxs-lookup"><span data-stu-id="6f159-147">The following example stops the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG OFF;  
```  
  
##### <a name="c-specifying-the-location-of-the-diagnostic-logs"></a><span data-ttu-id="6f159-148">В.</span><span class="sxs-lookup"><span data-stu-id="6f159-148">C.</span></span> <span data-ttu-id="6f159-149">Задание расположения журналов диагностических данных</span><span class="sxs-lookup"><span data-stu-id="6f159-149">Specifying the location of the diagnostic logs</span></span>  
 <span data-ttu-id="6f159-150">В следующем примере для журналов диагностических данных задается расположение по указанному пути к файлам.</span><span class="sxs-lookup"><span data-stu-id="6f159-150">The following example sets the location of the diagnostic logs to the specified file path.</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET DIAGNOSTICS LOG PATH = 'C:\logs';  
```  
  
##### <a name="d-specifying-the-maximum-size-of-each-diagnostic-log"></a><span data-ttu-id="6f159-151">Г.</span><span class="sxs-lookup"><span data-stu-id="6f159-151">D.</span></span> <span data-ttu-id="6f159-152">Задание максимального размера каждого из журналов диагностики</span><span class="sxs-lookup"><span data-stu-id="6f159-152">Specifying the maximum size of each diagnostic log</span></span>  
 <span data-ttu-id="6f159-153">В следующем примере задан максимальный размер каждого из журналов диагностики, равный 10 мегабайтам.</span><span class="sxs-lookup"><span data-stu-id="6f159-153">The following example set the maximum size of each diagnostic log to 10 megabytes.</span></span>  
  
```  
ALTER SERVER CONFIGURATION   
SET DIAGNOSTICS LOG MAX_SIZE = 10 MB;  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f159-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f159-154">See Also</span></span>  
 [<span data-ttu-id="6f159-155">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="6f159-155">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
  
  
