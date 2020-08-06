---
title: Обновление столбцов определяемых пользователем типов с помощью DataAdapter | Документация Майкрософт
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
- ADO.NET [CLR integration]
- updating data [CLR integration]
- populating DataSet
- datasets [CLR integration]
- UDTs [CLR integration], ADO.NET
- updating UDT columns
- user-defined types [CLR integration], ADO.NET
- data adapters [CLR integration]
ms.assetid: 4489c938-ba03-4fdb-b533-cc3f5975ae50
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b908db850b1b77216824a5225d9bd8874387f78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666095"
---
# <a name="updating-udt-columns-with-dataadapters"></a><span data-ttu-id="c1be9-102">Обновление столбцов определяемых пользователем типов с помощью DataAdapter</span><span class="sxs-lookup"><span data-stu-id="c1be9-102">Updating UDT Columns with DataAdapters</span></span>
  <span data-ttu-id="c1be9-103">Определяемые пользователем типы поддерживаются с помощью объектов `System.Data.DataSet` и `System.Data.SqlClient.SqlDataAdapter` для получения и изменения данных.</span><span class="sxs-lookup"><span data-stu-id="c1be9-103">User-defined types (UDTs) are supported by using a `System.Data.DataSet` and a `System.Data.SqlClient.SqlDataAdapter` to retrieve and modify data.</span></span>  
  
## <a name="populating-a-dataset"></a><span data-ttu-id="c1be9-104">Заполнение набора данных</span><span class="sxs-lookup"><span data-stu-id="c1be9-104">Populating a Dataset</span></span>  
 <span data-ttu-id="c1be9-105">Инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT можно использовать для выбора значений столбцов определяемых пользователем типов, чтобы заполнить набор данных с помощью адаптера обработки данных.</span><span class="sxs-lookup"><span data-stu-id="c1be9-105">You can use a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement to select UDT column values to populate a dataset using a data adapter.</span></span> <span data-ttu-id="c1be9-106">В следующем примере предполагается, что у вас есть таблица **points** , определенная со следующей структурой и некоторыми примерами данных.</span><span class="sxs-lookup"><span data-stu-id="c1be9-106">The following example assumes that you have a **Points** table defined with the following structure and some sample data.</span></span> <span data-ttu-id="c1be9-107">Следующие [!INCLUDE[tsql](../../includes/tsql-md.md)] инструкции создают таблицу **points** и вставляют несколько строк.</span><span class="sxs-lookup"><span data-stu-id="c1be9-107">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements create the **Points** table and insert a few rows.</span></span>  
  
```  
CREATE TABLE dbo.Points (id int PRIMARY Key, p Point);  
  
INSERT INTO dbo.Points VALUES (1, CONVERT(Point, '1,3'));  
INSERT INTO dbo.Points VALUES (2, CONVERT(Point, '2,4'));  
INSERT INTO dbo.Points VALUES (3, CONVERT(Point, '3,5'));  
INSERT INTO dbo.Points VALUES (4, CONVERT(Point, '4,6'));  
GO  
```  
  
 <span data-ttu-id="c1be9-108">Следующий фрагмент кода ADO.NET извлекает допустимую строку соединения, создает новый объект `SqlDataAdapter` и заполняет его `System.Data.DataTable` строками данных из таблицы **points** .</span><span class="sxs-lookup"><span data-stu-id="c1be9-108">The following ADO.NET code fragment retrieves a valid connection string, creates a new `SqlDataAdapter`, and populates a `System.Data.DataTable` with the rows of data from the **Points** table.</span></span>  
  
```vb  
Dim da As New SqlDataAdapter( _  
    "SELECT id, p FROM dbo.Points", connectionString)  
Dim datTable As New DataTable("Points")  
da.Fill(datTable)  
```  
  
```csharp  
SqlDataAdapter da = new SqlDataAdapter(  
   "SELECT id, p FROM dbo.Points", connectionString);  
DataTable datTable = new DataTable("Points");  
da.Fill(datTable);  
```  
  
## <a name="updating-udt-data-in-a-dataset"></a><span data-ttu-id="c1be9-109">Обновление данных определяемых пользователем типов в наборе данных</span><span class="sxs-lookup"><span data-stu-id="c1be9-109">Updating UDT Data in a Dataset</span></span>  
 <span data-ttu-id="c1be9-110">Можно использовать два метода, чтобы обновить столбец данных определяемых пользователем типов в объекте `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="c1be9-110">You can use two methods to update a UDT column in a `DataSet`:</span></span>  
  
-   <span data-ttu-id="c1be9-111">Предоставить пользовательские объекты `InsertCommand`, `UpdateCommand` и `DeleteCommand` для объекта `SqlDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="c1be9-111">Provide custom `InsertCommand`, `UpdateCommand` and `DeleteCommand` objects for a `SqlDataAdapter` object.</span></span>  
  
-   <span data-ttu-id="c1be9-112">Использовать построитель команд (`System.Data.SqlClient.SqlCommandBuilder`) для автоматического создания команд INSERT, UPDATE и DELETE.</span><span class="sxs-lookup"><span data-stu-id="c1be9-112">Use the command builder (`System.Data.SqlClient.SqlCommandBuilder`) to create automatically the INSERT, UPDATE, and DELETE commands for you.</span></span> <span data-ttu-id="c1be9-113">Чтобы обнаруживать конфликты, добавьте столбец `timestamp` (псевдоним `rowversion`) в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которая содержит определяемый пользователем тип данных.</span><span class="sxs-lookup"><span data-stu-id="c1be9-113">In order to have conflict detection, add a `timestamp` column (alias `rowversion`) to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table that contains the UDT.</span></span> <span data-ttu-id="c1be9-114">Тип данных `timestamp` позволяет отмечать версии строк в таблице и гарантированно уникален в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c1be9-114">The `timestamp` data type allows you to version-stamp the rows in a table, and is guaranteed to be unique within a database.</span></span> <span data-ttu-id="c1be9-115">Если значение в таблице изменяется, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически обновляет 8-байтовое двоичное число для строки, затронутой изменением.</span><span class="sxs-lookup"><span data-stu-id="c1be9-115">When a value in the table is changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically updates the eight-byte binary number for the row affected by the change.</span></span>  
  
 <span data-ttu-id="c1be9-116">Обратите внимание, что объект `SqlCommandBuilder` не учитывает определяемый пользователем тип при обнаружении конфликтов, если в базовой таблице нет столбца `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="c1be9-116">Note that the `SqlCommandBuilder` does not consider the UDT for conflict detection unless there is a `timestamp` column in the underlying table.</span></span> <span data-ttu-id="c1be9-117">Определяемые пользователем типы могут быть несопоставимы, поэтому они не включаются в предложение WHERE, если для формирования команды используется режим сравнения с первоначальными значениями.</span><span class="sxs-lookup"><span data-stu-id="c1be9-117">UDTs may or may not be comparable, so they are not included in the WHERE clause when the "compare original values" option is used to generate a command.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c1be9-118">Пример</span><span class="sxs-lookup"><span data-stu-id="c1be9-118">Example</span></span>  
 <span data-ttu-id="c1be9-119">В следующем примере требуется создать вторую таблицу, содержащую столбец определяемого пользователем типа `Point`, а также столбец `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="c1be9-119">The following example requires the creation of a second table containing the `Point` UDT column as well as a `timestamp` column.</span></span> <span data-ttu-id="c1be9-120">Обе таблицы используются, чтобы показать, как создать пользовательские командные объекты для обновления данных и как выполнить обновление с помощью столбца `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="c1be9-120">Both tables are used to illustrate how to create custom command objects to update data, and how to update using a `timestamp` column.</span></span> <span data-ttu-id="c1be9-121">Запустите следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)], чтобы создать вторую таблицу и заполнить ее образцами данными.</span><span class="sxs-lookup"><span data-stu-id="c1be9-121">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to create the second table and populate it with sample data.</span></span>  
  
```  
CREATE TABLE dbo.Points_ts (id int PRIMARY KEY, p Point, ts timestamp);  
  
INSERT INTO dbo.Points_ts (id, p) VALUES (1, CONVERT(Point, '1,3'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (2, CONVERT(Point, '2,4'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (3, CONVERT(Point, '3,5'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (4, CONVERT(Point, '4,6'));  
```  
  
 <span data-ttu-id="c1be9-122">В следующем примере ADO.NET используются два метода.</span><span class="sxs-lookup"><span data-stu-id="c1be9-122">The following ADO.NET example has two methods:</span></span>  
  
-   <span data-ttu-id="c1be9-123">`UserProvidedCommands`, в котором демонстрируется предоставление `InsertCommand` `UpdateCommand` объектов, и `DeleteCommand` для обновления `Point` определяемого пользователем типа в таблице **points** (которая не содержит `timestamp` столбца).</span><span class="sxs-lookup"><span data-stu-id="c1be9-123">`UserProvidedCommands`, which demonstrates how to supply `InsertCommand`, `UpdateCommand`, and `DeleteCommand` objects for updating the `Point` UDT in the **Points** table (which does not contain a `timestamp` column).</span></span>  
  
-   <span data-ttu-id="c1be9-124">`CommandBuilder`, который демонстрирует использование `SqlCommandBuilder` в таблице **Points_ts** , содержащей `timestamp` столбец.</span><span class="sxs-lookup"><span data-stu-id="c1be9-124">`CommandBuilder`, which demonstrates how to use a `SqlCommandBuilder` in the **Points_ts** table that contains the `timestamp` column.</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
    ' Retrieves the connection string  
    Private connString As String = GetConnectionString()  
  
    Sub Main()  
        UserProvidedCommands()  
        CommandBuilder()  
    End Sub  
  
    Private Sub UserProvidedCommands()  
        ' Create a new SqlDataAdapter  
        Dim da As New SqlDataAdapter( _  
          "SELECT id, p FROM dbo.Points", connString)  
  
        ' Setup the INSERT/UPDATE/DELETE commands  
        Dim idParam As SqlParameter  
        Dim pointParam As SqlParameter  
  
        da.InsertCommand = New SqlCommand( _  
          "INSERT INTO dbo.Points (id, p) VALUES (@id, @p)", _  
          da.SelectCommand.Connection)  
        idParam = da.InsertCommand.Parameters.Add( _  
          "@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
        pointParam = da.InsertCommand.Parameters.Add( _  
          "@p", SqlDbType.Udt)  
        pointParam.SourceColumn = "p"  
        pointParam.UdtTypeName = "dbo.Point"  
  
        da.UpdateCommand = New SqlCommand( _  
          "UPDATE dbo.Points SET p = @p WHERE id = @id", _  
          da.SelectCommand.Connection)  
        idParam = _  
           da.UpdateCommand.Parameters.Add("@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
        pointParam = da.UpdateCommand.Parameters.Add( _  
          "@p", SqlDbType.Udt)  
        pointParam.SourceColumn = "p"  
        pointParam.UdtTypeName = "dbo.Point"  
  
        da.DeleteCommand = New SqlCommand( _  
          "DELETE dbo.Points WHERE id = @id", _  
          da.SelectCommand.Connection)  
        idParam = da.DeleteCommand.Parameters.Add( _  
          "@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
  
        ' Fill the DataTable with UDT rows  
        Dim datTable As New DataTable("Points")  
        da.Fill(datTable)  
  
        ' Display the contents of the p (Point) column  
        Dim r As DataRow  
        For Each r In datTable.Rows  
            Dim p As Point = CType(r(1), Point)  
            Console.WriteLine( _  
              "ID: {0}, x={1}, y={1}", r(0), p.X, p.Y)  
        Next r  
  
        ' Update a row if the DataTable has at least 1 row  
        If datTable.Rows.Count > 0 Then  
            Dim oldPoint As Point = _  
              CType(datTable.Rows(0)(1), Point)  
            datTable.Rows(0)(1) = _  
              New Point(oldPoint.X + 1, oldPoint.Y + 1)  
        End If  
  
        ' Delete the last row  
        If datTable.Rows.Count > 0 Then  
            ' If we have at least 1 row  
            datTable.Rows(1).Delete()  
        End If  
  
        ' Insert a row. This will fail if run twice  
        ' because 100 is a primary key value.  
        datTable.Rows.Add(100, New Point(100, 200))  
  
        ' Send the changes back to the database  
        da.Update(datTable)  
    End Sub  
  
    Private Sub CommandBuilder()  
        ' Create a new SqlDataAdapter  
        Dim da As New SqlDataAdapter( _  
          "SELECT id, ts, p FROM dbo.Points_ts", connString)  
  
        ' Select a few rows with UDTs from the database  
        Dim datTable As New DataTable("Points")  
        da.Fill(datTable)  
  
        ' Display the contents of the p (Point) column  
        Dim r As DataRow  
        For Each r In datTable.Rows  
            Dim p As Point = CType(r(2), Point)  
            Console.WriteLine( _  
              "ID: {0}, x={1}, y={1}", r(0), p.X, p.Y)  
        Next r  
  
        ' Update a row if DataTable has at least 1 row  
        If datTable.Rows.Count > 0 Then  
            Dim oldPoint As Point = _  
              CType(datTable.Rows(0)(2), Point)  
            datTable.Rows(0)(2) = _  
              New Point(oldPoint.X + 1, oldPoint.Y + 1)  
        End If  
  
        ' Delete the last row  
        If datTable.Rows.Count > 0 Then  
            ' if we have at least 1 row  
            datTable.Rows(1).Delete()  
        End If  
  
        ' Insert a row. This will fail if run twice  
        ' because 100 is a primary key value  
        datTable.Rows.Add(100, Nothing, New Point(100, 200))  
  
        ' Use the CommandBuilder to generate DML statements  
        Dim bld As New SqlCommandBuilder(da)  
        bld.ConflictDetection = ConflictOptions.CompareRowVersion  
  
        ' Send the changes back to the database  
        da.Update(datTable)  
    End Sub  
  
  Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,   
      ' you can retrieve it from a configuration file.  
     Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
       & "Integrated Security=SSPI"  
   End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Class1  
  {  
// Retrieves the connection string  
private string connString = GetConnectionString();  
  
static void Main()  
{  
        UserProvidedCommands();  
        CommandBuilder();  
 }  
    static void UserProvidedCommands()  
    {  
        // Create a new SqlDataAdapter  
        SqlDataAdapter da = new SqlDataAdapter(  
          "SELECT id, p FROM dbo.Points", connString);  
  
        // Setup the INSERT/UPDATE/DELETE commands  
        SqlParameter idParam;  
        SqlParameter pointParam;  
  
        da.InsertCommand = new SqlCommand(  
            "INSERT INTO dbo.Points (id, p) VALUES (@id, @p)",   
             da.SelectCommand.Connection);  
        idParam =   
            da.InsertCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
        pointParam =   
            da.InsertCommand.Parameters.Add("@p", SqlDbType.Udt);  
        pointParam.SourceColumn = "p";  
        pointParam.UdtTypeName = "dbo.Point";  
  
        da.UpdateCommand = new SqlCommand(  
            "UPDATE dbo.Points SET p = @p WHERE id = @id",   
            da.SelectCommand.Connection);  
        idParam =   
            da.UpdateCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
        pointParam =   
            da.UpdateCommand.Parameters.Add("@p", SqlDbType.Udt);  
        pointParam.SourceColumn = "p";  
        pointParam.UdtTypeName = "dbo.Point";   
  
        da.DeleteCommand = new SqlCommand(  
            "DELETE dbo.Points WHERE id = @id",   
            da.SelectCommand.Connection);  
        idParam =   
            da.DeleteCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
  
        // Fill the DataTable with UDT rows  
        DataTable datTable = new DataTable("Points");  
        da.Fill(datTable);  
  
        // Display the contents of the p (Point) column  
        foreach(DataRow r in datTable.Rows)   
        {  
            Point p = (Point)r[1];  
            Console.WriteLine(  
                "ID: {0}, x={1}, y={1}", r[0], p.X, p.Y);  
        }  
  
        // Update a row if the DataTable has at least 1 row  
        if(datTable.Rows.Count > 0 )   
        {   
            Point oldPoint = (Point)datTable.Rows[0][1];  
            datTable.Rows[0][1] =   
                new Point(oldPoint.X+1, oldPoint.Y+1);  
        }  
  
        // Delete the last row  
        if(datTable.Rows.Count > 0 )   
        { // If we have at least 1 row  
            datTable.Rows[1].Delete();  
        }  
  
        // Insert a row. This will fail if run twice  
        // because 100 is a primary key value.  
        datTable.Rows.Add(100, new Point(100, 200));   
  
        // Send the changes back to the database  
        da.Update(datTable);  
    }  
  
    static void CommandBuilder()  
    {  
        // Create a new SqlDataAdapter  
        SqlDataAdapter da = new SqlDataAdapter(  
            "SELECT id, ts, p FROM dbo.Points_ts", connString);  
  
        // Select a few rows with UDTs from the database  
        DataTable datTable = new DataTable("Points");  
        da.Fill(datTable);  
  
        // Display the contents of the p (Point) column  
        foreach (DataRow r in datTable.Rows)  
        {  
            Point p = (Point)r[2];  
            Console.WriteLine(  
                "ID: {0}, x={1}, y={1}", r[0], p.X, p.Y);  
        }  
  
        // Update a row if DataTable has at least 1 row  
        if (datTable.Rows.Count > 0)  
        {   
            Point oldPoint = (Point)datTable.Rows[0][2];  
            datTable.Rows[0][2] =   
                new Point(oldPoint.X + 1, oldPoint.Y + 1);  
        }  
  
        // Delete the last row  
        if (datTable.Rows.Count > 0)  
        { // if we have at least 1 row  
            datTable.Rows[1].Delete();  
        }  
  
        // Insert a row. This will fail if run twice  
        // because 100 is a primary key value  
        datTable.Rows.Add(100, null, new Point(100, 200));   
  
        // Use the CommandBuilder to generate DML statements  
        SqlCommandBuilder bld = new SqlCommandBuilder(da);  
        bld.ConflictDetection = ConflictOptions.CompareRowVersion;  
  
        // Send the changes back to the database  
        da.Update(datTable);  
    }  
  
 static private string GetConnectionString()  
 {  
 // To avoid storing the connection string in your code,   
 // you can retrieve it from a configuration file.  
    return "Data Source=localhost;Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1be9-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="c1be9-125">See Also</span></span>  
 [<span data-ttu-id="c1be9-126">Доступ к определяемым пользователем типам в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c1be9-126">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
