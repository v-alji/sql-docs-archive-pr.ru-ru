---
title: Присоединение к роли | Документация Майкрософт
ms.custom: ''
ms.date: 07/14/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.MEMBERSHIP.F1
helpviewer_keywords:
- adding a member to a role
- join a role
ms.assetid: 05c8d10d-5823-46c6-8b1a-81722da6a42b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 58e8c071672c8c3afba8d6c424488899dcf76be7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656279"
---
# <a name="join-a-role"></a><span data-ttu-id="ecacd-102">присоединение к роли</span><span class="sxs-lookup"><span data-stu-id="ecacd-102">Join a Role</span></span>
  <span data-ttu-id="ecacd-103">В этом разделе описывается назначение ролей для имен входа и пользователей базы данных в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecacd-103">This topic describes how to assign roles to logins and database users in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ecacd-104">Для эффективного управления разрешениями в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] используются роли.</span><span class="sxs-lookup"><span data-stu-id="ecacd-104">Use roles in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to efficiently manage permissions.</span></span> <span data-ttu-id="ecacd-105">Назначайте разрешения ролям, а затем добавляйте и удаляйте пользователей и имена входа в роли.</span><span class="sxs-lookup"><span data-stu-id="ecacd-105">Assign permissions to roles, and then add and remove users and logins to the roles.</span></span> <span data-ttu-id="ecacd-106">Благодаря ролям нет необходимости задавать разрешения для каждого пользователя в отдельности.</span><span class="sxs-lookup"><span data-stu-id="ecacd-106">By using roles, permissions do not have to be individually maintained for each user.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="ecacd-107">поддерживает четыре типа ролей.</span><span class="sxs-lookup"><span data-stu-id="ecacd-107">supports four types of roles.</span></span>  
  
-   <span data-ttu-id="ecacd-108">Предопределенные роли сервера</span><span class="sxs-lookup"><span data-stu-id="ecacd-108">Fixed server roles</span></span>  
  
-   <span data-ttu-id="ecacd-109">Определяемые пользователем роли сервера</span><span class="sxs-lookup"><span data-stu-id="ecacd-109">User-defined server roles</span></span>  
  
-   <span data-ttu-id="ecacd-110">Предопределенные роли базы данных</span><span class="sxs-lookup"><span data-stu-id="ecacd-110">Fixed database roles</span></span>  
  
-   <span data-ttu-id="ecacd-111">Определяемые пользователем роли базы данных</span><span class="sxs-lookup"><span data-stu-id="ecacd-111">User-defined database roles</span></span>  
  
 <span data-ttu-id="ecacd-112">Предопределенные роли доступны в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]автоматически.</span><span class="sxs-lookup"><span data-stu-id="ecacd-112">The fixed roles are automatically available in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ecacd-113">Предопределенные роли обладают необходимыми разрешениями для выполнения типичных задач.</span><span class="sxs-lookup"><span data-stu-id="ecacd-113">Fixed roles have the necessary permissions to accomplish common tasks.</span></span> <span data-ttu-id="ecacd-114">Дополнительные сведения о предопределенных ролях см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ecacd-114">For more information about fixed roles, see the following links.</span></span> <span data-ttu-id="ecacd-115">Определяемые пользователем роли создаются пользователем, им могут быть заданы любые разрешения по его выбору.</span><span class="sxs-lookup"><span data-stu-id="ecacd-115">User-defined roles are created by you, and can be customized with the permissions that you select.</span></span> <span data-ttu-id="ecacd-116">Дополнительные сведения об определяемых пользователем ролях см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ecacd-116">For more information about user-defined roles, see the following links.</span></span>  
  
 <span data-ttu-id="ecacd-117">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ecacd-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ecacd-118">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ecacd-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ecacd-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ecacd-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ecacd-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ecacd-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ecacd-121">**Для назначения ролей именам входа и пользователям базы данных используется:**</span><span class="sxs-lookup"><span data-stu-id="ecacd-121">**To assign roles to logins and database users, using:**</span></span>  
  
     [<span data-ttu-id="ecacd-122">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ecacd-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ecacd-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ecacd-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ecacd-124">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ecacd-124">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ecacd-125">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ecacd-125">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ecacd-126">Изменение имени роли базы данных не изменяет идентификационный номер, владельца или разрешения роли.</span><span class="sxs-lookup"><span data-stu-id="ecacd-126">Changing the name of a database role does not change ID number, owner, or permissions of the role.</span></span>  
  
-   <span data-ttu-id="ecacd-127">Роли базы данных видны в представлениях каталога sys.database_role_members и sys.database_principals.</span><span class="sxs-lookup"><span data-stu-id="ecacd-127">Database roles are visible in the sys.database_role_members and sys.database_principals catalog views.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ecacd-128">безопасность</span><span class="sxs-lookup"><span data-stu-id="ecacd-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ecacd-129">Permissions</span><span class="sxs-lookup"><span data-stu-id="ecacd-129">Permissions</span></span>  
 <span data-ttu-id="ecacd-130">Требуется `ALTER ANY ROLE` разрешение для базы данных, `ALTER` разрешение на роль или членство в **db_securityadmin**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-130">Requires `ALTER ANY ROLE` permission on the database, `ALTER` permission on the role, or membership in **db_securityadmin**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ecacd-131">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ecacd-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="ecacd-132">Добавление члена в предопределенную роль сервера</span><span class="sxs-lookup"><span data-stu-id="ecacd-132">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="ecacd-133">В обозревателе объектов разверните сервер, для которого нужно изменить предопределенную роль сервера.</span><span class="sxs-lookup"><span data-stu-id="ecacd-133">In Object Explorer, expand the server in which you want to edit a fixed server role.</span></span>  
  
2.  <span data-ttu-id="ecacd-134">Разверните папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="ecacd-134">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="ecacd-135">Разверните папку **Роли сервера**</span><span class="sxs-lookup"><span data-stu-id="ecacd-135">Expand the **Server Roles** folder</span></span>  
  
4.  <span data-ttu-id="ecacd-136">Щелкните правой кнопкой мыши роль, которую необходимо изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-136">Right-click the role you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="ecacd-137">В диалоговом окне **Свойства роли сервера —**_Server_role_name_ на странице **члены** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-137">In the **Server Role Properties -**_server_role_name_ dialog box, on the **Members** page, click **Add**.</span></span>  
  
6.  <span data-ttu-id="ecacd-138">В диалоговом окне **Выбор имени входа или роли сервера** в разделе **Введите имена объектов для выбора (примеры)** введите имя входа или роль сервера для добавления в эту роль сервера.</span><span class="sxs-lookup"><span data-stu-id="ecacd-138">In the **Select Server Login or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or server role to add to this server role.</span></span> <span data-ttu-id="ecacd-139">Также можно нажать кнопку **Обзор** и выбрать любые из доступных объектов в диалоговом окне **Выбор объектов**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-139">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="ecacd-140">Нажмите кнопку **ОК** , чтобы вернуться к диалоговому окну **Свойства роли сервера —**_server_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="ecacd-140">Click **OK** to return to the **Server Role Properties -**_server_role_name_ dialog box.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="ecacd-141">Добавление члена к определяемой пользователем роли базы данных</span><span class="sxs-lookup"><span data-stu-id="ecacd-141">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="ecacd-142">В обозревателе объектов разверните сервер, для которого нужно изменить определяемую пользователем роль базы данных.</span><span class="sxs-lookup"><span data-stu-id="ecacd-142">In Object Explorer, expand the server in which you want to edit a user-defined database role.</span></span>  
  
2.  <span data-ttu-id="ecacd-143">Разверните папку **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="ecacd-143">Expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="ecacd-144">Разверните базу данных, в которой нужно изменить определяемую пользователем роль базы данных.</span><span class="sxs-lookup"><span data-stu-id="ecacd-144">Expand the database in which you want to edit a user-defined database role.</span></span>  
  
4.  <span data-ttu-id="ecacd-145">Разверните папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="ecacd-145">Expand the **Security** folder.</span></span>  
  
5.  <span data-ttu-id="ecacd-146">Разверните папку **Роли** .</span><span class="sxs-lookup"><span data-stu-id="ecacd-146">Expand the **Roles** folder.</span></span>  
  
6.  <span data-ttu-id="ecacd-147">Разверните папку **Роли сервера** .</span><span class="sxs-lookup"><span data-stu-id="ecacd-147">Expand the **Server Roles** folder.</span></span>  
  
7.  <span data-ttu-id="ecacd-148">Щелкните правой кнопкой мыши роль, которую необходимо изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-148">Right-click the role you want to edit and select **Properties**.</span></span>  
  
8.  <span data-ttu-id="ecacd-149">В диалоговом окне **Свойства роли базы данных —**_Database_role_name_ на странице **Общие** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-149">In the **Database Role Properties -**_database_role_name_ dialog box, in the **General** page, click **Add**.</span></span>  
  
9. <span data-ttu-id="ecacd-150">В диалоговом окне **Выбор пользователя или роли базы данных** в разделе **Введите имена объектов для выбора (примеры)** введите имя входа или роль базы данных для добавления в эту роль базы данных.</span><span class="sxs-lookup"><span data-stu-id="ecacd-150">In the **Select Database User or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or database role to add to this database role.</span></span> <span data-ttu-id="ecacd-151">Также можно нажать кнопку **Обзор** и выбрать любые из доступных объектов в диалоговом окне **Выбор объектов**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-151">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="ecacd-152">Нажмите кнопку **ОК** , чтобы вернуться к диалоговому окну **Свойства роли базы данных —**_database_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="ecacd-152">Click **OK** to return to the **Database Role Properties -**_database_role_name_ dialog box.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ecacd-153">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ecacd-153">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="ecacd-154">Добавление члена в предопределенную роль сервера</span><span class="sxs-lookup"><span data-stu-id="ecacd-154">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="ecacd-155">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecacd-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ecacd-156">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-156">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ecacd-157">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-157">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER SERVER ROLE diskadmin ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="ecacd-158">Дополнительные сведения см. в разделе [ALTER ROLE (Transact-SQL)](/sql/t-sql/statements/alter-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ecacd-158">For more information, see [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span></span>  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="ecacd-159">Добавление члена к определяемой пользователем роли базы данных</span><span class="sxs-lookup"><span data-stu-id="ecacd-159">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="ecacd-160">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecacd-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ecacd-161">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ecacd-162">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ecacd-162">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER ROLE Marketing ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="ecacd-163">Дополнительные сведения см. в статье [sp_addrolemember (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ecacd-163">For more information, see [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecacd-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="ecacd-164">See Also</span></span>  
 <span data-ttu-id="ecacd-165">[Роли уровня сервера](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="ecacd-165">[Server-Level Roles](server-level-roles.md) </span></span>  
 <span data-ttu-id="ecacd-166">[Роли уровня базы данных](../authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="ecacd-166">[Database-Level Roles](../authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="ecacd-167">Роли приложений</span><span class="sxs-lookup"><span data-stu-id="ecacd-167">Application Roles</span></span>](../authentication-access/application-roles.md)  
  
  
