---
title: Объект предупреждений (агент SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Alerts object
- SQLAgent:Alerts
ms.assetid: e5e37f74-ee88-46d0-ad8f-71fd1b1fa64a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9aa6fa871730af8cf129b3ea6b0aa4f1853d7e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657064"
---
# <a name="sql-server-agent-alerts-object"></a><span data-ttu-id="03974-102">Агент SQL Server, объект Alerts</span><span class="sxs-lookup"><span data-stu-id="03974-102">SQL Server Agent, Alerts Object</span></span>
  <span data-ttu-id="03974-103">Объект производительности **Alerts** агента SQL Server содержит счетчики производительности, которые предоставляют сведения о предупреждениях агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="03974-103">The SQL Server Agent **Alerts** performance object contains performance counters that report information about SQL Server Agent alerts.</span></span> <span data-ttu-id="03974-104">В следующей таблице перечислены счетчики этого объекта.</span><span class="sxs-lookup"><span data-stu-id="03974-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="03974-105">В таблице ниже перечислены счетчики **SQLAgent:Alerts** .</span><span class="sxs-lookup"><span data-stu-id="03974-105">The table below contains the **SQLAgent:Alerts** counters.</span></span>  
  
|<span data-ttu-id="03974-106">Имя</span><span class="sxs-lookup"><span data-stu-id="03974-106">Name</span></span>|<span data-ttu-id="03974-107">Описание</span><span class="sxs-lookup"><span data-stu-id="03974-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="03974-108">**Активированные предупреждения**</span><span class="sxs-lookup"><span data-stu-id="03974-108">**Activated alerts**</span></span>|<span data-ttu-id="03974-109">Этот счетчик показывает полное число предупреждений, которые активировал агент SQL Server со своего последнего перезапуска.</span><span class="sxs-lookup"><span data-stu-id="03974-109">This counter reports the total number of alerts that SQL Server Agent has activated since the last time that SQL Server Agent restarted.</span></span>|  
|<span data-ttu-id="03974-110">**Предупреждения, активированные за минуту**</span><span class="sxs-lookup"><span data-stu-id="03974-110">**Alerts activated/minute**</span></span>|<span data-ttu-id="03974-111">Этот счетчик показывает количество предупреждений, активированных агентом SQL Server за последнюю минуту.</span><span class="sxs-lookup"><span data-stu-id="03974-111">This counter reports the number of alerts that SQL Server Agent activated within the last minute.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="03974-112">Чтобы использовать этот объект агента SQL Server, необходимо быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="03974-112">To use this SQL Server Agent object, users must be a member of the **sysadmin** fixed server role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03974-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="03974-113">See Also</span></span>  
 <span data-ttu-id="03974-114">[Alerts](../../ssms/agent/alerts.md) </span><span class="sxs-lookup"><span data-stu-id="03974-114">[Alerts](../../ssms/agent/alerts.md) </span></span>  
 <span data-ttu-id="03974-115">[Использование объектов производительности](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="03974-115">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="03974-116">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="03974-116">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
