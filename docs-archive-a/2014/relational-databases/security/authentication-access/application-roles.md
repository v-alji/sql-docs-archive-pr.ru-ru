---
title: Роли приложений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- application roles [SQL Server], about application roles
- principals [SQL Server], application roles
- credentials [SQL Server], roles
- application roles [SQL Server]
- roles [SQL Server], application
- permissions [SQL Server], roles
- users [SQL Server], application roles
- authentication [SQL Server], roles
- groups [SQL Server], roles
ms.assetid: dca18b8a-ca03-4b7f-9a46-8474d5b66f76
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: f2fcc7b1e333bb42a00675da5bb9fd559d1c34f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656283"
---
# <a name="application-roles"></a><span data-ttu-id="53941-102">Роли приложений</span><span class="sxs-lookup"><span data-stu-id="53941-102">Application Roles</span></span>
  <span data-ttu-id="53941-103">Роль приложения — это участник базы данных, позволяющий приложению выполняться со своими, подобными пользовательским, правами доступа.</span><span class="sxs-lookup"><span data-stu-id="53941-103">An application role is a database principal that enables an application to run with its own, user-like permissions.</span></span> <span data-ttu-id="53941-104">Роли приложений можно использовать для разрешения доступа к определенным данным только тем пользователям, которые подключены посредством конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="53941-104">You can use application roles to enable access to specific data to only those users who connect through a particular application.</span></span> <span data-ttu-id="53941-105">В отличие от ролей баз данных, роли приложений не содержат элементов и по умолчанию находятся в неактивном состоянии.</span><span class="sxs-lookup"><span data-stu-id="53941-105">Unlike database roles, application roles contain no members and are inactive by default.</span></span> <span data-ttu-id="53941-106">Роли приложений работают с обоими режимами проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="53941-106">Application roles work with both authentication modes.</span></span> <span data-ttu-id="53941-107">Роли приложений активируются с помощью процедуры **sp_setapprole**, которая требует указания пароля.</span><span class="sxs-lookup"><span data-stu-id="53941-107">Application roles are enabled by using **sp_setapprole**, which requires a password.</span></span> <span data-ttu-id="53941-108">Так как роли приложений являются участниками на уровне базы данных, они имеют доступ к другим базам данных только с разрешениями, предоставленными учетной записи пользователя **guest**в этих базах данных.</span><span class="sxs-lookup"><span data-stu-id="53941-108">Because application roles are a database-level principal, they can access other databases only through permissions granted in those databases to **guest**.</span></span> <span data-ttu-id="53941-109">Таким образом, любая база данных, в которой была отключена учетная запись пользователя **guest** , не будет доступна для ролей приложений в других базах данных.</span><span class="sxs-lookup"><span data-stu-id="53941-109">Therefore, any database in which **guest** has been disabled will be inaccessible to application roles in other databases.</span></span>  
  
 <span data-ttu-id="53941-110">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]роли приложений не имеют доступ к метаданным уровня сервера, так как они не связаны с участником на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="53941-110">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], application roles cannot access server-level metadata because they are not associated with a server-level principal.</span></span> <span data-ttu-id="53941-111">Чтобы отключить это ограничение, позволив тем самым ролям приложений получать доступ к метаданным уровня сервера, установите глобальный флаг 4616.</span><span class="sxs-lookup"><span data-stu-id="53941-111">To disable this restriction and thereby allow application roles to access server-level metadata, set the global flag 4616.</span></span> <span data-ttu-id="53941-112">Дополнительные сведения см. в разделах [Флаги трассировки (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql) и [DBCC TRACEON (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53941-112">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql) and [DBCC TRACEON &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql).</span></span>  
  
## <a name="connecting-with-an-application-role"></a><span data-ttu-id="53941-113">Соединение с ролью приложения</span><span class="sxs-lookup"><span data-stu-id="53941-113">Connecting with an Application Role</span></span>  
 <span data-ttu-id="53941-114">Ниже представлены этапы процесса, при помощи которого роль приложения переключает контексты безопасности.</span><span class="sxs-lookup"><span data-stu-id="53941-114">The following steps make up the process by which an application role switches security contexts:</span></span>  
  
1.  <span data-ttu-id="53941-115">Пользователь выполняет клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="53941-115">A user executes a client application.</span></span>  
  
2.  <span data-ttu-id="53941-116">Клиентское приложение соединяется с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в качестве пользователя.</span><span class="sxs-lookup"><span data-stu-id="53941-116">The client application connects to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the user.</span></span>  
  
3.  <span data-ttu-id="53941-117">Приложение выполняет хранимую процедуру **sp_setapprole** с использованием пароля, известного только этому приложению.</span><span class="sxs-lookup"><span data-stu-id="53941-117">The application then executes the **sp_setapprole** stored procedure with a password known only to the application.</span></span>  
  
4.  <span data-ttu-id="53941-118">Если имя и пароль роли приложения достоверны, она становится активной.</span><span class="sxs-lookup"><span data-stu-id="53941-118">If the application role name and password are valid, the application role is enabled.</span></span>  
  
5.  <span data-ttu-id="53941-119">На этом этапе соединение утрачивает разрешения пользователя и приобретает разрешения роли приложения.</span><span class="sxs-lookup"><span data-stu-id="53941-119">At this point the connection loses the permissions of the user and assumes the permissions of the application role.</span></span>  
  
 <span data-ttu-id="53941-120">Разрешения, полученные через роль приложения, действуют в течение всего соединения.</span><span class="sxs-lookup"><span data-stu-id="53941-120">The permissions acquired through the application role remain in effect for the duration of the connection.</span></span>  
  
 <span data-ttu-id="53941-121">В более ранних версиях [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]единственным способом для пользователя вновь приобрести свой исходный контекст безопасности после активации роли приложения было отсоединение и повторное соединение с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53941-121">In earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the only way for a user to reacquire its original security context after starting an application role is to disconnect and reconnect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="53941-122">Начиная с версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]процедура **sp_setapprole** имеет новый параметр, который создает файл cookie.</span><span class="sxs-lookup"><span data-stu-id="53941-122">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], **sp_setapprole** has an option that creates a cookie.</span></span> <span data-ttu-id="53941-123">Этот файл содержит сведения о контексте до того, как роль приложения переходит в активное состояние.</span><span class="sxs-lookup"><span data-stu-id="53941-123">The cookie contains context information before the application role is enabled.</span></span> <span data-ttu-id="53941-124">Файл cookie может использоваться процедурой **sp_unsetapprole** для возврата сеанса в исходный контекст.</span><span class="sxs-lookup"><span data-stu-id="53941-124">The cookie can be used by **sp_unsetapprole** to revert the session to its original context.</span></span> <span data-ttu-id="53941-125">Сведения об этом новом параметре и пример см. в разделе [sp_setapprole (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-setapprole-transact-sql)в этих базах данных.</span><span class="sxs-lookup"><span data-stu-id="53941-125">For information about this new option and an example, see [sp_setapprole &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setapprole-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="53941-126">Параметр **encrypt** ODBC не поддерживается в **SqlClient**.</span><span class="sxs-lookup"><span data-stu-id="53941-126">The ODBC **encrypt** option is not supported by **SqlClient**.</span></span> <span data-ttu-id="53941-127">При передаче конфиденциальных сведений по сети следует пользоваться протоколом SSL или IPSec для шифрования канала.</span><span class="sxs-lookup"><span data-stu-id="53941-127">When you are transmitting confidential information over a network, use Secure Sockets Layer (SSL) or IPsec to encrypt the channel.</span></span> <span data-ttu-id="53941-128">Если необходимо сохранить учетные данные в клиентском приложении, следует зашифровать их при помощи функций API шифрования.</span><span class="sxs-lookup"><span data-stu-id="53941-128">If you must persist credentials in the client application, encrypt the credentials by using the crypto API functions.</span></span> <span data-ttu-id="53941-129">В [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] и более поздних версиях параметр *password* хранится в виде одностороннего хэша.</span><span class="sxs-lookup"><span data-stu-id="53941-129">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later versions, the parameter *password* is stored as a one-way hash.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="53941-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="53941-130">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53941-131">Создание роли приложения.</span><span class="sxs-lookup"><span data-stu-id="53941-131">Create an application role.</span></span>|<span data-ttu-id="53941-132">[Создание роли приложения](create-an-application-role.md) и [CREATE APPLICATION ROLE (Transact-SQL)](/sql/t-sql/statements/create-application-role-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="53941-132">[Create an Application Role](create-an-application-role.md) and [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql)</span></span>|  
|<span data-ttu-id="53941-133">Изменение роли приложения.</span><span class="sxs-lookup"><span data-stu-id="53941-133">Alter an application role.</span></span>|[<span data-ttu-id="53941-134">ALTER APPLICATION ROLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="53941-134">ALTER APPLICATION ROLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-application-role-transact-sql)|  
|<span data-ttu-id="53941-135">Удаление роли приложения.</span><span class="sxs-lookup"><span data-stu-id="53941-135">Delete an application role.</span></span>|[<span data-ttu-id="53941-136">DROP APPLICATION ROLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="53941-136">DROP APPLICATION ROLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-application-role-transact-sql)|  
|<span data-ttu-id="53941-137">Использование роли приложения.</span><span class="sxs-lookup"><span data-stu-id="53941-137">Using an application role.</span></span>|[<span data-ttu-id="53941-138">sp_setapprole (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="53941-138">sp_setapprole &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-setapprole-transact-sql)|  
  
## <a name="see-also"></a><span data-ttu-id="53941-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="53941-139">See Also</span></span>  
 [<span data-ttu-id="53941-140">Обеспечение безопасности SQL Server</span><span class="sxs-lookup"><span data-stu-id="53941-140">Securing SQL Server</span></span>](../securing-sql-server.md)  
  
  
