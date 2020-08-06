---
title: Создание уникальных индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- unique indexes
- designing indexes [SQL Server], unique
- clustered indexes, unique
- indexes [SQL Server], unique
- nonclustered indexes [SQL Server], unique
- unique indexes, design guidelines
ms.assetid: 56b5982e-cb94-46c0-8fbb-772fc275354a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c96c4e17a8ce0863452db171302d650f6114919
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749840"
---
# <a name="create-unique-indexes"></a><span data-ttu-id="12168-102">Создание уникальных индексов</span><span class="sxs-lookup"><span data-stu-id="12168-102">Create Unique Indexes</span></span>
  <span data-ttu-id="12168-103">В данном разделе описывается создание уникальных индексов в таблице в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12168-103">This topic describes how to create a unique index on a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="12168-104">Уникальный индекс гарантирует, что ключ индекса не будет содержать одинаковых значений, а значит, каждая строка в таблице будет уникальна.</span><span class="sxs-lookup"><span data-stu-id="12168-104">A unique index guarantees that the index key contains no duplicate values and therefore every row in the table is in some way unique.</span></span> <span data-ttu-id="12168-105">Нет существенных различий между созданием ограничения UNIQUE и созданием уникального индекса, не зависящего от ограничения.</span><span class="sxs-lookup"><span data-stu-id="12168-105">There are no significant differences between creating a UNIQUE constraint and creating a unique index that is independent of a constraint.</span></span> <span data-ttu-id="12168-106">Проверка данных происходит подобным же образом, и оптимизатор запросов не делает различия между уникальным индексом, который создан ограничением, и индексом, созданным вручную.</span><span class="sxs-lookup"><span data-stu-id="12168-106">Data validation occurs in the same manner, and the query optimizer does not differentiate between a unique index created by a constraint or manually created.</span></span> <span data-ttu-id="12168-107">Однако при создании ограничения UNIQUE для столбца назначение индекса становится очевидным.</span><span class="sxs-lookup"><span data-stu-id="12168-107">However, creating a UNIQUE constraint on the column makes the objective of the index clear.</span></span> <span data-ttu-id="12168-108">Дополнительные сведения об ограничениях UNIQUE см. в разделе [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="12168-108">For more information on UNIQUE constraints, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="12168-109">При создании уникального индекса можно установить параметр пропуска дублирующихся ключей.</span><span class="sxs-lookup"><span data-stu-id="12168-109">When you create a unique index, you can set an option to ignore duplicate keys.</span></span> <span data-ttu-id="12168-110">Если для этого параметра установлено значение **Да** , то при попытке создать дублирующиеся ключи путем добавления данных, которые влияют на несколько строк (при помощи инструкции INSERT), строка, содержащая дубликат, добавлена не будет.</span><span class="sxs-lookup"><span data-stu-id="12168-110">If this option is set to **Yes** and you attempt to create duplicate keys by adding data that affects multiple rows (with the INSERT statement), the row containing a duplicate is not added.</span></span> <span data-ttu-id="12168-111">Если для параметра установлено значение **Нет**, вся операция вставки завершится неудачно и будет выполнен откат всех данных.</span><span class="sxs-lookup"><span data-stu-id="12168-111">If it is set to **No**, the entire insert operation fails and all the data is rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12168-112">Нельзя создать уникальный индекс для одного столбца, если в более чем одной строке этого столбца содержится значение NULL.</span><span class="sxs-lookup"><span data-stu-id="12168-112">You cannot create a unique index on a single column if that column contains NULL in more than one row.</span></span> <span data-ttu-id="12168-113">Нельзя также создать уникальный индекс для нескольких столбцов, если в более чем одной строке такой комбинации столбцов содержится значение NULL.</span><span class="sxs-lookup"><span data-stu-id="12168-113">Similarly, you cannot create a unique index on multiple columns if the combination of columns contains NULL in more than one row.</span></span> <span data-ttu-id="12168-114">При индексировании такие значения будут рассматриваться как дубликаты.</span><span class="sxs-lookup"><span data-stu-id="12168-114">These are treated as duplicate values for indexing purposes.</span></span>  
  
 <span data-ttu-id="12168-115">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="12168-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="12168-116">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="12168-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="12168-117">Преимущества уникального индекса</span><span class="sxs-lookup"><span data-stu-id="12168-117">Benefits of a Unique Index</span></span>](#Benefits)  
  
     [<span data-ttu-id="12168-118">Стандартные реализации</span><span class="sxs-lookup"><span data-stu-id="12168-118">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="12168-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="12168-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="12168-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="12168-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="12168-121">**Создание уникального индекса для таблицы с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="12168-121">**To create a unique index on a table, using:**</span></span>  
  
     [<span data-ttu-id="12168-122">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12168-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="12168-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12168-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="12168-124">Перед началом</span><span class="sxs-lookup"><span data-stu-id="12168-124">Before You Begin</span></span>  
  
###  <a name="benefits-of-a-unique-index"></a><a name="Benefits"></a> <span data-ttu-id="12168-125">Преимущества уникального индекса</span><span class="sxs-lookup"><span data-stu-id="12168-125">Benefits of a Unique Index</span></span>  
  
-   <span data-ttu-id="12168-126">Использование уникальных индексов по нескольким столбцам позволяет гарантировать уникальность всех сочетаний значений в ключе индекса.</span><span class="sxs-lookup"><span data-stu-id="12168-126">Multicolumn unique indexes guarantee that each combination of values in the index key is unique.</span></span> <span data-ttu-id="12168-127">Например, если уникальный индекс создан для комбинации столбцов **LastName**, **FirstName**и **MiddleName** , то никакие две строки в таблице не могут образовывать одну и ту же комбинацию этих значений.</span><span class="sxs-lookup"><span data-stu-id="12168-127">For example, if a unique index is created on a combination of **LastName**, **FirstName**, and **MiddleName** columns, no two rows in the table could have the same combination of values for these columns.</span></span>  
  
-   <span data-ttu-id="12168-128">При условии уникальности данных в каждом столбце можно создать уникальный кластеризованный индекс и несколько уникальных некластеризованных индексов для одной и той же таблицы.</span><span class="sxs-lookup"><span data-stu-id="12168-128">Provided that the data in each column is unique, you can create both a unique clustered index and multiple unique nonclustered indexes on the same table.</span></span>  
  
-   <span data-ttu-id="12168-129">Уникальные индексы гарантируют целостность данных в определенных столбцах.</span><span class="sxs-lookup"><span data-stu-id="12168-129">Unique indexes ensure the data integrity of the defined columns.</span></span>  
  
-   <span data-ttu-id="12168-130">Уникальные индексы обеспечивают дополнительные сведения, которые могут использоваться оптимизатором запросов для создания более эффективных планов выполнения.</span><span class="sxs-lookup"><span data-stu-id="12168-130">Unique indexes provide additional information helpful to the query optimizer that can produce more efficient execution plans.</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="12168-131">Стандартные реализации</span><span class="sxs-lookup"><span data-stu-id="12168-131">Typical Implementations</span></span>  
 <span data-ttu-id="12168-132">Уникальные индексы реализуются следующими способами:</span><span class="sxs-lookup"><span data-stu-id="12168-132">Unique indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="12168-133">**Ограничение PRIMARY KEY или UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="12168-133">**PRIMARY KEY or UNIQUE constraint**</span></span>  
  
     <span data-ttu-id="12168-134">Если кластеризованный индекс в таблице еще не создан, а уникальный некластеризованный индекс еще не указан, то при создании ограничения PRIMARY KEY в одном или нескольких столбцах автоматически создается уникальный кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="12168-134">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="12168-135">В первичном ключевом столбце недопустимы значения NULL.</span><span class="sxs-lookup"><span data-stu-id="12168-135">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="12168-136">При создании ограничения UNIQUE создается уникальный некластеризованный индекс. Он нужен, чтобы принудительно применять ограничение UNIQUE по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="12168-136">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="12168-137">Если кластеризованный индекс в таблице еще не создан, то можно указать уникальный кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="12168-137">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="12168-138">Дополнительные сведения см. в разделах [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) и [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="12168-138">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) and [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span></span>  
  
-   <span data-ttu-id="12168-139">**Индекс, не зависящий от ограничения**</span><span class="sxs-lookup"><span data-stu-id="12168-139">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="12168-140">По таблице может быть определено несколько уникальных некластеризованных индексов.</span><span class="sxs-lookup"><span data-stu-id="12168-140">Multiple unique nonclustered indexes can be defined on a table.</span></span>  
  
     <span data-ttu-id="12168-141">Дополнительные сведения см. в разделе [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12168-141">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="12168-142">**Индексированное представление**</span><span class="sxs-lookup"><span data-stu-id="12168-142">**Indexed view**</span></span>  
  
     <span data-ttu-id="12168-143">Чтобы создать индексированное представление, по одному или нескольким столбцам представления определяется уникальный кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="12168-143">To create an indexed view, a unique clustered index is defined on one or more view columns.</span></span> <span data-ttu-id="12168-144">Представление выполняется и результирующий набор сохраняется на конечном уровне индекса аналогично хранению данных таблиц в кластеризованном индексе.</span><span class="sxs-lookup"><span data-stu-id="12168-144">The view is executed and the result set is stored in the leaf level of the index in the same way table data is stored in a clustered index.</span></span> <span data-ttu-id="12168-145">Дополнительные сведения см. в разделе [Создание индексированных представлений](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="12168-145">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="12168-146">Ограничения</span><span class="sxs-lookup"><span data-stu-id="12168-146">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="12168-147">Уникальный индекс и ограничения UNIQUE и PRIMARY KEY не могут быть созданы, если дублирующиеся значения уже существуют.</span><span class="sxs-lookup"><span data-stu-id="12168-147">A unique index, UNIQUE constraint, or PRIMARY KEY constraint cannot be created if duplicate key values exist in the data.</span></span>  
  
-   <span data-ttu-id="12168-148">Уникальный некластеризованный индекс может содержать любые неключевые столбцы.</span><span class="sxs-lookup"><span data-stu-id="12168-148">A unique nonclustered index can contain included nonkey columns.</span></span> <span data-ttu-id="12168-149">Дополнительные сведения см. в статье [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="12168-149">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="12168-150">безопасность</span><span class="sxs-lookup"><span data-stu-id="12168-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="12168-151">Permissions</span><span class="sxs-lookup"><span data-stu-id="12168-151">Permissions</span></span>  
 <span data-ttu-id="12168-152">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="12168-152">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="12168-153">Пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенных ролей базы данных **db_ddladmin** и **db_owner**.</span><span class="sxs-lookup"><span data-stu-id="12168-153">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="12168-154">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12168-154">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-index-by-using-the-table-designer"></a><span data-ttu-id="12168-155">Создание уникального индекса с помощью конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="12168-155">To create a unique index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="12168-156">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо создать уникальный индекс.</span><span class="sxs-lookup"><span data-stu-id="12168-156">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="12168-157">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="12168-157">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="12168-158">Щелкните правой кнопкой мыши таблицу, в которой нужно создать уникальный индекс, и выберите **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="12168-158">Right-click the table on which you want to create a unique index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="12168-159">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи**.</span><span class="sxs-lookup"><span data-stu-id="12168-159">On the **Table Designer** menu, select **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="12168-160">В диалоговом окне **Индексы и ключи** нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="12168-160">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="12168-161">Выберите новый индекс в текстовом поле **Выбранный первичный/уникальный ключ или индекс** .</span><span class="sxs-lookup"><span data-stu-id="12168-161">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="12168-162">В основной сетке в **(Общие)** выберите **Тип** , а затем выберите в списке **Индекс** .</span><span class="sxs-lookup"><span data-stu-id="12168-162">In the main grid, under **(General)**, select **Type** and then choose **Index** from the list.</span></span>  
  
8.  <span data-ttu-id="12168-163">Выберите **Столбцы** и затем нажмите кнопку с многоточием **(…)** .</span><span class="sxs-lookup"><span data-stu-id="12168-163">Select **Columns**, and then click the ellipsis **(...)**.</span></span>  
  
9. <span data-ttu-id="12168-164">В диалоговом окне **Столбцы индекса** в поле **Имя столбца**выберите столбцы, которые необходимо индексировать.</span><span class="sxs-lookup"><span data-stu-id="12168-164">In the **Index Columns** dialog box, under **Column Name**, select the columns you want to index.</span></span> <span data-ttu-id="12168-165">Выбрать можно до 16 столбцов.</span><span class="sxs-lookup"><span data-stu-id="12168-165">You can select up to 16 columns.</span></span> <span data-ttu-id="12168-166">Для оптимальной производительности следует выбирать только один или два столбца на индекс.</span><span class="sxs-lookup"><span data-stu-id="12168-166">For optimal performance, select only one or two columns per index.</span></span> <span data-ttu-id="12168-167">Для каждого выбранного столбца укажите, будут ли значения данного столбца располагаться в индексе в возрастающем или убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="12168-167">For each column you select, indicate whether the index arranges values of this column in ascending or descending order.</span></span>  
  
10. <span data-ttu-id="12168-168">После выбора всех столбцов для индекса щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12168-168">When all columns for the index are selected, click **OK**.</span></span>  
  
11. <span data-ttu-id="12168-169">В сетке в **(Общие)** выберите **Уникальный** , а затем выберите в списке **Да** .</span><span class="sxs-lookup"><span data-stu-id="12168-169">In the grid, under **(General)**, select **Is Unique** and then choose **Yes** from the list.</span></span>  
  
12. <span data-ttu-id="12168-170">Дополнительно. В основной сетке в разделе **Конструктор таблиц**выберите **Пропустить повторяющиеся ключи** , а затем выберите в списке значение **Да** .</span><span class="sxs-lookup"><span data-stu-id="12168-170">Optional: In the main grid, under **Table Designer**, select **Ignore Duplicate Keys** and then choose **Yes** from the list.</span></span> <span data-ttu-id="12168-171">Сделайте это, если необходимо пропустить попытки добавления данных, создающих повторяющиеся ключи в уникальном индексе.</span><span class="sxs-lookup"><span data-stu-id="12168-171">Do this if you want to ignore attempts to add data that would create a duplicate key in the unique index.</span></span>  
  
13. <span data-ttu-id="12168-172">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="12168-172">Click **Close**.</span></span>  
  
14. <span data-ttu-id="12168-173">В меню **Файл** выберите пункт **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="12168-173">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="create-a-unique-index-by-using-object-explorer"></a><span data-ttu-id="12168-174">Создание уникального индекса в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="12168-174">Create a unique index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="12168-175">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо создать уникальный индекс.</span><span class="sxs-lookup"><span data-stu-id="12168-175">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="12168-176">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="12168-176">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="12168-177">Разверните таблицу, для которой необходимо создать уникальный индекс.</span><span class="sxs-lookup"><span data-stu-id="12168-177">Expand the table on which you want to create a unique index.</span></span>  
  
4.  <span data-ttu-id="12168-178">Щелкните правой кнопкой мыши папку **Индексы**, выберите **Создать индекс** и **Некластеризованный индекс...**</span><span class="sxs-lookup"><span data-stu-id="12168-178">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="12168-179">В диалоговом окне **Создание индекса** на странице **Общие** введите имя нового индекса в поле **Имя индекса** .</span><span class="sxs-lookup"><span data-stu-id="12168-179">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="12168-180">Установите флажок **Уникальный** .</span><span class="sxs-lookup"><span data-stu-id="12168-180">Select the **Unique** check box.</span></span>  
  
7.  <span data-ttu-id="12168-181">В разделе **Ключевые столбцы индекса** щелкните **Добавить…** .</span><span class="sxs-lookup"><span data-stu-id="12168-181">Under **Index key columns**, click **Add...**.</span></span>  
  
8.  <span data-ttu-id="12168-182">В диалоговом окне **Выбор столбцов из**_table_name_ установите флажки для столбцов таблицы или столбцов, которые будут добавлены в уникальный индекс.</span><span class="sxs-lookup"><span data-stu-id="12168-182">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
9. <span data-ttu-id="12168-183">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12168-183">Click **OK**.</span></span>  
  
10. <span data-ttu-id="12168-184">В диалоговом окне **Создание индекса** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12168-184">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="12168-185">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12168-185">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-index-on-a-table"></a><span data-ttu-id="12168-186">Создание уникального индекса в таблице</span><span class="sxs-lookup"><span data-stu-id="12168-186">To create a unique index on a table</span></span>  
  
1.  <span data-ttu-id="12168-187">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12168-187">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="12168-188">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="12168-188">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="12168-189">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="12168-189">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named AK_UnitMeasure_Name and delete it if found  
    IF EXISTS (SELECT name from sys.indexes  
               WHERE name = N'AK_UnitMeasure_Name')   
       DROP INDEX AK_UnitMeasure_Name ON Production.UnitMeasure;   
    GO  
    -- Create a unique index called AK_UnitMeasure_Name  
    -- on the Production.UnitMeasure table using the Name column.  
    CREATE UNIQUE INDEX AK_UnitMeasure_Name   
       ON Production.UnitMeasure (Name);   
    GO  
    ```  
  
 <span data-ttu-id="12168-190">Дополнительные сведения см. в разделе [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12168-190">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
