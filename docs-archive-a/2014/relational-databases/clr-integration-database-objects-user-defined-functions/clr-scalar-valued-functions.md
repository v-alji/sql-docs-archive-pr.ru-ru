---
title: Функции CLR с скалярными значениями | Документация Майкрософт
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
- SVF
- scalar-valued functions
ms.assetid: 20dcf802-c27d-4722-9cd3-206b1e77bee0
author: rothja
ms.author: jroth
ms.openlocfilehash: be8f9616fb285d6a68d6734924874ded06fb3bd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730750"
---
# <a name="clr-scalar-valued-functions"></a><span data-ttu-id="bc531-102">Скалярные функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="bc531-102">CLR Scalar-Valued Functions</span></span>
  <span data-ttu-id="bc531-103">Скалярная функция (SVF) возвращает единственное значение, например строку, целочисленное или битовое значение. Определяемые пользователем скалярные функции можно создавать в управляемом коде на любом языке программирования платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc531-103">A scalar-valued function (SVF) returns a single value, such as a string, integer, or bit value.You can create scalar-valued user-defined functions in managed code using any .NET Framework programming language.</span></span> <span data-ttu-id="bc531-104">Эти функции доступны для [!INCLUDE[tsql](../../includes/tsql-md.md)] и другого управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bc531-104">These functions are accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span> <span data-ttu-id="bc531-105">Сведения о преимуществах интеграции со средой CLR и выборе между управляемым кодом и [!INCLUDE[tsql](../../includes/tsql-md.md)] см. в разделе [Обзор интеграции со средой CLR](../clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc531-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-scalar-valued-functions"></a><span data-ttu-id="bc531-106">Требования к скалярным функциям среды CLR</span><span class="sxs-lookup"><span data-stu-id="bc531-106">Requirements for CLR Scalar-Valued Functions</span></span>  
 <span data-ttu-id="bc531-107">Скалярные функции .NET Framework реализуются в виде методов класса в сборке .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc531-107">.NET Framework SVFs are implemented as methods on a class in a .NET Framework assembly.</span></span> <span data-ttu-id="bc531-108">Входные параметры и тип, возвращаемый из SVF, могут быть любыми скалярными типами данных, поддерживаемыми [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , за исключением,,,,,,, `varchar` `char` `rowversion` `text` `ntext` `image` `timestamp` `table` или `cursor` .</span><span class="sxs-lookup"><span data-stu-id="bc531-108">The input parameters and the type returned from a SVF can be any of the scalar data types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except `varchar`, `char`, `rowversion`, `text`, `ntext`, `image`, `timestamp`, `table`, or `cursor`.</span></span> <span data-ttu-id="bc531-109">Скалярные функции должны обеспечивать соответствие типа данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и типа данных, возвращаемого методом реализации.</span><span class="sxs-lookup"><span data-stu-id="bc531-109">SVFs must ensure a match between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type and the return data type of the implementation method.</span></span> <span data-ttu-id="bc531-110">Дополнительные сведения о преобразовании типов см. в разделе [сопоставление данных параметров CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="bc531-110">For more information about type conversions, see [Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
 <span data-ttu-id="bc531-111">При реализации скалярной функции .NET Framework на одном из языков .NET Framework можно включить дополнительные сведения о функции, задав пользовательский атрибут `SqlFunction`.</span><span class="sxs-lookup"><span data-stu-id="bc531-111">When implementing a .NET Framework SVF in a .NET Framework language, the `SqlFunction` custom attribute can be specified to include additional information about the function.</span></span> <span data-ttu-id="bc531-112">Атрибут `SqlFunction` указывает, получает ли функция доступ к данным или вносит изменения в данные, является ли детерминированной и предусматривает ли выполнение операций с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="bc531-112">The `SqlFunction` attribute indicates whether or not the function accesses or modifies data, if it is deterministic, and if the function involves floating point operations.</span></span>  
  
 <span data-ttu-id="bc531-113">Определяемые пользователем скалярные функции могут быть детерминированными или недетерминированными.</span><span class="sxs-lookup"><span data-stu-id="bc531-113">Scalar-valued user-defined functions may be deterministic or non-deterministic.</span></span> <span data-ttu-id="bc531-114">Детерминированная функция всегда возвращает один и тот же результат при вызове с конкретным набором входных параметров.</span><span class="sxs-lookup"><span data-stu-id="bc531-114">A deterministic function always returns the same result when it is called with a specific set of input parameters.</span></span> <span data-ttu-id="bc531-115">Недетерминированная функция может возвращать разные результаты при вызове с конкретным набором входных параметров.</span><span class="sxs-lookup"><span data-stu-id="bc531-115">A non-deterministic function may return different results when it is called with a specific set of input parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc531-116">Не следует помечать функцию как детерминированную, если она не всегда выдает одинаковые выходные значения при передаче одинаковых входных значений и при одинаковом состоянии базы данных.</span><span class="sxs-lookup"><span data-stu-id="bc531-116">Do not mark a function as deterministic if the function does not always produces the same output values, given the same input values and the same database state.</span></span> <span data-ttu-id="bc531-117">Не следует определять функцию как детерминированную, если в действительности она таковой не является. Это может привести к искажению индексированных представлений и вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="bc531-117">Marking a function as deterministic, when the function isn't truly deterministic can result in corrupted indexed views and computed columns.</span></span> <span data-ttu-id="bc531-118">Определить функцию как детерминированную можно, задав для свойства `IsDeterministic` значение true.</span><span class="sxs-lookup"><span data-stu-id="bc531-118">You mark a function as deterministic by setting the `IsDeterministic` property to true.</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="bc531-119">Параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="bc531-119">Table-Valued Parameters</span></span>  
 <span data-ttu-id="bc531-120">Возвращающие табличное значение параметры — это определяемые пользователем табличные типы, которые передаются в процедуру или функцию, предоставляя эффективный способ передачи на сервер нескольких строк данных.</span><span class="sxs-lookup"><span data-stu-id="bc531-120">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="bc531-121">Возвращающие табличное значение параметры выполняют функции, аналогичные массивам параметров, но обладают большей гибкостью и лучше интегрируются с [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc531-121">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bc531-122">Они также обеспечивают возможность повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="bc531-122">They also provide the potential for better performance.</span></span> <span data-ttu-id="bc531-123">Кроме того, возвращающие табличное значение параметры способствуют сокращению циклов приема-передачи данных с сервера и на сервер.</span><span class="sxs-lookup"><span data-stu-id="bc531-123">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="bc531-124">Вместо того чтобы отправлять на сервер несколько запросов (как в случае списка скалярных параметров), данные можно отправить в виде возвращающего табличное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="bc531-124">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="bc531-125">Определяемый пользователем табличный тип нельзя передавать в виде возвращающего табличное значение параметра в управляемую хранимую процедуру или функцию, которая выполняется в процессе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Кроме того, такие процедуры и функции не могут возвращать определяемые пользователем табличные типы.</span><span class="sxs-lookup"><span data-stu-id="bc531-125">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="bc531-126">Дополнительные сведения о TVP см. в разделе [Использование возвращающих табличное значение параметров &#40;ядро СУБД&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="bc531-126">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="example-of-a-clr-scalar-valued-function"></a><span data-ttu-id="bc531-127">Пример скалярной функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="bc531-127">Example of a CLR Scalar-Valued Function</span></span>  
 <span data-ttu-id="bc531-128">Ниже приводится простой пример скалярной функции, получающей доступ к данным и возвращающей целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="bc531-128">Here is a simple SVF that accesses data and returns an integer value:</span></span>  
  
```csharp  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public class T  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static int ReturnOrderCount()  
    {  
        using (SqlConnection conn   
            = new SqlConnection("context connection=true"))  
        {  
            conn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
            return (int)cmd.ExecuteScalar();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public Class T  
    <SqlFunction(DataAccess:=DataAccessKind.Read)> _  
    Public Shared Function ReturnOrderCount() As Integer  
        Using conn As New SqlConnection("context connection=true")  
            conn.Open()  
            Dim cmd As New SqlCommand("SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
            Return CType(cmd.ExecuteScalar(), Integer)  
        End Using  
    End Function  
End Class  
```  
  
 <span data-ttu-id="bc531-129">В первой строке кода содержится ссылка на объект `Microsoft.SqlServer.Server` для доступа к атрибутам и на объект `System.Data.SqlClient` для доступа к пространству имен ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="bc531-129">The first line of code references `Microsoft.SqlServer.Server` to access attributes and `System.Data.SqlClient` to access the ADO.NET namespace.</span></span> <span data-ttu-id="bc531-130">(Это пространство имен содержит `SqlClient`, поставщик данных .NET Framework для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="bc531-130">(This namespace contains `SqlClient`, the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="bc531-131">Далее функция получает пользовательский атрибут `SqlFunction`, относящийся к пространству имен `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="bc531-131">Next, the function receives the `SqlFunction` custom attribute, which is found in the `Microsoft.SqlServer.Server` namespace.</span></span> <span data-ttu-id="bc531-132">Пользовательский атрибут указывает, используется ли определяемая пользователем функция (UDF) внутрипроцессным поставщиком для чтения данных с сервера.</span><span class="sxs-lookup"><span data-stu-id="bc531-132">The custom attribute indicates whether or not the user-defined function (UDF) uses the in-process provider to read data in the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc531-133">не позволяет определяемым пользователем функциям обновлять, вставлять и удалять данные.</span><span class="sxs-lookup"><span data-stu-id="bc531-133">does not allow UDFs to update, insert, or delete data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc531-134">может оптимизировать выполнение определяемой пользователем функции, не использующей внутрипроцессный поставщик.</span><span class="sxs-lookup"><span data-stu-id="bc531-134">can optimize execution of a UDF that does not use the in-process provider.</span></span> <span data-ttu-id="bc531-135">На это указывает параметр `DataAccessKind`, имеющий значение `DataAccessKind.None`.</span><span class="sxs-lookup"><span data-stu-id="bc531-135">This is indicated by setting `DataAccessKind` to `DataAccessKind.None`.</span></span> <span data-ttu-id="bc531-136">На следующей строке целевой метод определяется как public static (или на языке Visual Basic .NET — shared).</span><span class="sxs-lookup"><span data-stu-id="bc531-136">On the next line, the target method is a public static (shared in Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="bc531-137">После этого класс `SqlContext`, находящийся в пространстве имен `Microsoft.SqlServer.Server`, может получить доступ к объекту `SqlCommand` с уже созданным соединением с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc531-137">The `SqlContext` class, located in the `Microsoft.SqlServer.Server` namespace, can then access a `SqlCommand` object with a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is already set up.</span></span> <span data-ttu-id="bc531-138">Кроме того, становится доступным в рамках API `System.Transactions` контекст текущей транзакции, хотя в данном случае не используется.</span><span class="sxs-lookup"><span data-stu-id="bc531-138">Although not used here, the current transaction context is also available through the `System.Transactions` application programming interface (API).</span></span>  
  
 <span data-ttu-id="bc531-139">Большая часть строк кода в тексте функции должна быть знакома для разработчика, имеющего опыт написания клиентских приложений с использованием типов из пространства имен `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="bc531-139">Most of the lines of code in the function body should look familiar to developers who have written client applications that use the types found in the `System.Data.SqlClient` namespace.</span></span>  
  
 <span data-ttu-id="bc531-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="bc531-140">[C#]</span></span>  
  
```  
using(SqlConnection conn = new SqlConnection("context connection=true"))   
{  
   conn.Open();  
   SqlCommand cmd = new SqlCommand(  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
   return (int) cmd.ExecuteScalar();  
}    
```  
  
 <span data-ttu-id="bc531-141">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="bc531-141">[Visual Basic]</span></span>  
  
```  
Using conn As New SqlConnection("context connection=true")  
   conn.Open()  
   Dim cmd As New SqlCommand( _  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
   Return CType(cmd.ExecuteScalar(), Integer)  
End Using  
```  
  
 <span data-ttu-id="bc531-142">Необходимый текст команды можно задать путем инициализации объекта `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="bc531-142">The appropriate command text is specified by initializing the `SqlCommand` object.</span></span> <span data-ttu-id="bc531-143">В предыдущем примере подсчитывалось число строк в таблице `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="bc531-143">The previous example counts the number of rows in table `SalesOrderHeader`.</span></span> <span data-ttu-id="bc531-144">Далее вызывается метод `ExecuteScalar` объекта `cmd`.</span><span class="sxs-lookup"><span data-stu-id="bc531-144">Next, the `ExecuteScalar` method of the `cmd` object is called.</span></span> <span data-ttu-id="bc531-145">Он возвращает значение типа `int` на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="bc531-145">This returns a value of type `int` based on the query.</span></span> <span data-ttu-id="bc531-146">Наконец происходит возврат сведений о количестве заказов в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="bc531-146">Finally, the order count is returned to the caller.</span></span>  
  
 <span data-ttu-id="bc531-147">После сохранения в файле с именем FirstUdf.cs этот код можно скомпилировать в сборку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bc531-147">If this code is saved in a file called FirstUdf.cs, it could be compiled into as assembly as follows:</span></span>  
  
 <span data-ttu-id="bc531-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="bc531-148">[C#]</span></span>  
  
```  
csc.exe /t:library /out:FirstUdf.dll FirstUdf.cs   
```  
  
 <span data-ttu-id="bc531-149">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="bc531-149">[Visual Basic]</span></span>  
  
```  
vbc.exe /t:library /out:FirstUdf.dll FirstUdf.vb  
```  
  
> [!NOTE]  
>  <span data-ttu-id="bc531-150">`/t:library` указывает, что результатом компиляции должна быть библиотека, а не исполняемый объект.</span><span class="sxs-lookup"><span data-stu-id="bc531-150">`/t:library` indicates that a library, rather than an executable, should be produced.</span></span> <span data-ttu-id="bc531-151">Исполняемые объекты нельзя регистрировать в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc531-151">Executables cannot be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc531-152">Выполнение объектов базы данных, написанных на языке Visual C++ и скомпилированных с параметром `/clr:pure`, в СУБД [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bc531-152">Visual C++ database objects compiled with `/clr:pure` are not supported for execution on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bc531-153">В частности, такими объектами базы данных являются скалярные функции.</span><span class="sxs-lookup"><span data-stu-id="bc531-153">For example, such database objects include scalar-valued functions.</span></span>  
  
 <span data-ttu-id="bc531-154">Ниже приведены запрос [!INCLUDE[tsql](../../includes/tsql-md.md)] и образец вызова для регистрации сборки и определяемой пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="bc531-154">The [!INCLUDE[tsql](../../includes/tsql-md.md)] query and a sample invocation to register the assembly and UDF are:</span></span>  
  
```  
CREATE ASSEMBLY FirstUdf FROM 'FirstUdf.dll';  
GO  
  
CREATE FUNCTION CountSalesOrderHeader() RETURNS INT   
AS EXTERNAL NAME FirstUdf.T.ReturnOrderCount;   
GO  
  
SELECT dbo.CountSalesOrderHeader();  
GO  
  
```  
  
 <span data-ttu-id="bc531-155">Обратите внимание, что имя функции в [!INCLUDE[tsql](../../includes/tsql-md.md)] не обязательно должно соответствовать имени общего статического целевого метода.</span><span class="sxs-lookup"><span data-stu-id="bc531-155">Note that the function name as exposed in [!INCLUDE[tsql](../../includes/tsql-md.md)] does not need to match the name of the target public static method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc531-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc531-156">See Also</span></span>  
 <span data-ttu-id="bc531-157">[Сопоставление данных параметров среды CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span><span class="sxs-lookup"><span data-stu-id="bc531-157">[Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span></span>  
 <span data-ttu-id="bc531-158">[Общие сведения о настраиваемых атрибутах интеграции со средой CLR](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="bc531-158">[Overview of CLR Integration Custom Attributes](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span></span>  
 <span data-ttu-id="bc531-159">[Определяемые пользователем функции](../user-defined-functions/user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="bc531-159">[User-Defined Functions](../user-defined-functions/user-defined-functions.md) </span></span>  
 [<span data-ttu-id="bc531-160">Доступ к данным из объектов среды CLR для работы с базами данных</span><span class="sxs-lookup"><span data-stu-id="bc531-160">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
