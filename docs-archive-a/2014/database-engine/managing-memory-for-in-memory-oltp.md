---
title: Управление памятью для выполняющейся в памяти OLTP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d82f21fa-6be1-4723-a72e-f2526fafd1b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90f9b638697d59a0a573a9a31c0a5faade23e870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738687"
---
# <a name="managing-memory-for-in-memory-oltp"></a><span data-ttu-id="2e142-102">Управление памятью для компонента In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="2e142-102">Managing Memory for In-Memory OLTP</span></span>
  <span data-ttu-id="2e142-103">Оптимизированные для памяти таблицы требуют наличия достаточного объема памяти для хранения всех строк и индексов в памяти.</span><span class="sxs-lookup"><span data-stu-id="2e142-103">Memory-optimized tables require that sufficient memory exist to keep all of the rows and indexes in memory.</span></span> <span data-ttu-id="2e142-104">Поскольку память является ограниченным ресурсом, важно понимать принципы управления загруженностью памяти в системе.</span><span class="sxs-lookup"><span data-stu-id="2e142-104">Because memory is a finite resource, it is important that you understand and manage memory usage on your system.</span></span> <span data-ttu-id="2e142-105">Темы в этом разделе описывают распространенные сценарии использования и управления памятью.</span><span class="sxs-lookup"><span data-stu-id="2e142-105">The topics in this section cover common memory use and management scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e142-106">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="2e142-106">In this section</span></span>  
  
|<span data-ttu-id="2e142-107">Section</span><span class="sxs-lookup"><span data-stu-id="2e142-107">Section</span></span>|<span data-ttu-id="2e142-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2e142-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e142-109">Оценка требований к объему памяти для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="2e142-109">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)|<span data-ttu-id="2e142-110">Оценка потребностей в памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="2e142-110">Estimate a table's memory needs.</span></span>|  
|[<span data-ttu-id="2e142-111">Привязка базы данных с таблицами, оптимизированными для памяти, к пулу ресурсов</span><span class="sxs-lookup"><span data-stu-id="2e142-111">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)|<span data-ttu-id="2e142-112">Пошаговое руководство для связывания базы данных с пулом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2e142-112">Step by step walkthrough to bind a database with a resource pool.</span></span>|  
|[<span data-ttu-id="2e142-113">Мониторинг и устранение неполадок с использованием памяти</span><span class="sxs-lookup"><span data-stu-id="2e142-113">Monitor and Troubleshoot Memory Usage</span></span>](../relational-databases/in-memory-oltp/monitor-and-troubleshoot-memory-usage.md)|<span data-ttu-id="2e142-114">Средства, с помощью которых можно контролировать использование памяти.</span><span class="sxs-lookup"><span data-stu-id="2e142-114">Tools you can use to monitor your memory usage.</span></span> <span data-ttu-id="2e142-115">Также описывается устранение неполадок при слишком сильной загрузке памяти.</span><span class="sxs-lookup"><span data-stu-id="2e142-115">Also covers troubleshooting if memory usage gets too high.</span></span>|  
|[<span data-ttu-id="2e142-116">Устранение проблем нехватки памяти</span><span class="sxs-lookup"><span data-stu-id="2e142-116">Resolve Out Of Memory Issues</span></span>](../relational-databases/in-memory-oltp/resolve-out-of-memory-issues.md)|<span data-ttu-id="2e142-117">Шаги для устранения ситуаций, возникающих из-за нехватки памяти (OOM - Out of Memory).</span><span class="sxs-lookup"><span data-stu-id="2e142-117">Steps to recover from an OOM (Out of Memory) situation.</span></span>|  
|[<span data-ttu-id="2e142-118">восстановить базу данных и привязать ее к пулу ресурсов</span><span class="sxs-lookup"><span data-stu-id="2e142-118">Restore a Database and Bind it to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md)|<span data-ttu-id="2e142-119">Шаги для восстановления базы данных [!INCLUDE[hek_2](../includes/hek-2-md.md)] и ее привязки к именованному пулу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2e142-119">Steps to restore an [!INCLUDE[hek_2](../includes/hek-2-md.md)] database and bind it to a named resource pool.</span></span>|  
|[<span data-ttu-id="2e142-120">Сборка мусора модулем In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="2e142-120">In-Memory OLTP Garbage Collection</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-garbage-collection.md)|<span data-ttu-id="2e142-121">Общие сведения о сборке мусора для удаленных строк.</span><span class="sxs-lookup"><span data-stu-id="2e142-121">Understand how garbage collection operates on deleted rows.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e142-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e142-122">See Also</span></span>  
 [<span data-ttu-id="2e142-123">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="2e142-123">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
