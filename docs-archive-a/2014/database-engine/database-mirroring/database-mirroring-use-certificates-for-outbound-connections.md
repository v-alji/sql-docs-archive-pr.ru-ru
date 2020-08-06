---
title: Разрешить использование сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- outbound connections [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 464c9096-10d6-4c5e-8bb1-19acba27ad9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f380f268f8d0f8d033db9c28f83d066d3f134571
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655928"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-outbound-connections-transact-sql"></a><span data-ttu-id="1f19a-102">Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1f19a-102">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="1f19a-103">В этом подразделе описаны этапы настройки экземпляров сервера для использования сертификатов проверки подлинности исходящих соединений при зеркальном отображении базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f19a-103">This topic describes the steps for configuring server instances to use certificates to authenticate outbound connections for database mirroring.</span></span> <span data-ttu-id="1f19a-104">Конфигурацию исходящих соединений необходимо выполнить до настройки входящих соединений.</span><span class="sxs-lookup"><span data-stu-id="1f19a-104">Outbound connection configuration must be done before you can set up inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f19a-105">Все соединения зеркального отображения экземпляра сервера используют одну и ту же конечную точку зеркального отображения базы данных, и при ее создании необходимо задать метод проверки подлинности экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="1f19a-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span>  
  
 <span data-ttu-id="1f19a-106">Конфигурирование исходящих соединений включает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="1f19a-106">The process of configuring outbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="1f19a-107">В базе данных **master** создайте главный ключ базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f19a-107">In the **master** database, create a database Master Key.</span></span>  
  
2.  <span data-ttu-id="1f19a-108">В базе данных **master** создайте зашифрованный сертификат для экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="1f19a-108">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="1f19a-109">Создайте конечную точку для экземпляра сервера при использовании его сертификата.</span><span class="sxs-lookup"><span data-stu-id="1f19a-109">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="1f19a-110">Создайте резервную копию сертификата в файле и защищенным образом скопируйте этот файл на другие системы.</span><span class="sxs-lookup"><span data-stu-id="1f19a-110">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="1f19a-111">Все эти этапы необходимо выполнить для каждого из участников, а также для следящего сервера, если он есть.</span><span class="sxs-lookup"><span data-stu-id="1f19a-111">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="1f19a-112">Ниже эти шаги описаны подробно.</span><span class="sxs-lookup"><span data-stu-id="1f19a-112">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="1f19a-113">Для каждого шага приведен пример настройки экземпляра сервера в системе с именем HOST_A.</span><span class="sxs-lookup"><span data-stu-id="1f19a-113">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="1f19a-114">В соответствующем разделе «Пример» показаны те же шаги для другого экземпляра сервера в системе с именем HOST_B.</span><span class="sxs-lookup"><span data-stu-id="1f19a-114">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="1f19a-115">Процедура</span><span class="sxs-lookup"><span data-stu-id="1f19a-115">Procedure</span></span>  
  
#### <a name="to-configure-server-instances-for-outbound-mirroring-connections-on-host_a"></a><span data-ttu-id="1f19a-116">Настройка экземпляров сервера на исходящие соединения зеркального отображения (на HOST_A)</span><span class="sxs-lookup"><span data-stu-id="1f19a-116">To configure server instances for outbound mirroring connections (On HOST_A)</span></span>  
  
1.  <span data-ttu-id="1f19a-117">В базе данных **master** создайте главный ключ базы данных, если он еще не создан.</span><span class="sxs-lookup"><span data-stu-id="1f19a-117">On the **master** database, create the database Master Key, if none exists.</span></span> <span data-ttu-id="1f19a-118">Для просмотра существующих ключей базы данных предназначено представление каталога [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="1f19a-118">To view the existing keys for a database, use the [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) catalog view.</span></span>  
  
     <span data-ttu-id="1f19a-119">Создание главного ключа базы данных производится следующей инструкцией [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="1f19a-119">To create the database Master Key, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command:</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
     <span data-ttu-id="1f19a-120">Используйте уникальный надежный пароль, запишите его и храните в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="1f19a-120">Use a unique, strong password, and record it in a safe place.</span></span>  
  
     <span data-ttu-id="1f19a-121">Дополнительные сведения см. в разделах [CREATE MASTER KEY (Transact-SQL)](/sql/t-sql/statements/create-master-key-transact-sql) и [Создание главного ключа базы данных](../../relational-databases/security/encryption/create-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="1f19a-121">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) and [Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md).</span></span>  
  
2.  <span data-ttu-id="1f19a-122">В базе данных **master** создайте зашифрованный сертификат экземпляра сервера, он будет использоваться для исходящих соединений этого экземпляра при зеркальном отображении базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f19a-122">In the **master** database, create an encrypted certificate on the server instance to use for its outbound connections for database mirroring.</span></span>  
  
     <span data-ttu-id="1f19a-123">Например, чтобы создать сертификат для системы HOST_A.</span><span class="sxs-lookup"><span data-stu-id="1f19a-123">For example, to create a certificate for the HOST_A system.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1f19a-124">Если планируется использование сертификата в течение срока, превышающего один год, укажите дату истечения срока действия в формате UTC с помощью параметра EXPIRY_DATE инструкции CREATE CERTIFICATE.</span><span class="sxs-lookup"><span data-stu-id="1f19a-124">If you intend to use the certificate for more than one year, specify the expiry date in UTC time by using the EXPIRY_DATE option in your CREATE CERTIFICATE statement.</span></span> <span data-ttu-id="1f19a-125">Кроме того, рекомендуется использовать среду SQL Server Management Studio для создания правила управления на основе политик, чтобы получать предупреждения при завершении срока действия сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1f19a-125">Also, we recommend that you use SQL Server Management Studio to create a Policy-Based Management rule to alert you when your certificates are expiring.</span></span> <span data-ttu-id="1f19a-126">В диалоговом окне **Создание нового условия** создайте это правило в поле **@ExpirationDate** аспекта **Certificate** .</span><span class="sxs-lookup"><span data-stu-id="1f19a-126">Using the Policy Management **Create New Condition** dialog box, create this rule on the **@ExpirationDate** field of the **Certificate** facet.</span></span> <span data-ttu-id="1f19a-127">Дополнительные сведения см. в разделах [Администрирование серверов с помощью управления на основе политик](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) и [Обеспечение безопасности SQL Server](../../relational-databases/security/securing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f19a-127">For more information, see [Administer Servers by Using Policy-Based Management](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) and [Securing SQL Server](../../relational-databases/security/securing-sql-server.md).</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate for database mirroring',   
       EXPIRY_DATE = '11/30/2013';  
    GO  
    ```  
  
     <span data-ttu-id="1f19a-128">Дополнительные сведения см. в разделе [CREATE CERTIFICATE (Transact-SQL)](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1f19a-128">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="1f19a-129">Просмотр сертификатов в базе данных **master** можно выполнить с помощью следующих инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="1f19a-129">To view the certificates in the **master** database, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="1f19a-130">Дополнительные сведения см. в разделе [sys.certificates (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1f19a-130">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
3.  <span data-ttu-id="1f19a-131">Убедитесь, что в каждом экземпляре сервера существует конечная точка зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f19a-131">Ensure that the database mirroring endpoint exist on each of the server instances.</span></span>  
  
     <span data-ttu-id="1f19a-132">Если конечная точка уже имеется для данного экземпляра сервера, она используется для всех сеансов, устанавливаемых для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1f19a-132">If a database mirroring endpoint already exists for the server instance, you should reuse that endpoint for any other sessions you establish on the server instance.</span></span> <span data-ttu-id="1f19a-133">Чтобы определить, существует ли конечная точка зеркального отображения базы данных в экземпляре сервера и просмотреть ее конфигурацию, выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="1f19a-133">To determine whether a database mirroring endpoint exists on a server instance and to view its configuration, use the following statement:</span></span>  
  
    ```  
    SELECT name, role_desc, state_desc, connection_auth_desc, encryption_algorithm_desc   
       FROM sys.database_mirroring_endpoints;  
    ```  
  
     <span data-ttu-id="1f19a-134">Если конечная точка не существует, создайте конечную точку, которая использует этот сертификат для исходящих соединений и его учетные данные для проверки на других системах.</span><span class="sxs-lookup"><span data-stu-id="1f19a-134">If no endpoint exists, create an endpoint that uses this certificate for outbound connections and that uses the certificate's credentials for verification on the other system.</span></span> <span data-ttu-id="1f19a-135">Это конечная точка на уровне сервера, используемая всеми зеркальными сеансами, в которых участвует экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="1f19a-135">This is a server-wide endpoint that is used by all mirroring sessions in which the server instance participates.</span></span>  
  
     <span data-ttu-id="1f19a-136">Например, чтобы создать конечную точку зеркального отображения для экземпляра сервера HOST_A.</span><span class="sxs-lookup"><span data-stu-id="1f19a-136">For example, to create a mirroring endpoint for the example server instance on HOST_A.</span></span>  
  
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
  
     <span data-ttu-id="1f19a-137">Дополнительные сведения см. в разделе [CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1f19a-137">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
4.  <span data-ttu-id="1f19a-138">Создайте резервную копию сертификата и скопируйте ее на другую систему или системы.</span><span class="sxs-lookup"><span data-stu-id="1f19a-138">Back up the certificate and copy it to the other system or systems.</span></span> <span data-ttu-id="1f19a-139">Она понадобится при конфигурировании на них входящих соединений.</span><span class="sxs-lookup"><span data-stu-id="1f19a-139">This is necessary in order to configure inbound connections on the other system.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
     <span data-ttu-id="1f19a-140">Дополнительные сведения см. в разделе [BACKUP CERTIFICATE (Transact-SQL)](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1f19a-140">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="1f19a-141">Скопируйте этот сертификат любым безопасным способом.</span><span class="sxs-lookup"><span data-stu-id="1f19a-141">Copy this certificate using any secure method you choose.</span></span> <span data-ttu-id="1f19a-142">Отнеситесь с особым вниманием к хранению сертификатов в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="1f19a-142">Be extremely careful to keep all of your certificates secure.</span></span>  
  
 <span data-ttu-id="1f19a-143">Программный код примеров на предыдущих шагах конфигурирует исходящие соединения на HOST_A.</span><span class="sxs-lookup"><span data-stu-id="1f19a-143">The example code in the preceding steps configure outbound connections on HOST_A.</span></span>  
  
 <span data-ttu-id="1f19a-144">Необходимо выполнить аналогичные шаги для настройки исходящего соединения для HOST_B.</span><span class="sxs-lookup"><span data-stu-id="1f19a-144">You now need to perform the equivalent outbound steps for HOST_B.</span></span> <span data-ttu-id="1f19a-145">Они показаны в следующем разделе примеров.</span><span class="sxs-lookup"><span data-stu-id="1f19a-145">These steps are illustrated in the following Example section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f19a-146">Пример</span><span class="sxs-lookup"><span data-stu-id="1f19a-146">Example</span></span>  
 <span data-ttu-id="1f19a-147">В следующем примере показано конфигурирование исходящих соединений на HOST_Б.</span><span class="sxs-lookup"><span data-stu-id="1f19a-147">The following example demonstrates configuring HOST_B for outbound connections.</span></span>  
  
```  
USE master;  
--Create the database Master Key, if needed.  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
GO  
-- Make a certifcate on HOST_B server instance.  
CREATE CERTIFICATE HOST_B_cert   
   WITH SUBJECT = 'HOST_B certificate for database mirroring',   
   EXPIRY_DATE = '11/30/2013';  
GO  
--Create a mirroring endpoint for the server instance on HOST_B.  
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
--Backup HOST_B certificate.  
BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
GO   
--Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.  
```  
  
 <span data-ttu-id="1f19a-148">Скопируйте этот сертификат в другую систему любым безопасным способом.</span><span class="sxs-lookup"><span data-stu-id="1f19a-148">Copy the certificate to the other system using any secure method you choose.</span></span> <span data-ttu-id="1f19a-149">Отнеситесь с особым вниманием к хранению сертификатов в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="1f19a-149">Be extremely careful to keep all of your certificates secure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1f19a-150">После настройки исходящих соединений необходимо настроить входящие соединения на каждом экземпляре сервера для остальных экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="1f19a-150">After you set up outbound connections, you must configure inbound connections on each server instance for the other server instance or instances.</span></span> <span data-ttu-id="1f19a-151">Дополнительные сведения см. в разделе [Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="1f19a-151">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
 <span data-ttu-id="1f19a-152">Дополнительные сведения о создании зеркальной базы данных, содержащей пример Transact-SQL, см. в разделе [Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f19a-152">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="1f19a-153">Пример Transact-SQL, устанавливающий сеанс в режиме высокой производительности, см. в разделе [Пример. Настройка зеркального отображения с помощью сертификатов (Transact-SQL)](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1f19a-153">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1f19a-154">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1f19a-154">.NET Framework Security</span></span>  
 <span data-ttu-id="1f19a-155">За исключением случаев, когда сеть гарантированно защищена, рекомендуется для соединений зеркального отображения базы данных применять шифрование.</span><span class="sxs-lookup"><span data-stu-id="1f19a-155">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="1f19a-156">При копировании сертификата на другую систему используйте безопасный метод копирования.</span><span class="sxs-lookup"><span data-stu-id="1f19a-156">When copying a certificate to another system, use a secure copy method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f19a-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f19a-157">See Also</span></span>  
 <span data-ttu-id="1f19a-158">[Выбор алгоритма шифрования](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="1f19a-158">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="1f19a-159">[Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1f19a-159">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="1f19a-160">[ALTER ENDPOINT (Transact-SQL)](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f19a-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="1f19a-161">[Пример. Настройка зеркального отображения с помощью сертификатов (Transact-SQL)](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="1f19a-161">[Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span></span>  
 <span data-ttu-id="1f19a-162">[Конечная точка зеркального отображения базы данных (SQL Server)](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1f19a-162">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="1f19a-163">[Диагностика конфигурации зеркального отображения базы данных (SQL Server)](troubleshoot-database-mirroring-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1f19a-163">[Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span></span>  
 [<span data-ttu-id="1f19a-164">Настройка зашифрованной зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="1f19a-164">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
