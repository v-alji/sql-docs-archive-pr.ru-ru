---
title: Принудительный запуск кластера WSFC без кворума | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: 4a121375-7424-4444-b876-baefa8fe9015
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6f2110b706de015d0c7b19475b335908c118267
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659273"
---
# <a name="force-a-wsfc-cluster-to-start-without-a-quorum"></a><span data-ttu-id="6bac7-102">Принудительный запуск кластера WSFC без кворума</span><span class="sxs-lookup"><span data-stu-id="6bac7-102">Force a WSFC Cluster to Start Without a Quorum</span></span>
  <span data-ttu-id="6bac7-103">В этом разделе описан порядок принудительного запуска узла отказоустойчивого кластера Windows Server (WSFC) без кворума.</span><span class="sxs-lookup"><span data-stu-id="6bac7-103">This topic describes how to force a Windows Server Failover Clustering (WSFC) cluster node to start without a quorum.</span></span>  <span data-ttu-id="6bac7-104">Это может потребоваться в случае аварийного восстановления, в сценариях с несколькими подсетями и восстановлением данных и высокой доступности экземпляров отказоустойчивого кластера [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6bac7-104">This may be required in disaster recovery and multi-subnet scenarios to recover data and fully re-establish high-availability for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="6bac7-105">**Перед началом:**  [Рекомендации](#Recommendations), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="6bac7-105">**Before you start:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="6bac7-106">**Принудительный запуск кластера без кворума с использованием**  [Использование диспетчера отказоустойчивого кластера.](#FailoverClusterManagerProcedure), [Использование Powershell](#PowerShellProcedure), [Использование Net.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="6bac7-106">**To force a cluster to start without a quorum using:**  [Using Failover Cluster Manager](#FailoverClusterManagerProcedure), [Using Powershell](#PowerShellProcedure), [Using Net.exe](#CommandPromptProcedure)</span></span>  
  
-   <span data-ttu-id="6bac7-107">**Дальнейшие действия:**  [исполнению: после перезапуска кластера для запуска без кворума](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="6bac7-107">**Follow up:**  [Follow Up: After Forcing Cluster to Start without a Quorum](#FollowUp)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6bac7-108">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="6bac7-108">Before You Start</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6bac7-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="6bac7-109">Recommendations</span></span>  
 <span data-ttu-id="6bac7-110">Процедуры в этом разделе (кроме указанных явно случаев) должны успешно действовать при выполнении на любом узле отказоустойчивого кластера WSFC.</span><span class="sxs-lookup"><span data-stu-id="6bac7-110">Except where explicitly directed, the procedures in this topic should work if you execute them from any node in the WSFC cluster.</span></span>  <span data-ttu-id="6bac7-111">Однако можно получить лучшие результаты и избежать проблем с сетью при выполнении этих действий с узла, который планируется запускать принудительно без кворума.</span><span class="sxs-lookup"><span data-stu-id="6bac7-111">However, you may obtain better results, and avoid networking issues, by executing these steps from the node that you intend to force to start without a quorum.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6bac7-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="6bac7-112">Security</span></span>  
 <span data-ttu-id="6bac7-113">Пользователь должен входить в учетную запись домена, которая является членом локальной группы администраторов, на каждом узле кластера WSFC.</span><span class="sxs-lookup"><span data-stu-id="6bac7-113">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-failover-cluster-manager"></a><a name="FailoverClusterManagerProcedure"></a><span data-ttu-id="6bac7-114">Использование диспетчер отказоустойчивости кластеров</span><span class="sxs-lookup"><span data-stu-id="6bac7-114">Using Failover Cluster Manager</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="6bac7-115">Принудительный запуск кластера без кворума</span><span class="sxs-lookup"><span data-stu-id="6bac7-115">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="6bac7-116">Откройте диспетчер отказоустойчивого кластера и подключитесь к требуемому узлу кластера в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="6bac7-116">Open a Failover Cluster Manager and connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="6bac7-117">На панели **действия** выберите **Принудительное начало работы кластера**, а затем щелкните **Да — принудительно запустить мой кластер**.</span><span class="sxs-lookup"><span data-stu-id="6bac7-117">In the **Actions** pane, click **Force Cluster Start**, and then click **Yes - Force my cluster to start**.</span></span>  
  
3.  <span data-ttu-id="6bac7-118">На левой панели в дереве **Диспетчер отказоустойчивого кластера** щелкните имя кластера.</span><span class="sxs-lookup"><span data-stu-id="6bac7-118">In the left pane, in the **Failover Cluster Manager** tree, click the cluster name.</span></span>  
  
4.  <span data-ttu-id="6bac7-119">На сводной панели подтвердите, что текущим значением **Настройка кворума** является  **Предупреждение: кластер находится в состоянии принудительного кворума**.</span><span class="sxs-lookup"><span data-stu-id="6bac7-119">In the summary pane, confirm that the current **Quorum Configuration** value is:  **Warning: Cluster is running in ForceQuorum state**.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a><span data-ttu-id="6bac7-120">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bac7-120">Using Powershell</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="6bac7-121">Принудительный запуск кластера без кворума</span><span class="sxs-lookup"><span data-stu-id="6bac7-121">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="6bac7-122">Запустите повышенный режим Windows PowerShell с помощью команды **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="6bac7-122">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="6bac7-123">Импортируйте модуль `FailoverClusters` для включения командлетов кластера.</span><span class="sxs-lookup"><span data-stu-id="6bac7-123">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="6bac7-124">С помощью `Stop-ClusterNode` обеспечьте остановку службы кластеров.</span><span class="sxs-lookup"><span data-stu-id="6bac7-124">Use `Stop-ClusterNode` to make sure that the cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="6bac7-125">Принудительный запуск службы кластеров с помощью `Start-ClusterNode` с `-FixQuorum` .</span><span class="sxs-lookup"><span data-stu-id="6bac7-125">Use `Start-ClusterNode` with `-FixQuorum` to force the cluster service to start.</span></span>  
  
5.  <span data-ttu-id="6bac7-126">С помощью `Get-ClusterNode` с `-Propery NodeWieght = 1` установите значение, которое гарантирует для узла право голоса в кворуме.</span><span class="sxs-lookup"><span data-stu-id="6bac7-126">Use `Get-ClusterNode` with `-Propery NodeWieght = 1` to set the value the guarantees that the node is a voting member of the quorum.</span></span>  
  
6.  <span data-ttu-id="6bac7-127">Выведите свойства узла кластера в удобном для чтения формате.</span><span class="sxs-lookup"><span data-stu-id="6bac7-127">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="6bac7-128">Пример (Powershell)</span><span class="sxs-lookup"><span data-stu-id="6bac7-128">Example (Powershell)</span></span>  
 <span data-ttu-id="6bac7-129">В следующем примере происходит принудительный запуск службы кластеров узла AlwaysOnSrv02 без кворума: задается значение `NodeWeight = 1`, затем перечисляется состояние узла кластера с вновь запущенного узла.</span><span class="sxs-lookup"><span data-stu-id="6bac7-129">The following example forces the AlwaysOnSrv02 node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv02"  
Stop-ClusterNode -Name $node  
Start-ClusterNode -Name $node -FixQuorum  
  
(Get-ClusterNode $node).NodeWeight = 1  
  
$nodes = Get-ClusterNode -Cluster $node  
$nodes | Format-Table -property NodeName, State, NodeWeight
```  
  
##  <a name="using-netexe"></a><a name="CommandPromptProcedure"></a><span data-ttu-id="6bac7-130">Использование Net.exe</span><span class="sxs-lookup"><span data-stu-id="6bac7-130">Using Net.exe</span></span>  
  
### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="6bac7-131">Принудительный запуск кластера без кворума</span><span class="sxs-lookup"><span data-stu-id="6bac7-131">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="6bac7-132">С помощью удаленного рабочего стола подключитесь к нужному узлу кластера в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="6bac7-132">Use Remote Desktop to connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="6bac7-133">Запустите повышенный режим командной строки с помощью команды **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="6bac7-133">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
3.  <span data-ttu-id="6bac7-134">С помощью **net.exe** остановите локальную службу кластеров.</span><span class="sxs-lookup"><span data-stu-id="6bac7-134">Use **net.exe** to make sure that the local cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="6bac7-135">С помощью **net.exe** с `/forcequorum` принудительно запустите локальную службу кластеров.</span><span class="sxs-lookup"><span data-stu-id="6bac7-135">Use **net.exe** with `/forcequorum` to force the local cluster service to start.</span></span>  
  
### <a name="example-netexe"></a><span data-ttu-id="6bac7-136">Пример (Net.exe)</span><span class="sxs-lookup"><span data-stu-id="6bac7-136">Example (Net.exe)</span></span>  
 <span data-ttu-id="6bac7-137">В следующем примере происходит принудительный запуск службы кластеров узла без кворума: задается значение `NodeWeight = 1`, затем перечисляется состояние узла кластера с вновь запущенного узла.</span><span class="sxs-lookup"><span data-stu-id="6bac7-137">The following example forces a node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```cmd
net.exe stop clussvc  
net.exe start clussvc /forcequorum  
```  
  
##  <a name="follow-up-after-forcing-cluster-to-start-without-a-quorum"></a><a name="FollowUp"></a><span data-ttu-id="6bac7-138">Дальнейшие действия. После принудительного запуска кластера без кворума</span><span class="sxs-lookup"><span data-stu-id="6bac7-138">Follow Up: After Forcing Cluster to Start without a Quorum</span></span>  
  
-   <span data-ttu-id="6bac7-139">Необходимо повторно оценить и настроить значения параметров NodeWeight для правильного построения нового кворума, прежде чем переключать другие узлы обратно в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="6bac7-139">You must re-evaluate and reconfigure NodeWeight values to correctly construct a new quorum before bringing other nodes back online.</span></span> <span data-ttu-id="6bac7-140">В противном случае кластер может снова вернуться в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="6bac7-140">Otherwise, the cluster may go back offline again.</span></span>  
  
     <span data-ttu-id="6bac7-141">Дополнительные сведения см. в статье [Режимы кворума и конфигурация голосования WSFC (SQL Server)](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6bac7-141">For more information, see [WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="6bac7-142">Процедуры в этом разделе представляют только один шаг в возвращении отказоустойчивого кластера Windows обратно в режим «в сети» в случае незапланированного сбоя кворума.</span><span class="sxs-lookup"><span data-stu-id="6bac7-142">The procedures in this topic are only one step in bringing the WSFC cluster back online if an un-planned quorum failure were to occur.</span></span>  <span data-ttu-id="6bac7-143">Кроме того, могут потребоваться дополнительные действия, позволяющие предотвратить помехи со стороны других узлов отказоустойчивого кластера WSFC в настройке нового кворума.</span><span class="sxs-lookup"><span data-stu-id="6bac7-143">You may also want to take additional steps to prevent other WSFC cluster nodes from interfering with the new quorum configuration.</span></span>  
  
-   <span data-ttu-id="6bac7-144">Другие функции [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , например [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], зеркальное отображение базы данных и доставка журналов, могут также требовать последующих действий по восстановлению данных и полному восстановлению высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="6bac7-144">Other [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features such as [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], database mirroring, and log shipping may also require subsequent actions to recover data and to fully re-establish high-availability.</span></span>  
  
     <span data-ttu-id="6bac7-145">**Дополнительные сведения:**</span><span class="sxs-lookup"><span data-stu-id="6bac7-145">**For more information:**</span></span>  
  
     [<span data-ttu-id="6bac7-146">Выполнение принудительного перехода на другой ресурс вручную для группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6bac7-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](../../../database-engine/availability-groups/windows/perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
     [<span data-ttu-id="6bac7-147">Принудительный запуск службы в сеансе зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6bac7-147">Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](../../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)  
  
     [<span data-ttu-id="6bac7-148">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6bac7-148">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](../../../database-engine/log-shipping/fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="6bac7-149">См. также</span><span class="sxs-lookup"><span data-stu-id="6bac7-149">Related Content</span></span>  
  
-   <span data-ttu-id="6bac7-150">[Просмотр событий и журналов для отказоустойчивого кластера](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="6bac7-150">[View Events and Logs for a Failover Cluster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span></span>  
  
-   [<span data-ttu-id="6bac7-151">Командлет Get-ClusterLog отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="6bac7-151">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="6bac7-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="6bac7-152">See Also</span></span>  
 <span data-ttu-id="6bac7-153">[Аварийное восстановление WSFC с помощью принудительного &#40;кворума SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6bac7-153">[WSFC Disaster Recovery through Forced Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span></span>  
 <span data-ttu-id="6bac7-154">[Настройка параметров NodeWeight кворума кластера](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="6bac7-154">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="6bac7-155">[Командлеты отказоустойчивого кластера в Windows PowerShell по выполняемым задачам](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="6bac7-155">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
