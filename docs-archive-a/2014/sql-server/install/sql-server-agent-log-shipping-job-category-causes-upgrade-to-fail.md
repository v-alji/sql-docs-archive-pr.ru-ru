---
title: Категория заданий доставки журналов агент SQL Server приводит к сбою обновления | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
- job categories [SQL Server Agent]
ms.assetid: ef05ce53-c6ce-42ec-9df8-46c951626424
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2f5947e8fc8d459388fe35d86c75666e25b5d907
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751676"
---
# <a name="sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail"></a><span data-ttu-id="0e852-102">Категория заданий доставки журналов агента SQL Server приводит к ошибке обновления</span><span class="sxs-lookup"><span data-stu-id="0e852-102">SQL Server Agent log shipping job category causes upgrade to fail</span></span>
  <span data-ttu-id="0e852-103">Процесс обновления закончится ошибкой, если категория задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с именем «Доставка журналов» существует.</span><span class="sxs-lookup"><span data-stu-id="0e852-103">The upgrade process will fail if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category named Log Shipping exists.</span></span>  
  
## <a name="component"></a><span data-ttu-id="0e852-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="0e852-104">Component</span></span>  
 <span data-ttu-id="0e852-105">Агент[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e852-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="0e852-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0e852-106">Description</span></span>  
 <span data-ttu-id="0e852-107">Существует системная категория заданий «Доставка журналов».</span><span class="sxs-lookup"><span data-stu-id="0e852-107">There is a system job category named Log Shipping.</span></span> <span data-ttu-id="0e852-108">Если в обновляемой установке уже содержится созданная пользователем категория задания с именем «Доставка журналов», необходимо переименовать категорию задания перед обновлением; в противном случае процесс обновления завершится неуспешно.</span><span class="sxs-lookup"><span data-stu-id="0e852-108">If an installation that is being upgraded already contains a user-created job category named Log Shipping, you must rename the job category before you upgrade; otherwise, the upgrade process will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e852-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e852-109">See Also</span></span>  
 <span data-ttu-id="0e852-110">[Доставка журналов не будет выполняться после обновления](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span><span class="sxs-lookup"><span data-stu-id="0e852-110">[Log shipping will not run after upgrading](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span></span>  
 <span data-ttu-id="0e852-111">[При обновлении агент SQL Server учетная запись-посредник пользователя изменится на временную UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="0e852-111">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 [<span data-ttu-id="0e852-112">Проблемы обновления агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="0e852-112">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
