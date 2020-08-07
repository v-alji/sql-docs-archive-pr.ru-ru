---
title: Локализация проблем производительности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- isolating performance problems [SQL Server]
- monitoring performance [SQL Server], isolating problems
- database monitoring [SQL Server], isolating problems
- tuning databases [SQL Server], isolating problems
- monitoring server performance [SQL Server], isolating problems
- database performance [SQL Server], isolating problems
- server performance [SQL Server], isolating problems
ms.assetid: 2eb425cb-9166-4027-ae08-c8fc2d236f44
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b42d780a8174ab57d00de72e8b00ef7af0abc17e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732609"
---
# <a name="isolate-performance-problems"></a><span data-ttu-id="cc26d-102">Локализация проблем производительности</span><span class="sxs-lookup"><span data-stu-id="cc26d-102">Isolate Performance Problems</span></span>
  <span data-ttu-id="cc26d-103">Зачастую для локализации проблем производительности базы данных более эффективным является совместное использование нескольких средств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или Microsoft Windows вместо одного.</span><span class="sxs-lookup"><span data-stu-id="cc26d-103">It is often more effective to use several [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Microsoft Windows tools together to isolate database performance problems than to use one tool at a time.</span></span> <span data-ttu-id="cc26d-104">Например, возможность графического плана выполнения, также называемая инструкцией Showplan, помогает быстро распознать взаимоблокировки в отдельном запросе.</span><span class="sxs-lookup"><span data-stu-id="cc26d-104">For example, the graphical Execution Plan feature, also called Showplan, helps you quickly recognize deadlocks in a single query.</span></span> <span data-ttu-id="cc26d-105">Однако при совместном использовании возможности контроля [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и Windows можно с еще большей легкостью распознать некоторые другие проблемы производительности.</span><span class="sxs-lookup"><span data-stu-id="cc26d-105">However, you can recognize some other performance problems more easily if you use the monitoring features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows together.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="cc26d-106">может быть использовано для контроля и диагностики проблем, связанных с языком Transact-SQL и приложениями.</span><span class="sxs-lookup"><span data-stu-id="cc26d-106">can be used to monitor and troubleshoot Transact-SQL and application-related problems.</span></span> <span data-ttu-id="cc26d-107">Системный монитор может быть использован для контроля проблем аппаратного обеспечения и других системных проблем.</span><span class="sxs-lookup"><span data-stu-id="cc26d-107">System Monitor can be used to monitor hardware and other system-related problems.</span></span>  
  
 <span data-ttu-id="cc26d-108">Для поиска и устранения проблем можно осуществлять контроль следующих областей:</span><span class="sxs-lookup"><span data-stu-id="cc26d-108">You can monitor the following areas to troubleshoot problems:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cc26d-109">или пакеты инструкций языка [!INCLUDE[tsql](../../includes/tsql-md.md)] , переданные пользовательскими приложениями;</span><span class="sxs-lookup"><span data-stu-id="cc26d-109">stored procedures or batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements submitted by user applications.</span></span>  
  
-   <span data-ttu-id="cc26d-110">деятельность пользователя, например блокировки и взаимоблокировки;</span><span class="sxs-lookup"><span data-stu-id="cc26d-110">User activity, such as blocking locks or deadlocks.</span></span>  
  
-   <span data-ttu-id="cc26d-111">работа аппаратного обеспечения, например использование диска.</span><span class="sxs-lookup"><span data-stu-id="cc26d-111">Hardware activity, such as disk usage.</span></span>  
  
 <span data-ttu-id="cc26d-112">Проблемы могут включать:</span><span class="sxs-lookup"><span data-stu-id="cc26d-112">Problems can include:</span></span>  
  
-   <span data-ttu-id="cc26d-113">ошибки разработки приложения, включающие неверно написанные инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="cc26d-113">Application development errors involving incorrectly written [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
-   <span data-ttu-id="cc26d-114">ошибки аппаратного обеспечения, например ошибки, связанные с диском или сетью;</span><span class="sxs-lookup"><span data-stu-id="cc26d-114">Hardware errors, such as disk- or network-related errors.</span></span>  
  
-   <span data-ttu-id="cc26d-115">чрезмерное блокирование из-за неверно спроектированной базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc26d-115">Excessive blocking due to an incorrectly designed database.</span></span>  
  
## <a name="tools-for-common-performance-problems"></a><span data-ttu-id="cc26d-116">Средства для устранения общих проблем производительности</span><span class="sxs-lookup"><span data-stu-id="cc26d-116">Tools for Common Performance Problems</span></span>  
 <span data-ttu-id="cc26d-117">Не менее важным является тщательный выбор проблем производительности, за которыми будет следить каждый инструмент.</span><span class="sxs-lookup"><span data-stu-id="cc26d-117">Equally important is careful selection of the performance problem that you want each tool to monitor or tune.</span></span> <span data-ttu-id="cc26d-118">Инструменты и программы зависят от типа проблемы производительности, которую необходимо устранить.</span><span class="sxs-lookup"><span data-stu-id="cc26d-118">The tool and the utility depend on the type of performance problem you want to resolve.</span></span>  
  
 <span data-ttu-id="cc26d-119">В следующих подразделах описывается набор средств контроля и настройки, а также проблемы, для устранения которых они используются.</span><span class="sxs-lookup"><span data-stu-id="cc26d-119">The following topics describe a variety of monitoring and tuning tools and the problems they uncover.</span></span>  
  
 [<span data-ttu-id="cc26d-120">Выявление узких мест</span><span class="sxs-lookup"><span data-stu-id="cc26d-120">Identify Bottlenecks</span></span>](identify-bottlenecks.md)  
  
 [<span data-ttu-id="cc26d-121">Отслеживание использования памяти</span><span class="sxs-lookup"><span data-stu-id="cc26d-121">Monitor Memory Usage</span></span>](../performance-monitor/monitor-memory-usage.md)  
  
  
