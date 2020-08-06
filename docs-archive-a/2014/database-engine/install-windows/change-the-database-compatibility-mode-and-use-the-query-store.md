---
title: Миграция планов запросов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- query plans [SQL Server], migrating
- upgrading SQL Server, migrating query plans
- plan guides [SQL Server], migrating query plans
ms.assetid: 7e02a137-6867-4f6a-a45a-2b02674f7e65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dafd3a5f8a460bb08e63919c2cb853ad74dc2f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734433"
---
# <a name="migrate-query-plans"></a><span data-ttu-id="a50a4-102">Перенос планов запросов</span><span class="sxs-lookup"><span data-stu-id="a50a4-102">Migrate Query Plans</span></span>
  <span data-ttu-id="a50a4-103">В большинстве случаев обновление базы данных до последней версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] приведет к повышению производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="a50a4-103">In most cases, upgrading a database to the most recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will result in improved query performance.</span></span> <span data-ttu-id="a50a4-104">Однако при наличии ответственных запросов, для которых производительность тщательно настроена, перед началом обновления может оказаться полезным сохранить планы запросов, создав для каждого из них структуру плана.</span><span class="sxs-lookup"><span data-stu-id="a50a4-104">However, if you have mission-critical queries that have been carefully tuned for performance, you may want to preserve the query plans for these queries before upgrading by creating a plan guide for each query.</span></span> <span data-ttu-id="a50a4-105">Если после обновления оптимизатор запросов выбирает для некоторых запросов менее эффективный план, можно разрешить использование старых структур планов и заставить оптимизатор запросов пользоваться ими.</span><span class="sxs-lookup"><span data-stu-id="a50a4-105">If, after upgrading, the query optimizer chooses a less efficient plan for one or more of the queries, you can enable the plan guides and force the query optimizer to use the pre-upgrade plans.</span></span>  
  
 <span data-ttu-id="a50a4-106">Чтобы создать структуру плана, перед началом обновления выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a50a4-106">To create plan guides before upgrading follow these steps:</span></span>  
  
1.  <span data-ttu-id="a50a4-107">Запишите текущий план для каждого критического запроса, используя хранимую процедуру [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) и указав план запроса в указании запроса USE PLAN.</span><span class="sxs-lookup"><span data-stu-id="a50a4-107">Record the current plan for each mission critical query by using the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure and specifying the query plan in the USE PLAN query hint.</span></span>  
  
2.  <span data-ttu-id="a50a4-108">Убедитесь в том, что структура плана применена к запросу.</span><span class="sxs-lookup"><span data-stu-id="a50a4-108">Verify that the plan guide is applied to the query.</span></span>  
  
3.  <span data-ttu-id="a50a4-109">Обновите базу данных до более новой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a50a4-109">Upgrade the database to the newer version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="a50a4-110">Планы сохранятся в структурах плана обновленной базы данных и понадобятся в том случае, если потребуется регрессия планов после обновления.</span><span class="sxs-lookup"><span data-stu-id="a50a4-110">The plans are persisted in the upgraded database in the plan guides and serve as a fallback in case of plan regressions after the upgrade.</span></span>  
  
     <span data-ttu-id="a50a4-111">Рекомендуется не включать структуры планов после обновления, это может позволить упустить возможность применения в новой версии более оптимальных планов или полезных перекомпиляций в соответствии с обновленной статистикой.</span><span class="sxs-lookup"><span data-stu-id="a50a4-111">We recommend that you not enable the plan guides after the upgrade because you might miss opportunities for better plans in the new release or beneficial recompiles due to updated statistics.</span></span>  
  
4.  <span data-ttu-id="a50a4-112">Если после обновления выбираются менее эффективные планы, включите все или некоторые из структур планов, заменив ими новые.</span><span class="sxs-lookup"><span data-stu-id="a50a4-112">If less efficient plans are chosen after the upgrade, activate all or a subset of the plan guides to override the new plans.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a50a4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="a50a4-113">Example</span></span>  
 <span data-ttu-id="a50a4-114">Следующий пример иллюстрирует запись старого плана для запроса путем создания структуры плана.</span><span class="sxs-lookup"><span data-stu-id="a50a4-114">The following example shows how to record a pre-upgrade plan for a query by creating a plan guide.</span></span>  
  
### <a name="step-1-collect-the-plan"></a><span data-ttu-id="a50a4-115">Шаг 1. Получение плана</span><span class="sxs-lookup"><span data-stu-id="a50a4-115">Step 1: Collect the Plan</span></span>  
 <span data-ttu-id="a50a4-116">План запроса, записываемый в структуру плана, должен иметь формат XML.</span><span class="sxs-lookup"><span data-stu-id="a50a4-116">The query plan recorded in the plan guide must be in XML format.</span></span> <span data-ttu-id="a50a4-117">Планы запросов в формате XML могут быть созданы следующими способами.</span><span class="sxs-lookup"><span data-stu-id="a50a4-117">XML-formatted query plans can be produced through the following ways:</span></span>  
  
-   [<span data-ttu-id="a50a4-118">SET SHOWPLAN_XML</span><span class="sxs-lookup"><span data-stu-id="a50a4-118">SET SHOWPLAN_XML</span></span>](/sql/t-sql/statements/set-showplan-xml-transact-sql)  
  
-   [<span data-ttu-id="a50a4-119">SET STATISTICS XML</span><span class="sxs-lookup"><span data-stu-id="a50a4-119">SET STATISTICS XML</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
-   <span data-ttu-id="a50a4-120">Запрос query_plan столбца функции динамического управления [sys. dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a50a4-120">Querying the query_plan column of the [sys.dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) dynamic management function.</span></span>  
  
-   <span data-ttu-id="a50a4-121">[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Классы событий [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md)и [Showplan XML для запросов Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="a50a4-121">The [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md), and [Showplan XML For Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) event classes.</span></span>  
  
 <span data-ttu-id="a50a4-122">Следующий пример собирает план запроса для инструкции `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` путем запроса динамических административных представлений.</span><span class="sxs-lookup"><span data-stu-id="a50a4-122">The following example collects the query plan for the statement `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` by querying dynamic management views.</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%';  
GO  
```  
  
### <a name="step-2-create-the-plan-guide-to-force-the-plan"></a><span data-ttu-id="a50a4-123">Шаг 2. Создание структуры плана для принудительного применения плана</span><span class="sxs-lookup"><span data-stu-id="a50a4-123">Step 2: Create the Plan Guide to Force the Plan</span></span>  
 <span data-ttu-id="a50a4-124">Скопируйте план запроса в формате XML, полученный любым из описанных выше способов, из структуры плана, а затем вставьте его в виде строкового литерала в указание запроса USE PLAN предложения OPTION процедуры sp_create_plan_guide.</span><span class="sxs-lookup"><span data-stu-id="a50a4-124">Using the XML-formatted query plan (obtained by any of the methods previously described) in the plan guide, copy and paste the query plan as a string literal inside the USE PLAN query hint specified in the OPTION clause of sp_create_plan_guide.</span></span>  
  
 <span data-ttu-id="a50a4-125">В самом XML-плане перед созданием структуры плана необходимо экранировать входящие в него кавычки (').</span><span class="sxs-lookup"><span data-stu-id="a50a4-125">Within the XML plan itself, escape quotation marks (') that appear in the plan with a second quotation mark before creating the plan guide.</span></span> <span data-ttu-id="a50a4-126">Например, план, содержащий `WHERE A.varchar = 'This is a string'`, должен быть изменен и содержать `WHERE A.varchar = ''This is a string''`.</span><span class="sxs-lookup"><span data-stu-id="a50a4-126">For example, a plan that contains `WHERE A.varchar = 'This is a string'` must be escaped by modifying the code to `WHERE A.varchar = ''This is a string''`.</span></span>  
  
 <span data-ttu-id="a50a4-127">В следующем примере создается структура плана для плана запроса, собранного на шаге 1, и в параметр `@hints` вставляется XML Showplan для запроса.</span><span class="sxs-lookup"><span data-stu-id="a50a4-127">The following example creates a plan guide for the query plan collected in step 1 and inserts the XML Showplan for the query in the `@hints` parameter.</span></span> <span data-ttu-id="a50a4-128">Для краткости в пример включена только часть выходных данных Showplan.</span><span class="sxs-lookup"><span data-stu-id="a50a4-128">For brevity, only partial Showplan output is included in the example.</span></span>  
  
```  
EXECUTE sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',  
@type = N'SQL',  
@module_or_batch = NULL,  
@params = NULL,  
@hints = N'OPTION(USE PLAN N''<ShowPlanXML xmlns=''''https://schemas.microsoft.com/sqlserver/2004/07/showplan''''   
    Version=''''0.5'''' Build=''''9.00.1116''''>  
    <BatchSequence><Batch><Statements><StmtSimple>  
    ...  
    </StmtSimple></Statements></Batch>  
    </BatchSequence></ShowPlanXML>'')';  
GO  
```  
  
### <a name="step-3-verify-that-the-plan-guide-is-applied-to-the-query"></a><span data-ttu-id="a50a4-129">Шаг 3. Проверка применения структуры плана к запросу</span><span class="sxs-lookup"><span data-stu-id="a50a4-129">Step 3: Verify That the Plan Guide Is Applied to the Query</span></span>  
 <span data-ttu-id="a50a4-130">Выполните запрос еще раз и проверьте созданный план запроса.</span><span class="sxs-lookup"><span data-stu-id="a50a4-130">Run the query again and examine the query plan that is produced.</span></span> <span data-ttu-id="a50a4-131">Убедитесь, что план выполнения совпадает с тем, что был указан в структуре плана.</span><span class="sxs-lookup"><span data-stu-id="a50a4-131">You should see that the plan matches the one that you specified in the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50a4-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="a50a4-132">See Also</span></span>  
 <span data-ttu-id="a50a4-133">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a50a4-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="a50a4-134">[Указания запросов (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="a50a4-134">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="a50a4-135">Руководства планов</span><span class="sxs-lookup"><span data-stu-id="a50a4-135">Plan Guides</span></span>](../../relational-databases/performance/plan-guides.md)  
  
  
