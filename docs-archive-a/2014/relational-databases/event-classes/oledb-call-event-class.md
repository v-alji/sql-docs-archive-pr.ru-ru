---
title: Класс событий OLEDB Call | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- OLEDB Call event class
ms.assetid: e1be1e90-98cc-47a3-addd-59d4aeca6547
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1a26781a34b75893dfb8aad54cea8e7f6d2c2e4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655762"
---
# <a name="oledb-call-event-class"></a><span data-ttu-id="7e377-102">OLEDB Call, класс событий</span><span class="sxs-lookup"><span data-stu-id="7e377-102">OLEDB Call Event Class</span></span>
  <span data-ttu-id="7e377-103">События класса событий **OLEDB Call** происходят, когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запрашивает распределенные запросы и удаленные хранимые процедуры у поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7e377-103">The **OLEDB Call** event class occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] calls an OLE DB provider for distributed queries and remote stored procedures.</span></span>  
  
 <span data-ttu-id="7e377-104">Включайте класс событий **OLEDB Call** для контроля только за теми запросами, которые не посылают запросы и не запрашивают данные, выполненные методом, отличным от **QueryInterface** .</span><span class="sxs-lookup"><span data-stu-id="7e377-104">Include the **OLEDB Call** event class in traces to monitor only those calls that do not request data or calls that are not made to the **QueryInterface** method.</span></span> <span data-ttu-id="7e377-105">При включении в трассировку класса событий **OLEDB Call** количество сигналов зависит от того, насколько часто во время трассировки происходят запросы к базе данных с помощью технологии OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7e377-105">When the **OLEDB Call** event class is included in a trace the amount of overhead incurred depends on how frequently OLE DB calls occur against the database during the trace.</span></span> <span data-ttu-id="7e377-106">Если такие вызовы происходят часто, трассировка может заметно снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="7e377-106">If calls occur frequently, the trace may significantly impede performance.</span></span>  
  
## <a name="oledb-call-event-class-data-columns"></a><span data-ttu-id="7e377-107">Столбцы данных класса событий OLEDB Call</span><span class="sxs-lookup"><span data-stu-id="7e377-107">OLEDB Call Event Class Data Columns</span></span>  
  
|<span data-ttu-id="7e377-108">Имя столбца данных</span><span class="sxs-lookup"><span data-stu-id="7e377-108">Data column name</span></span>|<span data-ttu-id="7e377-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7e377-109">Data type</span></span>|<span data-ttu-id="7e377-110">Description</span><span class="sxs-lookup"><span data-stu-id="7e377-110">Description</span></span>|<span data-ttu-id="7e377-111">Идентификатор столбца</span><span class="sxs-lookup"><span data-stu-id="7e377-111">Column ID</span></span>|<span data-ttu-id="7e377-112">Фильтруемый</span><span class="sxs-lookup"><span data-stu-id="7e377-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="7e377-113">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="7e377-113">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="7e377-114">Имя клиентского приложения, установившего соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e377-114">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7e377-115">Этот столбец заполняется значениями, передаваемыми приложением, а не отображаемым именем программы.</span><span class="sxs-lookup"><span data-stu-id="7e377-115">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="7e377-116">10</span><span class="sxs-lookup"><span data-stu-id="7e377-116">10</span></span>|<span data-ttu-id="7e377-117">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-117">Yes</span></span>|  
|<span data-ttu-id="7e377-118">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="7e377-118">ClientProcessID</span></span>|`Int`|<span data-ttu-id="7e377-119">Идентификатор, присвоенный главным компьютером сервера процессу, в котором работает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="7e377-119">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="7e377-120">Этот столбец данных заполняется в том случае, если клиент предоставляет идентификатор клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="7e377-120">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="7e377-121">9</span><span class="sxs-lookup"><span data-stu-id="7e377-121">9</span></span>|<span data-ttu-id="7e377-122">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-122">Yes</span></span>|  
|<span data-ttu-id="7e377-123">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="7e377-123">DatabaseID</span></span>|`Int`|<span data-ttu-id="7e377-124">Идентификатор базы данных, указанной в инструкции USE *database* , или базы данных по умолчанию, если для данного экземпляра инструкция USE *database* не выполнялась.</span><span class="sxs-lookup"><span data-stu-id="7e377-124">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="7e377-125">отображает имя базы данных, если столбец данных **ServerName** захвачен при трассировке и сервер доступен.</span><span class="sxs-lookup"><span data-stu-id="7e377-125">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="7e377-126">Определите значение для базы данных, используя функцию DB_ID.</span><span class="sxs-lookup"><span data-stu-id="7e377-126">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="7e377-127">3</span><span class="sxs-lookup"><span data-stu-id="7e377-127">3</span></span>|<span data-ttu-id="7e377-128">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-128">Yes</span></span>|  
|<span data-ttu-id="7e377-129">имя_базы_данных</span><span class="sxs-lookup"><span data-stu-id="7e377-129">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="7e377-130">Имя базы данных, в которой выполняется пользовательская инструкция.</span><span class="sxs-lookup"><span data-stu-id="7e377-130">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="7e377-131">35</span><span class="sxs-lookup"><span data-stu-id="7e377-131">35</span></span>|<span data-ttu-id="7e377-132">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-132">Yes</span></span>|  
|<span data-ttu-id="7e377-133">Duration</span><span class="sxs-lookup"><span data-stu-id="7e377-133">Duration</span></span>|`Bigint`|<span data-ttu-id="7e377-134">Время, необходимое для выполнения события «Вызов OLE DB».</span><span class="sxs-lookup"><span data-stu-id="7e377-134">Length of time to complete the OLE DB Call event.</span></span>|<span data-ttu-id="7e377-135">13</span><span class="sxs-lookup"><span data-stu-id="7e377-135">13</span></span>|<span data-ttu-id="7e377-136">нет</span><span class="sxs-lookup"><span data-stu-id="7e377-136">No</span></span>|  
|<span data-ttu-id="7e377-137">EndTime</span><span class="sxs-lookup"><span data-stu-id="7e377-137">EndTime</span></span>|`Datetime`|<span data-ttu-id="7e377-138">Время окончания события.</span><span class="sxs-lookup"><span data-stu-id="7e377-138">Time that the event ended.</span></span>|<span data-ttu-id="7e377-139">15</span><span class="sxs-lookup"><span data-stu-id="7e377-139">15</span></span>|<span data-ttu-id="7e377-140">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-140">Yes</span></span>|  
|<span data-ttu-id="7e377-141">Error</span><span class="sxs-lookup"><span data-stu-id="7e377-141">Error</span></span>|`int`|<span data-ttu-id="7e377-142">Номер ошибки для данного события.</span><span class="sxs-lookup"><span data-stu-id="7e377-142">Error number of a given event.</span></span> <span data-ttu-id="7e377-143">Часто это номер ошибки, который хранится в представлении каталога sys.messages.</span><span class="sxs-lookup"><span data-stu-id="7e377-143">Often this is the error number stored in the sys.messages catalog view.</span></span>|<span data-ttu-id="7e377-144">31</span><span class="sxs-lookup"><span data-stu-id="7e377-144">31</span></span>|<span data-ttu-id="7e377-145">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-145">Yes</span></span>|  
|<span data-ttu-id="7e377-146">EventClass</span><span class="sxs-lookup"><span data-stu-id="7e377-146">EventClass</span></span>|`Int`|<span data-ttu-id="7e377-147">Тип события = 119.</span><span class="sxs-lookup"><span data-stu-id="7e377-147">Type of event = 119.</span></span>|<span data-ttu-id="7e377-148">27</span><span class="sxs-lookup"><span data-stu-id="7e377-148">27</span></span>|<span data-ttu-id="7e377-149">Нет</span><span class="sxs-lookup"><span data-stu-id="7e377-149">No</span></span>|  
|<span data-ttu-id="7e377-150">EventSequence</span><span class="sxs-lookup"><span data-stu-id="7e377-150">EventSequence</span></span>|`Int`|<span data-ttu-id="7e377-151">Порядковый номер класса событий OLE DB в пакете.</span><span class="sxs-lookup"><span data-stu-id="7e377-151">Sequence of OLE DB event class in batch.</span></span>|<span data-ttu-id="7e377-152">51</span><span class="sxs-lookup"><span data-stu-id="7e377-152">51</span></span>|<span data-ttu-id="7e377-153">Нет</span><span class="sxs-lookup"><span data-stu-id="7e377-153">No</span></span>|  
|<span data-ttu-id="7e377-154">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="7e377-154">EventSubClass</span></span>|`Int`|<span data-ttu-id="7e377-155">0 = начало</span><span class="sxs-lookup"><span data-stu-id="7e377-155">0=Starting</span></span><br /><br /> <span data-ttu-id="7e377-156">1 = завершение</span><span class="sxs-lookup"><span data-stu-id="7e377-156">1=Completed</span></span>|<span data-ttu-id="7e377-157">21</span><span class="sxs-lookup"><span data-stu-id="7e377-157">21</span></span>|<span data-ttu-id="7e377-158">Нет</span><span class="sxs-lookup"><span data-stu-id="7e377-158">No</span></span>|  
|<span data-ttu-id="7e377-159">GroupID</span><span class="sxs-lookup"><span data-stu-id="7e377-159">GroupID</span></span>|`int`|<span data-ttu-id="7e377-160">Идентификатор группы рабочей нагрузки, в которой запускается событие трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="7e377-160">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="7e377-161">66</span><span class="sxs-lookup"><span data-stu-id="7e377-161">66</span></span>|<span data-ttu-id="7e377-162">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-162">Yes</span></span>|  
|<span data-ttu-id="7e377-163">HostName</span><span class="sxs-lookup"><span data-stu-id="7e377-163">HostName</span></span>|`nvarchar`|<span data-ttu-id="7e377-164">Имя компьютера, на котором выполняется клиентская программа.</span><span class="sxs-lookup"><span data-stu-id="7e377-164">Name of the computer on which the client is running.</span></span> <span data-ttu-id="7e377-165">Этот столбец данных заполняется, если клиент предоставляет имя узла.</span><span class="sxs-lookup"><span data-stu-id="7e377-165">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="7e377-166">Чтобы определить имя узла, используйте функцию HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="7e377-166">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="7e377-167">8</span><span class="sxs-lookup"><span data-stu-id="7e377-167">8</span></span>|<span data-ttu-id="7e377-168">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-168">Yes</span></span>|  
|<span data-ttu-id="7e377-169">IsSystem</span><span class="sxs-lookup"><span data-stu-id="7e377-169">IsSystem</span></span>|`int`|<span data-ttu-id="7e377-170">Указывает, произошло событие в системном или в пользовательском процессе.</span><span class="sxs-lookup"><span data-stu-id="7e377-170">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="7e377-171">1 = системный, 0 = пользовательский.</span><span class="sxs-lookup"><span data-stu-id="7e377-171">1 = system, 0 = user.</span></span>|<span data-ttu-id="7e377-172">60</span><span class="sxs-lookup"><span data-stu-id="7e377-172">60</span></span>|<span data-ttu-id="7e377-173">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-173">Yes</span></span>|  
|<span data-ttu-id="7e377-174">LinkedServerName</span><span class="sxs-lookup"><span data-stu-id="7e377-174">LinkedServerName</span></span>|`nvarchar`|<span data-ttu-id="7e377-175">Имя связанного сервера.</span><span class="sxs-lookup"><span data-stu-id="7e377-175">Name of the linked server.</span></span>|<span data-ttu-id="7e377-176">45</span><span class="sxs-lookup"><span data-stu-id="7e377-176">45</span></span>|<span data-ttu-id="7e377-177">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-177">Yes</span></span>|  
|<span data-ttu-id="7e377-178">LoginName</span><span class="sxs-lookup"><span data-stu-id="7e377-178">LoginName</span></span>|`nvarchar`|<span data-ttu-id="7e377-179">Имя входа пользователя (либо защищенное имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , либо учетные данные входа [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows в формате домен\имя_пользователя).</span><span class="sxs-lookup"><span data-stu-id="7e377-179">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\Username).</span></span>|<span data-ttu-id="7e377-180">11</span><span class="sxs-lookup"><span data-stu-id="7e377-180">11</span></span>|<span data-ttu-id="7e377-181">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-181">Yes</span></span>|  
|<span data-ttu-id="7e377-182">LoginSid</span><span class="sxs-lookup"><span data-stu-id="7e377-182">LoginSid</span></span>|`Image`|<span data-ttu-id="7e377-183">Идентификатор безопасности вошедшего в систему пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e377-183">Security identifier (SID) of the logged-in user.</span></span> <span data-ttu-id="7e377-184">Эти сведения можно найти в представлении каталога sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="7e377-184">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="7e377-185">Значение идентификатора безопасности уникально для каждого имени входа на сервере.</span><span class="sxs-lookup"><span data-stu-id="7e377-185">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="7e377-186">41</span><span class="sxs-lookup"><span data-stu-id="7e377-186">41</span></span>|<span data-ttu-id="7e377-187">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-187">Yes</span></span>|  
|<span data-ttu-id="7e377-188">MethodName</span><span class="sxs-lookup"><span data-stu-id="7e377-188">MethodName</span></span>|`nvarchar`|<span data-ttu-id="7e377-189">Имя метода OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7e377-189">Name of the OLE DB method.</span></span>|<span data-ttu-id="7e377-190">47</span><span class="sxs-lookup"><span data-stu-id="7e377-190">47</span></span>|<span data-ttu-id="7e377-191">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-191">Yes</span></span>|  
|<span data-ttu-id="7e377-192">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="7e377-192">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="7e377-193">Домен Windows, к которому принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="7e377-193">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="7e377-194">7</span><span class="sxs-lookup"><span data-stu-id="7e377-194">7</span></span>|<span data-ttu-id="7e377-195">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-195">Yes</span></span>|  
|<span data-ttu-id="7e377-196">NTUserName</span><span class="sxs-lookup"><span data-stu-id="7e377-196">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="7e377-197">Имя пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="7e377-197">Windows user name.</span></span>|<span data-ttu-id="7e377-198">6</span><span class="sxs-lookup"><span data-stu-id="7e377-198">6</span></span>|<span data-ttu-id="7e377-199">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-199">Yes</span></span>|  
|<span data-ttu-id="7e377-200">ProviderName</span><span class="sxs-lookup"><span data-stu-id="7e377-200">ProviderName</span></span>|`nvarchar`|<span data-ttu-id="7e377-201">Имя поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7e377-201">Name of the OLE DB provider.</span></span>|<span data-ttu-id="7e377-202">46</span><span class="sxs-lookup"><span data-stu-id="7e377-202">46</span></span>|<span data-ttu-id="7e377-203">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-203">Yes</span></span>|  
|<span data-ttu-id="7e377-204">RequestID</span><span class="sxs-lookup"><span data-stu-id="7e377-204">RequestID</span></span>|`Int`|<span data-ttu-id="7e377-205">Идентификатор запроса, содержащего инструкцию.</span><span class="sxs-lookup"><span data-stu-id="7e377-205">ID of the request containing the statement.</span></span>|<span data-ttu-id="7e377-206">49</span><span class="sxs-lookup"><span data-stu-id="7e377-206">49</span></span>|<span data-ttu-id="7e377-207">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-207">Yes</span></span>|  
|<span data-ttu-id="7e377-208">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="7e377-208">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="7e377-209">Имя входа пользователя, создавшего этот сеанс.</span><span class="sxs-lookup"><span data-stu-id="7e377-209">Login name of the user who originated the session.</span></span> <span data-ttu-id="7e377-210">Например, если подключиться к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] под именем Имя_входа1 и выполнить инструкцию как пользователь с именем Имя_входа2, в столбце `SessionLoginName` выводится значение Имя_входа1, а в столбце `LoginName` — значение Имя_входа2.</span><span class="sxs-lookup"><span data-stu-id="7e377-210">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, `SessionLoginName` shows Login1 and `LoginName` shows Login2.</span></span> <span data-ttu-id="7e377-211">В этом столбце отображаются как имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и имена входа Windows.</span><span class="sxs-lookup"><span data-stu-id="7e377-211">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="7e377-212">64</span><span class="sxs-lookup"><span data-stu-id="7e377-212">64</span></span>|<span data-ttu-id="7e377-213">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-213">Yes</span></span>|  
|<span data-ttu-id="7e377-214">SPID</span><span class="sxs-lookup"><span data-stu-id="7e377-214">SPID</span></span>|`Int`|<span data-ttu-id="7e377-215">Идентификатор сеанса, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="7e377-215">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="7e377-216">12</span><span class="sxs-lookup"><span data-stu-id="7e377-216">12</span></span>|<span data-ttu-id="7e377-217">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-217">Yes</span></span>|  
|<span data-ttu-id="7e377-218">StartTime</span><span class="sxs-lookup"><span data-stu-id="7e377-218">StartTime</span></span>|`datetime`|<span data-ttu-id="7e377-219">Время начала события, если оно известно.</span><span class="sxs-lookup"><span data-stu-id="7e377-219">Time at which the event started, if available.</span></span>|<span data-ttu-id="7e377-220">14</span><span class="sxs-lookup"><span data-stu-id="7e377-220">14</span></span>|<span data-ttu-id="7e377-221">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-221">Yes</span></span>|  
|<span data-ttu-id="7e377-222">TextData</span><span class="sxs-lookup"><span data-stu-id="7e377-222">TextData</span></span>|`nvarchar`|<span data-ttu-id="7e377-223">Параметры, которые отправляются и принимаются в вызове OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7e377-223">Parameters sent and received in the OLE DB call.</span></span>|<span data-ttu-id="7e377-224">1</span><span class="sxs-lookup"><span data-stu-id="7e377-224">1</span></span>|<span data-ttu-id="7e377-225">Нет</span><span class="sxs-lookup"><span data-stu-id="7e377-225">No</span></span>|  
|<span data-ttu-id="7e377-226">TransactionID</span><span class="sxs-lookup"><span data-stu-id="7e377-226">TransactionID</span></span>|`bigint`|<span data-ttu-id="7e377-227">Назначенный системой идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="7e377-227">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="7e377-228">4</span><span class="sxs-lookup"><span data-stu-id="7e377-228">4</span></span>|<span data-ttu-id="7e377-229">Да</span><span class="sxs-lookup"><span data-stu-id="7e377-229">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e377-230">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e377-230">See Also</span></span>  
 <span data-ttu-id="7e377-231">[Расширенные события](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="7e377-231">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="7e377-232">[Хранимая процедура sp_trace_setevent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e377-232">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="7e377-233">Объекты OLE-автоматизации в Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e377-233">OLE Automation Objects in Transact-SQL</span></span>](../stored-procedures/ole-automation-objects-in-transact-sql.md)  
  
  