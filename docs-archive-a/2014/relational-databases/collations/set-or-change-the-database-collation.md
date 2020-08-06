---
title: Установка и изменение параметров сортировки базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], database
- database collations [SQL Server]
ms.assetid: 1379605c-1242-4ac8-ab1b-e2a2b5b1f895
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d7f7c3e3ddba7ba0ea9701993dbe0fad3a8d975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668916"
---
# <a name="set-or-change-the-database-collation"></a><span data-ttu-id="ade1f-102">Установка и изменение параметров сортировки базы данных</span><span class="sxs-lookup"><span data-stu-id="ade1f-102">Set or Change the Database Collation</span></span>
  <span data-ttu-id="ade1f-103">В этом разделе описано, как задать и изменить параметры сортировки базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade1f-103">This topic describes how set and change the database collation in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ade1f-104">Если параметры сортировки не указаны, используются параметры сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="ade1f-104">If no collation is specified, the server collation is used.</span></span>  
  
 <span data-ttu-id="ade1f-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ade1f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ade1f-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ade1f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ade1f-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ade1f-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ade1f-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="ade1f-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ade1f-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ade1f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ade1f-110">**Задание и изменение параметров сортировки базы данных с помощью:**</span><span class="sxs-lookup"><span data-stu-id="ade1f-110">**To set or change the database collation, using:**</span></span>  
  
     [<span data-ttu-id="ade1f-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ade1f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ade1f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ade1f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ade1f-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ade1f-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ade1f-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ade1f-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ade1f-115">Параметры сортировки Windows только для Юникода могут использоваться только с предложением COLLATE для применения параметров сортировки к данным типов `nchar`, `nvarchar` и `ntext` на уровне столбца и на уровне выражения.</span><span class="sxs-lookup"><span data-stu-id="ade1f-115">Windows Unicode-only collations can only be used with the COLLATE clause to apply collations to the `nchar`, `nvarchar`, and `ntext` data types on column level and expression-level data.</span></span> <span data-ttu-id="ade1f-116">Их нельзя использовать с предложением COLLATE для изменения параметров сортировки базы данных или экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="ade1f-116">They cannot be used with the COLLATE clause to change the collation of a database or server instance.</span></span>  
  
-   <span data-ttu-id="ade1f-117">Если указанные или используемые объектом по ссылке параметры сортировки используют кодовую страницу, не поддерживаемую Windows, то компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] выдаст ошибку.</span><span class="sxs-lookup"><span data-stu-id="ade1f-117">If the specified collation or the collation used by the referenced object uses a code page that is not supported by Windows, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] displays an error.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ade1f-118">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="ade1f-118">Recommendations</span></span>  
  
-   <span data-ttu-id="ade1f-119">Имена поддерживаемых параметров сортировки вы можете найти в статьях [Имя параметров сортировки Windows (Transact-SQL)](/sql/t-sql/statements/windows-collation-name-transact-sql) и [Имя параметров сортировки SQL Server (Transact-SQL)](/sql/t-sql/statements/sql-server-collation-name-transact-sql)или воспользоваться системной функцией [sys.fn_helpcollations (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ade1f-119">You can find the supported collation names in [Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) and [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql); or you can use the [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) system function.</span></span>  
  
-   <span data-ttu-id="ade1f-120">Если изменяются параметры сортировки базы данных, то изменяется следующее:</span><span class="sxs-lookup"><span data-stu-id="ade1f-120">When you change the database collation, you change the following:</span></span>  
  
    -   <span data-ttu-id="ade1f-121">Все столбцы типа `char`, `varchar`, `text`, `nchar`, `nvarchar` или `ntext` в системных таблицах заменяются новым параметром сортировки.</span><span class="sxs-lookup"><span data-stu-id="ade1f-121">Any `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` columns in system tables are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="ade1f-122">Все существующие параметры типа `char`, `varchar`, `text`, `nchar`, `nvarchar` или `ntext` и возвращаемые скалярные значения для хранимых процедур и определяемых пользователем функций заменяются новым параметром сортировки.</span><span class="sxs-lookup"><span data-stu-id="ade1f-122">All existing `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` parameters and scalar return values for stored procedures and user-defined functions are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="ade1f-123">Системные типы данных `char`, `varchar`, `text`, `nchar`, `nvarchar` и `ntext` и все определяемые пользователем типы данных, основанные на этих системных типах данных, заменяются новым параметром сортировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ade1f-123">The `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` system data types, and all user-defined data types based on these system data types, are changed to the new default collation.</span></span>  
  
-   <span data-ttu-id="ade1f-124">Можно изменить параметры сортировки любых новых объектов, созданных в пользовательской базе данных, с помощью предложения COLLATE инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ade1f-124">You can change the collation of any new objects that are created in a user database by using the COLLATE clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="ade1f-125">Эта инструкция не изменяет параметры сортировки столбцов в любых существующих пользовательских таблицах.</span><span class="sxs-lookup"><span data-stu-id="ade1f-125">This statement does not change the collation of the columns in any existing user-defined tables.</span></span> <span data-ttu-id="ade1f-126">Он может быть изменен с помощью предложения COLLATE инструкции [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ade1f-126">These can be changed by using the COLLATE clause of [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ade1f-127">безопасность</span><span class="sxs-lookup"><span data-stu-id="ade1f-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ade1f-128">Permissions</span><span class="sxs-lookup"><span data-stu-id="ade1f-128">Permissions</span></span>  
 <span data-ttu-id="ade1f-129">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="ade1f-129">CREATE DATABASE</span></span>  
 <span data-ttu-id="ade1f-130">Требуется разрешение CREATE DATABASE в базе данных **master** , или требуется разрешение CREATE ANY DATABASE или ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="ade1f-130">Requires CREATE DATABASE permission in the **master** database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="ade1f-131">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="ade1f-131">ALTER DATABASE</span></span>  
 <span data-ttu-id="ade1f-132">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="ade1f-132">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ade1f-133">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ade1f-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-or-change-the-database-collation"></a><span data-ttu-id="ade1f-134">Задание и изменение параметров сортировки базы данных</span><span class="sxs-lookup"><span data-stu-id="ade1f-134">To set or change the database collation</span></span>  
  
1.  <span data-ttu-id="ade1f-135">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], разверните его, а затем разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="ade1f-135">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="ade1f-136">При создании новой базы данных щелкните правой кнопкой мыши **Базы данных** и выберите пункт **Создать базу данных**.</span><span class="sxs-lookup"><span data-stu-id="ade1f-136">If you are creating a new database, right-click **Databases** and then click **New Database**.</span></span> <span data-ttu-id="ade1f-137">Если использовать параметры сортировки по умолчанию не нужно, то перейдите на страницу **Параметры** и выберите нужный вариант в раскрывающемся списке **Параметры сортировки** .</span><span class="sxs-lookup"><span data-stu-id="ade1f-137">If you do not want the default collation, click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
     <span data-ttu-id="ade1f-138">Если база данных уже существует, щелкните правой кнопкой мыши нужную базу данных и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ade1f-138">Alternatively, if the database already exists, right-click the database that you want and click **Properties**.</span></span> <span data-ttu-id="ade1f-139">Перейдите на страницу **Параметры** , а затем выберите нужный вариант в раскрывающемся списке **Параметры сортировки** .</span><span class="sxs-lookup"><span data-stu-id="ade1f-139">Click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
3.  <span data-ttu-id="ade1f-140">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ade1f-140">After you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ade1f-141">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ade1f-141">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-database-collation"></a><span data-ttu-id="ade1f-142">Задание параметров сортировки базы данных</span><span class="sxs-lookup"><span data-stu-id="ade1f-142">To set the database collation</span></span>  
  
1.  <span data-ttu-id="ade1f-143">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade1f-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ade1f-144">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ade1f-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ade1f-145">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ade1f-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ade1f-146">В этом примере показано задание параметров сортировки с помощью предложения [COLLATE](/sql/t-sql/statements/collations) .</span><span class="sxs-lookup"><span data-stu-id="ade1f-146">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause to specify a collation name.</span></span> <span data-ttu-id="ade1f-147">В примере создается база данных `MyOptionsTest` , в которой используются параметры сортировки `Latin1_General_100_CS_AS_SC` .</span><span class="sxs-lookup"><span data-stu-id="ade1f-147">The example creates the database `MyOptionsTest` that uses the `Latin1_General_100_CS_AS_SC` collation.</span></span> <span data-ttu-id="ade1f-148">Чтобы проверить параметр, после создания базы данных выполните инструкцию `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="ade1f-148">After you create the database, execute the `SELECT` statement to verify the setting.</span></span>  
  
```sql  
USE master;  
GO  
IF DB_ID (N'MyOptionsTest') IS NOT NULL  
DROP DATABASE MyOptionsTest;  
GO  
CREATE DATABASE MyOptionsTest  
COLLATE Latin1_General_100_CS_AS_SC;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
#### <a name="to-change-the-database-collation"></a><span data-ttu-id="ade1f-149">Изменение параметров сортировки базы данных</span><span class="sxs-lookup"><span data-stu-id="ade1f-149">To change the database collation</span></span>  
  
1.  <span data-ttu-id="ade1f-150">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade1f-150">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ade1f-151">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ade1f-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ade1f-152">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ade1f-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ade1f-153">В этом примере показано изменение имени параметров сортировки с помощью предложения [COLLATE](/sql/t-sql/statements/collations) в инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ade1f-153">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause in an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to change the collation name.</span></span> <span data-ttu-id="ade1f-154">Выполните инструкцию `SELECT` , чтобы проверить изменение.</span><span class="sxs-lookup"><span data-stu-id="ade1f-154">Execute the `SELECT` statement to verify the change.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE MyOptionsTest  
COLLATE French_CI_AS ;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ade1f-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="ade1f-155">See Also</span></span>  
 <span data-ttu-id="ade1f-156">[Поддержка параметров сортировки и Юникода](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="ade1f-156">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="ade1f-157">[sys.fn_helpcollations (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ade1f-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="ade1f-158">[sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ade1f-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="ade1f-159">[Имя параметров сортировки SQL Server (Transact-SQL)](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ade1f-159">[SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="ade1f-160">[Имя параметров сортировки Windows (Transact-SQL)](/sql/t-sql/statements/windows-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ade1f-160">[Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="ade1f-161">[COLLATE (Transact-SQL)](/sql/t-sql/statements/collations) </span><span class="sxs-lookup"><span data-stu-id="ade1f-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span></span>  
 <span data-ttu-id="ade1f-162">[Очередность параметров сортировки (Transact-SQL)](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ade1f-162">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 <span data-ttu-id="ade1f-163">[CREATE TABLE (Transact-SQL)](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ade1f-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="ade1f-164">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ade1f-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="ade1f-165">[ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ade1f-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="ade1f-166">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ade1f-166">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
