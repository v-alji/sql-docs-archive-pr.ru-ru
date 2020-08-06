---
title: Параметры сортировки и кодовые страницы | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c626dcac-0474-432d-acc0-cfa643345372
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab904771fa8ac4acf25a624cbf3e1139f7e96434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665581"
---
# <a name="collations-and-code-pages"></a><span data-ttu-id="e0a6e-102">Параметры сортировки и кодовые страницы</span><span class="sxs-lookup"><span data-stu-id="e0a6e-102">Collations and Code Pages</span></span>
  [!INCLUDE[hek_2](../includes/hek-2-md.md)] <span data-ttu-id="e0a6e-103">имеет ограничения на поддерживаемые кодовые страницы для столбцов (var)char в оптимизированных для памяти таблицах и на параметры сортировки, используемые в индексах и скомпилированные в собственном коде в хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-103">has restrictions on supported code pages for (var)char columns in memory-optimized tables and supported collations used in indexes and natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="e0a6e-104">Кодовая страница для значений a (var)char определяет сопоставление символов и байтовое представление, которое хранится в таблице.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-104">The code page for a (var)char value determines the mapping between characters and the byte representation that is stored in the table.</span></span> <span data-ttu-id="e0a6e-105">Например, в кодовой странице 1252 (Latin1 Windows; по умолчанию [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]) символ «a» соответствует байту 0x61.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-105">For example, with the Windows Latin 1 code page (1252; the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default), the character 'a' corresponds to the byte 0x61.</span></span>  
  
 <span data-ttu-id="e0a6e-106">Кодовая страница значения (var)char определяется параметрами сортировки, связанными со значением.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-106">The code page of a (var)char value is determined by the collation associated with the value.</span></span> <span data-ttu-id="e0a6e-107">Например, параметры сортировки SQL_Latin1_General_CP1_CI_AS имеют связанную кодовую страницу 1252.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-107">For example, the collation SQL_Latin1_General_CP1_CI_AS has the associated code page 1252.</span></span>  
  
 <span data-ttu-id="e0a6e-108">Параметры сортировки значения наследуются от параметров сортировки базы данных или могут быть заданы явным образом с помощью ключевого слова COLLATE.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-108">The collation of a value is either inherited from the database collation, or can be specified explicitly using the COLLATE keyword.</span></span> <span data-ttu-id="e0a6e-109">Параметры сортировки базы данных нельзя изменить, если база данных содержит таблицы, оптимизированные для памяти, или скомпилированные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-109">Database collation cannot be changed if the database contains memory-optimized tables or natively compiled stored procedures.</span></span> <span data-ttu-id="e0a6e-110">Следующий пример устанавливает параметры сортировки базы данных и создает таблицу, которая содержит столбец с иными параметрами сортировки.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-110">The following example sets the database collation and creates a table, which has a column with a different collation.</span></span> <span data-ttu-id="e0a6e-111">База данных использует параметры сортировки Latin без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-111">The database uses Latin case-insensitive collation.</span></span>  
  
 <span data-ttu-id="e0a6e-112">Индексы могут создаваться только для столбцов строкового типа, если они используют параметры сортировки BIN2.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-112">Indexes can only be created on string columns if they use a BIN2 collation.</span></span> <span data-ttu-id="e0a6e-113">Переменная LastName использует параметры сортировки BIN2.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-113">The LastName variable uses BIN2 collation.</span></span> <span data-ttu-id="e0a6e-114">FirstName использует значение по умолчанию для базы данных CI_AS (без учета регистра, с учетом диакритических знаков).</span><span class="sxs-lookup"><span data-stu-id="e0a6e-114">FirstName uses the database default, which is CI_AS (case-insensitive, accent-sensitive).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e0a6e-115">Нельзя использовать функции упорядочивания и группировки в столбцах строк индекса, в которых не используются параметры сортировки BIN2.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-115">You cannot use order by or group by on index string columns that do not use BIN2 collation.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP  
  
ALTER DATABASE IMOLTP ADD FILEGROUP IMOLTP_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP ADD FILE( NAME = 'IMOLTP_mod' , FILENAME = 'c:\data\IMOLTP_mod') TO FILEGROUP IMOLTP_mod;  
--GO  
  
--  set the database collations  
ALTER DATABASE IMOLTP COLLATE Latin1_General_100_CI_AS  
GO  
  
--  
USE IMOLTP   
GO  
  
-- create a table with collation  
CREATE TABLE Employees (  
  EmployeeID int NOT NULL ,   
  LastName nvarchar(20) COLLATE Latin1_General_100_BIN2 NOT NULL INDEX IX_LastName NONCLUSTERED,   
  FirstName nvarchar(10) NOT NULL ,  
  CONSTRAINT PK_Employees PRIMARY KEY NONCLUSTERED HASH(EmployeeID)  WITH (BUCKET_COUNT=1024)  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_AND_DATA)  
GO  
```  
  
 <span data-ttu-id="e0a6e-116">Следующие ограничения применяются к таблицам, оптимизированным для памяти, и хранимым процедурам, скомпилированным в собственном коде:</span><span class="sxs-lookup"><span data-stu-id="e0a6e-116">The following restrictions apply to memory-optimized tables and natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="e0a6e-117">Столбцы (var)char в таблицах, оптимизированных для памяти, должны использовать параметры сортировки кодовой страницы 1252.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-117">(var)char columns in memory-optimized tables must use code page 1252 collation.</span></span> <span data-ttu-id="e0a6e-118">Данное ограничение не относится к столбцам n(var)char.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-118">This restriction does not apply to n(var)char columns.</span></span> <span data-ttu-id="e0a6e-119">Следующий код извлекает все параметры сортировки 1252:</span><span class="sxs-lookup"><span data-stu-id="e0a6e-119">The following code retrieves all 1252 collations:</span></span>  
  
    ```sql  
    -- all supported collations for (var)char columns in memory-optimized tables  
    select * from sys.fn_helpcollations()  
    where collationproperty(name, 'codepage') = 1252;  
    ```  
  
     <span data-ttu-id="e0a6e-120">Если необходимо сохранять символы, отличные от латиницы, используйте столбцы n(var)char.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-120">If you need to store non-Latin characters, use n(var)char columns.</span></span>  
  
-   <span data-ttu-id="e0a6e-121">Индексы столбцов (n)var(char) могут быть определены только с параметрами сортировки BIN2 (см. первый пример).</span><span class="sxs-lookup"><span data-stu-id="e0a6e-121">Indexes on (n)(var)char columns can only be specified with BIN2 collations (see the first example).</span></span> <span data-ttu-id="e0a6e-122">Следующий запрос получает все поддерживаемые параметры сортировки BIN2:</span><span class="sxs-lookup"><span data-stu-id="e0a6e-122">The following query retrieves all supported BIN2 collations:</span></span>  
  
    ```sql  
    -- all supported collations for indexes on memory-optimized tables and   
    -- comparison/sorting in natively compiled stored procedures  
    select * from sys.fn_helpcollations() where name like '%BIN2'  
    ```  
  
     <span data-ttu-id="e0a6e-123">Если доступ к таблице осуществляется через интерпретируемый [!INCLUDE[tsql](../includes/tsql-md.md)], можно использовать ключевое слово `COLLATE` для изменения параметров сортировки с выражениями или операциями сортировки.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-123">If you access the table through interpreted [!INCLUDE[tsql](../includes/tsql-md.md)], you can use the `COLLATE` keyword to change the collation with expressions or sort operations.</span></span> <span data-ttu-id="e0a6e-124">Образец этого см. в последнем примере.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-124">See the last example for a sample of this.</span></span>  
  
-   <span data-ttu-id="e0a6e-125">Скомпилированные хранимые процедуры не могут использовать параметры, локальные переменные и строковые константы типа (var)char, если параметры сортировки базы данных отличаются от кодовой страницы 1252.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-125">Natively compiled stored procedures cannot use parameters, local variables, or string constants of (var)char type if the database collation is not a code page 1252 collation.</span></span>  
  
-   <span data-ttu-id="e0a6e-126">Все выражения и операции сортировки в хранимых процедурах, скомпилированных в собственном коде, должны использовать параметры сортировки BIN2.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-126">All expressions and sort operations inside natively compiled stored procedures must use BIN2 collations.</span></span> <span data-ttu-id="e0a6e-127">Подразумевается, что все сравнения и операции сортировки создаются на основе кодовых точек символов Юникода (двоичных представлений).</span><span class="sxs-lookup"><span data-stu-id="e0a6e-127">The implication is that all comparisons and sort operations are based on the Unicode code points of the characters (binary representations).</span></span> <span data-ttu-id="e0a6e-128">Например, все сортировки выполняются с учетом регистра («Z» находится перед «a»).</span><span class="sxs-lookup"><span data-stu-id="e0a6e-128">For example all sorting is case sensitive ('Z' comes before 'a').</span></span> <span data-ttu-id="e0a6e-129">При необходимости используйте интерпретируемый [!INCLUDE[tsql](../includes/tsql-md.md)] без учета регистра для сортировки и сравнения.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-129">If necessary, use interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] for case-insensitive sorting and comparison.</span></span>  
  
-   <span data-ttu-id="e0a6e-130">Усечение данных UTF-16, неподдерживаемых внутри хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-130">Truncation of UTF-16 data is not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="e0a6e-131">Это означает, что значения n (VAR) char (*n*) не могут быть преобразованы в тип n (VAR) char (*i*) *, если*  <  *n*параметры сортировки имеют _SC свойство.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-131">This means that n(var)char(*n*) values cannot be converted to type n(var)char(*i*), if *i* < *n*, if the collation has _SC property.</span></span> <span data-ttu-id="e0a6e-132">Например, следующее выражение не поддерживается:</span><span class="sxs-lookup"><span data-stu-id="e0a6e-132">For example, the following is not supported:</span></span>  
  
    ```sql  
    -- column definition using an _SC collation  
     c2 nvarchar(200) collate Latin1_General_100_CS_AS_SC not null   
    -- assignment to a smaller variable, requiring truncation  
     declare @c2 nvarchar(100) = '';  
     select @c2 = c2  
    ```  
  
     <span data-ttu-id="e0a6e-133">Функции обработки строк, такие как LEN, SUBSTRING, LTRIM и RTRIM, с данными UTF-16 не поддерживаются в хранимых процедурах, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-133">String manipulation functions, such as LEN, SUBSTRING, LTRIM, and RTRIM with UTF-16 data are not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="e0a6e-134">Нельзя использовать эти функции для значений типа n(var)char с параметрами сортировки _SC.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-134">You cannot use these string manipulation functions for n(var)char values that have an _SC collation.</span></span>  
  
     <span data-ttu-id="e0a6e-135">Объявляйте переменные с типами, объем памяти которых позволит избежать усечения.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-135">Declare variables using types that are large enough to avoid truncation.</span></span>  
  
 <span data-ttu-id="e0a6e-136">В следующем примере показаны некоторые последствия и решения для ограничений параметров сортировки в OLTP в памяти.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-136">The following example shows some of the implications and workarounds for the collation limitations in In-Memory OLTP.</span></span> <span data-ttu-id="e0a6e-137">В примере используется приведенная выше таблица Employees.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-137">The example uses the Employees table specified above.</span></span> <span data-ttu-id="e0a6e-138">В этом примере список всех сотрудников.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-138">This sample list all employees .</span></span> <span data-ttu-id="e0a6e-139">Обратите внимание, что для LastName вследствие параметров двоичной сортировки имена в верхнем регистре варианта сортируются раньше имен в нижнем регистре.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-139">Notice that for LastName, due to the binary collation, the upper case names are sorted before lower case.</span></span> <span data-ttu-id="e0a6e-140">Поэтому «Thomas» предшествует «nolan», так как символы в верхнем регистре имеют более низкие кодовые точки.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-140">Therefore, 'Thomas' comes before 'nolan' because upper case characters have lower code points.</span></span> <span data-ttu-id="e0a6e-141">FirstName имеет параметры сортировки без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-141">FirstName has a case-insensitive collation.</span></span> <span data-ttu-id="e0a6e-142">Поэтому сортировка выполняется по буквам алфавита, а не кодовым точкам символов.</span><span class="sxs-lookup"><span data-stu-id="e0a6e-142">So, sorting is by letter of the alphabet, not code point of the characters.</span></span>  
  
```sql  
-- insert a number of values  
INSERT Employees VALUES (1,'thomas', 'john')  
INSERT Employees VALUES (2,'Thomas', 'rupert')  
INSERT Employees VALUES (3,'Thomas', 'Jack')  
INSERT Employees VALUES (4,'Thomas', 'annie')  
INSERT Employees VALUES (5,'nolan', 'John')  
GO  
  
-- ===========  
SELECT EmployeeID, LastName, FirstName FROM Employees  
ORDER BY LastName, FirstName  
GO  
  
-- ===========  
-- specify collation: sorting uses case-insensitive collation, thus 'nolan' comes before 'Thomas'  
SELECT * FROM Employees  
ORDER BY LastName COLLATE Latin1_General_100_CI_AS, FirstName  
GO  
  
-- ===========  
-- retrieve employee by Name  
-- must use BIN2 collation for comparison in natively compiled stored procedures  
CREATE PROCEDURE usp_EmployeeByName @LastName nvarchar(20), @FirstName nvarchar(10)  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH   
(  TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
  LANGUAGE = N'us_english'  
)  
  SELECT EmployeeID, LastName, FirstName FROM dbo.Employees  
  WHERE   
    LastName = @LastName AND  
    FirstName COLLATE Latin1_General_100_BIN2 = @FirstName  
  
END  
GO  
  
-- this does not return any rows, as EmployeeID 1 has first name 'john', which is not equal to 'John' in a binary collation  
EXEC usp_EmployeeByName 'thomas', 'John'  
  
-- this retrieves EmployeeID 1  
EXEC usp_EmployeeByName 'thomas', 'john'  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0a6e-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0a6e-143">See Also</span></span>  
 [<span data-ttu-id="e0a6e-144">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="e0a6e-144">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
