---
title: Конфигурация сети кластера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster network selection, Setup
- cluster network selection
ms.assetid: 579482ef-a023-45b2-9176-b4a4188adf9d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 17ab563817a3b9b476dfd566f4a7f2beda98ca26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659213"
---
# <a name="cluster-network-configuration"></a><span data-ttu-id="1f1ff-102">Конфигурация сети кластера</span><span class="sxs-lookup"><span data-stu-id="1f1ff-102">Cluster Network Configuration</span></span>
  <span data-ttu-id="1f1ff-103">Страница **Выбор сети кластера** используется для указания сетевого ресурса для экземпляра отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-103">Use the **Cluster Network Selection** page to specify the network resources for your failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f1ff-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="1f1ff-104">Options</span></span>  
 <span data-ttu-id="1f1ff-105">\*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Сетевое имя отказоустойчивого кластера\*\* — это имя, используемое для обнаружения экземпляра отказоустойчивого кластера в сети.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-105">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Failover Cluster Network Name** - This is the name used to identify your failover cluster instance on the network.</span></span>  
  
 <span data-ttu-id="1f1ff-106">**Сетевые параметры** — тип IP-адреса и IP-адрес для конкретного экземпляра отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-106">**Network Settings** - Specify the IP type and IP address for your failover cluster instance.</span></span>  
  
 <span data-ttu-id="1f1ff-107">Во время операций добавления или удаления узла [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображает доступный только для чтения список существующих IP-адресов для отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f1ff-107">During the Add Node and Remove Node operations, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a read-only list of the existing IP addresses for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="1f1ff-108">Интегрированная установка:</span><span class="sxs-lookup"><span data-stu-id="1f1ff-108">Integrated Install:</span></span>  
  
    -   <span data-ttu-id="1f1ff-109">При добавлении узла, поддерживающего идентичный набор подсетей, поддерживаемый существующими узлами отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , дополнительный IP-адрес добавить невозможно.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-109">If you are adding a node that supports an identical set of network subnets supported by the existing nodes of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP addresses can be added.</span></span> <span data-ttu-id="1f1ff-110">Параметр зависимости остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-110">The dependency setting remains unchanged.</span></span>  
  
    -   <span data-ttu-id="1f1ff-111">При добавлении узла, поддерживающего подмножество подсетей, поддерживаемое существующими узлами отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , дополнительные IP-адреса ресурсов добавить невозможно.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-111">If you are adding a node that supports a subset of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP address resources can be added.</span></span> <span data-ttu-id="1f1ff-112">Для параметра зависимости ресурса IP-адреса задается значение ИЛИ, указывающее, что все указанные IP-адреса являются недопустимыми на всех узлах кластера.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-112">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="1f1ff-113">При добавлении узла, поддерживающего подсети в дополнение к подсетям, поддерживаемым существующими узлами отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , есть возможность добавить новые допустимые IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-113">If you are adding a node that supports subnets in addition to the subnets already supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you have the option of adding new valid IP addresses.</span></span> <span data-ttu-id="1f1ff-114">Если указаны новые IP-адреса, для параметра зависимости ресурса IP-адреса задается значение ИЛИ, указывающее, что все указанные IP-адреса являются недопустимыми на всех узлах кластера.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-114">If new IP addresses are specified, the IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="1f1ff-115">При добавлении узла, поддерживающего дополнительные подсети, но не поддерживающего ни одну из подсетей, поддерживаемых существующими узлами отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо добавить дополнительные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-115">If you are adding a node that supports additional network subnets, but supports none of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are required to add additional IP addresses.</span></span> <span data-ttu-id="1f1ff-116">Для параметра зависимости ресурса IP-адреса задается значение ИЛИ, указывающее, что все указанные IP-адреса являются недопустимыми на всех узлах кластера.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-116">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
-   <span data-ttu-id="1f1ff-117">Расширенная установка: на шаге завершения установки укажите IP-адрес для всех узлов и подсетей экземпляра отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-117">Advanced Install: During the Complete step of the installation, specify the IP address for all the nodes and subnets for your failover cluster instance.</span></span> <span data-ttu-id="1f1ff-118">Для отказоустойчивого кластера с несколькими подсетями можно задать несколько IP-адресов, но поддерживается только один IP-адрес для каждой подсети.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-118">You can specify multiple IP addresses for a multi-subnet failover cluster, but only one IP address per subnet is supported.</span></span> <span data-ttu-id="1f1ff-119">Каждый подготовленный узел должен быть владельцем по крайней мере одного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-119">Every prepared node should be an owner of at least one IP address.</span></span> <span data-ttu-id="1f1ff-120">Если в кластере отработки отказа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеется несколько подсетей, появится запрос на указание для параметра зависимости ресурса IP-адреса значения OR.Remove Node:</span><span class="sxs-lookup"><span data-stu-id="1f1ff-120">If you have multiple subnets in your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are prompted to set the IP address resource dependency to OR.Remove Node:</span></span>  
  
    -   <span data-ttu-id="1f1ff-121">Если оставшиеся IP-адреса поддерживаются на всех оставшихся узлах, появится запрос на указание для параметра зависимости ресурса IP-адреса значения И.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-121">If the remaining IP addresses are supported on all the remaining nodes, you are prompted to set the IP address resource dependencyto AND.</span></span>  
  
    -   <span data-ttu-id="1f1ff-122">Если оставшиеся IP-адреса не поддерживаются на всех оставшихся узлах, то для параметра зависимости ресурса IP-адреса останется значение ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="1f1ff-122">If the remaining IP addresses are not supported on all the remaining nodes, the IP address resource dependency is left as OR.</span></span>  
  
  
