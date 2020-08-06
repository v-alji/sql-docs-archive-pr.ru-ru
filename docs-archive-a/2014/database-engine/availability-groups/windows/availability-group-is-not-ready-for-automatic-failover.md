---
title: Группа доступности не готова для автоматического перехода на другой ресурс | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp3autofailover.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 28261014-342c-442a-bd89-6d04b8d4e8b7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2995ddec51cd70d8a3f209229d0ecb9b0132c79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655387"
---
# <a name="availability-group-is-not-ready-for-automatic-failover"></a><span data-ttu-id="74d6b-102">Группа доступности не готова для автоматического перехода на другой ресурс</span><span class="sxs-lookup"><span data-stu-id="74d6b-102">Availability group is not ready for automatic failover</span></span>
    
## <a name="introduction"></a><span data-ttu-id="74d6b-103">Введение</span><span class="sxs-lookup"><span data-stu-id="74d6b-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74d6b-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="74d6b-104">**Policy Name**</span></span>|<span data-ttu-id="74d6b-105">Готовность группы доступности к автоматическому переходу на другой ресурс при сбое</span><span class="sxs-lookup"><span data-stu-id="74d6b-105">Availability Group Automatic Failover Readiness</span></span>|  
|<span data-ttu-id="74d6b-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="74d6b-106">**Issue**</span></span>|<span data-ttu-id="74d6b-107">Группа доступности не готова к автоматическому переходу на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="74d6b-107">Availability group is not ready for automatic failover.</span></span>|  
|<span data-ttu-id="74d6b-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="74d6b-108">**Category**</span></span>|<span data-ttu-id="74d6b-109">**Критическая**</span><span class="sxs-lookup"><span data-stu-id="74d6b-109">**Critical**</span></span>|  
|<span data-ttu-id="74d6b-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="74d6b-110">**Facet**</span></span>|<span data-ttu-id="74d6b-111">группа доступности</span><span class="sxs-lookup"><span data-stu-id="74d6b-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="74d6b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="74d6b-112">Description</span></span>  
 <span data-ttu-id="74d6b-113">Эта политика проверяет наличие в группе доступности хотя бы одной вторичной реплики, готовой к переходу на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="74d6b-113">This policy checks to verify that the availability group has at least one secondary replica that is failover ready.</span></span> <span data-ttu-id="74d6b-114">Политика находится в нерабочем состоянии и, если для первичной реплики настроен автоматический режим перехода на другой ресурс, но ни одна из вторичных реплик в группе доступности не готова к переходу на другой ресурс, формируется предупреждение.</span><span class="sxs-lookup"><span data-stu-id="74d6b-114">The policy is in an unhealthy state and an alert is raised when the failover mode of the primary replica is automatic, however none of the secondary replicas in the availability group are failover ready.</span></span>  
  
 <span data-ttu-id="74d6b-115">Политика находится в рабочем состоянии, если по крайней мере одна вторичная реплика готова к автоматическому переходу на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="74d6b-115">The policy is in a healthy state when at least one secondary replica is automatic failover ready.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74d6b-116">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях доступны в разделе [Группа доступности не готова для автоматического перехода на другой ресурс](https://go.microsoft.com/fwlink/p/?LinkId=220851) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="74d6b-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is not ready for automatic failover](https://go.microsoft.com/fwlink/p/?LinkId=220851) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="74d6b-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="74d6b-117">Possible Causes</span></span>  
 <span data-ttu-id="74d6b-118">Группа доступности не готова к автоматическому переходу на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="74d6b-118">The availability group is not ready for automatic failover.</span></span> <span data-ttu-id="74d6b-119">Для первичной реплики настроен автоматический переход на другой ресурс. Однако вторичная реплика не готова к автоматическому переходу на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="74d6b-119">The primary replica is configured for automatic failover; however, the secondary replica is not ready for automatic failover.</span></span> <span data-ttu-id="74d6b-120">Вторичная реплика, настроенная для автоматического перехода на другой ресурс, может быть недоступна, или ее состояние синхронизации данных в настоящий момент отлично от SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="74d6b-120">The secondary replica that is configured for automatic failover might be unavailable or its data synchronization state is currently not SYNCHRONIZED.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="74d6b-121">Возможные решения</span><span class="sxs-lookup"><span data-stu-id="74d6b-121">Possible Solutions</span></span>  
 <span data-ttu-id="74d6b-122">Ниже перечислены возможные решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="74d6b-122">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="74d6b-123">Убедитесь, что по крайней мере для одной вторичной реплики настроен автоматический переход на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="74d6b-123">Verify that at least one secondary replica is configured as automatic failover.</span></span> <span data-ttu-id="74d6b-124">При отсутствии вторичных реплик, для которых настроен автоматический переход на другой ресурс, обновите конфигурацию вторичной реплики для настройки ее в качестве целевой реплики для автоматического перехода на другой ресурс с синхронной фиксацией.</span><span class="sxs-lookup"><span data-stu-id="74d6b-124">If there is not a secondary replica configured as automatic failover, update the configuration of a secondary replica to be the automatic failover target with synchronous commit.</span></span>  
  
-   <span data-ttu-id="74d6b-125">Используйте политику, чтобы убедиться, что данные находятся в состоянии синхронизации, и что у целевого узла автоматического перехода на другой ресурс имеется состояние SYNCHRONIZED, а затем устраните проблему в реплике доступности.</span><span class="sxs-lookup"><span data-stu-id="74d6b-125">Use the policy to verify that the data is in a synchronization state and the automatic failover target is SYNCHRONIZED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d6b-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="74d6b-126">See Also</span></span>  
 <span data-ttu-id="74d6b-127">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="74d6b-127">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="74d6b-128">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="74d6b-128">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
