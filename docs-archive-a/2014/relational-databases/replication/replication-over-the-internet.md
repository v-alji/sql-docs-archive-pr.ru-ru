---
title: Репликация через Интернет | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web publishing [SQL Server replication], about Web publishing
- Web publishing [SQL Server replication]
- Internet [SQL Server replication]
- Internet [SQL Server replication], publishing
ms.assetid: 04e7f4ed-e244-4bbe-ba12-09c33abea09e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46c61f8a5383c87d46fa0dbda18876b43ffb7739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655039"
---
# <a name="replication-over-the-internet"></a><span data-ttu-id="2a519-102">Репликация через Интернет</span><span class="sxs-lookup"><span data-stu-id="2a519-102">Replication over the Internet</span></span>
  <span data-ttu-id="2a519-103">Репликация данных через Интернет обеспечивает доступ удаленных автономных пользователей к нужным для них данным с использованием соединения через Интернет.</span><span class="sxs-lookup"><span data-stu-id="2a519-103">Replicating data over the Internet allows remote, disconnected users to access data when they need it using a connection to the Internet.</span></span> <span data-ttu-id="2a519-104">Репликация данных через Интернет:</span><span class="sxs-lookup"><span data-stu-id="2a519-104">Replicate data over the Internet using:</span></span>  
  
-   <span data-ttu-id="2a519-105">Виртуальная частная сеть.</span><span class="sxs-lookup"><span data-stu-id="2a519-105">A Virtual Private Network (VPN).</span></span> <span data-ttu-id="2a519-106">Дополнительные сведения см. в статье [Публикация данных через Интернет с помощью виртуальных частных сетей](publish-data-over-the-internet-using-vpn.md).</span><span class="sxs-lookup"><span data-stu-id="2a519-106">For more information, see [Publish Data over the Internet Using VPN](publish-data-over-the-internet-using-vpn.md).</span></span>  
  
-   <span data-ttu-id="2a519-107">Параметр веб-синхронизации для репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="2a519-107">The Web synchronization option for merge replication.</span></span> <span data-ttu-id="2a519-108">Дополнительные сведения см. в статье [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="2a519-108">For more information, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
 <span data-ttu-id="2a519-109">Репликации [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] всех типов могут реплицировать данные через виртуальную частную сеть, но для репликации слиянием необходимо предусмотреть веб-синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="2a519-109">All types of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication can replicate data over a VPN, but you should consider Web synchronization if you are using merge replication.</span></span>  
  
  
