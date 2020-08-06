---
title: Некоторые реплики доступности отключены | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp7allconnected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: aea808be-6f0f-40c2-9aa2-a2a435ec6443
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1bb6535b513770b9b4718a0e8372c0a5bc3cba84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664505"
---
# <a name="some-availability-replicas-are-disconnected"></a><span data-ttu-id="216d4-102">Некоторые реплики доступности отключены</span><span class="sxs-lookup"><span data-stu-id="216d4-102">Some availability replicas are disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="216d4-103">Введение</span><span class="sxs-lookup"><span data-stu-id="216d4-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="216d4-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="216d4-104">**Policy Name**</span></span>|<span data-ttu-id="216d4-105">Состояние соединения с репликами доступности</span><span class="sxs-lookup"><span data-stu-id="216d4-105">Availability Replicas Connection State</span></span>|  
|<span data-ttu-id="216d4-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="216d4-106">**Issue**</span></span>|<span data-ttu-id="216d4-107">Некоторые реплики доступности отключены.</span><span class="sxs-lookup"><span data-stu-id="216d4-107">Some availability replicas are disconnected.</span></span>|  
|<span data-ttu-id="216d4-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="216d4-108">**Category**</span></span>|<span data-ttu-id="216d4-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="216d4-109">**Warning**</span></span>|  
|<span data-ttu-id="216d4-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="216d4-110">**Facet**</span></span>|<span data-ttu-id="216d4-111">группа доступности</span><span class="sxs-lookup"><span data-stu-id="216d4-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="216d4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="216d4-112">Description</span></span>  
 <span data-ttu-id="216d4-113">Эта политика опрашивает состояние подключения всех реплик доступности и проверяет наличие реплик, имеющих состояние DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="216d4-113">This policy rolls up the connection state of all availability replicas and checks for any availability replicas that are DISCONENCTED.</span></span> <span data-ttu-id="216d4-114">Эта политика находится в неисправном состоянии, если любая реплика доступности находится в состоянии DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="216d4-114">The policy is in an unhealthy state when any availability replica is DISCONNECTED.</span></span> <span data-ttu-id="216d4-115">В остальном политика находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="216d4-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="216d4-116"> Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях приведены в разделе [Некоторые реплики доступности отключены](https://go.microsoft.com/fwlink/p/?LinkId=220855) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="216d4-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220855) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="216d4-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="216d4-117">Possible Causes</span></span>  
 <span data-ttu-id="216d4-118">По крайней мере одна вторичная реплика доступности не подключена к основной реплике в этой группе доступности.</span><span class="sxs-lookup"><span data-stu-id="216d4-118">In this availability group, at least one secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="216d4-119">Состояние соединения — DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="216d4-119">The connected state is DISCONNECTED.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="216d4-120">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="216d4-120">Possible Solution</span></span>  
 <span data-ttu-id="216d4-121">Используйте состояние политики реплик доступности для поиска реплики доступности с состоянием DISCONNECTED и устраните проблему в реплике доступности.</span><span class="sxs-lookup"><span data-stu-id="216d4-121">Use the availability replica policy state to find the availability replica that is DISCONNECTED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216d4-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="216d4-122">See Also</span></span>  
 <span data-ttu-id="216d4-123">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="216d4-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="216d4-124">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="216d4-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
