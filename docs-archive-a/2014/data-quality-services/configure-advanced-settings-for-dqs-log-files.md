---
title: Настройка дополнительных параметров для файлов журнала DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- log files,advanced settings
- dqs log files,advanced settings
ms.assetid: 1d565748-9759-425c-ae38-4d2032a86868
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ad41b0cac95f9bfe5565ccbac16b0fda3e28ddf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728737"
---
# <a name="configure-advanced-settings-for-dqs-log-files"></a><span data-ttu-id="5d723-102">Configure Advanced Settings for DQS Log Files</span><span class="sxs-lookup"><span data-stu-id="5d723-102">Configure Advanced Settings for DQS Log Files</span></span>
  <span data-ttu-id="5d723-103">В этом разделе описано, как настроить дополнительные параметры файлов журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] и [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , такие как скользящий предельный размер файла для файлов журнала, шаблон метки времени для событий и т. д.</span><span class="sxs-lookup"><span data-stu-id="5d723-103">This topic describes how to configure advanced settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log files, such as set the rolling file size limit of the log files, set the time stamp pattern of the events, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d723-104">Эти действия нельзя выполнить с помощью приложения [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], они предназначены только для продвинутых пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d723-104">These activities cannot be performed using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and is intended for advanced users only.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d723-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5d723-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d723-106">безопасность</span><span class="sxs-lookup"><span data-stu-id="5d723-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d723-107">Permissions</span><span class="sxs-lookup"><span data-stu-id="5d723-107">Permissions</span></span>  
  
-   <span data-ttu-id="5d723-108">Учетная запись Windows должна быть членом предопределенной роли сервера sysadmin на этом экземпляре SQL Server для изменения параметров конфигурации в таблице A_CONFIGURATION базы данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="5d723-108">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to modify configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
-   <span data-ttu-id="5d723-109">Чтобы настраивать параметры журналов [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , необходимо быть членом группы администраторов на компьютере, где изменяется файл DQLog.Client.xml.</span><span class="sxs-lookup"><span data-stu-id="5d723-109">You must be logged on as a member of the Administrators group on the computer where you are modifying the DQLog.Client.xml file to configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] logging settings.</span></span>  
  
##  <a name="configure-data-quality-server-log-settings"></a><a name="DQSServer"></a><span data-ttu-id="5d723-110">Настройка параметров журнала сервера Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="5d723-110">Configure Data Quality Server Log Settings</span></span>  
 <span data-ttu-id="5d723-111">Параметры журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] представлены в формате XML в столбце **VALUE** строки **ServerLogging** в таблице A_CONFIGURATION базы данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="5d723-111">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings are present in an XML format in the **VALUE** column of the **ServerLogging** row in the A_CONFIGURATION table in the DQS_MAIN database.</span></span> <span data-ttu-id="5d723-112">Вы можете выполнить следующий SQL-запрос для просмотра сведений о конфигурации:</span><span class="sxs-lookup"><span data-stu-id="5d723-112">You can run the following SQL query to view the configuration information:</span></span>  
  
```sql  
select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'; 
```  
  
 <span data-ttu-id="5d723-113">Необходимо обновить соответствующие сведения в столбце **VALUE** строки **ServerLogging** , чтобы изменить параметры конфигурации для журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d723-113">You must update the appropriate information in the **VALUE** column of the **ServerLogging** row to change the configuration settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging.</span></span> <span data-ttu-id="5d723-114">В этом примере обновляются параметры журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , устанавливается скользящий предел файла данных равным 25 000 KБ (по умолчанию он равен 20 000 KБ).</span><span class="sxs-lookup"><span data-stu-id="5d723-114">In this example, we will update the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings to set the rolling file size limit to 25000 KB (the default is 20000 KB).</span></span>  
  
1.  <span data-ttu-id="5d723-115">Запустите среду Microsoft SQL Server Management Studio и подключитесь к соответствующему экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d723-115">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="5d723-116">В обозревателе объектов щелкните сервер правой кнопкой мыши и выберите команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5d723-116">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5d723-117">В окно редактора запросов скопируйте следующие инструкции SQL:</span><span class="sxs-lookup"><span data-stu-id="5d723-117">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    -- Begin the transaction.  
    BEGIN TRAN  
    GO  
    -- set the XML value field for the row with name=ServerLogging  
    update DQS_MAIN.dbo.A_CONFIGURATION   
    set VALUE='<configuration>  
      <configSections>  
        <section name="loggingConfiguration" type="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.LoggingSettings, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" />  
      </configSections>  
      <loggingConfiguration name="Logging Application Block" tracingEnabled="true" defaultCategory="" logWarningsWhenNoCategoriesMatch="true">  
        <listeners>  
          <add fileName="###REPLACE_THIS_WITH_SQL_SERVER_INSTANCE_LOG_FOLDER_NAME###DQServerLog.###REPLACE_THIS_WITH_SQL_CATALOG_NAME###.log" footer="" formatter="Custom Text Formatter" header="" rollFileExistsBehavior="Increment" rollInterval="None" rollSizeKB="25000" timeStampPattern="yyyy-MM-dd" listenerDataType="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.RollingFlatFileTraceListenerData, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" traceOutputOptions="None" filter="All" type="Microsoft.Practices.EnterpriseLibrary.Logging.TraceListeners.RollingFlatFileTraceListener, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Rolling Flat File Trace Listener" />  
        </listeners>  
        <formatters>  
          <add template="{timestamp(local)}|[{threadName}]|{dictionary({value}|)}{message}" type="Microsoft.Practices.EnterpriseLibrary.Logging.Formatters.TextFormatter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Custom Text Formatter" />  
        </formatters>  
        <logFilters>  
          <add enabled="true" type="Microsoft.Practices.EnterpriseLibrary.Logging.Filters.LogEnabledFilter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="LogEnabled Filter" />  
        </logFilters>  
        <categorySources />  
        <specialSources>  
          <allEvents switchValue="All" name="All Events" />  
          <notProcessed switchValue="All" name="Unprocessed Category" />  
          <errors switchValue="All" name="Logging Errors & Warnings">  
            <listeners>  
              <add name="Rolling Flat File Trace Listener" />  
            </listeners>  
          </errors>  
        </specialSources>  
      </loggingConfiguration>  
    </configuration>'  
    WHERE NAME='ServerLogging'  
    GO  
    -- check the result  
    select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'  
  
    -- Commit the transaction.  
    COMMIT TRAN  
  
    ```  
  
4.  <span data-ttu-id="5d723-118">Нажмите клавишу F5, чтобы выполнить инструкции.</span><span class="sxs-lookup"><span data-stu-id="5d723-118">Press F5 to execute the statements.</span></span> <span data-ttu-id="5d723-119">Откройте область **Результаты** , чтобы удостовериться в успешном выполнении инструкций.</span><span class="sxs-lookup"><span data-stu-id="5d723-119">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
5.  <span data-ttu-id="5d723-120">Чтобы применить изменения, внесенные в конфигурацию журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , необходимо выполнить следующие инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5d723-120">To apply changes done to the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging configuration, you must run the following Transact-SQL statements.</span></span> <span data-ttu-id="5d723-121">Откройте новое окно редактора запросов и вставьте следующие инструкции Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="5d723-121">Open a new Query Editor window, and paste the following Transact-SQL statements:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    DECLARE @return_value int  
    EXEC @return_value = [internal_core].[RefreshLogSettings]  
    SELECT 'Return Value' = @return_value  
    GO  
    ```  
  
6.  <span data-ttu-id="5d723-122">Нажмите клавишу F5, чтобы выполнить инструкции.</span><span class="sxs-lookup"><span data-stu-id="5d723-122">Press F5 to execute the statements.</span></span> <span data-ttu-id="5d723-123">Откройте область **Результаты** , чтобы удостовериться в успешном выполнении инструкций.</span><span class="sxs-lookup"><span data-stu-id="5d723-123">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d723-124">Конфигурация параметров журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] создается автоматически и хранится в файле DQS_MAIN.Log, который обычно находится в папке «C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log», если был установлен экземпляр SQL Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5d723-124">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging settings configuration is dynamically generated and stored in the DQS_MAIN.Log file, which is typically available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log if you installed the default instance of SQL Server.</span></span> <span data-ttu-id="5d723-125">Однако изменения, внесенные непосредственно в этот файл, не сохраняются, они перезаписываются параметрами конфигурации из таблицы A_CONFIGURATION базы данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="5d723-125">However, changes done directly in this file do not hold, and are overwritten by the configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
##  <a name="configure-data-quality-client-log-settings"></a><a name="DQSClient"></a><span data-ttu-id="5d723-126">Настройка параметров журнала Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="5d723-126">Configure Data Quality Client Log Settings</span></span>  
 <span data-ttu-id="5d723-127">[!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]Файл конфигурации параметров журнала, DQLog.Client.xml, обычно доступен по адресу C:\Program FILES\MICROSOFT SQL Server\120\Tools\Binn\DQ\config. Содержимое XML-файла похоже на XML-файл, который был изменен ранее для [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] параметров конфигурации журнала.</span><span class="sxs-lookup"><span data-stu-id="5d723-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log setting configuration file, DQLog.Client.xml, is typically available at C:\Program Files\Microsoft SQL Server\120\Tools\Binn\DQ\config. The contents of the XML file is similar to the XML file that you modified earlier for the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="5d723-128">Настройка параметров журнала [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="5d723-128">To configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log settings:</span></span>  
  
1.  <span data-ttu-id="5d723-129">Откройте любой редактор XML-файлов или Блокнот с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="5d723-129">Run any XML editing tool or notepad as an administrator.</span></span>  
  
2.  <span data-ttu-id="5d723-130">Откройте файл DQLog.Client.xml в этом редакторе или в Блокноте.</span><span class="sxs-lookup"><span data-stu-id="5d723-130">Open the DQLog.Client.xml file in the tool or notepad.</span></span>  
  
3.  <span data-ttu-id="5d723-131">Внесите необходимые изменения и сохраните этот файл, чтобы изменения журнала были применены.</span><span class="sxs-lookup"><span data-stu-id="5d723-131">Make the required changes, and save the file to apply the new logging changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d723-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d723-132">See Also</span></span>  
 [<span data-ttu-id="5d723-133">Настройка степеней серьезности для файлов журнала DQS</span><span class="sxs-lookup"><span data-stu-id="5d723-133">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)  
  
  
