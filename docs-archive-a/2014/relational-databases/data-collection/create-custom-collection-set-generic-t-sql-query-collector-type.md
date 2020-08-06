---
title: Создание пользовательского набора элементов сбора, использующего тип сборщика «Универсальный запрос T-SQL» (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- T-SQL Query collector type
- collection sets [SQL Server], creating custom
ms.assetid: 6b06db5b-cfdc-4ce0-addd-ec643460605b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab21ad5fd65556dec639fd5ca6999d23e2de673b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666093"
---
# <a name="create-a-custom-collection-set-that-uses-the-generic-t-sql-query-collector-type-transact-sql"></a><span data-ttu-id="6de8a-102">Создание пользовательского набора элементов сбора, использующего тип сборщика «Универсальный запрос T-SQL» (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6de8a-102">Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type (Transact-SQL)</span></span>
  <span data-ttu-id="6de8a-103">Можно создать пользовательский набор сбора с элементами, которые будут использовать тип сборщика «Универсальный запрос T-SQL» с помощью хранимых процедур, поставляемых вместе со сборщиком данных.</span><span class="sxs-lookup"><span data-stu-id="6de8a-103">You can create a custom collection set with collection items that use the Generic T-SQL Query collector type by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="6de8a-104">Эта задача решается с помощью редактора запросов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для выполнения следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="6de8a-104">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedures:</span></span>  
  
-   <span data-ttu-id="6de8a-105">Настройка расписаний передачи.</span><span class="sxs-lookup"><span data-stu-id="6de8a-105">Configure upload schedules.</span></span>  
  
-   <span data-ttu-id="6de8a-106">Определение и создание набора элементов сбора</span><span class="sxs-lookup"><span data-stu-id="6de8a-106">Define and create the collection set.</span></span>  
  
-   <span data-ttu-id="6de8a-107">Определение и создание элемента сбора.</span><span class="sxs-lookup"><span data-stu-id="6de8a-107">Define and create a collection item.</span></span>  
  
-   <span data-ttu-id="6de8a-108">Проверка существования набора сбора и элементов сбора.</span><span class="sxs-lookup"><span data-stu-id="6de8a-108">Verify that the collection set and collection items exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6de8a-109">Перед созданием пользовательского набора сбора необходимо настроить параметры сбора данных.</span><span class="sxs-lookup"><span data-stu-id="6de8a-109">Before you create a custom collection set, you must configure data collection parameters.</span></span> <span data-ttu-id="6de8a-110">Дополнительные сведения см. в разделе [Настройка параметров сбора данных (Transact-SQL)](configure-data-collection-parameters-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6de8a-110">For more information, see [Configure Data Collection Parameters &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span></span>  
  
### <a name="define-and-create-the-collection-set"></a><span data-ttu-id="6de8a-111">Определение и создание набора элементов сбора</span><span class="sxs-lookup"><span data-stu-id="6de8a-111">Define and create the collection set</span></span>  
  
1.  <span data-ttu-id="6de8a-112">Определите новый набор сбора с помощью хранимой процедуры sp_syscollector_create_collection_set.</span><span class="sxs-lookup"><span data-stu-id="6de8a-112">Define a new collection set using the sp_syscollector_create_collection_set stored procedure.</span></span>  
  
    ```  
    USE msdb;  
    DECLARE @collection_set_id int;  
    DECLARE @collection_set_uid uniqueidentifier;  
    EXEC sp_syscollector_create_collection_set   
        @name=N'DMV Test 1',   
        @collection_mode=0,   
        @description=N'This is a test collection set',   
        @logging_level=1,   
        @days_until_expiration=14,   
        @schedule_name=N'CollectorSchedule_Every_15min',   
        @collection_set_id=@collection_set_id OUTPUT,   
        @collection_set_uid=@collection_set_uid OUTPUT;  
    SELECT @collection_set_id, @collection_set_uid;  
    ```  
  
     <span data-ttu-id="6de8a-113">В качестве режима сбора можно задать либо 0 (с кэшированием), либо 1 (без кэширования).</span><span class="sxs-lookup"><span data-stu-id="6de8a-113">The collection mode can be set to either 0 (cached) or to 1 (non-cached).</span></span>  
  
     <span data-ttu-id="6de8a-114">Уровень ведения журнала можно установить в значение 0, 1 или 2.</span><span class="sxs-lookup"><span data-stu-id="6de8a-114">The logging level can be set to 0, 1 or 2.</span></span>  
  
     <span data-ttu-id="6de8a-115">Следующие предварительно настроенные расписания поставляются со сборщиком данных.</span><span class="sxs-lookup"><span data-stu-id="6de8a-115">The following preconfigured schedules are provided with the data collector:</span></span>  
  
    -   <span data-ttu-id="6de8a-116">CollectorSchedule_Every_5min</span><span class="sxs-lookup"><span data-stu-id="6de8a-116">CollectorSchedule_Every_5min</span></span>  
  
    -   <span data-ttu-id="6de8a-117">CollectorSchedule_Every_10min</span><span class="sxs-lookup"><span data-stu-id="6de8a-117">CollectorSchedule_Every_10min</span></span>  
  
    -   <span data-ttu-id="6de8a-118">CollectorSchedule_Every_15min</span><span class="sxs-lookup"><span data-stu-id="6de8a-118">CollectorSchedule_Every_15min</span></span>  
  
    -   <span data-ttu-id="6de8a-119">CollectorSchedule_Every_30min</span><span class="sxs-lookup"><span data-stu-id="6de8a-119">CollectorSchedule_Every_30min</span></span>  
  
    -   <span data-ttu-id="6de8a-120">CollectorSchedule_Every_60min</span><span class="sxs-lookup"><span data-stu-id="6de8a-120">CollectorSchedule_Every_60min</span></span>  
  
    -   <span data-ttu-id="6de8a-121">CollectorSchedule_Every_6h</span><span class="sxs-lookup"><span data-stu-id="6de8a-121">CollectorSchedule_Every_6h</span></span>  
  
     <span data-ttu-id="6de8a-122">При необходимости можно создать новое расписание и использовать его в наборе сбора.</span><span class="sxs-lookup"><span data-stu-id="6de8a-122">If you do not want to use one of the schedules that are provided, you can create a new schedule and use it for the collection set.</span></span> <span data-ttu-id="6de8a-123">Дополнительные сведения см. в разделе [Создание и присоединение расписаний к заданиям](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6de8a-123">For more information, see [Create and Attach Schedules to Jobs](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span></span>  
  
### <a name="define-and-create-a-collection-item"></a><span data-ttu-id="6de8a-124">Определение и создание элемента сбора</span><span class="sxs-lookup"><span data-stu-id="6de8a-124">Define and create a collection item</span></span>  
  
1.  <span data-ttu-id="6de8a-125">Поскольку новый элемент сбора создан на базе универсального типа сборщика, который уже установлен, можно выполнить следующий код, чтобы изменить его идентификатор GUID для соответствия типу «Универсальный сборщик запросов T-SQL».</span><span class="sxs-lookup"><span data-stu-id="6de8a-125">Because the new collection item is based on a generic collector type that is already installed, you can run the following code to set the GUID to correspond to the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid uniqueidentifier;  
    SELECT @collector_type_uid = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
    WHERE name = N'Generic T-SQL Query Collector Type';  
    DECLARE @collection_item_id int;  
    ```  
  
2.  <span data-ttu-id="6de8a-126">С помощью хранимой процедуры sp_syscollector_create_collection_item создайте элемент сбора.</span><span class="sxs-lookup"><span data-stu-id="6de8a-126">Use the sp_syscollector_create_collection_item stored procedure to create the collection item.</span></span> <span data-ttu-id="6de8a-127">Объявите схему для элемента сбора, чтобы он был сопоставлен со схемой, необходимой для типа сборщика «Универсальный запрос T-SQL».</span><span class="sxs-lookup"><span data-stu-id="6de8a-127">Declare the schema for the collection item so it maps to the schema that is required for the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    EXEC sp_syscollector_create_collection_item   
        @name=N'Query Stats - Test 1',   
        @parameters=N'  
            <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
            <Query>  
            <Value>SELECT * FROM sys.dm_exec_query_stats</Value>  
            <OutputTable>dm_exec_query_stats</OutputTable>  
            </Query>  
            </ns:TSQLQueryCollector>',   
        @collection_item_id=@collection_item_id OUTPUT,   
        @frequency=5,   
        @collection_set_id=@collection_set_id,   
        @collector_type_uid=@collector_type_uid;  
    SELECT @collection_item_id;  
    ```  
  
### <a name="verify-that-the-new-collection-set-and-collection-item-exist"></a><span data-ttu-id="6de8a-128">Проверка существования набора сбора и элемента сбора</span><span class="sxs-lookup"><span data-stu-id="6de8a-128">Verify that the new collection set and collection item exist</span></span>  
  
1.  <span data-ttu-id="6de8a-129">Перед запуском нового набора сбора запустите следующий запрос, чтобы убедиться, что новый набор сбора и его элемент сбора были созданы:</span><span class="sxs-lookup"><span data-stu-id="6de8a-129">Before starting the new collection set, run the following query to verify that the new collection set and its collection item have been created.</span></span>  
  
    ```sql  
    USE msdb;  
    SELECT * FROM syscollector_collection_sets;  
    SELECT * FROM syscollector_collection_items;  
    GO  
    ```  
  
     <span data-ttu-id="6de8a-130">Можно также провести визуальную проверку в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6de8a-130">You can also do a visual check in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6de8a-131">В обозревателе объектов разверните узел **Управление** , затем узел **Сбор данных**.</span><span class="sxs-lookup"><span data-stu-id="6de8a-131">In Object Explorer, expand the **Management** node, and then expand **Data Collection**.</span></span> <span data-ttu-id="6de8a-132">Будет отображен новый набор сбора.</span><span class="sxs-lookup"><span data-stu-id="6de8a-132">The new collection set will be displayed.</span></span> <span data-ttu-id="6de8a-133">Красный круглый кружок на значке набора сбора означает, что набор сбора остановлен.</span><span class="sxs-lookup"><span data-stu-id="6de8a-133">The red circle icon for the collection set indicates that the collection set is stopped.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6de8a-134">Пример</span><span class="sxs-lookup"><span data-stu-id="6de8a-134">Example</span></span>  
 <span data-ttu-id="6de8a-135">В следующем образце кода объединены примеры, приведенные в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="6de8a-135">The following code sample combines the examples that are documented in the previous steps.</span></span> <span data-ttu-id="6de8a-136">Обратите внимание, что частота сбора, установленная для данного элемента сбора (5 секунд), не учитывается, поскольку для набора сбора установлен режим сбора 0, то есть режим с кэшированием.</span><span class="sxs-lookup"><span data-stu-id="6de8a-136">Note that the collection frequency that is set for the collection item (5 seconds) is ignored because the collection set collection mode is set to 0, which is cached mode.</span></span> <span data-ttu-id="6de8a-137">Дополнительные сведения см. в разделе [Data Collection](data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="6de8a-137">For more information, see [Data Collection](data-collection.md).</span></span>  
  
```sql  
USE msdb;  
  
DECLARE @collection_set_id int;  
DECLARE @collection_set_uid uniqueidentifier  
  
EXEC dbo.sp_syscollector_create_collection_set  
    @name = N'DMV Stats Test 1',  
    @collection_mode = 0,  
    @description = N'This is a test collection set',  
    @logging_level=1,  
    @days_until_expiration = 14,  
    @schedule_name=N'CollectorSchedule_Every_15min',  
    @collection_set_id = @collection_set_id OUTPUT,  
    @collection_set_uid = @collection_set_uid OUTPUT;  
SELECT @collection_set_id,@collection_set_uid;  
  
DECLARE @collector_type_uid uniqueidentifier;  
SELECT @collector_type_uid = collector_type_uid FROM syscollector_collector_types   
WHERE name = N'Generic T-SQL Query Collector Type';  
  
DECLARE @collection_item_id int;  
EXEC sp_syscollector_create_collection_item  
@name= N'Query Stats - Test 1',  
@parameters=N'  
<ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
<Query>  
  <Value>select * from sys.dm_exec_query_stats</Value>  
  <OutputTable>dm_exec_query_stats</OutputTable>  
</Query>  
 </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 5, -- This parameter is ignored in cached mode  
    @collection_set_id = @collection_set_id,  
    @collector_type_uid = @collector_type_uid;  
SELECT @collection_item_id;  
  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6de8a-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="6de8a-138">See Also</span></span>  
 <span data-ttu-id="6de8a-139">[Хранимые процедуры сборщика данных (Transact-SQL)](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6de8a-139">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="6de8a-140">[Управление расписаниями](../../ssms/agent/manage-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="6de8a-140">[Manage Schedules](../../ssms/agent/manage-schedules.md) </span></span>  
 [<span data-ttu-id="6de8a-141">Запуск или остановка набора элементов сбора</span><span class="sxs-lookup"><span data-stu-id="6de8a-141">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
  
