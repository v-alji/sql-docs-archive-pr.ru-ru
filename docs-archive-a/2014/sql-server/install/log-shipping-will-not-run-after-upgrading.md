---
title: Доставка журналов не будет выполняться после обновления | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server]
ms.assetid: 6727cb7d-ac01-4972-a730-dbb7cdc29705
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2af60743cb2cbf9bf455397fe052c4e81f5a06d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668621"
---
# <a name="log-shipping-will-not-run-after-upgrading"></a><span data-ttu-id="b9a00-102">Доставка журналов перестанет работать после обновления</span><span class="sxs-lookup"><span data-stu-id="b9a00-102">Log shipping will not run after upgrading</span></span>
  <span data-ttu-id="b9a00-103">Помощник по обновлению обнаружил, что используется доставка журналов.</span><span class="sxs-lookup"><span data-stu-id="b9a00-103">Upgrade Advisor has detected that you are using log shipping.</span></span> <span data-ttu-id="b9a00-104">Доставка журналов [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] несовместима с доставкой журналов [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] и не может быть обновлена напрямую.</span><span class="sxs-lookup"><span data-stu-id="b9a00-104">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] log shipping is incompatible with log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and cannot be upgraded directly.</span></span> <span data-ttu-id="b9a00-105">После обновления до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]настройте повторно доставку журналов с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="b9a00-105">After upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], reconfigure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a00-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9a00-106">See Also</span></span>  
 <span data-ttu-id="b9a00-107">[Категория заданий доставки журналов агент SQL Server приводит к сбою обновления](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="b9a00-107">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 <span data-ttu-id="b9a00-108">[При обновлении агент SQL Server учетная запись-посредник пользователя изменится на временную UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="b9a00-108">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 <span data-ttu-id="b9a00-109">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b9a00-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b9a00-110">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="b9a00-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
