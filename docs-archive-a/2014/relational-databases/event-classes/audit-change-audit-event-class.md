---
title: Класс событий Audit Change Audit | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Audit Change Audit event class
ms.assetid: 8cfacc82-cee8-4199-a69e-acedecfc0b3b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 199a3f073e0844489d4e4bbe10e6fb87cd92b48f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732674"
---
# <a name="audit-change-audit-event-class"></a><span data-ttu-id="0f427-102">Audit Change Audit, класс событий</span><span class="sxs-lookup"><span data-stu-id="0f427-102">Audit Change Audit Event Class</span></span>
  <span data-ttu-id="0f427-103">Класс событий **Audit Change Audit** происходят при изменении трассировки.</span><span class="sxs-lookup"><span data-stu-id="0f427-103">The **Audit Change Audit** event class occurs whenever an audit trace modification is made.</span></span>  
  
## <a name="audit-change-audit-event-class-data-columns"></a><span data-ttu-id="0f427-104">Столбцы данных класса событий Audit Change Audit</span><span class="sxs-lookup"><span data-stu-id="0f427-104">Audit Change Audit Event Class Data Columns</span></span>  
  
|<span data-ttu-id="0f427-105">Имя столбца данных</span><span class="sxs-lookup"><span data-stu-id="0f427-105">Data column name</span></span>|<span data-ttu-id="0f427-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0f427-106">Data type</span></span>|<span data-ttu-id="0f427-107">Description</span><span class="sxs-lookup"><span data-stu-id="0f427-107">Description</span></span>|<span data-ttu-id="0f427-108">Идентификатор столбца</span><span class="sxs-lookup"><span data-stu-id="0f427-108">Column ID</span></span>|<span data-ttu-id="0f427-109">Фильтруемый</span><span class="sxs-lookup"><span data-stu-id="0f427-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="0f427-110">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="0f427-110">**ApplicationName**</span></span>|<span data-ttu-id="0f427-111">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-111">**nvarchar**</span></span>|<span data-ttu-id="0f427-112">Имя клиентского приложения, установившего соединение с экземпляром [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f427-112">Name of the client application that created the connection to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0f427-113">Этот столбец заполняется значениями, передаваемыми приложением, а не отображаемым именем программы.</span><span class="sxs-lookup"><span data-stu-id="0f427-113">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="0f427-114">10</span><span class="sxs-lookup"><span data-stu-id="0f427-114">10</span></span>|<span data-ttu-id="0f427-115">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-115">Yes</span></span>|  
|<span data-ttu-id="0f427-116">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="0f427-116">**ClientProcessID**</span></span>|<span data-ttu-id="0f427-117">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-117">**int**</span></span>|<span data-ttu-id="0f427-118">Идентификатор, присвоенный главным компьютером сервера процессу, в котором работает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="0f427-118">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="0f427-119">Этот столбец данных заполняется в том случае, если клиент предоставляет идентификатор клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="0f427-119">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="0f427-120">9</span><span class="sxs-lookup"><span data-stu-id="0f427-120">9</span></span>|<span data-ttu-id="0f427-121">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-121">Yes</span></span>|  
|<span data-ttu-id="0f427-122">**ColumnPermissions**</span><span class="sxs-lookup"><span data-stu-id="0f427-122">**ColumnPermissions**</span></span>|<span data-ttu-id="0f427-123">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-123">**int**</span></span>|<span data-ttu-id="0f427-124">Указывает, было ли установлено разрешение на доступ к столбцу.</span><span class="sxs-lookup"><span data-stu-id="0f427-124">Indicator of whether a column permission was set.</span></span> <span data-ttu-id="0f427-125">Проанализируйте текст инструкции для определения того, какие разрешения были применены к каким столбцам.</span><span class="sxs-lookup"><span data-stu-id="0f427-125">Parse the statement text to determine which permissions were applied to which columns.</span></span>|<span data-ttu-id="0f427-126">44</span><span class="sxs-lookup"><span data-stu-id="0f427-126">44</span></span>|<span data-ttu-id="0f427-127">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-127">Yes</span></span>|  
|<span data-ttu-id="0f427-128">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="0f427-128">**DatabaseID**</span></span>|<span data-ttu-id="0f427-129">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-129">**int**</span></span>|<span data-ttu-id="0f427-130">Идентификатор базы данных, указанной в инструкции USE *database* , или базы данных по умолчанию, если для данного экземпляра инструкция USE *database* не выполнялась.</span><span class="sxs-lookup"><span data-stu-id="0f427-130">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="0f427-131">отображает имя базы данных, если столбец данных **ServerName** захвачен при трассировке и сервер доступен.</span><span class="sxs-lookup"><span data-stu-id="0f427-131">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="0f427-132">Определите значение для базы данных, используя функцию DB_ID.</span><span class="sxs-lookup"><span data-stu-id="0f427-132">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="0f427-133">3</span><span class="sxs-lookup"><span data-stu-id="0f427-133">3</span></span>|<span data-ttu-id="0f427-134">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-134">Yes</span></span>|  
|<span data-ttu-id="0f427-135">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="0f427-135">**DatabaseName**</span></span>|<span data-ttu-id="0f427-136">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-136">**nvarchar**</span></span>|<span data-ttu-id="0f427-137">Имя базы данных, в которой выполняется пользовательская инструкция.</span><span class="sxs-lookup"><span data-stu-id="0f427-137">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="0f427-138">35</span><span class="sxs-lookup"><span data-stu-id="0f427-138">35</span></span>|<span data-ttu-id="0f427-139">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-139">Yes</span></span>|  
|<span data-ttu-id="0f427-140">**DBUserName**</span><span class="sxs-lookup"><span data-stu-id="0f427-140">**DBUserName**</span></span>|<span data-ttu-id="0f427-141">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-141">**nvarchar**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0f427-142">.</span><span class="sxs-lookup"><span data-stu-id="0f427-142">user name of the client.</span></span>|<span data-ttu-id="0f427-143">40</span><span class="sxs-lookup"><span data-stu-id="0f427-143">40</span></span>|<span data-ttu-id="0f427-144">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-144">Yes</span></span>|  
|<span data-ttu-id="0f427-145">**EventClass**</span><span class="sxs-lookup"><span data-stu-id="0f427-145">**EventClass**</span></span>|<span data-ttu-id="0f427-146">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-146">**int**</span></span>|<span data-ttu-id="0f427-147">Тип события = 117.</span><span class="sxs-lookup"><span data-stu-id="0f427-147">Type of event = 117.</span></span>|<span data-ttu-id="0f427-148">27</span><span class="sxs-lookup"><span data-stu-id="0f427-148">27</span></span>|<span data-ttu-id="0f427-149">нет</span><span class="sxs-lookup"><span data-stu-id="0f427-149">No</span></span>|  
|<span data-ttu-id="0f427-150">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="0f427-150">**EventSequence**</span></span>|<span data-ttu-id="0f427-151">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-151">**int**</span></span>|<span data-ttu-id="0f427-152">Последовательность данного события в запросе.</span><span class="sxs-lookup"><span data-stu-id="0f427-152">Sequence of a given event within the request.</span></span>|<span data-ttu-id="0f427-153">51</span><span class="sxs-lookup"><span data-stu-id="0f427-153">51</span></span>|<span data-ttu-id="0f427-154">нет</span><span class="sxs-lookup"><span data-stu-id="0f427-154">No</span></span>|  
|<span data-ttu-id="0f427-155">**EventSubClass**</span><span class="sxs-lookup"><span data-stu-id="0f427-155">**EventSubClass**</span></span>|<span data-ttu-id="0f427-156">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-156">**int**</span></span>|<span data-ttu-id="0f427-157">Тип подкласса события.</span><span class="sxs-lookup"><span data-stu-id="0f427-157">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="0f427-158">1 = начало аудита,</span><span class="sxs-lookup"><span data-stu-id="0f427-158">1=Audit started</span></span><br /><br /> <span data-ttu-id="0f427-159">2 = завершение аудита,</span><span class="sxs-lookup"><span data-stu-id="0f427-159">2=Audit stopped</span></span><br /><br /> <span data-ttu-id="0f427-160">3 = режим C2 включен (ON),</span><span class="sxs-lookup"><span data-stu-id="0f427-160">3=C2 mode ON</span></span><br /><br /> <span data-ttu-id="0f427-161">4 = режим C2 выключен (OFF).</span><span class="sxs-lookup"><span data-stu-id="0f427-161">4=C2 mode OFF</span></span>|<span data-ttu-id="0f427-162">21</span><span class="sxs-lookup"><span data-stu-id="0f427-162">21</span></span>|<span data-ttu-id="0f427-163">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-163">Yes</span></span>|  
|<span data-ttu-id="0f427-164">**HostName**</span><span class="sxs-lookup"><span data-stu-id="0f427-164">**HostName**</span></span>|<span data-ttu-id="0f427-165">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-165">**nvarchar**</span></span>|<span data-ttu-id="0f427-166">Имя компьютера, на котором выполняется клиентская программа.</span><span class="sxs-lookup"><span data-stu-id="0f427-166">Name of the computer on which the client is running.</span></span> <span data-ttu-id="0f427-167">Этот столбец данных заполняется, если клиент предоставляет имя узла.</span><span class="sxs-lookup"><span data-stu-id="0f427-167">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="0f427-168">Чтобы определить имя узла, используйте функцию HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="0f427-168">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="0f427-169">8</span><span class="sxs-lookup"><span data-stu-id="0f427-169">8</span></span>|<span data-ttu-id="0f427-170">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-170">Yes</span></span>|  
|<span data-ttu-id="0f427-171">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="0f427-171">**IsSystem**</span></span>|<span data-ttu-id="0f427-172">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-172">**int**</span></span>|<span data-ttu-id="0f427-173">Указывает, произошло событие в системном или в пользовательском процессе.</span><span class="sxs-lookup"><span data-stu-id="0f427-173">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="0f427-174">1 = системный, 0 = пользовательский.</span><span class="sxs-lookup"><span data-stu-id="0f427-174">1 = system, 0 = user.</span></span>|<span data-ttu-id="0f427-175">60</span><span class="sxs-lookup"><span data-stu-id="0f427-175">60</span></span>|<span data-ttu-id="0f427-176">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-176">Yes</span></span>|  
|<span data-ttu-id="0f427-177">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="0f427-177">**LoginName**</span></span>|<span data-ttu-id="0f427-178">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-178">**nvarchar**</span></span>|<span data-ttu-id="0f427-179">Имя входа пользователя (либо имя входа безопасности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , либо учетные данные входа [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows в формате «ДОМЕН\имя_пользователя»).</span><span class="sxs-lookup"><span data-stu-id="0f427-179">Name of the login of the user (either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="0f427-180">11</span><span class="sxs-lookup"><span data-stu-id="0f427-180">11</span></span>|<span data-ttu-id="0f427-181">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-181">Yes</span></span>|  
|<span data-ttu-id="0f427-182">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="0f427-182">**LoginSid**</span></span>|<span data-ttu-id="0f427-183">**image**</span><span class="sxs-lookup"><span data-stu-id="0f427-183">**image**</span></span>|<span data-ttu-id="0f427-184">Идентификатор безопасности вошедшего в систему пользователя.</span><span class="sxs-lookup"><span data-stu-id="0f427-184">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="0f427-185">Эти сведения можно найти в представлении каталога **sys.server_principals** .</span><span class="sxs-lookup"><span data-stu-id="0f427-185">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="0f427-186">Значение идентификатора безопасности уникально для каждого имени входа на сервере.</span><span class="sxs-lookup"><span data-stu-id="0f427-186">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="0f427-187">41</span><span class="sxs-lookup"><span data-stu-id="0f427-187">41</span></span>|<span data-ttu-id="0f427-188">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-188">Yes</span></span>|  
|<span data-ttu-id="0f427-189">**NestLevel**</span><span class="sxs-lookup"><span data-stu-id="0f427-189">**NestLevel**</span></span>|<span data-ttu-id="0f427-190">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-190">**int**</span></span>|<span data-ttu-id="0f427-191">Целочисленное значение, представляющее данные, возвращаемые функцией @@NESTLEVEL.</span><span class="sxs-lookup"><span data-stu-id="0f427-191">Integer representing the data returned by @@NESTLEVEL.</span></span>|<span data-ttu-id="0f427-192">29</span><span class="sxs-lookup"><span data-stu-id="0f427-192">29</span></span>|<span data-ttu-id="0f427-193">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-193">Yes</span></span>|  
|<span data-ttu-id="0f427-194">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="0f427-194">**NTDomainName**</span></span>|<span data-ttu-id="0f427-195">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-195">**nvarchar**</span></span>|<span data-ttu-id="0f427-196">Домен Windows, к которому принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="0f427-196">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="0f427-197">7</span><span class="sxs-lookup"><span data-stu-id="0f427-197">7</span></span>|<span data-ttu-id="0f427-198">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-198">Yes</span></span>|  
|<span data-ttu-id="0f427-199">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="0f427-199">**NTUserName**</span></span>|<span data-ttu-id="0f427-200">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-200">**nvarchar**</span></span>|<span data-ttu-id="0f427-201">Имя пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="0f427-201">Windows user name.</span></span>|<span data-ttu-id="0f427-202">6</span><span class="sxs-lookup"><span data-stu-id="0f427-202">6</span></span>|<span data-ttu-id="0f427-203">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-203">Yes</span></span>|  
|<span data-ttu-id="0f427-204">**OwnerName**</span><span class="sxs-lookup"><span data-stu-id="0f427-204">**OwnerName**</span></span>|<span data-ttu-id="0f427-205">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-205">**nvarchar**</span></span>|<span data-ttu-id="0f427-206">Имя пользователя базы данных, владеющего объектом.</span><span class="sxs-lookup"><span data-stu-id="0f427-206">Database user name of the object owner.</span></span>|<span data-ttu-id="0f427-207">37</span><span class="sxs-lookup"><span data-stu-id="0f427-207">37</span></span>|<span data-ttu-id="0f427-208">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-208">Yes</span></span>|  
|<span data-ttu-id="0f427-209">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="0f427-209">**RequestID**</span></span>|<span data-ttu-id="0f427-210">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-210">**int**</span></span>|<span data-ttu-id="0f427-211">Идентификатор запроса, содержащего инструкцию.</span><span class="sxs-lookup"><span data-stu-id="0f427-211">ID of the request containing the statement.</span></span>|<span data-ttu-id="0f427-212">49</span><span class="sxs-lookup"><span data-stu-id="0f427-212">49</span></span>|<span data-ttu-id="0f427-213">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-213">Yes</span></span>|  
|<span data-ttu-id="0f427-214">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="0f427-214">**ServerName**</span></span>|<span data-ttu-id="0f427-215">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-215">**nvarchar**</span></span>|<span data-ttu-id="0f427-216">Имя экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], для которого производится трассировка.</span><span class="sxs-lookup"><span data-stu-id="0f427-216">Name of the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="0f427-217">26</span><span class="sxs-lookup"><span data-stu-id="0f427-217">26</span></span>|<span data-ttu-id="0f427-218">нет</span><span class="sxs-lookup"><span data-stu-id="0f427-218">No</span></span>|  
|<span data-ttu-id="0f427-219">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="0f427-219">**SessionLoginName**</span></span>|<span data-ttu-id="0f427-220">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="0f427-220">**nvarchar**</span></span>|<span data-ttu-id="0f427-221">Имя входа пользователя, создавшего этот сеанс.</span><span class="sxs-lookup"><span data-stu-id="0f427-221">Login name of the user who originated the session.</span></span> <span data-ttu-id="0f427-222">Например, при подключении к [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по имени "Имя_входа1" и при выполнении инструкции под именем "Имя_входа2" **SessionLoginName** содержит значение "Имя_входа1", а **LoginName** — значение "Имя_входа2".</span><span class="sxs-lookup"><span data-stu-id="0f427-222">For example, if you connect to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="0f427-223">В этом столбце отображаются как имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и имена входа Windows.</span><span class="sxs-lookup"><span data-stu-id="0f427-223">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="0f427-224">64</span><span class="sxs-lookup"><span data-stu-id="0f427-224">64</span></span>|<span data-ttu-id="0f427-225">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-225">Yes</span></span>|  
|<span data-ttu-id="0f427-226">**SPID**</span><span class="sxs-lookup"><span data-stu-id="0f427-226">**SPID**</span></span>|<span data-ttu-id="0f427-227">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-227">**int**</span></span>|<span data-ttu-id="0f427-228">Идентификатор сеанса, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="0f427-228">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="0f427-229">12</span><span class="sxs-lookup"><span data-stu-id="0f427-229">12</span></span>|<span data-ttu-id="0f427-230">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-230">Yes</span></span>|  
|<span data-ttu-id="0f427-231">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="0f427-231">**StartTime**</span></span>|<span data-ttu-id="0f427-232">**datetime**</span><span class="sxs-lookup"><span data-stu-id="0f427-232">**datetime**</span></span>|<span data-ttu-id="0f427-233">Время начала события, если оно известно.</span><span class="sxs-lookup"><span data-stu-id="0f427-233">Time at which the event started, if available.</span></span>|<span data-ttu-id="0f427-234">14</span><span class="sxs-lookup"><span data-stu-id="0f427-234">14</span></span>|<span data-ttu-id="0f427-235">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-235">Yes</span></span>|  
|<span data-ttu-id="0f427-236">**Успешно**</span><span class="sxs-lookup"><span data-stu-id="0f427-236">**Success**</span></span>|<span data-ttu-id="0f427-237">**int**</span><span class="sxs-lookup"><span data-stu-id="0f427-237">**int**</span></span>|<span data-ttu-id="0f427-238">1 = успешное завершение.</span><span class="sxs-lookup"><span data-stu-id="0f427-238">1 = success.</span></span> <span data-ttu-id="0f427-239">0 = неуспешное завершение.</span><span class="sxs-lookup"><span data-stu-id="0f427-239">0 = failure.</span></span> <span data-ttu-id="0f427-240">Например, значение 1 означает успешную проверку разрешений, а значение 0 означает, что эта проверка не пройдена.</span><span class="sxs-lookup"><span data-stu-id="0f427-240">For example, a value of 1 indicates success of a permissions check and a value of 0 indicates failure of that check.</span></span>|<span data-ttu-id="0f427-241">23</span><span class="sxs-lookup"><span data-stu-id="0f427-241">23</span></span>|<span data-ttu-id="0f427-242">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-242">Yes</span></span>|  
|<span data-ttu-id="0f427-243">**TextData**</span><span class="sxs-lookup"><span data-stu-id="0f427-243">**TextData**</span></span>|<span data-ttu-id="0f427-244">**ntext**</span><span class="sxs-lookup"><span data-stu-id="0f427-244">**ntext**</span></span>|<span data-ttu-id="0f427-245">Текстовое значение, зависящее от класса событий, фиксируемых при трассировке.</span><span class="sxs-lookup"><span data-stu-id="0f427-245">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="0f427-246">1</span><span class="sxs-lookup"><span data-stu-id="0f427-246">1</span></span>|<span data-ttu-id="0f427-247">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-247">Yes</span></span>|  
|<span data-ttu-id="0f427-248">**XactSequence**</span><span class="sxs-lookup"><span data-stu-id="0f427-248">**XactSequence**</span></span>|<span data-ttu-id="0f427-249">**bigint**</span><span class="sxs-lookup"><span data-stu-id="0f427-249">**bigint**</span></span>|<span data-ttu-id="0f427-250">Токен, используемый для описания текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="0f427-250">Token used to describe the current transaction.</span></span>|<span data-ttu-id="0f427-251">50</span><span class="sxs-lookup"><span data-stu-id="0f427-251">50</span></span>|<span data-ttu-id="0f427-252">Да</span><span class="sxs-lookup"><span data-stu-id="0f427-252">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f427-253">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f427-253">See Also</span></span>  
 <span data-ttu-id="0f427-254">[Расширенные события](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="0f427-254">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="0f427-255">Хранимая процедура sp_trace_setevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0f427-255">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  