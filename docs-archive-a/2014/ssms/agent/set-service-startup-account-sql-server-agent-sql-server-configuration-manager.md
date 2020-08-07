---
title: Настройка стартовой учетной записи службы для агент SQL Server (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- startup accounts [SQL Server]
- service startup accounts [SQL Server Agent]
ms.assetid: 46ffe818-ebb5-43a0-840b-923f219a2472
author: stevestein
ms.author: sstein
ms.openlocfilehash: 63e5ba7c24f1aa1a3f79f80e5ca28c02a0cd5812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731322"
---
# <a name="set-the-service-startup-account-for-sql-server-agent-sql-server-configuration-manager"></a><span data-ttu-id="db574-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="db574-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="db574-103">Стартовая учетная запись службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет учетную запись Windows, которая запускает агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а также его сетевые разрешения.</span><span class="sxs-lookup"><span data-stu-id="db574-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account defines the Windows account that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs as, as well as its network permissions.</span></span> <span data-ttu-id="db574-104">Этот раздел посвящен назначению учетных записей службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db574-104">This topic describes how to set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="db574-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="db574-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="db574-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="db574-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="db574-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="db574-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="db574-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="db574-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="db574-109">Назначение стартовой учетной записи службы для службы агента SQL Server при помощи среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="db574-109">To set the Service Startup Account for SQL Server Agent using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="db574-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="db574-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="db574-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="db574-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="db574-112">Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] больше не требует, чтобы стартовая учетная запись была элементом группы администраторов [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db574-112">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer requires that the service startup account be a member of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Administrators group.</span></span> <span data-ttu-id="db574-113">Однако стартовая учетная запись службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должна быть членом предопределенной роли сервера sysadmin [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db574-113">However, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account must be a member of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin fixed server role.</span></span> <span data-ttu-id="db574-114">Чтобы использовать обработку заданий в многосерверной среде, учетная запись должна быть членом роли "TargetServersRole" базы данных "msdb" на главном сервере.</span><span class="sxs-lookup"><span data-stu-id="db574-114">The account must also be a member of the msdb database role TargetServersRole on the master server if multiserver job processing is used.</span></span>  
  
-   <span data-ttu-id="db574-115">Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="db574-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="db574-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="db574-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="db574-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="db574-117">Permissions</span></span>  
 <span data-ttu-id="db574-118">Для выполнения своих функций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Агент должен быть настроен на использование учетных данных учетной записи, которая является членом `sysadmin` предопределенной роли сервера в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db574-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the `sysadmin` fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="db574-119">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="db574-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="db574-120">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="db574-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="db574-121">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="db574-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="db574-122">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="db574-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="db574-123">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="db574-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="db574-124">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="db574-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="db574-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="db574-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-service-startup-account-for-sql-server-agent"></a><span data-ttu-id="db574-126">Назначение стартовой учетной записи службы агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="db574-126">To set the Service Startup Account for SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="db574-127">В списке **Зарегистрированные серверы**щелкните знак «плюс», чтобы развернуть **Ядро СУБД**.</span><span class="sxs-lookup"><span data-stu-id="db574-127">In **Registered Servers**, click the plus sign to expand **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="db574-128">Чтобы развернуть папку **Группы локальных серверов** , щелкните знак «плюс» (+).</span><span class="sxs-lookup"><span data-stu-id="db574-128">Click the plus sign to expand the **Local Server Groups** folder.</span></span>  
  
3.  <span data-ttu-id="db574-129">Щелкните правой кнопкой мыши экземпляр сервера, в котором нужно назначить стартовую учетную запись службы, и выберите **Диспетчер конфигурации SQL Server...**</span><span class="sxs-lookup"><span data-stu-id="db574-129">Right-click the server instance where you want set up the Service Startup Account, and select **SQL Server Configuration Manager...**.</span></span>  
  
4.  <span data-ttu-id="db574-130">В диалоговом окне **Контроль учетных записей** нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="db574-130">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="db574-131">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на панели консоли выберите **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="db574-131">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, select **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="db574-132">В области сведений щелкните правой кнопкой мыши **Агент SQL Server**_(server_name)_, где *server_name* — имя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляра агента, для которого необходимо изменить стартовую учетную запись службы, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="db574-132">In the details pane, right-click **SQL Server Agent**_(server_name)_, where *server_name* is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance for which you want to change the service startup account, and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="db574-133">В диалоговом окне **свойства** **Агент SQL Server**_(server_name)_ на вкладке **Вход** в систему выберите один из следующих параметров в разделе **Вход в систему как**.</span><span class="sxs-lookup"><span data-stu-id="db574-133">In the **SQL Server Agent**_(server_name)_ **Properties** dialog box, in the **Log On** tab, select one of the following options under **Log on as**:</span></span>  
  
    -   <span data-ttu-id="db574-134">**Встроенная учетная запись**. Выберите этот параметр, если заданиям требуются ресурсы только с локального сервера.</span><span class="sxs-lookup"><span data-stu-id="db574-134">**Built-in account**: select this option if your jobs require resources from the local server only.</span></span> <span data-ttu-id="db574-135">Дополнительные сведения о выборе типа встроенной учетной записи Windows см. в разделе [Выбор учетной записи для службы агента SQL Server.](https://msdn.microsoft.com/library/ms191543.aspx)</span><span class="sxs-lookup"><span data-stu-id="db574-135">For information about how to choose a Windows built-in account type, see [Selecting an Account for SQL Server Agent Service.](https://msdn.microsoft.com/library/ms191543.aspx)</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="db574-136"> Служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживает учетную запись **Локальная служба** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db574-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service does not support the **Local Service** account in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="db574-137">**Указанная учетная запись**. Выберите этот параметр, если заданиям требуются сетевые ресурсы (в том числе ресурсы приложений), а также если необходимо передавать события журналам других программ Windows или уведомлять операторов по электронной почте или на пейджер.</span><span class="sxs-lookup"><span data-stu-id="db574-137">**This account**: select this option if your jobs require resources across the network, including application resources; if you want to forward events to other Windows application logs; or if you want to notify operators through e-mail or pagers.</span></span>  
  
         <span data-ttu-id="db574-138">В случае использования этого параметра:</span><span class="sxs-lookup"><span data-stu-id="db574-138">If you select this option:</span></span>  
  
        1.  <span data-ttu-id="db574-139">В поле **Имя учетной записи** введите учетную запись, которая будет использоваться для запуска агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="db574-139">In the **Account Name** box, enter the account that will be used to run SQL Server Agent.</span></span> <span data-ttu-id="db574-140">Или нажмите кнопку **Обзор** , чтобы открыть диалоговое окно **Выбор пользователя или группы** , и выберите учетную запись для использования.</span><span class="sxs-lookup"><span data-stu-id="db574-140">Alternately, click **Browse** to open the **Select User or Group** dialog box and select the account to use.</span></span>  
  
        2.  <span data-ttu-id="db574-141">В поле **Пароль** введите пароль, соответствующий учетной записи.</span><span class="sxs-lookup"><span data-stu-id="db574-141">In the **Password** box, enter the password for the account.</span></span> <span data-ttu-id="db574-142">Повторно введите пароль в поле **Подтверждение пароля** .</span><span class="sxs-lookup"><span data-stu-id="db574-142">Re-enter the password in the **Confirm password** box.</span></span>  
  
8.  <span data-ttu-id="db574-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="db574-143">Click **OK**.</span></span>  
  
9. <span data-ttu-id="db574-144">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] нажмите кнопку **Закрыть** .</span><span class="sxs-lookup"><span data-stu-id="db574-144">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click the **Close** button.</span></span>  
  
  
