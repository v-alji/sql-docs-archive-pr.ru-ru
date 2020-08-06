---
title: Задание псевдонима SQL Server для службы агент SQL Server (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], creating
- SQL Server Agent, aliases
ms.assetid: 02d6295d-ab52-44f0-8f1b-f3910a507d8f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b178d91a47d907b182ef7962b98c7f22d4454094
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655332"
---
# <a name="set-a-sql-server-alias-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="d51ca-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d51ca-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d51ca-103">В этом разделе описывается, как задать [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] псевдоним [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] агента для подключения к [!INCLUDE[ssDE](../includes/ssde-md.md)] компоненту с помощью [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d51ca-103">This topic describes how to set a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to use to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d51ca-104">По умолчанию служба агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] соединяется с экземпляром [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] через именованные каналы по динамическим именам серверов, которые не требуют дополнительной настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="d51ca-104">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] over named pipes by using dynamic server names that require no additional client configuration.</span></span> <span data-ttu-id="d51ca-105">Необходимо настроить только псевдоним соединения сервера, если не используется установленный по умолчанию сетевой механизм передачи данных или если происходит подключение к экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , прослушивающему по альтернативному именованному каналу.</span><span class="sxs-lookup"><span data-stu-id="d51ca-105">You need to configure a server connection alias only if you are not using the default network transport or if you are connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="d51ca-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d51ca-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d51ca-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d51ca-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d51ca-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d51ca-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d51ca-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d51ca-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="d51ca-110">Настройка псевдонима SQL Server для службы агента SQL Server в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d51ca-110">To set a SQL Server Alias for the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d51ca-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d51ca-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d51ca-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d51ca-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="d51ca-113">не будет работать правильно до тех пор, пока не будет выбран псевдоним, относящийся к местному экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d51ca-113">Agent will not work correctly unless you select an alias that refers to the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="d51ca-114">Узел агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="d51ca-114">Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d51ca-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="d51ca-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d51ca-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="d51ca-116">Permissions</span></span>  
 <span data-ttu-id="d51ca-117">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d51ca-117">To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d51ca-118">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="d51ca-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="d51ca-119">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="d51ca-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="d51ca-120">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="d51ca-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="d51ca-121">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="d51ca-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="d51ca-122">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="d51ca-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="d51ca-123">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d51ca-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d51ca-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d51ca-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-sql-server-alias-for-the-sql-server-agent-service"></a><span data-ttu-id="d51ca-125">Настройка псевдонима SQL Server для службы агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="d51ca-125">To set a SQL Server Alias for the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="d51ca-126">В **Обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] и раскройте его.</span><span class="sxs-lookup"><span data-stu-id="d51ca-126">In the **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d51ca-127">Щелкните правой кнопкой мыши **агент SQL Server**, затем выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d51ca-127">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d51ca-128">В диалоговом окне **Агент SQL Server свойства**_server_name_ в разделе **Выбор страницы**выберите **Подключение**и</span><span class="sxs-lookup"><span data-stu-id="d51ca-128">In the **SQL Server Agent Properties**_server_name_ dialog box, under **Select a page**, select **Connection**, and</span></span>  
  
4.  <span data-ttu-id="d51ca-129">в поле **Псевдоним локального хоста сервера** введите псевдоним сервера, с которым должен соединяться агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d51ca-129">In the **Alias local host server** box, type the alias of the server to which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should connect.</span></span>  
  
5.  <span data-ttu-id="d51ca-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d51ca-130">Click **OK**.</span></span>  
  
  
