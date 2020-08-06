---
title: Хранимые процедуры CLR | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration], stored procedures
- stored procedures [CLR integration]
- common language runtime [SQL Server], stored procedures
- building database objects [CLR integration], stored procedures
- output parameters [CLR integration]
- tabular results
ms.assetid: bbdd51b2-a9b4-4916-ba6f-7957ac6c3f33
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f8c69435e28bfa67c72e26b7a54e419cd91ef220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657256"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="80685-102">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="80685-102">CLR Stored Procedures</span></span>
  <span data-ttu-id="80685-103">Хранимыми процедурами являются процедуры, которые нельзя использовать в скалярных выражениях.</span><span class="sxs-lookup"><span data-stu-id="80685-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="80685-104">В отличие от скалярных функций, они могут возвращать клиенту табличные результаты и сообщения, вызывать инструкции языка описания данных DDL и языка обработки данных DML, а также возвращать выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="80685-104">Unlike scalar functions, they can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span> <span data-ttu-id="80685-105">Сведения о преимуществах интеграции со средой CLR и выборе между управляемым кодом и [!INCLUDE[tsql](../../includes/tsql-md.md)] см. в разделе [Обзор интеграции со средой CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="80685-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-stored-procedures"></a><span data-ttu-id="80685-106">Требования для хранимых процедур CLR</span><span class="sxs-lookup"><span data-stu-id="80685-106">Requirements for CLR Stored Procedures</span></span>  
 <span data-ttu-id="80685-107">В среде CLR хранимые процедуры реализуются как открытые статические методы в классе в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] сборке.</span><span class="sxs-lookup"><span data-stu-id="80685-107">In the common language runtime (CLR), stored procedures are implemented as public static methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span></span> <span data-ttu-id="80685-108">Статический метод может быть объявлен как void или может возвратить целое значение.</span><span class="sxs-lookup"><span data-stu-id="80685-108">The static method can either be declared as void, or return an integer value.</span></span> <span data-ttu-id="80685-109">Если он возвращает целое значение, возвращенное целое число рассматривается как код возврата из процедуры.</span><span class="sxs-lookup"><span data-stu-id="80685-109">If it returns an integer value, the integer returned is treated as the return code from the procedure.</span></span> <span data-ttu-id="80685-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="80685-110">For example:</span></span>  
  
 `EXECUTE @return_status = procedure_name`  
  
 <span data-ttu-id="80685-111">@return_statusПеременная будет содержать значение, возвращаемое методом.</span><span class="sxs-lookup"><span data-stu-id="80685-111">The @return_status variable will contain the value returned by the method.</span></span> <span data-ttu-id="80685-112">Если метод объявляется как void, код возврата равен 0.</span><span class="sxs-lookup"><span data-stu-id="80685-112">If the method is declared void, the return code is 0.</span></span>  
  
 <span data-ttu-id="80685-113">Если метод принимает параметры, число параметров в реализации [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] должно быть равно числу параметров, используемых в декларации [!INCLUDE[tsql](../../includes/tsql-md.md)] хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="80685-113">If the method takes parameters, the number of parameters in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] implementation should be the same as the number of parameters used in the [!INCLUDE[tsql](../../includes/tsql-md.md)] declaration of the stored procedure.</span></span>  
  
 <span data-ttu-id="80685-114">Параметры, передаваемые в хранимую процедуру CLR, могут быть любого собственного типа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], имеющего эквивалент в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="80685-114">Parameters passed to a CLR stored procedure can be any of the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types that have an equivalent in managed code.</span></span> <span data-ttu-id="80685-115">Для синтаксиса [!INCLUDE[tsql](../../includes/tsql-md.md)], используемого при создании процедуры, такие типы должны задаваться при помощи наиболее подходящего эквивалента собственного типа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80685-115">For the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax to create the procedure, these types should be specified with the most appropriate native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type equivalent.</span></span> <span data-ttu-id="80685-116">Дополнительные сведения о преобразовании типов см. в разделе [сопоставление данных параметров CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="80685-116">For more information about type conversions, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="80685-117">Параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="80685-117">Table-Valued Parameters</span></span>  
 <span data-ttu-id="80685-118">Возвращающие табличное значение параметры — это определяемые пользователем табличные типы, которые передаются в процедуру или функцию, предоставляя эффективный способ передачи на сервер нескольких строк данных.</span><span class="sxs-lookup"><span data-stu-id="80685-118">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="80685-119">Возвращающие табличное значение параметры выполняют функции, аналогичные массивам параметров, но обладают большей гибкостью и лучше интегрируются с [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80685-119">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="80685-120">Они также обеспечивают возможность повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="80685-120">They also provide the potential for better performance.</span></span> <span data-ttu-id="80685-121">Кроме того, возвращающие табличное значение параметры способствуют сокращению циклов приема-передачи данных с сервера и на сервер.</span><span class="sxs-lookup"><span data-stu-id="80685-121">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="80685-122">Вместо того чтобы отправлять на сервер несколько запросов (как в случае списка скалярных параметров), данные можно отправить в виде возвращающего табличное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="80685-122">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="80685-123">Определяемый пользователем табличный тип нельзя передавать в виде возвращающего табличное значение параметра в управляемую хранимую процедуру или функцию, которая выполняется в процессе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Кроме того, такие процедуры и функции не могут возвращать определяемые пользователем табличные типы.</span><span class="sxs-lookup"><span data-stu-id="80685-123">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="80685-124">Дополнительные сведения о TVP см. в разделе [Использование возвращающих табличное значение параметров &#40;ядро СУБД&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="80685-124">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="returning-results-from-clr-stored-procedures"></a><span data-ttu-id="80685-125">Возврат результатов хранимых процедур CLR</span><span class="sxs-lookup"><span data-stu-id="80685-125">Returning Results from CLR Stored Procedures</span></span>  
 <span data-ttu-id="80685-126">Возврат данных из хранимых процедур [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] может осуществляться несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="80685-126">Information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures in several ways.</span></span> <span data-ttu-id="80685-127">Это относится к выходным параметрам, табличным результатам и сообщениям.</span><span class="sxs-lookup"><span data-stu-id="80685-127">This includes output parameters, tabular results, and messages.</span></span>  
  
### <a name="output-parameters-and-clr-stored-procedures"></a><span data-ttu-id="80685-128">Параметры OUTPUT и хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="80685-128">OUTPUT Parameters and CLR Stored Procedures</span></span>  
 <span data-ttu-id="80685-129">Так же как и для хранимых процедур [!INCLUDE[tsql](../../includes/tsql-md.md)], данные могут возвращаться из хранимых процедур [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] при помощи параметров, описанных с ключевым словом OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="80685-129">As with [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures using OUTPUT parameters.</span></span> <span data-ttu-id="80685-130">Синтаксис [!INCLUDE[tsql](../../includes/tsql-md.md)] DML, используемый для создания хранимых процедур [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], тот же, что и синтаксис, используемый для создания хранимых процедур, написанных на [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80685-130">The [!INCLUDE[tsql](../../includes/tsql-md.md)] DML syntax used for creating [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures is the same as that used for creating stored procedures written in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="80685-131">Соответствующий параметр в коде реализации в классе [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] должен использовать в качестве аргумента параметр, передаваемый по ссылке.</span><span class="sxs-lookup"><span data-stu-id="80685-131">The corresponding parameter in the implementation code in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="80685-132">Обратите внимание, что Visual Basic не поддерживает выходные параметры точно так же, как это делает C#.</span><span class="sxs-lookup"><span data-stu-id="80685-132">Note that Visual Basic does not support output parameters in the same way that C# does.</span></span> <span data-ttu-id="80685-133">Необходимо указать параметр по ссылке и применить \<Out()> атрибут для представления выходного параметра, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="80685-133">You must specify the parameter by reference and apply the \<Out()> attribute to represent an OUTPUT parameter, as in the following:</span></span>  
  
```vb
Imports System.Runtime.InteropServices  
...  
Public Shared Sub PriceSum ( <Out()> ByRef value As SqlInt32)  
```  
  
 <span data-ttu-id="80685-134">Следующий пример представляет хранимую процедуру с входным и выходным параметрами:</span><span class="sxs-lookup"><span data-stu-id="80685-134">The following shows a stored procedure returning information through an OUTPUT parameter:</span></span>  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void PriceSum(out SqlInt32 value)  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         value = 0;  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT Price FROM Products", connection);  
         SqlDataReader reader = command.ExecuteReader();  
  
         using (reader)  
         {  
            while( reader.Read() )  
            {  
               value += reader.GetSqlInt32(0);  
            }  
         }           
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Runtime.InteropServices  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Executes a query and iterates over the results to perform a summation.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
  
        Using connection As New SqlConnection("context connection=true")  
           value = 0  
           Connection.Open()  
           Dim command As New SqlCommand("SELECT Price FROM Products", connection)  
           Dim reader As SqlDataReader  
           reader = command.ExecuteReader()  
  
           Using reader  
              While reader.Read()  
                 value += reader.GetSqlInt32(0)  
              End While  
           End Using  
        End Using          
    End Sub  
End Class  
```  
  
 <span data-ttu-id="80685-135">После того как сборка, содержащая указанную выше хранимую процедуру CLR, была построена и создана на сервере, [!INCLUDE[tsql](../../includes/tsql-md.md)] для создания процедуры в базе данных используется следующая функция и в качестве выходного параметра указывается *Sum* .</span><span class="sxs-lookup"><span data-stu-id="80685-135">Once the assembly containing the above CLR stored procedure has been built and created on the server, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] is used to create the procedure in the database, and specifies *sum* as an OUTPUT parameter.</span></span>  
  
```sql
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
-- if StoredProcedures class was inside a namespace, called MyNS,  
-- you would use:  
-- AS EXTERNAL NAME TestStoredProc.[MyNS.StoredProcedures].PriceSum  
```  
  
 <span data-ttu-id="80685-136">Обратите внимание, что *Sum* объявляется как `int` тип данных SQL Server, а параметр *значения* , определенный в хранимой процедуре CLR, указывается как `SqlInt32` тип данных CLR.</span><span class="sxs-lookup"><span data-stu-id="80685-136">Note that *sum* is declared as an `int` SQL Server data type, and that the *value* parameter defined in the CLR stored procedure is specified as a `SqlInt32` CLR data type.</span></span> <span data-ttu-id="80685-137">Когда вызывающая программа выполняет хранимую процедуру CLR, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически преобразует `SqlInt32` тип данных CLR в `int` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] тип данных.</span><span class="sxs-lookup"><span data-stu-id="80685-137">When a calling program executes the CLR stored procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically converts the `SqlInt32` CLR data type to an `int`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  <span data-ttu-id="80685-138">Дополнительные сведения о том, какие типы данных CLR могут и не могут быть преобразованы, см. в разделе [сопоставление данных параметров CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="80685-138">For more information about which CLR data types can and cannot be converted, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="80685-139">Возврат табличных результатов и сообщений</span><span class="sxs-lookup"><span data-stu-id="80685-139">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="80685-140">Возврат клиенту табличных результатов и сообщений выполняется через объект `SqlPipe`, получаемый при использовании свойства `Pipe` класса `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="80685-140">Returning tabular results and messages to the client is done through the `SqlPipe` object, which is obtained by using the `Pipe` property of the `SqlContext` class.</span></span> <span data-ttu-id="80685-141">Объект `SqlPipe` имеет метод `Send`.</span><span class="sxs-lookup"><span data-stu-id="80685-141">The `SqlPipe` object has a `Send` method.</span></span> <span data-ttu-id="80685-142">Вызвав метод `Send`, можно передать данные по каналу вызывающему приложению.</span><span class="sxs-lookup"><span data-stu-id="80685-142">By calling the `Send` method, you can transmit data through the pipe to the calling application.</span></span>  
  
 <span data-ttu-id="80685-143">Далее приводятся несколько перегрузок метода `SqlPipe.Send`, включая перегрузку, которая посылает объект `SqlDataReader`, а также другую перегрузку, которая просто посылает текстовую строку.</span><span class="sxs-lookup"><span data-stu-id="80685-143">These are several overloads of the `SqlPipe.Send` method, including one that sends a `SqlDataReader` and another that simply sends a text string.</span></span>  
  
###### <a name="returning-messages"></a><span data-ttu-id="80685-144">Возврат сообщений</span><span class="sxs-lookup"><span data-stu-id="80685-144">Returning Messages</span></span>  
 <span data-ttu-id="80685-145">Метод `SqlPipe.Send(string)` используется для передачи сообщений в клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="80685-145">Use `SqlPipe.Send(string)` to send messages to the client application.</span></span> <span data-ttu-id="80685-146">Текст сообщения ограничен 8000 символов.</span><span class="sxs-lookup"><span data-stu-id="80685-146">The text of the message is limited to 8000 characters.</span></span> <span data-ttu-id="80685-147">Если размер сообщения превышает 8000 символов, сообщение усекается.</span><span class="sxs-lookup"><span data-stu-id="80685-147">If the message exceeds 8000 characters, it will be truncated.</span></span>  
  
###### <a name="returning-tabular-results"></a><span data-ttu-id="80685-148">Возврат табличных результатов</span><span class="sxs-lookup"><span data-stu-id="80685-148">Returning Tabular Results</span></span>  
 <span data-ttu-id="80685-149">Чтобы послать результаты запроса непосредственно клиенту, используется один из перегруженных методов `Execute` на объекте `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="80685-149">To send the results of a query directly to the client, use one of the overloads of the `Execute` method on the `SqlPipe` object.</span></span> <span data-ttu-id="80685-150">Это наиболее эффективный способ возврата результатов клиенту, поскольку данные передаются в сетевые буферы без копирования в управляемую память.</span><span class="sxs-lookup"><span data-stu-id="80685-150">This is the most efficient way to return results to the client, since the data is transferred to the network buffers without being copied into managed memory.</span></span> <span data-ttu-id="80685-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="80685-151">For example:</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the results to the client directly.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void ExecuteToClient()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version", connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub ExecuteToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="80685-152">Чтобы послать результаты ранее выполненного запроса через внутрипроцессного поставщика или чтобы предварительно обработать данные с использованием пользовательской реализации `SqlDataReader`, используется перегрузка метода `Send`, которая принимает `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="80685-152">To send the results of a query that was executed previously through the in-process provider (or to pre-process the data using a custom implementation of `SqlDataReader`), use the overload of the `Send` method that takes a `SqlDataReader`.</span></span> <span data-ttu-id="80685-153">Этот метод немного медленнее, чем описанный выше непосредственный метод, но он обеспечивает большую гибкость при обработке данных перед их отправкой клиенту.</span><span class="sxs-lookup"><span data-stu-id="80685-153">This method is slightly slower than the direct method described previously, but it offers greater flexibility to manipulate the data before it is sent to the client.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the resulting reader to the client  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendReaderToClient()  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("select @@version", connection);  
         SqlDataReader r = command.ExecuteReader();  
         SqlContext.Pipe.Send(r);  
      }  
   }  
}  
```  
 
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendReaderToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="80685-154">Чтобы создать динамический результирующий набор, заполнить его и послать клиенту, можно создать записи на текущем соединении и послать их при помощи `SqlPipe.Send`.</span><span class="sxs-lookup"><span data-stu-id="80685-154">To create a dynamic result set, populate it and send it to the client, you can create records from the current connection and send them using `SqlPipe.Send`.</span></span>  
  
```csharp  
using System.Data;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
using System.Data.SqlTypes;  
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Create a result set on the fly and send it to the client.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendTransientResultSet()  
   {  
      // Create a record object that represents an individual row, including it's metadata.  
      SqlDataRecord record = new SqlDataRecord(new SqlMetaData("stringcol", SqlDbType.NVarChar, 128));  
  
      // Populate the record.  
      record.SetSqlString(0, "Hello World!");  
  
      // Send the record to the client.  
      SqlContext.Pipe.Send(record);  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Create a result set on the fly and send it to the client.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendTransientResultSet()  
        ' Create a record object that represents an individual row, including it's metadata.  
        Dim record As New SqlDataRecord(New SqlMetaData("stringcol", SqlDbType.NVarChar, 128) )  
  
        ' Populate the record.  
        record.SetSqlString(0, "Hello World!")  
  
        ' Send the record to the client.  
        SqlContext.Pipe.Send(record)          
    End Sub  
End Class   
```  
  
 <span data-ttu-id="80685-155">Здесь представлен пример отправки табличных результатов и сообщения через `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="80685-155">Here is an example of sending a tabular result and a message through `SqlPipe`.</span></span>  
  
```csharp  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void HelloWorld()  
   {  
      SqlContext.Pipe.Send("Hello world! It's now " + System.DateTime.Now.ToString()+"\n");  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT ProductNumber FROM ProductMaster", connection);  
         SqlDataReader reader = command.ExecuteReader();  
         SqlContext.Pipe.Send(reader);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub HelloWorld()  
        SqlContext.Pipe.Send("Hello world! It's now " & System.DateTime.Now.ToString() & "\n")  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT ProductNumber FROM ProductMaster", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class   
```  
  
 <span data-ttu-id="80685-156">Первый метод `Send` отправляет клиенту сообщение, а второй — табличные результаты с помощью объекта `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="80685-156">The first `Send` sends a message to the client, while the second sends a tabular result using `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="80685-157">Следует отметить, что эти примеры служат только для иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="80685-157">Note that these examples are for illustrative purposes only.</span></span> <span data-ttu-id="80685-158">Для приложений, ориентированных в основном на большой объем вычислений, больше подходят функции CLR, чем простые инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80685-158">CLR functions are more appropriate than simple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for computation-intensive applications.</span></span> <span data-ttu-id="80685-159">Эта хранимая процедура [!INCLUDE[tsql](../../includes/tsql-md.md)] почти эквивалентна процедуре из предыдущего примера:</span><span class="sxs-lookup"><span data-stu-id="80685-159">An almost equivalent [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure to the previous example is:</span></span>  
  
```sql
CREATE PROCEDURE HelloWorld() AS  
BEGIN  
PRINT('Hello world!')  
SELECT ProductNumber FROM ProductMaster  
END;  
```  
  
> [!NOTE]  
>  <span data-ttu-id="80685-160">Сообщения и результирующие наборы в клиентском приложении получаются по-разному.</span><span class="sxs-lookup"><span data-stu-id="80685-160">Messages and result sets are retrieved differently in the client application.</span></span> <span data-ttu-id="80685-161">Например, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] результирующие наборы отображаются в представлении **результатов** , а сообщения отображаются на панели **сообщений** .</span><span class="sxs-lookup"><span data-stu-id="80685-161">For instance, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] result sets appear in the **Results** view, and messages appear in the **Messages** pane.</span></span>  
  
 <span data-ttu-id="80685-162">Если сохранить приведенный выше код на языке Visual C# в файле с именем MyFirstUdp.cs и скомпилировать его следующей командой:</span><span class="sxs-lookup"><span data-stu-id="80685-162">If the above Visual C# code is saved in a file MyFirstUdp.cs and compiled with:</span></span>  
  
```console
csc /t:library /out:MyFirstUdp.dll MyFirstUdp.cs   
```  
  
 <span data-ttu-id="80685-163">Или если сохранить приведенный выше код на языке Visual Basic в файле с именем MyFirstUdp.vb и скомпилировать его следующей командой:</span><span class="sxs-lookup"><span data-stu-id="80685-163">Or, if the above Visual Basic code is saved in a file MyFirstUdp.vb and compiled with:</span></span>  
  
```console
vbc /t:library /out:MyFirstUdp.dll MyFirstUdp.vb   
```  
  
> [!NOTE]  
>  <span data-ttu-id="80685-164">Начиная с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], выполнение объектов баз данных языка Visual C++ (например, хранимых процедур), скомпилированных с параметром `/clr:pure`, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="80685-164">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], Visual C++ database objects (such as stored procedures) compiled with `/clr:pure` are not supported for execution.</span></span>  
  
 <span data-ttu-id="80685-165">Следующая инструкция DDL регистрирует результирующую сборку и вызывает точку входа:</span><span class="sxs-lookup"><span data-stu-id="80685-165">The resulting assembly can be registered, and the entry point invoked, with the following DDL:</span></span>  
  
```sql
CREATE ASSEMBLY MyFirstUdp FROM 'C:\Programming\MyFirstUdp.dll';  
CREATE PROCEDURE HelloWorld  
AS EXTERNAL NAME MyFirstUdp.StoredProcedures.HelloWorld;  
EXEC HelloWorld;  
```  
  
## <a name="see-also"></a><span data-ttu-id="80685-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="80685-166">See Also</span></span>  
 <span data-ttu-id="80685-167">[Определяемые пользователем функции среды CLR](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="80685-167">[CLR User-Defined Functions](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="80685-168">[Определяемые пользователем типы CLR](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="80685-168">[CLR User-Defined Types](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 [<span data-ttu-id="80685-169">Триггеры CLR</span><span class="sxs-lookup"><span data-stu-id="80685-169">CLR Triggers</span></span>](../../../2014/database-engine/dev-guide/clr-triggers.md)  
  
  
