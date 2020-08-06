---
title: Добавление элемента сбора в набор элементов сбора (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection items [SQL Server]
- collection sets [SQL Server], adding items
ms.assetid: 9fe6454e-8c0e-4b50-937b-d9871b20fd13
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0b21508761bdfbaf8918242b074f78203c1bcaed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668904"
---
# <a name="add-a-collection-item-to-a-collection-set-transact-sql"></a><span data-ttu-id="9d8ff-102">Добавление элемента сбора в набор элементов сбора (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9d8ff-102">Add a Collection Item to a Collection Set (Transact-SQL)</span></span>
  <span data-ttu-id="9d8ff-103">Добавить новый элемент сбора в существующий набор сбора можно с помощью хранимых процедур, предоставляемых вместе со сборщиком данных.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-103">You can add a collection item to an existing collection set using the stored procedures that are provided with the data collector.</span></span>  
  
 <span data-ttu-id="9d8ff-104">Выполните следующие шаги с помощью редактора запросов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d8ff-104">Carry out the following steps using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="add-a-collection-item-to-a-collection-set"></a><span data-ttu-id="9d8ff-105">Добавление элемента сбора в набор элементов сбора</span><span class="sxs-lookup"><span data-stu-id="9d8ff-105">Add a collection item to a collection set</span></span>  
  
1.  <span data-ttu-id="9d8ff-106">Остановите набор сбора, в который необходимо добавить элемент, запустив хранимую процедуру **sp_syscollector_stop_collection_set** .</span><span class="sxs-lookup"><span data-stu-id="9d8ff-106">Stop the collection set that you want to add the item to by running the **sp_syscollector_stop_collection_set** stored procedure.</span></span> <span data-ttu-id="9d8ff-107">Например, чтобы остановить набор сбора с именем «Тестовый набор сбора», выполните следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="9d8ff-107">For example, to stop a collection set that is named "Test Collection Set", run the following statements:</span></span>  
  
    ```sql  
    USE msdb  
    DECLARE @csid int  
    SELECT @csid = collection_set_id  
    FROM syscollector_collection_sets  
    WHERE name = 'Test Collection Set'  
    SELECT @csid  
    EXEC dbo.sp_syscollector_stop_collection_set @collection_set_id = @csid  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d8ff-108">Кроме того, набор сбора можно остановить с помощью обозревателя объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d8ff-108">You can also stop the collection set by using Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="9d8ff-109">Дополнительные сведения см. в разделе [Запуск или остановка набора элементов сбора](start-or-stop-a-collection-set.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ff-109">For more information, see [Start or Stop a Collection Set](start-or-stop-a-collection-set.md).</span></span>  
  
2.  <span data-ttu-id="9d8ff-110">Объявите набор сбора, в который нужно добавить элемент сбора.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-110">Declare the collection set that you want to add the collection item to.</span></span> <span data-ttu-id="9d8ff-111">В следующем коде представлен пример объявления идентификатора набора сбора.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-111">The following code provides an example of how to declare the collection set ID.</span></span>  
  
    ```sql  
    DECLARE @collection_set_id_1 int  
    SELECT @collection_set_id_1 = collection_set_id FROM [msdb].[dbo].[syscollector_collection_sets]  
    WHERE name = N'Test Collection Set'; -- name of collection set  
    ```  
  
3.  <span data-ttu-id="9d8ff-112">Объявление типа сборщика.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-112">Declare the collector type.</span></span> <span data-ttu-id="9d8ff-113">В следующем коде представлен пример объявления типа сборщика «Универсальный запрос T-SQL».</span><span class="sxs-lookup"><span data-stu-id="9d8ff-113">The following code provides an example of how to declare the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid_1 uniqueidentifier  
    SELECT @collector_type_uid_1 = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
       WHERE name = N'Generic T-SQL Query Collector Type';  
    ```  
  
     <span data-ttu-id="9d8ff-114">С помощью приведенного ниже кода можно получить список установленных типов сборщика:</span><span class="sxs-lookup"><span data-stu-id="9d8ff-114">You can run the following code to obtain a list of the installed collector types:</span></span>  
  
    ```sql  
    USE msdb  
    SELECT * from syscollector_collector_types  
    GO  
    ```  
  
4.  <span data-ttu-id="9d8ff-115">Запустите хранимую процедуру **sp_syscollector_create_collection_item** , чтобы создать элемент сбора.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-115">Run the **sp_syscollector_create_collection_item** stored procedure to create the collection item.</span></span> <span data-ttu-id="9d8ff-116">Необходимо объявить схему для элемента сбора, чтобы он был сопоставлен с требуемой схемой для сборщика нужного типа.</span><span class="sxs-lookup"><span data-stu-id="9d8ff-116">You must declare the schema for the collection item so that it maps to the required schema for the desired collector type.</span></span> <span data-ttu-id="9d8ff-117">В следующем примере используется схема «Универсальный запрос T-SQL».</span><span class="sxs-lookup"><span data-stu-id="9d8ff-117">The following example uses the Generic T-SQL Query input schema.</span></span>  
  
    ```sql  
    DECLARE @collection_item_id int;  
    EXEC [msdb].[dbo].[sp_syscollector_create_collection_item]   
    @name=N'OS Wait Stats', --name of collection item  
    @parameters=N'  
    <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
     <Query>  
      <Value>select * from sys.dm_os_wait_stats</Value>  
      <OutputTable>os_wait_stats</OutputTable>  
    </Query>  
    </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 60,  
    @collection_set_id = @collection_set_id_1, --- Provides the collection set ID number  
    @collector_type_uid = @collector_type_uid_1 -- Provides the collector type UID  
    SELECT @collection_item_id     
    ```  
  
5.  <span data-ttu-id="9d8ff-118">Перед запуском обновленного набора сбора запустите следующий запрос, чтобы убедиться, что новый элемент сбора был создан:</span><span class="sxs-lookup"><span data-stu-id="9d8ff-118">Before starting the updated collection set, run the following query to verify that the new collection item has been created:</span></span>  
  
    ```xaml  
    USE msdb  
    SELECT * from syscollector_collection_sets  
    SELECT * from syscollector_collection_items  
    GO  
    ```  
  
     <span data-ttu-id="9d8ff-119">Наборы сбора и их элементы сбора отображаются на вкладке **Результаты** .</span><span class="sxs-lookup"><span data-stu-id="9d8ff-119">The collection sets and their collection items are displayed in the **Results** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8ff-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d8ff-120">See Also</span></span>  
 <span data-ttu-id="9d8ff-121">[Создание пользовательского набора элементов сбора, использующего тип сборщика "Универсальный запрос T-SQL" (Transact-SQL)](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span><span class="sxs-lookup"><span data-stu-id="9d8ff-121">[Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span></span>  
 [<span data-ttu-id="9d8ff-122">Хранимые процедуры сборщика данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9d8ff-122">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
