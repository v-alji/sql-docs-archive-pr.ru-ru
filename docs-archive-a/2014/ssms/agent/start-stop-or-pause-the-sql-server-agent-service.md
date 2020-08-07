---
title: Запуск, остановка или приостановка службы агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- SQL Server Agent, pausing
- SQL Server Agent, stopping
ms.assetid: c95a9759-dd30-4ab6-9ab0-087bb3bfb97c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2feb6a18c602271b1bec871fbfc9793979b100e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727889"
---
# <a name="start-stop-or-pause-the-sql-server-agent-service"></a><span data-ttu-id="afc41-102">Start, Stop, or Pause the SQL Server Agent Service</span><span class="sxs-lookup"><span data-stu-id="afc41-102">Start, Stop, or Pause the SQL Server Agent Service</span></span>
  <span data-ttu-id="afc41-103">В этом разделе описывается, как запустить, остановить или перезапустить службу агента SQL Server в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afc41-103">This topic describes how to start, stop, or restart the SQL Server Agent Service in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="afc41-104">Службу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно настроить для автоматического запуска вместе с операционной системой или запуска вручную для выполнения определенных заданий.</span><span class="sxs-lookup"><span data-stu-id="afc41-104">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically when the operating system starts, or you can start it manually when you need to complete jobs.</span></span> <span data-ttu-id="afc41-105">Службу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно остановить или приостановить, чтобы прекратить выполнение заданий, уведомления операторов и оповещения.</span><span class="sxs-lookup"><span data-stu-id="afc41-105">You can stop or pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to suspend jobs, operator notifications, and alerts.</span></span>  
  
 <span data-ttu-id="afc41-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="afc41-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="afc41-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="afc41-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="afc41-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="afc41-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="afc41-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="afc41-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="afc41-110">Запуск, остановка и перезапуск службы агента SQL Server с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afc41-110">To start, stop, or restart the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="afc41-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="afc41-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="afc41-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="afc41-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="afc41-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Для автоматизации административных задач агент должен работать как служба.</span><span class="sxs-lookup"><span data-stu-id="afc41-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running as a service in order to automate administrative tasks.</span></span> <span data-ttu-id="afc41-114">Дополнительные сведения см. в статье [Configure SQL Server Agent](configure-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="afc41-114">For more information, see [Configure SQL Server Agent](configure-sql-server-agent.md).</span></span>  
  
-   <span data-ttu-id="afc41-115">Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="afc41-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="afc41-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="afc41-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="afc41-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="afc41-117">Permissions</span></span>  
 <span data-ttu-id="afc41-118">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afc41-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="afc41-119">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="afc41-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="afc41-120">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="afc41-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="afc41-121">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="afc41-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="afc41-122">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="afc41-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="afc41-123">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="afc41-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="afc41-124">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="afc41-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="afc41-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afc41-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-stop-or-restart-the-sql-server-agent-service"></a><span data-ttu-id="afc41-126">Запуск, остановка и перезапуск службы агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="afc41-126">To start, stop, or restart the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="afc41-127">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, на котором нужно управлять службой агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="afc41-127">In **Object Explorer**, click the plus sign to expand the server where you want to manage SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="afc41-128">Щелкните правой кнопкой мыши элемент **Агент SQL Server**и выберите команду **Запуск**, **Стоп**или **Перезапуск**.</span><span class="sxs-lookup"><span data-stu-id="afc41-128">Right-click **SQL Server Agent**, and then select either **Start**, **Stop**, or **Restart**.</span></span>  
  
3.  <span data-ttu-id="afc41-129">В диалоговом окне **Контроль учетных записей** нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="afc41-129">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="afc41-130">При появлении запроса о необходимости выполнения действия нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="afc41-130">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
 <span data-ttu-id="afc41-131">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="afc41-131">For more information, see:</span></span>  
  
-   [<span data-ttu-id="afc41-132">Запуск, остановка, приостановка, возобновление и перезапуск компонента Database Engine, агента SQL и службы браузера SQL Server</span><span class="sxs-lookup"><span data-stu-id="afc41-132">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
-   [<span data-ttu-id="afc41-133">Автоматический запуск агента SQL Server (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="afc41-133">Autostart SQL Server Agent &#40;SQL Server Management Studio&#41;</span></span>](autostart-sql-server-agent-sql-server-management-studio.md)  
  
  
