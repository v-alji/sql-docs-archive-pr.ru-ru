---
title: Установка подключения SQL Server для службы агент SQL Server (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, connections
- connections [SQL Server], SQL Server Agent service
ms.assetid: 28b6178b-0a9e-4f2c-8562-7a62d2d2a285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30f68967d6bdb8b0495cbddb1a5b0bd447cd5168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669237"
---
# <a name="set-the-sql-server-connection-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="879ab-102">Настройка соединения SQL Server для агента SQL Server (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="879ab-102">Set the SQL Server Connection for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="879ab-103">В этом разделе описывается настройка соединения между агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="879ab-103">This topic describes how to set the connection between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="879ab-104">Служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может подключаться к локальному экземпляру SQL Server с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="879ab-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can connect to a local instance of SQL Server by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="879ab-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="879ab-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="879ab-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="879ab-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="879ab-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="879ab-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="879ab-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="879ab-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="879ab-109">**Для настройки соединения SQL Server с агентом SQL Server используется:**</span><span class="sxs-lookup"><span data-stu-id="879ab-109">**To set the SQL Server Connection for the SQL Server Agent, using:**</span></span>  
  
     [<span data-ttu-id="879ab-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="879ab-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="879ab-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="879ab-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="879ab-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="879ab-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="879ab-113">Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="879ab-113">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="879ab-114">Начиная с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживает проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="879ab-114">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="879ab-115">Данная возможность доступна только в случае администрирования более ранней версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="879ab-115">This option is available only when you administer an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="879ab-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="879ab-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="879ab-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="879ab-117">Permissions</span></span>  
 <span data-ttu-id="879ab-118">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="879ab-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="879ab-119">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="879ab-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="879ab-120">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="879ab-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="879ab-121">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="879ab-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="879ab-122">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="879ab-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="879ab-123">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="879ab-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="879ab-124">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="879ab-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="879ab-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="879ab-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-sql-server-connection"></a><span data-ttu-id="879ab-126">Настройка соединения с сервером SQL Server</span><span class="sxs-lookup"><span data-stu-id="879ab-126">To set the SQL Server connection</span></span>  
  
1.  <span data-ttu-id="879ab-127">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, который нужно настроить для соединения со службой агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="879ab-127">In **Object Explorer**, click the plus sign to expand the server that you want to set up with a connection to its SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="879ab-128">Щелкните правой кнопкой мыши **Агент SQL Server** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="879ab-128">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="879ab-129">В диалоговом окне **SQL Server Agent Properties** (Свойства агента SQL Server) в разделе **Выберите страницу** щелкните **Соединение**.</span><span class="sxs-lookup"><span data-stu-id="879ab-129">In the **SQL Server Agent Properties** dialog box, under **Select a page**, click **Connection**.</span></span>  
  
4.  <span data-ttu-id="879ab-130">В разделе **Соединение с SQL Server** выберите **Использовать проверку подлинности Windows**, чтобы включить подключение агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности Windows [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="879ab-130">Under **SQL Server connection**, select **Use Windows Authentication** to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="879ab-131">Проверка подлинности Windows необходима для соединений с базами данных [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="879ab-131">Connections to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later databases require Windows Authentication.</span></span>  
  
  
