---
title: Реплика доступности не присоединена | Документы Майкрософт
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp4joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 9c0d10b1-9e12-430c-83b9-ca2bd0a3afc4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7c4f76e98d373e50124f5ca2b135a9fad8f34226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733153"
---
# <a name="availability-replica-is-not-joined"></a><span data-ttu-id="cba2b-102">Реплика доступности не присоединена</span><span class="sxs-lookup"><span data-stu-id="cba2b-102">Availability replica is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="cba2b-103">Введение</span><span class="sxs-lookup"><span data-stu-id="cba2b-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cba2b-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="cba2b-104">**Policy Name**</span></span>|<span data-ttu-id="cba2b-105">Состояние присоединения реплики доступности</span><span class="sxs-lookup"><span data-stu-id="cba2b-105">Availability Replica Join State</span></span>|  
|<span data-ttu-id="cba2b-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="cba2b-106">**Issue**</span></span>|<span data-ttu-id="cba2b-107">Реплика доступности не присоединена.</span><span class="sxs-lookup"><span data-stu-id="cba2b-107">Availability Replica is not joined.</span></span>|  
|<span data-ttu-id="cba2b-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="cba2b-108">**Category**</span></span>|<span data-ttu-id="cba2b-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="cba2b-109">**Warning**</span></span>|  
|<span data-ttu-id="cba2b-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="cba2b-110">**Facet**</span></span>|<span data-ttu-id="cba2b-111">Реплика доступности</span><span class="sxs-lookup"><span data-stu-id="cba2b-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cba2b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cba2b-112">Description</span></span>  
 <span data-ttu-id="cba2b-113">Эта политика проверяет состояние присоединения реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="cba2b-113">This policy checks the join state of the availability replica.</span></span> <span data-ttu-id="cba2b-114">Политика находится в состоянии неисправности, когда реплика доступности добавлена в группу доступности, но она не присоединена с соблюдением всех требований.</span><span class="sxs-lookup"><span data-stu-id="cba2b-114">The policy is in an unhealthy state when the availability replica is added to the availability group, but is not joined properly.</span></span> <span data-ttu-id="cba2b-115">В остальном политика находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="cba2b-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cba2b-116">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях приведены в разделе [Реплика доступности не присоединена](https://go.microsoft.com/fwlink/p/?LinkId=220859) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="cba2b-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220859) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="cba2b-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="cba2b-117">Possible Causes</span></span>  
 <span data-ttu-id="cba2b-118">Вторичная реплика не присоединена к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="cba2b-118">The secondary replica is not joined to the availability group.</span></span> <span data-ttu-id="cba2b-119">Реплика доступности успешно присоединена к группе доступности, когда она имеет состояние присоединения «Присоединенный автономный экземпляр» (1) или «Присоединенный отказоустойчивый кластер» (2).</span><span class="sxs-lookup"><span data-stu-id="cba2b-119">For an availability replica to be successfully joined to the availability group, the join state must be Joined Standalone Instance (1) or Joined Failover Cluster (2).</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="cba2b-120">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="cba2b-120">Possible Solution</span></span>  
 <span data-ttu-id="cba2b-121">Используйте Transact-SQL, PowerShell или среду SQL Server Management Studio для присоединения вторичной реплики к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="cba2b-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="cba2b-122">Дополнительные сведения о присоединении вторичных реплик к группам доступности приведены в разделе [Присоединение вторичной реплики к группе доступности (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="cba2b-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba2b-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="cba2b-123">See Also</span></span>  
 <span data-ttu-id="cba2b-124">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cba2b-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="cba2b-125">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cba2b-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
