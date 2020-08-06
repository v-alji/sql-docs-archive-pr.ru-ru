---
title: Реплика доступности отключена | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp2connected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 1a2162d3-54fb-4356-b349-effbdc15a5a4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1db92b8e73b6daaee7edf5042b1d73cfeb471d1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733154"
---
# <a name="availability-replica-is-disconnected"></a><span data-ttu-id="a1549-102">Реплика доступности отключена</span><span class="sxs-lookup"><span data-stu-id="a1549-102">Availability replica is disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="a1549-103">Введение</span><span class="sxs-lookup"><span data-stu-id="a1549-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a1549-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="a1549-104">**Policy Name**</span></span>|<span data-ttu-id="a1549-105">Состояние соединения с репликами доступности</span><span class="sxs-lookup"><span data-stu-id="a1549-105">Availability Replica Connection State</span></span>|  
|<span data-ttu-id="a1549-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="a1549-106">**Issue**</span></span>|<span data-ttu-id="a1549-107">Реплика доступности отключена.</span><span class="sxs-lookup"><span data-stu-id="a1549-107">Availability replica is disconnected.</span></span>|  
|<span data-ttu-id="a1549-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="a1549-108">**Category**</span></span>|<span data-ttu-id="a1549-109">**Критическая**</span><span class="sxs-lookup"><span data-stu-id="a1549-109">**Critical**</span></span>|  
|<span data-ttu-id="a1549-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="a1549-110">**Facet**</span></span>|<span data-ttu-id="a1549-111">Реплика доступности</span><span class="sxs-lookup"><span data-stu-id="a1549-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a1549-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a1549-112">Description</span></span>  
 <span data-ttu-id="a1549-113">Эта политика проверяет состояние соединения между репликами доступности.</span><span class="sxs-lookup"><span data-stu-id="a1549-113">This policy checks the connection state between availability replicas.</span></span> <span data-ttu-id="a1549-114">Эта политика находится в нерабочем состоянии, если подключение к реплике доступности имеет состояние DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="a1549-114">The policy is in an unhealthy state when the connection state of the availability replica is DISCONNECTED.</span></span> <span data-ttu-id="a1549-115">В остальном политика находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="a1549-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1549-116"> Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях доступны в разделе [Реплика доступности отключена](https://go.microsoft.com/fwlink/p/?LinkId=220857) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="a1549-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220857) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="a1549-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="a1549-117">Possible Causes</span></span>  
 <span data-ttu-id="a1549-118">Вторичная реплика не подключена к первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="a1549-118">The secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="a1549-119">Состояние соединения — DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="a1549-119">The connected state is DISCONNECTED.</span></span> <span data-ttu-id="a1549-120">Возможны следующие причины этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="a1549-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="a1549-121">Порт подключения может конфликтовать с другим приложением.</span><span class="sxs-lookup"><span data-stu-id="a1549-121">The connection port might be in conflict with another application.</span></span>  
  
-   <span data-ttu-id="a1549-122">Несоответствие типа или алгоритма шифрования.</span><span class="sxs-lookup"><span data-stu-id="a1549-122">The encryption type or algorithm is mismatched.</span></span>  
  
-   <span data-ttu-id="a1549-123">Конечная точка подключения была удалена или не была запущена.</span><span class="sxs-lookup"><span data-stu-id="a1549-123">The connection endpoint has been deleted or has not been started.</span></span>  
  
-   <span data-ttu-id="a1549-124">Транспорт отключен.</span><span class="sxs-lookup"><span data-stu-id="a1549-124">The transport is disconnected.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="a1549-125">Возможные решения</span><span class="sxs-lookup"><span data-stu-id="a1549-125">Possible Solutions</span></span>  
 <span data-ttu-id="a1549-126">Ниже перечислены возможные решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="a1549-126">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="a1549-127">Проверьте конфигурацию конечной точки зеркального отображения базы данных для экземпляров первичной и вторичной реплики и обновите конфигурацию с несоответствием.</span><span class="sxs-lookup"><span data-stu-id="a1549-127">Check the database mirroring endpoint configuration for the instances of the primary and secondary replica and update the mismatched configuration.</span></span>  
  
-   <span data-ttu-id="a1549-128">Проверьте наличие конфликта портов и при его обнаружении измените номер порта.</span><span class="sxs-lookup"><span data-stu-id="a1549-128">Check if the port is conflicting, and if so, change the port number.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1549-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1549-129">See Also</span></span>  
 <span data-ttu-id="a1549-130">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a1549-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="a1549-131">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a1549-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
