---
title: Изменение схемы секционирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 515de63f-dfc5-434d-9adb-f3b5992f745a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d57984228e23143d2061df6bf447f978f9bd3c46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666009"
---
# <a name="modify-a-partition-scheme"></a><span data-ttu-id="d7714-102">Изменение схемы секционирования</span><span class="sxs-lookup"><span data-stu-id="d7714-102">Modify a Partition Scheme</span></span>
  <span data-ttu-id="d7714-103">Можно изменить схему секционирования в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , назначив файловую группу для размещения следующей секции, которая добавляется в секционированную таблицу, с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7714-103">You can modify a partition scheme in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by designating a filegroup to hold the next partition that is added to a partitioned table using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d7714-104">Это делается путем присваивания файловой группе свойства NEXT USED.</span><span class="sxs-lookup"><span data-stu-id="d7714-104">You do this by assigning the NEXT USED property to a filegroup.</span></span> <span data-ttu-id="d7714-105">Можно присвоить свойство NEXT USED пустой файловой группе или группе, уже хранящей секцию.</span><span class="sxs-lookup"><span data-stu-id="d7714-105">You can assign the NEXT USED property to an empty filegroup or to one that already holds a partition.</span></span> <span data-ttu-id="d7714-106">Другими словами, файловая группа может содержать несколько секций.</span><span class="sxs-lookup"><span data-stu-id="d7714-106">In other words, a filegroup can hold more than one partition.</span></span>  
  
 <span data-ttu-id="d7714-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d7714-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d7714-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d7714-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d7714-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d7714-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d7714-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d7714-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d7714-111">**Создание секционированной таблицы или индекса с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="d7714-111">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="d7714-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d7714-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d7714-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d7714-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d7714-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d7714-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d7714-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d7714-115">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d7714-116">Все файловые группы, на которые действует инструкция ALTER PARTITION SCHEME, должны быть в режиме "в сети".</span><span class="sxs-lookup"><span data-stu-id="d7714-116">Any filegroup affected by ALTER PARTITION SCHEME must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d7714-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="d7714-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d7714-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="d7714-118">Permissions</span></span>  
 <span data-ttu-id="d7714-119">Для выполнения инструкции ALTER PARTITION SCHEME необходимы следующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="d7714-119">The following permissions can be used to execute ALTER PARTITION SCHEME:</span></span>  
  
-   <span data-ttu-id="d7714-120">Разрешение ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="d7714-120">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="d7714-121">Это разрешение назначено по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенных ролей базы данных **db_owner** и **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="d7714-121">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="d7714-122">Разрешение CONTROL или ALTER на базу данных, в которой была создана схема секционирования.</span><span class="sxs-lookup"><span data-stu-id="d7714-122">CONTROL or ALTER permission on the database in which the partition scheme was created.</span></span>  
  
-   <span data-ttu-id="d7714-123">Разрешения CONTROL SERVER или ALTER ANY DATABASE на сервер базы данных, в которой была создана схема секционирования.</span><span class="sxs-lookup"><span data-stu-id="d7714-123">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition scheme was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d7714-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d7714-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d7714-125">**Изменение схемы секционирования**</span><span class="sxs-lookup"><span data-stu-id="d7714-125">**To modify a partition scheme:**</span></span>  
  
 <span data-ttu-id="d7714-126">Это действие не может быть выполнено при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7714-126">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d7714-127">Чтобы изменить схему секционирования, необходимо сначала удалить схему, после чего создать новую с нужными свойствами при помощи мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="d7714-127">In order to modify a partition scheme, you must first delete the scheme and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="d7714-128">Дополнительные сведения см. в разделах [Создание секционированных таблиц и индексов с помощью SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) в разделе **Создание секционированных таблиц и индексов**.</span><span class="sxs-lookup"><span data-stu-id="d7714-128">For more information, see [Create Partitioned Tables and Indexes Using SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) under **Create Partitioned Tables and Indexes**.</span></span>  
  
#### <a name="to-delete-a-partition-scheme"></a><span data-ttu-id="d7714-129">Удаление схемы секционирования</span><span class="sxs-lookup"><span data-stu-id="d7714-129">To delete a partition scheme</span></span>  
  
1.  <span data-ttu-id="d7714-130">Щелкните знак «плюс», чтобы развернуть базу данных, в которой нужно удалить схему секционирования.</span><span class="sxs-lookup"><span data-stu-id="d7714-130">Click the plus sign to expand the database where you want to delete the partition scheme.</span></span>  
  
2.  <span data-ttu-id="d7714-131">Чтобы развернуть папку **Хранение** , щелкните знак «плюс».</span><span class="sxs-lookup"><span data-stu-id="d7714-131">Click the plus sign to expand the **Storage** folder.</span></span>  
  
3.  <span data-ttu-id="d7714-132">Щелкните знак «плюс», чтобы развернуть папку **Схемы секционирования** .</span><span class="sxs-lookup"><span data-stu-id="d7714-132">Click the plus sign to expand the **Partition Schemes** folder.</span></span>  
  
4.  <span data-ttu-id="d7714-133">Щелкните правой кнопкой мыши схему секционирования, которую нужно удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d7714-133">Right-click the partition scheme you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="d7714-134">В диалоговом окне **Удаление объекта** убедитесь, что выбрана верная схема секционирования, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d7714-134">In the **Delete Object** dialog box, ensure that the correct partition scheme is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d7714-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d7714-135">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-partition-scheme"></a><span data-ttu-id="d7714-136">Изменение схемы секционирования</span><span class="sxs-lookup"><span data-stu-id="d7714-136">To modify a partition scheme</span></span>  
  
1.  <span data-ttu-id="d7714-137">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7714-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d7714-138">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d7714-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d7714-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d7714-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- add five new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test5fg;  
    GO  
    -- if the "myRangePF1" partition function and the "myRangePS1" partition scheme exist,  
    -- drop them from the AdventureWorks2012 database  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
    DROP PARTITION FUNCTION myRangePF1;  
    GO  
    IF EXISTS (SELECT * FROM sys.partition_schemes  
        WHERE name = 'myRangePS1')  
    DROP PARTITION SCHEME myRangePS1;  
    GO  
    -- create the new partition function "myRangePF1" with four partition groups  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    -- create the new partition scheme "myRangePS1"that will use   
    -- the "myRangePF1" partition function with five file groups.  
    -- The last filegroup, "test5fg," will be kept empty but marked  
    -- as the next used filegroup in the partition scheme.  
    CREATE PARTITION SCHEME myRangePS1  
    AS PARTITION myRangePF1  
    TO (test1fg, test2fg, test3fg, test4fg, test5fg);  
    GO  
    --Split "myRangePS1" between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    GO  
    -- Allow the "myRangePS1" partition scheme to use the filegroup "test5fg"  
    -- for the partition with boundary_values of 100 and 500  
    ALTER PARTITION SCHEME myRangePS1  
    NEXT USED test5fg;  
    GO  
    ```  
  
 <span data-ttu-id="d7714-140">Дополнительные сведения см. в разделе [ALTER PARTITION SCHEME (Transact-SQL)](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d7714-140">For more information, see [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span></span>  
  
  
