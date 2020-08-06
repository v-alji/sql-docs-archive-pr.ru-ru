---
title: Обновление статистики | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- updating statistics
- statistics [SQL Server], updating
ms.assetid: 4b97c0b4-03ff-4cfb-9c3f-3b33290b7a2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 28491dda23c2ba9402e91dc051249f5bdcdf28d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667625"
---
# <a name="update-statistics"></a><span data-ttu-id="2ccb3-102">Обновить статистику</span><span class="sxs-lookup"><span data-stu-id="2ccb3-102">Update Statistics</span></span>
  <span data-ttu-id="2ccb3-103">Обновить статистику оптимизации запросов для таблицы или индексированного представления в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ccb3-103">You can update query optimization statistics on a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2ccb3-104">По умолчанию оптимизатор запросов обновляет статистику по мере необходимости для усовершенствования плана запроса. В некоторых случаях можно повысить производительность запроса, выполняя обновление статистики с помощью инструкции UPDATE STATISTICS или хранимой процедуры `sp_updatestats` чаще, чем это происходит по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-104">By default, the query optimizer already updates statistics as necessary to improve the query plan; in some cases you can improve query performance by using UPDATE STATISTICS or the stored procedure `sp_updatestats` to update statistics more frequently than the default updates.</span></span>  
  
 <span data-ttu-id="2ccb3-105">Обновление статистики гарантирует, что запросы будут компилироваться с актуальной статистикой.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-105">Updating statistics ensures that queries compile with up-to-date statistics.</span></span> <span data-ttu-id="2ccb3-106">Однако обновление статистики вызывает перекомпиляцию запросов.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-106">However, updating statistics causes queries to recompile.</span></span> <span data-ttu-id="2ccb3-107">Рекомендуется не обновлять статистику слишком часто, поскольку необходимо найти баланс между выигрышем в производительности за счет усовершенствованных планов запросов и потерей времени на перекомпиляцию запросов.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-107">We recommend not updating statistics too frequently because there is a performance tradeoff between improving query plans and the time it takes to recompile queries.</span></span> <span data-ttu-id="2ccb3-108">Критерии выбора компромиссного решения зависят от приложения.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-108">The specific tradeoffs depend on your application.</span></span> <span data-ttu-id="2ccb3-109">UPDATE STATISTICS может использовать базу данных tempdb для сортировки образцов строк для построения статистики.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-109">UPDATE STATISTICS can use tempdb to sort the sample of rows for building statistics.</span></span>  
  
 <span data-ttu-id="2ccb3-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2ccb3-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2ccb3-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2ccb3-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2ccb3-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2ccb3-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2ccb3-113">**Для обновления объекта статистики используются:**</span><span class="sxs-lookup"><span data-stu-id="2ccb3-113">**To update a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="2ccb3-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2ccb3-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2ccb3-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2ccb3-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2ccb3-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2ccb3-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2ccb3-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="2ccb3-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2ccb3-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="2ccb3-118">Permissions</span></span>  
 <span data-ttu-id="2ccb3-119">При использовании инструкции UPDATE STATISTICS или внесении изменений в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]необходимо разрешение ALTER на таблицу или представление.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-119">If using UPDATE STATISTICS or making changes through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], requires ALTER permission on the table or view.</span></span> <span data-ttu-id="2ccb3-120">При использовании процедуры `sp_updatestats`необходимо быть членом предопределенной роли сервера **sysadmin** или владельцем базы данных (**dbo**).</span><span class="sxs-lookup"><span data-stu-id="2ccb3-120">If using `sp_updatestats`, requires membership in the **sysadmin** fixed server role, or ownership of the database (**dbo**).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2ccb3-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2ccb3-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-update-a-statistics-object"></a><span data-ttu-id="2ccb3-122">Обновление объекта статистики</span><span class="sxs-lookup"><span data-stu-id="2ccb3-122">To update a statistics object</span></span>  
  
1.  <span data-ttu-id="2ccb3-123">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть базу данных, в которой нужно обновить статистику.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-123">In **Object Explorer**, click the plus sign to expand the database in which you want to update the statistic.</span></span>  
  
2.  <span data-ttu-id="2ccb3-124">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="2ccb3-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2ccb3-125">Щелкните значок «плюс», чтобы развернуть таблицу, в которой нужно обновить статистику.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-125">Click the plus sign to expand the table in which you want to update the statistic.</span></span>  
  
4.  <span data-ttu-id="2ccb3-126">Щелкните значок «плюс», чтобы развернуть папку **Статистика** .</span><span class="sxs-lookup"><span data-stu-id="2ccb3-126">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="2ccb3-127">Щелкните правой кнопкой мыши объект статистики, который нужно обновить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-127">Right-click the statistics object you wish to update and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="2ccb3-128">В диалоговом окне **Свойства статистики —**_Statistics_name_ установите флажок **Обновить статистику для этих столбцов** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-128">In the **Statistics Properties -**_statistics_name_ dialog box, select the **Update statistics for these columns** check box and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2ccb3-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2ccb3-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-a-specific-statistics-object"></a><span data-ttu-id="2ccb3-130">Обновление указанного объекта статистики</span><span class="sxs-lookup"><span data-stu-id="2ccb3-130">To update a specific statistics object</span></span>  
  
1.  <span data-ttu-id="2ccb3-131">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ccb3-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2ccb3-132">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2ccb3-133">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example updates the statistics for the AK_SalesOrderDetail_rowguid index of the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail AK_SalesOrderDetail_rowguid;   
    GO  
    ```  
  
#### <a name="to-update-all-statistics-in-a-table"></a><span data-ttu-id="2ccb3-134">Обновление всей статистики в таблице</span><span class="sxs-lookup"><span data-stu-id="2ccb3-134">To update all statistics in a table</span></span>  
  
1.  <span data-ttu-id="2ccb3-135">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ccb3-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2ccb3-136">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2ccb3-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all indexes on the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail;   
    GO  
    ```  
  
 <span data-ttu-id="2ccb3-138">Дополнительные сведения см. в статье [UPDATE STATISTICS (Transact-SQL)](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ccb3-138">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
#### <a name="to-update-all-statistics-in-a-database"></a><span data-ttu-id="2ccb3-139">Обновление всей статистики в базе данных</span><span class="sxs-lookup"><span data-stu-id="2ccb3-139">To update all statistics in a database</span></span>  
  
1.  <span data-ttu-id="2ccb3-140">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ccb3-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2ccb3-141">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2ccb3-142">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all tables in the database.   
    EXEC sp_updatestats;  
    ```  
  
 <span data-ttu-id="2ccb3-143">Дополнительные сведения см. в статье [sp_updatestats (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ccb3-143">For more information, see [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span></span>  
  
  
