---
title: Установка параметров индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- ALLOW_ROW_LOCKS option
- SORT_IN_TEMPDB option
- DROP_EXISTING clause
- large data, indexes
- PAD_INDEX
- STATISTICS_NORECOMPUTE
- MAXDOP index option, setting
- index options [SQL Server]
- MAXDOP index option
- IGNORE_DUP_KEY option
- ALLOW_PAGE_LOCKS option
- ONLINE
ms.assetid: 7969af33-e94c-41f7-ab89-9d9a2747cd5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9f2d7f0bbbf0d152d3f510ae9ddbe3168634ef96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739962"
---
# <a name="set-index-options"></a><span data-ttu-id="d1e14-102">Установка параметров индекса</span><span class="sxs-lookup"><span data-stu-id="d1e14-102">Set Index Options</span></span>
  <span data-ttu-id="d1e14-103">В этом разделе описывается процесс изменения свойств индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1e14-103">This topic describes how to modify the properties of an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d1e14-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d1e14-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d1e14-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d1e14-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d1e14-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d1e14-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d1e14-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d1e14-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d1e14-108">**Изменение свойств индекса различными средствами.**</span><span class="sxs-lookup"><span data-stu-id="d1e14-108">**To modify the properties of an index, using:**</span></span>  
  
     [<span data-ttu-id="d1e14-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1e14-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d1e14-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1e14-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d1e14-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d1e14-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d1e14-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d1e14-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d1e14-113">К индексу с помощью предложения SET в инструкции ALTER INDEX немедленно применяются следующие параметры: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY и STATISTICS_NORECOMPUTE.</span><span class="sxs-lookup"><span data-stu-id="d1e14-113">The following options are immediately applied to the index by using the SET clause in the ALTER INDEX statement: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY, and STATISTICS_NORECOMPUTE.</span></span>  
  
-   <span data-ttu-id="d1e14-114">Следующие параметры индекса можно установить при перестройке индекса с помощью инструкции ALTER INDEX REBUILD или CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP и DROP_EXISTING (только для CREATE INDEX).</span><span class="sxs-lookup"><span data-stu-id="d1e14-114">The following options can be set when you rebuild an index by using either ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP, and DROP_EXISTING (CREATE INDEX only).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d1e14-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="d1e14-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d1e14-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="d1e14-116">Permissions</span></span>  
 <span data-ttu-id="d1e14-117">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="d1e14-117">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d1e14-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1e14-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-table-designer"></a><span data-ttu-id="d1e14-119">Изменение свойств индекса при помощи конструктора таблиц.</span><span class="sxs-lookup"><span data-stu-id="d1e14-119">To modify the properties of an index in Table Designer</span></span>  
  
1.  <span data-ttu-id="d1e14-120">В обозревателе объектов щелкните значок плюса, чтобы развернуть базу данных, содержащую таблицу, в которой необходимо изменить свойства индекса.</span><span class="sxs-lookup"><span data-stu-id="d1e14-120">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="d1e14-121">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="d1e14-121">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="d1e14-122">Щелкните правой кнопкой мыши таблицу, в которой необходимо изменить свойства индекса, а затем выберите пункт **Проект**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-122">Right-click the table on which you want to modify an index's properties and select **Design**.</span></span>  
  
4.  <span data-ttu-id="d1e14-123">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-123">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="d1e14-124">Выберите индекс, свойства которого необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="d1e14-124">Select the index that you want to modify.</span></span> <span data-ttu-id="d1e14-125">Его свойства отобразятся в основной сетке.</span><span class="sxs-lookup"><span data-stu-id="d1e14-125">Its properties will show up in the main grid.</span></span>  
  
6.  <span data-ttu-id="d1e14-126">Измените значения любого или всех свойств, чтобы внести изменения в индекс.</span><span class="sxs-lookup"><span data-stu-id="d1e14-126">Change the settings of any and all properties to customize the index.</span></span>  
  
7.  <span data-ttu-id="d1e14-127">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-127">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="d1e14-128">В меню **Файл** выберите пункт **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="d1e14-128">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-object-explorer"></a><span data-ttu-id="d1e14-129">Изменение свойств индекса при помощи обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="d1e14-129">To modify the properties of an index in Object Explorer</span></span>  
  
1.  <span data-ttu-id="d1e14-130">В обозревателе объектов щелкните значок плюса, чтобы развернуть базу данных, содержащую таблицу, в которой необходимо изменить свойства индекса.</span><span class="sxs-lookup"><span data-stu-id="d1e14-130">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="d1e14-131">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="d1e14-131">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="d1e14-132">Щелкните значок плюса (+), чтобы развернуть таблицу, в которой необходимо изменить свойства индекса.</span><span class="sxs-lookup"><span data-stu-id="d1e14-132">Click the plus sign to expand the table on which you want to modify an index's properties.</span></span>  
  
4.  <span data-ttu-id="d1e14-133">Чтобы развернуть папку **Индексы** , щелкните знак «плюс» (+).</span><span class="sxs-lookup"><span data-stu-id="d1e14-133">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="d1e14-134">Щелкните правой кнопкой мыши индекс, свойства которого требуется изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-134">Right-click the index of which you want to modify the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="d1e14-135">В разделе **Выбор страницы**щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-135">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="d1e14-136">Измените значения любого или всех свойств, чтобы внести изменения в индекс.</span><span class="sxs-lookup"><span data-stu-id="d1e14-136">Change the settings of any and all properties to customize the index.</span></span>  
  
8.  <span data-ttu-id="d1e14-137">Чтобы добавить столбец индекса, удалить или изменить его позицию, выберите страницу **Общие** в диалоговом окне **Свойства индекса ―**  _имя_индекса_.</span><span class="sxs-lookup"><span data-stu-id="d1e14-137">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties -** _index_name_ dialog box.</span></span> <span data-ttu-id="d1e14-138">Дополнительные сведения см. в разделе [Index Properties F1 Help](index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="d1e14-138">For more information, see [Index Properties F1 Help](index-properties-f1-help.md)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d1e14-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1e14-139">Using Transact-SQL</span></span>  
  
#### <a name="to-see-the-properties-of-all-the-indexes-in-a-table"></a><span data-ttu-id="d1e14-140">Просмотр свойств всех индексов в таблице</span><span class="sxs-lookup"><span data-stu-id="d1e14-140">To see the properties of all the indexes in a table</span></span>  
  
1.  <span data-ttu-id="d1e14-141">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1e14-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d1e14-142">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d1e14-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT i.name AS index_name,   
        i.type_desc,   
        i.is_unique,   
        ds.type_desc AS filegroup_or_partition_scheme,   
        ds.name AS filegroup_or_partition_scheme_name,   
        i.ignore_dup_key,   
        i.is_primary_key,   
        i.is_unique_constraint,   
        i.fill_factor,   
        i.is_padded,   
        i.is_disabled,   
        i.allow_row_locks,   
        i.allow_page_locks,   
        i.has_filter,   
        i.filter_definition  
    FROM sys.indexes AS i  
       INNER JOIN sys.data_spaces AS ds ON i.data_space_id = ds.data_space_id  
    WHERE is_hypothetical = 0 AND i.index_id <> 0   
       AND i.object_id = OBJECT_ID('HumanResources.Employee');   
    GO  
  
    ```  
  
#### <a name="to-set-the-properties-of-an-index"></a><span data-ttu-id="d1e14-144">Задание свойств индекса</span><span class="sxs-lookup"><span data-stu-id="d1e14-144">To set the properties of an index</span></span>  
  
1.  <span data-ttu-id="d1e14-145">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1e14-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d1e14-146">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d1e14-147">Скопируйте следующие примеры в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d1e14-147">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="d1e14-148">Дополнительные сведения см. в разделе [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d1e14-148">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
