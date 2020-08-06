---
title: Восстановление по журналу после сбоя экземпляра отказоустойчивого кластера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], recovery from failure
- failover clustering [SQL Server], recovery from failure
- hardware failures [SQL Server]
- recovering failover cluster failures [SQL Server]
ms.assetid: 3d151d0c-e841-4325-8606-c094de37d7d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60db4c2e480b094c18d0a8071e947a38cdc779d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749651"
---
# <a name="recover-from-failover-cluster-instance-failure"></a><span data-ttu-id="b40e3-102">Восстановление по журналу после сбоя экземпляра отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="b40e3-102">Recover from Failover Cluster Instance Failure</span></span>
  <span data-ttu-id="b40e3-103">В этом разделе описывается восстановление кластера с помощью оснастки «Диспетчер отказоустойчивости кластеров» после отработки отказа в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b40e3-103">This topic describes how to recover from cluster failures by using the Failover Cluster Manager snap-in after a failover occurs in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b40e3-104">Оснастка «Диспетчер отказоустойчивости кластеров» — это приложение управления кластером для службы WSFC.</span><span class="sxs-lookup"><span data-stu-id="b40e3-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Serer Failover Clustering (WSFC) service.</span></span>  
  
-   [<span data-ttu-id="b40e3-105">Восстановление после неустранимого сбоя</span><span class="sxs-lookup"><span data-stu-id="b40e3-105">Recover from an irreparable failure</span></span>](#Scenario1)  
  
-   [<span data-ttu-id="b40e3-106">Восстановление после программного сбоя</span><span class="sxs-lookup"><span data-stu-id="b40e3-106">Recover from a software failure</span></span>](#Scenario2)  
  
##  <a name="recover-from-an-irreparable-failure"></a><a name="Scenario1"></a><span data-ttu-id="b40e3-107">Восстановление после сбоя неустранимого</span><span class="sxs-lookup"><span data-stu-id="b40e3-107">Recover from an irreparable failure</span></span>  
 <span data-ttu-id="b40e3-108">Для восстановления после неустранимого сбоя выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b40e3-108">Use the following steps to recover from an irreparable failure.</span></span> <span data-ttu-id="b40e3-109">Причина могла, например, заключаться в неисправности дискового контроллера или сбое операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b40e3-109">The failure could be caused, for example, by the failure of a disk controller or the operating system.</span></span> <span data-ttu-id="b40e3-110">В данном случае в кластере, состоящем из двух узлов, сбой вызван отказом оборудования в узле 1.</span><span class="sxs-lookup"><span data-stu-id="b40e3-110">In this case, failure is caused by hardware failure in Node 1 of a two-node cluster.</span></span>  
  
1.  <span data-ttu-id="b40e3-111">После сбоя на узле 1 отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] FCI переключается на узел 2.</span><span class="sxs-lookup"><span data-stu-id="b40e3-111">After Node 1 fails, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="b40e3-112">Исключите узел 1 из FCI.</span><span class="sxs-lookup"><span data-stu-id="b40e3-112">Evict Node 1 from the FCI.</span></span> <span data-ttu-id="b40e3-113">Для этого откройте оснастку "Диспетчер отказоустойчивости кластеров" из узла 2, щелкните правой кнопкой узел 1, выберите пункт **Действия перемещения**, а затем выберите команду **Исключить узел**.</span><span class="sxs-lookup"><span data-stu-id="b40e3-113">To do this, from Node 2, open the Failover Cluster Manager snap-in, right-click Node1, click **Move Actions**, and then click **Evict Node**.</span></span>  
  
3.  <span data-ttu-id="b40e3-114">Проверьте, исключен ли узел 1 из определения кластера.</span><span class="sxs-lookup"><span data-stu-id="b40e3-114">Verify that Node 1 has been evicted from the cluster definition.</span></span>  
  
4.  <span data-ttu-id="b40e3-115">Установите новое оборудование взамен отказавшего в узле 1.</span><span class="sxs-lookup"><span data-stu-id="b40e3-115">Install new hardware to replace the failed hardware in Node 1.</span></span>  
  
5.  <span data-ttu-id="b40e3-116">При помощи оснастки «Диспетчер отказоустойчивости кластеров» добавьте к существующему кластеру узел 1.</span><span class="sxs-lookup"><span data-stu-id="b40e3-116">Using the Failover Cluster Manager snap-in, add Node 1 to the existing cluster.</span></span> <span data-ttu-id="b40e3-117">Дополнительные сведения см. в статье [Подготовка к установке отказоустойчивого кластера](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="b40e3-117">For more information, see [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
6.  <span data-ttu-id="b40e3-118">Убедитесь, что учетные записи администраторов одинаковы на всех узлах кластера.</span><span class="sxs-lookup"><span data-stu-id="b40e3-118">Ensure that the administrator accounts are the same on all cluster nodes.</span></span>  
  
7.  <span data-ttu-id="b40e3-119">Запустите программу установки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , чтобы добавить узел 1 к FCI.</span><span class="sxs-lookup"><span data-stu-id="b40e3-119">Run [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to add Node 1 to the FCI.</span></span> <span data-ttu-id="b40e3-120">Дополнительные сведения см. [в разделе Добавление или удаление узлов в отказоустойчивом кластере SQL Server &#40;установки&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="b40e3-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
##  <a name="recover-from-a-reparable-failure"></a><a name="Scenario2"></a><span data-ttu-id="b40e3-121">Восстановление после сбоя после устранимого</span><span class="sxs-lookup"><span data-stu-id="b40e3-121">Recover from a reparable failure</span></span>  
 <span data-ttu-id="b40e3-122">Для восстановления после устранимого сбоя выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b40e3-122">Us the following steps to recover from a reparable failure.</span></span> <span data-ttu-id="b40e3-123">В данном случае причиной сбоя является узел 1, неработающий или находящийся вне сети, но не поврежденный полностью.</span><span class="sxs-lookup"><span data-stu-id="b40e3-123">In this case, failure is caused by Node 1 being down or offline but not irretrievably broken.</span></span> <span data-ttu-id="b40e3-124">Это может вызываться ошибкой операционной системы, отказом оборудования или сбоем в самом экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b40e3-124">This could be caused by an operating system failure, hardware failure, or failure in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance itself.</span></span>  
  
1.  <span data-ttu-id="b40e3-125">После сбоя на узле 1 FCI переключается на узел 2.</span><span class="sxs-lookup"><span data-stu-id="b40e3-125">After Node 1 fails, the FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="b40e3-126">Разрешите проблему на узле 1.</span><span class="sxs-lookup"><span data-stu-id="b40e3-126">Resolve the problem with Node 1.</span></span>  
  
3.  <span data-ttu-id="b40e3-127">Убедитесь, что все узлы находятся в режиме «в сети» и работает служба WSFC.</span><span class="sxs-lookup"><span data-stu-id="b40e3-127">Ensure that all nodes are online and the WSFC service is working.</span></span>  
  
4.  <span data-ttu-id="b40e3-128">Переведите [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на восстановленный узел.</span><span class="sxs-lookup"><span data-stu-id="b40e3-128">Fail over [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the recovered node.</span></span>  
  
  
