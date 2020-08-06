---
title: Настройка параметров NodeWeight кворума кластера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: cb3fd9a6-39a2-4e9c-9157-619bf3db9951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e469d5fc0fc030304a7cf2f1bdd894eb578aa056
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659285"
---
# <a name="configure-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="a5260-102">Настройка параметров NodeWeight кворума кластера</span><span class="sxs-lookup"><span data-stu-id="a5260-102">Configure Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="a5260-103">В этом разделе описан порядок настройки параметров NodeWeight для узла элемента в отказоустойчивом кластере Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="a5260-103">This topic describes how to configure NodeWeight settings for a member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="a5260-104">Параметры NodeWeight используются при определении голосов в кворуме для поддержки аварийного восстановления и сценариев с несколькими подсетями для экземпляров отказоустойчивого кластера [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5260-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="a5260-105">**Перед началом работы:**  [Обязательные условия](#Prerequisites), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="a5260-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="a5260-106">**Просмотр параметров NodeWeight кворума с помощью:** [Powershell](#PowerShellProcedure), [Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="a5260-106">**To view quorum NodeWeight settings using:** [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
-   [<span data-ttu-id="a5260-107">См. также</span><span class="sxs-lookup"><span data-stu-id="a5260-107">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a5260-108">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a5260-108">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a5260-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a5260-109">Prerequisites</span></span>  
 <span data-ttu-id="a5260-110">Эта функция поддерживается только в [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="a5260-110">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a5260-111">Для использования параметров NodeWeight необходимо применить следующее исправление ко всем серверам в кластере WSFC:</span><span class="sxs-lookup"><span data-stu-id="a5260-111">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="a5260-112">[KB2494036](https://support.microsoft.com/kb/2494036): доступно исправление, позволяющее настраивать узел кластера, не имеющий голосов кворума, в [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] и [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5260-112">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a5260-113">Если это исправление не установлено, то в примерах этого раздела будут возвращены пустые значения или значения NULL для NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="a5260-113">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a5260-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="a5260-114">Security</span></span>  
 <span data-ttu-id="a5260-115">Пользователь должен входить в учетную запись домена, которая является членом локальной группы администраторов, на каждом узле кластера WSFC.</span><span class="sxs-lookup"><span data-stu-id="a5260-115">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a5260-116">Использование Powershell</span><span class="sxs-lookup"><span data-stu-id="a5260-116">Using Powershell</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="a5260-117">Настройка параметров NodeWeight</span><span class="sxs-lookup"><span data-stu-id="a5260-117">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="a5260-118">Запустите повышенный режим Windows PowerShell с помощью команды **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="a5260-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="a5260-119">Импортируйте модуль `FailoverClusters` для включения командлетов кластера.</span><span class="sxs-lookup"><span data-stu-id="a5260-119">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="a5260-120">Используйте объект `Get-ClusterNode` для задания свойства `NodeWeight` для каждого узла в кластере.</span><span class="sxs-lookup"><span data-stu-id="a5260-120">Use the `Get-ClusterNode` object to set the `NodeWeight` property for each node in the cluster.</span></span>  
  
4.  <span data-ttu-id="a5260-121">Выведите свойства узла кластера в удобном для чтения формате.</span><span class="sxs-lookup"><span data-stu-id="a5260-121">Output the cluster node properties in a readable format.</span></span>  
  
 <span data-ttu-id="a5260-122">В следующем примере изменяется параметр NodeWeight в целях удаления голоса кворума для узла AlwaysOnSrv1, а затем происходит вывод параметров для всех узлов в этом кластере.</span><span class="sxs-lookup"><span data-stu-id="a5260-122">The following example changes the NodeWeight setting to remove the quorum vote for the "AlwaysOnSrv1" node, and then outputs the settings for all nodes in the cluster.</span></span>
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv1"  
(Get-ClusterNode $node).NodeWeight = 0  
  
$cluster = (Get-ClusterNode $node).Cluster  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="a5260-123">Использование Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="a5260-123">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5260-124">Программа cluster.exe является устаревшей в выпуске [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5260-124">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="a5260-125">Для будущих разработок используйте PowerShell с отказоустойчивым кластером.</span><span class="sxs-lookup"><span data-stu-id="a5260-125">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="a5260-126">Программа cluster.exe будет удалена в следующем выпуске Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a5260-126">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="a5260-127">Дополнительные сведения см. в разделе [Сопоставление команд Cluster.exe с командлетами Windows PowerShell для отказоустойчивых кластеров](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="a5260-127">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="a5260-128">Настройка параметров NodeWeight</span><span class="sxs-lookup"><span data-stu-id="a5260-128">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="a5260-129">Запустите повышенный режим командной строки с помощью команды **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="a5260-129">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="a5260-130">Используйте программу **cluster.exe** для задания значений `NodeWeight` .</span><span class="sxs-lookup"><span data-stu-id="a5260-130">Use **cluster.exe** to set `NodeWeight` values.</span></span>  

 <span data-ttu-id="a5260-131">В следующем примере изменяется значение NodeWeight для удаления голоса кворума узла AlwaysOnSrv1 в кластере Cluster001.</span><span class="sxs-lookup"><span data-stu-id="a5260-131">The following example changes the NodeWeight value to remove the quorum vote of the "AlwaysOnSrv1" node in the "Cluster001" cluster.</span></span>  
  
```cmd
cluster.exe Cluster001 node AlwaysOnSrv1 /prop NodeWeight=0  
```  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="a5260-132">См. также</span><span class="sxs-lookup"><span data-stu-id="a5260-132">Related Content</span></span>  
  
-   <span data-ttu-id="a5260-133">[Просмотр событий и журналов для отказоустойчивого кластера](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a5260-133">[View Events and Logs for a Failover Cluster](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="a5260-134">Командлет Get-ClusterLog отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="a5260-134">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="a5260-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5260-135">See Also</span></span>  
 <span data-ttu-id="a5260-136">[Режимы кворума WSFC и &#40;настройки голосования SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a5260-136">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="a5260-137">[Просмотр параметров NodeWeight кворума кластера](view-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="a5260-137">[View Cluster Quorum NodeWeight Settings](view-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="a5260-138">[Командлеты отказоустойчивого кластера в Windows PowerShell по выполняемым задачам](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a5260-138">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
