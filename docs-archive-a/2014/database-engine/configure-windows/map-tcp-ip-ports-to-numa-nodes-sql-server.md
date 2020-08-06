---
title: Сопоставление портов TCP/IP с узлами NUMA (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- NUMA
- memory [SQL Server], NUMA
- affinity NUMA
- ports [SQL Server], working with NUMA
- CPU [SQL Server], NUMA support
- NUMA, How to map a port to a NUMA node
- NUMA affinity
- TCP/IP [SQL Server], NUMA support
- non-uniform memory access
ms.assetid: 07727642-0266-4cbc-8c55-3c367e4458ca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf4a1bd7e02719d3884011ad3faa20a1ccc6466a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728693"
---
# <a name="map-tcp-ip-ports-to-numa-nodes-sql-server"></a><span data-ttu-id="3d51f-102">Сопоставление портов TCP/IP с узлами NUMA (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3d51f-102">Map TCP IP Ports to NUMA Nodes (SQL Server)</span></span>
  <span data-ttu-id="3d51f-103">В этом разделе описывается сопоставление портов TCP/IP с узлами архитектуры доступа к неоднородной памяти (NUMA) с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d51f-103">This topic describes how to map TCP/IP ports to non-uniform memory access (NUMA) nodes by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="3d51f-104">При запуске компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] записывает сведения об узле в журнал ошибок.</span><span class="sxs-lookup"><span data-stu-id="3d51f-104">On startup, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] writes the node information to the error log.</span></span>  
  
 <span data-ttu-id="3d51f-105">Для определения номера используемого узла прочитайте сведения об узле в журнале ошибок или в представлении **sys.dm_os_schedulers** .</span><span class="sxs-lookup"><span data-stu-id="3d51f-105">To determine the node number of the node you want to use, either read the node information from the error log, or from the **sys.dm_os_schedulers** view.</span></span> <span data-ttu-id="3d51f-106">Для установки адреса и порта TCP/IP для одного или нескольких узлов добавьте битовую карту идентификации узла (маску схожести) в квадратных скобках после номера порта.</span><span class="sxs-lookup"><span data-stu-id="3d51f-106">To set a TCP/IP address and port to single or multiple nodes, append a node identification bitmap (an affinity mask) in brackets after the port number.</span></span> <span data-ttu-id="3d51f-107">Узлы могут быть указаны как в десятичном, так и в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="3d51f-107">Nodes can be specified in either decimal or hexadecimal format.</span></span> <span data-ttu-id="3d51f-108">Для создания битовой карты пронумеруйте узлы справа налево начиная от нуля, то есть в порядке 76543210.</span><span class="sxs-lookup"><span data-stu-id="3d51f-108">To create the bitmap, first number the nodes from right to left starting with zero, as in 76543210.</span></span> <span data-ttu-id="3d51f-109">Создайте битовое представление списка узлов, указывая 1 для используемых узлов и 0 — для неиспользуемых.</span><span class="sxs-lookup"><span data-stu-id="3d51f-109">Create a binary representation of the node list, providing 1 for nodes you want to use, and 0 for nodes you do not want to use.</span></span> <span data-ttu-id="3d51f-110">Например, чтобы задействовать узлы NUMA 0, 2 и 5, укажите 00100101.</span><span class="sxs-lookup"><span data-stu-id="3d51f-110">For example, to use NUMA nodes 0, 2, and 5, specify 00100101.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3d51f-111">номер узла NUMA</span><span class="sxs-lookup"><span data-stu-id="3d51f-111">NUMA node number</span></span>|<span data-ttu-id="3d51f-112">76543210</span><span class="sxs-lookup"><span data-stu-id="3d51f-112">76543210</span></span>|  
|<span data-ttu-id="3d51f-113">Отметьте 0, 2 и 5, считая справа</span><span class="sxs-lookup"><span data-stu-id="3d51f-113">Mask for 0, 2, and 5 counting from right</span></span>|<span data-ttu-id="3d51f-114">00100101</span><span class="sxs-lookup"><span data-stu-id="3d51f-114">00100101</span></span>|  
  
 <span data-ttu-id="3d51f-115">Преобразуйте двоичное представление (00100101) в десятичное `[37]`или шестнадцатеричное `[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="3d51f-115">Convert the binary representation (00100101), into decimal `[37]`, or hexadecimal `[0x25]`.</span></span> <span data-ttu-id="3d51f-116">Для прослушивания всех узлов не указывайте идентификатор узла.</span><span class="sxs-lookup"><span data-stu-id="3d51f-116">To listen on all nodes, provide no node identifier.</span></span>  
  
 <span data-ttu-id="3d51f-117">Если порт сопоставлен с более чем одним узлом NUMA, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] назначает соединения с узлами циклическим образом, не пытаясь сохранить баланс нагрузки между разными узлами.</span><span class="sxs-lookup"><span data-stu-id="3d51f-117">If a port is mapped to more than one NUMA node, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns connections to nodes in a round-robin fashion without attempting to balance load across the nodes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3d51f-118">Чтобы настроить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на прослушивание нескольких портов TCP для каждого IP-адреса, см. раздел [Настройка компонента Database Engine на прослушивание нескольких портов TCP](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span><span class="sxs-lookup"><span data-stu-id="3d51f-118">To enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on multiple TCP ports for each IP address, see [Configure the Database Engine to Listen on Multiple TCP Ports](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3d51f-119">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d51f-119">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-map-a-tcpip-port-to-a-numa-node"></a><span data-ttu-id="3d51f-120">Сопоставление порта TCP/IP узлу NUMA</span><span class="sxs-lookup"><span data-stu-id="3d51f-120">To map a TCP/IP port to a NUMA node</span></span>  
  
1.  <span data-ttu-id="3d51f-121">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] раскройте раздел **Сетевая конфигурация SQL Server** и щелкните элемент **Протоколы для**  *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="3d51f-121">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="3d51f-122">В области сведений дважды щелкните **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="3d51f-122">In the details pane, double-click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="3d51f-123">На вкладке **IP-адреса** в разделе, соответствующем настраиваемому IP-адресу, в поле **TCP-порт** добавьте идентификатор узла NUMA в квадратных скобках после номера порта.</span><span class="sxs-lookup"><span data-stu-id="3d51f-123">On the **IP Addresses** tab, in the section corresponding to the IP address to configure, in the **TCP Port** box, add the NUMA node identifier in brackets after the port number.</span></span> <span data-ttu-id="3d51f-124">Например, для TCP-порта 1500 и узлов 0, 2 и 5 используйте `1500[37]` или `1500[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="3d51f-124">For example, for TCP port 1500 and nodes 0, 2, and 5, use `1500[37]`, or `1500[0x25]`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d51f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d51f-125">See Also</span></span>  
 [<span data-ttu-id="3d51f-126">Настройка SQL Server для использования &#40;SQL Server с мягкими NUMA&#41;</span><span class="sxs-lookup"><span data-stu-id="3d51f-126">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)  
  
  
