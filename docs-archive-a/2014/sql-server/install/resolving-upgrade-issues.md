---
title: Устранение проблем с обновлением | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Upgrade Advisor [SQL Server], reference
- component issue resolution [Upgrade Advisor]
- resolving upgrade issues
- upgrade blocks [Upgrade Advisor]
- detecting upgrade issues
- finding upgrade issues
- Upgrade Advisor [SQL Server], blocking issues
- configurations preventing upgrading [Upgrade Advisor]
- locating upgrade issues
- blocking issues [Upgrade Advisor]
- issues preventing upgrading [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, reference
- analyzing system [Upgrade Advisor], resolving issues
- settings preventing upgrading [Upgrade Advisor]
- upgrade issue reference [Upgrade Advisor]
- identifying upgrade issues
- fixing upgrade issues [Upgrade Advisor]
ms.assetid: 113eb435-8d36-4ed6-9790-b5e4c14809c8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c00b08d40bc8c17013e6af19b5d11b0b7ad78c4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668608"
---
# <a name="resolving-upgrade-issues"></a><span data-ttu-id="b24c3-102">Разрешение проблем при обновлении</span><span class="sxs-lookup"><span data-stu-id="b24c3-102">Resolving Upgrade Issues</span></span>
  <span data-ttu-id="b24c3-103">В подразделах данного раздела содержатся описания проблем, которые могут быть выявлены, а также проблем, которые не могут быть выявлены, но которые могут повлиять на обновление или работу после обновления.</span><span class="sxs-lookup"><span data-stu-id="b24c3-103">The topics in this section describe upgrade issues that can be detected as well as those that cannot be detected, but that might affect the upgrade or post-upgrade experience.</span></span> <span data-ttu-id="b24c3-104">Проблемы упорядочены по компонентам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b24c3-104">The issues are organized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b24c3-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b24c3-105">In This Section</span></span>  
  
-   [<span data-ttu-id="b24c3-106">Сведения о последних критических проблемах при обновлении</span><span class="sxs-lookup"><span data-stu-id="b24c3-106">Late-Breaking Upgrade Issues</span></span>](../../../2014/sql-server/install/late-breaking-upgrade-issues.md)  
  
-   [<span data-ttu-id="b24c3-107">Проблемы обновления ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="b24c3-107">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
-   [<span data-ttu-id="b24c3-108">Проблемы обновления полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="b24c3-108">Full-Text Search Upgrade Issues</span></span>](../../../2014/sql-server/install/full-text-search-upgrade-issues.md)  
  
-   [<span data-ttu-id="b24c3-109">Проблемы репликации при обновлении</span><span class="sxs-lookup"><span data-stu-id="b24c3-109">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
-   [<span data-ttu-id="b24c3-110">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="b24c3-110">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b24c3-111">Проблемы обновления агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="b24c3-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
## <a name="issues-that-prevent-upgrading"></a><span data-ttu-id="b24c3-112">Проблемы, препятствующие обновлению</span><span class="sxs-lookup"><span data-stu-id="b24c3-112">Issues That Prevent Upgrading</span></span>  
 <span data-ttu-id="b24c3-113">Некоторые настройки или параметры конфигурации предыдущей версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут стать препятствием для обновления до версии [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b24c3-113">A few configurations or settings in a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b24c3-114">Если они обнаружены при установке [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], то процесс обновления будет остановлен и программа установки потребует запуска советника по переходу и устранения всех критических препятствий.</span><span class="sxs-lookup"><span data-stu-id="b24c3-114">If Setup detects these issues when you install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Setup stops the upgrade process and requests that you run Upgrade Advisor and fix any blocking issues.</span></span>  
  
### [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
 <span data-ttu-id="b24c3-115">Если в отчете по обновлению компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] присутствуют перечисленные ниже задачи, то обновление до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] станет возможным только после того, как указанные действия будут выполнены.</span><span class="sxs-lookup"><span data-stu-id="b24c3-115">If the following tasks are listed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)] upgrade report, you must perform the required actions before you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span></span>  
  
-   [<span data-ttu-id="b24c3-116">Отсоедините базу данных с идентификатором 32767</span><span class="sxs-lookup"><span data-stu-id="b24c3-116">Detach database ID 32767</span></span>](../../../2014/sql-server/install/detach-database-id-32767.md)  
  
-   [<span data-ttu-id="b24c3-117">Переименование имен для входа, которые совпадают с именами предопределенной роли сервера</span><span class="sxs-lookup"><span data-stu-id="b24c3-117">Rename logins matching fixed server role names</span></span>](../../../2014/sql-server/install/rename-logins-matching-fixed-server-role-names.md)  
  
-   [<span data-ttu-id="b24c3-118">Переименуйте пользователя с именем sys</span><span class="sxs-lookup"><span data-stu-id="b24c3-118">Rename user sys</span></span>](../../../2014/sql-server/install/rename-user-sys.md)  
  
-   [<span data-ttu-id="b24c3-119">При помощи хранимой процедуры sp_rename переименуйте повторяющиеся имена индексов</span><span class="sxs-lookup"><span data-stu-id="b24c3-119">Use sp_rename to rename duplicate index name</span></span>](../../../2014/sql-server/install/use-sp-rename-to-rename-duplicate-index-name.md)  
  
## <a name="see-also"></a><span data-ttu-id="b24c3-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="b24c3-120">See Also</span></span>  
 [<span data-ttu-id="b24c3-121">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="b24c3-121">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
