---
title: Переименование журнала ошибок агента SQL Server (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- renaming SQL Server Agent error log
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: dee2b199-48af-44cb-9177-d029a5edb169
author: stevestein
ms.author: sstein
ms.openlocfilehash: c1c85550a29bfff316ffc275ba2d4e4df10686d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668566"
---
# <a name="rename-a-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="96353-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="96353-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="96353-103">В этом разделе описывается, как переименовать файл, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в который записываются ошибки агента [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96353-103">This topic describes how to rename the file where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent errors are written in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="96353-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="96353-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="96353-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="96353-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="96353-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="96353-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="96353-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="96353-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="96353-108">Переименование журнала ошибок агента SQL Server с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96353-108">To rename a SQL Server Agent error log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96353-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="96353-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="96353-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="96353-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="96353-111">Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="96353-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96353-112">будет записывать сведения в новый файл журнала только после перезапуска службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96353-112">Agent will not write to the new log file until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is restarted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="96353-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="96353-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="96353-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="96353-114">Permissions</span></span>  
 <span data-ttu-id="96353-115">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96353-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="96353-116">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="96353-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="96353-117">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="96353-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="96353-118">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="96353-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="96353-119">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="96353-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="96353-120">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="96353-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="96353-121">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="96353-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96353-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96353-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-sql-server-agent-error-log"></a><span data-ttu-id="96353-123">Переименование журнала ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="96353-123">To rename a SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="96353-124">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, содержащий журнал агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который необходимо переименовать.</span><span class="sxs-lookup"><span data-stu-id="96353-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to rename.</span></span>  
  
2.  <span data-ttu-id="96353-125">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="96353-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="96353-126">Щелкните правой кнопкой мыши папку **Журналы ошибок** и выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="96353-126">Right-click the **Error Logs** folder and select **Configure**.</span></span>  
  
4.  <span data-ttu-id="96353-127">В диалоговом окне **Настройка журналов ошибок агента SQL Server** введите путь к новому файлу и имя файла журнала ошибок в поле **Файл журнала ошибок** .</span><span class="sxs-lookup"><span data-stu-id="96353-127">In the **Configure SQL Server Agent Error Logs** dialog box, in the **Error log file** box, enter the new file path and file name for the error log.</span></span> <span data-ttu-id="96353-128">Можно также щелкнуть многоточие **(...)** и открыть диалоговое окно **Укажите расположение журнала ошибок агента** .</span><span class="sxs-lookup"><span data-stu-id="96353-128">Alternately, click the ellipsis **(...)** to open the **Specify agent error log location** dialog box.</span></span>  
  
5.  <span data-ttu-id="96353-129">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="96353-129">When finished, click **OK**.</span></span>  
  
  
