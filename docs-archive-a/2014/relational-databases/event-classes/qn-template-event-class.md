---
title: Класс событий QN:Template | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], QN:Template
ms.assetid: 9f752040-5901-42e1-8fdc-105528d9960a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 120272f43152402c1a402ca9ce493a6e059f8cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654306"
---
# <a name="qntemplate-event-class"></a><span data-ttu-id="ae116-102">Класс событий QN: Template</span><span class="sxs-lookup"><span data-stu-id="ae116-102">QN:Template Event Class</span></span>
  <span data-ttu-id="ae116-103">Событие QN:Template возвращает данные о внутреннем использовании шаблонов запросов.</span><span class="sxs-lookup"><span data-stu-id="ae116-103">The QN:Template event reports information on the internal use of query templates.</span></span> <span data-ttu-id="ae116-104">Шаблоны запросов представляют собой механизм, который компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] применяет для рассылки определений запроса, о котором будут распространяться уведомления.</span><span class="sxs-lookup"><span data-stu-id="ae116-104">Query templates are the mechanism that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] uses to share definitions of a query for notification.</span></span> <span data-ttu-id="ae116-105">Эти шаблоны создаются одновременно с таблицами параметров.</span><span class="sxs-lookup"><span data-stu-id="ae116-105">These templates are created along with parameter tables.</span></span> <span data-ttu-id="ae116-106">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] создает событие этого типа, когда шаблон запроса создается, применяется или разрушается.</span><span class="sxs-lookup"><span data-stu-id="ae116-106">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] creates an event of this type when a query template is created, used, or destroyed.</span></span>  
  
## <a name="qntemplate-event-class-data-columns"></a><span data-ttu-id="ae116-107">Столбцы данных класса событий QN:Template</span><span class="sxs-lookup"><span data-stu-id="ae116-107">QN:Template Event Class Data Columns</span></span>  
  
|<span data-ttu-id="ae116-108">Столбец данных</span><span class="sxs-lookup"><span data-stu-id="ae116-108">Data column</span></span>|<span data-ttu-id="ae116-109">Тип</span><span class="sxs-lookup"><span data-stu-id="ae116-109">Type</span></span>|<span data-ttu-id="ae116-110">Description</span><span class="sxs-lookup"><span data-stu-id="ae116-110">Description</span></span>|<span data-ttu-id="ae116-111">Номер столбца</span><span class="sxs-lookup"><span data-stu-id="ae116-111">Column number</span></span>|<span data-ttu-id="ae116-112">Фильтруемый</span><span class="sxs-lookup"><span data-stu-id="ae116-112">Filterable</span></span>|  
|-----------------|----------|-----------------|-------------------|----------------|  
|<span data-ttu-id="ae116-113">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="ae116-113">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="ae116-114">Имя клиентского приложения, установившего соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae116-114">The name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ae116-115">Этот столбец заполняется значениями, передаваемыми приложением, а не отображаемым именем программы.</span><span class="sxs-lookup"><span data-stu-id="ae116-115">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="ae116-116">10</span><span class="sxs-lookup"><span data-stu-id="ae116-116">10</span></span>|<span data-ttu-id="ae116-117">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-117">Yes</span></span>|  
|<span data-ttu-id="ae116-118">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="ae116-118">ClientProcessID</span></span>|`int`|<span data-ttu-id="ae116-119">Идентификатор, присвоенный компьютером сервера процессу, в котором работает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="ae116-119">The ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="ae116-120">Этот столбец данных заполняется в том случае, если клиент вводит идентификатор клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="ae116-120">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="ae116-121">9</span><span class="sxs-lookup"><span data-stu-id="ae116-121">9</span></span>|<span data-ttu-id="ae116-122">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-122">Yes</span></span>|  
|<span data-ttu-id="ae116-123">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="ae116-123">DatabaseID</span></span>|`int`|<span data-ttu-id="ae116-124">Идентификатор базы данных, указанной в инструкции USE *database* , или базы данных по умолчанию, если для данного экземпляра инструкция USE *database*не выполнялась.</span><span class="sxs-lookup"><span data-stu-id="ae116-124">The ID of the database specified by the USE *database* statement, or the ID of the default database if no USE *database*statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="ae116-125">отображает имя базы данных, если столбец данных «Имя сервера» захвачен при трассировке и сервер доступен.</span><span class="sxs-lookup"><span data-stu-id="ae116-125">displays the name of the database if the Server Name data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="ae116-126">Определите значение для базы данных, используя функцию DB_ID.</span><span class="sxs-lookup"><span data-stu-id="ae116-126">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="ae116-127">3</span><span class="sxs-lookup"><span data-stu-id="ae116-127">3</span></span>|<span data-ttu-id="ae116-128">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-128">Yes</span></span>|  
|<span data-ttu-id="ae116-129">имя_базы_данных</span><span class="sxs-lookup"><span data-stu-id="ae116-129">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="ae116-130">Имя базы данных, в которой выполняется инструкция пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae116-130">The name of the database in which the user statement is running.</span></span>|<span data-ttu-id="ae116-131">35</span><span class="sxs-lookup"><span data-stu-id="ae116-131">35</span></span>|<span data-ttu-id="ae116-132">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-132">Yes</span></span>|  
|<span data-ttu-id="ae116-133">EventClass</span><span class="sxs-lookup"><span data-stu-id="ae116-133">EventClass</span></span>|`int`|<span data-ttu-id="ae116-134">Тип события = 201.</span><span class="sxs-lookup"><span data-stu-id="ae116-134">Type of event = 201.</span></span>|<span data-ttu-id="ae116-135">27</span><span class="sxs-lookup"><span data-stu-id="ae116-135">27</span></span>|<span data-ttu-id="ae116-136">Нет</span><span class="sxs-lookup"><span data-stu-id="ae116-136">No</span></span>|  
|<span data-ttu-id="ae116-137">EventSequence</span><span class="sxs-lookup"><span data-stu-id="ae116-137">EventSequence</span></span>|`int`|<span data-ttu-id="ae116-138">Порядковый номер этого события.</span><span class="sxs-lookup"><span data-stu-id="ae116-138">Sequence number for this event.</span></span>|<span data-ttu-id="ae116-139">51</span><span class="sxs-lookup"><span data-stu-id="ae116-139">51</span></span>|<span data-ttu-id="ae116-140">Нет</span><span class="sxs-lookup"><span data-stu-id="ae116-140">No</span></span>|  
|<span data-ttu-id="ae116-141">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="ae116-141">EventSubClass</span></span>|`nvarchar`|<span data-ttu-id="ae116-142">Тип подкласса событий, предоставляющий дополнительные сведения о каждом классе события.</span><span class="sxs-lookup"><span data-stu-id="ae116-142">The type of event subclass, providing further information about each event class.</span></span> <span data-ttu-id="ae116-143">Данный столбец может содержать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="ae116-143">This column may contain the following values:</span></span><br /><br /> <span data-ttu-id="ae116-144">Template created: указывает, что в базе данных создан шаблон уведомления запроса.</span><span class="sxs-lookup"><span data-stu-id="ae116-144">Template created: Indicates that a query notification template has been created in the database.</span></span><br /><br /> <span data-ttu-id="ae116-145">Template matched: указывает, когда шаблон уведомления запроса используется повторно.</span><span class="sxs-lookup"><span data-stu-id="ae116-145">Template matched: Indicates when a query notification template is reused.</span></span><br /><br /> <span data-ttu-id="ae116-146">Template dropped: указывает, когда шаблон уведомления запроса удаляется из базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae116-146">Template dropped: Indicates when a query notification template is removed from the database.</span></span>|<span data-ttu-id="ae116-147">21</span><span class="sxs-lookup"><span data-stu-id="ae116-147">21</span></span>|<span data-ttu-id="ae116-148">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-148">Yes</span></span>|  
|<span data-ttu-id="ae116-149">GroupID</span><span class="sxs-lookup"><span data-stu-id="ae116-149">GroupID</span></span>|`int`|<span data-ttu-id="ae116-150">Идентификатор группы рабочей нагрузки, в которой запускается событие трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="ae116-150">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="ae116-151">66</span><span class="sxs-lookup"><span data-stu-id="ae116-151">66</span></span>|<span data-ttu-id="ae116-152">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-152">Yes</span></span>|  
|<span data-ttu-id="ae116-153">HostName</span><span class="sxs-lookup"><span data-stu-id="ae116-153">HostName</span></span>|`nvarchar`|<span data-ttu-id="ae116-154">Имя компьютера, на котором выполняется клиентская программа.</span><span class="sxs-lookup"><span data-stu-id="ae116-154">The name of the computer on which the client is running.</span></span> <span data-ttu-id="ae116-155">Заполнение этого столбца данных производится в том случае, если клиент предоставляет имя узла.</span><span class="sxs-lookup"><span data-stu-id="ae116-155">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="ae116-156">Чтобы определить имя узла, используйте функцию HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="ae116-156">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="ae116-157">8</span><span class="sxs-lookup"><span data-stu-id="ae116-157">8</span></span>|<span data-ttu-id="ae116-158">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-158">Yes</span></span>|  
|<span data-ttu-id="ae116-159">IsSystem</span><span class="sxs-lookup"><span data-stu-id="ae116-159">IsSystem</span></span>|`int`|<span data-ttu-id="ae116-160">Указывает, произошло событие в системном или в пользовательском процессе.</span><span class="sxs-lookup"><span data-stu-id="ae116-160">Indicates whether the event occurred on a system process or a user process.</span></span><br /><br /> <span data-ttu-id="ae116-161">0 = пользовательский процесс</span><span class="sxs-lookup"><span data-stu-id="ae116-161">0 = user</span></span><br /><br /> <span data-ttu-id="ae116-162">1 = системный процесс</span><span class="sxs-lookup"><span data-stu-id="ae116-162">1 = system</span></span>|<span data-ttu-id="ae116-163">60</span><span class="sxs-lookup"><span data-stu-id="ae116-163">60</span></span>|<span data-ttu-id="ae116-164">нет</span><span class="sxs-lookup"><span data-stu-id="ae116-164">No</span></span>|  
|<span data-ttu-id="ae116-165">LoginName</span><span class="sxs-lookup"><span data-stu-id="ae116-165">LoginName</span></span>|`nvarchar`|<span data-ttu-id="ae116-166">Имя учетной записи пользователя (имя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] входа безопасности или учетные данные входа Windows в формате *домен \ имя_пользователя*).</span><span class="sxs-lookup"><span data-stu-id="ae116-166">The name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the Windows login credentials in the form of *DOMAIN\Username*).</span></span>|<span data-ttu-id="ae116-167">11</span><span class="sxs-lookup"><span data-stu-id="ae116-167">11</span></span>|<span data-ttu-id="ae116-168">Нет</span><span class="sxs-lookup"><span data-stu-id="ae116-168">No</span></span>|  
|<span data-ttu-id="ae116-169">LoginSID</span><span class="sxs-lookup"><span data-stu-id="ae116-169">LoginSID</span></span>|`image`|<span data-ttu-id="ae116-170">Идентификатор безопасности вошедшего в систему пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae116-170">The security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="ae116-171">Эти сведения можно найти в представлении каталога sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="ae116-171">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="ae116-172">Значение идентификатора безопасности уникально для каждого имени входа на сервере.</span><span class="sxs-lookup"><span data-stu-id="ae116-172">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="ae116-173">41</span><span class="sxs-lookup"><span data-stu-id="ae116-173">41</span></span>|<span data-ttu-id="ae116-174">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-174">Yes</span></span>|  
|<span data-ttu-id="ae116-175">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="ae116-175">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="ae116-176">Домен Windows, к которому принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="ae116-176">The Windows domain to which the user belongs.</span></span>|<span data-ttu-id="ae116-177">7</span><span class="sxs-lookup"><span data-stu-id="ae116-177">7</span></span>|<span data-ttu-id="ae116-178">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-178">Yes</span></span>|  
|<span data-ttu-id="ae116-179">NTUserName</span><span class="sxs-lookup"><span data-stu-id="ae116-179">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="ae116-180">Имя пользователя, которому принадлежит соединение, создавшее это событие.</span><span class="sxs-lookup"><span data-stu-id="ae116-180">The name of the user that owns the connection that generated this event.</span></span>|<span data-ttu-id="ae116-181">6</span><span class="sxs-lookup"><span data-stu-id="ae116-181">6</span></span>|<span data-ttu-id="ae116-182">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-182">Yes</span></span>|  
|<span data-ttu-id="ae116-183">RequestID</span><span class="sxs-lookup"><span data-stu-id="ae116-183">RequestID</span></span>|`int`|<span data-ttu-id="ae116-184">Идентификатор запроса, содержащего инструкцию.</span><span class="sxs-lookup"><span data-stu-id="ae116-184">Identifier of the request that contains the statement.</span></span>|<span data-ttu-id="ae116-185">49</span><span class="sxs-lookup"><span data-stu-id="ae116-185">49</span></span>|<span data-ttu-id="ae116-186">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-186">Yes</span></span>|  
|<span data-ttu-id="ae116-187">ServerName</span><span class="sxs-lookup"><span data-stu-id="ae116-187">ServerName</span></span>|`nvarchar`|<span data-ttu-id="ae116-188">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , подвергаемого трассировке.</span><span class="sxs-lookup"><span data-stu-id="ae116-188">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="ae116-189">26</span><span class="sxs-lookup"><span data-stu-id="ae116-189">26</span></span>|<span data-ttu-id="ae116-190">Нет</span><span class="sxs-lookup"><span data-stu-id="ae116-190">No</span></span>|  
|<span data-ttu-id="ae116-191">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="ae116-191">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="ae116-192">Имя входа пользователя, создавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="ae116-192">Login name of the user that originated the session.</span></span> <span data-ttu-id="ae116-193">Например, если приложение соединяется с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] под именем Имя_входа1, а выполняет инструкции под именем Имя_входа2, то SessionLoginName содержит значение «Имя_входа1», а LoginName содержит значение «Имя_входа2».</span><span class="sxs-lookup"><span data-stu-id="ae116-193">For example, if an application connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and executes a statement as Login2, SessionLoginName shows "Login1" and LoginName shows "Login2".</span></span> <span data-ttu-id="ae116-194">В этом столбце отображаются как имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и имена входа Windows.</span><span class="sxs-lookup"><span data-stu-id="ae116-194">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="ae116-195">64</span><span class="sxs-lookup"><span data-stu-id="ae116-195">64</span></span>|<span data-ttu-id="ae116-196">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-196">Yes</span></span>|  
|<span data-ttu-id="ae116-197">SPID</span><span class="sxs-lookup"><span data-stu-id="ae116-197">SPID</span></span>|`int`|<span data-ttu-id="ae116-198">Идентификатор сеанса, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="ae116-198">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="ae116-199">12</span><span class="sxs-lookup"><span data-stu-id="ae116-199">12</span></span>|<span data-ttu-id="ae116-200">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-200">Yes</span></span>|  
|<span data-ttu-id="ae116-201">StartTime</span><span class="sxs-lookup"><span data-stu-id="ae116-201">StartTime</span></span>|`datetime`|<span data-ttu-id="ae116-202">Время начала события, если оно известно.</span><span class="sxs-lookup"><span data-stu-id="ae116-202">Time at which the event started, if available.</span></span>|<span data-ttu-id="ae116-203">14</span><span class="sxs-lookup"><span data-stu-id="ae116-203">14</span></span>|<span data-ttu-id="ae116-204">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-204">Yes</span></span>|  
|<span data-ttu-id="ae116-205">TextData</span><span class="sxs-lookup"><span data-stu-id="ae116-205">TextData</span></span>|`ntext`|<span data-ttu-id="ae116-206">Возвращает XML-документ, содержащий сведения, специфические для этого события.</span><span class="sxs-lookup"><span data-stu-id="ae116-206">Returns an XML document containing information specific to this event.</span></span> <span data-ttu-id="ae116-207">Этот документ соответствует XML-схеме, доступной на странице [Схема событий приложения SQL Server Query Notification Profiler](https://go.microsoft.com/fwlink/?LinkId=63331) .</span><span class="sxs-lookup"><span data-stu-id="ae116-207">This document conforms to the XML schema available at the [SQL Server Query Notification Profiler Event Schema](https://go.microsoft.com/fwlink/?LinkId=63331) page.</span></span>|<span data-ttu-id="ae116-208">1</span><span class="sxs-lookup"><span data-stu-id="ae116-208">1</span></span>|<span data-ttu-id="ae116-209">Да</span><span class="sxs-lookup"><span data-stu-id="ae116-209">Yes</span></span>|  
  
  