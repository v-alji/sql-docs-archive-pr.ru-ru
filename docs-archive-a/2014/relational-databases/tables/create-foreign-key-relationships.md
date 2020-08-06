---
title: Создание связей по внешнему ключу | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], creating
ms.assetid: 867a54b8-5be4-46e6-9702-49ae6dabf67c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ee0de3311eb6abffcdb71ab725d0650fe96b04c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669356"
---
# <a name="create-foreign-key-relationships"></a><span data-ttu-id="e18c4-102">Создание связей по внешнему ключу</span><span class="sxs-lookup"><span data-stu-id="e18c4-102">Create Foreign Key Relationships</span></span>
  <span data-ttu-id="e18c4-103">В данном разделе описывается создание связей внешнего ключа в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e18c4-103">This topic describes how to create foreign key relationships in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e18c4-104">Связь создается между двумя таблицами, чтобы связать строки одной таблицы со строками другой.</span><span class="sxs-lookup"><span data-stu-id="e18c4-104">You create a relationship between two tables when you want to associate rows of one table with rows of another.</span></span>  
  
 <span data-ttu-id="e18c4-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="e18c4-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e18c4-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e18c4-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e18c4-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e18c4-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e18c4-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e18c4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e18c4-109">**Создание связей внешнего ключа с помощью:**</span><span class="sxs-lookup"><span data-stu-id="e18c4-109">**To Create Foreign Key Relationships by using:**</span></span>  
  
     [<span data-ttu-id="e18c4-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e18c4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e18c4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e18c4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e18c4-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e18c4-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e18c4-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e18c4-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e18c4-114">Ограничение внешнего ключа не обязательно должно быть связано только с ограничением первичного ключа в другой таблице. Кроме того, это ограничение может быть определено для ссылки на столбцы с ограничением UNIQUE в другой таблице.</span><span class="sxs-lookup"><span data-stu-id="e18c4-114">A foreign key constraint does not have to be linked only to a primary key constraint in another table; it can also be defined to reference the columns of a UNIQUE constraint in another table.</span></span>  
  
-   <span data-ttu-id="e18c4-115">Если столбцу, имеющему ограничение внешнего ключа, задается значение, отличное от NULL, такое же значение должно существовать и в указываемом столбце; в противном случае будет возвращено сообщение о нарушении внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="e18c4-115">When a value other than NULL is entered into the column of a FOREIGN KEY constraint, the value must exist in the referenced column; otherwise, a foreign key violation error message is returned.</span></span> <span data-ttu-id="e18c4-116">Для обеспечения проверки всех значений сложного ограничения внешнего ключа задайте параметр NOT NULL для всех столбцов, участвующих в индексе.</span><span class="sxs-lookup"><span data-stu-id="e18c4-116">To make sure that all values of a composite foreign key constraint are verified, specify NOT NULL on all the participating columns.</span></span>  
  
-   <span data-ttu-id="e18c4-117">Ограничения FOREIGN KEY могут ссылаться только на таблицы в пределах той же базы данных на том же сервере.</span><span class="sxs-lookup"><span data-stu-id="e18c4-117">FOREIGN KEY constraints can reference only tables within the same database on the same server.</span></span> <span data-ttu-id="e18c4-118">Межбазовую ссылочную целостность необходимо реализовать посредством триггеров.</span><span class="sxs-lookup"><span data-stu-id="e18c4-118">Cross-database referential integrity must be implemented through triggers.</span></span> <span data-ttu-id="e18c4-119">Дополнительные сведения см. в разделе [CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e18c4-119">For more information, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
-   <span data-ttu-id="e18c4-120">Ограничения FOREIGN KEY могут ссылаться на другие столбцы той же таблицы.</span><span class="sxs-lookup"><span data-stu-id="e18c4-120">FOREIGN KEY constraints can reference another column in the same table.</span></span> <span data-ttu-id="e18c4-121">Это называется самовызовом.</span><span class="sxs-lookup"><span data-stu-id="e18c4-121">This is referred to as a self-reference.</span></span>  
  
-   <span data-ttu-id="e18c4-122">Ограничение FOREIGN KEY, определенное на уровне столбцов, может содержать только один ссылочный столбец.</span><span class="sxs-lookup"><span data-stu-id="e18c4-122">A FOREIGN KEY constraint specified at the column level can list only one reference column.</span></span> <span data-ttu-id="e18c4-123">Этот столбец должен принадлежать к тому же типу данных, что и столбец, для которого определяется ограничение.</span><span class="sxs-lookup"><span data-stu-id="e18c4-123">This column must have the same data type as the column on which the constraint is defined.</span></span>  
  
-   <span data-ttu-id="e18c4-124">Ограничение FOREIGN KEY, определенное на уровне таблицы, должно содержать такое же число ссылочных столбцов, какое содержится в списке столбцов в ограничении.</span><span class="sxs-lookup"><span data-stu-id="e18c4-124">A FOREIGN KEY constraint specified at the table level must have the same number of reference columns as the number of columns in the constraint column list.</span></span> <span data-ttu-id="e18c4-125">Тип данных каждого ссылочного столбца должен также совпадать с типом соответствующего столбца в списке столбцов.</span><span class="sxs-lookup"><span data-stu-id="e18c4-125">The data type of each reference column must also be the same as the corresponding column in the column list.</span></span>  
  
-   <span data-ttu-id="e18c4-126">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] не имеет стандартного предела на количество ограничений FOREIGN KEY, содержащихся в таблице, ссылающейся на другие таблицы, или на количество ограничений FOREIGN KEY в других таблицах, ссылающихся на указанную таблицу.</span><span class="sxs-lookup"><span data-stu-id="e18c4-126">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not have a predefined limit on either the number of FOREIGN KEY constraints a table can contain that reference other tables, or the number of FOREIGN KEY constraints that are owned by other tables that reference a specific table.</span></span> <span data-ttu-id="e18c4-127">Тем не менее фактическое количество ограничений FOREIGN KEY, доступных для использования, ограничивается конфигурацией оборудования, базы данных и приложения.</span><span class="sxs-lookup"><span data-stu-id="e18c4-127">Nevertheless, the actual number of FOREIGN KEY constraints that can be used is limited by the hardware configuration and by the design of the database and application.</span></span> <span data-ttu-id="e18c4-128">Рекомендуется, чтобы таблица содержала не более 253 ограничений FOREIGN KEY, а также чтобы на нее ссылалось не более 253 ограничений FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="e18c4-128">We recommend that a table contain no more than 253 FOREIGN KEY constraints, and that it be referenced by no more than 253 FOREIGN KEY constraints.</span></span>  
  
-   <span data-ttu-id="e18c4-129">Ограничения FOREIGN KEY не применяются к временным таблицам.</span><span class="sxs-lookup"><span data-stu-id="e18c4-129">FOREIGN KEY constraints are not enforced on temporary tables.</span></span>  
  
-   <span data-ttu-id="e18c4-130">Если внешний ключ определен на столбце определяемого пользователем типа данных CLR, реализация этого типа должна поддерживать двоичную сортировку.</span><span class="sxs-lookup"><span data-stu-id="e18c4-130">If a foreign key is defined on a CLR user-defined type column, the implementation of the type must support binary ordering.</span></span> <span data-ttu-id="e18c4-131">Дополнительные сведения об определяемых пользователем типах данных CLR см. в разделе [Определяемые пользователем типы данных CLR](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="e18c4-131">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
-   <span data-ttu-id="e18c4-132">Столбец типа `varchar(max)` может участвовать в ограничении FOREIGN KEY только при условии, что первичный ключ, на который он ссылается, также имеет тип данных `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="e18c4-132">A column of type `varchar(max)` can participate in a FOREIGN KEY constraint only if the primary key it references is also defined as type `varchar(max)`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e18c4-133">безопасность</span><span class="sxs-lookup"><span data-stu-id="e18c4-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e18c4-134">Permissions</span><span class="sxs-lookup"><span data-stu-id="e18c4-134">Permissions</span></span>  
 <span data-ttu-id="e18c4-135">Создание новой таблицы с внешним ключом требует разрешения CREATE TABLE в базе данных и разрешения ALTER на схему, в которой создается таблица.</span><span class="sxs-lookup"><span data-stu-id="e18c4-135">Creating a new table with a foreign key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="e18c4-136">Создание внешнего ключа в существующей таблице требует разрешения ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="e18c4-136">Creating a foreign key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e18c4-137">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e18c4-137">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-foreign-key-relationship-in-table-designer"></a><span data-ttu-id="e18c4-138">Создание связи по внешнему ключу в конструкторе таблиц</span><span class="sxs-lookup"><span data-stu-id="e18c4-138">To create a foreign key relationship in Table Designer</span></span>  
  
1.  <span data-ttu-id="e18c4-139">В обозревателе объектов щелкните правой кнопкой мыши таблицу, которая будет содержать внешний ключ для связи, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="e18c4-139">In Object Explorer, right-click the table that will be on the foreign-key side of the relationship and click **Design**.</span></span>  
  
     <span data-ttu-id="e18c4-140">Таблица откроется в окне **Конструктор таблиц**.</span><span class="sxs-lookup"><span data-stu-id="e18c4-140">The table opens in **Table Designer**.</span></span>  
  
2.  <span data-ttu-id="e18c4-141">В меню **конструктора таблиц** выберите пункт **Связи**.</span><span class="sxs-lookup"><span data-stu-id="e18c4-141">From the **Table Designer** menu, click **Relationships**.</span></span>  
  
3.  <span data-ttu-id="e18c4-142">В диалоговом окне **Связи внешнего ключа** щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e18c4-142">In the **Foreign-key Relationships** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="e18c4-143">Связь появится в списке **Выбранные связи** с именем, установленным системой, в формате format FK_\<*tablename*>_\<*tablename*>, где *tablename* (имя таблицы) является именем внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="e18c4-143">The relationship appears in the **Selected Relationship** list with a system-provided name in the format FK_\<*tablename*>_\<*tablename*>, where *tablename* is the name of the foreign key table.</span></span>  
  
4.  <span data-ttu-id="e18c4-144">Щелкните нужную связь в списке **Выбранные связи** .</span><span class="sxs-lookup"><span data-stu-id="e18c4-144">Click the relationship in the **Selected Relationship** list.</span></span>  
  
5.  <span data-ttu-id="e18c4-145">Щелкните **Спецификация таблиц и столбцов** в сетке справа и нажмите кнопку с многоточием ( **...** ) справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="e18c4-145">Click **Tables and Columns Specification** in the grid to the right and click the ellipses (**...**) to the right of the property.</span></span>  
  
6.  <span data-ttu-id="e18c4-146">В диалоговом окне **Таблицы и столбы** в раскрывающемся списке **Первичный ключ** выберите таблицу, которая будет находиться на стороне первичного ключа связи.</span><span class="sxs-lookup"><span data-stu-id="e18c4-146">In the **Tables and Columns** dialog box, in the **Primary Key** drop-down list, choose the table that will be on the primary-key side of the relationship.</span></span>  
  
7.  <span data-ttu-id="e18c4-147">В сетке внизу выберите столбцы, составляющие первичный ключ таблицы.</span><span class="sxs-lookup"><span data-stu-id="e18c4-147">In the grid beneath, choose the columns contributing to the table's primary key.</span></span> <span data-ttu-id="e18c4-148">В соседней ячейке сетки слева от каждого столбца выберите соответствующий столбец внешнего ключа таблицы внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="e18c4-148">In the adjacent grid cell to the left of each column, choose the corresponding foreign-key column of the foreign-key table.</span></span>  
  
     <span data-ttu-id="e18c4-149">**Конструктор таблиц** автоматически предлагает имя для связи.</span><span class="sxs-lookup"><span data-stu-id="e18c4-149">**Table Designer** suggests a name for the relationship.</span></span> <span data-ttu-id="e18c4-150">Чтобы его изменить, отредактируйте содержимое текстового поля **Имя связи** .</span><span class="sxs-lookup"><span data-stu-id="e18c4-150">To change this name, edit the contents of the **Relationship Name** text box.</span></span>  
  
8.  <span data-ttu-id="e18c4-151">Нажмите кнопку **OК** , чтобы создать связь.</span><span class="sxs-lookup"><span data-stu-id="e18c4-151">Choose **OK** to create the relationship.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e18c4-152">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e18c4-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-foreign-key-in-a-new-table"></a><span data-ttu-id="e18c4-153">Создание внешнего ключа в новой таблице</span><span class="sxs-lookup"><span data-stu-id="e18c4-153">To create a foreign key in a new table</span></span>  
  
1.  <span data-ttu-id="e18c4-154">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e18c4-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e18c4-155">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e18c4-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e18c4-156">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e18c4-156">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e18c4-157">В этом примере создается таблица и определяется ограничение внешнего ключа для столбца `TempID` , ссылающегося на столбец `SalesReasonID` в таблице `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="e18c4-157">The example creates a table and defines a foreign key constraint on the column `TempID` that references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span> <span data-ttu-id="e18c4-158">Предложения ON DELETE CASCADE и ON UPDATE CASCADE используются для обеспечения распространения изменений, вносимых в таблицу `Sales.SalesReason` на таблицу `Sales.TempSalesReason` .</span><span class="sxs-lookup"><span data-stu-id="e18c4-158">The ON DELETE CASCADE and ON UPDATE CASCADE clauses are used to ensure that changes made to `Sales.SalesReason` table are automatically propagated to the `Sales.TempSalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Sales.TempSalesReason (TempID int NOT NULL, Name nvarchar(50),   
    CONSTRAINT PK_TempSales PRIMARY KEY NONCLUSTERED (TempID),   
    CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    );GO  
  
    ```  
  
#### <a name="to-create-a-foreign-key-in-an-existing-table"></a><span data-ttu-id="e18c4-159">Создание внешнего ключа в существующей таблице</span><span class="sxs-lookup"><span data-stu-id="e18c4-159">To create a foreign key in an existing table</span></span>  
  
1.  <span data-ttu-id="e18c4-160">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e18c4-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e18c4-161">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e18c4-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e18c4-162">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e18c4-162">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e18c4-163">В этом примере создается внешний ключ для столбца `TempID`, ссылающийся на столбец `SalesReasonID` в таблице `Sales.SalesReason`.</span><span class="sxs-lookup"><span data-stu-id="e18c4-163">The example creates a foreign key on the column `TempID` and references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Sales.TempSalesReason   
    ADD CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    ;  
    GO  
  
    ```  
  
     <span data-ttu-id="e18c4-164">Дополнительные сведения см. в разделах [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE (Transact-SQL)](/sql/t-sql/statements/create-table-transact-sql) и [table_constraint (Transact-SQL)](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e18c4-164">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
  
