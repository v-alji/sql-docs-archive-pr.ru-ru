---
title: Создание первичных ключей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- primary keys [SQL Server], creating
ms.assetid: 85c623ca-4656-4d70-a9db-ee4d897cd214
author: stevestein
ms.author: sstein
ms.openlocfilehash: c515ef8f978b41225ff45e87646b0aa7a9706a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669357"
---
# <a name="create-primary-keys"></a><span data-ttu-id="e6215-102">Создание первичных ключей</span><span class="sxs-lookup"><span data-stu-id="e6215-102">Create Primary Keys</span></span>
  <span data-ttu-id="e6215-103">Определить первичный ключ в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6215-103">You can define a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e6215-104">Создание первичного ключа автоматически приводит к созданию соответствующего уникального кластеризованного или некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="e6215-104">Creating a primary key automatically creates a corresponding unique, clustered or nonclustered index.</span></span>  
  
 <span data-ttu-id="e6215-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="e6215-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e6215-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e6215-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e6215-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e6215-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e6215-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e6215-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e6215-109">**Создание первичного ключа с помощью:**</span><span class="sxs-lookup"><span data-stu-id="e6215-109">**To create a primary key, using:**</span></span>  
  
     [<span data-ttu-id="e6215-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6215-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e6215-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6215-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e6215-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e6215-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e6215-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e6215-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e6215-114">В таблице возможно наличие только одного ограничения по первичному ключу.</span><span class="sxs-lookup"><span data-stu-id="e6215-114">A table can contain only one PRIMARY KEY constraint.</span></span>  
  
-   <span data-ttu-id="e6215-115">Все столбцы с ограничением PRIMARY KEY должны иметь признак NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="e6215-115">All columns defined within a PRIMARY KEY constraint must be defined as NOT NULL.</span></span> <span data-ttu-id="e6215-116">Если допустимость значения NULL не указана, то для всех столбцов c ограничением PRIMARY KEY устанавливается признак NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="e6215-116">If nullability is not specified, all columns participating in a PRIMARY KEY constraint have their nullability set to NOT NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e6215-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="e6215-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e6215-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="e6215-118">Permissions</span></span>  
 <span data-ttu-id="e6215-119">Создание новой таблицы с первичным ключом требует разрешения CREATE TABLE в базе данных и разрешения ALTER на схему, в которой создается таблица.</span><span class="sxs-lookup"><span data-stu-id="e6215-119">Creating a new table with a primary key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="e6215-120">Создание первичного ключа в существующей таблице требует разрешения ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="e6215-120">Creating a primary key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e6215-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6215-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-primary-key"></a><span data-ttu-id="e6215-122">Создание первичного ключа</span><span class="sxs-lookup"><span data-stu-id="e6215-122">To create a primary key</span></span>  
  
1.  <span data-ttu-id="e6215-123">В обозревателе объектов щелкните правой кнопкой мыши таблицу, в которую необходимо добавить ограничение UNIQUE, и выберите пункт **конструктор**.</span><span class="sxs-lookup"><span data-stu-id="e6215-123">In Object Explorer, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="e6215-124">В **Конструкторе таблиц**щелкните селектор строк для столбца базы данных, который необходимо определить в качестве первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="e6215-124">In **Table Designer**, click the row selector for the database column you want to define as the primary key.</span></span> <span data-ttu-id="e6215-125">Чтобы выделить несколько столбцов, нажмите и удерживайте клавишу CTRL и щелкните селекторы строк для остальных столбцов.</span><span class="sxs-lookup"><span data-stu-id="e6215-125">If you want to select multiple columns, hold down the CTRL key while you click the row selectors for the other columns.</span></span>  
  
3.  <span data-ttu-id="e6215-126">Щелкните правой кнопкой мыши средство выбора строк столбца и выберите команду **Задать первичный ключ**.</span><span class="sxs-lookup"><span data-stu-id="e6215-126">Right-click the row selector for the column and select **Set Primary Key**.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e6215-127">Чтобы переопределить первичный ключ, необходимо удалить все связи с существующим первичным ключом и только после этого создавать новый первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e6215-127">If you want to redefine the primary key, any relationships to the existing primary key must be deleted before the new primary key can be created.</span></span> <span data-ttu-id="e6215-128">Появится сообщение, предупреждающее об автоматическом удалении в ходе процесса всех существующих связей.</span><span class="sxs-lookup"><span data-stu-id="e6215-128">A message will warn you that existing relationships will be automatically deleted as part of this process.</span></span>  
  
 <span data-ttu-id="e6215-129">Ключевой столбец-источник идентифицируется символом первичного ключа в соответствующем селекторе строк.</span><span class="sxs-lookup"><span data-stu-id="e6215-129">A primary key column is identified by a primary key symbol in its row selector.</span></span>  
  
 <span data-ttu-id="e6215-130">Если первичный ключ состоит более чем из одного столбца, то в одном столбце могут встречаться дублирующиеся значения, но все сочетания значений изо всех столбцов первичного ключа должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="e6215-130">If a primary key consists of more than one column, duplicate values are allowed in one column, but each combination of values from all the columns in the primary key must be unique.</span></span>  
  
 <span data-ttu-id="e6215-131">При определении составного ключа порядок столбцов в первичном ключе совпадает с порядком столбцов, показанным в таблице.</span><span class="sxs-lookup"><span data-stu-id="e6215-131">If you define a compound key, the order of columns in the primary key matches the order of columns as shown in the table.</span></span> <span data-ttu-id="e6215-132">Однако после создания первичного ключа порядок столбцов можно изменить.</span><span class="sxs-lookup"><span data-stu-id="e6215-132">However, you can change the order of columns after the primary key is created.</span></span> <span data-ttu-id="e6215-133">Дополнительные сведения см. в разделе [Изменение первичных ключей](modify-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="e6215-133">For more information, see [Modify Primary Keys](modify-primary-keys.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e6215-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6215-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-primary-key-in-an-existing-table"></a><span data-ttu-id="e6215-135">Создание первичного ключа в существующей таблице</span><span class="sxs-lookup"><span data-stu-id="e6215-135">To create a primary key in an existing table</span></span>  
  
1.  <span data-ttu-id="e6215-136">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6215-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e6215-137">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e6215-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e6215-138">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e6215-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e6215-139">В этом примере создается первичный ключ в столбце `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="e6215-139">The example creates a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Production.TransactionHistoryArchive   
    ADD CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID);  
    GO  
  
    ```  
  
#### <a name="to-create-a-primary-key-in-a-new-table"></a><span data-ttu-id="e6215-140">Создание первичного ключа в новой таблице</span><span class="sxs-lookup"><span data-stu-id="e6215-140">To create a primary key in a new table</span></span>  
  
1.  <span data-ttu-id="e6215-141">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6215-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e6215-142">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e6215-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e6215-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e6215-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e6215-144">В этом примере создается таблица и определяется первичный ключ для столбца `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="e6215-144">The example creates a table and defines a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive1  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="e6215-145">Дополнительные сведения см. в разделах [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE (Transact-SQL)](/sql/t-sql/statements/create-table-transact-sql) и [table_constraint (Transact-SQL)](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6215-145">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
