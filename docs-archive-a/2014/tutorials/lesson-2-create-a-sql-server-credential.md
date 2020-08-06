---
title: Занятие 2. Создание учетных данных SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 64f8805c-1ddc-4c96-a47c-22917d12e1ab
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e8b13c8d4d9e5937064cef5503ec64bfd6e4a2d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751603"
---
# <a name="lesson-2-create-a-sql-server-credential"></a><span data-ttu-id="d1a47-102">Урок 2. Создание учетных данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1a47-102">Lesson 2: Create a SQL Server Credential</span></span>
  <span data-ttu-id="d1a47-103">**Учетные данные**. Учетные данные [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] являются объектом, который используется для хранения информации о проверке подлинности, которая необходима для подключения к источнику за пределами SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1a47-103">**Credential:** A [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="d1a47-104">Здесь [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] процессы резервного копирования и восстановления используют учетные данные для проверки подлинности в службе хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="d1a47-104">Here, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="d1a47-105">Учетные данные хранят имя учетной записи хранилища и значения **ключа доступа** учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="d1a47-105">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="d1a47-106">После создания учетных данных их необходимо указать в параметре WITH CREDENTIAL при выполнении инструкций BACKUP/RESTORE.</span><span class="sxs-lookup"><span data-stu-id="d1a47-106">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="d1a47-107">Дополнительную информацию о просмотре, копировании или повторном создании учетной записи хранилища **access keys**см. в разделе [Ключи доступа к учетной записи](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="d1a47-107">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="d1a47-108">Общие сведения об учетных данных см. в разделе [учетные данные](../relational-databases/security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="d1a47-108">For general information about credentials, see [Credentials](../relational-databases/security/authentication-access/credentials-database-engine.md).</span></span>  
  
 <span data-ttu-id="d1a47-109">Дополнительные сведения о других примерах использования учетных данных см. в статье [создание агент SQL Server прокси-сервера](../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="d1a47-109">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d1a47-110">Требования к созданию учетных данных SQL Server, описанных ниже, относятся к SQL Server процессам резервного копирования ([SQL Server резервное копирование на URL-адрес](../relational-databases/backup-restore/sql-server-backup-to-url.md)и [SQL Server управляемого резервного копирования в Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span><span class="sxs-lookup"><span data-stu-id="d1a47-110">The requirements for creating a SQL Server credential described below are specific to SQL Server backup processes ([SQL Server Backup to URL](../relational-databases/backup-restore/sql-server-backup-to-url.md), and [SQL Server Managed  Backup to Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span></span> <span data-ttu-id="d1a47-111">SQL Server, при доступе к хранилищу Azure для записи или чтения резервных копий, использует информацию об имени и ключе доступа учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="d1a47-111">SQL Server, when accessing Azure storage to write or read backups uses the storage account name and access key information.</span></span>  <span data-ttu-id="d1a47-112">Дополнительную информацию о создании учетных данных для хранения файлов базы данных в хранилище Azure можно узнать в статье [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md).</span><span class="sxs-lookup"><span data-stu-id="d1a47-112">For more information on creating credentials for storing database files in Azure storage, see [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span></span>  
  
## <a name="create-a-sql-server-credential"></a><span data-ttu-id="d1a47-113">Создание учетных данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1a47-113">Create a SQL Server Credential</span></span>  
 <span data-ttu-id="d1a47-114">Для создания учетных данных SQL Server выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d1a47-114">To create a SQL Server Credential, use the following steps:</span></span>  
  
1.  <span data-ttu-id="d1a47-115">Подключитесь к среде Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d1a47-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="d1a47-116">В обозревателе объектов подключитесь к экземпляру компонента Database Engine, на котором установлена база данных AdventureWorks2012, или воспользуйтесь собственной базой данных, запланированной для усвоения материала этого учебника.</span><span class="sxs-lookup"><span data-stu-id="d1a47-116">In Object Explorer, connect to the instance of Database Engine that has AdventureWorks2012 database installed, or use your own database you plan to use for this tutorial.</span></span>  
  
3.  <span data-ttu-id="d1a47-117">На панели инструментов **Стандартная** выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d1a47-117">On the **Standard** tool bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="d1a47-118">Скопируйте и вставьте следующий пример в окно запроса (при необходимости измените).</span><span class="sxs-lookup"><span data-stu-id="d1a47-118">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account (See Lesson 1)   
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account (See Lesson 1)  
  
    ```  
  
     <span data-ttu-id="d1a47-119">![сопоставление учетной записи хранилища с учетными данными SQL](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "сопоставление учетной записи хранилища с учетными данными SQL")</span><span class="sxs-lookup"><span data-stu-id="d1a47-119">![mapping storage account to sql credentials](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
5.  <span data-ttu-id="d1a47-120">Проверьте инструкцию T-SQL и нажмите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d1a47-120">Verify the T-SQL statement and click **Execute**.</span></span>  
  
 <span data-ttu-id="d1a47-121">Дополнительные сведения о службе хранилища BLOB-объектов Azure для основных понятий и требований для резервного копирования см. [в статье SQL Server резервное копирование и восстановление с помощью службы хранилища BLOB-объектов Azure](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="d1a47-121">For more information about the Azure Blob storage service for backup concepts and requirements, see [SQL Server Backup and Restore with Azure Blob Storage Service](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="d1a47-122">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="d1a47-122">Next Lesson</span></span>  
 <span data-ttu-id="d1a47-123">[Занятие 3. запись полной резервной копии базы данных в службу хранилища BLOB-объектов Azure](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="d1a47-123">[Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span></span>  
  
  
