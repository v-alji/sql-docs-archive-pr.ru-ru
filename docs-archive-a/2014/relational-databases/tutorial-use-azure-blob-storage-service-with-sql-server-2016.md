---
title: Учебник. SQL Server файлов данных в службе хранилища Azure | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e69be67d-da1c-41ae-8c9a-6b12c8c2fb61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 21a0fc11706a0c5ee35cf71e1af69f2927adc9db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668723"
---
# <a name="tutorial-sql-server-data-files-in-azure-storage-service"></a><span data-ttu-id="60541-102">Руководство по Файлы данных SQL Server в службе хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="60541-102">Tutorial: SQL Server Data Files in Azure Storage service</span></span>
  <span data-ttu-id="60541-103">Добро пожаловать в учебник по SQL Server файлы данных в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="60541-103">Welcome to the  SQL Server Data Files in Azure Storage Service tutorial.</span></span> <span data-ttu-id="60541-104">С помощью этого руководства вы научитесь напрямую сохранять файлы данных SQL Server в службе хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="60541-104">This tutorial helps you understand how to store SQL Server data files in the Azure Blob storage service directly.</span></span>  
  
 <span data-ttu-id="60541-105">Поддержка интеграции SQL Server для службы хранилища BLOB-объектов Azure — это усовершенствование SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="60541-105">SQL Server integration support for the Azure Blob storage service is a SQL Server 2014 enhancement.</span></span> <span data-ttu-id="60541-106">Общие сведения о функциональных возможностях и преимуществах использования этой функции см. [в статье SQL Server файлы данных в Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="60541-106">For an overview of the functionality and benefits of using this functionality, see [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="60541-107">Новые знания</span><span class="sxs-lookup"><span data-stu-id="60541-107">What you will learn</span></span>  
 <span data-ttu-id="60541-108">В этом руководстве показано, как хранить файлы данных SQL Server в службе хранилища Azure на нескольких занятиях.</span><span class="sxs-lookup"><span data-stu-id="60541-108">This tutorial shows you how to store SQL Server Data Files in Azure Storage service in multiple lessons.</span></span> <span data-ttu-id="60541-109">Каждое занятие сфокусировано на конкретной задаче.</span><span class="sxs-lookup"><span data-stu-id="60541-109">Each lesson is focused on a specific task.</span></span> <span data-ttu-id="60541-110">Во-первых, вы узнаете, как создать учетную запись хранения и контейнер в Azure.</span><span class="sxs-lookup"><span data-stu-id="60541-110">First, you will learn how to create a storage account and a container in Azure.</span></span> <span data-ttu-id="60541-111">Затем вы узнаете, как создать SQL Server учетные данные для интеграции SQL Server с хранилищем Azure.</span><span class="sxs-lookup"><span data-stu-id="60541-111">Then, you will learn how to create a SQL Server credential to be able to integrate SQL Server with Azure Storage.</span></span> <span data-ttu-id="60541-112">Затем вы создадите базу данных непосредственно в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="60541-112">Then, you will create a database in Azure Storage directly.</span></span> <span data-ttu-id="60541-113">Кроме того, в учебнике демонстрируются сценарии шифрования, миграции, резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="60541-113">In addition, the tutorial will demonstrate encryption, migration, and backup and restore scenarios.</span></span>  
  
 <span data-ttu-id="60541-114">Учебник разделен на девять занятий.</span><span class="sxs-lookup"><span data-stu-id="60541-114">This tutorial is divided into nine lessons:</span></span>  
  
 <span data-ttu-id="60541-115">**[Урок 1. Создание учетной записи службы хранилища Azure и контейнера](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-115">**[Lesson 1: Create Azure Storage Account and Container](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span></span>  
 <span data-ttu-id="60541-116">На этом занятии вы создадите учетную запись хранения Azure и контейнер.</span><span class="sxs-lookup"><span data-stu-id="60541-116">In this lesson, you create an Azure Storage account and a container.</span></span>  
  
 <span data-ttu-id="60541-117">**[Занятие 2. Создание политики в контейнере и создание подписанного URL-адрес &#40;ключ SAS&#41;](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-117">**[Lesson 2. Create a policy on container and generate a Shared Access Signature &#40;SAS&#41; key](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="60541-118">На этом занятии вы создадите политику в контейнере больших двоичных объектов, а также сформируете подписанный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="60541-118">In this lesson, you create a policy on the Blob container and also generate a shared access signature.</span></span>  
  
 <span data-ttu-id="60541-119">**[Урок 3. Создание учетных данных SQL Server](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-119">**[Lesson 3: Create a SQL Server Credential](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="60541-120">На этом занятии вы создадите учетные данные для хранения сведений о безопасности, которые будут использоваться для доступа к учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="60541-120">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="60541-121">**[Занятие 4: Создание базы данных в службе хранилища Azure](../relational-databases/lesson-3-database-backup-to-url.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-121">**[Lesson 4: Create a database in Azure Storage](../relational-databases/lesson-3-database-backup-to-url.md)**</span></span>  
 <span data-ttu-id="60541-122">На этом занятии вы создадите базу данных в службе хранилища Azure, используя параметр создания имени файла базы данных.</span><span class="sxs-lookup"><span data-stu-id="60541-122">In this lesson, you create a database in Azure Storage using CREATE Database FILENAME option.</span></span>  
  
 <span data-ttu-id="60541-123">**[Занятие 5. &#40;необязательно&#41; шифрование базы данных с помощью TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-123">**[Lesson 5. &#40;Optional&#41; Encrypt your database using TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span></span>  
 <span data-ttu-id="60541-124">На этом занятии вы зашифруете базу данных с помощью прозрачного шифрования данных (TDE) и сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="60541-124">In this lesson, you encrypt your database by using a transparent data encryption (TDE) and a server certificate.</span></span>  
  
 <span data-ttu-id="60541-125">**[Занятие 6: Перенос базы данных с исходного локального компьютера на целевой компьютер в Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-125">**[Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="60541-126">На этом занятии вы перенесете базу данных из локальной среды в виртуальную машину в Azure с помощью команды CREATE DATABASE для ATTACH.</span><span class="sxs-lookup"><span data-stu-id="60541-126">In this lesson, you migrate a database from on-premises to a virtual machine in Azure using CREATE DATABASE FOR ATTACH option.</span></span>  
  
 <span data-ttu-id="60541-127">**[Занятие 7: Перенос файлов данных в службу хранилища Azure](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-127">**[Lesson 7: Move your data files to Azure Storage](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="60541-128">На этом занятии вы перемещаете файлы данных в службу хранилища Azure с помощью инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="60541-128">In this lesson, you move your data files to Azure Storage using ALTER DATABASE statement.</span></span>  
  
 <span data-ttu-id="60541-129">**[Занятие 8. Восстановление базы данных в службе хранилища Azure](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-129">**[Lesson 8. Restore a database to Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span></span>  
 <span data-ttu-id="60541-130">На этом занятии вы восстановите базу данных в службе хранилища Azure с помощью параметра RESTORE DATABASE MOVE.</span><span class="sxs-lookup"><span data-stu-id="60541-130">In this lesson, you restore a database to Azure Storage using RESTORE Database MOVE option.</span></span>  
  
 <span data-ttu-id="60541-131">**[Занятие 9. Восстановление базы данных из службы хранилища Azure](lesson-8-restore-as-new-database-from-log-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="60541-131">**[Lesson 9. Restore a database from Azure Storage](lesson-8-restore-as-new-database-from-log-backup.md)**</span></span>  
 <span data-ttu-id="60541-132">На этом занятии вы восстановите базу данных из службы хранилища Azure с помощью параметра RESTORE DATABASE MOVE.</span><span class="sxs-lookup"><span data-stu-id="60541-132">In this lesson, you restore a database from Azure Storage using RESTORE Database MOVE option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60541-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="60541-133">See Also</span></span>  
 [<span data-ttu-id="60541-134">SQL Server файлы данных в Azure</span><span class="sxs-lookup"><span data-stu-id="60541-134">SQL Server Data Files in Azure</span></span>](databases/sql-server-data-files-in-microsoft-azure.md)  
  
  
