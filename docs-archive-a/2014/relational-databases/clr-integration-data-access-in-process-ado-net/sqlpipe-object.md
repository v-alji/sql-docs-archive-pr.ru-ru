---
title: Объект SqlPipe | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- custom result sets [CLR integration]
- SqlPipe object
- tabular results
ms.assetid: 3e090faf-085f-4c01-a565-79e3f1c36e3b
author: rothja
ms.author: jroth
ms.openlocfilehash: 0044815a0b20d72b48b87bfe8f693d7196aaeaf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665384"
---
# <a name="sqlpipe-object"></a><span data-ttu-id="dd723-102">Объект SqlPipe</span><span class="sxs-lookup"><span data-stu-id="dd723-102">SqlPipe Object</span></span>
  <span data-ttu-id="dd723-103">В предыдущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]обычным было написание хранимой процедуры (или расширенной хранимой процедуры), которая отправляет результаты или выдает выходные параметры вызывающему клиенту.</span><span class="sxs-lookup"><span data-stu-id="dd723-103">In previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is very common to write a stored procedure (or an extended stored procedure) that sends results or output parameters to the calling client.</span></span>  
  
 <span data-ttu-id="dd723-104">В хранимой процедуре [!INCLUDE[tsql](../../includes/tsql-md.md)] любая инструкция `SELECT`, которая возвращает ноль или более строк, отправляет результаты в «канал» подключенного вызывающего.</span><span class="sxs-lookup"><span data-stu-id="dd723-104">In a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, any `SELECT` statement that returns zero or more rows sends the results to the connected caller's "pipe."</span></span>  
  
 <span data-ttu-id="dd723-105">Результаты по объектам базы данных CLR, работающей на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], могут отправляться в подключенный канал при помощи методов `Send` объекта `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="dd723-105">For common language runtime (CLR) database objects running in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can send results to the connected pipe using the `Send` methods of the `SqlPipe` object.</span></span> <span data-ttu-id="dd723-106">Обратитесь к свойству `Pipe` объекта `SqlContext`, чтобы получить объект `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="dd723-106">Access the `Pipe` property of the `SqlContext` object to obtain the `SqlPipe` object.</span></span> <span data-ttu-id="dd723-107">Класс `SqlPipe` принципиально подобен классу `Response` в ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dd723-107">The `SqlPipe` class is conceptually similar to the `Response` class found in ASP.NET.</span></span> <span data-ttu-id="dd723-108">Дополнительные сведения см. в справочной документации по классу SqlPipe в пакете средств разработки программного обеспечения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dd723-108">For more information, see the SqlPipe Class reference documentation in the .NET Framework software development kit.</span></span>  
  
## <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="dd723-109">Возврат табличных результатов и сообщений</span><span class="sxs-lookup"><span data-stu-id="dd723-109">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="dd723-110">Класс `SqlPipe` имеет метод `Send`, который имеет три перегрузки.</span><span class="sxs-lookup"><span data-stu-id="dd723-110">The `SqlPipe` has a `Send` method, which has three overloads.</span></span> <span data-ttu-id="dd723-111">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="dd723-111">They are:</span></span>  
  
-   `void Send(string message)`  
  
-   `void Send(SqlDataReader reader)`  
  
-   `void Send(SqlDataRecord record)`  
  
 <span data-ttu-id="dd723-112">Метод `Send` пересылает данные напрямую клиенту или вызывающему.</span><span class="sxs-lookup"><span data-stu-id="dd723-112">The `Send` method sends data straight to the client or caller.</span></span> <span data-ttu-id="dd723-113">Обычно клиент использует выход из `SqlPipe`, но в случае вложенных хранимых процедур CLR потребителем выхода также может быть хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="dd723-113">It is usually the client that consumes the output from the `SqlPipe`, but in the case of nested CLR stored procedures the output consumer can also be a stored procedure.</span></span> <span data-ttu-id="dd723-114">Например, Procedure1 вызывает SqlCommand.ExecuteReader() с текстом команды «EXEC Procedure2».</span><span class="sxs-lookup"><span data-stu-id="dd723-114">For example, Procedure1 calls SqlCommand.ExecuteReader() with the command text "EXEC Procedure2".</span></span> <span data-ttu-id="dd723-115">Procedure2 — это также управляемая хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="dd723-115">Procedure2 is also a managed stored procedure.</span></span> <span data-ttu-id="dd723-116">Если Procedure2 вызывает SqlPipe.Send( SqlDataRecord ), строка передается модулю чтения Procedure1, но не клиенту.</span><span class="sxs-lookup"><span data-stu-id="dd723-116">If Procedure2 now calls SqlPipe.Send( SqlDataRecord ), the row is sent to Procedure1's reader, not the client.</span></span>  
  
 <span data-ttu-id="dd723-117">Метод `Send` посылает строку сообщения, которая отображается на клиенте как информационное сообщение, эквивалентное PRINT в [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd723-117">The `Send` method sends a string message that appears on the client as an information message, equivalent to PRINT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="dd723-118">Метод может также послать однострочный результирующий набор с помощью `SqlDataRecord` или многострочный результирующий набор с использованием `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="dd723-118">It can also send a single-row result-set using `SqlDataRecord`, or a multi-row result-set using a `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="dd723-119">Объект `SqlPipe` также имеет метод `ExecuteAndSend`.</span><span class="sxs-lookup"><span data-stu-id="dd723-119">The `SqlPipe` object also has an `ExecuteAndSend` method.</span></span> <span data-ttu-id="dd723-120">Этот метод можно использовать, чтобы выполнять команды (переданные как объект `SqlCommand`) и напрямую отправлять результаты назад вызывающему.</span><span class="sxs-lookup"><span data-stu-id="dd723-120">This method can be used to execute a command (passed as a `SqlCommand` object) and send results directly back to the caller.</span></span> <span data-ttu-id="dd723-121">Если в представленной команде есть ошибки, исключения передаются в канал, но копия пересылается также вызывающему управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="dd723-121">If there are errors in the command that was submitted, exceptions are sent to the pipe, but a copy is also sent to calling managed code.</span></span> <span data-ttu-id="dd723-122">Если вызывающий код не перехватывает исключение, оно распространяется по стеку в код [!INCLUDE[tsql](../../includes/tsql-md.md)] и дважды появляется в выходе.</span><span class="sxs-lookup"><span data-stu-id="dd723-122">If the calling code does not catch the exception, it propagates up the stack to the [!INCLUDE[tsql](../../includes/tsql-md.md)] code and appears in the output twice.</span></span> <span data-ttu-id="dd723-123">Если вызывающий код перехватывает исключение, потребитель канала по-прежнему видит ошибку, но повторяющейся ошибки нет.</span><span class="sxs-lookup"><span data-stu-id="dd723-123">If the calling code does catch the exception, the pipe consumer still sees the error, but there is not a duplicate error.</span></span>  
  
 <span data-ttu-id="dd723-124">Он может принять только команду `SqlCommand`, которая ассоциирована с контекстным соединением. Этот метод не может принять команду, которая сопоставлена соединению вне данного контекста.</span><span class="sxs-lookup"><span data-stu-id="dd723-124">It can only take a `SqlCommand` that is associated with the context connection; it cannot take a command that is associated with the non-context connection.</span></span>  
  
## <a name="returning-custom-result-sets"></a><span data-ttu-id="dd723-125">Возвращение пользовательских результирующих наборов</span><span class="sxs-lookup"><span data-stu-id="dd723-125">Returning Custom Result Sets</span></span>  
 <span data-ttu-id="dd723-126">Управляемые хранимые процедуры могут отправлять результирующие наборы, которые не исходят из `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="dd723-126">Managed stored procedures can send result sets that do not come from a `SqlDataReader`.</span></span> <span data-ttu-id="dd723-127">Метод `SendResultsStart` вместе с методами `SendResultsRow` и `SendResultsEnd` позволяет хранимым процедурам отправлять клиенту пользовательские результирующие наборы.</span><span class="sxs-lookup"><span data-stu-id="dd723-127">The `SendResultsStart` method, along with `SendResultsRow` and `SendResultsEnd`, allows stored procedures to send custom result sets to the client.</span></span>  
  
 <span data-ttu-id="dd723-128">Метод `SendResultsStart` принимает объект `SqlDataRecord` в качестве ввода.</span><span class="sxs-lookup"><span data-stu-id="dd723-128">`SendResultsStart` takes a `SqlDataRecord` as an input.</span></span> <span data-ttu-id="dd723-129">Он отмечает начало результирующего набора и при помощи метаданных записи составляет метаданные, описывающие результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="dd723-129">It marks the beginning of a result set and uses the record metadata to construct the metadata that describes the result set.</span></span> <span data-ttu-id="dd723-130">Он не отправляет значение записи с `SendResultsStart`.</span><span class="sxs-lookup"><span data-stu-id="dd723-130">It does not send the value of the record with `SendResultsStart`.</span></span> <span data-ttu-id="dd723-131">Все последующие строки, отправленные при помощи метода `SendResultsRow`, должны соответствовать этому определению метаданных.</span><span class="sxs-lookup"><span data-stu-id="dd723-131">All the subsequent rows, sent using `SendResultsRow`, must match that metadata definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd723-132">После вызова метода `SendResultsStart` можно вызвать только методы `SendResultsRow` и `SendResultsEnd`.</span><span class="sxs-lookup"><span data-stu-id="dd723-132">After calling the `SendResultsStart` method only `SendResultsRow` and `SendResultsEnd` can be called.</span></span> <span data-ttu-id="dd723-133">Вызов любого другого метода в том же экземпляре объекта `SqlPipe` приводит к исключению `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="dd723-133">Calling any other method in the same instance of `SqlPipe` causes an `InvalidOperationException`.</span></span> <span data-ttu-id="dd723-134">Метод `SendResultsEnd` возвращает объект `SqlPipe` в исходное состояние, в котором можно вызывать другие методы.</span><span class="sxs-lookup"><span data-stu-id="dd723-134">`SendResultsEnd` sets `SqlPipe` back to the initial state in which other methods can be called.</span></span>  
  
### <a name="example"></a><span data-ttu-id="dd723-135">Пример</span><span class="sxs-lookup"><span data-stu-id="dd723-135">Example</span></span>  
 <span data-ttu-id="dd723-136">Хранимая процедура `uspGetProductLine` возвращает название, номер продукта, цвет и цену по прейскуранту всех продуктов в указанной линейке продуктов.</span><span class="sxs-lookup"><span data-stu-id="dd723-136">The `uspGetProductLine` stored procedure returns the name, product number, color, and list price of all products within a specified product line.</span></span> <span data-ttu-id="dd723-137">Эта хранимая процедура принимает точные совпадения с *prodLine*.</span><span class="sxs-lookup"><span data-stu-id="dd723-137">This stored procedure accepts exact matches for *prodLine*.</span></span>  
  
 <span data-ttu-id="dd723-138">C#</span><span class="sxs-lookup"><span data-stu-id="dd723-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspGetProductLine(SqlString prodLine)  
{  
    // Connect through the context connection.  
    using (SqlConnection connection = new SqlConnection("context connection=true"))  
    {  
        connection.Open();  
  
        SqlCommand command = new SqlCommand(  
            "SELECT Name, ProductNumber, Color, ListPrice " +  
            "FROM Production.Product " +   
            "WHERE ProductLine = @prodLine;", connection);  
  
        command.Parameters.AddWithValue("@prodLine", prodLine);  
  
        try  
        {  
            // Execute the command and send the results to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command);  
        }  
        catch (System.Data.SqlClient.SqlException ex)  
        {  
            // An error occurred executing the SQL command.  
        }  
     }  
}  
};  
```  
  
 <span data-ttu-id="dd723-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd723-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub uspGetProductLine(ByVal prodLine As SqlString)  
    Dim command As SqlCommand  
  
    ' Connect through the context connection.  
    Using connection As New SqlConnection("context connection=true")  
        connection.Open()  
  
        command = New SqlCommand( _  
        "SELECT Name, ProductNumber, Color, ListPrice " & _  
        "FROM Production.Product " & _  
        "WHERE ProductLine = @prodLine;", connection)  
        command.Parameters.AddWithValue("@prodLine", prodLine)  
  
        Try  
            ' Execute the command and send the results   
            ' directly to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command)  
        Catch ex As System.Data.SqlClient.SqlException  
            ' An error occurred executing the SQL command.  
        End Try  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="dd723-140">Следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] выполняет процедуру `uspGetProduct`, которая возвращает список продуктов, относящихся к категории туристических велосипедов.</span><span class="sxs-lookup"><span data-stu-id="dd723-140">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement executes the `uspGetProduct` procedure, which returns a list of touring bike products.</span></span>  
  
```  
EXEC uspGetProductLineVB 'T';  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd723-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd723-141">See Also</span></span>  
 <span data-ttu-id="dd723-142">[Объект SqlDataRecord](sqldatarecord-object.md) </span><span class="sxs-lookup"><span data-stu-id="dd723-142">[SqlDataRecord Object](sqldatarecord-object.md) </span></span>  
 <span data-ttu-id="dd723-143">[Хранимые процедуры CLR](../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dd723-143">[CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="dd723-144">Внутрипроцессные расширения SQL Server для ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dd723-144">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
