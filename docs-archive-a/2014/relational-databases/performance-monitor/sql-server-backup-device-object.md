---
title: SQL Server, объект Backup Device | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Backup Device
- Backup Device object
ms.assetid: 52e7febf-d5e0-4674-945b-aacc40a9ad6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e3126310ad31dcc153fc79508dbfaccf86f5da78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658216"
---
# <a name="sql-server-backup-device-object"></a><span data-ttu-id="9c15e-102">SQL Server, объект Backup Device</span><span class="sxs-lookup"><span data-stu-id="9c15e-102">SQL Server, Backup Device Object</span></span>
  <span data-ttu-id="9c15e-103">**Устройство резервного копирования** предоставляет счетчики для контроля над устройствами резервного копирования и операциями восстановления Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c15e-103">The **Backup Device** object provides counters to monitor Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices used for backup and restore operations.</span></span> <span data-ttu-id="9c15e-104">Контролировать устройства резервного копирования нужно, если необходимо определить пропускную способность, состояние или производительность операций резервного копирования и восстановления для каждого из устройств.</span><span class="sxs-lookup"><span data-stu-id="9c15e-104">Monitor backup devices when you want to determine the throughput or the progress and performance of your backup and restore operations on a per device basis.</span></span> <span data-ttu-id="9c15e-105">Чтобы контролировать пропускную способность операции резервного копирования или восстановить всю **базу данных**, используйте счетчик **Пропускная способность резервного копирования/восстановления в байтах/с** объекта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c15e-105">To monitor the throughput of the entire database backup or restore operation, use the **Backup/Restore Throughput/sec** counter of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Databases** object.</span></span> <span data-ttu-id="9c15e-106">Дополнительные сведения см. в статье [SQL Server, Databases Object](sql-server-databases-object.md).</span><span class="sxs-lookup"><span data-stu-id="9c15e-106">For more information, see [SQL Server, Databases Object](sql-server-databases-object.md).</span></span>  
  
 <span data-ttu-id="9c15e-107">В следующей таблице описан счетчик [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Устройство резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="9c15e-107">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Backup Device** counter.</span></span>  
  
|<span data-ttu-id="9c15e-108">Счетчики устройств резервного копирования SQL Server</span><span class="sxs-lookup"><span data-stu-id="9c15e-108">SQL Server Backup Device counters</span></span>|<span data-ttu-id="9c15e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9c15e-109">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="9c15e-110">**Пропускная способность устройства, байт/с**</span><span class="sxs-lookup"><span data-stu-id="9c15e-110">**Device Throughput Bytes/sec**</span></span>|<span data-ttu-id="9c15e-111">Пропускная способность операций чтения и записи (в байтах на секунду) для устройства резервного копирования при создании резервной копии базы данных или ее восстановлении.</span><span class="sxs-lookup"><span data-stu-id="9c15e-111">Throughput of read and write operations (in bytes per second) for a backup device used when backing up or restoring databases.</span></span> <span data-ttu-id="9c15e-112">Этот счетчик существует, только если выполняется операция резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="9c15e-112">This counter exists only while the backup or restore operation is executing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c15e-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c15e-113">See Also</span></span>  
 <span data-ttu-id="9c15e-114">[Устройства резервного копирования (SQL Server)](../backup-restore/backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c15e-114">[Backup Devices &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="9c15e-115">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="9c15e-115">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
