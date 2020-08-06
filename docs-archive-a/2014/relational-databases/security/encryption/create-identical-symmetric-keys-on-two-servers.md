---
title: Создание идентичных симметричных ключей на двух серверах | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- symmetric keys [SQL Server], creating
ms.assetid: a13d0b21-a43b-43c0-9c22-7ba8f3d15e80
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 38eaccffff89b0be7e59f628fcfb9b6e772a02b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750616"
---
# <a name="create-identical-symmetric-keys-on-two-servers"></a><span data-ttu-id="3e521-102">Создание идентичных симметричных ключей на двух серверах</span><span class="sxs-lookup"><span data-stu-id="3e521-102">Create Identical Symmetric Keys on Two Servers</span></span>
  <span data-ttu-id="3e521-103">В этом разделе описывается создание идентичных симметричных ключей на двух разных серверах в среде [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e521-103">This topic describes how to create identical symmetric keys on two different servers in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3e521-104">Для расшифровки текста необходим ключ, который был использован для его шифрования.</span><span class="sxs-lookup"><span data-stu-id="3e521-104">In order to decrypt ciphertext, you need the key that was used to encrypt it.</span></span> <span data-ttu-id="3e521-105">Если шифрование и расшифровка происходят в одной и той же базе данных, ключ хранится в базе данных и доступен для шифрования и расшифровки в зависимости от разрешений.</span><span class="sxs-lookup"><span data-stu-id="3e521-105">When both encryption and decryption occur in a single database, the key is stored in the database and it is available, depending on permissions, for both encryption and decryption.</span></span> <span data-ttu-id="3e521-106">Но если шифрование и расшифровка происходят в разных базах данных или на разных серверах, ключ хранится в одной из них и недоступен для использования в другой.</span><span class="sxs-lookup"><span data-stu-id="3e521-106">But when encryption and decryption occur in separate databases or on separate servers, the key stored in one database is not available for use on the second database</span></span>  
  
 <span data-ttu-id="3e521-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3e521-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3e521-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3e521-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3e521-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3e521-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3e521-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3e521-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="3e521-111">Создание идентичных симметричных ключей на двух разных серверах с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e521-111">To create identical symmetric keys on two different servers, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3e521-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3e521-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3e521-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3e521-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3e521-114">После создания симметричный ключ должен быть зашифрован с помощью хотя бы одного из следующих средств: сертификат, пароль, симметричный ключ, асимметричный ключ или PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="3e521-114">When a symmetric key is created, the symmetric key must be encrypted by using at least one of the following: certificate, password, symmetric key, asymmetric key, or PROVIDER.</span></span> <span data-ttu-id="3e521-115">Ключ может быть зашифрован более чем один раз для каждого типа шифрования.</span><span class="sxs-lookup"><span data-stu-id="3e521-115">The key can have more than one encryption of each type.</span></span> <span data-ttu-id="3e521-116">Другими словами, один симметричный ключ может быть зашифрован с использованием нескольких сертификатов, симметричных ключей и асимметричных ключей одновременно.</span><span class="sxs-lookup"><span data-stu-id="3e521-116">In other words, a single symmetric key can be encrypted by using multiple certificates, passwords, symmetric keys, and asymmetric keys at the same time.</span></span>  
  
-   <span data-ttu-id="3e521-117">Если симметричный ключ шифруется с использованием пароля вместо открытого ключа главного ключа базы данных, то используется алгоритм шифрования TRIPLE DES.</span><span class="sxs-lookup"><span data-stu-id="3e521-117">When a symmetric key is encrypted with a password instead of the public key of the database master key, the TRIPLE DES encryption algorithm is used.</span></span> <span data-ttu-id="3e521-118">Поэтому ключи, созданные с помощью сильных алгоритмов шифрования, таких как AES, защищены с помощью более слабого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="3e521-118">Because of this, keys that are created with a strong encryption algorithm, such as AES, are themselves secured by a weaker algorithm.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e521-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="3e521-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3e521-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="3e521-120">Permissions</span></span>  
 <span data-ttu-id="3e521-121">Необходимо разрешение ALTER ANY SYMMETRIC KEY на базу данных.</span><span class="sxs-lookup"><span data-stu-id="3e521-121">Requires ALTER ANY SYMMETRIC KEY permission on the database.</span></span> <span data-ttu-id="3e521-122">Если указан аргумент AUTHORIZATION, то требуется разрешение IMPERSONATE для пользователя базы данных или разрешение ALTER для роли приложения.</span><span class="sxs-lookup"><span data-stu-id="3e521-122">If AUTHORIZATION is specified, requires IMPERSONATE permission on the database user or ALTER permission on the application role.</span></span> <span data-ttu-id="3e521-123">Если для шифрования использовался сертификат или асимметричный ключ, то требуется разрешение VIEW DEFINITION для сертификата или асимметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="3e521-123">If encryption is by certificate or asymmetric key, requires VIEW DEFINITION permission on the certificate or asymmetric key.</span></span> <span data-ttu-id="3e521-124">Симметричные ключи могут принадлежать только именам входа Windows, именам входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и ролям приложений.</span><span class="sxs-lookup"><span data-stu-id="3e521-124">Only Windows logins, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins, and application roles can own symmetric keys.</span></span> <span data-ttu-id="3e521-125">Симметричные ключи не могут принадлежать группам и ролям.</span><span class="sxs-lookup"><span data-stu-id="3e521-125">Groups and roles cannot own symmetric keys.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3e521-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e521-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-identical-symmetric-keys-on-two-different-servers"></a><span data-ttu-id="3e521-127">Создание идентичных симметричных ключей на двух разных серверах</span><span class="sxs-lookup"><span data-stu-id="3e521-127">To create identical symmetric keys on two different servers</span></span>  
  
1.  <span data-ttu-id="3e521-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e521-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3e521-129">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3e521-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3e521-130">Создайте ключ, выполнив следующие инструкции CREATE MASTER KEY, CREATE CERTIFICATE и CREATE SYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="3e521-130">Create a key by running the following CREATE MASTER KEY, CREATE CERTIFICATE, and CREATE SYMMETRIC KEY statements.</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'My p@55w0Rd';  
    GO  
    CREATE CERTIFICATE [cert_keyProtection] WITH SUBJECT = 'Key Protection';  
    GO  
    CREATE SYMMETRIC KEY [key_DataShare] WITH  
        KEY_SOURCE = 'My key generation bits. This is a shared secret!',  
        ALGORITHM = AES_256,   
        IDENTITY_VALUE = 'Key Identity generation bits. Also a shared secret'  
        ENCRYPTION BY CERTIFICATE [cert_keyProtection];  
    GO  
    ```  
  
4.  <span data-ttu-id="3e521-131">Подключитесь к отдельному экземпляру сервера, откройте новое окно запросов и выполните приведенные выше SQL-инструкции для создания того же ключа на втором сервере.</span><span class="sxs-lookup"><span data-stu-id="3e521-131">Connect to a separate server instance, open a different Query Window, and run the SQL statements above to create the same key on the second server.</span></span>  
  
5.  <span data-ttu-id="3e521-132">Проверьте ключи, запустив на одном сервере вначале инструкцию OPEN SYMMETRIC KEY, а затем инструкцию SELECT.</span><span class="sxs-lookup"><span data-stu-id="3e521-132">Test the keys by first running the OPEN SYMMETRIC KEY statement and the SELECT statement below on the first server.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    SELECT encryptbykey(key_guid('key_DataShare'), 'MyData' )  
    GO  
    -- For example, the output might look like this: 0x2152F8DA8A500A9EDC2FAE26D15C302DA70D25563DAE7D5D1102E3056CE9EF95CA3E7289F7F4D0523ED0376B155FE9C3  
    ```  
  
6.  <span data-ttu-id="3e521-133">На втором сервере вставьте результат выполнения инструкции SELECT в приведенный ниже программный код в качестве значения `@blob` и выполните его, чтобы убедиться, что данные расшифровываются вторым ключом.</span><span class="sxs-lookup"><span data-stu-id="3e521-133">On the second server, paste the result of the previous SELECT statement into the following code as the value of `@blob` and run the following code to verify that the duplicate key can decrypt the ciphertext.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    DECLARE @blob varbinary(8000);  
    SET @blob = SELECT CONVERT(varchar(8000), decryptbykey(@blob));  
    GO  
    ```  
  
7.  <span data-ttu-id="3e521-134">Закройте симметричные ключи на обоих серверах.</span><span class="sxs-lookup"><span data-stu-id="3e521-134">Close the symmetric key on both servers.</span></span>  
  
    ```  
    CLOSE SYMMETRIC KEY [key_DataShare];  
    GO  
    ```  
  
 <span data-ttu-id="3e521-135">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3e521-135">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="3e521-136">CREATE MASTER KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e521-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="3e521-137">CREATE CERTIFICATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e521-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="3e521-138">CREATE SYMMETRIC KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e521-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)  
  
-   [<span data-ttu-id="3e521-139">ENCRYPTBYKEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e521-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
  
-   [<span data-ttu-id="3e521-140">DECRYPTBYKEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e521-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/decryptbykey-transact-sql)  
  
-   [<span data-ttu-id="3e521-141">OPEN SYMMETRIC KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e521-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/open-symmetric-key-transact-sql)  
  
  
