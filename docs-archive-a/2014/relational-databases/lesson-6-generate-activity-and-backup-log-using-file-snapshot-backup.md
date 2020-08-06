---
title: Занятие 7. Перемещение файлов данных в службу хранилища Azure | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 26aa534a-afe7-4a14-b99f-a9184fc699bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 753863d7b8b8d8fa554f1579bee6837c525efd9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666587"
---
# <a name="lesson-7-move-your-data-files-to-azure-storage"></a><span data-ttu-id="a243d-102">Занятие 7: Перенос файлов данных в службу хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="a243d-102">Lesson 7: Move your data files to Azure Storage</span></span>
  <span data-ttu-id="a243d-103">На этом занятии вы узнаете, как перемещать файлы данных в службу хранилища Azure (но не на экземпляр SQL Server).</span><span class="sxs-lookup"><span data-stu-id="a243d-103">In this lesson, you will learn how to move your data files to Azure Storage (but not your SQL Server instance).</span></span> <span data-ttu-id="a243d-104">Для прохождения этого занятия не требуется завершать занятия 4, 5 и 6.</span><span class="sxs-lookup"><span data-stu-id="a243d-104">To follow this lesson, you do not need to complete Lesson 4, 5, and 6.</span></span>  
  
 <span data-ttu-id="a243d-105">Чтобы переместить файлы данных в службу хранилища Azure, можно использовать `ALTER DATABASE` инструкцию, так как она помогает изменить расположение файлов данных.</span><span class="sxs-lookup"><span data-stu-id="a243d-105">To move your data files to Azure Storage, you can use the `ALTER DATABASE` statement as it helps to change the location of the data files.</span></span>  
  
 <span data-ttu-id="a243d-106">Для этого занятия предполагается, что вы уже выполнили следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="a243d-106">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="a243d-107">У вас есть учетная запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="a243d-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="a243d-108">Вы создали контейнер в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="a243d-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="a243d-109">Создали политику в контейнере с правами на чтение, запись и перечисление.</span><span class="sxs-lookup"><span data-stu-id="a243d-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="a243d-110">Создали ключ SAS.</span><span class="sxs-lookup"><span data-stu-id="a243d-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="a243d-111">Создали учетные данные SQL Server на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a243d-111">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="a243d-112">Затем выполните следующие действия, чтобы переместить файлы данных в службу хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="a243d-112">Next, use the following steps to move your data files to Azure Storage:</span></span>  
  
1.  <span data-ttu-id="a243d-113">Сначала создайте тестовую базу данных на исходном компьютере и добавьте в нее данные.</span><span class="sxs-lookup"><span data-stu-id="a243d-113">First, create a test database in the source machine and add some data to it.</span></span>  
  
    ```sql  
  
    USE master;   
    CREATE DATABASE TestDB1Alter;   
    GO   
    USE TestDB1Alter;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
2.  <span data-ttu-id="a243d-114">Выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="a243d-114">Run the following code:</span></span>  
  
    ```sql  
  
    -- In the following statement, modify the path specified in FILENAME to   
    -- the new location of the file in Azure Storage container.   
    ALTER DATABASE TestDB1Alter    
        MODIFY FILE ( NAME = TestDB1Alter,    
                    FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontaineralter/TestDB1AlterData.mdf');   
    GO  
  
    ```  
  
3.  <span data-ttu-id="a243d-115">При выполнении этой задачи вы увидите следующее сообщение: "файл" TestDB1Alter "был изменен в системном каталоге.</span><span class="sxs-lookup"><span data-stu-id="a243d-115">When you run this, you will see this message: "The file "TestDB1Alter" has been modified in the system catalog.</span></span> <span data-ttu-id="a243d-116">Новый путь будет использоваться при следующем запуске базы данных ".</span><span class="sxs-lookup"><span data-stu-id="a243d-116">The new path will be used the next time the database is started."</span></span>  
  
4.  <span data-ttu-id="a243d-117">Затем переведите базу данных в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="a243d-117">Then, set the database offline.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET OFFLINE;   
    GO  
  
    ```  
  
5.  <span data-ttu-id="a243d-118">Теперь необходимо скопировать файлы данных в службу хранилища Azure с помощью одного из следующих методов: [средство AzCopy](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [размещение страницы](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Справочник по клиентской библиотеке хранилища](https://msdn.microsoft.com/library/azure/dn261237.aspx)или средство обозревателя хранилищ сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="a243d-118">Now, you need to copy the data files to Azure Storage by using one of the following methods: [AzCopy Tool](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [Put Page](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Storage Client Library Reference](https://msdn.microsoft.com/library/azure/dn261237.aspx), or a third-party storage explorer tool.</span></span>  
  
     <span data-ttu-id="a243d-119">**Внимание!** При использовании этого расширения всегда проверяйте, что создается большой двоичный объект страницы, а не блока.</span><span class="sxs-lookup"><span data-stu-id="a243d-119">**Important:** When using this new enhancement, always make sure that you create a page blob not a block blob.</span></span>  
  
6.  <span data-ttu-id="a243d-120">Затем переведите базу данных в оперативный режим.</span><span class="sxs-lookup"><span data-stu-id="a243d-120">Then, set the database online.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET ONLINE;   
    GO  
  
    ```  
  
 <span data-ttu-id="a243d-121">**Следующее занятие:**</span><span class="sxs-lookup"><span data-stu-id="a243d-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="a243d-122">Занятие 8. Восстановление базы данных в службе хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="a243d-122">Lesson 8. Restore a database to Azure Storage</span></span>](lesson-7-restore-a-database-to-a-point-in-time.md)  
  
  
