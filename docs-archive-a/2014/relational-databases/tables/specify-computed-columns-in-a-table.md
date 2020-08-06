---
title: Указание вычисляемых столбцов в таблице | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, define
ms.assetid: 731a4576-09c1-47f0-a8f6-edd0b55679f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22e4df8d67b61e50383ffd8e33f982990ff3f2ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666974"
---
# <a name="specify-computed-columns-in-a-table"></a><span data-ttu-id="8a175-102">Указание вычисляемых столбцов в таблице</span><span class="sxs-lookup"><span data-stu-id="8a175-102">Specify Computed Columns in a Table</span></span>
  <span data-ttu-id="8a175-103">Вычисляемый столбец представляет собой виртуальный столбец, физически не хранящийся в таблице, если для него не установлен признак PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="8a175-103">A computed column is a virtual column that is not physically stored in the table, unless the column is marked PERSISTED.</span></span> <span data-ttu-id="8a175-104">В выражении вычисляемого столбца для вычисления значения могут использоваться данные из других столбцов.</span><span class="sxs-lookup"><span data-stu-id="8a175-104">A computed column expression can use data from other columns to calculate a value for the column to which it belongs.</span></span> <span data-ttu-id="8a175-105">Вы можете задать выражение для вычисляемого столбца в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с использованием [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a175-105">You can specify an expression for a computed column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8a175-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8a175-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8a175-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8a175-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8a175-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8a175-108">Limitations and Restrictions</span></span>](#Limitations)  
  
     [<span data-ttu-id="8a175-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8a175-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8a175-110">**Задание вычисляемого столбца с использованием:**</span><span class="sxs-lookup"><span data-stu-id="8a175-110">**To specify a computed column, using:**</span></span>  
  
     [<span data-ttu-id="8a175-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8a175-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8a175-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8a175-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8a175-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8a175-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="8a175-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8a175-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8a175-115">Вычисляемый столбец нельзя использовать ни в качестве определения ограничения DEFAULT или FOREIGN KEY, ни вместе с определением ограничения NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="8a175-115">A computed column cannot be used as a DEFAULT or FOREIGN KEY constraint definition or with a NOT NULL constraint definition.</span></span> <span data-ttu-id="8a175-116">Однако если вычисляемый столбец определен детерминированным выражением и тип данных результата допускается для индексных столбцов, то вычисляемый столбец может быть использован как ключевой столбец в индексе или как часть ограничений PRIMARY KEY или UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="8a175-116">However, if the computed column value is defined by a deterministic expression and the data type of the result is allowed in index columns, a computed column can be used as a key column in an index or as part of any PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="8a175-117">Например, если таблица содержит столбцы a и b со значениями целого типа, то вычисляемый столбец a + b может быть индексирован, но вычисляемый столбец a+DATEPART(dd, GETDATE()) не может быть индексирован, так как значение может меняться при каждом следующем вычислении.</span><span class="sxs-lookup"><span data-stu-id="8a175-117">For example, if the table has integer columns a and b, the computed column a + b may be indexed, but computed column a + DATEPART(dd, GETDATE()) cannot be indexed, because the value might change in subsequent invocations.</span></span>  
  
-   <span data-ttu-id="8a175-118">Вычисляемый столбец не может быть целевым столбцом инструкций INSERT или UPDATE.</span><span class="sxs-lookup"><span data-stu-id="8a175-118">A computed column cannot be the target of an INSERT or UPDATE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8a175-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="8a175-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8a175-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="8a175-120">Permissions</span></span>  
 <span data-ttu-id="8a175-121">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="8a175-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8a175-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8a175-122">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-add-a-new-computed-column"></a><a name="NewColumn"></a> <span data-ttu-id="8a175-123">Добавление нового вычисляемого столбца</span><span class="sxs-lookup"><span data-stu-id="8a175-123">To add a new computed column</span></span>  
  
1.  <span data-ttu-id="8a175-124">В **обозревателе объектов**разверните таблицу, в которую нужно добавить новый вычисляемый столбец.</span><span class="sxs-lookup"><span data-stu-id="8a175-124">In **Object Explorer**, expand the table for which you want to add the new computed column.</span></span> <span data-ttu-id="8a175-125">Щелкните правой кнопкой мыши **Столбцы** и выберите **Создать столбец**.</span><span class="sxs-lookup"><span data-stu-id="8a175-125">Right-click **Columns** and select **New Column**.</span></span>  
  
2.  <span data-ttu-id="8a175-126">Введите имя столбца и выберите тип данных по умолчанию (`nchar` (10)).</span><span class="sxs-lookup"><span data-stu-id="8a175-126">Enter the column name and accept the default data type (`nchar`(10)).</span></span> <span data-ttu-id="8a175-127">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] определяет тип данных вычисляемого столбца путем применения правил очередности типов данных к выражениям, указанным в формуле.</span><span class="sxs-lookup"><span data-stu-id="8a175-127">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines the data type of the computed column by applying the rules of data type precedence to the expressions specified in the formula.</span></span> <span data-ttu-id="8a175-128">Например, если формула ссылается на столбец типа `money` и столбец типа `int`, то вычисляемый столбец имеет тип `money`, поскольку этот тип данных имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="8a175-128">For example, if the formula references a column of type `money` and a column of type `int`, the computed column will be of type `money` because that data type has the higher precedence.</span></span> <span data-ttu-id="8a175-129">Дополнительные сведения см. в разделе [Приоритет типов данных (Transact-SQL)](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a175-129">For more information, see [Data Type Precedence &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span></span>  
  
3.  <span data-ttu-id="8a175-130">На вкладке **Свойства столбца** раскройте свойство **Спецификация вычисляемого столбца** .</span><span class="sxs-lookup"><span data-stu-id="8a175-130">In the **Column Properties** tab, expand the **Computed Column Specification** property.</span></span>  
  
4.  <span data-ttu-id="8a175-131">В дочернем свойстве **(Формула)** введите выражение для этого столбца в ячейку сетки справа.</span><span class="sxs-lookup"><span data-stu-id="8a175-131">In the **(Formula)** child property, enter the expression for this column in the grid cell to the right.</span></span> <span data-ttu-id="8a175-132">Например, в столбце `SalesTotal` можно ввести формулу `SubTotal+TaxAmt+Freight`, чтобы добавить значения в этих столбцах для каждой строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="8a175-132">For example, in a `SalesTotal` column, the formula you enter might be `SubTotal+TaxAmt+Freight`, which adds the value in these columns for each row in the table.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8a175-133">Если формула связывает два выражения различных типов данных, то по правилам приоритета типов данных определяется, какой тип данных имеет меньший приоритет и будет преобразован в тип данных с большим приоритетом.</span><span class="sxs-lookup"><span data-stu-id="8a175-133">When a formula combines two expressions of different data types, the rules for data type precedence specify that the data type with the lower precedence is converted to the data type with the higher precedence.</span></span> <span data-ttu-id="8a175-134">Если неявное преобразование не поддерживается, возвращается ошибка «`Error validating the formula for column column_name.`».</span><span class="sxs-lookup"><span data-stu-id="8a175-134">If the conversion is not a supported implicit conversion, the error "`Error validating the formula for column column_name.`" is returned.</span></span> <span data-ttu-id="8a175-135">Используйте функцию CAST или CONVERT, чтобы устранить конфликт типа данных.</span><span class="sxs-lookup"><span data-stu-id="8a175-135">Use the CAST or CONVERT function to resolve the data type conflict.</span></span> <span data-ttu-id="8a175-136">Например, если столбец типа `nvarchar` объединяется со столбцом типа `int`, то целочисленный тип необходимо преобразовать в `nvarchar`, как показано в следующей формуле: `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span><span class="sxs-lookup"><span data-stu-id="8a175-136">For example, if a column of type `nvarchar` is combined with a column of type `int`, the integer type must be converted to `nvarchar` as shown in this formula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span></span> <span data-ttu-id="8a175-137">Дополнительные сведения см. в разделе [Функции CAST и CONVERT (Transact-SQL)](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a175-137">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
5.  <span data-ttu-id="8a175-138">Выберите **Да** или **Нет** в раскрывающемся списке для дочернего свойства **Материализованный** , чтобы указать, следует ли сохранять данные.</span><span class="sxs-lookup"><span data-stu-id="8a175-138">Indicate whether the data is persisted by choosing **Yes** or **No** from the drop-down for the **Is Persisted** child property.</span></span>  
  
6.  <span data-ttu-id="8a175-139">В меню **Файл** выберите команду **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="8a175-139">On the **File** menu, click **Save**_table name_.</span></span>  
  
#### <a name="to-add-a-computed-column-definition-to-an-existing-column"></a><span data-ttu-id="8a175-140">Добавление определения вычисляемого столбца к существующему столбцу</span><span class="sxs-lookup"><span data-stu-id="8a175-140">To add a computed column definition to an existing column</span></span>  
  
1.  <span data-ttu-id="8a175-141">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу со столбцом, определение которого необходимо изменить, и разверните папку **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="8a175-141">In **Object Explorer**, right-click the table with the column for which you want to change and expand the **Columns** folder.</span></span>  
  
2.  <span data-ttu-id="8a175-142">Щелкните правой кнопкой мыши столбец, для которого необходимо задать формулу вычисляемого столбца, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8a175-142">Right-click the column for which you want to specify a computed column formula and click **Delete**.</span></span> <span data-ttu-id="8a175-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8a175-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="8a175-144">Добавьте новый столбец и укажите формулу вычисляемого столбца в соответствии с предыдущей процедурой, чтобы добавить новый вычисляемый столбец.</span><span class="sxs-lookup"><span data-stu-id="8a175-144">Add a new column and specify the computed column formula by following the previous procedure to add a new computed column.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8a175-145">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8a175-145">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-computed-column-when-creating-a-table"></a><span data-ttu-id="8a175-146">Добавление вычисляемого столбца при создании таблицы</span><span class="sxs-lookup"><span data-stu-id="8a175-146">To add a computed column when creating a table</span></span>  
  
1.  <span data-ttu-id="8a175-147">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a175-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8a175-148">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8a175-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8a175-149">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8a175-149">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="8a175-150">В этом примере создается таблица с вычисляемым столбцом, который умножает значение столбца `QtyAvailable` на значение, указанное в столбце `UnitPrice` .</span><span class="sxs-lookup"><span data-stu-id="8a175-150">The example creates a table with a computed column that multiplies the value in the `QtyAvailable` column times the value in the `UnitPrice` column.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products   
    (  
        ProductID int IDENTITY (1,1) NOT NULL  
      , QtyAvailable smallint  
      , UnitPrice money  
      , InventoryValue AS QtyAvailable * UnitPrice  
    );  
  
    -- Insert values into the table.  
    INSERT INTO dbo.Products (QtyAvailable, UnitPrice)  
    VALUES (25, 2.00), (10, 1.5);  
  
    -- Display the rows in the table.  
    SELECT ProductID, QtyAvailable, UnitPrice, InventoryValue  
    FROM dbo.Products;  
  
    ```  
  
#### <a name="to-add-a-new-computed-column-to-an-existing-table"></a><span data-ttu-id="8a175-151">Добавление нового вычисляемого столбца в существующую таблицу</span><span class="sxs-lookup"><span data-stu-id="8a175-151">To add a new computed column to an existing table</span></span>  
  
1.  <span data-ttu-id="8a175-152">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a175-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8a175-153">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8a175-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8a175-154">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8a175-154">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="8a175-155">В следующем примере в таблицу, созданную в предыдущем примере, будет добавлен новый столбец.</span><span class="sxs-lookup"><span data-stu-id="8a175-155">The following example adds a new column to the table created in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.35);  
  
    ```  
  
#### <a name="to-change-an-existing-column-to-a-computed-column"></a><span data-ttu-id="8a175-156">Замена существующего столбца на вычисляемый столбец</span><span class="sxs-lookup"><span data-stu-id="8a175-156">To change an existing column to a computed column</span></span>  
  
1.  <span data-ttu-id="8a175-157">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a175-157">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8a175-158">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8a175-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8a175-159">Чтобы заменить существующий столбец на вычисляемый столбец, нужно удалить и создать повторно вычисляемый столбец.</span><span class="sxs-lookup"><span data-stu-id="8a175-159">To change an existing column to a computed column you must drop and re-create the computed column.</span></span> <span data-ttu-id="8a175-160">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8a175-160">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="8a175-161">В следующем примере изменяется столбец, добавленный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="8a175-161">The following example modifies the column added in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products DROP COLUMN RetailValue;  
    GO  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.5);  
  
    ```  
  
     <span data-ttu-id="8a175-162">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a175-162">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
