---
title: Send SQL Server Agent Error Messages | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- messages [SQL Server], SQL Server Agent
- sending messages
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 2597d0d7-951a-48cf-989f-abb67b9fdb36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 03e38b02188eaced65a86b22ed4f22cb6984ce0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665753"
---
# <a name="send-sql-server-agent-error-messages"></a><span data-ttu-id="3ca4f-102">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="3ca4f-102">Send SQL Server Agent Error Messages</span></span>
  <span data-ttu-id="3ca4f-103">В этом разделе описывается настройка [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агента для отправки сообщений об ошибках с помощью команды net send в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ca4f-103">This topic describes how to how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send its error messages by way of net send in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3ca4f-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3ca4f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3ca4f-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3ca4f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3ca4f-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3ca4f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3ca4f-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3ca4f-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="3ca4f-108">Отправка сообщений об ошибках агента SQL Server с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ca4f-108">To send SQL Server Agent error messages using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3ca4f-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3ca4f-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3ca4f-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3ca4f-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3ca4f-111">Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="3ca4f-112">Для приема сообщений net send необходимо запустить службу [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger service must be running to receive net send events.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3ca4f-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="3ca4f-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3ca4f-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="3ca4f-114">Permissions</span></span>  
 <span data-ttu-id="3ca4f-115">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ca4f-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3ca4f-116">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="3ca4f-117">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="3ca4f-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="3ca4f-118">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="3ca4f-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="3ca4f-119">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="3ca4f-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="3ca4f-120">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="3ca4f-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="3ca4f-121">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3ca4f-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3ca4f-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ca4f-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-send-sql-server-agent-error-messages"></a><span data-ttu-id="3ca4f-123">Отправка сообщений об ошибках агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ca4f-123">To send SQL Server Agent error messages</span></span>  
  
1.  <span data-ttu-id="3ca4f-124">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий журнал ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , из которого необходимо отправлять сообщения об ошибках командой net send.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log from which you want to send error messages via net send.</span></span>  
  
2.  <span data-ttu-id="3ca4f-125">Щелкните правой кнопкой мыши **Агент SQL Server** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-125">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="3ca4f-126">В диалоговом окне **свойства агент SQL Server —**_server_name_ в разделе **журнал ошибок** на странице **Общие** введите имя пользователя или компьютера, для которого нужно отправить сообщения об ошибках, в поле **Получатель net send** .</span><span class="sxs-lookup"><span data-stu-id="3ca4f-126">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, , type the user name or computer name to which you want to send error messages in the **Net send recipient** box.</span></span>  
  
4.  <span data-ttu-id="3ca4f-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-127">Click **OK**.</span></span>  
  
  
