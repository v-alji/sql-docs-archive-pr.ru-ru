---
title: Сетевой доступ к конечной точке зеркального отображения базы данных
description: Узнайте, как разрешить сетевому аусентикатино Windows доступ к конечной точке зеркального отображения базы данных для SQL Server.
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 28c8fec5-5feb-4c84-8d72-f2bd1ae3b40d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d1d8786d128ef2cc99fe571e33f89c4c4e7699c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666730"
---
# <a name="allow-network-access-to-a-database-mirroring-endpoint-using-windows-authentication-sql-server"></a><span data-ttu-id="265ea-103">Разрешение сетевого доступа к конечной точке зеркального отображения базы данных с использованием проверки подлинности Windows (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="265ea-103">Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication (SQL Server)</span></span>
  <span data-ttu-id="265ea-104">При проверке подлинности Windows для соединения с конечными точками зеркального отображения базы данных двух экземпляров [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] необходимо вручную задать учетные записи для входа с учетом следующих факторов.</span><span class="sxs-lookup"><span data-stu-id="265ea-104">Using Windows Authentication for connecting the database mirroring endpoints of two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requires manual configuration of login accounts under the following conditions:</span></span>  
  
-   <span data-ttu-id="265ea-105">Если экземпляры [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] выполняются как службы под разными учетными записями домена (одного или других доверенных доменов), нужно создать имя входа для каждой учетной записи в базе данных **master** на каждом удаленном экземпляре сервера и предоставить этому имени входа разрешение CONNECT для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="265ea-105">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as services under different domain accounts (in the same or trusted domains), the login of each account must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span>  
  
-   <span data-ttu-id="265ea-106">Если экземпляры [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] выполняются как учетные записи сетевой службы, нужно создать в базе данных **master** на каждом из удаленных экземпляров серверов имя входа для каждой учетной записи главного компьютера (*имя_домена***\\***имя_компьютера$* ) и предоставить этому имени входа разрешение CONNECT для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="265ea-106">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as the Network Service account, the login of the each host computer account (*DomainName***\\***ComputerName$*) must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span> <span data-ttu-id="265ea-107">Это обусловлено тем, что экземпляр сервера, выполняемый под учетной записью Network Service, выполняет проверку подлинности с помощью учетной записи домена главного компьютера.</span><span class="sxs-lookup"><span data-stu-id="265ea-107">This is because a server instance running under the Network Service account authenticates using the domain account of the host computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="265ea-108">Убедитесь, что конечная точка существует для каждого из экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="265ea-108">Ensure that an endpoint exists for each of the server instances.</span></span> <span data-ttu-id="265ea-109">Дополнительные сведения см. в разделе [Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="265ea-109">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
### <a name="to-configure-logins-for-windows-authentication"></a><span data-ttu-id="265ea-110">Настройка имен входа для проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="265ea-110">To configure logins for Windows Authentication</span></span>  
  
1.  <span data-ttu-id="265ea-111">Для учетной записи пользователя каждого экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]создайте имя входа в других экземплярах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="265ea-111">For the user account of each instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], create a login on the other instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="265ea-112">Выполняйте инструкцию [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) с предложением FROM WINDOWS.</span><span class="sxs-lookup"><span data-stu-id="265ea-112">Use a [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) statement with the FROM WINDOWS clause.</span></span>  
  
     <span data-ttu-id="265ea-113">Дополнительные сведения см. в разделе [Создание имени входа](../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="265ea-113">For more information, see [Create a Login](../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
2.  <span data-ttu-id="265ea-114">Кроме того, чтобы выполнивший вход пользователь гарантированно имел доступ к конечной точке, предоставьте имени входа разрешения на соединение с конечной точкой с помощью инструкции [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="265ea-114">Also, to ensure that the login user has access to the endpoint, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement to grant connect permissions on the endpoint to the login.</span></span> <span data-ttu-id="265ea-115">Обратите внимание, что разрешения на подключение к конечной точке предоставлять не требуется, если пользователь является администратором.</span><span class="sxs-lookup"><span data-stu-id="265ea-115">Note that granting connect permissions to the endpoint is unnecessary if the user is an Administrator.</span></span>  
  
     <span data-ttu-id="265ea-116">Дополнительные сведения см. в статье [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="265ea-116">For more information, see [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="265ea-117">Пример</span><span class="sxs-lookup"><span data-stu-id="265ea-117">Example</span></span>  
 <span data-ttu-id="265ea-118">В следующем примере [!INCLUDE[tsql](../includes/tsql-md.md)] создается имя входа [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для учетной записи пользователя `Otheruser` , которая принадлежит домену `Adomain`.</span><span class="sxs-lookup"><span data-stu-id="265ea-118">The following [!INCLUDE[tsql](../includes/tsql-md.md)] example creates a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login for a user account named `Otheruser` that belongs to a domain called `Adomain`.</span></span> <span data-ttu-id="265ea-119">Затем пользователю предоставляются разрешения на подключение к существующей конечной точке зеркального отображения базы данных `Mirroring_Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="265ea-119">The example then grants this user connect permissions to a pre-existing database mirroring endpoint named `Mirroring_Endpoint`.</span></span>  
  
```  
USE master;  
GO  
CREATE LOGIN [Adomain\Otheruser] FROM WINDOWS;  
GO  
GRANT CONNECT on ENDPOINT::Mirroring_Endpoint TO [Adomain\Otheruser];  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="265ea-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="265ea-120">See Also</span></span>  
 <span data-ttu-id="265ea-121">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="265ea-121">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="265ea-122">[Зеркальное отображение базы данных (SQL Server)](database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="265ea-122">[Database Mirroring &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="265ea-123">[Безопасность транспорта для зеркального отображения базы данных и группы доступности AlwaysOn &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="265ea-123">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span></span>  
 [<span data-ttu-id="265ea-124">Конечная точка зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="265ea-124">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
  
  
