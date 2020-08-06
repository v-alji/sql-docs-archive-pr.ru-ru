---
title: Изменение группы доступности в автономном режиме
description: Действия по настройке группы доступности Always On в автономном режиме
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], take offline
ms.assetid: 50f5aad8-0dff-45ef-8350-f9596d3db898
author: rothja
ms.author: jroth
ms.openlocfilehash: db2f56befe6905b9c3de6bd1ab6a2e5a4a00b1b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665096"
---
# <a name="take-an-availability-group-offline-sql-server"></a><span data-ttu-id="f71cd-103">Перевод группы доступности в режим «вне сети» (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f71cd-103">Take an Availability Group Offline (SQL Server)</span></span>
  <span data-ttu-id="f71cd-104">В этом разделе описывается перевод группы доступности AlwaysOn из состояния ONLINE в состояние OFFLINE с помощью [!INCLUDE[tsql](../includes/tsql-md.md)] в [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f71cd-104">This topic describes how to take an AlwaysOn availability group from the ONLINE state to the OFFLINE state by using [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="f71cd-105">У баз данных с синхронной фиксацией потери данных не происходит, поскольку реплика с синхронной фиксацией не синхронизирована, режим OFFLINE вызывает ошибку, а группа доступности остается в режиме ONLINE.</span><span class="sxs-lookup"><span data-stu-id="f71cd-105">There is no data loss for synchronous-commit databases because if any synchronous-commit replica is not synchronized, the OFFLINE operation raises an error and leaves the availability group ONLINE.</span></span> <span data-ttu-id="f71cd-106">Продолжение работы группы доступности в режиме «в сети» защищает несинхронизированные базы данных с синхронной фиксацией от возможной потери данных.</span><span class="sxs-lookup"><span data-stu-id="f71cd-106">Keeping the availability group online protects unsynchronized synchronous-commit databases from possible data loss.</span></span> <span data-ttu-id="f71cd-107">После перехода группы доступности в режим «вне сети» ее базы данных становятся недоступными для клиентов, при этом невозможно перевести группу доступности обратно в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="f71cd-107">After an availability group goes offline, its databases become unavailable to clients and you cannot bring the availability group back online.</span></span> <span data-ttu-id="f71cd-108">Таким образом, переводить группу доступности в режим «вне сети» следует только в целях миграции ресурсов этой группы доступности с одного кластера WSFC на другой.</span><span class="sxs-lookup"><span data-stu-id="f71cd-108">Therefore, take an availability group offline only to migrate the availability group resources from one WSFC cluster to another.</span></span>  
  
 <span data-ttu-id="f71cd-109">Если во время миграции [!INCLUDE[ssHADR](../includes/sshadr-md.md)]с одного кластера на другой какие-либо приложения подключаются напрямую к первичной реплике группы доступности, то эту группу доступности необходимо перевести в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="f71cd-109">During a cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)], if any applications connect directly to the primary replica of an availability group, the availability group must be taken offline.</span></span> <span data-ttu-id="f71cd-110">Миграция [!INCLUDE[ssHADR](../includes/sshadr-md.md)] поддерживает обновление операционной системы с минимальным временем простоя групп доступности.</span><span class="sxs-lookup"><span data-stu-id="f71cd-110">Cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] supports OS upgrade with minimal downtime of availability groups.</span></span> <span data-ttu-id="f71cd-111">Типичный сценарий — использование миграции [!INCLUDE[ssHADR](../includes/sshadr-md.md)] с одного сервера на другой для обновления до [!INCLUDE[win8](../includes/win8-md.md)] или [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f71cd-111">The typical scenario is to use cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] for OS upgrade to [!INCLUDE[win8](../includes/win8-md.md)] or [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span></span> <span data-ttu-id="f71cd-112">Дополнительные сведения см. в документе [Миграция между кластерами групп доступности AlwaysOn для обновления ОС](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="f71cd-112">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f71cd-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f71cd-113">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f71cd-114">Используйте вариант OFFLINE только для миграции ресурсов группы доступности с одного кластера на другой.</span><span class="sxs-lookup"><span data-stu-id="f71cd-114">Use the OFFLINE option only for a cross-cluster migration of availability group resources.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f71cd-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f71cd-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="f71cd-116">На экземпляре сервера, где вводится команда OFFLINE, должны быть запущены службы [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] или более поздней версии (выпуск Enterprise Edition или более продвинутый выпуск).</span><span class="sxs-lookup"><span data-stu-id="f71cd-116">The server instance on which you enter the OFFLINE command must be running [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="f71cd-117">Группа доступности должна быть в данный момент в сети.</span><span class="sxs-lookup"><span data-stu-id="f71cd-117">The availability group must currently be online.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f71cd-118">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f71cd-118">Recommendations</span></span>  
 <span data-ttu-id="f71cd-119">Прежде чем переводить группу доступности в режим «вне сети», удалите прослушиватели группы доступности.</span><span class="sxs-lookup"><span data-stu-id="f71cd-119">Before you take the availability group offline, delete the availability group listener or listeners.</span></span> <span data-ttu-id="f71cd-120">Дополнительные сведения см. в документе [Удаление прослушивателя группы доступности (SQL Server)](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f71cd-120">For more information, see [Remove an Availability Group Listener &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f71cd-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="f71cd-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f71cd-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="f71cd-122">Permissions</span></span>  
 <span data-ttu-id="f71cd-123">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="f71cd-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f71cd-124">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f71cd-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="f71cd-125">**Перевод группы доступности в режим «вне сети»**</span><span class="sxs-lookup"><span data-stu-id="f71cd-125">**To take an availability group offline**</span></span>  
  
1.  <span data-ttu-id="f71cd-126">Подключитесь к экземпляру сервера, где размещается реплика доступности для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="f71cd-126">Connect to a server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="f71cd-127">Эта реплика может быть первичной или вторичной.</span><span class="sxs-lookup"><span data-stu-id="f71cd-127">This replica can be the primary replica or a secondary replica.</span></span>  
  
2.  <span data-ttu-id="f71cd-128">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f71cd-128">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="f71cd-129">ALTER AVAILABILITY GROUP *имя_группы* OFFLINE</span><span class="sxs-lookup"><span data-stu-id="f71cd-129">ALTER AVAILABILITY GROUP *group_name* OFFLINE</span></span>  
  
     <span data-ttu-id="f71cd-130">где *имя_группы* — это имя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="f71cd-130">where *group_name* is the name of the availability group.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f71cd-131">Пример</span><span class="sxs-lookup"><span data-stu-id="f71cd-131">Example</span></span>  
 <span data-ttu-id="f71cd-132">В следующем примере выполняется перевод группы доступности `AccountsAG` в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="f71cd-132">The following example takes the `AccountsAG` availability group offline.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AccountsAG OFFLINE;  
```  
  
##  <a name="follow-up-after-the-availability-group-goes-offline"></a><a name="FollowUp"></a> <span data-ttu-id="f71cd-133">Дальнейшие действия. После перехода группы доступности в режим "вне сети"</span><span class="sxs-lookup"><span data-stu-id="f71cd-133">Follow Up: After the Availability Group Goes Offline</span></span>  
  
-   <span data-ttu-id="f71cd-134">**Ведение журнала операций OFFLINE**.  Идентификатор узла WSFC, где была инициирована операция OFFLINE, сохраняется как в журнале кластера WSFC, так и в журнале SQL ERRORLOG.</span><span class="sxs-lookup"><span data-stu-id="f71cd-134">**Logging of OFFLINE operation:**  The identity of the WSFC node where the OFFLINE operation was initiated is stored in both the WSFC cluster log and the SQL ERRORLOG.</span></span>  
  
-   <span data-ttu-id="f71cd-135">**Если прослушиватель группы доступности не был удален до перевода группы в автономный режим**.  При переносе группы доступности на другой кластер WSFC удалите имя виртуальной сети и виртуальный IP-адрес прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="f71cd-135">**If you did not delete the availability group listener before taking the group offline:**  If you are migrating the availability group to another WSFC cluster, delete the VNN and VIP of the listener.</span></span> <span data-ttu-id="f71cd-136">Их можно удалить с помощью консоли управления отказоустойчивым кластером либо с помощью командлета [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) PowerShell или [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f71cd-136">You can delete them by using either the Failover Cluster Management console, the [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) PowerShell cmdlet, or [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span></span> <span data-ttu-id="f71cd-137">Обратите внимание, что программа cluster.exe в Windows 8 является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="f71cd-137">Note that cluster.exe is deprecated on Windows 8.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f71cd-138">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f71cd-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f71cd-139">Удаление прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f71cd-139">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](availability-groups/windows/remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="f71cd-140">Смена контекста кластера HADR экземпляра сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f71cd-140">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](availability-groups/windows/change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="f71cd-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f71cd-141">Related Content</span></span>  
  
-   <span data-ttu-id="f71cd-142">[Технические статьи по SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f71cd-142">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="f71cd-143">Блог группы разработчиков SQL Server AlwaysOn: официальный блог группы разработчиков SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f71cd-143">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
## <a name="see-also"></a><span data-ttu-id="f71cd-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="f71cd-144">See Also</span></span>  
 [<span data-ttu-id="f71cd-145">Группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f71cd-145">AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/always-on-availability-groups-sql-server.md)  
