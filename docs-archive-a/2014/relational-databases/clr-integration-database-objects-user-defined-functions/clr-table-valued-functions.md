---
title: Функции CLR с табличным значением | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- Transact-SQL table-valued functions
- table-valued functions [CLR integration]
- TVFs [CLR integration]
ms.assetid: 9a6133ea-36e9-45bf-b572-1c0df3d6c194
author: rothja
ms.author: jroth
ms.openlocfilehash: b700aba5a753ecd8ee50ee9b7679cafb2f1f8581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664952"
---
# <a name="clr-table-valued-functions"></a><span data-ttu-id="57cce-102">Функции среды CLR с табличным значением</span><span class="sxs-lookup"><span data-stu-id="57cce-102">CLR Table-Valued Functions</span></span>
  <span data-ttu-id="57cce-103">Функция с табличным значением представляет собой определяемую пользователем функцию, которая возвращает таблицу.</span><span class="sxs-lookup"><span data-stu-id="57cce-103">A table-valued function is a user-defined function that returns a table.</span></span>  
  
 <span data-ttu-id="57cce-104">Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] расширяет возможности возвращающих табличное значение функций, позволяя определить функцию с табличным значением на любом управляемом языке.</span><span class="sxs-lookup"><span data-stu-id="57cce-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extends the functionality of table-valued functions by allowing you to define a table-valued function in any managed language.</span></span> <span data-ttu-id="57cce-105">Функция с табличным значением возвращает данные через объект `IEnumerable` или `IEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="57cce-105">Data is returned from a table-valued function through an `IEnumerable` or `IEnumerator` object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="57cce-106">Для функций с табличным значением столбцы возвращаемого табличного типа не могут включать столбцы отметок времени и столбцы строкового типа данных не в Юникоде (например, `char`, `varchar` и `text`).</span><span class="sxs-lookup"><span data-stu-id="57cce-106">For table-valued functions, the columns of the return table type cannot include timestamp columns or non-Unicode string data type columns (such as `char`, `varchar`, and `text`).</span></span> <span data-ttu-id="57cce-107">Ограничение NOT NULL не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57cce-107">The NOT NULL constraint is not supported.</span></span>  
  
## <a name="differences-between-transact-sql-and-clr-table-valued-functions"></a><span data-ttu-id="57cce-108">Различия между функциями Transact-SQL и среды CLR с табличным значением</span><span class="sxs-lookup"><span data-stu-id="57cce-108">Differences Between Transact-SQL and CLR Table-Valued Functions</span></span>  
 <span data-ttu-id="57cce-109">Возвращающие табличное значение функции [!INCLUDE[tsql](../../includes/tsql-md.md)] материализуют результаты вызова в промежуточной таблице.</span><span class="sxs-lookup"><span data-stu-id="57cce-109">[!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued functions materialize the results of calling the function into an intermediate table.</span></span> <span data-ttu-id="57cce-110">По этой причине они поддерживают в результатах ограничения и уникальные индексы.</span><span class="sxs-lookup"><span data-stu-id="57cce-110">Since they use an intermediate table, they can support constraints and unique indexes over the results.</span></span> <span data-ttu-id="57cce-111">Это исключительно полезно при возвращении результатов большого объема.</span><span class="sxs-lookup"><span data-stu-id="57cce-111">These features can be extremely useful when large results are returned.</span></span>  
  
 <span data-ttu-id="57cce-112">Функции CLR с табличным значением, напротив, представляют альтернативу в виде потока.</span><span class="sxs-lookup"><span data-stu-id="57cce-112">In contrast, CLR table-valued functions represent a streaming alternative.</span></span> <span data-ttu-id="57cce-113">Материализация всего результирующего набора в одной таблице не требуется.</span><span class="sxs-lookup"><span data-stu-id="57cce-113">There is no requirement that the entire set of results be materialized in a single table.</span></span> <span data-ttu-id="57cce-114">Объект `IEnumerable`, возвращаемый управляемой функцией, напрямую вызывается планом выполнения запроса, который вызывает функцию с табличным значением, а обработка результатов происходит по мере их получения.</span><span class="sxs-lookup"><span data-stu-id="57cce-114">The `IEnumerable` object returned by the managed function is directly called by the execution plan of the query that calls the table-valued function, and the results are consumed in an incremental manner.</span></span> <span data-ttu-id="57cce-115">Такая потоковая модель обеспечивает немедленную обработку результатов сразу после получения первой строки, вместо того чтобы ожидать заполнения всей таблицы.</span><span class="sxs-lookup"><span data-stu-id="57cce-115">This streaming model ensures that results can be consumed immediately after the first row is available, instead of waiting for the entire table to be populated.</span></span> <span data-ttu-id="57cce-116">Она также полезна, если возвращается очень большое число строк, поскольку таблица не материализуется в памяти как единое целое.</span><span class="sxs-lookup"><span data-stu-id="57cce-116">It is also a better alternative if you have very large numbers of rows returned, because they do not have to be materialized in memory as a whole.</span></span> <span data-ttu-id="57cce-117">Например, функция с табличным значением может использоваться для синтаксического анализа текстового файла и возвращения каждой строки текста в виде строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="57cce-117">For example, a managed table-valued function could be used to parse a text file and return each line as a row.</span></span>  
  
## <a name="implementing-table-valued-functions"></a><span data-ttu-id="57cce-118">Реализация функций с табличным значением</span><span class="sxs-lookup"><span data-stu-id="57cce-118">Implementing Table-Valued Functions</span></span>  
 <span data-ttu-id="57cce-119">Функции с табличным значением реализуются в виде методов класса в сборке [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57cce-119">Implement table-valued functions as methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework assembly.</span></span> <span data-ttu-id="57cce-120">В коде функции с табличным значением должен быть реализован интерфейс `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="57cce-120">Your table-valued function code must implement the `IEnumerable` interface.</span></span> <span data-ttu-id="57cce-121">Интерфейс `IEnumerable` определен в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57cce-121">The `IEnumerable` interface is defined in the .NET Framework.</span></span> <span data-ttu-id="57cce-122">Типы, представляющие массивы и коллекции в .NET Framework, уже реализованы в интерфейсе `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="57cce-122">Types representing arrays and collections in the .NET Framework already implement the `IEnumerable` interface.</span></span> <span data-ttu-id="57cce-123">Это облегчает написание функций с табличным значением, преобразующих коллекцию или массив в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="57cce-123">This makes it easy for writing table-valued functions that convert a collection or an array into a result set.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="57cce-124">Параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="57cce-124">Table-Valued Parameters</span></span>  
 <span data-ttu-id="57cce-125">Возвращающие табличное значение параметры — это определяемые пользователем табличные типы, которые передаются в процедуру или функцию, предоставляя эффективный способ передачи на сервер нескольких строк данных.</span><span class="sxs-lookup"><span data-stu-id="57cce-125">Table-valued parameters are user-defined table types that are passed into a procedure or function and provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="57cce-126">Возвращающие табличное значение параметры выполняют функции, аналогичные массивам параметров, но обладают большей гибкостью и лучше интегрируются с [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57cce-126">Table-valued parameters provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="57cce-127">Они также обеспечивают возможность повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="57cce-127">They also provide the potential for better performance.</span></span> <span data-ttu-id="57cce-128">Кроме того, возвращающие табличное значение параметры способствуют сокращению циклов приема-передачи данных с сервера и на сервер.</span><span class="sxs-lookup"><span data-stu-id="57cce-128">Table-valued parameters also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="57cce-129">Вместо того чтобы отправлять на сервер несколько запросов (как в случае списка скалярных параметров), данные можно отправить в виде возвращающего табличное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="57cce-129">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a table-valued parameter.</span></span> <span data-ttu-id="57cce-130">Определяемый пользователем табличный тип нельзя передавать в виде возвращающего табличное значение параметра в управляемую хранимую процедуру или функцию, которая выполняется в процессе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Кроме того, такие процедуры и функции не могут возвращать определяемые пользователем табличные типы.</span><span class="sxs-lookup"><span data-stu-id="57cce-130">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="57cce-131">Дополнительные сведения о возвращающих табличные значения параметрах см. в разделе [Использование параметров, возвращающих табличные значения (ядро СУБД)](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="57cce-131">For more information about table-valued parameters, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="output-parameters-and-table-valued-functions"></a><span data-ttu-id="57cce-132">Выходные параметры и функции с табличным значением</span><span class="sxs-lookup"><span data-stu-id="57cce-132">Output Parameters and Table-Valued Functions</span></span>  
 <span data-ttu-id="57cce-133">Возврат данных из функции с табличным значением может производиться через выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="57cce-133">Information may be returned from table-valued functions using output parameters.</span></span> <span data-ttu-id="57cce-134">Соответствующий аргумент в коде реализации функции с табличным значением должен передаваться по ссылке.</span><span class="sxs-lookup"><span data-stu-id="57cce-134">The corresponding parameter in the implementation code table-valued function should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="57cce-135">Следует отметить, что язык Visual Basic не поддерживает выходные параметры так, как они поддерживаются в языке Visual C#.</span><span class="sxs-lookup"><span data-stu-id="57cce-135">Note that Visual Basic does not support output parameters in the same way that Visual C# does.</span></span> <span data-ttu-id="57cce-136">Необходимо указать параметр по ссылке и применить \<Out()> атрибут для представления выходного параметра, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="57cce-136">You must specify the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
...  
Public Shared Sub FillRow ( <Out()> ByRef value As SqlInt32)  
```  
  
### <a name="defining-a-table-valued-function-in-transact-sql"></a><span data-ttu-id="57cce-137">Определение функции с табличным значением на языке Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57cce-137">Defining a Table-Valued Function in Transact-SQL</span></span>  
 <span data-ttu-id="57cce-138">Синтаксис определения функции CLR с табличным значением напоминает синтаксис объявления функции [!INCLUDE[tsql](../../includes/tsql-md.md)] с табличным значением с добавлением предложения `EXTERNAL NAME`.</span><span class="sxs-lookup"><span data-stu-id="57cce-138">The syntax for defining a CLR table-valued function is similar to that of a [!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued function, with the addition of the `EXTERNAL NAME` clause.</span></span> <span data-ttu-id="57cce-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="57cce-139">For example:</span></span>  
  
```  
CREATE FUNCTION GetEmpFirstLastNames()  
RETURNS TABLE (FirstName NVARCHAR(4000), LastName NVARCHAR(4000))  
EXTERNAL NAME MyDotNETAssembly.[MyNamespace.MyClassname]. GetEmpFirstLastNames;  
```  
  
 <span data-ttu-id="57cce-140">Функции с табличным значением используются для представления данных в реляционном формате для дальнейшей обработки в запросах, например:</span><span class="sxs-lookup"><span data-stu-id="57cce-140">Table-valued functions are used to represent data in relational form for further processing in queries such as:</span></span>  
  
```  
select * from function();  
select * from tbl join function() f on tbl.col = f.col;  
select * from table t cross apply function(t.column);  
```  
  
 <span data-ttu-id="57cce-141">Функции с табличным значением могут вернуть таблицу в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="57cce-141">Table-valued functions can return a table when:</span></span>  
  
-   <span data-ttu-id="57cce-142">Если они созданы из скалярных входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="57cce-142">Created from scalar input arguments.</span></span> <span data-ttu-id="57cce-143">Например, функция с табличным значением, принимающая строку чисел, разделенных запятыми, и преобразующая ее в таблицу.</span><span class="sxs-lookup"><span data-stu-id="57cce-143">For example, a table-valued function that takes a comma-delimited string of numbers and pivots them into a table.</span></span>  
  
-   <span data-ttu-id="57cce-144">Если они созданы из внешних данных.</span><span class="sxs-lookup"><span data-stu-id="57cce-144">Generated from external data.</span></span> <span data-ttu-id="57cce-145">Например, функция с табличным значением, считывающая журнал событий и представляющая его в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="57cce-145">For example, a table-valued function that reads the event log and exposes it as a table.</span></span>  
  
 <span data-ttu-id="57cce-146">**Примечание** . Функция с табличным значением может выполнять доступ к данным только с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] запроса в `InitMethod` методе, а не в `FillRow` методе.</span><span class="sxs-lookup"><span data-stu-id="57cce-146">**Note** A table-valued function can only perform data access through a [!INCLUDE[tsql](../../includes/tsql-md.md)] query in the `InitMethod` method, and not in the `FillRow` method.</span></span> <span data-ttu-id="57cce-147">Метод `InitMethod` не должен быть помечен свойством атрибута `SqlFunction.DataAccess.Read`, если выполняется запрос [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57cce-147">The `InitMethod` should be marked with the `SqlFunction.DataAccess.Read` attribute property if a [!INCLUDE[tsql](../../includes/tsql-md.md)] query is performed.</span></span>  
  
## <a name="a-sample-table-valued-function"></a><span data-ttu-id="57cce-148">Образец функции с табличным значением</span><span class="sxs-lookup"><span data-stu-id="57cce-148">A Sample Table-Valued Function</span></span>  
 <span data-ttu-id="57cce-149">Следующая функция с табличным значением возвращает сведения из журнала системных событий.</span><span class="sxs-lookup"><span data-stu-id="57cce-149">The following table-valued function returns information from the system event log.</span></span> <span data-ttu-id="57cce-150">Функция принимает один строковый аргумент, содержащий имя журнала событий.</span><span class="sxs-lookup"><span data-stu-id="57cce-150">The function takes a single string argument containing the name of the event log to read.</span></span>  
  
###### <a name="sample-code"></a><span data-ttu-id="57cce-151">Пример кода</span><span class="sxs-lookup"><span data-stu-id="57cce-151">Sample Code</span></span>  
  
```csharp  
using System;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Collections;  
using System.Data.SqlTypes;  
using System.Diagnostics;  
  
public class TabularEventLog  
{  
    [SqlFunction(FillRowMethodName = "FillRow")]  
    public static IEnumerable InitMethod(String logname)  
    {  
        return new EventLog(logname).Entries;    }  
  
    public static void FillRow(Object obj, out SqlDateTime timeWritten, out SqlChars message, out SqlChars category, out long instanceId)  
    {  
        EventLogEntry eventLogEntry = (EventLogEntry)obj;  
        timeWritten = new SqlDateTime(eventLogEntry.TimeWritten);  
        message = new SqlChars(eventLogEntry.Message);  
        category = new SqlChars(eventLogEntry.Category);  
        instanceId = eventLogEntry.InstanceId;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data.Sql  
Imports Microsoft.SqlServer.Server  
Imports System.Collections  
Imports System.Data.SqlTypes  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Public Class TabularEventLog  
    <SqlFunction(FillRowMethodName:="FillRow")> _  
    Public Shared Function InitMethod(ByVal logname As String) As IEnumerable  
        Return New EventLog(logname).Entries  
    End Function  
  
    Public Shared Sub FillRow(ByVal obj As Object, <Out()> ByRef timeWritten As SqlDateTime, <Out()> ByRef message As SqlChars, <Out()> ByRef category As SqlChars, <Out()> ByRef instanceId As Long)  
        Dim eventLogEnTry As EventLogEntry = CType(obj, EventLogEntry)  
        timeWritten = New SqlDateTime(eventLogEnTry.TimeWritten)  
        message = New SqlChars(eventLogEnTry.Message)  
        category = New SqlChars(eventLogEnTry.Category)  
        instanceId = eventLogEnTry.InstanceId  
    End Sub  
End Class  
```  
  
###### <a name="declaring-and-using-the-sample-table-valued-function"></a><span data-ttu-id="57cce-152">Объявление и использование образца функции с табличным значением</span><span class="sxs-lookup"><span data-stu-id="57cce-152">Declaring and Using the Sample Table-Valued Function</span></span>  
 <span data-ttu-id="57cce-153">После компиляции образца возвращающей табличное значение функции его можно объявить в [!INCLUDE[tsql](../../includes/tsql-md.md)] следующим образом.</span><span class="sxs-lookup"><span data-stu-id="57cce-153">After the sample table-valued function has been compiled, it can be declared in [!INCLUDE[tsql](../../includes/tsql-md.md)] like this:</span></span>  
  
```  
use master;  
-- Replace SQL_Server_logon with your SQL Server user credentials.  
GRANT EXTERNAL ACCESS ASSEMBLY TO [SQL_Server_logon];   
-- Modify the following line to specify a different database.  
ALTER DATABASE master SET TRUSTWORTHY ON;  
  
-- Modify the next line to use the appropriate database.  
CREATE ASSEMBLY tvfEventLog   
FROM 'D:\assemblies\tvfEventLog\tvfeventlog.dll'   
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
GO  
CREATE FUNCTION ReadEventLog(@logname nvarchar(100))  
RETURNS TABLE   
(logTime datetime,Message nvarchar(4000),Category nvarchar(4000),InstanceId bigint)  
AS   
EXTERNAL NAME tvfEventLog.TabularEventLog.InitMethod;  
GO  
```  
  
 <span data-ttu-id="57cce-154">Выполнение объектов базы данных, написанных на языке Visual C++ и скомпилированных с параметром /clr:pure, не поддерживается в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57cce-154">Visual C++ database objects compiled with /clr:pure are not supported for execution on [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="57cce-155">Например, в число таких объектов базы данных входят функции с табличным значением.</span><span class="sxs-lookup"><span data-stu-id="57cce-155">For example, such database objects include table-valued functions.</span></span>  
  
 <span data-ttu-id="57cce-156">Чтобы проверить образец, выполните следующий код [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57cce-156">To test the sample, try the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
```  
-- Select the top 100 events,  
SELECT TOP 100 *  
FROM dbo.ReadEventLog(N'Security') as T;  
go  
  
-- Select the last 10 login events.  
SELECT TOP 10 T.logTime, T.Message, T.InstanceId   
FROM dbo.ReadEventLog(N'Security') as T  
WHERE T.Category = N'Logon/Logoff';  
go  
```  
  
## <a name="sample-returning-the-results-of-a-sql-server-query"></a><span data-ttu-id="57cce-157">Образец. Возвращение результатов запроса SQL Server</span><span class="sxs-lookup"><span data-stu-id="57cce-157">Sample: Returning the Results of a SQL Server Query</span></span>  
 <span data-ttu-id="57cce-158">В следующем образце показана возвращающая табличное значение функция, которая запрашивает базу данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57cce-158">The following sample shows a table-valued function that queries a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="57cce-159">В этом образце используется база данных AdventureWorks Light из [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57cce-159">This sample uses the AdventureWorks Light database from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="57cce-160">[https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843)Дополнительные сведения о скачивании AdventureWorks см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="57cce-160">See [https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843) for more information on downloading AdventureWorks.</span></span>  
  
 <span data-ttu-id="57cce-161">Задайте для файла исходного кода имя FindInvalidEmails.cs или FindInvalidEmails.vb.</span><span class="sxs-lookup"><span data-stu-id="57cce-161">Name your source code file FindInvalidEmails.cs or FindInvalidEmails.vb.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
  
using Microsoft.SqlServer.Server;  
  
public partial class UserDefinedFunctions {  
   private class EmailResult {  
      public SqlInt32 CustomerId;  
      public SqlString EmailAdress;  
  
      public EmailResult(SqlInt32 customerId, SqlString emailAdress) {  
         CustomerId = customerId;  
         EmailAdress = emailAdress;  
      }  
   }  
  
   public static bool ValidateEmail(SqlString emailAddress) {  
      if (emailAddress.IsNull)  
         return false;  
  
      if (!emailAddress.Value.EndsWith("@adventure-works.com"))  
         return false;  
  
      // Validate the address. Put any more rules here.  
      return true;  
   }  
  
   [SqlFunction(  
       DataAccess = DataAccessKind.Read,  
       FillRowMethodName = "FindInvalidEmails_FillRow",  
       TableDefinition="CustomerId int, EmailAddress nvarchar(4000)")]  
   public static IEnumerable FindInvalidEmails(SqlDateTime modifiedSince) {  
      ArrayList resultCollection = new ArrayList();  
  
      using (SqlConnection connection = new SqlConnection("context connection=true")) {  
         connection.Open();  
  
         using (SqlCommand selectEmails = new SqlCommand(  
             "SELECT " +  
             "[CustomerID], [EmailAddress] " +  
             "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " +  
             "WHERE [ModifiedDate] >= @modifiedSince",  
             connection)) {  
            SqlParameter modifiedSinceParam = selectEmails.Parameters.Add(  
                "@modifiedSince",  
                SqlDbType.DateTime);  
            modifiedSinceParam.Value = modifiedSince;  
  
            using (SqlDataReader emailsReader = selectEmails.ExecuteReader()) {  
               while (emailsReader.Read()) {  
                  SqlString emailAddress = emailsReader.GetSqlString(1);  
                  if (ValidateEmail(emailAddress)) {  
                     resultCollection.Add(new EmailResult(  
                         emailsReader.GetSqlInt32(0),  
                         emailAddress));  
                  }  
               }  
            }  
         }  
      }  
  
      return resultCollection;  
   }  
  
   public static void FindInvalidEmails_FillRow(  
       object emailResultObj,  
       out SqlInt32 customerId,  
       out SqlString emailAdress) {  
      EmailResult emailResult = (EmailResult)emailResultObj;  
  
      customerId = emailResult.CustomerId;  
      emailAdress = emailResult.EmailAdress;  
   }  
};  
```  
  
```vb  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, ByRef customerId As SqlInt32, ByRef emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End ClassImports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, customerId As SqlInt32, emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="57cce-162">Скомпилируйте исходный код в библиотеку DLL и скопируйте ее в корневой каталог диска C.</span><span class="sxs-lookup"><span data-stu-id="57cce-162">Compile the source code to a DLL and copy the DLL to the root directory of your C drive.</span></span>  <span data-ttu-id="57cce-163">Затем выполните следующий запрос [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57cce-163">Then, execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] query.</span></span>  
  
```  
use AdventureWorksLT2008;  
go  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'FindInvalidEmails')  
   DROP FUNCTION FindInvalidEmails;  
go  
  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'MyClrCode')  
   DROP ASSEMBLY MyClrCode;  
go  
  
CREATE ASSEMBLY MyClrCode FROM 'C:\FindInvalidEmails.dll'  
WITH PERMISSION_SET = SAFE -- EXTERNAL_ACCESS;  
GO  
  
CREATE FUNCTION FindInvalidEmails(@ModifiedSince datetime)   
RETURNS TABLE (  
   CustomerId int,  
   EmailAddress nvarchar(4000)  
)  
AS EXTERNAL NAME MyClrCode.UserDefinedFunctions.[FindInvalidEmails];  
go  
  
SELECT * FROM FindInvalidEmails('2000-01-01');  
go  
```  
  
