---
title: Репликация на подписчиков, оптимизированных для памяти таблиц | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
ms.assetid: 1a8e6bc7-433e-471d-b646-092dc80a2d1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df61b83d2f6d07cbbd21773b8940dd4e5341f76b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655036"
---
# <a name="replication-to-memory-optimized-table-subscribers"></a><span data-ttu-id="aa43e-102">Репликация на подписчиков оптимизированных для памяти таблиц</span><span class="sxs-lookup"><span data-stu-id="aa43e-102">Replication to Memory-Optimized Table Subscribers</span></span>
  <span data-ttu-id="aa43e-103">Таблицы, выступающие в качестве подписчиков репликации транзакций, за исключением одноранговой репликации транзакций, можно настроить как оптимизированные для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="aa43e-103">Tables acting as transactional replication subscribers, excluding Peer-to-peer transactional replication, can be configured as memory-optimized tables.</span></span> <span data-ttu-id="aa43e-104">Другие конфигурации репликации несовместимы с таблицами, оптимизированными для памяти.</span><span class="sxs-lookup"><span data-stu-id="aa43e-104">Other replication configurations are not compatible with memory-optimized tables.</span></span>  
  
## <a name="configuring-a-memory-optimized-table-as-a-subscriber"></a><span data-ttu-id="aa43e-105">Настройка оптимизированной для памяти таблицы в качестве подписчика</span><span class="sxs-lookup"><span data-stu-id="aa43e-105">Configuring a memory-optimized table as a subscriber</span></span>  
 <span data-ttu-id="aa43e-106">Чтобы настроить оптимизированную для памяти таблицу в качестве подписчика, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="aa43e-106">To configure a memory-optimized table as a subscriber, perform the following steps.</span></span>  
  
 <span data-ttu-id="aa43e-107">**Создание и включение публикации**</span><span class="sxs-lookup"><span data-stu-id="aa43e-107">**Create and Enable Publication**</span></span>  
  
1.  <span data-ttu-id="aa43e-108">Создание публикации.</span><span class="sxs-lookup"><span data-stu-id="aa43e-108">Create a publication.</span></span>  
  
2.  <span data-ttu-id="aa43e-109">Добавьте статьи к публикации.</span><span class="sxs-lookup"><span data-stu-id="aa43e-109">Add articles to the publication.</span></span> <span data-ttu-id="aa43e-110">Для параметра `@upd_cmd` используются соглашения SCALL или SQL.</span><span class="sxs-lookup"><span data-stu-id="aa43e-110">For the `@upd_cmd` parameter, use the SCALL or SQL convention.</span></span>  
  
    ```  
    EXEC sp_addarticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @source_owner = N'dbo',  
        @source_object = N'Mem_Table',  
        @type = N'logbased',  
        @description = null,  
        @creation_script = null,  
        @pre_creation_cmd = N'none',  
        @schema_option = 0x00000000080050DF,  
        @identityrangemanagementoption = N'manual',  
        @destination_table = N'Mem_Table',  
        @destination_owner = N'dbo',  
        @vertical_partition = N'false',  
        @ins_cmd = N'CALL sp_MSins_Mem_Table',  
        @del_cmd = N'CALL sp_MSdel_Mem_Table',  
        @upd_cmd = N'SCALL sp_MSupd_Mem_Table';  
    GO  
    ```  
  
 <span data-ttu-id="aa43e-111">**Создание моментального снимка и изменение схемы**</span><span class="sxs-lookup"><span data-stu-id="aa43e-111">**Generate a Snapshot and Adjust the Schema**</span></span>  
  
1.  <span data-ttu-id="aa43e-112">Создайте задание моментального снимка и сформируйте моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="aa43e-112">Create a snapshot job and generate a snapshot.</span></span>  
  
    ```  
    EXEC sp_addpublication_snapshot @publication = N'Publication1', @frequency_type = 1;  
    EXEC sp_startpublication_snapshot @publication = N'Publication1';  
    ```  
  
2.  <span data-ttu-id="aa43e-113">Перейдите в папку моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="aa43e-113">Navigate to the snapshot folder.</span></span> <span data-ttu-id="aa43e-114">Расположение по умолчанию — «C:\Program Files\Microsoft SQL Server\MSSQL12. \<INSTANCE> \Мсскл\реплдата\унк\кскскс\ииииммддххммсс \\ ".</span><span class="sxs-lookup"><span data-stu-id="aa43e-114">The default location is "C:\Program Files\Microsoft SQL Server\MSSQL12.\<INSTANCE>\MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS\\".</span></span>  
  
3.  <span data-ttu-id="aa43e-115">Нахождение **. SCH** File для таблицы и открывается в Management Studio.</span><span class="sxs-lookup"><span data-stu-id="aa43e-115">Locate the **.SCH** file for your table and open it in Management Studio.</span></span> <span data-ttu-id="aa43e-116">Измените схему таблицы и обновите хранимую процедуру, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="aa43e-116">Change the table schema and update the stored procedure as described below.</span></span>  
  
     <span data-ttu-id="aa43e-117">Вычислите индексы, определенные в IDX-файле.</span><span class="sxs-lookup"><span data-stu-id="aa43e-117">Evaluate the indexes defined in the IDX file.</span></span> <span data-ttu-id="aa43e-118">Измените инструкцию `CREATE TABLE`, чтобы указать необходимые индексы, ограничения, первичный ключ и оптимизированный для памяти синтаксис.</span><span class="sxs-lookup"><span data-stu-id="aa43e-118">Modify `CREATE TABLE` to specify the required indexes, constraints, primary key, and memory-optimized syntax.</span></span> <span data-ttu-id="aa43e-119">В оптимизированных для памяти таблицах столбцы индексов НЕ должны иметь значение NULL, а столбцов индексов с символьными типами данных должны быть представлены в Юникоде и использовать параметры сортировки BIN2.</span><span class="sxs-lookup"><span data-stu-id="aa43e-119">For memory-optimized tables, index columns should be NOT NULL and index columns of character types must be Unicode and use BIN2 collation.</span></span> <span data-ttu-id="aa43e-120">См. пример далее.</span><span class="sxs-lookup"><span data-stu-id="aa43e-120">See example below:</span></span>  
  
    ```  
    SET ANSI_PADDING ON;  
    GO  
  
    SET ANSI_NULLS ON;  
    GO  
  
    SET QUOTED_IDENTIFIER ON;  
    GO  
  
    CREATE TABLE [dbo].[Mem_Table]([c1] [int] NOT NULL,  
        [c2] [float] NOT NULL,  
        [c3] [decimal](10, 2) NOT NULL,  
        [c4] [nvarchar](5) COLLATE SQL_Latin1_General_CP850_BIN2 NOT NULL,  
        INDEX [hash_index_sample_memoryoptimizedtable_c2] HASH (c2) WITH (BUCKET_COUNT = 1024),  
        INDEX [index_sample_memoryoptimizedtable_c3] NONCLUSTERED ([c3]),  
        INDEX [nvarchar_index_sample_memoryoptimizedtable_c4] ([c4]),  
        CONSTRAINT [PK_sample_memoryoptimizedtable] PRIMARY KEY NONCLUSTERED ([c1])) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA);  
    GO  
    ```  
  
4.  <span data-ttu-id="aa43e-121">При использовании соглашения SCALL для параметра `@upd_cmd` перейдите к файлу схемы (SCH) и измените инструкцию обновления таблицы в `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]`, удалив столбцы первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="aa43e-121">When using SCALL convention for the `@upd_cmd` parameter, go to the schema (.SCH) file and change the table update statement in `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` to remove primary key columns.</span></span>  
  
     <span data-ttu-id="aa43e-122">Для поддержки обновления первичного ключа используйте пользовательскую хранимую процедуру обновления, заменив ей инструкцию обновления первичного ключа, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="aa43e-122">To support primary key updates, use a custom update stored procedure to replace the primary key update statement, as follows:</span></span>  
  
    1.  <span data-ttu-id="aa43e-123">Выберите отсутствующие значения столбцов (SCALL предоставляет только столбец, задействованный в операции обновления).</span><span class="sxs-lookup"><span data-stu-id="aa43e-123">Select missing column values (SCALL only provides the column involved into the update operation).</span></span>  
  
    2.  <span data-ttu-id="aa43e-124">Удалите существующую запись.</span><span class="sxs-lookup"><span data-stu-id="aa43e-124">Delete the existing record.</span></span>  
  
    3.  <span data-ttu-id="aa43e-125">Вставьте новую запись с новыми значениями, в том числе с новым первичным ключом.</span><span class="sxs-lookup"><span data-stu-id="aa43e-125">Insert a new record with new values provided including the new primary key.</span></span>  
  
     <span data-ttu-id="aa43e-126">Первоначальная процедура обновления выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="aa43e-126">The original update procedure looks like this:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
                   [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="aa43e-127">Если первичный ключ никогда не должен обновляться у издателя.</span><span class="sxs-lookup"><span data-stu-id="aa43e-127">If the primary key should never be updated on a publisher.</span></span> <span data-ttu-id="aa43e-128">Закомментируйте обновление таких столбцов в процедуре обновления следующим образом.</span><span class="sxs-lookup"><span data-stu-id="aa43e-128">Comment out the update to such columns in the update procedure as follows:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
    --             [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="aa43e-129">Чтобы разрешить поддержку обновлений первичного ключа, добавьте чтение в процедуру обновления следующим образом.</span><span class="sxs-lookup"><span data-stu-id="aa43e-129">To allow the support of updates to the primary key, modify the update procedure to read as follows</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                    @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    select  
                   @c1 = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   @c2 = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   @c3 = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   @c4 = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    from [dbo].[Mem_Table] where [c1] = @pkc1  
    if @@rowcount <> 0 begin  
            delete [dbo].[Mem_Table] where [c1] = @pkc1  
            if @@rowcount <> 0  
                   insert into [dbo].[Mem_Table]([c1],  
                           [c2],  
                           [c3],  
                           [c4]) values (  
                           @c1,  
                           @c2,  
                           @c3,  
                           @c4  
                   )   
    end  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
5.  <span data-ttu-id="aa43e-130">Создайте базу данных подписчика с помощью параметра " **повысить уровень изоляции моментального снимка** " и задайте для параметров сортировки по умолчанию значение Latin1_General_CS_AS_KS_WS в случае использования символьных типов данных, отличных от Юникода.</span><span class="sxs-lookup"><span data-stu-id="aa43e-130">Create subscriber database using the **elevate to snapshot isolation** option and set the default collation to Latin1_General_CS_AS_KS_WS in case of using non Unicode character data types.</span></span>  
  
    ```  
    CREATE DATABASE [Sub]   
    CONTAINMENT = NONE   
    ON PRIMARY ( NAME = [Sub], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.mdf]),   
    FILEGROUP [mem] CONTAINS MEMORY_OPTIMIZED_DATA ( NAME = [mem],   
    FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub])  
    LOG ON ( NAME = [Sub_log], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.ldf])  
    COLLATE Latin1_General_CS_AS_KS_WS;  
  
    ALTER DATABASE [Sub] SET MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT = ON;  
    GO  
    ```  
  
6.  <span data-ttu-id="aa43e-131">Примените схему к базе данных подписчика и сохраните схему для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="aa43e-131">Apply the schema to a subscriber's database and save the schema for future use.</span></span>  
  
7.  <span data-ttu-id="aa43e-132">Загрузка данных издателя (источник) на подписчик.</span><span class="sxs-lookup"><span data-stu-id="aa43e-132">Load the publisher (source) data to the subscriber.</span></span> <span data-ttu-id="aa43e-133">Данные на издателе не должны изменяться до тех пор, пока не будет добавлена подписка.</span><span class="sxs-lookup"><span data-stu-id="aa43e-133">Data should not change at the publisher until you add a subscription.</span></span>  <span data-ttu-id="aa43e-134">Можно использовать BCP, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="aa43e-134">You can use BCP as shown below:</span></span>  
  
    ```  
    bcp Pub.dbo.Mem_Table out Mem_Table.bcp -S. -T -C1252 -n  
    bcp Sub.dbo.Mem_Table in Mem_Table.bcp -S. -T -C1252 -n  
    ```  
  
8.  <span data-ttu-id="aa43e-135">Измените статью, отключив изменения схемы на подписчике.</span><span class="sxs-lookup"><span data-stu-id="aa43e-135">Reconfigure the article to disable schema changes on the subscriber:</span></span>  
  
    ```  
    EXEC sp_changearticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @property = N'schema_option',  
        @value = 0,  
        @force_invalidate_snapshot = 1,  
        @force_reinit_subscription = 1;  
    GO  
    ```  
  
 <span data-ttu-id="aa43e-136">**Добавление подписки no sync**</span><span class="sxs-lookup"><span data-stu-id="aa43e-136">**Add no sync Subscription**</span></span>  
  
 <span data-ttu-id="aa43e-137">Добавьте подписку nosync.</span><span class="sxs-lookup"><span data-stu-id="aa43e-137">Add a nosync subscription.</span></span>  
  
```  
EXEC sp_addsubscription  
    @publication = N' Publication1',  
    @subscriber = @@ServerName,  
    @destination_db = N'Sub',  
    @subscription_type = N'Push',  
    @sync_type = N'replication support only',  
    @article = N'all',  
    @update_mode = N'read only',  
    @subscriber_type = 0;  
GO  
```  
  
 <span data-ttu-id="aa43e-138">После этого оптимизированные для памяти таблицы должны начать получать обновления от издателя.</span><span class="sxs-lookup"><span data-stu-id="aa43e-138">Memory-optimized tables should now start receiving updates from the publisher.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="aa43e-139">Ограничения</span><span class="sxs-lookup"><span data-stu-id="aa43e-139">Restrictions</span></span>  
 <span data-ttu-id="aa43e-140">Поддерживается только односторонняя репликация транзакций.</span><span class="sxs-lookup"><span data-stu-id="aa43e-140">Only one-way transactional replication is supported.</span></span> <span data-ttu-id="aa43e-141">Одноранговая репликация транзакций не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="aa43e-141">Peer-to-peer transactional replication is not supported.</span></span>  
  
 <span data-ttu-id="aa43e-142">Оптимизированные для памяти таблицы нельзя публиковать.</span><span class="sxs-lookup"><span data-stu-id="aa43e-142">Memory-optimized tables cannot be published.</span></span>  
  
 <span data-ttu-id="aa43e-143">Таблицы репликации на распространителе нельзя настраивать в качестве оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="aa43e-143">Replication tables on the distributor cannot be configured as memory-optimized tables.</span></span>  
  
 <span data-ttu-id="aa43e-144">Репликация слиянием не может содержать оптимизированные для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="aa43e-144">Merge replication cannot include memory-optimized tables.</span></span>  
  
 <span data-ttu-id="aa43e-145">Таблицы, участвующие в репликации транзакций можно настроить на подписчике как оптимизированные для памяти таблицы, но таблицы подписчика должны соответствовать требованиям к оптимизированным для памяти таблицам.</span><span class="sxs-lookup"><span data-stu-id="aa43e-145">At the subscriber, tables involved in transactional replication can be configured as memory optimized tables, but the subscriber tables must meet the requirements of memory-optimized tables.</span></span> <span data-ttu-id="aa43e-146">Для этого необходимы следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="aa43e-146">This requires the following restrictions.</span></span>  
  
-   <span data-ttu-id="aa43e-147">Чтобы создать оптимизированную для памяти таблицу на подписчике репликации транзакций, файлы схемы моментального снимка, используемые для создания оптимизированных для памяти таблиц, необходимо изменить вручную.</span><span class="sxs-lookup"><span data-stu-id="aa43e-147">To create a memory-optimized table on a transactional replication subscriber, the snapshot schema files used to create the memory-optimized tables must be manually modified.</span></span> <span data-ttu-id="aa43e-148">Дополнительные сведения см. [в разделе изменение файла схемы](#Schema).</span><span class="sxs-lookup"><span data-stu-id="aa43e-148">For more information, see [Modifying a schema file](#Schema).</span></span>  
  
-   <span data-ttu-id="aa43e-149">На таблицы, которые реплицируются в оптимизированные для памяти таблицы на подписчике, налагается ограничение в 8060 байт на строку оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="aa43e-149">Tables replicated to memory-optimized tables on a subscriber are limited to the 8060 bytes per row limit of memory-optimized tables.</span></span>  
  
-   <span data-ttu-id="aa43e-150">В таблицах, которые реплицируются в оптимизированные для памяти таблицы на подписчике, можно использовать только типы данных, разрешенные в оптимизированных для памяти таблицах.</span><span class="sxs-lookup"><span data-stu-id="aa43e-150">Tables replicated to memory-optimized tables on a subscriber are limited to the data types permitted in memory-optimized tables.</span></span> <span data-ttu-id="aa43e-151">Дополнительные сведения см. в разделе [Поддерживаемые типы данных](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="aa43e-151">For more information, see [Supported Data Types](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span></span>  
  
-   <span data-ttu-id="aa43e-152">Имеются ограничения на обновление первичного ключа таблиц, которые реплицируются в оптимизированную для памяти таблицу на подписчике.</span><span class="sxs-lookup"><span data-stu-id="aa43e-152">There are restrictions on updating the primary key of tables being replicated to a memory-optimized table on a subscriber.</span></span> <span data-ttu-id="aa43e-153">Дополнительные сведения см. [в разделе Репликация изменений в первичный ключ](#PrimaryKey).</span><span class="sxs-lookup"><span data-stu-id="aa43e-153">For more information, see [Replicating changes to a primary key](#PrimaryKey).</span></span>  
  
-   <span data-ttu-id="aa43e-154">Внешний ключ, ограничение уникальности, триггеры, изменения схемы, ROWGUIDCOL, вычисляемые столбцы, сжатие данных, псевдонимы типов данных, управление версиями и блокировки не поддерживаются в оптимизированных для памяти таблицах.</span><span class="sxs-lookup"><span data-stu-id="aa43e-154">Foreign key, unique constraint, triggers, schema modifications, ROWGUIDCOL, computed columns, data compression, alias data types, versioning, and locks are not supported in memory-optimized tables.</span></span> <span data-ttu-id="aa43e-155">Сведения см. в разделе [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) .</span><span class="sxs-lookup"><span data-stu-id="aa43e-155">See [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) for information.</span></span>  
  
##  <a name="modifying-a-schema-file"></a><a name="Schema"></a><span data-ttu-id="aa43e-156">Изменение файла схемы</span><span class="sxs-lookup"><span data-stu-id="aa43e-156">Modifying a schema file</span></span>  
  
-   <span data-ttu-id="aa43e-157">Кластеризованные индексы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="aa43e-157">Clustered indexes are not supported.</span></span> <span data-ttu-id="aa43e-158">Измените любые кластеризованные индексы на некластеризованные индексы.</span><span class="sxs-lookup"><span data-stu-id="aa43e-158">Change any clustered indexes to nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="aa43e-159">Все столбцы в ключе индекса должна быть определены как `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="aa43e-159">All columns in the key of an index must be specified as `NOT NULL`.</span></span>  
  
-   <span data-ttu-id="aa43e-160">Если используется параметр `DURABILITY = SCHEMA_AND_DATA` оптимизированной для памяти таблицы, то таблица должна иметь некластеризованный индекс первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="aa43e-160">If using the memory-optimized table option `DURABILITY = SCHEMA_AND_DATA` the table must have a nonclustered primary key index.</span></span>  
  
-   <span data-ttu-id="aa43e-161">Параметр ANSI_PADDING должен быть установлен в значение ON.</span><span class="sxs-lookup"><span data-stu-id="aa43e-161">ANSI_PADDING must be ON.</span></span>  
  
##  <a name="replicating-changes-to-a-primary-key"></a><a name="PrimaryKey"></a><span data-ttu-id="aa43e-162">Репликация изменений в первичный ключ</span><span class="sxs-lookup"><span data-stu-id="aa43e-162">Replicating changes to a primary key</span></span>  
 <span data-ttu-id="aa43e-163">Первичный ключ оптимизированной для памяти таблицы нельзя обновить.</span><span class="sxs-lookup"><span data-stu-id="aa43e-163">The primary key of a memory-optimized table cannot be updated.</span></span> <span data-ttu-id="aa43e-164">Для репликации обновлений первичного ключа на подписчике измените хранимую процедуру обновления так, чтобы обновления доставлялись в виде пары удаления и вставки.</span><span class="sxs-lookup"><span data-stu-id="aa43e-164">To replicate a primary key update on a subscriber, modify the update stored procedure to deliver the update as a delete and insert pair.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa43e-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa43e-165">See Also</span></span>  
 [<span data-ttu-id="aa43e-166">Репликация SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa43e-166">SQL Server Replication</span></span>](sql-server-replication.md)  
  
  
