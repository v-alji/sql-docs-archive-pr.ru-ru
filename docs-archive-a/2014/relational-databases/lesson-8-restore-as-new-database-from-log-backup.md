---
title: Занятие 9. Восстановление базы данных из службы хранилища Azure | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ebba12c7-3d13-4c9d-8540-ad410a08356d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5e7c2350bb2a9b1f8c31da8e094459b5bc8ccd90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668299"
---
# <a name="lesson-9-restore-a-database-from-azure-storage"></a><span data-ttu-id="9f6d6-103">Занятие 9.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-103">Lesson 9.</span></span> <span data-ttu-id="9f6d6-104">Восстановление базы данных из службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="9f6d6-104">Restore a database from Azure Storage</span></span>
  <span data-ttu-id="9f6d6-105">На этом занятии вы узнаете, как восстановить файл резервной копии базы данных из хранилища Azure в базу данных, которая находится локально или на виртуальной машине в Azure.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-105">In this lesson, you will learn how to restore a database backup file from Azure Storage to a database, which either resides on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="9f6d6-106">Для прохождения этого занятия не требуется завершать занятия 4, 5, 6, 7 и 8.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-106">To follow this lesson, you do not need to complete Lesson 4, 5, 6, 7, and 8.</span></span>  
  
 <span data-ttu-id="9f6d6-107">Для этого занятия предполагается, что вы уже выполнили следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-107">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="9f6d6-108">Создали базу данных на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-108">You have created a database in the source machine.</span></span>  
  
-   <span data-ttu-id="9f6d6-109">Вы создали резервную копию базы данных (BAK-файла) в службе хранилища Azure с помощью [SQL Server резервное копирование и восстановление с помощью функции службы хранилища больших двоичных объектов Azure](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="9f6d6-109">You have created a backup of your database (.bak) in Azure Storage by using the [SQL Server Backup and Restore with Azure Blob Storage Service](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) feature.</span></span> <span data-ttu-id="9f6d6-110">Обратите внимание, что на этом шаге потребуется создать еще одни учетные данные SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-110">Note that you will need to create another SQL Server Credential in this step.</span></span> <span data-ttu-id="9f6d6-111">Эти учетные данные используют ключи учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-111">This credential uses storage account keys.</span></span>  
  
-   <span data-ttu-id="9f6d6-112">У вас есть учетная запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-112">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="9f6d6-113">Вы создали контейнер в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-113">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="9f6d6-114">Создали политику в контейнере с правами на чтение, запись и перечисление.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-114">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="9f6d6-115">Создали ключ SAS.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-115">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="9f6d6-116">Вы создали на своем компьютере учетные данные SQL Server для функции интеграции службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-116">You have created a SQL Server credential on your machine for Azure Storage Integration feature.</span></span> <span data-ttu-id="9f6d6-117">Обратите внимание, что для этих учетных данных требуется ключ подписанного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-117">Note that this credential requires a Shared Access Signature (SAS) key.</span></span>  
  
 <span data-ttu-id="9f6d6-118">Для восстановления базы данных из службы хранилища Azure можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-118">To restore a database from Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="9f6d6-119">Запустите среду SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-119">Start SQL Server Management Studio.</span></span> <span data-ttu-id="9f6d6-120">Подключитесь к экземпляру по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-120">Connect to the default instance.</span></span>  
  
2.  <span data-ttu-id="9f6d6-121">Нажмите кнопку **создать запрос** на панели инструментов Стандартная.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-121">Click **New Query** on the Standard Toolbar.</span></span>  
  
3.  <span data-ttu-id="9f6d6-122">Скопируйте и вставьте следующий полный скрипт в окно запроса.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-122">Copy and paste the following complete script to the query window.</span></span> <span data-ttu-id="9f6d6-123">При необходимости измените сценарий.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-123">Modify the script as needed.</span></span>  
  
     <span data-ttu-id="9f6d6-124">**Примечание.** Выполните `RESTORE` инструкцию, чтобы восстановить резервную копию базы данных (BAK) в службе хранилища Azure на экземпляр базы данных на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f6d6-124">**Note:** You run the `RESTORE` statement to restore the database backup (.bak) in Azure Storage to a database instance in another machine.</span></span>  
  
    ```sql  
  
    USE master   
    GO   
    -- Create a new database to be backed up.   
    CREATE DATABASE TestDbRestoreFrom;   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    SELECT * from dbo.Table1;   
    GO   
    -- Create a credential to be used by SQL Server Backup and Restore with Azure -----Blob Storage Service.   
    USE master;   
    GO   
    CREATE CREDENTIAL BackupCredential    
    WITH IDENTITY= 'teststorageaccnt',   
    SECRET = 'BO1nH/lWRdnc8TGPlQIXmGLWVCoEa48suYSGiAlC73+S0TX5VXo5/LCm8qiyGCYafDg4ZsueDIV3GQ5RXHaRGw=='    
    GO   
    -- Display the newly created credential   
    SELECT * from sys.credentials   
    -- Create a backup in Azure Storage.   
    BACKUP DATABASE TestDBRestoreFrom    
    TO URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
          WITH CREDENTIAL = 'BackupCredential'    
         ,COMPRESSION   
         ,STATS = 5;   
    GO    
    -- Create a Shared Access Signature credential   
    CREATE CREDENTIAL [https://teststorageaccnt.blob.core.windows.net/testrestorefrom]   
    WITH IDENTITY='SHARED ACCESS SIGNATURE',   
    SECRET = 'sv=2012-02-12&sr=c&si=policy_resfrom&sig=EhVpzLUXjG4ThAMLmVhrnoiCt8IfmD3BsuYiMawGzxc%3D'   
    GO   
    USE master;   
    GO   
    RESTORE DATABASE TestDBRestoreFrom    
    FROM URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
    WITH    
    CREDENTIAL = 'BackupCredential',    
    REPLACE,   
    MOVE 'TestDBRestoreFrom' TO 'C:\Backup\TestDBRestoreFrom.mdf',     
    MOVE 'TestDBRestoreFrom_log' TO 'C:\Backup\TestDBRestoreFrom_log.ldf';   
    GO  
  
    ```  
  
 <span data-ttu-id="9f6d6-125">**Конец руководства: SQL Server файлы данных в службе хранилища Azure**</span><span class="sxs-lookup"><span data-stu-id="9f6d6-125">**End of Tutorial: SQL Server Data Files in Azure Storage service**</span></span>  
  
  
