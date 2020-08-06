---
title: Некоторые реплики доступности не имеют исправной роли | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp6allroleshealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 7ec5b337-7201-4a66-a541-7560f8b18784
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 801fe20edf6f2dbe09bc800722cf4210988ebc69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664501"
---
# <a name="some-availability-replicas-do-not-have-a-healthy-role"></a><span data-ttu-id="50fb5-102">Некоторые реплики доступности не имеют исправной роли</span><span class="sxs-lookup"><span data-stu-id="50fb5-102">Some availability replicas do not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="50fb5-103">Введение</span><span class="sxs-lookup"><span data-stu-id="50fb5-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50fb5-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="50fb5-104">**Policy Name**</span></span>|<span data-ttu-id="50fb5-105">Состояние роли реплик доступности</span><span class="sxs-lookup"><span data-stu-id="50fb5-105">Availability Replicas Role State</span></span>|  
|<span data-ttu-id="50fb5-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="50fb5-106">**Issue**</span></span>|<span data-ttu-id="50fb5-107">Некоторые реплики доступности не имеют исправной роли.</span><span class="sxs-lookup"><span data-stu-id="50fb5-107">Some availability replicas do not have a healthy role.</span></span>|  
|<span data-ttu-id="50fb5-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="50fb5-108">**Category**</span></span>|<span data-ttu-id="50fb5-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="50fb5-109">**Warning**</span></span>|  
|<span data-ttu-id="50fb5-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="50fb5-110">**Facet**</span></span>|<span data-ttu-id="50fb5-111">группа доступности</span><span class="sxs-lookup"><span data-stu-id="50fb5-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="50fb5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="50fb5-112">Description</span></span>  
 <span data-ttu-id="50fb5-113">Эта политика опрашивает состояние подключения всех реплик доступности и проверяет наличие реплик, не имеющих исправной роли.</span><span class="sxs-lookup"><span data-stu-id="50fb5-113">This policy rolls up the connection state of all availability replicas and checks if there are any availability replicas that are not in a healthy role.</span></span> <span data-ttu-id="50fb5-114">Политика имеет неисправное состояние, когда любая из реплик доступности не является первичной или вторичной.</span><span class="sxs-lookup"><span data-stu-id="50fb5-114">The policy is in an unhealthy state when any availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="50fb5-115">В остальном политика находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="50fb5-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50fb5-116">Сведения о возможных причинах проблем и решениях для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]содержатся в разделе [Некоторые реплики доступности не имеют исправной роли](https://go.microsoft.com/fwlink/p/?LinkId=220854) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="50fb5-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas do not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220854) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="50fb5-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="50fb5-117">Possible Causes</span></span>  
 <span data-ttu-id="50fb5-118">По крайней мере одна реплика доступности в этой группе доступности не имеет первичной или вторичной роли.</span><span class="sxs-lookup"><span data-stu-id="50fb5-118">In this availability group, at least one availability replica does not currently have the primary or secondary role.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="50fb5-119">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="50fb5-119">Possible Solution</span></span>  
 <span data-ttu-id="50fb5-120">Используйте состояние политики реплик доступности для поиска реплики доступности, роль которой не является первичной или вторичной, после чего устраните неполадку в реплике доступности.</span><span class="sxs-lookup"><span data-stu-id="50fb5-120">Use the availability replica policy state to find the availability replica whose role is not primary or secondary, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50fb5-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="50fb5-121">See Also</span></span>  
 <span data-ttu-id="50fb5-122">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="50fb5-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="50fb5-123">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="50fb5-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
