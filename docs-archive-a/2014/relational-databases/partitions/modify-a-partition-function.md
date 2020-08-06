---
title: Изменение функции секционирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae5bfc09-f27a-4ea9-9518-485278b11674
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bf14e633e62839b1abca7f38f833efab933c18f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729421"
---
# <a name="modify-a-partition-function"></a><span data-ttu-id="24100-102">Изменение функции секционирования</span><span class="sxs-lookup"><span data-stu-id="24100-102">Modify a Partition Function</span></span>
  <span data-ttu-id="24100-103">Вы можете изменить способ секционирования таблицы или индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] путем увеличения или уменьшения указанного числа секций с шагом 1 в функции секционирования секционированной таблицы или индекса при помощи [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24100-103">You can change the way a table or index is partitioned in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by adding or subtracting the number of partitions specified, in increments of 1, in the partition function of the partitioned table or index by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="24100-104">Добавление секции осуществляется путем разбиения существующей секции на две и переопределением границ новых секций.</span><span class="sxs-lookup"><span data-stu-id="24100-104">When you add a partition, you do so by "splitting" an existing partition into two partitions and redefining the boundaries of the new partitions.</span></span> <span data-ttu-id="24100-105">Удаление секции происходит путем слияния двух секций в одну на границе.</span><span class="sxs-lookup"><span data-stu-id="24100-105">When you drop a partition, you do so by "merging" the boundaries of two partitions into one.</span></span> <span data-ttu-id="24100-106">Это действие повторно заполняет одну секцию и оставляет другую незаполненной.</span><span class="sxs-lookup"><span data-stu-id="24100-106">This last action repopulates one partition and leaves the other partition unassigned.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="24100-107">Несколько таблиц или индексов могут использовать одинаковую функцию секционирования.</span><span class="sxs-lookup"><span data-stu-id="24100-107">More than one table or index can use the same partition function.</span></span> <span data-ttu-id="24100-108">При изменении функции секционирования затрагиваются все таблицы и индексы в одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="24100-108">When you modify a partition function, you affect all of them in a single transaction.</span></span> <span data-ttu-id="24100-109">Проверьте зависимости функции секционирования перед внесением изменений.</span><span class="sxs-lookup"><span data-stu-id="24100-109">Check the partition function's dependencies before modifying it.</span></span>  
  
 <span data-ttu-id="24100-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="24100-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="24100-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="24100-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="24100-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="24100-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="24100-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="24100-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="24100-114">**Изменение функции секционирования при помощи:**</span><span class="sxs-lookup"><span data-stu-id="24100-114">**To modify a partition function, using:**</span></span>  
  
     [<span data-ttu-id="24100-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="24100-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="24100-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="24100-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="24100-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="24100-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="24100-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="24100-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="24100-119">Инструкция ALTER PARTITION FUNCTION может использоваться только для разделения одной секции на две или для слияния двух секций в одну.</span><span class="sxs-lookup"><span data-stu-id="24100-119">ALTER PARTITION FUNCTION can only be used for splitting one partition into two, or for merging two partitions into one.</span></span> <span data-ttu-id="24100-120">Чтобы изменить способ секционирование таблиц или индексов (например, с 10 секций до 5), вы можете использовать один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="24100-120">To change the way a table or index is partitioned (from 10 partitions to 5, for example), you can use any one of the following options:</span></span>  
  
    -   <span data-ttu-id="24100-121">Создайте новую секционированную таблицу с необходимой функцией секционирования, затем вставьте данные из старой таблицы в новую при помощи инструкции INSERT INTO... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] или воспользуйтесь **Мастером управления секциями** в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24100-121">Create a new partitioned table with the desired partition function, and then insert the data from the old table into the new table by using either an INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or the **Manage Partition Wizard** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="24100-122">Создайте секционированный кластеризованный индекс по всей куче.</span><span class="sxs-lookup"><span data-stu-id="24100-122">Create a partitioned clustered index on a heap.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="24100-123">Удаление результатов секционированного кластеризованного индекса в секционированной куче.</span><span class="sxs-lookup"><span data-stu-id="24100-123">Dropping a partitioned clustered index results in a partitioned heap.</span></span>  
  
    -   <span data-ttu-id="24100-124">Удалите и заново создайте существующий секционированный индекс с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX с предложением DROP EXISTING = ON.</span><span class="sxs-lookup"><span data-stu-id="24100-124">Drop and rebuild an existing partitioned index by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX statement with the DROP EXISTING = ON clause.</span></span>  
  
    -   <span data-ttu-id="24100-125">Выполните последовательность инструкций ALTER PARTITION FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="24100-125">Perform a sequence of ALTER PARTITION FUNCTION statements.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="24100-126">не поддерживает репликацию для изменения функций секционирования.</span><span class="sxs-lookup"><span data-stu-id="24100-126">does not provide replication support for modifying a partition function.</span></span> <span data-ttu-id="24100-127">Если нужно внести изменения в функцию секционирования в базе данных публикации, необходимо сделать это вручную и в базе данных подписки.</span><span class="sxs-lookup"><span data-stu-id="24100-127">If you want to make changes to a partition function in the publication database, you must do this manually in the subscription database.</span></span>  
  
-   <span data-ttu-id="24100-128">Все файловые группы, обрабатываемые ALTER PARTITION FUNCTION, должны находиться в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="24100-128">All filegroups that are affected by ALTER PARTITION FUNCTION must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="24100-129">безопасность</span><span class="sxs-lookup"><span data-stu-id="24100-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="24100-130">Permissions</span><span class="sxs-lookup"><span data-stu-id="24100-130">Permissions</span></span>  
 <span data-ttu-id="24100-131">Для выполнения инструкции ALTER PARTITION FUNCTION может использоваться одно из перечисленных ниже разрешений.</span><span class="sxs-lookup"><span data-stu-id="24100-131">Any one of the following permissions can be used to execute ALTER PARTITION FUNCTION:</span></span>  
  
-   <span data-ttu-id="24100-132">Разрешение ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="24100-132">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="24100-133">Это разрешение назначено по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенных ролей базы данных **db_owner** и **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="24100-133">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="24100-134">Разрешение CONTROL или ALTER в базе данных, в которой была создана функция секционирования.</span><span class="sxs-lookup"><span data-stu-id="24100-134">CONTROL or ALTER permission on the database in which the partition function was created.</span></span>  
  
-   <span data-ttu-id="24100-135">Разрешение CONTROL SERVER или ALTER ANY DATABASE на сервере базы данных, в которой была создана функция секционирования.</span><span class="sxs-lookup"><span data-stu-id="24100-135">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="24100-136">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="24100-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="24100-137">**Изменение функции секционирования**</span><span class="sxs-lookup"><span data-stu-id="24100-137">**To modify a partition function:**</span></span>  
  
 <span data-ttu-id="24100-138">Это действие не может быть выполнено при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24100-138">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="24100-139">Чтобы изменить функцию секционирования, необходимо сначала удалить функцию, после чего создать новую с нужными свойствами при помощи мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="24100-139">In order to modify a partition function, you must first delete the function and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="24100-140">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="24100-140">For more information, see</span></span>  
  
#### <a name="to-delete-a-partition-function"></a><span data-ttu-id="24100-141">Удаление функции секционирования</span><span class="sxs-lookup"><span data-stu-id="24100-141">To delete a partition function</span></span>  
  
1.  <span data-ttu-id="24100-142">Разверните базу данных, на которой требуется удалить функцию секционирования, а затем разверните папку **Хранение** .</span><span class="sxs-lookup"><span data-stu-id="24100-142">Expand the database where you want to delete the partition function and then expand the **Storage** folder.</span></span>  
  
2.  <span data-ttu-id="24100-143">Разверните папку **Функции секционирования** .</span><span class="sxs-lookup"><span data-stu-id="24100-143">Expand the **Partition Functions** folder.</span></span>  
  
3.  <span data-ttu-id="24100-144">Щелкните правой кнопкой мыши функцию секционирования, которую нужно удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="24100-144">Right-click the partition function you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="24100-145">В диалоговом окне **Удаление объекта** убедитесь, что выбрана верная функция секционирования, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="24100-145">In the **Delete Object** dialog box, ensure that the correct partition function is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="24100-146">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="24100-146">Using Transact-SQL</span></span>  
  
#### <a name="to-split-a-single-partition-into-two-partitions"></a><span data-ttu-id="24100-147">Разбиение одной секции на две</span><span class="sxs-lookup"><span data-stu-id="24100-147">To split a single partition into two partitions</span></span>  
  
1.  <span data-ttu-id="24100-148">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24100-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="24100-149">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="24100-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="24100-150">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="24100-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Split the partition between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    ```  
  
#### <a name="to-merge-two-partitions-into-one-partition"></a><span data-ttu-id="24100-151">Слияние двух секций в одну</span><span class="sxs-lookup"><span data-stu-id="24100-151">To merge two partitions into one partition</span></span>  
  
1.  <span data-ttu-id="24100-152">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24100-152">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="24100-153">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="24100-153">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="24100-154">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="24100-154">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Merge the partitions between boundary_values 1 and 100  
    --and between boundary_values 100 and 1000 to create one partition  
    --between boundary_values 1 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    MERGE RANGE (100);  
    ```  
  
 <span data-ttu-id="24100-155">Дополнительные сведения см. в статье [ALTER PARTITION FUNCTION (Transact-SQL)](/sql/t-sql/statements/alter-partition-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="24100-155">For more information, see [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span></span>  
  
  
