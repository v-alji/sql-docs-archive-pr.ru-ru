---
title: Состояние синхронизации данных базы данных доступности не в рабочем состоянии | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 4fd003e7-808e-4b0e-b28a-47d9f2616f06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a179008c20b108a2f6aaefd5dd80b22708e94a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752344"
---
# <a name="data-synchronization-state-of-availability-database-is-not-healthy"></a><span data-ttu-id="cd287-102">Состояние синхронизации данных баз данных доступности не является исправным</span><span class="sxs-lookup"><span data-stu-id="cd287-102">Data synchronization state of availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="cd287-103">Введение</span><span class="sxs-lookup"><span data-stu-id="cd287-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd287-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="cd287-104">**Policy Name**</span></span>|<span data-ttu-id="cd287-105">Состояние синхронизации базы данных доступности</span><span class="sxs-lookup"><span data-stu-id="cd287-105">Availability Database Data Synchronization State</span></span>|  
|<span data-ttu-id="cd287-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="cd287-106">**Issue**</span></span>|<span data-ttu-id="cd287-107">Состояние синхронизации данных некоторых баз данных доступности не является рабочим.</span><span class="sxs-lookup"><span data-stu-id="cd287-107">Data synchronization state of availability database is not healthy.</span></span>|  
|<span data-ttu-id="cd287-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="cd287-108">**Category**</span></span>|<span data-ttu-id="cd287-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="cd287-109">**Warning**</span></span>|  
|<span data-ttu-id="cd287-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="cd287-110">**Facet**</span></span>|<span data-ttu-id="cd287-111">База данных доступности</span><span class="sxs-lookup"><span data-stu-id="cd287-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cd287-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cd287-112">Description</span></span>  
 <span data-ttu-id="cd287-113">Эта политика выполняет сведение состояния синхронизации данных для всех баз данных доступности (которые также называются «реплики баз данных») в реплике доступности.</span><span class="sxs-lookup"><span data-stu-id="cd287-113">This policy rolls up the data synchronization state of all availability databases (also known as "database replicas") in the availability replica.</span></span> <span data-ttu-id="cd287-114">Политика находится в нерабочем состоянии при нахождении какой-либо из реплик баз данных в непредвиденном состоянии синхронизации данных.</span><span class="sxs-lookup"><span data-stu-id="cd287-114">The policy is in an unhealthy sate when any database replica is not in the expected data synchronization state.</span></span> <span data-ttu-id="cd287-115">В остальном политика находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="cd287-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd287-116">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях доступны в разделе [Состояние синхронизации данных некоторых баз данных доступности не является исправным](https://go.microsoft.com/fwlink/p/?LinkId=220858) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="cd287-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of some availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220858) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="cd287-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="cd287-117">Possible Causes</span></span>  
 <span data-ttu-id="cd287-118">Состояние синхронизации данных некоторых баз данных доступности не является рабочим.</span><span class="sxs-lookup"><span data-stu-id="cd287-118">The data synchronization state of this availability database is unhealthy.</span></span> <span data-ttu-id="cd287-119">Если это реплика доступности с асинхронной фиксацией, все базы данных доступности должны находиться в состоянии SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="cd287-119">On an asynchronous-commit availability replica, every availability database should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="cd287-120">При синхронной фиксации реплик доступности у всех баз данных доступности должно быть состояние SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="cd287-120">On a synchronous-commit replica, every availability database must be in the SYNCHRONIZED state.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="cd287-121">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="cd287-121">Possible Solution</span></span>  
 <span data-ttu-id="cd287-122">Используйте политику реплик баз данных для поиска реплики баз данных с нерабочим состоянием синхронизации данных и устраните проблему в реплике базы данных.</span><span class="sxs-lookup"><span data-stu-id="cd287-122">Use the database replica policy to find the database replica with an unhealthy data synchronization state, and then resolve the issue at the database replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd287-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd287-123">See Also</span></span>  
 <span data-ttu-id="cd287-124">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cd287-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="cd287-125">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cd287-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
