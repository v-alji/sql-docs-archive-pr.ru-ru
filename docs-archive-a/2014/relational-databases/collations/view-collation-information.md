---
title: Просмотр сведений о параметрах сортировки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], view
ms.assetid: 1338b4ea-7142-44bc-a3b9-44e54431405f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 995e559cfd7ca871f5abd90751f2f79167bdf76f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668908"
---
# <a name="view-collation-information"></a><span data-ttu-id="7353d-102">Просмотр сведений о параметрах сортировки</span><span class="sxs-lookup"><span data-stu-id="7353d-102">View Collation Information</span></span>
    
##  <a name="you-can-view-the-collation-of-a-server-database-or-column-in-ssmanstudiofull-using-object-explorer-menu-options-or-by-using-tsql"></a><a name="Top"></a> <span data-ttu-id="7353d-103">Просмотреть параметры сортировки сервера, базы данных или столбца в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] можно, используя команды меню обозревателя объектов или при помощи инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7353d-103">You can view the collation of a server, database, or column in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
##  <a name="how-to-view-a-collation-setting"></a><a name="Procedures"></a> <span data-ttu-id="7353d-104">Как просмотреть параметры сортировки</span><span class="sxs-lookup"><span data-stu-id="7353d-104">How to View a Collation Setting</span></span>  
 <span data-ttu-id="7353d-105">Можно использовать один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="7353d-105">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="7353d-106">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7353d-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="7353d-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7353d-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7353d-108">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7353d-108">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7353d-109">**Просмотр параметров сортировки для сервера (экземпляра SQL Server) в обозревателе объектов.**</span><span class="sxs-lookup"><span data-stu-id="7353d-109">**To view a collation setting for a server (instance of SQL Server) in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7353d-110">В обозревателе объектов установите соединение с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7353d-110">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7353d-111">Щелкните экземпляр правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7353d-111">Right-click the instance and select **Properties**.</span></span>  
  
 <span data-ttu-id="7353d-112">**Просмотр параметров сортировки для базы данных в обозревателе объектов**</span><span class="sxs-lookup"><span data-stu-id="7353d-112">**To view a collation setting for a database in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7353d-113">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="7353d-113">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7353d-114">Разверните узел **Базы данных**, щелкните базу данных правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7353d-114">Expand **Databases**, right-click the database and select **Properties**.</span></span>  
  
 <span data-ttu-id="7353d-115">**Просмотр параметров сортировки для столбца в обозревателе объектов**</span><span class="sxs-lookup"><span data-stu-id="7353d-115">**To view a collation setting for a column in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7353d-116">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="7353d-116">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7353d-117">Последовательно разверните узел **Базы данных**, базу данных и узел **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="7353d-117">Expand **Databases**, expand the database and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="7353d-118">Разверните таблицу, содержащую столбец и затем разверните **Столбцы**.</span><span class="sxs-lookup"><span data-stu-id="7353d-118">Expand the table that contains the column and then expand **Columns**.</span></span>  
  
4.  <span data-ttu-id="7353d-119">Щелкните правой кнопкой мыши столбец и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7353d-119">Right-click the column and select **Properties**.</span></span> <span data-ttu-id="7353d-120">Если параметры сортировки не указаны, то данный столбец не относится к символьному типу данных.</span><span class="sxs-lookup"><span data-stu-id="7353d-120">If the collation property is empty, the column is not a character data type.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7353d-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7353d-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="7353d-122">**Просмотр параметров сортировки для сервера**</span><span class="sxs-lookup"><span data-stu-id="7353d-122">**To view the collation setting of a server**</span></span>  
  
1.  <span data-ttu-id="7353d-123">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и выберите на панели инструментов команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7353d-123">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7353d-124">В окне запроса введите следующую инструкцию, которая использует системную функцию SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="7353d-124">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, SERVERPROPERTY('collation'));  
    ```  
  
3.  <span data-ttu-id="7353d-125">Кроме того, можно использовать системную хранимую процедуру sp_helpsort.</span><span class="sxs-lookup"><span data-stu-id="7353d-125">Alternatively, you can use the sp_helpsort system stored procedure.</span></span>  
  
    ```  
    EXECUTE sp_helpsort;  
    ```  
  
 <span data-ttu-id="7353d-126">**Просмотр всех параметров сортировки, поддерживаемых [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="7353d-126">**To view all collations supported by [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span></span>  
  
1.  <span data-ttu-id="7353d-127">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и выберите на панели инструментов команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7353d-127">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7353d-128">В окне запроса введите следующую инструкцию, которая использует системную функцию SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="7353d-128">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT name, description FROM sys.fn_helpcollations();  
    ```  
  
 <span data-ttu-id="7353d-129">**Просмотр параметров сортировки для базы данных**</span><span class="sxs-lookup"><span data-stu-id="7353d-129">**To view the collation setting of a database**</span></span>  
  
1.  <span data-ttu-id="7353d-130">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и выберите на панели инструментов команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7353d-130">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7353d-131">В окне запроса введите следующую инструкцию, которая использует системное представление каталога sys.databases.</span><span class="sxs-lookup"><span data-stu-id="7353d-131">In the query window, enter the following statement that uses the sys.databases system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.databases;  
    ```  
  
3.  <span data-ttu-id="7353d-132">Кроме того, можно использовать системную функцию DATABASEPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="7353d-132">Alternatively, you can use the DATABASEPROPERTYEX system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, DATABASEPROPERTYEX('database_name','collation'));  
    ```  
  
 <span data-ttu-id="7353d-133">**Просмотр параметров сортировки для столбца**</span><span class="sxs-lookup"><span data-stu-id="7353d-133">**To view the collation setting of a column**</span></span>  
  
1.  <span data-ttu-id="7353d-134">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и выберите на панели инструментов команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7353d-134">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7353d-135">В окне запроса введите следующую инструкцию, которая использует системное представление каталога sys.columns.</span><span class="sxs-lookup"><span data-stu-id="7353d-135">In the query window, enter the following statement that uses the sys.columns system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.columns WHERE name = N'<insert character data type column name>';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7353d-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="7353d-136">See Also</span></span>  
 <span data-ttu-id="7353d-137">[SERVERPROPERTY (Transact-SQL)](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7353d-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="7353d-138">[sys.fn_helpcollations (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7353d-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="7353d-139">[sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7353d-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="7353d-140">[sys.columns (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7353d-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span></span>  
 <span data-ttu-id="7353d-141">[Очередность параметров сортировки (Transact-SQL)](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7353d-141">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 [<span data-ttu-id="7353d-142">sp_helpsort (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7353d-142">sp_helpsort &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-helpsort-transact-sql)  
  
  
