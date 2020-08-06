---
title: Работа с отслеживанием изменений (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], making changes
- change tracking [SQL Server], troubleshooting
- updating data [SQL Server]
- troubleshooting [SQL Server], change tracking
- data changes [SQL Server]
- tracking data changes [SQL Server]
- data [SQL Server], changing
- change tracking [SQL Server], data restore
- change tracking [SQL Server], ensuring consistent results
- change tracking [SQL Server], handling changes
ms.assetid: 5aec22ce-ae6f-4048-8a45-59ed05f04dc5
author: rothja
ms.author: jroth
ms.openlocfilehash: bdb8205a789894caf8c8e2d3c3f491751757bab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668173"
---
# <a name="work-with-change-tracking-sql-server"></a><span data-ttu-id="9b52e-102">Работа с отслеживанием изменений (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9b52e-102">Work with Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="9b52e-103">Приложения, в которых используется отслеживание изменений, должны иметь возможность получать отслеженные изменения, применять эти изменения к другому хранилищу данных и обновлять базу данных-источник.</span><span class="sxs-lookup"><span data-stu-id="9b52e-103">Applications that use change tracking must be able to obtain tracked changes, apply these changes to another data store, and update the source database.</span></span> <span data-ttu-id="9b52e-104">В этом разделе описаны способы выполнения этих задач и роль отслеживания изменений в случае отработки отказа и необходимостью восстановить базу данных из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="9b52e-104">This topic describes how to perform these tasks, and also the role change tracking plays when a failover occurs and a database must be restored from a backup.</span></span>  
  
##  <a name="obtain-changes-by-using-change-tracking-functions"></a><a name="Obtain"></a> <span data-ttu-id="9b52e-105">Получение изменений с помощью функций отслеживания изменений</span><span class="sxs-lookup"><span data-stu-id="9b52e-105">Obtain Changes by Using Change Tracking Functions</span></span>  
 <span data-ttu-id="9b52e-106">Описывает, как использовать функции отслеживания изменений, чтобы получить изменения и сведения об изменениях, произведенных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-106">Describes how to use the change tracking functions to obtain changes and information about the changes that were made to a database.</span></span>  
  
### <a name="about-the-change-tracking-functions"></a><span data-ttu-id="9b52e-107">Сведения о функциях отслеживания изменений</span><span class="sxs-lookup"><span data-stu-id="9b52e-107">About the Change Tracking Functions</span></span>  
 <span data-ttu-id="9b52e-108">Чтобы получить изменения из базы данных и сведения об этих изменениях, приложения могут использовать следующие функции.</span><span class="sxs-lookup"><span data-stu-id="9b52e-108">Applications can use the following functions to obtain the changes that are made in a database and information about the changes:</span></span>  
  
 <span data-ttu-id="9b52e-109">Функция CHANGETABLE(CHANGES ...)</span><span class="sxs-lookup"><span data-stu-id="9b52e-109">CHANGETABLE(CHANGES ...) function</span></span>  
 <span data-ttu-id="9b52e-110">Эта функция, возвращающая набор строк, используется в запросе данных отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-110">This rowset function is used to query for change information.</span></span> <span data-ttu-id="9b52e-111">Функция запрашивает данные, хранящиеся во внутренних таблицах отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-111">The function queries the data stored in the internal change tracking tables.</span></span> <span data-ttu-id="9b52e-112">Она возвращает результирующий набор, содержащий первичные ключи измененных строк, а также другие сведения: операцию, число обновленных столбцов и версии строк.</span><span class="sxs-lookup"><span data-stu-id="9b52e-112">The function returns a results set that contains the primary keys of rows that have changed together with other change information such as the operation, columns updated and version for the row.</span></span>  
  
 <span data-ttu-id="9b52e-113">Функция CHANGETABLE(CHANGES ...) получает в качестве аргумента последнюю версию синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-113">CHANGETABLE(CHANGES ...) takes a last synchronization version as an argument.</span></span> <span data-ttu-id="9b52e-114">Версию, установленную при последней синхронизации, можно получить из переменной `@last_synchronization_version` .</span><span class="sxs-lookup"><span data-stu-id="9b52e-114">The last sychronization version is obtained using the `@last_synchronization_version` variable.</span></span> <span data-ttu-id="9b52e-115">Семантика последней версии синхронизации выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b52e-115">The semantics of the last synchronization version are as follows:</span></span>  
  
-   <span data-ttu-id="9b52e-116">Вызывающий клиент получает сведения обо всех изменениях, происшедших до момента последней синхронизированной версии включительно.</span><span class="sxs-lookup"><span data-stu-id="9b52e-116">The calling client has obtained changes and knows about all changes up to and including the last synchronization version.</span></span>  
  
-   <span data-ttu-id="9b52e-117">Функция CHANGETABLE(CHANGES ...) поэтому возвращает сведения обо всех изменениях, произошедших после последней версии синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-117">CHANGETABLE(CHANGES ...) will therefore return all changes that have occurred after the last synchronization version.</span></span>  
  
     <span data-ttu-id="9b52e-118">Ниже показано, как функция CHANGETABLE(CHANGES ...) используется для получения изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-118">The following illustration shows how CHANGETABLE(CHANGES ...) is used to obtain changes.</span></span>  
  
     <span data-ttu-id="9b52e-119">![Пример вывода результатов запроса на отслеживание изменений](../../database-engine/media/queryoutput.gif "Пример вывода результатов запроса на отслеживание изменений")</span><span class="sxs-lookup"><span data-stu-id="9b52e-119">![Example of change tracking query output](../../database-engine/media/queryoutput.gif "Example of change tracking query output")</span></span>  
  
 <span data-ttu-id="9b52e-120">Функция CHANGE_TRACKING_CURRENT_VERSION()</span><span class="sxs-lookup"><span data-stu-id="9b52e-120">CHANGE_TRACKING_CURRENT_VERSION() function</span></span>  
 <span data-ttu-id="9b52e-121">Используется для получения текущей версии, которая будет применяться при следующем запросе изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-121">Is used to obtain the current version that will be used the next time when querying changes.</span></span> <span data-ttu-id="9b52e-122">Эта версия представляет версию последней зафиксированной транзакции.</span><span class="sxs-lookup"><span data-stu-id="9b52e-122">This version represents the version of the last committed transaction.</span></span>  
  
 <span data-ttu-id="9b52e-123">Функция CHANGE_TRACKING_MIN_VALID_VERSION()</span><span class="sxs-lookup"><span data-stu-id="9b52e-123">CHANGE_TRACKING_MIN_VALID_VERSION()function</span></span>  
 <span data-ttu-id="9b52e-124">Используется для получения минимальной допустимой версии, имеющейся у клиента, при которой он еще сможет получать достоверные результаты из функции CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="9b52e-124">Is used to obtain the minimum valid version that a client can have and still obtain valid results from CHANGETABLE().</span></span> <span data-ttu-id="9b52e-125">Клиент должен сравнить последнюю версию синхронизации со значением, возвращенным этой функцией.</span><span class="sxs-lookup"><span data-stu-id="9b52e-125">The client should check the last synchronization version against the value thatis returned by this function.</span></span> <span data-ttu-id="9b52e-126">Если номер последней версии синхронизации меньше, чем возвращает эта функция, то он не сможет получить достоверные результаты из функции CHANGETABLE() и должен повторно инициализировать данные.</span><span class="sxs-lookup"><span data-stu-id="9b52e-126">If the last synchronization version is less than the version returned by this function, the client will be unable to obtain valid results from CHANGETABLE() and will have to reinitialize.</span></span>  
  
### <a name="obtaining-initial-data"></a><span data-ttu-id="9b52e-127">Получение первоначальных данных</span><span class="sxs-lookup"><span data-stu-id="9b52e-127">Obtaining Initial Data</span></span>  
 <span data-ttu-id="9b52e-128">Прежде чем приложение в первый раз получит изменения, оно должно выполнить запрос для получения первоначальных данных и версии синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-128">Before an application can obtain changes for the first time, the application must send a query to obtain the initial data and the synchronization version.</span></span> <span data-ttu-id="9b52e-129">Приложение должно получить соответствующие данные напрямую из таблицы, а затем вызвать функцию CHANGE_TRACKING_CURRENT_VERSION() для получения первоначальной версии.</span><span class="sxs-lookup"><span data-stu-id="9b52e-129">The application must obtain the appropriate data directly from the table, and then use CHANGE_TRACKING_CURRENT_VERSION() to obtain the initial version.</span></span> <span data-ttu-id="9b52e-130">Эта версия передается функции CHANGETABLE(CHANGES ...) при первом получении изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-130">This version will be passed to CHANGETABLE(CHANGES ...) the first time that changes are obtained.</span></span>  
  
 <span data-ttu-id="9b52e-131">В следующем примере показано получение первоначальной версии синхронизации и первоначального набора данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-131">The following example shows how to obtain the initial synchronization version and the initial data set.</span></span>  
  
```sql  
    -- Obtain the current synchronization version. This will be used next time that changes are obtained.  
    SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
    -- Obtain initial data set.  
    SELECT  
        P.ProductID, P.Name, P.ListPrice  
    FROM  
        SalesLT.Product AS P  
```  
  
### <a name="using-the-change-tracking-functions-to-obtain-changes"></a><span data-ttu-id="9b52e-132">Использование функций отслеживания изменений для получения изменений</span><span class="sxs-lookup"><span data-stu-id="9b52e-132">Using the Change Tracking Functions to Obtain Changes</span></span>  
 <span data-ttu-id="9b52e-133">Чтобы получить измененные строки таблицы и сведения об этих изменениях, используется функция CHANGETABLE(CHANGES...). Например, следующий запрос получает изменения в таблице `SalesLT.Product` .</span><span class="sxs-lookup"><span data-stu-id="9b52e-133">To obtain the changed rows for a table and information about the changes, use CHANGETABLE(CHANGES...). For example, the following query obtains changes for the `SalesLT.Product` table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, CT.SYS_CHANGE_OPERATION,  
    CT.SYS_CHANGE_COLUMNS, CT.SYS_CHANGE_CONTEXT  
FROM  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
  
```  
  
 <span data-ttu-id="9b52e-134">Как правило, клиенту нужно получить последние данные строки, а не просто первичные ключи.</span><span class="sxs-lookup"><span data-stu-id="9b52e-134">Usually, a client will want to obtain the latest data for a row instead of only the primary keys for the row.</span></span> <span data-ttu-id="9b52e-135">Поэтому приложение соединяет результаты запроса функции CHANGETABLE(CHANGES ...) с данными в пользовательской таблице.</span><span class="sxs-lookup"><span data-stu-id="9b52e-135">Therefore, an application would join the results from CHANGETABLE(CHANGES ...) with the data in the user table.</span></span> <span data-ttu-id="9b52e-136">Например, следующий запрос соединяется с таблицей `SalesLT.Product` , чтобы получить значения столбцов `Name` и `ListPrice` .</span><span class="sxs-lookup"><span data-stu-id="9b52e-136">For example, the following query joins with the `SalesLT.Product` table to obtain the values for the `Name` and `ListPrice` columns.</span></span> <span data-ttu-id="9b52e-137">Обратите внимание на использование `OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="9b52e-137">Note the use of `OUTER JOIN`.</span></span> <span data-ttu-id="9b52e-138">Это требуется, чтобы убедиться, что возвращаются сведения об изменениях в строках, удаленных из пользовательской таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b52e-138">This is required to make sure that the change information is returned for those rows that have been deleted from the user table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
 <span data-ttu-id="9b52e-139">Чтобы получить версию, которая будет использоваться в следующем перечислении изменений, используется функция CHANGE_TRACKING_CURRENT_VERSION(), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9b52e-139">To obtain the version for use in the next change enumeration, use CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION()  
```  
  
 <span data-ttu-id="9b52e-140">Когда приложение получает изменения, оно должно использовать как функцию CHANGETABLE(CHANGES...), так и CHANGE_TRACKING_CURRENT_VERSION(), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9b52e-140">When an application obtains changes, it must use both CHANGETABLE(CHANGES...) and CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
-- Obtain the current synchronization version. This will be used the next time CHANGETABLE(CHANGES...) is called.  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
-- Obtain incremental changes by using the synchronization version obtained the last time the data was synchronized.  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
### <a name="version-numbers"></a><span data-ttu-id="9b52e-141">Номера версий</span><span class="sxs-lookup"><span data-stu-id="9b52e-141">Version Numbers</span></span>  
 <span data-ttu-id="9b52e-142">База данных, для которой включено отслеживание изменений, содержит счетчик версий, который увеличивается при каждом изменении отслеживаемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="9b52e-142">A database that has change tracking enabled has a version counter that increases as changes are made to change tracked tables.</span></span> <span data-ttu-id="9b52e-143">Каждой изменяемой строке присваивается собственный номер версии.</span><span class="sxs-lookup"><span data-stu-id="9b52e-143">Each changed row has a version number that is associated with it.</span></span> <span data-ttu-id="9b52e-144">Когда в приложение отправляется запрос изменений, вызывается функция, возвращающая номер версии.</span><span class="sxs-lookup"><span data-stu-id="9b52e-144">When a request is sent to an application to query for changes, a function is called that supplies a version number.</span></span> <span data-ttu-id="9b52e-145">Эта функция возвращает сведения обо всех изменениях, которые были сделаны после этой версии.</span><span class="sxs-lookup"><span data-stu-id="9b52e-145">The function returns information about all the changes that have been made since that version.</span></span> <span data-ttu-id="9b52e-146">В некотором роде версия отслеживания изменений напоминает тип данных `rowversion`.</span><span class="sxs-lookup"><span data-stu-id="9b52e-146">In some ways, change tracking version is similar in concept to the `rowversion` data type.</span></span>  
  
### <a name="validating-the-last-synchronized-version"></a><span data-ttu-id="9b52e-147">Проверка последней синхронизированной версии</span><span class="sxs-lookup"><span data-stu-id="9b52e-147">Validating the Last Synchronized Version</span></span>  
 <span data-ttu-id="9b52e-148">Сведения об изменениях хранятся ограниченное время.</span><span class="sxs-lookup"><span data-stu-id="9b52e-148">Information about changes is maintained for a limited time.</span></span> <span data-ttu-id="9b52e-149">Длительность этого времени управляется параметром CHANGE_RETENTION, который указывается в инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="9b52e-149">The length of time is controlled by the CHANGE_RETENTION parameter that can be specified as part of the ALTER DATABASE.</span></span>  
  
 <span data-ttu-id="9b52e-150">Имейте в виду, что время, заданное параметром CHANGE_RETENTION, определяет, как  часто все приложения должны запрашивать изменения в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-150">Be aware that the time specified for CHANGE_RETENTION determines how frequently all applications must request changes from the database.</span></span> <span data-ttu-id="9b52e-151">Если значение параметра *last_synchronization_version* в приложении старше минимально допустимой версии синхронизации для таблицы, это приложение не сможет выполнить достоверное перечисление изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-151">If an application has a value for *last_synchronization_version* that is older than the minimum valid synchronization version for a table, that application cannot perform valid change enumeration.</span></span> <span data-ttu-id="9b52e-152">Это объясняется тем, что некоторые данные изменений могли быть очищены.</span><span class="sxs-lookup"><span data-stu-id="9b52e-152">This is because some change information might have been cleaned up.</span></span> <span data-ttu-id="9b52e-153">Прежде чем приложение получит изменения с помощью функции CHANGETABLE(CHANGES ...), оно должно проверить значение параметра *last_synchronization_version* , которое нужно передать функции CHANGETABLE(CHANGES ...). Если значение параметра *last_synchronization_version* недопустимо, приложение должно повторно инициализировать все данные.</span><span class="sxs-lookup"><span data-stu-id="9b52e-153">Before an application obtains changes by using CHANGETABLE(CHANGES ...), the application must validate the value for *last_synchronization_version* that it plans to pass to CHANGETABLE(CHANGES ...). If the value of *last_synchronization_version* is not valid, that application must reinitialize all the data.</span></span>  
  
 <span data-ttu-id="9b52e-154">В следующем примере показано, как проверять достоверность значения `last_synchronization_version` для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b52e-154">The following example shows how to verify the validity of the value of `last_synchronization_version` for each table.</span></span>  
  
```sql  
-- Check individual table.  
IF (@last_synchronization_version < CHANGE_TRACKING_MIN_VALID_VERSION(  
                                   OBJECT_ID('SalesLT.Product')))  
BEGIN  
  -- Handle invalid version and do not enumerate changes.  
  -- Client must be reinitialized.  
END  
```  
  
 <span data-ttu-id="9b52e-155">Как показано в следующем примере, достоверность значения `last_synchronization_version` можно проверить для всех таблиц в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-155">As the following example shows, the validity of the value of `last_synchronization_version` can be checked against all tables in the database.</span></span>  
  
```sql  
-- Check all tables with change tracking enabled  
IF EXISTS (  
  SELECT COUNT(*) FROM sys.change_tracking_tables  
  WHERE min_valid_version > @last_synchronization_version )  
BEGIN  
  -- Handle invalid version & do not enumerate changes  
  -- Client must be reinitialized  
END  
```  
  
### <a name="using-column-tracking"></a><span data-ttu-id="9b52e-156">Использование отслеживания столбцов</span><span class="sxs-lookup"><span data-stu-id="9b52e-156">Using Column Tracking</span></span>  
 <span data-ttu-id="9b52e-157">Отслеживание столбцов позволяет приложениям получать изменившиеся данные не всей строки, а только одного столбца.</span><span class="sxs-lookup"><span data-stu-id="9b52e-157">Column tracking enables applications to obtain the data for only the columns that have changed instead of the whole row.</span></span> <span data-ttu-id="9b52e-158">Например, рассмотрим ситуацию, когда в таблице имеются один или два больших, но редко изменяющихся столбца и другие столбцы, значения которых часто меняются.</span><span class="sxs-lookup"><span data-stu-id="9b52e-158">For example, consider the scenario in which a table has one or more columns that are large, but rarely change; and also has other columns that frequently change.</span></span> <span data-ttu-id="9b52e-159">Не применяя отслеживание столбцов, приложение может только определить изменение строки и синхронизировать все данные, включая данные больших столбцов.</span><span class="sxs-lookup"><span data-stu-id="9b52e-159">Without column tracking, an application can only determine that a row has changed and would have to synchronize all the data that includes the large column data.</span></span> <span data-ttu-id="9b52e-160">Но с помощью отслеживания столбцов приложение может определить, в каких столбцах изменились значения, и синхронизировать только изменившиеся данные.</span><span class="sxs-lookup"><span data-stu-id="9b52e-160">However, by using column tracking, an application can determine whether the large column data changed and only synchronize the data if it has changed.</span></span>  
  
 <span data-ttu-id="9b52e-161">Сведения об отслеживании столбцов отображаются в столбце SYS_CHANGE_COLUMNS, который возвращается функцией CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="9b52e-161">Column tracking information appears in the SYS_CHANGE_COLUMNS column that is returned by the CHANGETABLE(CHANGES ...) function.</span></span>  
  
 <span data-ttu-id="9b52e-162">Отслеживание столбцов может применяться таким образом, чтобы для всех неизменившихся столбцов возвращалось значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9b52e-162">Column tracking can be used so that NULL is returned for a column that has not changed.</span></span> <span data-ttu-id="9b52e-163">Если значение NULL недопустимо для того или иного столбца, можно возвратить отдельный столбец, который укажет, изменялись ли данные этого столбца.</span><span class="sxs-lookup"><span data-stu-id="9b52e-163">If the column can be changed to NULL, a separate column must be returned to indicate whether the column changed.</span></span>  
  
 <span data-ttu-id="9b52e-164">В следующем примере столбец `CT_ThumbnailPhoto` будет иметь значение `NULL` , если он не был изменен.</span><span class="sxs-lookup"><span data-stu-id="9b52e-164">In the following example, the `CT_ThumbnailPhoto` column will be `NULL` if that column did not change.</span></span> <span data-ttu-id="9b52e-165">Этот столбец может также принимать значение `NULL` , потому что он был изменен на `NULL` , поэтому приложение может использовать столбец `CT_ThumbNailPhoto_Changed` , чтобы определить, происходили ли изменения.</span><span class="sxs-lookup"><span data-stu-id="9b52e-165">This column could also be `NULL` because it was changed to `NULL` - the application can use the `CT_ThumbNailPhoto_Changed` column to determine whether the column changed.</span></span>  
  
```sql  
DECLARE @PhotoColumnId int = COLUMNPROPERTY(  
    OBJECT_ID('SalesLT.Product'),'ThumbNailPhoto', 'ColumnId')  
  
SELECT  
    CT.ProductID, P.Name, P.ListPrice, -- Always obtain values.  
    CASE  
           WHEN CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) = 1  
            THEN ThumbNailPhoto  
            ELSE NULL  
      END AS CT_ThumbNailPhoto,  
      CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) AS  
                                   CT_ThumbNailPhoto_Changed  
     CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
     CT.SYS_CHANGE_CONTEXT  
FROM  
     SalesLT.Product AS P  
INNER JOIN  
     CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
     P.ProductID = CT.ProductID AND  
     CT.SYS_CHANGE_OPERATION = 'U'  
```  
  
### <a name="obtaining-consistent-and-correct-results"></a><span data-ttu-id="9b52e-166">Получение согласованных и правильных результатов</span><span class="sxs-lookup"><span data-stu-id="9b52e-166">Obtaining Consistent and Correct Results</span></span>  
 <span data-ttu-id="9b52e-167">Для получения измененных данных для таблицы требуется несколько шагов.</span><span class="sxs-lookup"><span data-stu-id="9b52e-167">Obtaining the changed data for a table requires multiple steps.</span></span> <span data-ttu-id="9b52e-168">Имейте в виду, что, если не удастся решить некоторые проблемы, будут возвращены несогласованные или неверные результаты.</span><span class="sxs-lookup"><span data-stu-id="9b52e-168">Be aware that inconsistent or incorrect results could be returned if certain issues are not considered and handled.</span></span>  
  
 <span data-ttu-id="9b52e-169">Например, чтобы получить изменения в таблицах Sales и SalesOrders, приложение должно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b52e-169">For example, to obtain the changes that were made to a Sales table and SalesOrders table, an application would perform the following steps:</span></span>  
  
1.  <span data-ttu-id="9b52e-170">Проверить последнюю синхронизированную версию с помощью функции CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="9b52e-170">Validate the last synchronized version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
2.  <span data-ttu-id="9b52e-171">Получить версию, которая будет использована для получения изменений в следующий раз, с помощью функции CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="9b52e-171">Obtain the version that can be used to obtain change the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
3.  <span data-ttu-id="9b52e-172">Получите изменения для таблицы Sales с помощью функции CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="9b52e-172">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...).</span></span>  
  
4.  <span data-ttu-id="9b52e-173">Получите изменения для таблицы SalesOrders с помощью функции CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="9b52e-173">Obtain the changes for the SalesOrders table by using CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="9b52e-174">В базе данных выполняются следующие два процесса, которые могут повлиять на результаты, возвращаемые на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="9b52e-174">Two processes are occurring in the database that can affect the results that are returned by the previous steps:</span></span>  
  
-   <span data-ttu-id="9b52e-175">Процесс очистки выполняется в фоновом режиме и удаляет данные отслеживания изменений старше указанного срока хранения.</span><span class="sxs-lookup"><span data-stu-id="9b52e-175">The cleanup process runs in the background and removes change tracking information that is older than the specified retention period.</span></span>  
  
     <span data-ttu-id="9b52e-176">Процесс очистки является отдельным фоновым процессом и руководствуется сроком хранения, заданным при настройке отслеживания изменений в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-176">The cleanup process is a separate background process that uses the retention period that is specified when you configure change tracking for the database.</span></span> <span data-ttu-id="9b52e-177">Проблема заключается в том, что он может выполняться в промежуток между проверкой последней версии синхронизации и вызовом функции CHANGETABLE(CHANGES...).</span><span class="sxs-lookup"><span data-stu-id="9b52e-177">The issue is that the cleanup process can occur in the time between when the last synchronization version was validated and when the call to CHANGETABLE(CHANGES...) is made.</span></span> <span data-ttu-id="9b52e-178">Последняя достоверная версия синхронизации может оказаться ошибочной ко времени получения изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-178">A last synchronization version that was just valid might no longer be valid by the time the changes are obtained.</span></span> <span data-ttu-id="9b52e-179">Поэтому функция может возвратить неверные результаты.</span><span class="sxs-lookup"><span data-stu-id="9b52e-179">Therefore, incorrect results might be returned.</span></span>  
  
-   <span data-ttu-id="9b52e-180">В таблицах Sales и SalesOrders постоянно выполняются операции DML, например следующие.</span><span class="sxs-lookup"><span data-stu-id="9b52e-180">Ongoing DML operations are occurring in the Sales and SalesOrders tables, such as the following operations:</span></span>  
  
    -   <span data-ttu-id="9b52e-181">В таблицах могут происходить изменения после того, как с помощью функции CHANGE_TRACKING_CURRENT_VERSION() была получена последняя версия синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-181">Changes can be made to the tables after the version for next time has been obtained by using CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="9b52e-182">Следовательно, функция может вернуть больше изменений, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="9b52e-182">Therefore, more changes can be returned than expected.</span></span>  
  
    -   <span data-ttu-id="9b52e-183">Между вызовами функций для получения изменений из таблицы Sales и из таблицы SalesOrders могут быть зафиксированы транзакции.</span><span class="sxs-lookup"><span data-stu-id="9b52e-183">A transaction could commit in the time between the call to obtain changes from the Sales table and the call to obtain changes from the SalesOrders table.</span></span> <span data-ttu-id="9b52e-184">Следовательно, результаты для таблицы SalesOrder могут содержать внешние ключи, не имеющиеся в таблице Sales.</span><span class="sxs-lookup"><span data-stu-id="9b52e-184">Therefore, the results for the SalesOrder table could have foreign key value that does not exist in the Sales table.</span></span>  
  
 <span data-ttu-id="9b52e-185">Для преодоления приведенных выше проблем рекомендуется применять изоляцию моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="9b52e-185">To overcome the previously listed challenges, we recommend that you use snapshot isolation.</span></span> <span data-ttu-id="9b52e-186">Это позволит обеспечить согласованность сведений об изменениях и избежать соперничества при выполнении задач фоновой очистки.</span><span class="sxs-lookup"><span data-stu-id="9b52e-186">This will help to ensure consistency of change information and avoid race conditions that are related to the background cleanup task.</span></span> <span data-ttu-id="9b52e-187">Если не применять транзакции моментального снимка, разработка приложения, использующего отслеживание изменений, может потребовать значительно больше усилий.</span><span class="sxs-lookup"><span data-stu-id="9b52e-187">If you do not use snapshot transactions, developing an application that uses change tracking could require significantly more effort.</span></span>  
  
#### <a name="using-snapshot-isolation"></a><span data-ttu-id="9b52e-188">Использование изоляции моментального снимка</span><span class="sxs-lookup"><span data-stu-id="9b52e-188">Using Snapshot Isolation</span></span>  
 <span data-ttu-id="9b52e-189">Отслеживание изменений было разработано для слаженной работы вместе с изоляцией моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="9b52e-189">Change tracking has been designed to work well with snapshot isolation.</span></span> <span data-ttu-id="9b52e-190">В базе данных необходимо активировать изоляцию моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="9b52e-190">Snapshot isolation must be enabled for the database.</span></span> <span data-ttu-id="9b52e-191">Все шаги, необходимые для получения изменений, должны включаться в транзакцию моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="9b52e-191">All the steps that are required to obtain changes must be included inside a snapshot transaction.</span></span> <span data-ttu-id="9b52e-192">Этим обеспечивается то, что все изменения данных, выполненные во время получения изменений, не будут видны запросам внутри транзакции моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="9b52e-192">This will ensure that all changes that are made to data while obtaining changes will not be visible to the queries inside the snapshot transaction.</span></span>  
  
 <span data-ttu-id="9b52e-193">Чтобы получить данные в транзакции моментального снимка, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b52e-193">To obtain data inside a snapshot transaction, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="9b52e-194">Установите уровень изоляции транзакции на уровень моментальных снимков и запустите транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9b52e-194">Set the transaction isolation level to snapshot and start a transaction.</span></span>  
  
2.  <span data-ttu-id="9b52e-195">Проверьте последнюю версию синхронизации с помощью функции CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="9b52e-195">Validate the last synchronization version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
3.  <span data-ttu-id="9b52e-196">Получите версию, которая будет использоваться в следующий раз, с помощью функции CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="9b52e-196">Obtain the version to be used the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
4.  <span data-ttu-id="9b52e-197">Получите изменения для таблицы Sales с помощью функции CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="9b52e-197">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...)</span></span>  
  
5.  <span data-ttu-id="9b52e-198">Получите изменения для таблицы SalesOrders с помощью функции CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="9b52e-198">Obtain the changes for the Salesorders table by using CHANGETABLE(CHANGES ...)</span></span>  
  
6.  <span data-ttu-id="9b52e-199">Зафиксируйте транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9b52e-199">Commit the transaction.</span></span>  
  
 <span data-ttu-id="9b52e-200">Необходимо помнить, что все действия для получения изменений находятся внутри транзакции моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="9b52e-200">Some points to remember as all steps to obtain changes are inside a snapshot transaction:</span></span>  
  
-   <span data-ttu-id="9b52e-201">Если очистка происходит после проверки последней версии синхронизации, результаты функции CHANGETABLE(CHANGES ...) будут, тем не менее, достоверными, так как операция удаления, выполняемая процессом очистки, не будет видна внутри транзакции.</span><span class="sxs-lookup"><span data-stu-id="9b52e-201">If cleanup occurs after the last synchronization version is validated, the results from CHANGETABLE(CHANGES ...) will still be valid as the delete operations performed by cleanup will not be visible inside the transaction.</span></span>  
  
-   <span data-ttu-id="9b52e-202">Все изменения в таблице Sales или SalesOrders после получения версии следующей синхронизации не будут видны в транзакции, поэтому вызовы функции CHANGETABLE(CHANGES ...) никогда не будут возвращать изменения с версией более поздней, чем возвращенные функцией CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="9b52e-202">Any changes that are made to the Sales table or the SalesOrders table after the next synchronization version is obtained will not be visible, and the calls to CHANGETABLE(CHANGES ...) will never return changes with a version later than that returned by CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="9b52e-203">Сохранится также согласованность между таблицами Sales и SalesOrders, поскольку транзакции, зафиксированные между вызовами функции CHANGETABLE(CHANGES ...), будут невидимы.</span><span class="sxs-lookup"><span data-stu-id="9b52e-203">Consistency between the Sales table and the SalesOrders table will also be maintained, because the transactions that were committed in the time between calls to CHANGETABLE(CHANGES ...) will not be visible.</span></span>  
  
 <span data-ttu-id="9b52e-204">В следующем примере показано включение изоляции моментального снимка в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-204">The following example shows how snapshot isolation is enabled for a database.</span></span>  
  
```sql  
-- The database must be configured to enable snapshot isolation.  
ALTER DATABASE AdventureWorksLT  
    SET ALLOW_SNAPSHOT_ISOLATION ON;  
```  
  
 <span data-ttu-id="9b52e-205">Транзакция моментального снимка используется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b52e-205">A snapshot transaction is used as follows:</span></span>  
  
```sql  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
  -- Verify that version of the previous synchronization is valid.  
  -- Obtain the version to use next time.  
  -- Obtain changes.  
COMMIT TRAN  
```  
  
 <span data-ttu-id="9b52e-206">Дополнительные сведения о транзакциях моментальных снимков см. в разделе [SET TRANSACTION ISOLATION LEVEL (Transact-SQL)](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b52e-206">For more information about snapshot transactions, see [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
#### <a name="alternatives-to-using-snapshot-isolation"></a><span data-ttu-id="9b52e-207">Альтернативы для изоляции моментального снимка</span><span class="sxs-lookup"><span data-stu-id="9b52e-207">Alternatives to Using Snapshot Isolation</span></span>  
 <span data-ttu-id="9b52e-208">Существуют альтернативы использованию изоляции моментального снимка, но они требуют больше усилий, чтобы обеспечить требования всех приложений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-208">There are alternatives to using snapshot isolation, but they require more work to make sure all application requirements are met.</span></span> <span data-ttu-id="9b52e-209">Чтобы убедиться в достоверности параметра *last_synchronization_version* , а также в том, что данные не удаляются процессом очистки до получения изменений, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b52e-209">To make sure the *last_synchronization_version* is valid and data is not removed by the cleanup process before changes are obtained, do the following:</span></span>  
  
1.  <span data-ttu-id="9b52e-210">Проверьте параметр *last_synchronization_version* после вызовов функции CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="9b52e-210">Check *last_synchronization_version* after the calls to CHANGETABLE().</span></span>  
  
2.  <span data-ttu-id="9b52e-211">Проверяйте параметр *last_synchronization_version* в составе каждого запроса, чтобы получить изменения с помощью функции CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="9b52e-211">Check *last_synchronization_version* as part of each query to obtain changes by using CHANGETABLE().</span></span>  
  
 <span data-ttu-id="9b52e-212">Изменения могут происходить после получения версии синхронизации для следующего перечисления.</span><span class="sxs-lookup"><span data-stu-id="9b52e-212">Changes can occur after the synchronization version for the next enumeration has been obtained.</span></span> <span data-ttu-id="9b52e-213">Для обхода этой ситуации существует два способа.</span><span class="sxs-lookup"><span data-stu-id="9b52e-213">There are two ways to handle this situation.</span></span> <span data-ttu-id="9b52e-214">Используемый вариант зависит от приложения и обработки побочных эффектов каждого подхода.</span><span class="sxs-lookup"><span data-stu-id="9b52e-214">The option that is used depends on the application and how it can handle the side-effects of each approach:</span></span>  
  
-   <span data-ttu-id="9b52e-215">Пропускайте изменения с версиями больше, чем новая версия синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-215">Ignore changes that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="9b52e-216">Побочный эффект этого подхода заключается в том, что новая или обновленная строка будет пропущена, если она была создана или обновлена перед версией новой синхронизации, а затем обновлена после нее.</span><span class="sxs-lookup"><span data-stu-id="9b52e-216">This approach has the side effect that a new or updated row would be skipped if it was created or updated before the new synchronization version, but then updated afterward.</span></span> <span data-ttu-id="9b52e-217">Если имеется новая строка, может возникнуть нарушение ссылочной целостности, если в другой таблице была создана строка, которая ссылалась на  пропущенную строку.</span><span class="sxs-lookup"><span data-stu-id="9b52e-217">If there is a new row, a referential integrity problem might occur if there was a row in another table that was created that referenced the skipped row.</span></span> <span data-ttu-id="9b52e-218">Если существует обновленная строка, она будет пропущена и не синхронизирована до следующего раза.</span><span class="sxs-lookup"><span data-stu-id="9b52e-218">If there is an updated existing row, the row will be skipped and not synchronized until the next time.</span></span>  
  
-   <span data-ttu-id="9b52e-219">Включайте все изменения, даже с версиями больше, чем версия новой синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-219">Include all changes, even those that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="9b52e-220">Строки с версиями больше, чем версия новой синхронизации, будут опять получены во время следующей синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-220">The rows that have a version larger than the new synchronization version will be obtained again on the next synchronization.</span></span> <span data-ttu-id="9b52e-221">Приложение должно предполагать такую ситуацию и обрабатывать ее.</span><span class="sxs-lookup"><span data-stu-id="9b52e-221">This must be expected and handled by the application.</span></span>  
  
 <span data-ttu-id="9b52e-222">Кроме двух предыдущих вариантов можно разработать подход, сочетающий обе возможности в зависимости от операции.</span><span class="sxs-lookup"><span data-stu-id="9b52e-222">In addition to the previous two options, you can devise approach that combines both options, depending on the operation.</span></span> <span data-ttu-id="9b52e-223">Например, приложение может пропустить более новые изменения, чем версия следующей синхронизации, в том что касается создания или удаления, но не игнорировать обновления.</span><span class="sxs-lookup"><span data-stu-id="9b52e-223">For example, you might want an application for which it is best to ignore changes newer than the next synchronization version in which the row was created or deleted, but updates are not ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b52e-224">Выбор оптимального подхода для приложения, работающего с отслеживанием изменений, или любого пользовательского средства отслеживания изменений требует тщательного анализа.</span><span class="sxs-lookup"><span data-stu-id="9b52e-224">Choosing the approach that will work for the application when you are using change tracking (or any custom tracking mechanism), requires significant analysis.</span></span> <span data-ttu-id="9b52e-225">Поэтому намного проще использовать изоляцию моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="9b52e-225">Therefore, it is much simpler to use snapshot isolation.</span></span>  
  
##  <a name="how-change-tracking-handles-changes-to-a-database"></a><a name="Handles"></a><span data-ttu-id="9b52e-226">Как Отслеживание изменений обрабатывает изменения в базе данных</span><span class="sxs-lookup"><span data-stu-id="9b52e-226">How Change Tracking Handles Changes to a Database</span></span>  
 <span data-ttu-id="9b52e-227">Некоторые приложения, использующие отслеживание изменений, выполняют двустороннюю синхронизацию с другими хранилищами данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-227">Some applications that use change tracking perform two-way synchronization with another data store.</span></span> <span data-ttu-id="9b52e-228">Это означает, что изменения в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обновляются в другом хранилище данных, а изменения в другом хранилище данных обновляются в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b52e-228">That is, changes that are made in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database are updated in the other data store, and changes that are made in the other store are updated in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="9b52e-229">Если приложение обновляет локальную базу данных изменениями, сделанными в другом хранилище данных, оно должно выполнить следующие операции.</span><span class="sxs-lookup"><span data-stu-id="9b52e-229">When an application updates the local database with changes from another data store, the application must perform the following operations:</span></span>  
  
-   <span data-ttu-id="9b52e-230">Проверить наличие конфликтов.</span><span class="sxs-lookup"><span data-stu-id="9b52e-230">Check for conflicts.</span></span>  
  
     <span data-ttu-id="9b52e-231">Конфликт возникает, когда одни и те же данные одновременно изменяются в обоих хранилищах данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-231">A conflict occurs when the same data is changed at the same time in both data stores.</span></span> <span data-ttu-id="9b52e-232">Приложение должно иметь возможность проверить наличие конфликта и получить достаточно информации для его разрешения.</span><span class="sxs-lookup"><span data-stu-id="9b52e-232">The application must be able to check for a conflict and obtain enough information to enable the conflict to be resolved.</span></span>  
  
-   <span data-ttu-id="9b52e-233">Сохранить контекстные сведения приложения.</span><span class="sxs-lookup"><span data-stu-id="9b52e-233">Store application context information.</span></span>  
  
     <span data-ttu-id="9b52e-234">Приложение хранит данные, с которыми связана информация отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-234">The application stores data that has the change tracking information.</span></span> <span data-ttu-id="9b52e-235">Эта информация должна быть доступна вместе с другими данными отслеживания изменений, если изменения были получены из локальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-235">This information would be available together with other change tracking information when changes were obtained from the local database.</span></span> <span data-ttu-id="9b52e-236">Типичный пример таких контекстных сведений – идентификатор хранилища данных, которое было источником изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-236">A common example of this contextual information is an identifier for the data store that was the source of the change.</span></span>  
  
 <span data-ttu-id="9b52e-237">Для выполнения вышеуказанных операций приложение синхронизации может использовать следующие функции:</span><span class="sxs-lookup"><span data-stu-id="9b52e-237">To perform the previous operations, a synchronization application can use the following functions:</span></span>  
  
-   <span data-ttu-id="9b52e-238">CHANGETABLE(VERSION...)</span><span class="sxs-lookup"><span data-stu-id="9b52e-238">CHANGETABLE(VERSION...)</span></span>  
  
     <span data-ttu-id="9b52e-239">Когда приложение выполняет изменения, оно может использовать эту функцию для проверки конфликтов.</span><span class="sxs-lookup"><span data-stu-id="9b52e-239">When an application is making changes, it can use this function to check for conflicts.</span></span> <span data-ttu-id="9b52e-240">Функция получает последние данные отслеживания изменений в заданной строке в таблицу отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-240">The function obtains the latest change tracking information for a specified row in a change tracked table.</span></span> <span data-ttu-id="9b52e-241">Эти данные содержат версию последней измененной строки.</span><span class="sxs-lookup"><span data-stu-id="9b52e-241">The change tracking information includes the version of the row that was last changed.</span></span> <span data-ttu-id="9b52e-242">Это позволяет приложению определить, изменилась ли строка с момента последней синхронизации приложения.</span><span class="sxs-lookup"><span data-stu-id="9b52e-242">This information enables an application to determine whether the row was changed after the last time that the application was synchronized.</span></span>  
  
-   <span data-ttu-id="9b52e-243">WITH CHANGE_TRACKING_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="9b52e-243">WITH CHANGE_TRACKING_CONTEXT</span></span>  
  
     <span data-ttu-id="9b52e-244">Приложение может использовать это предложение для хранения контекстных данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-244">An application can use this clause to store context data.</span></span>  
  
### <a name="checking-for-conflicts"></a><span data-ttu-id="9b52e-245">Проверка наличия конфликтов</span><span class="sxs-lookup"><span data-stu-id="9b52e-245">Checking for Conflicts</span></span>  
 <span data-ttu-id="9b52e-246">В сценарии двусторонней синхронизации клиентское приложение должно определить, обновлялась ли строка с момента получения приложением последних изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-246">In a two-way synchronization scenario, the client application must determine whether a row has not been updated since the application last obtained the changes.</span></span>  
  
 <span data-ttu-id="9b52e-247">В следующем примере показано использование функции CHANGETABLE(VERSION ...) для проверки конфликтов самым эффективным способом — без отдельного запроса.</span><span class="sxs-lookup"><span data-stu-id="9b52e-247">The following example shows how to use the CHANGETABLE(VERSION ...) function to check for conflicts in the most efficient way, without a separate query.</span></span> <span data-ttu-id="9b52e-248">В примере `CHANGETABLE(VERSION ...)` определяет `SYS_CHANGE_VERSION` для строки, заданной аргументом `@product id`.</span><span class="sxs-lookup"><span data-stu-id="9b52e-248">In the example, `CHANGETABLE(VERSION ...)` determines the `SYS_CHANGE_VERSION` for the row specified by `@product id`.</span></span> <span data-ttu-id="9b52e-249">`CHANGETABLE(CHANGES ...)` может получить те же сведения, но это будет менее эффективным.</span><span class="sxs-lookup"><span data-stu-id="9b52e-249">`CHANGETABLE(CHANGES ...)` can obtain the same information, but that would be less efficient.</span></span> <span data-ttu-id="9b52e-250">Если значение `SYS_CHANGE_VERSION` для строки больше, чем значение `@last_sync_version`, существует конфликт.</span><span class="sxs-lookup"><span data-stu-id="9b52e-250">If the value of `SYS_CHANGE_VERSION` for the row is larger than the value of `@last_sync_version`, there is a conflict.</span></span> <span data-ttu-id="9b52e-251">Если возникает конфликт, эта строка не будет обновляться.</span><span class="sxs-lookup"><span data-stu-id="9b52e-251">If there is a conflict, the row will not be updated.</span></span> <span data-ttu-id="9b52e-252">Проверка `ISNULL()` необходима, поскольку для строки может не иметься информации об изменениях.</span><span class="sxs-lookup"><span data-stu-id="9b52e-252">The `ISNULL()` check is required because there might be no change information available for the row.</span></span> <span data-ttu-id="9b52e-253">Информации об изменениях не будет, если строка не была обновлена со времени включения отслеживания изменений или времени очистки информации об изменениях.</span><span class="sxs-lookup"><span data-stu-id="9b52e-253">No change information would exist if the row had not been updated since change tracking was enabled or since the change information was cleaned up.</span></span>  
  
```sql  
-- Assumption: @last_sync_version has been validated.  
  
UPDATE  
    SalesLT.Product  
SET  
    ListPrice = @new_listprice  
FROM  
    SalesLT.Product AS P  
WHERE  
    ProductID = @product_id AND  
    @last_sync_version >= ISNULL (  
        SELECT CT.SYS_CHANGE_VERSION  
        FROM CHANGETABLE(VERSION SalesLT.Product,  
                        (ProductID), (P.ProductID)) AS CT),  
        0)  
```  
  
 <span data-ttu-id="9b52e-254">Следующий код проверяет обновленное число строк и может предоставить более подробные сведения о конфликте.</span><span class="sxs-lookup"><span data-stu-id="9b52e-254">The following code can check the updated row count and can identify more information about the conflict.</span></span>  
  
```sql  
-- If the change cannot be made, find out more information.  
IF (@@ROWCOUNT = 0)  
BEGIN  
    -- Obtain the complete change information for the row.  
    SELECT  
        CT.SYS_CHANGE_VERSION, CT.SYS_CHANGE_CREATION_VERSION,  
        CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS  
    FROM  
        CHANGETABLE(CHANGES SalesLT.Product, @last_sync_version) AS CT  
    WHERE  
        CT.ProductID = @product_id;  
  
    -- Check CT.SYS_CHANGE_VERSION to verify that it really was a conflict.  
    -- Check CT.SYS_CHANGE_OPERATION to determine the type of conflict:  
    -- update-update or update-delete.  
    -- The row that is specified by @product_id might no longer exist   
    -- if it has been deleted.  
END  
```  
  
### <a name="setting-context-information"></a><span data-ttu-id="9b52e-255">Установка контекстных данных</span><span class="sxs-lookup"><span data-stu-id="9b52e-255">Setting Context Information</span></span>  
 <span data-ttu-id="9b52e-256">С помощью предложения WITH CHANGE_TRACKING_CONTEXT приложение может хранить контекстные данные вместе с информацией об изменениях.</span><span class="sxs-lookup"><span data-stu-id="9b52e-256">By using the WITH CHANGE_TRACKING_CONTEXT clause, an application can store context information together with the change information.</span></span> <span data-ttu-id="9b52e-257">Затем эти данные можно получить в столбце SYS_CHANGE_CONTEXT, который возвращает функция CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="9b52e-257">This information can then be obtained from the SYS_CHANGE_CONTEXT column that is returned by CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="9b52e-258">Контекстные данные обычно используются для определения источника изменений.</span><span class="sxs-lookup"><span data-stu-id="9b52e-258">Context information is typically used to identify the source of the changes.</span></span> <span data-ttu-id="9b52e-259">Если источник изменений можно определить, эти данные могут использоваться хранилищем данных, чтобы не получать изменения при повторной синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-259">If the source of the change can be identified, that information can be used by a data store to avoid obtaining changes when it synchronizes again.</span></span>  
  
```sql  
  -- Try to update the row and check for a conflict.  
  WITH CHANGE_TRACKING_CONTEXT (@source_id)  
  UPDATE  
     SalesLT.Product  
  SET  
      ListPrice = @new_listprice  
  FROM  
      SalesLT.Product AS P  
  WHERE  
     ProductID = @product_id AND  
     @last_sync_version >= ISNULL (  
         (SELECT CT.SYS_CHANGE_VERSION FROM CHANGETABLE(VERSION SalesLT.Product,  
         (ProductID), (P.ProductID)) AS CT),  
         0)  
```  
  
### <a name="ensuring-consistent-and-correct-results"></a><span data-ttu-id="9b52e-260">Обеспечение согласованных и правильных результатов</span><span class="sxs-lookup"><span data-stu-id="9b52e-260">Ensuring Consistent and Correct Results</span></span>  
 <span data-ttu-id="9b52e-261">Приложение должно учитывать процесс очистки при проверке значения параметра @last_sync_version.</span><span class="sxs-lookup"><span data-stu-id="9b52e-261">An application must consider the cleanup process when it validates the value of @last_sync_version.</span></span> <span data-ttu-id="9b52e-262">Это объясняется тем, что данные могли быть удалены после вызова функции CHANGE_TRACKING_MIN_VALID_VERSION(), но перед тем, как было выполнено обновление.</span><span class="sxs-lookup"><span data-stu-id="9b52e-262">This is because data could have been removed after CHANGE_TRACKING_MIN_VALID_VERSION() was called, but before the update was made.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9b52e-263">Рекомендуется использовать изоляцию моментального снимка и выполнять изменения в транзакции моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="9b52e-263">We recommend that you use snapshot isolation and make the changes within a snapshot transaction.</span></span>  
  
```sql  
-- Prerequisite is to ensure ALLOW_SNAPSHOT_ISOLATION is ON for the database.  
  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
    -- Verify that last_sync_version is valid.  
    IF (@last_sync_version <  
CHANGE_TRACKING_MIN_VALID_VERSION(OBJECT_ID('SalesLT.Product')))  
    BEGIN  
       RAISERROR (N'Last_sync_version too old', 16, -1);  
    END  
    ELSE  
    BEGIN  
        -- Try to update the row.  
        -- Check @@ROWCOUNT and check for a conflict.  
    END  
COMMIT TRAN  
```  
  
> [!NOTE]  
>  <span data-ttu-id="9b52e-264">Существует вероятность того, что обновляемая в рамках транзакции моментальных снимков строка уже была обновлена в другой транзакции после начала транзакции моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="9b52e-264">There is a possibility that the row being updated within the snapshot transaction could have been updated in another transaction after the snapshot transaction was started.</span></span> <span data-ttu-id="9b52e-265">В этом случае произойдет конфликт обновления при изоляции моментальных снимков, который вызовет прекращение транзакции.</span><span class="sxs-lookup"><span data-stu-id="9b52e-265">In this case, a snapshot isolation update conflict will occur and lead to the transaction being terminated.</span></span> <span data-ttu-id="9b52e-266">В этом случае повторите попытку обновления.</span><span class="sxs-lookup"><span data-stu-id="9b52e-266">If this happens, retry the update.</span></span> <span data-ttu-id="9b52e-267">В дальнейшем это приведет к обнаружению конфликта отслеживания изменений и ни одна из строк обновлена не будет.</span><span class="sxs-lookup"><span data-stu-id="9b52e-267">This will then lead to a change tracking conflict being detected and no rows being changed.</span></span>  
  
##  <a name="change-tracking-and-data-restore"></a><a name="DataRestore"></a><span data-ttu-id="9b52e-268">Отслеживание изменений и восстановление данных</span><span class="sxs-lookup"><span data-stu-id="9b52e-268">Change Tracking and Data Restore</span></span>  
 <span data-ttu-id="9b52e-269">Приложения, для которых необходима синхронизация, должны учитывать возможность восстановления базы данных, для которой включено отслеживание изменений, в предыдущее состояние.</span><span class="sxs-lookup"><span data-stu-id="9b52e-269">Applications that require synchronization must consider the case in which a database that has change tracking enabled reverts to an earlier version of the data.</span></span> <span data-ttu-id="9b52e-270">Речь идет о восстановлении базы данных из резервной копии при отработке отказа на асинхронную зеркальную базу данных или сбое при доставке журналов.</span><span class="sxs-lookup"><span data-stu-id="9b52e-270">This can occur after a database is restored from a backup, when there is a failover to an asynchronous database mirror, or when there is a failure when using log shipping.</span></span> <span data-ttu-id="9b52e-271">Эту проблему иллюстрирует следующий сценарий.</span><span class="sxs-lookup"><span data-stu-id="9b52e-271">The following scenario illustrates the issue:</span></span>  
  
1.  <span data-ttu-id="9b52e-272">Для таблицы Т1 включено отслеживание изменений. Минимальный действительный номер версии равен 50.</span><span class="sxs-lookup"><span data-stu-id="9b52e-272">Table T1 is change tracked, and the minimum valid version for table is 50.</span></span>  
  
2.  <span data-ttu-id="9b52e-273">Клиентское приложение синхронизирует данные версии 100 и получает все данные отслеживания изменений, произведенных с версии 50 до версии 100.</span><span class="sxs-lookup"><span data-stu-id="9b52e-273">A client application synchronizes data at version 100 and obtains information about all changes between versions 50 and 100.</span></span>  
  
3.  <span data-ttu-id="9b52e-274">После версии 100 в таблицу Т1 были внесены дополнительные изменения.</span><span class="sxs-lookup"><span data-stu-id="9b52e-274">Additional changes are made to table T1 after version 100.</span></span>  
  
4.  <span data-ttu-id="9b52e-275">После создания версии 120 произошел сбой, и участник базы данных восстанавливает базу с потерей части данных.</span><span class="sxs-lookup"><span data-stu-id="9b52e-275">At version 120, there is a failure and the database administrator restores the database with data loss.</span></span> <span data-ttu-id="9b52e-276">После завершения восстановления таблица содержит данные до версии 70, а минимальная синхронизированная версия по-прежнему равна 50.</span><span class="sxs-lookup"><span data-stu-id="9b52e-276">After the restore operation, the table contains data up through version 70, and the minimum synchronized version is still 50.</span></span>  
  
     <span data-ttu-id="9b52e-277">Это означает, что синхронизированное хранилище данных содержит данные, которых уже нет в первичном хранилище.</span><span class="sxs-lookup"><span data-stu-id="9b52e-277">This means that the synchronized data store has data that no longer exists in the primary data store.</span></span>  
  
5.  <span data-ttu-id="9b52e-278">Таблица Т1 обновлялась многократно.</span><span class="sxs-lookup"><span data-stu-id="9b52e-278">T1 is updated many times.</span></span> <span data-ttu-id="9b52e-279">Текущий номер версии для нее — 130.</span><span class="sxs-lookup"><span data-stu-id="9b52e-279">This brings the current version to 130.</span></span>  
  
6.  <span data-ttu-id="9b52e-280">Клиентское приложение синхронизируется вновь и получает номер последней синхронизации 100.</span><span class="sxs-lookup"><span data-stu-id="9b52e-280">The client application synchronizes again and supplies a last-synchronized version of 100.</span></span> <span data-ttu-id="9b52e-281">Проверка этого номера клиентом происходит успешно, так как 100 больше 50.</span><span class="sxs-lookup"><span data-stu-id="9b52e-281">The client validates this number successfully because 100 is greater than 50.</span></span>  
  
     <span data-ttu-id="9b52e-282">Клиент получает изменения между версиями 100 и 130.</span><span class="sxs-lookup"><span data-stu-id="9b52e-282">The client obtains changes between version 100 and 130.</span></span> <span data-ttu-id="9b52e-283">В этот момент времени клиент не знает, что изменения между версиями 70 и 100 уже не те, что были прежде.</span><span class="sxs-lookup"><span data-stu-id="9b52e-283">At this point, the client is not aware that the changes between 70 and 100 are not the same as before.</span></span> <span data-ttu-id="9b52e-284">Данные клиента и сервера не синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="9b52e-284">The data on the client and server are not synchronized.</span></span>  
  
 <span data-ttu-id="9b52e-285">Обратите внимание, что если бы база данных была восстановлена на момент времени после версии 100, то проблем с синхронизацией не возникло бы.</span><span class="sxs-lookup"><span data-stu-id="9b52e-285">Note that if the database was recovered to a point after version 100, there would be no problems with synchronization.</span></span> <span data-ttu-id="9b52e-286">Клиент и сервер должны правильно синхронизировать данные во время следующего интервала синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-286">The client and server would synchronize data correctly during the next synchronization interval.</span></span>  
  
 <span data-ttu-id="9b52e-287">Отслеживание изменений не помогает в случае необходимости восстановления утраченных данных по журналу.</span><span class="sxs-lookup"><span data-stu-id="9b52e-287">Change tracking does not provide support for recovering from the loss of data.</span></span> <span data-ttu-id="9b52e-288">Однако существует две возможности обнаружения проблем синхронизации такого рода.</span><span class="sxs-lookup"><span data-stu-id="9b52e-288">However, there are two options for detecting these types of synchronization issues:</span></span>  
  
-   <span data-ttu-id="9b52e-289">Сохраните идентификатор версии базы данных на сервере и обновляйте это значение при каждом восстановлении данных или их потере, вызванной любыми другими причинами.</span><span class="sxs-lookup"><span data-stu-id="9b52e-289">Store a database version ID on the server, and update this value whenever a database is recovered or otherwise loses data.</span></span> <span data-ttu-id="9b52e-290">Этот идентификатор должно хранить и проверять во время синхронизации данных каждое клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="9b52e-290">Each client application would store the ID, and each client would have to validate this ID when it synchronizes data.</span></span> <span data-ttu-id="9b52e-291">При потере данных идентификаторы не совпадут, что заставит клиента произвести повторную инициализацию.</span><span class="sxs-lookup"><span data-stu-id="9b52e-291">If data loss occurs, the IDs will not match and the clients would reinitialize.</span></span> <span data-ttu-id="9b52e-292">Недостатком такого подхода является то, что клиент может проводить повторную инициализацию, которая окажется ненужной в случае, если потеря данных не пересекала границу последней синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9b52e-292">One drawback is if the data loss had not crossed the last synchronized boundary, the client might do unnecessary reinitialization.</span></span>  
  
-   <span data-ttu-id="9b52e-293">Когда клиент делает запрос об изменениях, сохраните номер последней версии синхронизации каждого клиента сервера.</span><span class="sxs-lookup"><span data-stu-id="9b52e-293">When a client queries for changes, record the last synchronization version number for each client on the server.</span></span> <span data-ttu-id="9b52e-294">При возникновении проблем с данными номера последней синхронизированной версии не совпадут.</span><span class="sxs-lookup"><span data-stu-id="9b52e-294">If there is a problem with the data, the last synchronized version numbers would not match.</span></span> <span data-ttu-id="9b52e-295">Это будет означать, что необходима повторная инициализация.</span><span class="sxs-lookup"><span data-stu-id="9b52e-295">This indicates that a reinitialization is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b52e-296">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b52e-296">See Also</span></span>  
 <span data-ttu-id="9b52e-297">[Отслеживание измененных данных (SQL Server)](../track-changes/track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b52e-297">[Track Data Changes &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="9b52e-298">[Об отслеживании изменений (SQL Server)](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b52e-298">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="9b52e-299">[Управление Отслеживание изменений &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b52e-299">[Manage Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="9b52e-300">[Включение и отключение Отслеживание изменений &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b52e-300">[Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="9b52e-301">[&#40;"CHANGETABLE" Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b52e-301">[CHANGETABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span></span>  
 <span data-ttu-id="9b52e-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b52e-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span></span>  
 <span data-ttu-id="9b52e-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b52e-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span></span>  
 [<span data-ttu-id="9b52e-304">WITH CHANGE_TRACKING_CONTEXT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9b52e-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/with-change-tracking-context-transact-sql)  
  
  
