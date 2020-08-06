---
title: Занятие 5. Используемых Шифрование базы данных с помощью TDE | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ba793c8f-665a-4c46-b68d-f558a37906b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 613b66c04a69364f3c9be1059f95021dd3eff595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665335"
---
# <a name="lesson-5-optional-encrypt-your-database-using-tde"></a><span data-ttu-id="cb918-103">Занятие 5.</span><span class="sxs-lookup"><span data-stu-id="cb918-103">Lesson 5.</span></span> <span data-ttu-id="cb918-104">(Необязательно) Шифрование базы данных с помощью TDE</span><span class="sxs-lookup"><span data-stu-id="cb918-104">(Optional) Encrypt your database using TDE</span></span>
  <span data-ttu-id="cb918-105">В качестве дополнительного шага вы можете зашифровать созданную базу данных.</span><span class="sxs-lookup"><span data-stu-id="cb918-105">As an optional step, you can encrypt the newly created database.</span></span> <span data-ttu-id="cb918-106">Функция прозрачного шифрования данных (TDE) выполняет в реальном времени шифрование и дешифрование файлов данных и журналов в операциях ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="cb918-106">Transparent data encryption (TDE) performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="cb918-107">При таком типе шифрования используется ключ шифрования базы данных (DEK), который хранится в загрузочной записи базы данных, чтобы он был доступен при восстановлении.</span><span class="sxs-lookup"><span data-stu-id="cb918-107">This kind of encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="cb918-108">Дополнительные сведения см. в статьях [прозрачное шифрование данных &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) и [Перемещение защищенной базы данных TDE на другой SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cb918-108">For more information, see [Transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) and [Move a TDE Protected Database to Another SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span></span>  
  
 <span data-ttu-id="cb918-109">Для этого занятия предполагается, что вы уже выполнили следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="cb918-109">This lesson assumes you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="cb918-110">У вас есть учетная запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="cb918-110">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="cb918-111">Вы создали контейнер в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="cb918-111">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="cb918-112">Создали политику в контейнере с правами на чтение, запись и перечисление.</span><span class="sxs-lookup"><span data-stu-id="cb918-112">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="cb918-113">Создали ключ SAS.</span><span class="sxs-lookup"><span data-stu-id="cb918-113">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="cb918-114">Создали учетные данные SQL Server на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cb918-114">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="cb918-115">Создали базу данных с помощью процедуры, описанной в занятии 4.</span><span class="sxs-lookup"><span data-stu-id="cb918-115">You have created a database by following the steps that are described in Lesson 4.</span></span>  
  
 <span data-ttu-id="cb918-116">Чтобы зашифровать базу данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="cb918-116">If you want to encrypt a database, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cb918-117">На исходном компьютере внесите изменения и выполните в окне запроса следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="cb918-117">In the source machine, modify and run the following statements in a query window:</span></span>  
  
    ```  
  
    -- Create a master key and a server certificate   
    USE master   
    GO   
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01';   
    GO   
    CREATE CERTIFICATE MySQLCert WITH SUBJECT = 'SQL - Azure Storage Certification'   
    GO   
    -- Create a backup of the server certificate in the master database.   
    -- Store TDS certificates in the source machine locally.   
    BACKUP CERTIFICATE MySQLCert   
    TO FILE = 'C:\certs\MySQLCert.CER'   
    WITH PRIVATE KEY   
    (   
    FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
    ENCRYPTION BY PASSWORD = 'MySQLKey01'   
    );  
  
    ```  
  
2.  <span data-ttu-id="cb918-118">Затем зашифруйте новую базу данных на исходном компьютере, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="cb918-118">Then, encrypt your new database in the source machine by following these steps:</span></span>  
  
    ```  
  
    -- Switch to the new database.   
    -- Create a database encryption key, that is protected by the server certificate in the master database.    
    -- Alter the new database to encrypt the database using TDE.   
    USE TestDB1;   
    GO   
    -- Encrypt your database   
    CREATE DATABASE ENCRYPTION KEY   
    WITH ALGORITHM = AES_256   
    ENCRYPTION BY SERVER CERTIFICATE MySQLCert   
    GO   
  
    ALTER DATABASE TestDB1   
    SET ENCRYPTION ON   
    GO  
  
    ```  
  
 <span data-ttu-id="cb918-119">Чтобы узнать состояние шифрования базы данных и связанных ключей шифрования базы данных, выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="cb918-119">If you want to learn the encryption state of a database and its associated database encryption keys, run the following statement:</span></span>  
  
```  
  
SELECT * FROM sys.dm_database_encryption_keys;   
GO  
  
```  
  
 <span data-ttu-id="cb918-120">Подробные сведения о инструкциях Transact-SQL, которые использовались в этом занятии, см. в статьях [Создание базы данных &#40;SQL Server Transact-sql&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [Создание главного ключа &#40;Transact-sql&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [CREATE CERTIFICATE &#40;transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql)и [sys. dm_database_encryption_keys &#40;Transact-SQL ](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql)&#41;.</span><span class="sxs-lookup"><span data-stu-id="cb918-120">For detailed information the Transact-SQL statements that have been used in this lesson, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql), and [sys.dm_database_encryption_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span></span>  
  
 <span data-ttu-id="cb918-121">**Следующее занятие:**</span><span class="sxs-lookup"><span data-stu-id="cb918-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="cb918-122">Занятие 6: Перенос базы данных с исходного локального компьютера на целевой компьютер в Azure</span><span class="sxs-lookup"><span data-stu-id="cb918-122">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>](lesson-5-backup-database-using-file-snapshot-backup.md)  
  
  
