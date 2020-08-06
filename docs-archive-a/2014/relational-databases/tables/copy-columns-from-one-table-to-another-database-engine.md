---
title: Копирование столбцов из одной таблицы в другую (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying columns
- columns [SQL Server], copying
ms.assetid: 5f5e70dc-69f9-44b8-bc48-b5d51ac20d77
author: stevestein
ms.author: sstein
ms.openlocfilehash: 37b98bf0910cbbb4c2a1d7fe01f11d52703ec88c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669364"
---
# <a name="copy-columns-from-one-table-to-another-database-engine"></a><span data-ttu-id="c8f6e-102">Копирование столбцов из одной таблицы в другую (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="c8f6e-102">Copy Columns from One Table to Another (Database Engine)</span></span>
  <span data-ttu-id="c8f6e-103">В этом разделе описывается копирование столбцов из одной таблицы в другую, когда копируется либо только определение столбца, либо определение и данные из [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8f6e-103">This topic describes how to copy columns from one table to another, copying either just the column definition, or the definition and data in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c8f6e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c8f6e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c8f6e-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c8f6e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c8f6e-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c8f6e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c8f6e-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c8f6e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c8f6e-108">**Копирование столбцов с помощью**</span><span class="sxs-lookup"><span data-stu-id="c8f6e-108">**To coy columns, using:**</span></span>  
  
     [<span data-ttu-id="c8f6e-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8f6e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c8f6e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8f6e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c8f6e-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c8f6e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c8f6e-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c8f6e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c8f6e-113">При копировании из одной базы данных в другую столбца, имеющего псевдоним типа данных, исходный тип данных в целевой базе данных может оказаться недоступным.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-113">When you copy a column that has an alias data type from one database to another, the alias data type may not be available in the destination database.</span></span> <span data-ttu-id="c8f6e-114">В этом случае столбцу будет назначен ближайший подходящий базовый тип данных, доступный в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-114">In such a case, the column will be assigned the nearest matching base data type available in that database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c8f6e-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="c8f6e-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c8f6e-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="c8f6e-116">Permissions</span></span>  
 <span data-ttu-id="c8f6e-117">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c8f6e-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8f6e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="c8f6e-119">Копирование определения столбца из одной таблицы в другую</span><span class="sxs-lookup"><span data-stu-id="c8f6e-119">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="c8f6e-120">Щелкнув правой кнопкой мыши, откройте таблицу со столбцами, предназначенными к копированию, и таблицу, в которую необходимо выполнить копирование, затем нажмите кнопку **Разработка**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-120">Open the table with columns you want to copy and the one you want to copy into by right-clicking the tables, and then clicking **Design**.</span></span>  
  
2.  <span data-ttu-id="c8f6e-121">Выберите вкладку исходной таблицы и выделите нужные столбцы.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-121">Click the tab for the table with the columns you want to copy and select those columns.</span></span>  
  
3.  <span data-ttu-id="c8f6e-122">В меню **Правка** выберите **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-122">From the **Edit** menu, click **Copy**.</span></span>  
  
4.  <span data-ttu-id="c8f6e-123">Выберите вкладку таблицы, в которую требуется скопировать столбцы.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-123">Click the tab for the table into which you want to copy the columns.</span></span>  
  
5.  <span data-ttu-id="c8f6e-124">Выделите столбец, после которого нужно поместить вставляемые столбцы, и в меню **Правка** выберите **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-124">Select the column you want to follow the inserted columns and, from the **Edit** menu, click **Paste**.</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="c8f6e-125">Копирование данных из одной таблицы в другую</span><span class="sxs-lookup"><span data-stu-id="c8f6e-125">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="c8f6e-126">Следуйте приведенным выше инструкциям для копирования определения столбцов.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-126">Follow the directions for copying column definitions above.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8f6e-127">Прежде чем скопировать данные из одной таблицы в другую, убедитесь, что типы данных целевых столбцов совместимы с типами данных исходных.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-127">Before you begin to copy data from one table to another, make sure that the data types in the destination columns are compatible with the data types of the source columns</span></span>  
  
2.  <span data-ttu-id="c8f6e-128">В обозревателе объектов щелкните правой кнопкой мыши папку **Представления** и выберите в контекстном меню пункт **Создать представление**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-128">In Object Explorer, right-click the **Views** node, and then click **New View**.</span></span>  
  
3.  <span data-ttu-id="c8f6e-129">В меню **Конструктор запросов** выберите пункт **Тип изменения**, а затем пункт **Вставить результаты**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-129">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
4.  <span data-ttu-id="c8f6e-130">В диалоговом окне **Выберите целевую таблицу для инструкции Insert Results** выберите таблицу, куда необходимо скопировать данные, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-130">In the **Choose Target Table for Insert Results** dialog box, select the table into which you want to copy the data, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c8f6e-131">При копировании строк внутри таблицы в качестве целевой таблицы нужно указать исходную.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-131">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8f6e-132">**Конструктор запросов** не может определить заранее, какие таблицы и представления доступны для обновления.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-132">**Query Designer** cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="c8f6e-133">Поэтому в диалоговом окне **Выберите целевую таблицу для инструкции Insert Results** приведен список всех таблиц и представлений, доступных этому подключению к данным, даже тех, копирование строк в которые будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-133">Therefore, the list of tables in the **Choose Target Table for Insert Results** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
5.  <span data-ttu-id="c8f6e-134">Щелкните правой кнопкой мыши панель диаграммы и в контекстном меню выберите пункт **Добавить таблицу в диаграмму**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-134">Right-click in the body of the diagram pane and, from the shortcut menu, click **Add Table to Diagram**.</span></span>  
  
6.  <span data-ttu-id="c8f6e-135">В диалоговом окне **Добавить таблицу** выберите таблицы, из которых требуется скопировать данные, нажмите сначала кнопку **Добавить**, а затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-135">In the **Add Table** dialog box, select each table from which you want to copy data, click **Add**, and then click **Close**.</span></span>  
  
     <span data-ttu-id="c8f6e-136">Таблицы появляются на панели диаграммы в сокращенной форме.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-136">The tables, in an abbreviated form, appear in the diagram pane.</span></span>  
  
7.  <span data-ttu-id="c8f6e-137">В таблицах отметьте столбцы, данные из которых необходимо скопировать.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-137">In the abbreviated tables, check the boxes for any columns from which you want to copy data.</span></span>  
  
8.  <span data-ttu-id="c8f6e-138">На панели критериев в столбце **Присоединение** для каждого целевого столбца выберите столбец, из которого должны быть скопированы данные.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-138">In the criteria pane, in the **Append** column, for each target column choose a column from which you want to copy data.</span></span>  
  
9. <span data-ttu-id="c8f6e-139">Укажите строки, которые необходимо скопировать, заданием условий поиска на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-139">Specify the rows to copy by entering search conditions in the criteria pane.</span></span> <span data-ttu-id="c8f6e-140">Подробные сведения см. в разделе [Указание условий поиска (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c8f6e-140">For details, see [Specify Search Conditions &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="c8f6e-141">Если условия поиска не заданы, в целевую таблицу будут скопированы все строки исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-141">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
10. <span data-ttu-id="c8f6e-142">Если необходимо скопировать сводные данные, укажите параметры **Group By** .</span><span class="sxs-lookup"><span data-stu-id="c8f6e-142">If you want to copy summary information, specify **Group By** options.</span></span> <span data-ttu-id="c8f6e-143">Подробные сведения см. в разделе [Получение суммарных или статистических значений для всех строк в таблице (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c8f6e-143">For details, see [Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span></span>  
  
11. <span data-ttu-id="c8f6e-144">Для запуска запроса нажмите кнопку **Выполнить SQL** .</span><span class="sxs-lookup"><span data-stu-id="c8f6e-144">Click the **Execute SQL button** to run the query.</span></span>  
  
     <span data-ttu-id="c8f6e-145">При выполнении запроса по вставке результатов результаты не отображаются на панели [Результаты](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c8f6e-145">When you execute an insert results query, no results are reported in the [Results Pane](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="c8f6e-146">Вместо этого появляется сообщение о количестве скопированных строк.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-146">Instead, a message appears indicating how many rows were copied.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c8f6e-147">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8f6e-147">Using Transact-SQL</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="c8f6e-148">Копирование определения столбца из одной таблицы в другую</span><span class="sxs-lookup"><span data-stu-id="c8f6e-148">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="c8f6e-149">Нельзя копировать отдельные столбцы из одной таблицы в другую (существующую) с использованием инструкций Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-149">You cannot copy individual columns from one table to another existing table by using Transact-SQL statements.</span></span> <span data-ttu-id="c8f6e-150">Однако можно создать новую таблицу в файловой группе по умолчанию и вставить в нее результирующие строки из запроса с помощью инструкции SELECT INTO.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-150">However, you can create a new table in the default filegroup and inserts the resulting rows from the query into it by using SELECT INTO.</span></span> <span data-ttu-id="c8f6e-151">Дополнительные сведения см. в разделе [Предложение INTO (Transact-SQL)](/sql/t-sql/queries/select-into-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8f6e-151">For more information, see [INTO Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="c8f6e-152">Копирование данных из одной таблицы в другую</span><span class="sxs-lookup"><span data-stu-id="c8f6e-152">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="c8f6e-153">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8f6e-153">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c8f6e-154">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-154">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c8f6e-155">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c8f6e-155">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.EmployeeSales  
    ( BusinessEntityID   varchar(11) NOT NULL,  
      SalesYTD money NOT NULL  
    );  
    GO  
    INSERT INTO dbo.EmployeeSales  
        SELECT BusinessEntityID, SalesYTD   
        FROM Sales.SalesPerson;  
    GO  
    ```  
  
  
