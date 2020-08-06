---
title: Разрешить использование сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- inbound connections
- database mirroring [SQL Server], security
ms.assetid: 5d48bb98-61f0-4b99-8f1a-b53f831d63d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c05397dfbd1740293c4b154ace1ed5704cec11a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655929"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-inbound-connections-transact-sql"></a><span data-ttu-id="b1b7e-102">Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b1b7e-102">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="b1b7e-103">В этом разделе описаны этапы настройки экземпляров сервера для использования сертификатов проверки подлинности входящих соединений при зеркальном отображении базы данных.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-103">This topic describes the steps for configuring server instances to use certificates to authenticate inbound connections for database mirroring.</span></span> <span data-ttu-id="b1b7e-104">Перед настройкой входящих соединений необходимо настроить исходящие соединения на каждом экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-104">Before you can set up inbound connections, you must configure outbound connections on each server instance.</span></span> <span data-ttu-id="b1b7e-105">Дополнительные сведения см. в разделе [Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-105">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
 <span data-ttu-id="b1b7e-106">Процесс настройки входящих соединений состоит из следующих основных шагов:</span><span class="sxs-lookup"><span data-stu-id="b1b7e-106">The process of configuring inbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="b1b7e-107">Создайте имя входа для другой системы.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-107">Create a login for other system.</span></span>  
  
2.  <span data-ttu-id="b1b7e-108">Создайте пользователя для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-108">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="b1b7e-109">Получите сертификат для конечной точки зеркального отображения другого экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-109">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="b1b7e-110">Свяжите сертификат с пользователем, созданным на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-110">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="b1b7e-111">Предоставьте этому имени входа разрешение CONNECT на эту конечную точку зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-111">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="b1b7e-112">Если имеется следящий сервер, для него также необходимо настроить входящие соединения.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-112">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="b1b7e-113">Для этого нужно настроить имена входа, пользователей и сертификаты для следящего сервера на обоих участниках, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-113">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="b1b7e-114">Ниже эти шаги описаны подробно.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-114">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="b1b7e-115">Для каждого шага приведен пример настройки экземпляра сервера в системе с именем HOST_A.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-115">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="b1b7e-116">В соответствующем разделе «Пример» показаны те же шаги для другого экземпляра сервера в системе с именем HOST_B.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-116">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
### <a name="to-configure-server-instances-for-inbound-mirroring-connections-on-host_a"></a><span data-ttu-id="b1b7e-117">Настройка экземпляров сервера на входящие соединения зеркального отображения (на узле HOST_A)</span><span class="sxs-lookup"><span data-stu-id="b1b7e-117">To configure server instances for inbound mirroring connections (on HOST_A)</span></span>  
  
1.  <span data-ttu-id="b1b7e-118">Создайте имя входа для другой системы.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-118">Create a login for the other system.</span></span>  
  
     <span data-ttu-id="b1b7e-119">В следующем примере в базе данных **master** экземпляра сервера на узле HOST_А создается имя входа для системы HOST_B; созданное имя входа называется `HOST_B_login`.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-119">The following example creates a login for the system, HOST_B, in the **master** database of the server instance on HOST_A; in this example, the login is named `HOST_B_login`.</span></span> <span data-ttu-id="b1b7e-120">Подставьте в пример свой собственный пароль.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-120">Substitute a password of your own for the sample password.</span></span>  
  
    ```sql  
    USE master;  
    CREATE LOGIN HOST_B_login   
       WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
     <span data-ttu-id="b1b7e-121">Дополнительные сведения см. в разделе [CREATE LOGIN (Transact-SQL)](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-121">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
     <span data-ttu-id="b1b7e-122">Чтобы просмотреть имена входа для данного экземпляра сервера, необходимо выполнить следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b1b7e-122">To view the logins on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.server_principals;  
    ```  
  
     <span data-ttu-id="b1b7e-123">Дополнительные сведения см. в разделе [sys.server_principals (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-123">For more information, see [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span></span>  
  
2.  <span data-ttu-id="b1b7e-124">Создайте пользователя для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-124">Create a user for that login.</span></span>  
  
     <span data-ttu-id="b1b7e-125">В следующем примере для имени входа, созданного на предыдущем шаге, создается пользователь `HOST_B_user`.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-125">The following example creates a user, `HOST_B_user`, for the login created in the preceding step.</span></span>  
  
    ```sql  
    USE master;  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
     <span data-ttu-id="b1b7e-126">Дополнительные сведения см. в разделе [CREATE USER (Transact-SQL)](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-126">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
     <span data-ttu-id="b1b7e-127">Чтобы просмотреть пользователей данного экземпляра сервера, необходимо выполнить следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b1b7e-127">To view the users on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.sysusers;  
    ```  
  
     <span data-ttu-id="b1b7e-128">Дополнительные сведения см. в разделе [sys.sysusers (Transact-SQL)](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-128">For more information, see [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span></span>  
  
3.  <span data-ttu-id="b1b7e-129">Получите сертификат для конечной точки зеркального отображения другого экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-129">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
     <span data-ttu-id="b1b7e-130">Необходимо получить копию сертификата для конечной точки зеркального отображения удаленного экземпляра сервера, если это еще не было сделано во время настройки исходящих соединений.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-130">If you have not already done so when configuring outbound connections, obtain a copy of the certificate for the mirroring endpoint of the remote server instance.</span></span> <span data-ttu-id="b1b7e-131">Для этого создайте резервную копию сертификата в соответствующем экземпляре сервера, как описано в разделе [Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-131">To do this, back up the certificate on that server instance as described in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span> <span data-ttu-id="b1b7e-132">При копировании сертификата на другую систему используйте безопасный метод копирования.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-132">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="b1b7e-133">Отнеситесь с особым вниманием к хранению сертификатов в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-133">Be extremely careful to keep all of your certificates secure.</span></span>  
  
     <span data-ttu-id="b1b7e-134">Дополнительные сведения см. в разделе [BACKUP CERTIFICATE (Transact-SQL)](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-134">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
4.  <span data-ttu-id="b1b7e-135">Свяжите сертификат с пользователем, созданным на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-135">Associate the certificate with the user created in step 2.</span></span>  
  
     <span data-ttu-id="b1b7e-136">В следующем примере сертификат узла HOST_B связывается с соответствующим пользователем на узле HOST_А.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-136">The following example, associates the certificate of HOST_B with its user on HOST_A.</span></span>  
  
    ```sql  
    USE master;  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
     <span data-ttu-id="b1b7e-137">Дополнительные сведения см. в разделе [CREATE CERTIFICATE (Transact-SQL)](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-137">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="b1b7e-138">Чтобы просмотреть сертификаты данного экземпляра сервера, необходимо выполнить следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b1b7e-138">To view the certificates on this server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="b1b7e-139">Дополнительные сведения см. в разделе [sys.certificates (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-139">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
5.  <span data-ttu-id="b1b7e-140">Предоставьте данной учетной записи разрешение CONNECT на эту удаленную конечную точку зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-140">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
     <span data-ttu-id="b1b7e-141">Например, чтобы предоставить разрешение HOST_A удаленному экземпляру сервера на HOST_B для подключения к его локальной учетной записи, то есть подключиться к `HOST_B_login`, необходимо выполнить следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1b7e-141">For example, to grant permission on HOST_A to the remote server instance on HOST_B to connect to its local login-that is, to connect to `HOST_B_login`-use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```sql  
    USE master;  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
     <span data-ttu-id="b1b7e-142">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений на конечную точку (Transact-SQL)](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-142">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="b1b7e-143">Настройка проверки подлинности сертификата, выданного узлу HOST_B для входа в систему HOST_A, завершена.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-143">This completes setting up certificate authentication for HOST_B to log in to HOST_A.</span></span>  
  
 <span data-ttu-id="b1b7e-144">Необходимо выполнить аналогичные шаги для настройки входящего соединения от узла HOST_A к узлу HOST_B.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-144">You now need to perform the equivalent inbound steps for HOST_A on HOST_B.</span></span> <span data-ttu-id="b1b7e-145">Они перечислены ниже в разделе «Примеры» и проиллюстрированы в части входящих соединений, описанных в примере.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-145">These steps are illustrated in the inbound portion of the example in the Example section, below.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1b7e-146">Пример</span><span class="sxs-lookup"><span data-stu-id="b1b7e-146">Example</span></span>  
 <span data-ttu-id="b1b7e-147">В следующем примере показано, как настроить узел HOST_B для входящих соединений.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-147">The following example demonstrates configuring HOST_B for inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1b7e-148">В этом примере используется файл сертификата, содержащий сертификата HOST_A, который создан фрагментом кода из раздела [Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-148">This example uses a certificate file containing the HOST_A certificate that is created by a code snippet in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
```sql  
USE master;  
--On HOST_B, create a login for HOST_A.  
CREATE LOGIN HOST_A_login WITH PASSWORD = 'AStrongPassword!@#';  
GO  
--Create a user, HOST_A_user, for that login.  
CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
GO  
--Obtain HOST_A certificate. (See the note   
--   preceding this example.)  
--Asscociate this certificate with the user, HOST_A_user.  
CREATE CERTIFICATE HOST_A_cert  
   AUTHORIZATION HOST_A_user  
   FROM FILE = 'C:\HOST_A_cert.cer';  
GO  
--Grant CONNECT permission for the server instance on HOST_A.  
GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO HOST_A_login;  
GO  
```  
  
 <span data-ttu-id="b1b7e-149">Если предполагается работа в режиме высокого уровня безопасности с автоматическим переходом на другой ресурс, необходимо повторить те же самые этапы для настройки следящего сервера на входящие и исходящие соединения.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-149">If you intend to run in high-safety mode with automatic failover, you must repeat the same set up steps to configure the witness for outbound and inbound connections.</span></span>  
  
 <span data-ttu-id="b1b7e-150">Дополнительные сведения о создании зеркальной базы данных, содержащей пример Transact-SQL, см. в разделе [Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-150">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="b1b7e-151">Пример Transact-SQL, устанавливающий сеанс в режиме высокой производительности, см. в разделе [Пример. Настройка зеркального отображения с помощью сертификатов (Transact-SQL)](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b1b7e-151">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b1b7e-152">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b1b7e-152">.NET Framework Security</span></span>  
 <span data-ttu-id="b1b7e-153">При копировании сертификата на другую систему используйте безопасный метод копирования.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-153">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="b1b7e-154">Отнеситесь с особым вниманием к хранению сертификатов в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="b1b7e-154">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b7e-155">См. также</span><span class="sxs-lookup"><span data-stu-id="b1b7e-155">See Also</span></span>  
 <span data-ttu-id="b1b7e-156">[Безопасность транспорта для зеркального отображения базы данных и группы доступности AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="b1b7e-156">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="b1b7e-157">[GRANT, предоставление разрешений конечной точке (Transact-SQL)](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1b7e-157">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 <span data-ttu-id="b1b7e-158">[Настройка зашифрованной зеркальной базы данных](set-up-an-encrypted-mirror-database.md) </span><span class="sxs-lookup"><span data-stu-id="b1b7e-158">[Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md) </span></span>  
 <span data-ttu-id="b1b7e-159">[Конечная точка зеркального отображения базы данных (SQL Server)](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b1b7e-159">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 [<span data-ttu-id="b1b7e-160">Диагностика конфигурации зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b1b7e-160">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
