---
title: Создание и тестирование пользовательской функции-классификатора | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function create
- classifier function [SQL Server], test
- classifier function [SQL Server], create
- Resource Governor, classifier function test
ms.assetid: 7866b3c9-385b-40c6-aca5-32d3337032be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1b8e5371762e38cf2b3ac8c1d506b467dcfa7e3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731485"
---
# <a name="create-and-test-a-classifier-user-defined-function"></a><span data-ttu-id="c59b1-102">Создать и проверить определяемую пользователем функцию-классификатор</span><span class="sxs-lookup"><span data-stu-id="c59b1-102">Create and Test a Classifier User-Defined Function</span></span>
  <span data-ttu-id="c59b1-103">В этом разделе описывается создание и проверка определяемой пользователем функции-классификатора (UDF).</span><span class="sxs-lookup"><span data-stu-id="c59b1-103">This topic shows how to create and test a classifier user-defined function (UDF).</span></span> <span data-ttu-id="c59b1-104">Шаги включают выполнение инструкций языка [!INCLUDE[tsql](../../includes/tsql-md.md)] в редакторе запросов [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c59b1-104">The steps involve executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="c59b1-105">Пример, показанный в следующей процедуре, иллюстрирует возможности создания довольно сложной определяемой пользователем функции-классификатора.</span><span class="sxs-lookup"><span data-stu-id="c59b1-105">The example shown in the following procedure illustrates the possibilities for creating a fairly complex classifier user-defined function.</span></span>  
  
 <span data-ttu-id="c59b1-106">Пример.</span><span class="sxs-lookup"><span data-stu-id="c59b1-106">In our example:</span></span>  
  
-   <span data-ttu-id="c59b1-107">Пул ресурсов (pProductionProcessing) и группа рабочей нагрузки (gProductionProcessing) создаются для рабочей обработки в течение определенного диапазона времени.</span><span class="sxs-lookup"><span data-stu-id="c59b1-107">A resource pool (pProductionProcessing) and workload group (gProductionProcessing) are created for production processing during a specified time range.</span></span>  
  
-   <span data-ttu-id="c59b1-108">Пул ресурсов (pOffHoursProcessing) и группа рабочей нагрузки (gOffHoursProcessing) создаются для управления соединениями, не удовлетворяющими требованиям рабочей обработки.</span><span class="sxs-lookup"><span data-stu-id="c59b1-108">A resource pool (pOffHoursProcessing) and workload group (gOffHoursProcessing) are created for handling connections that do not meet the requirements for production processing.</span></span>  
  
-   <span data-ttu-id="c59b1-109">Таблица (TblClassificationTimeTable) создается в базе данных master для сохранения времени запуска и остановки, которые можно вычислить после времени входа в систему.</span><span class="sxs-lookup"><span data-stu-id="c59b1-109">A table (TblClassificationTimeTable) is created in master to hold start and end times that can be evaluated against a login time.</span></span> <span data-ttu-id="c59b1-110">Она должна быть создана в базе данных master, так как регулятор ресурсов использует для функций-классификаторов привязку к схеме.</span><span class="sxs-lookup"><span data-stu-id="c59b1-110">This must be created in master because Resource Governor uses schema binding for classifier functions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c59b1-111">Рекомендуется хранить большие часто обновляемые таблицы за пределами базы данных master.</span><span class="sxs-lookup"><span data-stu-id="c59b1-111">As a best practice, you should not store large, frequently updated tables in master.</span></span>  
  
 <span data-ttu-id="c59b1-112">Функция-классификатор увеличивает время входа в систему.</span><span class="sxs-lookup"><span data-stu-id="c59b1-112">The classifier function extends the login time.</span></span> <span data-ttu-id="c59b1-113">Излишне сложная функция может вызвать истечение времени ожидания при входе или снизить скорость быстрых соединений.</span><span class="sxs-lookup"><span data-stu-id="c59b1-113">An overly complex function can cause logins to time out or slow down fast connections.</span></span>  
  
### <a name="to-create-the-classifier-user-defined-function"></a><span data-ttu-id="c59b1-114">Создание определяемой пользователем функции-классификатора</span><span class="sxs-lookup"><span data-stu-id="c59b1-114">To create the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="c59b1-115">Создайте и настройте новые пулы ресурсов и группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="c59b1-115">Create and configure the new resource pools and workload groups.</span></span> <span data-ttu-id="c59b1-116">Назначьте каждую группу рабочей нагрузки соответствующему пулу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c59b1-116">Assign each workload group to the appropriate resource pool.</span></span>  
  
    ```  
    --- Create a resource pool for production processing  
    --- and set limits.  
    USE master  
    GO  
    CREATE RESOURCE POOL pProductionProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 100,  
         MIN_CPU_PERCENT = 50  
    )  
    GO  
    --- Create a workload group for production processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gProductionProcessing  
    WITH  
    (  
         IMPORTANCE = MEDIUM  
    )  
    --- Assign the workload group to the production processing  
    --- resource pool.  
    USING pProductionProcessing  
    GO  
    --- Create a resource pool for off-hours processing  
    --- and set limits.  
  
    CREATE RESOURCE POOL pOffHoursProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 50,  
         MIN_CPU_PERCENT = 0  
    )  
    GO  
    --- Create a workload group for off-hours processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gOffHoursProcessing  
    WITH  
    (  
         IMPORTANCE = LOW  
    )  
    --- Assign the workload group to the off-hours processing  
    --- resource pool.  
    USING pOffHoursProcessing  
    GO  
    ```  
  
2.  <span data-ttu-id="c59b1-117">Обновите конфигурацию, хранимую в памяти.</span><span class="sxs-lookup"><span data-stu-id="c59b1-117">Update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
3.  <span data-ttu-id="c59b1-118">Создайте таблицу и определите время запуска и остановки диапазона времени рабочей обработки.</span><span class="sxs-lookup"><span data-stu-id="c59b1-118">Create a table and define the start and end times for the production processing time range.</span></span>  
  
    ```  
    USE master  
    GO  
    CREATE TABLE tblClassificationTimeTable  
    (  
         strGroupName     sysname          not null,  
         tStartTime       time              not null,  
         tEndTime         time              not null  
    )  
    GO  
    --- Add time values that the classifier will use to  
    --- determine the workload group for a session.  
    INSERT into tblClassificationTimeTable VALUES('gProductionProcessing', '6:35 AM', '6:15 PM')  
    go  
    ```  
  
4.  <span data-ttu-id="c59b1-119">Создайте функцию-классификатор, использующую функции и значения времени, которые можно оценить со временем в таблице подстановки.</span><span class="sxs-lookup"><span data-stu-id="c59b1-119">Create the classifier function that uses time functions and values that can be evaluated against the times in the lookup table.</span></span> <span data-ttu-id="c59b1-120">Дополнительные сведения об использовании таблиц подстановки в функции-классификаторе см. в разделе "Рекомендации по использованию таблиц подстановки в функции-классификаторе" этой статьи.</span><span class="sxs-lookup"><span data-stu-id="c59b1-120">For information about using Lookup Tables in a classifier function, see "Best practices for using Lookup Tables in a classifier function" in this topic.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="c59b1-121">представлен расширенный набор типов данных и функций даты и времени.</span><span class="sxs-lookup"><span data-stu-id="c59b1-121">introduced an expanded set of date and time data types and functions.</span></span> <span data-ttu-id="c59b1-122">Дополнительные сведения см. в статье [Типы данных и функции даты и времени (Transact-SQL)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c59b1-122">For more information, see [Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
    ```  
    CREATE FUNCTION fnTimeClassifier()  
    RETURNS sysname  
    WITH SCHEMABINDING  
    AS  
    BEGIN  
         DECLARE @strGroup sysname  
         DECLARE @loginTime time  
         SET @loginTime = CONVERT(time,GETDATE())  
         SELECT TOP 1 @strGroup = strGroupName  
              FROM dbo.tblClassificationTimeTable  
              WHERE tStartTime <= @loginTime and tEndTime >= @loginTime  
         IF(@strGroup is not null)  
         BEGIN  
              RETURN @strGroup  
         END  
    --- Use the default workload group if there is no match  
    --- on the lookup.  
         RETURN N'gOffHoursProcessing'  
    END  
    GO  
    ```  
  
5.  <span data-ttu-id="c59b1-123">Зарегистрируйте функцию-классификатор и обновите конфигурацию, хранимую в памяти.</span><span class="sxs-lookup"><span data-stu-id="c59b1-123">Register the classifier function and update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR with (CLASSIFIER_FUNCTION = dbo.fnTimeClassifier)  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
### <a name="to-verify-the-resource-pools-workload-groups-and-the-classifier-user-defined-function"></a><span data-ttu-id="c59b1-124">Проверка пулов ресурсов, групп рабочей нагрузки и определяемой пользователем функции-классификатора</span><span class="sxs-lookup"><span data-stu-id="c59b1-124">To verify the resource pools, workload groups, and the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="c59b1-125">Получите пул ресурсов и настройку группы рабочей нагрузки при помощи следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="c59b1-125">Obtain the resource pool and workload group configuration by using the following query.</span></span>  
  
    ```  
    USE master  
    SELECT * FROM sys.resource_governor_resource_pools  
    SELECT * FROM sys.resource_governor_workload_groups  
    GO  
    ```  
  
2.  <span data-ttu-id="c59b1-126">С помощью следующих запросов убедитесь в том, что функция-классификатор существует и включена.</span><span class="sxs-lookup"><span data-stu-id="c59b1-126">Verify that the classifier function exists and is enabled by using the following queries.</span></span>  
  
    ```  
    --- Get the classifier function Id and state (enabled).  
    SELECT * FROM sys.resource_governor_configuration  
    GO  
    --- Get the classifer function name and the name of the schema  
    --- that it is bound to.  
    SELECT   
          object_schema_name(classifier_function_id) AS [schema_name],  
          object_name(classifier_function_id) AS [function_name]  
    FROM sys.dm_resource_governor_configuration  
  
    ```  
  
3.  <span data-ttu-id="c59b1-127">Получите текущие данные среды выполнения пулов ресурсов и групп рабочей нагрузки с помощью следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="c59b1-127">Obtain the current runtime data for the resource pools and workload groups by using the following query.</span></span>  
  
    ```  
    SELECT * FROM sys.dm_resource_governor_resource_pools  
    SELECT * FROM sys.dm_resource_governor_workload_groups  
    GO  
    ```  
  
4.  <span data-ttu-id="c59b1-128">С помощью следующего запроса выясните, какие сеансы существуют в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="c59b1-128">Find out what sessions are in each group by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, CAST(g.name as nvarchar(20)), s.session_id, s.login_time, CAST(s.host_name as nvarchar(20)), CAST(s.program_name AS nvarchar(20))  
              FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
              ON g.group_id = s.group_id  
    ORDER BY g.name  
    GO  
    ```  
  
5.  <span data-ttu-id="c59b1-129">С помощью следующего запроса выясните, какие запросы существуют в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="c59b1-129">Find out which requests are in each group by using the following query.</span></span>  
  
    ```  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
                ON g.group_id = r.group_id  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
6.  <span data-ttu-id="c59b1-130">С помощью следующего запроса выясните, какие запросы выполняются в классификаторе.</span><span class="sxs-lookup"><span data-stu-id="c59b1-130">Find out what requests are running in the classifier by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, g.name, s.session_id, s.login_time, s.host_name, s.program_name   
               FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = s.group_id  
                     AND 'preconnect' = s.status  
    ORDER BY g.name  
    GO  
  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = r.group_id  
                     AND 'preconnect' = r.status  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
### <a name="best-practices-for-using-lookup-tables-in-a-classifier-function"></a><span data-ttu-id="c59b1-131">Рекомендации по использованию таблиц подстановки в функции-классификаторе</span><span class="sxs-lookup"><span data-stu-id="c59b1-131">Best practices for using Lookup Tables in a classifier function</span></span>  
  
1.  <span data-ttu-id="c59b1-132">Не используйте таблицу подстановки без крайней необходимости.</span><span class="sxs-lookup"><span data-stu-id="c59b1-132">Do not use a lookup table unless it is absolutely necessary.</span></span> <span data-ttu-id="c59b1-133">Если таблицу подстановки необходимо использовать, ее можно включить в саму функцию, однако при этом следует учитывать сложность и динамические изменения функции-классификатора.</span><span class="sxs-lookup"><span data-stu-id="c59b1-133">If you need to use a lookup table, it can be hard coded into the function itself; however, this needs to be balanced with the complexity and dynamic changes of the classifier function.</span></span>  
  
2.  <span data-ttu-id="c59b1-134">Ограничьте ввод и вывод данных, выполняемые для таблиц подстановки.</span><span class="sxs-lookup"><span data-stu-id="c59b1-134">Limit the I/O performed for lookup tables.</span></span>  
  
    1.  <span data-ttu-id="c59b1-135">Воспользуйтесь инструкцией TOP 1, чтобы вернуть только одну строку.</span><span class="sxs-lookup"><span data-stu-id="c59b1-135">Use the TOP 1 to return only one row.</span></span>  
  
    2.  <span data-ttu-id="c59b1-136">Сведите к минимуму количество строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="c59b1-136">Minimize the number of rows in the table.</span></span>  
  
    3.  <span data-ttu-id="c59b1-137">Сделайте так, чтобы все строки таблицы были на одной странице или на небольшом количестве страниц.</span><span class="sxs-lookup"><span data-stu-id="c59b1-137">Make all rows of the table exist on a single page, or a small number of pages.</span></span>  
  
    4.  <span data-ttu-id="c59b1-138">Убедитесь, что строки, найденные с помощью операций Index Seek, используют как можно больше столбцов поиска.</span><span class="sxs-lookup"><span data-stu-id="c59b1-138">Confirm that rows found using the Index Seek operations use as many seeking columns as possible.</span></span>  
  
    5.  <span data-ttu-id="c59b1-139">Выполните денормализацию до одной таблицы, если необходимо использовать несколько таблиц с помощью инструкций объединения.</span><span class="sxs-lookup"><span data-stu-id="c59b1-139">De-normalize to a single table if you are considering using multiple tables with joins.</span></span>  
  
3.  <span data-ttu-id="c59b1-140">Запретите блокирование таблицы подстановки.</span><span class="sxs-lookup"><span data-stu-id="c59b1-140">Prevent blocking on the lookup table.</span></span>  
  
    1.  <span data-ttu-id="c59b1-141">Воспользуйтесь указанием `NOLOCK` для предотвращения блокирования или оператором `SET LOCK_TIMEOUT` в функции с максимальным значением 1000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="c59b1-141">Use the `NOLOCK` hint to prevent blocking or use `SET LOCK_TIMEOUT` in the function with a maximum value of 1000 milliseconds.</span></span>  
  
    2.  <span data-ttu-id="c59b1-142">Таблицы должны существовать в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="c59b1-142">Table(s) must exist in the master database.</span></span> <span data-ttu-id="c59b1-143">(Когда подключение устанавливают клиентские компьютеры, можно гарантировать восстановление только базы данных master.)</span><span class="sxs-lookup"><span data-stu-id="c59b1-143">(The master database is the only database that is guaranteed to be recovered when the client computers attempt to connect).</span></span>  
  
    3.  <span data-ttu-id="c59b1-144">Всегда указывайте полное имя таблицы со схемой.</span><span class="sxs-lookup"><span data-stu-id="c59b1-144">Always fully-qualify the table name with the schema.</span></span> <span data-ttu-id="c59b1-145">Имя базы данных не требуется, так как это должна быть база данных master.</span><span class="sxs-lookup"><span data-stu-id="c59b1-145">The database name is not necessary since it has to be the master database.</span></span>  
  
    4.  <span data-ttu-id="c59b1-146">Не используйте триггеры для таблицы.</span><span class="sxs-lookup"><span data-stu-id="c59b1-146">No triggers on the table.</span></span>  
  
    5.  <span data-ttu-id="c59b1-147">При обновлении содержимого таблицы обязательной используйте транзакцию уровня изоляции моментального снимка, чтобы запись не блокировала чтение.</span><span class="sxs-lookup"><span data-stu-id="c59b1-147">If you are updating the table contents, make sure to use a snapshot isolation level transaction to prevent Writer blocking Readers.</span></span> <span data-ttu-id="c59b1-148">Обратите внимание, что может также помочь использование указания `NOLOCK` .</span><span class="sxs-lookup"><span data-stu-id="c59b1-148">Note that using the `NOLOCK` hint should also mitigate this.</span></span>  
  
    6.  <span data-ttu-id="c59b1-149">По возможности отключите функцию-классификатор при изменении содержимого таблицы.</span><span class="sxs-lookup"><span data-stu-id="c59b1-149">If possible, disable the classifier function when changing the table contents.</span></span>  
  
        > [!WARNING]  
        >  <span data-ttu-id="c59b1-150">Рекомендуется использовать именно эти методы.</span><span class="sxs-lookup"><span data-stu-id="c59b1-150">We highly recommend following these best practices.</span></span> <span data-ttu-id="c59b1-151">Если что-то не позволяет использовать эти методы, рекомендуем связаться со службой технической поддержки Майкрософт для эффективного устранения возможных проблем.</span><span class="sxs-lookup"><span data-stu-id="c59b1-151">If there are issues that prevent you from following the best practices, we recommend that you contact Microsoft Support so that you can proactively prevent any future problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59b1-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="c59b1-152">See Also</span></span>  
 <span data-ttu-id="c59b1-153">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="c59b1-153">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="c59b1-154">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="c59b1-154">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="c59b1-155">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="c59b1-155">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="c59b1-156">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="c59b1-156">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="c59b1-157">[Настройка регулятора ресурсов с помощью шаблона](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="c59b1-157">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="c59b1-158">[Просмотр свойств регулятора ресурсов](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c59b1-158">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="c59b1-159">[ALTER RESOURCE GOVERNOR (Transact-SQL)](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c59b1-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span></span>  
 <span data-ttu-id="c59b1-160">[CREATE RESOURCE POOL (Transact-SQL)](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c59b1-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="c59b1-161">[CREATE WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c59b1-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="c59b1-162">[CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c59b1-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="c59b1-163">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c59b1-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
