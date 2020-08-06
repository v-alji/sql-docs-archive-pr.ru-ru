---
title: База данных доступности приостановлена | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp1notsuspended.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6baee70f-848c-4e86-b20d-78875c0f82cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07a547f217367f13df739348325461c862d831f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655391"
---
# <a name="availability-database-is-suspended"></a><span data-ttu-id="86b90-102">База данных доступности приостановлена</span><span class="sxs-lookup"><span data-stu-id="86b90-102">Availability database is suspended</span></span>
    
## <a name="introduction"></a><span data-ttu-id="86b90-103">Введение</span><span class="sxs-lookup"><span data-stu-id="86b90-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86b90-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="86b90-104">**Policy Name**</span></span>|<span data-ttu-id="86b90-105">Состояние приостановки базы данных доступности</span><span class="sxs-lookup"><span data-stu-id="86b90-105">Availability Database Suspension State</span></span>|  
|<span data-ttu-id="86b90-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="86b90-106">**Issue**</span></span>|<span data-ttu-id="86b90-107">База данных доступности приостановлена.</span><span class="sxs-lookup"><span data-stu-id="86b90-107">Availability database is suspended.</span></span>|  
|<span data-ttu-id="86b90-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="86b90-108">**Category**</span></span>|<span data-ttu-id="86b90-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="86b90-109">**Warning**</span></span>|  
|<span data-ttu-id="86b90-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="86b90-110">**Facet**</span></span>|<span data-ttu-id="86b90-111">База данных доступности</span><span class="sxs-lookup"><span data-stu-id="86b90-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="86b90-112">Описание</span><span class="sxs-lookup"><span data-stu-id="86b90-112">Description</span></span>  
 <span data-ttu-id="86b90-113">Эта политика проверяет состояние перемещения данных базы данных-получателя (которая также называется «реплика базы данных-получателя»).</span><span class="sxs-lookup"><span data-stu-id="86b90-113">This policy checks the state of data movement of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="86b90-114">Эта политика находится в нерабочем состоянии, если перемещение данных приостановлено.</span><span class="sxs-lookup"><span data-stu-id="86b90-114">The policy is in an unhealthy state when the data movement is suspended.</span></span> <span data-ttu-id="86b90-115">В остальном политика находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="86b90-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86b90-116"> Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях доступны в разделе [База данных доступности приостановлена](https://go.microsoft.com/fwlink/p/?LinkId=220860) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="86b90-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability database is suspended](https://go.microsoft.com/fwlink/p/?LinkId=220860) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="86b90-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="86b90-117">Possible Causes</span></span>  
 <span data-ttu-id="86b90-118">Возможны следующие причины приостановки синхронизации данных в этой базе данных доступности:</span><span class="sxs-lookup"><span data-stu-id="86b90-118">Data synchronization on this availability database might have been suspended because of the following:</span></span>  
  
-   <span data-ttu-id="86b90-119">Из-за ошибки система могла приостановить синхронизацию данных.</span><span class="sxs-lookup"><span data-stu-id="86b90-119">Due to an error, the system might have suspended data synchronization.</span></span>  
  
-   <span data-ttu-id="86b90-120">Администратор базы данных мог приостановить синхронизацию данных для выполнения задач технического обслуживания.</span><span class="sxs-lookup"><span data-stu-id="86b90-120">The database administrator might have suspended data synchronization for maintenance purposes.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="86b90-121">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="86b90-121">Possible Solution</span></span>  
 <span data-ttu-id="86b90-122">Восстановите синхронизацию данных.</span><span class="sxs-lookup"><span data-stu-id="86b90-122">Resume data synchronization.</span></span> <span data-ttu-id="86b90-123">При повторном возникновении проблемы проверьте группу доступности в журнале событий, а затем с помощью диагностики определите причину приостановки перемещения данных системой.</span><span class="sxs-lookup"><span data-stu-id="86b90-123">If the issue persists, check the availability group in the Event log, and then diagnose why the system suspended data movement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b90-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="86b90-124">See Also</span></span>  
 <span data-ttu-id="86b90-125">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="86b90-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="86b90-126">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="86b90-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
