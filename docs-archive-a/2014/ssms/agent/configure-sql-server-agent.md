---
title: Настройка агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, configuring
- accounts [SQL Server], SQL Server Agent
- SQL Server Agent, permissions
- security [SQL Server], SQL Server Agent
ms.assetid: 2e361a62-9e92-4fcd-80d7-d6960f127900
author: stevestein
ms.author: sstein
ms.openlocfilehash: 81c78faf733fac5ffb9a6e74dbf03f8caaff03d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659077"
---
# <a name="configure-sql-server-agent"></a><span data-ttu-id="def29-102">Configure SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="def29-102">Configure SQL Server Agent</span></span>
  <span data-ttu-id="def29-103">В этом разделе описывается задание некоторых параметров конфигурации для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="def29-103">This topic describes how to specify some configuration options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent during installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="def29-104">Доступ к полному набору параметров конфигурации агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно получить с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], управляющих объектов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SMO) или хранимых процедур агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="def29-104">The full set of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent configuration options is only available within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO), or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures.</span></span>  
  
 <span data-ttu-id="def29-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="def29-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="def29-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="def29-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="def29-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="def29-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="def29-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="def29-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="def29-109">Настройка агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="def29-109">To configure SQL Server Agent</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="def29-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="def29-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="def29-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="def29-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="def29-112">Щелкните элемент **Агент SQL Server** в обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для администрирования заданий, операторов, оповещений и службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="def29-112">Click **SQL Server Agent** in Object Explorer of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to administer jobs, operators, alerts, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="def29-113">Однако с узлом агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в обозревателе объектов можно работать только при наличии соответствующего разрешения.</span><span class="sxs-lookup"><span data-stu-id="def29-113">However, Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="def29-114">В экземплярах отказоустойчивых кластеров не должен быть включен автоматический перезапуск службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="def29-114">Auto-restart should not be enabled for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on failover cluster instances.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="def29-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="def29-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="def29-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="def29-116">Permissions</span></span>  
 <span data-ttu-id="def29-117">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="def29-117">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="def29-118">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="def29-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="def29-119">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="def29-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="def29-120">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="def29-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="def29-121">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="def29-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="def29-122">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="def29-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="def29-123">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="def29-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="def29-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="def29-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent"></a><span data-ttu-id="def29-125">Настройка агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="def29-125">To configure SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="def29-126">Нажмите кнопку **Пуск** и щелкните в меню **Пуск**  элемент **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="def29-126">Click the **Start** button, and then, on the **Start**  menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="def29-127">На панели управления выберите категорию **Система и безопасность**, щелкните элемент **Администрирование**, а затем выберите пункт **Локальная политика безопасности**.</span><span class="sxs-lookup"><span data-stu-id="def29-127">In Control Panel, click **System and Security**, click **Administrative Tools**, and then select **Local Security Policy**.</span></span>  
  
3.  <span data-ttu-id="def29-128">В окне «Локальная политика безопасности» щелкните треугольник, чтобы развернуть папку **Локальные политики** , а затем щелкните папку **Назначение прав пользователя** .</span><span class="sxs-lookup"><span data-stu-id="def29-128">In Local Security Policy, click the chevron to expand the **Local Policies** folder, and then click the **User Rights Assignment** folder.</span></span>  
  
4.  <span data-ttu-id="def29-129">Щелкните правой кнопкой мыши разрешение, которое нужно настроить для использования с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="def29-129">Right-click a permission that you want to configure for use with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="def29-130">В диалоговом окне свойств разрешения убедитесь, что указана учетная запись, с которой работает агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="def29-130">In the permission's properties dialog box, verify that the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs is listed.</span></span> <span data-ttu-id="def29-131">Если это не так, нажмите кнопку **Добавить пользователя или группу**, введите учетную запись, с которой работает агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в диалоговом окне **Выбор пользователей, компьютеров, учетных записей служб или групп** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="def29-131">If not, click **Add User or Group**, enter the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs in the **Select Users, Computers, Service Accounts, or Groups** dialog box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="def29-132">Повторите эту процедуру для каждого разрешения, которое нужно добавить для работы с агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="def29-132">Repeat for each permission that you want to add to run with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="def29-133">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="def29-133">When finished, click **OK**.</span></span>  
  
  
