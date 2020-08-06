---
title: Обновите все целевые серверы перед обновлением главного сервера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TSX [SQL Server Agent]
- target servers [SQL Server Agent]
- MSX [SQL Server Agent]
- master servers [SQL Server Agent]
ms.assetid: 2c231793-3878-4a5e-a425-1fa0d787ba84
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 031fedc4af4b058704cef1da8df846397b235305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655532"
---
# <a name="upgrade-all-target-servers-before-upgrading-the-master-server"></a><span data-ttu-id="bd419-102">Обновите все целевые серверы перед обновлением главного сервера</span><span class="sxs-lookup"><span data-stu-id="bd419-102">Upgrade all target servers before upgrading the master server</span></span>
  <span data-ttu-id="bd419-103">Перед обновлением главного сервера обновите все компьютеры, на которых работают серверы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , настроенные в качестве целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="bd419-103">Before you upgrade the master server, upgrade all computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are configured as target servers.</span></span>  
  
## <a name="component"></a><span data-ttu-id="bd419-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="bd419-104">Component</span></span>  
 <span data-ttu-id="bd419-105">Агент[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd419-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="bd419-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bd419-106">Description</span></span>  
 <span data-ttu-id="bd419-107">Чтобы автоматизировать администрирование многосерверной среды, необходимо иметь по меньшей мере один главный сервер и один целевой.</span><span class="sxs-lookup"><span data-stu-id="bd419-107">To automate administration in multiserver environments, you must have at least one master server and at least one target server.</span></span> <span data-ttu-id="bd419-108">Главный сервер распределяет задания целевым серверам и получает от них события.</span><span class="sxs-lookup"><span data-stu-id="bd419-108">A master server distributes jobs to, and receives events from, target servers.</span></span> <span data-ttu-id="bd419-109">На главном сервере также хранится центральная копия определений заданий, выполняющихся на целевых серверах.</span><span class="sxs-lookup"><span data-stu-id="bd419-109">A master server also stores the central copy of job definitions for jobs that are run on target servers.</span></span>  
  
 <span data-ttu-id="bd419-110">Если текущий сервер настроен как главный, необходимо сначала обновить все целевые серверы, а затем главный сервер.</span><span class="sxs-lookup"><span data-stu-id="bd419-110">If the current server is configured as a master server, upgrade all of your target servers first before you upgrade the master server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="bd419-111">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="bd419-111">Corrective Action</span></span>  
 <span data-ttu-id="bd419-112">Если нельзя обновить все целевые серверы до обновления главного сервера, то следует исключить все целевые серверы и после обновления прикрепить их повторно.</span><span class="sxs-lookup"><span data-stu-id="bd419-112">If you cannot upgrade all target servers before you upgrade the master server, you must defect all target servers and reenlist them after you upgrade.</span></span>  
  
 <span data-ttu-id="bd419-113">Дополнительные сведения об определении выполняемых задач см. в разделах «Автоматизация администрирования в масштабах предприятия», «Как отключить целевой сервер от главного сервера» и «Как прикрепить целевой сервер к главному серверу» в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd419-113">For more information, see the topics "Automating Administration across an Enterprise," "How to: Defect a Target Server from a Master Server," and "How to: Enlist a Target Server to a Master" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd419-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd419-114">See Also</span></span>  
 <span data-ttu-id="bd419-115">[Проблемы обновления агент SQL Server](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="bd419-115">[SQL Server Agent Upgrade Issues](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="bd419-116">Проблемы обновления агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd419-116">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
