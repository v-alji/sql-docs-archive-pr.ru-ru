---
title: Создание зашифрованной резервной копии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: e29061d3-c2ab-4d98-b9be-8e90a11d17fe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d46cc686684d87fe393a5db7cfe01194ae917836
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740088"
---
# <a name="create-an-encrypted-backup"></a><span data-ttu-id="bc7d3-102">Создание зашифрованной резервной копии</span><span class="sxs-lookup"><span data-stu-id="bc7d3-102">Create an Encrypted Backup</span></span>
  <span data-ttu-id="bc7d3-103">В этом разделе описаны шаги, необходимые для создания зашифрованной резервной копии с помощью Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-103">This topic describes the steps necessary to create an encrypted backup using Transact-SQL.</span></span>  
  
## <a name="backup-to-disk-with-encryption"></a><span data-ttu-id="bc7d3-104">Резервное копирование на диск с шифрованием</span><span class="sxs-lookup"><span data-stu-id="bc7d3-104">Backup to Disk with Encryption</span></span>  
 <span data-ttu-id="bc7d3-105">**Предварительные условия.**</span><span class="sxs-lookup"><span data-stu-id="bc7d3-105">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="bc7d3-106">Доступ к локальному диску или хранилищу с достаточным количеством места для создания резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-106">Access to a local disk or to storage with adequate space to create a backup of the database.</span></span>  
  
-   <span data-ttu-id="bc7d3-107">Главный ключ базы данных для базы данных master и сертификат или доступный асимметричный ключ на экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-107">A Database Master Key for the master database, and a certificate or asymmetric key available on the instance of SQL Server.</span></span> <span data-ttu-id="bc7d3-108">Требования и разрешения шифрования см. в разделе [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d3-108">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
 <span data-ttu-id="bc7d3-109">Выполните следующие шаги, чтобы создать зашифрованную резервную копию базы данных на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-109">Use the following steps to create an encrypted backup of a database to a local disk.</span></span> <span data-ttu-id="bc7d3-110">В примере используется пользовательская база данных MyTestDB.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-110">This example uses a user database called MyTestDB.</span></span>  
  
1.  <span data-ttu-id="bc7d3-111">**Создайте главный ключ базы данных master.** Выберите пароль для шифрования копии главного ключа базы данных, которая будет храниться в базе данных.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-111">**Create a Database Master Key of the master database:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="bc7d3-112">Подключитесь к ядру СУБД, откройте новое окно запроса, скопируйте в него следующий пример и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-112">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.   
    -- The key is encrypted using the password "<master key password>"  
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
2.  <span data-ttu-id="bc7d3-113">**Создайте сертификат резервной копии.** Создайте сертификат резервной копии в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-113">**Create a Backup Certificate:** Create a backup certificate in the master database.</span></span> <span data-ttu-id="bc7d3-114">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку **Выполнить**</span><span class="sxs-lookup"><span data-stu-id="bc7d3-114">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
    ```  
    Use Master  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDB Backup Encryption Certificate';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="bc7d3-115">**Выполните резервное копирование базы данных.** Укажите алгоритм шифрования и сертификат для использования.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-115">**Backup the database:** Specify the encryption algorithm and certificate to use.</span></span> <span data-ttu-id="bc7d3-116">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-116">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      COMPRESSION,  
      ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
 <span data-ttu-id="bc7d3-117">Пример шифрования резервной копии, защищенной с помощью EKM, см. в статье [Расширенное управление ключами с помощью хранилища ключей Azure (SQL Server)](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d3-117">For an example of encrypting a backup protected by an EKM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
### <a name="backup-to-azure-storage-with-encryption"></a><span data-ttu-id="bc7d3-118">Резервное копирование в службу хранилища Azure с шифрованием</span><span class="sxs-lookup"><span data-stu-id="bc7d3-118">Backup to Azure Storage with Encryption</span></span>  
 <span data-ttu-id="bc7d3-119">При создании резервной копии в хранилище Azure с помощью параметра **Резервное копирование SQL Server на URL-адрес** шаги шифрования остаются теми же, но в качестве места назначения необходимо использовать URL-адрес, а для проверки подлинности в хранилище Azure — учетные данные SQL.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-119">If you are creating a backup to Azure storage using the **SQL Server Backup to URL** option, the encryption steps are the same, but you must use URL as the destination and a SQL Credential to authenticate to the Azure storage.</span></span> <span data-ttu-id="bc7d3-120">Если вы хотите настроить [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] с параметрами шифрования, см. статью [Настройка SQL Server управляемого резервного копирования в Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) и [Настройка SQL Server управляемого резервного копирования в Azure для групп доступности](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d3-120">If you want to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with encryption options, see [Setting up SQL Server Managed Backup to Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 <span data-ttu-id="bc7d3-121">**Предварительные условия.**</span><span class="sxs-lookup"><span data-stu-id="bc7d3-121">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="bc7d3-122">Учетная запись хранения Windows и контейнер.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-122">A windows storage account and a container.</span></span> <span data-ttu-id="bc7d3-123">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="bc7d3-123">For more information, see.</span></span> <span data-ttu-id="bc7d3-124">[Занятие 1. Создание объектов службы хранилища Azure](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d3-124">[Lesson 1: Create Azure Storage Objects](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span></span>  
  
-   <span data-ttu-id="bc7d3-125">Главный ключ базы данных для базы данных master и сертификат или асимметричный ключ на экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-125">A Database Master Key for the master database, and a certificate or asymmetric key  on the instance of SQL Server.</span></span> <span data-ttu-id="bc7d3-126">Требования и разрешения шифрования см. в разделе [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d3-126">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
1.  <span data-ttu-id="bc7d3-127">**Создайте учетные данные SQL Server.** Для создания учетных данных SQL Server подключитесь к ядру СУБД, откройте новое окно запроса, скопируйте в него следующий пример и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-127">**Create SQL Server Credential:** To create a SQL Server credential, connect to the Database Engine, open a new query window, and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account    
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account  
    ```  
  
2.  <span data-ttu-id="bc7d3-128">**Создайте главный ключ базы данных.** Выберите пароль для шифрования копии главного ключа базы данных, которая будет храниться в базе данных.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-128">**Create a Database Master Key:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="bc7d3-129">Подключитесь к ядру СУБД, откройте новое окно запроса, скопируйте в него следующий пример и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-129">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.  
    -- The key is encrypted using the password "<master key password>"  
    USE Master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="bc7d3-130">**Создайте сертификат резервной копии.** Создайте сертификат резервной копии в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-130">**Create a Backup Certificate:** Create a Backup Certificate in the master database.</span></span> <span data-ttu-id="bc7d3-131">Вставьте следующий пример в окно запроса и нажмите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-131">Copy and paste the following example in the query window and click **Execute**</span></span>  
  
    ```  
    USE Master;  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDBBackupEncryptCert ';  
    GO  
  
    ```  
  
4.  <span data-ttu-id="bc7d3-132">**Выполните резервное копирование базы данных.** Укажите алгоритм шифрования и сертификат для использования.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-132">**Backup the database:** Specify the encryption algorithm and the certificate to use.</span></span> <span data-ttu-id="bc7d3-133">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bc7d3-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO URL = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      CREDENTIAL 'mycredential' - this is the name of the credential created in the first step.  
      ,COMPRESSION  
      ,ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
  
