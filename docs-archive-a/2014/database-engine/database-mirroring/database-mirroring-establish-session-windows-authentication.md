---
title: Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 143c68a5-589f-4e7f-be59-02707e1a430a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3088333fbfd4babd209df07f8880c838ce626d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655942"
---
# <a name="establish-a-database-mirroring-session-using-windows-authentication-transact-sql"></a><span data-ttu-id="00e5d-102">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="00e5d-102">Establish a Database Mirroring Session Using Windows Authentication (Transact-SQL)</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="00e5d-103">Вместо этого используйте [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00e5d-103">Use [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] instead.</span></span>  
  
 <span data-ttu-id="00e5d-104">После того как зеркальная база данных готова (см. раздел [Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md)), можно установить сеанс зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-104">After the mirror database is prepared (see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), you can establish a database mirroring session.</span></span> <span data-ttu-id="00e5d-105">Экземпляры участника, зеркала и следящего сервера должны быть отдельными экземплярами сервера, расположенными на отдельных системных узлах.</span><span class="sxs-lookup"><span data-stu-id="00e5d-105">The principal, mirror, and witness server instances must be separate server instances, which should be on separate host systems.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="00e5d-106">Настройку зеркального отображения базы данных рекомендуется выполнять в часы с наименьшей загрузкой, поскольку этот процесс может повлиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="00e5d-106">We recommend that you configure database mirroring during off-peak hours because configuring mirroring can impact performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00e5d-107">Указанный экземпляр сервера может быть задействован в нескольких одновременных сеансах зеркального отображения базы данных с одними и теми же или разными участниками.</span><span class="sxs-lookup"><span data-stu-id="00e5d-107">A given server instance can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="00e5d-108">В некоторых сеансах указанный экземпляр сервера может быть участником, в других — следящим сервером.</span><span class="sxs-lookup"><span data-stu-id="00e5d-108">A server instance can be a partner in some sessions and a witness in other sessions.</span></span> <span data-ttu-id="00e5d-109">На экземпляре зеркального сервера должен работать тот же выпуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , что и на экземпляре основного сервера.</span><span class="sxs-lookup"><span data-stu-id="00e5d-109">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the principal server instance.</span></span> <span data-ttu-id="00e5d-110">Зеркальное отображение баз данных поддерживается не во всех выпусках [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00e5d-110">Database mirroring is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00e5d-111">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="00e5d-112">Кроме того, настоятельно рекомендуется размещать серверы в системах со сравнимой производительностью, которые могут справляться с одинаковой рабочей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="00e5d-112">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
### <a name="to-establish-a-database-mirroring-session"></a><span data-ttu-id="00e5d-113">Установка сеанса зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="00e5d-113">To establish a database mirroring session</span></span>  
  
1.  <span data-ttu-id="00e5d-114">Создайте зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-114">Create the mirror database.</span></span> <span data-ttu-id="00e5d-115">Дополнительные сведения см. в статье [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-115">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="00e5d-116">Настройка безопасности на каждом из экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="00e5d-116">Set up security on each server instance.</span></span>  
  
     <span data-ttu-id="00e5d-117">В сеансе зеркального отображения базы данных каждому экземпляру сервера требуется конечная точка зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-117">Each server instance in a database mirroring session requires a database mirroring endpoint.</span></span> <span data-ttu-id="00e5d-118">Если конечная точка отсутствует, ее необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="00e5d-118">If the endpoint does not exist, you must create it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00e5d-119">Метод проверки подлинности, применяемый экземпляром сервера при зеркальном отображении базы данных, является свойством его конечной точки зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-119">The form of authentication used for database mirroring by a server instance is a property of its database mirroring endpoint.</span></span> <span data-ttu-id="00e5d-120">Для зеркального отображения базы данных доступны два типа защиты транспорта: проверка подлинности Windows или проверка подлинности на основе сертификата.</span><span class="sxs-lookup"><span data-stu-id="00e5d-120">Two types of transport security are available for database mirroring: Windows Authentication or certificate-based authentication.</span></span> <span data-ttu-id="00e5d-121">Дополнительные сведения см. в разделе [Безопасность транспорта для зеркального отображения базы данных и группы доступности AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-121">For more information, see [Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span></span>  
  
     <span data-ttu-id="00e5d-122">На каждом сервере-партнере убедитесь, что конечная точка существует для зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-122">On each partner server, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="00e5d-123">Независимо от поддерживаемого количества сеансов зеркального отображения экземпляр сервера может иметь только одну конечную точку зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-123">Regardless of the number of mirroring sessions to be supported, the server instance can have only one database mirroring endpoint.</span></span> <span data-ttu-id="00e5d-124">Если этот экземпляр сервера будет использоваться исключительно для участников сеансов зеркального отображения базы данных, можно присвоить роль участника конечной точке (ROLE **=** PARTNER).</span><span class="sxs-lookup"><span data-stu-id="00e5d-124">If you intend to use this server instance exclusively for partners in database mirroring sessions, you can assign the role of partner to the endpoint (ROLE**=** PARTNER).</span></span> <span data-ttu-id="00e5d-125">Если этот сервер будет использоваться также в качестве следящего сервера в других сеансах зеркального отображения базы данных, присвойте роли конечной точки значение ALL.</span><span class="sxs-lookup"><span data-stu-id="00e5d-125">If you intend also to use this server for the witness in other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="00e5d-126">Для выполнения инструкции SET PARTNER требуется, чтобы параметры STATE конечных точек обоих участников имели значение STARTED.</span><span class="sxs-lookup"><span data-stu-id="00e5d-126">To execute a SET PARTNER statement, the STATE of the endpoints of both partners must be set to STARTED.</span></span>  
  
     <span data-ttu-id="00e5d-127">Чтобы узнать, имеет ли экземпляр сервера конечную точку зеркального отображения базы данных, а также узнать ее роль и состояние на этом экземпляре, используйте следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="00e5d-127">To learn whether a server instance has a database mirroring endpoint and to learn its role and state, on that instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="00e5d-128">Не изменяйте конфигурацию используемой конечной точки зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-128">Do not reconfigure an in-use database mirroring endpoint.</span></span> <span data-ttu-id="00e5d-129">Если конечная точка зеркального отображения базы данных существует и уже используется, рекомендуется использовать эту конечную точку для каждого сеанса экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="00e5d-129">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="00e5d-130">Удаление используемой конечной точки приведет к перезапуску конечной точки, завершению всех соединений всех существующих сеансов, что может привести к ошибке для других экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="00e5d-130">Dropping an in-use endpoint can cause the endpoint to restart, disrupting the connections of the existing sessions, which can appear to be an error to the other server instances.</span></span> <span data-ttu-id="00e5d-131">Это является особо важным в режиме повышенной безопасности с автоматической отработкой отказа. В данном режиме изменение конфигурации конечной точки участника может привести к выполнению отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="00e5d-131">This is particularly important in high-safety mode with automatic failover, in which reconfiguring the endpoint on a partner could cause a failover to occur.</span></span> <span data-ttu-id="00e5d-132">Если для сеанса указан следящий сервер, удаление конечных точек зеркального отображения базы данных может привести к тому, что основной сервер потеряет кворум, поэтому база данных будет переведена в режим «вне сети» и ее пользователи будут отключены.</span><span class="sxs-lookup"><span data-stu-id="00e5d-132">Also, if a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="00e5d-133">Дополнительные сведения см. в статье [Кворум. Как следящий сервер влияет на доступность базы данных &#40;зеркальное отображение базы данных&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-133">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="00e5d-134">Если каждый участник нуждается в конечной точке, см. раздел [Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-134">If either partner lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
3.  <span data-ttu-id="00e5d-135">Если экземпляры участников запущены под другими учетными записями пользователей домена, для каждой требуется имя входа в базе данных **master** .</span><span class="sxs-lookup"><span data-stu-id="00e5d-135">If server instances are running under different domain user accounts, each requires a login in the **master** database of the others.</span></span> <span data-ttu-id="00e5d-136">Если имя входа отсутствует, его необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="00e5d-136">If the login does not exist, you must create it.</span></span> <span data-ttu-id="00e5d-137">Дополнительные сведения см. в разделе [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-137">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
4.  <span data-ttu-id="00e5d-138">Для установка основного сервера в качестве участника на зеркальной базе данных, подключитесь к зеркальному серверу и выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="00e5d-138">To set the principal server as partner on the mirror database, connect to the mirror server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="00e5d-139">ALTER DATABASE *<имя_базы_данных>* SET PARTNER **=**_<сетевой_адрес_сервера>_</span><span class="sxs-lookup"><span data-stu-id="00e5d-139">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="00e5d-140">здесь *<имя_базы_данных>*  — имя базы данных, подлежащей зеркальному отображению (это имя является одинаковым на обоих участниках), а *<сетевой_адрес_сервера>*  — сетевой адрес основного сервера.</span><span class="sxs-lookup"><span data-stu-id="00e5d-140">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the principal server.</span></span>  
  
     <span data-ttu-id="00e5d-141">Чтобы указать сетевой адрес сервера, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="00e5d-141">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="00e5d-142">TCP<strong>://</strong> \<*system-address> \*<strong>:</strong> \<*port> \*</span><span class="sxs-lookup"><span data-stu-id="00e5d-142">TCP<strong>://</strong>\<*system-address>*<strong>:</strong>\<*port>*</span></span>  
  
     <span data-ttu-id="00e5d-143">где \<*system-address>* — строка, однозначно идентифицирующая целевой компьютер, а \<*port>* — номер порта, используемого конечной точкой зеркального отображения экземпляра сервера-участника.</span><span class="sxs-lookup"><span data-stu-id="00e5d-143">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="00e5d-144">Дополнительные сведения см. в разделе [Указание сетевого адреса сервера (зеркальное отображение базы данных)](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-144">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="00e5d-145">Например, на экземпляре зеркального сервера следующая инструкция ALTER DATABASE устанавливает участника в качестве исходного экземпляра основного сервера:</span><span class="sxs-lookup"><span data-stu-id="00e5d-145">For example, on the mirror server instance, the following ALTER DATABASE statement sets the partner as the original principal server instance.</span></span> <span data-ttu-id="00e5d-146">Имя базы данных — **AdventureWorks**, системный адрес — DBSERVER1 (имя системы участника), а 7022 — порт, используемый конечной точкой зеркального отображения базы данных участника:</span><span class="sxs-lookup"><span data-stu-id="00e5d-146">The database name is **AdventureWorks**, the system address is DBSERVER1-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7022:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
       SET PARTNER = 'TCP://DBSERVER1:7022'  
    ```  
  
     <span data-ttu-id="00e5d-147">Эта инструкция подготавливает зеркальный сервер для формирования сеанса, когда с ним соединяется основной сервер.</span><span class="sxs-lookup"><span data-stu-id="00e5d-147">This statement prepares the mirror server to form a session when it is contacted by the principal server.</span></span>  
  
5.  <span data-ttu-id="00e5d-148">Для установки зеркального сервера в качестве участника на основной базе данных, подключитесь к основному серверу и выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="00e5d-148">To set the mirror server as partner on the principal database, connect to the principal server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="00e5d-149">ALTER DATABASE *<имя_базы_данных>* SET PARTNER **=**_<сетевой_адрес_сервера>_</span><span class="sxs-lookup"><span data-stu-id="00e5d-149">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="00e5d-150">Дополнительные сведения см. в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="00e5d-150">For more information, see step 4.</span></span>  
  
     <span data-ttu-id="00e5d-151">Например, в экземпляре основного сервера следующая инструкция ALTER DATABASE устанавливает участника в качестве исходного экземпляра зеркального сервера:</span><span class="sxs-lookup"><span data-stu-id="00e5d-151">For example, on the principal server instance, the following ALTER DATABASE statement sets the partner as the original mirror server instance.</span></span> <span data-ttu-id="00e5d-152">Имя базы данных — **AdventureWorks**, системный адрес — DBSERVER2 (имя системы участника), а 7025 — порт, используемый конечной точкой зеркального отображения базы данных участника:</span><span class="sxs-lookup"><span data-stu-id="00e5d-152">The database name is **AdventureWorks**, the system address is DBSERVER2-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7025:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks SET PARTNER = 'TCP://DBSERVER2:7022'  
    ```  
  
     <span data-ttu-id="00e5d-153">Ввод этой инструкции на основном сервере начинает сеанс зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-153">Entering this statement on the principal server begins the database mirroring session.</span></span>  
  
6.  <span data-ttu-id="00e5d-154">По умолчанию сеанс установлен в состояние полной безопасности транзакций (параметр SAFETY установлен в FULL), что способствует запуску сеанса в синхронном, высокого уровня защиты режиме без автоматической отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="00e5d-154">By default a session is set to full transaction safety (SAFETY is set to FULL), which starts the session in synchronous, high-safety mode without automatic failover.</span></span> <span data-ttu-id="00e5d-155">Можно перенастроить сеанс для выполнения либо в режиме высокого уровня защиты с автоматической отработкой отказа, либо в асинхронном режиме высокого уровня производительности, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="00e5d-155">You can reconfigure the session to run in high-safety mode with automatic failover or in asynchronous, high-performance mode, as follows:</span></span>  
  
    -   <span data-ttu-id="00e5d-156">**Режим высокого уровня защиты с автоматической отработкой отказа**</span><span class="sxs-lookup"><span data-stu-id="00e5d-156">**High-safety mode with automatic failover**</span></span>  
  
         <span data-ttu-id="00e5d-157">Чтобы сеанс высокого уровня защиты поддерживал автоматическую отработку отказа, добавьте экземпляр следящего сервера.</span><span class="sxs-lookup"><span data-stu-id="00e5d-157">If you want a high-safety mode session to support automatic failover, add a witness server instance.</span></span> <span data-ttu-id="00e5d-158">Дополнительные сведения см. в разделе [Добавление следящего сервера для зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-158">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
    -   <span data-ttu-id="00e5d-159">**Высокопроизводительный режим**</span><span class="sxs-lookup"><span data-stu-id="00e5d-159">**High-performance mode**</span></span>  
  
         <span data-ttu-id="00e5d-160">С другой стороны, если автоматическая отработка отказа нежелательна или важней производительность, а не высокий уровень доступности, можно выключить безопасность транзакций.</span><span class="sxs-lookup"><span data-stu-id="00e5d-160">Alternatively, if you do not want automatic failover and you prefer to emphasize performance over availability, turn off transaction safety.</span></span> <span data-ttu-id="00e5d-161">Дополнительные сведения см. в разделе [Изменение безопасности транзакций в сеансах зеркального отображения базы данных (Transact-SQL)](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-161">For more information, see [Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="00e5d-162">В высокопроизводительном режиме параметр WITNESS должен быть установлен в OFF.</span><span class="sxs-lookup"><span data-stu-id="00e5d-162">In high-performance mode, WITNESS should be set to OFF.</span></span> <span data-ttu-id="00e5d-163">Дополнительные сведения см. в статье [Кворум. Как следящий сервер влияет на доступность базы данных &#40;зеркальное отображение базы данных&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-163">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00e5d-164">Пример</span><span class="sxs-lookup"><span data-stu-id="00e5d-164">Example</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00e5d-165">Следующий пример устанавливает сеанс зеркального отображения базы данных между участниками для существующей зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-165">The following example establishes a database mirroring session between partners for an existing mirror database.</span></span> <span data-ttu-id="00e5d-166">Дополнительные сведения о создании зеркальной базы данных см. в разделе [Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-166">For information on creating a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)=.</span></span>  
  
 <span data-ttu-id="00e5d-167">Пример показывает основные шаги для создания сеанса зеркального отображения базы данных без следящего сервера.</span><span class="sxs-lookup"><span data-stu-id="00e5d-167">The example shows the basic steps for creating a database mirroring session without a witness.</span></span> <span data-ttu-id="00e5d-168">Эти два участника являются экземплярами сервера по умолчанию на двух компьютерных системах (PARTNERHOST1 и PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="00e5d-168">The two partners are the default server instances on two computer systems (PARTNERHOST1 and PARTNERHOST5).</span></span> <span data-ttu-id="00e5d-169">Оба экземпляра-участника выполняются под одной и той же учетной записью пользователя домена Windows (MYDOMAIN\dbousername).</span><span class="sxs-lookup"><span data-stu-id="00e5d-169">The two partner instances run the same Windows domain user account (MYDOMAIN\dbousername).</span></span>  
  
1.  <span data-ttu-id="00e5d-170">На экземпляре основного сервера (экземпляр по умолчанию на PARTNERHOST1) создается конечная точка, которая поддерживает все роли, используя порт 7022:</span><span class="sxs-lookup"><span data-stu-id="00e5d-170">On the principal server instance (default instance on PARTNERHOST1), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="00e5d-171">Пример настройки имени входа см. в разделе [Разрешение сетевого доступа к конечной точке зеркального отображения базы данных с использованием проверки подлинности Windows (SQL Server)](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-171">For an example of how to setup a login, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
2.  <span data-ttu-id="00e5d-172">На экземпляре зеркального сервера (экземпляр по умолчанию на PARTNERHOST5) создается конечная точка, которая поддерживает все роли, используя порт 7022:</span><span class="sxs-lookup"><span data-stu-id="00e5d-172">On the mirror server instance (default instance on PARTNERHOST5), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
3.  <span data-ttu-id="00e5d-173">На экземпляре основного сервера (на PARTNERHOST1) создается резервная копия базы данных:</span><span class="sxs-lookup"><span data-stu-id="00e5d-173">On the principal server instance (on PARTNERHOST1), back up the database:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdvWorks_dbmirror.bak'   
        WITH FORMAT  
    GO  
    ```  
  
4.  <span data-ttu-id="00e5d-174">На экземпляре зеркального сервера (на компьютере `PARTNERHOST5`) восстанавливается база данных:</span><span class="sxs-lookup"><span data-stu-id="00e5d-174">On the mirror server instance (on `PARTNERHOST5`), restore the database:</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks   
        FROM DISK = 'Z:\AdvWorks_dbmirror.bak'   
        WITH NORECOVERY  
    GO  
    ```  
  
5.  <span data-ttu-id="00e5d-175">После того, как полная резервная копия базы данных создана, обязательно создается резервная копия журнала для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="00e5d-175">After you create the full database backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="00e5d-176">В следующем примере с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] создается резервная копия журналов для того же файла, который использовался в предыдущей резервной копии базы данных:</span><span class="sxs-lookup"><span data-stu-id="00e5d-176">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding database backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="00e5d-177">Перед тем как приступать к зеркальному отображению, необходимо применить требуемую резервную копию журналов (и все последующие резервные копии журналов).</span><span class="sxs-lookup"><span data-stu-id="00e5d-177">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="00e5d-178">В следующем примере с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] восстанавливается первый журнал из файла «C:\AdventureWorks.bak»:</span><span class="sxs-lookup"><span data-stu-id="00e5d-178">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from C:\AdventureWorks.bak:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\ AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="00e5d-179">На экземпляре зеркального сервера установите экземпляр сервера на PARTNERHOST1 в качестве участника (делая его исходным основным сервером):</span><span class="sxs-lookup"><span data-stu-id="00e5d-179">On the mirror server instance, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1:7022'  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="00e5d-180">По умолчанию сеанс зеркального отображения базы данных выполняется в синхронном режиме, который зависит от наличия полной безопасности транзакций (параметр SAFETY установлен в FULL).</span><span class="sxs-lookup"><span data-stu-id="00e5d-180">default, a database mirroring session runs in synchronous mode, which depends on having full transaction safety (SAFETY is set to FULL).</span></span> <span data-ttu-id="00e5d-181">Чтобы сеанс выполнялся в асинхронном, высокопроизводительном режиме, установите параметр SAFETY в OFF.</span><span class="sxs-lookup"><span data-stu-id="00e5d-181">To cause a session to run in asynchronous, high-performance mode, set SAFETY to OFF.</span></span> <span data-ttu-id="00e5d-182">Дополнительные сведения см. в статье [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-182">For more information, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
8.  <span data-ttu-id="00e5d-183">На экземпляре основного сервера установите экземпляр сервера на компьютере `PARTNERHOST5` в качестве участника (сделав его исходным зеркальным сервером):</span><span class="sxs-lookup"><span data-stu-id="00e5d-183">On the principal server instance, set the server instance on `PARTNERHOST5` as the partner (making it the initial mirror server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5:7022'  
    GO  
    ```  
  
9. <span data-ttu-id="00e5d-184">Если необходимо использовать режим высокого уровня безопасности с автоматической отработкой отказа, дополнительно установите экземпляр следящего сервера.</span><span class="sxs-lookup"><span data-stu-id="00e5d-184">Optionally, if you intend to use high-safety mode with automatic failover, set up the witness server instance.</span></span> <span data-ttu-id="00e5d-185">Дополнительные сведения см. в разделе [Добавление следящего сервера для зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-185">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00e5d-186">Подробный пример настройки зеркального отображения базы данных, в котором показана настройка защиты, подготовка зеркальной базы данных, настройка партнеров и добавление следящего сервера, см. в разделе [Настройка зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00e5d-186">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e5d-187">См. также:</span><span class="sxs-lookup"><span data-stu-id="00e5d-187">See Also</span></span>  
 <span data-ttu-id="00e5d-188">[Настройка зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-188">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="00e5d-189">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="00e5d-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="00e5d-190">[Разрешение сетевого доступа к конечной точке зеркального отображения базы данных с использованием проверки подлинности Windows (SQL Server)](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-190">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="00e5d-191">[Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-191">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="00e5d-192">[Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-192">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="00e5d-193">[Зеркальное отображение баз данных и доставка журналов (SQL Server)](database-mirroring-and-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-193">[Database Mirroring and Log Shipping &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="00e5d-194">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-194">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="00e5d-195">[Зеркальное отображение и репликация баз данных (SQL Server)](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-195">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="00e5d-196">[Настройка зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-196">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="00e5d-197">[Указание сетевого адреса сервера (зеркальное отображение базы данных)](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="00e5d-197">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 [<span data-ttu-id="00e5d-198">Режимы работы зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="00e5d-198">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
