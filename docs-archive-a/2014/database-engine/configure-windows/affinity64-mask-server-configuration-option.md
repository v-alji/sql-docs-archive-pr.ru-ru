---
title: Параметр конфигурации сервера "affinity64 mask" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- affinity64 mask option
- binding processors [SQL Server]
ms.assetid: 75ed08c7-f85c-4e15-9ee1-e7bc545d3293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2ea6d2e364feaa67d91de0055617aac9dc285ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665568"
---
# <a name="affinity64-mask-server-configuration-option"></a><span data-ttu-id="1c6cc-102">Параметр конфигурации сервера «affinity64 mask»</span><span class="sxs-lookup"><span data-stu-id="1c6cc-102">affinity64 mask Server Configuration Option</span></span>
  <span data-ttu-id="1c6cc-103">Параметр affinity64 mask привязывает процессоры к конкретным потокам, аналогично параметру affinity mask.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-103">The affinity64 mask binds processors to specific threads, similar to the affinity mask option.</span></span> <span data-ttu-id="1c6cc-104">Используйте параметр affinity mask для привязки первых 32-разрядных процессоров и параметр affinity64 mask для привязки оставшихся процессоров на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-104">Use affinity mask to bind the first 32 processors, and use affinity64 mask to bind the remaining processors on the computer.</span></span> <span data-ttu-id="1c6cc-105">Этот параметр доступен только в 64-разрядной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c6cc-105">This option is only visible on the 64-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="1c6cc-106">Используйте вместо него инструкцию [ALTER SERVER CONFIGURATION (Transact-SQL)](/sql/t-sql/statements/alter-server-configuration-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1c6cc-106">Use [ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-configuration-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6cc-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="1c6cc-107">See Also</span></span>  
 <span data-ttu-id="1c6cc-108">[Параметр конфигурации сервера «affinity mask»](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="1c6cc-108">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="1c6cc-109">[Наблюдение за использованием ресурсов (системный монитор)](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1c6cc-109">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="1c6cc-110">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c6cc-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="1c6cc-111">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c6cc-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="1c6cc-112">RECONFIGURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1c6cc-112">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
