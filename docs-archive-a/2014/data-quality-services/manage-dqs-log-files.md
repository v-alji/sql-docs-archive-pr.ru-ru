---
title: Управление файлами журнала DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- logging
- log files
- dqs log files
ms.assetid: 4fccfd24-aede-4882-be69-ec1e82682e16
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ca85772b8cc8aca41b75ad05d028bc444f280378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667901"
---
# <a name="manage-dqs-log-files"></a><span data-ttu-id="03770-102">Управление файлами журнала DQS</span><span class="sxs-lookup"><span data-stu-id="03770-102">Manage DQS Log Files</span></span>
  <span data-ttu-id="03770-103">Файлы журнала[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) полезны при диагностике и устранении проблем в [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]и [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03770-103">[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) log files help you in diagnosing and troubleshooting issue with [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="03770-104">Отдельные файлы журнала создаются для [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]и [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03770-104">Separate log files are generated for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
 <span data-ttu-id="03770-105">С помощью [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] вы можете настроить параметр серьезности для записи в журнал для функций и модулей [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03770-105">You can use [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] to configure the log severity setting for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] features and modules.</span></span> <span data-ttu-id="03770-106">Кроме того, вы можете настроить некоторые другие (дополнительные) параметры для файлов журналов DQS, вручную изменив параметры конфигурации для журнала DQS в базе данных DQS_MAIN и XML-файле на компьютере [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03770-106">Additionally, you can also configure some other (advanced) settings for the DQS log files by manually changing the DQS log configuration settings in the DQS_MAIN database and an XML file on the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] computer.</span></span>  
  
##  <a name="data-quality-server-log-file"></a><a name="DQSServer"></a><span data-ttu-id="03770-107">Файл журнала сервера данных Data Quality</span><span class="sxs-lookup"><span data-stu-id="03770-107">Data Quality Server Log File</span></span>  
 <span data-ttu-id="03770-108">Файл журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , DQServerLog.DQS_MAIN.log, содержит журналы видов деятельности, которые запускаются на сервере [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03770-108">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, DQServerLog.DQS_MAIN.log, includes logs of activities that are run on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="03770-109">Если был установлен экземпляр SQL Server по умолчанию, файл DQServerLog.DQS_MAIN.log находится в папке «C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log».</span><span class="sxs-lookup"><span data-stu-id="03770-109">If you installed the default instance of SQL Server, the DQServerLog.DQS_MAIN.log file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span></span> <span data-ttu-id="03770-110">Файл журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] содержит следующие элементы данных, разделенные знаком вертикальной черты (|):</span><span class="sxs-lookup"><span data-stu-id="03770-110">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file contains the following pieces of information, each delimited by a pipe (|):</span></span>  
  
-   <span data-ttu-id="03770-111">Дата и время</span><span class="sxs-lookup"><span data-stu-id="03770-111">Date and time</span></span>  
  
-   <span data-ttu-id="03770-112">Имя потока</span><span class="sxs-lookup"><span data-stu-id="03770-112">Thread name</span></span>  
  
-   <span data-ttu-id="03770-113">Идентификатор потока</span><span class="sxs-lookup"><span data-stu-id="03770-113">Thread ID</span></span>  
  
-   <span data-ttu-id="03770-114">Серьезность сведений в журнале («Предупреждение», «Ошибка», «Неустранимая ошибка», «Сведения» и «Отладка»)</span><span class="sxs-lookup"><span data-stu-id="03770-114">Log severity (FATAL, ERROR, WARN, INFO, and DEBUG)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03770-115">Серьезность сведений в журнале «Отладка» — такая же, как «Подробные».</span><span class="sxs-lookup"><span data-stu-id="03770-115">The DEBUG logging severity is same as Verbose.</span></span>  
  
-   <span data-ttu-id="03770-116">UID (идентификатор внутренней инфраструктуры DQS)</span><span class="sxs-lookup"><span data-stu-id="03770-116">UID (internal DQS infrastructure ID)</span></span>  
  
-   <span data-ttu-id="03770-117">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="03770-117">Namespace</span></span>  
  
-   <span data-ttu-id="03770-118">Класс и метод</span><span class="sxs-lookup"><span data-stu-id="03770-118">Class and method</span></span>  
  
-   <span data-ttu-id="03770-119">Сообщение</span><span class="sxs-lookup"><span data-stu-id="03770-119">Message</span></span>  
  
 <span data-ttu-id="03770-120">Наряду с этим файл журнала отображает сведения о версии приложения, имени компьютера, имени пользователя и операционной системе.</span><span class="sxs-lookup"><span data-stu-id="03770-120">Along with these, the log file also displays information about the application version, computer name, user name, and operating system.</span></span>  
  
 <span data-ttu-id="03770-121">Образец записи в файле журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] выглядит так:</span><span class="sxs-lookup"><span data-stu-id="03770-121">A sample entry in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file looks like the following:</span></span>  
  
```  
23-08-2013 01:45:29|[]|4|INFO|PUID|InfInfoModuleStarting|Microsoft.Ssdqs.Core.Startup.ServerInit|Starting DQS ServerInit: version [12.0.0.0], machine name [DQS-TEST], user name [NT Service\MSSQLSERVER], operating system [Microsoft Windows NT 6.1.7600.0]...  
```  
  
 <span data-ttu-id="03770-122">Файл DQServerLog.DQS_MAIN.log — последовательно обновляемый, и новый файл журнала создается после того, как размер существующего файла превышает предел, указанный в параметрах конфигурации журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03770-122">The DQServerLog.DQS_MAIN.log file is a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="03770-123">Дополнительные сведения см. в разделе [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="03770-123">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="data-quality-client-log-file"></a><a name="DQSClient"></a><span data-ttu-id="03770-124">Файл журнала Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="03770-124">Data Quality Client Log File</span></span>  
 <span data-ttu-id="03770-125">Файл журнала [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , DQClientLog.log, включает журналы на клиентской стороне.</span><span class="sxs-lookup"><span data-stu-id="03770-125">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file, DQClientLog.log, includes the client side logs.</span></span> <span data-ttu-id="03770-126">Файл журнала [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] находится в папке % APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="03770-126">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="03770-127">Файл журнала [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] содержит такой же набор сведений, как файл журнала сервера, но на клиентской стороне.</span><span class="sxs-lookup"><span data-stu-id="03770-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file contains similar set of information as in the server log file, but for the client side.</span></span>  
  
 <span data-ttu-id="03770-128">Как и файл журнала [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , файл журнала [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , также последовательно обновляемый, и новый файл журнала создаются после того, как размер существующего файла превышает предел, указанный в параметрах конфигурации журнала [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03770-128">As with the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is also a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log configuration settings.</span></span> <span data-ttu-id="03770-129">Дополнительные сведения см. в разделе [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="03770-129">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="dqs-cleansing-component-log-file"></a><a name="DQSCleansing"></a><span data-ttu-id="03770-130">Файл журнала компонента очистки DQS</span><span class="sxs-lookup"><span data-stu-id="03770-130">DQS Cleansing Component Log File</span></span>  
 <span data-ttu-id="03770-131">Файл журнала [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] , DQSSSISLog.log, включает журналы действий, выполненных с использованием [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03770-131">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file, DQSSSISLog.log, includes logs of activities performed using the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="03770-132">Файл журнала компонента [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] находится в папке % APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="03770-132">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] component log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="03770-133">Файл журнала [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] содержит такой же набор сведений, как файл журнала сервера, но для [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03770-133">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file contains similar set of information as in the server log file, but for the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
##  <a name="related-tasks"></a><a name="RT"></a> <span data-ttu-id="03770-134">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="03770-134">Related Tasks</span></span>  
  
|<span data-ttu-id="03770-135">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="03770-135">Task Description</span></span>|<span data-ttu-id="03770-136">Раздел</span><span class="sxs-lookup"><span data-stu-id="03770-136">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="03770-137">Инструкции по настройке параметров серьезности записи в журнал для файлов журнала DQS с помощью [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03770-137">Describes how to configure log severity settings for DQS log files using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>|[<span data-ttu-id="03770-138">Настройка степеней серьезности для файлов журнала DQS</span><span class="sxs-lookup"><span data-stu-id="03770-138">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)|  
|<span data-ttu-id="03770-139">Инструкции по ручной настройке дополнительных параметров для файлов журнала DQS.</span><span class="sxs-lookup"><span data-stu-id="03770-139">Describes how to manually configure advanced settings for DQS log files.</span></span>|[<span data-ttu-id="03770-140">Configure Advanced Settings for DQS Log Files</span><span class="sxs-lookup"><span data-stu-id="03770-140">Configure Advanced Settings for DQS Log Files</span></span>](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)|  
  
## <a name="see-also"></a><span data-ttu-id="03770-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="03770-141">See Also</span></span>  
 [<span data-ttu-id="03770-142">администрирование DQS</span><span class="sxs-lookup"><span data-stu-id="03770-142">DQS Administration</span></span>](../../2014/data-quality-services/dqs-administration.md)  
  
  
