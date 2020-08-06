---
title: Резервное копирование в SQL Server по URL-адресу | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 11be89e9-ff2a-4a94-ab5d-27d8edf9167d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6918a099e00b1de9e773320b5c6c0e4089859e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734194"
---
# <a name="sql-server-backup-to-url"></a><span data-ttu-id="1cd07-102">Резервное копирование в SQL Server по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="1cd07-102">SQL Server Backup to URL</span></span>
  <span data-ttu-id="1cd07-103">В этом разделе представлены основные понятия, требования и компоненты, необходимые для использования службы хранилища BLOB-объектов Azure в качестве места назначения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="1cd07-103">This topic introduces the concepts, requirements and components necessary to use the Azure Blob storage service as a backup destination.</span></span> <span data-ttu-id="1cd07-104">Функции резервного копирования и восстановления аналогичны при использовании DISK и TAPE, но имеют некоторые отличия.</span><span class="sxs-lookup"><span data-stu-id="1cd07-104">The backup and restore functionality are same or similar to when using DISK or TAPE, with a few differences.</span></span> <span data-ttu-id="1cd07-105">В данном разделе описаны различия и все важные исключения, а также приведено несколько примеров кода.</span><span class="sxs-lookup"><span data-stu-id="1cd07-105">The differences are and any notable exceptions, and a few code examples are included in this topic.</span></span>  
  
## <a name="requirements-components-and-concepts"></a><span data-ttu-id="1cd07-106">Требования, компоненты и основные понятия</span><span class="sxs-lookup"><span data-stu-id="1cd07-106">Requirements, Components, and Concepts</span></span>  
 <span data-ttu-id="1cd07-107">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="1cd07-107">**In this section:**</span></span>  
  
-   [<span data-ttu-id="1cd07-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1cd07-108">Security</span></span>](#security)  
  
-   [<span data-ttu-id="1cd07-109">Введение в основные компоненты и понятия</span><span class="sxs-lookup"><span data-stu-id="1cd07-109">Introduction to Key Components and Concepts</span></span>](#intorkeyconcepts)  
  
-   [<span data-ttu-id="1cd07-110">Служба хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="1cd07-110">Azure Blob Storage Service</span></span>](#Blob)  
  
-   [<span data-ttu-id="1cd07-111">Компоненты SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cd07-111">SQL Server Components</span></span>](#sqlserver)  
  
-   [<span data-ttu-id="1cd07-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1cd07-112">Limitations</span></span>](#limitations)  
  
-   [<span data-ttu-id="1cd07-113">Поддержка инструкций Backup/Restore</span><span class="sxs-lookup"><span data-stu-id="1cd07-113">Support for Backup/Restore Statements</span></span>](#Support)  
  
-   [<span data-ttu-id="1cd07-114">Использование задачи резервного копирования в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1cd07-114">Using Backup Task in SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#BackupTaskSSMS)  
  
-   [<span data-ttu-id="1cd07-115">Резервное копирование SQL Server на URL-адрес с помощью мастера планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="1cd07-115">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>](sql-server-backup-to-url.md#MaintenanceWiz)  
  
-   [<span data-ttu-id="1cd07-116">Восстановление из хранилища Azure с помощью SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1cd07-116">Restoring from Azure storage Using SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#RestoreSSMS)  
  
###  <a name="security"></a><a name="security"></a> <span data-ttu-id="1cd07-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="1cd07-117">Security</span></span>  
 <span data-ttu-id="1cd07-118">Ниже приведены рекомендации по безопасности и требования к резервному копированию или восстановлению из служб хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-118">The following are security considerations and requirements when backing up to or restoring from the Azure Blob storage services.</span></span>  
  
-   <span data-ttu-id="1cd07-119">При создании контейнера для службы хранилища BLOB-объектов Azure рекомендуется установить доступ к **частному**.</span><span class="sxs-lookup"><span data-stu-id="1cd07-119">When creating a container for the Azure Blob storage service, we recommend that you set the access to **private**.</span></span> <span data-ttu-id="1cd07-120">Установка закрытых прав доступа означает, что доступ получают только те пользователи и учетные записи, которые могут предоставить необходимую информацию для проверки подлинности в учетной записи Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-120">Setting the access to private restricts the access to users or accounts able to provide the necessary information to authenticate to the Azure account.</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1cd07-121">требует, чтобы имя учетной записи Azure и проверка подлинности ключей доступа хранились в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1cd07-121">requires Azure account name and access key authentication to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential.</span></span> <span data-ttu-id="1cd07-122">Эти сведения используются для проверки подлинности учетной записи Azure при выполнении операций резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="1cd07-122">This information is used to authenticate to the Azure account when it performs backup or restore operations.</span></span>  
  
-   <span data-ttu-id="1cd07-123">Учетная запись пользователя, применяемая для выдачи команды BACKUP или RESTORE, должна находиться в роли базы данных **db_backup operator** с разрешениями **Alter any credential** .</span><span class="sxs-lookup"><span data-stu-id="1cd07-123">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
###  <a name="introduction-to-key-components-and-concepts"></a><a name="intorkeyconcepts"></a><span data-ttu-id="1cd07-124">Общие сведения о ключевых компонентах и концепциях</span><span class="sxs-lookup"><span data-stu-id="1cd07-124">Introduction to Key Components and Concepts</span></span>  
 <span data-ttu-id="1cd07-125">В следующих двух разделах представлены службы хранилища BLOB-объектов Azure, а также [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] компоненты, используемые при резервном копировании или восстановлении из службы хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-125">The following two sections introduce the Azure Blob storage service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components used when backing up to or restoring from the Azure Blob storage service.</span></span> <span data-ttu-id="1cd07-126">Важно понимать компоненты и взаимодействие между ними, чтобы выполнить резервное копирование или восстановление из службы хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-126">It is important to understand the components and the interaction between them to do a backup to or restore from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="1cd07-127">Создание учетной записи Azure является первым этапом этого процесса.</span><span class="sxs-lookup"><span data-stu-id="1cd07-127">Creating an Azure account is the first step to this process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1cd07-128">использует **имя учетной записи хранения Azure** и ее значения **ключа доступа** для проверки подлинности, записи и чтения больших двоичных объектов в службе хранилища.</span><span class="sxs-lookup"><span data-stu-id="1cd07-128">uses the **Azure storage account name** and its **access key** values to authenticate and write and read blobs to the storage service.</span></span> <span data-ttu-id="1cd07-129">Учетные данные службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] хранят эту информацию для проверки подлинности и используются при выполнении операций резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="1cd07-129">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential stores this authentication information and is used during the backup or restore operations.</span></span> <span data-ttu-id="1cd07-130">Полное пошаговое руководство по созданию учетной записи хранения и выполнению простого восстановления см. в статье [руководство по использованию службы хранилища Azure для SQL Server резервного копирования и восстановления](https://go.microsoft.com/fwlink/?LinkId=271615).</span><span class="sxs-lookup"><span data-stu-id="1cd07-130">For a complete walkthrough of creating a storage account and performing a simple restore, see [Tutorial Using Azure Storage Service for SQL Server Backup and Restore](https://go.microsoft.com/fwlink/?LinkId=271615).</span></span>  
  
 <span data-ttu-id="1cd07-131">![сопоставление учетной записи хранилища с учетными данными SQL](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "сопоставление учетной записи хранилища с учетными данными SQL")</span><span class="sxs-lookup"><span data-stu-id="1cd07-131">![mapping storage account to sql credentials](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
###  <a name="azure-blob-storage-service"></a><a name="Blob"></a><span data-ttu-id="1cd07-132">Служба хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="1cd07-132">Azure Blob Storage Service</span></span>  
 <span data-ttu-id="1cd07-133">**Учетная запись хранения**. Учетная запись хранения является отправной точкой для всех служб хранилища.</span><span class="sxs-lookup"><span data-stu-id="1cd07-133">**Storage Account:** The storage account is the starting point for all storage services.</span></span> <span data-ttu-id="1cd07-134">Чтобы получить доступ к службе хранилища BLOB-объектов Azure, сначала создайте учетную запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-134">To access the Azure Blob Storage service, first create an Azure storage account.</span></span> <span data-ttu-id="1cd07-135">**Имя учетной записи хранения** и ее свойства **ключа доступа** необходимы для проверки подлинности в службе хранилища BLOB-объектов Azure и ее компонентах.</span><span class="sxs-lookup"><span data-stu-id="1cd07-135">The **storage account name** and its **access key** properties are required to authenticate to the Azure Blob Storage service and its components.</span></span>  
  
 <span data-ttu-id="1cd07-136">**Контейнер:** Контейнер предоставляет Группирование набора больших двоичных объектов и может хранить неограниченное количество больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="1cd07-136">**Container:** A container provides a grouping of a set of Blobs, and can store an unlimited number of Blobs.</span></span> <span data-ttu-id="1cd07-137">Чтобы создать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] резервную копию в службе BLOB-объектов Azure, необходимо создать по крайней мере корневой контейнер.</span><span class="sxs-lookup"><span data-stu-id="1cd07-137">To write a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to the Azure Blob service, you must have at least the root container created.</span></span>  
  
 <span data-ttu-id="1cd07-138">**Большой двоичный объект**. Файл любого типа и размера.</span><span class="sxs-lookup"><span data-stu-id="1cd07-138">**Blob:** A file of any type and size.</span></span> <span data-ttu-id="1cd07-139">Существует два типа больших двоичных объектов, которые можно хранить в службе хранилища больших двоичных объектов Azure: блочные и страничные BLOB-объекты.</span><span class="sxs-lookup"><span data-stu-id="1cd07-139">There are two types of blobs that can be stored in the Azure Blob storage service: block and page blobs.</span></span> <span data-ttu-id="1cd07-140">В резервном копировании [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используются страничные большие двоичные объекты.</span><span class="sxs-lookup"><span data-stu-id="1cd07-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup uses page Blobs as the Blob type.</span></span> <span data-ttu-id="1cd07-141">Для адресации больших двоичных объектов используется следующий формат URL-адреса: https:// \<storage account> . BLOB.Core.Windows.NET/\<container>/\<blob></span><span class="sxs-lookup"><span data-stu-id="1cd07-141">Blobs are addressable using the following URL format: https://\<storage account>.blob.core.windows.net/\<container>/\<blob></span></span>  
  
 <span data-ttu-id="1cd07-142">![Хранилище BLOB-объектов Azure](../../database-engine/media/backuptocloud-blobarchitecture.gif "хранилище BLOB-объектов Azure")</span><span class="sxs-lookup"><span data-stu-id="1cd07-142">![Azure Blob Storage](../../database-engine/media/backuptocloud-blobarchitecture.gif "Azure Blob Storage")</span></span>  
  
 <span data-ttu-id="1cd07-143">Дополнительные сведения о службе хранилища BLOB-объектов Azure см. в статье [Использование службы хранилища BLOB-объектов Azure](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/) .</span><span class="sxs-lookup"><span data-stu-id="1cd07-143">For more information about the Azure Blob storage service, see [How to use the Azure Blob Storage Service](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span></span>  
  
 <span data-ttu-id="1cd07-144">Дополнительные сведения о страничных BLOB-объектах см. в статье [Understanding Block and Page Blobs](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx) (Основные сведения о блочных, добавочных и страничных BLOB-объектах).</span><span class="sxs-lookup"><span data-stu-id="1cd07-144">For more information about page Blobs, see [Understanding Block and Page Blobs](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span></span>  
  
###  <a name="ssnoversion-components"></a><span data-ttu-id="1cd07-145">Компоненты <a name="sqlserver"></a> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cd07-145"><a name="sqlserver"></a> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components</span></span>  
 <span data-ttu-id="1cd07-146">**URL-адрес**. URL-адрес определяет универсальный идентификатор ресурса (URI) для уникального файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="1cd07-146">**URL:** A URL specifies a Uniform Resource Identifier (URI) to a unique backup file.</span></span> <span data-ttu-id="1cd07-147">URL-адрес используется для предоставления местоположения и имени файла резервной копии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cd07-147">The URL is used to provide the location and name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup file.</span></span> <span data-ttu-id="1cd07-148">В этой реализации единственным допустимым URL-адресом является тот, который указывает на страничный BLOB-объект в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-148">In this implementation, the only valid URL is one that points to a page Blob in an Azure storage account.</span></span> <span data-ttu-id="1cd07-149">URL-адрес должен указывать на фактический большой двоичный объект, а не просто контейнер.</span><span class="sxs-lookup"><span data-stu-id="1cd07-149">The URL must point to an actual Blob, not just a container.</span></span> <span data-ttu-id="1cd07-150">Если большой двоичный объект не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="1cd07-150">If the Blob does not exist, it is created.</span></span> <span data-ttu-id="1cd07-151">Если указан существующий большой двоичный объект, происходит сбой резервного копирования, если не указан параметр «WITH FORMAT».</span><span class="sxs-lookup"><span data-stu-id="1cd07-151">If an existing Blob is specified, BACKUP fails, unless the "WITH FORMAT" option is specified.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="1cd07-152">Если вы решили скопировать и передать файл резервной копии в службу хранилища больших двоичных объектов Azure, используйте страничный BLOB-объект в качестве хранилища.</span><span class="sxs-lookup"><span data-stu-id="1cd07-152">If you choose to copy and upload a backup file to the Azure Blob storage service, use page blob as your storage option.</span></span> <span data-ttu-id="1cd07-153">Восстановление из блочных больших двоичных объектов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-153">Restores from Block Blobs are not supported.</span></span> <span data-ttu-id="1cd07-154">Попытка выполнить RESTORE из большого двоичного объекта блочного типа приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="1cd07-154">RESTORE from a block blob type fails with an error.</span></span>  
  
 <span data-ttu-id="1cd07-155">Ниже приведен пример значения URL-адреса: HTTP [s]://Аккаунтнаме.блоб.коре.Виндовс.нет/ \<CONTAINER> / \<FILENAME.bak> .</span><span class="sxs-lookup"><span data-stu-id="1cd07-155">Here is a sample URL value: http[s]://ACCOUNTNAME.Blob.core.windows.net/\<CONTAINER>/\<FILENAME.bak>.</span></span> <span data-ttu-id="1cd07-156">Указывать HTTPS необязательно, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="1cd07-156">HTTPS is not required, but is recommended.</span></span>  
  
 <span data-ttu-id="1cd07-157">**Учетные данные**. Учетные данные [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] являются объектом, который используется для хранения информации о проверке подлинности, которая необходима для подключения к источнику за пределами SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1cd07-157">**Credential:** A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="1cd07-158">Здесь [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] процессы резервного копирования и восстановления используют учетные данные для проверки подлинности в службе хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-158">Here, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="1cd07-159">Учетные данные хранят имя учетной записи хранилища и значения **ключа доступа** учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="1cd07-159">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="1cd07-160">После создания учетных данных их необходимо указать в параметре WITH CREDENTIAL при выполнении инструкций BACKUP/RESTORE.</span><span class="sxs-lookup"><span data-stu-id="1cd07-160">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="1cd07-161">Дополнительную информацию о просмотре, копировании или повторном создании учетной записи хранилища **access keys**см. в разделе [Ключи доступа к учетной записи](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cd07-161">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="1cd07-162">Пошаговые инструкции по созданию учетных данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в примере [Create a Credential](#credential) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1cd07-162">For step by step instructions about how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential, see [Create a Credential](#credential) example later in this topic.</span></span>  
  
 <span data-ttu-id="1cd07-163">Общие сведения об учетных данных см. в разделе [Учетные данные](../security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="1cd07-163">For general information about credentials, see [Credentials](../security/authentication-access/credentials-database-engine.md)</span></span>  
  
 <span data-ttu-id="1cd07-164">Дополнительные сведения о других примерах использования учетных данных см. в статье [создание агент SQL Server прокси-сервера](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="1cd07-164">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
###  <a name="limitations"></a><a name="limitations"></a> <span data-ttu-id="1cd07-165">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1cd07-165">Limitations</span></span>  
  
-   <span data-ttu-id="1cd07-166">Резервное копирование в хранилище класса Premium не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-166">Backup to premium storage is not supported.</span></span>  
  
-   <span data-ttu-id="1cd07-167">Максимальный поддерживаемый размер резервной копии — 1 ТБ.</span><span class="sxs-lookup"><span data-stu-id="1cd07-167">The maximum backup size supported is 1 TB.</span></span>  
  
-   <span data-ttu-id="1cd07-168">Инструкции резервного копирования и восстановления можно выполнить с помощью TSQL, SMO и командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1cd07-168">You can issue backup or restore statements by using TSQL, SMO, or PowerShell cmdlets.</span></span> <span data-ttu-id="1cd07-169">Резервное копирование или восстановление из службы хранилища BLOB-объектов Azure с помощью SQL Server Management Studio мастер резервного копирования или восстановления в настоящее время не включен.</span><span class="sxs-lookup"><span data-stu-id="1cd07-169">A backup to or restoring from the Azure Blob storage service by using SQL Server Management Studio Backup or Restore wizard is not currently enabled.</span></span>  
  
-   <span data-ttu-id="1cd07-170">Функция создания логического имени устройства не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-170">Creating a logical device name is not supported.</span></span> <span data-ttu-id="1cd07-171">Таким образом, не поддерживается функция добавления URL-адреса в качестве устройства резервного копирования с помощью sp_dumpdevice или SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="1cd07-171">So adding URL as a backup device using sp_dumpdevice or through SQL Server Management Studio is not supported.</span></span>  
  
-   <span data-ttu-id="1cd07-172">Функция присоединения к существующим резервным большим двоичным объектам не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-172">Appending to existing backup blobs is not supported.</span></span> <span data-ttu-id="1cd07-173">Создать резервную копию в существующем большом двоичном объекте можно только путем перезаписи с помощью параметра WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="1cd07-173">Backups to an existing Blob can only be overwritten by using the WITH FORMAT option.</span></span>  
  
-   <span data-ttu-id="1cd07-174">Функция создания резервных копий в нескольких больших двоичных объектах в одной операции резервного копирования не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-174">Backup to multiple blobs in a single backup operation is not supported.</span></span> <span data-ttu-id="1cd07-175">К примеру, следующие действия приводят к ошибке.</span><span class="sxs-lookup"><span data-stu-id="1cd07-175">For example, the following returns an error:</span></span>  
  
    ```sql
    BACKUP DATABASE AdventureWorks2012
    TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_1.bak'
       URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_2.bak'
          WITH CREDENTIAL = 'mycredential'
         ,STATS = 5;  
    GO
    ```  
  
-   <span data-ttu-id="1cd07-176">Функция указания размера блока с помощью `BACKUP` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-176">Specifying a block size with `BACKUP` is not supported.</span></span>  
  
-   <span data-ttu-id="1cd07-177">Функция указания `MAXTRANSFERSIZE` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-177">Specifying `MAXTRANSFERSIZE` is not supported.</span></span>  
  
-   <span data-ttu-id="1cd07-178">Указание набора параметров резервного набора данных `RETAINDAYS` и `EXPIREDATE` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-178">Specifying backupset options - `RETAINDAYS` and `EXPIREDATE` are not supported.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1cd07-179">— 259 символов.</span><span class="sxs-lookup"><span data-stu-id="1cd07-179">has a maximum limit of 259 characters for a backup device name.</span></span> <span data-ttu-id="1cd07-180">Функция BACKUP TO URL использует 36 символов для необходимых элементов, которые нужны для указания URL (https://.blob.core.windows.net//.bak ), оставляя 223 символа для имен учетной записи, контейнера и большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="1cd07-180">The BACKUP TO URL consumes 36 characters for the required elements used to specify the URL - 'https://.blob.core.windows.net//.bak', leaving 223 characters for account, container, and blob names put together.</span></span>  
  
###  <a name="support-for-backuprestore-statements"></a><a name="Support"></a> <span data-ttu-id="1cd07-181">Поддержка инструкций резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="1cd07-181">Support for Backup/Restore Statements</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1cd07-182">Инструкции BACKUP и RESTORE</span><span class="sxs-lookup"><span data-stu-id="1cd07-182">Backup/Restore Statement</span></span>|<span data-ttu-id="1cd07-183">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1cd07-183">Supported</span></span>|<span data-ttu-id="1cd07-184">Исключения</span><span class="sxs-lookup"><span data-stu-id="1cd07-184">Exceptions</span></span>|<span data-ttu-id="1cd07-185">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1cd07-185">Comments</span></span>|  
|<span data-ttu-id="1cd07-186">BACKUP</span><span class="sxs-lookup"><span data-stu-id="1cd07-186">BACKUP</span></span>|<span data-ttu-id="1cd07-187">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-187">&#x2713;</span></span>|<span data-ttu-id="1cd07-188">BLOCKSIZE и MAXTRANSFERSIZE не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1cd07-188">BLOCKSIZE, and MAXTRANSFERSIZE are not supported.</span></span>|<span data-ttu-id="1cd07-189">Необходимо использовать инструкцию WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-189">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1cd07-190">RESTORE</span><span class="sxs-lookup"><span data-stu-id="1cd07-190">RESTORE</span></span>|<span data-ttu-id="1cd07-191">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-191">&#x2713;</span></span>||<span data-ttu-id="1cd07-192">Необходимо использовать инструкцию WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-192">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1cd07-193">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="1cd07-193">RESTORE FILELISTONLY</span></span>|<span data-ttu-id="1cd07-194">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-194">&#x2713;</span></span>||<span data-ttu-id="1cd07-195">Необходимо использовать инструкцию WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-195">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1cd07-196">инструкция RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="1cd07-196">RESTORE HEADERONLY</span></span>|<span data-ttu-id="1cd07-197">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-197">&#x2713;</span></span>||<span data-ttu-id="1cd07-198">Необходимо использовать инструкцию WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-198">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1cd07-199">RESTORE LABELONLY</span><span class="sxs-lookup"><span data-stu-id="1cd07-199">RESTORE LABELONLY</span></span>|<span data-ttu-id="1cd07-200">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-200">&#x2713;</span></span>||<span data-ttu-id="1cd07-201">Необходимо использовать инструкцию WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-201">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1cd07-202">RESTORE VERIFYONLY</span><span class="sxs-lookup"><span data-stu-id="1cd07-202">RESTORE VERIFYONLY</span></span>|<span data-ttu-id="1cd07-203">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-203">&#x2713;</span></span>||<span data-ttu-id="1cd07-204">Необходимо использовать инструкцию WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-204">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1cd07-205">RESTORE REWINDONLY</span><span class="sxs-lookup"><span data-stu-id="1cd07-205">RESTORE REWINDONLY</span></span>|<span data-ttu-id="1cd07-206">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-206">&#x2713;</span></span>|||  
  
 <span data-ttu-id="1cd07-207">Общую информацию и синтаксис инструкций резервного копирования см. в разделе [BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1cd07-207">For syntax and general information about backup statements, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="1cd07-208">Общую информацию и синтаксис инструкций восстановления см. в разделе [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1cd07-208">For syntax and general information about restore statements, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
### <a name="support-for-backup-arguments"></a><span data-ttu-id="1cd07-209">Поддержка аргументов резервного копирования</span><span class="sxs-lookup"><span data-stu-id="1cd07-209">Support for Backup Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1cd07-210">Аргумент</span><span class="sxs-lookup"><span data-stu-id="1cd07-210">Argument</span></span>|<span data-ttu-id="1cd07-211">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1cd07-211">Supported</span></span>|<span data-ttu-id="1cd07-212">Исключение</span><span class="sxs-lookup"><span data-stu-id="1cd07-212">Exception</span></span>|<span data-ttu-id="1cd07-213">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1cd07-213">Comments</span></span>|  
|<span data-ttu-id="1cd07-214">DATABASE</span><span class="sxs-lookup"><span data-stu-id="1cd07-214">DATABASE</span></span>|<span data-ttu-id="1cd07-215">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-215">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-216">LOG</span><span class="sxs-lookup"><span data-stu-id="1cd07-216">LOG</span></span>|<span data-ttu-id="1cd07-217">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-217">&#x2713;</span></span>|||  
||  
|<span data-ttu-id="1cd07-218">TO (URL)</span><span class="sxs-lookup"><span data-stu-id="1cd07-218">TO (URL)</span></span>|<span data-ttu-id="1cd07-219">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-219">&#x2713;</span></span>|<span data-ttu-id="1cd07-220">В отличие от DISK и TAPE URL-адрес не поддерживает функцию указания или создания логического имени.</span><span class="sxs-lookup"><span data-stu-id="1cd07-220">Unlike DISK and TAPE, URL does not support specifying or creating a logical name.</span></span>|<span data-ttu-id="1cd07-221">Этот аргумент используется, чтобы указать URL-адрес для файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="1cd07-221">This argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="1cd07-222">MIRROR TO</span><span class="sxs-lookup"><span data-stu-id="1cd07-222">MIRROR TO</span></span>|<span data-ttu-id="1cd07-223">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-223">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-224">**WITH OPTIONS:**</span><span class="sxs-lookup"><span data-stu-id="1cd07-224">**WITH OPTIONS:**</span></span>||||  
|<span data-ttu-id="1cd07-225">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-225">CREDENTIAL</span></span>|<span data-ttu-id="1cd07-226">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-226">&#x2713;</span></span>||<span data-ttu-id="1cd07-227">С УЧЕТными данными поддерживается только при использовании параметра BACKUP TO URL для резервного копирования в службу хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-227">WITH CREDENTIAL is only supported when using BACKUP TO URL option to back up to the Azure Blob storage service.</span></span>|  
|<span data-ttu-id="1cd07-228">DIFFERENTIAL (разностная)</span><span class="sxs-lookup"><span data-stu-id="1cd07-228">DIFFERENTIAL</span></span>|<span data-ttu-id="1cd07-229">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-229">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-230">COPY_ONLY</span><span class="sxs-lookup"><span data-stu-id="1cd07-230">COPY_ONLY</span></span>|<span data-ttu-id="1cd07-231">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-231">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-232">COMPRESSION&#124;NO_COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="1cd07-232">COMPRESSION&#124;NO_COMPRESSION</span></span>|<span data-ttu-id="1cd07-233">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-233">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-234">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1cd07-234">DESCRIPTION</span></span>|<span data-ttu-id="1cd07-235">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-235">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-236">NAME</span><span class="sxs-lookup"><span data-stu-id="1cd07-236">NAME</span></span>|<span data-ttu-id="1cd07-237">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-237">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-238">EXPIREDATE &#124; RETAINDAYS</span><span class="sxs-lookup"><span data-stu-id="1cd07-238">EXPIREDATE &#124; RETAINDAYS</span></span>|<span data-ttu-id="1cd07-239">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-239">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-240">NOINIT &#124; INIT</span><span class="sxs-lookup"><span data-stu-id="1cd07-240">NOINIT &#124; INIT</span></span>|<span data-ttu-id="1cd07-241">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-241">&#x2713;</span></span>||<span data-ttu-id="1cd07-242">Даже если этот параметр указан, он пропускается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-242">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="1cd07-243">Добавление к большим двоичным объектам невозможно.</span><span class="sxs-lookup"><span data-stu-id="1cd07-243">Appending to blobs is not possible.</span></span> <span data-ttu-id="1cd07-244">Для перезаписи резервной копии используйте аргумент FORMAT.</span><span class="sxs-lookup"><span data-stu-id="1cd07-244">To overwrite a backup use the FORMAT argument.</span></span>|  
|<span data-ttu-id="1cd07-245">NOSKIP &#124; SKIP</span><span class="sxs-lookup"><span data-stu-id="1cd07-245">NOSKIP &#124; SKIP</span></span>|<span data-ttu-id="1cd07-246">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-246">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-247">NOFORMAT &#124; FORMAT</span><span class="sxs-lookup"><span data-stu-id="1cd07-247">NOFORMAT &#124; FORMAT</span></span>|<span data-ttu-id="1cd07-248">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-248">&#x2713;</span></span>||<span data-ttu-id="1cd07-249">Даже если этот параметр указан, он пропускается.</span><span class="sxs-lookup"><span data-stu-id="1cd07-249">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="1cd07-250">Создание резервных копий в существующем большом двоичном объекте завершается ошибкой, если не указан аргумент WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="1cd07-250">A backup taken to an existing blob fails unless WITH FORMAT is specified.</span></span> <span data-ttu-id="1cd07-251">Если аргумент WITH FORMAT указан, существующий большой двоичный объект будет перезаписан.</span><span class="sxs-lookup"><span data-stu-id="1cd07-251">The existing blob is overwritten when WITH FORMAT is specified.</span></span>|  
|<span data-ttu-id="1cd07-252">MEDIADESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1cd07-252">MEDIADESCRIPTION</span></span>|<span data-ttu-id="1cd07-253">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-253">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-254">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="1cd07-254">MEDIANAME</span></span>|<span data-ttu-id="1cd07-255">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-255">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-256">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="1cd07-256">BLOCKSIZE</span></span>|<span data-ttu-id="1cd07-257">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-257">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-258">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="1cd07-258">BUFFERCOUNT</span></span>|<span data-ttu-id="1cd07-259">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-259">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-260">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="1cd07-260">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="1cd07-261">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-261">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-262">NO_CHECKSUM &#124; CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="1cd07-262">NO_CHECKSUM &#124; CHECKSUM</span></span>|<span data-ttu-id="1cd07-263">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-263">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="1cd07-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="1cd07-265">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-265">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-266">STATS</span><span class="sxs-lookup"><span data-stu-id="1cd07-266">STATS</span></span>|<span data-ttu-id="1cd07-267">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-267">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-268">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="1cd07-268">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="1cd07-269">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-269">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-270">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="1cd07-270">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="1cd07-271">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-271">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-272">NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="1cd07-272">NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="1cd07-273">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-273">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-274">NO_TRUNCATE</span><span class="sxs-lookup"><span data-stu-id="1cd07-274">NO_TRUNCATE</span></span>|<span data-ttu-id="1cd07-275">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-275">&#x2713;</span></span>|||  
  
 <span data-ttu-id="1cd07-276">Дополнительные сведения об аргументах резервного копирования см. в разделе [BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1cd07-276">For more information about backup arguments, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="support-for-restore-arguments"></a><span data-ttu-id="1cd07-277">Поддержка аргументов восстановления</span><span class="sxs-lookup"><span data-stu-id="1cd07-277">Support for Restore Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1cd07-278">Аргумент</span><span class="sxs-lookup"><span data-stu-id="1cd07-278">Argument</span></span>|<span data-ttu-id="1cd07-279">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1cd07-279">Supported</span></span>|<span data-ttu-id="1cd07-280">Исключения</span><span class="sxs-lookup"><span data-stu-id="1cd07-280">Exceptions</span></span>|<span data-ttu-id="1cd07-281">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1cd07-281">Comments</span></span>|  
|<span data-ttu-id="1cd07-282">DATABASE</span><span class="sxs-lookup"><span data-stu-id="1cd07-282">DATABASE</span></span>|<span data-ttu-id="1cd07-283">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-283">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-284">LOG</span><span class="sxs-lookup"><span data-stu-id="1cd07-284">LOG</span></span>|<span data-ttu-id="1cd07-285">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-285">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-286">FROM (URL)</span><span class="sxs-lookup"><span data-stu-id="1cd07-286">FROM (URL)</span></span>|<span data-ttu-id="1cd07-287">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-287">&#x2713;</span></span>||<span data-ttu-id="1cd07-288">Аргумент FROM URL используется, чтобы указать URL-адрес для файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="1cd07-288">The FROM URL argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="1cd07-289">**WITH Options:**</span><span class="sxs-lookup"><span data-stu-id="1cd07-289">**WITH Options:**</span></span>||||  
|<span data-ttu-id="1cd07-290">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-290">CREDENTIAL</span></span>|<span data-ttu-id="1cd07-291">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-291">&#x2713;</span></span>||<span data-ttu-id="1cd07-292">С УЧЕТными данными поддерживается только при использовании параметра восстановить из URL-адреса для восстановления из службы хранилища больших двоичных объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-292">WITH CREDENTIAL is only supported when using RESTORE FROM URL option to restore from Azure Blob Storage service.</span></span>|  
|<span data-ttu-id="1cd07-293">PARTIAL</span><span class="sxs-lookup"><span data-stu-id="1cd07-293">PARTIAL</span></span>|<span data-ttu-id="1cd07-294">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-294">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="1cd07-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="1cd07-296">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-296">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-297">LOADHISTORY</span><span class="sxs-lookup"><span data-stu-id="1cd07-297">LOADHISTORY</span></span>|<span data-ttu-id="1cd07-298">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-298">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-299">MOVE</span><span class="sxs-lookup"><span data-stu-id="1cd07-299">MOVE</span></span>|<span data-ttu-id="1cd07-300">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-300">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-301">REPLACE</span><span class="sxs-lookup"><span data-stu-id="1cd07-301">REPLACE</span></span>|<span data-ttu-id="1cd07-302">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-302">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-303">RESTART</span><span class="sxs-lookup"><span data-stu-id="1cd07-303">RESTART</span></span>|<span data-ttu-id="1cd07-304">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-304">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-305">RESTRICTED_USER</span><span class="sxs-lookup"><span data-stu-id="1cd07-305">RESTRICTED_USER</span></span>|<span data-ttu-id="1cd07-306">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-306">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-307">FILE</span><span class="sxs-lookup"><span data-stu-id="1cd07-307">FILE</span></span>|<span data-ttu-id="1cd07-308">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-308">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-309">PASSWORD</span><span class="sxs-lookup"><span data-stu-id="1cd07-309">PASSWORD</span></span>|<span data-ttu-id="1cd07-310">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-310">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-311">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="1cd07-311">MEDIANAME</span></span>|<span data-ttu-id="1cd07-312">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-312">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-313">MEDIAPASSWORD</span><span class="sxs-lookup"><span data-stu-id="1cd07-313">MEDIAPASSWORD</span></span>|<span data-ttu-id="1cd07-314">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-314">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-315">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="1cd07-315">BLOCKSIZE</span></span>|<span data-ttu-id="1cd07-316">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-316">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-317">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="1cd07-317">BUFFERCOUNT</span></span>|<span data-ttu-id="1cd07-318">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-318">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-319">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="1cd07-319">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="1cd07-320">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-320">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-321">CHECKSUM &#124; NO_CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="1cd07-321">CHECKSUM &#124; NO_CHECKSUM</span></span>|<span data-ttu-id="1cd07-322">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-322">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="1cd07-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="1cd07-324">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-324">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-325">FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1cd07-325">FILESTREAM</span></span>|<span data-ttu-id="1cd07-326">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-326">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-327">STATS</span><span class="sxs-lookup"><span data-stu-id="1cd07-327">STATS</span></span>|<span data-ttu-id="1cd07-328">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-328">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-329">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="1cd07-329">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="1cd07-330">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-330">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-331">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="1cd07-331">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="1cd07-332">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-332">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-333">KEEP_REPLICATION</span><span class="sxs-lookup"><span data-stu-id="1cd07-333">KEEP_REPLICATION</span></span>|<span data-ttu-id="1cd07-334">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-334">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-335">KEEP_CDC</span><span class="sxs-lookup"><span data-stu-id="1cd07-335">KEEP_CDC</span></span>|<span data-ttu-id="1cd07-336">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-336">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span><span class="sxs-lookup"><span data-stu-id="1cd07-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span></span>|<span data-ttu-id="1cd07-338">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-338">&#x2713;</span></span>|||  
|<span data-ttu-id="1cd07-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span><span class="sxs-lookup"><span data-stu-id="1cd07-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span></span>|<span data-ttu-id="1cd07-340">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1cd07-340">&#x2713;</span></span>|||  
  
 <span data-ttu-id="1cd07-341">Дополнительные сведения об аргументах восстановления см. в разделе [Аргументы инструкции RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1cd07-341">For more information about Restore arguments, see [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
##  <a name="using-backup-task-in-sql-server-management-studio"></a><a name="BackupTaskSSMS"></a><span data-ttu-id="1cd07-342">Использование задачи резервного копирования в SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1cd07-342">Using Backup Task in SQL Server Management Studio</span></span>  
 <span data-ttu-id="1cd07-343">Задача резервного копирования в SQL Server Management Studio была улучшена для включения URL-адреса в качестве одного из вариантов назначения и других вспомогательных объектов, необходимых для резервного копирования в службу хранилища Azure, например учетные данные SQL.</span><span class="sxs-lookup"><span data-stu-id="1cd07-343">The Backup task in SQL Server Management Studio has been enhanced to include URL as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span>  
  
 <span data-ttu-id="1cd07-344">Следующие шаги описывают изменения, внесенные в задачу «Резервное копирование базы данных», чтобы обеспечить резервное копирование в службу хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-344">The following steps describe the changes made to the Back Up Database task to allow for backing up to Azure storage.:</span></span>  
  
1.  <span data-ttu-id="1cd07-345">Запустите среду SQL Server Management Studio и подключитесь к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1cd07-345">Start SQL Server Management Studio and connect to the SQL Server instance.</span></span>  <span data-ttu-id="1cd07-346">Выберите базу данных, которую необходимо создать резервную копию, и щелкните правой кнопкой мыши **задачи**и выберите пункт **создать резервную копию..**. Откроется диалоговое окно Резервное копирование базы данных.</span><span class="sxs-lookup"><span data-stu-id="1cd07-346">Select a database you want to backup, and right click on **Tasks**, and select **Back Up..**. This opens the Back Up Database dialog box.</span></span>  
  
2.  <span data-ttu-id="1cd07-347">На странице Общие параметр **URL-адрес** используется для создания резервной копии в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-347">On the general page the **URL** option is used to create a backup to Azure storage.</span></span> <span data-ttu-id="1cd07-348">Если выбран этот параметр, на странице будут показаны другие параметры.</span><span class="sxs-lookup"><span data-stu-id="1cd07-348">When you select this option, you see other options enabled on this page:</span></span>  
  
    1.  <span data-ttu-id="1cd07-349">**Имя файла.** Имя файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="1cd07-349">**File Name:** Name of the backup file.</span></span>  
  
    2.  <span data-ttu-id="1cd07-350">**Учетные данные SQL:** Можно либо указать существующие учетные данные SQL Server, либо создать новый, щелкнув **создать** рядом с полем учетные данные SQL.</span><span class="sxs-lookup"><span data-stu-id="1cd07-350">**SQL Credential:** You can either specify an existing SQL Server Credential, or can create a new one by clicking on the **Create** next to the SQL Credential box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="1cd07-351">В диалоговом окне, которое открывается при нажатии кнопки **Создать** , необходимо ввести сертификат управления или профиль публикации подписки.</span><span class="sxs-lookup"><span data-stu-id="1cd07-351">The dialog that opens when you click **Create** requires a management certificate or the publishing profile for the subscription.</span></span> <span data-ttu-id="1cd07-352">SQL Server в настоящий момент поддерживает версию 2.0 профиля публикации.</span><span class="sxs-lookup"><span data-stu-id="1cd07-352">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="1cd07-353">Для загрузки поддерживаемой версии профиля публикации см. раздел [Загрузка профиля публикации 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="1cd07-353">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
        >   
        >  <span data-ttu-id="1cd07-354">Если у вас нет доступа к сертификату управления или профилю публикации, можно создать учетные данные SQL, указав имя учетной записи хранилища и сведения ключа доступа при помощи Transact-SQL или SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="1cd07-354">If you do not have access to the management certificate or publishing profile, you can create a SQL Credential by specifying the storage account name and access key information using Transact-SQL or SQL Server Management Studio.</span></span> <span data-ttu-id="1cd07-355">Образец кода для создания учетных данных с помощью Transact-SQL см. в разделе [Создание учетных данных](#credential) .</span><span class="sxs-lookup"><span data-stu-id="1cd07-355">See the sample code in the [Create a Credential](#credential) section to create a credential using Transact-SQL.</span></span> <span data-ttu-id="1cd07-356">Также можно в среде SQL Server Management Studio, из экземпляра компонента database engine, щелкнуть правой кнопкой мыши **Безопасность**и выбрать пункт **Создать**, а затем **Учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="1cd07-356">Alternatively, using SQL Server Management Studio, from the database engine instance, right click **Security**, select **New**, and select **Credential**.</span></span> <span data-ttu-id="1cd07-357">Укажите имя учетной записи хранения в поле **Идентификатор** и ключ доступа в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="1cd07-357">Specify the storage account name for **Identity** and the access key in the **Password** field.</span></span>  
  
    3.  <span data-ttu-id="1cd07-358">**Контейнер хранилища Azure:** Имя контейнера службы хранилища Azure для хранения файлов резервных копий.</span><span class="sxs-lookup"><span data-stu-id="1cd07-358">**Azure storage container:** The name of the Azure storage container to store the backup files.</span></span>  
  
    4.  <span data-ttu-id="1cd07-359">**Префикс URL-адреса.** Создается автоматически на основе сведений, указанных в полях, описанных на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="1cd07-359">**URL prefix:** This is built automatically using the information specified in the fields described in the previous steps.</span></span> <span data-ttu-id="1cd07-360">При изменении этого значения вручную убедитесь в том, что оно соответствует прочим данным, указанным ранее.</span><span class="sxs-lookup"><span data-stu-id="1cd07-360">If you do edit this value manually, make sure it matches with the other information you provided previously.</span></span> <span data-ttu-id="1cd07-361">Например, при изменении URL-адреса хранения убедитесь, что учетные данные SQL заданы для проверки подлинности в той же самой учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="1cd07-361">For example if you modify the storage URL, make sure the SQL Credential is set to authenticate to the same storage account.</span></span>  
  
 <span data-ttu-id="1cd07-362">При выборе URL-адреса в качестве назначения некоторые параметры на странице **Параметры носителя** отключаются.</span><span class="sxs-lookup"><span data-stu-id="1cd07-362">When you select URL as the destination, certain options in the **Media Options** page are disabled.</span></span>  <span data-ttu-id="1cd07-363">Следующие разделы содержат дополнительные сведения о диалоговом окне «Резервное копирование базы данных»:</span><span class="sxs-lookup"><span data-stu-id="1cd07-363">The following topics have more information on the Back Up Database dialog:</span></span>  
  
 [<span data-ttu-id="1cd07-364">Резервное копирование базы данных (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="1cd07-364">Back Up Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
 [<span data-ttu-id="1cd07-365">Резервное копирование базы данных (страница "Параметры носителя")</span><span class="sxs-lookup"><span data-stu-id="1cd07-365">Back Up Database &#40;Media Options Page&#41;</span></span>](back-up-database-media-options-page.md)  
  
 [<span data-ttu-id="1cd07-366">Резервное копирование базы данных (страница "Параметры резервного копирования")</span><span class="sxs-lookup"><span data-stu-id="1cd07-366">Back Up Database &#40;Backup Options Page&#41;</span></span>](back-up-database-backup-options-page.md)  
  
 [<span data-ttu-id="1cd07-367">Создание учетных данных — проверка подлинности в хранилище Azure</span><span class="sxs-lookup"><span data-stu-id="1cd07-367">Create Credential - Authenticate to Azure Storage</span></span>](create-credential-authenticate-to-azure-storage.md)  
  
##  <a name="sql-server-backup-to-url-using-maintenance-plan-wizard"></a><a name="MaintenanceWiz"></a><span data-ttu-id="1cd07-368">SQL Server резервного копирования на URL-адрес с помощью мастера планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="1cd07-368">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>  
 <span data-ttu-id="1cd07-369">Аналогично задаче резервного копирования, описанной выше, мастер планов обслуживания в SQL Server Management Studio был усовершенствован для включения **URL-адреса** в качестве одного из вариантов назначения и других вспомогательных объектов, необходимых для резервного копирования в службу хранилища Azure, например учетные данные SQL.</span><span class="sxs-lookup"><span data-stu-id="1cd07-369">Similar to the backup task described previously, the Maintenance Plan Wizard in SQL Server Management Studio has been enhanced to include **URL** as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span> <span data-ttu-id="1cd07-370">Дополнительные сведения см. в разделе **Определение задач резервного копирования** статьи [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span><span class="sxs-lookup"><span data-stu-id="1cd07-370">For more information, see  the **Define Backup Tasks** section in [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span></span>  
  
##  <a name="restoring-from-azure-storage-using-sql-server-management-studio"></a><a name="RestoreSSMS"></a><span data-ttu-id="1cd07-371">Восстановление из хранилища Azure с помощью SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1cd07-371">Restoring from Azure storage Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1cd07-372">При восстановлении базы данных **URL-адрес** включается в качестве устройства для восстановления с него.</span><span class="sxs-lookup"><span data-stu-id="1cd07-372">If you are restoring a database, **URL** is included as the device to restore from.</span></span> <span data-ttu-id="1cd07-373">Следующие шаги описывают изменения в задаче восстановления, чтобы разрешить восстановление из хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-373">Following steps describe the changes in the Restore task to allow restoring from Azure storage:</span></span>  
  
1.  <span data-ttu-id="1cd07-374">При выборе пункта **Устройства** на странице **Общие** задачи восстановления в SQL Server Management Studio открывается диалоговое окно **Выберите устройства резервного копирования** , где в качестве типа носителя резервной копии можно выбрать **URL-адрес** .</span><span class="sxs-lookup"><span data-stu-id="1cd07-374">When you select **Devices** in the **General** page of the Restore task in SQL Server Management Studio, this takes you to the **Select backup devices** dialog box which includes **URL** as a backup media type.</span></span>  
  
2.  <span data-ttu-id="1cd07-375">Если выбрать вариант **URL-адрес** и нажать **Добавить**, откроется диалоговое окно **Подключение к хранилищу Azure** .</span><span class="sxs-lookup"><span data-stu-id="1cd07-375">When you select **URL** and click **Add**, this opens the **Connect to Azure storage** dialog.</span></span> <span data-ttu-id="1cd07-376">Укажите учетные данные SQL для проверки подлинности в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-376">Specify the SQL Credential information to authenticate to Azure storage.</span></span>  
  
3.  <span data-ttu-id="1cd07-377">После этого SQL Server подключается к службе хранилища Azure с помощью предоставленных учетных данных SQL и открывает диалоговое окно " **Размещение файла резервной копии в Azure** ".</span><span class="sxs-lookup"><span data-stu-id="1cd07-377">SQL Server then connects to Azure storage using the SQL Credential information you provided and opens the **Locate Backup File in Azure** dialog.</span></span> <span data-ttu-id="1cd07-378">Файлы резервной копии, находящиеся в хранилище, отобразятся на этой странице.</span><span class="sxs-lookup"><span data-stu-id="1cd07-378">The backup files residing in the storage are displayed on this page.</span></span> <span data-ttu-id="1cd07-379">Выберите файл, который требуется использовать для восстановления, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1cd07-379">Select the file you want to use to restore and click **OK**.</span></span> <span data-ttu-id="1cd07-380">После этого откроется диалоговое окно **Выбор устройств резервного копирования** **и в этом** диалоговом окне откроется основное диалоговое окно **восстановления** , в котором вы сможете выполнить восстановление.</span><span class="sxs-lookup"><span data-stu-id="1cd07-380">This takes you back to the **Select Backup Devices** dialog, and Clicking **OK** on this dialog takes you back to the main **Restore** dialog where you will be able complete the restore.</span></span>  <span data-ttu-id="1cd07-381">Дополнительные сведения см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="1cd07-381">For more information see, the following topics:</span></span>  
  
     [<span data-ttu-id="1cd07-382">Восстановление базы данных (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="1cd07-382">Restore Database &#40;General Page&#41;</span></span>](restore-database-general-page.md)  
  
     [<span data-ttu-id="1cd07-383">Восстановление базы данных (страница "Файлы")</span><span class="sxs-lookup"><span data-stu-id="1cd07-383">Restore Database &#40;Files Page&#41;</span></span>](restore-database-files-page.md)  
  
     [<span data-ttu-id="1cd07-384">Восстановление базы данных (страница "Параметры")</span><span class="sxs-lookup"><span data-stu-id="1cd07-384">Restore Database &#40;Options Page&#41;</span></span>](restore-database-options-page.md)  
  
##  <a name="code-examples"></a><a name="Examples"></a> <span data-ttu-id="1cd07-385">Примеры кода</span><span class="sxs-lookup"><span data-stu-id="1cd07-385">Code Examples</span></span>  
 <span data-ttu-id="1cd07-386">В этом разделе содержатся следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="1cd07-386">This section contains the following examples.</span></span>  
  
-   [<span data-ttu-id="1cd07-387">Создание учетных данных</span><span class="sxs-lookup"><span data-stu-id="1cd07-387">Create a Credential</span></span>](#credential)  
  
-   [<span data-ttu-id="1cd07-388">Создание резервной копии всей базы данных</span><span class="sxs-lookup"><span data-stu-id="1cd07-388">Backing up a complete database</span></span>](#complete)  
  
-   [<span data-ttu-id="1cd07-389">Создание резервной копии базы данных и журнала</span><span class="sxs-lookup"><span data-stu-id="1cd07-389">Backing up the database and log</span></span>](#databaselog)  
  
-   [<span data-ttu-id="1cd07-390">Создание полной резервной копии первичной файловой группы</span><span class="sxs-lookup"><span data-stu-id="1cd07-390">Creating a full file backup of the primary filegroup</span></span>](#filebackup)  
  
-   [<span data-ttu-id="1cd07-391">Создание разностной резервной копии файлов первичных файловых групп</span><span class="sxs-lookup"><span data-stu-id="1cd07-391">Creating a differential file backup of the primary filegroups</span></span>](#differential)  
  
-   [<span data-ttu-id="1cd07-392">Восстановление базы данных и перемещение файлов</span><span class="sxs-lookup"><span data-stu-id="1cd07-392">Restoring a database and move files</span></span>](#restoredbwithmove)  
  
-   [<span data-ttu-id="1cd07-393">Восстановление состояния на определенный момент времени с помощью STOPAT</span><span class="sxs-lookup"><span data-stu-id="1cd07-393">Restoring to a point-in-time using STOPAT</span></span>](#PITR)  
  
###  <a name="create-a-credential"></a><a name="credential"></a> <span data-ttu-id="1cd07-394">Создание учетных данных</span><span class="sxs-lookup"><span data-stu-id="1cd07-394">Create a Credential</span></span>  
 <span data-ttu-id="1cd07-395">В следующем примере создаются учетные данные, в которых хранятся данные проверки подлинности службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-395">The following example creates a credential that stores the Azure Storage authentication information.</span></span>  

   ```sql
   IF NOT EXISTS  
   (SELECT * FROM sys.credentials   
   WHERE credential_identity = 'mycredential')  
   CREATE CREDENTIAL mycredential WITH IDENTITY = 'mystorageaccount'  
   ,SECRET = '<storage access key>' ;  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
   string secret = "<storage access key>";  
  
   // Create a Credential  
   string credentialName = "mycredential";  
   Credential credential = new Credential(server, credentialName);  
   credential.Create(identity, secret);  
   ```  
  
   ```powershell
   # create variables  
   $storageAccount = "mystorageaccount"  
   $storageKey = "<storage access key>"  
   $secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
   $credentialName = "mycredential"  
  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Create a credential  
   New-SqlCredential -Name $credentialName -Path $srvpath -Identity $storageAccount -Secret $secureString
   ```  
  
###  <a name="backing-up-a-complete-database"></a><a name="complete"></a><span data-ttu-id="1cd07-396">Резервное копирование всей базы данных</span><span class="sxs-lookup"><span data-stu-id="1cd07-396">Backing up a complete database</span></span>  
 <span data-ttu-id="1cd07-397">В следующем примере производится резервное копирование базы данных AdventureWorks2012 в службу хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="1cd07-397">The following example backs up the AdventureWorks2012 database to the Azure Blob storage service.</span></span>
  
   ```sql
   BACKUP DATABASE AdventureWorks2012   
   TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
         WITH CREDENTIAL = 'mycredential'   
         ,COMPRESSION  
         ,STATS = 5;  
   GO
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);  
   ```
  
   ```powershell
   # create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"   
   # for default instance, the $srvpath varilable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance  
   CD $srvPath   
   $backupFile = $backupUrlContainer + "AdventureWorks2012" +  ".bak"  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On
   ```  
  
###  <a name="backing-up-the-database-and-log"></a><a name="databaselog"></a><span data-ttu-id="1cd07-398">Резервное копирование базы данных и журнала</span><span class="sxs-lookup"><span data-stu-id="1cd07-398">Backing up the database and log</span></span>  
 <span data-ttu-id="1cd07-399">В следующем примере используется образец базы данных AdventureWorks2012, которая по умолчанию использует простую модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="1cd07-399">The following example backups up the AdventureWorks2012 sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="1cd07-400">Для поддержки резервного копирования журналов база данных AdventureWorks2012 перенастраивается на использование модели полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1cd07-400">To support log backups, the AdventureWorks2012 database is modified to use the full recovery model.</span></span> <span data-ttu-id="1cd07-401">Затем в примере создается полная резервная копия базы данных в большом двоичном объекте Azure, а после периода обновления — резервная копия журнала.</span><span class="sxs-lookup"><span data-stu-id="1cd07-401">The example then creates a full database backup to Azure Blob, and after a period of update activity, backs up the log.</span></span> <span data-ttu-id="1cd07-402">В этом примере будет создано имя резервной копии файла с меткой времени.</span><span class="sxs-lookup"><span data-stu-id="1cd07-402">This example creates a backup file name with a datetime stamp.</span></span>  
  
   ```sql
   -- To permit log backups, before the full database backup, modify the database   
   -- to use the full recovery model.  
   USE master;  
   GO  
   ALTER DATABASE AdventureWorks2012  
      SET RECOVERY FULL;  
   GO  
  
   -- Back up the full AdventureWorks2012 database.  
          -- First create a file name for the backup file with DateTime stamp  
  
   DECLARE @Full_Filename AS VARCHAR (300);  
   SET @Full_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Full_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.bak';   
   --Back up Adventureworks2012 database  
  
   BACKUP DATABASE AdventureWorks2012  
   TO URL =  @Full_Filename  
   WITH CREDENTIAL = 'mycredential';  
   ,COMPRESSION  
   GO  
   -- Back up the AdventureWorks2012 log.  
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url for data backup  
   string urlDataBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Data-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database to Url  
   Backup backupData = new Backup();  
   backupData.CredentialName = credentialName;  
   backupData.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupData.Devices.AddDevice(urlDataBackup, DeviceType.Url);  
   backupData.SqlBackup(server);  
  
   // Generate Unique Url for data backup  
   string urlLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Log-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database Log to Url  
   Backup backupLog = new Backup();  
   backupLog.CredentialName = credentialName;  
   backupLog.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupLog.Devices.AddDevice(urlLogBackup, DeviceType.Url);  
   backupLog.Action = BackupActionType.Log;  
   backupLog.SqlBackup(server);  
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to theSQL Server Instance
   CD $srvPath   
   #Create a unique file name for the full database backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Backup Database to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Database    
  
   #Create a unique file name for log backup  
  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup Log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Log
   ```  
  
###  <a name="creating-a-full-file-backup-of-the-primary-filegroup"></a><a name="filebackup"></a><span data-ttu-id="1cd07-403">Создание полной резервной копии файла первичной файловой группы</span><span class="sxs-lookup"><span data-stu-id="1cd07-403">Creating a full file backup of the primary filegroup</span></span>  
 <span data-ttu-id="1cd07-404">В следующем примере создается полная резервная копия файлов первичной файловой группы.</span><span class="sxs-lookup"><span data-stu-id="1cd07-404">The following example creates a full file backup of the primary filegroup.</span></span>
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012files.bck'  
       WITH CREDENTIAL = 'mycredential'  
       ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bck",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to the SQL Server Instance  
  
   CD $srvPath   
   #Create a unique file name for the file backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bck"  
  
   #Backup Primary File Group to URL  
  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary
   ```  
  
###  <a name="creating-a-differential-file-backup-of-the-primary-filegroup"></a><a name="differential"></a><span data-ttu-id="1cd07-405">Создание разностной резервной копии файлов первичной файловой группы</span><span class="sxs-lookup"><span data-stu-id="1cd07-405">Creating a differential file backup of the primary filegroup</span></span>  
 <span data-ttu-id="1cd07-406">В следующем примере создается разностная резервная копия файлов первичной файловой группы.</span><span class="sxs-lookup"><span data-stu-id="1cd07-406">The following example creates a differential file backup of the primary filegroup.</span></span>  
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012filesdiff.bck'  
       WITH   
          CREDENTIAL = 'mycredential'  
          ,COMPRESSION  
      ,DIFFERENTIAL;  
   GO
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.Incremental = true;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server); 
   ```

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Create a differential backup of the primary filegroup
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary -Incremental
   ```  
  
###  <a name="restore-a-database-and-move-files"></a><a name="restoredbwithmove"></a><span data-ttu-id="1cd07-407">Восстановление базы данных и перемещение файлов</span><span class="sxs-lookup"><span data-stu-id="1cd07-407">Restore a database and move files</span></span>  
 <span data-ttu-id="1cd07-408">Чтобы восстановить полную резервную копию базы данных и переместить восстановленную базу данных в папку C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1cd07-408">To restore a full database backup and move the restored database to C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data directory, use the following steps.</span></span>
  
   ```sql
   -- Backup the tail of the log first
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,NORECOVERY;  
   GO  
  
   RESTORE DATABASE AdventureWorks2012 FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'  
   WITH CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,MOVE 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,STATS = 5
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for tail log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName+ "_Log", newLogFilePath));  
   restore.SqlRestore(server);
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTNACENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On      
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery    
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath)
   ```  
  
###  <a name="restoring-to-a-point-in-time-using-stopat"></a><a name="PITR"></a> <span data-ttu-id="1cd07-409">Восстановление состояния на определенный момент времени с помощью STOPAT</span><span class="sxs-lookup"><span data-stu-id="1cd07-409">Restoring to a point-in-time using STOPAT</span></span>  
 <span data-ttu-id="1cd07-410">В следующем примере производится восстановление базы данных к состоянию на определенный момент времени и демонстрируется операция восстановления.</span><span class="sxs-lookup"><span data-stu-id="1cd07-410">The following example restores a database to its state to a point in time, and shows a restore operation.</span></span>  
  
   ```sql
   RESTORE DATABASE AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
   WITH   
     CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,Move 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,NORECOVERY  
    --,REPLACE  
    ,STATS = 5;  
   GO   
  
   RESTORE LOG AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.trn'   
   WITH CREDENTIAL = 'mycredential'  
    ,RECOVERY   
    ,STOPAT = 'Oct 23, 2012 5:00 PM'   
   GO  
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for Tail Log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.NoRecovery = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName + "_Log", newLogFilePath));  
   restore.SqlRestore(server);  
      
   // Restore transaction Log with stop at   
   Restore restoreLog = new Restore();  
   restoreLog.CredentialName = credentialName;  
   restoreLog.Database = dbName;  
   restoreLog.Action = RestoreActionType.Log;  
   restoreLog.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restoreLog.ToPointInTime = DateTime.Now.ToString();   
   restoreLog.SqlRestore(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Navigate to SQL Server Instance Directory
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On     
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery     
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath) -NoRecovery    
  
   # Restore Transaction log with Stop At:  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backuplogFile  -ToPointInTime (Get-Date).ToString()
   ```  
  
## <a name="see-also"></a><span data-ttu-id="1cd07-411">См. также:</span><span class="sxs-lookup"><span data-stu-id="1cd07-411">See Also</span></span>  
 <span data-ttu-id="1cd07-412">[Резервное копирование SQL Server на URL-адрес — рекомендации и устранение неполадок](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="1cd07-412">[SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span></span>  
 [<span data-ttu-id="1cd07-413">Резервное копирование и восстановление системных баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1cd07-413">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](back-up-and-restore-of-system-databases-sql-server.md)   
