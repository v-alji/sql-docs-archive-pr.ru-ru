---
title: Субъекты (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectroll.f1
- sql12.swb.databaseuser.permissions.user.f1--May use common.permissions
helpviewer_keywords:
- certificates [SQL Server], principals
- roles [SQL Server], principals
- permissions [SQL Server], principals
- '##MS_SQLAuthenticatorCertificate##'
- principals [SQL Server]
- '##MS_SQLResourceSigningCertificate##'
- groups [SQL Server], principals
- '##MS_AgentSigningCertificate##'
- authentication [SQL Server], principals
- schemas [SQL Server], principals
- principals [SQL Server], about principals
- security [SQL Server], principals
- users [SQL Server], principals
- '##MS_SQLReplicationSigningCertificate##'
ms.assetid: 3f7adbf7-6e40-4396-a8ca-71cbb843b5c2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 808c8516b3ed9e95ea4c724736461cb00923a7fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668729"
---
# <a name="principals-database-engine"></a><span data-ttu-id="aeab7-102">Субъекты (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="aeab7-102">Principals (Database Engine)</span></span>
  <span data-ttu-id="aeab7-103">*Субъекты* — это сущности, которые могут запрашивать ресурсы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aeab7-103">*Principals* are entities that can request [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources.</span></span> <span data-ttu-id="aeab7-104">Как и другие компоненты модели авторизации [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , участников можно иерархически упорядочить.</span><span class="sxs-lookup"><span data-stu-id="aeab7-104">Like other components of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authorization model, principals can be arranged in a hierarchy.</span></span> <span data-ttu-id="aeab7-105">Область влияния субъекта зависит от области его определения: Windows, сервер, база данных, — а также от того, неделимый это субъект или коллекция.</span><span class="sxs-lookup"><span data-stu-id="aeab7-105">The scope of influence of a principal depends on the scope of the definition of the principal: Windows, server, database; and whether the principal is indivisible or a collection.</span></span> <span data-ttu-id="aeab7-106">Имя входа Windows является примером индивидуального (неделимого) субъекта, а группа Windows — коллективного.</span><span class="sxs-lookup"><span data-stu-id="aeab7-106">A Windows Login is an example of an indivisible principal, and a Windows Group is an example of a principal that is a collection.</span></span> <span data-ttu-id="aeab7-107">Каждый субъект имеет идентификатор безопасности (SID).</span><span class="sxs-lookup"><span data-stu-id="aeab7-107">Every principal has a security identifier (SID).</span></span>  
  
 <span data-ttu-id="aeab7-108">**Субъекты уровня Windows**</span><span class="sxs-lookup"><span data-stu-id="aeab7-108">**Windows-level principals**</span></span>  
  
-   <span data-ttu-id="aeab7-109">Имя входа домена Windows</span><span class="sxs-lookup"><span data-stu-id="aeab7-109">Windows Domain Login</span></span>  
  
-   <span data-ttu-id="aeab7-110">Локальное имя входа Windows</span><span class="sxs-lookup"><span data-stu-id="aeab7-110">Windows Local Login</span></span>  
  
 <span data-ttu-id="aeab7-111">**SQL Server** - **level** **субъекты** уровня</span><span class="sxs-lookup"><span data-stu-id="aeab7-111">**SQL Server**-**level** **principals**</span></span>  
  
-   <span data-ttu-id="aeab7-112">Имя входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aeab7-112">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Login</span></span>  
  
-   <span data-ttu-id="aeab7-113">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="aeab7-113">Server Role</span></span>  
  
 <span data-ttu-id="aeab7-114">**Субъекты уровня базы данных**</span><span class="sxs-lookup"><span data-stu-id="aeab7-114">**Database-level principals**</span></span>  
  
-   <span data-ttu-id="aeab7-115">Пользователь базы данных</span><span class="sxs-lookup"><span data-stu-id="aeab7-115">Database User</span></span>  
  
-   <span data-ttu-id="aeab7-116">Роль базы данных</span><span class="sxs-lookup"><span data-stu-id="aeab7-116">Database Role</span></span>  
  
-   <span data-ttu-id="aeab7-117">Роль приложения</span><span class="sxs-lookup"><span data-stu-id="aeab7-117">Application Role</span></span>  
  
## <a name="the-sql-server-sa-login"></a><span data-ttu-id="aeab7-118">Имя входа «sa» SQL Server</span><span class="sxs-lookup"><span data-stu-id="aeab7-118">The SQL Server sa Login</span></span>  
 <span data-ttu-id="aeab7-119">Имя входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sa является субъектом уровня сервера.</span><span class="sxs-lookup"><span data-stu-id="aeab7-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sa log in is a server-level principal.</span></span> <span data-ttu-id="aeab7-120">По умолчанию оно создается при установке экземпляра.</span><span class="sxs-lookup"><span data-stu-id="aeab7-120">By default, it is created when an instance is installed.</span></span> <span data-ttu-id="aeab7-121">Начиная с версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]базой данных для имени входа sa по умолчанию является master.</span><span class="sxs-lookup"><span data-stu-id="aeab7-121">Beginning in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the default database of sa is master.</span></span> <span data-ttu-id="aeab7-122">Это поведение было изменено по сравнению с предыдущими версиями [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aeab7-122">This is a change of behavior from earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="public-database-role"></a><span data-ttu-id="aeab7-123">Роль базы данных public</span><span class="sxs-lookup"><span data-stu-id="aeab7-123">public Database Role</span></span>  
 <span data-ttu-id="aeab7-124">Каждый пользователь базы данных является членом роли базы данных public.</span><span class="sxs-lookup"><span data-stu-id="aeab7-124">Every database user belongs to the public database role.</span></span> <span data-ttu-id="aeab7-125">Если пользователю не были предоставлены или запрещены особые разрешения на доступ к защищаемому объекту, то он наследует для него разрешения роли public.</span><span class="sxs-lookup"><span data-stu-id="aeab7-125">When a user has not been granted or denied specific permissions on a securable, the user inherits the permissions granted to public on that securable.</span></span>  
  
## <a name="information_schema-and-sys"></a><span data-ttu-id="aeab7-126">INFORMATION_SCHEMA и sys</span><span class="sxs-lookup"><span data-stu-id="aeab7-126">INFORMATION_SCHEMA and sys</span></span>  
 <span data-ttu-id="aeab7-127">Каждая база данных включает в себя две сущности, которые отображены в качестве пользователей в представлениях каталога: INFORMATION_SCHEMA и sys.</span><span class="sxs-lookup"><span data-stu-id="aeab7-127">Every database includes two entities that appear as users in catalog views: INFORMATION_SCHEMA and sys.</span></span> <span data-ttu-id="aeab7-128">Они необходимы для работы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)];</span><span class="sxs-lookup"><span data-stu-id="aeab7-128">These entities are required by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aeab7-129">эти пользователи не являются субъектами и не могут быть изменены или удалены.</span><span class="sxs-lookup"><span data-stu-id="aeab7-129">They are not principals, and they cannot be modified or dropped.</span></span>  
  
## <a name="certificate-based-sql-server-logins"></a><span data-ttu-id="aeab7-130">Имена входа SQL Server на основе сертификата</span><span class="sxs-lookup"><span data-stu-id="aeab7-130">Certificate-based SQL Server Logins</span></span>  
 <span data-ttu-id="aeab7-131">Субъекты уровня сервера, имеющие имена, заключенные в хэш-символы (##), — только для внутреннего системного пользования.</span><span class="sxs-lookup"><span data-stu-id="aeab7-131">Server principals with names enclosed by double hash marks (##) are for internal system use only.</span></span> <span data-ttu-id="aeab7-132">Следующие участники создаются из сертификатов при установке [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и не должны удаляться.</span><span class="sxs-lookup"><span data-stu-id="aeab7-132">The following principals are created from certificates when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is installed, and should not be deleted.</span></span>  
  
-   <span data-ttu-id="aeab7-133">\##MS_SQLResourceSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="aeab7-133">\##MS_SQLResourceSigningCertificate##</span></span>  
  
-   <span data-ttu-id="aeab7-134">\##MS_SQLReplicationSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="aeab7-134">\##MS_SQLReplicationSigningCertificate##</span></span>  
  
-   <span data-ttu-id="aeab7-135">\##MS_SQLAuthenticatorCertificate##</span><span class="sxs-lookup"><span data-stu-id="aeab7-135">\##MS_SQLAuthenticatorCertificate##</span></span>  
  
-   <span data-ttu-id="aeab7-136">\##MS_AgentSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="aeab7-136">\##MS_AgentSigningCertificate##</span></span>  
  
-   <span data-ttu-id="aeab7-137">\##MS_PolicyEventProcessingLogin##</span><span class="sxs-lookup"><span data-stu-id="aeab7-137">\##MS_PolicyEventProcessingLogin##</span></span>  
  
-   <span data-ttu-id="aeab7-138">\##MS_PolicySigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="aeab7-138">\##MS_PolicySigningCertificate##</span></span>  
  
-   <span data-ttu-id="aeab7-139">\##MS_PolicyTsqlExecutionLogin##</span><span class="sxs-lookup"><span data-stu-id="aeab7-139">\##MS_PolicyTsqlExecutionLogin##</span></span>  
  
## <a name="the-guest-user"></a><span data-ttu-id="aeab7-140">Пользователь-гость</span><span class="sxs-lookup"><span data-stu-id="aeab7-140">The guest User</span></span>  
 <span data-ttu-id="aeab7-141">Каждая база данных включает в себя пользователя **guest**.</span><span class="sxs-lookup"><span data-stu-id="aeab7-141">Each database includes a **guest**.</span></span> <span data-ttu-id="aeab7-142">Разрешения, предоставленные пользователю **guest** , наследуются пользователями, которые имеют доступ к базе данных, но не обладают учетной записью пользователя в ней.</span><span class="sxs-lookup"><span data-stu-id="aeab7-142">Permissions granted to the **guest** user are inherited by users who have access to the database, but who do not have a user account in the database.</span></span> <span data-ttu-id="aeab7-143">**Гостевой** пользователь нельзя удалить, но его можно отключить, отменив его `CONNECT` разрешение.</span><span class="sxs-lookup"><span data-stu-id="aeab7-143">The **guest** user cannot be dropped, but it can be disabled by revoking it's `CONNECT` permission.</span></span> <span data-ttu-id="aeab7-144">`CONNECT`Разрешение можно отозвать, выполнив `REVOKE CONNECT FROM GUEST` в любой базе данных, отличной от Master или tempdb.</span><span class="sxs-lookup"><span data-stu-id="aeab7-144">The `CONNECT` permission can be revoked by executing `REVOKE CONNECT FROM GUEST` within any database other than master or tempdb.</span></span>  
  
## <a name="client-and-database-server"></a><span data-ttu-id="aeab7-145">Клиент и сервер базы данных</span><span class="sxs-lookup"><span data-stu-id="aeab7-145">Client and Database Server</span></span>  
 <span data-ttu-id="aeab7-146">По определению клиент и сервер базы данных являются защищаемыми субъектами безопасности.</span><span class="sxs-lookup"><span data-stu-id="aeab7-146">By definition, a client and a database server are security principals and can be secured.</span></span> <span data-ttu-id="aeab7-147">Данные сущности могут пройти взаимную проверку подлинности перед установкой безопасного сетевого соединения.</span><span class="sxs-lookup"><span data-stu-id="aeab7-147">These entities can be mutually authenticated before a secure network connection is established.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="aeab7-148">поддерживает протокол проверки подлинности [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) , который определяет, как клиенты взаимодействуют со службой проверки подлинности сети.</span><span class="sxs-lookup"><span data-stu-id="aeab7-148">supports the [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) authentication protocol, which defines how clients interact with a network authentication service.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="aeab7-149">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="aeab7-149">Related Tasks</span></span>  
 <span data-ttu-id="aeab7-150">Данный раздел электронной документации по [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] содержит следующие подразделы.</span><span class="sxs-lookup"><span data-stu-id="aeab7-150">The following topics are included in this section of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="aeab7-151">Инструкции по управлению именами входа, пользователями и схемами</span><span class="sxs-lookup"><span data-stu-id="aeab7-151">Managing Logins, Users, and Schemas How-to Topics</span></span>](managing-logins-users-and-schemas-how-to-topics.md)  
  
-   [<span data-ttu-id="aeab7-152">Роли уровня сервера</span><span class="sxs-lookup"><span data-stu-id="aeab7-152">Server-Level Roles</span></span>](server-level-roles.md)  
  
-   [<span data-ttu-id="aeab7-153">Роли уровня базы данных</span><span class="sxs-lookup"><span data-stu-id="aeab7-153">Database-Level Roles</span></span>](database-level-roles.md)  
  
-   [<span data-ttu-id="aeab7-154">Роли приложений</span><span class="sxs-lookup"><span data-stu-id="aeab7-154">Application Roles</span></span>](application-roles.md)  
  
## <a name="see-also"></a><span data-ttu-id="aeab7-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="aeab7-155">See Also</span></span>  
 <span data-ttu-id="aeab7-156">[Обеспечение безопасности SQL Server](../securing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aeab7-156">[Securing SQL Server](../securing-sql-server.md) </span></span>  
 <span data-ttu-id="aeab7-157">[sys.database_principals (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aeab7-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span></span>  
 <span data-ttu-id="aeab7-158">[sys.server_principals (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aeab7-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span></span>  
 <span data-ttu-id="aeab7-159">[sys.sql_logins (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aeab7-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span></span>  
 <span data-ttu-id="aeab7-160">[sys.database_role_members (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aeab7-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span></span>  
 <span data-ttu-id="aeab7-161">[Роли уровня сервера](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="aeab7-161">[Server-Level Roles](server-level-roles.md) </span></span>  
 [<span data-ttu-id="aeab7-162">Роли уровня базы данных</span><span class="sxs-lookup"><span data-stu-id="aeab7-162">Database-Level Roles</span></span>](database-level-roles.md)  
  
  
