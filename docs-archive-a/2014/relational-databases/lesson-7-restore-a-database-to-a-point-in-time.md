---
title: Занятие 8. Восстановление базы данных в службе хранилища Azure | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9f99670-e1de-441e-972c-69faffcac17a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: adec725d1b519fb67560dc572823ba0a116aaa54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668300"
---
# <a name="lesson-8-restore-a-database-to-azure-storage"></a><span data-ttu-id="b12eb-103">Занятие 8.</span><span class="sxs-lookup"><span data-stu-id="b12eb-103">Lesson 8.</span></span> <span data-ttu-id="b12eb-104">Восстановление базы данных в службу хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="b12eb-104">Restore a database to Azure Storage</span></span>
  <span data-ttu-id="b12eb-105">На этом занятии вы узнаете, как создать файл резервной копии локально, а затем восстановить его в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="b12eb-105">In this lesson, you will learn how to create a backup file locally and then restore it to Azure Storage.</span></span> <span data-ttu-id="b12eb-106">Обратите внимание, что базу данных можно настроить либо локально, либо на виртуальной машине в Azure.</span><span class="sxs-lookup"><span data-stu-id="b12eb-106">Note that you can have your database either on either on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="b12eb-107">Для прохождения этого занятия не требуется завершать занятия 4, 5, 6 и 7.</span><span class="sxs-lookup"><span data-stu-id="b12eb-107">To follow this lesson, you do not need to complete Lesson 4, 5, 6, and 7.</span></span>  
  
 <span data-ttu-id="b12eb-108">Для этого занятия предполагается, что вы уже выполнили следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="b12eb-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="b12eb-109">У вас есть учетная запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="b12eb-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="b12eb-110">Вы создали контейнер в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="b12eb-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="b12eb-111">Создали политику в контейнере с правами на чтение, запись и перечисление.</span><span class="sxs-lookup"><span data-stu-id="b12eb-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="b12eb-112">Создали ключ SAS.</span><span class="sxs-lookup"><span data-stu-id="b12eb-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="b12eb-113">Создали учетные данные SQL Server на исходном компьютере на основе подписанного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b12eb-113">You have created a SQL Server credential on the source machine based on Shared Access Signature.</span></span>  
  
-   <span data-ttu-id="b12eb-114">Создали базу данных на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b12eb-114">You have created a database in the source machine.</span></span>  
  
 <span data-ttu-id="b12eb-115">Для восстановления базы данных в службе хранилища Azure можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b12eb-115">To restore a database to Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="b12eb-116">На исходном компьютере запустите среду SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="b12eb-116">In the source machine, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="b12eb-117">При подключении к созданной базе данных откройте окно запроса.</span><span class="sxs-lookup"><span data-stu-id="b12eb-117">When connected to the newly created database, open the query window.</span></span> <span data-ttu-id="b12eb-118">Выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="b12eb-118">Run the following statement:</span></span>  
  
    ```sql  
  
    USE TestDB3Restore;   
    GO   
    BACKUP DATABASE TestDB3Restore   
    TO DISK = 'C:\BACKUP\TestDB3Restore.Bak'   
       WITH FORMAT,   
       NAME = 'Full Backup of TestDB3Restore'   
    GO  
  
    ```  
  
3.  <span data-ttu-id="b12eb-119">Затем скопируйте и выполните следующие инструкции в окне запроса.</span><span class="sxs-lookup"><span data-stu-id="b12eb-119">Next, copy and run the following statements in the Query window.</span></span>  
  
    ```sql  
  
    USE master;   
    GO   
    RESTORE DATABASE TestDB3Restore    
    FROM DISK = 'C:\BACKUP\TestDB3Restore.bak'    
    WITH REPLACE,   
    MOVE 'TestDB3Restore' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore.mdf',     
    MOVE 'TestDB3Restore_log' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore_log.ldf';   
    GO  
  
    ```  
  
     <span data-ttu-id="b12eb-120">После завершения этого шага контейнер должен отображать файлы данных (MDF) и журналов (LDF) на портале управления.</span><span class="sxs-lookup"><span data-stu-id="b12eb-120">At the end of this step, your container should list data (.mdf) and (.ldf) files on the Management Portal.</span></span>  
  
 <span data-ttu-id="b12eb-121">Чтобы восстановить базу данных с файлами данных и журналов, указывающими на службу хранилища Azure, с помощью SQL Server Management Studio пользовательского интерфейса, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b12eb-121">To restore a database with data and log files pointing to Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="b12eb-122">В **обозревателе объектов**щелкните имя сервера, чтобы развернуть дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="b12eb-122">In **Object Explorer**, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b12eb-123">Разверните узел **базы данных**и выберите свою базу данных.</span><span class="sxs-lookup"><span data-stu-id="b12eb-123">Expand **Databases**, and, select your database.</span></span>  
  
3.  <span data-ttu-id="b12eb-124">Щелкните правой кнопкой мыши базу данных, укажите на пункт **Задачи**и щелкните **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="b12eb-124">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="b12eb-125">На странице **Общие** в разделе Источник **восстановления** щелкните **исходное** устройство.</span><span class="sxs-lookup"><span data-stu-id="b12eb-125">On the **General** page, in the **Restore** source section, click **Source** device.</span></span>  
  
5.  <span data-ttu-id="b12eb-126">Нажмите кнопку Обзор для текстового поля **исходное** устройство, после чего откроется диалоговое окно **Выбор устройств резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="b12eb-126">Click the browse button for the **Source** device text box, which opens the **Select Backup Devices** dialog box.</span></span>  
  
6.  <span data-ttu-id="b12eb-127">В текстовом поле Носитель резервной копии выберите **файл**и нажмите кнопку **Добавить** , чтобы указать файл резервной копии (BAK).</span><span class="sxs-lookup"><span data-stu-id="b12eb-127">In the Backup media text box, select **File**, and click the **Add** button to locate the backup (.bak) file.</span></span> <span data-ttu-id="b12eb-128">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b12eb-128">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="b12eb-129">На первой странице щелкните **файлы** .</span><span class="sxs-lookup"><span data-stu-id="b12eb-129">Click **Files** on the first page.</span></span>  
  
8.  <span data-ttu-id="b12eb-130">В разделе **Восстановление файлов базы данных** как в поле **восстановить как** введите следующее:</span><span class="sxs-lookup"><span data-stu-id="b12eb-130">In the **Restore Database Files** as section, under **Restore As** field, type the followings:</span></span>  
  
     <span data-ttu-id="b12eb-131">Для файла данных введите: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf` .</span><span class="sxs-lookup"><span data-stu-id="b12eb-131">For data file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf`.</span></span> <span data-ttu-id="b12eb-132">В качестве файла журнала введите: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf` .</span><span class="sxs-lookup"><span data-stu-id="b12eb-132">For log file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf`.</span></span>  
  
     <span data-ttu-id="b12eb-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="b12eb-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span></span>  
  
9. <span data-ttu-id="b12eb-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b12eb-134">Click **OK**.</span></span>  
  
 <span data-ttu-id="b12eb-135">После завершения восстановления войдите на портал управления.</span><span class="sxs-lookup"><span data-stu-id="b12eb-135">When the restore is done, log in to the Management Portal.</span></span> <span data-ttu-id="b12eb-136">Вы должны увидеть MDF- и LDF-файлы в контейнере следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b12eb-136">You should be able to see the .mdf and .ldf files in the container as follows:</span></span>  
  
 <span data-ttu-id="b12eb-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="b12eb-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="b12eb-138">**Следующее занятие:**</span><span class="sxs-lookup"><span data-stu-id="b12eb-138">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="b12eb-139">Занятие 9. Восстановление базы данных из службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="b12eb-139">Lesson 9. Restore a database from Azure Storage</span></span>](../relational-databases/lesson-8-restore-as-new-database-from-log-backup.md)  
  
  
