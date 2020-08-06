---
title: Переименование таблиц (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table renaming [SQL Server]
- table names [SQL Server]
- tables [SQL Server], Visual Database Tools
- renaming tables
ms.assetid: 2f5c922d-4d71-4694-9fca-28dd99375799
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e73bbb92d8fd3fdcaa7756ce1dcb74d8cd598b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666976"
---
# <a name="rename-tables-database-engine"></a><span data-ttu-id="85e41-102">Переименование таблиц (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="85e41-102">Rename Tables (Database Engine)</span></span>
  <span data-ttu-id="85e41-103">Таблицу в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно переименовать, используя [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85e41-103">You can rename a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="85e41-104">Каждое переименование таблицы следует тщательно планировать.</span><span class="sxs-lookup"><span data-stu-id="85e41-104">Think carefully before you rename a table.</span></span> <span data-ttu-id="85e41-105">Если существующие запросы, представления, определяемые пользователем функции, хранимые процедуры или программы ссылаются на таблицу, изменение имени таблицы сделает эти объекты недействительными.</span><span class="sxs-lookup"><span data-stu-id="85e41-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="85e41-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="85e41-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="85e41-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="85e41-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="85e41-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="85e41-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="85e41-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="85e41-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="85e41-110">**Переименование таблицы с использованием:**</span><span class="sxs-lookup"><span data-stu-id="85e41-110">**To rename a table, using:**</span></span>  
  
     [<span data-ttu-id="85e41-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="85e41-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="85e41-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="85e41-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="85e41-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="85e41-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="85e41-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="85e41-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="85e41-115">Переименование таблицы не приводит к автоматическому переименованию ссылок на эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="85e41-115">Renaming a table will not automatically rename references to that table.</span></span> <span data-ttu-id="85e41-116">Необходимо вручную изменить все объекты, которые ссылаются на переименованную таблицу.</span><span class="sxs-lookup"><span data-stu-id="85e41-116">You must manually modify any objects that reference the renamed table.</span></span> <span data-ttu-id="85e41-117">Например, если переименована таблица и на эту таблицу имеется ссылка в триггере, то необходимо изменить триггер, указав новое имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="85e41-117">For example, if you rename a table and that table is referenced in a trigger, you must modify the trigger to reflect the new table name.</span></span> <span data-ttu-id="85e41-118">Используйте представление каталога [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) , чтобы составить список зависимостей для таблицы перед переименованием.</span><span class="sxs-lookup"><span data-stu-id="85e41-118">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the table before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="85e41-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="85e41-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="85e41-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="85e41-120">Permissions</span></span>  
 <span data-ttu-id="85e41-121">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="85e41-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="85e41-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="85e41-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="85e41-123">Переименование таблицы</span><span class="sxs-lookup"><span data-stu-id="85e41-123">To rename a table</span></span>  
  
1.  <span data-ttu-id="85e41-124">В обозревателе объектов правой кнопкой мыши щелкните таблицу, имя которой хотите переименовать, и в контекстном меню выберите пункт **Конструирование** .</span><span class="sxs-lookup"><span data-stu-id="85e41-124">In Object Explorer, right-click the table you want to rename and choose **Design** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="85e41-125">В меню **Просмотр** выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="85e41-125">From the **View** menu, choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="85e41-126">В поле **Имя** окна **Свойства** введите новое имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="85e41-126">In the field for the **Name** value in the **Properties** window, type a new name for the table.</span></span>  
  
4.  <span data-ttu-id="85e41-127">Чтобы отменить это действие, нажмите клавишу ESC перед тем, как выйти из этого поля.</span><span class="sxs-lookup"><span data-stu-id="85e41-127">To cancel this action, press the ESC key before leaving this field.</span></span>  
  
5.  <span data-ttu-id="85e41-128">В меню **файл** выберите команду **сохранить**_имя таблицы_.</span><span class="sxs-lookup"><span data-stu-id="85e41-128">From the **File** menu choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="85e41-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="85e41-129">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="85e41-130">Переименование таблицы</span><span class="sxs-lookup"><span data-stu-id="85e41-130">To rename a table</span></span>  
  
1.  <span data-ttu-id="85e41-131">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85e41-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="85e41-132">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="85e41-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="85e41-133">В следующем примере столбец `SalesTerritory` в таблице `SalesTerr` переименовывается в `Sales` .</span><span class="sxs-lookup"><span data-stu-id="85e41-133">The following example renames the `SalesTerritory` table to `SalesTerr` in the `Sales` schema.</span></span> <span data-ttu-id="85e41-134">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="85e41-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    EXEC sp_rename 'Sales.SalesTerritory', 'SalesTerr';  
    ```  
  
 <span data-ttu-id="85e41-135">Дополнительные примеры см. в статье [sp_rename (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85e41-135">For additional examples, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
