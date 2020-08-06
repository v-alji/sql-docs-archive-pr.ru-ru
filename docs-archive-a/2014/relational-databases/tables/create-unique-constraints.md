---
title: Создание ограничения уникальности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- UNIQUE constraints [SQL Server], creating
- constraints [SQL Server], creating
- constraints [SQL Server], unique
ms.assetid: a86f9d6f-f242-43be-b65d-b3435b71b62a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 252de63f965f98734a6d62d94bfff9dc5774cab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738168"
---
# <a name="create-unique-constraints"></a><span data-ttu-id="b4576-102">Создание ограничений уникальности</span><span class="sxs-lookup"><span data-stu-id="b4576-102">Create Unique Constraints</span></span>
  <span data-ttu-id="b4576-103">Можно создать ограничение уникальности в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] , чтобы гарантировать, что в определенных столбцах, не участвующих в первичном ключе, не будут встречаться повторяющиеся значения.</span><span class="sxs-lookup"><span data-stu-id="b4576-103">You can create a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] to ensure no duplicate values are entered in specific columns that do not participate in a primary key.</span></span> <span data-ttu-id="b4576-104">Создание ограничения уникальности автоматически приводит к созданию соответствующего уникального индекса.</span><span class="sxs-lookup"><span data-stu-id="b4576-104">Creating a unique constraint automatically creates a corresponding unique index.</span></span>  
  
 <span data-ttu-id="b4576-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b4576-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b4576-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b4576-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b4576-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b4576-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b4576-108">**Создание ограничения уникальности с использованием:**</span><span class="sxs-lookup"><span data-stu-id="b4576-108">**To create a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="b4576-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b4576-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b4576-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4576-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b4576-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b4576-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b4576-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="b4576-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b4576-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="b4576-113">Permissions</span></span>  
 <span data-ttu-id="b4576-114">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="b4576-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b4576-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b4576-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="b4576-116">Создание ограничения уникальности</span><span class="sxs-lookup"><span data-stu-id="b4576-116">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="b4576-117">В **Обозревателе объектов**щелкните правой кнопкой мыши таблицу, в которую необходимо добавить ограничение уникальности, и выберите **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="b4576-117">In **Object Explorer**, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="b4576-118">В меню **Конструктор таблиц** выберите пункт **Индексы/Ключи**.</span><span class="sxs-lookup"><span data-stu-id="b4576-118">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="b4576-119">В диалоговом окне **Индексы и ключи** нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b4576-119">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="b4576-120">В сетке в разделе **Общие**щелкните **Тип** и выберите **Уникальный ключ** в раскрывающемся списке справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="b4576-120">In the grid under **General**, click **Type** and choose **Unique Key** from the drop-down list box to the right of the property.</span></span>  
  
5.  <span data-ttu-id="b4576-121">В меню **Файл** выберите команду **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="b4576-121">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b4576-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4576-122">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="b4576-123">Создание ограничения уникальности</span><span class="sxs-lookup"><span data-stu-id="b4576-123">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="b4576-124">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4576-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4576-125">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b4576-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b4576-126">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b4576-126">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b4576-127">В этом примере создаются таблица `TransactionHistoryArchive4` и ограничение уникальности в столбце `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="b4576-127">The example creates the table `TransactionHistoryArchive4` and creates a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive4  
     (  
       TransactionID int NOT NULL,   
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)   
    );   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-on-an-existing-table"></a><span data-ttu-id="b4576-128">Создание ограничения уникальности в существующей таблице</span><span class="sxs-lookup"><span data-stu-id="b4576-128">To create a unique constraint on an existing table</span></span>  
  
1.  <span data-ttu-id="b4576-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4576-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4576-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b4576-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b4576-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b4576-131">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b4576-132">В этом примере создается ограничение уникальности в столбцах `PasswordHash` и `PasswordSalt` в таблице `Person.Password`.</span><span class="sxs-lookup"><span data-stu-id="b4576-132">The example creates a unique constraint on the columns `PasswordHash` and `PasswordSalt` in the table `Person.Password`.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    ALTER TABLE Person.Password   
    ADD CONSTRAINT AK_Password UNIQUE (PasswordHash, PasswordSalt);   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-in-an-new-table"></a><span data-ttu-id="b4576-133">Создание ограничения уникальности в новой таблице</span><span class="sxs-lookup"><span data-stu-id="b4576-133">To create a unique constraint in an new table</span></span>  
  
1.  <span data-ttu-id="b4576-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4576-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4576-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b4576-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b4576-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b4576-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b4576-137">В этом примере создается таблица и определяется ограничение уникальности в столбце `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="b4576-137">The example creates a table and defines a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive2  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="b4576-138">Дополнительные сведения см. в разделах [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE (Transact-SQL)](/sql/t-sql/statements/create-table-transact-sql) и [table_constraint (Transact-SQL)](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b4576-138">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
