---
title: Реплика доступности не в рабочем состоянии | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp1rolehealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: ebb2c9f4-2097-4688-b4fb-8f0571047317
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7be26945903a5e3b602ef4a99c269de6a58b04a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733161"
---
# <a name="availability-replica-does-not-have-a-healthy-role"></a><span data-ttu-id="50eb6-102">Доступность репликации не имеет исправной роли</span><span class="sxs-lookup"><span data-stu-id="50eb6-102">Availability replica does not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="50eb6-103">Введение</span><span class="sxs-lookup"><span data-stu-id="50eb6-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50eb6-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="50eb6-104">**Policy Name**</span></span>|<span data-ttu-id="50eb6-105">Состояние роли реплики доступности</span><span class="sxs-lookup"><span data-stu-id="50eb6-105">Availability Replica Role State</span></span>|  
|<span data-ttu-id="50eb6-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="50eb6-106">**Issue**</span></span>|<span data-ttu-id="50eb6-107">Реплике доступности не назначена допустимая роль.</span><span class="sxs-lookup"><span data-stu-id="50eb6-107">Availability replica does not have a healthy role.</span></span>|  
|<span data-ttu-id="50eb6-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="50eb6-108">**Category**</span></span>|<span data-ttu-id="50eb6-109">**Критическая**</span><span class="sxs-lookup"><span data-stu-id="50eb6-109">**Critical**</span></span>|  
|<span data-ttu-id="50eb6-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="50eb6-110">**Facet**</span></span>|<span data-ttu-id="50eb6-111">Реплика доступности</span><span class="sxs-lookup"><span data-stu-id="50eb6-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="50eb6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="50eb6-112">Description</span></span>  
 <span data-ttu-id="50eb6-113">Эта политика проверяет состояние роли реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="50eb6-113">This policy checks the state of the role of the availability replica.</span></span> <span data-ttu-id="50eb6-114">Политика находится в состоянии неисправности, если роль реплики доступности не является первичной или вторичной.</span><span class="sxs-lookup"><span data-stu-id="50eb6-114">The policy is in an unhealthy state when the role of the availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="50eb6-115">В остальном политика находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="50eb6-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50eb6-116">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблемы и ее решении доступны в разделе [Реплика доступности не имеет исправной роли](https://go.microsoft.com/fwlink/p/?LinkId=220856) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="50eb6-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica does not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220856) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="50eb6-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="50eb6-117">Possible Causes</span></span>  
 <span data-ttu-id="50eb6-118">Роль этой реплики доступности неисправна.</span><span class="sxs-lookup"><span data-stu-id="50eb6-118">The role of this availability replica is unhealthy.</span></span> <span data-ttu-id="50eb6-119">Реплике не назначена роль первичной или вторичной.</span><span class="sxs-lookup"><span data-stu-id="50eb6-119">The replica does not have either the primary or secondary role.</span></span>  
  
## <a name="possible-solution-information_still_to_come"></a><span data-ttu-id="50eb6-120">Возможное решение: Information_still_to_come</span><span class="sxs-lookup"><span data-stu-id="50eb6-120">Possible Solution: Information_still_to_come</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50eb6-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="50eb6-121">See Also</span></span>  
 <span data-ttu-id="50eb6-122">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="50eb6-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="50eb6-123">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="50eb6-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
