---
title: Просмотр или изменение свойств базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- displaying databases
- database viewing [SQL Server]
- databases [SQL Server], viewing
- viewing databases
ms.assetid: 9e8ac097-84b7-46c7-85e3-c1e79f94d747
author: stevestein
ms.author: sstein
ms.openlocfilehash: d6aee7503ca02d47575be4e8103641f61d9696d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749960"
---
# <a name="view-or-change-the-properties-of-a-database"></a><span data-ttu-id="3ab4e-102">Просмотр или изменение свойств базы данных</span><span class="sxs-lookup"><span data-stu-id="3ab4e-102">View or Change the Properties of a Database</span></span>
  <span data-ttu-id="3ab4e-103">В этом разделе описывается просмотр и изменение свойств базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ab4e-103">This topic describes how to view or change the properties of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3ab4e-104">После задания нового значения свойства базы данных изменение вступает в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-104">After you change a database property, the modification takes effect immediately.</span></span>  
  
 <span data-ttu-id="3ab4e-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3ab4e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3ab4e-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3ab4e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3ab4e-107">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="3ab4e-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="3ab4e-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3ab4e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3ab4e-109">**Просмотр или изменение свойств базы данных различными средствами**</span><span class="sxs-lookup"><span data-stu-id="3ab4e-109">**To view or change the properties of a database, using:**</span></span>  
  
     [<span data-ttu-id="3ab4e-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ab4e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3ab4e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ab4e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3ab4e-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3ab4e-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3ab4e-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="3ab4e-113">Recommendations</span></span>  
  
-   <span data-ttu-id="3ab4e-114">Если параметр AUTO_CLOSE имеет значение ON, некоторые столбцы в представлении каталога [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) и функция DATABASEPROPERTYEX будут возвращать значение NULL, так как база данных будет недоступна для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-114">When AUTO_CLOSE is ON, some columns in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view and DATABASEPROPERTYEX function will return NULL because the database is unavailable to retrieve the data.</span></span> <span data-ttu-id="3ab4e-115">Для решения этой проблемы выполните инструкцию USE, чтобы открыть базу данных.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-115">To resolve this, execute a USE statement to open the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3ab4e-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="3ab4e-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3ab4e-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="3ab4e-117">Permissions</span></span>  
 <span data-ttu-id="3ab4e-118">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3ab4e-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ab4e-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-properties-of-a-database"></a><span data-ttu-id="3ab4e-120">Просмотр или изменение свойств базы данных</span><span class="sxs-lookup"><span data-stu-id="3ab4e-120">To view or change the properties of a database</span></span>  
  
1.  <span data-ttu-id="3ab4e-121">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3ab4e-122">Разверните **Базы данных**, правой кнопкой мыши щелкните базу данных для просмотра, затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-122">Expand **Databases**, right-click the database to view, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3ab4e-123">В диалоговом окне **Свойства базы данных** выберите страницу, чтобы просмотреть соответствующие сведения.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-123">In the **Database Properties** dialog box, select a page to view the corresponding information.</span></span> <span data-ttu-id="3ab4e-124">Например, выберите страницу **Файлы** , чтобы просмотреть сведения о файлах данных и журнала.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-124">For example, select the **Files** page to view data and log file information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3ab4e-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ab4e-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-property-of-a-database-by-using-databasepropertyex"></a><span data-ttu-id="3ab4e-126">Просмотр свойства базы данных с помощью функции DATABASEPROPERTYEX</span><span class="sxs-lookup"><span data-stu-id="3ab4e-126">To view a property of a database by using DATABASEPROPERTYEX</span></span>  
  
1.  <span data-ttu-id="3ab4e-127">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ab4e-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3ab4e-128">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3ab4e-129">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3ab4e-130">В этом примере используется системная функция [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) , предназначенная для возвращения состояния параметра базы данных AUTO_SHRINK в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ab4e-130">This example uses the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) system function to return the status of the AUTO_SHRINK database option in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="3ab4e-131">Возвращенное значение 1 означает, что этот параметр установлен в значение ON, а возвращенное значение 0, означает, что параметр имеет значение OFF.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-131">A return value of 1 means that the option is set to ON, and a return value of 0 means that the option is set to OFF.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT DATABASEPROPERTYEX('AdventureWorks2012', 'IsAutoShrink');  
GO  
  
```  
  
#### <a name="to-view-the-properties-of-a-database-by-querying-sysdatabases"></a><span data-ttu-id="3ab4e-132">Просмотр свойств базы данных при помощи запроса к представлению каталога sys.databases</span><span class="sxs-lookup"><span data-stu-id="3ab4e-132">To view the properties of a database by querying sys.databases</span></span>  
  
1.  <span data-ttu-id="3ab4e-133">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ab4e-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3ab4e-134">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3ab4e-135">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3ab4e-136">В этом примере выполняется опрос к представлению каталога [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) для просмотра нескольких свойств базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ab4e-136">This example queries the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to view several properties of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="3ab4e-137">В этом примере возвращается идентификационный номер базы данных (`database_id`), вне зависимости от того, предназначена ли она только для чтения или для чтения и записи (`is_read_only`), параметры сортировки базы данных (`collation_name`) и уровень совместимости базы данных (`compatibility_level`).</span><span class="sxs-lookup"><span data-stu-id="3ab4e-137">This example returns the database ID number (`database_id`), whether the database is read-only or read-write (`is_read_only`), the collation for the database (`collation_name`), and the database compatibility level (`compatibility_level`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT database_id, is_read_only, collation_name, compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-properties-of-a-database"></a><span data-ttu-id="3ab4e-138">Изменение свойств базы данных</span><span class="sxs-lookup"><span data-stu-id="3ab4e-138">To change the properties of a database</span></span>  
  
1.  <span data-ttu-id="3ab4e-139">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ab4e-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3ab4e-140">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3ab4e-141">Скопируйте и вставьте следующий пример в окно запроса.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-141">Copy and paste the following example into the query window.</span></span> <span data-ttu-id="3ab4e-142">В этом примере определяется состояние изоляции моментального снимка в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , выполняется изменение состояния этого свойства и выполняется проверка изменения.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-142">The example determines the state of snapshot isolation on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, changes the state of the property, and then verifies the change.</span></span>  
  
     <span data-ttu-id="3ab4e-143">Чтобы определить состояние изоляции моментального снимка, выберите первую инструкцию `SELECT` и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-143">To determine the state of snapshot isolation, select the first `SELECT` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="3ab4e-144">Чтобы изменить состояние изоляции моментального снимка, выберите инструкцию `ALTER DATABASE` и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-144">To change the state of snapshot isolation, select the `ALTER DATABASE` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="3ab4e-145">Чтобы проверить изменение, выберите вторую инструкцию `SELECT` и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3ab4e-145">To verify the change, select the second `SELECT` statement, and click **Execute**.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase9](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase9)]  
  
## <a name="see-also"></a><span data-ttu-id="3ab4e-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="3ab4e-146">See Also</span></span>  
 <span data-ttu-id="3ab4e-147">[sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3ab4e-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="3ab4e-148">[ALTER DATABASE SET HADR (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="3ab4e-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="3ab4e-149">[Параметры ALTER DATABASE SET (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="3ab4e-149">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="3ab4e-150">[Зеркальное отображение базы данных ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="3ab4e-150">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="3ab4e-151">[Уровень совместимости инструкции ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="3ab4e-151">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 [<span data-ttu-id="3ab4e-152">Параметры инструкции ALTER DATABASE для файлов и файловых групп (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3ab4e-152">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
  
