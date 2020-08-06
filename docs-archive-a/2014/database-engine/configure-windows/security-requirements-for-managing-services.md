---
title: Требования безопасности к службам управления | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent service, security
- services [SQL Server], security
- SQL Server services, security
- WMI Providers [SQL Server]
- server configuration [SQL Server]
- security [SQL Server], services
- services [SQL Server], WMI
ms.assetid: 1874a317-ddb2-425d-98d9-b53e1be6fc6a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 46a777858c01bf3057093d34b29b9a2093668e97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738750"
---
# <a name="security-requirements-for-managing-services"></a><span data-ttu-id="b344c-102">Требования безопасности к службам управления</span><span class="sxs-lookup"><span data-stu-id="b344c-102">Security Requirements for Managing Services</span></span>
  <span data-ttu-id="b344c-103">Чтобы управлять [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и службами агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], используйте диспетчер конфигурации SQL Server или среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b344c-103">To manage the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Services, use either SQL Server Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b344c-104">Управление службами на кластеризованных серверах выполняется с помощью администратора кластера.</span><span class="sxs-lookup"><span data-stu-id="b344c-104">Manage the services on clustered servers with the Cluster Administrator.</span></span>  
  
 <span data-ttu-id="b344c-105">Чтобы управлять службой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и устанавливать параметры конфигурации сервера, необходимо быть членом предопределенной роли сервера **serveradmin** или **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="b344c-105">To manage the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service and set the server configuration options, you must be a member of the **serveradmin** fixed server role or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="b344c-106">Члены группы **Администраторы** Windows могут запускать и останавливать службы и настраивать параметры сервера, предоставляемые Windows.</span><span class="sxs-lookup"><span data-stu-id="b344c-106">Members of the Windows **Administrators** group can start and stop services and configure the server options that Windows provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b344c-107">Чтобы правильно функционировать, учетные записи, используемые для служб, должны быть настроены на правильный домен, файловую систему и разрешения реестра.</span><span class="sxs-lookup"><span data-stu-id="b344c-107">To operate properly, the accounts used for the services must be configured with the correct domain, file system, and registry permissions.</span></span> <span data-ttu-id="b344c-108">Сведения о необходимых разрешениях см. в разделе [Настройка учетных записей службы Windows и разрешений](configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b344c-108">For information about the required permissions, see [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md).</span></span>  
  
## <a name="windows-management-instrumentation"></a><span data-ttu-id="b344c-109">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="b344c-109">Windows Management Instrumentation</span></span>  
 <span data-ttu-id="b344c-110">Диспетчер конфигурации SQL Server и среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] используют инструментарий управления Windows (WMI) для отображения и изменения некоторых свойств сервера.</span><span class="sxs-lookup"><span data-stu-id="b344c-110">SQL Server Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] use Windows Management Instrumentation (WMI) to display and modify some of the server properties.</span></span> <span data-ttu-id="b344c-111">Чтобы управлять службами и получать состояния служб, пользователь должен иметь права доступа к объекту инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="b344c-111">To manage services and obtain the status of the services, the user must have rights to access the WMI object.</span></span> <span data-ttu-id="b344c-112">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]следующие страницы свойств сервера используют инструментарий WMI:</span><span class="sxs-lookup"><span data-stu-id="b344c-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the following server property pages use WMI:</span></span>  
  
-   <span data-ttu-id="b344c-113">Службы, запускаемые автоматически</span><span class="sxs-lookup"><span data-stu-id="b344c-113">Autostart Services</span></span>  
  
-   <span data-ttu-id="b344c-114">Параметры запуска</span><span class="sxs-lookup"><span data-stu-id="b344c-114">Startup Parameters</span></span>  
  
-   <span data-ttu-id="b344c-115">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b344c-115">Security</span></span>  
  
-   <span data-ttu-id="b344c-116">Прочие параметры сервера</span><span class="sxs-lookup"><span data-stu-id="b344c-116">Misc Server Settings</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b344c-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="b344c-117">Related Tasks</span></span>  
 [<span data-ttu-id="b344c-118">Настройка инструментария WMI для отображения состояния сервера в инструментальных средствах SQL Server</span><span class="sxs-lookup"><span data-stu-id="b344c-118">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
## <a name="related-content"></a><span data-ttu-id="b344c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b344c-119">Related Content</span></span>  
 [<span data-ttu-id="b344c-120">Основные понятия о поставщике WMI для управления конфигурацией</span><span class="sxs-lookup"><span data-stu-id="b344c-120">WMI Provider for Configuration Management Concepts</span></span>](../../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
