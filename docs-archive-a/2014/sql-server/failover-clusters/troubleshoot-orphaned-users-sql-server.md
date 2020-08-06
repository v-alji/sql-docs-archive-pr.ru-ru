---
title: Устранение неполадок, связанных с пользователями, утратившими связь с учетной записью (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- orphaned users [SQL Server]
- logins [SQL Server], orphaned users
- troubleshooting [SQL Server], user accounts
- user accounts [SQL Server], orphaned users
- failover [SQL Server], managing metadata
- database mirroring [SQL Server], metadata
- users [SQL Server], orphaned
ms.assetid: 11eefa97-a31f-4359-ba5b-e92328224133
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5df714d818949b921ff2236e50d58913eab0e0db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659292"
---
# <a name="troubleshoot-orphaned-users-sql-server"></a><span data-ttu-id="63753-102">Диагностика пользователей, утративших связь с учетной записью (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="63753-102">Troubleshoot Orphaned Users (SQL Server)</span></span>
  <span data-ttu-id="63753-103">Чтобы войти в экземпляр Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], участник должен иметь допустимое имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63753-103">To log into an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a principal must have a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="63753-104">Это имя используется в процессе проверки подлинности, который проверяет, разрешено ли участнику подключаться к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63753-104">This login is used in the authentication process that verifies whether the principal is allowed to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="63753-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Имена входа на экземпляре сервера отображаются в представлении каталога **sys. server_principals** и в представлении совместимости **sys.sysных имен входа** .</span><span class="sxs-lookup"><span data-stu-id="63753-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins on a server instance are visible in the **sys.server_principals** catalog view and the **sys.syslogins** compatibility view.</span></span>  
  
 <span data-ttu-id="63753-106">Имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] получают доступ к отдельным базам данных с помощью пользователя базы данных, сопоставленного с именем входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63753-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins access individual databases using a database user that is mapped to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="63753-107">Существует два исключения из этого правила:</span><span class="sxs-lookup"><span data-stu-id="63753-107">There are two exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="63753-108">Учетная запись гостя.</span><span class="sxs-lookup"><span data-stu-id="63753-108">The guest account.</span></span>  
  
     <span data-ttu-id="63753-109">Если в базе данных эта учетная запись включена, она позволяет именам входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которые не сопоставлены с пользователями базы данных, входить в базу данных как пользователь-гость.</span><span class="sxs-lookup"><span data-stu-id="63753-109">This is an account that, when enabled in the database, enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are not mapped to a database user to enter the database as the guest user.</span></span>  
  
-   <span data-ttu-id="63753-110">Членство в группе Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="63753-110">Microsoft Windows group memberships.</span></span>  
  
     <span data-ttu-id="63753-111">Имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , созданное из учетной записи пользователя Windows, может войти в базу данных, если пользователь Windows входит в группу Windows, являющуюся также пользователем базы данных.</span><span class="sxs-lookup"><span data-stu-id="63753-111">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login created from a Windows user can enter a database if the Windows user is a member of a Windows group that is also a user in the database.</span></span>  
  
 <span data-ttu-id="63753-112">Сведения о сопоставлении имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с пользователем базы данных хранятся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="63753-112">Information about the mapping of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to a database user is stored within the database.</span></span> <span data-ttu-id="63753-113">Эти сведения включают в себя имя пользователя базы данных и идентификатор безопасности соответствующего имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63753-113">It includes the name of the database user and the SID of the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="63753-114">Разрешения этого пользователя базы данных используются для авторизации в базе данных.</span><span class="sxs-lookup"><span data-stu-id="63753-114">The permissions of this database user are used for authorization in the database.</span></span>  
  
 <span data-ttu-id="63753-115">Пользователь базы данных, соответствующее имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] которого для экземпляра сервера не определено или задано неправильно, не сможет подключиться к этому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="63753-115">A database user for which the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is undefined or is incorrectly defined on a server instance cannot log in to the instance.</span></span> <span data-ttu-id="63753-116">Такой пользователь называется *утратившим связь с учетной записью* базы данных на этом экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="63753-116">Such a user is said to be an *orphaned user* of the database on that server instance.</span></span> <span data-ttu-id="63753-117">Пользователь базы данных может утратить связь с учетной записью в случае удаления соответствующего имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63753-117">A database user can become orphaned if the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is dropped.</span></span> <span data-ttu-id="63753-118">Кроме того, пользователь базы данных может утратить связь с учетной записью после того, как база данных будет восстановлена или прикреплена к другому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63753-118">Also, a database user can become orphaned after a database is restored or attached to a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="63753-119">Утрата связи с учетной записью может произойти, если пользователь базы данных сопоставлен с идентификатором безопасности, отсутствующим в новом экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="63753-119">Orphaning can happen if the database user is mapped to a SID that is not present in the new server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63753-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Имя входа не может получить доступ к базе данных, в которой отсутствует соответствующий пользователь базы данных, если в этой базе данных не включен **гостевой** учет.</span><span class="sxs-lookup"><span data-stu-id="63753-120">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login cannot access a database in which it lacks a corresponding database user unless **guest** is enabled in that database.</span></span> <span data-ttu-id="63753-121">Сведения о создании учетной записи пользователя базы данных см. в разделе [CREATE user &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="63753-121">For information about creating a database user account, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="to-detect-orphaned-users"></a><span data-ttu-id="63753-122">Обнаружение утративших связь с учетной записью пользователей</span><span class="sxs-lookup"><span data-stu-id="63753-122">To Detect Orphaned Users</span></span>  
 <span data-ttu-id="63753-123">Чтобы обнаружить пользователей, утративших связь с учетной записью, выполните следующие инструкции языка Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="63753-123">To detect orphaned users, execute the following Transact-SQL statements:</span></span>  
  
```  
USE <database_name>;  
GO;   
sp_change_users_login @Action='Report';  
GO;  
```  
  
 <span data-ttu-id="63753-124">Выходные данные содержат список пользователей и соответствующие идентификаторы безопасности в текущей базе данных, которые не связаны ни с одним именем входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63753-124">The output lists the users and corresponding security identifiers (SID) in the current database that are not linked to any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="63753-125">Дополнительные сведения см. в разделе [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="63753-125">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63753-126">**sp_change_users_login** нельзя использовать с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] именами входа, созданными из Windows.</span><span class="sxs-lookup"><span data-stu-id="63753-126">**sp_change_users_login** cannot be used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are created from Windows.</span></span>  
  
## <a name="to-resolve-an-orphaned-user"></a><span data-ttu-id="63753-127">Разрешение пользователей, утративших связь с учетной записью</span><span class="sxs-lookup"><span data-stu-id="63753-127">To Resolve an Orphaned User</span></span>  
 <span data-ttu-id="63753-128">Чтобы разрешить пользователя, утратившего связь с учетной записью, используйте следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="63753-128">To resolve an orphaned user, use the following procedure:</span></span>  
  
1.  <span data-ttu-id="63753-129">Следующая команда повторно связывает учетную запись входа сервера, указанную *<login_name,>* с пользователем базы данных, заданным \*<database_user \*>.</span><span class="sxs-lookup"><span data-stu-id="63753-129">The following command relinks the server login account specified by *<login_name>* with the database user specified by *<database_user>*.</span></span>  
  
    ```  
    USE <database_name>;  
    GO  
    sp_change_users_login @Action='update_one', @UserNamePattern='<database_user>', @LoginName='<login_name>';  
    GO  
  
    ```  
  
     <span data-ttu-id="63753-130">Дополнительные сведения см. в разделе [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="63753-130">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
2.  <span data-ttu-id="63753-131">После того как будет выполнен код на предыдущем шаге, пользователь сможет обращаться к базе данных.</span><span class="sxs-lookup"><span data-stu-id="63753-131">After you run the code in the preceding step, the user can access the database.</span></span> <span data-ttu-id="63753-132">Затем пользователь может изменить пароль *<login_name>* учетной записи входа с помощью хранимой процедуры **sp_password** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="63753-132">The user then can alter the password of the *<login_name>* login account by using the **sp_password** stored procedure, as follows:</span></span>  
  
    ```  
    USE master   
    GO  
    sp_password @old=NULL, @new='password', @loginame='<login_name>';  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="63753-133">Только имена входа с разрешением ALTER ANY LOGIN могут изменять пароль других имен входа пользователей.</span><span class="sxs-lookup"><span data-stu-id="63753-133">Only logins with the ALTER ANY LOGIN permission can change the password of another user's login.</span></span> <span data-ttu-id="63753-134">Однако только члены роли **sysadmin** могут изменять пароли членов роли **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="63753-134">However, only members of the **sysadmin** role can modify passwords of **sysadmin** role members.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63753-135">**sp_password** нельзя использовать для [!INCLUDE[msCoName](../../includes/msconame-md.md)] учетных записей Windows.</span><span class="sxs-lookup"><span data-stu-id="63753-135">**sp_password** cannot be used for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows accounts.</span></span> <span data-ttu-id="63753-136">Пользователи, соединяющиеся с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] через свою сетевую учетную запись Windows, проходят проверку подлинности в Windows, поэтому их пароли могут быть изменены только в Windows.</span><span class="sxs-lookup"><span data-stu-id="63753-136">Users connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through their Windows network account are authenticated by Windows; therefore, their passwords can only be changed in Windows.</span></span>  
  
     <span data-ttu-id="63753-137">Дополнительные сведения см. в разделе [sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="63753-137">For more information, see [sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63753-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="63753-138">See Also</span></span>  
 <span data-ttu-id="63753-139">[CREATE USER (Transact-SQL)](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="63753-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="63753-140">[CREATE LOGIN (Transact-SQL)](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="63753-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="63753-141">[sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="63753-141">[sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span></span>  
 <span data-ttu-id="63753-142">[sp_addlogin (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="63753-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span></span>  
 <span data-ttu-id="63753-143">[sp_grantlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="63753-143">[sp_grantlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span></span>  
 <span data-ttu-id="63753-144">[sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="63753-144">[sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span></span>  
 <span data-ttu-id="63753-145">[sys.sysпользователей &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="63753-145">[sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span></span>  
 [<span data-ttu-id="63753-146">sys.sysимена входа &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="63753-146">sys.syslogins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql)  
  
  
