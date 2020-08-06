---
title: Создание статистики | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.propertis.f1
- sql12.swb.statistics.filter.f1
- sql12.swb.stat.properties.f1
- sql12.swb.stat.columns.f1
helpviewer_keywords:
- creating statistics
- statistics [SQL Server], creating
ms.assetid: 95a455fb-664d-4c95-851e-c6b62d7ebe04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 230bd4d840c3d59dc1267dd6801754b68386cb32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667637"
---
# <a name="create-statistics"></a><span data-ttu-id="2ccb6-102">Создание статистики</span><span class="sxs-lookup"><span data-stu-id="2ccb6-102">Create Statistics</span></span>
  <span data-ttu-id="2ccb6-103">Создать статистику по оптимизации запроса для одного или нескольких столбцов таблицы или индексированного представления в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ccb6-103">You can create query optimization statistics on one or more columns of a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2ccb6-104">Для большинства запросов оптимизатор уже создает необходимую статистику для формирования высококачественного плана запроса, но в некоторых случаях нужно создавать дополнительные статистические данные.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-104">For most queries, the query optimizer already generates the necessary statistics for a high-quality query plan; in a few cases, you need to create additional statistics.</span></span>  
  
 <span data-ttu-id="2ccb6-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2ccb6-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2ccb6-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2ccb6-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2ccb6-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2ccb6-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2ccb6-109">**Для создания статистики используются:**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-109">**To create statistics, using:**</span></span>  
  
     [<span data-ttu-id="2ccb6-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2ccb6-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2ccb6-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2ccb6-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2ccb6-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2ccb6-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2ccb6-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2ccb6-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2ccb6-114">Прежде чем создавать статистику с помощью инструкции CREATE STATISTICS, убедитесь, что на уровне базы данных установлен параметр AUTO_CREATE_STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-114">Before creating statistics with the CREATE STATISTICS statement, verify that the AUTO_CREATE_STATISTICS option is set at the database level.</span></span> <span data-ttu-id="2ccb6-115">Это гарантирует, что оптимизатор запросов продолжит регулярно создавать статистику по отдельным столбцам для столбцов предиката запроса.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-115">This will ensure that the query optimizer continues to routinely create single-column statistics for query predicate columns.</span></span>  
  
-   <span data-ttu-id="2ccb6-116">Каждый объект статистики может содержать до 32 столбцов.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-116">You can list up to 32 columns per statistics object.</span></span>  
  
-   <span data-ttu-id="2ccb6-117">Удалить, переименовать или изменить определение столбца таблицы, определенного в предикате отфильтрованной статистики, нельзя.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-117">You cannot drop, rename, or alter the definition of a table column that is defined in a filtered statistics predicate.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2ccb6-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="2ccb6-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2ccb6-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="2ccb6-119">Permissions</span></span>  
 <span data-ttu-id="2ccb6-120">Пользователь должен быть владельцем таблицы или индексированного представления либо членом одной из следующих ролей: предопределенная роль сервера **sysadmin** , предопределенная роль базы данных **db_owner** или предопределенная роль базы данных **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="2ccb6-120">Requires that the user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2ccb6-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2ccb6-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="2ccb6-122">Создание статистики</span><span class="sxs-lookup"><span data-stu-id="2ccb6-122">To create statistics</span></span>  
  
1.  <span data-ttu-id="2ccb6-123">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть базу данных, в которой нужно создать новую статистику.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-123">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="2ccb6-124">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="2ccb6-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2ccb6-125">Щелкните значок «плюс», чтобы развернуть таблицу, в которой нужно создать новую статистику.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-125">Click the plus sign to expand the table in which you want to create a new statistic.</span></span>  
  
4.  <span data-ttu-id="2ccb6-126">Щелкните правой кнопкой мыши папку **Статистика** и выберите пункт **Создать статистику...** .</span><span class="sxs-lookup"><span data-stu-id="2ccb6-126">Right-click the **Statistics** folder and select **New Statistics...**.</span></span>  
  
     <span data-ttu-id="2ccb6-127">Следующие свойства отображаются на странице **Общие** в диалоговом окне **Новая статистика по таблице**_table_name_ .</span><span class="sxs-lookup"><span data-stu-id="2ccb6-127">The following properties show on the **General** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="2ccb6-128">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-128">**Table Name**</span></span>  
     <span data-ttu-id="2ccb6-129">Отображает имя таблицы, которую описывает данная статистика.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-129">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="2ccb6-130">**Имя статистики**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-130">**Statistics Name**</span></span>  
     <span data-ttu-id="2ccb6-131">Отображает имя объекта базы данных, в котором сохранена статистика.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-131">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="2ccb6-132">**Столбцы статистики**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-132">**Statistics Columns**</span></span>  
     <span data-ttu-id="2ccb6-133">Сетка отображает столбцы, описанные набором статистических данных.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-133">This grid shows the columns described by this set of statistics.</span></span> <span data-ttu-id="2ccb6-134">Все значения сетки доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-134">All values in the grid are read-only.</span></span>  
  
     <span data-ttu-id="2ccb6-135">**имя**;</span><span class="sxs-lookup"><span data-stu-id="2ccb6-135">**Name**</span></span>  
     <span data-ttu-id="2ccb6-136">Отображает имя столбца, описываемого статистикой.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-136">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="2ccb6-137">Это может быть один столбец или комбинация столбцов одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-137">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="2ccb6-138">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-138">**Data Type**</span></span>  
     <span data-ttu-id="2ccb6-139">Указывает тип данных столбцов, описываемых статистикой.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-139">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="2ccb6-140">**Размер**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-140">**Size**</span></span>  
     <span data-ttu-id="2ccb6-141">Отображает размер типа данных для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-141">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="2ccb6-142">**Удостоверение**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-142">**Identity**</span></span>  
     <span data-ttu-id="2ccb6-143">Если флажок установлен, обозначает столбец идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-143">Indicates an identity column when it is checked.</span></span>  
  
     <span data-ttu-id="2ccb6-144">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-144">**Allow Nulls**</span></span>  
     <span data-ttu-id="2ccb6-145">Указывает, допускает ли столбец значения NULL.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-145">Indicates whether the column accepts NULL values.</span></span>  
  
     <span data-ttu-id="2ccb6-146">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-146">**Add**</span></span>  
     <span data-ttu-id="2ccb6-147">Добавить дополнительные столбцы из таблицы в сетку статистики.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-147">Add additional columns from the table to the statistics grid.</span></span>  
  
     <span data-ttu-id="2ccb6-148">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-148">**Remove**</span></span>  
     <span data-ttu-id="2ccb6-149">Удалите выбранный столбец из сетки статистики.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-149">Remove the selected column from the statistics grid.</span></span>  
  
     <span data-ttu-id="2ccb6-150">**Вверх**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-150">**Move Up**</span></span>  
     <span data-ttu-id="2ccb6-151">Переместите выбранный столбец ближе к началу сетки статистики.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-151">Move the selected column to an earlier location in the statistics grid.</span></span> <span data-ttu-id="2ccb6-152">Расположение в сетке может существенно влиять на ценность статистики.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-152">The location in the grid can substantially impact the usefulness of the statistics.</span></span>  
  
     <span data-ttu-id="2ccb6-153">**Вниз**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-153">**Move Down**</span></span>  
     <span data-ttu-id="2ccb6-154">Переместить выбранный столбец ближе к концу сетки статистики.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-154">Move the selected column to a later location in the statistics grid.</span></span>  
  
     <span data-ttu-id="2ccb6-155">**Последнее обновление статистики по этим столбцам:**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-155">**Statistics for these columns were last updated:**</span></span>  
     <span data-ttu-id="2ccb6-156">Указывает давность статистики.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-156">Indicates how old the statistics are.</span></span> <span data-ttu-id="2ccb6-157">Статистика представляет большую ценность, если она актуальна.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-157">Statistics are more valuable when they are current.</span></span> <span data-ttu-id="2ccb6-158">Следует обновлять статистику после больших изменений в данных или после добавления нетипичных данных.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-158">Update statistics after large changes to the data or after adding atypical data.</span></span> <span data-ttu-id="2ccb6-159">Статистику для таблиц с равномерным распределением данных можно обновлять реже.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-159">Statistics for tables that have a consistent distribution of data need to be updated less frequently.</span></span>  
  
     <span data-ttu-id="2ccb6-160">**Обновить статистику для этих столбцов**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-160">**Update statistics for these columns**</span></span>  
     <span data-ttu-id="2ccb6-161">Установите флажок для обновления статистики после закрытия диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-161">Check to update the statistics when the dialog box is closed.</span></span>  
  
     <span data-ttu-id="2ccb6-162">Следующее свойство отображается на странице **Фильтр** диалогового окна **Новая статистика по таблице**_table_name_ .</span><span class="sxs-lookup"><span data-stu-id="2ccb6-162">The following property shows on the **Filter** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="2ccb6-163">**Критерий фильтра**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-163">**Filter Expression**</span></span>  
     <span data-ttu-id="2ccb6-164">Определяет столбцы данных, которые будут включены в статистику фильтрации.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-164">Defines which data rows to include in the filtered statistics.</span></span> <span data-ttu-id="2ccb6-165">Например `Production.ProductSubcategoryID IN ( 1,2,3 )`.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-165">For example, `Production.ProductSubcategoryID IN ( 1,2,3 )`</span></span>  
  
5.  <span data-ttu-id="2ccb6-166">В диалоговом окне **Новая статистика по таблице**_table_name_ на странице **Общие** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-166">In the **New Statistics on Table**_table_name_ dialog box, on the **General** page, click **Add**.</span></span>  
  
     <span data-ttu-id="2ccb6-167">В диалоговом окне **Выбор столбцов** будут показаны следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-167">The following properties show in the **Select Columns** dialog box.</span></span> <span data-ttu-id="2ccb6-168">Эти данные доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-168">This information is read-only.</span></span>  
  
     <span data-ttu-id="2ccb6-169">**имя**;</span><span class="sxs-lookup"><span data-stu-id="2ccb6-169">**Name**</span></span>  
     <span data-ttu-id="2ccb6-170">Отображает имя столбца, описываемого статистикой.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-170">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="2ccb6-171">Это может быть один столбец или комбинация столбцов одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-171">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="2ccb6-172">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-172">**Data Type**</span></span>  
     <span data-ttu-id="2ccb6-173">Указывает тип данных столбцов, описываемых статистикой.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-173">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="2ccb6-174">**Размер**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-174">**Size**</span></span>  
     <span data-ttu-id="2ccb6-175">Отображает размер типа данных для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-175">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="2ccb6-176">**Удостоверение**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-176">**Identity**</span></span>  
     <span data-ttu-id="2ccb6-177">Указывает на столбец идентификаторов, если этот параметр выбран.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-177">Indicates an identity column when checked.</span></span>  
  
     <span data-ttu-id="2ccb6-178">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="2ccb6-178">**Allow NULLs**</span></span>  
     <span data-ttu-id="2ccb6-179">Указывает, допускает ли столбец значения NULL.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-179">Indicates whether the column accepts NULL values.</span></span>  
  
6.  <span data-ttu-id="2ccb6-180">В диалоговом окне **Выбор столбцов** установите флажки рядом со всеми столбцами, для которых нужно создать статистику, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-180">In the **Select Columns** dialog box, select the check box or check boxes of each column for which you want to create a statistic and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="2ccb6-181">В диалоговом окне **Новая статистика по таблице**_table_name_ нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-181">In the **New Statistics on Table**_table_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2ccb6-182">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2ccb6-182">Using Transact-SQL</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="2ccb6-183">Создание статистики</span><span class="sxs-lookup"><span data-stu-id="2ccb6-183">To create statistics</span></span>  
  
1.  <span data-ttu-id="2ccb6-184">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ccb6-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2ccb6-185">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2ccb6-186">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Create new statistic object called ContactMail1  
    -- on the BusinessEntityID and EmailPromotion columns in the Person.Person table.   
  
    CREATE STATISTICS ContactMail1  
        ON Person.Person (BusinessEntityID, EmailPromotion);   
    GO  
    ```  
  
4.  <span data-ttu-id="2ccb6-187">Статистика, созданная выше, потенциально может улучшить результаты следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="2ccb6-187">The statistic created above potentially improves the results for the following query.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT LastName, FirstName  
    FROM Person.Person  
    WHERE EmailPromotion = 2  
    ORDER BY LastName, FirstName;   
    GO  
    ```  
  
 <span data-ttu-id="2ccb6-188">Дополнительные сведения см. в статье [CREATE STATISTICS (Transact-SQL)](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ccb6-188">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
