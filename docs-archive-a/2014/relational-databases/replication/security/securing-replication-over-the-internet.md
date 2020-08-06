---
title: Защита репликации через Интернет | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], Internet
- Internet [SQL Server replication], security
ms.assetid: 25b7af05-2721-4b24-9083-fb671e8bf4e0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47408b2b9559d33da4563c6fc9560d20338ee01d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749704"
---
# <a name="securing-replication-over-the-internet"></a><span data-ttu-id="9e096-102">Securing Replication Over the Internet</span><span class="sxs-lookup"><span data-stu-id="9e096-102">Securing Replication Over the Internet</span></span>
  <span data-ttu-id="9e096-103">Репликация через Интернет может предоставить гибкость, особенно для мобильных подписчиков, но при этом необходимо сконфигурировать репликации через Интернет с обеспечением требуемой безопасности.</span><span class="sxs-lookup"><span data-stu-id="9e096-103">Replication over the Internet can provide flexibility, particularly for mobile Subscribers, but you must configure Internet replication appropriately to ensure adequate security.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="9e096-104">рекомендует использование одной из двух техник безопасной публикации сведений через Интернет.</span><span class="sxs-lookup"><span data-stu-id="9e096-104">recommends using one of two techniques for securely sharing information over the Internet:</span></span>  
  
-   <span data-ttu-id="9e096-105">Виртуальная частная сеть (VPN)</span><span class="sxs-lookup"><span data-stu-id="9e096-105">Virtual private network (VPN)</span></span>  
  
-   <span data-ttu-id="9e096-106">Параметр веб-синхронизации для репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="9e096-106">The Web synchronization option for merge replication</span></span>  
  
## <a name="virtual-private-network"></a><span data-ttu-id="9e096-107">Виртуальная частная сеть</span><span class="sxs-lookup"><span data-stu-id="9e096-107">Virtual Private Network</span></span>  
 <span data-ttu-id="9e096-108">Виртуальные частные сети обеспечивают простой и безопасный многоуровневый подход к репликации данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] через Интернет.</span><span class="sxs-lookup"><span data-stu-id="9e096-108">Virtual private networks provide a simple and secure layered approach to replicating [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data over the Internet.</span></span> <span data-ttu-id="9e096-109">Соединение с виртуальной частной сетью через Интернет логически функционирует как соединение глобальной сети (WAN) между сайтами.</span><span class="sxs-lookup"><span data-stu-id="9e096-109">The VPN connection over the Internet logically operates as a Wide Area Network (WAN) link between the sites.</span></span>  
  
 <span data-ttu-id="9e096-110">Это достигается за счет разрешения пользователям доступа к туннелю через Интернет или другую публичную сеть с помощью протокола PPTP корпорации [!INCLUDE[msCoName](../../../includes/msconame-md.md)] , доступного в операционных системах [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT версии 4.0 или [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000, либо протокола L2TP, доступного в операционной системе Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="9e096-110">This is achieved by allowing the user to tunnel through the Internet or another public network using a protocol such as [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Point-to-Point Tunneling Protocol (PPTP) available with the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT version 4.0 or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000 operating system, or Layer Two Tunneling Protocol (L2TP) available with the Windows 2000 operating system.</span></span> <span data-ttu-id="9e096-111">Этот процесс обеспечивает безопасность и функции, подобные тем, которые доступны в частной сети.</span><span class="sxs-lookup"><span data-stu-id="9e096-111">This process provides security and features similar to those available in a private network.</span></span>  
  
 <span data-ttu-id="9e096-112">Дополнительные сведения о настройке виртуальных частных сетей см. в документации по [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="9e096-112">For more information about setting up a VPN, see the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
## <a name="web-synchronization-through-iis"></a><span data-ttu-id="9e096-113">Веб-синхронизация через IIS</span><span class="sxs-lookup"><span data-stu-id="9e096-113">Web Synchronization Through IIS</span></span>  
 <span data-ttu-id="9e096-114">Параметр веб-синхронизации для репликации слиянием обеспечивает возможность репликации данных по протоколу HTTPS, что представляет собой удобный подход к репликации данных через брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="9e096-114">The web synchronization option for merge replication provides the ability to replicate data using the HTTPS protocol, which can be a convenient approach to replicating data through a firewall.</span></span> <span data-ttu-id="9e096-115">Дополнительные сведения см. в статьях [Настройка веб-синхронизации](../configure-web-synchronization.md) и [Архитектура безопасности для веб-синхронизации](security-architecture-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="9e096-115">For more information, see [Configure Web Synchronization](../configure-web-synchronization.md) and [Security Architecture for Web Synchronization](security-architecture-for-web-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e096-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e096-116">See Also</span></span>  
 <span data-ttu-id="9e096-117">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="9e096-117">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="9e096-118">Безопасность Репликация SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e096-118">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  
