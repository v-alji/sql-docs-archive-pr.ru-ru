---
title: Определение базовых показателей производительности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], baselines
- monitoring performance [SQL Server], baselines
- tuning databases [SQL Server], baselines
- server performance [SQL Server], baselines
- performance [SQL Server], baselines
- baseline performance [SQL Server]
- measurements for baseline statistics [SQL Server]
- monitoring server performance [SQL Server], establishing baseline
- database monitoring [SQL Server], baselines
ms.assetid: dc5aa8d6-2507-448f-ad86-4196443915fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0cb85ae8ad370b816c6240b58aabd247c7593c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729381"
---
# <a name="establish-a-performance-baseline"></a><span data-ttu-id="80f30-102">Формирование базовых показателей производительности</span><span class="sxs-lookup"><span data-stu-id="80f30-102">Establish a Performance Baseline</span></span>
  <span data-ttu-id="80f30-103">Чтобы определить, оптимально ли функционирует система [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо измерять производительность через определенные промежутки времени, даже если не возникает никаких проблем, для установления базового уровня производительности.</span><span class="sxs-lookup"><span data-stu-id="80f30-103">To determine whether your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system is performing optimally, take performance measurements at regular intervals over time, even when no problems occur, to establish a server performance baseline.</span></span> <span data-ttu-id="80f30-104">Сравните каждый новый набор измерений с полученными ранее.</span><span class="sxs-lookup"><span data-stu-id="80f30-104">Compare each new set of measurements with those taken earlier.</span></span>  
  
 <span data-ttu-id="80f30-105">Ниже представлены зоны, влияющие на производительность [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="80f30-105">The following areas affect the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="80f30-106">ресурсы системы (оборудование);</span><span class="sxs-lookup"><span data-stu-id="80f30-106">System resources (hardware)</span></span>  
  
-   <span data-ttu-id="80f30-107">Сетевая архитектура</span><span class="sxs-lookup"><span data-stu-id="80f30-107">Network architecture</span></span>  
  
-   <span data-ttu-id="80f30-108">операционная система;</span><span class="sxs-lookup"><span data-stu-id="80f30-108">The operating system</span></span>  
  
-   <span data-ttu-id="80f30-109">приложения базы данных;</span><span class="sxs-lookup"><span data-stu-id="80f30-109">Database applications</span></span>  
  
-   <span data-ttu-id="80f30-110">Клиентские приложения</span><span class="sxs-lookup"><span data-stu-id="80f30-110">Client applications</span></span>  
  
 <span data-ttu-id="80f30-111">Как минимум используйте измерения базового уровня для определения следующих значений:</span><span class="sxs-lookup"><span data-stu-id="80f30-111">At a minimum, use baseline measurements to determine:</span></span>  
  
-   <span data-ttu-id="80f30-112">пиковые и непиковые часы операции;</span><span class="sxs-lookup"><span data-stu-id="80f30-112">Peak and off-peak hours of operation.</span></span>  
  
-   <span data-ttu-id="80f30-113">время ответа на подачу запроса или команды пакета;</span><span class="sxs-lookup"><span data-stu-id="80f30-113">Production-query or batch-command response times.</span></span>  
  
-   <span data-ttu-id="80f30-114">время завершения резервного копирования и восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="80f30-114">Database backup and restore completion times.</span></span>  
  
 <span data-ttu-id="80f30-115">После установления базового уровня производительности сервера сравните статистику базовых строк с текущей производительностью сервера.</span><span class="sxs-lookup"><span data-stu-id="80f30-115">After you establish a server performance baseline, compare the baseline statistics to current server performance.</span></span> <span data-ttu-id="80f30-116">Числа намного выше и намного ниже базового уровня являются кандидатами для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="80f30-116">Numbers far above or far below your baseline are candidates for further investigation.</span></span> <span data-ttu-id="80f30-117">Они могут указывать зоны, которым необходимы настройка или повторная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="80f30-117">They may indicate areas in need of tuning or reconfiguration.</span></span> <span data-ttu-id="80f30-118">Например, если количество времени для выполнения набора запросов увеличивается, изучите запросы, чтобы определить, могут ли они быть переписаны и есть ли необходимость добавлять статистику столбца или новые индексы.</span><span class="sxs-lookup"><span data-stu-id="80f30-118">For example, if the amount of time to execute a set of queries increases, examine the queries to determine if they can be rewritten, or if column statistics or new indexes must be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f30-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="80f30-119">See Also</span></span>  
 [<span data-ttu-id="80f30-120">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="80f30-120">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
