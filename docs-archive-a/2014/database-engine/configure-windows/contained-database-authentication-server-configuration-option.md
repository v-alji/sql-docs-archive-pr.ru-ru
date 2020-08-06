---
title: Параметр конфигурации сервера "проверка подлинности автономной базы данных" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- contained_database_authentication_TSQL
- contained database authentication
helpviewer_keywords:
- contained database, enabling
- contained database authentication option
ms.assetid: b80768d2-ac20-4035-a335-d9adb74b3f6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf5bf07c8b0913ff81f31ff0ca64a18eee0f2ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665541"
---
# <a name="contained-database-authentication-server-configuration-option"></a><span data-ttu-id="e8380-102">Параметр конфигурации сервера «проверка подлинности автономной базы данных»</span><span class="sxs-lookup"><span data-stu-id="e8380-102">contained database authentication Server Configuration Option</span></span>
  <span data-ttu-id="e8380-103">Параметр **проверка подлинности автономной базы данных** позволяет включить автономные базы данных на экземпляре [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8380-103">Use the **contained database authentication** option to enable contained databases on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e8380-104">Данный параметр сервера позволяет управлять **проверкой подлинности автономной базы данных**.</span><span class="sxs-lookup"><span data-stu-id="e8380-104">This server option allows you to control **contained database authentication**.</span></span>  
  
-   <span data-ttu-id="e8380-105">Если **проверка подлинности автономной базы данных** в экземпляре выключена (0), автономные базы нельзя создавать или присоединять к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8380-105">When **contained database authentication** is off (0) for the instance, contained databases cannot be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="e8380-106">Если **проверка подлинности автономной базы данных** в экземпляре включена (1), автономные базы можно создавать или присоединять к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8380-106">When **contained database authentication** is on (1) for the instance, contained databases can be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="e8380-107">Автономная база данных содержит все параметры базы данных и метаданные, необходимые для определения базы данных, и не зависит от экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , где установлена базы данных.</span><span class="sxs-lookup"><span data-stu-id="e8380-107">A contained database includes all database settings and metadata required to define the database and has no configuration dependencies on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] where the database is installed.</span></span> <span data-ttu-id="e8380-108">Пользователи могут соединяться с базой данных без проверки подлинности имени входа на уровне компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8380-108">Users can connect to the database without authenticating a login at the [!INCLUDE[ssDE](../../includes/ssde-md.md)] level.</span></span> <span data-ttu-id="e8380-109">Если изолировать базу данных от компонента Database Engine, будет легко переместить эту базу данных на другой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8380-109">Isolating the database from the Database Engine makes it possible to easily move the database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e8380-110">Помещение всех параметров базы данных внутрь базы данных позволяет ее владельцу управлять всеми параметрами для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="e8380-110">Including all the database settings in the database enables database owners to manage all the configuration settings for the database.</span></span> <span data-ttu-id="e8380-111">Дополнительные сведения об автономных базах данных см. в разделе [Автономные базы данных](../../relational-databases/databases/contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e8380-111">For more information about contained databases, see [Contained Databases](../../relational-databases/databases/contained-databases.md).</span></span>  
  
 <span data-ttu-id="e8380-112">Если экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] содержит автономные базы данных, можно установить параметр **contained database authentication** в значение 0 с помощью инструкции **RECONFIGURE WITH OVERRIDE** .</span><span class="sxs-lookup"><span data-stu-id="e8380-112">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has any contained databases the **contained database authentication** setting can be set to 0 by using the **RECONFIGURE WITH OVERRIDE** statement.</span></span> <span data-ttu-id="e8380-113">Значение параметра **contained database authentication** , равное 0, отключает проверку подлинности автономной базы данных для автономных баз данных.</span><span class="sxs-lookup"><span data-stu-id="e8380-113">Setting **contained database authentication** to 0 will disable contained database authentication for the contained databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8380-114">При включении автономных баз данных базы данных пользователи с разрешением ALTER ANY USER, такие как члены роли базы данных db_owner или db_accessadmin, могут предоставлять доступ к базам данных и таким образом предоставлять доступ к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8380-114">When contained databases are enabled, database users with the ALTER ANY USER permission, such as members of the db_owner and db_accessadmin database roles, can grant access to databases and by doing so, grant access to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e8380-115">Это означает, что управление доступом к серверу больше не принадлежит только членам предопределенной роли сервера sysadmin и securityadmin и входам с разрешениями CONTROL SERVER и ALTER ANY LOGIN на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="e8380-115">This means that control over access to the server is no longer limited to members of the sysadmin and securityadmin fixed server role, and logins with the server level CONTROL SERVER and ALTER ANY LOGIN permission.</span></span> <span data-ttu-id="e8380-116">С использованием автономных баз данных связаны определенные риски.</span><span class="sxs-lookup"><span data-stu-id="e8380-116">Before allowing contained databases, you should understand the risks associated with contained databases.</span></span> <span data-ttu-id="e8380-117">Дополнительные сведения см. в разделе [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e8380-117">For more information, see [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e8380-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="e8380-118">Examples</span></span>  
 <span data-ttu-id="e8380-119">В следующем примере в экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]создаются автономные базы данных.</span><span class="sxs-lookup"><span data-stu-id="e8380-119">The following example enables contained databases on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8380-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8380-120">See Also</span></span>  
 <span data-ttu-id="e8380-121">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e8380-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="e8380-122">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e8380-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 [<span data-ttu-id="e8380-123">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e8380-123">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
