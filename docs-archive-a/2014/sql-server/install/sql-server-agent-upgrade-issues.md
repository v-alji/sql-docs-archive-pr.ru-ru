---
title: Проблемы обновления агент SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server Agent
- SQL Server Agent, upgrades
ms.assetid: 77e303ff-febd-4103-ae5d-6e5b85bc8009
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ac234a757510af5ebfac261ea6d3e7e57d2f426f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732289"
---
# <a name="sql-server-agent-upgrade-issues"></a><span data-ttu-id="decbc-102">Проблемы обновления агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="decbc-102">SQL Server Agent Upgrade Issues</span></span>
  <span data-ttu-id="decbc-103">В следующих разделах описываются проблемы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которые могут повлиять на обновление.</span><span class="sxs-lookup"><span data-stu-id="decbc-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent issues that might affect an upgrade.</span></span> <span data-ttu-id="decbc-104">В разделах описываются действия, которые могут уменьшить последствия этих изменений в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="decbc-104">The topics describe actions that you can take to help reduce the effect of these changes on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="decbc-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="decbc-105">In This Section</span></span>  
  
-   [<span data-ttu-id="decbc-106">Планы обслуживания базы данных заменены</span><span class="sxs-lookup"><span data-stu-id="decbc-106">Database maintenance plans superseded</span></span>](../../../2014/sql-server/install/database-maintenance-plans-superseded.md)  
  
-   [<span data-ttu-id="decbc-107">Только пользователи с правами sysadmin могут записывать файлы журнала шагов заданий в файловую систему</span><span class="sxs-lookup"><span data-stu-id="decbc-107">Only sysadmin users can write job step log files to the file system</span></span>](../../../2014/sql-server/install/only-sysadmin-users-can-write-job-step-log-files-to-the-file-system.md)  
  
-   [<span data-ttu-id="decbc-108">Замена вызовов расширенной хранимой процедуры xp_sqlagent_proxy_account на вызовы новых хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="decbc-108">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>](../../../2014/sql-server/install/replace-xp-sqlagent-proxy-account-extended-sp-with-new-stored-procedures.md)  
  
-   [<span data-ttu-id="decbc-109">Категория заданий доставки журналов агента SQL Server приводит к ошибке обновления</span><span class="sxs-lookup"><span data-stu-id="decbc-109">SQL Server Agent log shipping job category causes upgrade to fail</span></span>](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md)  
  
-   [<span data-ttu-id="decbc-110">Служба агента SQL Server не может использовать проверку подлинности SQL Server</span><span class="sxs-lookup"><span data-stu-id="decbc-110">SQL Server Agent Service cannot use SQL Server Authentication</span></span>](../../../2014/sql-server/install/sql-server-agent-service-cannot-use-sql-server-authentication.md)  
  
-   [<span data-ttu-id="decbc-111">Обновите синтаксис токенов в шагах заданий агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="decbc-111">Update token syntax in SQL Server Agent job steps</span></span>](../../../2014/sql-server/install/update-token-syntax-in-sql-server-agent-job-steps.md)  
  
-   [<span data-ttu-id="decbc-112">Обновите все целевые серверы перед обновлением главного сервера</span><span class="sxs-lookup"><span data-stu-id="decbc-112">Upgrade all target servers before upgrading the master server</span></span>](../../../2014/sql-server/install/upgrade-all-target-servers-before-upgrading-the-master-server.md)  
  
-   [<span data-ttu-id="decbc-113">При обновлении пользовательская учетная запись-посредник агента SQL Server изменится на временную учетную запись-посредник UpgradedProxyAccount</span><span class="sxs-lookup"><span data-stu-id="decbc-113">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md)  
  
## <a name="see-also"></a><span data-ttu-id="decbc-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="decbc-114">See Also</span></span>  
 <span data-ttu-id="decbc-115">[Советник по переходу SQL Server 2014 &#91;New&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="decbc-115">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="decbc-116">Решение проблем при обновлении</span><span class="sxs-lookup"><span data-stu-id="decbc-116">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
