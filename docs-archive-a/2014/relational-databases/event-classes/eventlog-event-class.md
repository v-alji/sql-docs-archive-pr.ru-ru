---
title: Класс событий EventLog | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- EventLog event class
ms.assetid: ba4b4e15-b923-4fab-987e-6bede2e73f53
author: stevestein
ms.author: sstein
ms.openlocfilehash: 74a6db063168cf0eb444a2ee442ff44e3b09958b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735230"
---
# <a name="eventlog-event-class"></a><span data-ttu-id="d8163-102">Класс событий EventLog</span><span class="sxs-lookup"><span data-stu-id="d8163-102">EventLog Event Class</span></span>
  <span data-ttu-id="d8163-103">Класс событий EventLog указывает, что события регистрируются в журнале событий [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="d8163-103">The EventLogevent class indicates that events have been logged in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows event log.</span></span>  
  
## <a name="eventlog-event-class-data-columns"></a><span data-ttu-id="d8163-104">Столбцы данных класса событий EventLog</span><span class="sxs-lookup"><span data-stu-id="d8163-104">EventLog Event Class Data Columns</span></span>  
  
|<span data-ttu-id="d8163-105">Имя столбца данных</span><span class="sxs-lookup"><span data-stu-id="d8163-105">Data column name</span></span>|<span data-ttu-id="d8163-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d8163-106">Data type</span></span>|<span data-ttu-id="d8163-107">Description</span><span class="sxs-lookup"><span data-stu-id="d8163-107">Description</span></span>|<span data-ttu-id="d8163-108">Идентификатор столбца</span><span class="sxs-lookup"><span data-stu-id="d8163-108">Column ID</span></span>|<span data-ttu-id="d8163-109">Фильтруемый</span><span class="sxs-lookup"><span data-stu-id="d8163-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="d8163-110">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d8163-110">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="d8163-111">Имя клиентского приложения, установившего соединение с экземпляром [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8163-111">Name of the client application that created the connection to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d8163-112">Этот столбец заполняется значениями, передаваемыми приложением, а не отображаемым именем программы.</span><span class="sxs-lookup"><span data-stu-id="d8163-112">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="d8163-113">10</span><span class="sxs-lookup"><span data-stu-id="d8163-113">10</span></span>|<span data-ttu-id="d8163-114">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-114">Yes</span></span>|  
|<span data-ttu-id="d8163-115">BinaryData</span><span class="sxs-lookup"><span data-stu-id="d8163-115">BinaryData</span></span>|`image`|<span data-ttu-id="d8163-116">Значение типа Binary, зависящее от класса событий, фиксируемых при трассировке.</span><span class="sxs-lookup"><span data-stu-id="d8163-116">Binary value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="d8163-117">2</span><span class="sxs-lookup"><span data-stu-id="d8163-117">2</span></span>|<span data-ttu-id="d8163-118">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-118">Yes</span></span>|  
|<span data-ttu-id="d8163-119">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="d8163-119">ClientProcessID</span></span>|`int`|<span data-ttu-id="d8163-120">Идентификатор, присвоенный главным компьютером сервера процессу, в котором работает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="d8163-120">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="d8163-121">Этот столбец данных заполняется в том случае, если клиент предоставляет идентификатор клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="d8163-121">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="d8163-122">9</span><span class="sxs-lookup"><span data-stu-id="d8163-122">9</span></span>|<span data-ttu-id="d8163-123">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-123">Yes</span></span>|  
|<span data-ttu-id="d8163-124">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="d8163-124">DatabaseID</span></span>|`int`|<span data-ttu-id="d8163-125">Идентификатор базы данных, указанной в инструкции USE *database* , или базы данных по умолчанию, если для данного экземпляра инструкция USE *database* не выполнялась.</span><span class="sxs-lookup"><span data-stu-id="d8163-125">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="d8163-126">отображает имя базы данных, если столбец данных ServerName захвачен при трассировке и сервер доступен.</span><span class="sxs-lookup"><span data-stu-id="d8163-126">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="d8163-127">Определите значение для базы данных, используя функцию DB_ID.</span><span class="sxs-lookup"><span data-stu-id="d8163-127">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="d8163-128">3</span><span class="sxs-lookup"><span data-stu-id="d8163-128">3</span></span>|<span data-ttu-id="d8163-129">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-129">Yes</span></span>|  
|<span data-ttu-id="d8163-130">имя_базы_данных</span><span class="sxs-lookup"><span data-stu-id="d8163-130">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="d8163-131">Имя базы данных, в которой выполняется пользовательская инструкция.</span><span class="sxs-lookup"><span data-stu-id="d8163-131">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="d8163-132">35</span><span class="sxs-lookup"><span data-stu-id="d8163-132">35</span></span>|<span data-ttu-id="d8163-133">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-133">Yes</span></span>|  
|<span data-ttu-id="d8163-134">Error</span><span class="sxs-lookup"><span data-stu-id="d8163-134">Error</span></span>|`int`|<span data-ttu-id="d8163-135">Номер ошибки данного события, если он известен.</span><span class="sxs-lookup"><span data-stu-id="d8163-135">Error number of a given event, if available.</span></span>|<span data-ttu-id="d8163-136">31</span><span class="sxs-lookup"><span data-stu-id="d8163-136">31</span></span>|<span data-ttu-id="d8163-137">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-137">Yes</span></span>|  
|<span data-ttu-id="d8163-138">EventClass</span><span class="sxs-lookup"><span data-stu-id="d8163-138">EventClass</span></span>|`int`|<span data-ttu-id="d8163-139">Тип события = 21.</span><span class="sxs-lookup"><span data-stu-id="d8163-139">Type of event = 21.</span></span>|<span data-ttu-id="d8163-140">27</span><span class="sxs-lookup"><span data-stu-id="d8163-140">27</span></span>|<span data-ttu-id="d8163-141">Нет</span><span class="sxs-lookup"><span data-stu-id="d8163-141">No</span></span>|  
|<span data-ttu-id="d8163-142">EventSequence</span><span class="sxs-lookup"><span data-stu-id="d8163-142">EventSequence</span></span>|`int`|<span data-ttu-id="d8163-143">Последовательность данного события в запросе.</span><span class="sxs-lookup"><span data-stu-id="d8163-143">Sequence of a given event within the request.</span></span>|<span data-ttu-id="d8163-144">51</span><span class="sxs-lookup"><span data-stu-id="d8163-144">51</span></span>|<span data-ttu-id="d8163-145">Нет</span><span class="sxs-lookup"><span data-stu-id="d8163-145">No</span></span>|  
|<span data-ttu-id="d8163-146">HostName</span><span class="sxs-lookup"><span data-stu-id="d8163-146">HostName</span></span>|`nvarchar`|<span data-ttu-id="d8163-147">Имя компьютера, на котором выполняется клиентская программа.</span><span class="sxs-lookup"><span data-stu-id="d8163-147">Name of the computer on which the client is running.</span></span> <span data-ttu-id="d8163-148">Этот столбец данных заполняется, если клиент предоставляет имя узла.</span><span class="sxs-lookup"><span data-stu-id="d8163-148">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="d8163-149">Чтобы определить имя узла, используйте функцию HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="d8163-149">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="d8163-150">8</span><span class="sxs-lookup"><span data-stu-id="d8163-150">8</span></span>|<span data-ttu-id="d8163-151">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-151">Yes</span></span>|  
|<span data-ttu-id="d8163-152">IsSystem</span><span class="sxs-lookup"><span data-stu-id="d8163-152">IsSystem</span></span>|`int`|<span data-ttu-id="d8163-153">Указывает, произошло событие в системном или в пользовательском процессе.</span><span class="sxs-lookup"><span data-stu-id="d8163-153">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="d8163-154">1 = системный, 0 = пользовательский.</span><span class="sxs-lookup"><span data-stu-id="d8163-154">1 = system, 0 = user.</span></span>|<span data-ttu-id="d8163-155">60</span><span class="sxs-lookup"><span data-stu-id="d8163-155">60</span></span>|<span data-ttu-id="d8163-156">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-156">Yes</span></span>|  
|<span data-ttu-id="d8163-157">LoginName</span><span class="sxs-lookup"><span data-stu-id="d8163-157">LoginName</span></span>|`nvarchar`|<span data-ttu-id="d8163-158">Имя входа пользователя (либо защищенное имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , либо учетные данные входа Windows в формате домен\имя_пользователя).</span><span class="sxs-lookup"><span data-stu-id="d8163-158">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="d8163-159">11</span><span class="sxs-lookup"><span data-stu-id="d8163-159">11</span></span>|<span data-ttu-id="d8163-160">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-160">Yes</span></span>|  
|<span data-ttu-id="d8163-161">LoginSid</span><span class="sxs-lookup"><span data-stu-id="d8163-161">LoginSid</span></span>|`image`|<span data-ttu-id="d8163-162">Идентификатор безопасности вошедшего в систему пользователя.</span><span class="sxs-lookup"><span data-stu-id="d8163-162">Security identifier (SID) of the logged-in user.</span></span> <span data-ttu-id="d8163-163">Эти сведения можно найти в представлении каталога sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="d8163-163">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="d8163-164">Значение идентификатора безопасности уникально для каждого имени входа на сервере.</span><span class="sxs-lookup"><span data-stu-id="d8163-164">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="d8163-165">41</span><span class="sxs-lookup"><span data-stu-id="d8163-165">41</span></span>|<span data-ttu-id="d8163-166">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-166">Yes</span></span>|  
|<span data-ttu-id="d8163-167">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="d8163-167">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="d8163-168">Домен Windows, к которому принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="d8163-168">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="d8163-169">7</span><span class="sxs-lookup"><span data-stu-id="d8163-169">7</span></span>|<span data-ttu-id="d8163-170">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-170">Yes</span></span>|  
|<span data-ttu-id="d8163-171">NTUserName</span><span class="sxs-lookup"><span data-stu-id="d8163-171">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="d8163-172">Имя пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="d8163-172">Windows user name.</span></span>|<span data-ttu-id="d8163-173">6</span><span class="sxs-lookup"><span data-stu-id="d8163-173">6</span></span>|<span data-ttu-id="d8163-174">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-174">Yes</span></span>|  
|<span data-ttu-id="d8163-175">RequestID</span><span class="sxs-lookup"><span data-stu-id="d8163-175">RequestID</span></span>|`int`|<span data-ttu-id="d8163-176">Идентификатор запроса, содержащего инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d8163-176">ID of the request containing the statement.</span></span>|<span data-ttu-id="d8163-177">49</span><span class="sxs-lookup"><span data-stu-id="d8163-177">49</span></span>|<span data-ttu-id="d8163-178">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-178">Yes</span></span>|  
|<span data-ttu-id="d8163-179">ServerName</span><span class="sxs-lookup"><span data-stu-id="d8163-179">ServerName</span></span>|`nvarchar`|<span data-ttu-id="d8163-180">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого производится трассировка.</span><span class="sxs-lookup"><span data-stu-id="d8163-180">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="d8163-181">26</span><span class="sxs-lookup"><span data-stu-id="d8163-181">26</span></span>|<span data-ttu-id="d8163-182">Нет</span><span class="sxs-lookup"><span data-stu-id="d8163-182">No</span></span>|  
|<span data-ttu-id="d8163-183">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="d8163-183">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="d8163-184">Имя входа пользователя, создавшего этот сеанс.</span><span class="sxs-lookup"><span data-stu-id="d8163-184">Login name of the user who originated the session.</span></span> <span data-ttu-id="d8163-185">Например, при соединении с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] под именем Login1 и при выполнении инструкции под именем Login2 SessionLoginName будет содержать значение Login1, а LoginName — значение Login2.</span><span class="sxs-lookup"><span data-stu-id="d8163-185">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="d8163-186">В этом столбце отображаются как имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и имена входа Windows.</span><span class="sxs-lookup"><span data-stu-id="d8163-186">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="d8163-187">64</span><span class="sxs-lookup"><span data-stu-id="d8163-187">64</span></span>|<span data-ttu-id="d8163-188">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-188">Yes</span></span>|  
|<span data-ttu-id="d8163-189">Уровень серьезности</span><span class="sxs-lookup"><span data-stu-id="d8163-189">Severity</span></span>|`int`|<span data-ttu-id="d8163-190">Степень серьезности исключения.</span><span class="sxs-lookup"><span data-stu-id="d8163-190">Severity level of an exception.</span></span>|<span data-ttu-id="d8163-191">20</span><span class="sxs-lookup"><span data-stu-id="d8163-191">20</span></span>|<span data-ttu-id="d8163-192">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-192">Yes</span></span>|  
|<span data-ttu-id="d8163-193">SPID</span><span class="sxs-lookup"><span data-stu-id="d8163-193">SPID</span></span>|`int`|<span data-ttu-id="d8163-194">Идентификатор сеанса, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="d8163-194">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="d8163-195">12</span><span class="sxs-lookup"><span data-stu-id="d8163-195">12</span></span>|<span data-ttu-id="d8163-196">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-196">Yes</span></span>|  
|<span data-ttu-id="d8163-197">StartTime</span><span class="sxs-lookup"><span data-stu-id="d8163-197">StartTime</span></span>|`datetime`|<span data-ttu-id="d8163-198">Время начала события, если оно известно.</span><span class="sxs-lookup"><span data-stu-id="d8163-198">Time at which the event started, if available.</span></span>|<span data-ttu-id="d8163-199">14</span><span class="sxs-lookup"><span data-stu-id="d8163-199">14</span></span>|<span data-ttu-id="d8163-200">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-200">Yes</span></span>|  
|<span data-ttu-id="d8163-201">TextData</span><span class="sxs-lookup"><span data-stu-id="d8163-201">TextData</span></span>|`ntext`|<span data-ttu-id="d8163-202">Текст сообщения об ошибке, если он известен.</span><span class="sxs-lookup"><span data-stu-id="d8163-202">Text of the error message, if available.</span></span>|<span data-ttu-id="d8163-203">1</span><span class="sxs-lookup"><span data-stu-id="d8163-203">1</span></span>|<span data-ttu-id="d8163-204">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-204">Yes</span></span>|  
|<span data-ttu-id="d8163-205">TransactionID</span><span class="sxs-lookup"><span data-stu-id="d8163-205">TransactionID</span></span>|`bigint`|<span data-ttu-id="d8163-206">Назначенный системой идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="d8163-206">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="d8163-207">4</span><span class="sxs-lookup"><span data-stu-id="d8163-207">4</span></span>|<span data-ttu-id="d8163-208">Да</span><span class="sxs-lookup"><span data-stu-id="d8163-208">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8163-209">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8163-209">See Also</span></span>  
 <span data-ttu-id="d8163-210">[Расширенные события](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="d8163-210">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="d8163-211">Хранимая процедура sp_trace_setevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d8163-211">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  