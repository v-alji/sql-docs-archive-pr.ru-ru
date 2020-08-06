---
title: Топологии для веб-синхронизации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web synchronization, topologies
- IIS server configuration [SQL Server replication]
ms.assetid: 59444faf-bcb6-4421-a3df-8715753e453b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5e28ca5a222e2286d154c16ef41d3147dc56e25a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664861"
---
# <a name="topologies-for-web-synchronization"></a><span data-ttu-id="2397c-102">Topologies for Web Synchronization</span><span class="sxs-lookup"><span data-stu-id="2397c-102">Topologies for Web Synchronization</span></span>
  <span data-ttu-id="2397c-103">Существует несколько топологий репликации [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="2397c-103">You can choose from a variety of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Web synchronization replication topologies.</span></span> <span data-ttu-id="2397c-104">Наиболее часто используемые способы настройки веб-синхронизации включают в себя следующие.</span><span class="sxs-lookup"><span data-stu-id="2397c-104">Common ways to configure Web synchronization include:</span></span>  
  
-   <span data-ttu-id="2397c-105">Отдельный сервер</span><span class="sxs-lookup"><span data-stu-id="2397c-105">Single server</span></span>  
  
-   <span data-ttu-id="2397c-106">Два сервера</span><span class="sxs-lookup"><span data-stu-id="2397c-106">Two servers</span></span>  
  
-   <span data-ttu-id="2397c-107">Несколько системы на основе служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] IIS и переиздание с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2397c-107">Multiple [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) systems and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] republishing</span></span>  
  
 <span data-ttu-id="2397c-108">Дополнительные сведения о конфигурации для веб-синхронизации см. в статье [Настройка веб-синхронизации](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="2397c-108">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="single-server"></a><span data-ttu-id="2397c-109">Одиночный сервер</span><span class="sxs-lookup"><span data-stu-id="2397c-109">Single Server</span></span>  
 <span data-ttu-id="2397c-110">В самой простой топологии, службах IIS, издатель [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и распространитель [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] вместе находятся на одиночном сервере.</span><span class="sxs-lookup"><span data-stu-id="2397c-110">In the simplest topology, IIS, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor all reside on a single server.</span></span> <span data-ttu-id="2397c-111">Подписчики осуществляют синхронизацию, подключаясь к службам IIS на издателе.</span><span class="sxs-lookup"><span data-stu-id="2397c-111">Subscribers synchronize by connecting to IIS on the Publisher.</span></span> <span data-ttu-id="2397c-112">Издатель может быть защищен брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="2397c-112">The Publisher can be located behind a firewall.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2397c-113">Данная конфигурация рекомендуется только для сценариев, использующих корпоративные сети.</span><span class="sxs-lookup"><span data-stu-id="2397c-113">This configuration is recommended only for intranet scenarios.</span></span> <span data-ttu-id="2397c-114">Для других сценариев рекомендуется, чтобы сервер IIS и издатель/распространитель [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] находились на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="2397c-114">For other scenarios, it is recommended that the IIS server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher/Distributor be on separate computers.</span></span>  
  
 <span data-ttu-id="2397c-115">![Веб-синхронизация с одиночным сервером](media/web-sync02.gif "Веб-синхронизация с одиночным сервером")</span><span class="sxs-lookup"><span data-stu-id="2397c-115">![Web synchronization with a single server](media/web-sync02.gif "Web synchronization with a single server")</span></span>  
  
## <a name="two-servers"></a><span data-ttu-id="2397c-116">Два сервера</span><span class="sxs-lookup"><span data-stu-id="2397c-116">Two Servers</span></span>  
 <span data-ttu-id="2397c-117">Можно установить службы IIS на один сервер и настроить издатель и распространитель [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на другом сервере.</span><span class="sxs-lookup"><span data-stu-id="2397c-117">You can place IIS on one server and configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher and Distributor on another server.</span></span> <span data-ttu-id="2397c-118">Сервер, на котором запускаются службы IIS, может быть изолирован от Интернета брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="2397c-118">The server running IIS can be isolated from the Internet by a firewall.</span></span> <span data-ttu-id="2397c-119">Подписчики осуществляют синхронизацию, подключаясь к службам IIS.</span><span class="sxs-lookup"><span data-stu-id="2397c-119">Subscribers synchronize by connecting to IIS.</span></span>  
  
 <span data-ttu-id="2397c-120">![Веб-синхронизация с двумя серверами](media/web-sync03.gif "Веб-синхронизация с двумя серверами")</span><span class="sxs-lookup"><span data-stu-id="2397c-120">![Web synchronization with two servers](media/web-sync03.gif "Web synchronization with two servers")</span></span>  
  
## <a name="multiple-iis-systems-and-sql-server-republishing"></a><span data-ttu-id="2397c-121">Несколько систем IIS и переиздание с помощью SQL Server</span><span class="sxs-lookup"><span data-stu-id="2397c-121">Multiple IIS Systems and SQL Server Republishing</span></span>  
 <span data-ttu-id="2397c-122">При необходимости поддержки очень большого количества подписчиков, одновременно осуществляющих синхронизацию, можно разделить работу между несколькими компьютерам, на которых выполняются службы IIS.</span><span class="sxs-lookup"><span data-stu-id="2397c-122">If you need to support very large numbers of Subscribers that synchronize at the same time, you can partition the work across multiple computers running IIS.</span></span>  
  
 <span data-ttu-id="2397c-123">![Веб-синхронизация с несколькими серверами IIS](media/web-sync04.gif "Веб-синхронизация с несколькими серверами IIS")</span><span class="sxs-lookup"><span data-stu-id="2397c-123">![Web synchronization with multiple IIS servers](media/web-sync04.gif "Web synchronization with multiple IIS servers")</span></span>  
  
 <span data-ttu-id="2397c-124">Если требуется дополнительная балансировка нагрузки на компьютере, использующем [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], можно создать иерархию переиздания на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="2397c-124">If further load balancing is required on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can create a republishing hierarchy on multiple computers.</span></span> <span data-ttu-id="2397c-125">Издатель верхнего уровня публикует данные на подписчики, которые, в свою очередь, переиздают данные, осуществляя выравнивание нагрузки при обработке запросов от подписчиков.</span><span class="sxs-lookup"><span data-stu-id="2397c-125">The top-level Publisher publishes data to Subscribers, which in turn republish the data, load balancing requests from the Subscribers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2397c-126">Подписчики могут синхронизироваться только с конкретным издателем.</span><span class="sxs-lookup"><span data-stu-id="2397c-126">Subscribers can only synchronize with a specific Publisher.</span></span> <span data-ttu-id="2397c-127">Например, подписчик на переиздающий подписчик A не может синхронизироваться с переиздающим подписчиком Б, если переиздающий подписчик А недоступен.</span><span class="sxs-lookup"><span data-stu-id="2397c-127">For example, a Subscriber to republisher A cannot synchronize with republisher B when A is not available.</span></span>  
  
 <span data-ttu-id="2397c-128">![Веб-синхронизация с повторной публикацией](media/web-sync05.gif "Веб-синхронизация с повторной публикацией")</span><span class="sxs-lookup"><span data-stu-id="2397c-128">![Web synchronization with republishing](media/web-sync05.gif "Web synchronization with republishing")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2397c-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="2397c-129">See Also</span></span>  
 <span data-ttu-id="2397c-130">[Configure Web Synchronization](configure-web-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="2397c-130">[Configure Web Synchronization](configure-web-synchronization.md) </span></span>  
 [<span data-ttu-id="2397c-131">Web Synchronization for Merge Replication</span><span class="sxs-lookup"><span data-stu-id="2397c-131">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
