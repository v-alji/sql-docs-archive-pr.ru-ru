---
title: Создание секционированных таблиц и индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.createpartition.partitionscheme.f1
- sql12.swb.createpartition.selectoutput.f1
- sql12.swb.createpartition.finish.f1
- sql12.swb.createpartition.summary.f1
- sql12.swb.createpartition.mappartition.f1
- sql12.swb.createpartition.partitioncolumn.f1
- sql12.swb.createpartition.progress.f1
- sql12.swb.createpartition.createjob.f1
- sql12.swb.createpartition.getstart.f1
- sql12.swb.createpartition.partitionfunction.f1
helpviewer_keywords:
- partitioned indexes [SQL Server], creating
- partition schemes [SQL Server], creating
- partition functions [SQL Server], creating
- partitioned tables [SQL Server], creating
- partition functions [SQL Server]
- partition schemes [SQL Server]
ms.assetid: 7641df10-1921-42a7-ba6e-4cb03b3ba9c8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 76ccd8b784902f8542f06f3823e5f8dcb78e9201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658221"
---
# <a name="create-partitioned-tables-and-indexes"></a><span data-ttu-id="b9893-102">Создание секционированных таблиц и индексов</span><span class="sxs-lookup"><span data-stu-id="b9893-102">Create Partitioned Tables and Indexes</span></span>
  <span data-ttu-id="b9893-103">Можно создать секционированную таблицу или индекс в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9893-103">You can create a partitioned table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b9893-104">Данные в секционированной таблице и индексах горизонтально разделены на блоки, которые могут быть распределены между несколькими файловыми группами в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b9893-104">The data in partitioned tables and indexes is horizontally divided into units that can be spread across more than one filegroup in a database.</span></span> <span data-ttu-id="b9893-105">Секционирование может улучшить управляемость и масштабируемость больших таблиц и индексов.</span><span class="sxs-lookup"><span data-stu-id="b9893-105">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
 <span data-ttu-id="b9893-106">Создание секционированной таблицы или индекса обычно включает четыре этапа:</span><span class="sxs-lookup"><span data-stu-id="b9893-106">Creating a partitioned table or index typically happens in four parts:</span></span>  
  
1.  <span data-ttu-id="b9893-107">Создание файловой группы или файловых групп и соответствующих файлов, которые будут содержать секции в соответствии со схемой секционирования.</span><span class="sxs-lookup"><span data-stu-id="b9893-107">Create a filegroup or filegroups and corresponding files that will hold the partitions specified by the partition scheme.</span></span>  
  
2.  <span data-ttu-id="b9893-108">Создание функции секционирования, которая сопоставляет строки таблицы или индекса с секциями, основываясь на значениях элементов заданного столбца.</span><span class="sxs-lookup"><span data-stu-id="b9893-108">Create a partition function that maps the rows of a table or index into partitions based on the values of a specified column.</span></span>  
  
3.  <span data-ttu-id="b9893-109">Создание схемы секционирования, которая сопоставляет секции секционированной таблицы или индекса с новыми файловыми группами.</span><span class="sxs-lookup"><span data-stu-id="b9893-109">Create a partition scheme that maps the partitions of a partitioned table or index to the new filegroups.</span></span>  
  
4.  <span data-ttu-id="b9893-110">Создание или изменение таблицы или индекса и указание схемы секционирования в качестве местоположения хранения.</span><span class="sxs-lookup"><span data-stu-id="b9893-110">Create or modify a table or index and specify the partition scheme as the storage location.</span></span>  
  
 <span data-ttu-id="b9893-111">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b9893-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b9893-112">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b9893-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b9893-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b9893-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b9893-114">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b9893-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b9893-115">**Создание секционированной таблицы или индекса с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="b9893-115">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="b9893-116">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9893-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b9893-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9893-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b9893-118">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b9893-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b9893-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b9893-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b9893-120">Область действия функции и схемы секционирования ограничена базой данных, в которой она была создана.</span><span class="sxs-lookup"><span data-stu-id="b9893-120">The scope of a partition function and scheme is limited to the database in which they have been created.</span></span> <span data-ttu-id="b9893-121">Функции секционирования располагаются в отдельном от других функций пространстве имен внутри базы данных.</span><span class="sxs-lookup"><span data-stu-id="b9893-121">Within the database, partition functions reside in a separate namespace from other functions.</span></span>  
  
-   <span data-ttu-id="b9893-122">Если у каких-либо строк в функции секционирования имеются столбцы секционирования со значениями NULL, эти строки размещаются в крайней левой секции.</span><span class="sxs-lookup"><span data-stu-id="b9893-122">If any rows within a partition function have partitioning columns with null values, these rows are allocated to the left-most partition.</span></span> <span data-ttu-id="b9893-123">Однако если значение NULL указано в качестве граничного значения и указан параметр RIGHT, крайняя левая секция остается пустой, а значения NULL располагаются во второй секции.</span><span class="sxs-lookup"><span data-stu-id="b9893-123">However, if NULL is specified as a boundary value and RIGHT is indicated, the left-most partition remains empty and NULL values are placed in the second partition.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b9893-124">безопасность</span><span class="sxs-lookup"><span data-stu-id="b9893-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b9893-125">Permissions</span><span class="sxs-lookup"><span data-stu-id="b9893-125">Permissions</span></span>  
 <span data-ttu-id="b9893-126">Для создания секционированной таблицы требуется разрешение CREATE TABLE в базе данных и разрешение ALTER для схемы, в которой создается таблица.</span><span class="sxs-lookup"><span data-stu-id="b9893-126">Creating a partitioned table requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span> <span data-ttu-id="b9893-127">Для создания секционированного индекса требуется разрешение ALTER на таблицу или представление, в которых создается индекс.</span><span class="sxs-lookup"><span data-stu-id="b9893-127">Creating a partitioned index requires ALTER permission on the table or view where the index is being created.</span></span> <span data-ttu-id="b9893-128">Создание секционированной таблицы или индекса требует любого из следующих дополнительных разрешений:</span><span class="sxs-lookup"><span data-stu-id="b9893-128">Creating either a partitioned table or index requires any one of the following additional permissions:</span></span>  
  
-   <span data-ttu-id="b9893-129">Разрешение ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="b9893-129">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="b9893-130">Это разрешение назначено по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенных ролей базы данных **db_owner** и **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="b9893-130">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="b9893-131">Разрешение CONTROL или ALTER для базы данных, в которой создаются функция и схема секционирования.</span><span class="sxs-lookup"><span data-stu-id="b9893-131">CONTROL or ALTER permission on the database in which the partition function and partition scheme are being created.</span></span>  
  
-   <span data-ttu-id="b9893-132">Разрешение CONTROL SERVER или ALTER ANY DATABASE для сервера базы данных, в которой создаются функция и схема секционирования.</span><span class="sxs-lookup"><span data-stu-id="b9893-132">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function and partition scheme are being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b9893-133">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9893-133">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b9893-134">Выполните пошаговые инструкции в этой процедуре для создания одной или нескольких файловых групп, соответствующих файлов и таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9893-134">Follow the steps in this procedure to create one or more filegroups, corresponding files, and a table.</span></span> <span data-ttu-id="b9893-135">В следующем примере при создании секционированной таблицы будут приведены ссылки на эти объекты.</span><span class="sxs-lookup"><span data-stu-id="b9893-135">You will reference these objects in the next procedure when you create the partitioned table.</span></span>  
  
#### <a name="to-create-new-filegroups-for-a-partitioned-table"></a><span data-ttu-id="b9893-136">Создание новых файловых групп для секционированной таблицы</span><span class="sxs-lookup"><span data-stu-id="b9893-136">To create new filegroups for a partitioned table</span></span>  
  
1.  <span data-ttu-id="b9893-137">В обозревателе объектов щелкните правой кнопкой мыши базу данных, в которой нужно создать секционированную таблицу, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b9893-137">In Object Explorer, right-click the database in which you want to create a partitioned table and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b9893-138">В диалоговом окне **Свойства базы данных —** *имя_базы_данных* в области **Выбор страницы** щелкните **Файловые группы**.</span><span class="sxs-lookup"><span data-stu-id="b9893-138">In the **Database Properties -** *database_name* dialog box, under **Select a page**, select **Filegroups**.</span></span>  
  
3.  <span data-ttu-id="b9893-139">Ниже **Строки**щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b9893-139">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="b9893-140">В новой строке введите имя файловой группы.</span><span class="sxs-lookup"><span data-stu-id="b9893-140">In the new row, enter the filegroup name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="b9893-141">В дополнение к числу файловых групп, указанному в качестве граничных значений при создании секций, всегда требуется еще одна дополнительная файловая группа.</span><span class="sxs-lookup"><span data-stu-id="b9893-141">You must always have one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
4.  <span data-ttu-id="b9893-142">Продолжайте добавлять строки до создания всех файловых групп для секционированной таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9893-142">Continue adding rows until you have created all of the filegroups for the partitioned table.</span></span>  
  
5.  <span data-ttu-id="b9893-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b9893-143">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="b9893-144">Ниже **Выбор страницы**щелкните **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="b9893-144">Under **Select a page**, select **Files**.</span></span>  
  
7.  <span data-ttu-id="b9893-145">Ниже **Строки**щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b9893-145">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="b9893-146">В новой строке введите имя файла и выберите файловую группу.</span><span class="sxs-lookup"><span data-stu-id="b9893-146">In the new row, enter a filename and select a filegroup.</span></span>  
  
8.  <span data-ttu-id="b9893-147">Продолжайте добавлять строки до создания не менее одного файла для каждой файловой группы.</span><span class="sxs-lookup"><span data-stu-id="b9893-147">Continue adding rows until you have created at least one file for each filegroup.</span></span>  
  
9. <span data-ttu-id="b9893-148">Разверните папку **Таблицы** и создайте таблицу, как обычно.</span><span class="sxs-lookup"><span data-stu-id="b9893-148">Expand the **Tables** folder and create a table as you normally would.</span></span> <span data-ttu-id="b9893-149">Дополнительные сведения см. в статье [Создание таблиц (компонент Database Engine)](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="b9893-149">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span> <span data-ttu-id="b9893-150">В качестве альтернативы можно указать существующую таблицу в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="b9893-150">Alternatively, you can specify an existing table in the next procedure.</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="b9893-151">Создание секционированной таблицы</span><span class="sxs-lookup"><span data-stu-id="b9893-151">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="b9893-152">Щелкните правой кнопкой мыши таблицу для секционирования, выберите **Хранение** и щелкните **Создать секцию…** .</span><span class="sxs-lookup"><span data-stu-id="b9893-152">Right-click the table that you wish to partition, point to **Storage**, and then click **Create Partition...**.</span></span>  
  
2.  <span data-ttu-id="b9893-153">В **Мастере создания секций**на странице **Приветствия мастера создания секций** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9893-153">In the **Create Partition Wizard**, on the **Welcome to the Create Partition Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="b9893-154">На странице **Выбор столбца секционирования** в сетке **Доступные столбцы секционирования** выберите столбец, по которому необходимо секционировать таблицу.</span><span class="sxs-lookup"><span data-stu-id="b9893-154">On the **Select a Partitioning Column** page, in the **Available partitioning columns** grid, select the column on which you want to partition your table.</span></span> <span data-ttu-id="b9893-155">В сетке **Доступные столбцы секционирования** отображаются только столбцы с типами данных, по которым можно секционировать данные.</span><span class="sxs-lookup"><span data-stu-id="b9893-155">Only columns with data types that can be used to partition data will be displayed in the **Available partitioning columns** grid.</span></span> <span data-ttu-id="b9893-156">Если выбрать в качестве столбца секционирования вычисляемый столбец, его необходимо назначить постоянным.</span><span class="sxs-lookup"><span data-stu-id="b9893-156">If you select a computed column as the partitioning column, the column must be designated as a persisted column.</span></span>  
  
     <span data-ttu-id="b9893-157">Выбор столбца секционирования и диапазона значений определяется прежде всего степенью, до которой данные должны быть логически сгруппированы.</span><span class="sxs-lookup"><span data-stu-id="b9893-157">The choices you have for the partitioning column and the values range are determined primarily by the extent to which your data can be grouped in a logical way.</span></span> <span data-ttu-id="b9893-158">Например, можно разделить данные на логические группы по месяцам или кварталам года.</span><span class="sxs-lookup"><span data-stu-id="b9893-158">For example, you may choose to divide your data into logical groupings by months or quarters of a year.</span></span> <span data-ttu-id="b9893-159">Планируемые запросы к данным определяют, адекватно ли такое логическое группирование для управления секциями таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9893-159">The queries you plan to make against your data will determine whether this logical grouping is adequate for managing your table partitions.</span></span> <span data-ttu-id="b9893-160">В качестве столбцов секционирования могут использоваться данные любого типа, кроме `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, типов данных-псевдонимов, а также определяемых пользователем типов данных CLR.</span><span class="sxs-lookup"><span data-stu-id="b9893-160">All data types are valid for use as partitioning columns, except `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, alias data types, or CLR user-defined data types.</span></span>  
  
     <span data-ttu-id="b9893-161">На этой странице доступны следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="b9893-161">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="b9893-162">**Совместное размещение этой таблицы с выбранной секционированной таблицей**</span><span class="sxs-lookup"><span data-stu-id="b9893-162">**Collocate this table to the selected partitioned table**</span></span>  
     <span data-ttu-id="b9893-163">Позволяет выбрать секционированную таблицу, которая содержит связанные данные, для соединения с данной таблицей по столбцу секционирования.</span><span class="sxs-lookup"><span data-stu-id="b9893-163">Allows you to select a partitioned table that contains related data to join with this table on the partitioning column.</span></span> <span data-ttu-id="b9893-164">Таблицы с секциями, объединенные по столбцам секционирования, обычно более эффективны в запросах.</span><span class="sxs-lookup"><span data-stu-id="b9893-164">Tables with partitions joined on the partitioning columns are typically queried more efficiently.</span></span>  
  
     <span data-ttu-id="b9893-165">**Выровнять хранение неуникальных и уникальных индексов с индексированным столбцом секционирования**</span><span class="sxs-lookup"><span data-stu-id="b9893-165">**Storage-align non-unique indexes and unique indexes with an indexed partition column**</span></span>  
     <span data-ttu-id="b9893-166">Выравнивает все индексы таблицы, секционированные с помощью одной и той же схемы.</span><span class="sxs-lookup"><span data-stu-id="b9893-166">Aligns all indexes of the table that are partitioned with the same partition scheme.</span></span> <span data-ttu-id="b9893-167">При выравнивании таблицы и ее индексов секции можно более эффективно перемещать в секционированные таблицы и из них, так как данные секционируются по одному и тому же алгоритму.</span><span class="sxs-lookup"><span data-stu-id="b9893-167">When a table and its indexes are aligned, you can move partitions in and out of partitioned tables more effectively, because your data is partitioned with the same algorithm.</span></span>  
  
     <span data-ttu-id="b9893-168">После выбора столбца секционирования и других столбцов щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9893-168">After selecting the partitioning column and any other options, click **Next**.</span></span>  
  
4.  <span data-ttu-id="b9893-169">На странице **Выбор функции секционирования** в разделе **Выберите функцию секционирования**щелкните **Создать функцию секционирования** или **Существующая функция секционирования**.</span><span class="sxs-lookup"><span data-stu-id="b9893-169">On the **Select a Partition Function** page, under **Select partition function**, click either **New partition function** or **Existing partition function**.</span></span> <span data-ttu-id="b9893-170">При выборе **Создать функцию секционирования**введите имя функции.</span><span class="sxs-lookup"><span data-stu-id="b9893-170">If you choose **New partition function**, enter the name of the function.</span></span> <span data-ttu-id="b9893-171">Если выбран вариант **Существующая функция секционирования**, то выберите в списке имя функции, которая будет использоваться для секционирования.</span><span class="sxs-lookup"><span data-stu-id="b9893-171">If you choose **Existing partition function**, select the name of the function you'd like to use from the list.</span></span> <span data-ttu-id="b9893-172">Обратите внимание, что при отсутствии в базе данных других функций секционирования параметр **Существующая функция секционирования** будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="b9893-172">The **Existing partition function** option will not be available if there are no other partition functions on the database.</span></span>  
  
     <span data-ttu-id="b9893-173">После завершения работы с этой страницей нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9893-173">After completing this page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="b9893-174">На странице **Выбор схемы секционирования** в разделе **Выберите схему секционирования**щелкните **Создать схему секционирования** или **Существующая схема секционирования**.</span><span class="sxs-lookup"><span data-stu-id="b9893-174">On the **Select a Partition Scheme** page, under **Select partition scheme**, click either **New partition scheme** or **Existing partition scheme**.</span></span> <span data-ttu-id="b9893-175">При выборе **Создать схему секционирования**введите имя схемы.</span><span class="sxs-lookup"><span data-stu-id="b9893-175">If you choose **New partition scheme**, enter the name of the scheme.</span></span> <span data-ttu-id="b9893-176">Если выбран вариант **Существующая схема секционирования**, то выберите в списке имя схемы, которая будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="b9893-176">If you choose **Existing partition scheme**, select the name of the scheme you'd like to use from the list.</span></span> <span data-ttu-id="b9893-177">При отсутствии других схем секционирования в базе данных параметр **Существующая схема секционирования** будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="b9893-177">The **Existing partition scheme** option will not be available if there are no other partition schemes on the database.</span></span>  
  
     <span data-ttu-id="b9893-178">После завершения работы с этой страницей нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9893-178">After completing this page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="b9893-179">На странице **Сопоставление секций** в разделе **Диапазон**выберите **Левая граница** или **Правая граница** , чтобы выбрать для включения во все создаваемые файловые группы наибольшее или наименьшее ограничивающее значение.</span><span class="sxs-lookup"><span data-stu-id="b9893-179">On the **Map Partitions** page, under **Range**, select either **Left boundary** or **Right boundary** to specify whether to include the highest or lowest bounding value within each filegroup you create.</span></span> <span data-ttu-id="b9893-180">В дополнение к числу файловых групп, указанному в качестве граничных значений при создании секций, необходимо всегда вводить еще одну дополнительную файловую группу.</span><span class="sxs-lookup"><span data-stu-id="b9893-180">You must always enter one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
     <span data-ttu-id="b9893-181">В сетке **Выбор файловых групп и указание граничных значений** в поле **Файловая группа**выберите файловую группу, в которую будут секционироваться данные.</span><span class="sxs-lookup"><span data-stu-id="b9893-181">In the **Select filegroups and specify boundary values** grid, under **Filegroup**, select the filegroup into which you want to partition your data.</span></span> <span data-ttu-id="b9893-182">В разделе **Граница**введите граничное значение для каждой файловой группы.</span><span class="sxs-lookup"><span data-stu-id="b9893-182">Under **Boundary**, enter the boundary value for each filegroup.</span></span> <span data-ttu-id="b9893-183">Если граничное значение не указано, функция секционирования сопоставляет всю таблицу или индекс с одной секцией, используя имя функции секционирования.</span><span class="sxs-lookup"><span data-stu-id="b9893-183">If boundary value is left empty, the partition function maps the whole table or index into a single partition using the partition function name.</span></span>  
  
     <span data-ttu-id="b9893-184">На этой странице доступны следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="b9893-184">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="b9893-185">**Установить границы…**</span><span class="sxs-lookup"><span data-stu-id="b9893-185">**Set Boundaries...**</span></span>  
     <span data-ttu-id="b9893-186">Открытие диалогового окна **Установка граничных значений** , в котором можно выбрать граничные значения и диапазоны дат для секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-186">Opens the **Set Boundary Values** dialog box to select the boundary values and date ranges you want for your partitions.</span></span> <span data-ttu-id="b9893-187">Этот параметр доступен, только если выбран столбец секционирования, содержащий данные одного из следующих типов: `date`, `datetime`, `smalldatetime`, `datetime2` или `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="b9893-187">This option is only available when you have selected a partitioning column that contains one of the following data types: `date`, `datetime`, `smalldatetime`, `datetime2`, or `datetimeoffset`.</span></span>  
  
     <span data-ttu-id="b9893-188">**Оценка хранения**</span><span class="sxs-lookup"><span data-stu-id="b9893-188">**Estimate storage**</span></span>  
     <span data-ttu-id="b9893-189">Оценка количества строк, необходимого и доступного пространства для хранения каждой файловой группы, указанной для секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-189">Estimates rowcount, required space, and available space for storage for each filegroup specified for the partitions.</span></span> <span data-ttu-id="b9893-190">Эти значения доступны в сетке только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b9893-190">These values are displayed in the grid as read-only values.</span></span>  
  
     <span data-ttu-id="b9893-191">В диалоговом окне **Задание граничных значений** можно задать следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="b9893-191">The **Set Boundary Values** dialog box allows for the following additional options:</span></span>  
  
     <span data-ttu-id="b9893-192">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="b9893-192">**Start date**</span></span>  
     <span data-ttu-id="b9893-193">Выбор даты начала для значений диапазона секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-193">Selects the starting date for the range values of your partitions.</span></span>  
  
     <span data-ttu-id="b9893-194">**Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b9893-194">**End date**</span></span>  
     <span data-ttu-id="b9893-195">Выбор даты окончания для значений диапазона секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-195">Selects the ending date for the range values of your partitions.</span></span> <span data-ttu-id="b9893-196">При выборе **Левая граница** на странице **Сопоставление секций** эта дата будет последним значением для каждой из файловых групп и секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-196">If you selected **Left boundary** on the **Map Partitions** page, this date will be the last value for each filegroup/partition.</span></span> <span data-ttu-id="b9893-197">При выборе **Правая граница** на странице **Сопоставление секций** эта дата будет первым значением в предпоследней файловой группе.</span><span class="sxs-lookup"><span data-stu-id="b9893-197">If you selected **Right boundary** on the **Map Partitions** page, this date will be the first value in the next-to-last filegroup.</span></span>  
  
     <span data-ttu-id="b9893-198">**Диапазон даты**</span><span class="sxs-lookup"><span data-stu-id="b9893-198">**Date range**</span></span>  
     <span data-ttu-id="b9893-199">Выбор степени детализации дат или шага значения диапазона для каждой секции.</span><span class="sxs-lookup"><span data-stu-id="b9893-199">Selects the date granularity or range value increment you want for each partition.</span></span>  
  
     <span data-ttu-id="b9893-200">После завершения работы с этой страницей нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9893-200">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="b9893-201">На странице **Выбор выходного параметра** укажите способ заполнения секционированной таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9893-201">In the **Select an Output Option** page, specify how you want to complete your partitioned table.</span></span> <span data-ttu-id="b9893-202">Выберите **Создать скрипт** для создания скрипта SQL на основе данных на предыдущих страницах мастера.</span><span class="sxs-lookup"><span data-stu-id="b9893-202">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="b9893-203">Выберите **Запустить немедленно** , чтобы создать новую секционированную таблицу после завершения работ со всеми оставшимися страницами мастера.</span><span class="sxs-lookup"><span data-stu-id="b9893-203">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="b9893-204">Выберите **Расписание** , чтобы создать новую секционированную таблицу в заранее заданное время в будущем.</span><span class="sxs-lookup"><span data-stu-id="b9893-204">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="b9893-205">При выборе **Создать скрипт**в **Параметры скрипта**будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b9893-205">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="b9893-206">**Вывести скрипт в файл**</span><span class="sxs-lookup"><span data-stu-id="b9893-206">**Script to file**</span></span>  
     <span data-ttu-id="b9893-207">Создание скрипта как SQL-файла.</span><span class="sxs-lookup"><span data-stu-id="b9893-207">Generates the script as a .sql file.</span></span> <span data-ttu-id="b9893-208">Введите имя и местоположение файла в поле **Имя файла** или щелкните **Обзор** , чтобы открыть диалоговое окно **Расположение файла скрипта** .</span><span class="sxs-lookup"><span data-stu-id="b9893-208">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="b9893-209">В разделе **Сохранить как**выберите **Текст в Юникоде** или **Текст ANSI**.</span><span class="sxs-lookup"><span data-stu-id="b9893-209">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="b9893-210">**Вывести скрипт в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="b9893-210">**Script to Clipboard**</span></span>  
     <span data-ttu-id="b9893-211">Сохранение скрипта в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="b9893-211">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="b9893-212">**Вывести скрипт в новое окно запроса**</span><span class="sxs-lookup"><span data-stu-id="b9893-212">**Script to New Query Window**</span></span>  
     <span data-ttu-id="b9893-213">Скрипт создается в новом окне редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="b9893-213">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="b9893-214">Это параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b9893-214">This is the default selection.</span></span>  
  
     <span data-ttu-id="b9893-215">При выборе **Расписание**щелкните **Изменить расписание**.</span><span class="sxs-lookup"><span data-stu-id="b9893-215">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="b9893-216">В диалоговом окне **Создание расписания задания** в поле **Имя** введите имя расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-216">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="b9893-217">В списке **Тип расписания** выберите тип расписания:</span><span class="sxs-lookup"><span data-stu-id="b9893-217">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="b9893-218">**Запускать автоматически при запуске агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b9893-218">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="b9893-219">**Запускать при бездействии процессоров**</span><span class="sxs-lookup"><span data-stu-id="b9893-219">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="b9893-220">**Повторяющееся**.</span><span class="sxs-lookup"><span data-stu-id="b9893-220">**Recurring**.</span></span> <span data-ttu-id="b9893-221">Выберите этот параметр, если новая секционированная таблица регулярно обновляется с учетом новых данных.</span><span class="sxs-lookup"><span data-stu-id="b9893-221">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="b9893-222">**Однократно**.</span><span class="sxs-lookup"><span data-stu-id="b9893-222">**One time**.</span></span> <span data-ttu-id="b9893-223">Это параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b9893-223">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="b9893-224">Установите или снимите флажок **Включен** , чтобы включить или отключить расписание.</span><span class="sxs-lookup"><span data-stu-id="b9893-224">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="b9893-225">При выборе **Повторяющееся**:</span><span class="sxs-lookup"><span data-stu-id="b9893-225">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="b9893-226">В разделе **Частота**в списке **Выполняется** укажите частоту выполнения:</span><span class="sxs-lookup"><span data-stu-id="b9893-226">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="b9893-227">При выборе **Ежедневно**в поле **Выполняется каждые** укажите частоту повторного выполнения расписания задания в днях.</span><span class="sxs-lookup"><span data-stu-id="b9893-227">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="b9893-228">При выборе **Еженедельно**в поле **Выполняется каждые** укажите частоту повторного выполнения расписания задания в неделях.</span><span class="sxs-lookup"><span data-stu-id="b9893-228">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="b9893-229">Выберите день или дни недели, в которые выполняется расписание задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-229">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="b9893-230">При выборе **Ежемесячно**щелкните **День** или **Определенный**.</span><span class="sxs-lookup"><span data-stu-id="b9893-230">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="b9893-231">При выборе **День**введите дату месяца, в которую должно выполняться расписание задания, и укажите частоту повторного выполнения расписания задания в месяцах.</span><span class="sxs-lookup"><span data-stu-id="b9893-231">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="b9893-232">Например, если требуется, чтобы расписание задания выполнялось 15 числа каждого второго месяца, выберите **День** и введите в первом поле 15 и 2 — во втором поле.</span><span class="sxs-lookup"><span data-stu-id="b9893-232">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="b9893-233">Обратите внимание, что число, введенное во втором поле, не должно превышать 99.</span><span class="sxs-lookup"><span data-stu-id="b9893-233">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="b9893-234">При выборе **Определенный**выберите определенный день недели в месяце, в котором должно выполняться расписание задания, и укажите частоту повторного выполнения расписания задания в месяцах.</span><span class="sxs-lookup"><span data-stu-id="b9893-234">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="b9893-235">Например, если требуется, чтобы расписание задания выполнялось в последний день недели каждого второго месяца, выберите **День**, затем **последний** в первом списке и **рабочий день** во втором списке, а потом введите "2" во втором поле.</span><span class="sxs-lookup"><span data-stu-id="b9893-235">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="b9893-236">Еще можно выбрать **первый**, **второй**, **третий**или **четвертый**, а также конкретные дни недели (например, воскресенье или среду) в первых двух списках.</span><span class="sxs-lookup"><span data-stu-id="b9893-236">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="b9893-237">Обратите внимание, что число, введенное в последнем поле, не должно превышать 99.</span><span class="sxs-lookup"><span data-stu-id="b9893-237">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="b9893-238">В поле **Сколько раз в день**укажите частоту повторного выполнения расписания задания в день запуска расписания задания:</span><span class="sxs-lookup"><span data-stu-id="b9893-238">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="b9893-239">При выборе **Выполнять раз в**укажите определенное время дня для запуска расписания задания в поле **Выполнять раз в** .</span><span class="sxs-lookup"><span data-stu-id="b9893-239">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="b9893-240">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="b9893-240">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="b9893-241">При выборе **Выполняется каждые**укажите частоту выполнения задания в выбранный день в поле **Частота**.</span><span class="sxs-lookup"><span data-stu-id="b9893-241">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="b9893-242">Например, если требуется, чтобы расписание задания выполнялось каждые 2 часа в день запуска расписания задания, выберите **Выполняется кажд.** , введите "2" в первом поле, а затем выберите в списке **часы**.</span><span class="sxs-lookup"><span data-stu-id="b9893-242">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="b9893-243">В этом списке также можно выбрать **минуты** и **секунды**.</span><span class="sxs-lookup"><span data-stu-id="b9893-243">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="b9893-244">Обратите внимание, что число, введенное в первом поле, не должно превышать 100.</span><span class="sxs-lookup"><span data-stu-id="b9893-244">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="b9893-245">В поле **Начинать в** введите время для начала запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-245">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="b9893-246">В поле **Заканчивать в** введите время для завершения повторного выполнения расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-246">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="b9893-247">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="b9893-247">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="b9893-248">В разделе **Длительность**, в области **Дата начала**введите дату начала запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-248">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="b9893-249">Выберите **Дата окончания** или **Без даты окончания** , чтобы указать дату завершения выполнения расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-249">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="b9893-250">При выборе **Дата окончания**введите дату завершения запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-250">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="b9893-251">При выборе значения **Однократно**в **Однократное выполнение**в поле **Дата** введите дату запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-251">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="b9893-252">В поле **Время** введите время запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-252">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="b9893-253">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="b9893-253">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="b9893-254">В разделе **Сводка**в **Описание**проверьте правильность всех параметров расписания задания.</span><span class="sxs-lookup"><span data-stu-id="b9893-254">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="b9893-255">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b9893-255">Click **OK**.</span></span>  
  
     <span data-ttu-id="b9893-256">После завершения работы с этой страницей нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9893-256">After completing this page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="b9893-257">На странице **Просмотр сводки** в разделе **Просмотр выбранных параметров**разверните все доступные параметры, чтобы убедиться в правильности всех настроек секции.</span><span class="sxs-lookup"><span data-stu-id="b9893-257">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all partition settings are correct.</span></span> <span data-ttu-id="b9893-258">Если все настройки правильные, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b9893-258">If everything is as expected, click **Finish**.</span></span>  
  
9. <span data-ttu-id="b9893-259">Страница **Выполнение** мастера создания секций используется для отслеживания сведений о состоянии действий мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-259">On the **Create Partition Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="b9893-260">В зависимости от действий, выбранных в мастере, страница выполнения может содержать одно или несколько действий.</span><span class="sxs-lookup"><span data-stu-id="b9893-260">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="b9893-261">В верхнем поле показано общее состояние мастера и число полученных им сообщений о состоянии, предупреждений и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="b9893-261">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="b9893-262">На странице **Выполнение** мастера создания секций доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b9893-262">The following options are available on the **Create Partition Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="b9893-263">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="b9893-263">**Details**</span></span>  
     <span data-ttu-id="b9893-264">Сведения о событии, состоянии и любых сообщениях, которые возвращены в результате действий мастера.</span><span class="sxs-lookup"><span data-stu-id="b9893-264">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="b9893-265">**Действие**</span><span class="sxs-lookup"><span data-stu-id="b9893-265">**Action**</span></span>  
     <span data-ttu-id="b9893-266">Задает тип и имя каждого действия.</span><span class="sxs-lookup"><span data-stu-id="b9893-266">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="b9893-267">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="b9893-267">**Status**</span></span>  
     <span data-ttu-id="b9893-268">Указывает, вернуло ли действие мастера в целом значение **Успешно** или **Ошибка**.</span><span class="sxs-lookup"><span data-stu-id="b9893-268">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="b9893-269">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="b9893-269">**Message**</span></span>  
     <span data-ttu-id="b9893-270">Любые сообщения об ошибках или предупреждения от процесса.</span><span class="sxs-lookup"><span data-stu-id="b9893-270">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="b9893-271">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="b9893-271">**Report**</span></span>  
     <span data-ttu-id="b9893-272">Создание отчета, содержащего результаты мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-272">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="b9893-273">Доступные параметры: **Просмотреть отчет**, **Сохранить отчет в файл**, **Копировать отчет в буфер обмена**и **Отправить отчет по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="b9893-273">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="b9893-274">**Просмотреть отчет**</span><span class="sxs-lookup"><span data-stu-id="b9893-274">**View Report**</span></span>  
     <span data-ttu-id="b9893-275">Открытие диалогового окна **Просмотр отчета** , которое содержит текстовый отчет о работе мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-275">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="b9893-276">**Сохранить отчет в файл**</span><span class="sxs-lookup"><span data-stu-id="b9893-276">**Save Report to File**</span></span>  
     <span data-ttu-id="b9893-277">Открытие диалогового окна **Сохранить отчет как** .</span><span class="sxs-lookup"><span data-stu-id="b9893-277">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="b9893-278">**Копировать отчет в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="b9893-278">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="b9893-279">Копирование результатов отчета о работе мастера в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="b9893-279">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="b9893-280">**Отправить отчет по электронной почте**</span><span class="sxs-lookup"><span data-stu-id="b9893-280">**Send Report as Email**</span></span>  
     <span data-ttu-id="b9893-281">Копирование результатов отчета о состоянии мастера в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b9893-281">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="b9893-282">Завершив выбор параметров, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b9893-282">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="b9893-283">Мастер создания секций создаст функцию и схему секционирования, а затем применит секционирование к указанной таблице.</span><span class="sxs-lookup"><span data-stu-id="b9893-283">The Create Partition Wizard creates the partition function and scheme and then applies the partitioning to the specified table.</span></span> <span data-ttu-id="b9893-284">Чтобы проверить секционирование таблицы, в обозревателе объектов щелкните правой кнопкой мыши таблицу и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b9893-284">To verify the table partitioning, in Object Explorer, right-click the table and select **Properties**.</span></span> <span data-ttu-id="b9893-285">Перейдите на страницу **Хранилище** .</span><span class="sxs-lookup"><span data-stu-id="b9893-285">Click the **Storage** page.</span></span> <span data-ttu-id="b9893-286">На странице отображается информация, в том числе имя функции секционирования, схема и число секций.</span><span class="sxs-lookup"><span data-stu-id="b9893-286">The page displays information such as the name of the partition function and scheme and the number of partitions.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b9893-287">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9893-287">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="b9893-288">Создание секционированной таблицы</span><span class="sxs-lookup"><span data-stu-id="b9893-288">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="b9893-289">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9893-289">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b9893-290">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b9893-290">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b9893-291">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b9893-291">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b9893-292">В следующем примере показано создание файловых групп, функции и схемы секционирования.</span><span class="sxs-lookup"><span data-stu-id="b9893-292">The example creates new filegroups, a partition function, and a partition scheme.</span></span> <span data-ttu-id="b9893-293">Новая таблица создается при указании схемы секционирования в качестве места хранения.</span><span class="sxs-lookup"><span data-stu-id="b9893-293">A new table is created with the partition scheme specified as the storage location.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Adds four new filegroups to the AdventureWorks2012 database  
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
  
    -- Adds one file for each filegroup.  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test1dat1,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t1dat1.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test1fg;  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test2dat2,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t2dat2.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test3dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t3dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test4dat4,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t4dat4.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test4fg;  
    GO  
    -- Creates a partition function called myRangePF1 that will partition a table into four partitions  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
        AS RANGE LEFT FOR VALUES (1, 100, 1000) ;  
    GO  
    -- Creates a partition scheme called myRangePS1 that applies myRangePF1 to the four filegroups created above  
    CREATE PARTITION SCHEME myRangePS1  
        AS PARTITION myRangePF1  
        TO (test1fg, test2fg, test3fg, test4fg) ;  
    GO  
    -- Creates a partitioned table called PartitionTable that uses myRangePS1 to partition col1  
    CREATE TABLE PartitionTable (col1 int PRIMARY KEY, col2 char(10))  
        ON myRangePS1 (col1) ;  
    GO  
    ```  
  
#### <a name="to-determine-if-a-table-is-partitioned"></a><span data-ttu-id="b9893-294">Определение секционирования таблицы</span><span class="sxs-lookup"><span data-stu-id="b9893-294">To determine if a table is partitioned</span></span>  
  
1.  <span data-ttu-id="b9893-295">Следующий запрос возвращает одну или несколько строк, если таблица `PartitionTable` секционирована.</span><span class="sxs-lookup"><span data-stu-id="b9893-295">The following query returns one or more rows if the table `PartitionTable` is partitioned.</span></span> <span data-ttu-id="b9893-296">Если таблица не секционирована, не возвращается ни одна строка.</span><span class="sxs-lookup"><span data-stu-id="b9893-296">If the table is not partitioned, no rows are returned.</span></span>  
  
    ```  
    SELECT *   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] IN (0,1)   
    JOIN sys.partition_schemes ps   
        ON i.data_space_id = ps.data_space_id   
    WHERE t.name = 'PartitionTable';   
    GO  
    ```  
  
#### <a name="to-determine-the-boundary-values-for-a-partitioned-table"></a><span data-ttu-id="b9893-297">Определение граничных значений для секционированной таблицы</span><span class="sxs-lookup"><span data-stu-id="b9893-297">To determine the boundary values for a partitioned table</span></span>  
  
1.  <span data-ttu-id="b9893-298">Следующий запрос возвращает граничные значения для каждой секции в таблице `PartitionTable` .</span><span class="sxs-lookup"><span data-stu-id="b9893-298">The following query returns the boundary values for each partition in the `PartitionTable` table.</span></span>  
  
    ```  
    SELECT t.name AS TableName, i.name AS IndexName, p.partition_number, p.partition_id, i.data_space_id, f.function_id, f.type_desc, r.boundary_id, r.value AS BoundaryValue   
    FROM sys.tables AS t  
    JOIN sys.indexes AS i  
        ON t.object_id = i.object_id  
    JOIN sys.partitions AS p  
        ON i.object_id = p.object_id AND i.index_id = p.index_id   
    JOIN  sys.partition_schemes AS s   
        ON i.data_space_id = s.data_space_id  
    JOIN sys.partition_functions AS f   
        ON s.function_id = f.function_id  
    LEFT JOIN sys.partition_range_values AS r   
        ON f.function_id = r.function_id and r.boundary_id = p.partition_number  
    WHERE t.name = 'PartitionTable' AND i.type <= 1  
    ORDER BY p.partition_number;  
    ```  
  
#### <a name="to-determine-the-partition-column-for-a-partitioned-table"></a><span data-ttu-id="b9893-299">Определение столбца секционирования секционированной таблицы</span><span class="sxs-lookup"><span data-stu-id="b9893-299">To determine the partition column for a partitioned table</span></span>  
  
1.  <span data-ttu-id="b9893-300">Следующий запрос возвращает имя столбца секционирования таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9893-300">The following query returns the name of the partitioning column for table.</span></span> <span data-ttu-id="b9893-301">`PartitionTable`.</span><span class="sxs-lookup"><span data-stu-id="b9893-301">`PartitionTable`.</span></span>  
  
    ```  
    SELECT   
        t.[object_id] AS ObjectID   
        , t.name AS TableName   
        , ic.column_id AS PartitioningColumnID   
        , c.name AS PartitioningColumnName   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] <= 1 -- clustered index or a heap   
    JOIN sys.partition_schemes AS ps   
        ON ps.data_space_id = i.data_space_id   
    JOIN sys.index_columns AS ic   
        ON ic.[object_id] = i.[object_id]   
        AND ic.index_id = i.index_id   
        AND ic.partition_ordinal >= 1 -- because 0 = non-partitioning column   
    JOIN sys.columns AS c   
        ON t.[object_id] = c.[object_id]   
        AND ic.column_id = c.column_id   
    WHERE t.name = 'PartitionTable' ;   
    GO  
    ```  
  
 <span data-ttu-id="b9893-302">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="b9893-302">For more information, see:</span></span>  
  
-   [<span data-ttu-id="b9893-303">Параметры инструкции ALTER DATABASE для файлов и файловых групп (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9893-303">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
-   [<span data-ttu-id="b9893-304">CREATE PARTITION FUNCTION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9893-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-function-transact-sql)  
  
-   [<span data-ttu-id="b9893-305">CREATE PARTITION SCHEME (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9893-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-scheme-transact-sql)  
  
-   [<span data-ttu-id="b9893-306">CREATE TABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9893-306">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
