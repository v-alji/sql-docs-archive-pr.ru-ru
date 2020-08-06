---
title: Указание коэффициента заполнения для индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- fill factor [SQL Server]
- page splits [SQL Server]
ms.assetid: 237a577e-b42b-4adb-90cf-aa7fb174f3ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ac54f2b22de55ed74c4635ec0f86d008c7624a42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739917"
---
# <a name="specify-fill-factor-for-an-index"></a><span data-ttu-id="4c5ab-102">Укажите коэффициент заполнения для индекса</span><span class="sxs-lookup"><span data-stu-id="4c5ab-102">Specify Fill Factor for an Index</span></span>
  <span data-ttu-id="4c5ab-103">В этом разделе приведено описание коэффициента заполнения и описываются способы указания значения коэффициента заполнения в индексе в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c5ab-103">This topic describes what fill factor is and how to specify a fill factor value on an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4c5ab-104">Коэффициент заполнения (параметр fill factor) служит для точной настройки хранения и производительности индекса.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-104">The fill-factor option is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="4c5ab-105">При создании или перестроении индекса коэффициент заполнения отображает процент заполнения пространства каждой страницы конечного уровня, что позволяет зарезервировать для будущего расширения оставшееся на каждой странице пространство как свободное.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the remainder on each page as free space for future growth.</span></span> <span data-ttu-id="4c5ab-106">Например, при указании для коэффициента заполнения значения 80 на каждой странице конечного уровня будет зарезервировано 20 процентов занимаемого ею дискового пространства. Данное дисковое пространство будет использовано для расширения индекса при добавлении в базовую таблицу новых данных.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-106">For example, specifying a fill-factor value of 80 means that 20 percent of each leaf-level page will be left empty, providing space for index expansion as data is added to the underlying table.</span></span> <span data-ttu-id="4c5ab-107">Пустое место резервируется не в конце индекса, а между строками индекса.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-107">The empty space is reserved between the index rows rather than at the end of the index.</span></span>  
  
 <span data-ttu-id="4c5ab-108">Коэффициент заполнения — это значение в процентах от 1 до 100; значение по умолчанию на сервере — 0, что означает полное заполнение страниц конечного уровня.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-108">The fill-factor value is a percentage from 1 to 100, and the server-wide default is 0 which means that the leaf-level pages are filled to capacity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c5ab-109">Значения коэффициента заполнения 0 и 100 равнозначны.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-109">Fill-factor values 0 and 100 are the same in all respects.</span></span>  
  
 <span data-ttu-id="4c5ab-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="4c5ab-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4c5ab-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="4c5ab-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4c5ab-112">Вопросы производительности</span><span class="sxs-lookup"><span data-stu-id="4c5ab-112">Performance Considerations</span></span>](#Performance)  
  
     [<span data-ttu-id="4c5ab-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="4c5ab-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4c5ab-114">**Указание коэффициента заполнения для индекса с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="4c5ab-114">**To specify a fill factor in an index, using:**</span></span>  
  
     [<span data-ttu-id="4c5ab-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c5ab-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4c5ab-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c5ab-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4c5ab-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="4c5ab-117">Before You Begin</span></span>  
  
###  <a name="performance-considerations"></a><a name="Performance"></a> <span data-ttu-id="4c5ab-118">Вопросы производительности</span><span class="sxs-lookup"><span data-stu-id="4c5ab-118">Performance Considerations</span></span>  
  
#### <a name="page-splits"></a><span data-ttu-id="4c5ab-119">Разбиения страниц</span><span class="sxs-lookup"><span data-stu-id="4c5ab-119">Page Splits</span></span>  
 <span data-ttu-id="4c5ab-120">Правильный выбор значения коэффициента заполнения уменьшает потенциальное разделение страниц, предоставляя достаточно места для увеличения индекса при добавлении данных в базовую таблицу. При добавлении новой строки на страницу, которая используется в полнотекстовом индексировании, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] перемещает примерно половину имеющихся на ней данных на новую страницу, таким образом освобождая пространство для новой строки.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-120">A correctly chosen fill-factor value can reduce potential page splits by providing enough space for index expansion as data is added to the underlying table.When a new row is added to a full index page, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] moves approximately half the rows to a new page to make room for the new row.</span></span> <span data-ttu-id="4c5ab-121">Такая реорганизация называется разбиением страницы.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-121">This reorganization is known as a page split.</span></span> <span data-ttu-id="4c5ab-122">Операция разбиения страницы позволяет выделить пространство для размещения новых записей, однако является ресурсоемкой и может выполняться длительное время.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-122">A page split makes room for new records, but can take time to perform and is a resource intensive operation.</span></span> <span data-ttu-id="4c5ab-123">Также указанная операция может вызвать фрагментацию, что приводит к увеличению количества операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-123">Also, it can cause fragmentation that causes increased I/O operations.</span></span> <span data-ttu-id="4c5ab-124">Для предотвращения слишком частого разбиения страниц необходимо перераспределить данные, перестроив индекс с помощью нового или уже существующего коэффициента заполнения.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-124">When frequent page splits occur, the index can be rebuilt by using a new or existing fill-factor value to redistribute the data.</span></span> <span data-ttu-id="4c5ab-125">Дополнительные сведения см. в статье [Реорганизация и перестроение индексов](reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4c5ab-125">For more information, see [Reorganize and Rebuild Indexes](reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="4c5ab-126">Хотя низкое значение коэффициента заполнения (отличное от 0) может снизить необходимость в разделении страниц при расширении индекса, для его хранения требуется больший объем памяти, что приводит к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-126">Although a low, nonzero fill-factor value may reduce the requirement to split pages as the index grows, the index will require more storage space and can decrease read performance.</span></span> <span data-ttu-id="4c5ab-127">Даже для приложений, ориентированных на выполнение множества операций вставки и обновления, количество операций считывания обычно в 5–10 раз превышает количество операций записи.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-127">Even for an application oriented for many insert and update operations, the number of database reads typically outnumber database writes by a factor of 5 to 10.</span></span> <span data-ttu-id="4c5ab-128">Поэтому при задании значения коэффициента заполнения, отличного от значения по умолчанию, производительность операций считывания снижается обратно пропорционально значению коэффициента заполнения.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-128">Therefore, specifying a fill factor other than the default can decrease database read performance by an amount inversely proportional to the fill-factor setting.</span></span> <span data-ttu-id="4c5ab-129">Например, значение коэффициента заполнения, равное 50, может снизить производительность операций чтения в два раза.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-129">For example, a fill-factor value of 50 can cause database read performance to decrease by two times.</span></span> <span data-ttu-id="4c5ab-130">Производительность операций чтения снижается из-за того, что в индексе содержится большее количество страниц, что увеличивает количество операций ввода-вывода, проводимых для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-130">Read performance is decreased because the index contains more pages, therefore increasing the disk IO operations required to retrieve the data.</span></span>  
  
#### <a name="adding-data-to-the-end-of-the-table"></a><span data-ttu-id="4c5ab-131">Добавление данных в конец таблицы</span><span class="sxs-lookup"><span data-stu-id="4c5ab-131">Adding Data to the End of the Table</span></span>  
 <span data-ttu-id="4c5ab-132">Ненулевой коэффициент заполнения, отличный от 0 и 100, может повысить производительность, если новые данные равномерно распределяются по таблице.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-132">A nonzero fill factor other than 0 or 100 can be good for performance if the new data is evenly distributed throughout the table.</span></span> <span data-ttu-id="4c5ab-133">Однако, если данные добавляются в конец таблицы, пустое место на страницах индекса заполняться не будет.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-133">However, if all the data is added to the end of the table, the empty space in the index pages will not be filled.</span></span> <span data-ttu-id="4c5ab-134">Например, если ключевым столбцом индекса является столбец IDENTITY, ключ для новых строк будет постоянно увеличиваться и строки индекса будут логически добавляться в конец индекса.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-134">For example, if the index key column is an IDENTITY column, the key for new rows is always increasing and the index rows are logically added to the end of the index.</span></span> <span data-ttu-id="4c5ab-135">Если существующие строки будут обновляться данными, увеличивающими размер строк, следует использовать коэффициент заполнения менее 100.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-135">If existing rows will be updated with data that lengthens the size of the rows, use a fill factor of less than 100.</span></span> <span data-ttu-id="4c5ab-136">Дополнительные байты на каждой странице помогут снизить до минимума разбиение страниц с помощью увеличения длины строк.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-136">The extra bytes on each page will help to minimize page splits caused by extra length in the rows.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4c5ab-137">безопасность</span><span class="sxs-lookup"><span data-stu-id="4c5ab-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c5ab-138">Permissions</span><span class="sxs-lookup"><span data-stu-id="4c5ab-138">Permissions</span></span>  
 <span data-ttu-id="4c5ab-139">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-139">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="4c5ab-140">Пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенных ролей базы данных **db_ddladmin** и **db_owner**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-140">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4c5ab-141">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c5ab-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-fill-factor-by-using-table-designer"></a><span data-ttu-id="4c5ab-142">Задание коэффициента заполнения с помощью конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="4c5ab-142">To specify a fill factor by using Table Designer</span></span>  
  
1.  <span data-ttu-id="4c5ab-143">В обозревателе объектов щелкните значок плюса, чтобы развернуть базу данных, содержащую таблицу, в которой необходимо указать коэффициент заполнения индекса.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-143">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="4c5ab-144">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="4c5ab-144">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4c5ab-145">Щелкните правой кнопкой мыши таблицу, для которой необходимо указать коэффициент заполнения индекса, а затем выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-145">Right-click the table on which you want to specify an index's fill factor and select **Design**.</span></span>  
  
4.  <span data-ttu-id="4c5ab-146">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-146">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="4c5ab-147">Выберите индекс с коэффициентом заполнения, который необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-147">Select the index with the fill factor that you want to specify.</span></span>  
  
6.  <span data-ttu-id="4c5ab-148">Разверните **Характеристики заполнения**, выберите строку **Коэффициент заполнения** и введите в строке необходимый коэффициент заполнения.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-148">Expand **Fill Specification**, select the **Fill Factor** row and enter the fill factor you want in the row.</span></span>  
  
7.  <span data-ttu-id="4c5ab-149">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-149">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="4c5ab-150">В меню **Файл** выберите пункт **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-150">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-index-by-using-object-explorer"></a><span data-ttu-id="4c5ab-151">Указание коэффициента заполнения для индекса с помощью обозревателя объектов:</span><span class="sxs-lookup"><span data-stu-id="4c5ab-151">To specify a fill factor in an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="4c5ab-152">В обозревателе объектов щелкните значок плюса, чтобы развернуть базу данных, содержащую таблицу, в которой необходимо указать коэффициент заполнения индекса.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="4c5ab-153">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="4c5ab-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4c5ab-154">Щелкните знак плюса (+), чтобы развернуть таблицу, для которой необходимо указать коэффициент заполнения индекса.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-154">Click the plus sign to expand the table on which you want to specify an index's fill factor.</span></span>  
  
4.  <span data-ttu-id="4c5ab-155">Чтобы развернуть папку **Индексы** , щелкните знак «плюс» (+).</span><span class="sxs-lookup"><span data-stu-id="4c5ab-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="4c5ab-156">Щелкните правой кнопкой мыши индекс с коэффициентом заполнения, который нужно указать, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-156">Right-click the index with the fill factor that you want to specify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="4c5ab-157">В разделе **Выбор страницы**щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="4c5ab-158">В строке **Коэффициент заполнения** введите нужный коэффициент заполнения.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-158">In the **Fill factor** row, enter the fill factor that you want.</span></span>  
  
8.  <span data-ttu-id="4c5ab-159">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4c5ab-160">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c5ab-160">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-existing-index"></a><span data-ttu-id="4c5ab-161">Указание коэффициента заполнения для существующего индекса</span><span class="sxs-lookup"><span data-stu-id="4c5ab-161">To specify a fill factor in an existing index</span></span>  
  
1.  <span data-ttu-id="4c5ab-162">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c5ab-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c5ab-163">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c5ab-164">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-164">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4c5ab-165">В примере перестраивается существующий индекс и применяется коэффициент заполнения во время операции перестроения.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-165">The example rebuilds an existing index and applies the specified fill factor during the rebuild operation.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Rebuilds the IX_Employee_OrganizationLevel_OrganizationNode index   
    -- with a fill factor of 80 on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD WITH (FILLFACTOR = 80);   
    GO  
    ```  
  
#### <a name="another-way-to-specify-a-fill-factor-in-an-index"></a><span data-ttu-id="4c5ab-166">Другой способ указания коэффициента заполнения в индексе</span><span class="sxs-lookup"><span data-stu-id="4c5ab-166">Another way to specify a fill factor in an index</span></span>  
  
1.  <span data-ttu-id="4c5ab-167">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c5ab-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c5ab-168">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c5ab-169">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4c5ab-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    /* Drops and re-creates the IX_Employee_OrganizationLevel_OrganizationNode index on the HumanResources.Employee table with a fill factor of 80.  
    */  
  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)   
    WITH (DROP_EXISTING = ON, FILLFACTOR = 80);   
    GO  
    ```  
  
 <span data-ttu-id="4c5ab-170">Дополнительные сведения см. в разделе [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4c5ab-170">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
