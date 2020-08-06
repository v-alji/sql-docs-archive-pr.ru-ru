---
title: Параметр конфигурации сервера "blocked process threshold" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- thresholds [SQL Server]
- blocked process threshold option
ms.assetid: 3d46d143-bc6a-4220-8b55-6baa37547c25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9d5b61aaf23a8e74cb11afbf4e8bdb958fde6abe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736782"
---
# <a name="blocked-process-threshold-server-configuration-option"></a><span data-ttu-id="cfd67-102">Параметр конфигурации сервера «blocked process threshold»</span><span class="sxs-lookup"><span data-stu-id="cfd67-102">blocked process threshold Server Configuration Option</span></span>
  <span data-ttu-id="cfd67-103">Параметр **blocked process threshold** определяет пороговое значение (в секундах), в течение которого блокированный процесс порождает сообщения.</span><span class="sxs-lookup"><span data-stu-id="cfd67-103">Use the **blocked process threshold** option to specify the threshold, in seconds, at which blocked process reports are generated.</span></span> <span data-ttu-id="cfd67-104">Пороговое значение может быть задано в диапазоне от 0 до 86 400.</span><span class="sxs-lookup"><span data-stu-id="cfd67-104">The threshold can be set from 0 to 86,400.</span></span> <span data-ttu-id="cfd67-105">По умолчанию отчеты о заблокированных процессах не создаются.</span><span class="sxs-lookup"><span data-stu-id="cfd67-105">By default, no blocked process reports are produced.</span></span> <span data-ttu-id="cfd67-106">Это событие не формируется для системных задач и для задач, которые ожидают ресурсы, не производящие отслеживаемых взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="cfd67-106">This event is not generated for system tasks or for tasks that are waiting on resources that do not generate detectable deadlocks.</span></span>  
  
 <span data-ttu-id="cfd67-107">При формировании данного события можно выдать [предупреждение](../../ssms/agent/alerts.md) .</span><span class="sxs-lookup"><span data-stu-id="cfd67-107">You can define an [alert](../../ssms/agent/alerts.md) to be executed when this event is generated.</span></span> <span data-ttu-id="cfd67-108">Например, можно выдать администратору на пейджер сообщение о необходимости разобраться с блокировкой.</span><span class="sxs-lookup"><span data-stu-id="cfd67-108">So for example, you can choose to page the administrator to take appropriate action to handle the blocking situation.</span></span>  
  
 <span data-ttu-id="cfd67-109">Мониторинг порога блокировки процесса использует фоновый поток отслеживания взаимоблокировок, который просматривает список задач, ожидающих выполнения в течение времени, превышающего указанное в настройках пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="cfd67-109">Blocked process threshold uses the deadlock monitor background thread to walk through the list of tasks waiting for a time greater than or multiples of the configured threshold.</span></span> <span data-ttu-id="cfd67-110">Это событие формируется один раз в течение отчетного интервала для каждой из заблокированных задач.</span><span class="sxs-lookup"><span data-stu-id="cfd67-110">The event is generated once per reporting interval for each of the blocked tasks.</span></span>  
  
 <span data-ttu-id="cfd67-111">Отчет о блокированном процессе выполняется по принципу оптимальных затрат.</span><span class="sxs-lookup"><span data-stu-id="cfd67-111">The blocked process report is done on a best effort basis.</span></span> <span data-ttu-id="cfd67-112">Нет никакой гарантии, что он будет выдаваться в реальном времени или хотя бы достаточно быстро.</span><span class="sxs-lookup"><span data-stu-id="cfd67-112">There is no guarantee of any real-time or even close to real-time reporting.</span></span>  
  
 <span data-ttu-id="cfd67-113">Новые настройки вступают в силу сразу же, без остановки или перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="cfd67-113">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cfd67-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="cfd67-114">Examples</span></span>  
 <span data-ttu-id="cfd67-115">В следующем примере параметр `blocked process threshold` устанавливается в значение `20` секунд, выдавая отчет о заблокированных процессах.</span><span class="sxs-lookup"><span data-stu-id="cfd67-115">The following example sets the `blocked process threshold` to `20` seconds, generating a blocked process report for each task that is blocked.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 20 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfd67-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfd67-116">See Also</span></span>  
 <span data-ttu-id="cfd67-117">[Хранимая процедура sp_trace_setevent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfd67-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="cfd67-118">Класс событий Blocked Process Report</span><span class="sxs-lookup"><span data-stu-id="cfd67-118">Blocked Process Report Event Class</span></span>](../../relational-databases/event-classes/blocked-process-report-event-class.md)  
  
  
