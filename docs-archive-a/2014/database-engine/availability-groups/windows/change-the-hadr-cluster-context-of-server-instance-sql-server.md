---
title: Смена контекста кластера HADR экземпляра сервера (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- Availability replicas [SQL Server], change WSFC cluster context
ms.assetid: ecd99f91-b9a2-4737-994e-507065a12f80
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbc29fa2ebaaf2bbc9e577b5bd303e8a0dd0ec4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750215"
---
# <a name="change-the-hadr-cluster-context-of-server-instance-sql-server"></a><span data-ttu-id="48260-102">Смена контекста кластера HADR экземпляра сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-102">Change the HADR Cluster Context of Server Instance (SQL Server)</span></span>
  <span data-ttu-id="48260-103">В этом разделе описывается переключение контекста кластера HADR экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью [!INCLUDE[tsql](../../../includes/tsql-md.md)] в [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="48260-103">This topic describes how to switch the HADR cluster context of an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="48260-104">*Контекст кластера HADR* определяет кластер отказоустойчивой кластеризации Windows Server (WSFC), который управляет метаданными для реплик доступности, размещенных в экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="48260-104">The *HADR cluster context* determines which Windows Server Failover Clustering (WSFC) cluster manages the metadata for availability replicas hosted by the server instance.</span></span>  
  
 <span data-ttu-id="48260-105">Переключать контекст кластера HADR следует только во время миграции с кластера [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] на экземпляр [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] в новом кластере WSFC.</span><span class="sxs-lookup"><span data-stu-id="48260-105">Switch the HADR cluster context only during a cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] to an instance of [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] on a new WSFC cluster.</span></span> <span data-ttu-id="48260-106">Миграция с кластера [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] поддерживает обновление операционной системы до [!INCLUDE[win8](../../../includes/win8-md.md)] или [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] с минимальным временем простоя групп доступности.</span><span class="sxs-lookup"><span data-stu-id="48260-106">Cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] supports OS upgrade to [!INCLUDE[win8](../../../includes/win8-md.md)] or [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] with minimal downtime of availability groups.</span></span> <span data-ttu-id="48260-107">Дополнительные сведения см. в документе [Миграция между кластерами групп доступности AlwaysOn для обновления ОС](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="48260-107">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="48260-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="48260-108">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="48260-109">Переключать контекст кластера HADR следует только во время миграции между кластерами развертываний [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48260-109">Switch the HADR cluster context only during cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] deployments.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="48260-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="48260-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="48260-111">Переключать контекст кластера HADR можно только с локального кластера WSFC на удаленный и обратно с удаленного кластера на локальный.</span><span class="sxs-lookup"><span data-stu-id="48260-111">You can switch the HADR cluster context only from the local WSFC cluster to a remote cluster and then back from the remote cluster to the local cluster.</span></span> <span data-ttu-id="48260-112">Нельзя переключить контекст кластера HADR с одного удаленного кластера на другой удаленный кластер.</span><span class="sxs-lookup"><span data-stu-id="48260-112">You cannot switch the HADR cluster context from one remote cluster to another remote cluster.</span></span>  
  
-   <span data-ttu-id="48260-113">Контекст кластера HADR можно переключить на удаленный кластер, только если на экземпляре SQL Server не размещено ни одной реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="48260-113">The HADR cluster context can be switched to a remote cluster only when the instance of SQL Server is not hosting any availability replicas.</span></span>  
  
-   <span data-ttu-id="48260-114">Удаленный контекст кластера HADR можно переключить обратно на локальный кластер в любое время.</span><span class="sxs-lookup"><span data-stu-id="48260-114">A remote HADR cluster context can be switched back to the local cluster at any time.</span></span> <span data-ttu-id="48260-115">Однако контекст нельзя переключать повторно, пока на экземпляре сервера содержатся реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="48260-115">However, the context cannot be switched again as long as the server instance is hosting any availability replicas.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="48260-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="48260-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="48260-117">На экземпляре сервера, на котором необходимо изменить контекст кластера HADR, должна выполняться [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] или более новая версия (выпуск Enterprise Edition или выше).</span><span class="sxs-lookup"><span data-stu-id="48260-117">The server instance on which you change the HADR cluster context must be running [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="48260-118">Экземпляр сервера должен быть включен для AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="48260-118">The server instance must be enabled for AlwaysOn.</span></span> <span data-ttu-id="48260-119">Дополнительные сведения см. в разделе [Включение и отключение групп доступности AlwaysOn (SQL Server)](enable-and-disable-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="48260-119">For more information, see [Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="48260-120">Чтобы отвечать требованиям к переключению с контекста локального кластера на контекст удаленного кластера, на экземпляре сервера не могут размещаться реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="48260-120">To be eligible to be switched from the local cluster context to a remote cluster cluster, a server instance cannot be hosting any availability replicas.</span></span> <span data-ttu-id="48260-121">Представление каталога [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) не должно возвращать строк.</span><span class="sxs-lookup"><span data-stu-id="48260-121">The [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) catalog view should not return any rows.</span></span>  
  
     <span data-ttu-id="48260-122">Если на экземпляре сервера существуют реплики доступности, то перед изменением контекста кластера HADR необходимо выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="48260-122">If any availability replicas exist on the server instance, before you can change the HADR cluster context, you must do one of the following:</span></span>  
  
    |<span data-ttu-id="48260-123">Роль реплики</span><span class="sxs-lookup"><span data-stu-id="48260-123">Replica Role</span></span>|<span data-ttu-id="48260-124">Действие</span><span class="sxs-lookup"><span data-stu-id="48260-124">Action</span></span>|<span data-ttu-id="48260-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="48260-125">Link</span></span>|  
    |------------------|------------|----------|  
    |<span data-ttu-id="48260-126">Первичная</span><span class="sxs-lookup"><span data-stu-id="48260-126">Primary</span></span>|<span data-ttu-id="48260-127">Перевод группы доступности в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="48260-127">Take the availability group offline.</span></span>|[<span data-ttu-id="48260-128">Перевод группы доступности в режим "вне сети" (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-128">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)|  
    |<span data-ttu-id="48260-129">Вторичная</span><span class="sxs-lookup"><span data-stu-id="48260-129">Secondary</span></span>|<span data-ttu-id="48260-130">Удалить реплику из ее группы доступности</span><span class="sxs-lookup"><span data-stu-id="48260-130">Remove the replica from its availability group</span></span>|[<span data-ttu-id="48260-131">Удаление вторичной реплики из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-131">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)|  
  
-   <span data-ttu-id="48260-132">Перед тем как станет возможным переключение с удаленного кластера на локальный кластер, все локальные реплики с синхронной фиксацией должны перейти в состояние SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="48260-132">Before you can switch from a remote cluster to the local cluster, all synchronous-commit replicas must be SYNCHRONIZED.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="48260-133">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="48260-133">Recommendations</span></span>  
  
-   <span data-ttu-id="48260-134">Рекомендуется указывать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="48260-134">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="48260-135">Это необходимо потому, что для поиска целевого IP-адреса короткого имени ALTER SERVER CONFIGURATION использует разрешение DNS.</span><span class="sxs-lookup"><span data-stu-id="48260-135">This is because to find the target IP address of a short name, ALTER SERVER CONFIGURATION uses DNS resolution.</span></span> <span data-ttu-id="48260-136">В некоторых ситуациях в зависимости от порядка поиска DNS использование кратких имен может вызвать затруднения.</span><span class="sxs-lookup"><span data-stu-id="48260-136">Under some situations, depending on the DNS searching order, using a short name could cause confusion.</span></span> <span data-ttu-id="48260-137">Например, рассмотрим следующую команду, которая выполняется на узле в домене `abc` (`node1.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="48260-137">For example, consider the following command, which is executed on a node in the `abc` domain, (`node1.abc.com`).</span></span> <span data-ttu-id="48260-138">Целевым кластером назначения является кластер `CLUS01` в домене `xyz` (`clus01.xyz.com`).</span><span class="sxs-lookup"><span data-stu-id="48260-138">The intended destination cluster is the `CLUS01` cluster in the `xyz` domain (`clus01.xyz.com`).</span></span> <span data-ttu-id="48260-139">Однако на узлах локального домена также размещен кластер с именем `CLUS01` (`clus01.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="48260-139">However, the local  domain hosts also hosts a cluster named `CLUS01` (`clus01.abc.com`).</span></span>  
  
     <span data-ttu-id="48260-140">Если было указано короткое имя целевого кластера `CLUS01`, разрешение имени DNS может вернуть IP-адрес неправильного кластера `clus01.abc.com`.</span><span class="sxs-lookup"><span data-stu-id="48260-140">If the short name of the target cluster, `CLUS01`, were specified, DNS name resolution could return the IP address of the wrong cluster, `clus01.abc.com`.</span></span> <span data-ttu-id="48260-141">Чтобы избежать подобной путаницы, указывайте полное имя целевого кластера, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="48260-141">To avoid such confusion, specify the full name of the target cluster, as in the following example:</span></span>  
  
    ```  
    ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com'  
    ```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="48260-142">безопасность</span><span class="sxs-lookup"><span data-stu-id="48260-142">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="48260-143">Permissions</span><span class="sxs-lookup"><span data-stu-id="48260-143">Permissions</span></span>  
  
-   <span data-ttu-id="48260-144">**Имя входа SQL Server**</span><span class="sxs-lookup"><span data-stu-id="48260-144">**SQL Server login**</span></span>  
  
     <span data-ttu-id="48260-145">Необходимо разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="48260-145">Requires CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="48260-146">**Учетная запись службы SQL Server**</span><span class="sxs-lookup"><span data-stu-id="48260-146">**SQL Server service account**</span></span>  
  
     <span data-ttu-id="48260-147">Учетная запись службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] экземпляра сервера должна иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="48260-147">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account of the server instance must have:</span></span>  
  
    -   <span data-ttu-id="48260-148">Разрешение на открытие целевого кластера WSFC.</span><span class="sxs-lookup"><span data-stu-id="48260-148">Permission to open the destination WSFC cluster.</span></span>  
  
    -   <span data-ttu-id="48260-149">Доступ в режиме чтения или записи к удаленному WSFC.</span><span class="sxs-lookup"><span data-stu-id="48260-149">Remote WSFC read-write access.</span></span>  
  
 
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="48260-150">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="48260-150">Using Transact-SQL</span></span>  
 <span data-ttu-id="48260-151">**Изменение контекста кластера WSFC для реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="48260-151">**To change the WSFC cluster context of an availability replica**</span></span>  
  
1.  <span data-ttu-id="48260-152">Подключитесь к экземпляру сервера, на котором размещена либо первичная, либо вторичная реплика группы доступности.</span><span class="sxs-lookup"><span data-stu-id="48260-152">Connect to the server instance that hosts either the primary replica or a secondary replica of the availability group.</span></span>  
  
2.  <span data-ttu-id="48260-153">Используйте предложение SET HADR CLUSTER CONTEXT инструкции [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="48260-153">Use the SET HADR CLUSTER CONTEXT clause of the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="48260-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **' *`windows_cluster`* '** | Языковые</span><span class="sxs-lookup"><span data-stu-id="48260-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **'*`windows_cluster`*'** | LOCAL }</span></span>  
  
     <span data-ttu-id="48260-155">где</span><span class="sxs-lookup"><span data-stu-id="48260-155">where,</span></span>  
  
     <span data-ttu-id="48260-156">*кластер_windows*</span><span class="sxs-lookup"><span data-stu-id="48260-156">*windows_cluster*</span></span>  
     <span data-ttu-id="48260-157">Объект имени WSFC-кластера (CNO).</span><span class="sxs-lookup"><span data-stu-id="48260-157">The cluster object name (CON) of a WSFC cluster.</span></span> <span data-ttu-id="48260-158">Вы можете указать короткое имя или полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="48260-158">You can specify either the short name or the full domain name.</span></span> <span data-ttu-id="48260-159">Рекомендуется указывать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="48260-159">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="48260-160">Дополнительные сведения см. в разделе [рекомендации](#Recommendations)ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="48260-160">For more information, see [Recommendations](#Recommendations), earlier in this topic.</span></span>  
  
     <span data-ttu-id="48260-161">LOCAL</span><span class="sxs-lookup"><span data-stu-id="48260-161">LOCAL</span></span>  
     <span data-ttu-id="48260-162">Локальный кластер WSFC.</span><span class="sxs-lookup"><span data-stu-id="48260-162">The local WSFC cluster.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="48260-163">Примеры</span><span class="sxs-lookup"><span data-stu-id="48260-163">Examples</span></span>  
 <span data-ttu-id="48260-164">В следующем примере выполняется смена контекста кластера HADR на другой кластер.</span><span class="sxs-lookup"><span data-stu-id="48260-164">The following example changes the HADR cluster context to a different cluster.</span></span> <span data-ttu-id="48260-165">Для определения целевого кластера WSFC `clus01`в примере указывается полное имя объекта кластера `clus01.xyz.com`.</span><span class="sxs-lookup"><span data-stu-id="48260-165">To identify the destination WSFC cluster, `clus01`, the example specifies the full cluster object name, `clus01.xyz.com`.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com';  
```  
  
 <span data-ttu-id="48260-166">В следующем примере выполняется смена контекста кластера HADR на локальный кластер WSFC.</span><span class="sxs-lookup"><span data-stu-id="48260-166">The following example changes the HADR cluster context to the local WSFC cluster.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = LOCAL;  
```  
  

  
##  <a name="follow-up-after-switching-the-cluster-context-of-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="48260-167">Дальнейшие действия. После переключения контекста кластера реплики доступности</span><span class="sxs-lookup"><span data-stu-id="48260-167">Follow Up: After Switching the Cluster Context of an Availability Replica</span></span>  
 <span data-ttu-id="48260-168">Новый контекст кластера HADR вступает в силу сразу, без перезапуска экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="48260-168">The new HADR cluster context takes effect immediately, without restarting the server instance.</span></span> <span data-ttu-id="48260-169">Настройка контекста кластера HADR является постоянной установкой уровня экземпляра, которая остается неизменной при перезапуске экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="48260-169">The HADR cluster context setting is a persistent instance-level setting that remains unchanged if the server instance restarts.</span></span>  
  
 <span data-ttu-id="48260-170">Проверить новый контекст кластера HADR можно, выполнив запрос к динамическому административному представлению [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="48260-170">Confirm the new HADR cluster context by querying the [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) dynamic management view, as follows:</span></span>  
  
```  
SELECT cluster_name FROM sys.dm_hadr_cluster  
```  
  
 <span data-ttu-id="48260-171">Этот запрос должен возвращать имя кластера, на который был переключен контекст кластера HADR.</span><span class="sxs-lookup"><span data-stu-id="48260-171">This query should return the name of the cluster to which you set the HADR cluster context.</span></span>  
  
 <span data-ttu-id="48260-172">Если контекст кластера HADR был переключен на новый кластер.</span><span class="sxs-lookup"><span data-stu-id="48260-172">When the HADR cluster context is switched to a new cluster:</span></span>  
  
-   <span data-ttu-id="48260-173">Выполняется очистка метаданных для всех реплик доступности, которые в настоящее время размещены в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48260-173">The metadata is cleaned up for any availability replicas that are currently hosted by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="48260-174">Все базы данных, которые ранее принадлежали к реплике доступности, теперь находятся в состоянии RESTORING.</span><span class="sxs-lookup"><span data-stu-id="48260-174">All the databases that previously belonged to an availability replica are now in the RESTORING state.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="48260-175">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="48260-175">Related Tasks</span></span>  
  
-   [<span data-ttu-id="48260-176">Удаление прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-176">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="48260-177">Перевод группы доступности в режим "вне сети" (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-177">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
-   [<span data-ttu-id="48260-178">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="48260-179">Удаление вторичной реплики из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-179">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="48260-180">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-180">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="48260-181">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48260-181">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
 
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="48260-182">См. также</span><span class="sxs-lookup"><span data-stu-id="48260-182">Related Content</span></span>  
  
-   <span data-ttu-id="48260-183">[Технические статьи по SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="48260-183">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="48260-184">Блог группы разработчиков SQL Server AlwaysOn: официальный блог группы разработчиков SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="48260-184">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="48260-185">См. также:</span><span class="sxs-lookup"><span data-stu-id="48260-185">See Also</span></span>  
 <span data-ttu-id="48260-186">[Отказоустойчивая кластеризация Windows Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) [группы доступности AlwaysOn (SQL Server)](always-on-availability-groups-sql-server.md) &#40;&#41; WSFC с SQL Server </span><span class="sxs-lookup"><span data-stu-id="48260-186">[AlwaysOn Availability Groups (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="48260-187">ALTER SERVER CONFIGURATION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="48260-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-server-configuration-transact-sql)  
  
  
