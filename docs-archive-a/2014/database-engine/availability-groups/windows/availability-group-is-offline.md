---
title: Группа доступности в режиме вне сети | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp2online.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 093c5208-bf7a-49f4-a546-72b48197cadf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b25e5b22a09783c8dfcad862500b5c0dfcb2c319
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655384"
---
# <a name="availability-group-is-offline"></a><span data-ttu-id="28769-102">Группа доступности в режиме вне сети</span><span class="sxs-lookup"><span data-stu-id="28769-102">Availability group is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="28769-103">Введение</span><span class="sxs-lookup"><span data-stu-id="28769-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28769-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="28769-104">**Policy Name**</span></span>|<span data-ttu-id="28769-105">Режим «в сети» группы доступности</span><span class="sxs-lookup"><span data-stu-id="28769-105">Availability Group Online State</span></span>|  
|<span data-ttu-id="28769-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="28769-106">**Issue**</span></span>|<span data-ttu-id="28769-107">Группа доступности находится в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="28769-107">Availability group is offline.</span></span>|  
|<span data-ttu-id="28769-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="28769-108">**Category**</span></span>|<span data-ttu-id="28769-109">**Критическая**</span><span class="sxs-lookup"><span data-stu-id="28769-109">**Critical**</span></span>|  
|<span data-ttu-id="28769-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="28769-110">**Facet**</span></span>|<span data-ttu-id="28769-111">группа доступности</span><span class="sxs-lookup"><span data-stu-id="28769-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="28769-112">Описание</span><span class="sxs-lookup"><span data-stu-id="28769-112">Description</span></span>  
 <span data-ttu-id="28769-113">Эта политика проверяет состояние группы доступности (режим «в сети» или режим «вне сети»).</span><span class="sxs-lookup"><span data-stu-id="28769-113">This policy checks the online or offline state of the availability group.</span></span> <span data-ttu-id="28769-114">Политика находится в нерабочем состоянии и при переходе кластерного ресурса группы доступности в режим «вне сети» и отсутствии у группы доступности первичной реплики формируется предупреждение.</span><span class="sxs-lookup"><span data-stu-id="28769-114">The policy is in an unhealthy state and an alert is raised when the cluster resource of the availability group is offline or the availability group does not have a primary replica.</span></span>  
  
 <span data-ttu-id="28769-115">Политика находится в рабочем состоянии, если кластерный ресурс группы доступности находится в режиме «в сети», а у группы доступности имеется первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="28769-115">The policy state is healthy when the cluster resource of the availability group is online and the availability group has a primary replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28769-116"> Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях доступны в разделе [Группа доступности в режиме «вне сети»](https://go.microsoft.com/fwlink/p/?LinkId=220850) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="28769-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="28769-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="28769-117">Possible Causes</span></span>  
 <span data-ttu-id="28769-118">Эта проблема могла быть вызвана сбоем в работе экземпляра сервера, на котором размещается первичная реплика, или переходом в режим «вне сети» ресурса группы доступности отказоустойчивого кластера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="28769-118">This issue can be caused by a failure in the server instance that hosts the primary replica or by the Windows Server Failover Cluster (WSFC) availability group resource going offline.</span></span> <span data-ttu-id="28769-119">Ниже перечислены возможные причины работы группы доступности в режиме «вне сети»:</span><span class="sxs-lookup"><span data-stu-id="28769-119">Following are possible causes for the availability group to be offline:</span></span>  
  
-   <span data-ttu-id="28769-120">Для группы доступности не настроен режим автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="28769-120">The availability group is not configured with automatic failover mode.</span></span> <span data-ttu-id="28769-121">Первичная реплика становится недоступной и у всех реплик в группе доступности появляется роль RESOLVING.</span><span class="sxs-lookup"><span data-stu-id="28769-121">The primary replica becomes unavailable and the role of all replicas in the availability group become RESOLVING.</span></span>  
  
    -   <span data-ttu-id="28769-122">Служба экземпляра первичной реплики не работает или не отвечает.</span><span class="sxs-lookup"><span data-stu-id="28769-122">The primary replica instance service is down or unresponsive.</span></span>  
  
    -   <span data-ttu-id="28769-123">В группе доступности произошел разрыв подключения к кластеру.</span><span class="sxs-lookup"><span data-stu-id="28769-123">The availability group has a connectivity issue with the cluster.</span></span>  
  
-   <span data-ttu-id="28769-124">Для группы доступности не настроен режим автоматического перехода на другой ресурс и переход был завершен с ошибками.</span><span class="sxs-lookup"><span data-stu-id="28769-124">The availability group is configured with automatic failover mode and does not complete successfully.</span></span>  
  
    -   <span data-ttu-id="28769-125">При автоматическом переходе на другой ресурс проверка первичной готовности целевой реплики завершается ошибкой, вследствие чего отсутствуют реплики, которые могут стать новой первичной репликой.</span><span class="sxs-lookup"><span data-stu-id="28769-125">During the automatic failover, the primary readiness check on the target replica fails, and there is no replica available to become the new primary.</span></span>  
  
-   <span data-ttu-id="28769-126">Ресурс группы доступности в кластере переходит в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="28769-126">The availability group resource in the cluster becomes offline.</span></span>  
  
    -   <span data-ttu-id="28769-127">В каком-либо из зависимых кластерных ресурсов возникает критическая ошибка и он переходит в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="28769-127">Any dependent cluster resource encounters a critical issue and becomes offline.</span></span> <span data-ttu-id="28769-128">Ресурс группы доступности также находится в режиме «вне сети» до тех пор, пока зависимый ресурс не переходит в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="28769-128">The availability group resource is also offline until the dependent resource becomes online.</span></span>  
  
    -   <span data-ttu-id="28769-129">Произошло отключение ресурса группы доступности вследствие критической ошибки в кластере.</span><span class="sxs-lookup"><span data-stu-id="28769-129">A critical issue in the cluster turns off the availability group resource.</span></span>  
  
-   <span data-ttu-id="28769-130">Для группы доступности выполняется автоматический, выполняемый вручную или принудительный переход на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="28769-130">There is an automatic, manual, or forced failover in progress for the availability group.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="28769-131">Возможные решения</span><span class="sxs-lookup"><span data-stu-id="28769-131">Possible Solutions</span></span>  
 <span data-ttu-id="28769-132">Ниже перечислены возможные решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="28769-132">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="28769-133">При переходе экземпляра SQL Server первичной реплики в нерабочее состояние перезапустите сервер и убедитесь в восстановлении рабочего состояния группы доступности.</span><span class="sxs-lookup"><span data-stu-id="28769-133">If the SQL Server instance of the primary replica is down, restart the server and then verify that the availability group recovers to a healthy state.</span></span>  
  
-   <span data-ttu-id="28769-134">При ошибке автоматического перехода на другой ресурс в случае сбоя убедитесь, что базы данных в реплике синхронизированы с предыдущей первичной репликой, а затем выполните переход на первичную реплику.</span><span class="sxs-lookup"><span data-stu-id="28769-134">If the automatic failover appears to have failed, verify that the databases on the replica are synchronized with the previously known primary replica, and then failover to the primary replica.</span></span> <span data-ttu-id="28769-135">Если базы данных не синхронизированы, выберите реплику с минимальной потерей данных и выполните восстановление до режима отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="28769-135">If the databases are not synchronized, select a replica with a minimum loss of data, and then recover to failover mode.</span></span>  
  
-   <span data-ttu-id="28769-136">Если ресурс в кластере работает в режиме «вне сети», а экземпляры SQL Server находятся в рабочем состоянии, используйте диспетчер отказоустойчивого кластера для проверки работоспособности и других проблем с кластерами на сервере.</span><span class="sxs-lookup"><span data-stu-id="28769-136">If the resource in the cluster is offline while the instances of SQL Server appear to be healthy, use Failover Cluster Manager to check the cluster health or other cluster issues on the server.</span></span> <span data-ttu-id="28769-137">Также можно использовать диспетчер отказоустойчивого кластера для перехода группы доступности в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="28769-137">You can also use the Failover Cluster Manager to attempt to turn the availability group resource online.</span></span>  
  
-   <span data-ttu-id="28769-138">Если выполняется отработка отказа, дождитесь его завершения.</span><span class="sxs-lookup"><span data-stu-id="28769-138">If there is a failover in progress, wait for the failover to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28769-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="28769-139">See Also</span></span>  
 <span data-ttu-id="28769-140">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28769-140">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="28769-141">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="28769-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
