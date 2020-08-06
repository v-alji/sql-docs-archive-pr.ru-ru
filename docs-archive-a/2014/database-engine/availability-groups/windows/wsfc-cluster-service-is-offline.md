---
title: WSFC служба кластеров работает в режиме вне сети | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp1WSFCquorum.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: d502548d-ece6-4a42-9ded-2157d33e3d21
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6e7b48f96eb09638291b1d0655d385d606b1666
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733145"
---
# <a name="wsfc-cluster-service-is-offline"></a><span data-ttu-id="8983f-102">WSFC служба кластеров работает в режиме вне сети</span><span class="sxs-lookup"><span data-stu-id="8983f-102">WSFC cluster service is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="8983f-103">Введение</span><span class="sxs-lookup"><span data-stu-id="8983f-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8983f-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="8983f-104">**Policy Name**</span></span>|<span data-ttu-id="8983f-105">Состояние кластера WSFC</span><span class="sxs-lookup"><span data-stu-id="8983f-105">WSFC Cluster State</span></span>|  
|<span data-ttu-id="8983f-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="8983f-106">**Issue**</span></span>|<span data-ttu-id="8983f-107">Служба кластеров WSFC находится вне сети.</span><span class="sxs-lookup"><span data-stu-id="8983f-107">WSFC cluster service is offline.</span></span>|  
|<span data-ttu-id="8983f-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="8983f-108">**Category**</span></span>|<span data-ttu-id="8983f-109">**Критическая**</span><span class="sxs-lookup"><span data-stu-id="8983f-109">**Critical**</span></span>|  
|<span data-ttu-id="8983f-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="8983f-110">**Facet**</span></span>|<span data-ttu-id="8983f-111">Экземпляр SQL Server</span><span class="sxs-lookup"><span data-stu-id="8983f-111">Instance of SQL Server</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8983f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8983f-112">Description</span></span>  
 <span data-ttu-id="8983f-113">Эта политика проверяет состояние отказоустойчивого кластера Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="8983f-113">This policy checks the state of the Windows Server Failover Cluster (WSFC).</span></span> <span data-ttu-id="8983f-114">Политика находится в неисправном состоянии и выдает предупреждение, если кластер WSFC находится вне сети или в состоянии «принудительный кворум».</span><span class="sxs-lookup"><span data-stu-id="8983f-114">The policy is in an unhealthy state and an alert is raised when the WSFC cluster is offline or in the forced quorum state.</span></span> <span data-ttu-id="8983f-115">Все группы доступности, размещенные на этом кластере, находятся в режиме «вне сети», либо требуется процедура аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="8983f-115">All availability groups hosted within this cluster are offline or a disaster recovery action is required.</span></span>  
  
 <span data-ttu-id="8983f-116">Эта политика находится в исправном состоянии, если состояние кластера — «нормальный кворум».</span><span class="sxs-lookup"><span data-stu-id="8983f-116">The policy state is healthy when the cluster state is in the normal quorum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8983f-117">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], сведения о возможных причинах проблем и решениях приведены в разделе [Служба кластера WSFC не в сети](https://go.microsoft.com/fwlink/p/?LinkId=220849) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="8983f-117">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [WSFC cluster service is offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="8983f-118">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="8983f-118">Possible Causes</span></span>  
 <span data-ttu-id="8983f-119">Эта неполадка может возникать из-за неисправности службы кластера либо при потере кворума в кластере.</span><span class="sxs-lookup"><span data-stu-id="8983f-119">This issue can be caused by a cluster service issue or by the loss of the quorum in the cluster.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="8983f-120">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="8983f-120">Possible Solution</span></span>  
 <span data-ttu-id="8983f-121">Используйте администратор кластеров для запуска процедур принудительного кворума или аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="8983f-121">Use the Cluster Administrator tool to perform the forced quorum or disaster recovery workflow.</span></span> <span data-ttu-id="8983f-122">Если проблему не удается устранить при помощи процедур принудительного кворума или аварийного восстановления, обратитесь к администратору кластера за помощью в устранении этой неполадки.</span><span class="sxs-lookup"><span data-stu-id="8983f-122">If you cannot resolve the issue by performing the forced quorum or disaster recovery, contact your cluster administrator to help resolve this issue.</span></span> <span data-ttu-id="8983f-123">Дополнительные сведения см. в разделе [Принудительный запуск кластера WSFC без кворума](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) электронной документации по [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8983f-123">For more information, see [Force a WSFC Cluster to Start Without a Quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8983f-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="8983f-124">See Also</span></span>  
 <span data-ttu-id="8983f-125">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8983f-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="8983f-126">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8983f-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
