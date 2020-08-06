---
title: MSSQLSERVER_916 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 916 (Database Engine error)
ms.assetid: 73eb6581-99fe-49a5-9b42-e239d7ffe27f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ee67c1e2f67c3c7903c67082ec3793d9d9820061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658753"
---
# <a name="mssqlserver_916"></a><span data-ttu-id="35409-102">MSSQLSERVER_916</span><span class="sxs-lookup"><span data-stu-id="35409-102">MSSQLSERVER_916</span></span>
    
## <a name="details"></a><span data-ttu-id="35409-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="35409-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35409-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="35409-104">Product Name</span></span>|<span data-ttu-id="35409-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="35409-105">SQL Server</span></span>|  
|<span data-ttu-id="35409-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="35409-106">Event ID</span></span>|<span data-ttu-id="35409-107">916</span><span class="sxs-lookup"><span data-stu-id="35409-107">916</span></span>|  
|<span data-ttu-id="35409-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="35409-108">Event Source</span></span>|<span data-ttu-id="35409-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="35409-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="35409-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="35409-110">Component</span></span>|<span data-ttu-id="35409-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="35409-111">SQLEngine</span></span>|  
|<span data-ttu-id="35409-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="35409-112">Symbolic Name</span></span>|<span data-ttu-id="35409-113">NOTUSER</span><span class="sxs-lookup"><span data-stu-id="35409-113">NOTUSER</span></span>|  
|<span data-ttu-id="35409-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="35409-114">Message Text</span></span>|<span data-ttu-id="35409-115">Субъект сервера "%.\*ls" не может получить доступ к базе данных "%.\*ls" в текущем контексте безопасности.</span><span class="sxs-lookup"><span data-stu-id="35409-115">The server principal "%.\*ls" is not able to access the database "%.\*ls" under the current security context.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="35409-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="35409-116">Explanation</span></span>  
 <span data-ttu-id="35409-117">У имени входа отсутствуют необходимые разрешения для соединения с именованной базой данных.</span><span class="sxs-lookup"><span data-stu-id="35409-117">The login does not have sufficient permissions to connect to the named database.</span></span> <span data-ttu-id="35409-118">Имена входа, которые могут использоваться для подключения к этому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но не имеют специальных разрешений в базе данных, получают разрешения пользователя guest.</span><span class="sxs-lookup"><span data-stu-id="35409-118">Logins that can connect to this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but that do not have specific permissions in a database receive the permissions of the guest user.</span></span> <span data-ttu-id="35409-119">Это одна из мер безопасности, которая не позволяет пользователям одной базы данных подключаться к другим базам данных, в которых они не имеют прав доступа.</span><span class="sxs-lookup"><span data-stu-id="35409-119">This is a security measure to prevent users in one database from connecting to other databases where they do not have privileges.</span></span> <span data-ttu-id="35409-120">Это сообщение об ошибке отображается, если у пользователя guest отсутствует разрешение CONNECT для подключения к именованной базе данных и свойство доверительных отношений не включено.</span><span class="sxs-lookup"><span data-stu-id="35409-120">This error message can occur when the guest user does not have CONNECT permission to the named database and the trustworthy property is not set.</span></span> <span data-ttu-id="35409-121">Это сообщение об ошибке отображается, если у пользователя guest отсутствует разрешение CONNECT для соединения с именованной базой данных.</span><span class="sxs-lookup"><span data-stu-id="35409-121">This error message can occur when the guest user does not have CONNECT permission to the named database.</span></span>  
  
 <span data-ttu-id="35409-122">Если разрешение CONNECT для подключения к базе данных msdb не предоставлено или отозвано, такая ошибка может произойти в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] при попытке обозревателя объектов отобразить состояние управления на основе политик для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="35409-122">When CONNECT permission to the msdb database is denied or revoked, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] can receive this error when Object Explorer tries to show the Policy Based Management status of each database.</span></span> <span data-ttu-id="35409-123">Обозреватель объектов использует разрешения текущего имени для входа, чтобы получить эту информацию из базы данных msdb, что и вызывает указанную ошибку.</span><span class="sxs-lookup"><span data-stu-id="35409-123">Object Explorer uses the permissions of the current login to query the msdb database for this information, which causes the error.</span></span> <span data-ttu-id="35409-124">Также отображается следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="35409-124">The following error message also occurs:</span></span>  
  
 <span data-ttu-id="35409-125">Ошибка при получении данных по этому запросу.</span><span class="sxs-lookup"><span data-stu-id="35409-125">Failed to retrieve data for this request.</span></span> <span data-ttu-id="35409-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span><span class="sxs-lookup"><span data-stu-id="35409-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35409-127">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="35409-127">User Action</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="35409-128">Прежде чем обойти эту меру безопасности, необходимо достичь четкого понимания того, какие пользователи проходят проверку в различных базах данных.</span><span class="sxs-lookup"><span data-stu-id="35409-128">Before circumventing this security measure be sure to have a clear understanding of users are authenticated in various databases.</span></span> <span data-ttu-id="35409-129">Следующие методы могут позволить пользователям, имеющим разрешения в одной базе данных, подключаться к другим базам данных, в результате чего доступ к данным может получить злонамеренный пользователь.</span><span class="sxs-lookup"><span data-stu-id="35409-129">The following methods may allow users that have permissions in one database to connect to other databases which could expose data to a malicious user.</span></span> <span data-ttu-id="35409-130">Если автономные базы данных включены, владельцы этих баз данных могут выполнить следующие шаги в одной базе данных, чтобы предоставить доступ к другой базе данных на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35409-130">When contained databases are enabled, the following steps can allow database owners in one database to grant access to other database on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="35409-131">Можно подключиться к базе данных одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="35409-131">You can connect to the database in one of the following ways:</span></span>  
  
-   <span data-ttu-id="35409-132">Предоставить имени входа специальный доступ к указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="35409-132">Grant the specific login access to the named database.</span></span> <span data-ttu-id="35409-133">В следующем примере предоставляется разрешение для имени входа для доступа `Adventure-Works\Larry` к базе данных `msdb`.</span><span class="sxs-lookup"><span data-stu-id="35409-133">The following example grants the login `Adventure-Works\Larry` access to the `msdb` database.</span></span>  
  
     <span data-ttu-id="35409-134">USE msdb;</span><span class="sxs-lookup"><span data-stu-id="35409-134">USE msdb ;</span></span>  
  
     <span data-ttu-id="35409-135">GO</span><span class="sxs-lookup"><span data-stu-id="35409-135">GO</span></span>  
  
     <span data-ttu-id="35409-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span><span class="sxs-lookup"><span data-stu-id="35409-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span></span>  
  
-   <span data-ttu-id="35409-137">Предоставить для пользователя guest разрешение CONNECT для базы данных, указанной в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="35409-137">Grant the CONNECT permission to the database named in the error message for the guest user.</span></span> <span data-ttu-id="35409-138">В следующем примере пользователю `CONNECT` предоставляется разрешение `msdb` для базы данных `guest`.</span><span class="sxs-lookup"><span data-stu-id="35409-138">The following example grants the `CONNECT` permission to the `msdb` database for the user `guest`.</span></span>  
  
     <span data-ttu-id="35409-139">USE msdb;</span><span class="sxs-lookup"><span data-stu-id="35409-139">USE msdb ;</span></span>  
  
     <span data-ttu-id="35409-140">GO</span><span class="sxs-lookup"><span data-stu-id="35409-140">GO</span></span>  
  
     <span data-ttu-id="35409-141">GRANT CONNECT TO guest ;</span><span class="sxs-lookup"><span data-stu-id="35409-141">GRANT CONNECT TO guest ;</span></span>  
  
-   <span data-ttu-id="35409-142">Включите свойство TRUSTWORTHY в базе данных, применительно к которой прошел проверку пользователь.</span><span class="sxs-lookup"><span data-stu-id="35409-142">Enable the TRUSTWORTHY property on the database that has authenticated the user.</span></span>  
  
     `ALTER DATABASE AdventureWorks SET TRUSTWORTHY ON;`  
  
  
