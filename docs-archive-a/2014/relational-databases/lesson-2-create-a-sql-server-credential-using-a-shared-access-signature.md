---
title: Занятие 3. Создание учетных данных SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 29e57ebd-828f-4dff-b473-c10ab0b1c597
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 808438e544e3beb18b2e2afa9c399b5666277483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739920"
---
# <a name="lesson-3-create-a-sql-server-credential"></a><span data-ttu-id="a4e56-102">Урок 3. Создание учетных данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="a4e56-102">Lesson 3: Create a SQL Server Credential</span></span>
  <span data-ttu-id="a4e56-103">На этом занятии будут созданы учетные данные для хранения сведений о безопасности, используемых для доступа к учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="a4e56-103">In this lesson, you will create a credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="a4e56-104">Учетные данные SQL Server — это объект, который используется для хранения сведений, необходимых для проверки подлинности при подключении к ресурсу вне SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a4e56-104">A SQL Server credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span> <span data-ttu-id="a4e56-105">Учетные данные хранят URI-путь к контейнеру хранилища и значениям ключа подписанного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="a4e56-105">The credential stores the URI path of the storage container and the shared access signature key values.</span></span> <span data-ttu-id="a4e56-106">Для каждого контейнера хранилища, используемого файлом данных или журнала, необходимо создать учетные данные SQL Server, имя которых соответствует пути контейнера.</span><span class="sxs-lookup"><span data-stu-id="a4e56-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span>  
  
 <span data-ttu-id="a4e56-107">Общие сведения об учетных данных см. в разделе [учетные данные &#40;ядро СУБД&#41;](security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a4e56-107">For general information about credentials, see [Credentials &#40;Database Engine&#41;](security/authentication-access/credentials-database-engine.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a4e56-108">Требования к созданию учетных данных SQL Server, описанных ниже, относятся к [SQL Serverным файлам данных в Azure](databases/sql-server-data-files-in-microsoft-azure.md) .</span><span class="sxs-lookup"><span data-stu-id="a4e56-108">The requirements for creating a SQL Server credential described below are specific to the [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md) feature.</span></span> <span data-ttu-id="a4e56-109">Сведения о создании учетных данных для резервного копирования процессов в хранилище Azure см. в разделе [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="a4e56-109">For information on creating credentials for backup processes in Azure storage, see [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
 <span data-ttu-id="a4e56-110">Для создания учетных данных SQL Server выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a4e56-110">To create a SQL Server Credential, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a4e56-111">Подключитесь к среде Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="a4e56-111">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="a4e56-112">В обозревателе объектов подключитесь к экземпляру установленного компонента Database Engine.</span><span class="sxs-lookup"><span data-stu-id="a4e56-112">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="a4e56-113">На панели инструментов Стандартная выберите пункт Создать запрос.</span><span class="sxs-lookup"><span data-stu-id="a4e56-113">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="a4e56-114">Скопируйте и вставьте следующий пример в окно запроса (при необходимости измените).</span><span class="sxs-lookup"><span data-stu-id="a4e56-114">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="a4e56-115">Следующая инструкция создаст SQL Server учетные данные для хранения сертификата общего доступа контейнера хранилища.</span><span class="sxs-lookup"><span data-stu-id="a4e56-115">The following statement will create a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
    ```sql  
  
    USE master  
    CREATE CREDENTIAL credentialname - this name should match the container path and it must start with https.   
       WITH IDENTITY='SHARED ACCESS SIGNATURE', -- this is a mandatory string and do not change it.   
       SECRET = 'sharedaccesssignature' -- this is the shared access signature key that you obtained in Lesson 2.   
    GO  
  
    ```  
  
     <span data-ttu-id="a4e56-116">Дополнительные сведения см. в разделе [Создание учетных данных &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) в Электронная документация на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a4e56-116">For detailed information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) in SQL Server Books Online.</span></span>  
  
5.  <span data-ttu-id="a4e56-117">Чтобы увидеть все доступные учетные данные, можно выполнить следующую инструкцию в окне запроса:</span><span class="sxs-lookup"><span data-stu-id="a4e56-117">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
    ```sql  
    SELECT * from sys.credentials  
    ```  
  
     <span data-ttu-id="a4e56-118">Дополнительные сведения об sys. Credentials см. в разделе [sys. credentials &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) в Электронная документация на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a4e56-118">For more information on sys.credentials, see [sys.credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="a4e56-119">**Следующее занятие:**</span><span class="sxs-lookup"><span data-stu-id="a4e56-119">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="a4e56-120">Занятие 4: Создание базы данных в службе хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="a4e56-120">Lesson 4: Create a database in Azure Storage</span></span>](lesson-3-database-backup-to-url.md)  
  
  
