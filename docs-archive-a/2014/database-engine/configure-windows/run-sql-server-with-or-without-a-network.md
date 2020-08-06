---
title: Запуск SQL Server при наличии и отсутствии сети | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- verifying Server service has been started
- net start [SQL Server]
- command prompt [SQL Server], connections
- SQL Server services, networks
- status information [SQL Server], Server service
- running SQL Server
- networking [SQL Server], SQL Server with or without
- services [SQL Server], networks
- starting Server service
- SQL Server, running
ms.assetid: 54eac961-5c7a-4481-982d-f93a64b5c2f4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a80e7e4d42f322bc42d0c67c57e3a1f9bddb87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664486"
---
# <a name="run-sql-server-with-or-without-a-network"></a><span data-ttu-id="34904-102">Запуск SQL Server при наличии и отсутствии сети</span><span class="sxs-lookup"><span data-stu-id="34904-102">Run SQL Server With or Without a Network</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="34904-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может работать в сети или без подключения к ней.</span><span class="sxs-lookup"><span data-stu-id="34904-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can run on a network, or it can function without a network.</span></span>  
  
## <a name="running-sql-server-on-a-network"></a><span data-ttu-id="34904-104">Запуск SQL Server при подключении к сети</span><span class="sxs-lookup"><span data-stu-id="34904-104">Running SQL Server on a Network</span></span>  
 <span data-ttu-id="34904-105">Чтобы сервер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] мог взаимодействовать с клиентами и другими серверами в сети, должна быть запущена служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34904-105">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to communicate over a network, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service must be running.</span></span> <span data-ttu-id="34904-106">По умолчанию [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows автоматически запускает встроенную службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34904-106">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows automatically starts the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="34904-107">Чтобы определить, была ли запущена служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="34904-107">To find out whether the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has been started, at the command prompt, type the following:</span></span>  
  
 <span data-ttu-id="34904-108">**net start**</span><span class="sxs-lookup"><span data-stu-id="34904-108">**net start**</span></span>  
  
 <span data-ttu-id="34904-109">Если службы, связанные с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , запущены, следующие службы отобразятся в выходных данных команды **net start** :</span><span class="sxs-lookup"><span data-stu-id="34904-109">If the services associated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] have been started, the following services will appear in the **net start** output:</span></span>  
  
-   <span data-ttu-id="34904-110">Службы Analysis Services (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="34904-110">Analysis Services (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="34904-111">SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="34904-111">SQL Server (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="34904-112">SQL Server Agent (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="34904-112">SQL Server Agent (MSSQLSERVER)</span></span>  
  
## <a name="running-sql-server-without-a-network"></a><span data-ttu-id="34904-113">Запуск SQL Server без подключения к сети</span><span class="sxs-lookup"><span data-stu-id="34904-113">Running SQL Server Without a Network</span></span>  
 <span data-ttu-id="34904-114">При запуске экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] без подключения к сети нет необходимости запускать встроенную службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34904-114">When running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without a network, you do not need to start the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="34904-115">Поскольку [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], диспетчер конфигураций SQL Server и команды **net start** и **net stop** могут работать даже без подключения к сети, процедуры запуска и остановки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] аналогичны при работе в сети и автономной работе.</span><span class="sxs-lookup"><span data-stu-id="34904-115">Because [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], SQL Server Configuration Manager, and the **net start** and **net stop** commands are functional even without a network, the procedures for starting and stopping an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are identical for a network or stand-alone operation.</span></span>  
  
 <span data-ttu-id="34904-116">При подключении к изолированному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из локального клиента, например **sqlcmd**, осуществляется обход сети и подключение к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] напрямую через локальный канал.</span><span class="sxs-lookup"><span data-stu-id="34904-116">When connecting to an instance of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a local client such as **sqlcmd**, you bypass the network and connect directly to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a local pipe.</span></span> <span data-ttu-id="34904-117">Разница между локальным и сетевым каналами заключается в использовании сети.</span><span class="sxs-lookup"><span data-stu-id="34904-117">The difference between a local pipe and a network pipe is whether you are using a network.</span></span> <span data-ttu-id="34904-118">И локальный, и сетевой каналы устанавливают соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] через стандартный канал (\\\\.\pipe\sql\query), если не указано другое.</span><span class="sxs-lookup"><span data-stu-id="34904-118">Both local and network pipes establish a connection with an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the standard pipe (\\\\.\pipe\sql\query), unless otherwise directed.</span></span>  
  
 <span data-ttu-id="34904-119">При подключении к локальному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] без указания имени сервера используется локальный канал.</span><span class="sxs-lookup"><span data-stu-id="34904-119">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without specifying a server name, you are using a local pipe.</span></span> <span data-ttu-id="34904-120">При подключении к локальному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с явным указанием имени сервера используется или сетевой канал, или другой механизм сетевого межпроцессного взаимодействия (IPC), например через протоколы межсетевого и последовательного обмена пакетами (IPX/SPX), если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен для работы с несколькими сетями.</span><span class="sxs-lookup"><span data-stu-id="34904-120">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and specify a server name explicitly, you are using either a network pipe or another network interprocess communication (IPC) mechanism, such as Internetwork Packet Exchange/Sequenced Packet Exchange (IPX/SPX) (assuming you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use multiple networks).</span></span> <span data-ttu-id="34904-121">Так как отдельный сервер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживает сетевые каналы, при соединении с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из клиента ненужный аргумент **/** _<имя_сервера>_ необходимо опустить.</span><span class="sxs-lookup"><span data-stu-id="34904-121">Because a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support network pipes, you must omit the unnecessary **/**_<Server_name>_ argument when connecting to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client.</span></span> <span data-ttu-id="34904-122">Например, для подключения к отдельному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из **osql**введите:</span><span class="sxs-lookup"><span data-stu-id="34904-122">For example, to connect to a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from **osql**, type:</span></span>  
  
 <span data-ttu-id="34904-123">**osql /Usa /P** _\<saPassword>_</span><span class="sxs-lookup"><span data-stu-id="34904-123">**osql /Usa /P** _\<saPassword>_</span></span>  
  
  
