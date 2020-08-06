---
title: Параметр конфигурации сервера "affinity64 Input-Output mask" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- binding processors [SQL Server]
- affinity64 I/O mask option
ms.assetid: d304eae7-5116-40ee-a0fa-0a3c0bc20c01
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19616f5718254bde5601ea1beeec21412ad867de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665570"
---
# <a name="affinity64-input-output-mask-server-configuration-option"></a><span data-ttu-id="fe6fb-102">Параметр конфигурации сервера "affinity64 Input-Output mask"</span><span class="sxs-lookup"><span data-stu-id="fe6fb-102">affinity64 Input-Output mask Server Configuration Option</span></span>
  <span data-ttu-id="fe6fb-103">Параметр **affinity64 I/O mask** , подобно параметру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affinity I/O mask **, привязывает операции ввода-вывода сервера** к заданному подмножеству процессоров.</span><span class="sxs-lookup"><span data-stu-id="fe6fb-103">The **affinity64 I/O mask** binds [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/O to a specified subset of CPUs, similar to the **affinity I/O mask** option.</span></span> <span data-ttu-id="fe6fb-104">Параметр **affinity I/O mask** используется для привязки первых 32 процессоров, оставшиеся процессоры компьютера привязываются при помощи параметра **affinity64 I/O mask** .</span><span class="sxs-lookup"><span data-stu-id="fe6fb-104">Use **affinity I/O mask** to bind the first 32 processors, and use **affinity64 I/O mask** to bind the remaining processors on the computer.</span></span> <span data-ttu-id="fe6fb-105">После изменения параметра **affinity64 I/O mask**необходимо перезапустить экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe6fb-105">If you reconfigure the **affinity64 I/O mask**, you must restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fe6fb-106">Этот параметр доступен только в 64-разрядной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe6fb-106">This option is only visible on the 64-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6fb-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe6fb-107">See Also</span></span>  
 <span data-ttu-id="fe6fb-108">[Параметр конфигурации сервера "affinity Input-Output mask"](affinity-input-output-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="fe6fb-108">[affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="fe6fb-109">[Наблюдение за использованием ресурсов (системный монитор)](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="fe6fb-109">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="fe6fb-110">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe6fb-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="fe6fb-111">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fe6fb-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="fe6fb-112">RECONFIGURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fe6fb-112">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
