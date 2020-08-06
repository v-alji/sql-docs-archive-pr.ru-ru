---
title: MSSQLSERVER_207 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 207 (Database Engine error)
ms.assetid: d1ab00c7-0331-437a-84fe-bae53b82feec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd6044c08ecd5a73f539bfbc1139d6257c2db9d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730714"
---
# <a name="mssqlserver_207"></a><span data-ttu-id="79659-102">MSSQLSERVER_207</span><span class="sxs-lookup"><span data-stu-id="79659-102">MSSQLSERVER_207</span></span>
    
## <a name="details"></a><span data-ttu-id="79659-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="79659-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79659-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="79659-104">Product Name</span></span>|<span data-ttu-id="79659-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="79659-105">SQL Server</span></span>|  
|<span data-ttu-id="79659-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="79659-106">Event ID</span></span>|<span data-ttu-id="79659-107">207</span><span class="sxs-lookup"><span data-stu-id="79659-107">207</span></span>|  
|<span data-ttu-id="79659-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="79659-108">Event Source</span></span>|<span data-ttu-id="79659-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="79659-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="79659-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="79659-110">Component</span></span>|<span data-ttu-id="79659-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="79659-111">SQLEngine</span></span>|  
|<span data-ttu-id="79659-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="79659-112">Symbolic Name</span></span>|<span data-ttu-id="79659-113">SQ_BADCOL</span><span class="sxs-lookup"><span data-stu-id="79659-113">SQ_BADCOL</span></span>|  
|<span data-ttu-id="79659-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="79659-114">Message Text</span></span>|<span data-ttu-id="79659-115">Недопустимое имя столбца «%.\*ls».</span><span class="sxs-lookup"><span data-stu-id="79659-115">Invalid column name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="79659-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="79659-116">Explanation</span></span>  
 <span data-ttu-id="79659-117">Возможны следующие причины возникновения этой ошибки запроса.</span><span class="sxs-lookup"><span data-stu-id="79659-117">This query error can be caused by one of the following problems.</span></span>  
  
-   <span data-ttu-id="79659-118">Имя столбца неправильно указано, либо столбец не существует ни в одной указанной таблице.</span><span class="sxs-lookup"><span data-stu-id="79659-118">The column name is misspelled or the column does not exist in any of the specified tables.</span></span>  
  
-   <span data-ttu-id="79659-119">Параметры сортировки базы данных учитывают регистр, а регистр имени столбца, указанный в запросе, не совпадает с регистром столбца, определенного в таблице.</span><span class="sxs-lookup"><span data-stu-id="79659-119">The collation of the database is case-sensitive and the case of the column name specified in the query does not match the case of the column defined in the table.</span></span> <span data-ttu-id="79659-120">Например, если столбец определен в таблице как **LastName**, а для базы данных используются параметры сортировки с учетом регистра, при выполнении запросов, в которых для этого столбца указано имя **Lastname** или **lastname**, возникнет ошибка 207, так как имена столбцов не совпадают.</span><span class="sxs-lookup"><span data-stu-id="79659-120">For example, when a column is defined in a table as **LastName** and the database uses a case-sensitive collation, queries that refer to the column as **Lastname** or **lastname** will cause error 207 to return because the column name does not match.</span></span>  
  
-   <span data-ttu-id="79659-121">Псевдоним столбца, определенный в предложении SELECT, упоминается в другом предложении, например WHERE или GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="79659-121">A column alias, defined in the SELECT clause, is referenced in another clause such as a WHERE or GROUP BY clause.</span></span> <span data-ttu-id="79659-122">Например, следующий запрос определяет псевдоним столбца `Year` в предложении SELECT и упоминает его в предложении GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="79659-122">For example, the following query defines the column alias `Year` in the SELECT clause and refers to it in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year, SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY Year;  
    ```  
  
     <span data-ttu-id="79659-123">Порядок логической обработки предложений запросов вызывает возвращение ошибки 207.</span><span class="sxs-lookup"><span data-stu-id="79659-123">Due to the order in which query clauses are logically processed, the example returns error 207.</span></span> <span data-ttu-id="79659-124">Далее приводится порядок обработки.</span><span class="sxs-lookup"><span data-stu-id="79659-124">The processing order is as follows:</span></span>  
  
    1.  <span data-ttu-id="79659-125">FROM</span><span class="sxs-lookup"><span data-stu-id="79659-125">FROM</span></span>  
  
    2.  <span data-ttu-id="79659-126">ON</span><span class="sxs-lookup"><span data-stu-id="79659-126">ON</span></span>  
  
    3.  <span data-ttu-id="79659-127">JOIN</span><span class="sxs-lookup"><span data-stu-id="79659-127">JOIN</span></span>  
  
    4.  <span data-ttu-id="79659-128">WHERE</span><span class="sxs-lookup"><span data-stu-id="79659-128">WHERE</span></span>  
  
    5.  <span data-ttu-id="79659-129">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="79659-129">GROUP BY</span></span>  
  
    6.  <span data-ttu-id="79659-130">WITH CUBE или WITH ROLLUP</span><span class="sxs-lookup"><span data-stu-id="79659-130">WITH CUBE or WITH ROLLUP</span></span>  
  
    7.  <span data-ttu-id="79659-131">HAVING</span><span class="sxs-lookup"><span data-stu-id="79659-131">HAVING</span></span>  
  
    8.  <span data-ttu-id="79659-132">SELECT</span><span class="sxs-lookup"><span data-stu-id="79659-132">SELECT</span></span>  
  
    9. <span data-ttu-id="79659-133">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="79659-133">DISTINCT</span></span>  
  
    10. <span data-ttu-id="79659-134">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="79659-134">ORDER BY</span></span>  
  
    11. <span data-ttu-id="79659-135">В начало</span><span class="sxs-lookup"><span data-stu-id="79659-135">TOP</span></span>  
  
     <span data-ttu-id="79659-136">Поскольку псевдоним столбца не определяется до обработки предложения SELECT, псевдоним неизвестен при обработке предложения GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="79659-136">Because a column alias is not defined until the SELECT clause is processed, the alias name is unknown when the GROUP BY clause is processed.</span></span>  
  
-   <span data-ttu-id="79659-137">Инструкция MERGE выдает эту ошибку, когда исходная таблица в предложении WHEN NOT MATCHED BY SOURCE не возвращает строк, а предложение *<merge_matched>* ссылается на столбцы в исходной таблице.</span><span class="sxs-lookup"><span data-stu-id="79659-137">The MERGE statement raises this error when the *<merge_matched>* clause references columns in the source table but no rows are returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="79659-138">Данная ошибка возникает из-за того, что невозможно обратиться к столбцам в исходной таблице, если запрос не возвратил строк.</span><span class="sxs-lookup"><span data-stu-id="79659-138">The error occurs because the columns in the source table cannot be accessed when no rows are returned to the query.</span></span> <span data-ttu-id="79659-139">Например, предложение `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` может стать причиной ошибки инструкции из-за недоступности столбца `Col1` в исходной таблице.</span><span class="sxs-lookup"><span data-stu-id="79659-139">For example, the clause `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` may cause the statement to fail if `Col1` in the source table is inaccessible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79659-140">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="79659-140">User Action</span></span>  
 <span data-ttu-id="79659-141">Проверьте следующую информацию и исправьте инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="79659-141">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="79659-142">Наличие имени столбца в таблице и правильность его указания.</span><span class="sxs-lookup"><span data-stu-id="79659-142">The column name exists in the table and is spelled correctly.</span></span> <span data-ttu-id="79659-143">В следующем примере запрос к представлению каталога **sys.columns** возвращает все имена столбцов для этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="79659-143">The following example queries the **sys.columns** catalog view to return all column names for a given table.</span></span>  
  
    ```  
    SELECT name FROM sys.columns WHERE object_id = OBJECT_ID('schema_name.table_name');  
    ```  
  
-   <span data-ttu-id="79659-144">Учет регистра в параметрах сортировки базы данных.</span><span class="sxs-lookup"><span data-stu-id="79659-144">The case sensitivity of the database collation.</span></span> <span data-ttu-id="79659-145">Следующая инструкция возвращает параметры сортировки для указанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="79659-145">The following statement returns the collation of the specified database.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="79659-146">Аббревиатура CS в имени параметров сортировки означает, что учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="79659-146">The abbreviation CS in the collation name indicates the collation is case-sensitive.</span></span> <span data-ttu-id="79659-147">Например, Latin1_General_CS_AS определяет параметры сортировки с учетом диакритических знаков и с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="79659-147">For example, Latin1_General_CS_AS is a case-sensitive and accent-sensitive collation.</span></span> <span data-ttu-id="79659-148">Измените имя столбца, чтобы оно совпадало с тем именем столбца, которое было определено в таблице, вплоть до регистра.</span><span class="sxs-lookup"><span data-stu-id="79659-148">Modify the column name to match the case of the column name as it is defined in the table.</span></span>  
  
-   <span data-ttu-id="79659-149">Неправильное упоминание псевдонима столбца.</span><span class="sxs-lookup"><span data-stu-id="79659-149">A column alias is referenced incorrectly.</span></span> <span data-ttu-id="79659-150">Измените инструкцию, повторив выражение, определяющее псевдоним, в соответствующем предложении или использовав производную таблицу.</span><span class="sxs-lookup"><span data-stu-id="79659-150">Modify the statement by repeating the expression that defines the alias in the appropriate clause or by using a derived table.</span></span> <span data-ttu-id="79659-151">В следующем примере в предложении GROUP BY повторяются выражения, определяющие псевдоним `Year`.</span><span class="sxs-lookup"><span data-stu-id="79659-151">The following example repeats the expressions that define the `Year` alias in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year ,SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY DATEPART(yyyy,OrderDate);  
    ```  
  
     <span data-ttu-id="79659-152">В следующем примере производная таблица используется для того, чтобы сделать псевдоним доступным для других предложений в запросе.</span><span class="sxs-lookup"><span data-stu-id="79659-152">The following example uses a derived table to make the alias name available to other clauses in the query.</span></span> <span data-ttu-id="79659-153">Следует заметить, что псевдоним `Year` определяется в предложении FROM, которое обрабатывается в первую очередь, что делает псевдоним доступным для использования в других предложениях запроса.</span><span class="sxs-lookup"><span data-stu-id="79659-153">Notice that the alias `Year` is defined in the FROM clause, which is processed first, and so makes the alias available for use in other clauses in the query.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT d.Year, SUM(TotalDue) AS Total  
    FROM (SELECT DATEPART(yyyy,OrderDate) AS Year, TotalDue  
          FROM Sales.SalesOrderHeader)AS d  
    GROUP BY Year;  
    ```  
  
-   <span data-ttu-id="79659-154">В предложении WHEN NOT MATCHED BY SOURCE инструкции MERGE упоминается значение к которому может осуществляться доступ.</span><span class="sxs-lookup"><span data-stu-id="79659-154">The WHEN NOT MATCHED BY SOURCE clause in the MERGE statement refers to a value that can be accessed.</span></span> <span data-ttu-id="79659-155">Измените инструкцию MERGE, чтобы по крайней мере одна строка была возвращена исходной таблицей в предложении WHEN NOT MATCHED BY SOURCE.</span><span class="sxs-lookup"><span data-stu-id="79659-155">Modify the MERGE statement so that at least one row is returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="79659-156">Например, может потребоваться добавить или изменить условие поиска, указанное для предложения.</span><span class="sxs-lookup"><span data-stu-id="79659-156">For example, you might need to add or revise the search condition specified for the clause.</span></span> <span data-ttu-id="79659-157">В качестве альтернативы можно изменить предложение, чтобы указать значение, не ссылающееся на исходную таблицу.</span><span class="sxs-lookup"><span data-stu-id="79659-157">Alternatively, you can modify the clause to specify a value that does not reference the source table.</span></span> <span data-ttu-id="79659-158">Например, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span><span class="sxs-lookup"><span data-stu-id="79659-158">For example, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79659-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="79659-159">See Also</span></span>  
 <span data-ttu-id="79659-160">[MERGE (Transact-SQL)](/sql/t-sql/statements/merge-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="79659-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span></span>  
 <span data-ttu-id="79659-161">[FROM (Transact-SQL)](/sql/t-sql/queries/from-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="79659-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span></span>  
 <span data-ttu-id="79659-162">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="79659-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="79659-163">UPDATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="79659-163">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
