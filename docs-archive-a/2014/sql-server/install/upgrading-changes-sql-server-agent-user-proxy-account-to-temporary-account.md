---
title: При обновлении агент SQL Server учетная запись-посредник пользователя изменится на временную UpgradedProxyAccount | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
ms.assetid: cd2d08c3-4e56-4034-8b68-0c78df8b5471
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2bca80580a50f2acebed1b6fbea2dec1f6458dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654738"
---
# <a name="upgrading-will-change-the-sql-server-agent-user-proxy-account-to-the-temporary-upgradedproxyaccount"></a><span data-ttu-id="c1e48-102">При обновлении пользовательская учетная запись-посредник агента SQL Server изменится на временную учетную запись-посредник UpgradedProxyAccount</span><span class="sxs-lookup"><span data-stu-id="c1e48-102">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>
  <span data-ttu-id="c1e48-103">Планы обслуживания базы данных с доставкой журналов не будут включены после обновления.</span><span class="sxs-lookup"><span data-stu-id="c1e48-103">Database maintenance plans that have log shipping enabled will not be enabled after upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c1e48-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="c1e48-104">Component</span></span>  
 <span data-ttu-id="c1e48-105">Агент[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1e48-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="c1e48-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c1e48-106">Description</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c1e48-107">предоставляет новый набор функций доставки журналов, которые несовместимы напрямую с планами обслуживания баз данных.</span><span class="sxs-lookup"><span data-stu-id="c1e48-107">provides a new set of log shipping functions that are not directly compatible with database maintenance plans.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c1e48-108">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="c1e48-108">Corrective Action</span></span>  
 <span data-ttu-id="c1e48-109">Пользователи [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], которые используют планы обслуживания баз данных, содержащие функции доставки журналов, должны настроить доставку журналов с использованием этих новых функций.</span><span class="sxs-lookup"><span data-stu-id="c1e48-109">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] users that have database maintenance plans that contain log shipping functions should configure log shipping by using the new functions.</span></span> <span data-ttu-id="c1e48-110">Дополнительные сведения можно получить, осуществив поиск слов «доставка журналов» в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1e48-110">For more information, search on "log shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e48-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="c1e48-111">See Also</span></span>  
 <span data-ttu-id="c1e48-112">[Категория заданий доставки журналов агент SQL Server приводит к сбою обновления](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="c1e48-112">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 [<span data-ttu-id="c1e48-113">Доставка журналов перестанет работать после обновления</span><span class="sxs-lookup"><span data-stu-id="c1e48-113">Log shipping will not run after upgrading</span></span>](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md)  
  
  
