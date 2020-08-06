---
title: Автоматический запуск агента SQL Server (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- autostart SQL Server Agent
ms.assetid: 2ea332da-0ede-4d2b-b122-c4c10eaca191
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39c7c7a112370797a965cfa601bc07f983a7a37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665761"
---
# <a name="autostart-sql-server-agent-sql-server-management-studio"></a><span data-ttu-id="de42b-102">Autostart SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="de42b-102">Autostart SQL Server Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="de42b-103">В этом разделе описано, как настроить [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Автоматический перезапуск агента в случае непредвиденной остановки в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de42b-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically restart if it should stop unexpectedly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="de42b-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="de42b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="de42b-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="de42b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="de42b-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="de42b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="de42b-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="de42b-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="de42b-108">Настройка агента SQL Server на автоматический перезапуск с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de42b-108">To configure SQL Server Agent to automatically restart, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="de42b-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="de42b-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="de42b-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="de42b-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="de42b-111">Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="de42b-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="de42b-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="de42b-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="de42b-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="de42b-113">Permissions</span></span>  
 <span data-ttu-id="de42b-114">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de42b-114">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="de42b-115">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="de42b-115">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="de42b-116">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="de42b-116">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="de42b-117">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="de42b-117">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="de42b-118">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="de42b-118">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="de42b-119">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="de42b-119">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="de42b-120">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="de42b-120">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="de42b-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de42b-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent-to-automatically-restart"></a><span data-ttu-id="de42b-122">Настройка агента SQL Server на автоматический перезапуск</span><span class="sxs-lookup"><span data-stu-id="de42b-122">To configure SQL Server Agent to automatically restart</span></span>  
  
1.  <span data-ttu-id="de42b-123">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, на котором необходимо настроить агент SQL Server на автоматический перезапуск.</span><span class="sxs-lookup"><span data-stu-id="de42b-123">In **Object Explorer**, click the plus sign to expand the server where you want to configure SQL Server Agent to automatically restart.</span></span>  
  
2.  <span data-ttu-id="de42b-124">Щелкните правой кнопкой мыши **агент SQL Server**, затем выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="de42b-124">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="de42b-125">На странице **Общие** установите флажок **Автоматически запускать агент SQL Server в случае непредвиденной остановки**.</span><span class="sxs-lookup"><span data-stu-id="de42b-125">On the **General** page, check **Auto restart SQL Server Agent if it stops unexpectedly**.</span></span>  
  
  
