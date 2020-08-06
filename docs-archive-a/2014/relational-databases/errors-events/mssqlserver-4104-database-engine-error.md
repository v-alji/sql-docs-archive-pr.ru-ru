---
title: MSSQLSERVER_4104 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4104 (Database Engine error)
ms.assetid: 52dc32d8-97ad-4ef0-834d-2e68f215d007
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbbc28a3e15af6fdc8fd44633ccbdfc46e49149d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666650"
---
# <a name="mssqlserver_4104"></a><span data-ttu-id="7bf0c-102">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="7bf0c-102">MSSQLSERVER_4104</span></span>
    
## <a name="details"></a><span data-ttu-id="7bf0c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7bf0c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7bf0c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7bf0c-104">Product Name</span></span>|<span data-ttu-id="7bf0c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7bf0c-105">SQL Server</span></span>|  
|<span data-ttu-id="7bf0c-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7bf0c-106">Event ID</span></span>|<span data-ttu-id="7bf0c-107">4104</span><span class="sxs-lookup"><span data-stu-id="7bf0c-107">4104</span></span>|  
|<span data-ttu-id="7bf0c-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7bf0c-108">Event Source</span></span>|<span data-ttu-id="7bf0c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7bf0c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7bf0c-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7bf0c-110">Component</span></span>|<span data-ttu-id="7bf0c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7bf0c-111">SQLEngine</span></span>|  
|<span data-ttu-id="7bf0c-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7bf0c-112">Symbolic Name</span></span>|<span data-ttu-id="7bf0c-113">ALG_MULTI_ID_BAD</span><span class="sxs-lookup"><span data-stu-id="7bf0c-113">ALG_MULTI_ID_BAD</span></span>|  
|<span data-ttu-id="7bf0c-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7bf0c-114">Message Text</span></span>|<span data-ttu-id="7bf0c-115">Не удалось выполнить привязку составного идентификатора "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="7bf0c-115">The multi-part identifier "%.\*ls" could not be bound.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7bf0c-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7bf0c-116">Explanation</span></span>  
 <span data-ttu-id="7bf0c-117">Имя сущности в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяется ее *идентификатором*.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-117">The name of an entity in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is referred to as its *identifier*.</span></span> <span data-ttu-id="7bf0c-118">Идентификаторы используются, например, всегда при ссылках на сущности путем указания в запросе имен столбца и таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-118">You use identifiers whenever you reference entities, for example, by specifying column and table names in a query.</span></span> <span data-ttu-id="7bf0c-119">Составной идентификатор содержит один или несколько квалификаторов, являющихся префиксом для идентификатора.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-119">A multi-part identifier contains one or more qualifiers as a prefix for the identifier.</span></span> <span data-ttu-id="7bf0c-120">Например, перед идентификатором таблицы можно указывать такие квалификаторы, как имя базы данных и имя схемы, в которых содержится таблица, а перед идентификатором столбца могут находиться такие квалификаторы, как имя таблицы или псевдоним таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-120">For example, a table identifier may be prefixed with qualifiers such as the database name and schema name in which the table is contained, or a column identifier may be prefixed with qualifiers such as a table name or table alias.</span></span>  
  
 <span data-ttu-id="7bf0c-121">Ошибка 4104 указывает, что заданный составной идентификатор не может быть сопоставлен существующей сущности.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-121">Error 4104 indicates that the specified multi-part identifier could not be mapped to an existing entity.</span></span> <span data-ttu-id="7bf0c-122">Эта ошибка может быть возвращена при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-122">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="7bf0c-123">Квалификатор, заданный в качестве префикса для имени столбца, не совпадает ни с одним именем таблицы или псевдонима, используемым в запросе.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-123">The qualifier supplied as a prefix for a column name does not correspond to any table or alias name used in the query.</span></span>  
  
     <span data-ttu-id="7bf0c-124">Например, в следующей инструкции псевдоним таблицы (`Dept`) используется как префикс столбца, но в предложении FROM нет ссылки на псевдоним таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-124">For example, the following statement uses a table alias (`Dept`) as a column prefix, but the table alias is not referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department;  
    ```  
  
     <span data-ttu-id="7bf0c-125">В следующих инструкциях составной идентификатор столбца `TableB.KeyCol` задан в предложении WHERE как часть условия JOIN между двумя таблицами, но в запросе нет явной ссылки на таблицу `TableB`.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-125">In the following statements, a multi-part column identifier `TableB.KeyCol` is specified in the WHERE clause as part of a JOIN condition between two tables, however, `TableB` is not explicitly referenced in the query.</span></span>  
  
    ```  
    DELETE FROM TableA WHERE TableA.KeyCol = TableB.KeyCol;  
    ```  
  
    ```  
    SELECT 'X' FROM TableA WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="7bf0c-126">Имя псевдонима для таблицы указывается в предложении FROM, но квалификатор, указанный для столбца, является именем таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-126">An alias name for the table is supplied in the FROM clause, but the qualifier supplied for a column is the table name.</span></span> <span data-ttu-id="7bf0c-127">Например, в следующей инструкции имя таблицы (`Department`) используется как префикс столбца; но у таблицы есть псевдоним (`Dept`), ссылка на который содержится в предложении FROM.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-127">For example, the following statement uses the table name `Department` as the column prefix; however, the table has an alias (`Dept`) referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department AS Dept;  
    ```  
  
     <span data-ttu-id="7bf0c-128">Когда используется псевдоним, имя таблицы не может использоваться в других частях инструкции.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-128">When an alias is used, the table name cannot be used elsewhere in the statement.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7bf0c-129">не может определить, указывает ли составной идентификатор на столбец, предваряемый таблицей, или на определяемый пользователем тип данных CLR, предваряемый столбцом.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-129">is unable to determine if the multi-part identifier refers to a column prefixed by a table or to a property of a CLR user-defined data type (UDT) prefixed by a column.</span></span> <span data-ttu-id="7bf0c-130">Это происходит потому, что ссылка на свойства столбцов определяемых пользователем типов задается с использованием точки (.) в качестве разделителя между именем столбца и именем свойства, так же как имя столбца предваряется именем таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-130">This happens because properties of UDT columns are referenced by using the period separator (.) between the column name and the property name in the same way that a column name is prefixed with a table name.</span></span> <span data-ttu-id="7bf0c-131">В следующем примере создается две таблицы, `a` и `b`.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-131">The following example creates two tables, `a` and `b`.</span></span> <span data-ttu-id="7bf0c-132">Таблица `b` содержит столбец `a`, в котором в качестве типа данных используется определяемый пользователем тип данных CLR `dbo.myudt2`.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-132">Table `b` contains column `a`, which uses a CLR UDT `dbo.myudt2` as its data type.</span></span> <span data-ttu-id="7bf0c-133">Инструкция SELECT содержит составной идентификатор `a.c2`.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-133">The SELECT statement contains a multi-part identifier `a.c2`.</span></span>  
  
    ```  
    CREATE TABLE a (c2 int);   
    GO  
    ```  
  
    ```  
    CREATE TABLE b (a dbo.myudt2);   
    GO  
    ```  
  
    ```  
    SELECT a.c2 FROM a, b;   
    ```  
  
     <span data-ttu-id="7bf0c-134">Если определяемый пользователем тип данных `myudt2` не имеет свойства с именем `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не сможет определить, указывает ли идентификатор `a.c2` на столбец `c2` в таблице `a` или на столбец `a`, свойство `c2` в таблице `b`.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-134">Assuming that the UDT `myudt2` does not have a property named `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot determine whether identifier `a.c2`refers to column `c2` in table `a` or to the column `a`, property `c2` in table `b`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7bf0c-135">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7bf0c-135">User Action</span></span>  
  
-   <span data-ttu-id="7bf0c-136">Префиксы столбцов должны быть согласованы с именами таблиц или псевдонимами, указанными в предложении FROM запроса.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-136">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="7bf0c-137">Если псевдоним определен для имени таблицы в предложении FROM, то псевдоним можно использовать только как квалификатор для столбцов, связанных с этой таблицей.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-137">If an alias is defined for a table name in the FROM clause, you can only use the alias as a qualifier for columns associated with that table.</span></span>  
  
     <span data-ttu-id="7bf0c-138">Приведенные выше инструкции, которые содержат ссылки на таблицу `HumanResources.Department`, можно исправить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bf0c-138">The statements above that reference the `HumanResources.Department` table can be corrected as follows:</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department AS Dept;  
    GO  
    ```  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department;  
    GO  
    ```  
  
-   <span data-ttu-id="7bf0c-139">Проверьте, что все таблицы указаны в запросе и условия JOIN между таблицами заданы верно.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-139">Ensure that all tables are specified in the query and that the JOIN conditions between tables are specified correctly.</span></span> <span data-ttu-id="7bf0c-140">Инструкция DELETE выше может быть исправлена следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bf0c-140">The DELETE statement above can be corrected as follows:</span></span>  
  
    ```  
    DELETE FROM dbo.TableA  
    WHERE TableA.KeyCol = (SELECT TableB.KeyCol   
                            FROM TableB   
                            WHERE TableA.KeyCol = TableB.KeyCol);  
    GO  
    ```  
  
     <span data-ttu-id="7bf0c-141">Приведенная выше инструкция SELECT для таблицы `TableA` может быть исправлена следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bf0c-141">The SELECT statement above for `TableA` can be corrected as follows:</span></span>  
  
    ```  
    SELECT 'X' FROM TableA, TableB WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
     <span data-ttu-id="7bf0c-142">или диспетчер конфигурации служб</span><span class="sxs-lookup"><span data-stu-id="7bf0c-142">or</span></span>  
  
    ```  
    SELECT 'X' FROM TableA INNER JOIN TableB ON TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="7bf0c-143">Используйте для идентификаторов уникальные, понятные имена.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-143">Use unique, clearly defined names for identifiers.</span></span> <span data-ttu-id="7bf0c-144">В результате будет проще читать и исправлять исходный текст, и снижается опасность неоднозначных ссылок на несколько сущностей.</span><span class="sxs-lookup"><span data-stu-id="7bf0c-144">Doing so makes your code easier to read and maintain, and it also minimizes the risk of ambiguous references to multiple entities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf0c-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="7bf0c-145">See Also</span></span>  
 <span data-ttu-id="7bf0c-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="7bf0c-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span></span>  
 [<span data-ttu-id="7bf0c-147">Идентификаторы баз данных</span><span class="sxs-lookup"><span data-stu-id="7bf0c-147">Database Identifiers</span></span>](../databases/database-identifiers.md)  
  
  
