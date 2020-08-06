---
title: Шифрование резервной копии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 334b95a8-6061-4fe0-9e34-b32c9f1706ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6a78ae4969982fbfe5295ee4219855f48ac60793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752236"
---
# <a name="backup-encryption"></a><span data-ttu-id="690e5-102">Шифрование резервной копии</span><span class="sxs-lookup"><span data-stu-id="690e5-102">Backup Encryption</span></span>
  <span data-ttu-id="690e5-103">В этом разделе приводится общее описание параметров шифрования для резервного копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="690e5-103">This topic provides an overview of the encryption options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="690e5-104">Он содержит сведения об использовании, преимуществах и рекомендациях для шифрования при резервном копировании.</span><span class="sxs-lookup"><span data-stu-id="690e5-104">It includes details of the usage, benefits, and recommended practices for encrypting during backup.</span></span>  
  
  
##  <a name="overview"></a><a name="Overview"></a> <span data-ttu-id="690e5-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="690e5-105">Overview</span></span>  
 <span data-ttu-id="690e5-106">Начиная с [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], в SQL Server имеется возможность шифровать данные при создании резервных копий.</span><span class="sxs-lookup"><span data-stu-id="690e5-106">Starting in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SQL Server has the ability to encrypt the data while creating a backup.</span></span> <span data-ttu-id="690e5-107">Указав алгоритм шифрования и шифратор (сертификат или асимметричный ключ), можно задать для резервных копий создание зашифрованного файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="690e5-107">By specifying the encryption algorithm and the encryptor (a Certificate or Asymmetric Key) when creating a backup, you can create an encrypted backup file.</span></span> <span data-ttu-id="690e5-108">Все назначения хранилища: поддерживаются локальное хранилище и хранилище Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="690e5-108">All storage destinations: on-premises and Window Azure storage are supported.</span></span> <span data-ttu-id="690e5-109">Кроме того, можно настроить параметры шифрования для операций служб [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] (новая функция, введенная в [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="690e5-109">In addition, encryption options can be configured for [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] operations, a new feature introduced in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="690e5-110">Для шифрования резервной копии необходимо указать алгоритм шифрования и шифратор для защиты ключа шифрования.</span><span class="sxs-lookup"><span data-stu-id="690e5-110">To encrypt during backup, you must specify an encryption algorithm, and an encryptor to secure the encryption key.</span></span> <span data-ttu-id="690e5-111">Поддерживаются следующие варианты шифрования:</span><span class="sxs-lookup"><span data-stu-id="690e5-111">The following are the supported encryption options:</span></span>  
  
-   <span data-ttu-id="690e5-112">**Алгоритм шифрования:** поддерживаются следующие алгоритмы шифрования: AES 128, AES 192, AES 256 и Triple DES.</span><span class="sxs-lookup"><span data-stu-id="690e5-112">**Encryption Algorithm:** The supported encryption algorithms are: AES 128, AES 192, AES 256, and Triple DES</span></span>  
  
-   <span data-ttu-id="690e5-113">**Шифратор:** сертификат или асимметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="690e5-113">**Encryptor:** A certificate or asymmetric Key</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="690e5-114">Очень важно создать резервную копию сертификата или асимметричного ключа и предпочтительно в ином местоположении, чем зашифрованный ими файл резервной копии.</span><span class="sxs-lookup"><span data-stu-id="690e5-114">It is very important to back up the certificate or asymmetric key, and preferably to a different location than the backup file it was used to encrypt.</span></span> <span data-ttu-id="690e5-115">Без сертификата или асимметричного ключа резервную копию нельзя будет восстановить, т. е. файл резервной копии будет непригоден для использования.</span><span class="sxs-lookup"><span data-stu-id="690e5-115">Without the certificate or asymmetric key, you cannot restore the backup, rendering the backup file unusable.</span></span>  
  
 <span data-ttu-id="690e5-116">**Восстановление из зашифрованной резервной копии**. Восстановление SQL Server не требует указания никаких параметров шифрования во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="690e5-116">**Restoring the encrypted backup:** SQL Server restore does not require any encryption parameters to be specified during restores.</span></span> <span data-ttu-id="690e5-117">Для него требуется, чтобы сертификат или асимметричный ключ, использованный при шифровании файла резервной копии, был доступен в экземпляре, на который производится восстановление.</span><span class="sxs-lookup"><span data-stu-id="690e5-117">It does require that the certificate or the asymmetric key used to encrypt the backup file be available on the instance that you are restoring to.</span></span> <span data-ttu-id="690e5-118">Учетная запись пользователя, выполняющего восстановление, должна иметь разрешения `VIEW DEFINITION` на сертификат или ключ.</span><span class="sxs-lookup"><span data-stu-id="690e5-118">The user account performing the restore must have `VIEW DEFINITION` permissions on the certificate or key.</span></span> <span data-ttu-id="690e5-119">Если зашифрованная резервная копия восстанавливается на другой экземпляр, необходимо убедиться, что сертификат доступен на этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="690e5-119">If you are restoring the encrypted backup to a different instance, you must make sure that the certificate is available on that instance.</span></span>  
  
 <span data-ttu-id="690e5-120">При восстановлении резервной копии из базы данных c прозрачным шифрованием сертификат TDE должен быть доступен на экземпляре, на который производится восстановление.</span><span class="sxs-lookup"><span data-stu-id="690e5-120">If you are restoring a backup from a TDE encrypted database, the TDE certificate should be available on the instance you are restoring to.</span></span>  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="690e5-121">Преимущества</span><span class="sxs-lookup"><span data-stu-id="690e5-121">Benefits</span></span>  
  
1.  <span data-ttu-id="690e5-122">Шифрование резервных копий базы данных помогает обезопасить данные: SQL Server предоставляет возможность шифрования данных при создании резервных копий.</span><span class="sxs-lookup"><span data-stu-id="690e5-122">Encrypting the database backups helps secure the data: SQL Server provides the option to encrypt the backup data while creating a backup.</span></span>  
  
2.  <span data-ttu-id="690e5-123">Шифрование можно также использовать для баз данных, зашифрованных с помощью прозрачного шифрования.</span><span class="sxs-lookup"><span data-stu-id="690e5-123">Encryption can also be used for databases that are encrypted using TDE.</span></span>  
  
3.  <span data-ttu-id="690e5-124">Шифрование поддерживается для резервных копий, созданных с помощью служб [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)], предоставляющих дополнительную защиту для сторонних резервных копий.</span><span class="sxs-lookup"><span data-stu-id="690e5-124">Encryption is supported for backups done by [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)], which provides additional security for off-site backups.</span></span>  
  
4.  <span data-ttu-id="690e5-125">Эта функция поддерживает несколько алгоритмов шифрования вплоть до 256-битного AES.</span><span class="sxs-lookup"><span data-stu-id="690e5-125">This feature supports multiple encryption algorithms up to AES 256 bit.</span></span> <span data-ttu-id="690e5-126">Это дает возможность выбрать алгоритм, соответствующий требованиям.</span><span class="sxs-lookup"><span data-stu-id="690e5-126">This gives you the option to select an algorithm that aligns with your requirements.</span></span>  
  
5.  <span data-ttu-id="690e5-127">Ключи шифрования можно интегрировать с поставщиками расширенного управления ключами (EKM).</span><span class="sxs-lookup"><span data-stu-id="690e5-127">You can integrate encryption keys with Extended Key Management (EKM) providers.</span></span>  
  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="690e5-128">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="690e5-128">Prerequisites</span></span>  
 <span data-ttu-id="690e5-129">Предварительные требования, обязательные для шифрования резервной копии:</span><span class="sxs-lookup"><span data-stu-id="690e5-129">The following are prerequisites for encrypting a backup:</span></span>  
  
1.  <span data-ttu-id="690e5-130">**Создайте главный ключ базы данных для базы данных master**. Главный ключ базы данных — это симметричный ключ, который применяется для защиты закрытых ключей сертификатов и асимметричный ключей, которые есть в базе данных.</span><span class="sxs-lookup"><span data-stu-id="690e5-130">**Create a Database Master Key for the master database:** The database master key is a symmetric key that is used to protect the private keys of certificates and asymmetric keys that are present in the database.</span></span> <span data-ttu-id="690e5-131">Дополнительные сведения см. в разделе [Ключи шифрования базы данных и SQL Server (компонент Database Engine)](../security/encryption/sql-server-and-database-encryption-keys-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="690e5-131">For more information, see [SQL Server and Database Encryption Keys &#40;Database Engine&#41;](../security/encryption/sql-server-and-database-encryption-keys-database-engine.md).</span></span>  
  
2.  <span data-ttu-id="690e5-132">Создайте сертификат или асимметричный ключ для шифрования резервной копии.</span><span class="sxs-lookup"><span data-stu-id="690e5-132">Create a certificate or asymmetric Key to use for backup encryption.</span></span> <span data-ttu-id="690e5-133">Дополнительные сведения о создании сертификата см. в разделе [CREATE CERTIFICATE (Transact-SQL)](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="690e5-133">For more information on creating a certificate, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span> <span data-ttu-id="690e5-134">Дополнительные сведения о создании асимметричного ключа см. в разделе [CREATE ASYMMETRIC KEY (Transact-SQL)](/sql/t-sql/statements/create-asymmetric-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="690e5-134">For more information on creating an asymmetric key, see [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="690e5-135">Поддерживаются только асимметричные ключи, относящиеся к расширенному управлению ключами (EKM).</span><span class="sxs-lookup"><span data-stu-id="690e5-135">Only asymmetric keys residing in an Extended Key Management (EKM) are supported.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="690e5-136">Ограничения</span><span class="sxs-lookup"><span data-stu-id="690e5-136">Restrictions</span></span>  
 <span data-ttu-id="690e5-137">К параметрам шифрования применяются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="690e5-137">The following are restrictions that apply to the encryption options:</span></span>  
  
-   <span data-ttu-id="690e5-138">При шифровании резервной копии с помощью асимметричного ключа поддерживаются только асимметричные ключи, находящиеся в поставщике расширенного управления ключами.</span><span class="sxs-lookup"><span data-stu-id="690e5-138">If you are using asymmetric key to encrypt the backup data, only asymmetric keys residing in the EKM provider are supported.</span></span>  
  
-   <span data-ttu-id="690e5-139">SQL Server Express и SQL Server Web не поддерживают шифрование при резервном копировании.</span><span class="sxs-lookup"><span data-stu-id="690e5-139">SQL Server Express and SQL Server Web do not support encryption during backup.</span></span> <span data-ttu-id="690e5-140">Однако восстановление из зашифрованной резервной копии в экземпляр SQL Server Express или SQL Server Web поддерживается.</span><span class="sxs-lookup"><span data-stu-id="690e5-140">However restoring from an encrypted backup to an instance of SQL Server Express or SQL Server Web is supported.</span></span>  
  
-   <span data-ttu-id="690e5-141">В предыдущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] считывание зашифрованных резервных копий не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="690e5-141">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read encrypted backups.</span></span>  
  
-   <span data-ttu-id="690e5-142">Присоединение к существующему резервному набору данных для зашифрованных резервных копий не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="690e5-142">Appending to an existing backup set option is not supported for encrypted backups.</span></span>  
  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="690e5-143">Permissions</span><span class="sxs-lookup"><span data-stu-id="690e5-143">Permissions</span></span>  
 <span data-ttu-id="690e5-144">**Для шифрования резервной копии или восстановления из зашифрованной резервной копии требуется следующее:**</span><span class="sxs-lookup"><span data-stu-id="690e5-144">**To encrypt a backup or to restore from an encrypted backup:**</span></span>  
  
 <span data-ttu-id="690e5-145">Разрешение `VIEW DEFINITION` на сертификат или асимметричный ключ, используемый для шифрования резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="690e5-145">`VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database backup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="690e5-146">Доступ к сертификату TDE для резервного копирования или восстановления базы данных, защищенной прозрачным шифрованием, не требуется.</span><span class="sxs-lookup"><span data-stu-id="690e5-146">Access to the TDE certificate is not required to back up or restore a TDE protected database.</span></span>  
  
##  <a name="backup-encryption-methods"></a><a name="Methods"></a> <span data-ttu-id="690e5-147">Методы шифрования резервной копии</span><span class="sxs-lookup"><span data-stu-id="690e5-147">Backup Encryption Methods</span></span>  
 <span data-ttu-id="690e5-148">В разделах ниже представлен краткий обзор шагов шифрования данных при резервном копировании.</span><span class="sxs-lookup"><span data-stu-id="690e5-148">The sections below provide a brief introduction to the steps to encrypting the data during backup.</span></span> <span data-ttu-id="690e5-149">Полное пошаговое руководство по различным этапам шифрования резервных копий с помощью Transact-SQL см. в разделе [Создание зашифрованной резервной копии](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="690e5-149">For a complete walkthrough of the different steps of encrypting your backup using Transact-SQL, see [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
### <a name="using-sql-server-management-studio"></a><span data-ttu-id="690e5-150">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="690e5-150">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="690e5-151">Резервную копию базы данных можно зашифровать при ее создании в одном из следующих диалоговых окон:</span><span class="sxs-lookup"><span data-stu-id="690e5-151">You can encrypt a backup when creating the backup of a database in any of the following dialog boxes:</span></span>  
  
1.  <span data-ttu-id="690e5-152">[Резервное копирование базы данных (страница "Параметры резервного копирования")](back-up-database-backup-options-page.md) На странице **Параметры резервного копирования** можно выбрать **Шифрование** и указать алгоритм шифрования и сертификат или асимметричный ключ, используемый для него.</span><span class="sxs-lookup"><span data-stu-id="690e5-152">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) On the **Backup Options** page, you can select **Encryption**, and specify the encryption algorithm and the certificate or asymmetric key to use for the encryption.</span></span>  
  
2.  <span data-ttu-id="690e5-153">[Использование мастера планов обслуживания](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure) При выборе задачи резервного копирования на вкладке **Параметры** страницы **Определение задач резервного копирования** можно выбрать **Шифрование резервной копии**и указать алгоритм шифрования и ключ или сертификат, используемый для него.</span><span class="sxs-lookup"><span data-stu-id="690e5-153">[Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure) When you select a backup task, on the **Options** tab of the **Define Backup ()Task** page, you can select **Backup Encryption**, and specify the encryption algorithm and the certificate or key to use for the encryption.</span></span>  
  
### <a name="using-transact-sql"></a><span data-ttu-id="690e5-154">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="690e5-154">Using Transact SQL</span></span>  
 <span data-ttu-id="690e5-155">Ниже приведен пример инструкции Transact-SQL для шифрования файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="690e5-155">Following is a sample Transact-SQL statement to encrypt the backup file:</span></span>  
  
```sql
BACKUP DATABASE [MYTestDB]  
TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
WITH  
  COMPRESSION,  
  ENCRYPTION   
   (  
   ALGORITHM = AES_256,  
   SERVER CERTIFICATE = BackupEncryptCert  
   ),  
  STATS = 10  
GO
```  
  
 <span data-ttu-id="690e5-156">Полный синтаксис инструкции Transact-SQL см. в разделе [BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="690e5-156">For the full Transact-SQL statement syntax, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="using-powershell"></a><span data-ttu-id="690e5-157">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="690e5-157">Using PowerShell</span></span>  
 <span data-ttu-id="690e5-158">В этом примере создаются параметры шифрования, которые используются в качестве значения параметра в командлете **Backup-SqlDatabase** для создания зашифрованной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="690e5-158">This example creates the encryption options and uses it as a parameter value in **Backup-SqlDatabase** cmdlet to create an encrypted backup.</span></span>  
  
```powershell
$encryptionOption = New-SqlBackupEncryptionOption -Algorithm Aes256 -EncryptorType ServerCertificate -EncryptorName "BackupCert"  
Backup-SqlDatabase -ServerInstance . -Database "MyTestDB" -BackupFile "MyTestDB.bak" -CompressionOption On -EncryptionOption $encryptionOption  
```  
  
##  <a name="recommended-practices"></a><a name="RecommendedPractices"></a> <span data-ttu-id="690e5-159">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="690e5-159">Recommended Practices</span></span>  
 <span data-ttu-id="690e5-160">Создавайте резервную копию сертификата и ключей шифрования в каталоге, отличном от локального компьютера, где установлен экземпляр.</span><span class="sxs-lookup"><span data-stu-id="690e5-160">Create a backup of the encryption certificate and keys to a location other than your local machine where the instance is installed.</span></span> <span data-ttu-id="690e5-161">С учетом сценариев аварийного восстановления рекомендуется сохранять резервную копию сертификата или ключа в стороннем местоположении.</span><span class="sxs-lookup"><span data-stu-id="690e5-161">To account for disaster recovery scenarios, consider storing a backup of the certificate or key to an off-site location.</span></span> <span data-ttu-id="690e5-162">Восстановить зашифрованную резервную копию без сертификата, использованного при ее шифровании, нельзя.</span><span class="sxs-lookup"><span data-stu-id="690e5-162">You cannot restore an encrypted backup without the certificate used to encrypt the backup.</span></span>  
  
 <span data-ttu-id="690e5-163">Для восстановления зашифрованной резервной копии первоначальный сертификат, используемый при создании резервной копии, а также соответствующий ему отпечаток должны быть доступны на экземпляре, где производится восстановление.</span><span class="sxs-lookup"><span data-stu-id="690e5-163">To restore an encrypted backup, the original certificate used when the backup was taken with the matching thumbprint should be available on the instance you are restoring to.</span></span> <span data-ttu-id="690e5-164">Поэтому сертификат не должен быть возобновлен по истечении срока или изменен каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="690e5-164">Therefore, the certificate should not be renewed on expiry or changed in any way.</span></span> <span data-ttu-id="690e5-165">Возобновление может привести к обновлению сертификата, запускающему изменение отпечатка сертификата, из-за чего сертификат станет недействительным для файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="690e5-165">Renewal can result in updating the certificate triggering the change of the thumbprint, therefore making the certificate invalid for the backup file.</span></span> <span data-ttu-id="690e5-166">Учетная запись, выполняющая восстановление, должна иметь разрешения VIEW DEFINITION на сертификат или асимметричный ключ, использованные для шифрования резервной копии.</span><span class="sxs-lookup"><span data-stu-id="690e5-166">The account performing the restore should have VIEW DEFINITION permissions on the certificate or the asymmetric key used to encrypt during backup.</span></span>  
  
 <span data-ttu-id="690e5-167">Резервное копирование баз данных группы доступности обычно выполняется на предпочитаемой резервной реплике.</span><span class="sxs-lookup"><span data-stu-id="690e5-167">Availability Group database backups are typically performed on the preferred backup replica.</span></span>  <span data-ttu-id="690e5-168">При восстановлении резервной копии на реплике, отличной от той, на которой эта резервная копия была сделана, убедитесь, что исходный сертификат для резервной копии доступен на той реплике, где производится восстановление.</span><span class="sxs-lookup"><span data-stu-id="690e5-168">If restoring a backup on a replica other than where the backup was taken from, ensure that the original certificate used for backup is available on the replica you are restoring to.</span></span>  
  
 <span data-ttu-id="690e5-169">Если в базе данных включено TDE, выберите различные сертификаты или асимметричные ключи для шифрования базы данных и резервной копии для повышения безопасности.</span><span class="sxs-lookup"><span data-stu-id="690e5-169">If the database is TDE enabled, choose different certificates or asymmetric keys for encrypting the database and the backup to increase security.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="690e5-170">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="690e5-170">Related Tasks</span></span>  
  
|<span data-ttu-id="690e5-171">Раздел или задача</span><span class="sxs-lookup"><span data-stu-id="690e5-171">Topic/Task</span></span>|<span data-ttu-id="690e5-172">Описание</span><span class="sxs-lookup"><span data-stu-id="690e5-172">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="690e5-173">Создание зашифрованной резервной копии</span><span class="sxs-lookup"><span data-stu-id="690e5-173">Create an Encrypted Backup</span></span>](create-an-encrypted-backup.md)|<span data-ttu-id="690e5-174">Описывает основные шаги, которые необходимо выполнить, чтобы создать зашифрованную резервную копию.</span><span class="sxs-lookup"><span data-stu-id="690e5-174">Describes the basic steps required to create an encrypted backup</span></span>|  
|[<span data-ttu-id="690e5-175">Управляемое резервное копирование SQL Server в Azure — настройки периода хранения и хранилища</span><span class="sxs-lookup"><span data-stu-id="690e5-175">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)|<span data-ttu-id="690e5-176">Описывает основные шаги, необходимые для настройки [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] с указанием параметров шифрования.</span><span class="sxs-lookup"><span data-stu-id="690e5-176">Describes the basic steps required to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with the encryption options specified.</span></span>|  
|[<span data-ttu-id="690e5-177">Расширенное управление ключами с помощью хранилища ключей Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="690e5-177">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md)|<span data-ttu-id="690e5-178">Предоставлен пример создания зашифрованной резервной копии, защищенной ключами в хранилище ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="690e5-178">Provides an example of creating an encrypted backup protected by keys in the Azure Key Vault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="690e5-179">См. также:</span><span class="sxs-lookup"><span data-stu-id="690e5-179">See Also</span></span>  
 [<span data-ttu-id="690e5-180">Общие сведения о резервном копировании (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="690e5-180">Backup Overview &#40;SQL Server&#41;</span></span>](backup-overview-sql-server.md)  
  
  
