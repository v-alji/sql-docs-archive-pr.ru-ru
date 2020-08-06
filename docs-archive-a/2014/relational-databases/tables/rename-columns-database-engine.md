---
title: Переименование столбцов (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], names
- renaming columns
- column names [SQL Server]
ms.assetid: 7c71ec9f-0180-4398-b32a-4bfb7592e75d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6871ab82eaa17aa5e392e6b2bb3f5c60058f9af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666979"
---
# <a name="rename-columns-database-engine"></a><span data-ttu-id="b21f9-102">Переименование столбцов (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="b21f9-102">Rename Columns (Database Engine)</span></span>
  <span data-ttu-id="b21f9-103">Столбец таблицы в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно переименовать, используя [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b21f9-103">You can rename a table column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b21f9-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b21f9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b21f9-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b21f9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b21f9-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b21f9-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b21f9-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b21f9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b21f9-108">**Переименование столбцов с помощью:**</span><span class="sxs-lookup"><span data-stu-id="b21f9-108">**To rename columns, using:**</span></span>  
  
     [<span data-ttu-id="b21f9-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b21f9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b21f9-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b21f9-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b21f9-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b21f9-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b21f9-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b21f9-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b21f9-113">Переименование столбца таблицы не приводит к автоматическому переименованию ссылок на этот столбец.</span><span class="sxs-lookup"><span data-stu-id="b21f9-113">Renaming a column will not automatically rename references to that column.</span></span> <span data-ttu-id="b21f9-114">Необходимо вручную изменить все объекты, которые ссылаются на переименованный столбец.</span><span class="sxs-lookup"><span data-stu-id="b21f9-114">You must modify any objects that reference the renamed column manually.</span></span> <span data-ttu-id="b21f9-115">Например, если переименован столбец таблицы и на этот столбец имеется ссылка в триггере, то необходимо изменить триггер, указав новое имя столбца.</span><span class="sxs-lookup"><span data-stu-id="b21f9-115">For example, if you rename a table column and that column is referenced in a trigger, you must modify the trigger to reflect the new column name.</span></span> <span data-ttu-id="b21f9-116">Используйте [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) , чтобы составить список зависимостей для объекта перед его переименованием.</span><span class="sxs-lookup"><span data-stu-id="b21f9-116">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the object before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b21f9-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="b21f9-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b21f9-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="b21f9-118">Permissions</span></span>  
 <span data-ttu-id="b21f9-119">Необходимо разрешение ALTER на объект.</span><span class="sxs-lookup"><span data-stu-id="b21f9-119">Requires ALTER permission on the object.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b21f9-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b21f9-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-column-using-object-explorer"></a><span data-ttu-id="b21f9-121">Переименование столбца в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="b21f9-121">To rename a column using Object Explorer</span></span>  
  
1.  <span data-ttu-id="b21f9-122">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b21f9-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b21f9-123">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу, в которой нужно переименовать столбцы, и выберите пункт **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="b21f9-123">In **Object Explorer**, right-click the table in which you want to rename columns and choose **Rename**.</span></span>  
  
3.  <span data-ttu-id="b21f9-124">Введите новое имя столбца.</span><span class="sxs-lookup"><span data-stu-id="b21f9-124">Type a new column name.</span></span>  
  
#### <a name="to-rename-a-column-using-table-designer"></a><span data-ttu-id="b21f9-125">Переименование столбца в конструкторе таблиц</span><span class="sxs-lookup"><span data-stu-id="b21f9-125">To rename a column using Table Designer</span></span>  
  
1.  <span data-ttu-id="b21f9-126">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу, в которой нужно переименовать столбцы, и выберите пункт **Конструирование**.</span><span class="sxs-lookup"><span data-stu-id="b21f9-126">In **Object Explorer**, right-click the table to which you want to rename columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="b21f9-127">В разделе **Имя столбца**выберите имя, которое нужно изменить, и введите новое.</span><span class="sxs-lookup"><span data-stu-id="b21f9-127">Under **Column Name**, select the name you want to change and type a new one.</span></span>  
  
3.  <span data-ttu-id="b21f9-128">В меню **Файл** выберите команду **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="b21f9-128">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b21f9-129">Имя столбца можно также изменить на вкладке **Свойства столбца** . Выберите столбец, имя которого нужно изменить, и введите новое значение в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="b21f9-129">You can also change the name of a column in the **Column Properties** tab. Select the column whose name you want to change and type a new value for **Name**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b21f9-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b21f9-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="b21f9-131">**Переименование столбца**</span><span class="sxs-lookup"><span data-stu-id="b21f9-131">**To rename a column**</span></span>  
  
#### <a name="to-rename-a-column"></a><span data-ttu-id="b21f9-132">Переименование столбца</span><span class="sxs-lookup"><span data-stu-id="b21f9-132">To rename a column</span></span>  
  
1.  <span data-ttu-id="b21f9-133">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b21f9-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b21f9-134">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b21f9-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b21f9-135">В следующем примере столбец `TerritoryID` в таблице `Sales.SalesTerritory` переименовывается в `TerrID`.</span><span class="sxs-lookup"><span data-stu-id="b21f9-135">The following example renames the column `TerritoryID` in the table `Sales.SalesTerritory` to `TerrID`.</span></span> <span data-ttu-id="b21f9-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b21f9-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename 'Sales.SalesTerritory.TerritoryID', 'TerrID', 'COLUMN';  
    GO  
    ```  
  
 <span data-ttu-id="b21f9-137">Дополнительные сведения см. в разделе [sp_rename (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b21f9-137">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
