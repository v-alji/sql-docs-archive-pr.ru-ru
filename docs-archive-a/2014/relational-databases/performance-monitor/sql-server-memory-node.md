---
title: Узел памяти (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 55b28ba9-b6d5-4ea9-8103-db8a72f42982
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5bbc3f581ea9ececeb7d55a614ef27c3c72de7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668260"
---
# <a name="sql-server-memory-node"></a><span data-ttu-id="45bc6-102">SQL Server, память узла</span><span class="sxs-lookup"><span data-stu-id="45bc6-102">SQL Server, Memory Node</span></span>
  <span data-ttu-id="45bc6-103">Объект **Память узла** в Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обеспечивает счетчики для сервера мониторинга использования памяти на узлах NUMA.</span><span class="sxs-lookup"><span data-stu-id="45bc6-103">The **Memory Node** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor server memory usage on NUMA nodes.</span></span>  
  
## <a name="memory-node-counters"></a><span data-ttu-id="45bc6-104">Счетчики памяти узла</span><span class="sxs-lookup"><span data-stu-id="45bc6-104">Memory Node Counters</span></span>  
 <span data-ttu-id="45bc6-105">В этой таблице описываются счетчики [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Память узла**.</span><span class="sxs-lookup"><span data-stu-id="45bc6-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Memory Node** counters.</span></span>  
  
|<span data-ttu-id="45bc6-106">SQL Server, счетчики диспетчера памяти</span><span class="sxs-lookup"><span data-stu-id="45bc6-106">SQL Server Memory Manager counters</span></span>|<span data-ttu-id="45bc6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="45bc6-107">Description</span></span>|  
|----------------------------------------|-----------------|  
|<span data-ttu-id="45bc6-108">**Память узла базы данных (КБ)**</span><span class="sxs-lookup"><span data-stu-id="45bc6-108">**Database Node Memory (KB)**</span></span>|<span data-ttu-id="45bc6-109">Указывает объем памяти, который используется в настоящий момент сервером на данном узле для страниц базы данных.</span><span class="sxs-lookup"><span data-stu-id="45bc6-109">Specifies the amount of memory the server is currently using on this node for database pages.</span></span>|  
|<span data-ttu-id="45bc6-110">**Свободная память узла (КБ)**</span><span class="sxs-lookup"><span data-stu-id="45bc6-110">**Free Node Memory (KB)**</span></span>|<span data-ttu-id="45bc6-111">Указывает объем памяти, который не используется сервером на данном узле.</span><span class="sxs-lookup"><span data-stu-id="45bc6-111">Specifies the amount of memory the server is not using on this node.</span></span>|  
|<span data-ttu-id="45bc6-112">**Внешняя память узла (КБ)**</span><span class="sxs-lookup"><span data-stu-id="45bc6-112">**Foreign Node Memory (KB)**</span></span>|<span data-ttu-id="45bc6-113">Указывает объем локальной памяти, отличной от NUMA, на данном узле.</span><span class="sxs-lookup"><span data-stu-id="45bc6-113">Specifies the amount of non NUMA-local memory on this node.</span></span>|  
|<span data-ttu-id="45bc6-114">**Заимствованная память узла (КБ)**</span><span class="sxs-lookup"><span data-stu-id="45bc6-114">**Stolen Memory Node (KB)**</span></span>|<span data-ttu-id="45bc6-115">Указывает объем памяти, который используется в настоящий момент сервером на данном узле не для страниц базы данных, а для других целей.</span><span class="sxs-lookup"><span data-stu-id="45bc6-115">Specifies the amount of memory the server is using on this node for purposes other than database pages.</span></span>|  
|<span data-ttu-id="45bc6-116">**Целевая память узла.**</span><span class="sxs-lookup"><span data-stu-id="45bc6-116">**Target Node Memory**</span></span>|<span data-ttu-id="45bc6-117">Указывает идеальный объем памяти для данного узла.</span><span class="sxs-lookup"><span data-stu-id="45bc6-117">Specifies the ideal amount of memory for this node.</span></span>|  
|<span data-ttu-id="45bc6-118">**Общая память узла**</span><span class="sxs-lookup"><span data-stu-id="45bc6-118">**Total Node Memory**</span></span>|<span data-ttu-id="45bc6-119">Указывает общий объем памяти, выделенной серверу на данном узле.</span><span class="sxs-lookup"><span data-stu-id="45bc6-119">Indicates the total amount of memory the server has committed on this node.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45bc6-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="45bc6-120">See Also</span></span>  
 <span data-ttu-id="45bc6-121">[Наблюдение за использованием ресурсов (системный монитор)](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="45bc6-121">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="45bc6-122">[SQL Server, объект Buffer Manager](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="45bc6-122">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="45bc6-123">sys.dm_os_performance_counters (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="45bc6-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
