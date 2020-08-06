---
title: Занятие 6. Миграция базы данных с исходного компьютера на конечный компьютер в Azure | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: d9134ade-7b03-4c5c-8ed3-3bc369a61691
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9af8a260493561f9728d1677b7667bd3f36cb46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666588"
---
# <a name="lesson-6-migrate-a-database-from-a-source-machine-on-premises-to-a-destination-machine-in-azure"></a><span data-ttu-id="36687-102">Занятие 6: Перенос базы данных с исходного локального компьютера на целевой компьютер в Azure</span><span class="sxs-lookup"><span data-stu-id="36687-102">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>
  <span data-ttu-id="36687-103">В этом занятии предполагается, что у вас уже есть другой SQL Server, который может находиться на другом локальном компьютере или на виртуальной машине в Azure.</span><span class="sxs-lookup"><span data-stu-id="36687-103">This lesson assumes that you already have another SQL Server, which might reside in another on-premises computer or in a virtual machine in Azure.</span></span> <span data-ttu-id="36687-104">Сведения о том, как создать виртуальную машину SQL Server в Azure, см. в статье [Подготовка виртуальной машины SQL Server в Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span><span class="sxs-lookup"><span data-stu-id="36687-104">For information on how to create a SQL Server virtual machine in Azure, see [Provisioning a SQL Server Virtual Machine on Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span></span> <span data-ttu-id="36687-105">После подготовки SQL Server виртуальной машины в Azure убедитесь, что вы можете подключиться к экземпляру SQL Server на этой виртуальной машине с помощью SQL Server Management Studio на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="36687-105">After provisioning a SQL Server virtual machine in Azure, make sure that you can connect to an instance of SQL Server in this virtual machine via SQL Server Management Studio in another computer.</span></span>  
  
 <span data-ttu-id="36687-106">Для этого занятия также предполагается, что вы уже выполнили следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="36687-106">This lesson also assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="36687-107">У вас есть учетная запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="36687-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="36687-108">Вы создали контейнер в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="36687-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="36687-109">Создали политику в контейнере с правами на чтение, запись и перечисление.</span><span class="sxs-lookup"><span data-stu-id="36687-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="36687-110">Создали ключ SAS.</span><span class="sxs-lookup"><span data-stu-id="36687-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="36687-111">Создали учетные данные SQL Server на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="36687-111">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="36687-112">Вы уже создали целевую виртуальную машину SQL Server в Azure.</span><span class="sxs-lookup"><span data-stu-id="36687-112">You already have created a destination SQL Server virtual machine in Azure.</span></span> <span data-ttu-id="36687-113">Рекомендуется создать ее, выбрав образ платформы, содержащий SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="36687-113">We recommend that you create it by selecting a platform image that includes SQL Server 2014.</span></span>  
  
 <span data-ttu-id="36687-114">Чтобы перенести базу данных из локальной SQL Server в другую виртуальную машину в Azure, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="36687-114">To migrate a database from SQL Server on-premises to another virtual machine in Azure, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="36687-115">На исходном компьютере (в этом учебнике это локальный компьютер) откройте окно запросов среды SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="36687-115">In the source machine (which is an on-premises computer in this tutorial), open a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="36687-116">Отсоедините базу данных, чтобы переместить ее на другой компьютер, выполнив следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="36687-116">Detach your database to move it to another machine by executing these statements:</span></span>  
  
    ```  
    -- Detach the database in the source machine   
    USE master  
    EXEC sp_detach_db 'TestDB1', 'true';  
    ```  
  
2.  <span data-ttu-id="36687-117">Если требуется перенести базу данных на целевой компьютер, сначала его необходимо подготовить.</span><span class="sxs-lookup"><span data-stu-id="36687-117">If you need to transfer a database to a destination machine, first you must prepare it.</span></span> <span data-ttu-id="36687-118">Для этого необходимо создать на целевом компьютере учетные данные SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36687-118">To prepare your destination machine, first you need to create a SQL Server credential in the destination machine.</span></span> <span data-ttu-id="36687-119">Если это зашифрованная база данных, необходимо также импортировать сертификат с исходного компьютера на целевой.</span><span class="sxs-lookup"><span data-stu-id="36687-119">If it is an encrypted database, you need to import the certificate from the source machine to the destination machine as well.</span></span>  
  
    1.  <span data-ttu-id="36687-120">Для создания учетных данных SQL Server на целевом компьютере выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="36687-120">To create a SQL Server Credential in the destination machine, follow these steps:</span></span>  
  
        1.  <span data-ttu-id="36687-121">Подключитесь к целевому компьютеру с помощью среды SQL Server Management Studio, которая работает на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="36687-121">Connect to the destination machine via SQL Server Management Studio in your source computer.</span></span>  <span data-ttu-id="36687-122">Или запустите среду SQL Server Management Studio непосредственно на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="36687-122">Or, start SQL Server Management Studio in your destination computer directly.</span></span>  
  
        2.  <span data-ttu-id="36687-123">На панели инструментов Стандартная выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="36687-123">On the Standard tool bar, click **New Query**.</span></span>  
  
        3.  <span data-ttu-id="36687-124">Скопируйте и вставьте следующий пример в окно запроса (при необходимости измените).</span><span class="sxs-lookup"><span data-stu-id="36687-124">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="36687-125">Следующая инструкция создает SQL Server учетные данные для хранения сертификата общего доступа контейнера хранилища.</span><span class="sxs-lookup"><span data-stu-id="36687-125">The following statement creates a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
            ```sql  
  
            USE master   
            GO   
            CREATE CREDENTIAL [http://teststorageaccnt.blob.core.windows.net/testcontainer]   
            WITH IDENTITY='SHARED ACCESS SIGNATURE',   
            SECRET = 'your SAS key'   
            GO  
  
            ```  
  
        4.  <span data-ttu-id="36687-126">Чтобы увидеть все доступные учетные данные, можно выполнить следующую инструкцию в окне запроса:</span><span class="sxs-lookup"><span data-stu-id="36687-126">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
            ```sql  
            SELECT * from sys.credentials   
            ```  
  
        5.  <span data-ttu-id="36687-127">После установления соединения с целевым сервером откройте окно запроса и выполните команду:</span><span class="sxs-lookup"><span data-stu-id="36687-127">When connected to the destination server, open query window, and run:</span></span>  
  
            ```sql  
  
            -- Create a master key and a server certificate   
            USE master   
            GO   
            CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01'; -- You may use a different password.   
            GO   
            CREATE CERTIFICATE MySQLCert   
            FROM FILE = 'C:\certs\MySQLCert.CER'   
            WITH PRIVATE KEY   
            (   
            FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
            DECRYPTION BY PASSWORD = 'MySQLKey01'   
            );   
            GO  
  
            ```  
  
             <span data-ttu-id="36687-128">После завершения этого шага сертификат шифрования, резервная копия которого была получена с исходного компьютера, будет импортирован на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="36687-128">At the end of this step, the destination machine has imported the encryption certificate that was backed up from the source machine.</span></span> <span data-ttu-id="36687-129">Далее можно присоединить файлы данных на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="36687-129">Next, you can attach the data files in the destination machine.</span></span>  
  
    2.  <span data-ttu-id="36687-130">Затем создайте базу данных с файлами данных и журналов, указывающими на существующие файлы в службе хранилища Azure, с помощью команды FOR ATTACH.</span><span class="sxs-lookup"><span data-stu-id="36687-130">Then, create a database with data and log files pointing to the existing files in Azure Storage by using FOR ATTACH option.</span></span> <span data-ttu-id="36687-131">В окне запроса введите следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="36687-131">In the query window, run the following statement:</span></span>  
  
        ```sql  
  
        --Create a database on the destination server   
        CREATE DATABASE TestDB1onDest   
        ON   
        (NAME = TestDB1_data,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf' )   
        LOG ON   
         (NAME = TestDB1_log,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
        FOR ATTACH   
        GO  
  
        ```  
  
    3.  <span data-ttu-id="36687-132">В обозревателе объектов щелкните «Базы данных» и щелкните правой кнопкой «Обновить».</span><span class="sxs-lookup"><span data-stu-id="36687-132">On the Object Explorer, click Databases, right-click Refresh.</span></span> <span data-ttu-id="36687-133">Вы должны увидеть созданную базу данных TestDB1onDest.</span><span class="sxs-lookup"><span data-stu-id="36687-133">You should be able to see the newly created database TestDB1onDest listed.</span></span>  
  
    4.  <span data-ttu-id="36687-134">Затем в окне запроса выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="36687-134">Next, run the following statement in the query window:</span></span>  
  
        ```sql  
  
        USE TestDB1onDest   
        SELECT * FROM Table1;   
        GO  
  
        ```  
  
         <span data-ttu-id="36687-135">Должен быть приведен список всех данных, введенных на занятии 4.</span><span class="sxs-lookup"><span data-stu-id="36687-135">This should list all the data you entered in Lesson 4.</span></span>  
  
 <span data-ttu-id="36687-136">Обратите внимание, что зашифрованная база данных была передана в другой вычислительный экземпляр без перемещения данных.</span><span class="sxs-lookup"><span data-stu-id="36687-136">Note that the encrypted database was transferred to another compute instance with no data movement.</span></span>  
  
 <span data-ttu-id="36687-137">Чтобы создать базу данных с файлами данных и журналов, указывающими на существующие файлы в службе хранилища Azure с помощью SQL Server Management Studio пользовательского интерфейса, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="36687-137">To create a database with data and log files pointing to the existing files in Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="36687-138">В **обозревателе объектов**подключитесь к экземпляру компонента SQL Server Database Engine и разверните его.</span><span class="sxs-lookup"><span data-stu-id="36687-138">In **Object Explorer**, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="36687-139">Щелкните правой кнопкой мыши элемент **Базы данных**, а затем выберите пункт **Создать базу данных**.</span><span class="sxs-lookup"><span data-stu-id="36687-139">Right-click **Databases**, and then click **New Database**.</span></span> <span data-ttu-id="36687-140">Затем щелкните правой кнопкой мыши TestDB1.</span><span class="sxs-lookup"><span data-stu-id="36687-140">Then, right-click TestDB1.</span></span> <span data-ttu-id="36687-141">Щелкните «Задачи» и выберите команду «Отсоединить».</span><span class="sxs-lookup"><span data-stu-id="36687-141">Click Tasks, and then click Detach.</span></span> <span data-ttu-id="36687-142">В диалоговом окне отсоединения установите флажок «Удалить соединения».</span><span class="sxs-lookup"><span data-stu-id="36687-142">In the Detach dialog window, check Drop Connections.</span></span> <span data-ttu-id="36687-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="36687-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="36687-144">Подключитесь к целевому компьютеру, на котором установлен SQL Server 2014 CTP2 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="36687-144">Connect to the destination machine, which has SQL Server 2014 CTP2 or later.</span></span> <span data-ttu-id="36687-145">Чтобы подготовить целевой компьютер, на нем необходимо создать учетные данные SQL Server, которые указывают на тот же контейнер, размещенный в TestDB1.</span><span class="sxs-lookup"><span data-stu-id="36687-145">To prepare your destination machine, you need to create a SQL Server credential in the destination machine to point to the same container that you put TestDB1 in.</span></span> <span data-ttu-id="36687-146">Если вы собираетесь повторно присоединить базу данных на том же компьютере, то нет необходимости создавать другие учетные данные.</span><span class="sxs-lookup"><span data-stu-id="36687-146">If you are going to re-attach in the same computer, you do not need to create another credential.</span></span>  
  
4.  <span data-ttu-id="36687-147">В **обозревателе объектов**щелкните правой кнопкой мыши **базы данных** и выберите команду **присоединить**.</span><span class="sxs-lookup"><span data-stu-id="36687-147">In **Object Explorer**, right-click **Databases** and click **Attach**.</span></span>  
  
5.  <span data-ttu-id="36687-148">Чтобы указать присоединяемую базу данных, в диалоговом окне **Присоединение баз данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="36687-148">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="36687-149">В диалоговом окне « **Размещение файлов базы данных** » выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="36687-149">In the **Locate Database Files** dialog window:</span></span>  
  
     <span data-ttu-id="36687-150">В качестве расположения файла данных базы данных введите: `https://teststorageaccnt.blob.core.windows.net/testcontainer/` .</span><span class="sxs-lookup"><span data-stu-id="36687-150">For Database Data File Location, type: `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span>  
  
     <span data-ttu-id="36687-151">В качестве имени файла введите: `TestDB1Data.mdf` .</span><span class="sxs-lookup"><span data-stu-id="36687-151">For File name, type: `TestDB1Data.mdf`.</span></span>  
  
6.  <span data-ttu-id="36687-152">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="36687-152">Click **OK**.</span></span>  
  
     <span data-ttu-id="36687-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="36687-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="36687-154">**Следующее занятие:**</span><span class="sxs-lookup"><span data-stu-id="36687-154">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="36687-155">Занятие 7: Перенос файлов данных в службу хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="36687-155">Lesson 7: Move your data files to Azure Storage</span></span>](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)  
  
