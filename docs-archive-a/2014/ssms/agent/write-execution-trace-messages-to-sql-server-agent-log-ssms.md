---
title: Запись сообщений трассировки выполнения в агент SQL Server журнал ошибок (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- writing trace messages
- traces [SQL Server], SQL Server Agent logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 90e3731e-6fae-43db-833e-9accecdd1c03
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38b08452ef2680b654dd735b901488cb5f5f5f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734886"
---
# <a name="write-execution-trace-messages-to-the-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="46e6c-102">Запись сообщений трассировки выполнения в журнал ошибок агента SQL Server (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="46e6c-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="46e6c-103">В этом разделе описывается настройка [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агента для включения сообщений трассировки выполнения в журнал ошибок в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46e6c-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to include execution trace messages in its error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="46e6c-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="46e6c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="46e6c-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="46e6c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="46e6c-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="46e6c-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="46e6c-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="46e6c-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="46e6c-108">Запись сообщений трассировки выполнения в журнал ошибок агента SQL Server с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="46e6c-108">To write execution trace messages to the SQL Server Agent Error Log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="46e6c-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="46e6c-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="46e6c-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="46e6c-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="46e6c-111">Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="46e6c-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="46e6c-112">Включайте сообщения трассировки выполнения в журнал ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] только при возникновении конкретной проблемы в работе агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , поскольку его использование приводит к резкому увеличению объема журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="46e6c-112">Because this option can cause the error log to become large, only include execution trace messages in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs when investigating a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent problem.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="46e6c-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="46e6c-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="46e6c-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="46e6c-114">Permissions</span></span>  
 <span data-ttu-id="46e6c-115">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46e6c-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="46e6c-116">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="46e6c-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="46e6c-117">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="46e6c-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="46e6c-118">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="46e6c-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="46e6c-119">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="46e6c-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="46e6c-120">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="46e6c-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="46e6c-121">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="46e6c-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>   
#### <a name="to-write-execution-trace-messages-to-the-sql-server-agent-error-log"></a><span data-ttu-id="46e6c-122">Запись сообщений трассировки выполнения в журнал ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="46e6c-122">To write execution trace messages to the SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="46e6c-123">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий журнал ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в который необходимо записать сообщения трассировки выполнения.</span><span class="sxs-lookup"><span data-stu-id="46e6c-123">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log to which you want to write execution trace messages.</span></span>  
  
2.  <span data-ttu-id="46e6c-124">Щелкните правой кнопкой мыши **Агент SQL Server** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="46e6c-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="46e6c-125">В диалоговом окне **свойства агент SQL Server —**_server_name_ в разделе **журнал ошибок** на странице **Общие** установите флажок **включить сообщения трассировки выполнения** .</span><span class="sxs-lookup"><span data-stu-id="46e6c-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, select the **Include execution trace messages** check box.</span></span>  
  
4.  <span data-ttu-id="46e6c-126">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="46e6c-126">Click **OK**.</span></span>  
  
  
