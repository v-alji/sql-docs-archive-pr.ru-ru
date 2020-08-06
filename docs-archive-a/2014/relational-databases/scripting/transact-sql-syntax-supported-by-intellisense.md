---
title: Синтаксис языка Transact-SQL, поддерживаемый технологией IntelliSense
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL IntelliSense
- IntelliSense [SQL Server], Transact-SQL syntax
ms.assetid: 194e8f4f-fd7e-4f32-a169-f23531128004
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d34fc79dd7817e64b34b61083415477860ce97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733834"
---
# <a name="transact-sql-syntax-supported-by-intellisense"></a><span data-ttu-id="c8d05-102">Синтаксис языка Transact-SQL, поддерживаемый технологией IntelliSense</span><span class="sxs-lookup"><span data-stu-id="c8d05-102">Transact-SQL Syntax Supported by IntelliSense</span></span>
  <span data-ttu-id="c8d05-103">В этом разделе описываются инструкции и элементы синтаксиса [!INCLUDE[tsql](../../includes/tsql-md.md)] , которые поддерживаются технологией IntelliSense в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8d05-103">This topic describes the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and syntax elements that are supported by IntelliSense in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="statements-supported-by-intellisense"></a><span data-ttu-id="c8d05-104">Инструкции, поддерживаемые технологией IntelliSense</span><span class="sxs-lookup"><span data-stu-id="c8d05-104">Statements Supported by IntelliSense</span></span>  
 <span data-ttu-id="c8d05-105">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]технология IntelliSense поддерживается только для наиболее часто используемых инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8d05-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense supports only the most commonly used [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="c8d05-106">Некоторые общие условия редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] могут блокировать работу технологии IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c8d05-106">Some general [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor conditions might prevent IntelliSense from functioning.</span></span> <span data-ttu-id="c8d05-107">Дополнительные сведения см. в разделе [Устранение сбоев в работе IntelliSense (среда SQL Server Management Studio)](troubleshooting-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="c8d05-107">For more information, see [Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8d05-108">Технология IntelliSense недоступна для зашифрованных объектов баз данных, например зашифрованных хранимых процедур или определяемых пользователем функций.</span><span class="sxs-lookup"><span data-stu-id="c8d05-108">IntelliSense is not available for encrypted database objects, such as encrypted stored procedures or user-defined functions.</span></span> <span data-ttu-id="c8d05-109">Справка и краткие сведения по параметрам недоступны для параметров расширенных хранимых процедур и определяемых пользователем типов при интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="c8d05-109">Parameter help and Quick Info are not available for the parameters of extended stored procedures and CLR Integration user-defined types.</span></span>  
  
### <a name="select-statement"></a><span data-ttu-id="c8d05-110">Инструкция SELECT</span><span class="sxs-lookup"><span data-stu-id="c8d05-110">SELECT Statement</span></span>  
 <span data-ttu-id="c8d05-111">Редактор запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] обеспечивает поддержку технологии IntelliSense для следующих синтаксических элементов в инструкции SELECT:</span><span class="sxs-lookup"><span data-stu-id="c8d05-111">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor provides IntelliSense support for the following syntax elements in the SELECT statement:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c8d05-112">SELECT</span><span class="sxs-lookup"><span data-stu-id="c8d05-112">SELECT</span></span>|<span data-ttu-id="c8d05-113">WHERE</span><span class="sxs-lookup"><span data-stu-id="c8d05-113">WHERE</span></span>|  
|<span data-ttu-id="c8d05-114">FROM</span><span class="sxs-lookup"><span data-stu-id="c8d05-114">FROM</span></span>|<span data-ttu-id="c8d05-115">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="c8d05-115">ORDER BY</span></span>|  
|<span data-ttu-id="c8d05-116">HAVING</span><span class="sxs-lookup"><span data-stu-id="c8d05-116">HAVING</span></span>|<span data-ttu-id="c8d05-117">UNION</span><span class="sxs-lookup"><span data-stu-id="c8d05-117">UNION</span></span>|  
|<span data-ttu-id="c8d05-118">FOR</span><span class="sxs-lookup"><span data-stu-id="c8d05-118">FOR</span></span>|<span data-ttu-id="c8d05-119">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="c8d05-119">GROUP BY</span></span>|  
|<span data-ttu-id="c8d05-120">В начало</span><span class="sxs-lookup"><span data-stu-id="c8d05-120">TOP</span></span>|<span data-ttu-id="c8d05-121">OPTION (указание)</span><span class="sxs-lookup"><span data-stu-id="c8d05-121">OPTION (hint)</span></span>|  
  
### <a name="additional-transact-sql-statements-that-are-supported"></a><span data-ttu-id="c8d05-122">Дополнительные поддерживаемые инструкции Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8d05-122">Additional Transact-SQL Statements That Are Supported</span></span>  
 <span data-ttu-id="c8d05-123">Редактор запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] также обеспечивает поддержку технологии IntelliSense для инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] , приведенных в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="c8d05-123">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor also provides IntelliSense support for [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are shown in the following table.</span></span>  
  
|<span data-ttu-id="c8d05-124">Инструкция Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8d05-124">Transact-SQL statement</span></span>|<span data-ttu-id="c8d05-125">Поддерживаемый синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8d05-125">Syntax supported</span></span>|  
|-----------------------------|----------------------|  
|[<span data-ttu-id="c8d05-126">INSERT</span><span class="sxs-lookup"><span data-stu-id="c8d05-126">INSERT</span></span>](/sql/t-sql/statements/insert-transact-sql)|<span data-ttu-id="c8d05-127">Все синтаксические конструкции, кроме предложения *execute_statement* .</span><span class="sxs-lookup"><span data-stu-id="c8d05-127">All syntax, except the *execute_statement* clause.</span></span>|  
|[<span data-ttu-id="c8d05-128">UPDATE</span><span class="sxs-lookup"><span data-stu-id="c8d05-128">UPDATE</span></span>](/sql/t-sql/queries/update-transact-sql)|<span data-ttu-id="c8d05-129">Все синтаксические конструкции.</span><span class="sxs-lookup"><span data-stu-id="c8d05-129">All syntax.</span></span>|  
|[<span data-ttu-id="c8d05-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="c8d05-130">DELETE</span></span>](/sql/t-sql/statements/delete-transact-sql)|<span data-ttu-id="c8d05-131">Все синтаксические конструкции.</span><span class="sxs-lookup"><span data-stu-id="c8d05-131">All syntax.</span></span>|  
|[<span data-ttu-id="c8d05-132">ДЕКЛАРИРОВАТЬ@local_variable</span><span class="sxs-lookup"><span data-stu-id="c8d05-132">DECLARE @local_variable</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)|<span data-ttu-id="c8d05-133">Все синтаксические конструкции.</span><span class="sxs-lookup"><span data-stu-id="c8d05-133">All syntax.</span></span>|  
|[<span data-ttu-id="c8d05-134">ПАРАМЕТР@local_variable</span><span class="sxs-lookup"><span data-stu-id="c8d05-134">SET @local_variable</span></span>](/sql/t-sql/language-elements/set-local-variable-transact-sql)|<span data-ttu-id="c8d05-135">Все синтаксические конструкции.</span><span class="sxs-lookup"><span data-stu-id="c8d05-135">All syntax.</span></span>|  
|[<span data-ttu-id="c8d05-136">РАБОТАТЬ</span><span class="sxs-lookup"><span data-stu-id="c8d05-136">EXECUTE</span></span>](/sql/t-sql/language-elements/execute-transact-sql)|<span data-ttu-id="c8d05-137">Выполнение определяемых пользователем хранимых процедур, системных хранимых процедур, определяемых пользователем функций и системных функций.</span><span class="sxs-lookup"><span data-stu-id="c8d05-137">Execution of user-defined stored procedures, system stored procedures, user-defined functions, and system functions.</span></span>|  
|[<span data-ttu-id="c8d05-138">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="c8d05-138">CREATE TABLE</span></span>](/sql/t-sql/statements/create-table-transact-sql)|<span data-ttu-id="c8d05-139">Все синтаксические конструкции.</span><span class="sxs-lookup"><span data-stu-id="c8d05-139">All syntax.</span></span>|  
|[<span data-ttu-id="c8d05-140">CREATE VIEW</span><span class="sxs-lookup"><span data-stu-id="c8d05-140">CREATE VIEW</span></span>](/sql/t-sql/statements/create-view-transact-sql)|<span data-ttu-id="c8d05-141">Все синтаксические конструкции.</span><span class="sxs-lookup"><span data-stu-id="c8d05-141">All syntax.</span></span>|  
|[<span data-ttu-id="c8d05-142">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="c8d05-142">CREATE PROCEDURE</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)|<span data-ttu-id="c8d05-143">Все синтаксические конструкции, кроме следующих.</span><span class="sxs-lookup"><span data-stu-id="c8d05-143">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="c8d05-144">Для предложения EXTERNAL NAME технология IntelliSense не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c8d05-144">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="c8d05-145">В предложении AS технология IntelliSense поддерживается только для тех инструкций и синтаксических конструкций, которые перечислены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c8d05-145">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="c8d05-146">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="c8d05-146">ALTER PROCEDURE</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)|<span data-ttu-id="c8d05-147">Все синтаксические конструкции, кроме следующих.</span><span class="sxs-lookup"><span data-stu-id="c8d05-147">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="c8d05-148">Для предложения EXTERNAL NAME технология IntelliSense не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c8d05-148">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="c8d05-149">В предложении AS технология IntelliSense поддерживается только для тех инструкций и синтаксических конструкций, которые перечислены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c8d05-149">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="c8d05-150">ИСПОЛЬЗУЕТ</span><span class="sxs-lookup"><span data-stu-id="c8d05-150">USE</span></span>](/sql/t-sql/language-elements/use-transact-sql)|<span data-ttu-id="c8d05-151">Все синтаксические конструкции.</span><span class="sxs-lookup"><span data-stu-id="c8d05-151">All syntax.</span></span>|  
  
## <a name="intellisense-in-supported-statements"></a><span data-ttu-id="c8d05-152">Технология IntelliSense в поддерживаемых инструкциях</span><span class="sxs-lookup"><span data-stu-id="c8d05-152">IntelliSense in Supported Statements</span></span>  
 <span data-ttu-id="c8d05-153">В редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] технология IntelliSense поддерживается для следующих синтаксических элементов при их использовании в одной из поддерживаемых инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c8d05-153">IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following syntax elements when they are used in one of the supported [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
-   <span data-ttu-id="c8d05-154">Все типы соединений, включая APPLY</span><span class="sxs-lookup"><span data-stu-id="c8d05-154">All join types, including APPLY</span></span>  
  
-   <span data-ttu-id="c8d05-155">PIVOT и UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="c8d05-155">PIVOT and UNPIVOT</span></span>  
  
-   <span data-ttu-id="c8d05-156">Ссылки на следующие объекты базы данных.</span><span class="sxs-lookup"><span data-stu-id="c8d05-156">References to the following database objects:</span></span>  
  
    -   <span data-ttu-id="c8d05-157">Базы данных и схемы</span><span class="sxs-lookup"><span data-stu-id="c8d05-157">Databases and schemas</span></span>  
  
    -   <span data-ttu-id="c8d05-158">Таблицы, представления, функции с табличным значением и табличные выражения</span><span class="sxs-lookup"><span data-stu-id="c8d05-158">Tables, views, table-valued functions, and table expressions</span></span>  
  
    -   <span data-ttu-id="c8d05-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="c8d05-159">Columns</span></span>  
  
    -   <span data-ttu-id="c8d05-160">Процедуры и параметры процедур</span><span class="sxs-lookup"><span data-stu-id="c8d05-160">Procedures and procedure parameters</span></span>  
  
    -   <span data-ttu-id="c8d05-161">Скалярные функции и скалярные выражения</span><span class="sxs-lookup"><span data-stu-id="c8d05-161">Scalar functions and scalar expressions</span></span>  
  
    -   <span data-ttu-id="c8d05-162">Локальные переменные</span><span class="sxs-lookup"><span data-stu-id="c8d05-162">Local variables</span></span>  
  
    -   <span data-ttu-id="c8d05-163">Обобщенные табличные выражения</span><span class="sxs-lookup"><span data-stu-id="c8d05-163">Common table expressions (CTE)</span></span>  
  
-   <span data-ttu-id="c8d05-164">Объекты базы данных, ссылки на которые имеются только в инструкциях CREATE или ALTER в скрипте или пакете, но которые не существуют в базе данных, поскольку скрипт или пакет еще не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="c8d05-164">Database objects that are referenced only in CREATE or ALTER statements in the script or batch, but which do not exist in the database because the script or batch has not yet been run.</span></span> <span data-ttu-id="c8d05-165">Ниже приведены эти объекты.</span><span class="sxs-lookup"><span data-stu-id="c8d05-165">These objects are as follows:</span></span>  
  
    -   <span data-ttu-id="c8d05-166">Таблицы и процедуры, указанные в инструкции CREATE TABLE или CREATE PROCEDURE в скрипте или пакете.</span><span class="sxs-lookup"><span data-stu-id="c8d05-166">Tables and procedures that have been specified in a CREATE TABLE or CREATE PROCEDURE statement in the script or batch.</span></span>  
  
    -   <span data-ttu-id="c8d05-167">Изменения в таблицах и процедурах, указанных в инструкции ALTER TABLE или ALTER PROCEDURE в скрипте или пакете.</span><span class="sxs-lookup"><span data-stu-id="c8d05-167">Changes to tables and procedures that have been specified in an ALTER TABLE or ALTER PROCEDURE statement in the script or batch.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8d05-168">Технология IntelliSense недоступна для столбцов инструкции CREATE VIEW, пока инструкция CREATE VIEW не будет исполнена.</span><span class="sxs-lookup"><span data-stu-id="c8d05-168">IntelliSense is not available for the columns of a CREATE VIEW statement until the CREATE VIEW statement has been executed.</span></span>  
  
 <span data-ttu-id="c8d05-169">Поддержка технологии IntelliSense для приведенных ранее элементов при их использовании в других инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)] не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="c8d05-169">IntelliSense is not provided for the previously listed elements when they are used in other [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="c8d05-170">Например, поддержка технологии IntelliSense предоставляется для имен столбцов, которые используются в инструкции SELECT, но не для столбцов, используемых в инструкции CREATE FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="c8d05-170">For example, there is IntelliSense support for column names that are used in a SELECT statement, but not for columns that are used in the CREATE FUNCTION statement.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c8d05-171">Примеры</span><span class="sxs-lookup"><span data-stu-id="c8d05-171">Examples</span></span>  
 <span data-ttu-id="c8d05-172">Внутри скрипта или пакета [!INCLUDE[tsql](../../includes/tsql-md.md)] технология IntelliSense в редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] поддерживается только для тех инструкций и синтаксических конструкций, которые перечислены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c8d05-172">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports only the statements and syntax that are listed in this topic.</span></span> <span data-ttu-id="c8d05-173">В следующих примерах кода [!INCLUDE[tsql](../../includes/tsql-md.md)] показано, для каких инструкций и элементов синтаксиса поддерживается технология IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c8d05-173">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code examples show what statements and syntax elements IntelliSense supports.</span></span> <span data-ttu-id="c8d05-174">Например, в приведенном ниже пакете технология IntelliSense доступна для инструкции `SELECT`, когда она используется в коде самостоятельно, а не `SELECT` содержится в инструкции `CREATE FUNCTION`.</span><span class="sxs-lookup"><span data-stu-id="c8d05-174">For example, in the following batch, IntelliSense is available for the `SELECT` statement when it is coded by itself, but not when the `SELECT` is contained in a `CREATE FUNCTION` statement.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Name  
FROM Production.Product  
WHERE Name LIKE N'Road-250%' and Color = N'Red';  
GO  
CREATE FUNCTION Production.ufn_Red250 ()  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT Name  
    FROM AdventureWorks2012.Production.Product  
    WHERE Name LIKE N'Road-250%'  
      AND Color = N'Red'  
);GO  
```  
  
 <span data-ttu-id="c8d05-175">Эта функциональность также применяется к наборам инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] в предложении AS инструкций CREATE PROCEDURE или ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="c8d05-175">This functionality also applies to the sets of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the AS clause of a CREATE PROCEDURE or ALTER PROCEDURE statement.</span></span>  
  
 <span data-ttu-id="c8d05-176">Внутри скрипта или пакета [!INCLUDE[tsql](../../includes/tsql-md.md)] поддержка технологии IntelliSense обеспечивается для объектов, указанных в инструкции CREATE или ALTER. Однако эти объекты не существуют в базе данных, так как инструкции еще не выполнялись.</span><span class="sxs-lookup"><span data-stu-id="c8d05-176">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense supports objects that have been specified in a CREATE or ALTER statement; however, these objects do not exist in the database because the statements have not been executed.</span></span> <span data-ttu-id="c8d05-177">Например, в редакторе запросов можно ввести следующий код:</span><span class="sxs-lookup"><span data-stu-id="c8d05-177">For example, you might enter the following code in the Query Editor:</span></span>  
  
```  
USE MyTestDB;  
GO  
CREATE TABLE MyTable  
    (PrimaryKeyCol   INT PRIMARY KEY,  
    FirstNameCol      NVARCHAR(50),  
   LastNameCol       NVARCHAR(50));  
GO  
SELECT   
```  
  
 <span data-ttu-id="c8d05-178">После ввода инструкции `SELECT`технология IntelliSense выдаст список, содержащий в качестве возможных вариантов выбора **PrimaryKeyCol**, **FirstNameCol**и **LastNameCol** даже в том случае, если скрипт еще не выполнялся и таблица `MyTable` пока не существует в базе данных `MyTestDB`.</span><span class="sxs-lookup"><span data-stu-id="c8d05-178">After you type `SELECT`, IntelliSense lists **PrimaryKeyCol**, **FirstNameCol**, and **LastNameCol** as possible elements in the select list, even if the script has not been executed and `MyTable` does not yet exist in `MyTestDB`.</span></span>  
  
  
