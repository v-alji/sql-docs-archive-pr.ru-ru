---
title: Настройка параметра конфигурации сервера max worker threads | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- worker threads [SQL Server]
- max worker threads option
ms.assetid: abeadfa4-a14d-469a-bacf-75812e48fac1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4881cefee350d34d93b539c56be6f43866d3ddfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665562"
---
# <a name="configure-the-max-worker-threads-server-configuration-option"></a><span data-ttu-id="9efd8-102">Настройка параметра конфигурации сервера max worker threads</span><span class="sxs-lookup"><span data-stu-id="9efd8-102">Configure the max worker threads Server Configuration Option</span></span>
  <span data-ttu-id="9efd8-103">В этом разделе описываются способы настройки параметра конфигурации сервера **max worker threads** в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9efd8-103">This topic describes how to configure the **max worker threads** server configuration option in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9efd8-104">Параметр **max worker threads** используется для установки количества рабочих потоков, доступных процессам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9efd8-104">The **max worker threads** option configures the number of worker threads that are available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9efd8-105">используются собственные службы для потоков операционных систем, поэтому один или несколько потоков одновременно поддерживают все сети, которые поддерживает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , еще один поток обрабатывает контрольные точки базы данных, а пул потоков обрабатывает запросы от всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="9efd8-105">uses the native thread services of the operating systems so that one or more threads support each network that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports simultaneously, another thread handles database checkpoints, and a pool of threads handles all users.</span></span> <span data-ttu-id="9efd8-106">Значение по умолчанию для параметра **max worker threads** — 0.</span><span class="sxs-lookup"><span data-stu-id="9efd8-106">The default value for **max worker threads** is 0.</span></span> <span data-ttu-id="9efd8-107">Это позволяет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически настраивать количество рабочих потоков при запуске.</span><span class="sxs-lookup"><span data-stu-id="9efd8-107">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically configure the number of worker threads at startup.</span></span> <span data-ttu-id="9efd8-108">Настройка по умолчанию является оптимальной для большинства систем.</span><span class="sxs-lookup"><span data-stu-id="9efd8-108">The default setting is best for most systems.</span></span> <span data-ttu-id="9efd8-109">Но иногда, в зависимости от конфигурации системы, установка параметра **max worker threads** в другое определенное значение может улучшить производительность.</span><span class="sxs-lookup"><span data-stu-id="9efd8-109">However, depending on your system configuration, setting **max worker threads** to a specific value sometimes improves performance.</span></span>  
  
 <span data-ttu-id="9efd8-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="9efd8-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9efd8-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="9efd8-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9efd8-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9efd8-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9efd8-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9efd8-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="9efd8-114">Безопасность</span><span class="sxs-lookup"><span data-stu-id="9efd8-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9efd8-115">**Настройка параметра max worker threads с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="9efd8-115">**To configure the max worker threads option, using:**</span></span>  
  
     [<span data-ttu-id="9efd8-116">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9efd8-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9efd8-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9efd8-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="9efd8-118">**Дальнейшие действия.**  [После настройки параметра max worker threads](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="9efd8-118">**Follow Up:**  [After you configure the max worker threads option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9efd8-119">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9efd8-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9efd8-120">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9efd8-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9efd8-121">Если реальное количество запросов меньше значения, заданного параметром **max worker threads**, каждый запрос обрабатывается одним потоком.</span><span class="sxs-lookup"><span data-stu-id="9efd8-121">When the actual number of query requests is less than the amount set in **max worker threads**, one thread handles each query request.</span></span> <span data-ttu-id="9efd8-122">Однако если фактическое число запросов превышает объем, заданный в параметре **max worker threads**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Пулы рабочих потоков следует использовать, чтобы следующий доступный рабочий поток мог справиться с запросом.</span><span class="sxs-lookup"><span data-stu-id="9efd8-122">However, if the actual number of query request exceeds the amount set in **max worker threads**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pools the worker threads so that the next available worker thread can handle the request.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9efd8-123">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9efd8-123">Recommendations</span></span>  
  
-   <span data-ttu-id="9efd8-124">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9efd8-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="9efd8-125">Пул потоков помогает оптимизировать производительность при подключении к серверу большого числа пользователей.</span><span class="sxs-lookup"><span data-stu-id="9efd8-125">Thread pooling helps optimize performance when large numbers of clients are connected to the server.</span></span> <span data-ttu-id="9efd8-126">Обычно для каждого запроса в операционной системе создается отдельный поток.</span><span class="sxs-lookup"><span data-stu-id="9efd8-126">Usually, a separate operating system thread is created for each query request.</span></span> <span data-ttu-id="9efd8-127">Однако в случае сотен соединений с сервером, использование одного потока на каждый запрос приводит к потреблению большого числа системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9efd8-127">However, with hundreds of connections to the server, using one thread per query request can consume large amounts of system resources.</span></span> <span data-ttu-id="9efd8-128">Параметр **max worker threads** позволяет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создавать пул рабочих потоков, чтобы обслужить большое число запросов, что улучшает производительность.</span><span class="sxs-lookup"><span data-stu-id="9efd8-128">The **max worker threads** option enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to create a pool of worker threads to service a larger number of query requests, which improves performance.</span></span>  
  
-   <span data-ttu-id="9efd8-129">В следующей таблице показано автоматически настраиваемое максимальное число рабочих потоков для различных сочетаний процессоров и версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9efd8-129">The following table shows the automatically configured number of max worker threads for various combinations of CPUs and versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    |<span data-ttu-id="9efd8-130">Число процессоров</span><span class="sxs-lookup"><span data-stu-id="9efd8-130">Number of CPUs</span></span>|<span data-ttu-id="9efd8-131">32-разрядный компьютер</span><span class="sxs-lookup"><span data-stu-id="9efd8-131">32-bit computer</span></span>|<span data-ttu-id="9efd8-132">64-разрядный компьютер</span><span class="sxs-lookup"><span data-stu-id="9efd8-132">64-bit computer</span></span>|  
    |--------------------|----------------------|----------------------|  
    |<span data-ttu-id="9efd8-133">\< — 4 процессора</span><span class="sxs-lookup"><span data-stu-id="9efd8-133">\<= 4 processors</span></span>|<span data-ttu-id="9efd8-134">256</span><span class="sxs-lookup"><span data-stu-id="9efd8-134">256</span></span>|<span data-ttu-id="9efd8-135">512</span><span class="sxs-lookup"><span data-stu-id="9efd8-135">512</span></span>|  
    |<span data-ttu-id="9efd8-136">8 процессоров</span><span class="sxs-lookup"><span data-stu-id="9efd8-136">8 processors</span></span>|<span data-ttu-id="9efd8-137">288</span><span class="sxs-lookup"><span data-stu-id="9efd8-137">288</span></span>|<span data-ttu-id="9efd8-138">576</span><span class="sxs-lookup"><span data-stu-id="9efd8-138">576</span></span>|  
    |<span data-ttu-id="9efd8-139">16 процессоров</span><span class="sxs-lookup"><span data-stu-id="9efd8-139">16 processors</span></span>|<span data-ttu-id="9efd8-140">352</span><span class="sxs-lookup"><span data-stu-id="9efd8-140">352</span></span>|<span data-ttu-id="9efd8-141">704</span><span class="sxs-lookup"><span data-stu-id="9efd8-141">704</span></span>|  
    |<span data-ttu-id="9efd8-142">32 процессора</span><span class="sxs-lookup"><span data-stu-id="9efd8-142">32 processors</span></span>|<span data-ttu-id="9efd8-143">480</span><span class="sxs-lookup"><span data-stu-id="9efd8-143">480</span></span>|<span data-ttu-id="9efd8-144">960</span><span class="sxs-lookup"><span data-stu-id="9efd8-144">960</span></span>|  
    |<span data-ttu-id="9efd8-145">64 процессора</span><span class="sxs-lookup"><span data-stu-id="9efd8-145">64 processors</span></span>|<span data-ttu-id="9efd8-146">736</span><span class="sxs-lookup"><span data-stu-id="9efd8-146">736</span></span>|<span data-ttu-id="9efd8-147">1472</span><span class="sxs-lookup"><span data-stu-id="9efd8-147">1472</span></span>|  
    |<span data-ttu-id="9efd8-148">128 процессоров</span><span class="sxs-lookup"><span data-stu-id="9efd8-148">128 processors</span></span>|<span data-ttu-id="9efd8-149">4224</span><span class="sxs-lookup"><span data-stu-id="9efd8-149">4224</span></span>|<span data-ttu-id="9efd8-150">4480</span><span class="sxs-lookup"><span data-stu-id="9efd8-150">4480</span></span>|  
    |<span data-ttu-id="9efd8-151">256 процессоров</span><span class="sxs-lookup"><span data-stu-id="9efd8-151">256 processors</span></span>|<span data-ttu-id="9efd8-152">8320</span><span class="sxs-lookup"><span data-stu-id="9efd8-152">8320</span></span>|<span data-ttu-id="9efd8-153">8576</span><span class="sxs-lookup"><span data-stu-id="9efd8-153">8576</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="9efd8-154">Рекомендации по использованию процессоров в количестве, превышающем 64, см. в разделе [Рекомендации по использованию SQL Server на компьютерах, которые имеют более 64 процессоров](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="9efd8-154">For recommendations on using more than 64 CPUs, refer to [Best Practices for Running SQL Server on Computers That Have More Than 64 CPUs](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="9efd8-155">Для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , работающего в 32-разрядном компьютере, рекомендуется ограничить число рабочих потоков до 1024.</span><span class="sxs-lookup"><span data-stu-id="9efd8-155">We recommend 1024 as the maximum number of worker threads for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on a 32-bit computer.</span></span>  
  
-   <span data-ttu-id="9efd8-156">Если все рабочие потоки заняты выполнением длительных запросов, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может не отвечать на другие запросы, пока один из потоков не завершит работу и не станет доступным.</span><span class="sxs-lookup"><span data-stu-id="9efd8-156">When all worker threads are active with long running queries, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might appear unresponsive until a worker thread completes and becomes available.</span></span> <span data-ttu-id="9efd8-157">Хотя это и не ошибка, такое поведение иногда нежелательно.</span><span class="sxs-lookup"><span data-stu-id="9efd8-157">Although this is not a defect, it can sometimes be undesirable.</span></span> <span data-ttu-id="9efd8-158">Если процесс не отвечает и новые запросы не могут быть обработаны, подключитесь к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] через выделенное административное соединение (DAC) и уничтожьте процесс.</span><span class="sxs-lookup"><span data-stu-id="9efd8-158">If a process appears to be unresponsive and no new queries can be processed, then connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the dedicated administrator connection (DAC), and kill the process.</span></span> <span data-ttu-id="9efd8-159">Во избежание этого увеличьте максимальное число потоков управления.</span><span class="sxs-lookup"><span data-stu-id="9efd8-159">To prevent this, increase the number of max worker threads.</span></span>  
  
 <span data-ttu-id="9efd8-160">Параметр конфигурации сервера **max worker threads** не учитывает потоки, которые необходимы для всех системных задач, таких как группы доступности, компонент Service Broker, диспетчер блокировок и другие.</span><span class="sxs-lookup"><span data-stu-id="9efd8-160">The **max worker threads** server configuration option does not take into account threads that are required for all the system tasks such as Availibility Groups, Service Broker, Lock Manager, and others.</span></span>  <span data-ttu-id="9efd8-161">Если число настроенных потоков превышается, то следующий запрос будет содержать сведения о системных задачах, породивших дополнительные потоки.</span><span class="sxs-lookup"><span data-stu-id="9efd8-161">If the number of threads configured are being exceeded, the following query will provide information about the system tasks that have spawned the additional threads.</span></span>  
  
```  
SELECT  
s.session_id,  
r.command,  
r.status,  
r.wait_type,  
r.scheduler_id,  
w.worker_address,  
w.is_preemptive,  
w.state,  
t.task_state,  
t.session_id,  
t.exec_context_id,  
t.request_id  
FROM sys.dm_exec_sessions AS s  
INNERJOIN sys.dm_exec_requests AS r  
    ON s.session_id = r.session_id  
INNER JOIN sys.dm_os_tasks AS t  
    ON r.task_address = t.task_address  
INNER JOIN sys.dm_os_workers AS w  
    ON t.worker_address = w.worker_address  
WHERE s.is_user_process = 0;  
  
```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9efd8-162">безопасность</span><span class="sxs-lookup"><span data-stu-id="9efd8-162">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9efd8-163">Permissions</span><span class="sxs-lookup"><span data-stu-id="9efd8-163">Permissions</span></span>  
 <span data-ttu-id="9efd8-164">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="9efd8-164">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="9efd8-165">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="9efd8-165">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="9efd8-166">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="9efd8-166">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9efd8-167">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9efd8-167">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="9efd8-168">Настройка параметра max worker threads</span><span class="sxs-lookup"><span data-stu-id="9efd8-168">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="9efd8-169">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9efd8-169">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="9efd8-170">Щелкните узел **Процессоры** .</span><span class="sxs-lookup"><span data-stu-id="9efd8-170">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="9efd8-171">В поле **max worker threads (максимальное число рабочих потоков** ) введите или выберите значение от 128 до 32767.</span><span class="sxs-lookup"><span data-stu-id="9efd8-171">In the **Max worker threads** box, type or select a value from 128 through 32767.</span></span>  
  
     <span data-ttu-id="9efd8-172">Используйте параметр **max worker threads** для установки количества рабочих потоков, доступных процессам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9efd8-172">Use the **max worker threads** option to configure the number of worker threads available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> <span data-ttu-id="9efd8-173">Значение по умолчанию параметра **max worker threads** является оптимальным для большинства систем.</span><span class="sxs-lookup"><span data-stu-id="9efd8-173">The default setting for **max worker threads** is best for most systems.</span></span> <span data-ttu-id="9efd8-174">Но в зависимости от конфигурации системы установка параметра **max worker threads** в меньшее значение может улучшить производительность.</span><span class="sxs-lookup"><span data-stu-id="9efd8-174">However, depending on your system configuration, setting **max worker threads** to a smaller value sometimes improves performance.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9efd8-175">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9efd8-175">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="9efd8-176">Настройка параметра max worker threads</span><span class="sxs-lookup"><span data-stu-id="9efd8-176">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="9efd8-177">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9efd8-177">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9efd8-178">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="9efd8-178">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9efd8-179">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="9efd8-179">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9efd8-180">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `max worker threads` равным `900`.</span><span class="sxs-lookup"><span data-stu-id="9efd8-180">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max worker threads` option to `900`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'max worker threads', 900 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="9efd8-181">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9efd8-181">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-worker-threads-option"></a><a name="FollowUp"></a> <span data-ttu-id="9efd8-182">Дальнейшие действия. После настройки параметра "Максимальное количество рабочих потоков"</span><span class="sxs-lookup"><span data-stu-id="9efd8-182">Follow Up: After you configure the max worker threads option</span></span>  
 <span data-ttu-id="9efd8-183">Изменения вступят в силу немедленно без необходимости перезапуска компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9efd8-183">The change will take effect immediately without requiring the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efd8-184">См. также:</span><span class="sxs-lookup"><span data-stu-id="9efd8-184">See Also</span></span>  
 <span data-ttu-id="9efd8-185">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9efd8-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="9efd8-186">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9efd8-186">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="9efd8-187">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9efd8-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="9efd8-188">Диагностическое соединение для администраторов баз данных</span><span class="sxs-lookup"><span data-stu-id="9efd8-188">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
