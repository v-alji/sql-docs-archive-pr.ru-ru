---
title: Добавление следящего сервера для зеркального отображения базы данных с использованием проверки подлинности Windows (язык Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- Windows authentication [SQL Server]
- database mirroring [SQL Server], witness
ms.assetid: bf5e87df-91a4-49f9-ae88-2a6dcf644510
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 88684c3a1ca12ea579859759ed804ca281647fa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657302"
---
# <a name="add-a-database-mirroring-witness-using-windows-authentication-transact-sql"></a><span data-ttu-id="86e62-102">Добавление следящего сервера для зеркального отображения базы данных с использованием проверки подлинности Windows (язык Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="86e62-102">Add a Database Mirroring Witness Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="86e62-103">Чтобы настроить следящий сервер для базы данных, ее владелец назначает экземпляру компонента Database Engine роль следящего сервера.</span><span class="sxs-lookup"><span data-stu-id="86e62-103">To set up a witness for a database, the database owner assigns a Database Engine instance to the role of witness server.</span></span> <span data-ttu-id="86e62-104">Экземпляр следящего сервера может быть запущен на том же компьютере, что и экземпляры основного или зеркального серверов, но это значительно уменьшает надежность автоматической отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="86e62-104">The witness server instance can run on the same computer as the principal or mirror server instance, but this substantially reduces the robustness of automatic failover.</span></span>  
  
 <span data-ttu-id="86e62-105">Настоятельно рекомендуется размещать следящий сервер на отдельном компьютере.</span><span class="sxs-lookup"><span data-stu-id="86e62-105">We strongly recommend that the witness reside on a separate computer.</span></span> <span data-ttu-id="86e62-106">Указанный сервер может быть задействован в нескольких одновременных сеансах зеркального отображения базы данных с одними и теми же или разными участниками.</span><span class="sxs-lookup"><span data-stu-id="86e62-106">A given server can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="86e62-107">В некоторых сеансах указанный сервер может быть участником, в некоторых — следящим сервером.</span><span class="sxs-lookup"><span data-stu-id="86e62-107">A given server can be a partner in some sessions and a witness in other sessions.</span></span>  
  
 <span data-ttu-id="86e62-108">Следящий сервер предназначен исключительно для режима высокой надежности с автоматической отработкой отказа.</span><span class="sxs-lookup"><span data-stu-id="86e62-108">The witness is intended exclusively for high-safety mode with automatic failover.</span></span> <span data-ttu-id="86e62-109">Перед установкой следящего сервера настоятельно рекомендуется убедиться, что для свойства SAFETY установлено значение FULL.</span><span class="sxs-lookup"><span data-stu-id="86e62-109">Before you set a witness, we strongly recommend that you ensure that the SAFETY property is currently set to FULL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="86e62-110">Настройку зеркального отображения базы данных рекомендуется выполнять в часы с наименьшей загрузкой, поскольку этот процесс может оказать влияние на производительность.</span><span class="sxs-lookup"><span data-stu-id="86e62-110">We recommend that you configure database mirroring during off-peak hours because configuration can impact performance.</span></span>  
  
### <a name="to-establish-a-witness"></a><span data-ttu-id="86e62-111">Настройка следящего сервера</span><span class="sxs-lookup"><span data-stu-id="86e62-111">To establish a witness</span></span>  
  
1.  <span data-ttu-id="86e62-112">Убедитесь, что на экземпляре следящего сервера существует конечная точка зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="86e62-112">On the witness server instance, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="86e62-113">Независимо от числа сеансов зеркального отображения, которые будут поддерживаться, на экземпляре сервера должна быть только одна конечная точка зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="86e62-113">Regardless of the number of mirroring session to be supported, the server instance must have only one database mirroring endpoint.</span></span> <span data-ttu-id="86e62-114">Если вы планируете использовать этот экземпляр сервера исключительно в качестве следящего сервера в сеансах зеркального отображения базы данных, назначьте роль следящего сервера конечной точке ( **=** следящий сервер роли).</span><span class="sxs-lookup"><span data-stu-id="86e62-114">If you intend to use this server instance exclusively as a witness in database mirroring sessions, assign the role of witness to the endpoint (ROLE **=** WITNESS).</span></span> <span data-ttu-id="86e62-115">Если экземпляр данного сервера может выступать как участник одного или несколько сеансов зеркального отображения, назначьте конечной точке роль ALL.</span><span class="sxs-lookup"><span data-stu-id="86e62-115">If you intend to use this server instance as a partner in one or more other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="86e62-116">Чтобы выполнить инструкцию SET WITNESS, нужно сначала открыть сеанс зеркального отображения базы данных (между партнерами), а состоянием конечной точки следящего сервера должно быть STARTED.</span><span class="sxs-lookup"><span data-stu-id="86e62-116">To execute a SET WITNESS statement, the database mirroring session must already be started (between the partners), and the STATE of the endpoint of the witness must be set to STARTED.</span></span>  
  
     <span data-ttu-id="86e62-117">Чтобы определить, есть ли на экземпляре следящего сервера конечная точка зеркального отображения его базы данных, а также узнать ее роль и состояние, выполните следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="86e62-117">To learn whether the witness server instance has its database mirroring endpoint and to learn its role and state, on that instance, use the following Transact-SQL statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="86e62-118">Если конечная точка зеркального отображения базы данных существует и уже используется, рекомендуется использовать эту конечную точку для каждого сеанса экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="86e62-118">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="86e62-119">Удаление используемой конечной точки разрушает связь существующих сеансов.</span><span class="sxs-lookup"><span data-stu-id="86e62-119">Dropping an in-use endpoint disrupts the connections of the existing sessions.</span></span> <span data-ttu-id="86e62-120">Если для сеанса указан следящий сервер, удаление конечной точки зеркального отображения базы данных может привести к тому, что основной сервер этого сеанса потеряет кворум, вследствие чего база данных будет переведена в режим «вне сети» и ее пользователи будут отключены.</span><span class="sxs-lookup"><span data-stu-id="86e62-120">If a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="86e62-121">Дополнительные сведения см. в статье [Кворум. Как следящий сервер влияет на доступность базы данных &#40;зеркальное отображение базы данных&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="86e62-121">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="86e62-122">Если конечная точка на следящем сервере отсутствует, см. раздел [Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="86e62-122">If the witness lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="86e62-123">Если экземпляры участников запущены от имени пользователей других доменов, создайте имя входа для разных учетных записей в базе данных master каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="86e62-123">If the partner instances are running under different domain user accounts, create a login for the different accounts in the master database of each instance.</span></span> <span data-ttu-id="86e62-124">Дополнительные сведения см. в разделе [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="86e62-124">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="86e62-125">Подключите следящий сервер к основному, выполнив следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="86e62-125">Connect to the principal server and issue the following statement:</span></span>  
  
     <span data-ttu-id="86e62-126">ALTER DATABASE *<database_name>* SET следящи **=** _<server_network_address>_</span><span class="sxs-lookup"><span data-stu-id="86e62-126">ALTER DATABASE *<database_name>* SET WITNESS **=** _<server_network_address>_</span></span>  
  
     <span data-ttu-id="86e62-127">Здесь *<имя_базы_данных>*  — имя базы данных, подлежащей зеркальному отображению (это имя является одинаковым в обоих партнерах), а *<сетевой_адрес_сервера>*  — сетевой адрес экземпляра следящего сервера.</span><span class="sxs-lookup"><span data-stu-id="86e62-127">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the witness server instance.</span></span>  
  
     <span data-ttu-id="86e62-128">Чтобы указать сетевой адрес сервера, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="86e62-128">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="86e62-129">TCP **://** \<_system-address> _**:**\<*port>\*</span><span class="sxs-lookup"><span data-stu-id="86e62-129">TCP **://**\<_system-address>_**:**\<*port>\*</span></span>  
  
     <span data-ttu-id="86e62-130">где \<*system-address>* — строка, однозначно идентифицирующая целевой компьютер, а \<*port>* — номер порта, используемого конечной точкой зеркального отображения экземпляра сервера-участника.</span><span class="sxs-lookup"><span data-stu-id="86e62-130">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="86e62-131">Дополнительные сведения см. в разделе [Указание сетевого адреса сервера (зеркальное отображение базы данных)](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="86e62-131">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="86e62-132">Например, на экземпляре основного сервера следующая инструкция ALTER DATABASE установит следящий сервер.</span><span class="sxs-lookup"><span data-stu-id="86e62-132">For example, on the principal server instance, the following ALTER DATABASE statement sets the witness.</span></span> <span data-ttu-id="86e62-133">Имя базы данных — **AdventureWorks**, адрес системы — DBSERVER3 (имя следящей системы), а порт, используемый конечной точкой зеркального отображения базы данных на следящем сервере, — `7022`:</span><span class="sxs-lookup"><span data-stu-id="86e62-133">The database name is **AdventureWorks**, the system address is DBSERVER3-the name of the witness system, and the port used by the database mirroring endpoint of the witness is `7022`:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
      SET WITNESS = 'TCP://DBSERVER3:7022'  
    ```  
  
## <a name="example"></a><span data-ttu-id="86e62-134">Пример</span><span class="sxs-lookup"><span data-stu-id="86e62-134">Example</span></span>  
 <span data-ttu-id="86e62-135">В следующем примере настраивается следящий сервер зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="86e62-135">The following example establishes a data mirroring witness.</span></span> <span data-ttu-id="86e62-136">На экземпляре следящего сервера (экземпляр по умолчанию на компьютере `WITNESSHOST4`):</span><span class="sxs-lookup"><span data-stu-id="86e62-136">On the witness server instance (default instance on `WITNESSHOST4`):</span></span>  
  
1.  <span data-ttu-id="86e62-137">Создайте конечную точку для экземпляра сервера с ролью WITNESS и портом `7022`.</span><span class="sxs-lookup"><span data-stu-id="86e62-137">Create an endpoint for this server instance for the WITNESS role only using port `7022`.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    ```  
  
2.  <span data-ttu-id="86e62-138">Создайте имя входа для учетной записи пользователя домена экземпляров-участников, если они находятся в другом домене, например пусть следящий сервер запущен от имени `SOMEDOMAIN\witnessuser`, а участники — от имени `MYDOMAIN\dbousername`.</span><span class="sxs-lookup"><span data-stu-id="86e62-138">Create a login for domain user account of partner instances, if different; for example, assume that the witness is running as `SOMEDOMAIN\witnessuser`, but the partners are running as `MYDOMAIN\dbousername`.</span></span> <span data-ttu-id="86e62-139">Создайте имя входа для партнеров таким образом:</span><span class="sxs-lookup"><span data-stu-id="86e62-139">Create a login for the partners, as follows:</span></span>  
  
    ```  
    --Create a login for the partner server instances,  
    --which are both running as MYDOMAIN\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [MYDOMAIN\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [MYDOMAIN\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="86e62-140">На каждом экземпляре сервера-участника создайте имя входа для экземпляра следящего сервера:</span><span class="sxs-lookup"><span data-stu-id="86e62-140">On each of the partner server instances, create a login for the witness server instance:</span></span>  
  
    ```  
    --Create a login for the witness server instance,  
    --which is running as SOMEDOMAIN\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [SOMEDOMAIN\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [SOMEDOMAIN\witnessuser];  
    GO  
    ```  
  
4.  <span data-ttu-id="86e62-141">На основном сервере определите следящий сервер (запущенный на компьютере `WITNESSHOST4`):</span><span class="sxs-lookup"><span data-stu-id="86e62-141">On the principal server, set the witness (which is on `WITNESSHOST4`):</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4:7022'  
    GO  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="86e62-142">Сетевой адрес сервера определяет целевой экземпляр сервера по номеру порта, который соответствует конечной точке этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="86e62-142">The server network address indicates the target server instance by the port number, which maps to the mirroring endpoint of the instance.</span></span>  
  
 <span data-ttu-id="86e62-143">Подробный пример настройки зеркального отображения базы данных, в котором показана настройка защиты, подготовка зеркальной базы данных, настройка партнеров и добавление следящего сервера, см. в разделе [Настройка зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="86e62-143">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e62-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="86e62-144">See Also</span></span>  
 <span data-ttu-id="86e62-145">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="86e62-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="86e62-146">[Разрешение сетевого доступа к конечной точке зеркального отображения базы данных с использованием проверки подлинности Windows (SQL Server)](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="86e62-146">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="86e62-147">[Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="86e62-147">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="86e62-148">[Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)](database-mirroring-establish-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="86e62-148">[Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span></span>  
 <span data-ttu-id="86e62-149">[Удаление следящего сервера из сеанса зеркального отображения базы данных (SQL Server)](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="86e62-149">[Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="86e62-150">Следящий сервер зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="86e62-150">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
