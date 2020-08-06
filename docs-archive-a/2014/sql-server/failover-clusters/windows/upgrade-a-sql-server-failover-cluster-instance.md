---
title: Обновление SQL Server отказоустойчивого кластера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- upgrading failover clusters
- clusters [SQL Server], upgrading
- failover clustering [SQL Server], upgrading
ms.assetid: daac41fe-7d0b-4f14-84c2-62952ad8cbfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ca08e83c362e714f234a60ee358df3bcb03ade93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659272"
---
# <a name="upgrade-a-sql-server-failover-cluster"></a><span data-ttu-id="9cc29-102">Обновление отказоустойчивого кластера SQL Server</span><span class="sxs-lookup"><span data-stu-id="9cc29-102">Upgrade a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9cc29-103">поддерживает отдельное обновление компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] и служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] с версий [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] и [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] отказоустойчивого кластера на всех узлах отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="9cc29-103">supports upgrade of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)], and [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all failover cluster nodes.</span></span>  
  
 <span data-ttu-id="9cc29-104">Далее приведены сведения о поддержке:</span><span class="sxs-lookup"><span data-stu-id="9cc29-104">Support details are as follows:</span></span>  
  
-   <span data-ttu-id="9cc29-105">Обновление поддерживается как через пользовательский интерфейс, так и из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9cc29-105">Upgrade is supported both through the user interface and from the command prompt.</span></span> <span data-ttu-id="9cc29-106">Дополнительные сведения см. в статьях [Обновление экземпляра отказоустойчивого кластера SQL Server (программа установки)](upgrade-a-sql-server-failover-cluster-instance-setup.md) и [Установка SQL Server 2014 из командной строки](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="9cc29-106">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) and [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
-   <span data-ttu-id="9cc29-107">Обновление с. для [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] обновления каждого узла кластера можно запустить обновление из командной строки на каждом узле отказоустойчивого кластера или с помощью пользовательского интерфейса программы установки.</span><span class="sxs-lookup"><span data-stu-id="9cc29-107">Upgrading from [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] - You can run upgrade from the command prompt on each failover cluster node, or by using the Setup UI to upgrade each cluster node.</span></span> <span data-ttu-id="9cc29-108">Если компоненты Full-Text Search и репликации не существуют на обновляемом экземпляре, они будут установлены автоматически, при этом возможности отключить их установку нет.</span><span class="sxs-lookup"><span data-stu-id="9cc29-108">If Full-text search and Replication features do not exist on the instance being upgraded, they will be installed automatically with no option to omit them.</span></span>  
  
-   <span data-ttu-id="9cc29-109">Установка пакета обновления — на отказоустойчивых кластерах [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] пакеты обновления и обновления [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] следует устанавливать для каждого узла отдельно.</span><span class="sxs-lookup"><span data-stu-id="9cc29-109">Service pack installation - you must apply [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service packs and patches to [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all nodes.</span></span>  
  
-   <span data-ttu-id="9cc29-110">Следующие сценарии не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="9cc29-110">The following scenarios are not supported:</span></span>  
  
    -   <span data-ttu-id="9cc29-111">Невозможно перенести изолированный экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на кластер отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="9cc29-111">You cannot migrate from a stand-alone instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to a failover cluster.</span></span>  
  
    -   <span data-ttu-id="9cc29-112">Добавление компонентов в кластер отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="9cc29-112">Add features to a failover cluster.</span></span> <span data-ttu-id="9cc29-113">Например, невозможно добавить компонент [!INCLUDE[ssDE](../../../includes/ssde-md.md)] в существующий отказоустойчивый кластер, имеющий только службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cc29-113">For example, you cannot add the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to an existing [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]-only failover cluster.</span></span>  
  
    -   <span data-ttu-id="9cc29-114">Невозможно понизить узел отказоустойчивого кластера до изолированного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9cc29-114">You cannot downgrade a failover cluster node to a stand-alone instance.</span></span>  
  
-   <span data-ttu-id="9cc29-115">Дополнительные сведения см. в статье [Экземпляры отказоустойчивого кластера (режим AlwaysOn) (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9cc29-115">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="upgrading-a-ssnoversion-multi-subnet-failover-cluster"></a><span data-ttu-id="9cc29-116">Обновление отказоустойчивого кластера с несколькими подсетями [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc29-116">Upgrading a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Multi-Subnet Failover Cluster</span></span>  
 <span data-ttu-id="9cc29-117">Нельзя напрямую обновить отказоустойчивый кластер, не использующий несколько подсетей, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] отказоустойчивый кластер с несколькими подсетями.</span><span class="sxs-lookup"><span data-stu-id="9cc29-117">You cannot directly upgrade a non-multi-subnet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] multi-subnet failover cluster.</span></span> <span data-ttu-id="9cc29-118">Дополнительные сведения см. на разделе [Обновление экземпляра отказоустойчивого кластера SQL Server (программа установки)](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span><span class="sxs-lookup"><span data-stu-id="9cc29-118">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc29-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="9cc29-119">See Also</span></span>  
 <span data-ttu-id="9cc29-120">[Поддерживаемые обновления версий и выпусков](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="9cc29-120">[Supported Version and Edition Upgrades](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 <span data-ttu-id="9cc29-121">[Обновление экземпляра отказоустойчивого кластера SQL Server &#40;установки&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="9cc29-121">[Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="9cc29-122">Install SQL Server 2014 from the Command Prompt</span><span class="sxs-lookup"><span data-stu-id="9cc29-122">Install SQL Server 2014 from the Command Prompt</span></span>](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)  
  
  
