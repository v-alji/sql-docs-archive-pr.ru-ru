---
title: Пример. Настройка зеркального отображения базы данных с помощью проверки подлинности Windows (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- Windows authentication [SQL Server]
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: 35800769-aede-4aac-b077-0e0e487e302f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95df855e8e41c5937aae02884c71792537eb2bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655911"
---
# <a name="example-setting-up-database-mirroring-using-windows-authentication-transact-sql"></a><span data-ttu-id="e8251-102">Пример. Настройка зеркального отображения базы данных с помощью проверки подлинности Windows (язык Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e8251-102">Example: Setting Up Database Mirroring Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="e8251-103">В этом примере показаны все этапы создания сеанса зеркального отображения базы данных со следящим сервером, использующим проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e8251-103">This example shows all the stages required to create a database mirroring session with a witness using Windows Authentication.</span></span> <span data-ttu-id="e8251-104">Примеры в этом подразделе используют язык [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8251-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e8251-105">Обратите внимание, что в качестве альтернативы использованию этапов [!INCLUDE[tsql](../../includes/tsql-md.md)] для установки зеркального отображения баз данных можно воспользоваться мастером конфигурации безопасности зеркального отображения баз данных.</span><span class="sxs-lookup"><span data-stu-id="e8251-105">Note that as an alternative to using [!INCLUDE[tsql](../../includes/tsql-md.md)] steps, you can use the Configure Database Mirroring Security Wizard for database mirroring setup.</span></span> <span data-ttu-id="e8251-106">Дополнительные сведения см. в подразделе [Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)](establish-database-mirroring-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e8251-106">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="e8251-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e8251-107">Prerequisite</span></span>  
 <span data-ttu-id="e8251-108">В примере используется образец базы данных **AdventureWorks** , которая по умолчанию использует простую модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="e8251-108">The example uses the **AdventureWorks** sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="e8251-109">Для зеркального отображения этой базы данных нужно переключить ее на модель полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="e8251-109">To use database mirroring with this database, you must alter it to use the full recovery model.</span></span> <span data-ttu-id="e8251-110">Чтобы сделать это средствами языка [!INCLUDE[tsql](../../includes/tsql-md.md)], выполните следующую инструкцию ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="e8251-110">To do this in [!INCLUDE[tsql](../../includes/tsql-md.md)], use the ALTER DATABASE statement, as follows:</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE AdventureWorks   
SET RECOVERY FULL;  
GO  
```  
  
 <span data-ttu-id="e8251-111">Дополнительные сведения об изменении модели восстановления в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] см. в разделе [Просмотр или изменение модели восстановления базы данных (SQL Server)](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e8251-111">For information on changing the recovery model in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="e8251-112">Разрешения</span><span class="sxs-lookup"><span data-stu-id="e8251-112">Permissions</span></span>  
 <span data-ttu-id="e8251-113">Требуется разрешение ALTER для базы данных и разрешение CREATE ENDPOINT либо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e8251-113">Requires ALTER permission on the database and CREATE ENDPOINT permission, or membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8251-114">Пример</span><span class="sxs-lookup"><span data-stu-id="e8251-114">Example</span></span>  
 <span data-ttu-id="e8251-115">В этом примере два участника и следящий сервер являются экземплярами серверов по умолчанию на трех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="e8251-115">In this example, the two partners and the witness are the default server instances on three computer systems.</span></span> <span data-ttu-id="e8251-116">На трех экземплярах сервера работает один и тот же домен Windows, но в данном примере для каждого экземпляра следящего сервера предусмотрены разные учетные записи пользователя (применяемые в качестве учетной записи запуска для службы).</span><span class="sxs-lookup"><span data-stu-id="e8251-116">The three server instances run the same Windows domain, but the user account (used as the startup service account) is different for the example's witness server instance.</span></span>  
  
 <span data-ttu-id="e8251-117">В следующей таблице представлены все значения, использованные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="e8251-117">The following table summarizes the values used in this example.</span></span>  
  
|<span data-ttu-id="e8251-118">Начальная роль зеркального отображения</span><span class="sxs-lookup"><span data-stu-id="e8251-118">Initial mirroring role</span></span>|<span data-ttu-id="e8251-119">Система размещения</span><span class="sxs-lookup"><span data-stu-id="e8251-119">Host system</span></span>|<span data-ttu-id="e8251-120">Учетная запись пользователя домена</span><span class="sxs-lookup"><span data-stu-id="e8251-120">Domain user account</span></span>|  
|----------------------------|-----------------|-------------------------|  
|<span data-ttu-id="e8251-121">Основной</span><span class="sxs-lookup"><span data-stu-id="e8251-121">Principal</span></span>|<span data-ttu-id="e8251-122">PARTNERHOST1</span><span class="sxs-lookup"><span data-stu-id="e8251-122">PARTNERHOST1</span></span>|<span data-ttu-id="e8251-123">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="e8251-123">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="e8251-124">Зеркальное отображение</span><span class="sxs-lookup"><span data-stu-id="e8251-124">Mirror</span></span>|<span data-ttu-id="e8251-125">PARTNERHOST5</span><span class="sxs-lookup"><span data-stu-id="e8251-125">PARTNERHOST5</span></span>|<span data-ttu-id="e8251-126">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="e8251-126">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="e8251-127">Свидетель</span><span class="sxs-lookup"><span data-stu-id="e8251-127">Witness</span></span>|<span data-ttu-id="e8251-128">WITNESSHOST4</span><span class="sxs-lookup"><span data-stu-id="e8251-128">WITNESSHOST4</span></span>|<span data-ttu-id="e8251-129">*\<Somedomain>\\<witnessuser\>*</span><span class="sxs-lookup"><span data-stu-id="e8251-129">*\<Somedomain>\\<witnessuser\>*</span></span>|  
  
1.  <span data-ttu-id="e8251-130">Создайте конечную точку на экземпляре основного сервера (экземпляр по умолчанию для PARTNERHOST1).</span><span class="sxs-lookup"><span data-stu-id="e8251-130">Create an endpoint on the principal server instance (default instance on PARTNERHOST1).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=PARTNER)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    -- Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
2.  <span data-ttu-id="e8251-131">Создайте конечную точку на экземпляре зеркального сервера (экземпляр по умолчанию для PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="e8251-131">Create an endpoint on the mirror server instance (default instance on PARTNERHOST5).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="e8251-132">Создайте конечную точку на экземпляре следящего сервера (экземпляр по умолчанию для WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="e8251-132">Create an endpoint on the witness server instance (default instance on WITNESSHOST4).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    --Create a login for the partner server instances,  
    --which are both running as Mydomain\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [Mydomain\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
4.  <span data-ttu-id="e8251-133">Создайте зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="e8251-133">Create the mirror database.</span></span> <span data-ttu-id="e8251-134">Дополнительные сведения см. в статье [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e8251-134">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="e8251-135">На экземпляре зеркального сервера PARTNERHOST5 установите экземпляр сервера PARTNERHOST1 в качестве участника (для этого его нужно сделать начальным экземпляром основного сервера).</span><span class="sxs-lookup"><span data-stu-id="e8251-135">On the mirror server instance on PARTNERHOST5, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1.COM:7022'  
    GO  
    ```  
  
6.  <span data-ttu-id="e8251-136">На экземпляре основного сервера PARTNERHOST1 установите экземпляр сервера PARTNERHOST5 в качестве участника (для этого нужно сделать его начальным экземпляром зеркального сервера).</span><span class="sxs-lookup"><span data-stu-id="e8251-136">On the principal server instance on PARTNERHOST1, set the server instance on PARTNERHOST5 as the partner (making it the initial mirror server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5.COM:7022'  
    GO  
    ```  
  
7.  <span data-ttu-id="e8251-137">На основном сервере задайте следящий сервер (находящийся на экземпляре WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="e8251-137">On the principal server, set the witness (which is on WITNESSHOST4).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4.COM:7022'  
    GO  
    ```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e8251-138">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="e8251-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e8251-139">Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e8251-139">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="e8251-140">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e8251-140">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
-   [<span data-ttu-id="e8251-141">Настройка зеркальной базы данных на использование свойства TRUSTWORTHY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e8251-141">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
-   [<span data-ttu-id="e8251-142">Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e8251-142">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="e8251-143">Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e8251-143">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="e8251-144">Пример. Настройка зеркального отображения с помощью сертификатов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e8251-144">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="e8251-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8251-145">See Also</span></span>  
 <span data-ttu-id="e8251-146">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e8251-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="e8251-147">[Конечная точка зеркального отображения базы данных (SQL Server)](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e8251-147">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="e8251-148">[Безопасность транспорта для зеркального отображения базы данных и группы доступности AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="e8251-148">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="e8251-149">[Управление метаданными при обеспечении доступности базы данных на другом экземпляре сервера (SQL Server)](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span><span class="sxs-lookup"><span data-stu-id="e8251-149">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span></span>  
 [<span data-ttu-id="e8251-150">Центр безопасности для ядра СУБД SQL Server и Базы данных Azure SQL</span><span class="sxs-lookup"><span data-stu-id="e8251-150">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
