---
title: Некоторые синхронные реплики не синхронизированы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp5synchronized.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: e58ed56e-4c30-42e6-a9fc-a8c401620e02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecef2d16e80e128834a71e1f1f112096f8ccc9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664496"
---
# <a name="some-synchronous-replicas-are-not-synchronized"></a><span data-ttu-id="e35bf-102">Некоторые синхронные реплики не синхронизированы</span><span class="sxs-lookup"><span data-stu-id="e35bf-102">Some synchronous replicas are not synchronized</span></span>
    
## <a name="introduction"></a><span data-ttu-id="e35bf-103">Введение</span><span class="sxs-lookup"><span data-stu-id="e35bf-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e35bf-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="e35bf-104">**Policy Name**</span></span>|<span data-ttu-id="e35bf-105">Состояние синхронизации данных синхронных реплик</span><span class="sxs-lookup"><span data-stu-id="e35bf-105">Synchronous Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="e35bf-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="e35bf-106">**Issue**</span></span>|<span data-ttu-id="e35bf-107">Некоторые синхронные реплики не синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="e35bf-107">Some synchronous replicas are not synchronized.</span></span>|  
|<span data-ttu-id="e35bf-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="e35bf-108">**Category**</span></span>|<span data-ttu-id="e35bf-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="e35bf-109">**Warning**</span></span>|  
|<span data-ttu-id="e35bf-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="e35bf-110">**Facet**</span></span>|<span data-ttu-id="e35bf-111">группа доступности</span><span class="sxs-lookup"><span data-stu-id="e35bf-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e35bf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e35bf-112">Description</span></span>  
 <span data-ttu-id="e35bf-113">Эта политика сворачивает состояние синхронизации данных всех реплик доступности и проверяет наличие реплик доступности, состояние синхронизации которых отличается от ожидаемого.</span><span class="sxs-lookup"><span data-stu-id="e35bf-113">This policy rolls up the data synchronization state of all availability replicas and checks for any availability replicas that are not in the expected synchronization state.</span></span> <span data-ttu-id="e35bf-114">Политика находится в неисправном состоянии, если любая асинхронная реплика не находится в состоянии SYNCHRONIZING, а любая синхронная реплика не находится в состоянии SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="e35bf-114">The policy is in an unhealthy state when any asynchronous replica is not in a SYNCHRONIZING state and any synchronous replica is not in a SYNCHRONIZED state.</span></span> <span data-ttu-id="e35bf-115">Состояние политики исправно при других условиях.</span><span class="sxs-lookup"><span data-stu-id="e35bf-115">The policy state is otherwise healthy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e35bf-116">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблемы и ее решении доступны в разделе [Некоторые синхронные реплики не синхронизированы](https://go.microsoft.com/fwlink/p/?LinkId=220853) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="e35bf-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some synchronous replicas are not synchronized](https://go.microsoft.com/fwlink/p/?LinkId=220853) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="e35bf-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="e35bf-117">Possible Causes</span></span>  
 <span data-ttu-id="e35bf-118">В этой группе доступности не синхронизирована по меньшей мере одна реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="e35bf-118">In this availability group, at least one synchronous replica is not currently synchronized.</span></span> <span data-ttu-id="e35bf-119">Состоянием синхронизации реплики может быть либо SYNCHONIZING либо NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="e35bf-119">The replica synchronization state could be either SYNCHONIZING or NOT SYNCHRONIZING.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="e35bf-120">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="e35bf-120">Possible Solution</span></span>  
 <span data-ttu-id="e35bf-121">Используйте состояние политики реплики доступности для поиска реплики доступности с неверным состоянием синхронизации, после чего устраните неполадку в реплике доступности.</span><span class="sxs-lookup"><span data-stu-id="e35bf-121">Use the availability replica policy state to find the availability replica with the incorrect synchronization state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35bf-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="e35bf-122">See Also</span></span>  
 <span data-ttu-id="e35bf-123">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e35bf-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="e35bf-124">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e35bf-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
