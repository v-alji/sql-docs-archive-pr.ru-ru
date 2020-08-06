---
title: Состояние синхронизации данных некоторых баз данных доступности не находится в рабочем состоянии | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 89f95d15-33c6-4768-bccd-9dbf8c4f49a9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 221f25a1ee7e4a8719acc133372c742ca4a79303
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752335"
---
# <a name="data-synchronization-state-of-some-availability-database-is-not-healthy"></a><span data-ttu-id="47887-102">Состояние синхронизации данных некоторых баз данных доступности не является исправным</span><span class="sxs-lookup"><span data-stu-id="47887-102">Data synchronization state of some availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="47887-103">Введение</span><span class="sxs-lookup"><span data-stu-id="47887-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47887-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="47887-104">**Policy Name**</span></span>|<span data-ttu-id="47887-105">Состояние синхронизации данных реплики доступности</span><span class="sxs-lookup"><span data-stu-id="47887-105">Availability Replica Data Synchronization State</span></span>|  
|<span data-ttu-id="47887-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="47887-106">**Issue**</span></span>|<span data-ttu-id="47887-107">Состояние синхронизации данных некоторых баз данных доступности не является исправным.</span><span class="sxs-lookup"><span data-stu-id="47887-107">Data synchronization state of some availability database is not healthy.</span></span>|  
|<span data-ttu-id="47887-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="47887-108">**Category**</span></span>|<span data-ttu-id="47887-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="47887-109">**Warning**</span></span>|  
|<span data-ttu-id="47887-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="47887-110">**Facet**</span></span>|<span data-ttu-id="47887-111">Реплика доступности</span><span class="sxs-lookup"><span data-stu-id="47887-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="47887-112">Описание</span><span class="sxs-lookup"><span data-stu-id="47887-112">Description</span></span>  
 <span data-ttu-id="47887-113">Эта политика проверяет состояние синхронизации базы данных доступности (также называемой «реплика базы данных»).</span><span class="sxs-lookup"><span data-stu-id="47887-113">This policy checks the data synchronization state of the availability database (also known as a "database replica").</span></span> <span data-ttu-id="47887-114">Политика находится в неисправном состоянии, когда синхронизация данных приобретает состояние NOT SYNCRONIZING, либо не является SYNCHRONIZED при синхронной фиксации реплики баз данных.</span><span class="sxs-lookup"><span data-stu-id="47887-114">The policy is in an unhealthy state when the data synchronization state is NOT SYNCHRONIZING or the state is not SYNCHRONIZED for the synchronous-commit database replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47887-115">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях приведены в разделе [Состояние синхронизации данных некоторых баз данных доступности не является исправным](https://go.microsoft.com/fwlink/p/?LinkId=220863) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="47887-115">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220863) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="47887-116">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="47887-116">Possible Causes</span></span>  
 <span data-ttu-id="47887-117">Одна или несколько баз данных доступности в этой реплике не находятся в исправном состоянии синхронизации данных.</span><span class="sxs-lookup"><span data-stu-id="47887-117">At least one availability database on the replica has an unhealthy data synchronization state.</span></span> <span data-ttu-id="47887-118">Если это реплика доступности с асинхронной фиксацией, все базы данных доступности должны находиться в состоянии SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="47887-118">If this is an asynchronous-commit availability replica, all availability databases should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="47887-119">Если эта реплика доступности настроена для синхронной фиксации, все базы данных доступности должны быть в состоянии SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="47887-119">If this is a synchronous-commit availability replica, all availability databases should be in the SYNCHRONIZED state.</span></span> <span data-ttu-id="47887-120">Возможны следующие причины этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="47887-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="47887-121">Возможно, эта реплика доступности отключена.</span><span class="sxs-lookup"><span data-stu-id="47887-121">The availability replica might be disconnected.</span></span>  
  
-   <span data-ttu-id="47887-122">Перемещение данных может быть временно приостановлено.</span><span class="sxs-lookup"><span data-stu-id="47887-122">The data movement might be suspended.</span></span>  
  
-   <span data-ttu-id="47887-123">База данных может быть недоступна.</span><span class="sxs-lookup"><span data-stu-id="47887-123">The database might not be accessible.</span></span>  
  
-   <span data-ttu-id="47887-124">Возможны некоторые задержки из-за проблем с сетью или нагрузки на основную или дополнительную реплику.</span><span class="sxs-lookup"><span data-stu-id="47887-124">There might be a temporary delay issue due to network latency or the load on the primary or secondary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="47887-125">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="47887-125">Possible Solution</span></span>  
 <span data-ttu-id="47887-126">Устраните все неполадки, связанные с подключением или приостановкой перемещения данных.</span><span class="sxs-lookup"><span data-stu-id="47887-126">Resolve any connection or data movement suspend issues.</span></span> <span data-ttu-id="47887-127">Проверьте события, связанные с этой неполадкой при помощи среды SQL Server Management Studio, и найдите ошибку базы данных.</span><span class="sxs-lookup"><span data-stu-id="47887-127">Check the events for this issue using SQL Server Management Studio, and find the database error.</span></span> <span data-ttu-id="47887-128">Выполните действия по устранению неполадок, предписанные для этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="47887-128">Follow the troubleshooting steps for the specific error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47887-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="47887-129">See Also</span></span>  
 <span data-ttu-id="47887-130">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="47887-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="47887-131">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="47887-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
