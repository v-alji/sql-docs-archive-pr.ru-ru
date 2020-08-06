---
title: Включение индексов и ограничений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], enabling
- nonclustered indexes [SQL Server], enabling a disabled index
- index enabling [SQL Server]
- disabled indexes [SQL Server], how to enable
- constraints [SQL Server], enabling
- clustered indexes, enabling disabled indexes
ms.assetid: c55c8865-322e-4ab0-ba04-ea1f56735353
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4e79689b80a40d00958fa557fe51df2adf9c14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668324"
---
# <a name="enable-indexes-and-constraints"></a><span data-ttu-id="78f6a-102">Включение индексов и ограничений</span><span class="sxs-lookup"><span data-stu-id="78f6a-102">Enable Indexes and Constraints</span></span>
  <span data-ttu-id="78f6a-103">В этом разделе описывается включение отключенного индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78f6a-103">This topic describes how to enable a disabled index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="78f6a-104">После отключения индекс остается в отключенном состоянии до тех пор, пока он не будет перестроен или удален.</span><span class="sxs-lookup"><span data-stu-id="78f6a-104">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped</span></span>  
  
 <span data-ttu-id="78f6a-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="78f6a-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="78f6a-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="78f6a-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="78f6a-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="78f6a-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="78f6a-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="78f6a-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="78f6a-109">**Включение отключенного индекса с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="78f6a-109">**To enable a disabled index, using:**</span></span>  
  
     [<span data-ttu-id="78f6a-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78f6a-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="78f6a-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78f6a-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78f6a-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="78f6a-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="78f6a-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="78f6a-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="78f6a-114">После перестроения индекса нужно вручную включить все ограничения, которые были отключены из-за отключения индекса.</span><span class="sxs-lookup"><span data-stu-id="78f6a-114">After rebuilding the index, any constraints that were disabled because of disabling the index must be manually enabled.</span></span> <span data-ttu-id="78f6a-115">Ограничения PRIMARY KEY и UNIQUE включаются путем перестроения соответствующего индекса.</span><span class="sxs-lookup"><span data-stu-id="78f6a-115">PRIMARY KEY and UNIQUE constraints are enabled by rebuilding the associated index.</span></span> <span data-ttu-id="78f6a-116">Индекс должен быть перестроен (включен) до включения ограничений FOREIGN KEY, которые ссылаются на ограничение PRIMARY KEY или UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="78f6a-116">This index must be rebuilt (enabled) before you can enable FOREIGN KEY constraints that reference the PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="78f6a-117">Ограничения FOREIGN KEY включаются с помощью инструкции ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="78f6a-117">FOREIGN KEY constraints are enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="78f6a-118">Перестройка отключенного кластеризованного индекса не может быть выполнена, если параметр ONLINE имеет значение ON.</span><span class="sxs-lookup"><span data-stu-id="78f6a-118">Rebuilding a disabled clustered index cannot be performed when the ONLINE option is set to ON.</span></span>  
  
-   <span data-ttu-id="78f6a-119">Когда кластеризованный индекс отключен или включен, а некластеризованный индекс отключен, действие кластеризованного индекса на отключенный некластеризованный индекс дает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="78f6a-119">When the clustered index is disabled or enabled and the nonclustered index is disabled, the clustered index action has the following results on the disabled nonclustered index.</span></span>  
  
    |<span data-ttu-id="78f6a-120">Действие кластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="78f6a-120">Clustered Index Action</span></span>|<span data-ttu-id="78f6a-121">Отключенный некластеризованный индекс ...</span><span class="sxs-lookup"><span data-stu-id="78f6a-121">Disabled Nonclustered Index ...</span></span>|  
    |----------------------------|-----------------------------------|  
    |<span data-ttu-id="78f6a-122">ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="78f6a-122">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="78f6a-123">Остается отключенным.</span><span class="sxs-lookup"><span data-stu-id="78f6a-123">Remains disabled.</span></span>|  
    |<span data-ttu-id="78f6a-124">ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="78f6a-124">ALTER INDEX ALL REBUILD.</span></span>|<span data-ttu-id="78f6a-125">Будет перестроен и включен.</span><span class="sxs-lookup"><span data-stu-id="78f6a-125">Is rebuilt and enabled.</span></span>|  
    |<span data-ttu-id="78f6a-126">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="78f6a-126">DROP INDEX.</span></span>|<span data-ttu-id="78f6a-127">Остается отключенным.</span><span class="sxs-lookup"><span data-stu-id="78f6a-127">Remains disabled.</span></span>|  
    |<span data-ttu-id="78f6a-128">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="78f6a-128">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="78f6a-129">Остается отключенным.</span><span class="sxs-lookup"><span data-stu-id="78f6a-129">Remains disabled.</span></span>|  
  
     <span data-ttu-id="78f6a-130">При создании нового кластеризованного индекса работает аналогично инструкции ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="78f6a-130">Creating a new clustered index, behaves the same as ALTER INDEX ALL REBUILD.</span></span>  
  
-   <span data-ttu-id="78f6a-131">Разрешенные действия на некластеризованных индексах, связанных с кластеризованным индексом, зависят от состояния (отключен или включен) обоих типов индекса.</span><span class="sxs-lookup"><span data-stu-id="78f6a-131">Allowed actions on nonclustered indexes associated with a clustered index depend on the state, whether disabled or enabled, of both index types.</span></span> <span data-ttu-id="78f6a-132">Следующая таблица обобщает разрешенные действия на некластеризованных индексах.</span><span class="sxs-lookup"><span data-stu-id="78f6a-132">The following table summarizes the allowed actions on nonclustered indexes.</span></span>  
  
    |<span data-ttu-id="78f6a-133">Действие некластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="78f6a-133">Nonclustered Index Action</span></span>|<span data-ttu-id="78f6a-134">Когда и кластеризованные, и некластеризованные индексы отключены.</span><span class="sxs-lookup"><span data-stu-id="78f6a-134">When both the clustered and nonclustered indexes are disabled.</span></span>|<span data-ttu-id="78f6a-135">Когда кластеризованный индекс включен, а некластеризованный индекс либо отключен, либо включен.</span><span class="sxs-lookup"><span data-stu-id="78f6a-135">When the clustered index is enabled and the nonclustered index is in either state.</span></span>|  
    |-------------------------------|--------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
    |<span data-ttu-id="78f6a-136">ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="78f6a-136">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="78f6a-137">Не удалось выполнить операцию.</span><span class="sxs-lookup"><span data-stu-id="78f6a-137">The action fails.</span></span>|<span data-ttu-id="78f6a-138">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="78f6a-138">The action succeeds.</span></span>|  
    |<span data-ttu-id="78f6a-139">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="78f6a-139">DROP INDEX.</span></span>|<span data-ttu-id="78f6a-140">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="78f6a-140">The action succeeds.</span></span>|<span data-ttu-id="78f6a-141">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="78f6a-141">The action succeeds.</span></span>|  
    |<span data-ttu-id="78f6a-142">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="78f6a-142">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="78f6a-143">Не удалось выполнить операцию.</span><span class="sxs-lookup"><span data-stu-id="78f6a-143">The action fails.</span></span>|<span data-ttu-id="78f6a-144">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="78f6a-144">The action succeeds.</span></span>|  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="78f6a-145">безопасность</span><span class="sxs-lookup"><span data-stu-id="78f6a-145">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="78f6a-146">Permissions</span><span class="sxs-lookup"><span data-stu-id="78f6a-146">Permissions</span></span>  
 <span data-ttu-id="78f6a-147">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="78f6a-147">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="78f6a-148">При использовании инструкции DBCC DBREINDEX пользователь должен быть владельцем таблицы, членом предопределенной роли сервера **sysadmin** либо предопределенной роли базы данных **db_ddladmin** или **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="78f6a-148">If using DBCC DBREINDEX, eser must either own the table or be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78f6a-149">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78f6a-149">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-a-disabled-index"></a><span data-ttu-id="78f6a-150">Включение отключенного индекса</span><span class="sxs-lookup"><span data-stu-id="78f6a-150">To enable a disabled index</span></span>  
  
1.  <span data-ttu-id="78f6a-151">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо включить индекс.</span><span class="sxs-lookup"><span data-stu-id="78f6a-151">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable an index.</span></span>  
  
2.  <span data-ttu-id="78f6a-152">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="78f6a-152">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="78f6a-153">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо включить индекс.</span><span class="sxs-lookup"><span data-stu-id="78f6a-153">Click the plus sign to expand the table on which you want to enable an index.</span></span>  
  
4.  <span data-ttu-id="78f6a-154">Чтобы развернуть папку **Индексы** , щелкните знак «плюс» (+).</span><span class="sxs-lookup"><span data-stu-id="78f6a-154">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="78f6a-155">Щелкните правой кнопкой мыши индекс, который необходимо включить, и выберите пункт **Перестроить**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-155">Right-click the index you want to enable and select **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="78f6a-156">В диалоговом окне **Перестроение индексов** убедитесь, что нужный индекс приведен в сетке **Индексы для перестройки** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-156">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
#### <a name="to-enable-all-indexes-on-a-table"></a><span data-ttu-id="78f6a-157">Включение всех индексов таблицы</span><span class="sxs-lookup"><span data-stu-id="78f6a-157">To enable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="78f6a-158">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо включить индексы.</span><span class="sxs-lookup"><span data-stu-id="78f6a-158">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable the indexes.</span></span>  
  
2.  <span data-ttu-id="78f6a-159">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="78f6a-159">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="78f6a-160">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо включить индексы.</span><span class="sxs-lookup"><span data-stu-id="78f6a-160">Click the plus sign to expand the table on which you want to enable the indexes.</span></span>  
  
4.  <span data-ttu-id="78f6a-161">Щелкните правой кнопкой мыши папку **Индексы** и выберите **Перестроить все**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-161">Right-click the **Indexes** folder and select **Rebuild All**.</span></span>  
  
5.  <span data-ttu-id="78f6a-162">В диалоговом окне **Перестройка индексов** убедитесь, что нужные индексы приведены в сетке **Индексы для перестроения** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-162">In the **Rebuild Indexes** dialog box, verify that the correct indexes are in the **Indexes to rebuild** grid and click **OK**.</span></span> <span data-ttu-id="78f6a-163">Для удаления индекса из сетки **Индексы для перестроения** выделите индекс и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="78f6a-163">To remove an index from the **Indexes to rebuild** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="78f6a-164">В диалоговом окне **Перестроение индексов** приведены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="78f6a-164">The following information is available in the **Rebuild Indexes** dialog box:</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="78f6a-165">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78f6a-165">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-a-disabled-index-using-alter-index"></a><span data-ttu-id="78f6a-166">Использование инструкции ALTER INDEX для включения отключенного индекса</span><span class="sxs-lookup"><span data-stu-id="78f6a-166">To enable a disabled index using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="78f6a-167">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78f6a-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78f6a-168">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78f6a-169">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD;   
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-create-index"></a><span data-ttu-id="78f6a-170">Использование инструкции CREATE INDEX для включения отключенного индекса</span><span class="sxs-lookup"><span data-stu-id="78f6a-170">To enable a disabled index using CREATE INDEX</span></span>  
  
1.  <span data-ttu-id="78f6a-171">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78f6a-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78f6a-172">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78f6a-173">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- re-creates the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    -- using the OrganizationLevel and OrganizationNode columns  
    -- and then deletes the existing IX_Employee_OrganizationLevel_OrganizationNode index  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)  
    WITH (DROP_EXISTING = ON);  
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-dbcc-dbreindex"></a><span data-ttu-id="78f6a-174">Использование инструкции DBCC DBREINDEX для включения отключенного индекса</span><span class="sxs-lookup"><span data-stu-id="78f6a-174">To enable a disabled index using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="78f6a-175">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78f6a-175">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78f6a-176">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-176">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78f6a-177">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-177">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", IX_Employee_OrganizationLevel_OrganizationNode);  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-alter-index"></a><span data-ttu-id="78f6a-178">Использование инструкции ALTER INDEX для включения всех индексов в таблице</span><span class="sxs-lookup"><span data-stu-id="78f6a-178">To enable all indexes on a table using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="78f6a-179">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78f6a-179">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78f6a-180">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-180">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78f6a-181">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-181">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    ALTER INDEX ALL ON HumanResources.Employee  
    REBUILD;  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-dbcc-dbreindex"></a><span data-ttu-id="78f6a-182">Использование инструкции DBCC DBREINDEX для включения всех индексов в таблице</span><span class="sxs-lookup"><span data-stu-id="78f6a-182">To enable all indexes on a table using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="78f6a-183">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78f6a-183">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78f6a-184">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-184">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78f6a-185">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78f6a-185">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", " ");  
    GO  
    ```  
  
 <span data-ttu-id="78f6a-186">Дополнительные сведения см. в разделах [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql) и [DBCC DBREINDEX (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78f6a-186">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql), and [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span></span>  
  
  
