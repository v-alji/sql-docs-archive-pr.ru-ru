---
title: Изменение IP-адреса для экземпляра отказоустойчивого кластера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- modifying IP addresses
- failover clustering [SQL Server], IP addresses
- IP addresses [SQL Server]
- clusters [SQL Server], IP addresses
ms.assetid: b685f400-cbfe-4c5d-a070-227a1123dae4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45d3ef0b70282efd870e4a076663719c2549deaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659287"
---
# <a name="change-the-ip-address-of-a-failover-cluster-instance"></a><span data-ttu-id="f185d-102">Изменение IP-адреса экземпляра отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="f185d-102">Change the IP Address of a Failover Cluster Instance</span></span>
  <span data-ttu-id="f185d-103">В этом разделе описывается изменение ресурса IP-адреса в экземпляре отказоустойчивого кластера (FCI) AlwaysOn с помощью оснастки «Диспетчер отказоустойчивости кластеров».</span><span class="sxs-lookup"><span data-stu-id="f185d-103">This topic describes how to change the IP address resource in an AlwaysOn Failover Cluster Instance (FCI) by using the Failover Cluster Manager snap-in.</span></span> <span data-ttu-id="f185d-104">Оснастка «Диспетчер отказоустойчивости кластеров» — это приложение управления кластером для службы WSFC.</span><span class="sxs-lookup"><span data-stu-id="f185d-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Server Failover Clustering (WSFC) service.</span></span>  
  
-   <span data-ttu-id="f185d-105">**Перед началом работы**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="f185d-105">**Before you begin:**  [Security](#Security)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f185d-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f185d-106">Before You Begin</span></span>  
 <span data-ttu-id="f185d-107">Перед тем как продолжить, просмотрите следующий подраздел электронной документации по [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] : [Подготовка к установке отказоустойчивого кластера](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="f185d-107">Before you begin, review the following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online topic: [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f185d-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="f185d-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f185d-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="f185d-109">Permissions</span></span>  
 <span data-ttu-id="f185d-110">Обслуживание или обновление экземпляра FCI должно производиться локальным администратором, имеющим разрешение на вход в систему в качестве службы на всех узлах FCI.</span><span class="sxs-lookup"><span data-stu-id="f185d-110">To maintain or update an FCI, you must be a local administrator with permission to logon as a service on all nodes of the FCI.</span></span>  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="f185d-111">Использование оснастки «Диспетчер отказоустойчивости кластеров»</span><span class="sxs-lookup"><span data-stu-id="f185d-111">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="f185d-112">**Изменение ресурса IP-адреса для FCI**</span><span class="sxs-lookup"><span data-stu-id="f185d-112">**To change the IP address resource for an FCI**</span></span>  
  
1.  <span data-ttu-id="f185d-113">Откройте оснастку «Диспетчер отказоустойчивости кластеров»</span><span class="sxs-lookup"><span data-stu-id="f185d-113">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="f185d-114">Разверните узел **Службы и приложения** , на левой панели щелкните экземпляр FCI.</span><span class="sxs-lookup"><span data-stu-id="f185d-114">Expand the **Services and applications** node, in the left pane and click on the FCI.</span></span>  
  
3.  <span data-ttu-id="f185d-115">В правой части панели в категории **Имя сервера** щелкните правой кнопкой мыши экземпляр SQL Server и выберите пункт **Свойства** , чтобы открыть диалоговое окно **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="f185d-115">On the right pane, under the **Server Name** category, right-click the SQL Server Instance, and select **Properties** option to open the **Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="f185d-116">На вкладке **Общие** измените ресурс IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="f185d-116">On the **General** tab, change the IP address resource.</span></span>  
  
5.  <span data-ttu-id="f185d-117">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="f185d-117">Click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="f185d-118">На панели справа щелкните правой кнопкой мыши элемент SQL IP Address1 (имя экземпляра отказоустойчивого кластера) и выберите пункт **Перейти в режим "вне сети"**.</span><span class="sxs-lookup"><span data-stu-id="f185d-118">In the right-hand pane, right-click the SQL IP Address1(failover cluster instance name) and select **Take Offline**.</span></span> <span data-ttu-id="f185d-119">Состояние SQL IP Address1 (имя экземпляра отказоустойчивого кластера), SQL Network Name (имя экземпляра отказоустойчивого кластера) и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] изменится с «в сети» на «ожидание сети», затем на «вне сети».</span><span class="sxs-lookup"><span data-stu-id="f185d-119">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Online to Offline Pending, and then to Offline.</span></span>  
  
7.  <span data-ttu-id="f185d-120">На панели справа щелкните правой кнопкой мыши [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]и выберите пункт **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="f185d-120">In the right-hand pane, right-click [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and then select **Bring Online**.</span></span> <span data-ttu-id="f185d-121">Состояние SQL IP Address1 (имя экземпляра отказоустойчивого кластера), SQL Network Name (имя экземпляра отказоустойчивого кластера) и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] изменится с «вне сети» на «ожидание сети», затем на «в сети».</span><span class="sxs-lookup"><span data-stu-id="f185d-121">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Offline to Online Pending, and then to Online.</span></span>  
  
8.  <span data-ttu-id="f185d-122">Закройте оснастку «Диспетчер отказоустойчивости кластеров».</span><span class="sxs-lookup"><span data-stu-id="f185d-122">Close the Failover Cluster Manager snap-in.</span></span>  
  
  
