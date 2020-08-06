---
title: Пример. Настройка зеркального отображения базы данных с помощью сертификатов (язык Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: df489ecd-deee-465c-a26a-6d1bef6d7b66
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea87e2de984107c5a0fda6eb2629ee5cfd197841
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751468"
---
# <a name="example-setting-up-database-mirroring-using-certificates-transact-sql"></a><span data-ttu-id="5cb25-102">Пример Настройка зеркального отображения с помощью сертификатов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5cb25-102">Example: Setting Up Database Mirroring Using Certificates (Transact-SQL)</span></span>
  <span data-ttu-id="5cb25-103">В этом примере описаны все действия, выполняемые при создании сеанса зеркального отображения базы данных с использованием проверки подлинности на основе сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5cb25-103">This example shows all the stages required to create a database mirroring session using certificate-based authentication.</span></span> <span data-ttu-id="5cb25-104">Примеры в этом подразделе используют язык [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cb25-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5cb25-105">За исключением случаев, когда сеть гарантированно защищена, рекомендуется для соединений зеркального отображения базы данных применять шифрование.</span><span class="sxs-lookup"><span data-stu-id="5cb25-105">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="5cb25-106">При копировании сертификата на другую систему используйте безопасный метод копирования.</span><span class="sxs-lookup"><span data-stu-id="5cb25-106">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="5cb25-107">Отнеситесь с особым вниманием к хранению сертификатов в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="5cb25-107">Be extremely careful to keep all of your certificates secure.</span></span>  
  
##  <a name="example"></a><a name="ExampleH2"></a> <span data-ttu-id="5cb25-108">Пример</span><span class="sxs-lookup"><span data-stu-id="5cb25-108">Example</span></span>  
 <span data-ttu-id="5cb25-109">В следующем примере показано, что необходимо сделать на одном участнике, который находится на узле HOST_A.</span><span class="sxs-lookup"><span data-stu-id="5cb25-109">The following example demonstrates what must be done on one partner that resides on HOST_A.</span></span> <span data-ttu-id="5cb25-110">В этом примере два участника являются экземплярами сервера по умолчанию в трех компьютерных системах.</span><span class="sxs-lookup"><span data-stu-id="5cb25-110">In this example, the two partners are the default server instances on three computer systems.</span></span> <span data-ttu-id="5cb25-111">Два экземпляра сервера запущены в ненадежных доменах Windows, поэтому необходима проверка подлинности на основе сертификата.</span><span class="sxs-lookup"><span data-stu-id="5cb25-111">The two server instances run in nontrusted Windows domains, so certificate-based authentication is required.</span></span>  
  
 <span data-ttu-id="5cb25-112">Начальная основная роль принимается узлом HOST_A, а зеркальная роль — узлом HOST_B.</span><span class="sxs-lookup"><span data-stu-id="5cb25-112">The initial principal role is taken by HOST_A, and the mirror role is taken by HOST_B.</span></span>  
  
 <span data-ttu-id="5cb25-113">Настройка зеркального отображения базы данных с помощью сертификатов состоит из четырех основных этапов, три из которых — 1, 2 и 4 — показаны в этом примере.</span><span class="sxs-lookup"><span data-stu-id="5cb25-113">Setting up database mirroring using certificates involves four general stages, of which three stages-1, 2, and 4-are demonstrated by this example.</span></span> <span data-ttu-id="5cb25-114">Ниже приведены эти этапы.</span><span class="sxs-lookup"><span data-stu-id="5cb25-114">These stages are as follows:</span></span>  
  
1.  [<span data-ttu-id="5cb25-115">Настройка исходящих соединений</span><span class="sxs-lookup"><span data-stu-id="5cb25-115">Configuring Outbound Connections</span></span>](#ConfiguringOutboundConnections)  
  
     <span data-ttu-id="5cb25-116">В этом примере приводится пошаговое описание следующих процессов.</span><span class="sxs-lookup"><span data-stu-id="5cb25-116">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="5cb25-117">Настройка узла Host_A для исходящих соединений.</span><span class="sxs-lookup"><span data-stu-id="5cb25-117">Configuring Host_A for outbound connections.</span></span>  
  
    2.  <span data-ttu-id="5cb25-118">Настройка узла Host_B для исходящих соединений.</span><span class="sxs-lookup"><span data-stu-id="5cb25-118">Configuring Host_B for outbound connections.</span></span>  
  
     <span data-ttu-id="5cb25-119">Сведения об этом этапе настройки зеркального отображения базы данных см. в разделе [Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="5cb25-119">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
2.  [<span data-ttu-id="5cb25-120">Настройка входящих соединений</span><span class="sxs-lookup"><span data-stu-id="5cb25-120">Configuring Inbound Connections</span></span>](#ConfigureInboundConnections)  
  
     <span data-ttu-id="5cb25-121">В этом примере приводится пошаговое описание следующих процессов.</span><span class="sxs-lookup"><span data-stu-id="5cb25-121">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="5cb25-122">Настройка узла Host_A для входящих соединений.</span><span class="sxs-lookup"><span data-stu-id="5cb25-122">Configuring Host_A for inbound connections.</span></span>  
  
    2.  <span data-ttu-id="5cb25-123">Настройка узла Host_B для входящих соединений.</span><span class="sxs-lookup"><span data-stu-id="5cb25-123">Configuring Host_B for inbound connections.</span></span>  
  
     <span data-ttu-id="5cb25-124">Сведения об этом этапе настройки зеркального отображения базы данных см. в разделе [Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="5cb25-124">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
3.  <span data-ttu-id="5cb25-125">Создание зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="5cb25-125">Creating the Mirror Database</span></span>  
  
     <span data-ttu-id="5cb25-126">Дополнительные сведения о создании зеркальной базы данных см. в разделе [Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5cb25-126">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
4.  [<span data-ttu-id="5cb25-127">Настройка участников зеркального отображения</span><span class="sxs-lookup"><span data-stu-id="5cb25-127">Configuring the Mirroring Partners</span></span>](#ConfigureMirroringPartners)  
  
###  <a name="configuring-outbound-connections"></a><a name="ConfiguringOutboundConnections"></a> <span data-ttu-id="5cb25-128">Настройка исходящих соединений</span><span class="sxs-lookup"><span data-stu-id="5cb25-128">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="5cb25-129">**Настройка узла Host_A для исходящих соединений**</span><span class="sxs-lookup"><span data-stu-id="5cb25-129">**To configure Host_A for outbound connections**</span></span>  
  
1.  <span data-ttu-id="5cb25-130">При необходимости создайте в базе данных master главный ключ базы данных.</span><span class="sxs-lookup"><span data-stu-id="5cb25-130">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
2.  <span data-ttu-id="5cb25-131">Сделайте сертификат для данного экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="5cb25-131">Make a certificate for this server instance.</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate';  
    GO  
    ```  
  
3.  <span data-ttu-id="5cb25-132">Создайте конечную точку для экземпляра сервера с использованием его сертификата.</span><span class="sxs-lookup"><span data-stu-id="5cb25-132">Create a mirroring endpoint for server instance using the certificate.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_A_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="5cb25-133">Создайте резервную копию сертификата HOST_A и скопируйте ее на другую систему HOST_B.</span><span class="sxs-lookup"><span data-stu-id="5cb25-133">Back up the HOST_A certificate, and copy it to other system, HOST_B.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
5.  <span data-ttu-id="5cb25-134">С помощью безопасного метода скопируйте файл «C:\HOST_A_cert.cer» на узел HOST_B.</span><span class="sxs-lookup"><span data-stu-id="5cb25-134">Using any secure copy method, copy C:\HOST_A_cert.cer to HOST_B.</span></span>  
  
 <span data-ttu-id="5cb25-135">**Настройка узла Host_B для исходящих соединений**</span><span class="sxs-lookup"><span data-stu-id="5cb25-135">**To configure Host_B for outbound connections**</span></span>  
  
1.  <span data-ttu-id="5cb25-136">При необходимости создайте в базе данных master главный ключ базы данных.</span><span class="sxs-lookup"><span data-stu-id="5cb25-136">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
    GO  
    ```  
  
2.  <span data-ttu-id="5cb25-137">Создайте сертификат для экземпляра сервера HOST_B.</span><span class="sxs-lookup"><span data-stu-id="5cb25-137">Make a certificate on the HOST_B server instance.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert   
       WITH SUBJECT = 'HOST_B certificate for database mirroring';  
    GO  
    ```  
  
3.  <span data-ttu-id="5cb25-138">Создайте конечную точку зеркального отображения для экземпляра сервера на узле HOST_B.</span><span class="sxs-lookup"><span data-stu-id="5cb25-138">Create a mirroring endpoint for the server instance on HOST_B.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_B_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="5cb25-139">Создайте резервную копию сертификата HOST_B.</span><span class="sxs-lookup"><span data-stu-id="5cb25-139">Back up HOST_B certificate.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
    GO   
    ```  
  
5.  <span data-ttu-id="5cb25-140">С помощью безопасного метода скопируйте файл «C:\HOST_B_cert.cer» на узел HOST_A.</span><span class="sxs-lookup"><span data-stu-id="5cb25-140">Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.</span></span>  
  
 <span data-ttu-id="5cb25-141">Дополнительные сведения см. в разделе [Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="5cb25-141">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
###  <a name="configuring-inbound-connections"></a><a name="ConfigureInboundConnections"></a> <span data-ttu-id="5cb25-142">Настройка входящих соединений</span><span class="sxs-lookup"><span data-stu-id="5cb25-142">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="5cb25-143">**Настройка узла Host_A для входящих соединений**</span><span class="sxs-lookup"><span data-stu-id="5cb25-143">**To configure Host_A for inbound connections**</span></span>  
  
1.  <span data-ttu-id="5cb25-144">Создайте имя входа на узле HOST_A для узла HOST_B.</span><span class="sxs-lookup"><span data-stu-id="5cb25-144">Create a login on HOST_A for HOST_B.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_B_login WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
2.  <span data-ttu-id="5cb25-145">Создайте пользователя для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="5cb25-145">--Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="5cb25-146">Свяжите сертификат с пользователем.</span><span class="sxs-lookup"><span data-stu-id="5cb25-146">--Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="5cb25-147">Предоставьте данной учетной записи разрешение CONNECT на эту удаленную конечную точку зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="5cb25-147">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
 <span data-ttu-id="5cb25-148">**Настройка узла Host_B для входящих соединений**</span><span class="sxs-lookup"><span data-stu-id="5cb25-148">**To configure Host_B for inbound connections**</span></span>  
  
1.  <span data-ttu-id="5cb25-149">Создайте имя входа на узле HOST_B для узла HOST_A.</span><span class="sxs-lookup"><span data-stu-id="5cb25-149">Create a login on HOST_B for HOST_A.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_A_login WITH PASSWORD = '=Sample#2_Strong_Password2';  
    GO  
    ```  
  
2.  <span data-ttu-id="5cb25-150">Создайте пользователя для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="5cb25-150">Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="5cb25-151">Свяжите сертификат с пользователем.</span><span class="sxs-lookup"><span data-stu-id="5cb25-151">Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_A_cert  
       AUTHORIZATION HOST_A_user  
       FROM FILE = 'C:\HOST_A_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="5cb25-152">Предоставьте данной учетной записи разрешение CONNECT на эту удаленную конечную точку зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="5cb25-152">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_A_login];  
    GO  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5cb25-153">При необходимости запуска в режиме высокого уровня защиты с автоматической отработкой отказа нужно повторить эти шаги установки, чтобы настроить следящий сервер для исходящих и входящих соединений.</span><span class="sxs-lookup"><span data-stu-id="5cb25-153">If you intend to run in high-safety mode with automatic failover, you must repeat the same setup steps to configure the witness for outbound and inbound connections.</span></span> <span data-ttu-id="5cb25-154">При настройке входящих соединений с задействованным следящим сервером необходимо настроить имена входа и пользователей для следящего сервера на обоих участниках и для обоих участников на следящем сервере.</span><span class="sxs-lookup"><span data-stu-id="5cb25-154">Setting up the inbound connections when a witness is involved requires that you set up logins and users for the witness on both of the partners and for both partners on the witness.</span></span>  
  
 <span data-ttu-id="5cb25-155">Дополнительные сведения см. в разделе [Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="5cb25-155">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
### <a name="creating-the-mirror-database"></a><span data-ttu-id="5cb25-156">Создание зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="5cb25-156">Creating the Mirror Database</span></span>  
 <span data-ttu-id="5cb25-157">Дополнительные сведения о создании зеркальной базы данных см. в разделе [Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5cb25-157">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
###  <a name="configuring-the-mirroring-partners"></a><a name="ConfigureMirroringPartners"></a> <span data-ttu-id="5cb25-158">Настройка участников зеркального отображения</span><span class="sxs-lookup"><span data-stu-id="5cb25-158">Configuring the Mirroring Partners</span></span>  
  
1.  <span data-ttu-id="5cb25-159">В экземпляре зеркального сервера, расположенного на узле HOST_B, установите в качестве участника экземпляр сервера, расположенного на узле HOST_A (сделав его начальным экземпляром основного сервера).</span><span class="sxs-lookup"><span data-stu-id="5cb25-159">On the mirror server instance on HOST_B, set the server instance on HOST_A as the partner (making it the initial principal server instance).</span></span> <span data-ttu-id="5cb25-160">Замените допустимый сетевой адрес на `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="5cb25-160">Substitute a valid network address for `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span></span> <span data-ttu-id="5cb25-161">Дополнительные сведения см. в разделе [Указание сетевого адреса сервера (зеркальное отображение базы данных)](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="5cb25-161">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
    ```  
    --At HOST_B, set server instance on HOST_A as partner (principal server):  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_A.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
2.  <span data-ttu-id="5cb25-162">В экземпляре основного сервера, расположенного на узле HOST_A, установите в качестве участника экземпляр сервера, расположенного на узле HOST_B (сделав его начальным экземпляром зеркального сервера).</span><span class="sxs-lookup"><span data-stu-id="5cb25-162">On the principal server instance on HOST_A, set the server instance on HOST_B as the partner (making it the initial mirror server instance).</span></span> <span data-ttu-id="5cb25-163">Замените допустимый сетевой адрес на `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="5cb25-163">Substitute a valid network address for `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span></span>  
  
    ```  
    --At HOST_A, set server instance on HOST_B as partner (mirror server).  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
3.  <span data-ttu-id="5cb25-164">В этом примере предполагается, что сеанс будет выполнен в режиме высокой производительности.</span><span class="sxs-lookup"><span data-stu-id="5cb25-164">This example assumes that the session will be running in high-performance mode.</span></span> <span data-ttu-id="5cb25-165">Чтобы настроить этот сеанс для использования режима высокой производительности, в экземпляре основного сервера (на узле HOST_A) установите безопасность транзакций в положение OFF.</span><span class="sxs-lookup"><span data-stu-id="5cb25-165">To configure this session for high-performance mode, on the principal server instance (on HOST_A), set transaction safety to OFF.</span></span>  
  
    ```  
    --Change to high-performance mode by turning off transacton safety.  
    ALTER DATABASE AdventureWorks   
        SET PARTNER SAFETY OFF  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="5cb25-166">Если вы планируете работать в режиме высокого уровня безопасности с автоматической отработкой отказа, оставьте параметр безопасность транзакций установленным в значение Full (значение по умолчанию) и добавьте следящий сервер как можно скорее после выполнения второго оператора Set Partner **' *`partner_server`* '** .</span><span class="sxs-lookup"><span data-stu-id="5cb25-166">If you intend to run in high-safety mode with automatic failover, leave transaction safety set to FULL (the default setting) and add the witness as soon as possible after executing the second SET PARTNER **'*`partner_server`*'** statement.</span></span> <span data-ttu-id="5cb25-167">Обратите внимание, что следящий сервер вначале нужно настроить для исходящих и входящих соединений.</span><span class="sxs-lookup"><span data-stu-id="5cb25-167">Note that the witness must first be configured for outbound and inbound connections.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5cb25-168">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="5cb25-168">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5cb25-169">Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5cb25-169">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="5cb25-170">Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5cb25-170">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="5cb25-171">Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5cb25-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="5cb25-172">Управление именами входа и заданиями после переключения ролей (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5cb25-172">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
-   <span data-ttu-id="5cb25-173">[Управление метаданными при обеспечении доступности базы данных на другом экземпляре сервера (SQL Server)](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5cb25-173">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span></span>  
  
-   [<span data-ttu-id="5cb25-174">Диагностика конфигурации зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5cb25-174">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="5cb25-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="5cb25-175">See Also</span></span>  
 <span data-ttu-id="5cb25-176">[Безопасность транспорта для зеркального отображения базы данных и группы доступности AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="5cb25-176">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="5cb25-177">[Указание сетевого адреса сервера (зеркальное отображение базы данных)](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="5cb25-177">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="5cb25-178">[Конечная точка зеркального отображения базы данных (SQL Server)](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5cb25-178">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="5cb25-179">[Использование сертификатов для конечной точки зеркального отображения базы данных (Transact-SQL)](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="5cb25-179">[Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span></span>  
 <span data-ttu-id="5cb25-180">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5cb25-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="5cb25-181">Центр безопасности для ядра СУБД SQL Server и Базы данных Azure SQL</span><span class="sxs-lookup"><span data-stu-id="5cb25-181">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
