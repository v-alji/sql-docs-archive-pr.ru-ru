---
title: 'Класс событий TM: Rollback Tran Starting | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- 'TM: Rollback Tran Starting event class'
ms.assetid: 3b4d0d56-c51f-4f07-a116-5d4bd6ec1a3c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0492c7df719b9c6177c947d9848c95fc151ac093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728294"
---
# <a name="tm-rollback-tran-starting-event-class"></a><span data-ttu-id="9597e-102">Класс событий TM: Rollback Tran Starting</span><span class="sxs-lookup"><span data-stu-id="9597e-102">TM: Rollback Tran Starting Event Class</span></span>
  <span data-ttu-id="9597e-103">Класс событий "TM:Rollback Tran Starting" указывает на начало выполнения запроса ROLLBACK TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="9597e-103">The TM: Rollback Tran Starting event class indicates that a ROLLBACK TRANSACTION request is starting.</span></span> <span data-ttu-id="9597e-104">Клиент направляет этот запрос через интерфейс управления транзакциями.</span><span class="sxs-lookup"><span data-stu-id="9597e-104">The client sends the request through the transaction management interface.</span></span> <span data-ttu-id="9597e-105">Столбец EventSubClass указывает, будет ли начата новая транзакция после отката текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="9597e-105">The EventSubClass column indicates if a new transaction will be started after the current transaction is rolled back.</span></span>  
  
## <a name="tm-rollback-tran-starting-event-class-data-columns"></a><span data-ttu-id="9597e-106">Столбцы данных класса событий TM: Rollback Tran Starting</span><span class="sxs-lookup"><span data-stu-id="9597e-106">TM: Rollback Tran Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="9597e-107">Имя столбца данных</span><span class="sxs-lookup"><span data-stu-id="9597e-107">Data column name</span></span>|<span data-ttu-id="9597e-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9597e-108">Data type</span></span>|<span data-ttu-id="9597e-109">Description</span><span class="sxs-lookup"><span data-stu-id="9597e-109">Description</span></span>|<span data-ttu-id="9597e-110">Идентификатор столбца</span><span class="sxs-lookup"><span data-stu-id="9597e-110">Column ID</span></span>|<span data-ttu-id="9597e-111">Фильтруемый</span><span class="sxs-lookup"><span data-stu-id="9597e-111">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="9597e-112">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="9597e-112">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="9597e-113">Имя клиентского приложения, установившего соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9597e-113">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9597e-114">Этот столбец заполняется значениями, передаваемыми приложением, а не отображаемым именем программы.</span><span class="sxs-lookup"><span data-stu-id="9597e-114">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="9597e-115">10</span><span class="sxs-lookup"><span data-stu-id="9597e-115">10</span></span>|<span data-ttu-id="9597e-116">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-116">Yes</span></span>|  
|<span data-ttu-id="9597e-117">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="9597e-117">ClientProcessID</span></span>|`int`|<span data-ttu-id="9597e-118">Идентификатор, присвоенный главным компьютером сервера процессу, в котором работает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="9597e-118">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="9597e-119">Этот столбец данных заполняется в том случае, если клиент вводит идентификатор клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="9597e-119">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="9597e-120">9</span><span class="sxs-lookup"><span data-stu-id="9597e-120">9</span></span>|<span data-ttu-id="9597e-121">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-121">Yes</span></span>|  
|<span data-ttu-id="9597e-122">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="9597e-122">DatabaseID</span></span>|`int`|<span data-ttu-id="9597e-123">Идентификатор базы данных, указанной в инструкции USE *database* , или базы данных по умолчанию, если для данного экземпляра инструкция USE *database* не выполнялась.</span><span class="sxs-lookup"><span data-stu-id="9597e-123">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="9597e-124">отображает имя базы данных, если столбец данных ServerName захвачен при трассировке и сервер доступен.</span><span class="sxs-lookup"><span data-stu-id="9597e-124">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="9597e-125">Определите значение для базы данных, используя функцию DB_ID.</span><span class="sxs-lookup"><span data-stu-id="9597e-125">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="9597e-126">3</span><span class="sxs-lookup"><span data-stu-id="9597e-126">3</span></span>|<span data-ttu-id="9597e-127">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-127">Yes</span></span>|  
|<span data-ttu-id="9597e-128">имя_базы_данных</span><span class="sxs-lookup"><span data-stu-id="9597e-128">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="9597e-129">Имя базы данных, в которой выполняется пользовательская инструкция.</span><span class="sxs-lookup"><span data-stu-id="9597e-129">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="9597e-130">35</span><span class="sxs-lookup"><span data-stu-id="9597e-130">35</span></span>|<span data-ttu-id="9597e-131">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-131">Yes</span></span>|  
|<span data-ttu-id="9597e-132">EventClass</span><span class="sxs-lookup"><span data-stu-id="9597e-132">EventClass</span></span>|`int`|<span data-ttu-id="9597e-133">Тип события = 187.</span><span class="sxs-lookup"><span data-stu-id="9597e-133">Type of event = 187.</span></span>|<span data-ttu-id="9597e-134">27</span><span class="sxs-lookup"><span data-stu-id="9597e-134">27</span></span>|<span data-ttu-id="9597e-135">Нет</span><span class="sxs-lookup"><span data-stu-id="9597e-135">No</span></span>|  
|<span data-ttu-id="9597e-136">EventSequence</span><span class="sxs-lookup"><span data-stu-id="9597e-136">EventSequence</span></span>|`int`|<span data-ttu-id="9597e-137">Порядковый номер данного события в запросе.</span><span class="sxs-lookup"><span data-stu-id="9597e-137">The sequence of a given event within the request.</span></span>|<span data-ttu-id="9597e-138">51</span><span class="sxs-lookup"><span data-stu-id="9597e-138">51</span></span>|<span data-ttu-id="9597e-139">Нет</span><span class="sxs-lookup"><span data-stu-id="9597e-139">No</span></span>|  
|<span data-ttu-id="9597e-140">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="9597e-140">EventSubClass</span></span>|`int`|<span data-ttu-id="9597e-141">Тип подкласса события.</span><span class="sxs-lookup"><span data-stu-id="9597e-141">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="9597e-142">1 = откат;</span><span class="sxs-lookup"><span data-stu-id="9597e-142">1=Rollback</span></span><br /><br /> <span data-ttu-id="9597e-143">2 = откат и начало.</span><span class="sxs-lookup"><span data-stu-id="9597e-143">2=Rollback and Begin</span></span>|<span data-ttu-id="9597e-144">21</span><span class="sxs-lookup"><span data-stu-id="9597e-144">21</span></span>|<span data-ttu-id="9597e-145">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-145">Yes</span></span>|  
|<span data-ttu-id="9597e-146">GroupID</span><span class="sxs-lookup"><span data-stu-id="9597e-146">GroupID</span></span>|`int`|<span data-ttu-id="9597e-147">Идентификатор группы рабочей нагрузки, в которой запускается событие трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="9597e-147">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="9597e-148">66</span><span class="sxs-lookup"><span data-stu-id="9597e-148">66</span></span>|<span data-ttu-id="9597e-149">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-149">Yes</span></span>|  
|<span data-ttu-id="9597e-150">HostName</span><span class="sxs-lookup"><span data-stu-id="9597e-150">HostName</span></span>|`nvarchar`|<span data-ttu-id="9597e-151">Имя компьютера, на котором выполняется клиентская программа.</span><span class="sxs-lookup"><span data-stu-id="9597e-151">Name of the computer on which the client is running.</span></span> <span data-ttu-id="9597e-152">Этот столбец данных заполняется, если клиент предоставляет имя узла.</span><span class="sxs-lookup"><span data-stu-id="9597e-152">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="9597e-153">Чтобы определить имя узла, используйте функцию HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="9597e-153">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="9597e-154">8</span><span class="sxs-lookup"><span data-stu-id="9597e-154">8</span></span>|<span data-ttu-id="9597e-155">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-155">Yes</span></span>|  
|<span data-ttu-id="9597e-156">IsSystem</span><span class="sxs-lookup"><span data-stu-id="9597e-156">IsSystem</span></span>|`int`|<span data-ttu-id="9597e-157">Указывает, произошло событие в системном или в пользовательском процессе.</span><span class="sxs-lookup"><span data-stu-id="9597e-157">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="9597e-158">1 = системный, 0 = пользовательский.</span><span class="sxs-lookup"><span data-stu-id="9597e-158">1 = system, 0 = user.</span></span>|<span data-ttu-id="9597e-159">60</span><span class="sxs-lookup"><span data-stu-id="9597e-159">60</span></span>|<span data-ttu-id="9597e-160">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-160">Yes</span></span>|  
|<span data-ttu-id="9597e-161">LoginName</span><span class="sxs-lookup"><span data-stu-id="9597e-161">LoginName</span></span>|`nvarchar`|<span data-ttu-id="9597e-162">Имя входа пользователя (либо защищенное имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , либо учетные данные входа [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows в формате «ДОМЕН\имя_пользователя»).</span><span class="sxs-lookup"><span data-stu-id="9597e-162">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="9597e-163">11</span><span class="sxs-lookup"><span data-stu-id="9597e-163">11</span></span>|<span data-ttu-id="9597e-164">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-164">Yes</span></span>|  
|<span data-ttu-id="9597e-165">LoginSid</span><span class="sxs-lookup"><span data-stu-id="9597e-165">LoginSid</span></span>|`image`|<span data-ttu-id="9597e-166">Идентификатор безопасности вошедшего в систему пользователя.</span><span class="sxs-lookup"><span data-stu-id="9597e-166">Security identifier (SID) of the logged-in user.</span></span> <span data-ttu-id="9597e-167">Эти сведения можно найти в представлении каталога sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="9597e-167">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="9597e-168">Значение идентификатора безопасности уникально для каждого имени входа на сервере.</span><span class="sxs-lookup"><span data-stu-id="9597e-168">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="9597e-169">41</span><span class="sxs-lookup"><span data-stu-id="9597e-169">41</span></span>|<span data-ttu-id="9597e-170">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-170">Yes</span></span>|  
|<span data-ttu-id="9597e-171">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="9597e-171">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="9597e-172">Домен Windows, к которому принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="9597e-172">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="9597e-173">7</span><span class="sxs-lookup"><span data-stu-id="9597e-173">7</span></span>|<span data-ttu-id="9597e-174">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-174">Yes</span></span>|  
|<span data-ttu-id="9597e-175">NTUserName</span><span class="sxs-lookup"><span data-stu-id="9597e-175">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="9597e-176">Имя пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="9597e-176">Windows user name.</span></span>|<span data-ttu-id="9597e-177">6</span><span class="sxs-lookup"><span data-stu-id="9597e-177">6</span></span>|<span data-ttu-id="9597e-178">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-178">Yes</span></span>|  
|<span data-ttu-id="9597e-179">RequestID</span><span class="sxs-lookup"><span data-stu-id="9597e-179">RequestID</span></span>|`int`|<span data-ttu-id="9597e-180">Идентификатор запроса, содержащего инструкцию.</span><span class="sxs-lookup"><span data-stu-id="9597e-180">ID of the request containing the statement.</span></span>|<span data-ttu-id="9597e-181">49</span><span class="sxs-lookup"><span data-stu-id="9597e-181">49</span></span>|<span data-ttu-id="9597e-182">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-182">Yes</span></span>|  
|<span data-ttu-id="9597e-183">ServerName</span><span class="sxs-lookup"><span data-stu-id="9597e-183">ServerName</span></span>|`nvarchar`|<span data-ttu-id="9597e-184">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого производится трассировка.</span><span class="sxs-lookup"><span data-stu-id="9597e-184">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="9597e-185">26</span><span class="sxs-lookup"><span data-stu-id="9597e-185">26</span></span>|<span data-ttu-id="9597e-186">Нет</span><span class="sxs-lookup"><span data-stu-id="9597e-186">No</span></span>|  
|<span data-ttu-id="9597e-187">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="9597e-187">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="9597e-188">Имя входа пользователя, создавшего этот сеанс.</span><span class="sxs-lookup"><span data-stu-id="9597e-188">Login name of the user who originated the session.</span></span> <span data-ttu-id="9597e-189">Например, при соединении с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] под именем Login1 и при выполнении инструкции под именем Login2 SessionLoginName будет содержать значение Login1, а LoginName — значение Login2.</span><span class="sxs-lookup"><span data-stu-id="9597e-189">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="9597e-190">В этом столбце отображаются как имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и имена входа Windows.</span><span class="sxs-lookup"><span data-stu-id="9597e-190">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="9597e-191">64</span><span class="sxs-lookup"><span data-stu-id="9597e-191">64</span></span>|<span data-ttu-id="9597e-192">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-192">Yes</span></span>|  
|<span data-ttu-id="9597e-193">SPID</span><span class="sxs-lookup"><span data-stu-id="9597e-193">SPID</span></span>|`int`|<span data-ttu-id="9597e-194">Идентификатор сеанса, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="9597e-194">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="9597e-195">12</span><span class="sxs-lookup"><span data-stu-id="9597e-195">12</span></span>|<span data-ttu-id="9597e-196">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-196">Yes</span></span>|  
|<span data-ttu-id="9597e-197">StartTime</span><span class="sxs-lookup"><span data-stu-id="9597e-197">StartTime</span></span>|`datetime`|<span data-ttu-id="9597e-198">Время начала события, если оно известно.</span><span class="sxs-lookup"><span data-stu-id="9597e-198">Time at which the event started, if available.</span></span>|<span data-ttu-id="9597e-199">14</span><span class="sxs-lookup"><span data-stu-id="9597e-199">14</span></span>|<span data-ttu-id="9597e-200">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-200">Yes</span></span>|  
|<span data-ttu-id="9597e-201">TextData</span><span class="sxs-lookup"><span data-stu-id="9597e-201">TextData</span></span>|`ntext`|<span data-ttu-id="9597e-202">Текстовое значение, зависящее от класса событий, фиксируемых при трассировке.</span><span class="sxs-lookup"><span data-stu-id="9597e-202">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="9597e-203">1</span><span class="sxs-lookup"><span data-stu-id="9597e-203">1</span></span>|<span data-ttu-id="9597e-204">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-204">Yes</span></span>|  
|<span data-ttu-id="9597e-205">TransactionID</span><span class="sxs-lookup"><span data-stu-id="9597e-205">TransactionID</span></span>|`bigint`|<span data-ttu-id="9597e-206">Назначенный системой идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="9597e-206">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="9597e-207">4</span><span class="sxs-lookup"><span data-stu-id="9597e-207">4</span></span>|<span data-ttu-id="9597e-208">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-208">Yes</span></span>|  
|<span data-ttu-id="9597e-209">XactSequence</span><span class="sxs-lookup"><span data-stu-id="9597e-209">XactSequence</span></span>|`bigint`|<span data-ttu-id="9597e-210">Токен, который описывает текущую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9597e-210">Token that describes the current transaction.</span></span>|<span data-ttu-id="9597e-211">50</span><span class="sxs-lookup"><span data-stu-id="9597e-211">50</span></span>|<span data-ttu-id="9597e-212">Да</span><span class="sxs-lookup"><span data-stu-id="9597e-212">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9597e-213">См. также:</span><span class="sxs-lookup"><span data-stu-id="9597e-213">See Also</span></span>  
 <span data-ttu-id="9597e-214">[ROLLBACK TRANSACTION &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/rollback-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9597e-214">[ROLLBACK TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/rollback-transaction-transact-sql) </span></span>  
 [<span data-ttu-id="9597e-215">Хранимая процедура sp_trace_setevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9597e-215">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  