---
title: Вызов методов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- methods [SMO]
- calling methods
- SQL Server Management Objects, method calling
- SMO [SQL Server], method calling
ms.assetid: c88d5c5f-9ff0-4f84-b2b6-24c6b90fa15e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13216b4c533527d4249471073580d7c86f6b07e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735178"
---
# <a name="calling-methods"></a><span data-ttu-id="5ce27-102">Вызов методов</span><span class="sxs-lookup"><span data-stu-id="5ce27-102">Calling Methods</span></span>
  <span data-ttu-id="5ce27-103">Методы выполняют определенные задачи, связанные с объектом, такие как выдача объекта `Checkpoint` в базе данных или запрос перечислимого списка входов для экземпляра [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ce27-103">Methods perform specific tasks related to the object, such as issuing a `Checkpoint` on a database or requesting an enumerated list of logons for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5ce27-104">Методы выполняют операции с объектом.</span><span class="sxs-lookup"><span data-stu-id="5ce27-104">Methods perform an operation on an object.</span></span> <span data-ttu-id="5ce27-105">Они могут принимать параметры и часто возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="5ce27-105">Methods can take parameters and often have a return value.</span></span> <span data-ttu-id="5ce27-106">Возвращаемое значение может быть простым типом данных, сложным объектом или структурой, содержащей большое число членов.</span><span class="sxs-lookup"><span data-stu-id="5ce27-106">The return value can be a simple data type, a complex object, or a structure that contains many members.</span></span>  
  
 <span data-ttu-id="5ce27-107">Для проверки успешного выполнения метода используется обработка исключений.</span><span class="sxs-lookup"><span data-stu-id="5ce27-107">Use exception handling to detect whether the method has been successful.</span></span> <span data-ttu-id="5ce27-108">Дополнительные сведения см. в статье [Handling SMO Exceptions](handling-smo-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="5ce27-108">For more information, see [Handling SMO Exceptions](handling-smo-exceptions.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5ce27-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="5ce27-109">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="using-a-simple-smo-method-in-visual-basic"></a><span data-ttu-id="5ce27-110">Использование простого метода SMO на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ce27-110">Using a Simple SMO Method in Visual Basic</span></span>  
 <span data-ttu-id="5ce27-111">В этом примере метод <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> не принимает параметры и не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="5ce27-111">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods1](SMO How to#SMO_VBMethods1)]  -->  
  
## <a name="using-a-simple-smo-method-in-visual-c"></a><span data-ttu-id="5ce27-112">Использование простого метода SMO на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="5ce27-112">Using a Simple SMO Method in Visual C#</span></span>  
 <span data-ttu-id="5ce27-113">В этом примере метод <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> не принимает параметры и не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="5ce27-113">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define a Database object variable by supplying the parent server and the database name arguments in the constructor.   
Database db;   
db = new Database(srv, "Test_SMO_Database");   
//Call the Create method to create the database on the instance of SQL Server.   
db.Create();   
```  
  
 <span data-ttu-id="5ce27-114">}</span><span class="sxs-lookup"><span data-stu-id="5ce27-114">}</span></span>  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-basic"></a><span data-ttu-id="5ce27-115">Использование метода SMO с параметром на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ce27-115">Using an SMO Method with a Parameter in Visual Basic</span></span>  
 <span data-ttu-id="5ce27-116">Объект <xref:Microsoft.SqlServer.Management.Smo.Table> вызывает метод <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-116">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="5ce27-117">Этому методу требуется числовой параметр, задающий `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="5ce27-117">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
Dim srv As Server  
srv = New Server  
Dim tb As Table  
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources")  
tb.RebuildIndexes(70)  
```  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-c"></a><span data-ttu-id="5ce27-118">Использование метода SMO с параметром на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="5ce27-118">Using an SMO Method with a Parameter in Visual C#</span></span>  
 <span data-ttu-id="5ce27-119">Объект <xref:Microsoft.SqlServer.Management.Smo.Table> вызывает метод <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-119">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="5ce27-120">Этому методу требуется числовой параметр, задающий `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="5ce27-120">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
{   
Server srv = default(Server);   
srv = new Server();   
Table tb = default(Table);   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
}   
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-basic"></a><span data-ttu-id="5ce27-121">Использование метода перечисления, который возвращает объект DataTable, на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ce27-121">Using an Enumeration Method that Returns a DataTable Object in Visual Basic</span></span>  
 <span data-ttu-id="5ce27-122">В этом разделе описывается вызов метода перечисления и обработка данных в возвращаемом объекте <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-122">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="5ce27-123">Метод <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> возвращает объект <xref:System.Data.DataTable>, который требует дальнейшего перехода для доступа ко всем имеющимся сведениям о параметрах сортировки в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ce27-123">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a <xref:System.Data.DataTable> object, which requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
'Connect to the local, default instance of SQL Server.  
Dim srv As Server  
srv = New Server  
'Call the EnumCollations method and return collation information to DataTable variable.  
Dim d As DataTable  
'Select the returned data into an array of DataRow.  
d = srv.EnumCollations  
'Iterate through the rows and display collation details for the instance of SQL Server.  
Dim r As DataRow  
Dim c As DataColumn  
For Each r In d.Rows  
    Console.WriteLine("==")  
    For Each c In r.Table.Columns  
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)  
    Next  
Next  
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-c"></a><span data-ttu-id="5ce27-124">Использование метода перечисления, который возвращает объект DataTable, на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="5ce27-124">Using an Enumeration Method that Returns a DataTable Object in Visual C#</span></span>  
 <span data-ttu-id="5ce27-125">В этом разделе описывается вызов метода перечисления и обработка данных в возвращаемом объекте <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-125">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="5ce27-126">Метод <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> возвращает системный объект <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-126">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a system <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="5ce27-127">Объект <xref:System.Data.DataTable> требует дальнейшего перехода для доступа ко всем имеющимся сведениям о параметрах сортировки в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ce27-127">The <xref:System.Data.DataTable> object requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumCollations;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=========");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="constructing-an-object-in-visual-basic"></a><span data-ttu-id="5ce27-128">Создание объекта на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ce27-128">Constructing an Object in Visual Basic</span></span>  
 <span data-ttu-id="5ce27-129">Конструктор любого объекта можно вызвать с помощью оператора `New`.</span><span class="sxs-lookup"><span data-stu-id="5ce27-129">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="5ce27-130">Конструктор объектов <xref:Microsoft.SqlServer.Management.Smo.Database> перегружен, и версия конструктора объектов <xref:Microsoft.SqlServer.Management.Smo.Database>, приведенная в этом образце, принимает два параметра: родительский объект <xref:Microsoft.SqlServer.Management.Smo.Server>, которому принадлежит база данных, и строку, представляющую имя новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="5ce27-130">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods4](SMO How to#SMO_VBMethods4)]  -->  
  
## <a name="constructing-an-object-in-visual-c"></a><span data-ttu-id="5ce27-131">Создание объекта на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="5ce27-131">Constructing an Object in Visual C#</span></span>  
 <span data-ttu-id="5ce27-132">Конструктор любого объекта можно вызвать с помощью оператора `New`.</span><span class="sxs-lookup"><span data-stu-id="5ce27-132">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="5ce27-133">Конструктор объектов <xref:Microsoft.SqlServer.Management.Smo.Database> перегружен, и версия конструктора объектов <xref:Microsoft.SqlServer.Management.Smo.Database>, приведенная в этом образце, принимает два параметра: родительский объект <xref:Microsoft.SqlServer.Management.Smo.Server>, которому принадлежит база данных, и строку, представляющую имя новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="5ce27-133">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
Table tb;   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.   
Database d;   
d = new Database(srv, "Test_SMO_Database");   
//Create the database on the instance of SQL Server.   
d.Create();   
Console.WriteLine(d.Name);   
}  
```  
  
## <a name="copying-an-smo-object-in-visual-basic"></a><span data-ttu-id="5ce27-134">Копирование объекта SMO на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ce27-134">Copying an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="5ce27-135">В этом примере кода метод <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> используется для создания копии объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-135">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="5ce27-136">Объект <xref:Microsoft.SqlServer.Management.Smo.Server> представляет соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ce27-136">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VCMethods6](SMO How to#SMO_VCMethods6)]  -->  
  
## <a name="copying-an-smo-object-in-visual-c"></a><span data-ttu-id="5ce27-137">Копирование объекта SMO на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="5ce27-137">Copying an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="5ce27-138">В этом примере кода метод <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> используется для создания копии объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-138">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="5ce27-139">Объект <xref:Microsoft.SqlServer.Management.Smo.Server> представляет соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ce27-139">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv1;   
srv1 = new Server();   
//Modify the default database and the timeout period for the connection.   
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012";   
srv1.ConnectionContext.ConnectTimeout = 30;   
//Make a second connection using a copy of the ConnectionContext property and verify settings.   
Server srv2;   
srv2 = new Server(srv1.ConnectionContext.Copy);   
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString);   
}  
```  
  
## <a name="monitoring-server-processes-in-visual-basic"></a><span data-ttu-id="5ce27-140">Наблюдение за процессами сервера на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ce27-140">Monitoring Server Processes in Visual Basic</span></span>  
 <span data-ttu-id="5ce27-141">С помощью методов перечисления можно получить сведения о типе текущего состояния экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ce27-141">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="5ce27-142">В этом примере кода метод <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> используется для получения сведений о текущих процессах.</span><span class="sxs-lookup"><span data-stu-id="5ce27-142">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="5ce27-143">В нем также показана работа со столбцами и строками в возвращаемом объекте <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-143">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods5](SMO How to#SMO_VBMethods5)]  -->  
  
## <a name="monitoring-server-processes-in-visual-c"></a><span data-ttu-id="5ce27-144">Наблюдение за процессами сервера на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="5ce27-144">Monitoring Server Processes in Visual C#</span></span>  
 <span data-ttu-id="5ce27-145">С помощью методов перечисления можно получить сведения о типе текущего состояния экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ce27-145">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="5ce27-146">В этом примере кода метод <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> используется для получения сведений о текущих процессах.</span><span class="sxs-lookup"><span data-stu-id="5ce27-146">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="5ce27-147">В нем также показана работа со столбцами и строками в возвращаемом объекте <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="5ce27-147">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumProcesses;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=====");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="see-also"></a><span data-ttu-id="5ce27-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ce27-148">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
