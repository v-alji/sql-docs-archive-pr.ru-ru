---
title: Создание таблиц (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table creation [SQL Server], Visual Database Tools
ms.assetid: 6f7c6ac5-e6d3-4dca-831e-b28442ba535b
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d84a4da6a10fbcbae311fe1bf738c03b85a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669349"
---
# <a name="create-tables-database-engine"></a><span data-ttu-id="8aeb2-102">Создание таблиц (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="8aeb2-102">Create Tables (Database Engine)</span></span>
  <span data-ttu-id="8aeb2-103">Предусмотрена возможность создавать новые таблицы, присваивать им имена и добавлять к существующим базам данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , используя [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aeb2-103">You can create a new table, name it, and add it to an existing database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="8aeb2-104">При подключении к базе данных SQL Azure новый параметр таблицы запускает скрипт создания шаблона таблицы.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-104">If you are connected to a SQL Azure database, the new table option launches a create table template script.</span></span> <span data-ttu-id="8aeb2-105">Измените параметры, затем запустите скрипт для создания новой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-105">Edit the parameters, then run the script to create a new table.</span></span> <span data-ttu-id="8aeb2-106">Дополнительные сведения см. в разделе [Общие сведения о SQL Azure](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span><span class="sxs-lookup"><span data-stu-id="8aeb2-106">For more information, see [SQL Azure Overview](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span></span>

 <span data-ttu-id="8aeb2-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8aeb2-107">**In This Topic**</span></span>

-   <span data-ttu-id="8aeb2-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8aeb2-108">**Before you begin:**</span></span>

     [<span data-ttu-id="8aeb2-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8aeb2-109">Security</span></span>](#Security)

-   <span data-ttu-id="8aeb2-110">**Создание таблицы с использованием:**</span><span class="sxs-lookup"><span data-stu-id="8aeb2-110">**To create a table, using:**</span></span>

     [<span data-ttu-id="8aeb2-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8aeb2-111">SQL Server Management Studio</span></span>](#SSMSProcedure)

     [<span data-ttu-id="8aeb2-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8aeb2-112">Transact-SQL</span></span>](#TsqlProcedure)

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8aeb2-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8aeb2-113">Before You Begin</span></span>

###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8aeb2-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="8aeb2-114">Security</span></span>

####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8aeb2-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="8aeb2-115">Permissions</span></span>
 <span data-ttu-id="8aeb2-116">Требует разрешения CREATE TABLE в базе данных и разрешения ALTER на схему, в которой создается таблица.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-116">Requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>

 <span data-ttu-id="8aeb2-117">Если какие-либо столбцы в инструкции CREATE TABLE определены как принадлежащие к определяемому пользователем типу данных CLR, необходимо быть владельцем данного типа либо иметь разрешение REFERENCES на него.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-117">If any columns in the CREATE TABLE statement are defined as a CLR user-defined type, either ownership of the type or REFERENCES permission on it is required.</span></span>

 <span data-ttu-id="8aeb2-118">Если какие-либо столбцы в инструкции CREATE TABLE имеют связанную коллекцию схем XML, необходимо быть владельцем этого набора схем или иметь разрешение REFERENCES на него.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-118">If any columns in the CREATE TABLE statement have an XML schema collection associated with them, either ownership of the XML schema collection or REFERENCES permission on it is required.</span></span>

##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8aeb2-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8aeb2-119">Using SQL Server Management Studio</span></span>

#### <a name="to-create-a-table-with-table-designer"></a><span data-ttu-id="8aeb2-120">Создание таблицы в конструкторе таблиц</span><span class="sxs-lookup"><span data-stu-id="8aeb2-120">To create a table with Table Designer</span></span>

1.  <span data-ttu-id="8aeb2-121">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , который содержит изменяемую базу данных.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-121">In **Object Explorer**, connect to the instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] that contains the database to be modified.</span></span>

2.  <span data-ttu-id="8aeb2-122">В **обозревателе объектов**разверните узел **Базы данных** , а затем базу данных, в которой будет размещена новая таблица.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-122">In **Object Explorer**, expand the **Databases** node and then expand the database that will contain the new table.</span></span>

3.  <span data-ttu-id="8aeb2-123">В обозревателе объектов щелкните правой кнопкой мыши узел **Таблицы** базы данных и выберите **Создать таблицу**.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-123">In Object Explorer, right-click the **Tables** node of your database and then click **New Table**.</span></span>

4.  <span data-ttu-id="8aeb2-124">Введите имена столбцов, выберите типы данных и определите для каждого столбца, могут ли в нем присутствовать значения NULL, как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-124">Type column names, choose data types, and choose whether to allow nulls for each column as shown in the following illustration.</span></span>

     <span data-ttu-id="8aeb2-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span><span class="sxs-lookup"><span data-stu-id="8aeb2-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span></span>

5.  <span data-ttu-id="8aeb2-126">Вы также можете задать другие свойства столбца, например является ли этот столбец столбцом идентификаторов или вычисляемым столбцом. Для этого щелкните столбец на вкладке свойств столбцов.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-126">To specify more properties for a column, such as identity or computed column values, click the column and in the column properties tab, choose the appropriate properties.</span></span> <span data-ttu-id="8aeb2-127">Дополнительные сведения о свойствах столбцов см. в разделе [Свойства столбца таблицы (среда SQL Server Management Studio)](table-column-properties-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8aeb2-127">For more information about column properties, see [Table Column Properties &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span></span>

6.  <span data-ttu-id="8aeb2-128">Чтобы указать, что столбец является столбцом первичного ключа, щелкните его правой кнопкой мыши и выберите **Задать первичный ключ**.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-128">To specify a column as a primary key, right-click the column and select **Set Primary Key**.</span></span> <span data-ttu-id="8aeb2-129">Дополнительные сведения см. в статье [Create Primary Keys](../tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="8aeb2-129">For more information, see [Create Primary Keys](../tables/create-primary-keys.md).</span></span>

7.  <span data-ttu-id="8aeb2-130">Чтобы создать связи по внешнему ключу, проверочные ограничения или индексы, щелкните правой кнопкой мыши панель конструктора таблиц и выберите из списка объект, как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-130">To create foreign key relationships, check constraints, or indexes, right-click in the Table Designer pane and select an object from the list as shown in the following illustration.</span></span>

     <span data-ttu-id="8aeb2-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span><span class="sxs-lookup"><span data-stu-id="8aeb2-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span></span>

     <span data-ttu-id="8aeb2-132">Дополнительные сведения об этих объектах см. в разделах [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) и [Indexes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="8aeb2-132">For more information about these objects, see [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) and [Indexes](../indexes/indexes.md).</span></span>

8.  <span data-ttu-id="8aeb2-133">По умолчанию таблица содержится в схеме **dbo** .</span><span class="sxs-lookup"><span data-stu-id="8aeb2-133">By default, the table is contained in the **dbo** schema.</span></span> <span data-ttu-id="8aeb2-134">Чтобы указать другую схему для таблицы, щелкните правой кнопкой мыши панель конструктора таблиц и выберите **Свойства** , как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-134">To specify a different schema for the table, right-click in the Table Designer pane and select **Properties** as shown in the following illustration.</span></span> <span data-ttu-id="8aeb2-135">Выберите нужную схему из раскрывающегося списка **Схема** .</span><span class="sxs-lookup"><span data-stu-id="8aeb2-135">From the **Schema** drop-down list, select the appropriate schema.</span></span>

     <span data-ttu-id="8aeb2-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span><span class="sxs-lookup"><span data-stu-id="8aeb2-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span></span>

     <span data-ttu-id="8aeb2-137">Дополнительные сведения о схемах см. в разделе [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span><span class="sxs-lookup"><span data-stu-id="8aeb2-137">For more information about schemas, see [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span></span>

9. <span data-ttu-id="8aeb2-138">В меню **Файл** выберите команду **Сохранить** *имя_таблицы*.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-138">From the **File** menu, choose **Save** *table name*.</span></span>

10. <span data-ttu-id="8aeb2-139">В диалоговом окне **Выбор имени** введите имя таблицы и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-139">In the **Choose Name** dialog box, type a name for the table and click **OK**.</span></span>

11. <span data-ttu-id="8aeb2-140">Чтобы просмотреть новую таблицу, в **обозревателе объектов**разверните узел **Таблицы** , а затем нажмите клавишу **F5** , чтобы обновить список объектов.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-140">To view the new table, in **Object Explorer**, expand the **Tables** node and press **F5** to refresh the list of objects.</span></span> <span data-ttu-id="8aeb2-141">Новая таблица будет отображена в списке таблиц.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-141">The new table is displayed in the list of tables.</span></span>

##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8aeb2-142">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8aeb2-142">Using Transact-SQL</span></span>

#### <a name="to-create-a-table-in-the-query-editor"></a><span data-ttu-id="8aeb2-143">Создание таблицы в редакторе запросов</span><span class="sxs-lookup"><span data-stu-id="8aeb2-143">To create a table in the Query Editor</span></span>

1.  <span data-ttu-id="8aeb2-144">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aeb2-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>

2.  <span data-ttu-id="8aeb2-145">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-145">On the Standard bar, click **New Query**.</span></span>

3.  <span data-ttu-id="8aeb2-146">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8aeb2-146">Copy and paste the following example into the query window and click **Execute**.</span></span>

    ```
    CREATE TABLE dbo.PurchaseOrderDetail
    (
        PurchaseOrderID int NOT NULL
        ,LineNumber smallint NOT NULL
        ,ProductID int NULL
        ,UnitPrice money NULL
        ,OrderQty smallint NULL
        ,ReceivedQty float NULL
        ,RejectedQty float NULL
        ,DueDate datetime NULL
    );
    ```

 <span data-ttu-id="8aeb2-147">Дополнительные сведения см. в разделе [CREATE TABLE (Transact-SQL)](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8aeb2-147">For more examples, see [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>


