---
title: Объект статистики выполнения (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:ExecStatistics
- ExecStatistics object
ms.assetid: 4f8557a8-345f-4622-a8a5-763a0388ad94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d1a50c97add4708a58b9edc45fd49982b97a51ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656349"
---
# <a name="sql-server-execstatistics-object"></a><span data-ttu-id="b0046-102">SQL Server, объект ExecStatistics</span><span class="sxs-lookup"><span data-stu-id="b0046-102">SQL Server, ExecStatistics Object</span></span>
  <span data-ttu-id="b0046-103">Объект **SQLServer:ExecStatistics** в Microsoft SQL Server предоставляет счетчики для контроля над различными выполнениями.</span><span class="sxs-lookup"><span data-stu-id="b0046-103">The **SQLServer:ExecStatistics** object in Microsoft SQL Server provides counters to monitor various executions.</span></span>  
  
 <span data-ttu-id="b0046-104">В этой таблице приведено описание счетчиков **Ведения статистики** SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b0046-104">This table describes the SQL Server **Exec Statistics** counters.</span></span>  
  
|<span data-ttu-id="b0046-105">Счетчики ведения статистики SQL Server</span><span class="sxs-lookup"><span data-stu-id="b0046-105">SQL Server Exec Statistics counters</span></span>|<span data-ttu-id="b0046-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b0046-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="b0046-107">**Распределенный запрос**</span><span class="sxs-lookup"><span data-stu-id="b0046-107">**Distributed Query**</span></span>|<span data-ttu-id="b0046-108">Статистика, относящаяся к выполнению распределенных запросов.</span><span class="sxs-lookup"><span data-stu-id="b0046-108">Statistics relevant to execution of distributed queries.</span></span>|  
|<span data-ttu-id="b0046-109">**Вызовы DTC**</span><span class="sxs-lookup"><span data-stu-id="b0046-109">**DTC calls**</span></span>|<span data-ttu-id="b0046-110">Статистика, относящаяся к выполнению вызовов DTC.</span><span class="sxs-lookup"><span data-stu-id="b0046-110">Statistics relevant to execution of DTC calls.</span></span>|  
|<span data-ttu-id="b0046-111">**Расширенные процедуры**</span><span class="sxs-lookup"><span data-stu-id="b0046-111">**Extended Procedures**</span></span>|<span data-ttu-id="b0046-112">Статистика, относящаяся к выполнению расширенных процедур.</span><span class="sxs-lookup"><span data-stu-id="b0046-112">Statistics relevant to execution of extended procedures.</span></span>|  
|<span data-ttu-id="b0046-113">**Вызовы OLEDB**</span><span class="sxs-lookup"><span data-stu-id="b0046-113">**OLEDB calls**</span></span>|<span data-ttu-id="b0046-114">Статистика, относящаяся к выполнению вызовов OLEDB.</span><span class="sxs-lookup"><span data-stu-id="b0046-114">Statistics relevant to execution of OLEDB calls.</span></span>|  
  
 <span data-ttu-id="b0046-115">Каждый из счетчиков объекта содержит следующие экземпляры.</span><span class="sxs-lookup"><span data-stu-id="b0046-115">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="b0046-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="b0046-116">Item</span></span>|<span data-ttu-id="b0046-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b0046-117">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="b0046-118">**Среднее время выполнения (сек)**</span><span class="sxs-lookup"><span data-stu-id="b0046-118">**Average execution time (ms)**</span></span>|<span data-ttu-id="b0046-119">Среднее время выполнения выбранного типа выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0046-119">Average execution time of the selected type of execution.</span></span>|  
|<span data-ttu-id="b0046-120">**Совокупное время выполнения (мс) в секунду**</span><span class="sxs-lookup"><span data-stu-id="b0046-120">**Cumulative execution time (ms) per second**</span></span>|<span data-ttu-id="b0046-121">Агрегированное время выполнения выбранного типа выполнения в секунду.</span><span class="sxs-lookup"><span data-stu-id="b0046-121">Aggregated execution time per second, of the selected type of execution.</span></span>|  
|<span data-ttu-id="b0046-122">**Текущие выполняемые задачи**</span><span class="sxs-lookup"><span data-stu-id="b0046-122">**Execs in progress**</span></span>|<span data-ttu-id="b0046-123">Количество совершающихся в текущий момент выполнений выбранного типа выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0046-123">Number of execs in progress of the selected type of execution.</span></span>|  
|<span data-ttu-id="b0046-124">**Выполнения, запущенные в секунду**</span><span class="sxs-lookup"><span data-stu-id="b0046-124">**Exec started per second**</span></span>|<span data-ttu-id="b0046-125">Количество запущенных в секунду выполнений выбранного типа выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0046-125">Number of exes started per second of the selected type of execution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0046-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0046-126">See Also</span></span>  
 [<span data-ttu-id="b0046-127">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="b0046-127">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
