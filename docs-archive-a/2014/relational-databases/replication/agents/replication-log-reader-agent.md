---
title: Агент чтения журнала репликации | Документация Майкрософт
ms.custom: ''
ms.date: 10/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Log Reader Agent, executables
- Log Reader Agent, parameter reference
- agents [SQL Server replication], Log Reader Agent
- command prompt [SQL Server replication]
ms.assetid: 5487b645-d99b-454c-8bd2-aff470709a0e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 120c7418d8b16fe6d083961affcf0b8a9c9f6c65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664139"
---
# <a name="replication-log-reader-agent"></a><span data-ttu-id="ead4f-102">Агент чтения журнала репликации</span><span class="sxs-lookup"><span data-stu-id="ead4f-102">Replication Log Reader Agent</span></span>
  <span data-ttu-id="ead4f-103">Агент чтения журнала производит мониторинг журналов транзакций всех баз данных, включенных в репликацию транзакций, и копирует помеченные для репликации транзакции из журнала транзакций в базу данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-103">The Replication Log Reader Agent is an executable that monitors the transaction log of each database configured for transactional replication and copies the transactions marked for replication from the transaction log into the distribution database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ead4f-104">Параметры можно указывать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="ead4f-104">Parameters can be specified in any order.</span></span> <span data-ttu-id="ead4f-105">Если необязательные параметры не указаны, используются стандартные значения из профиля агента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ead4f-105">When optional parameters are not specified, predefined values based on the default agent profile are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ead4f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ead4f-106">Syntax</span></span>  
  
```  
  
      logread [-?]   
-Publisherserver_name[\instance_name]   
-PublisherDBpublisher_database   
[-Continuous]  
[-DefinitionFiledef_path_and_file_name]  
[-Distributorserver_name[\instance_name]]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-ExtendedEventConfigFileconfiguration_path_and_file_name]  
[-HistoryVerboseLevel [0|1|2]]  
[-KeepAliveMessageIntervalkeep_alive_message_interval_seconds]  
[-LoginTimeOutlogin_time_out_seconds]  
[-LogScanThresholdscan_threshold]  
[-MaxCmdsInTrannumber_of_commands]  
[-MessageIntervalmessage_interval]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2|3|4]]  
[-PacketSizepacket_size]  
[-PollingIntervalpolling_interval]  
[-ProfileNameprofile_name]   
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-PublisherSecurityMode [0|1]]  
[-PublisherLoginpublisher_login]  
[-PublisherPasswordpublisher_password]   
[-QueryTimeOutquery_time_out_seconds]  
[-ReadBatchSizenumber_of_transactions]   
[-ReadBatchThresholdread_batch_threshold]  
[-RecoverFromDataErrors]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ead4f-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ead4f-107">Arguments</span></span>  
 <span data-ttu-id="ead4f-108">**-?**</span><span class="sxs-lookup"><span data-stu-id="ead4f-108">**-?**</span></span>  
 <span data-ttu-id="ead4f-109">Отображает сведения об использовании.</span><span class="sxs-lookup"><span data-stu-id="ead4f-109">Displays usage information.</span></span>  
  
 <span data-ttu-id="ead4f-110">**-Publisher** _имя_сервера_[ **\\** _имя_экземпляра_]</span><span class="sxs-lookup"><span data-stu-id="ead4f-110">**-Publisher** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="ead4f-111">Имя издателя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-111">Is the name of the Publisher.</span></span> <span data-ttu-id="ead4f-112">Укажите *имя_сервера*, чтобы использовать экземпляр сервера [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ead4f-112">Specify *server_name* for the default instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="ead4f-113">Укажите _имя_сервера_ **\\** _имя_экземпляра_ для именованного экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="ead4f-113">Specify _server_name_**\\**_instance_name_ for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span>  
  
 <span data-ttu-id="ead4f-114">**-PublisherDB** _база_данных_издателя_</span><span class="sxs-lookup"><span data-stu-id="ead4f-114">**-PublisherDB** _publisher_database_</span></span>  
 <span data-ttu-id="ead4f-115">Имя базы данных издателя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-115">Is the name of the Publisher database.</span></span>  
  
 <span data-ttu-id="ead4f-116">**-Continuous**</span><span class="sxs-lookup"><span data-stu-id="ead4f-116">**-Continuous**</span></span>  
 <span data-ttu-id="ead4f-117">Указывает, производит ли агент непрерывный опрос транзакций для репликации.</span><span class="sxs-lookup"><span data-stu-id="ead4f-117">Specifies whether the agent tries to poll replicated transactions continually.</span></span> <span data-ttu-id="ead4f-118">Если да, то он с заданным интервалом производит запрос из источника транзакций, даже если транзакции отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="ead4f-118">If specified, the agent polls replicated transactions from the source at polling intervals even if there are no transactions pending.</span></span>  
  
 <span data-ttu-id="ead4f-119">**-DefinitionFile** _путь_и_имя_файла_определения_</span><span class="sxs-lookup"><span data-stu-id="ead4f-119">**-DefinitionFile** _def_path_and_file_name_</span></span>  
 <span data-ttu-id="ead4f-120">Путь к файлу определения агента.</span><span class="sxs-lookup"><span data-stu-id="ead4f-120">Is the path of the agent definition file.</span></span> <span data-ttu-id="ead4f-121">Файл определения агента содержит параметры командной строки для агента.</span><span class="sxs-lookup"><span data-stu-id="ead4f-121">An agent definition file contains command-line arguments for the agent.</span></span> <span data-ttu-id="ead4f-122">Содержимое файла анализируется как для исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="ead4f-122">The content of the file is parsed as an executable file.</span></span> <span data-ttu-id="ead4f-123">Значения аргумента, содержащие произвольные символы, следует заключать в двойные кавычки (").</span><span class="sxs-lookup"><span data-stu-id="ead4f-123">Use double quotation marks (") to specify argument values that contain arbitrary characters.</span></span>  
  
 <span data-ttu-id="ead4f-124">**-Distributor** _имя_сервера_[ **\\** _имя_экземпляра_]</span><span class="sxs-lookup"><span data-stu-id="ead4f-124">**-Distributor** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="ead4f-125">Имя распространителя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-125">Is the Distributor name.</span></span> <span data-ttu-id="ead4f-126">Укажите *server_name* , чтобы использовать экземпляр сервера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ead4f-126">Specify *server_name* for the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="ead4f-127">Укажите _имя_сервера_ **\\** _имя_экземпляра_ для именованного экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="ead4f-127">Specify _server_name_**\\**_instance_name_ for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span>  
  
 <span data-ttu-id="ead4f-128">**-DistributorLogin** _имя_входа_распространителя_</span><span class="sxs-lookup"><span data-stu-id="ead4f-128">**-DistributorLogin** _distributor_login_</span></span>  
 <span data-ttu-id="ead4f-129">Имя входа распространителя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-129">Is the Distributor login name.</span></span>  
  
 <span data-ttu-id="ead4f-130">**-DistributorPassword** _пароль_распространителя_</span><span class="sxs-lookup"><span data-stu-id="ead4f-130">**-DistributorPassword** _distributor_password_</span></span>  
 <span data-ttu-id="ead4f-131">Пароль распространителя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-131">Is the Distributor password.</span></span>  
  
 <span data-ttu-id="ead4f-132">**-DistributorSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="ead4f-132">**-DistributorSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="ead4f-133">Указывает режим безопасности распространителя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-133">Specifies the security mode of the Distributor.</span></span> <span data-ttu-id="ead4f-134">Значение **1** означает проверку подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Windows, а значение **0** — проверку подлинности [!INCLUDE[msCoName](../../../includes/msconame-md.md)] (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ead4f-134">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication Mode (default), and a value of **1** indicates [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="ead4f-135">**-EncryptionLevel** [ **0** | **1** | **2** ]</span><span class="sxs-lookup"><span data-stu-id="ead4f-135">**-EncryptionLevel** [ **0** | **1** | **2** ]</span></span>  
 <span data-ttu-id="ead4f-136">Уровень шифрования по протоколу SSL, который используется агентом чтения журнала при установлении соединений.</span><span class="sxs-lookup"><span data-stu-id="ead4f-136">Is the level of Secure Sockets Layer (SSL) encryption that is used by the Log Reader Agent when making connections.</span></span>  
  
|<span data-ttu-id="ead4f-137">Значение EncryptionLevel</span><span class="sxs-lookup"><span data-stu-id="ead4f-137">EncryptionLevel value</span></span>|<span data-ttu-id="ead4f-138">Описание</span><span class="sxs-lookup"><span data-stu-id="ead4f-138">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="ead4f-139">**0**</span><span class="sxs-lookup"><span data-stu-id="ead4f-139">**0**</span></span>|<span data-ttu-id="ead4f-140">Указывает, что SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="ead4f-140">Specifies that SSL is not used.</span></span>|  
|<span data-ttu-id="ead4f-141">**1**</span><span class="sxs-lookup"><span data-stu-id="ead4f-141">**1**</span></span>|<span data-ttu-id="ead4f-142">Указывает, что SSL используется, но агент не проверяет, подписан ли сертификат сервера SSL надежным издателем.</span><span class="sxs-lookup"><span data-stu-id="ead4f-142">Specifies that SSL is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer.</span></span>|  
|<span data-ttu-id="ead4f-143">**2**</span><span class="sxs-lookup"><span data-stu-id="ead4f-143">**2**</span></span>|<span data-ttu-id="ead4f-144">Указывает, что SSL используется и сертификат подтвержден.</span><span class="sxs-lookup"><span data-stu-id="ead4f-144">Specifies that SSL is used, and that the certificate is verified.</span></span>|  

 > [!NOTE]  
 >  <span data-ttu-id="ead4f-145">Допустимый SSL-сертификат задается с полным доменным именем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ead4f-145">A valid SSL certificate is defined with a fully qualified domain name of the SQL Server.</span></span> <span data-ttu-id="ead4f-146">Если параметр -EncryptionLevel имеет значение 2, то для подключения агента создайте псевдоним на локальном сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ead4f-146">In order for the agent to connect successfully when setting -EncryptionLevel to 2, create an alias on the local SQL Server.</span></span> <span data-ttu-id="ead4f-147">Для параметра Alias Name (Имя псевдонима) должно быть указано имя сервера, а для параметра Server (Сервер) — полное доменное имя SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ead4f-147">The 'Alias Name' parameter should be the server name and the 'Server' parameter should be set to the fully qualified name of the SQL Server.</span></span>
 
 <span data-ttu-id="ead4f-148">Дополнительные сведения см. в разделе [репликация SQL Server Security](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ead4f-148">For more information, see [SQL Server Replication Security](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="ead4f-149">**-ExtendedEventConfigFile** _путь_и_имя_файла_конфигурации_</span><span class="sxs-lookup"><span data-stu-id="ead4f-149">**-ExtendedEventConfigFile** _configuration_path_and_file_name_</span></span>  
 <span data-ttu-id="ead4f-150">Задает путь и имя файла для XML-файла конфигурации расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="ead4f-150">Specifies the path and file name for the extended events XML configuration file.</span></span> <span data-ttu-id="ead4f-151">Файл конфигурации расширенных событий позволяет настраивать сеансы и включать события для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ead4f-151">The extended events configuration file allows you to configure sessions and enable events for tracking.</span></span>  
  
 <span data-ttu-id="ead4f-152">**-HistoryVerboseLevel** [ **0**| **1**| **2**]</span><span class="sxs-lookup"><span data-stu-id="ead4f-152">**-HistoryVerboseLevel** [ **0**| **1**| **2**]</span></span>  
 <span data-ttu-id="ead4f-153">Указывает объем данных, заносимых в журнал во время операции чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="ead4f-153">Specifies the amount of history logged during a log reader operation.</span></span> <span data-ttu-id="ead4f-154">Влияние на производительность, оказываемое ведением журнала, можно максимально уменьшить, выбрав значение **1**.</span><span class="sxs-lookup"><span data-stu-id="ead4f-154">You can minimize the performance effect of history logging by selecting **1**.</span></span>  
  
|<span data-ttu-id="ead4f-155">Значение HistoryVerboseLevel</span><span class="sxs-lookup"><span data-stu-id="ead4f-155">HistoryVerboseLevel value</span></span>|<span data-ttu-id="ead4f-156">Описание</span><span class="sxs-lookup"><span data-stu-id="ead4f-156">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="ead4f-157">**0**</span><span class="sxs-lookup"><span data-stu-id="ead4f-157">**0**</span></span>||  
|<span data-ttu-id="ead4f-158">**1**</span><span class="sxs-lookup"><span data-stu-id="ead4f-158">**1**</span></span>|<span data-ttu-id="ead4f-159">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ead4f-159">Default.</span></span> <span data-ttu-id="ead4f-160">Всегда обновлять предыдущее сообщение журнала с таким же состоянием (запуск, выполнение, успех и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ead4f-160">Always update a previous history message of the same status (startup, progress, success, and so on).</span></span> <span data-ttu-id="ead4f-161">Если предыдущих сообщений с таким состоянием нет, то вставить новую запись.</span><span class="sxs-lookup"><span data-stu-id="ead4f-161">If no previous record with the same status exists, insert a new record.</span></span>|  
|<span data-ttu-id="ead4f-162">**2**</span><span class="sxs-lookup"><span data-stu-id="ead4f-162">**2**</span></span>|<span data-ttu-id="ead4f-163">Если есть сообщения о таких событиях, как состояние простоя или долго выполняемое задание, то обновить предыдущие записи, в противном случае вставить новые записи журнала.</span><span class="sxs-lookup"><span data-stu-id="ead4f-163">Insert new history records unless the record is for such things as idle messages or long-running job messages, in which case update the previous records.</span></span>|  
  
 <span data-ttu-id="ead4f-164">**-KeepAliveMessageInterval** _интервал_в_секундах_для_сообщения_keep_alive_</span><span class="sxs-lookup"><span data-stu-id="ead4f-164">**-KeepAliveMessageInterval** _keep_alive_message_interval_seconds_</span></span>  
 <span data-ttu-id="ead4f-165">Количество секунд до того, как поток журнала проверяет наличие соединений, ожидающих ответа от сервера.</span><span class="sxs-lookup"><span data-stu-id="ead4f-165">Is the number of seconds before the history thread checks if any of the existing connections is waiting for a response from the server.</span></span> <span data-ttu-id="ead4f-166">Это значение можно уменьшить, чтобы агент проверки не помечал агент чтения журнала как подозрительный при выполнении долго выполняющегося пакета.</span><span class="sxs-lookup"><span data-stu-id="ead4f-166">This value can be decreased to avoid having the checkup agent mark the Log Reader Agent as suspect when executing a long-running batch.</span></span> <span data-ttu-id="ead4f-167">Значение по умолчанию — 300 секунд.</span><span class="sxs-lookup"><span data-stu-id="ead4f-167">The default is 300 seconds.</span></span>  
  
 <span data-ttu-id="ead4f-168">**-LoginTimeOut** _время_ожидания_входа_в_секундах_</span><span class="sxs-lookup"><span data-stu-id="ead4f-168">**-LoginTimeOut** _login_time_out_seconds_</span></span>  
 <span data-ttu-id="ead4f-169">Время ожидания входа в секундах. Значение по умолчанию составляет 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="ead4f-169">Is the number of seconds before the login times out. The default is 15 seconds.</span></span>  
  
 <span data-ttu-id="ead4f-170">**-LogScanThreshold** _порог_сканирования_</span><span class="sxs-lookup"><span data-stu-id="ead4f-170">**-LogScanThreshold** _scan_threshold_</span></span>  
 <span data-ttu-id="ead4f-171">Только для внутреннего применения.</span><span class="sxs-lookup"><span data-stu-id="ead4f-171">Internal use only.</span></span>  
  
 <span data-ttu-id="ead4f-172">**-MaxCmdsInTran** _число_команд_</span><span class="sxs-lookup"><span data-stu-id="ead4f-172">**-MaxCmdsInTran** _number_of_commands_</span></span>  
 <span data-ttu-id="ead4f-173">Задает максимальное количество инструкций, группируемых в транзакцию, когда агент чтения журнала записывает команды в базу данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-173">Specifies the maximum number of statements grouped into a transaction as the Log Reader writes commands to the distribution database.</span></span> <span data-ttu-id="ead4f-174">Использование этого параметра позволяет агенту чтения журнала и агенту распространителя разделять большие транзакции (состоящие из множества команд) на издателе на несколько меньших транзакций при применении команд на подписчике.</span><span class="sxs-lookup"><span data-stu-id="ead4f-174">Using this parameter allows the Log Reader Agent and Distribution Agent to divide large transactions (consisting of many commands) at the Publisher into several smaller transactions when applied at the Subscriber.</span></span> <span data-ttu-id="ead4f-175">Задание этого параметра может снизить вероятность состязаний на распространителе и уменьшить задержку при передаче данных между издателем и подписчиком.</span><span class="sxs-lookup"><span data-stu-id="ead4f-175">Specifying this parameter can reduce contention at the Distributor and reduce latency between the Publisher and Subscriber.</span></span> <span data-ttu-id="ead4f-176">Поскольку исходная транзакция применяется меньшими по размеру блоками, подписчик может получить доступ к строкам большой логической транзакции издателя до завершения исходной транзакции, разбивая строгую атомарность транзакции.</span><span class="sxs-lookup"><span data-stu-id="ead4f-176">Because the original transaction is applied in smaller units, the Subscriber can access rows of a large logical Publisher transaction prior to the end of the original transaction, breaking strict transactional atomicity.</span></span> <span data-ttu-id="ead4f-177">По умолчанию установлено значение **0**, сохраняющее границы транзакции издателя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-177">The default is **0**, which preserves the transaction boundaries of the Publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ead4f-178">Данный параметр не учитывается для публикаций, отличных от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ead4f-178">This parameter is ignored for non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] publications.</span></span> <span data-ttu-id="ead4f-179">Дополнительные сведения см. в подразделе «Настройка задания наборов транзакций» раздела [Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="ead4f-179">For more information, see the section "Configuring the Transaction Set Job" in [Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md).</span></span>  
  
 <span data-ttu-id="ead4f-180">**-MessageInterval** _интервал_сообщений_</span><span class="sxs-lookup"><span data-stu-id="ead4f-180">**-MessageInterval** _message_interval_</span></span>  
 <span data-ttu-id="ead4f-181">Интервал времени, использующийся для ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="ead4f-181">Is the time interval used for history logging.</span></span> <span data-ttu-id="ead4f-182">Событие регистрируется в журнале, когда после регистрации последнего события достигнуто значение **MessageInterval** .</span><span class="sxs-lookup"><span data-stu-id="ead4f-182">A history event is logged when the **MessageInterval** value is reached after the last history event is logged.</span></span>  
  
 <span data-ttu-id="ead4f-183">При отсутствии реплицируемой транзакции на источнике агент передает распространителю сообщение об отсутствии транзакции.</span><span class="sxs-lookup"><span data-stu-id="ead4f-183">If there is no replicated transaction available at the source, the agent reports a no-transaction message to the Distributor.</span></span> <span data-ttu-id="ead4f-184">Данный параметр определяет период ожидания агента до передачи следующего сообщения об отсутствии транзакции.</span><span class="sxs-lookup"><span data-stu-id="ead4f-184">This option specifies how long the agent waits before reporting another no-transaction message.</span></span> <span data-ttu-id="ead4f-185">Агенты всегда передают сообщение об отсутствии транзакции, если на источнике после ранее обработанных реплицируемых транзакций не обнаруживается доступных транзакций.</span><span class="sxs-lookup"><span data-stu-id="ead4f-185">Agents always report a no-transaction message when they detect that there are no transactions available at the source after previously processing replicated transactions.</span></span> <span data-ttu-id="ead4f-186">Значение по умолчанию — 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="ead4f-186">The default is 60 seconds.</span></span>  
  
 <span data-ttu-id="ead4f-187">**-Output** _путь_и_имя_выходного_файла_</span><span class="sxs-lookup"><span data-stu-id="ead4f-187">**-Output** _output_path_and_file_name_</span></span>  
 <span data-ttu-id="ead4f-188">Путь к выходному файлу агента.</span><span class="sxs-lookup"><span data-stu-id="ead4f-188">Is the path of the agent output file.</span></span> <span data-ttu-id="ead4f-189">Если имя файла не указано, данные выводятся на консоль.</span><span class="sxs-lookup"><span data-stu-id="ead4f-189">If the file name is not provided, the output is sent to the console.</span></span> <span data-ttu-id="ead4f-190">Если указанный файл существует, то выходные данные добавляются в конец файла.</span><span class="sxs-lookup"><span data-stu-id="ead4f-190">If the specified file name exists, the output is appended to the file.</span></span>  
  
 <span data-ttu-id="ead4f-191">**-OutputVerboseLevel** [ **0**| **1**| **2** | **3** | **4** ]</span><span class="sxs-lookup"><span data-stu-id="ead4f-191">**-OutputVerboseLevel** [ **0**| **1**| **2** | **3** | **4** ]</span></span>  
 <span data-ttu-id="ead4f-192">Указывает, должны ли выводимые данные быть подробными.</span><span class="sxs-lookup"><span data-stu-id="ead4f-192">Specifies whether the output should be verbose.</span></span>  
  
|<span data-ttu-id="ead4f-193">Значение</span><span class="sxs-lookup"><span data-stu-id="ead4f-193">Value</span></span>|<span data-ttu-id="ead4f-194">Описание</span><span class="sxs-lookup"><span data-stu-id="ead4f-194">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ead4f-195">**0**</span><span class="sxs-lookup"><span data-stu-id="ead4f-195">**0**</span></span>|<span data-ttu-id="ead4f-196">Выводятся только сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ead4f-196">Only error messages are printed.</span></span>|  
|<span data-ttu-id="ead4f-197">**1**</span><span class="sxs-lookup"><span data-stu-id="ead4f-197">**1**</span></span>|<span data-ttu-id="ead4f-198">Выводятся все сообщения о ходе выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="ead4f-198">All agent progress report messages are printed.</span></span>|  
|<span data-ttu-id="ead4f-199">**2** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ead4f-199">**2** (default)</span></span>|<span data-ttu-id="ead4f-200">Выводятся все сообщения об ошибках и о ходе выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="ead4f-200">All error messages and agent progress report messages are printed.</span></span>|  
|<span data-ttu-id="ead4f-201">**3**</span><span class="sxs-lookup"><span data-stu-id="ead4f-201">**3**</span></span>|<span data-ttu-id="ead4f-202">Выводятся первые 100 байт для каждой реплицируемой команды.</span><span class="sxs-lookup"><span data-stu-id="ead4f-202">The first 100 bytes of each replicated command are printed.</span></span>|  
|<span data-ttu-id="ead4f-203">**4**</span><span class="sxs-lookup"><span data-stu-id="ead4f-203">**4**</span></span>|<span data-ttu-id="ead4f-204">Выводятся все реплицируемые команды.</span><span class="sxs-lookup"><span data-stu-id="ead4f-204">All replicated commands are printed.</span></span>|  
  
 <span data-ttu-id="ead4f-205">Значения 2-4 могут оказаться полезными при отладке.</span><span class="sxs-lookup"><span data-stu-id="ead4f-205">Values 2-4 are useful when debugging.</span></span>  
  
 <span data-ttu-id="ead4f-206">**-PacketSize** _размер_пакета_</span><span class="sxs-lookup"><span data-stu-id="ead4f-206">**-PacketSize** _packet_size_</span></span>  
 <span data-ttu-id="ead4f-207">Размер пакета в байтах.</span><span class="sxs-lookup"><span data-stu-id="ead4f-207">Is the packet size, in bytes.</span></span> <span data-ttu-id="ead4f-208">Значение по умолчанию равно 4 096 байт.</span><span class="sxs-lookup"><span data-stu-id="ead4f-208">The default is 4096 (bytes).</span></span>  
  
 <span data-ttu-id="ead4f-209">**-PollingInterval** _интервал_опроса_</span><span class="sxs-lookup"><span data-stu-id="ead4f-209">**-PollingInterval** _polling_interval_</span></span>  
 <span data-ttu-id="ead4f-210">Определяет частоту (в секундах) опроса журнала о реплицируемых транзакциях.</span><span class="sxs-lookup"><span data-stu-id="ead4f-210">Is how often, in seconds, the log is queried for replicated transactions.</span></span> <span data-ttu-id="ead4f-211">Значение по умолчанию — 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="ead4f-211">The default is 5 seconds.</span></span>  
  
 <span data-ttu-id="ead4f-212">**-ProfileName** _имя_профиля_</span><span class="sxs-lookup"><span data-stu-id="ead4f-212">**-ProfileName** _profile_name_</span></span>  
 <span data-ttu-id="ead4f-213">Указывает профиль агента, из которого берутся параметры агента.</span><span class="sxs-lookup"><span data-stu-id="ead4f-213">Specifies an agent profile to use for agent parameters.</span></span> <span data-ttu-id="ead4f-214">Если **ProfileName** имеет значение NULL, профиль агента отключен.</span><span class="sxs-lookup"><span data-stu-id="ead4f-214">If **ProfileName** is NULL, the agent profile is disabled.</span></span> <span data-ttu-id="ead4f-215">Если значение **ProfileName** не указано, используется профиль по умолчанию для агентов этого типа.</span><span class="sxs-lookup"><span data-stu-id="ead4f-215">If **ProfileName** is not specified, the default profile for the agent type is used.</span></span> <span data-ttu-id="ead4f-216">Дополнительные сведения см. в статье [Профили агента репликации](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ead4f-216">For information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="ead4f-217">**-PublisherFailoverPartner** _имя_сервера_[ **\\** _имя_экземпляра_]</span><span class="sxs-lookup"><span data-stu-id="ead4f-217">**-PublisherFailoverPartner** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="ead4f-218">Указывает партнера по обеспечению отработки отказа служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , участвующего в сеансе зеркального отображения базы данных с базой данных публикации.</span><span class="sxs-lookup"><span data-stu-id="ead4f-218">Specifies the failover partner instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participating in a database mirroring session with the publication database.</span></span> <span data-ttu-id="ead4f-219">Дополнительные сведения см. в статье [Зеркальное отображение и репликация баз данных (SQL Server)](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ead4f-219">For more information, see [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="ead4f-220">**-PublisherSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="ead4f-220">**-PublisherSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="ead4f-221">Указывает режим безопасности издателя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-221">Specifies the security mode of the Publisher.</span></span> <span data-ttu-id="ead4f-222">Значение **0** означает проверку подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (по умолчанию), а значение **1** — проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="ead4f-222">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication (default), and a value of **1** indicates Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="ead4f-223">**-PublisherLogin** _имя_входа_на_издателе_</span><span class="sxs-lookup"><span data-stu-id="ead4f-223">**-PublisherLogin** _publisher_login_</span></span>  
 <span data-ttu-id="ead4f-224">Имя входа издателя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-224">Is the Publisher login name.</span></span>  
  
 <span data-ttu-id="ead4f-225">**-PublisherPassword** _пароль_на_издателе_</span><span class="sxs-lookup"><span data-stu-id="ead4f-225">**-PublisherPassword** _publisher_password_</span></span>  
 <span data-ttu-id="ead4f-226">Пароль издателя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-226">Is the Publisher password.</span></span>  
  
 <span data-ttu-id="ead4f-227">**-QueryTimeOut** _время_ожидания_запроса_в_секундах_</span><span class="sxs-lookup"><span data-stu-id="ead4f-227">**-QueryTimeOut** _query_time_out_seconds_</span></span>  
 <span data-ttu-id="ead4f-228">Время ожидания запроса в секундах. Значение по умолчанию — 1800 секунд.</span><span class="sxs-lookup"><span data-stu-id="ead4f-228">Is the number of seconds before the query times out. The default is 1800 seconds.</span></span>  
  
 <span data-ttu-id="ead4f-229">**-ReadBatchSize** _число_транзакций_</span><span class="sxs-lookup"><span data-stu-id="ead4f-229">**-ReadBatchSize** _number_of_transactions_</span></span>  
 <span data-ttu-id="ead4f-230">Определяет максимальное число транзакций, которые считываются из журнала транзакций публикуемой базы данных за один цикл обработки (значение по умолчанию — 500).</span><span class="sxs-lookup"><span data-stu-id="ead4f-230">Is the maximum number of transactions read out of the transaction log of the publishing database per processing cycle, with a default of 500.</span></span> <span data-ttu-id="ead4f-231">Агент будет продолжать считывать транзакции пакетами, пока все они не будут считаны из журнала.</span><span class="sxs-lookup"><span data-stu-id="ead4f-231">The agent will continue to read transactions in batches until all transactions are read from the log.</span></span> <span data-ttu-id="ead4f-232">Этот параметр не поддерживается для издателей Oracle.</span><span class="sxs-lookup"><span data-stu-id="ead4f-232">This parameter is not supported for Oracle Publishers.</span></span>  
  
 <span data-ttu-id="ead4f-233">**-ReadBatchThreshold** _число_команд_</span><span class="sxs-lookup"><span data-stu-id="ead4f-233">**-ReadBatchThreshold** _number_of_commands_</span></span>  
 <span data-ttu-id="ead4f-234">Определяет число команд репликации, которые считываются из журнала транзакций перед отправкой подписчику агентом распространителя.</span><span class="sxs-lookup"><span data-stu-id="ead4f-234">Is the number of replication commands to be read from the transaction log before being issued to the Subscriber by the Distribution Agent.</span></span> <span data-ttu-id="ead4f-235">Значение по умолчанию равно 0.</span><span class="sxs-lookup"><span data-stu-id="ead4f-235">The default is 0.</span></span> <span data-ttu-id="ead4f-236">Если этот параметр не указан, то агент чтения журнала произведет считывание до конца журнала или до числа транзакций, указанного в параметре **-ReadBatchSize** .</span><span class="sxs-lookup"><span data-stu-id="ead4f-236">If this parameter is not specified, the Log Reader Agent will read to the end of the log or to the number specified in **-ReadBatchSize** (number of transactions).</span></span>  
  
 <span data-ttu-id="ead4f-237">**-RecoverFromDataErrors**</span><span class="sxs-lookup"><span data-stu-id="ead4f-237">**-RecoverFromDataErrors**</span></span>  
 <span data-ttu-id="ead4f-238">Указывает, что агент чтения журнала должен продолжить работу после возникновения ошибок данных в столбце, опубликованном издателем, отличным от SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ead4f-238">Specifies that the Log Reader Agent continue to run when it encounters errors in column data published from a non-SQL Server Publisher.</span></span> <span data-ttu-id="ead4f-239">По умолчанию такие ошибки приводят к завершению работы агента чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="ead4f-239">By default, such errors cause the Log Reader Agent to fail.</span></span> <span data-ttu-id="ead4f-240">Если указан параметр **-RecoverFromDataErrors**, то производится репликация ошибочных данных либо значениями NULL, либо другими соответствующими значениями, а предупреждающие сообщения записываются в таблицу [MSlogreader_history](/sql/relational-databases/system-tables/mslogreader-history-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ead4f-240">When you use **-RecoverFromDataErrors**, erroneous column data is replicated either as NULL or an appropriate nonnull value, and warning messages are logged to the [MSlogreader_history](/sql/relational-databases/system-tables/mslogreader-history-transact-sql) table.</span></span> <span data-ttu-id="ead4f-241">Этот параметр поддерживается только для издателей Oracle.</span><span class="sxs-lookup"><span data-stu-id="ead4f-241">This parameter is only supported for Oracle Publishers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ead4f-242">Remarks</span><span class="sxs-lookup"><span data-stu-id="ead4f-242">Remarks</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ead4f-243">Если агент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] настроен для запуска от учетной записи локальной системы, а не пользователя домена (по умолчанию), то служба имеет доступ только к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="ead4f-243">If you installed [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent to run under a local system account instead of under a domain user account (the default), the service can access only the local computer.</span></span> <span data-ttu-id="ead4f-244">Если агент чтения журнала, запускаемый агентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , настроен для входа в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]с проверкой подлинности Windows, то работа агента слияния завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ead4f-244">If the Log Reader Agent that runs under [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent is configured to use Windows Authentication Mode when it logs in to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the Log Reader Agent fails.</span></span> <span data-ttu-id="ead4f-245">Значением по умолчанию является проверка подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ead4f-245">The default setting is [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="ead4f-246">Дополнительные сведения об изменении учетных записей безопасности см. в разделе [View and Modify Replication Security Settings](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ead4f-246">For information about changing security accounts, see [View and Modify Replication Security Settings](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="ead4f-247">Чтобы запустить агент чтения журнала, выполните из командной строки программу **logread.exe** .</span><span class="sxs-lookup"><span data-stu-id="ead4f-247">To start the Log Reader Agent, execute **logread.exe** from the command prompt.</span></span> <span data-ttu-id="ead4f-248">Дополнительные сведения см. в статье [Основные понятия исполняемых файлов агента репликации](../concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="ead4f-248">For information, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="change-history"></a><span data-ttu-id="ead4f-249">Журнал изменений</span><span class="sxs-lookup"><span data-stu-id="ead4f-249">Change History</span></span>  
  
|<span data-ttu-id="ead4f-250">Обновленное содержимое</span><span class="sxs-lookup"><span data-stu-id="ead4f-250">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="ead4f-251">Добавлен параметр **-ExtendedEventConfigFile** .</span><span class="sxs-lookup"><span data-stu-id="ead4f-251">Added the **-ExtendedEventConfigFile** parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ead4f-252">См. также:</span><span class="sxs-lookup"><span data-stu-id="ead4f-252">See Also</span></span>  
 [<span data-ttu-id="ead4f-253">Администрирование агента репликации</span><span class="sxs-lookup"><span data-stu-id="ead4f-253">Replication Agent Administration</span></span>](replication-agent-administration.md)  
  
  
