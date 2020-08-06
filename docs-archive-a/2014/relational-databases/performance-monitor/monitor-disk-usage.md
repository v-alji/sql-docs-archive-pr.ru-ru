---
title: Мониторинг использования диска | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database monitoring [SQL Server], disk usage
- disks [SQL Server]
- monitoring performance [SQL Server], disk usage
- server performance [SQL Server], disk usage
- monitoring [SQL Server], disk activity
- excess paging [SQL Server]
- tuning databases [SQL Server], disk usage
- I/O [SQL Server], monitoring
- disks [SQL Server], monitoring activity
- isolating disk activity [SQL Server]
- database performance [SQL Server], disk usage
- monitoring server performance [SQL Server], disk usage
ms.assetid: 1525449c-ea7d-4222-b294-1ba1fe99c9ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 51479b024864322d34dc3b0208e29e93d7454184
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739743"
---
# <a name="monitor-disk-usage"></a><span data-ttu-id="4d0d6-102">Наблюдение за использованием диска</span><span class="sxs-lookup"><span data-stu-id="4d0d6-102">Monitor Disk Usage</span></span>
  <span data-ttu-id="4d0d6-103">В Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] операции чтения и записи на диск выполняются с помощью вызовов ввода-вывода операционной системы Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses Microsoft Windows operating system input/output (I/O) calls to perform read and write operations on your disk.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4d0d6-104">определяет, когда и каким образом выполняется дисковый ввод-вывод, однако базовые операции ввода-вывода выполняет сама операционная система Windows.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-104">manages when and how disk I/O is performed, but the Windows operating system performs the underlying I/O operations.</span></span> <span data-ttu-id="4d0d6-105">Подсистема ввода-вывода включает системную шину, платы контроллера диска, диски, накопители на магнитной ленте, дисковод компакт-дисков и много других устройств ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-105">The I/O subsystem includes the system bus, disk controller cards, disks, tape drives, CD-ROM drive, and many other I/O devices.</span></span> <span data-ttu-id="4d0d6-106">Дисковые операции ввода-вывода часто являются узким местом в системе.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-106">Disk I/O is frequently the cause of bottlenecks in a system.</span></span>  
  
 <span data-ttu-id="4d0d6-107">Контроль активности диска состоит из двух областей, на которые необходимо обратить внимание:</span><span class="sxs-lookup"><span data-stu-id="4d0d6-107">Monitoring disk activity involves two areas of focus:</span></span>  
  
-   <span data-ttu-id="4d0d6-108">Контроль дисковых операций ввода-вывода и обнаружение излишней подкачки.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-108">Monitoring Disk I/O and Detecting Excess Paging</span></span>  
  
-   <span data-ttu-id="4d0d6-109">Выделение активности диска, создаваемой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d0d6-109">Isolating Disk Activity That [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Creates</span></span>  
  
 <span data-ttu-id="4d0d6-110">Дополнительные сведения см. в разделе [мониторинг использования диска](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4d0d6-110">For more information see, [Monitoring Disk Usage](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span></span>  
  
  
