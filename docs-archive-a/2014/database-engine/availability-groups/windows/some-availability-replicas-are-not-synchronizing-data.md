---
title: Некоторые реплики доступности не выполняют синхронизацию данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp4synchronizing.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 3db6a569-e942-4321-a0dd-c4ab002087c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 762b7da1f7b8a07257c2a900307eb1bb10408653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664502"
---
# <a name="some-availability-replicas-are-not-synchronizing-data"></a><span data-ttu-id="41023-102">Некоторые реплики доступности не выполняют синхронизацию данных</span><span class="sxs-lookup"><span data-stu-id="41023-102">Some availability replicas are not synchronizing data</span></span>
    
## <a name="introduction"></a><span data-ttu-id="41023-103">Введение</span><span class="sxs-lookup"><span data-stu-id="41023-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41023-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="41023-104">**Policy Name**</span></span>|<span data-ttu-id="41023-105">Состояние синхронизации данных реплик доступности</span><span class="sxs-lookup"><span data-stu-id="41023-105">Availability Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="41023-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="41023-106">**Issue**</span></span>|<span data-ttu-id="41023-107">Некоторые реплики доступности не выполняют синхронизацию данных.</span><span class="sxs-lookup"><span data-stu-id="41023-107">Some availability replicas are not synchronizing data.</span></span>|  
|<span data-ttu-id="41023-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="41023-108">**Category**</span></span>|<span data-ttu-id="41023-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="41023-109">**Warning**</span></span>|  
|<span data-ttu-id="41023-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="41023-110">**Facet**</span></span>|<span data-ttu-id="41023-111">группа доступности</span><span class="sxs-lookup"><span data-stu-id="41023-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="41023-112">Описание</span><span class="sxs-lookup"><span data-stu-id="41023-112">Description</span></span>  
 <span data-ttu-id="41023-113">Эта политика сворачивает состояние синхронизации данных всех реплик доступности в группе доступности и проверяет рабочее состояние синхронизации у всех реплик доступности.</span><span class="sxs-lookup"><span data-stu-id="41023-113">This policy rolls up the data synchronization state of all availability replicas in the availability group and checks if the synchronization of any availability replica is not operational.</span></span> <span data-ttu-id="41023-114">Политика находится в нерабочем состоянии, если у какой-либо реплики доступности при синхронизации данных имеется состояние NOT SYNCRONIZING.</span><span class="sxs-lookup"><span data-stu-id="41023-114">The policy is in an unhealthy state if any of the data synchronization states of the availability replica is NOT SYNCRONIZING.</span></span>  
  
 <span data-ttu-id="41023-115">Политика находится в рабочем состоянии, если ни у одной из реплик доступности при синхронизации данных не имеется состояние NOT SYNCRONIZING.</span><span class="sxs-lookup"><span data-stu-id="41023-115">This policy is in a healthy state if none of the data synchronization states of the availability replica is NOT SYNCHRONIZING.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41023-116">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях доступны в разделе [Некоторые реплики доступности не выполняют синхронизацию данных](https://go.microsoft.com/fwlink/p/?LinkId=220852) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="41023-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are not synchronizing data](https://go.microsoft.com/fwlink/p/?LinkId=220852) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="41023-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="41023-117">Possible Causes</span></span>  
 <span data-ttu-id="41023-118">В этой группе доступности по крайней мере у одной вторичной реплики имеется состояние синхронизации NOT SYNCHRONIZING и она не получает данных от первичной реплики.</span><span class="sxs-lookup"><span data-stu-id="41023-118">In this availability group, at least one secondary replica has a NOT SYNCHRONIZING synchronization state and is not receiving data from the primary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="41023-119">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="41023-119">Possible Solution</span></span>  
 <span data-ttu-id="41023-120">Используйте состояние политики реплик доступности для поиска реплики доступности с состоянием NOT SYNCHROINIZING и устраните проблему в реплике доступности.</span><span class="sxs-lookup"><span data-stu-id="41023-120">Use the availability replica policy state to find the availability replica with a NOT SYNCHROINIZING state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41023-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="41023-121">See Also</span></span>  
 <span data-ttu-id="41023-122">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="41023-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="41023-123">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="41023-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
