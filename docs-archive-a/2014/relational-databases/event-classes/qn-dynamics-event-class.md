---
title: Класс событий QN:Dynamics | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], QN:Dynamics
ms.assetid: 3c1ffa0c-c9e5-40a6-a26b-28339f60ebc3
author: stevestein
ms.author: sstein
ms.openlocfilehash: e3273a9ac73e3850bd9989ce95713458931fa0b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666023"
---
# <a name="qndynamics-event-class"></a><span data-ttu-id="a978c-102">Класс событий QN:Dynamics</span><span class="sxs-lookup"><span data-stu-id="a978c-102">QN:Dynamics Event Class</span></span>
  <span data-ttu-id="a978c-103">Класс событий QN:Dynamics возвращает данные о фоновой активности компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] по поддержке уведомлений о запросах.</span><span class="sxs-lookup"><span data-stu-id="a978c-103">The QN:Dynamics event class reports information about the background activity that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] performs to support query notifications.</span></span> <span data-ttu-id="a978c-104">В пределах компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]фоновый поток осуществляет мониторинг тайм-аутов подписок, ожидающих подписки, которые необходимо запустить, и разрушение таблицы параметров.</span><span class="sxs-lookup"><span data-stu-id="a978c-104">Within the [!INCLUDE[ssDE](../../includes/ssde-md.md)], a background thread monitors subscription time-outs, pending subscriptions to be fired, and parameter table destruction.</span></span>  
  
## <a name="qndynamics-event-class-data-columns"></a><span data-ttu-id="a978c-105">Столбцы данных класса событий QN:Dynamics</span><span class="sxs-lookup"><span data-stu-id="a978c-105">QN:Dynamics Event Class Data Columns</span></span>  
  
|<span data-ttu-id="a978c-106">Столбец данных</span><span class="sxs-lookup"><span data-stu-id="a978c-106">Data column</span></span>|<span data-ttu-id="a978c-107">Тип</span><span class="sxs-lookup"><span data-stu-id="a978c-107">Type</span></span>|<span data-ttu-id="a978c-108">Description</span><span class="sxs-lookup"><span data-stu-id="a978c-108">Description</span></span>|<span data-ttu-id="a978c-109">Номер столбца</span><span class="sxs-lookup"><span data-stu-id="a978c-109">Column number</span></span>|<span data-ttu-id="a978c-110">Фильтруемый</span><span class="sxs-lookup"><span data-stu-id="a978c-110">Filterable</span></span>|  
|-----------------|----------|-----------------|-------------------|----------------|  
|<span data-ttu-id="a978c-111">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="a978c-111">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="a978c-112">Имя клиентского приложения, установившего соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a978c-112">The name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a978c-113">Этот столбец заполняется значениями, передаваемыми приложением, а не отображаемым именем программы.</span><span class="sxs-lookup"><span data-stu-id="a978c-113">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="a978c-114">10</span><span class="sxs-lookup"><span data-stu-id="a978c-114">10</span></span>|<span data-ttu-id="a978c-115">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-115">Yes</span></span>|  
|<span data-ttu-id="a978c-116">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="a978c-116">ClientProcessID</span></span>|`int`|<span data-ttu-id="a978c-117">Идентификатор, присвоенный компьютером сервера процессу, в котором работает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="a978c-117">The ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="a978c-118">Этот столбец данных заполняется в том случае, если клиент вводит идентификатор клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="a978c-118">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="a978c-119">9</span><span class="sxs-lookup"><span data-stu-id="a978c-119">9</span></span>|<span data-ttu-id="a978c-120">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-120">Yes</span></span>|  
|<span data-ttu-id="a978c-121">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="a978c-121">DatabaseID</span></span>|`int`|<span data-ttu-id="a978c-122">Идентификатор базы данных, указанной в инструкции USE *database* , или базы данных по умолчанию, если для данного экземпляра инструкция USE *database*не выполнялась.</span><span class="sxs-lookup"><span data-stu-id="a978c-122">The ID of the database specified by the USE *database* statement, or the ID of the default database if no USE *database*statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="a978c-123">отображает имя базы данных, если столбец данных «Имя сервера» захвачен при трассировке и сервер доступен.</span><span class="sxs-lookup"><span data-stu-id="a978c-123">displays the name of the database if the Server Name data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="a978c-124">Определите значение для базы данных, используя функцию DB_ID.</span><span class="sxs-lookup"><span data-stu-id="a978c-124">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="a978c-125">3</span><span class="sxs-lookup"><span data-stu-id="a978c-125">3</span></span>|<span data-ttu-id="a978c-126">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-126">Yes</span></span>|  
|<span data-ttu-id="a978c-127">имя_базы_данных</span><span class="sxs-lookup"><span data-stu-id="a978c-127">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="a978c-128">Имя базы данных, в которой выполняется инструкция пользователя.</span><span class="sxs-lookup"><span data-stu-id="a978c-128">The name of the database in which the user statement is running.</span></span>|<span data-ttu-id="a978c-129">35</span><span class="sxs-lookup"><span data-stu-id="a978c-129">35</span></span>|<span data-ttu-id="a978c-130">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-130">Yes</span></span>|  
|<span data-ttu-id="a978c-131">EventClass</span><span class="sxs-lookup"><span data-stu-id="a978c-131">EventClass</span></span>|`int`|<span data-ttu-id="a978c-132">Тип события = 202</span><span class="sxs-lookup"><span data-stu-id="a978c-132">Type of event = 202</span></span>|<span data-ttu-id="a978c-133">27</span><span class="sxs-lookup"><span data-stu-id="a978c-133">27</span></span>|<span data-ttu-id="a978c-134">Нет</span><span class="sxs-lookup"><span data-stu-id="a978c-134">No</span></span>|  
|<span data-ttu-id="a978c-135">EventSequence</span><span class="sxs-lookup"><span data-stu-id="a978c-135">EventSequence</span></span>|`int`|<span data-ttu-id="a978c-136">Порядковый номер этого события.</span><span class="sxs-lookup"><span data-stu-id="a978c-136">Sequence number for this event.</span></span>|<span data-ttu-id="a978c-137">51</span><span class="sxs-lookup"><span data-stu-id="a978c-137">51</span></span>|<span data-ttu-id="a978c-138">Нет</span><span class="sxs-lookup"><span data-stu-id="a978c-138">No</span></span>|  
|<span data-ttu-id="a978c-139">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="a978c-139">EventSubClass</span></span>|`nvarchar`|<span data-ttu-id="a978c-140">Тип подкласса событий, предоставляющий дополнительные сведения о каждом классе события.</span><span class="sxs-lookup"><span data-stu-id="a978c-140">The type of event subclass, providing further information about each event class.</span></span> <span data-ttu-id="a978c-141">Данный столбец может содержать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="a978c-141">This column may contain the following values:</span></span><br /><br /> <span data-ttu-id="a978c-142">Запуск часов запущен: указывает, что запущен фоновый поток в [!INCLUDE[ssDE](../../includes/ssde-md.md)] , планирующий таблицы параметров с истекшим сроком действия для очистки.</span><span class="sxs-lookup"><span data-stu-id="a978c-142">Clock run started: Indicates that the background thread in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that schedules expired parameter tables for cleanup has started.</span></span><br /><br /> <span data-ttu-id="a978c-143">Запуск часов завершен: указывает, что фоновый поток в [!INCLUDE[ssDE](../../includes/ssde-md.md)] , который планирует очистку таблиц параметров с истекшим сроком действия, завершен.</span><span class="sxs-lookup"><span data-stu-id="a978c-143">Clock run finished: Indicates that the background thread in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that schedules expired parameter tables for cleanup has finished.</span></span><br /><br /> <span data-ttu-id="a978c-144">Master cleanup task started. Определяет, когда будет запущена очистка (сборка мусора), удаляющая данные подписки на уведомления о запросах с истекшим сроком давности.</span><span class="sxs-lookup"><span data-stu-id="a978c-144">Master cleanup task started: Indicates when cleanup (garbage collection) to remove expired query notification subscription data starts.</span></span><br /><br /> <span data-ttu-id="a978c-145">Master cleanup task finished. Определяет, когда будет завершена очистка (сборка мусора), удаляющая данные подписки на уведомления о запросах с истекшим сроком давности.</span><span class="sxs-lookup"><span data-stu-id="a978c-145">Master cleanup task finished: Indicates when cleanup (garbage collection) to remove expired query notification subscription data finishes.</span></span><br /><br /> <span data-ttu-id="a978c-146">Задача "Основная Очистка" пропущена: указывает, что [!INCLUDE[ssDE](../../includes/ssde-md.md)] не выполнялась очистка (сборка мусора) для удаления просроченных данных подписки на уведомления о запросах.</span><span class="sxs-lookup"><span data-stu-id="a978c-146">Master cleanup task skipped: Indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] did not perform cleanup (garbage collection) to remove expired query notification subscription data.</span></span>|<span data-ttu-id="a978c-147">21</span><span class="sxs-lookup"><span data-stu-id="a978c-147">21</span></span>|<span data-ttu-id="a978c-148">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-148">Yes</span></span>|  
|<span data-ttu-id="a978c-149">GroupID</span><span class="sxs-lookup"><span data-stu-id="a978c-149">GroupID</span></span>|`int`|<span data-ttu-id="a978c-150">Идентификатор группы рабочей нагрузки, в которой запускается событие трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="a978c-150">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="a978c-151">66</span><span class="sxs-lookup"><span data-stu-id="a978c-151">66</span></span>|<span data-ttu-id="a978c-152">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-152">Yes</span></span>|  
|<span data-ttu-id="a978c-153">HostName</span><span class="sxs-lookup"><span data-stu-id="a978c-153">HostName</span></span>|`nvarchar`|<span data-ttu-id="a978c-154">Имя компьютера, на котором выполняется клиентская программа.</span><span class="sxs-lookup"><span data-stu-id="a978c-154">The name of the computer on which the client is running.</span></span> <span data-ttu-id="a978c-155">Заполнение этого столбца данных производится в том случае, если клиент предоставляет имя узла.</span><span class="sxs-lookup"><span data-stu-id="a978c-155">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="a978c-156">Чтобы определить имя узла, используйте функцию HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="a978c-156">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="a978c-157">8</span><span class="sxs-lookup"><span data-stu-id="a978c-157">8</span></span>|<span data-ttu-id="a978c-158">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-158">Yes</span></span>|  
|<span data-ttu-id="a978c-159">IsSystem</span><span class="sxs-lookup"><span data-stu-id="a978c-159">IsSystem</span></span>|`int`|<span data-ttu-id="a978c-160">Указывает, произошло событие в системном или в пользовательском процессе.</span><span class="sxs-lookup"><span data-stu-id="a978c-160">Indicates whether the event occurred on a system process or a user process.</span></span><br /><br /> <span data-ttu-id="a978c-161">0 = пользовательский процесс</span><span class="sxs-lookup"><span data-stu-id="a978c-161">0 = user</span></span><br /><br /> <span data-ttu-id="a978c-162">1 = системный процесс</span><span class="sxs-lookup"><span data-stu-id="a978c-162">1 = system</span></span>|<span data-ttu-id="a978c-163">60</span><span class="sxs-lookup"><span data-stu-id="a978c-163">60</span></span>|<span data-ttu-id="a978c-164">нет</span><span class="sxs-lookup"><span data-stu-id="a978c-164">No</span></span>|  
|<span data-ttu-id="a978c-165">LoginName</span><span class="sxs-lookup"><span data-stu-id="a978c-165">LoginName</span></span>|`nvarchar`|<span data-ttu-id="a978c-166">Имя учетной записи пользователя (имя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] входа безопасности или учетные данные входа Windows в формате *домен \ имя_пользователя*).</span><span class="sxs-lookup"><span data-stu-id="a978c-166">The name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the Windows login credentials in the form of *DOMAIN\Username*).</span></span>|<span data-ttu-id="a978c-167">11</span><span class="sxs-lookup"><span data-stu-id="a978c-167">11</span></span>|<span data-ttu-id="a978c-168">Нет</span><span class="sxs-lookup"><span data-stu-id="a978c-168">No</span></span>|  
|<span data-ttu-id="a978c-169">LoginSID</span><span class="sxs-lookup"><span data-stu-id="a978c-169">LoginSID</span></span>|`image`|<span data-ttu-id="a978c-170">Идентификатор безопасности вошедшего в систему пользователя.</span><span class="sxs-lookup"><span data-stu-id="a978c-170">The security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="a978c-171">Эти сведения можно найти в представлении каталога sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="a978c-171">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="a978c-172">Значение идентификатора безопасности уникально для каждого имени входа на сервере.</span><span class="sxs-lookup"><span data-stu-id="a978c-172">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="a978c-173">41</span><span class="sxs-lookup"><span data-stu-id="a978c-173">41</span></span>|<span data-ttu-id="a978c-174">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-174">Yes</span></span>|  
|<span data-ttu-id="a978c-175">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="a978c-175">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="a978c-176">Домен Windows, к которому принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="a978c-176">The Windows domain to which the user belongs.</span></span>|<span data-ttu-id="a978c-177">7</span><span class="sxs-lookup"><span data-stu-id="a978c-177">7</span></span>|<span data-ttu-id="a978c-178">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-178">Yes</span></span>|  
|<span data-ttu-id="a978c-179">NTUserName</span><span class="sxs-lookup"><span data-stu-id="a978c-179">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="a978c-180">Имя пользователя, которому принадлежит соединение, создавшее это событие.</span><span class="sxs-lookup"><span data-stu-id="a978c-180">The name of the user that owns the connection that generated this event.</span></span>|<span data-ttu-id="a978c-181">6</span><span class="sxs-lookup"><span data-stu-id="a978c-181">6</span></span>|<span data-ttu-id="a978c-182">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-182">Yes</span></span>|  
|<span data-ttu-id="a978c-183">RequestID</span><span class="sxs-lookup"><span data-stu-id="a978c-183">RequestID</span></span>|`int`|<span data-ttu-id="a978c-184">Идентификатор запроса, содержащего инструкцию.</span><span class="sxs-lookup"><span data-stu-id="a978c-184">Identifier of the request that contains the statement.</span></span>|<span data-ttu-id="a978c-185">49</span><span class="sxs-lookup"><span data-stu-id="a978c-185">49</span></span>|<span data-ttu-id="a978c-186">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-186">Yes</span></span>|  
|<span data-ttu-id="a978c-187">ServerName</span><span class="sxs-lookup"><span data-stu-id="a978c-187">ServerName</span></span>|`nvarchar`|<span data-ttu-id="a978c-188">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , подвергаемого трассировке.</span><span class="sxs-lookup"><span data-stu-id="a978c-188">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="a978c-189">26</span><span class="sxs-lookup"><span data-stu-id="a978c-189">26</span></span>|<span data-ttu-id="a978c-190">Нет</span><span class="sxs-lookup"><span data-stu-id="a978c-190">No</span></span>|  
|<span data-ttu-id="a978c-191">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="a978c-191">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="a978c-192">Имя входа пользователя, создавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a978c-192">Login name of the user that originated the session.</span></span> <span data-ttu-id="a978c-193">Например, если приложение соединяется с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] под именем Имя_входа1, а выполняет инструкции под именем Имя_входа2, то SessionLoginName содержит значение «Имя_входа1», а LoginName содержит значение «Имя_входа2».</span><span class="sxs-lookup"><span data-stu-id="a978c-193">For example, if an application connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and executes a statement as Login2, SessionLoginName shows "Login1" and LoginName shows "Login2".</span></span> <span data-ttu-id="a978c-194">В этом столбце отображаются как имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и имена входа Windows.</span><span class="sxs-lookup"><span data-stu-id="a978c-194">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="a978c-195">64</span><span class="sxs-lookup"><span data-stu-id="a978c-195">64</span></span>|<span data-ttu-id="a978c-196">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-196">Yes</span></span>|  
|<span data-ttu-id="a978c-197">SPID</span><span class="sxs-lookup"><span data-stu-id="a978c-197">SPID</span></span>|`int`|<span data-ttu-id="a978c-198">Идентификатор сеанса, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="a978c-198">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="a978c-199">12</span><span class="sxs-lookup"><span data-stu-id="a978c-199">12</span></span>|<span data-ttu-id="a978c-200">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-200">Yes</span></span>|  
|<span data-ttu-id="a978c-201">StartTime</span><span class="sxs-lookup"><span data-stu-id="a978c-201">StartTime</span></span>|`datetime`|<span data-ttu-id="a978c-202">Время начала события, если оно известно.</span><span class="sxs-lookup"><span data-stu-id="a978c-202">Time at which the event started, if available.</span></span>|<span data-ttu-id="a978c-203">14</span><span class="sxs-lookup"><span data-stu-id="a978c-203">14</span></span>|<span data-ttu-id="a978c-204">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-204">Yes</span></span>|  
|<span data-ttu-id="a978c-205">TextData</span><span class="sxs-lookup"><span data-stu-id="a978c-205">TextData</span></span>|`ntext`|<span data-ttu-id="a978c-206">Возвращает XML-документ, содержащий сведения, специфические для этого события.</span><span class="sxs-lookup"><span data-stu-id="a978c-206">Returns an XML document containing information specific to this event.</span></span> <span data-ttu-id="a978c-207">Этот документ соответствует XML-схеме, доступной на странице [Схема событий приложения SQL Server Query Notification Profiler](https://go.microsoft.com/fwlink/?LinkId=63331) .</span><span class="sxs-lookup"><span data-stu-id="a978c-207">This document conforms to the XML schema available at the [SQL Server Query Notification Profiler Event Schema](https://go.microsoft.com/fwlink/?LinkId=63331) page.</span></span>|<span data-ttu-id="a978c-208">1</span><span class="sxs-lookup"><span data-stu-id="a978c-208">1</span></span>|<span data-ttu-id="a978c-209">Да</span><span class="sxs-lookup"><span data-stu-id="a978c-209">Yes</span></span>|  
  
  