---
title: Занятие 4. Создание базы данных в службе хранилища Azure | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9ae1501-b614-49d3-b975-6569da8350b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50fca85111d5897b738e577e7735049e0b055a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668303"
---
# <a name="lesson-4-create-a-database-in-azure-storage"></a><span data-ttu-id="f5335-102">Занятие 4: Создание базы данных в службе хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="f5335-102">Lesson 4: Create a database in Azure Storage</span></span>
  <span data-ttu-id="f5335-103">На этом занятии вы узнаете, как создать базу данных с помощью компонента SQL Server Data Files в Azure.</span><span class="sxs-lookup"><span data-stu-id="f5335-103">In this lesson, you will learn how to create a database using the SQL Server Data Files in Azure feature.</span></span> <span data-ttu-id="f5335-104">Обратите внимание, что перед началом этого занятия необходимо завершить занятия 1, 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="f5335-104">Note that before this lesson, you must complete the Lesson 1, 2, and 3.</span></span> <span data-ttu-id="f5335-105">Занятие 3 является очень важным шагом, так как необходимо сохранить сведения о контейнере хранилища Azure и связанном с ним имени политики и ключе SAS в SQL Server хранилище учетных данных перед занятием 4.</span><span class="sxs-lookup"><span data-stu-id="f5335-105">Lesson 3 is a very important step because you need to store the information about your Azure storage container and its associated policy name and SAS key in the SQL Server credential store before Lesson 4.</span></span>  
  
 <span data-ttu-id="f5335-106">Для каждого контейнера хранилища, используемого файлом данных или журнала, необходимо создать учетные данные SQL Server, имя которых соответствует пути контейнера.</span><span class="sxs-lookup"><span data-stu-id="f5335-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span> <span data-ttu-id="f5335-107">Затем можно создать новую базу данных в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="f5335-107">Then, you can create a new database in Azure Storage</span></span>  
  
 <span data-ttu-id="f5335-108">Для этого занятия предполагается, что вы уже выполнили следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f5335-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="f5335-109">У вас есть учетная запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="f5335-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="f5335-110">Вы создали контейнер в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="f5335-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="f5335-111">Создали политику в контейнере с правами на чтение, запись и перечисление.</span><span class="sxs-lookup"><span data-stu-id="f5335-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="f5335-112">Создали ключ SAS.</span><span class="sxs-lookup"><span data-stu-id="f5335-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="f5335-113">Создали учетные данные SQL Server на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5335-113">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="f5335-114">Чтобы создать базу данных в Azure с помощью компонента SQL Server Data Files в службе хранилища Azure, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f5335-114">To create a database in Azure using the SQL Server Data Files in Azure Storage feature, follow these steps:</span></span>  
  
1.  <span data-ttu-id="f5335-115">Подключитесь к среде Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="f5335-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="f5335-116">В обозревателе объектов подключитесь к экземпляру установленного компонента Database Engine.</span><span class="sxs-lookup"><span data-stu-id="f5335-116">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="f5335-117">На панели инструментов Стандартная выберите пункт Создать запрос.</span><span class="sxs-lookup"><span data-stu-id="f5335-117">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="f5335-118">Скопируйте и вставьте следующий пример в окно запроса (при необходимости измените).</span><span class="sxs-lookup"><span data-stu-id="f5335-118">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="f5335-119">Обратите внимание, что поле FILENAME указывает URI-путь к файлу базы данных в контейнере хранилища, он должен начинаться с https.</span><span class="sxs-lookup"><span data-stu-id="f5335-119">Note that the FILENAME field refers to the URI path of the database file in storage container and it must start with https.</span></span>  
  
    ```  
  
    --Create a database that uses a SQL Server credential    
    CREATE DATABASE TestDB1    
    ON   
    (NAME = TestDB1_data,   
       FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf')   
     LOG ON   
    (NAME = TestDB1_log,   
        FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
    GO  
  
    ```  
  
     <span data-ttu-id="f5335-120">Добавьте данные в вашу базу данных.</span><span class="sxs-lookup"><span data-stu-id="f5335-120">Add some data to your database.</span></span>  
  
    ```  
  
    USE TestDB1;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
5.  <span data-ttu-id="f5335-121">Чтобы увидеть новую базу данных TestDB1 на локальном сервере SQL Server, обновите базы данных в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="f5335-121">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span>  
  
6.  <span data-ttu-id="f5335-122">Аналогично, чтобы увидеть вновь созданную базу данных в учетной записи хранения, подключитесь к учетной записи хранения с помощью среды SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="f5335-122">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="f5335-123">Чтобы получить сведения о подключении к хранилищу Azure с помощью SQL Server Management Studio, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f5335-123">For information on how to connect to an Azure storage using SQL Server Management Studio, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="f5335-124">Сначала получите сведения об учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="f5335-124">First, get the storage account information.</span></span> <span data-ttu-id="f5335-125">Войдите на портал управления.</span><span class="sxs-lookup"><span data-stu-id="f5335-125">Log in to the Management Portal.</span></span> <span data-ttu-id="f5335-126">После этого щелкните **Хранилище** и выберите нужную учетную запись хранилища.</span><span class="sxs-lookup"><span data-stu-id="f5335-126">Then, click **Storage** and choose your storage account.</span></span> <span data-ttu-id="f5335-127">Затем щелкните **Управление ключами доступа** в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="f5335-127">When a storage account is selected, click **Manage Access Keys** at the bottom of the page.</span></span> <span data-ttu-id="f5335-128">Откроется диалоговое окно, аналогичное следующему:</span><span class="sxs-lookup"><span data-stu-id="f5335-128">This opens a similar dialog window:</span></span>  
  
         <span data-ttu-id="f5335-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="f5335-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span></span>  
  
    2.  <span data-ttu-id="f5335-130">Скопируйте значения **имени учетной записи хранения** и **первичного ключа доступа** в диалоговое окно **Подключение к службе хранилища Azure** в SSMS.</span><span class="sxs-lookup"><span data-stu-id="f5335-130">Copy the **Storage Account Name** and **Primary Access Key** values to the **Connect to Azure Storage** dialog window in SSMS.</span></span> <span data-ttu-id="f5335-131">Затем нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="f5335-131">Then, click **Connect**.</span></span> <span data-ttu-id="f5335-132">Сведения о контейнерах учетной записи хранилища появятся в SSMS, как показано на снимке экрана ниже.</span><span class="sxs-lookup"><span data-stu-id="f5335-132">This brings the information about storage account containers to SSMS as shown in the following screenshot:</span></span>  
  
         <span data-ttu-id="f5335-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="f5335-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="f5335-134">На следующем снимке экрана показана новая созданная база данных в локальной среде службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="f5335-134">The following screenshot demonstrates the new created database both in on-premises and Azure Storage environment.</span></span>  
  
 <span data-ttu-id="f5335-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="f5335-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="f5335-136">**Примечание.** При наличии активных ссылок на файлы данных в контейнере любые попытки удалить связанные ученые данные SQL Server завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f5335-136">**Note:** If there are any active references to data files in a container, any attempts to delete the associated SQL Server credential fails.</span></span> <span data-ttu-id="f5335-137">Аналогично, если определенный файл базы данных в большом двоичном объекте уже арендуется и его необходимо удалить, вначале необходимо разорвать аренду в большом двоичном объекте.</span><span class="sxs-lookup"><span data-stu-id="f5335-137">Similarly, if there is already a lease on a specific database file in a blob and you want to delete it, first you need to break the lease on the blob.</span></span> <span data-ttu-id="f5335-138">Для этого можно использовать [большой двоичный объект](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span><span class="sxs-lookup"><span data-stu-id="f5335-138">To break the lease, you can use [Lease Blob](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span></span>  
  
 <span data-ttu-id="f5335-139">С помощью этой новой функции можно настроить SQL Server, чтобы любая инструкция CREATE DATABASE по умолчанию создавала облачную базу данных.</span><span class="sxs-lookup"><span data-stu-id="f5335-139">Using this new feature, you can configure SQL Server so that any CREATE DATABASE statement will default to a cloud enabled database.</span></span> <span data-ttu-id="f5335-140">Иными словами, можно задать данные и расположения журналов по умолчанию в свойствах экземпляра SQL Server Management Studio Server, так что при каждом создании базы данных все файлы базы данных (MDF, LDF) создаются как страничные BLOB-объекты в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="f5335-140">In other words, you can set default data and log locations in SQL Server Management Studio Server instance properties so anytime you create a database, all database files (.mdf, .ldf) are created as page blobs in Azure Storage.</span></span>  
  
 <span data-ttu-id="f5335-141">Чтобы создать базу данных в службе хранилища Azure с помощью SQL Server Management Studio пользовательского интерфейса, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f5335-141">To create a database in Azure Storage by using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="f5335-142">В обозревателе объектов подключитесь к экземпляру компонента SQL Server Database Engine и разверните его.</span><span class="sxs-lookup"><span data-stu-id="f5335-142">In Object Explorer, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f5335-143">Щелкните правой кнопкой мыши элемент Базы данных, а затем выберите пункт Создать базу данных.</span><span class="sxs-lookup"><span data-stu-id="f5335-143">Right-click Databases, and then click New Database.</span></span>  
  
3.  <span data-ttu-id="f5335-144">В диалоговом окне «Создание базы данных» введите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="f5335-144">In the New Database dialog window, type a database name.</span></span>  
  
4.  <span data-ttu-id="f5335-145">Измените значения первичных данных по умолчанию и файлов журнала транзакций, щелкнув соответствующую ячейку в сетке файлов базы данных и введя новое значение.</span><span class="sxs-lookup"><span data-stu-id="f5335-145">Change the default values of the primary data and transaction log files, in the Database files grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="f5335-146">Кроме того, укажите путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="f5335-146">Also, specify the path for the file location.</span></span> <span data-ttu-id="f5335-147">В поле «Путь» введите URL-адрес контейнера хранилища, например `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span><span class="sxs-lookup"><span data-stu-id="f5335-147">For Path, type the URL path of the storage container, such as `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span> <span data-ttu-id="f5335-148">В поле «Имя файла» введите физические имена файлов базы данных (MDF и LDF).</span><span class="sxs-lookup"><span data-stu-id="f5335-148">For FileName, type the physical file names of the database files (.mdf, .ldf).</span></span>  
  
     <span data-ttu-id="f5335-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="f5335-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span></span>  
  
     <span data-ttu-id="f5335-150">Дополнительные сведения см. в статье [AДобавление файлов данных или журналов в базу данных](databases/add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="f5335-150">For more information, see [Add Data or Log Files to a Database](databases/add-data-or-log-files-to-a-database.md).</span></span>  
  
5.  <span data-ttu-id="f5335-151">Для всех других параметров сохраните значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5335-151">Keep all other default values.</span></span>  
  
6.  <span data-ttu-id="f5335-152">Щелкните ОК.</span><span class="sxs-lookup"><span data-stu-id="f5335-152">Click OK.</span></span>  
  
 <span data-ttu-id="f5335-153">Чтобы увидеть новую базу данных TestDB1 на локальном сервере SQL Server, обновите базы данных в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="f5335-153">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span> <span data-ttu-id="f5335-154">Аналогично, чтобы увидеть вновь созданную базу данных в учетной записи хранилища, подключитесь к учетной записи хранилища с помощью среды SQL Server Management Studio (SSMS), как описано ранее в этом занятии.</span><span class="sxs-lookup"><span data-stu-id="f5335-154">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS) as explained earlier in this lesson.</span></span>  
  
 <span data-ttu-id="f5335-155">**Следующее занятие:**</span><span class="sxs-lookup"><span data-stu-id="f5335-155">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="f5335-156">Занятие 5. &#40;необязательно&#41; шифрование базы данных с помощью TDE</span><span class="sxs-lookup"><span data-stu-id="f5335-156">Lesson 5. &#40;Optional&#41; Encrypt your database using TDE</span></span>](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)  
  
  
