---
title: Создание роли сервера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverrole.members.f1
- SQL12.SWB.SERVERROLE.GENERAL.F1
- sql12.swb.serverrole.memberships.f1
helpviewer_keywords:
- SERVER ROLE, creating
ms.assetid: 74f19992-8082-4ed7-92a1-04fe676ee82d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45c3d5bb9c9c7fdae9abe18ab3cb808cae4c1fa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667003"
---
# <a name="create-a-server-role"></a><span data-ttu-id="c2716-102">Создание роли сервера</span><span class="sxs-lookup"><span data-stu-id="c2716-102">Create a Server Role</span></span>
  <span data-ttu-id="c2716-103">В этом разделе описывается создание новой роли сервера в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2716-103">This topic describes how to create a new server role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c2716-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c2716-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c2716-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c2716-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c2716-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c2716-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c2716-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c2716-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c2716-108">**Создание новой роли сервера с помощью:**</span><span class="sxs-lookup"><span data-stu-id="c2716-108">**To create a new server role, using:**</span></span>  
  
     [<span data-ttu-id="c2716-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c2716-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c2716-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c2716-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c2716-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c2716-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c2716-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c2716-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c2716-113">Ролям сервера нельзя предоставить разрешение на защищаемые объекты уровня базы данных.</span><span class="sxs-lookup"><span data-stu-id="c2716-113">Server roles cannot be granted permission on database-level securables.</span></span> <span data-ttu-id="c2716-114">Сведения о создании ролей базы данных см. в статье [CREATE ROLE (Transact-SQL)](/sql/t-sql/statements/create-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c2716-114">To create database roles, see [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c2716-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="c2716-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c2716-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="c2716-116">Permissions</span></span>  
  
-   <span data-ttu-id="c2716-117">Требует разрешения CREATE SERVER ROLE или членства в предопределенной роли сервера.</span><span class="sxs-lookup"><span data-stu-id="c2716-117">Requires CREATE SERVER ROLE permission or membership in the sysadmin fixed server role.</span></span>  
  
-   <span data-ttu-id="c2716-118">Также требует разрешения IMPERSONATE на *server_principal* для имен входа, разрешения ALTER для ролей сервера, которые используются в качестве *server_principal*, или членства в группе Windows, которая используется в качестве server_principal.</span><span class="sxs-lookup"><span data-stu-id="c2716-118">Also requires IMPERSONATE on the *server_principal* for logins, ALTER permission for server roles used as the *server_principal*, or membership in a Windows group that is used as the server_principal.</span></span>  
  
-   <span data-ttu-id="c2716-119">Если для назначения владельца роли сервера указывается параметр AUTHORIZATION, необходимы также следующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="c2716-119">When you use the AUTHORIZATION option to assign server role ownership, the following permissions are also required:</span></span>  
  
    -   <span data-ttu-id="c2716-120">Для передачи роли сервера во владение другому имени входа необходимо связанное с этим именем входа разрешение IMPERSONATE.</span><span class="sxs-lookup"><span data-stu-id="c2716-120">To assign ownership of a server role to another login, requires IMPERSONATE permission on that login.</span></span>  
  
    -   <span data-ttu-id="c2716-121">Для передачи роли сервера во владение другой роли сервера необходимо членство в роли сервера-получателя или связанное с этой ролью сервера разрешение ALTER.</span><span class="sxs-lookup"><span data-stu-id="c2716-121">To assign ownership of a server role to another server role, requires membership in the recipient server role or ALTER permission on that server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c2716-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c2716-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="c2716-123">Создание новой роли сервера</span><span class="sxs-lookup"><span data-stu-id="c2716-123">To create a new server role</span></span>  
  
1.  <span data-ttu-id="c2716-124">В обозревателе объектов разверните сервер, на котором необходимо создать новую роль сервера.</span><span class="sxs-lookup"><span data-stu-id="c2716-124">In Object Explorer, expand the server where you want to create the new server role.</span></span>  
  
2.  <span data-ttu-id="c2716-125">Разверните папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="c2716-125">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="c2716-126">Щелкните правой кнопкой мыши папку **Роли сервера** и выберите **Создать роль сервера…** .</span><span class="sxs-lookup"><span data-stu-id="c2716-126">Right-click the **Server Roles** folder and select **New Server Role...**.</span></span>  
  
4.  <span data-ttu-id="c2716-127">В диалоговом окне **Новая роль сервера —**_Server_role_name_ на странице **Общие** введите имя новой роли сервера в поле **имя роли сервера** .</span><span class="sxs-lookup"><span data-stu-id="c2716-127">In the **New Server Role -**_server_role_name_ dialog box, on the **General** page, enter a name for the new server role in the **Server role name** box.</span></span>  
  
5.  <span data-ttu-id="c2716-128">В поле **Владелец** введите имя участника на уровне сервера, которому будет принадлежать новая роль.</span><span class="sxs-lookup"><span data-stu-id="c2716-128">In the **Owner** box, enter the name of the server principal that will own the new role.</span></span> <span data-ttu-id="c2716-129">Также можно нажать кнопку с многоточием **(...)** , чтобы открыть диалоговое окно **Выбор имени входа или роли сервера**.</span><span class="sxs-lookup"><span data-stu-id="c2716-129">Alternately, click the ellipsis **(...)** to open the **Select Server Login or Role** dialog box.</span></span>  
  
6.  <span data-ttu-id="c2716-130">В поле **Защищаемые объекты**выберите один или несколько защищаемых объектов уровня сервера.</span><span class="sxs-lookup"><span data-stu-id="c2716-130">Under **Securables**, select one or more server-level securables.</span></span> <span data-ttu-id="c2716-131">Когда выбран защищаемый объект, роли сервера могут быть предоставлены или запрещены разрешения для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="c2716-131">When a securable is selected, this server role can be granted or denied permissions on that securable.</span></span>  
  
7.  <span data-ttu-id="c2716-132">В поле **Явные разрешения** установите флажок, чтобы предоставить, предоставить с правом передачи или отменить разрешение на выбранные защищаемые объекты для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="c2716-132">In the **Permissions: Explicit** box, select the check box to grant, grant with grant, or deny permission to this server role for the selected securables.</span></span> <span data-ttu-id="c2716-133">Если разрешение не может быть предоставлено или отменено для всех выделенных защищаемых объектов, разрешение представляется как частично выбранное.</span><span class="sxs-lookup"><span data-stu-id="c2716-133">If a permission cannot be granted or denied to all of the selected securables, the permission is represented as a partial select.</span></span>  
  
8.  <span data-ttu-id="c2716-134">На странице **Члены** с помощью кнопки **Добавить** добавьте имена входа, представляющие определенных пользователей или их группы, в новую роль сервера.</span><span class="sxs-lookup"><span data-stu-id="c2716-134">On the **Members** page, use the **Add** button to add logins that represent individuals or groups to the new server role.</span></span>  
  
9. <span data-ttu-id="c2716-135">Определяемая пользователем роль сервера может быть членом другой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="c2716-135">A user-defined server role can be a member of another server role.</span></span> <span data-ttu-id="c2716-136">На странице **Членство** установите флажок, чтобы текущая, определяемая пользователем роль сервера стала членом выбранной роли сервера.</span><span class="sxs-lookup"><span data-stu-id="c2716-136">On the **Memberships** page, select a check box to make the current user-defined server role a member of a selected server role.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c2716-137">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c2716-137">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="c2716-138">Создание новой роли сервера</span><span class="sxs-lookup"><span data-stu-id="c2716-138">To create a new server role</span></span>  
  
1.  <span data-ttu-id="c2716-139">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2716-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c2716-140">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c2716-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c2716-141">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c2716-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Creates the server role auditors that is owned the securityadmin fixed server role.  
    USE master;  
    CREATE SERVER ROLE auditors AUTHORIZATION securityadmin;  
    GO  
    ```  
  
 <span data-ttu-id="c2716-142">Дополнительные сведения см. в разделе [CREATE SERVER ROLE (Transact-SQL)](/sql/t-sql/statements/create-server-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c2716-142">For more information, see [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span></span>  
  
  
