---
title: Извлечение данных определяемого пользователем типа | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SqlDataReader object
- ADO.NET [CLR integration]
- binding UDTs [CLR integration]
- UDTs [CLR integration], ADO.NET
- assemblies [CLR integration], user-defined types
- query parameters [CLR integration]
- user-defined types [CLR integration], ADO.NET
- bytes [CLR integration]
ms.assetid: 6a98ac8c-0e69-4c03-83a4-2062cb782049
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9133ea45069f76e7590f6b74d3c1e1cb98c7bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666098"
---
# <a name="retrieving-udt-data"></a><span data-ttu-id="e9a70-102">Получение данных определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="e9a70-102">Retrieving UDT Data</span></span>
  <span data-ttu-id="e9a70-103">Чтобы создать на клиенте определяемый пользователем тип, сборка, зарегистрированная в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] как определяемый пользователем тип, должна быть доступна для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="e9a70-103">In order to create a user-defined type (UDT) on the client, the assembly that was registered as a UDT in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database must be available to the client application.</span></span> <span data-ttu-id="e9a70-104">Сборку определяемого пользователем типа можно разместить в одном каталоге с приложением или в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="e9a70-104">The UDT assembly can be placed in the same directory with the application, or in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="e9a70-105">Также можно задать ссылку на сборку в проекте.</span><span class="sxs-lookup"><span data-stu-id="e9a70-105">You can also set a reference to the assembly in your project.</span></span>  
  
## <a name="requirements-for-using-udts-in-adonet"></a><span data-ttu-id="e9a70-106">Требования к использованию определяемых пользователем типов в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9a70-106">Requirements for Using UDTs in ADO.NET</span></span>  
 <span data-ttu-id="e9a70-107">Чтобы создать на клиенте определяемый пользователем тип, сборка, загруженная в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], и сборка на клиенте должны быть совместимы.</span><span class="sxs-lookup"><span data-stu-id="e9a70-107">The assembly loaded in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the assembly on the client must be compatible in order for the UDT to be created on the client.</span></span> <span data-ttu-id="e9a70-108">Для определяемых пользователем типов, определенных с помощью формата сериализации `Native`, сборки должны быть структурно совместимы.</span><span class="sxs-lookup"><span data-stu-id="e9a70-108">For UDTs defined with the `Native` serialization format, the assemblies must be structurally compatible.</span></span> <span data-ttu-id="e9a70-109">Сборки, определенные с помощью формата `UserDefined`, должны быть доступны на клиенте.</span><span class="sxs-lookup"><span data-stu-id="e9a70-109">For assemblies defined with the `UserDefined` format, the assembly must be available on the client.</span></span>  
  
 <span data-ttu-id="e9a70-110">Для получения необработанных данных из столбца определяемого пользователем типа таблицы копировать сборку определяемого пользователем типа на клиент не нужно.</span><span class="sxs-lookup"><span data-stu-id="e9a70-110">You do not need a copy of the UDT assembly on the client in order to retrieve the raw data from a UDT column in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9a70-111">**SqlClient** может не загрузить определяемый пользователем тип в случае несовпадения версий ОПРЕДЕЛЯЕМОГО пользователем типа или других проблем.</span><span class="sxs-lookup"><span data-stu-id="e9a70-111">**SqlClient** may fail to load a UDT in the event of mismatched UDT versions or other problems.</span></span> <span data-ttu-id="e9a70-112">В этом случае для определения причин, по которым сборку, содержащую определяемый пользователем тип, нельзя использовать в вызывающем приложении, используйте обычные механизмы устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="e9a70-112">In this case, use regular troubleshooting mechanisms to determine why the assembly containing the UDT cannot be found by the calling application.</span></span> <span data-ttu-id="e9a70-113">Дополнительные сведения см. в разделе «Диагностика ошибок с помощью управляемых помощников по отладке» документации по платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9a70-113">For more information, read the topic titled "Diagnosing Errors with Managed Debugging Assistants" in the .NET Framework documentation.</span></span>  
  
## <a name="accessing-udts-with-a-sqldatareader"></a><span data-ttu-id="e9a70-114">Доступ к определяемым пользователем типам с помощью объекта SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="e9a70-114">Accessing UDTs with a SqlDataReader</span></span>  
 <span data-ttu-id="e9a70-115">Для получения результирующего набора, содержащего столбец определяемого пользователем типа, в клиентском коде можно использовать объект `System.Data.SqlClient.SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="e9a70-115">A `System.Data.SqlClient.SqlDataReader` can be used from client code to retrieve a result set that contains a UDT column, which is exposed as an instance of the object.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e9a70-116">Пример</span><span class="sxs-lookup"><span data-stu-id="e9a70-116">Example</span></span>  
 <span data-ttu-id="e9a70-117">В этом примере показано, как использовать метод `Main` для создания нового объекта `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="e9a70-117">This example shows how to use the `Main` method to create a new `SqlDataReader` object.</span></span> <span data-ttu-id="e9a70-118">В этом примере кода выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e9a70-118">The following actions occur within the code example:</span></span>  
  
1.  <span data-ttu-id="e9a70-119">Метод Main создает новый объект `SqlDataReader` и получает значения от таблицы Points, имеющей столбец определяемого пользователем типа с именем Point.</span><span class="sxs-lookup"><span data-stu-id="e9a70-119">The Main method creates a new `SqlDataReader` object and retrieves the values from the Points table, which has a UDT column named Point.</span></span>  
  
2.  <span data-ttu-id="e9a70-120">Определяемый пользователем тип Point представляет координаты X и Y, определенные как целые числа.</span><span class="sxs-lookup"><span data-stu-id="e9a70-120">The Point UDT exposes X and Y coordinates defined as integers.</span></span>  
  
3.  <span data-ttu-id="e9a70-121">Определяемый пользователем тип имеет методы `Distance` и `GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="e9a70-121">The UDT defines a `Distance` method and a `GetDistanceFromXY` method.</span></span>  
  
4.  <span data-ttu-id="e9a70-122">Образец кода получает значения первичного ключа и столбцов определяемого пользователем типа, чтобы продемонстрировать его возможности.</span><span class="sxs-lookup"><span data-stu-id="e9a70-122">The sample code retrieves the values of the primary key and UDT columns in order to demonstrate the capabilities of the UDT.</span></span>  
  
5.  <span data-ttu-id="e9a70-123">Образец кода вызывает методы `Point.Distance` и `Point.GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="e9a70-123">The sample code calls the `Point.Distance` and `Point.GetDistanceFromXY` methods.</span></span>  
  
6.  <span data-ttu-id="e9a70-124">Результаты выводятся в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="e9a70-124">The results are displayed in the console window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9a70-125">Приложение должно содержать ссылку на сборку определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="e9a70-125">The application must already have a reference to the UDT assembly.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module ReadPoints  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the value of the UDT  
                Dim pnt As Point = CType(rdr(1), Point)  
  
             ' You can also use GetSqlValue and GetValue  
             ' Dim pnt As Point = CType(rdr.GetSqlValue(1), Point)  
             ' Dim pnt As Point = CType(rdr.GetValue(1), Point)  
  
                ' Print values  
                Console.WriteLine( _  
                 "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}", _  
                  id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance())  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
         & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
namespace Microsoft.Samples.SqlServer  
{  
class ReadPoints  
{  
static void Main()  
{  
  string connectionString = GetConnectionString();  
  using (SqlConnection cnn = new SqlConnection(connectionString))  
  {  
    cnn.Open();  
    SqlCommand cmd = new SqlCommand(  
       "SELECT ID, Pnt FROM dbo.Points", cnn);  
    SqlDataReader rdr = cmd.ExecuteReader();  
  
    while (rdr.Read())  
    {  
      // Retrieve the value of the Primary Key column  
      int id = rdr.GetInt32(0);  
  
        // Retrieve the value of the UDT  
        Point pnt = (Point)rdr[1];  
  
        // You can also use GetSqlValue and GetValue  
        // Point pnt = (Point)rdr.GetSqlValue(1);  
        // Point pnt = (Point)rdr.GetValue(1);  
  
        Console.WriteLine(  
        "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}",   
        id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance());  
    }  
  rdr.Close();  
  Console.WriteLine("done");  
  }  
  static private string GetConnectionString()  
  {  
    // To avoid storing the connection string in your code,   
    // you can retrieve it from a configuration file.  
    return "Data Source=(local);Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="binding-udts-as-bytes"></a><span data-ttu-id="e9a70-126">Привязка определяемых пользователем типов в виде байт</span><span class="sxs-lookup"><span data-stu-id="e9a70-126">Binding UDTs as Bytes</span></span>  
 <span data-ttu-id="e9a70-127">Иногда может потребоваться получить необработанные данные из столбца определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="e9a70-127">In some situations, you may want to retrieve the raw data from the UDT column.</span></span> <span data-ttu-id="e9a70-128">Возможно, что тип недоступен локально, либо создание экземпляра определяемого пользователем типа нежелательно.</span><span class="sxs-lookup"><span data-stu-id="e9a70-128">Perhaps the type is not available locally, or you do not wish to instantiate an instance of the UDT.</span></span> <span data-ttu-id="e9a70-129">Можно считать необработанные байты в массив байтов с помощью метода **GetBytes** объекта `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="e9a70-129">You can read the raw bytes into a byte array using the **GetBytes** method of a `SqlDataReader`.</span></span> <span data-ttu-id="e9a70-130">Этот метод считывает поток байт с указанного смещения столбца в буфер в виде массива, начиная с указанного смещения.</span><span class="sxs-lookup"><span data-stu-id="e9a70-130">This method reads a stream of bytes from the specified column offset into the buffer of an array starting at a specified buffer offset.</span></span> <span data-ttu-id="e9a70-131">Другим вариантом является использование одного из методов **жетсклбитес** или **жетсклбинари** и чтение всего содержимого в одной операции.</span><span class="sxs-lookup"><span data-stu-id="e9a70-131">Another option is to use one of the **GetSqlBytes** or **GetSqlBinary** methods and read all of the contents in a single operation.</span></span> <span data-ttu-id="e9a70-132">В любом случае объект определяемого пользователем типа не создается, так что в клиентской сборке создание ссылки на определяемый пользователем тип не требуется.</span><span class="sxs-lookup"><span data-stu-id="e9a70-132">In either case, the UDT object is never instantiated, so you do not need to set a reference to the UDT in the client assembly.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e9a70-133">Пример</span><span class="sxs-lookup"><span data-stu-id="e9a70-133">Example</span></span>  
 <span data-ttu-id="e9a70-134">В этом примере показано, как получить данные **точки** как необработанные байты в массив байтов с помощью `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="e9a70-134">This example shows how to retrieve the **Point** data as raw bytes into a byte array using a `SqlDataReader`.</span></span> <span data-ttu-id="e9a70-135">В этом коде используется класс `System.Text.StringBuilder` для преобразования байтового в символьное представление, применяемое для отображения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="e9a70-135">The code uses a `System.Text.StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the raw bytes into a byte array  
                Dim buffer(31) As Byte  
                Dim byteCount As Integer = _  
                 CInt(rdr.GetBytes(1, 0, buffer, 0, 31))  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", buffer(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
        string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand("SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Retrieve the raw bytes into a byte array  
                byte[] buffer = new byte[32];  
                long byteCount = rdr.GetBytes(1, 0, buffer, 0, 32);  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", buffer[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
### <a name="example-using-getsqlbytes"></a><span data-ttu-id="e9a70-136">Пример использования функции GetSqlBytes</span><span class="sxs-lookup"><span data-stu-id="e9a70-136">Example Using GetSqlBytes</span></span>  
 <span data-ttu-id="e9a70-137">В этом примере показано, как получить данные **точки** как необработанные байты в одной операции с помощью метода **жетсклбитес** .</span><span class="sxs-lookup"><span data-stu-id="e9a70-137">This example shows how to retrieve the **Point** data as raw bytes in a single operation using the **GetSqlBytes** method.</span></span> <span data-ttu-id="e9a70-138">В этом коде используется класс `StringBuilder` для преобразования байтового в символьное представление, применяемое для отображения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="e9a70-138">The code uses a `StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Use SqlBytes to retrieve raw bytes  
                Dim sb As SqlBytes = rdr.GetSqlBytes(1)  
                Dim byteCount As Long = sb.Length  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", sb(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
         string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Use SqlBytes to retrieve raw bytes  
                SqlBytes sb = rdr.GetSqlBytes(1);  
                long byteCount = sb.Length;  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", sb[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="working-with-udt-parameters"></a><span data-ttu-id="e9a70-139">Работа с параметрами определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="e9a70-139">Working with UDT Parameters</span></span>  
 <span data-ttu-id="e9a70-140">Определяемые пользователем типы используются в коде ADO.NET как в качестве входных, так и в качестве выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="e9a70-140">UDTs can be used as both input and output parameters in your ADO.NET code.</span></span>  
  
## <a name="using-udts-in-query-parameters"></a><span data-ttu-id="e9a70-141">Использование определяемых пользователем типов в параметрах запроса</span><span class="sxs-lookup"><span data-stu-id="e9a70-141">Using UDTs in Query Parameters</span></span>  
 <span data-ttu-id="e9a70-142">Определяемые пользователем типы могут использоваться в качестве значений параметров при установке `SqlParameter` для объекта `System.Data.SqlClient.SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="e9a70-142">UDTs can be used as parameter values when setting up a `SqlParameter` for a `System.Data.SqlClient.SqlCommand` object.</span></span> <span data-ttu-id="e9a70-143">При вызове методом `SqlDbType.Udt` коллекции `SqlParameter`, перечисление `Add` объекта `Parameters` используется для указания того, что параметр имеет определяемый пользователем тип.</span><span class="sxs-lookup"><span data-stu-id="e9a70-143">The `SqlDbType.Udt` enumeration of a `SqlParameter` object is used to indicate that the parameter is a UDT when calling the `Add` method to the `Parameters` collection.</span></span> <span data-ttu-id="e9a70-144">`UdtTypeName`Свойство `SqlCommand` объекта используется для указания полного имени определяемого пользователем типа в базе данных с помощью синтаксиса *Database. schema_name. object_name* .</span><span class="sxs-lookup"><span data-stu-id="e9a70-144">The `UdtTypeName` property of a `SqlCommand` object is used to specify the fully qualified name of the UDT in the database using the *database.schema_name.object_name* syntax.</span></span> <span data-ttu-id="e9a70-145">Несмотря на то, что использование полного имени не требуется, это удаляет неоднозначность из кода.</span><span class="sxs-lookup"><span data-stu-id="e9a70-145">Although it is not required, using the fully qualified name removes ambiguity from your code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9a70-146">Локальная копия сборки определяемого пользователем типа должна быть доступна в проекте клиента.</span><span class="sxs-lookup"><span data-stu-id="e9a70-146">A local copy of the UDT assembly must be available to the client project.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e9a70-147">Пример</span><span class="sxs-lookup"><span data-stu-id="e9a70-147">Example</span></span>  
 <span data-ttu-id="e9a70-148">В коде данного примера создаются объекты `SqlCommand` и `SqlParameter` для вставки данных в столбец таблицы, имеющий определяемый пользователем тип.</span><span class="sxs-lookup"><span data-stu-id="e9a70-148">The code in this example creates `SqlCommand` and `SqlParameter` objects to insert data into a UDT column in a table.</span></span> <span data-ttu-id="e9a70-149">В коде перечисление `SqlDbType.Udt` используется для указания типа данных, а свойство `UdtTypeName` объекта `SqlParameter` — для указания в базе данных полного имени определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="e9a70-149">The code uses the `SqlDbType.Udt` enumeration to specify the data type, and the `UdtTypeName` property of the `SqlParameter` object to specify the fully qualified name of the UDT in the database.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports system.Data  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim ConnectionString As String = GetConnectionString()  
    Dim cnn As New SqlConnection(ConnectionString)  
    Using cnn  
      Dim cmd As SqlCommand = cnn.CreateCommand()  
      cmd.CommandText = "INSERT INTO dbo.Points (Pnt) VALUES (@Point)"  
      cmd.CommandType = CommandType.Text  
  
      Dim param As New SqlParameter("@Point", SqlDbType.Udt)      param.UdtTypeName = "TestPoint.dbo.Point"      param.Direction = ParameterDirection.Input      param.Value = New Point(5, 6)      cmd.Parameters.Add(param)  
  
      cnn.Open()  
      cmd.ExecuteNonQuery()  
      Console.WriteLine("done")  
    End Using  
  End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
class Class1  
{  
static void Main()  
{  
  string ConnectionString = GetConnectionString();  
     using (SqlConnection cnn = new SqlConnection(ConnectionString))  
     {  
       SqlCommand cmd = cnn.CreateCommand();  
       cmd.CommandText =   
         "INSERT INTO dbo.Points (Pnt) VALUES (@Point)";  
       cmd.CommandType = CommandType.Text;  
  
       SqlParameter param = new SqlParameter("@Point", SqlDbType.Udt);       param.UdtTypeName = "TestPoint.dbo.Point";       param.Direction = ParameterDirection.Input;       param.Value = new Point(5, 6);       cmd.Parameters.Add(param);  
  
       cnn.Open();  
       cmd.ExecuteNonQuery();  
       Console.WriteLine("done");  
     }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9a70-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9a70-150">See Also</span></span>  
 [<span data-ttu-id="e9a70-151">Доступ к определяемым пользователем типам в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9a70-151">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
