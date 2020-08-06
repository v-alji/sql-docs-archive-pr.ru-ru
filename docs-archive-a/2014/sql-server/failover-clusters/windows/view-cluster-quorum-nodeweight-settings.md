---
title: Просмотр параметров NodeWeight кворума кластера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: b845e73a-bb01-4de2-aac2-8ac12abebc95
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef2176d4916e8affbb9ef89c9b26499289c520ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659270"
---
# <a name="view-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="e21a6-102">Просмотр параметров NodeWeight кворума кластера</span><span class="sxs-lookup"><span data-stu-id="e21a6-102">View Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="e21a6-103">В этом разделе описан порядок просмотра параметров NodeWeight для каждого узла элемента в кластере отказоустойчивого кластера Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="e21a6-103">This topic describes how to view NodeWeight settings for each member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="e21a6-104">Параметры NodeWeight используются при определении голосов в кворуме для поддержки аварийного восстановления и сценариев с несколькими подсетями для экземпляров отказоустойчивого кластера [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e21a6-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="e21a6-105">**Перед началом работы:**  [Обязательные условия](#Prerequisites), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="e21a6-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="e21a6-106">**Просмотр параметров NodeWeight кворума с помощью:** [Transact-SQL](#TsqlProcedure), [PowerShell](#PowerShellProcedure), [Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="e21a6-106">**To view quorum NodeWeight settings using:** [Using Transact-SQL](#TsqlProcedure), [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e21a6-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e21a6-107">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="e21a6-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e21a6-108">Prerequisites</span></span>  
 <span data-ttu-id="e21a6-109">Эта функция поддерживается только в [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="e21a6-109">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e21a6-110">Для использования параметров NodeWeight необходимо применить следующее исправление ко всем серверам в кластере WSFC:</span><span class="sxs-lookup"><span data-stu-id="e21a6-110">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="e21a6-111">[KB2494036](https://support.microsoft.com/kb/2494036): доступно исправление, позволяющее настраивать узел кластера, не имеющий голосов кворума, в [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] и [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e21a6-111">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="e21a6-112">Если это исправление не установлено, то в примерах этого раздела будут возвращены пустые значения или значения NULL для NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="e21a6-112">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e21a6-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="e21a6-113">Security</span></span>  
 <span data-ttu-id="e21a6-114">Пользователь должен входить в учетную запись домена, которая является членом локальной группы администраторов, на каждом узле кластера WSFC.</span><span class="sxs-lookup"><span data-stu-id="e21a6-114">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e21a6-115">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e21a6-115">Using Transact-SQL</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="e21a6-116">Просмотр параметров NodeWeight</span><span class="sxs-lookup"><span data-stu-id="e21a6-116">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="e21a6-117">Подключитесь к любому экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в кластере.</span><span class="sxs-lookup"><span data-stu-id="e21a6-117">Connect to any [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the cluster.</span></span>  
  
2.  <span data-ttu-id="e21a6-118">Выполните запрос к представлению [sys].[dm_hadr_cluster_members].</span><span class="sxs-lookup"><span data-stu-id="e21a6-118">Query the [sys].[dm_hadr_cluster_members] view.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="e21a6-119">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e21a6-119">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="e21a6-120">В следующем примере выполняется запрос к системному представлению для возврата значений для всех узлов в кластере данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e21a6-120">The following example queries a system view to return values for all of the nodes in that instance's cluster.</span></span>  
  
```sql  
SELECT  member_name, member_state_desc, number_of_quorum_votes  
 FROM   sys.dm_hadr_cluster_members;  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="e21a6-121">Использование Powershell</span><span class="sxs-lookup"><span data-stu-id="e21a6-121">Using Powershell</span></span>  
  
### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="e21a6-122">Просмотр параметров NodeWeight</span><span class="sxs-lookup"><span data-stu-id="e21a6-122">To view NodeWeight settings</span></span>
  
1.  <span data-ttu-id="e21a6-123">Запустите повышенный режим Windows PowerShell с помощью команды **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="e21a6-123">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="e21a6-124">Импортируйте модуль `FailoverClusters` для включения командлетов кластера.</span><span class="sxs-lookup"><span data-stu-id="e21a6-124">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="e21a6-125">Использование объекта `Get-ClusterNode` для возврата коллекции объектов узла кластера.</span><span class="sxs-lookup"><span data-stu-id="e21a6-125">Use the `Get-ClusterNode` object to return a collection of cluster node objects.</span></span>  
  
4.  <span data-ttu-id="e21a6-126">Выведите свойства узла кластера в удобном для чтения формате.</span><span class="sxs-lookup"><span data-stu-id="e21a6-126">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="e21a6-127">Пример (Powershell)</span><span class="sxs-lookup"><span data-stu-id="e21a6-127">Example (Powershell)</span></span>  
 <span data-ttu-id="e21a6-128">В следующем примере показан вывод некоторых свойств узла для кластера с именем Cluster001.</span><span class="sxs-lookup"><span data-stu-id="e21a6-128">The following example output some of the node properties for the cluster called "Cluster001".</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$cluster = "Cluster001"  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -Property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="e21a6-129">Использование Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="e21a6-129">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e21a6-130">Программа cluster.exe является устаревшей в выпуске [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e21a6-130">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="e21a6-131">Для будущих разработок используйте PowerShell с отказоустойчивым кластером.</span><span class="sxs-lookup"><span data-stu-id="e21a6-131">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="e21a6-132">Программа cluster.exe будет удалена в следующем выпуске Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e21a6-132">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="e21a6-133">Дополнительные сведения см. в разделе [Сопоставление команд Cluster.exe с командлетами Windows PowerShell для отказоустойчивых кластеров](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="e21a6-133">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="e21a6-134">Просмотр параметров NodeWeight</span><span class="sxs-lookup"><span data-stu-id="e21a6-134">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="e21a6-135">Запустите повышенный режим командной строки с помощью команды **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="e21a6-135">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="e21a6-136">Использование **cluster.exe** для возврата состояния узла и значений NodeWeight</span><span class="sxs-lookup"><span data-stu-id="e21a6-136">Use **cluster.exe** to return node status and NodeWeight values</span></span>  
  
### <a name="example-clusterexe"></a><span data-ttu-id="e21a6-137">Пример (Cluster.exe)</span><span class="sxs-lookup"><span data-stu-id="e21a6-137">Example (Cluster.exe)</span></span>  
 <span data-ttu-id="e21a6-138">В следующем примере показан вывод некоторых свойств узла для кластера с именем Cluster001.</span><span class="sxs-lookup"><span data-stu-id="e21a6-138">The following example outputs some of the node properties for the cluster called "Cluster001".</span></span>  
  
```cmd
cluster.exe Cluster001 node /status /properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="e21a6-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="e21a6-139">See Also</span></span>  
 <span data-ttu-id="e21a6-140">[Режим кворума и участвующая в голосовании конфигурация WSFC (SQL Server)](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e21a6-140">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="e21a6-141">[Настройка параметров NodeWeight кворума кластера](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="e21a6-141">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="e21a6-142">[sys.dm_hadr_cluster_members (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e21a6-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span></span>  
 <span data-ttu-id="e21a6-143">[Командлеты отказоустойчивого кластера в Windows PowerShell по выполняемым задачам](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e21a6-143">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
