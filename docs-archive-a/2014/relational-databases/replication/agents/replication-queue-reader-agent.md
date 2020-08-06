---
title: Агент чтения очереди репликации | Документация Майкрософт
ms.custom: ''
ms.date: 10/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], Queue Reader Agent
- command prompt [SQL Server replication]
- Queue Reader Agent, parameter reference
- Queue Reader Agent, executables
ms.assetid: 8e227793-11f6-47c6-99dc-ffc282f5d4bf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 854c425db3fbaa346dab5eb2c41bd58cf03f65c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655668"
---
# <a name="replication-queue-reader-agent"></a><span data-ttu-id="77982-102">Агент чтения очереди репликации</span><span class="sxs-lookup"><span data-stu-id="77982-102">Replication Queue Reader Agent</span></span>
  <span data-ttu-id="77982-103">Агент чтения очереди репликации — это исполняемый файл, который считывает сообщения, хранящиеся в очереди [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или очереди сообщений [!INCLUDE[msCoName](../../../includes/msconame-md.md)], а затем применяет их к издателю.</span><span class="sxs-lookup"><span data-stu-id="77982-103">The Replication Queue Reader Agent is an executable that reads messages stored in a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue or a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue and then applies those messages to the Publisher.</span></span> <span data-ttu-id="77982-104">Агент чтения очереди используется совместно с публикациями транзакций и публикациями моментальных снимков, которые допускают обновление посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="77982-104">Queue Reader Agent is used with snapshot and transactional publications that allow queued updating.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77982-105">Параметры можно указывать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="77982-105">Parameters can be specified in any order.</span></span> <span data-ttu-id="77982-106">Если необязательные параметры не указаны, используются стандартные значения из профиля агента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77982-106">When optional parameters are not specified, predefined values based on the default agent profile are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77982-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77982-107">Syntax</span></span>  
  
```  
  
      qrdrsvc [-?]  
[-Continuous]  
[-DefinitionFiledefinition_file]  
[-Distributorserver_name[\instance_name]]  
[-DistributionDBdistribution_database]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-HistoryVerboseLevel [0|1|2|3]]  
[-LoginTimeOutlogin_time_out_seconds]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2]]  
[-PollingIntervalpolling_interval]  
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-ProfileNameagent_profile_name]  
[-QueryTimeOutquery_time_out_seconds]  
[-ResolverState [1|2|3]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="77982-108">Аргументы</span><span class="sxs-lookup"><span data-stu-id="77982-108">Arguments</span></span>  
 <span data-ttu-id="77982-109">**-?**</span><span class="sxs-lookup"><span data-stu-id="77982-109">**-?**</span></span>  
 <span data-ttu-id="77982-110">Отображает сведения об использовании.</span><span class="sxs-lookup"><span data-stu-id="77982-110">Displays usage information.</span></span>  
  
 <span data-ttu-id="77982-111">**-Continuous**</span><span class="sxs-lookup"><span data-stu-id="77982-111">**-Continuous**</span></span>  
 <span data-ttu-id="77982-112">Указывает, пытается ли агент обрабатывать находящиеся в очереди транзакции последовательно.</span><span class="sxs-lookup"><span data-stu-id="77982-112">Specifies whether the agent attempts to process queued transactions continuously.</span></span> <span data-ttu-id="77982-113">Если этот параметр указан, то агент продолжит работу даже в том случае, когда в очереди больше нет незавершенных транзакций, поступивших от какого-либо из подписчиков.</span><span class="sxs-lookup"><span data-stu-id="77982-113">If specified, the agent continues execution even if there are no queued transactions pending from any of the subscribers.</span></span>  
  
 <span data-ttu-id="77982-114">**-DefinitionFile** _путь_и_имя_файла_определения_</span><span class="sxs-lookup"><span data-stu-id="77982-114">**-DefinitionFile** _def_path_and_file_name_</span></span>  
 <span data-ttu-id="77982-115">Путь к файлу определения агента.</span><span class="sxs-lookup"><span data-stu-id="77982-115">Is the path of the agent definition file.</span></span> <span data-ttu-id="77982-116">Файл определения агента содержит параметры командной строки для агента.</span><span class="sxs-lookup"><span data-stu-id="77982-116">An agent definition file contains command-line arguments for the agent.</span></span> <span data-ttu-id="77982-117">Содержимое файла анализируется как для исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="77982-117">The content of the file is parsed as an executable file.</span></span> <span data-ttu-id="77982-118">Для указания значений параметров, содержащих произвольные символы, используются двойные кавычки (").</span><span class="sxs-lookup"><span data-stu-id="77982-118">Use double quotation marks (") to specify argument values containing arbitrary characters.</span></span>  
  
 <span data-ttu-id="77982-119">**-Distributor** _имя_сервера_[ **\\** _имя_экземпляра_]</span><span class="sxs-lookup"><span data-stu-id="77982-119">**-Distributor** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="77982-120">Имя распространителя.</span><span class="sxs-lookup"><span data-stu-id="77982-120">Is the Distributor name.</span></span> <span data-ttu-id="77982-121">Укажите *server_name* , чтобы использовать экземпляр сервера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77982-121">Specify *server_name* for the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="77982-122">Укажите *имя_сервера*\\*имя_экземпляра* для именованного экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="77982-122">Specify *server_name*\\*instance_name* for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="77982-123">Если же этот параметр не указан, то используется имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="77982-123">If not specified, the name defaults to the name of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="77982-124">**-DistributionDB** _база_данных_распространителя_</span><span class="sxs-lookup"><span data-stu-id="77982-124">**-DistributionDB** _distribution_database_</span></span>  
 <span data-ttu-id="77982-125">База данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="77982-125">Is the distribution database.</span></span>  
  
 <span data-ttu-id="77982-126">**-DistributorLogin** _имя_входа_распространителя_</span><span class="sxs-lookup"><span data-stu-id="77982-126">**-DistributorLogin** _distributor_login_</span></span>  
 <span data-ttu-id="77982-127">Имя входа распространителя.</span><span class="sxs-lookup"><span data-stu-id="77982-127">Is the Distributor login name.</span></span>  
  
 <span data-ttu-id="77982-128">**-DistributorPassword** _пароль_распространителя_</span><span class="sxs-lookup"><span data-stu-id="77982-128">**-DistributorPassword** _distributor_password_</span></span>  
 <span data-ttu-id="77982-129">Пароль распространителя.</span><span class="sxs-lookup"><span data-stu-id="77982-129">Is the Distributor password.</span></span>  
  
 <span data-ttu-id="77982-130">**-DistributorSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="77982-130">**-DistributorSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="77982-131">Указывает режим безопасности распространителя.</span><span class="sxs-lookup"><span data-stu-id="77982-131">Specifies the security mode of the Distributor.</span></span> <span data-ttu-id="77982-132">Значение **0** означает проверку подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (по умолчанию), а значение **1** — проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="77982-132">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication Mode (default), and a value of **1** indicates Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="77982-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span><span class="sxs-lookup"><span data-stu-id="77982-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span></span>  
 <span data-ttu-id="77982-134">Уровень шифрования по протоколу SSL, используемый агентом чтения очереди при установлении соединений.</span><span class="sxs-lookup"><span data-stu-id="77982-134">Is the level of Secure Sockets Layer (SSL) encryption used by the Queue Reader Agent when making connections.</span></span>  
  
|<span data-ttu-id="77982-135">Значение EncryptionLevel</span><span class="sxs-lookup"><span data-stu-id="77982-135">EncryptionLevel value</span></span>|<span data-ttu-id="77982-136">Описание</span><span class="sxs-lookup"><span data-stu-id="77982-136">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="77982-137">**0**</span><span class="sxs-lookup"><span data-stu-id="77982-137">**0**</span></span>|<span data-ttu-id="77982-138">Указывает, что SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="77982-138">Specifies that SSL is not used.</span></span>|  
|<span data-ttu-id="77982-139">**1**</span><span class="sxs-lookup"><span data-stu-id="77982-139">**1**</span></span>|<span data-ttu-id="77982-140">Указывает, что SSL используется, но агент не проверяет, подписан ли сертификат сервера SSL надежным издателем.</span><span class="sxs-lookup"><span data-stu-id="77982-140">Specifies that SSL is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer.</span></span>|  
|<span data-ttu-id="77982-141">**2**</span><span class="sxs-lookup"><span data-stu-id="77982-141">**2**</span></span>|<span data-ttu-id="77982-142">Указывает, что SSL используется и сертификат подтвержден.</span><span class="sxs-lookup"><span data-stu-id="77982-142">Specifies that SSL is used, and that the certificate is verified.</span></span>|  

 > [!NOTE]  
 >  <span data-ttu-id="77982-143">Допустимый SSL-сертификат задается с полным доменным именем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77982-143">A valid SSL certificate is defined with a fully qualified domain name of the SQL Server.</span></span> <span data-ttu-id="77982-144">Если параметр -EncryptionLevel имеет значение 2, то для подключения агента создайте псевдоним на локальном сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77982-144">In order for the agent to connect successfully when setting -EncryptionLevel to 2, create an alias on the local SQL Server.</span></span> <span data-ttu-id="77982-145">Для параметра Alias Name (Имя псевдонима) должно быть указано имя сервера, а для параметра Server (Сервер) — полное доменное имя SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77982-145">The 'Alias Name' parameter should be the server name and the 'Server' parameter should be set to the fully qualified name of the SQL Server.</span></span>
  
 <span data-ttu-id="77982-146">Дополнительные сведения см. в разделе [репликация SQL Server Security](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="77982-146">For more information, see [SQL Server Replication Security](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="77982-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="77982-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="77982-148">Указывает объем данных, регистрируемых в журнале при работе агента чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="77982-148">Specifies the amount of history logged during a queue reader operation.</span></span> <span data-ttu-id="77982-149">Выбрав значение **1**, можно свести к минимуму влияние ведения журнала на производительность.</span><span class="sxs-lookup"><span data-stu-id="77982-149">You can minimize the effect of history logging on performance by selecting **1**.</span></span>  
  
|<span data-ttu-id="77982-150">Значение HistoryVerboseLevel</span><span class="sxs-lookup"><span data-stu-id="77982-150">HistoryVerboseLevel value</span></span>|<span data-ttu-id="77982-151">Описание</span><span class="sxs-lookup"><span data-stu-id="77982-151">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="77982-152">**0**</span><span class="sxs-lookup"><span data-stu-id="77982-152">**0**</span></span>|<span data-ttu-id="77982-153">Ведение журнала отключено (не рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="77982-153">No history logging (not recommended).</span></span>|  
|<span data-ttu-id="77982-154">**1**</span><span class="sxs-lookup"><span data-stu-id="77982-154">**1**</span></span>|<span data-ttu-id="77982-155">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77982-155">Default.</span></span> <span data-ttu-id="77982-156">Всегда обновлять предыдущее сообщение журнала с таким же состоянием (запуск, выполнение, успех и т. д.).</span><span class="sxs-lookup"><span data-stu-id="77982-156">Always update a previous history message of the same status (startup, progress, success, and so on).</span></span> <span data-ttu-id="77982-157">Если предыдущих сообщений с таким состоянием нет, то вставить новую запись.</span><span class="sxs-lookup"><span data-stu-id="77982-157">If no previous record with the same status exists, insert a new record.</span></span>|  
|<span data-ttu-id="77982-158">**2**</span><span class="sxs-lookup"><span data-stu-id="77982-158">**2**</span></span>|<span data-ttu-id="77982-159">Вставлять в журнал новые записи, в том числе сообщения о простоях и долго выполняемых заданиях.</span><span class="sxs-lookup"><span data-stu-id="77982-159">Insert new history records, including idle messages or long-running job messages.</span></span>|  
|<span data-ttu-id="77982-160">**3**</span><span class="sxs-lookup"><span data-stu-id="77982-160">**3**</span></span>|<span data-ttu-id="77982-161">Вставлять в журнал новые записи, включая подробные сведения, которые могут оказаться полезными при устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="77982-161">Insert new history records that include additional details that may be useful for troubleshooting.</span></span>|  
  
 <span data-ttu-id="77982-162">**-LoginTimeOut** _время_ожидания_входа_в_секундах_</span><span class="sxs-lookup"><span data-stu-id="77982-162">**-LoginTimeOut** _login_time_out_seconds_</span></span>  
 <span data-ttu-id="77982-163">Время ожидания входа в секундах. Значение по умолчанию составляет 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="77982-163">Is the number of seconds before the login times out. The default is 15 seconds.</span></span>  
  
 <span data-ttu-id="77982-164">**-Output** _путь_и_имя_выходного_файла_</span><span class="sxs-lookup"><span data-stu-id="77982-164">**-Output** _output_path_and_file_name_</span></span>  
 <span data-ttu-id="77982-165">Путь к выходному файлу агента.</span><span class="sxs-lookup"><span data-stu-id="77982-165">Is the path of the agent output file.</span></span> <span data-ttu-id="77982-166">Если имя файла не указано, данные выводятся на консоль.</span><span class="sxs-lookup"><span data-stu-id="77982-166">If the file name is not provided, the output is sent to the console.</span></span> <span data-ttu-id="77982-167">Если указанный файл существует, то выходные данные добавляются в конец файла.</span><span class="sxs-lookup"><span data-stu-id="77982-167">If the specified file name exists, the output is appended to the file.</span></span>  
  
 <span data-ttu-id="77982-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span><span class="sxs-lookup"><span data-stu-id="77982-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span></span>  
 <span data-ttu-id="77982-169">Указывает, должны ли выводимые данные быть подробными.</span><span class="sxs-lookup"><span data-stu-id="77982-169">Specifies whether the output should be verbose.</span></span> <span data-ttu-id="77982-170">Если уровень подробностей равен **0**, выводятся только сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="77982-170">If the verbose level is **0**, only error messages are printed.</span></span> <span data-ttu-id="77982-171">Если уровень подробностей равен **1**, выводятся все сообщения отчета о состоянии.</span><span class="sxs-lookup"><span data-stu-id="77982-171">If the verbose level is **1**, all the progress report messages are printed.</span></span> <span data-ttu-id="77982-172">Если уровень подробностей равен **2** (по умолчанию), выводятся и сообщения об ошибках, и сообщения отчета о состоянии, что удобно для отладки.</span><span class="sxs-lookup"><span data-stu-id="77982-172">If the verbose level is **2** (default), all error messages and progress report messages are printed, which is useful for debugging.</span></span>  
  
 <span data-ttu-id="77982-173">**-PollingInterval** _интервал_опроса_</span><span class="sxs-lookup"><span data-stu-id="77982-173">**-PollingInterval** _polling_interval_</span></span>  
 <span data-ttu-id="77982-174">Относится только к обновлению подписок, использующих очереди на основе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77982-174">Is relevant only for updating subscriptions that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] based queues.</span></span> <span data-ttu-id="77982-175">Указывает частоту (в секундах) опроса очереди [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на наличие незавершенных транзакций.</span><span class="sxs-lookup"><span data-stu-id="77982-175">Specifies how often, in seconds, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue is polled for pending queued transactions.</span></span> <span data-ttu-id="77982-176">Значение может находиться в диапазоне от 0 до 240 секунд.</span><span class="sxs-lookup"><span data-stu-id="77982-176">The value can be between 0 and 240 seconds.</span></span> <span data-ttu-id="77982-177">Значение по умолчанию — 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="77982-177">The default is 5 seconds.</span></span>  
  
 <span data-ttu-id="77982-178">**-PublisherFailoverPartner** _имя_сервера_[ **\\** _имя_экземпляра_]</span><span class="sxs-lookup"><span data-stu-id="77982-178">**-PublisherFailoverPartner** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="77982-179">Указывает партнера по обеспечению отработки отказа служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , участвующего в сеансе зеркального отображения базы данных с базой данных публикации.</span><span class="sxs-lookup"><span data-stu-id="77982-179">Specifies the failover partner instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participating in a database mirroring session with the publication database.</span></span> <span data-ttu-id="77982-180">Дополнительные сведения см. в статье [Зеркальное отображение и репликация баз данных (SQL Server)](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="77982-180">For more information, see [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="77982-181">**-ProfileName** _имя_профиля_агента_</span><span class="sxs-lookup"><span data-stu-id="77982-181">**-ProfileName** _agent_profile_name_</span></span>  
 <span data-ttu-id="77982-182">Имя профиля агента, используемого для предоставления агенту набора значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77982-182">Is the name of an agent profile used to supply a set of default values to the agent.</span></span> <span data-ttu-id="77982-183">Дополнительные сведения см. в статье [Профили агента репликации](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="77982-183">For information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="77982-184">**-QueryTimeOut** _время_ожидания_запроса_в_секундах_</span><span class="sxs-lookup"><span data-stu-id="77982-184">**-QueryTimeOut** _query_time_out_seconds_</span></span>  
 <span data-ttu-id="77982-185">Время ожидания запроса в секундах. Значение по умолчанию — 1800 секунд.</span><span class="sxs-lookup"><span data-stu-id="77982-185">Is the number of seconds before the query times out. The default is 1800 seconds.</span></span>  
  
 <span data-ttu-id="77982-186">**-ResolverState** [ **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="77982-186">**-ResolverState** [ **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="77982-187">Определяет, каким образом разрешаются конфликты обновления посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="77982-187">Specifies how queued updating conflicts are resolved.</span></span> <span data-ttu-id="77982-188">Значение **1** указывает, что конфликт разрешается в пользу издателя, то есть на издателе и на подписчике будет произведен откат участвующей в конфликте текущей транзакции из очереди, а обработка последующих транзакций из очереди будет продолжена.</span><span class="sxs-lookup"><span data-stu-id="77982-188">A value of **1** indicates the Publisher wins the conflict, and the current conflicting queued transaction will be rolled back on the Publisher and the originating updating Subscriber; the processing of subsequent queued transactions will continue.</span></span> <span data-ttu-id="77982-189">Значение **2** указывает, что конфликт разрешается в пользу подписчика, то есть транзакция, находящаяся в очереди, переопределяет значения на издателе.</span><span class="sxs-lookup"><span data-stu-id="77982-189">A value of **2** indicates the Subscriber wins the conflict, and the queued transaction will override the values on the Publisher.</span></span> <span data-ttu-id="77982-190">Значение **3** указывает, что результатом любого конфликта будет повторная инициализация подписчика, то есть конфликт разрешается в пользу издателя и обработка последующих транзакций из очереди будет прекращена с повторной инициализации подписки.</span><span class="sxs-lookup"><span data-stu-id="77982-190">A value of **3** indicates that any conflict will result in Subscriber re-initialization; the Publisher wins the conflict, processing of subsequent queued transactions will be terminated, and the subscription will be reinitialized.</span></span> <span data-ttu-id="77982-191">Для публикаций транзакций значение по умолчанию равно **1** , а для публикаций моментальных снимков — **3** .</span><span class="sxs-lookup"><span data-stu-id="77982-191">The default setting is **1** for transactional publications and **3** for snapshot publications.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77982-192">Remarks</span><span class="sxs-lookup"><span data-stu-id="77982-192">Remarks</span></span>  
 <span data-ttu-id="77982-193">Для запуска агента чтения очереди выполните из командной строки файл **qrdrsvc.exe** .</span><span class="sxs-lookup"><span data-stu-id="77982-193">To start the Queue Reader Agent, execute **qrdrsvc.exe** from the command prompt.</span></span> <span data-ttu-id="77982-194">Дополнительные сведения см. в разделе [Исполняемые объекты агента репликации](../concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="77982-194">For information, see [Replication Agent Executables](../concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77982-195">См. также:</span><span class="sxs-lookup"><span data-stu-id="77982-195">See Also</span></span>  
 [<span data-ttu-id="77982-196">Администрирование агента репликации</span><span class="sxs-lookup"><span data-stu-id="77982-196">Replication Agent Administration</span></span>](replication-agent-administration.md)  
  
  
