---
title: Руководство по резервному копированию и восстановлению SQL Server с помощью службы хранилища BLOB-объектов Azure | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 9e1d94ce-2c93-45d1-ae2a-2a7d1fa094c4
author: rothja
ms.author: jroth
ms.openlocfilehash: d15200968011cdb314829736512f39730782dc0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729341"
---
# <a name="tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service"></a><span data-ttu-id="b30c7-102">Руководство по Резервное копирование и восстановление SQL Server с помощью службы хранилищ BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="b30c7-102">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>
  <span data-ttu-id="b30c7-103">Добро пожаловать в начало работы с помощью SQL Server резервного копирования и восстановления с помощью службы хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="b30c7-103">Welcome to the Getting Started with SQL Server Backup and Restore with Azure Blob Storage Service tutorial.</span></span> <span data-ttu-id="b30c7-104">С помощью этого руководства вы научитесь создавать и восстанавливать резервные копии, используя службу хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="b30c7-104">This tutorial helps you understand how to write backups to and restore from the Azure Blob storage service.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="b30c7-105">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="b30c7-105">What You Will Learn</span></span>  
 <span data-ttu-id="b30c7-106">В этом учебнике показано, как создать учетную запись хранения Windows, контейнер больших двоичных объектов, учетные данные для доступа к учетной записи хранения, как записать резервную копию в службу хранилищ больших двоичных объектов и выполнить простое восстановление.</span><span class="sxs-lookup"><span data-stu-id="b30c7-106">This tutorial shows you how to create a Windows Storage account, a blob container, creating credentials to access the storage account, writing a backup to the blob service, and performing a simple restore.</span></span> <span data-ttu-id="b30c7-107">Учебник разделен на четыре занятия.</span><span class="sxs-lookup"><span data-stu-id="b30c7-107">This tutorial is divided into four lessons:</span></span>  
  
 [<span data-ttu-id="b30c7-108">Занятие 1. Создание объектов службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="b30c7-108">Lesson 1: Create Azure Storage Objects</span></span>](../tutorials/lesson-1-create-windows-azure-storage-objects.md)  
 <span data-ttu-id="b30c7-109">На этом занятии вы создадите учетную запись хранения Azure и контейнер больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="b30c7-109">In this lesson, you create an Azure storage account and a blob container.</span></span>  
  
 [<span data-ttu-id="b30c7-110">Урок 2. Создание учетных данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="b30c7-110">Lesson 2: Create a SQL Server Credential</span></span>](../tutorials/lesson-2-create-a-sql-server-credential.md)  
 <span data-ttu-id="b30c7-111">На этом занятии вы создадите учетные данные для хранения сведений о безопасности, которые будут использоваться для доступа к учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="b30c7-111">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 [<span data-ttu-id="b30c7-112">Урок 3. Запись полной резервной копии базы данных в службу хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="b30c7-112">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>](../tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md)  
 <span data-ttu-id="b30c7-113">На этом занятии вам предстоит выполнить инструкцию Т-SQL для записи резервной копии базы данных AdventureWorks2012 в службу хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="b30c7-113">In this lesson, you issue a T-SQL statement to write a backup of the AdventureWorks2012 database to the Azure Blob storage service.</span></span>  
  
 [<span data-ttu-id="b30c7-114">Занятие 4: Восстановление базы данных из полной резервной копии</span><span class="sxs-lookup"><span data-stu-id="b30c7-114">Lesson 4: Perform a Restore From a Full Database Backup</span></span>](../tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md)  
 <span data-ttu-id="b30c7-115">На этом занятии также предстоит выполнить инструкцию T-SQL для восстановления из резервной копии базы данных, созданной на предыдущем занятии.</span><span class="sxs-lookup"><span data-stu-id="b30c7-115">In this lesson, you issue a T-SQL statement to restore from the database backup you created in the previous lesson.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="b30c7-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b30c7-116">Requirements</span></span>  
 <span data-ttu-id="b30c7-117">Чтобы выполнить задания этого руководства, необходимо владеть основными понятиями резервного копирования и восстановления [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и синтаксисом T-SQL.</span><span class="sxs-lookup"><span data-stu-id="b30c7-117">To complete this tutorial, you must be familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore concepts and T-SQL syntax.</span></span> <span data-ttu-id="b30c7-118">Для работы с этим учебником должны быть выполнены следующие требования.</span><span class="sxs-lookup"><span data-stu-id="b30c7-118">To use this tutorial, your system must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="b30c7-119">Установленный экземпляр [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] и база данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="b30c7-119">An instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], and AdventureWorks2012 database installed.</span></span>  
  
     <span data-ttu-id="b30c7-120">Экземпляр SQL Server может быть установлен на локальном компьютере или в виртуальной машине Azure.</span><span class="sxs-lookup"><span data-stu-id="b30c7-120">The SQL Server instance can be on-premises or in an Azure Virtual Machine.</span></span>  
  
     <span data-ttu-id="b30c7-121">Вместо базы данных AdventureWorks2012 можно использовать пользовательскую базу данных, соответственно изменив синтаксис инструкций T-SQL.</span><span class="sxs-lookup"><span data-stu-id="b30c7-121">You can use a user database in place of AdventureWorks2012, and modify the tsql syntax accordingly.</span></span>  
  
-   <span data-ttu-id="b30c7-122">Учетная запись пользователя, применяемая для выдачи команды BACKUP или RESTORE, должна находиться в роли базы данных **db_backup operator** с разрешениями **Alter any credential** .</span><span class="sxs-lookup"><span data-stu-id="b30c7-122">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
### <a name="additional-reading"></a><span data-ttu-id="b30c7-123">Дополнительные материалы</span><span class="sxs-lookup"><span data-stu-id="b30c7-123">Additional Reading</span></span>  
 <span data-ttu-id="b30c7-124">Чтобы разобраться в концепциях и предпочтительных методах использования службы хранилища BLOB-объектов Azure для резервного копирования [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], рекомендуется изучить перечисленные ниже материалы.</span><span class="sxs-lookup"><span data-stu-id="b30c7-124">Following are some recommended reading to understand the concepts, best practices when using Azure Blob storage service for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups.</span></span>  
  
1.  [<span data-ttu-id="b30c7-125">Резервное копирование и восстановление SQL Server с помощью службы хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="b30c7-125">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
2.  <span data-ttu-id="b30c7-126">[Резервное копирование SQL Server на URL-адрес — рекомендации и устранение неполадок](backup-restore/sql-server-backup-to-url-best-practices-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="b30c7-126">[SQL Server Backup to URL Best Practices and Troubleshooting](backup-restore/sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span></span>  
  
  
