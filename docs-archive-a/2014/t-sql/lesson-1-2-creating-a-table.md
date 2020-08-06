---
title: Создание таблицы (учебник) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating tables
ms.assetid: 653f2dd3-36a2-4bd5-8703-71a57d244661
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c772f2527bd5ddb8a6759cbaa72d8aed9277f5cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665700"
---
# <a name="creating-a-table-tutorial"></a><span data-ttu-id="814dd-102">Создание таблицы (Учебник)</span><span class="sxs-lookup"><span data-stu-id="814dd-102">Creating a Table (Tutorial)</span></span>
  <span data-ttu-id="814dd-103">Чтобы создать таблицу, нужно указать имя таблицы, имена и типы данных для каждого столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="814dd-103">To create a table, you must provide a name for the table, and the names and data types of each column in the table.</span></span> <span data-ttu-id="814dd-104">Также рекомендуется указывать, допускаются ли значения NULL для каждого из столбцов.</span><span class="sxs-lookup"><span data-stu-id="814dd-104">It is also a good practice to indicate whether null values are allowed in each column.</span></span>  
  
 <span data-ttu-id="814dd-105">Большинство таблиц имеют первичный ключ, состоящий из одной или нескольких столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="814dd-105">Most tables have a primary key, made up of one or more columns of the table.</span></span> <span data-ttu-id="814dd-106">Первичный ключ всегда уникален.</span><span class="sxs-lookup"><span data-stu-id="814dd-106">A primary key is always unique.</span></span> <span data-ttu-id="814dd-107">Компонент [!INCLUDE[ssDE](../includes/ssde-md.md)] потребует выполнения условия неповторения значения первичного ключа в таблице.</span><span class="sxs-lookup"><span data-stu-id="814dd-107">The [!INCLUDE[ssDE](../includes/ssde-md.md)] will enforce the restriction that any primary key value cannot be repeated in the table.</span></span>  
  
 <span data-ttu-id="814dd-108">Список типов данных и ссылки на их описание см. в разделе [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="814dd-108">For a list of data types and links for a description of each, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="814dd-109">Компонент [!INCLUDE[ssDE](../includes/ssde-md.md)] может быть установлен с учетом регистра и без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="814dd-109">The [!INCLUDE[ssDE](../includes/ssde-md.md)] can be installed as case sensitive or non-case sensitive.</span></span> <span data-ttu-id="814dd-110">Если компонент [!INCLUDE[ssDE](../includes/ssde-md.md)] установлен с учетом регистра, имена объектов должны иметь одно и тоже имя.</span><span class="sxs-lookup"><span data-stu-id="814dd-110">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as case sensitive, object names must always have the same case.</span></span> <span data-ttu-id="814dd-111">Например, таблица с именем OrderData будет отличаться от таблицы ORDERDATA.</span><span class="sxs-lookup"><span data-stu-id="814dd-111">For example, a table named OrderData is a different table from a table named ORDERDATA.</span></span> <span data-ttu-id="814dd-112">Если компонент [!INCLUDE[ssDE](../includes/ssde-md.md)] установлен без учета регистра, эти два имени таблицы будут рассматриваться как одна таблица, то есть имя может быть использовано только один раз.</span><span class="sxs-lookup"><span data-stu-id="814dd-112">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as non-case sensitive, those two table names are considered to be the same table, and that name can only be used one time.</span></span>  
  
### <a name="to-create-a-database-to-contain-the-new-table"></a><span data-ttu-id="814dd-113">Создание базы данных, в которой будет размещаться новая таблица</span><span class="sxs-lookup"><span data-stu-id="814dd-113">To create a database to contain the new table</span></span>  
  
-   <span data-ttu-id="814dd-114">Введите следующий код в окно редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="814dd-114">Enter the following code into a Query Editor window.</span></span>  
  
    ```  
    USE master;  
    GO  
  
    --Delete the TestData database if it exists.  
    IF EXISTS(SELECT * from sys.databases WHERE name='TestData')  
    BEGIN  
        DROP DATABASE TestData;  
    END  
  
    --Create a new database called TestData.  
    CREATE DATABASE TestData;  
    Press the F5 key to execute the code and create the database.  
    ```  
  
### <a name="switch-the-query-editor-connection-to-the-testdata-database"></a><span data-ttu-id="814dd-115">Переключение соединения редактора запросов на базу данных TestData</span><span class="sxs-lookup"><span data-stu-id="814dd-115">Switch the Query Editor connection to the TestData database</span></span>  
  
-   <span data-ttu-id="814dd-116">В окне редактора запросов введите и выполните следующий код, чтобы изменить соединение на базу данных `TestData` .</span><span class="sxs-lookup"><span data-stu-id="814dd-116">In a Query Editor window, type and execute the following code to change your connection to the `TestData` database.</span></span>  
  
    ```  
    USE TestData  
    GO  
    ```  
  
### <a name="to-create-a-table"></a><span data-ttu-id="814dd-117">Создание таблицы</span><span class="sxs-lookup"><span data-stu-id="814dd-117">To create a table</span></span>  
  
-   <span data-ttu-id="814dd-118">В окне редактора запросов введите и выполните следующий код, чтобы создать простую таблицу `Products`.</span><span class="sxs-lookup"><span data-stu-id="814dd-118">In a Query Editor window, type and execute the following code to create a simple table named `Products`.</span></span> <span data-ttu-id="814dd-119">Столбцы таблицы имеют имена `ProductID`, `ProductName`, `Price`и `ProductDescription`.</span><span class="sxs-lookup"><span data-stu-id="814dd-119">The columns in the table are named `ProductID`, `ProductName`, `Price`, and `ProductDescription`.</span></span> <span data-ttu-id="814dd-120">Столбец `ProductID` является первичным ключом таблицы.</span><span class="sxs-lookup"><span data-stu-id="814dd-120">The `ProductID` column is the primary key of the table.</span></span> <span data-ttu-id="814dd-121">`int`, `varchar(25)`, `money`и `text` .</span><span class="sxs-lookup"><span data-stu-id="814dd-121">`int`, `varchar(25)`, `money`, and `text` are all data types.</span></span> <span data-ttu-id="814dd-122">Только столбцы `Price` и `ProductionDescription` могут быть пустыми при вставке или изменении строки.</span><span class="sxs-lookup"><span data-stu-id="814dd-122">Only the `Price` and `ProductionDescription` columns can have no data when a row is inserted or changed.</span></span> <span data-ttu-id="814dd-123">Данная инструкция содержит необязательный элемент (`dbo.`), называемый схемой.</span><span class="sxs-lookup"><span data-stu-id="814dd-123">This statement contains an optional element (`dbo.`) called a schema.</span></span> <span data-ttu-id="814dd-124">Схема — это объект базы данных, к которому принадлежит таблица.</span><span class="sxs-lookup"><span data-stu-id="814dd-124">The schema is the database object that owns the table.</span></span> <span data-ttu-id="814dd-125">Если вы являетесь администратором, схемой по умолчанию будет схема `dbo` .</span><span class="sxs-lookup"><span data-stu-id="814dd-125">If you are an administrator, `dbo` is the default schema.</span></span> <span data-ttu-id="814dd-126">`dbo` означает владельца базы данных.</span><span class="sxs-lookup"><span data-stu-id="814dd-126">`dbo` stands for database owner.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products  
       (ProductID int PRIMARY KEY NOT NULL,  
        ProductName varchar(25) NOT NULL,  
        Price money NULL,  
        ProductDescription text NULL)  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="814dd-127">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="814dd-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="814dd-128">Вставка данных в таблицу и их обновление (учебник)</span><span class="sxs-lookup"><span data-stu-id="814dd-128">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](../t-sql/lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="814dd-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="814dd-129">See Also</span></span>  
 [<span data-ttu-id="814dd-130">CREATE TABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="814dd-130">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
